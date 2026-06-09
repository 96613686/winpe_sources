# SockpSanRegister

- ea: `0x180044380`
- end: `0x1800444fa`
- name: `SockpSanRegister`
- size: `378`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003eb24`
- `0x18004270c`
- `0x180042c70`
- `0x180044090`

## callees

- `0x18001e14c`
- `0x1800250e0`
- `0x180038104`
- `0x18003ae8c`
- `0x18003aec4`
- `0x180044380`

## import_xrefs

- `ntdll!NtCreateEvent` at `0x1800443b4`
- `ntdll!NtCreateEvent` at `0x1800443b4`
- `ntdll!NtSetInformationFile` at `0x18004443f`
- `ntdll!NtSetInformationFile` at `0x18004443f`
- `ntdll!NtClose` at `0x18004449d`
- `ntdll!NtClose` at `0x1800444da`
- `ntdll!NtClose` at `0x18004449d`
- `ntdll!NtClose` at `0x1800444da`

## pseudocode

```c
__int64 SockpSanRegister()
{
  __int64 result; // rax
  NTSTATUS Event; // eax
  unsigned int v2; // ebx
  int v3; // eax
  __int64 v4; // rcx
  NTSTATUS v5; // eax
  _QWORD FileInformation[2]; // [rsp+30h] [rbp-28h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-18h] BYREF

  if ( !SockAsyncQueuePort )
  {
    result = SockCreateAsyncQueuePort();
    if ( (int)result < 0 )
      return result;
  }
  Event = NtCreateEvent(&SockSanEvent, 0x1F0003u, 0, NotificationEvent, 0);
  v2 = Event;
  if ( Event < 0 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_d(1025, 29, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, (unsigned int)Event);
    return v2;
  }
  v3 = AfdRegisterSwitch();
  v2 = v3;
  if ( v3 < 0 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_l(v4, 32, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, (unsigned int)v3);
    goto LABEL_16;
  }
  FileInformation[0] = SockAsyncQueuePort;
  FileInformation[1] = SockSanCompletion;
  IoStatusBlock = 0;
  v5 = NtSetInformationFile(SockSanHelperHandle, &IoStatusBlock, FileInformation, 0x10u, FileCompletionInformation);
  v2 = v5;
  if ( v5 < 0 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_d(1025, 31, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, (unsigned int)v5);
    NtClose(SockSanHelperHandle);
    SockSanHelperHandle = 0;
LABEL_16:
    NtClose(SockSanEvent);
    SockSanEvent = 0;
    return v2;
  }
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_(1025, 30, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180044380  push    rbx
0x180044382  sub     rsp, 50h
0x180044386  cmp     cs:SockAsyncQueuePort, 0
0x18004438e  jnz     short loc_18004439D
0x180044390  call    SockCreateAsyncQueuePort
0x180044395  test    eax, eax
0x180044397  js      loc_1800444F3
0x18004439d  xor     r9d, r9d; EventType
0x1800443a0  mov     [rsp+58h+InitialState], 0; InitialState
0x1800443a5  xor     r8d, r8d; ObjectAttributes
0x1800443a8  lea     rcx, SockSanEvent; EventHandle
0x1800443af  mov     edx, 1F0003h; DesiredAccess
0x1800443b4  call    cs:__imp_NtCreateEvent
0x1800443bb  nop     dword ptr [rax+rax+00h]
0x1800443c0  mov     ebx, eax
0x1800443c2  test    eax, eax
0x1800443c4  jns     short loc_1800443F1
0x1800443c6  test    byte ptr cs:xmmword_180063D60, 2
0x1800443cd  jz      loc_1800444F1
0x1800443d3  mov     edx, 1Dh
0x1800443d8  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x1800443df  mov     ecx, 401h
0x1800443e4  mov     r9d, eax
0x1800443e7  call    WPP_SF_d
0x1800443ec  jmp     loc_1800444F1
0x1800443f1  call    AfdRegisterSwitch
0x1800443f6  mov     ebx, eax
0x1800443f8  test    eax, eax
0x1800443fa  js      loc_1800444B6
0x180044400  mov     rax, cs:SockAsyncQueuePort
0x180044407  lea     r8, [rsp+58h+FileInformation]; FileInformation
0x18004440c  mov     rcx, cs:SockSanHelperHandle; FileHandle
0x180044413  lea     rdx, [rsp+58h+IoStatusBlock]; IoStatusBlock
0x180044418  mov     [rsp+58h+FileInformation], rax
0x18004441d  xorps   xmm0, xmm0
0x180044420  lea     rax, SockSanCompletion
0x180044427  mov     dword ptr [rsp+58h+InitialState], 1Eh; FileInformationClass
0x18004442f  mov     r9d, 10h; Length
0x180044435  mov     [rsp+58h+var_20], rax
0x18004443a  movups  xmmword ptr [rsp+58h+IoStatusBlock], xmm0
0x18004443f  call    cs:__imp_NtSetInformationFile
0x180044446  nop     dword ptr [rax+rax+00h]
0x18004444b  mov     ebx, eax
0x18004444d  test    eax, eax
0x18004444f  js      short loc_180044474
0x180044451  test    byte ptr cs:xmmword_180063D60, 2
0x180044458  jz      short loc_180044470
0x18004445a  mov     edx, 1Eh
0x18004445f  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x180044466  mov     ecx, 401h
0x18004446b  call    WPP_SF_
0x180044470  xor     eax, eax
0x180044472  jmp     short loc_1800444F3
0x180044474  test    byte ptr cs:xmmword_180063D60, 2
0x18004447b  jz      short loc_180044496
0x18004447d  mov     edx, 1Fh
0x180044482  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x180044489  mov     ecx, 401h
0x18004448e  mov     r9d, eax
0x180044491  call    WPP_SF_d
0x180044496  mov     rcx, cs:SockSanHelperHandle; Handle
0x18004449d  call    cs:__imp_NtClose
0x1800444a4  nop     dword ptr [rax+rax+00h]
0x1800444a9  mov     cs:SockSanHelperHandle, 0
0x1800444b4  jmp     short loc_1800444D3
0x1800444b6  test    byte ptr cs:xmmword_180063D60, 2
0x1800444bd  jz      short loc_1800444D3
0x1800444bf  mov     edx, 20h ; ' '
0x1800444c4  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x1800444cb  mov     r9d, eax
0x1800444ce  call    WPP_SF_l
0x1800444d3  mov     rcx, cs:SockSanEvent; Handle
0x1800444da  call    cs:__imp_NtClose
0x1800444e1  nop     dword ptr [rax+rax+00h]
0x1800444e6  mov     cs:SockSanEvent, 0
0x1800444f1  mov     eax, ebx
0x1800444f3  add     rsp, 50h
0x1800444f7  pop     rbx
0x1800444f8  retn
```
