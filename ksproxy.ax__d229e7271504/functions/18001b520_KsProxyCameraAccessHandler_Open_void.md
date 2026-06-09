# KsProxyCameraAccessHandler::Open(void *)

- ea: `0x18001b520`
- end: `0x18001b5e9`
- name: `?Open@KsProxyCameraAccessHandler@@UEAAJPEAX@Z`
- size: `201`
- prototype: `__int64 __fastcall(KsProxyCameraAccessHandler *this, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007b38`
- `0x1800081e4`
- `0x180013cfc`
- `0x180016344`
- `0x18001b520`
- `0x180045010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001b55f`
- `KERNEL32!EnterCriticalSection` at `0x18001b55f`

## string_xrefs

- `0x18001b53f`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\ksproxycameraaccesshandler.cpp`
- `0x18001b5b9`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\ksproxycameraaccesshandler.cpp`

## pseudocode

```c
__int64 __fastcall KsProxyCameraAccessHandler::Open(KsProxyCameraAccessHandler *this, void *a2)
{
  unsigned int v4; // ebx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  bool v6; // zf
  __int64 v7; // rcx
  int Instance; // eax
  __int64 v9; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    v6 = *((_QWORD *)this + 2) == 0;
    v12 = v5;
    if ( v6
      && (wil::com_ptr_t<IKsProxyCameraAccessHandler,wil::err_returncode_policy>::reset((__int64 *)this + 2),
          Instance = ThreadProcHelper::CreateInstance(v7, a2, (_QWORD *)this + 2),
          v4 = Instance,
          Instance < 0) )
    {
      v9 = 51;
    }
    else
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2));
      v4 = Instance;
      if ( Instance >= 0 )
      {
        v4 = 0;
        goto LABEL_10;
      }
      v9 = 54;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\ksproxycameraaccesshandler.cpp",
      (const char *)(unsigned int)Instance);
LABEL_10:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v12);
    return v4;
  }
  v4 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A,
    (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\ksproxycameraaccesshandler.cpp",
    (const char *)0x80070057LL);
  return v4;
}

```

## disassembly

```asm
0x18001b520  mov     [rsp+arg_0], rbx
0x18001b525  mov     [rsp+arg_10], rsi
0x18001b52a  push    rdi; int
0x18001b52b  sub     rsp, 20h
0x18001b52f  mov     rsi, rdx
0x18001b532  mov     rdi, rcx
0x18001b535  test    rdx, rdx
0x18001b538  jnz     short loc_18001B558
0x18001b53a  mov     rcx, [rsp+28h]; this
0x18001b53f  lea     r8, aMultimediaDsho_2; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x18001b546  mov     ebx, 80070057h
0x18001b54b  lea     edx, [rsi+2Ah]; void *
0x18001b54e  mov     r9d, ebx; char *
0x18001b551  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b556  jmp     short loc_18001B5D6
0x18001b558  lea     rbx, [rcx+18h]
0x18001b55c  mov     rcx, rbx; lpCriticalSection
0x18001b55f  call    cs:__imp_EnterCriticalSection
0x18001b566  nop     dword ptr [rax+rax+00h]
0x18001b56b  cmp     qword ptr [rdi+10h], 0
0x18001b570  mov     [rsp+28h+arg_8], rbx
0x18001b575  jnz     short loc_18001B599
0x18001b577  lea     rcx, [rdi+10h]
0x18001b57b  call    ?reset@?$com_ptr_t@UIKsProxyCameraAccessHandler@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IKsProxyCameraAccessHandler,wil::err_returncode_policy>::reset(void)
0x18001b580  lea     r8, [rdi+10h]
0x18001b584  mov     rdx, rsi
0x18001b587  call    ?CreateInstance@ThreadProcHelper@@SAJW4ThreadProcWorkType@@PEAXPEAPEAUIThreadProcHelper@@@Z; ThreadProcHelper::CreateInstance(ThreadProcWorkType,void *,IThreadProcHelper * *)
0x18001b58c  mov     ebx, eax
0x18001b58e  test    eax, eax
0x18001b590  jns     short loc_18001B599
0x18001b592  mov     edx, 33h ; '3'
0x18001b597  jmp     short loc_18001B5B4
0x18001b599  mov     rcx, [rdi+10h]
0x18001b59d  mov     rax, [rcx]
0x18001b5a0  mov     rax, [rax+18h]
0x18001b5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5a9  mov     ebx, eax
0x18001b5ab  test    eax, eax
0x18001b5ad  jns     short loc_18001B5CA
0x18001b5af  mov     edx, 36h ; '6'; void *
0x18001b5b4  mov     rcx, [rsp+28h]; this
0x18001b5b9  lea     r8, aMultimediaDsho_2; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x18001b5c0  mov     r9d, eax; char *
0x18001b5c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b5c8  jmp     short loc_18001B5CC
0x18001b5ca  xor     ebx, ebx
0x18001b5cc  lea     rcx, [rsp+28h+arg_8]
0x18001b5d1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001b5d6  mov     rsi, [rsp+28h+arg_10]
0x18001b5db  mov     eax, ebx
0x18001b5dd  mov     rbx, [rsp+28h+arg_0]
0x18001b5e2  add     rsp, 20h
0x18001b5e6  pop     rdi
0x18001b5e7  retn
```
