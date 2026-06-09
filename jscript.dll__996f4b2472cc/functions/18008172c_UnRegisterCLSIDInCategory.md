# UnRegisterCLSIDInCategory

- ea: `0x18008172c`
- end: `0x1800817f2`
- name: `UnRegisterCLSIDInCategory`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800817f8`

## callees

- `0x180080dfc`
- `0x18008172c`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180081780`
- `ole32!CoCreateInstance` at `0x180081780`

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
0x18008172c  mov     [rsp+arg_8], rbx
0x180081731  mov     [rsp+arg_10], rsi
0x180081736  push    rdi
0x180081737  sub     rsp, 50h
0x18008173b  mov     rax, cs:__security_cookie
0x180081742  xor     rax, rsp
0x180081745  mov     [rsp+58h+var_10], rax
0x18008174a  mov     rsi, rdx
0x18008174d  mov     [rsp+58h+var_28], 0
0x180081756  mov     rdi, rcx
0x180081759  call    FExistsCLSID
0x18008175e  test    eax, eax
0x180081760  jz      short loc_1800817D4
0x180081762  xor     edx, edx; pUnkOuter
0x180081764  lea     rax, [rsp+58h+var_28]
0x180081769  lea     r9, IID_ICatRegister; riid
0x180081770  mov     [rsp+58h+ppv], rax; ppv
0x180081775  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18008177c  lea     r8d, [rdx+1]; dwClsContext
0x180081780  call    cs:__imp_CoCreateInstance
0x180081787  nop     dword ptr [rax+rax+00h]
0x18008178c  mov     ebx, eax
0x18008178e  test    eax, eax
0x180081790  js      short loc_1800817BC
0x180081792  mov     rcx, [rsp+58h+var_28]
0x180081797  lea     r9, [rsp+58h+var_20]
0x18008179c  movaps  xmm0, xmmword ptr [rsi]
0x18008179f  mov     r8d, 1
0x1800817a5  movdqu  [rsp+58h+var_20], xmm0
0x1800817ab  mov     rdx, rdi
0x1800817ae  mov     rax, [rcx]
0x1800817b1  mov     rax, [rax+30h]
0x1800817b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800817ba  mov     ebx, eax
0x1800817bc  mov     rcx, [rsp+58h+var_28]
0x1800817c1  test    rcx, rcx
0x1800817c4  jz      short loc_1800817D2
0x1800817c6  mov     rax, [rcx]
0x1800817c9  mov     rax, [rax+10h]
0x1800817cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800817d2  mov     eax, ebx
0x1800817d4  mov     rcx, [rsp+58h+var_10]
0x1800817d9  xor     rcx, rsp; StackCookie
0x1800817dc  call    __security_check_cookie
0x1800817e1  mov     rbx, [rsp+58h+arg_8]
0x1800817e6  mov     rsi, [rsp+58h+arg_10]
0x1800817eb  add     rsp, 50h
0x1800817ef  pop     rdi
0x1800817f0  retn
```
