# DepFSBugCheckNotEnoughSpace

- ea: `0x1800011a4`
- end: `0x1800012e1`
- name: `DepFSBugCheckNotEnoughSpace`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180008010`

## callees

- `0x1800011a4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1800012b2`
- `ntoskrnl!ZwClose` at `0x1800012b2`
- `ntoskrnl!ZwCreateEvent` at `0x180001282`
- `ntoskrnl!ZwCreateEvent` at `0x180001282`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1800012a2`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1800012a2`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18000120b`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18000120b`
- `ntoskrnl!KeBugCheckEx` at `0x1800012d4`
- `ntoskrnl!KeBugCheckEx` at `0x1800012d4`
- `ntoskrnl!KeDelayExecutionThread` at `0x180001261`
- `ntoskrnl!KeDelayExecutionThread` at `0x180001261`

## string_xrefs

- `0x1800011bc`: `\BaseNamedObjects\BootShellComplete`

## pseudocode

```c
void __fastcall __noreturn DepFSBugCheckNotEnoughSpace(int a1)
{
  ULONG_PTR v1; // rbx
  NTSTATUS v2; // eax
  void *EventHandle; // [rsp+30h] [rbp-29h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-21h] BYREF
  _LARGE_INTEGER Interval; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v6[2]; // [rsp+48h] [rbp-11h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-1h] BYREF
  __int128 SystemInformation; // [rsp+88h] [rbp+2Fh] BYREF
  __int128 v9; // [rsp+98h] [rbp+3Fh]

  v1 = a1;
  ReturnLength = 0;
  v6[1] = L"\\BaseNamedObjects\\BootShellComplete";
  EventHandle = 0;
  v6[0] = 4718662;
  Interval.QuadPart = 0;
  memset(&ObjectAttributes, 0, 44);
  SystemInformation = 0;
  v9 = 0;
  if ( ZwQuerySystemInformation(SystemBootEnvironmentInformation, &SystemInformation, 0x20u, &ReturnLength) >= 0
    && (BYTE8(v9) & 1) != 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v6;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    while ( 1 )
    {
      v2 = ZwCreateEvent(&EventHandle, 0x100000u, &ObjectAttributes, NotificationEvent, 0);
      if ( v2 != -1073741766 )
        break;
      Interval.QuadPart = -500000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
    if ( v2 >= 0 )
    {
      ZwWaitForSingleObject(EventHandle, 0, 0);
      ZwClose(EventHandle);
    }
  }
  KeBugCheckEx(0x136u, 0, v1, 0, 0);
}

```

## disassembly

```asm
0x1800011a4  mov     [rsp-8+arg_8], rbx
0x1800011a9  push    rbp
0x1800011aa  lea     rbp, [rsp-57h]
0x1800011af  sub     rsp, 0B0h
0x1800011b6  xorps   xmm0, xmm0
0x1800011b9  movsxd  rbx, ecx
0x1800011bc  lea     rax, aBasenamedobjec; "\\BaseNamedObjects\\BootShellComplete"
0x1800011c3  mov     [rbp+57h+ReturnLength], 0
0x1800011ca  mov     [rbp+57h+var_60], rax
0x1800011ce  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x1800011d2  xor     eax, eax
0x1800011d4  mov     [rbp+57h+EventHandle], 0
0x1800011dc  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800011e0  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x1800011e4  mov     [rbp+57h+var_68], 480046h
0x1800011ec  mov     qword ptr [rbp+57h+Interval], 0
0x1800011f4  lea     r8d, [rax+20h]; SystemInformationLength
0x1800011f8  lea     ecx, [rax+5Ah]; SystemInformationClass
0x1800011fb  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800011ff  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180001203  movups  [rbp+57h+SystemInformation], xmm0
0x180001207  movups  [rbp+57h+var_18], xmm0
0x18000120b  call    cs:__imp_ZwQuerySystemInformation
0x180001212  nop     dword ptr [rax+rax+00h]
0x180001217  test    eax, eax
0x180001219  js      loc_1800012BE
0x18000121f  test    byte ptr [rbp+57h+var_18+8], 1
0x180001223  jz      loc_1800012BE
0x180001229  lea     rax, [rbp+57h+var_68]
0x18000122d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180001234  xorps   xmm0, xmm0
0x180001237  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000123b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180001240  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180001248  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x18000124f  jmp     short loc_18000126D
0x180001251  lea     r8, [rbp+57h+Interval]; Interval
0x180001255  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFFF85EE0h
0x18000125d  xor     edx, edx; Alertable
0x18000125f  xor     ecx, ecx; WaitMode
0x180001261  call    cs:__imp_KeDelayExecutionThread
0x180001268  nop     dword ptr [rax+rax+00h]
0x18000126d  xor     r9d, r9d; EventType
0x180001270  mov     [rsp+0B0h+InitialState], 0; InitialState
0x180001275  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180001279  mov     edx, 100000h; DesiredAccess
0x18000127e  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x180001282  call    cs:__imp_ZwCreateEvent
0x180001289  nop     dword ptr [rax+rax+00h]
0x18000128e  cmp     eax, 0C000003Ah
0x180001293  jz      short loc_180001251
0x180001295  test    eax, eax
0x180001297  js      short loc_1800012BE
0x180001299  mov     rcx, [rbp+57h+EventHandle]; Handle
0x18000129d  xor     r8d, r8d; Timeout
0x1800012a0  xor     edx, edx; Alertable
0x1800012a2  call    cs:__imp_ZwWaitForSingleObject
0x1800012a9  nop     dword ptr [rax+rax+00h]
0x1800012ae  mov     rcx, [rbp+57h+EventHandle]; Handle
0x1800012b2  call    cs:__imp_ZwClose
0x1800012b9  nop     dword ptr [rax+rax+00h]
0x1800012be  mov     r8, rbx; BugCheckParameter2
0x1800012c1  mov     qword ptr [rsp+0B0h+InitialState], 0; BugCheckParameter4
0x1800012ca  xor     r9d, r9d; BugCheckParameter3
0x1800012cd  xor     edx, edx; BugCheckParameter1
0x1800012cf  mov     ecx, 136h; BugCheckCode
0x1800012d4  call    cs:__imp_KeBugCheckEx
```
