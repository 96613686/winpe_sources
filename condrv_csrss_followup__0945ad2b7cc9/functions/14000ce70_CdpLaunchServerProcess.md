# CdpLaunchServerProcess

- ea: `0x14000ce70`
- end: `0x14000d295`
- name: `CdpLaunchServerProcess`
- size: `1061`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x14000c870`

## callees

- `0x140001010`
- `0x1400014d0`
- `0x1400080c4`
- `0x140008128`
- `0x1400081a0`
- `0x1400081e8`
- `0x14000ce70`
- `0x14000d6b0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000d241`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d241`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d259`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d259`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000cee5`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000cf21`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000cf89`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000cee5`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000cf21`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000cf89`
- `ntoskrnl!_stricmp` at `0x14000d0b9`
- `ntoskrnl!_stricmp` at `0x14000d0b9`
- `ntoskrnl!PsAcquireProcessExitSynchronization` at `0x14000d037`
- `ntoskrnl!PsAcquireProcessExitSynchronization` at `0x14000d037`
- `ntoskrnl!KeStackAttachProcess` at `0x14000d058`
- `ntoskrnl!KeStackAttachProcess` at `0x14000d058`
- `ntoskrnl!PsGetProcessPeb` at `0x14000d129`
- `ntoskrnl!PsGetProcessPeb` at `0x14000d129`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000d1ea`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000d1ea`
- `ntoskrnl!PsReleaseProcessExitSynchronization` at `0x14000d1fe`
- `ntoskrnl!PsReleaseProcessExitSynchronization` at `0x14000d1fe`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000d014`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000d014`
- `ntoskrnl!IoFileObjectType` at `0x14000d07b`
- `ntoskrnl!ObCloseHandle` at `0x14000d1b9`
- `ntoskrnl!ObCloseHandle` at `0x14000d1d1`
- `ntoskrnl!ObCloseHandle` at `0x14000d22d`
- `ntoskrnl!ObCloseHandle` at `0x14000d1b9`
- `ntoskrnl!ObCloseHandle` at `0x14000d1d1`
- `ntoskrnl!ObCloseHandle` at `0x14000d22d`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14000cef4`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14000cef4`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14000cf30`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14000cf30`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000cf64`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000cfba`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000d099`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000cf64`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000cfba`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000d099`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14000cf75`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14000cf75`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d11a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d11a`
- `ntoskrnl!PsResumeProcess` at `0x14000d192`
- `ntoskrnl!PsResumeProcess` at `0x14000d192`
- `ntoskrnl!ZwTerminateProcess` at `0x14000d21a`
- `ntoskrnl!ZwTerminateProcess` at `0x14000d21a`
- `ntoskrnl!__imp_PsCaptureUserProcessParameters` at `0x14000cf0b`
- `ntoskrnl!__imp_PsCaptureUserProcessParameters` at `0x14000cf0b`

## pseudocode

```c
__int64 __fastcall CdpLaunchServerProcess(__int64 a1, char a2)
{
  struct _KPROCESS *Flink; // r12
  char v5; // r15
  __int64 CurrentProcess; // rax
  const char *ProcessImageFileName; // r14
  int v8; // eax
  int Process; // ebx
  struct _KPROCESS *v10; // rax
  PACCESS_TOKEN v11; // rdi
  void *v12; // rax
  int v13; // eax
  int *v14; // r8
  __int64 ProcessPeb; // rax
  __int64 ULong64FromUser; // r14
  void *v17; // rdi
  __int64 v18; // rsi
  PVOID Owner; // rcx
  POBJECT_TYPE ObjectType; // [rsp+20h] [rbp-C8h]
  _FAST_MUTEX FastMutex; // [rsp+48h] [rbp-A0h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+80h] [rbp-68h] BYREF

  memset(&ApcState, 0, sizeof(ApcState));
  FastMutex.Event.Header.WaitListHead.Blink = 0;
  if ( a2 != 1 )
    return 3221225659LL;
  memset(&FastMutex, 0, 32);
  Flink = 0;
  v5 = 0;
  CurrentProcess = PsGetCurrentProcess();
  ProcessImageFileName = (const char *)PsGetProcessImageFileName(CurrentProcess);
  PsCaptureUserProcessParameters(&FastMutex);
  Process = v8;
  if ( v8 >= 0 )
  {
    v10 = (struct _KPROCESS *)PsGetCurrentProcess();
    v11 = PsReferencePrimaryToken(v10);
    Process = ObOpenObjectByPointer(v11, 0x200u, 0, 0xBu, 0, 0, (PHANDLE)&FastMutex.Contention);
    PsDereferencePrimaryToken(v11);
    if ( Process >= 0 )
    {
      v12 = (void *)PsGetCurrentProcess();
      Process = ObOpenObjectByPointer(v12, 0x200u, 0, 0x1000u, 0, 0, (PHANDLE)&FastMutex.Event);
      if ( Process >= 0 )
      {
        Process = CdpCreateProcess((PEX_RUNDOWN_REF)&FastMutex.Owner);
        if ( Process >= 0 )
        {
          FastMutex.Event.Header.WaitListHead.Flink = 0;
          Process = ObReferenceObjectByHandle(
                      FastMutex.Owner,
                      0,
                      0,
                      0,
                      (PVOID *)&FastMutex.Event.Header.WaitListHead.Flink,
                      0);
          if ( Process >= 0 )
          {
            Flink = (struct _KPROCESS *)FastMutex.Event.Header.WaitListHead.Flink;
            *(_QWORD *)&FastMutex.OldIrql = FastMutex.Event.Header.WaitListHead.Flink;
            Process = PsAcquireProcessExitSynchronization(FastMutex.Event.Header.WaitListHead.Flink);
            if ( Process >= 0 )
            {
              KeStackAttachProcess(Flink, &ApcState);
              v5 = 1;
              Process = ObOpenObjectByPointer(
                          *(PVOID *)(a1 + 32),
                          0,
                          0,
                          0x10000000u,
                          (POBJECT_TYPE)IoFileObjectType,
                          1,
                          (PHANDLE)&FastMutex.Event.Header.WaitListHead.Blink);
              if ( Process >= 0 )
              {
                v13 = _stricmp(ProcessImageFileName, "ntvdm.exe");
                v14 = (int *)L" -ForceV1";
                if ( v13 )
                  v14 = &dword_1400046FC;
                LODWORD(ObjectType) = FastMutex.Event.Header.WaitListHead.Blink;
                Process = RtlStringCbPrintfW(
                            *(NTSTRSAFE_PWSTR *)(*(_QWORD *)&FastMutex.Count + 120LL),
                            *(unsigned __int16 *)(*(_QWORD *)&FastMutex.Count + 114LL),
                            L"%wZ 0x%x%s",
                            *(_QWORD *)&FastMutex.Count + 96LL,
                            ObjectType,
                            v14);
                if ( Process >= 0 )
                {
                  RtlInitUnicodeString(
                    (PUNICODE_STRING)(*(_QWORD *)&FastMutex.Count + 112LL),
                    *(PCWSTR *)(*(_QWORD *)&FastMutex.Count + 120LL));
                  ProcessPeb = PsGetProcessPeb(Flink);
                  ULong64FromUser = RtlReadULong64FromUser(ProcessPeb + 32);
                  v17 = (void *)RtlReadULong64FromUser(ULong64FromUser + 120);
                  RtlCopyToUser(
                    v17,
                    *(void **)(*(_QWORD *)&FastMutex.Count + 120LL),
                    *(unsigned __int16 *)(*(_QWORD *)&FastMutex.Count + 114LL));
                  *(_QWORD *)(*(_QWORD *)&FastMutex.Count + 120LL) = v17;
                  v18 = *(_QWORD *)(*(_QWORD *)&FastMutex.Count + 120LL);
                  RtlWriteULongToUser(ULong64FromUser + 112, *(unsigned int *)(*(_QWORD *)&FastMutex.Count + 112LL));
                  RtlWriteULong64ToUser(ULong64FromUser + 120, v18);
                  PsResumeProcess(Flink);
                }
              }
            }
          }
        }
      }
    }
  }
  if ( *(_QWORD *)&FastMutex.Contention )
    ObCloseHandle(*(HANDLE *)&FastMutex.Contention, 0);
  if ( *(_QWORD *)&FastMutex.Event.Header.Lock )
    ObCloseHandle(*(HANDLE *)&FastMutex.Event.Header.Lock, 0);
  if ( v5 )
  {
    KeUnstackDetachProcess(&ApcState);
    PsReleaseProcessExitSynchronization(Flink);
  }
  Owner = FastMutex.Owner;
  if ( FastMutex.Owner )
  {
    if ( Process < 0 )
    {
      ZwTerminateProcess(FastMutex.Owner, Process);
      Owner = FastMutex.Owner;
    }
    ObCloseHandle(Owner, 0);
  }
  if ( Flink )
    ObfDereferenceObject(Flink);
  if ( *(_QWORD *)&FastMutex.Count )
    ExFreePoolWithTag(*(PVOID *)&FastMutex.Count, 0);
  return (unsigned int)Process;
}

```

## disassembly

```asm
0x14000ce70  mov     r11, rsp
0x14000ce73  mov     [r11+10h], rbx
0x14000ce77  mov     [r11+20h], rsi
0x14000ce7b  push    rdi
0x14000ce7c  push    r12
0x14000ce7e  push    r13
0x14000ce80  push    r14
0x14000ce82  push    r15
0x14000ce84  sub     rsp, 0C0h
0x14000ce8b  mov     rax, cs:__security_cookie
0x14000ce92  xor     rax, rsp
0x14000ce95  mov     [rsp+0E8h+var_38], rax
0x14000ce9d  mov     rbx, r8
0x14000cea0  mov     rsi, rcx
0x14000cea3  xorps   xmm0, xmm0
0x14000cea6  movups  xmmword ptr [r11-68h], xmm0
0x14000ceab  movups  xmmword ptr [r11-58h], xmm0
0x14000ceb0  movups  xmmword ptr [r11-48h], xmm0
0x14000ceb5  xor     r13d, r13d
0x14000ceb8  mov     [r11-78h], r13
0x14000cebc  cmp     dl, 1
0x14000cebf  jz      short loc_14000CECB
0x14000cec1  mov     eax, 0C00000BBh
0x14000cec6  jmp     loc_14000D267
0x14000cecb  mov     qword ptr [rsp+0E8h+FastMutex.Count], r13
0x14000ced0  mov     qword ptr [rsp+0E8h+FastMutex.Event.Header], r13
0x14000ced5  mov     r12, r13
0x14000ced8  mov     [rsp+0E8h+FastMutex.Owner], r13
0x14000cedd  mov     qword ptr [rsp+0E8h+FastMutex.Contention], r13
0x14000cee2  xor     r15b, r15b
0x14000cee5  call    cs:__imp_PsGetCurrentProcess
0x14000ceec  nop     dword ptr [rax+rax+00h]
0x14000cef1  mov     rcx, rax
0x14000cef4  call    cs:__imp_PsGetProcessImageFileName
0x14000cefb  nop     dword ptr [rax+rax+00h]
0x14000cf00  mov     r14, rax
0x14000cf03  mov     rdx, rbx
0x14000cf06  lea     rcx, [rsp+0E8h+FastMutex]; FastMutex
0x14000cf0b  call    cs:__imp_PsCaptureUserProcessParameters
0x14000cf12  nop     dword ptr [rax+rax+00h]
0x14000cf17  mov     ebx, eax
0x14000cf19  test    eax, eax
0x14000cf1b  js      loc_14000D1AD
0x14000cf21  call    cs:__imp_PsGetCurrentProcess
0x14000cf28  nop     dword ptr [rax+rax+00h]
0x14000cf2d  mov     rcx, rax; Process
0x14000cf30  call    cs:__imp_PsReferencePrimaryToken
0x14000cf37  nop     dword ptr [rax+rax+00h]
0x14000cf3c  mov     rdi, rax
0x14000cf3f  lea     rax, [rsp+0E8h+FastMutex.Contention]
0x14000cf44  mov     [rsp+0E8h+Handle], rax; Handle
0x14000cf49  mov     [rsp+0E8h+AccessMode], r12b; AccessMode
0x14000cf4e  mov     [rsp+0E8h+ObjectType], r13; ObjectType
0x14000cf53  mov     r9d, 0Bh; DesiredAccess
0x14000cf59  xor     r8d, r8d; PassedAccessState
0x14000cf5c  mov     edx, 200h; HandleAttributes
0x14000cf61  mov     rcx, rdi; Object
0x14000cf64  call    cs:__imp_ObOpenObjectByPointer
0x14000cf6b  nop     dword ptr [rax+rax+00h]
0x14000cf70  mov     ebx, eax
0x14000cf72  mov     rcx, rdi; PrimaryToken
0x14000cf75  call    cs:__imp_PsDereferencePrimaryToken
0x14000cf7c  nop     dword ptr [rax+rax+00h]
0x14000cf81  test    ebx, ebx
0x14000cf83  js      loc_14000D1AD
0x14000cf89  call    cs:__imp_PsGetCurrentProcess
0x14000cf90  nop     dword ptr [rax+rax+00h]
0x14000cf95  mov     rcx, rax; Object
0x14000cf98  lea     rax, [rsp+0E8h+FastMutex.Event]
0x14000cf9d  mov     [rsp+0E8h+Handle], rax; Handle
0x14000cfa2  mov     [rsp+0E8h+AccessMode], r12b; AccessMode
0x14000cfa7  mov     [rsp+0E8h+ObjectType], r13; ObjectType
0x14000cfac  mov     r9d, 1000h; DesiredAccess
0x14000cfb2  xor     r8d, r8d; PassedAccessState
0x14000cfb5  mov     edx, 200h; HandleAttributes
0x14000cfba  call    cs:__imp_ObOpenObjectByPointer
0x14000cfc1  nop     dword ptr [rax+rax+00h]
0x14000cfc6  mov     ebx, eax
0x14000cfc8  test    eax, eax
0x14000cfca  js      loc_14000D1AD
0x14000cfd0  mov     r9, qword ptr [rsp+0E8h+FastMutex.Count]
0x14000cfd5  mov     r8, qword ptr [rsp+0E8h+FastMutex.Event.Header]
0x14000cfda  mov     rdx, qword ptr [rsp+0E8h+FastMutex.Contention]
0x14000cfdf  lea     rcx, [rsp+0E8h+FastMutex.Owner]; RunRef
0x14000cfe4  call    CdpCreateProcess
0x14000cfe9  mov     ebx, eax
0x14000cfeb  test    eax, eax
0x14000cfed  js      loc_14000D1AD
0x14000cff3  mov     [rsp+0E8h+FastMutex.Event.Header.WaitListHead.Flink], r13
0x14000cff8  mov     qword ptr [rsp+0E8h+AccessMode], r13; HandleInformation
0x14000cffd  lea     rax, [rsp+0E8h+FastMutex.Event.Header.WaitListHead]
0x14000d002  mov     [rsp+0E8h+ObjectType], rax; Object
0x14000d007  xor     r9d, r9d; AccessMode
0x14000d00a  xor     r8d, r8d; ObjectType
0x14000d00d  xor     edx, edx; DesiredAccess
0x14000d00f  mov     rcx, [rsp+0E8h+FastMutex.Owner]; Handle
0x14000d014  call    cs:__imp_ObReferenceObjectByHandle
0x14000d01b  nop     dword ptr [rax+rax+00h]
0x14000d020  mov     ebx, eax
0x14000d022  test    eax, eax
0x14000d024  js      loc_14000D1AD
0x14000d02a  mov     r12, [rsp+0E8h+FastMutex.Event.Header.WaitListHead.Flink]
0x14000d02f  mov     qword ptr [rsp+0E8h+FastMutex.OldIrql], r12
0x14000d034  mov     rcx, r12
0x14000d037  call    cs:__imp_PsAcquireProcessExitSynchronization
0x14000d03e  nop     dword ptr [rax+rax+00h]
0x14000d043  mov     ebx, eax
0x14000d045  test    eax, eax
0x14000d047  js      loc_14000D1AD
0x14000d04d  lea     rdx, [rsp+0E8h+ApcState]; ApcState
0x14000d055  mov     rcx, r12; PROCESS
0x14000d058  call    cs:__imp_KeStackAttachProcess
0x14000d05f  nop     dword ptr [rax+rax+00h]
0x14000d064  mov     r15b, 1
0x14000d067  mov     [rsp+0E8h+var_A8], r15b
0x14000d06c  lea     rax, [rsp+0E8h+FastMutex.Event.Header.WaitListHead.Blink]
0x14000d071  mov     [rsp+0E8h+Handle], rax; Handle
0x14000d076  mov     [rsp+0E8h+AccessMode], r15b; AccessMode
0x14000d07b  mov     rax, cs:__imp_IoFileObjectType
0x14000d082  mov     rdx, [rax]
0x14000d085  mov     [rsp+0E8h+ObjectType], rdx; ObjectType
0x14000d08a  mov     r9d, 10000000h; DesiredAccess
0x14000d090  xor     r8d, r8d; PassedAccessState
0x14000d093  xor     edx, edx; HandleAttributes
0x14000d095  mov     rcx, [rsi+20h]; Object
0x14000d099  call    cs:__imp_ObOpenObjectByPointer
0x14000d0a0  nop     dword ptr [rax+rax+00h]
0x14000d0a5  mov     ebx, eax
0x14000d0a7  test    eax, eax
0x14000d0a9  js      loc_14000D1AD
0x14000d0af  lea     rdx, Str2; "ntvdm.exe"
0x14000d0b6  mov     rcx, r14; Str1
0x14000d0b9  call    cs:__imp__stricmp
0x14000d0c0  nop     dword ptr [rax+rax+00h]
0x14000d0c5  lea     rcx, dword_1400046FC
0x14000d0cc  lea     r8, aForcev1; " -ForceV1"
0x14000d0d3  test    eax, eax
0x14000d0d5  cmovnz  r8, rcx
0x14000d0d9  mov     eax, dword ptr [rsp+0E8h+FastMutex.Event.Header.WaitListHead.Blink]
0x14000d0dd  mov     rcx, qword ptr [rsp+0E8h+FastMutex.Count]
0x14000d0e2  lea     r9, [rcx+60h]
0x14000d0e6  movzx   edx, word ptr [rcx+72h]; cbDest
0x14000d0ea  mov     qword ptr [rsp+0E8h+AccessMode], r8
0x14000d0ef  mov     dword ptr [rsp+0E8h+ObjectType], eax
0x14000d0f3  lea     r8, aWz0xXS; "%wZ 0x%x%s"
0x14000d0fa  mov     rcx, [rcx+78h]; pszDest
0x14000d0fe  call    RtlStringCbPrintfW
0x14000d103  mov     ebx, eax
0x14000d105  test    eax, eax
0x14000d107  js      loc_14000D1AD
0x14000d10d  mov     rdx, qword ptr [rsp+0E8h+FastMutex.Count]
0x14000d112  lea     rcx, [rdx+70h]; DestinationString
0x14000d116  mov     rdx, [rdx+78h]; SourceString
0x14000d11a  call    cs:__imp_RtlInitUnicodeString
0x14000d121  nop     dword ptr [rax+rax+00h]
0x14000d126  mov     rcx, r12
0x14000d129  call    cs:__imp_PsGetProcessPeb
0x14000d130  nop     dword ptr [rax+rax+00h]
0x14000d135  nop
0x14000d136  lea     rcx, [rax+20h]
0x14000d13a  call    RtlReadULong64FromUser
0x14000d13f  mov     r14, rax
0x14000d142  lea     rcx, [rax+78h]
0x14000d146  call    RtlReadULong64FromUser
0x14000d14b  mov     rdi, rax
0x14000d14e  mov     rdx, qword ptr [rsp+0E8h+FastMutex.Count]
0x14000d153  movzx   r8d, word ptr [rdx+72h]; Size
0x14000d158  mov     rdx, [rdx+78h]; Src
0x14000d15c  mov     rcx, rax; void *
0x14000d15f  call    RtlCopyToUser
0x14000d164  mov     rcx, qword ptr [rsp+0E8h+FastMutex.Count]
0x14000d169  mov     [rcx+78h], rdi
0x14000d16d  mov     rdx, qword ptr [rsp+0E8h+FastMutex.Count]
0x14000d172  mov     rsi, [rdx+78h]
0x14000d176  mov     edx, [rdx+70h]
0x14000d179  lea     rcx, [r14+70h]
0x14000d17d  call    RtlWriteULongToUser
0x14000d182  lea     rcx, [r14+78h]
0x14000d186  mov     rdx, rsi
0x14000d189  call    RtlWriteULong64ToUser
0x14000d18e  nop
0x14000d18f  mov     rcx, r12
0x14000d192  call    cs:__imp_PsResumeProcess
0x14000d199  nop     dword ptr [rax+rax+00h]
0x14000d19e  jmp     short loc_14000D1AD
0x14000d1a0  mov     ebx, eax
0x14000d1a2  movzx   r15d, [rsp+0E8h+var_A8]
0x14000d1a8  mov     r12, qword ptr [rsp+0E8h+FastMutex.OldIrql]
0x14000d1ad  mov     rcx, qword ptr [rsp+0E8h+FastMutex.Contention]; Handle
0x14000d1b2  test    rcx, rcx
0x14000d1b5  jz      short loc_14000D1C5
0x14000d1b7  xor     edx, edx; PreviousMode
0x14000d1b9  call    cs:__imp_ObCloseHandle
0x14000d1c0  nop     dword ptr [rax+rax+00h]
0x14000d1c5  mov     rcx, qword ptr [rsp+0E8h+FastMutex.Event.Header]; Handle
0x14000d1ca  test    rcx, rcx
0x14000d1cd  jz      short loc_14000D1DD
0x14000d1cf  xor     edx, edx; PreviousMode
0x14000d1d1  call    cs:__imp_ObCloseHandle
0x14000d1d8  nop     dword ptr [rax+rax+00h]
0x14000d1dd  test    r15b, r15b
0x14000d1e0  jz      short loc_14000D20A
0x14000d1e2  lea     rcx, [rsp+0E8h+ApcState]; ApcState
0x14000d1ea  call    cs:__imp_KeUnstackDetachProcess
0x14000d1f1  nop     dword ptr [rax+rax+00h]
0x14000d1f6  test    r15b, r15b
0x14000d1f9  jz      short loc_14000D20A
0x14000d1fb  mov     rcx, r12
0x14000d1fe  call    cs:__imp_PsReleaseProcessExitSynchronization
0x14000d205  nop     dword ptr [rax+rax+00h]
0x14000d20a  mov     rcx, [rsp+0E8h+FastMutex.Owner]; ProcessHandle
0x14000d20f  test    rcx, rcx
0x14000d212  jz      short loc_14000D239
0x14000d214  test    ebx, ebx
0x14000d216  jns     short loc_14000D22B
0x14000d218  mov     edx, ebx; ExitStatus
0x14000d21a  call    cs:__imp_ZwTerminateProcess
0x14000d221  nop     dword ptr [rax+rax+00h]
0x14000d226  mov     rcx, [rsp+0E8h+FastMutex.Owner]; Handle
0x14000d22b  xor     edx, edx; PreviousMode
0x14000d22d  call    cs:__imp_ObCloseHandle
0x14000d234  nop     dword ptr [rax+rax+00h]
0x14000d239  test    r12, r12
0x14000d23c  jz      short loc_14000D24D
0x14000d23e  mov     rcx, r12; Object
0x14000d241  call    cs:__imp_ObfDereferenceObject
0x14000d248  nop     dword ptr [rax+rax+00h]
0x14000d24d  mov     rcx, qword ptr [rsp+0E8h+FastMutex.Count]; P
0x14000d252  test    rcx, rcx
0x14000d255  jz      short loc_14000D265
0x14000d257  xor     edx, edx; Tag
0x14000d259  call    cs:__imp_ExFreePoolWithTag
0x14000d260  nop     dword ptr [rax+rax+00h]
0x14000d265  mov     eax, ebx
0x14000d267  mov     rcx, [rsp+0E8h+var_38]
0x14000d26f  xor     rcx, rsp; StackCookie
0x14000d272  call    __security_check_cookie
0x14000d277  lea     r11, [rsp+0E8h+var_28]
0x14000d27f  mov     rbx, [r11+38h]
0x14000d283  mov     rsi, [r11+48h]
0x14000d287  mov     rsp, r11
0x14000d28a  pop     r15
0x14000d28c  pop     r14
0x14000d28e  pop     r13
0x14000d290  pop     r12
0x14000d292  pop     rdi
0x14000d293  retn
```
