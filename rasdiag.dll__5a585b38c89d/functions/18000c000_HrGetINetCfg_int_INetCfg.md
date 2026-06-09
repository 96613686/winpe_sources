# HrGetINetCfg(int,INetCfg * *)

- ea: `0x18000c000`
- end: `0x18000c15e`
- name: `?HrGetINetCfg@@YAJHPEAPEAUINetCfg@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(int, LPVOID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000c7f0`
- `0x18000c8cc`

## callees

- `0x18000c000`
- `0x18000ca8c`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c040`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c040`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c0d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c0d7`

## string_xrefs

- `0x18000c0bd`: `HrGetINetCfg: AcquireWriteLock failed, lock acquired by %s`

## pseudocode

```c
__int64 __fastcall HrGetINetCfg(int a1, LPVOID *a2)
{
  HRESULT v4; // ebx
  LPVOID v5; // rcx
  void (*v6)(void); // rax
  __int64 v8; // [rsp+58h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_CNetCfg, 0, 1u, &IID_INetCfg, &ppv);
  if ( v4 < 0 )
    return (unsigned int)v4;
  v8 = 0;
  if ( a1 )
  {
    v4 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_INetCfgLock, &v8);
    if ( v4 < 0 )
      goto LABEL_14;
    pv = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, LPVOID *))(*(_QWORD *)v8 + 24LL))(
           v8,
           15000,
           L"RasDiagnostic Helper",
           &pv);
    if ( v4 == 1 )
    {
      v4 = -2147180508;
      RasDiagTrace("HrGetINetCfg: AcquireWriteLock failed, lock acquired by %s", (const char *)pv);
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( v4 < 0 )
      goto LABEL_14;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0);
  if ( v4 >= 0 )
  {
    v5 = ppv;
    *a2 = ppv;
    v6 = *(void (**)(void))(*(_QWORD *)v5 + 8LL);
LABEL_13:
    v6();
LABEL_14:
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    goto LABEL_16;
  }
  if ( v8 )
  {
    v6 = *(void (**)(void))(*(_QWORD *)v8 + 32LL);
    goto LABEL_13;
  }
LABEL_16:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c000  mov     [rsp-18h+arg_0], rbx
0x18000c005  push    rbp
0x18000c006  push    rsi
0x18000c007  push    rdi
0x18000c008  mov     rbp, rsp
0x18000c00b  sub     rsp, 30h
0x18000c00f  mov     rsi, rdx
0x18000c012  mov     qword ptr [rdx], 0
0x18000c019  xor     edx, edx; pUnkOuter
0x18000c01b  mov     [rbp+arg_10], 0
0x18000c023  mov     edi, ecx
0x18000c025  lea     rax, [rbp+arg_10]
0x18000c029  lea     r9, IID_INetCfg; riid
0x18000c030  mov     [rsp+30h+ppv], rax; ppv
0x18000c035  lea     rcx, CLSID_CNetCfg; rclsid
0x18000c03c  lea     r8d, [rdx+1]; dwClsContext
0x18000c040  call    cs:__imp_CoCreateInstance
0x18000c047  nop     dword ptr [rax+rax+00h]
0x18000c04c  mov     ebx, eax
0x18000c04e  test    eax, eax
0x18000c050  js      loc_18000C14E
0x18000c056  mov     [rbp+arg_8], 0
0x18000c05e  test    edi, edi
0x18000c060  jz      loc_18000C0E7
0x18000c066  mov     rcx, [rbp+arg_10]
0x18000c06a  lea     r8, [rbp+arg_8]
0x18000c06e  lea     rdx, IID_INetCfgLock
0x18000c075  mov     rax, [rcx]
0x18000c078  mov     rax, [rax]
0x18000c07b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c080  mov     ebx, eax
0x18000c082  test    eax, eax
0x18000c084  js      loc_18000C124
0x18000c08a  mov     rcx, [rbp+arg_8]
0x18000c08e  lea     r9, [rbp+pv]
0x18000c092  mov     [rbp+pv], 0
0x18000c09a  lea     r8, aRasdiagnosticH; "RasDiagnostic Helper"
0x18000c0a1  mov     edx, 3A98h
0x18000c0a6  mov     rax, [rcx]
0x18000c0a9  mov     rax, [rax+18h]
0x18000c0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0b2  mov     ebx, eax
0x18000c0b4  cmp     eax, 1
0x18000c0b7  jnz     short loc_18000C0CE
0x18000c0b9  mov     rdx, [rbp+pv]
0x18000c0bd  lea     rcx, aHrgetinetcfgAc; "HrGetINetCfg: AcquireWriteLock failed, "...
0x18000c0c4  mov     ebx, 8004A024h
0x18000c0c9  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000c0ce  mov     rcx, [rbp+pv]; pv
0x18000c0d2  test    rcx, rcx
0x18000c0d5  jz      short loc_18000C0E3
0x18000c0d7  call    cs:__imp_CoTaskMemFree
0x18000c0de  nop     dword ptr [rax+rax+00h]
0x18000c0e3  test    ebx, ebx
0x18000c0e5  js      short loc_18000C124
0x18000c0e7  mov     rcx, [rbp+arg_10]
0x18000c0eb  xor     edx, edx
0x18000c0ed  mov     rax, [rcx]
0x18000c0f0  mov     rax, [rax+18h]
0x18000c0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0f9  mov     ebx, eax
0x18000c0fb  test    eax, eax
0x18000c0fd  js      short loc_18000C10F
0x18000c0ff  mov     rcx, [rbp+arg_10]
0x18000c103  mov     [rsi], rcx
0x18000c106  mov     rax, [rcx]
0x18000c109  mov     rax, [rax+8]
0x18000c10d  jmp     short loc_18000C11F
0x18000c10f  mov     rcx, [rbp+arg_8]
0x18000c113  test    rcx, rcx
0x18000c116  jz      short loc_18000C139
0x18000c118  mov     rax, [rcx]
0x18000c11b  mov     rax, [rax+20h]
0x18000c11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c124  mov     rcx, [rbp+arg_8]
0x18000c128  test    rcx, rcx
0x18000c12b  jz      short loc_18000C139
0x18000c12d  mov     rax, [rcx]
0x18000c130  mov     rax, [rax+10h]
0x18000c134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c139  mov     rcx, [rbp+arg_10]
0x18000c13d  test    rcx, rcx
0x18000c140  jz      short loc_18000C14E
0x18000c142  mov     rax, [rcx]
0x18000c145  mov     rax, [rax+10h]
0x18000c149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c14e  mov     eax, ebx
0x18000c150  mov     rbx, [rsp+30h+arg_0]
0x18000c155  add     rsp, 30h
0x18000c159  pop     rdi
0x18000c15a  pop     rsi
0x18000c15b  pop     rbp
0x18000c15c  retn
```
