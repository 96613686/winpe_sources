# SecSendFileSetInformationEvent

- ea: `0x14002792c`
- end: `0x140027c2a`
- name: `SecSendFileSetInformationEvent`
- size: `766`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, __int64, PCEVENT_DESCRIPTOR EventDescriptor, char, __int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140025298`
- `0x140025580`

## callees

- `0x140005f34`
- `0x1400065e4`
- `0x140006854`
- `0x140006b6c`
- `0x140006d3c`
- `0x14000885c`
- `0x14000888c`
- `0x140009b80`
- `0x140010473`
- `0x140011650`
- `0x140026630`
- `0x14002792c`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140027ad6`
- `ntoskrnl!PsGetThreadId` at `0x140027ad6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027bfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044691`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027bfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044691`

## pseudocode

```c
void __fastcall SecSendFileSetInformationEvent(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        PCEVENT_DESCRIPTOR EventDescriptor,
        int a7,
        __int64 a8,
        __int64 a9)
{
  wchar_t *v12; // r15
  __int64 RequestorProcess; // rax
  __int64 v14; // r8
  int ProcessContextWithAssertions; // eax
  struct _KTHREAD *Thread; // rbx
  int v17; // edi
  int Next; // r8d
  struct _SLIST_ENTRY *v19; // r10
  void *Sid; // r11
  __int64 v21; // r9
  __int64 v22; // rdx
  unsigned int v23; // eax
  char ThreadId; // [rsp+90h] [rbp-78h]
  PSLIST_ENTRY ListEntry; // [rsp+98h] [rbp-70h] BYREF
  PVOID v26; // [rsp+A0h] [rbp-68h] BYREF
  PVOID P; // [rsp+A8h] [rbp-60h] BYREF
  PVOID v28; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v29[4]; // [rsp+B8h] [rbp-50h] BYREF
  ULONG SessionId; // [rsp+BCh] [rbp-4Ch] BYREF

  SessionId = 0;
  v28 = 0;
  P = 0;
  ListEntry = 0;
  v26 = 0;
  v29[0] = 0;
  v12 = 0;
  if ( (xmmword_14001B740 & 0x80u) == 0LL && (xmmword_14001B740 & 0x200000000000LL) == 0 )
    return;
  RequestorProcess = SecFltGetRequestorProcess(CallbackData);
  LOBYTE(v14) = 1;
  ProcessContextWithAssertions = SecGetProcessContextWithAssertions(RequestorProcess, &ListEntry, v14);
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
      if ( a5 )
      {
        v29[0] = 0;
        v26 = a5;
LABEL_10:
        ProcessContextWithAssertions = SecUnicodeStringToString(a3, &P);
        if ( ProcessContextWithAssertions >= 0 )
        {
          ProcessContextWithAssertions = SecUnicodeStringToString(a4, &v28);
          if ( ProcessContextWithAssertions >= 0 )
          {
            v17 = 0;
            if ( (unsigned int)(a7 - 2) <= 1 )
              v17 = 128;
            if ( a8 )
              v12 = *(wchar_t **)(a8 + 8);
            ThreadId = (unsigned __int8)PsGetThreadId(Thread);
            Next = (int)ListEntry[2].Next;
            v19 = ListEntry[3].Next;
            Sid = *(void **)v26;
            v21 = *((_QWORD *)&ListEntry[2].Next + 1);
            v22 = _InterlockedIncrement64((volatile signed __int64 *)SecData + 42);
            v23 = EventWriteSetInformationFile(
                    EventDescriptor,
                    v22,
                    Next,
                    v21,
                    ThreadId,
                    Sid,
                    SessionId,
                    (wchar_t *)P,
                    (wchar_t *)v28,
                    -1,
                    (char)v19,
                    a7,
                    v12,
                    v17,
                    a9);
            SecIncrementEtwCounters(v23);
            ProcessContextWithAssertions = 0;
          }
        }
        goto LABEL_17;
      }
      ProcessContextWithAssertions = SecGetEffectiveTokenUser(Thread, (__int64)ListEntry, &v26, v29, 0);
      if ( ProcessContextWithAssertions >= 0 )
        goto LABEL_10;
    }
  }
LABEL_17:
  if ( ProcessContextWithAssertions < 0 )
    SecIncrementInternalErrorCounter();
  if ( P )
    SecFreePool(P, 0x74736353u);
  if ( v28 )
    SecFreePool(v28, 0x74736353u);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( v26 )
  {
    if ( v29[0] )
      ExFreePoolWithTag(v26, 0);
  }
}

```

## disassembly

```asm
0x14002792c  mov     r11, rsp
0x14002792f  push    rbx
0x140027930  push    rsi
0x140027931  push    rdi
0x140027932  push    r12
0x140027934  push    r13
0x140027936  push    r14
0x140027938  push    r15
0x14002793a  sub     rsp, 0D0h
0x140027941  mov     rax, cs:__security_cookie
0x140027948  xor     rax, rsp
0x14002794b  mov     [rsp+108h+var_48], rax
0x140027953  mov     r12, r9
0x140027956  mov     rsi, r8
0x140027959  mov     rbx, rcx
0x14002795c  mov     rdi, [rsp+108h+arg_20]
0x140027964  mov     r13, [rsp+108h+EventDescriptor]
0x14002796c  mov     r14, [rsp+108h+arg_38]
0x140027974  mov     rax, [rsp+108h+arg_40]
0x14002797c  mov     [rsp+108h+var_80], rax
0x140027984  xor     eax, eax
0x140027986  mov     [rsp+108h+var_88], eax
0x14002798d  mov     [r11-4Ch], eax
0x140027991  mov     [r11-58h], rax
0x140027995  mov     [r11-60h], rax
0x140027999  mov     [r11-70h], rax
0x14002799d  mov     [r11-68h], rax
0x1400279a1  mov     [r11-50h], al
0x1400279a5  mov     r15d, eax
0x1400279a8  mov     rcx, qword ptr cs:xmmword_14001B740
0x1400279af  mov     al, cl
0x1400279b1  shr     al, 7
0x1400279b4  test    al, 1
0x1400279b6  jnz     short loc_1400279C5
0x1400279b8  shr     rcx, 2Dh
0x1400279bc  test    cl, 1
0x1400279bf  jz      loc_140027C06
0x1400279c5  mov     rcx, rbx
0x1400279c8  call    SecFltGetRequestorProcess
0x1400279cd  mov     rcx, rax
0x1400279d0  mov     r8b, 1
0x1400279d3  lea     rdx, [rsp+108h+ListEntry]
0x1400279db  call    SecGetProcessContextWithAssertions
0x1400279e0  mov     [rsp+108h+var_88], eax
0x1400279e7  test    eax, eax
0x1400279e9  js      loc_140027B98
0x1400279ef  lfence
0x1400279f2  lea     rdx, [rsp+108h+SessionId]; SessionId
0x1400279fa  mov     rcx, rbx; CallbackData
0x1400279fd  call    FltGetRequestorSessionId_0
0x140027a02  mov     [rsp+108h+var_88], eax
0x140027a09  test    eax, eax
0x140027a0b  js      loc_140027B98
0x140027a11  lfence
0x140027a14  mov     rbx, [rbx+8]
0x140027a18  test    rbx, rbx
0x140027a1b  jnz     short loc_140027A26
0x140027a1d  mov     rbx, gs:188h
0x140027a26  test    rdi, rdi
0x140027a29  jz      short loc_140027A3D
0x140027a2b  mov     [rsp+108h+var_50], 0
0x140027a33  mov     [rsp+108h+var_68], rdi
0x140027a3b  jmp     short loc_140027A75
0x140027a3d  mov     qword ptr [rsp+108h+var_E8], 0; __int64
0x140027a46  lea     r9, [rsp+108h+var_50]
0x140027a4e  lea     r8, [rsp+108h+var_68]
0x140027a56  mov     rdx, [rsp+108h+ListEntry]
0x140027a5e  mov     rcx, rbx; Thread
0x140027a61  call    SecGetEffectiveTokenUser
0x140027a66  mov     [rsp+108h+var_88], eax
0x140027a6d  test    eax, eax
0x140027a6f  js      loc_140027B98
0x140027a75  lea     rdx, [rsp+108h+P]
0x140027a7d  mov     rcx, rsi
0x140027a80  call    SecUnicodeStringToString
0x140027a85  mov     [rsp+108h+var_88], eax
0x140027a8c  test    eax, eax
0x140027a8e  js      loc_140027B98
0x140027a94  lea     rdx, [rsp+108h+var_58]
0x140027a9c  mov     rcx, r12
0x140027a9f  call    SecUnicodeStringToString
0x140027aa4  mov     [rsp+108h+var_88], eax
0x140027aab  test    eax, eax
0x140027aad  js      loc_140027B98
0x140027ab3  mov     esi, dword ptr [rsp+108h+arg_30]
0x140027aba  lea     eax, [rsi-2]
0x140027abd  xor     edi, edi
0x140027abf  mov     ecx, 80h
0x140027ac4  cmp     eax, 1
0x140027ac7  cmovbe  edi, ecx
0x140027aca  test    r14, r14
0x140027acd  jz      short loc_140027AD3
0x140027acf  mov     r15, [r14+8]
0x140027ad3  mov     rcx, rbx; Thread
0x140027ad6  call    cs:__imp_PsGetThreadId
0x140027add  nop     dword ptr [rax+rax+00h]
0x140027ae2  mov     rbx, rax
0x140027ae5  mov     [rsp+108h+var_78], rax
0x140027aed  mov     rdx, [rsp+108h+ListEntry]
0x140027af5  mov     r8d, [rdx+20h]
0x140027af9  mov     r10, [rdx+30h]
0x140027afd  mov     rcx, [rsp+108h+var_68]
0x140027b05  mov     r11, [rcx]
0x140027b08  mov     r9, [rdx+28h]
0x140027b0c  mov     rcx, cs:SecData
0x140027b13  mov     edx, 1
0x140027b18  lock xadd [rcx+150h], rdx
0x140027b21  inc     rdx
0x140027b24  mov     rax, [rsp+108h+var_80]
0x140027b2c  mov     [rsp+108h+var_98], rax; __int64
0x140027b31  mov     [rsp+108h+var_A0], edi; int
0x140027b35  mov     [rsp+108h+var_A8], r15; wchar_t *
0x140027b3a  mov     dword ptr [rsp+108h+var_B0], esi; char
0x140027b3e  mov     qword ptr [rsp+108h+var_B8], r10; char
0x140027b43  mov     dword ptr [rsp+108h+var_C0], 0FFFFFFFFh; char
0x140027b4b  mov     rax, [rsp+108h+var_58]
0x140027b53  mov     [rsp+108h+var_C8], rax; wchar_t *
0x140027b58  mov     rax, [rsp+108h+P]
0x140027b60  mov     [rsp+108h+Str], rax; Str
0x140027b65  mov     eax, [rsp+108h+SessionId]
0x140027b6c  mov     dword ptr [rsp+108h+var_D8], eax; char
0x140027b70  mov     [rsp+108h+Sid], r11; Sid
0x140027b75  mov     dword ptr [rsp+108h+var_E8], ebx; char
0x140027b79  mov     rcx, r13; EventDescriptor
0x140027b7c  call    EventWriteSetInformationFile
0x140027b81  mov     [rsp+108h+var_88], eax
0x140027b88  mov     ecx, eax
0x140027b8a  call    SecIncrementEtwCounters
0x140027b8f  xor     eax, eax
0x140027b91  mov     [rsp+108h+var_88], eax
0x140027b98  test    eax, eax
0x140027b9a  jns     short loc_140027BA1
0x140027b9c  call    SecIncrementInternalErrorCounter
0x140027ba1  mov     rcx, [rsp+108h+P]; P
0x140027ba9  test    rcx, rcx
0x140027bac  jz      short loc_140027BB8
0x140027bae  mov     edx, 74736353h; Tag
0x140027bb3  call    SecFreePool
0x140027bb8  mov     rcx, [rsp+108h+var_58]; P
0x140027bc0  test    rcx, rcx
0x140027bc3  jz      short loc_140027BCF
0x140027bc5  mov     edx, 74736353h; Tag
0x140027bca  call    SecFreePool
0x140027bcf  mov     rcx, [rsp+108h+ListEntry]; ListEntry
0x140027bd7  test    rcx, rcx
0x140027bda  jz      short loc_140027BE1
0x140027bdc  call    SecReleaseProcessContext
0x140027be1  mov     rcx, [rsp+108h+var_68]; P
0x140027be9  test    rcx, rcx
0x140027bec  jz      short loc_140027C06
0x140027bee  cmp     [rsp+108h+var_50], 0
0x140027bf6  jz      short loc_140027C06
0x140027bf8  xor     edx, edx; Tag
0x140027bfa  call    cs:__imp_ExFreePoolWithTag
0x140027c01  nop     dword ptr [rax+rax+00h]
0x140027c06  mov     rcx, [rsp+108h+var_48]
0x140027c0e  xor     rcx, rsp; StackCookie
0x140027c11  call    __security_check_cookie
0x140027c16  add     rsp, 0D0h
0x140027c1d  pop     r15
0x140027c1f  pop     r14
0x140027c21  pop     r13
0x140027c23  pop     r12
0x140027c25  pop     rdi
0x140027c26  pop     rsi
0x140027c27  pop     rbx
0x140027c28  retn
0x14004461f  push    rbp
0x140044621  sub     rsp, 80h
0x140044628  mov     rbp, rdx
0x14004462b  cmp     dword ptr [rbp+80h], 0
0x140044632  jge     short loc_14004463A
0x140044634  call    SecIncrementInternalErrorCounter
0x140044639  nop
0x14004463a  mov     rcx, [rbp+0A8h]; P
0x140044641  test    rcx, rcx
0x140044644  jz      short loc_140044651
0x140044646  mov     edx, 74736353h; Tag
0x14004464b  call    SecFreePool
0x140044650  nop
0x140044651  mov     rcx, [rbp+0B0h]; P
0x140044658  test    rcx, rcx
0x14004465b  jz      short loc_140044668
0x14004465d  mov     edx, 74736353h; Tag
0x140044662  call    SecFreePool
0x140044667  nop
0x140044668  mov     rcx, [rbp+98h]; ListEntry
0x14004466f  test    rcx, rcx
0x140044672  jz      short loc_14004467A
0x140044674  call    SecReleaseProcessContext
0x140044679  nop
0x14004467a  mov     rcx, [rbp+0A0h]; P
0x140044681  test    rcx, rcx
0x140044684  jz      short loc_14004469E
0x140044686  cmp     byte ptr [rbp+0B8h], 0
0x14004468d  jz      short loc_14004469E
0x14004468f  xor     edx, edx; Tag
0x140044691  call    cs:__imp_ExFreePoolWithTag
0x140044698  nop     dword ptr [rax+rax+00h]
0x14004469d  nop
0x14004469e  add     rsp, 80h
0x1400446a5  pop     rbp
0x1400446a6  retn
```
