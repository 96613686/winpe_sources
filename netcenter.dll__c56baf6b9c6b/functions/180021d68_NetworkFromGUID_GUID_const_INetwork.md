# _NetworkFromGUID(_GUID const &,INetwork * *)

- ea: `0x180021d68`
- end: `0x180021df5`
- name: `?_NetworkFromGUID@@YAJAEBU_GUID@@PEAPEAUINetwork@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(const struct _GUID *, struct INetwork **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021bfc`

## callees

- `0x180007e50`
- `0x180021d68`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021da9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021da9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _NetworkFromGUID(const struct _GUID *a1, struct INetwork **a2)
{
  HRESULT v4; // ebx
  __int128 v6; // [rsp+30h] [rbp-18h] BYREF
  LPVOID v7; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  v7 = 0;
  v4 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b, &v7);
  if ( v4 >= 0 )
  {
    v6 = (__int128)*a1;
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, struct INetwork **))(*(_QWORD *)v7 + 64LL))(v7, &v6, a2);
  }
  ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(&v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180021d68  mov     r11, rsp
0x180021d6b  mov     [r11+8], rbx
0x180021d6f  mov     [r11+18h], rsi
0x180021d73  push    rdi
0x180021d74  sub     rsp, 40h
0x180021d78  mov     rdi, rdx
0x180021d7b  mov     rsi, rcx
0x180021d7e  mov     qword ptr [rdx], 0
0x180021d85  mov     qword ptr [r11+10h], 0
0x180021d8d  lea     rax, [r11+10h]
0x180021d91  mov     [r11-28h], rax
0x180021d95  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x180021d9c  xor     edx, edx; pUnkOuter
0x180021d9e  lea     r8d, [rdx+1]; dwClsContext
0x180021da2  lea     rcx, CLSID_NetworkListManager; rclsid
0x180021da9  call    cs:__imp_CoCreateInstance
0x180021daf  mov     ebx, eax
0x180021db1  test    eax, eax
0x180021db3  js      short loc_180021DD9
0x180021db5  mov     rcx, [rsp+48h+arg_8]
0x180021dba  movups  xmm0, xmmword ptr [rsi]
0x180021dbd  movdqu  [rsp+48h+var_18], xmm0
0x180021dc3  mov     rax, [rcx]
0x180021dc6  mov     r8, rdi
0x180021dc9  lea     rdx, [rsp+48h+var_18]
0x180021dce  mov     rax, [rax+40h]
0x180021dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dd7  mov     ebx, eax
0x180021dd9  lea     rcx, [rsp+48h+arg_8]
0x180021dde  call    ??1?$CComPtrBase@UIShellFolder2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(void)
0x180021de3  mov     eax, ebx
0x180021de5  mov     rbx, [rsp+48h+arg_0]
0x180021dea  mov     rsi, [rsp+48h+arg_10]
0x180021def  add     rsp, 40h
0x180021df3  pop     rdi
0x180021df4  retn
```
