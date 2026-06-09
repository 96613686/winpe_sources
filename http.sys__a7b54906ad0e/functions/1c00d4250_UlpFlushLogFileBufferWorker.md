# UlpFlushLogFileBufferWorker

- ea: `0x1c00d4250`
- end: `0x1c00d440a`
- name: `UlpFlushLogFileBufferWorker`
- size: `442`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x1c00020e8`
- `0x1c0016fcc`
- `0x1c008f21c`
- `0x1c0090b30`
- `0x1c00a2b80`
- `0x1c00d4250`

## import_xrefs

- `ntoskrnl!ZwCreateEvent` at `0x1c00d4374`
- `ntoskrnl!ZwCreateEvent` at `0x1c00d4374`
- `ntoskrnl!ZwWriteFile` at `0x1c00d42f7`
- `ntoskrnl!ZwWriteFile` at `0x1c00d43bc`
- `ntoskrnl!ZwWriteFile` at `0x1c00d42f7`
- `ntoskrnl!ZwWriteFile` at `0x1c00d43bc`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1c00d43da`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1c00d43da`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1c00d429e`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1c00d429e`
- `ntoskrnl!ZwClose` at `0x1c00d43f1`
- `ntoskrnl!ZwClose` at `0x1c00d43f1`

## pseudocode

```c
__int64 __fastcall UlpFlushLogFileBufferWorker(__int64 *a1)
{
  __int64 v1; // rbx
  __int64 v3; // r15
  __int64 Current; // r14
  __int64 CurrentServerSilo; // rax
  NTSTATUS v6; // edi
  PVOID Buffer; // [rsp+28h] [rbp-58h]
  ULONG Length; // [rsp+30h] [rbp-50h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+B0h] [rbp+30h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+B8h] [rbp+38h] BYREF

  EventHandle = 0;
  v1 = a1[1];
  v3 = *a1;
  ByteOffset.QuadPart = -1;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Current = UxPodGetCurrent();
  if ( *((_BYTE *)a1 + 16) )
  {
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 512;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
    if ( v6 >= 0 )
    {
      v6 = ZwWriteFile(
             *(HANDLE *)(v3 + 64),
             EventHandle,
             0,
             0,
             (PIO_STATUS_BLOCK)(v1 + 24),
             *(PVOID *)(v1 + 64),
             *(_DWORD *)(v1 + 56),
             &ByteOffset,
             0);
      if ( v6 == 259 )
      {
        ZwWaitForSingleObject(EventHandle, 0, 0);
        v6 = *(_DWORD *)(a1[1] + 24);
      }
      ZwClose(EventHandle);
    }
  }
  else
  {
    CurrentServerSilo = PsGetCurrentServerSilo();
    *(_QWORD *)(v1 + 48) = CurrentServerSilo;
    UxPodReferenceSilo(CurrentServerSilo, 1280076885);
    Length = *(_DWORD *)(v1 + 56);
    Buffer = *(PVOID *)(v1 + 64);
    *(_BYTE *)(v1 + 40) = 1;
    v6 = ZwWriteFile(
           *(HANDLE *)(v3 + 64),
           0,
           UlpBufferFlushAPC,
           (PVOID)v1,
           (PIO_STATUS_BLOCK)(v1 + 24),
           Buffer,
           Length,
           &ByteOffset,
           0);
    if ( v6 >= 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(Current + 2776));
      goto LABEL_4;
    }
    if ( (*(_WORD *)&WPP_MAIN_CB.StackSize & 0x400) != 0 )
      WPP_SF_(21, WPP_07d3f8078d093d4b6da456c67947dc87_Traceguids);
  }
  UlFreeLogFileBuffer((PSLIST_ENTRY)v1);
LABEL_4:
  if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x400) != 0 )
    WPP_SF_qqdd(22, WPP_07d3f8078d093d4b6da456c67947dc87_Traceguids, v3, v1, *((unsigned __int8 *)a1 + 16), v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1c00d4250  mov     [rsp-28h+arg_10], rbx
0x1c00d4255  push    rbp
0x1c00d4256  push    rsi
0x1c00d4257  push    rdi
0x1c00d4258  push    r14
0x1c00d425a  push    r15
0x1c00d425c  mov     rbp, rsp
0x1c00d425f  sub     rsp, 80h
0x1c00d4266  and     [rbp+EventHandle], 0
0x1c00d426b  xorps   xmm0, xmm0
0x1c00d426e  mov     rbx, [rcx+8]
0x1c00d4272  mov     rsi, rcx
0x1c00d4275  mov     r15, [rcx]
0x1c00d4278  or      dword ptr [rbp+arg_8+4], 0FFFFFFFFh
0x1c00d427c  or      dword ptr [rbp+arg_8], 0FFFFFFFFh
0x1c00d4280  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1c00d4284  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1c00d4288  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1c00d428c  call    UxPodGetCurrent
0x1c00d4291  cmp     byte ptr [rsi+10h], 0
0x1c00d4295  mov     r14, rax
0x1c00d4298  jnz     loc_1C00D433F
0x1c00d429e  call    cs:__imp_PsGetCurrentServerSilo
0x1c00d42a5  nop     dword ptr [rax+rax+00h]
0x1c00d42aa  mov     rcx, rax
0x1c00d42ad  mov     [rbx+30h], rax
0x1c00d42b1  mov     edx, 4C4C6C55h
0x1c00d42b6  call    UxPodReferenceSilo
0x1c00d42bb  and     [rsp+80h+var_40], 0
0x1c00d42c1  lea     rax, [rbp+arg_8]
0x1c00d42c5  mov     [rsp+80h+ByteOffset], rax; ByteOffset
0x1c00d42ca  lea     rcx, [rbx+18h]
0x1c00d42ce  mov     eax, [rbx+38h]
0x1c00d42d1  lea     r8, UlpBufferFlushAPC; ApcRoutine
0x1c00d42d8  mov     [rsp+80h+Length], eax; Length
0x1c00d42dc  mov     r9, rbx; ApcContext
0x1c00d42df  mov     rax, [rbx+40h]
0x1c00d42e3  xor     edx, edx; Event
0x1c00d42e5  mov     [rsp+80h+Buffer], rax; Buffer
0x1c00d42ea  mov     [rsp+80h+IoStatusBlock], rcx; IoStatusBlock
0x1c00d42ef  mov     byte ptr [rbx+28h], 1
0x1c00d42f3  mov     rcx, [r15+40h]; FileHandle
0x1c00d42f7  call    cs:__imp_ZwWriteFile
0x1c00d42fe  nop     dword ptr [rax+rax+00h]
0x1c00d4303  mov     edi, eax
0x1c00d4305  test    eax, eax
0x1c00d4307  js      loc_1C00FC582
0x1c00d430d  lock inc dword ptr [r14+0AD8h]
0x1c00d4315  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 400h
0x1c00d431f  jnz     loc_1C00FC5A9
0x1c00d4325  mov     rbx, [rsp+80h+arg_10]
0x1c00d432d  mov     eax, edi
0x1c00d432f  add     rsp, 80h
0x1c00d4336  pop     r15
0x1c00d4338  pop     r14
0x1c00d433a  pop     rdi
0x1c00d433b  pop     rsi
0x1c00d433c  pop     rbp
0x1c00d433d  retn
0x1c00d433f  and     [rbp+ObjectAttributes.RootDirectory], 0
0x1c00d4344  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1c00d4348  and     [rbp+ObjectAttributes.ObjectName], 0
0x1c00d434d  lea     rcx, [rbp+EventHandle]; EventHandle
0x1c00d4351  xorps   xmm0, xmm0
0x1c00d4354  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1c00d435b  xor     r9d, r9d; EventType
0x1c00d435e  mov     [rbp+ObjectAttributes.Attributes], 200h
0x1c00d4365  mov     edx, 1F0003h; DesiredAccess
0x1c00d436a  mov     byte ptr [rsp+80h+IoStatusBlock], 0; InitialState
0x1c00d436f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1c00d4374  call    cs:__imp_ZwCreateEvent
0x1c00d437b  nop     dword ptr [rax+rax+00h]
0x1c00d4380  mov     edi, eax
0x1c00d4382  test    eax, eax
0x1c00d4384  js      short loc_1C00D43FD
0x1c00d4386  and     [rsp+80h+var_40], 0
0x1c00d438c  lea     rax, [rbp+arg_8]
0x1c00d4390  mov     rdx, [rbp+EventHandle]; Event
0x1c00d4394  lea     rcx, [rbx+18h]
0x1c00d4398  mov     [rsp+80h+ByteOffset], rax; ByteOffset
0x1c00d439d  xor     r9d, r9d; ApcContext
0x1c00d43a0  mov     eax, [rbx+38h]
0x1c00d43a3  xor     r8d, r8d; ApcRoutine
0x1c00d43a6  mov     [rsp+80h+Length], eax; Length
0x1c00d43aa  mov     rax, [rbx+40h]
0x1c00d43ae  mov     [rsp+80h+Buffer], rax; Buffer
0x1c00d43b3  mov     [rsp+80h+IoStatusBlock], rcx; IoStatusBlock
0x1c00d43b8  mov     rcx, [r15+40h]; FileHandle
0x1c00d43bc  call    cs:__imp_ZwWriteFile
0x1c00d43c3  nop     dword ptr [rax+rax+00h]
0x1c00d43c8  mov     edi, eax
0x1c00d43ca  cmp     eax, 103h
0x1c00d43cf  jnz     short loc_1C00D43ED
0x1c00d43d1  mov     rcx, [rbp+EventHandle]; Handle
0x1c00d43d5  xor     r8d, r8d; Timeout
0x1c00d43d8  xor     edx, edx; Alertable
0x1c00d43da  call    cs:__imp_ZwWaitForSingleObject
0x1c00d43e1  nop     dword ptr [rax+rax+00h]
0x1c00d43e6  mov     rax, [rsi+8]
0x1c00d43ea  mov     edi, [rax+18h]
0x1c00d43ed  mov     rcx, [rbp+EventHandle]; Handle
0x1c00d43f1  call    cs:__imp_ZwClose
0x1c00d43f8  nop     dword ptr [rax+rax+00h]
0x1c00d43fd  mov     rcx, rbx; ListEntry
0x1c00d4400  call    UlFreeLogFileBuffer
0x1c00d4405  jmp     loc_1C00D4315
0x1c00fc582  test    dword ptr cs:WPP_MAIN_CB.StackSize, 400h
0x1c00fc58c  jz      loc_1C00D43FD
0x1c00fc592  mov     ecx, 15h
0x1c00fc597  lea     rdx, WPP_07d3f8078d093d4b6da456c67947dc87_Traceguids
0x1c00fc59e  call    WPP_SF_
0x1c00fc5a3  nop
0x1c00fc5a4  jmp     loc_1C00D43FD
0x1c00fc5a9  movzx   eax, byte ptr [rsi+10h]
0x1c00fc5ad  lea     rdx, WPP_07d3f8078d093d4b6da456c67947dc87_Traceguids
0x1c00fc5b4  mov     ecx, 16h
0x1c00fc5b9  mov     dword ptr [rsp+80h+Buffer], edi
0x1c00fc5bd  mov     r9, rbx
0x1c00fc5c0  mov     dword ptr [rsp+80h+IoStatusBlock], eax
0x1c00fc5c4  mov     r8, r15
0x1c00fc5c7  call    WPP_SF_qqdd
0x1c00fc5cc  nop
0x1c00fc5cd  jmp     loc_1C00D4325
```
