# CProgressDialog_CreateInstance(uint,uint)

- ea: `0x180023ce4`
- end: `0x180023d84`
- name: `?CProgressDialog_CreateInstance@@YAPEAUIProgressDialog@@II@Z`
- size: `160`
- prototype: `struct IProgressDialog *__fastcall(UINT uID, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f25c`
- `0x18000f694`
- `0x180014c6c`

## callees

- `0x180002240`
- `0x180023ce4`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180023d46`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180023d46`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023d28`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023d28`

## pseudocode

```c
struct IProgressDialog *__fastcall CProgressDialog_CreateInstance(UINT uID)
{
  LPVOID ppv; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  ppv = 0;
  if ( CoCreateInstance(&CLSID_ProgressDialog, 0, 1u, &IID_IProgressDialog, &ppv) >= 0
    && LoadStringW(g_hinst, uID, Buffer, 260) )
  {
    (*(void (__fastcall **)(LPVOID, WCHAR *))(*(_QWORD *)ppv + 40LL))(ppv, Buffer);
  }
  return (struct IProgressDialog *)ppv;
}

```

## disassembly

```asm
0x180023ce4  push    rbx
0x180023ce6  sub     rsp, 260h
0x180023ced  mov     rax, cs:__security_cookie
0x180023cf4  xor     rax, rsp
0x180023cf7  mov     [rsp+268h+var_18], rax
0x180023cff  xor     edx, edx; pUnkOuter
0x180023d01  mov     [rsp+268h+var_238], 0
0x180023d0a  mov     ebx, ecx
0x180023d0c  lea     rax, [rsp+268h+var_238]
0x180023d11  lea     r9, IID_IProgressDialog; riid
0x180023d18  mov     [rsp+268h+ppv], rax; ppv
0x180023d1d  lea     rcx, CLSID_ProgressDialog; rclsid
0x180023d24  lea     r8d, [rdx+1]; dwClsContext
0x180023d28  call    cs:__imp_CoCreateInstance
0x180023d2e  test    eax, eax
0x180023d30  js      short loc_180023D66
0x180023d32  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180023d39  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x180023d3e  mov     r9d, 104h; cchBufferMax
0x180023d44  mov     edx, ebx; uID
0x180023d46  call    cs:__imp_LoadStringW
0x180023d4c  test    eax, eax
0x180023d4e  jz      short loc_180023D66
0x180023d50  mov     rcx, [rsp+268h+var_238]
0x180023d55  lea     rdx, [rsp+268h+Buffer]
0x180023d5a  mov     rax, [rcx]
0x180023d5d  mov     rax, [rax+28h]
0x180023d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d66  mov     rax, [rsp+268h+var_238]
0x180023d6b  mov     rcx, [rsp+268h+var_18]
0x180023d73  xor     rcx, rsp; StackCookie
0x180023d76  call    __security_check_cookie
0x180023d7b  add     rsp, 260h
0x180023d82  pop     rbx
0x180023d83  retn
```
