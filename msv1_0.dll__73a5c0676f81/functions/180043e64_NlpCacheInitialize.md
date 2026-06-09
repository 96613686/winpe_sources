# NlpCacheInitialize

- ea: `0x180043e64`
- end: `0x180044173`
- name: `NlpCacheInitialize`
- size: `783`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ec48`

## callees

- `0x18002ee7c`
- `0x18002f014`
- `0x18002ffec`
- `0x1800425d0`
- `0x180043e64`
- `0x18005c354`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043ff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043ff5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044106`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044106`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043efc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043efc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800440e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800440e9`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004402b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004402b`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180043fc2`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180043fc2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180044125`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180044125`
- `ntdll!RtlInitializeResource` at `0x180043e7d`
- `ntdll!RtlInitializeResource` at `0x180043e7d`
- `ntdll!NtCreateEvent` at `0x180043f5b`
- `ntdll!NtCreateEvent` at `0x180043f5b`

## pseudocode

```c
__int64 NlpCacheInitialize()
{
  _QWORD *v0; // rax
  const WCHAR *v1; // rcx
  int v2; // ebx
  DWORD LastError; // eax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  NTSTATUS Event; // eax
  DWORD pdwValue; // [rsp+40h] [rbp+8h] BYREF

  pdwValue = 0;
  RtlInitializeResource(&NlpLogonCacheCritSec);
  v0 = operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v0 )
  {
    v1 = 0;
    *v0 = 0;
  }
  qword_180089B08 = (__int64)v0;
  if ( v0 )
  {
    if ( SLGetWindowsInformationDWORD(v1, &pdwValue) || (pdwValue & 1) == 0 )
    {
      v2 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_905305d962583d6f838b30057de84013_Traceguids);
      HIDWORD(NlpCacheControl) = 0;
      qword_1800870F0 = (__int64)&NlpActiveCtes;
      NlpActiveCtes.Flink = &NlpActiveCtes;
      qword_1800870E0 = (__int64)&NlpInactiveCtes;
      NlpInactiveCtes.Flink = &NlpInactiveCtes;
    }
    else
    {
      LastError = RegOpenKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
                    0,
                    0x20019u,
                    &hKey);
      if ( LastError )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_12;
        v5 = 13;
LABEL_11:
        WPP_SF_d(v4[2], v5, WPP_905305d962583d6f838b30057de84013_Traceguids, LastError);
LABEL_12:
        v2 = -1073741823;
        goto LABEL_31;
      }
      Event = NtCreateEvent(&hObject, 0x1F0003u, 0, SynchronizationEvent, 0);
      v2 = Event;
      if ( Event >= 0 )
      {
        WaitHandle = (HANDLE)RegisterWaitForSingleObjectEx(hObject, NlpWatchCachedLogonsCountKey, 0, 0xFFFFFFFFLL, 128);
        if ( !WaitHandle )
        {
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_12;
          LastError = GetLastError();
          v5 = 15;
          v4 = WPP_GLOBAL_Control;
          goto LABEL_11;
        }
        LastError = RegNotifyChangeKeyValue(hKey, 1, 5u, hObject, 1);
        if ( LastError )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_12;
          v5 = 16;
          goto LABEL_11;
        }
        v2 = NlpInternalCacheInitialize();
        NlpCacheInitialized = 1;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_905305d962583d6f838b30057de84013_Traceguids,
          (unsigned int)Event);
      }
    }
    if ( v2 >= 0 )
      return (unsigned int)v2;
    goto LABEL_31;
  }
  v2 = -1073741801;
LABEL_31:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( WaitHandle )
  {
    if ( !UnregisterWaitEx(WaitHandle, 0)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_905305d962583d6f838b30057de84013_Traceguids);
    }
    WaitHandle = 0;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180043e64  mov     [rsp+arg_8], rbx
0x180043e69  push    rdi
0x180043e6a  sub     rsp, 30h
0x180043e6e  mov     [rsp+38h+pdwValue], 0
0x180043e76  lea     rcx, NlpLogonCacheCritSec; Resource
0x180043e7d  call    cs:__imp_RtlInitializeResource
0x180043e83  nop
0x180043e84  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180043e8b  mov     ecx, 8; unsigned __int64
0x180043e90  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180043e95  test    rax, rax
0x180043e98  jz      short loc_180043E9F
0x180043e9a  xor     ecx, ecx; pwszValueName
0x180043e9c  mov     [rax], rcx
0x180043e9f  mov     cs:qword_180089B08, rax
0x180043ea6  test    rax, rax
0x180043ea9  jnz     short loc_180043EBC
0x180043eab  mov     ebx, 0C0000017h
0x180043eb0  lea     rdi, WPP_GLOBAL_Control
0x180043eb7  jmp     loc_1800440DD
0x180043ebc  lea     rdx, [rsp+38h+pdwValue]; pdwValue
0x180043ec1  call    SLGetWindowsInformationDWORD
0x180043ec6  test    eax, eax
0x180043ec8  jnz     loc_180044077
0x180043ece  test    byte ptr [rsp+38h+pdwValue], 1
0x180043ed3  jz      loc_180044077
0x180043ed9  lea     rax, hKey
0x180043ee0  mov     [rsp+38h+phkResult], rax; phkResult
0x180043ee5  mov     r9d, 20019h; samDesired
0x180043eeb  xor     r8d, r8d; ulOptions
0x180043eee  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180043ef5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043efc  call    cs:__imp_RegOpenKeyExW
0x180043f02  test    eax, eax
0x180043f04  jz      short loc_180043F41
0x180043f06  lea     rdi, WPP_GLOBAL_Control
0x180043f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180043f14  cmp     rcx, rdi
0x180043f17  jz      short loc_180043F37
0x180043f19  test    byte ptr [rcx+1Ch], 2
0x180043f1d  jz      short loc_180043F37
0x180043f1f  mov     edx, 0Dh
0x180043f24  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x180043f2b  mov     r9d, eax
0x180043f2e  mov     rcx, [rcx+10h]
0x180043f32  call    WPP_SF_d
0x180043f37  mov     ebx, 0C0000001h
0x180043f3c  jmp     loc_1800440DD
0x180043f41  mov     byte ptr [rsp+38h+phkResult], 0; InitialState
0x180043f46  mov     r9d, 1; EventType
0x180043f4c  xor     r8d, r8d; ObjectAttributes
0x180043f4f  mov     edx, 1F0003h; DesiredAccess
0x180043f54  lea     rcx, hObject; EventHandle
0x180043f5b  call    cs:__imp_NtCreateEvent
0x180043f61  mov     ebx, eax
0x180043f63  test    eax, eax
0x180043f65  jns     short loc_180043FA5
0x180043f67  lea     rdi, WPP_GLOBAL_Control
0x180043f6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180043f75  cmp     rcx, rdi
0x180043f78  jz      loc_1800440D5
0x180043f7e  test    byte ptr [rcx+1Ch], 1
0x180043f82  jz      loc_1800440D5
0x180043f88  mov     edx, 0Eh
0x180043f8d  mov     r9d, eax
0x180043f90  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x180043f97  mov     rcx, [rcx+10h]
0x180043f9b  call    WPP_SF_d
0x180043fa0  jmp     loc_1800440D5
0x180043fa5  mov     dword ptr [rsp+38h+phkResult], 80h
0x180043fad  or      r9d, 0FFFFFFFFh
0x180043fb1  xor     r8d, r8d
0x180043fb4  lea     rdx, ?NlpWatchCachedLogonsCountKey@@YAXPEAXE@Z; NlpWatchCachedLogonsCountKey(void *,uchar)
0x180043fbb  mov     rcx, cs:hObject
0x180043fc2  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180043fc8  mov     cs:WaitHandle, rax
0x180043fcf  test    rax, rax
0x180043fd2  jnz     short loc_18004400C
0x180043fd4  lea     rdi, WPP_GLOBAL_Control
0x180043fdb  mov     rax, cs:WPP_GLOBAL_Control
0x180043fe2  cmp     rax, rdi
0x180043fe5  jz      loc_180043F37
0x180043feb  test    byte ptr [rax+1Ch], 1
0x180043fef  jz      loc_180043F37
0x180043ff5  call    cs:__imp_GetLastError
0x180043ffb  mov     edx, 0Fh
0x180044000  mov     rcx, cs:WPP_GLOBAL_Control
0x180044007  jmp     loc_180043F24
0x18004400c  mov     dword ptr [rsp+38h+phkResult], 1; fAsynchronous
0x180044014  mov     r9, cs:hObject; hEvent
0x18004401b  mov     edx, 1; bWatchSubtree
0x180044020  lea     r8d, [rdx+4]; dwNotifyFilter
0x180044024  mov     rcx, cs:hKey; hKey
0x18004402b  call    cs:__imp_RegNotifyChangeKeyValue
0x180044031  test    eax, eax
0x180044033  jz      short loc_180044060
0x180044035  lea     rdi, WPP_GLOBAL_Control
0x18004403c  mov     rcx, cs:WPP_GLOBAL_Control
0x180044043  cmp     rcx, rdi
0x180044046  jz      loc_180043F37
0x18004404c  test    byte ptr [rcx+1Ch], 1
0x180044050  jz      loc_180043F37
0x180044056  mov     edx, 10h
0x18004405b  jmp     loc_180043F24
0x180044060  call    ?NlpInternalCacheInitialize@@YAJXZ; NlpInternalCacheInitialize(void)
0x180044065  mov     ebx, eax
0x180044067  mov     cs:NlpCacheInitialized, 1
0x18004406e  lea     rdi, WPP_GLOBAL_Control
0x180044075  jmp     short loc_1800440D5
0x180044077  xor     ebx, ebx
0x180044079  lea     rdi, WPP_GLOBAL_Control
0x180044080  mov     rcx, cs:WPP_GLOBAL_Control
0x180044087  cmp     rcx, rdi
0x18004408a  jz      short loc_1800440A5
0x18004408c  test    byte ptr [rcx+1Ch], 2
0x180044090  jz      short loc_1800440A5
0x180044092  lea     edx, [rbx+0Ch]
0x180044095  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x18004409c  mov     rcx, [rcx+10h]
0x1800440a0  call    WPP_SF_
0x1800440a5  mov     dword ptr cs:NlpCacheControl+4, ebx
0x1800440ab  lea     rax, ?NlpActiveCtes@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlpActiveCtes
0x1800440b2  mov     cs:qword_1800870F0, rax
0x1800440b9  mov     cs:?NlpActiveCtes@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlpActiveCtes
0x1800440c0  lea     rax, ?NlpInactiveCtes@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlpInactiveCtes
0x1800440c7  mov     cs:qword_1800870E0, rax
0x1800440ce  mov     cs:?NlpInactiveCtes@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlpInactiveCtes
0x1800440d5  test    ebx, ebx
0x1800440d7  jns     loc_18004415F
0x1800440dd  mov     rcx, cs:hKey; hKey
0x1800440e4  test    rcx, rcx
0x1800440e7  jz      short loc_1800440FA
0x1800440e9  call    cs:__imp_RegCloseKey
0x1800440ef  mov     cs:hKey, 0
0x1800440fa  mov     rcx, cs:hObject; hObject
0x180044101  test    rcx, rcx
0x180044104  jz      short loc_180044117
0x180044106  call    cs:__imp_CloseHandle
0x18004410c  mov     cs:hObject, 0
0x180044117  mov     rcx, cs:WaitHandle; WaitHandle
0x18004411e  test    rcx, rcx
0x180044121  jz      short loc_18004415F
0x180044123  xor     edx, edx; CompletionEvent
0x180044125  call    cs:__imp_UnregisterWaitEx
0x18004412b  test    eax, eax
0x18004412d  jnz     short loc_180044154
0x18004412f  mov     rcx, cs:WPP_GLOBAL_Control
0x180044136  cmp     rcx, rdi
0x180044139  jz      short loc_180044154
0x18004413b  test    byte ptr [rcx+1Ch], 2
0x18004413f  jz      short loc_180044154
0x180044141  lea     edx, [rax+11h]
0x180044144  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x18004414b  mov     rcx, [rcx+10h]
0x18004414f  call    WPP_SF_
0x180044154  mov     cs:WaitHandle, 0
0x18004415f  mov     eax, ebx
0x180044161  jmp     short loc_180044168
0x180044163  mov     eax, 0C000009Ah
0x180044168  mov     rbx, [rsp+38h+arg_8]
0x18004416d  add     rsp, 30h
0x180044171  pop     rdi
0x180044172  retn
```
