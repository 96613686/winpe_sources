# COleScript::GetINETSecurityManagerNoRef(IInternetSecurityManager * *)

- ea: `0x18007badc`
- end: `0x18007bbc9`
- name: `?GetINETSecurityManagerNoRef@COleScript@@IEAAJPEAPEAUIInternetSecurityManager@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(COleScript *__hidden this, struct IInternetSecurityManager **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18007c258`

## callees

- `0x18007badc`
- `0x180098010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18007bb9e`
- `ole32!CoCreateInstance` at `0x18007bb9e`

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
0x18007badc  push    rbx
0x18007bade  push    rsi
0x18007badf  push    rdi
0x18007bae0  push    r14
0x18007bae2  sub     rsp, 38h
0x18007bae6  cmp     dword ptr [rcx+2E8h], 0
0x18007baed  mov     rsi, rdx
0x18007baf0  mov     rdi, rcx
0x18007baf3  mov     qword ptr [rdx], 0
0x18007bafa  mov     [rsp+58h+arg_0], 0
0x18007bb03  jz      short loc_18007BB0F
0x18007bb05  mov     eax, 80004005h
0x18007bb0a  jmp     loc_18007BBBE
0x18007bb0f  lea     r14, [rcx+2F8h]
0x18007bb16  mov     rax, [r14]
0x18007bb19  test    rax, rax
0x18007bb1c  jz      short loc_18007BB26
0x18007bb1e  mov     [rdx], rax
0x18007bb21  jmp     loc_18007BBBC
0x18007bb26  mov     rcx, [rcx+0B0h]
0x18007bb2d  lea     r8, [rsp+58h+arg_0]
0x18007bb32  lea     rdx, IID_IServiceProvider
0x18007bb39  mov     rax, [rcx]
0x18007bb3c  mov     rax, [rax]
0x18007bb3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bb44  test    eax, eax
0x18007bb46  js      short loc_18007BB81
0x18007bb48  mov     rcx, [rsp+58h+arg_0]
0x18007bb4d  lea     r8, IID_IInternetSecurityManager
0x18007bb54  mov     r9, r14
0x18007bb57  lea     rdx, IID_IInternetSecurityManager
0x18007bb5e  mov     rax, [rcx]
0x18007bb61  mov     rax, [rax+18h]
0x18007bb65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bb6a  mov     rcx, [rsp+58h+arg_0]
0x18007bb6f  mov     ebx, eax
0x18007bb71  mov     rdx, [rcx]
0x18007bb74  mov     rax, [rdx+10h]
0x18007bb78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bb7d  test    ebx, ebx
0x18007bb7f  jns     short loc_18007BBB6
0x18007bb81  mov     ebx, 1
0x18007bb86  mov     [rsp+58h+ppv], r14; ppv
0x18007bb8b  mov     r8d, ebx; dwClsContext
0x18007bb8e  lea     r9, IID_IInternetSecurityManager; riid
0x18007bb95  xor     edx, edx; pUnkOuter
0x18007bb97  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x18007bb9e  call    cs:__imp_CoCreateInstance
0x18007bba5  nop     dword ptr [rax+rax+00h]
0x18007bbaa  test    eax, eax
0x18007bbac  jns     short loc_18007BBB6
0x18007bbae  mov     [rdi+2E8h], ebx
0x18007bbb4  jmp     short loc_18007BBBE
0x18007bbb6  mov     rax, [r14]
0x18007bbb9  mov     [rsi], rax
0x18007bbbc  xor     eax, eax
0x18007bbbe  add     rsp, 38h
0x18007bbc2  pop     r14
0x18007bbc4  pop     rdi
0x18007bbc5  pop     rsi
0x18007bbc6  pop     rbx
0x18007bbc7  retn
```
