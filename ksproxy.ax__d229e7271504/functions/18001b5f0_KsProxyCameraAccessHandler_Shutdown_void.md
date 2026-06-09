# KsProxyCameraAccessHandler::Shutdown(void)

- ea: `0x18001b5f0`
- end: `0x18001b66e`
- name: `?Shutdown@KsProxyCameraAccessHandler@@UEAAJXZ`
- size: `126`
- prototype: `__int64 __fastcall(KsProxyCameraAccessHandler *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019108`

## callees

- `0x1800081e4`
- `0x180013cfc`
- `0x180016344`
- `0x18001b5f0`
- `0x180045010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001b604`
- `KERNEL32!EnterCriticalSection` at `0x18001b604`

## string_xrefs

- `0x18001b635`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\ksproxycameraaccesshandler.cpp`

## pseudocode

```c
__int64 __fastcall KsProxyCameraAccessHandler::Shutdown(KsProxyCameraAccessHandler *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  __int64 v3; // rcx
  int v4; // eax
  unsigned int v5; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v8; // [rsp+30h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v3 = *((_QWORD *)this + 2);
  v8 = v1;
  if ( !v3 )
    goto LABEL_5;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 32LL))(v3);
  v5 = v4;
  if ( v4 >= 0 )
  {
    wil::com_ptr_t<IKsProxyCameraAccessHandler,wil::err_returncode_policy>::reset((__int64 *)this + 2);
LABEL_5:
    v5 = 0;
    goto LABEL_6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x52,
    (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\ksproxycameraaccesshandler.cpp",
    (const char *)(unsigned int)v4);
LABEL_6:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v8);
  return v5;
}

```

## disassembly

```asm
0x18001b5f0  mov     [rsp+arg_8], rbx
0x18001b5f5  push    rdi; int
0x18001b5f6  sub     rsp, 20h
0x18001b5fa  lea     rbx, [rcx+18h]
0x18001b5fe  mov     rdi, rcx
0x18001b601  mov     rcx, rbx; lpCriticalSection
0x18001b604  call    cs:__imp_EnterCriticalSection
0x18001b60b  nop     dword ptr [rax+rax+00h]
0x18001b610  mov     rcx, [rdi+10h]
0x18001b614  mov     [rsp+28h+arg_0], rbx
0x18001b619  test    rcx, rcx
0x18001b61c  jz      short loc_18001B654
0x18001b61e  mov     rax, [rcx]
0x18001b621  mov     rax, [rax+20h]
0x18001b625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b62a  mov     ebx, eax
0x18001b62c  test    eax, eax
0x18001b62e  jns     short loc_18001B64B
0x18001b630  mov     rcx, [rsp+28h]; this
0x18001b635  lea     r8, aMultimediaDsho_2; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x18001b63c  mov     r9d, eax; char *
0x18001b63f  mov     edx, 52h ; 'R'; void *
0x18001b644  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b649  jmp     short loc_18001B656
0x18001b64b  lea     rcx, [rdi+10h]
0x18001b64f  call    ?reset@?$com_ptr_t@UIKsProxyCameraAccessHandler@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IKsProxyCameraAccessHandler,wil::err_returncode_policy>::reset(void)
0x18001b654  xor     ebx, ebx
0x18001b656  lea     rcx, [rsp+28h+arg_0]
0x18001b65b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001b660  mov     eax, ebx
0x18001b662  mov     rbx, [rsp+28h+arg_8]
0x18001b667  add     rsp, 20h
0x18001b66b  pop     rdi
0x18001b66c  retn
```
