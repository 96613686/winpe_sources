# HrCreateAndInitializeINetCfg

- ea: `0x180040bc8`
- end: `0x180040d28`
- name: `HrCreateAndInitializeINetCfg`
- size: `352`
- prototype: `__int64 __fastcall(_DWORD *, LPVOID *, int, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018628`
- `0x18001b134`
- `0x180037a14`

## callees

- `0x180040bc8`
- `0x180040ef8`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180040d12`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180040d12`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040c43`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040c43`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180040bf2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180040bf2`

## pseudocode

```c
__int64 __fastcall HrCreateAndInitializeINetCfg(_DWORD *a1, LPVOID *a2, int a3, __int64 a4, __int64 a5)
{
  HRESULT v8; // eax
  HRESULT v9; // ebx
  int v10; // eax
  LPVOID v11; // rcx
  void (*v12)(void); // rax
  LPVOID ppv; // [rsp+50h] [rbp+8h] BYREF
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  *a1 = 1;
  v8 = CoInitializeEx(0, 6u);
  if ( v8 >= 0 )
  {
    *a1 = 1;
LABEL_6:
    ppv = 0;
    v9 = CoCreateInstance(&CLSID_CNetCfg, 0, 1u, &IID_INetCfg, &ppv);
    if ( v9 < 0 )
    {
LABEL_18:
      if ( *a1 )
      {
        *a1 = 0;
        CoUninitialize();
      }
      return (unsigned int)v9;
    }
    v15 = 0;
    if ( !a3 )
      goto LABEL_12;
    v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_INetCfgLock, &v15);
    if ( v9 < 0 )
      goto LABEL_17;
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v15 + 24LL))(v15, 0, a5, 0);
    v9 = v10;
    if ( v10 == 1 )
    {
      v9 = -2147180508;
      goto LABEL_17;
    }
    if ( v10 >= 0 )
    {
LABEL_12:
      v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0);
      if ( v9 < 0 )
      {
        if ( !v15 )
          goto LABEL_17;
        v12 = *(void (**)(void))(*(_QWORD *)v15 + 32LL);
      }
      else
      {
        v11 = ppv;
        *a2 = ppv;
        v12 = *(void (**)(void))(*(_QWORD *)v11 + 8LL);
      }
      v12();
    }
LABEL_17:
    ReleaseObj(v15);
    ReleaseObj(ppv);
    if ( v9 >= 0 )
      return (unsigned int)v9;
    goto LABEL_18;
  }
  v9 = 0;
  *a1 = 0;
  if ( v8 != -2147417850 )
    v9 = v8;
  if ( v9 >= 0 )
    goto LABEL_6;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180040bc8  mov     [rsp+arg_10], rbx
0x180040bcd  push    rsi
0x180040bce  push    rdi
0x180040bcf  push    r14
0x180040bd1  sub     rsp, 30h
0x180040bd5  mov     qword ptr [rdx], 0
0x180040bdc  mov     r14, rdx
0x180040bdf  mov     dword ptr [rcx], 1
0x180040be5  mov     rdi, rcx
0x180040be8  xor     ecx, ecx; pvReserved
0x180040bea  mov     edx, 6; dwCoInit
0x180040bef  mov     esi, r8d
0x180040bf2  call    cs:__imp_CoInitializeEx
0x180040bf8  test    eax, eax
0x180040bfa  js      short loc_180040C04
0x180040bfc  mov     dword ptr [rdi], 1
0x180040c02  jmp     short loc_180040C1C
0x180040c04  xor     ebx, ebx
0x180040c06  mov     dword ptr [rdi], 0
0x180040c0c  cmp     eax, 80010106h
0x180040c11  cmovnz  ebx, eax
0x180040c14  test    ebx, ebx
0x180040c16  js      loc_180040D18
0x180040c1c  xor     edx, edx; pUnkOuter
0x180040c1e  mov     [rsp+48h+arg_0], 0
0x180040c27  lea     rax, [rsp+48h+arg_0]
0x180040c2c  lea     r9, IID_INetCfg; riid
0x180040c33  mov     [rsp+48h+ppv], rax; ppv
0x180040c38  lea     rcx, CLSID_CNetCfg; rclsid
0x180040c3f  lea     r8d, [rdx+1]; dwClsContext
0x180040c43  call    cs:__imp_CoCreateInstance
0x180040c49  mov     ebx, eax
0x180040c4b  test    eax, eax
0x180040c4d  js      loc_180040D07
0x180040c53  mov     [rsp+48h+arg_8], 0
0x180040c5c  test    esi, esi
0x180040c5e  jz      short loc_180040CAF
0x180040c60  mov     rcx, [rsp+48h+arg_0]
0x180040c65  lea     r8, [rsp+48h+arg_8]
0x180040c6a  lea     rdx, IID_INetCfgLock
0x180040c71  mov     rax, [rcx]
0x180040c74  mov     rax, [rax]
0x180040c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c7c  mov     ebx, eax
0x180040c7e  test    eax, eax
0x180040c80  js      short loc_180040CEF
0x180040c82  mov     rcx, [rsp+48h+arg_8]
0x180040c87  xor     r9d, r9d
0x180040c8a  mov     r8, [rsp+48h+arg_20]
0x180040c8f  xor     edx, edx
0x180040c91  mov     rax, [rcx]
0x180040c94  mov     rax, [rax+18h]
0x180040c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c9d  mov     ebx, eax
0x180040c9f  cmp     eax, 1
0x180040ca2  jnz     short loc_180040CAB
0x180040ca4  mov     ebx, 8004A024h
0x180040ca9  jmp     short loc_180040CEF
0x180040cab  test    eax, eax
0x180040cad  js      short loc_180040CEF
0x180040caf  mov     rcx, [rsp+48h+arg_0]
0x180040cb4  xor     edx, edx
0x180040cb6  mov     rax, [rcx]
0x180040cb9  mov     rax, [rax+18h]
0x180040cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cc2  mov     ebx, eax
0x180040cc4  test    eax, eax
0x180040cc6  js      short loc_180040CD9
0x180040cc8  mov     rcx, [rsp+48h+arg_0]
0x180040ccd  mov     [r14], rcx
0x180040cd0  mov     rax, [rcx]
0x180040cd3  mov     rax, [rax+8]
0x180040cd7  jmp     short loc_180040CEA
0x180040cd9  mov     rcx, [rsp+48h+arg_8]
0x180040cde  test    rcx, rcx
0x180040ce1  jz      short loc_180040CEF
0x180040ce3  mov     rax, [rcx]
0x180040ce6  mov     rax, [rax+20h]
0x180040cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cef  mov     rcx, [rsp+48h+arg_8]
0x180040cf4  call    ReleaseObj
0x180040cf9  mov     rcx, [rsp+48h+arg_0]
0x180040cfe  call    ReleaseObj
0x180040d03  test    ebx, ebx
0x180040d05  jns     short loc_180040D18
0x180040d07  cmp     dword ptr [rdi], 0
0x180040d0a  jz      short loc_180040D18
0x180040d0c  mov     dword ptr [rdi], 0
0x180040d12  call    cs:__imp_CoUninitialize
0x180040d18  mov     eax, ebx
0x180040d1a  mov     rbx, [rsp+48h+arg_10]
0x180040d1f  add     rsp, 30h
0x180040d23  pop     r14
0x180040d25  pop     rdi
0x180040d26  pop     rsi
0x180040d27  retn
```
