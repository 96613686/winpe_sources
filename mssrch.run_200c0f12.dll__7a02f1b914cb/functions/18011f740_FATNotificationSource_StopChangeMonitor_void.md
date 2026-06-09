# FATNotificationSource::StopChangeMonitor(void)

- ea: `0x18011f740`
- end: `0x18011f890`
- name: `?StopChangeMonitor@FATNotificationSource@@UEAAJXZ`
- size: `336`
- prototype: `__int64 __fastcall(FATNotificationSource *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18011f660`

## callees

- `0x18000bf8c`
- `0x18002bf00`
- `0x18011f740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011f762`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011f800`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011f762`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011f800`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18011f7c4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18011f7c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18011f7a2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18011f7a2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18011f7d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18011f7d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18011f7e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18011f7e3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18011f795`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18011f795`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011f813`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011f831`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011f84e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011f813`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011f831`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011f84e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FATNotificationSource::StopChangeMonitor(FATNotificationSource *this)
{
  struct _TP_IO *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  char *v7; // [rsp+30h] [rbp+8h] BYREF
  char *v8; // [rsp+38h] [rbp+10h] BYREF

  if ( !*((_BYTE *)this + 66160) )
  {
    v7 = (char *)this + 66112;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 66112));
    if ( !*((_BYTE *)this + 66160) )
    {
      *((_BYTE *)this + 66160) = 1;
      *((_BYTE *)this + 66056) = 0;
      v2 = (struct _TP_IO *)*((_QWORD *)this + 8256);
      if ( v2 )
      {
        WaitForThreadpoolIoCallbacks(v2, 1);
        CloseThreadpoolIo(*((PTP_IO *)this + 8256));
        *((_QWORD *)this + 8256) = 0;
      }
      if ( *((_QWORD *)this + 8273) )
      {
        SetEvent(*((HANDLE *)this + 8274));
        WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 8273), 1);
        CloseThreadpoolWork(*((PTP_WORK *)this + 8273));
        *((_QWORD *)this + 8273) = 0;
      }
      v8 = (char *)this + 66064;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 66064));
      v3 = (void *)*((_QWORD *)this + 8274);
      if ( v3 )
      {
        CloseHandle(v3);
        *((_QWORD *)this + 8274) = 0;
      }
      v4 = (void *)*((_QWORD *)this + 8251);
      if ( v4 != (void *)-1LL )
      {
        CloseHandle(v4);
        *((_QWORD *)this + 8251) = -1;
      }
      v5 = (void *)*((_QWORD *)this + 8255);
      if ( v5 )
      {
        CloseHandle(v5);
        *((_QWORD *)this + 8255) = 0;
        ETWLog::Log(L"CFatNotify - Stopped change monitor: %s", *((_QWORD *)this + 8200));
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v8);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18011f740  push    rbx
0x18011f742  sub     rsp, 20h
0x18011f746  mov     rbx, rcx
0x18011f749  cmp     byte ptr [rcx+10270h], 0
0x18011f750  jnz     loc_18011F888
0x18011f756  add     rcx, 10240h; lpCriticalSection
0x18011f75d  mov     [rsp+28h+arg_0], rcx
0x18011f762  call    cs:__imp_EnterCriticalSection
0x18011f768  nop
0x18011f769  cmp     byte ptr [rbx+10270h], 0
0x18011f770  jnz     loc_18011F87E
0x18011f776  mov     byte ptr [rbx+10270h], 1
0x18011f77d  mov     byte ptr [rbx+10208h], 0
0x18011f784  mov     rcx, [rbx+10200h]; pio
0x18011f78b  test    rcx, rcx
0x18011f78e  jz      short loc_18011F7B3
0x18011f790  mov     edx, 1; fCancelPendingCallbacks
0x18011f795  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x18011f79b  mov     rcx, [rbx+10200h]; pio
0x18011f7a2  call    cs:__imp_CloseThreadpoolIo
0x18011f7a8  mov     qword ptr [rbx+10200h], 0
0x18011f7b3  cmp     qword ptr [rbx+10288h], 0
0x18011f7bb  jz      short loc_18011F7F4
0x18011f7bd  mov     rcx, [rbx+10290h]; hEvent
0x18011f7c4  call    cs:__imp_SetEvent
0x18011f7ca  mov     edx, 1; fCancelPendingCallbacks
0x18011f7cf  mov     rcx, [rbx+10288h]; pwk
0x18011f7d6  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18011f7dc  mov     rcx, [rbx+10288h]; pwk
0x18011f7e3  call    cs:__imp_CloseThreadpoolWork
0x18011f7e9  mov     qword ptr [rbx+10288h], 0
0x18011f7f4  lea     rcx, [rbx+10210h]; lpCriticalSection
0x18011f7fb  mov     [rsp+28h+arg_8], rcx
0x18011f800  call    cs:__imp_EnterCriticalSection
0x18011f806  nop
0x18011f807  mov     rcx, [rbx+10290h]; hObject
0x18011f80e  test    rcx, rcx
0x18011f811  jz      short loc_18011F824
0x18011f813  call    cs:__imp_CloseHandle
0x18011f819  mov     qword ptr [rbx+10290h], 0
0x18011f824  mov     rcx, [rbx+101D8h]; hObject
0x18011f82b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18011f82f  jz      short loc_18011F842
0x18011f831  call    cs:__imp_CloseHandle
0x18011f837  mov     qword ptr [rbx+101D8h], 0FFFFFFFFFFFFFFFFh
0x18011f842  mov     rcx, [rbx+101F8h]; hObject
0x18011f849  test    rcx, rcx
0x18011f84c  jz      short loc_18011F873
0x18011f84e  call    cs:__imp_CloseHandle
0x18011f854  mov     qword ptr [rbx+101F8h], 0
0x18011f85f  mov     rdx, [rbx+10040h]
0x18011f866  lea     rcx, aCfatnotifyStop; "CFatNotify - Stopped change monitor: %s"
0x18011f86d  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x18011f872  nop
0x18011f873  lea     rcx, [rsp+28h+arg_8]
0x18011f878  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18011f87d  nop
0x18011f87e  lea     rcx, [rsp+28h+arg_0]
0x18011f883  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18011f888  xor     eax, eax
0x18011f88a  add     rsp, 20h
0x18011f88e  pop     rbx
0x18011f88f  retn
```
