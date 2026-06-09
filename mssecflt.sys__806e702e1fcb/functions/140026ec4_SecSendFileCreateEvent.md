# SecSendFileCreateEvent

- ea: `0x140026ec4`
- end: `0x1400271ae`
- name: `SecSendFileCreateEvent`
- size: `746`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140023e10`

## callees

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
- `0x140010473`
- `0x140011650`
- `0x140025cf8`
- `0x140026ec4`
- `0x140029658`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140027052`
- `ntoskrnl!PsGetThreadId` at `0x140027052`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002717e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044599`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002717e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044599`

## pseudocode

```c
void __fastcall SecSendFileCreateEvent(PFLT_CALLBACK_DATA CallbackData, __int64 a2, int a3, __int64 a4, __int64 a5)
{
  int v9; // esi
  __int64 RequestorProcess; // rax
  __int64 v11; // r8
  int ProcessContextWithAssertions; // eax
  struct _KTHREAD *Thread; // rdi
  int Next; // r14d
  wchar_t *v15; // r9
  struct _SLIST_ENTRY *v16; // r10
  int Information; // r11d
  void *Sid; // rbx
  __int64 v19; // r8
  signed __int64 v20; // rdi
  unsigned int v21; // eax
  int ThreadId; // [rsp+80h] [rbp-78h]
  PSLIST_ENTRY ListEntry; // [rsp+88h] [rbp-70h] BYREF
  PFLT_CONTEXT Context; // [rsp+90h] [rbp-68h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+98h] [rbp-60h]
  PVOID P; // [rsp+A0h] [rbp-58h] BYREF
  PVOID v27; // [rsp+A8h] [rbp-50h] BYREF
  _BYTE v28[4]; // [rsp+B0h] [rbp-48h] BYREF
  ULONG SessionId; // [rsp+B4h] [rbp-44h] BYREF

  v9 = 0;
  SessionId = 0;
  FileNameInformation = 0;
  P = 0;
  Context = 0;
  ListEntry = 0;
  v27 = 0;
  v28[0] = 0;
  if ( (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 0x400000) == 0 && (xmmword_14001B740 & 0x40) != 0 )
  {
    RequestorProcess = SecFltGetRequestorProcess(CallbackData);
    LOBYTE(v11) = 1;
    ProcessContextWithAssertions = SecGetProcessContextWithAssertions(RequestorProcess, &ListEntry, v11);
    if ( ProcessContextWithAssertions >= 0 )
    {
      ProcessContextWithAssertions = FltGetInstanceContext_0(*(PFLT_INSTANCE *)(a2 + 24), &Context);
      if ( ProcessContextWithAssertions >= 0 )
      {
        _mm_lfence();
        ProcessContextWithAssertions = SecQueryFileName(CallbackData);
        if ( ProcessContextWithAssertions >= 0 )
        {
          _mm_lfence();
          ProcessContextWithAssertions = FltGetRequestorSessionId_0(CallbackData, &SessionId);
          if ( ProcessContextWithAssertions >= 0 )
          {
            _mm_lfence();
            Thread = CallbackData->Thread;
            if ( !Thread )
              Thread = KeGetCurrentThread();
            ProcessContextWithAssertions = SecGetEffectiveTokenUser(Thread, (__int64)ListEntry, &v27, v28, 0);
            if ( ProcessContextWithAssertions >= 0 )
            {
              ProcessContextWithAssertions = SecUnicodeStringToString(&FileNameInformation->Name, &P);
              if ( ProcessContextWithAssertions >= 0 )
              {
                _mm_lfence();
                if ( (unsigned int)(a3 - 2) <= 1 )
                  v9 = 128;
                ThreadId = (unsigned int)PsGetThreadId(Thread);
                Next = (int)ListEntry[2].Next;
                v15 = *(wchar_t **)(a4 + 8);
                v16 = ListEntry[3].Next;
                Information = CallbackData->IoStatus.Information;
                Sid = *(void **)v27;
                v19 = *((_QWORD *)&ListEntry[2].Next + 1);
                v20 = _InterlockedExchangeAdd64((volatile signed __int64 *)SecData + 42, 1u);
                v21 = EventWriteCreateFile(
                        v20 + 1,
                        Next,
                        v19,
                        ThreadId,
                        Sid,
                        SessionId,
                        (wchar_t *)P,
                        -1,
                        Information,
                        (char)v16,
                        a3,
                        v15,
                        v9,
                        a5);
                SecIncrementEtwCounters(v21);
                ProcessContextWithAssertions = 0;
              }
            }
          }
        }
      }
    }
    if ( ProcessContextWithAssertions < 0 )
      SecIncrementInternalErrorCounter();
    if ( Context )
      FltReleaseContext_0(Context);
    if ( FileNameInformation )
      FltReleaseFileNameInformation_0(FileNameInformation);
    if ( P )
      SecFreePool(P, 0x74736353u);
    if ( ListEntry )
      SecReleaseProcessContext(ListEntry);
    if ( v27 )
    {
      if ( v28[0] )
        ExFreePoolWithTag(v27, 0);
    }
  }
}

```

## disassembly

```asm
0x140026ec4  mov     r11, rsp
0x140026ec7  push    rbx
0x140026ec8  push    rsi
0x140026ec9  push    rdi
0x140026eca  push    r12
0x140026ecc  push    r13
0x140026ece  push    r14
0x140026ed0  push    r15
0x140026ed2  sub     rsp, 0C0h
0x140026ed9  mov     rax, cs:__security_cookie
0x140026ee0  xor     rax, rsp
0x140026ee3  mov     [rsp+0F8h+var_40], rax
0x140026eeb  mov     r12, r9
0x140026eee  mov     r13d, r8d
0x140026ef1  mov     rdi, rdx
0x140026ef4  mov     rbx, rcx
0x140026ef7  mov     rax, [rsp+0F8h+arg_20]
0x140026eff  mov     [rsp+0F8h+var_80], rax
0x140026f04  xor     esi, esi
0x140026f06  mov     [rsp+0F8h+var_88], esi
0x140026f0a  mov     [r11-44h], esi
0x140026f0e  mov     [r11-60h], rsi
0x140026f12  mov     [r11-58h], rsi
0x140026f16  mov     [r11-68h], rsi
0x140026f1a  mov     [r11-70h], rsi
0x140026f1e  mov     [r11-50h], rsi
0x140026f22  mov     [r11-48h], sil
0x140026f26  mov     rax, [rdx+20h]
0x140026f2a  test    dword ptr [rax+50h], 400000h
0x140026f31  jnz     loc_14002718A
0x140026f37  mov     al, byte ptr cs:xmmword_14001B740
0x140026f3d  shr     al, 6
0x140026f40  test    al, 1
0x140026f42  jz      loc_14002718A
0x140026f48  call    SecFltGetRequestorProcess
0x140026f4d  mov     rcx, rax
0x140026f50  mov     r8b, 1
0x140026f53  lea     rdx, [rsp+0F8h+ListEntry]
0x140026f5b  call    SecGetProcessContextWithAssertions
0x140026f60  mov     [rsp+0F8h+var_88], eax
0x140026f64  test    eax, eax
0x140026f66  js      loc_14002710F
0x140026f6c  lea     rdx, [rsp+0F8h+Context]; Context
0x140026f74  mov     rcx, [rdi+18h]; Instance
0x140026f78  call    FltGetInstanceContext_0
0x140026f7d  mov     [rsp+0F8h+var_88], eax
0x140026f81  test    eax, eax
0x140026f83  js      loc_14002710F
0x140026f89  lfence
0x140026f8c  lea     r8, [rsp+0F8h+FileNameInformation]
0x140026f94  mov     rdx, [rsp+0F8h+Context]
0x140026f9c  mov     edx, [rdx+2Ch]
0x140026f9f  mov     rcx, rbx; CallbackData
0x140026fa2  call    SecQueryFileName
0x140026fa7  mov     [rsp+0F8h+var_88], eax
0x140026fab  test    eax, eax
0x140026fad  js      loc_14002710F
0x140026fb3  lfence
0x140026fb6  lea     rdx, [rsp+0F8h+SessionId]; SessionId
0x140026fbe  mov     rcx, rbx; CallbackData
0x140026fc1  call    FltGetRequestorSessionId_0
0x140026fc6  mov     [rsp+0F8h+var_88], eax
0x140026fca  test    eax, eax
0x140026fcc  js      loc_14002710F
0x140026fd2  lfence
0x140026fd5  mov     rdi, [rbx+8]
0x140026fd9  test    rdi, rdi
0x140026fdc  jnz     short loc_140026FE7
0x140026fde  mov     rdi, gs:188h
0x140026fe7  mov     [rsp+0F8h+Sid], rsi; __int64
0x140026fec  lea     r9, [rsp+0F8h+var_48]
0x140026ff4  lea     r8, [rsp+0F8h+var_50]
0x140026ffc  mov     rdx, [rsp+0F8h+ListEntry]
0x140027004  mov     rcx, rdi; Thread
0x140027007  call    SecGetEffectiveTokenUser
0x14002700c  mov     [rsp+0F8h+var_88], eax
0x140027010  test    eax, eax
0x140027012  js      loc_14002710F
0x140027018  mov     rcx, [rsp+0F8h+FileNameInformation]
0x140027020  add     rcx, 8
0x140027024  lea     rdx, [rsp+0F8h+P]
0x14002702c  call    SecUnicodeStringToString
0x140027031  mov     [rsp+0F8h+var_88], eax
0x140027035  test    eax, eax
0x140027037  js      loc_14002710F
0x14002703d  lfence
0x140027040  lea     eax, [r13-2]
0x140027044  mov     ecx, 80h
0x140027049  cmp     eax, 1
0x14002704c  cmovbe  esi, ecx
0x14002704f  mov     rcx, rdi; Thread
0x140027052  call    cs:__imp_PsGetThreadId
0x140027059  nop     dword ptr [rax+rax+00h]
0x14002705e  mov     r15, rax
0x140027061  mov     [rsp+0F8h+var_78], rax
0x140027069  mov     rdx, [rsp+0F8h+ListEntry]
0x140027071  mov     r14d, [rdx+20h]
0x140027075  mov     r9, [r12+8]
0x14002707a  mov     r10, [rdx+30h]
0x14002707e  mov     r11d, [rbx+20h]
0x140027082  mov     rcx, [rsp+0F8h+var_50]
0x14002708a  mov     rbx, [rcx]
0x14002708d  mov     r8, [rdx+28h]; int
0x140027091  mov     rcx, cs:SecData
0x140027098  mov     edi, 1
0x14002709d  lock xadd [rcx+150h], rdi
0x1400270a6  lea     rcx, [rdi+1]; int
0x1400270aa  mov     rax, [rsp+0F8h+var_80]
0x1400270af  mov     [rsp+0F8h+var_90], rax; __int64
0x1400270b4  mov     [rsp+0F8h+var_98], esi; int
0x1400270b8  mov     [rsp+0F8h+var_A0], r9; wchar_t *
0x1400270bd  mov     dword ptr [rsp+0F8h+var_A8], r13d; char
0x1400270c2  mov     qword ptr [rsp+0F8h+var_B0], r10; char
0x1400270c7  mov     dword ptr [rsp+0F8h+var_B8], r11d; char
0x1400270cc  mov     dword ptr [rsp+0F8h+var_C0], 0FFFFFFFFh; char
0x1400270d4  mov     rax, [rsp+0F8h+P]
0x1400270dc  mov     [rsp+0F8h+Str], rax; Str
0x1400270e1  mov     eax, [rsp+0F8h+SessionId]
0x1400270e8  mov     dword ptr [rsp+0F8h+var_D0], eax; char
0x1400270ec  mov     [rsp+0F8h+Sid], rbx; Sid
0x1400270f1  mov     r9d, r15d; int
0x1400270f4  mov     edx, r14d; int
0x1400270f7  call    EventWriteCreateFile
0x1400270fc  mov     [rsp+0F8h+var_88], eax
0x140027100  mov     ecx, eax
0x140027102  call    SecIncrementEtwCounters
0x140027107  xor     esi, esi
0x140027109  mov     eax, esi
0x14002710b  mov     [rsp+0F8h+var_88], eax
0x14002710f  test    eax, eax
0x140027111  jns     short loc_140027118
0x140027113  call    SecIncrementInternalErrorCounter
0x140027118  mov     rcx, [rsp+0F8h+Context]; Context
0x140027120  test    rcx, rcx
0x140027123  jz      short loc_14002712A
0x140027125  call    FltReleaseContext_0
0x14002712a  mov     rcx, [rsp+0F8h+FileNameInformation]; FileNameInformation
0x140027132  test    rcx, rcx
0x140027135  jz      short loc_14002713C
0x140027137  call    FltReleaseFileNameInformation_0
0x14002713c  mov     rcx, [rsp+0F8h+P]; P
0x140027144  test    rcx, rcx
0x140027147  jz      short loc_140027153
0x140027149  mov     edx, 74736353h; Tag
0x14002714e  call    SecFreePool
0x140027153  mov     rcx, [rsp+0F8h+ListEntry]; ListEntry
0x14002715b  test    rcx, rcx
0x14002715e  jz      short loc_140027165
0x140027160  call    SecReleaseProcessContext
0x140027165  mov     rcx, [rsp+0F8h+var_50]; P
0x14002716d  test    rcx, rcx
0x140027170  jz      short loc_14002718A
0x140027172  cmp     [rsp+0F8h+var_48], sil
0x14002717a  jz      short loc_14002718A
0x14002717c  xor     edx, edx; Tag
0x14002717e  call    cs:__imp_ExFreePoolWithTag
0x140027185  nop     dword ptr [rax+rax+00h]
0x14002718a  mov     rcx, [rsp+0F8h+var_40]
0x140027192  xor     rcx, rsp; StackCookie
0x140027195  call    __security_check_cookie
0x14002719a  add     rsp, 0C0h
0x1400271a1  pop     r15
0x1400271a3  pop     r14
0x1400271a5  pop     r13
0x1400271a7  pop     r12
0x1400271a9  pop     rdi
0x1400271aa  pop     rsi
0x1400271ab  pop     rbx
0x1400271ac  retn
0x140044520  push    rbp
0x140044522  sub     rsp, 70h
0x140044526  mov     rbp, rdx
0x140044529  cmp     dword ptr [rbp+70h], 0
0x14004452d  jge     short loc_140044535
0x14004452f  call    SecIncrementInternalErrorCounter
0x140044534  nop
0x140044535  mov     rcx, [rbp+90h]; Context
0x14004453c  test    rcx, rcx
0x14004453f  jz      short loc_140044547
0x140044541  call    FltReleaseContext_0
0x140044546  nop
0x140044547  mov     rcx, [rbp+98h]; FileNameInformation
0x14004454e  test    rcx, rcx
0x140044551  jz      short loc_140044559
0x140044553  call    FltReleaseFileNameInformation_0
0x140044558  nop
0x140044559  mov     rcx, [rbp+0A0h]; P
0x140044560  test    rcx, rcx
0x140044563  jz      short loc_140044570
0x140044565  mov     edx, 74736353h; Tag
0x14004456a  call    SecFreePool
0x14004456f  nop
0x140044570  mov     rcx, [rbp+88h]; ListEntry
0x140044577  test    rcx, rcx
0x14004457a  jz      short loc_140044582
0x14004457c  call    SecReleaseProcessContext
0x140044581  nop
0x140044582  mov     rcx, [rbp+0A8h]; P
0x140044589  test    rcx, rcx
0x14004458c  jz      short loc_1400445A6
0x14004458e  cmp     byte ptr [rbp+0B0h], 0
0x140044595  jz      short loc_1400445A6
0x140044597  xor     edx, edx; Tag
0x140044599  call    cs:__imp_ExFreePoolWithTag
0x1400445a0  nop     dword ptr [rax+rax+00h]
0x1400445a5  nop
0x1400445a6  add     rsp, 70h
0x1400445aa  pop     rbp
0x1400445ab  retn
```
