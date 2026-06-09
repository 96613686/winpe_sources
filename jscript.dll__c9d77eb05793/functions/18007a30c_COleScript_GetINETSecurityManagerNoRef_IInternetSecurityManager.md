# COleScript::GetINETSecurityManagerNoRef(IInternetSecurityManager * *)

- ea: `0x18007a30c`
- end: `0x18007a3f2`
- name: `?GetINETSecurityManagerNoRef@COleScript@@IEAAJPEAPEAUIInternetSecurityManager@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(COleScript *__hidden this, struct IInternetSecurityManager **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18007aa94`

## callees

- `0x18007a30c`
- `0x180096010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18007a3ce`
- `ole32!CoCreateInstance` at `0x18007a3ce`

## pseudocode

```c
HRESULT __fastcall COleScript::GetINETSecurityManagerNoRef(COleScript *this, struct IInternetSecurityManager **a2)
{
  bool v2; // zf
  HRESULT result; // eax
  LPVOID *ppv; // r14
  struct IInternetSecurityManager *v7; // rax
  int v8; // ebx
  __int64 v9; // [rsp+60h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 186) == 0;
  *a2 = 0;
  v9 = 0;
  if ( !v2 )
    return -2147467259;
  ppv = (LPVOID *)((char *)this + 760);
  v7 = (struct IInternetSecurityManager *)*((_QWORD *)this + 95);
  if ( v7 )
  {
    *a2 = v7;
  }
  else
  {
    if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 22))(
           *((_QWORD *)this + 22),
           &IID_IServiceProvider,
           &v9) < 0
      || (v8 = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, LPVOID *))(*(_QWORD *)v9 + 24LL))(
                 v9,
                 &IID_IInternetSecurityManager,
                 &IID_IInternetSecurityManager,
                 ppv),
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9),
          v8 < 0) )
    {
      result = CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &IID_IInternetSecurityManager, ppv);
      if ( result < 0 )
      {
        *((_DWORD *)this + 186) = 1;
        return result;
      }
    }
    *a2 = (struct IInternetSecurityManager *)*ppv;
  }
  return 0;
}

```

## disassembly

```asm
0x18007a30c  push    rbx
0x18007a30e  push    rsi
0x18007a30f  push    rdi
0x18007a310  push    r14
0x18007a312  sub     rsp, 38h
0x18007a316  cmp     dword ptr [rcx+2E8h], 0
0x18007a31d  mov     rsi, rdx
0x18007a320  mov     rdi, rcx
0x18007a323  mov     qword ptr [rdx], 0
0x18007a32a  mov     [rsp+58h+arg_0], 0
0x18007a333  jz      short loc_18007A33F
0x18007a335  mov     eax, 80004005h
0x18007a33a  jmp     loc_18007A3E8
0x18007a33f  lea     r14, [rcx+2F8h]
0x18007a346  mov     rax, [r14]
0x18007a349  test    rax, rax
0x18007a34c  jz      short loc_18007A356
0x18007a34e  mov     [rdx], rax
0x18007a351  jmp     loc_18007A3E6
0x18007a356  mov     rcx, [rcx+0B0h]
0x18007a35d  lea     r8, [rsp+58h+arg_0]
0x18007a362  lea     rdx, IID_IServiceProvider
0x18007a369  mov     rax, [rcx]
0x18007a36c  mov     rax, [rax]
0x18007a36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a374  test    eax, eax
0x18007a376  js      short loc_18007A3B1
0x18007a378  mov     rcx, [rsp+58h+arg_0]
0x18007a37d  lea     r8, IID_IInternetSecurityManager
0x18007a384  mov     r9, r14
0x18007a387  lea     rdx, IID_IInternetSecurityManager
0x18007a38e  mov     rax, [rcx]
0x18007a391  mov     rax, [rax+18h]
0x18007a395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a39a  mov     rcx, [rsp+58h+arg_0]
0x18007a39f  mov     ebx, eax
0x18007a3a1  mov     rdx, [rcx]
0x18007a3a4  mov     rax, [rdx+10h]
0x18007a3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a3ad  test    ebx, ebx
0x18007a3af  jns     short loc_18007A3E0
0x18007a3b1  mov     ebx, 1
0x18007a3b6  mov     [rsp+58h+ppv], r14; ppv
0x18007a3bb  mov     r8d, ebx; dwClsContext
0x18007a3be  lea     r9, IID_IInternetSecurityManager; riid
0x18007a3c5  xor     edx, edx; pUnkOuter
0x18007a3c7  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x18007a3ce  call    cs:__imp_CoCreateInstance
0x18007a3d4  test    eax, eax
0x18007a3d6  jns     short loc_18007A3E0
0x18007a3d8  mov     [rdi+2E8h], ebx
0x18007a3de  jmp     short loc_18007A3E8
0x18007a3e0  mov     rax, [r14]
0x18007a3e3  mov     [rsi], rax
0x18007a3e6  xor     eax, eax
0x18007a3e8  add     rsp, 38h
0x18007a3ec  pop     r14
0x18007a3ee  pop     rdi
0x18007a3ef  pop     rsi
0x18007a3f0  pop     rbx
0x18007a3f1  retn
```
