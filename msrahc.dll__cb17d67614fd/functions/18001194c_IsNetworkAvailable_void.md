# IsNetworkAvailable(void)

- ea: `0x18001194c`
- end: `0x1800119fc`
- name: `?IsNetworkAvailable@@YAHXZ`
- size: `176`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e4d0`

## callees

- `0x18001194c`
- `0x180014660`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011985`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011985`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 IsNetworkAvailable(void)
{
  BOOL v0; // ebx
  HRESULT v1; // eax
  const struct _EVENT_DESCRIPTOR *v2; // rdx
  CEventLogger *v3; // rcx
  unsigned int v4; // r9d
  int v6; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  v0 = 1;
  v6 = 1024;
  v1 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &IID_INetworkListManager, &ppv);
  if ( v1 < 0 )
  {
    v4 = 1743;
LABEL_3:
    CEventLogger::LogError(v3, v2, L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp", v4, L"IsNetworkAvailable", v1);
    goto LABEL_7;
  }
  v1 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 104LL))(ppv, &v6);
  if ( v1 < 0 )
  {
    v4 = 1746;
    goto LABEL_3;
  }
  v0 = v6 != 0;
LABEL_7:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v0;
}

```

## disassembly

```asm
0x18001194c  push    rbx
0x18001194e  sub     rsp, 30h
0x180011952  lea     rax, [rsp+38h+arg_8]
0x180011957  mov     [rsp+38h+arg_8], 0
0x180011960  mov     ebx, 1
0x180011965  mov     [rsp+38h+arg_0], 400h
0x18001196d  mov     r8d, ebx; dwClsContext
0x180011970  mov     [rsp+38h+ppv], rax; ppv
0x180011975  lea     r9, IID_INetworkListManager; riid
0x18001197c  xor     edx, edx; pUnkOuter
0x18001197e  lea     rcx, CLSID_NetworkListManager; rclsid
0x180011985  call    cs:__imp_CoCreateInstance
0x18001198b  test    eax, eax
0x18001198d  jns     short loc_1800119B3
0x18001198f  mov     r9d, 6CFh; unsigned int
0x180011995  mov     [rsp+38h+var_10], eax; unsigned int
0x180011999  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x1800119a0  lea     rax, aIsnetworkavail; "IsNetworkAvailable"
0x1800119a7  mov     [rsp+38h+ppv], rax; unsigned __int16 *
0x1800119ac  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800119b1  jmp     short loc_1800119DE
0x1800119b3  mov     rcx, [rsp+38h+arg_8]
0x1800119b8  lea     rdx, [rsp+38h+arg_0]
0x1800119bd  mov     rax, [rcx]
0x1800119c0  mov     rax, [rax+68h]
0x1800119c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119c9  test    eax, eax
0x1800119cb  jns     short loc_1800119D5
0x1800119cd  mov     r9d, 6D2h
0x1800119d3  jmp     short loc_180011995
0x1800119d5  xor     eax, eax
0x1800119d7  cmp     [rsp+38h+arg_0], eax
0x1800119db  cmovz   ebx, eax
0x1800119de  mov     rcx, [rsp+38h+arg_8]
0x1800119e3  test    rcx, rcx
0x1800119e6  jz      short loc_1800119F4
0x1800119e8  mov     rdx, [rcx]
0x1800119eb  mov     rax, [rdx+10h]
0x1800119ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119f4  mov     eax, ebx
0x1800119f6  add     rsp, 30h
0x1800119fa  pop     rbx
0x1800119fb  retn
```
