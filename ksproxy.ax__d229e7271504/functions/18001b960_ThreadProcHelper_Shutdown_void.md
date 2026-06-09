# ThreadProcHelper::Shutdown(void)

- ea: `0x18001b960`
- end: `0x18001ba64`
- name: `?Shutdown@ThreadProcHelper@@UEAAJXZ`
- size: `260`
- prototype: `__int64 __fastcall(ThreadProcHelper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001b8c0`

## callees

- `0x180006de0`
- `0x180015d50`
- `0x180016344`
- `0x18001b960`
- `0x1800433b0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18001b9d6`
- `KERNEL32!WaitForSingleObject` at `0x18001b9d6`
- `KERNEL32!EnterCriticalSection` at `0x18001b979`
- `KERNEL32!EnterCriticalSection` at `0x18001ba11`
- `KERNEL32!EnterCriticalSection` at `0x18001b979`
- `KERNEL32!EnterCriticalSection` at `0x18001ba11`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x18001b9b6`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x18001b9b6`

## string_xrefs

- `0x18001b9fd`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`
- `0x18001b9eb`: `CAM/AudioState thread shutdown timed out(60s)`

## pseudocode

```c
__int64 __fastcall ThreadProcHelper::Shutdown(ThreadProcHelper *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  unsigned __int64 v3; // rax
  const char *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v7; // [rsp+40h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v8; // [rsp+48h] [rbp+10h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v7 = v1;
  v3 = *((_QWORD *)this + 3) - 1LL;
  *((_BYTE *)this + 88) = 1;
  if ( v3 <= 0xFFFFFFFFFFFFFFFDuLL && !*((_DWORD *)this + 8) )
  {
    *((_DWORD *)this + 4) = 1;
    WakeByAddressSingle((char *)this + 16);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
      &v7,
      0);
    if ( WaitForSingleObject(*((HANDLE *)this + 3), 0xEA60u) )
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xA0,
        (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
        (const char *)0x800705B4LL,
        (int)"CAM/AudioState thread shutdown timed out(60s)",
        v5);
    EnterCriticalSection(v1);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
      &v7,
      v1);
    v8 = 0;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v8);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (void **)this + 3,
      0);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v7);
  return 0;
}

```

## disassembly

```asm
0x18001b960  mov     [rsp+arg_10], rbx
0x18001b965  mov     [rsp+arg_18], rsi
0x18001b96a  push    rdi
0x18001b96b  sub     rsp, 30h
0x18001b96f  lea     rdi, [rcx+30h]
0x18001b973  mov     rbx, rcx
0x18001b976  mov     rcx, rdi; lpCriticalSection
0x18001b979  call    cs:__imp_EnterCriticalSection
0x18001b980  nop     dword ptr [rax+rax+00h]
0x18001b985  lea     rsi, [rbx+18h]
0x18001b989  mov     [rsp+38h+arg_0], rdi
0x18001b98e  mov     rax, [rsi]
0x18001b991  dec     rax
0x18001b994  mov     byte ptr [rbx+58h], 1
0x18001b998  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b99c  ja      loc_18001BA47
0x18001b9a2  cmp     dword ptr [rbx+20h], 0
0x18001b9a6  jnz     loc_18001BA47
0x18001b9ac  lea     rcx, [rbx+10h]; Address
0x18001b9b0  mov     dword ptr [rcx], 1
0x18001b9b6  call    cs:__imp_WakeByAddressSingle
0x18001b9bd  nop     dword ptr [rax+rax+00h]
0x18001b9c2  xor     edx, edx
0x18001b9c4  lea     rcx, [rsp+38h+arg_0]
0x18001b9c9  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x18001b9ce  mov     rcx, [rsi]; hHandle
0x18001b9d1  mov     edx, 0EA60h; dwMilliseconds
0x18001b9d6  call    cs:__imp_WaitForSingleObject
0x18001b9dd  nop     dword ptr [rax+rax+00h]
0x18001b9e2  test    eax, eax
0x18001b9e4  jz      short loc_18001BA0E
0x18001b9e6  mov     rcx, [rsp+38h]; this
0x18001b9eb  lea     rax, aCamAudiostateT; "CAM/AudioState thread shutdown timed ou"...
0x18001b9f2  mov     r9d, 800705B4h; char *
0x18001b9f8  mov     qword ptr [rsp+38h+var_18], rax; int
0x18001b9fd  lea     r8, aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x18001ba04  mov     edx, 0A0h; void *
0x18001ba09  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001ba0e  mov     rcx, rdi; lpCriticalSection
0x18001ba11  call    cs:__imp_EnterCriticalSection
0x18001ba18  nop     dword ptr [rax+rax+00h]
0x18001ba1d  mov     rdx, rdi
0x18001ba20  lea     rcx, [rsp+38h+arg_0]
0x18001ba25  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x18001ba2a  lea     rcx, [rsp+38h+arg_8]
0x18001ba2f  mov     [rsp+38h+arg_8], 0
0x18001ba38  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001ba3d  xor     edx, edx
0x18001ba3f  mov     rcx, rsi
0x18001ba42  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001ba47  lea     rcx, [rsp+38h+arg_0]
0x18001ba4c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001ba51  mov     rbx, [rsp+38h+arg_10]
0x18001ba56  xor     eax, eax
0x18001ba58  mov     rsi, [rsp+38h+arg_18]
0x18001ba5d  add     rsp, 30h
0x18001ba61  pop     rdi
0x18001ba62  retn
```
