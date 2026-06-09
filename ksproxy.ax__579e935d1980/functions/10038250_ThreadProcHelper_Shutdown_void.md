# ThreadProcHelper::Shutdown(void)

- ea: `0x10038250`
- end: `0x10038316`
- name: `?Shutdown@ThreadProcHelper@@UAGJXZ`
- size: `198`
- prototype: `int __stdcall(ThreadProcHelper *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x100380b7`

## callees

- `0x1000f70b`
- `0x10038250`
- `0x10038804`
- `0x100394d3`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10038299`
- `KERNEL32!GetLastError` at `0x10038299`
- `KERNEL32!WaitForSingleObject` at `0x100382bd`
- `KERNEL32!WaitForSingleObject` at `0x100382bd`
- `KERNEL32!LeaveCriticalSection` at `0x100382a2`
- `KERNEL32!LeaveCriticalSection` at `0x10038307`
- `KERNEL32!LeaveCriticalSection` at `0x100382a2`
- `KERNEL32!LeaveCriticalSection` at `0x10038307`
- `KERNEL32!EnterCriticalSection` at `0x10038260`
- `KERNEL32!EnterCriticalSection` at `0x100382e7`
- `KERNEL32!EnterCriticalSection` at `0x10038260`
- `KERNEL32!EnterCriticalSection` at `0x100382e7`
- `KERNEL32!SetLastError` at `0x100382a9`
- `KERNEL32!SetLastError` at `0x100382a9`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x1003828f`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x1003828f`

## string_xrefs

- `0x100382d1`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`
- `0x100382c7`: `CAM/AudioState thread shutdown timed out(60s)`

## pseudocode

```c
int __stdcall ThreadProcHelper::Shutdown(ThreadProcHelper *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // edi
  HANDLE *v2; // ebx
  DWORD LastError; // esi
  const char *v5; // [esp+0h] [ebp-10h]
  wil::details::in1diag3 *retaddr; // [esp+14h] [ebp+4h]

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 28);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 28));
  v2 = (HANDLE *)((char *)this + 16);
  *((_BYTE *)this + 52) = 1;
  if ( *((_DWORD *)this + 4) && *v2 != (HANDLE)-1 && !*((_DWORD *)this + 5) )
  {
    *((_DWORD *)this + 3) = 1;
    WakeByAddressSingle((char *)this + 12);
    if ( this != (ThreadProcHelper *)-28 )
    {
      LastError = GetLastError();
      LeaveCriticalSection(v1);
      SetLastError(LastError);
    }
    if ( WaitForSingleObject(*v2, 0xEA60u) )
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xA0,
        (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
        (const char *)0x800705B4,
        (int)"CAM/AudioState thread shutdown timed out(60s)",
        v5);
    EnterCriticalSection(v1);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (__stdcall *)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned int,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(v1);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__stdcall *)(void *),&int CloseHandle(void *)>>::reset(0);
    v1 = 0;
  }
  if ( v1 )
    LeaveCriticalSection(v1);
  return 0;
}

```

## disassembly

```asm
0x10038250  mov     edi, edi
0x10038252  push    ebp
0x10038253  mov     ebp, esp
0x10038255  push    ecx
0x10038256  push    ebx
0x10038257  push    esi
0x10038258  mov     esi, [ebp+this]
0x1003825b  push    edi; char *
0x1003825c  lea     edi, [esi+1Ch]
0x1003825f  push    edi; lpCriticalSection
0x10038260  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10038266  lea     ebx, [esi+10h]
0x10038269  mov     byte ptr [esi+34h], 1
0x1003826d  cmp     dword ptr [ebx], 0
0x10038270  jz      loc_10038302
0x10038276  cmp     dword ptr [ebx], 0FFFFFFFFh
0x10038279  jz      loc_10038302
0x1003827f  cmp     dword ptr [esi+14h], 0
0x10038283  jnz     short loc_10038302
0x10038285  lea     eax, [esi+0Ch]
0x10038288  push    eax; Address
0x10038289  mov     dword ptr [eax], 1
0x1003828f  call    ds:__imp__WakeByAddressSingle@4; WakeByAddressSingle(x)
0x10038295  test    edi, edi
0x10038297  jz      short loc_100382AF
0x10038299  call    ds:__imp__GetLastError@0; GetLastError()
0x1003829f  push    edi; lpCriticalSection
0x100382a0  mov     esi, eax
0x100382a2  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100382a8  push    esi; dwErrCode
0x100382a9  call    ds:__imp__SetLastError@4; SetLastError(x)
0x100382af  push    0EA60h; dwMilliseconds
0x100382b4  push    dword ptr [ebx]; hHandle
0x100382b6  mov     [ebp+var_4], 0
0x100382bd  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x100382c3  test    eax, eax
0x100382c5  jz      short loc_100382E6
0x100382c7  push    offset aCamAudiostateT; "CAM/AudioState thread shutdown timed ou"...
0x100382cc  push    800705B4h; char *
0x100382d1  push    offset aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x100382d6  push    0A0h; void *
0x100382db  push    dword ptr [ebp+4]; this
0x100382de  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPAXIPBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x100382e3  add     esp, 14h
0x100382e6  push    edi; lpCriticalSection
0x100382e7  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100382ed  push    edi
0x100382ee  lea     ecx, [ebp+var_4]
0x100382f1  call    ?reset@?$unique_storage@U?$resource_policy@PAU_RTL_CRITICAL_SECTION@@P6GXPAU1@@Z$1?LeaveCriticalSection@@YGX0@ZU?$integral_constant@I$00@wistd@@PAU1@PAU1@$0A@$$T@details@wil@@@details@wil@@QAEXPAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<uint,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x100382f6  push    0
0x100382f8  mov     ecx, ebx
0x100382fa  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6GHPAX@Z$1?CloseHandle@@YGH0@Z@details@wil@@@details@wil@@QAEXPAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x100382ff  mov     edi, [ebp+var_4]
0x10038302  test    edi, edi
0x10038304  jz      short loc_1003830D
0x10038306  push    edi; lpCriticalSection
0x10038307  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1003830d  pop     edi
0x1003830e  pop     esi
0x1003830f  xor     eax, eax
0x10038311  pop     ebx
0x10038312  leave
0x10038313  retn    4
```
