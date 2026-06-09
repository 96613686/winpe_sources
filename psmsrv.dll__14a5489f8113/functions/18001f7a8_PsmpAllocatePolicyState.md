# PsmpAllocatePolicyState

- ea: `0x18001f7a8`
- end: `0x18001f9e1`
- name: `PsmpAllocatePolicyState`
- size: `569`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f1b0`

## callees

- `0x18001f7a8`
- `0x18001ff84`

## import_xrefs

- `ntdll!TpAllocTimer` at `0x18001f901`
- `ntdll!TpAllocTimer` at `0x18001f901`
- `ntdll!TpSetWait` at `0x18001f9c8`
- `ntdll!TpSetWait` at `0x18001f9c8`
- `ntdll!NtOpenKey` at `0x18001f86c`
- `ntdll!NtOpenKey` at `0x18001f86c`
- `ntdll!NtCreateEvent` at `0x18001f8b9`
- `ntdll!NtCreateEvent` at `0x18001f8b9`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18001f94b`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18001f94b`
- `ntdll!RtlInitUnicodeString` at `0x18001f830`
- `ntdll!RtlInitUnicodeString` at `0x18001f830`
- `ntdll!TpAllocWork` at `0x18001f802`
- `ntdll!TpAllocWork` at `0x18001f802`
- `ntdll!NtPowerInformation` at `0x18001f91f`
- `ntdll!NtPowerInformation` at `0x18001f91f`
- `ntdll!TpAllocWait` at `0x18001f8df`
- `ntdll!TpAllocWait` at `0x18001f9a9`
- `ntdll!TpAllocWait` at `0x18001f8df`
- `ntdll!TpAllocWait` at `0x18001f9a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f976`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f976`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f988`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001f968`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001f968`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f9b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f9b6`

## string_xrefs

- `0x18001f813`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\BackgroundModel\Policy`

## pseudocode

```c
NTSTATUS PsmpAllocatePolicyState()
{
  NTSTATUS result; // eax
  HANDLE v1; // rax
  void *v2; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES v5; // [rsp+70h] [rbp+27h] BYREF
  char OutputBuffer; // [rsp+B0h] [rbp+67h] BYREF
  int v7; // [rsp+B8h] [rbp+6Fh] BYREF
  __int64 v8; // [rsp+C0h] [rbp+77h] BYREF

  v7 = 0;
  OutputBuffer = 0;
  v8 = 0;
  memset(&v5, 0, 44);
  result = PsmpGetCpuSpeed(&v7);
  if ( result >= 0 )
  {
    result = TpAllocWork((char *)&xmmword_180040B10 + 8, PsmpNotificationQueueWorkCallback, &PsmpNotificationQueue, 0);
    if ( result >= 0 )
    {
      memset(&ObjectAttributes, 0, 44);
      DestinationString = 0;
      RtlInitUnicodeString(
        &DestinationString,
        L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\BackgroundModel\\Policy");
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0
        || (v5.Length = 48,
            memset(&v5.RootDirectory, 0, 20),
            *(_OWORD *)&v5.SecurityDescriptor = 0,
            result = NtCreateEvent(&Event, 0x1F0003u, &v5, SynchronizationEvent, 0),
            result >= 0)
        && (result = TpAllocWait(&qword_18003FE30, PsmpPolicyChangeCallback, PsmpPolicy, 0), result >= 0) )
      {
        result = TpAllocTimer(&qword_18003FE28, PsmpPolicyCallback, 0, 0);
        if ( result >= 0 )
        {
          result = NtPowerInformation((POWER_INFORMATION_LEVEL)66, 0, 0, &OutputBuffer, 1u);
          if ( result >= 0 )
          {
            if ( OutputBuffer )
            {
              RtlRunOnceExecuteOnce(&PsmpSystemIsXboxRunOnce, PsmpIsXboxRunOnceRoutine, 0, 0);
              if ( !PsmpSystemIsXbox )
              {
                v1 = OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartPhase1Done");
                v2 = v1;
                if ( !v1 )
                {
                  if ( (int)GetLastError() > 0 )
                    return (unsigned __int16)GetLastError() | 0xC0070000;
                  else
                    return GetLastError();
                }
                if ( (int)TpAllocWait(&v8, &PsmpRegisterDisconnectedStandbyNotificationAsync, v1, 0) >= 0 )
                  TpSetWait(v8, v2, 0);
                else
                  CloseHandle(v2);
              }
            }
            return 0;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001f7a8  mov     [rsp-8+arg_18], rbx
0x18001f7ad  push    rbp
0x18001f7ae  lea     rbp, [rsp-57h]
0x18001f7b3  sub     rsp, 0A0h
0x18001f7ba  xorps   xmm0, xmm0
0x18001f7bd  mov     [rbp+57h+arg_8], 0
0x18001f7c4  xor     eax, eax
0x18001f7c6  lea     rcx, [rbp+57h+arg_8]
0x18001f7ca  movups  xmmword ptr [rbp+57h+var_30.ObjectName], xmm0
0x18001f7ce  mov     [rbp+57h+OutputBuffer], al
0x18001f7d1  movups  xmmword ptr [rbp+57h+var_30+1Ch], xmm0
0x18001f7d5  mov     [rbp+57h+arg_10], rax
0x18001f7d9  movups  xmmword ptr [rbp+57h+var_30.Length], xmm0
0x18001f7dd  call    PsmpGetCpuSpeed
0x18001f7e2  test    eax, eax
0x18001f7e4  js      loc_18001F9D0
0x18001f7ea  xor     r9d, r9d
0x18001f7ed  lea     r8, PsmpNotificationQueue
0x18001f7f4  lea     rdx, PsmpNotificationQueueWorkCallback
0x18001f7fb  lea     rcx, xmmword_180040B10+8
0x18001f802  call    cs:__imp_TpAllocWork
0x18001f808  test    eax, eax
0x18001f80a  js      loc_18001F9D0
0x18001f810  xorps   xmm0, xmm0
0x18001f813  lea     rdx, SourceString; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18001f81a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001f81e  xor     eax, eax
0x18001f820  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001f824  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18001f828  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001f82c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18001f830  call    cs:__imp_RtlInitUnicodeString
0x18001f836  lea     rax, [rbp+57h+DestinationString]
0x18001f83a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001f841  xorps   xmm0, xmm0
0x18001f844  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001f848  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001f84c  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18001f854  mov     edx, 20019h; DesiredAccess
0x18001f859  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18001f860  lea     rcx, KeyHandle; KeyHandle
0x18001f867  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001f86c  call    cs:__imp_NtOpenKey
0x18001f872  mov     ebx, 1
0x18001f877  test    eax, eax
0x18001f879  js      short loc_18001F8ED
0x18001f87b  xorps   xmm0, xmm0
0x18001f87e  mov     [rbp+57h+var_30.Length], 30h ; '0'
0x18001f885  mov     r9d, ebx; EventType
0x18001f888  mov     [rbp+57h+var_30.RootDirectory], 0
0x18001f890  lea     r8, [rbp+57h+var_30]; ObjectAttributes
0x18001f894  mov     [rbp+57h+var_30.Attributes], 0
0x18001f89b  mov     edx, 1F0003h; DesiredAccess
0x18001f8a0  mov     [rbp+57h+var_30.ObjectName], 0
0x18001f8a8  lea     rcx, Event; EventHandle
0x18001f8af  mov     [rsp+0A0h+InitialState], 0; InitialState
0x18001f8b4  movdqu  xmmword ptr [rbp+57h+var_30.SecurityDescriptor], xmm0
0x18001f8b9  call    cs:__imp_NtCreateEvent
0x18001f8bf  test    eax, eax
0x18001f8c1  js      loc_18001F9D0
0x18001f8c7  xor     r9d, r9d
0x18001f8ca  lea     r8, PsmpPolicy
0x18001f8d1  lea     rdx, PsmpPolicyChangeCallback
0x18001f8d8  lea     rcx, qword_18003FE30
0x18001f8df  call    cs:__imp_TpAllocWait
0x18001f8e5  test    eax, eax
0x18001f8e7  js      loc_18001F9D0
0x18001f8ed  xor     r9d, r9d
0x18001f8f0  lea     rdx, PsmpPolicyCallback
0x18001f8f7  xor     r8d, r8d
0x18001f8fa  lea     rcx, qword_18003FE28
0x18001f901  call    cs:__imp_TpAllocTimer
0x18001f907  test    eax, eax
0x18001f909  js      loc_18001F9D0
0x18001f90f  xor     edx, edx; InputBuffer
0x18001f911  mov     dword ptr [rsp+0A0h+InitialState], ebx; OutputBufferLength
0x18001f915  lea     r9, [rbp+57h+OutputBuffer]; OutputBuffer
0x18001f919  xor     r8d, r8d; InputBufferLength
0x18001f91c  lea     ecx, [rdx+42h]; PowerInformationLevel
0x18001f91f  call    cs:__imp_NtPowerInformation
0x18001f925  test    eax, eax
0x18001f927  js      loc_18001F9D0
0x18001f92d  cmp     [rbp+57h+OutputBuffer], 0
0x18001f931  jz      loc_18001F9CE
0x18001f937  xor     r9d, r9d
0x18001f93a  lea     rdx, PsmpIsXboxRunOnceRoutine
0x18001f941  xor     r8d, r8d
0x18001f944  lea     rcx, PsmpSystemIsXboxRunOnce
0x18001f94b  call    cs:__imp_RtlRunOnceExecuteOnce
0x18001f951  cmp     cs:PsmpSystemIsXbox, 0
0x18001f958  jnz     short loc_18001F9CE
0x18001f95a  lea     r8, Name; "Global\\SC_AutoStartPhase1Done"
0x18001f961  xor     edx, edx; bInheritHandle
0x18001f963  mov     ecx, 100000h; dwDesiredAccess
0x18001f968  call    cs:__imp_OpenEventW
0x18001f96e  mov     rbx, rax
0x18001f971  test    rax, rax
0x18001f974  jnz     short loc_18001F998
0x18001f976  call    cs:__imp_GetLastError
0x18001f97c  test    eax, eax
0x18001f97e  jg      short loc_18001F988
0x18001f980  call    cs:__imp_GetLastError
0x18001f986  jmp     short loc_18001F9D0
0x18001f988  call    cs:__imp_GetLastError
0x18001f98e  movzx   eax, ax
0x18001f991  or      eax, 0C0070000h
0x18001f996  jmp     short loc_18001F9D0
0x18001f998  xor     r9d, r9d
0x18001f99b  lea     rdx, PsmpRegisterDisconnectedStandbyNotificationAsync
0x18001f9a2  mov     r8, rbx
0x18001f9a5  lea     rcx, [rbp+57h+arg_10]
0x18001f9a9  call    cs:__imp_TpAllocWait
0x18001f9af  test    eax, eax
0x18001f9b1  jns     short loc_18001F9BE
0x18001f9b3  mov     rcx, rbx; hObject
0x18001f9b6  call    cs:__imp_CloseHandle
0x18001f9bc  jmp     short loc_18001F9CE
0x18001f9be  mov     rcx, [rbp+57h+arg_10]
0x18001f9c2  xor     r8d, r8d
0x18001f9c5  mov     rdx, rbx
0x18001f9c8  call    cs:__imp_TpSetWait
0x18001f9ce  xor     eax, eax
0x18001f9d0  mov     rbx, [rsp+0A0h+arg_18]
0x18001f9d8  add     rsp, 0A0h
0x18001f9df  pop     rbp
0x18001f9e0  retn
```
