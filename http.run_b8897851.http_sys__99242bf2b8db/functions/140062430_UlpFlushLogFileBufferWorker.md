# UlpFlushLogFileBufferWorker

- ea: `0x140062430`
- end: `0x140062576`
- name: `UlpFlushLogFileBufferWorker`
- size: `326`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140037080`
- `0x140062430`
- `0x140062624`
- `0x14006295c`
- `0x1400b0234`
- `0x1401c4444`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ZwWaitForSingleObject` at `0x140177abc`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140177abc`
- `ntoskrnl!ZwWriteFile` at `0x1400624e9`
- `ntoskrnl!ZwWriteFile` at `0x140177a9e`
- `ntoskrnl!ZwWriteFile` at `0x1400624e9`
- `ntoskrnl!ZwWriteFile` at `0x140177a9e`
- `ntoskrnl!ZwCreateEvent` at `0x140177a53`
- `ntoskrnl!ZwCreateEvent` at `0x140177a53`
- `ntoskrnl!ZwClose` at `0x140177ad3`
- `ntoskrnl!ZwClose` at `0x140177ad3`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14006247f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14006247f`

## pseudocode

```c
__int64 __fastcall UlpFlushLogFileBufferWorker(__int64 *a1)
{
  __int64 v1; // rdi
  __int64 v2; // r15
  __int64 Current; // r14
  __int64 CurrentServerSilo; // rax
  NTSTATUS v6; // eax
  NTSTATUS v7; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+B0h] [rbp+30h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+B8h] [rbp+38h] BYREF

  v1 = a1[1];
  v2 = *a1;
  EventHandle = 0;
  ByteOffset.QuadPart = -1;
  memset(&ObjectAttributes, 0, 44);
  Current = UxPodGetCurrent();
  if ( *((_BYTE *)a1 + 16) )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
    if ( v7 >= 0 )
    {
      v7 = ZwWriteFile(
             *(HANDLE *)(v2 + 64),
             EventHandle,
             0,
             0,
             (PIO_STATUS_BLOCK)(v1 + 24),
             *(PVOID *)(v1 + 64),
             *(_DWORD *)(v1 + 56),
             &ByteOffset,
             0);
      if ( v7 == 259 )
      {
        ZwWaitForSingleObject(EventHandle, 0, 0);
        v7 = *(_DWORD *)(a1[1] + 24);
      }
      ZwClose(EventHandle);
    }
    UlFreeLogFileBuffer(v1);
  }
  else
  {
    CurrentServerSilo = PsGetCurrentServerSilo();
    *(_QWORD *)(v1 + 48) = CurrentServerSilo;
    UxPodReferenceSilo(CurrentServerSilo, 1280076885, 36);
    *(_BYTE *)(v1 + 40) = 1;
    _InterlockedIncrement((volatile signed __int32 *)(Current + 2976));
    v6 = ZwWriteFile(
           *(HANDLE *)(v2 + 64),
           0,
           UlpBufferFlushAPC,
           (PVOID)v1,
           (PIO_STATUS_BLOCK)(v1 + 24),
           *(PVOID *)(v1 + 64),
           *(_DWORD *)(v1 + 56),
           &ByteOffset,
           0);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( (BYTE9(xmmword_1401A2C90) & 8) != 0 )
        WPP_SF_d(779, 21, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids, (unsigned int)v6);
      UlpLogBufferWriteCompletion(v1, Current);
    }
  }
  if ( (BYTE9(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_qqdd(1291, 22, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids, v2, v1, *((unsigned __int8 *)a1 + 16), v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140062430  mov     [rsp-28h+arg_10], rbx
0x140062435  push    rbp
0x140062436  push    rsi
0x140062437  push    rdi
0x140062438  push    r14
0x14006243a  push    r15
0x14006243c  mov     rbp, rsp
0x14006243f  sub     rsp, 80h
0x140062446  mov     rdi, [rcx+8]
0x14006244a  xorps   xmm0, xmm0
0x14006244d  mov     r15, [rcx]
0x140062450  xor     eax, eax
0x140062452  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140062456  mov     rsi, rcx
0x140062459  mov     [rbp+EventHandle], rax
0x14006245d  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140062461  mov     qword ptr [rbp+arg_8], 0FFFFFFFFFFFFFFFFh
0x140062469  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14006246d  call    UxPodGetCurrent
0x140062472  cmp     byte ptr [rsi+10h], 0
0x140062476  mov     r14, rax
0x140062479  jnz     loc_140177A18
0x14006247f  call    cs:__imp_PsGetCurrentServerSilo
0x140062486  nop     dword ptr [rax+rax+00h]
0x14006248b  mov     edx, 4C4C6C55h
0x140062490  mov     r8d, 24h ; '$'
0x140062496  mov     rcx, rax
0x140062499  mov     [rdi+30h], rax
0x14006249d  call    UxPodReferenceSilo
0x1400624a2  mov     byte ptr [rdi+28h], 1
0x1400624a6  lock inc dword ptr [r14+0BA0h]
0x1400624ae  mov     [rsp+80h+Key], 0; Key
0x1400624b7  lea     rax, [rbp+arg_8]
0x1400624bb  mov     [rsp+80h+ByteOffset], rax; ByteOffset
0x1400624c0  lea     rcx, [rdi+18h]
0x1400624c4  mov     eax, [rdi+38h]
0x1400624c7  lea     r8, UlpBufferFlushAPC; ApcRoutine
0x1400624ce  mov     [rsp+80h+Length], eax; Length
0x1400624d2  mov     r9, rdi; ApcContext
0x1400624d5  mov     rax, [rdi+40h]
0x1400624d9  xor     edx, edx; Event
0x1400624db  mov     [rsp+80h+Buffer], rax; Buffer
0x1400624e0  mov     [rsp+80h+IoStatusBlock], rcx; IoStatusBlock
0x1400624e5  mov     rcx, [r15+40h]; FileHandle
0x1400624e9  call    cs:__imp_ZwWriteFile
0x1400624f0  nop     dword ptr [rax+rax+00h]
0x1400624f5  mov     ebx, eax
0x1400624f7  test    eax, eax
0x1400624f9  js      short loc_14006251E
0x1400624fb  test    byte ptr cs:xmmword_1401A2CA0+9, 8
0x140062502  jnz     short loc_14006254A
0x140062504  mov     eax, ebx
0x140062506  mov     rbx, [rsp+80h+arg_10]
0x14006250e  add     rsp, 80h
0x140062515  pop     r15
0x140062517  pop     r14
0x140062519  pop     rdi
0x14006251a  pop     rsi
0x14006251b  pop     rbp
0x14006251c  retn
0x14006251e  test    byte ptr cs:xmmword_1401A2C90+9, 8
0x140062525  jz      loc_140177AED
0x14006252b  mov     edx, 15h
0x140062530  lea     r8, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids
0x140062537  mov     ecx, 30Bh
0x14006253c  mov     r9d, eax
0x14006253f  call    WPP_SF_d
0x140062544  nop
0x140062545  jmp     loc_140177AED
0x14006254a  movzx   eax, byte ptr [rsi+10h]
0x14006254e  lea     r8, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids
0x140062555  mov     [rsp+80h+Length], ebx
0x140062559  mov     edx, 16h
0x14006255e  mov     dword ptr [rsp+80h+Buffer], eax
0x140062562  mov     ecx, 50Bh
0x140062567  mov     r9, r15
0x14006256a  mov     [rsp+80h+IoStatusBlock], rdi
0x14006256f  call    WPP_SF_qqdd
0x140062574  jmp     short loc_140062504
0x140177a18  xorps   xmm0, xmm0
0x140177a1b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140177a22  xor     r9d, r9d; EventType
0x140177a25  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140177a2d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140177a31  mov     [rbp+ObjectAttributes.Attributes], 200h
0x140177a38  mov     edx, 1F0003h; DesiredAccess
0x140177a3d  mov     [rbp+ObjectAttributes.ObjectName], 0
0x140177a45  lea     rcx, [rbp+EventHandle]; EventHandle
0x140177a49  mov     byte ptr [rsp+80h+IoStatusBlock], 0; InitialState
0x140177a4e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140177a53  call    cs:__imp_ZwCreateEvent
0x140177a5a  nop     dword ptr [rax+rax+00h]
0x140177a5f  mov     ebx, eax
0x140177a61  test    eax, eax
0x140177a63  js      short loc_140177ADF
0x140177a65  mov     rdx, [rbp+EventHandle]; Event
0x140177a69  lea     rax, [rbp+arg_8]
0x140177a6d  mov     [rsp+80h+Key], 0; Key
0x140177a76  lea     rcx, [rdi+18h]
0x140177a7a  mov     [rsp+80h+ByteOffset], rax; ByteOffset
0x140177a7f  xor     r9d, r9d; ApcContext
0x140177a82  mov     eax, [rdi+38h]
0x140177a85  xor     r8d, r8d; ApcRoutine
0x140177a88  mov     [rsp+80h+Length], eax; Length
0x140177a8c  mov     rax, [rdi+40h]
0x140177a90  mov     [rsp+80h+Buffer], rax; Buffer
0x140177a95  mov     [rsp+80h+IoStatusBlock], rcx; IoStatusBlock
0x140177a9a  mov     rcx, [r15+40h]; FileHandle
0x140177a9e  call    cs:__imp_ZwWriteFile
0x140177aa5  nop     dword ptr [rax+rax+00h]
0x140177aaa  mov     ebx, eax
0x140177aac  cmp     eax, 103h
0x140177ab1  jnz     short loc_140177ACF
0x140177ab3  mov     rcx, [rbp+EventHandle]; Handle
0x140177ab7  xor     r8d, r8d; Timeout
0x140177aba  xor     edx, edx; Alertable
0x140177abc  call    cs:__imp_ZwWaitForSingleObject
0x140177ac3  nop     dword ptr [rax+rax+00h]
0x140177ac8  mov     rax, [rsi+8]
0x140177acc  mov     ebx, [rax+18h]
0x140177acf  mov     rcx, [rbp+EventHandle]; Handle
0x140177ad3  call    cs:__imp_ZwClose
0x140177ada  nop     dword ptr [rax+rax+00h]
0x140177adf  mov     rcx, rdi
0x140177ae2  call    UlFreeLogFileBuffer
0x140177ae7  nop
0x140177ae8  jmp     loc_1400624FB
0x140177aed  mov     rdx, r14
0x140177af0  mov     rcx, rdi
0x140177af3  call    UlpLogBufferWriteCompletion
0x140177af8  nop
0x140177af9  jmp     loc_1400624FB
```
