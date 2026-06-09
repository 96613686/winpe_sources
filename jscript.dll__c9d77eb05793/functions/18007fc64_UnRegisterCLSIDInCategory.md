# UnRegisterCLSIDInCategory

- ea: `0x18007fc64`
- end: `0x18007fd23`
- name: `UnRegisterCLSIDInCategory`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007fd2c`

## callees

- `0x18007f424`
- `0x18007fc64`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18007fcb8`
- `ole32!CoCreateInstance` at `0x18007fcb8`

## pseudocode

```c
__int64 __fastcall UnRegisterCLSIDInCategory(const struct _GUID *a1, __int128 *a2, unsigned int a3)
{
  __int64 result; // rax
  HRESULT v6; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-28h] BYREF
  __int128 v8; // [rsp+38h] [rbp-20h] BYREF

  ppv = 0;
  result = FExistsCLSID(a1, (__int64)a2, a3);
  if ( (_DWORD)result )
  {
    v6 = CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatRegister, &ppv);
    if ( v6 >= 0 )
    {
      v8 = *a2;
      v6 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, __int64, __int128 *))(*(_QWORD *)ppv + 48LL))(
             ppv,
             a1,
             1,
             &v8);
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x18007fc64  mov     [rsp+arg_8], rbx
0x18007fc69  mov     [rsp+arg_10], rsi
0x18007fc6e  push    rdi
0x18007fc6f  sub     rsp, 50h
0x18007fc73  mov     rax, cs:__security_cookie
0x18007fc7a  xor     rax, rsp
0x18007fc7d  mov     [rsp+58h+var_10], rax
0x18007fc82  mov     rsi, rdx
0x18007fc85  mov     [rsp+58h+var_28], 0
0x18007fc8e  mov     rdi, rcx
0x18007fc91  call    FExistsCLSID
0x18007fc96  test    eax, eax
0x18007fc98  jz      short loc_18007FD06
0x18007fc9a  xor     edx, edx; pUnkOuter
0x18007fc9c  lea     rax, [rsp+58h+var_28]
0x18007fca1  lea     r9, IID_ICatRegister; riid
0x18007fca8  mov     [rsp+58h+ppv], rax; ppv
0x18007fcad  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18007fcb4  lea     r8d, [rdx+1]; dwClsContext
0x18007fcb8  call    cs:__imp_CoCreateInstance
0x18007fcbe  mov     ebx, eax
0x18007fcc0  test    eax, eax
0x18007fcc2  js      short loc_18007FCEE
0x18007fcc4  mov     rcx, [rsp+58h+var_28]
0x18007fcc9  lea     r9, [rsp+58h+var_20]
0x18007fcce  movaps  xmm0, xmmword ptr [rsi]
0x18007fcd1  mov     r8d, 1
0x18007fcd7  movdqu  [rsp+58h+var_20], xmm0
0x18007fcdd  mov     rdx, rdi
0x18007fce0  mov     rax, [rcx]
0x18007fce3  mov     rax, [rax+30h]
0x18007fce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fcec  mov     ebx, eax
0x18007fcee  mov     rcx, [rsp+58h+var_28]
0x18007fcf3  test    rcx, rcx
0x18007fcf6  jz      short loc_18007FD04
0x18007fcf8  mov     rax, [rcx]
0x18007fcfb  mov     rax, [rax+10h]
0x18007fcff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fd04  mov     eax, ebx
0x18007fd06  mov     rcx, [rsp+58h+var_10]
0x18007fd0b  xor     rcx, rsp; StackCookie
0x18007fd0e  call    __security_check_cookie
0x18007fd13  mov     rbx, [rsp+58h+arg_8]
0x18007fd18  mov     rsi, [rsp+58h+arg_10]
0x18007fd1d  add     rsp, 50h
0x18007fd21  pop     rdi
0x18007fd22  retn
```
