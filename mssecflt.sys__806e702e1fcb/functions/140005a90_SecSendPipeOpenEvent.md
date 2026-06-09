# SecSendPipeOpenEvent

- ea: `0x140005a90`
- end: `0x140005d8d`
- name: `SecSendPipeOpenEvent`
- size: `765`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x140023e10`
- `0x140024da0`

## callees

- `0x140005418`
- `0x140005a90`
- `0x140005f34`
- `0x1400065e4`
- `0x140006854`
- `0x140006b6c`
- `0x140006d3c`
- `0x14000885c`
- `0x14000888c`
- `0x140009b80`
- `0x1400102ff`
- `0x140010347`
- `0x1400103e3`
- `0x140010467`
- `0x140010473`
- `0x140011650`
- `0x140029598`
- `0x140029658`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140005c49`
- `ntoskrnl!PsGetThreadId` at `0x140005c49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d49`

## pseudocode

```c
void __fastcall SecSendPipeOpenEvent(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  int v4; // r13d
  __int64 RequestorProcess; // rax
  __int64 v6; // r8
  struct _KTHREAD *Thread; // rdi
  char v8; // r15
  char v9; // r12
  int ThreadId; // eax
  int Information; // r11d
  int Next; // r14d
  struct _SLIST_ENTRY *v13; // r10
  int v14; // r9d
  void *v15; // rbx
  __int64 v16; // r8
  __int64 v17; // rcx
  unsigned int v18; // eax
  PSLIST_ENTRY ListEntry; // [rsp+80h] [rbp-59h] BYREF
  PFLT_CONTEXT Context; // [rsp+88h] [rbp-51h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+90h] [rbp-49h]
  PVOID P; // [rsp+98h] [rbp-41h] BYREF
  PVOID v23; // [rsp+A0h] [rbp-39h] BYREF
  PVOID v24; // [rsp+A8h] [rbp-31h] BYREF
  __int64 *v25; // [rsp+B0h] [rbp-29h]
  __int64 v26; // [rsp+B8h] [rbp-21h]
  _BYTE v27[4]; // [rsp+C0h] [rbp-19h] BYREF
  ULONG SessionId; // [rsp+C4h] [rbp-15h] BYREF
  _OWORD FileInformation[2]; // [rsp+C8h] [rbp-11h] BYREF
  __int64 v30; // [rsp+E8h] [rbp+Fh]

  v25 = &qword_14001B000;
  ListEntry = 0;
  FileNameInformation = 0;
  SessionId = 0;
  v4 = 0;
  P = 0;
  Context = 0;
  v23 = 0;
  v27[0] = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v30 = 0;
  v24 = 0;
  v26 = 0;
  if ( (xmmword_14001B740 & 0x80000) != 0 )
  {
    RequestorProcess = SecFltGetRequestorProcess(CallbackData);
    LOBYTE(v6) = 1;
    if ( (int)SecGetProcessContextWithAssertions(RequestorProcess, &ListEntry, v6) < 0 )
      goto LABEL_14;
    if ( FltGetInstanceContext_0(*(PFLT_INSTANCE *)(a2 + 24), &Context) < 0 )
      goto LABEL_14;
    _mm_lfence();
    if ( (int)SecQueryFileName(CallbackData) < 0 )
      goto LABEL_14;
    _mm_lfence();
    if ( FltGetRequestorSessionId_0(CallbackData, &SessionId) < 0 )
      goto LABEL_14;
    _mm_lfence();
    Thread = CallbackData->Thread;
    if ( !Thread )
      Thread = KeGetCurrentThread();
    if ( (int)SecGetEffectiveTokenUser(Thread, (__int64)ListEntry, &v23, v27, 0) < 0
      || (int)SecUnicodeStringToString(&FileNameInformation->Name, &P) < 0
      || FltQueryInformationFile_0(
           *(PFLT_INSTANCE *)(a2 + 24),
           *(PFILE_OBJECT *)(a2 + 32),
           FileInformation,
           0x28u,
           FilePipeLocalInformation,
           0) < 0 )
    {
LABEL_14:
      SecIncrementInternalErrorCounter();
    }
    else
    {
      _mm_lfence();
      v8 = ((v30 & 0x100000000LL) == 0) + 1;
      v9 = 2 - ((FileInformation[0] & 2) != 0);
      if ( (unsigned int)SecPopulateFileShareContext(*(PFLT_FILTER *)(a2 + 8)) - 2 <= 1 )
      {
        SecUnicodeStringToString(v25, &v24);
        v4 = 128;
      }
      ThreadId = (unsigned int)PsGetThreadId(Thread);
      Information = CallbackData->IoStatus.Information;
      Next = (int)ListEntry[2].Next;
      v13 = ListEntry[3].Next;
      v14 = *(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16);
      v15 = *(void **)v23;
      v16 = *((_QWORD *)&ListEntry[2].Next + 1);
      v17 = _InterlockedIncrement64((volatile signed __int64 *)SecData + 42);
      v18 = EventWriteOpenPipe(
              v17,
              Next,
              v16,
              ThreadId,
              v15,
              SessionId,
              (wchar_t *)P,
              v9,
              v8,
              v14,
              Information,
              (char)v13,
              (wchar_t *)v24,
              v4,
              v26);
      SecIncrementEtwCounters(v18);
    }
    if ( Context )
      FltReleaseContext_0(Context);
    if ( FileNameInformation )
      FltReleaseFileNameInformation_0(FileNameInformation);
    if ( P )
      SecFreePool(P, 0x74736353u);
    if ( ListEntry )
      SecReleaseProcessContext(ListEntry);
    if ( v23 && v27[0] )
      ExFreePoolWithTag(v23, 0);
    if ( v24 )
      SecFreePool(v24, 0x74736353u);
  }
}

```

## disassembly

```asm
0x140005a90  mov     [rsp-8+arg_10], rbx
0x140005a95  push    rbp
0x140005a96  push    rsi
0x140005a97  push    rdi
0x140005a98  push    r12
0x140005a9a  push    r13
0x140005a9c  push    r14
0x140005a9e  push    r15
0x140005aa0  lea     rbp, [rsp-27h]
0x140005aa5  sub     rsp, 100h
0x140005aac  mov     rax, cs:__security_cookie
0x140005ab3  xor     rax, rsp
0x140005ab6  mov     [rbp+57h+var_40], rax
0x140005aba  xor     r14d, r14d
0x140005abd  lea     rax, qword_14001B000
0x140005ac4  xorps   xmm0, xmm0
0x140005ac7  mov     [rbp+57h+var_80], rax
0x140005acb  xor     eax, eax
0x140005acd  mov     [rbp+57h+ListEntry], r14
0x140005ad1  test    qword ptr cs:xmmword_14001B740, 80000h
0x140005adc  mov     rsi, rdx
0x140005adf  mov     rbx, rcx
0x140005ae2  mov     [rbp+57h+FileNameInformation], r14
0x140005ae6  mov     [rbp+57h+SessionId], r14d
0x140005aea  mov     r13d, r14d
0x140005aed  mov     [rbp+57h+P], r14
0x140005af1  mov     [rbp+57h+Context], r14
0x140005af5  mov     [rbp+57h+var_90], r14
0x140005af9  mov     [rbp+57h+var_70], r14b
0x140005afd  movups  [rbp+57h+FileInformation], xmm0
0x140005b01  mov     [rbp+57h+var_48], rax
0x140005b05  movups  [rbp+57h+var_58], xmm0
0x140005b09  mov     [rbp+57h+var_88], r14
0x140005b0d  mov     [rbp+57h+var_78], r14
0x140005b11  jz      loc_140005D65
0x140005b17  call    SecFltGetRequestorProcess
0x140005b1c  mov     rcx, rax
0x140005b1f  lea     rdx, [rbp+57h+ListEntry]
0x140005b23  mov     r8b, 1
0x140005b26  call    SecGetProcessContextWithAssertions
0x140005b2b  test    eax, eax
0x140005b2d  js      loc_140005CF4
0x140005b33  mov     rcx, [rsi+18h]; Instance
0x140005b37  lea     rdx, [rbp+57h+Context]; Context
0x140005b3b  call    FltGetInstanceContext_0
0x140005b40  test    eax, eax
0x140005b42  js      loc_140005CF4
0x140005b48  lfence
0x140005b4b  mov     rdx, [rbp+57h+Context]
0x140005b4f  lea     r8, [rbp+57h+FileNameInformation]
0x140005b53  mov     rcx, rbx; CallbackData
0x140005b56  mov     edx, [rdx+2Ch]
0x140005b59  call    SecQueryFileName
0x140005b5e  test    eax, eax
0x140005b60  js      loc_140005CF4
0x140005b66  lfence
0x140005b69  lea     rdx, [rbp+57h+SessionId]; SessionId
0x140005b6d  mov     rcx, rbx; CallbackData
0x140005b70  call    FltGetRequestorSessionId_0
0x140005b75  test    eax, eax
0x140005b77  js      loc_140005CF4
0x140005b7d  lfence
0x140005b80  mov     rdi, [rbx+8]
0x140005b84  test    rdi, rdi
0x140005b87  jnz     short loc_140005B92
0x140005b89  mov     rdi, gs:188h
0x140005b92  mov     rdx, [rbp+57h+ListEntry]
0x140005b96  lea     r9, [rbp+57h+var_70]
0x140005b9a  lea     r8, [rbp+57h+var_90]
0x140005b9e  mov     qword ptr [rsp+130h+FileInformationClass], r14; __int64
0x140005ba3  mov     rcx, rdi; Thread
0x140005ba6  call    SecGetEffectiveTokenUser
0x140005bab  test    eax, eax
0x140005bad  js      loc_140005CF4
0x140005bb3  mov     rcx, [rbp+57h+FileNameInformation]
0x140005bb7  lea     rdx, [rbp+57h+P]
0x140005bbb  add     rcx, 8
0x140005bbf  call    SecUnicodeStringToString
0x140005bc4  test    eax, eax
0x140005bc6  js      loc_140005CF4
0x140005bcc  mov     rdx, [rsi+20h]; FileObject
0x140005bd0  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140005bd4  mov     rcx, [rsi+18h]; Instance
0x140005bd8  mov     r9d, 28h ; '('; Length
0x140005bde  mov     [rsp+130h+LengthReturned], r14; LengthReturned
0x140005be3  mov     [rsp+130h+FileInformationClass], 18h; FileInformationClass
0x140005beb  call    FltQueryInformationFile_0
0x140005bf0  test    eax, eax
0x140005bf2  js      loc_140005CF4
0x140005bf8  lfence
0x140005bfb  mov     r15d, dword ptr [rbp+57h+var_48+4]
0x140005bff  lea     r9, [rbp+57h+var_78]
0x140005c03  mov     eax, dword ptr [rbp+57h+FileInformation]
0x140005c06  lea     r8, [rbp+57h+var_80]
0x140005c0a  mov     rcx, [rsi+8]; Filter
0x140005c0e  not     r15d
0x140005c11  and     r15d, 1
0x140005c15  and     al, 2
0x140005c17  inc     r15d
0x140005c1a  mov     rdx, rbx
0x140005c1d  neg     al
0x140005c1f  sbb     r12d, r12d
0x140005c22  add     r12d, 2
0x140005c26  call    SecPopulateFileShareContext
0x140005c2b  add     eax, 0FFFFFFFEh
0x140005c2e  cmp     eax, 1
0x140005c31  ja      short loc_140005C46
0x140005c33  mov     rcx, [rbp+57h+var_80]
0x140005c37  lea     rdx, [rbp+57h+var_88]
0x140005c3b  call    SecUnicodeStringToString
0x140005c40  mov     r13d, 80h
0x140005c46  mov     rcx, rdi; Thread
0x140005c49  call    cs:__imp_PsGetThreadId
0x140005c50  nop     dword ptr [rax+rax+00h]
0x140005c55  mov     rcx, [rbx+10h]
0x140005c59  mov     edi, 1
0x140005c5e  mov     r8, [rbp+57h+ListEntry]
0x140005c62  mov     rsi, rax
0x140005c65  mov     r11d, [rbx+20h]
0x140005c69  mov     rdx, [rcx+18h]
0x140005c6d  mov     rcx, [rbp+57h+var_90]
0x140005c71  mov     r14d, [r8+20h]
0x140005c75  mov     r10, [r8+30h]
0x140005c79  mov     r9d, [rdx+10h]
0x140005c7d  mov     rbx, [rcx]
0x140005c80  mov     rcx, cs:SecData
0x140005c87  mov     r8, [r8+28h]; int
0x140005c8b  lock xadd [rcx+150h], rdi
0x140005c94  mov     rax, [rbp+57h+var_78]
0x140005c98  lea     rcx, [rdi+1]; int
0x140005c9c  mov     [rsp+130h+var_C0], rax; __int64
0x140005ca1  mov     edx, r14d; int
0x140005ca4  mov     rax, [rbp+57h+var_88]
0x140005ca8  mov     [rsp+130h+var_C8], r13d; int
0x140005cad  mov     [rsp+130h+var_D0], rax; wchar_t *
0x140005cb2  mov     rax, [rbp+57h+P]
0x140005cb6  mov     qword ptr [rsp+130h+var_D8], r10; char
0x140005cbb  mov     dword ptr [rsp+130h+var_E0], r11d; char
0x140005cc0  mov     dword ptr [rsp+130h+var_E8], r9d; char
0x140005cc5  mov     r9d, esi; int
0x140005cc8  mov     dword ptr [rsp+130h+var_F0], r15d; char
0x140005ccd  mov     dword ptr [rsp+130h+var_F8], r12d; char
0x140005cd2  mov     [rsp+130h+Str], rax; Str
0x140005cd7  mov     eax, [rbp+57h+SessionId]
0x140005cda  mov     dword ptr [rsp+130h+LengthReturned], eax; char
0x140005cde  mov     qword ptr [rsp+130h+FileInformationClass], rbx; Sid
0x140005ce3  call    EventWriteOpenPipe
0x140005ce8  mov     ecx, eax
0x140005cea  call    SecIncrementEtwCounters
0x140005cef  xor     r14d, r14d
0x140005cf2  jmp     short loc_140005CF9
0x140005cf4  call    SecIncrementInternalErrorCounter
0x140005cf9  mov     rcx, [rbp+57h+Context]; Context
0x140005cfd  test    rcx, rcx
0x140005d00  jz      short loc_140005D07
0x140005d02  call    FltReleaseContext_0
0x140005d07  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140005d0b  test    rcx, rcx
0x140005d0e  jz      short loc_140005D15
0x140005d10  call    FltReleaseFileNameInformation_0
0x140005d15  mov     rcx, [rbp+57h+P]; P
0x140005d19  mov     ebx, 74736353h
0x140005d1e  test    rcx, rcx
0x140005d21  jz      short loc_140005D2A
0x140005d23  mov     edx, ebx; Tag
0x140005d25  call    SecFreePool
0x140005d2a  mov     rcx, [rbp+57h+ListEntry]; ListEntry
0x140005d2e  test    rcx, rcx
0x140005d31  jz      short loc_140005D38
0x140005d33  call    SecReleaseProcessContext
0x140005d38  mov     rcx, [rbp+57h+var_90]; P
0x140005d3c  test    rcx, rcx
0x140005d3f  jz      short loc_140005D55
0x140005d41  cmp     [rbp+57h+var_70], r14b
0x140005d45  jz      short loc_140005D55
0x140005d47  xor     edx, edx; Tag
0x140005d49  call    cs:__imp_ExFreePoolWithTag
0x140005d50  nop     dword ptr [rax+rax+00h]
0x140005d55  mov     rcx, [rbp+57h+var_88]; P
0x140005d59  test    rcx, rcx
0x140005d5c  jz      short loc_140005D65
0x140005d5e  mov     edx, ebx; Tag
0x140005d60  call    SecFreePool
0x140005d65  mov     rcx, [rbp+57h+var_40]
0x140005d69  xor     rcx, rsp; StackCookie
0x140005d6c  call    __security_check_cookie
0x140005d71  mov     rbx, [rsp+130h+arg_10]
0x140005d79  add     rsp, 100h
0x140005d80  pop     r15
0x140005d82  pop     r14
0x140005d84  pop     r13
0x140005d86  pop     r12
0x140005d88  pop     rdi
0x140005d89  pop     rsi
0x140005d8a  pop     rbp
0x140005d8b  retn
```
