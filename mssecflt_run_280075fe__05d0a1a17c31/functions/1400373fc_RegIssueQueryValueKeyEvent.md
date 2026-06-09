# RegIssueQueryValueKeyEvent

- ea: `0x1400373fc`
- end: `0x1400376ea`
- name: `RegIssueQueryValueKeyEvent`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x140038c50`

## callees

- `0x1400061dc`
- `0x140006684`
- `0x140006854`
- `0x140006b6c`
- `0x140006d3c`
- `0x14000885c`
- `0x140010080`
- `0x1400108b8`
- `0x140011650`
- `0x140036098`
- `0x1400373fc`
- `0x14003a4c4`
- `0x14003a5b8`
- `0x14003a768`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14003751d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400375c6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003751d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400375c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400376b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400376b6`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037489`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003754a`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400375fe`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037489`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003754a`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400375fe`

## pseudocode

```c
void __fastcall RegIssueQueryValueKeyEvent(__int64 a1, __int64 a2)
{
  const UNICODE_STRING *v3; // rcx
  PEPROCESS CurrentProcess; // rax
  __int64 v6; // r8
  unsigned int *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  char v10; // r15
  volatile signed __int64 *v11; // rbx
  int v12; // r12d
  struct _SLIST_ENTRY *v13; // rdi
  void *Sid; // rsi
  __int64 v15; // r14
  PEPROCESS v16; // rax
  char v17; // al
  __int64 v18; // rdx
  int SessionsFilterMasksAndAsimovNamespaces; // eax
  __int64 i; // r12
  char CurrentThreadId; // r13
  char v22; // di
  volatile signed __int64 *v23; // rbx
  struct _SLIST_ENTRY *Next; // rsi
  void *v25; // r14
  __int64 v26; // r15
  ULONG64 v27; // r12
  PEPROCESS v28; // rax
  char ProcessSessionId_0; // al
  __int64 v30; // rdx
  __int64 v31; // [rsp+50h] [rbp-49h]
  char v32; // [rsp+50h] [rbp-49h]
  int v33; // [rsp+60h] [rbp-39h]
  __int64 v34; // [rsp+68h] [rbp-31h]
  PSLIST_ENTRY ListEntry; // [rsp+70h] [rbp-29h] BYREF
  PVOID P; // [rsp+78h] [rbp-21h] BYREF
  __int64 v37; // [rsp+80h] [rbp-19h] BYREF
  __int64 v38; // [rsp+88h] [rbp-11h] BYREF
  wchar_t *Str; // [rsp+90h] [rbp-9h]
  __int64 v40; // [rsp+98h] [rbp-1h] BYREF
  wchar_t *v41; // [rsp+A0h] [rbp+7h]
  _BYTE v42[8]; // [rsp+A8h] [rbp+Fh] BYREF
  ULONG64 Filter; // [rsp+B0h] [rbp+17h] BYREF

  v3 = *(const UNICODE_STRING **)(a2 + 40);
  P = 0;
  v42[0] = 0;
  ListEntry = 0;
  v38 = 0;
  Str = 0;
  v40 = 0;
  v41 = 0;
  Filter = 0;
  v37 = 0;
  if ( v3 )
  {
    if ( !RtlUnicodeStringValidateWorker(v3, 0x7FFFu, 0) )
    {
      if ( *(_QWORD *)(a1 + 8) )
      {
        if ( *(_QWORD *)(a2 + 48) )
        {
          CurrentProcess = IoGetCurrentProcess();
          LOBYTE(v6) = 1;
          if ( (int)SecGetProcessContextWithAssertions(CurrentProcess, &ListEntry, v6) >= 0
            && (int)SecGetEffectiveTokenUser(KeGetCurrentThread(), (__int64)ListEntry, &P, v42, 0) >= 0
            && (int)SecUnicodeToNullTerminatedUnicode(*(_QWORD *)(a2 + 40), &v38) >= 0
            && (int)SecUnicodeToNullTerminatedUnicode(*(_QWORD *)(a1 + 8), &v40) >= 0 )
          {
            v7 = *(unsigned int **)(a2 + 48);
            v8 = *((_QWORD *)v7 + 1);
            v9 = *v7;
            if ( (BYTE8(xmmword_14001B740) & 0x40) != 0 )
            {
              SessionsFilterMasksAndAsimovNamespaces = SecGetSessionsFilterMasksAndAsimovNamespaces(v9, v8, &v37);
              if ( SessionsFilterMasksAndAsimovNamespaces < 0 )
                goto LABEL_16;
              for ( i = v37; ; i = *(_QWORD *)(v34 + 16) )
              {
                v34 = i;
                if ( !i )
                  break;
                CurrentThreadId = (unsigned __int8)PsGetCurrentThreadId();
                v22 = *(_BYTE *)(i + 8);
                v23 = (volatile signed __int64 *)SecData;
                Next = ListEntry[3].Next;
                v25 = *(void **)P;
                v26 = *((_QWORD *)&ListEntry[2].Next + 1);
                v27 = *(_QWORD *)i;
                v33 = (int)ListEntry[2].Next;
                v28 = IoGetCurrentProcess();
                ProcessSessionId_0 = PsGetProcessSessionId_0(v28);
                v30 = _InterlockedIncrement64(v23 + 42);
                LOBYTE(v31) = v22;
                SessionsFilterMasksAndAsimovNamespaces = EventWriteQueryValue(
                                                           v27,
                                                           v30,
                                                           v33,
                                                           v26,
                                                           CurrentThreadId,
                                                           v25,
                                                           ProcessSessionId_0,
                                                           Str,
                                                           v41,
                                                           Next,
                                                           v31);
              }
            }
            else
            {
              SecGetSessionsFilterMaskFromMatchEntries(v9, v8, &Filter);
              v10 = (unsigned __int8)PsGetCurrentThreadId();
              v11 = (volatile signed __int64 *)SecData;
              v12 = (int)ListEntry[2].Next;
              v13 = ListEntry[3].Next;
              Sid = *(void **)P;
              v15 = *((_QWORD *)&ListEntry[2].Next + 1);
              v16 = IoGetCurrentProcess();
              v17 = PsGetProcessSessionId_0(v16);
              v18 = _InterlockedIncrement64(v11 + 42);
              v32 = 0;
              SessionsFilterMasksAndAsimovNamespaces = EventWriteQueryValue(
                                                         Filter,
                                                         v18,
                                                         v12,
                                                         v15,
                                                         v10,
                                                         Sid,
                                                         v17,
                                                         Str,
                                                         v41,
                                                         v13,
                                                         v32);
            }
            SecIncrementEtwCounters((unsigned int)SessionsFilterMasksAndAsimovNamespaces);
          }
        }
      }
    }
  }
LABEL_16:
  SecReleaseSessionsFilterMasksAndAsimovNamespaces(v37);
  SecFreeNullTerminatedUnicode(&v38);
  SecFreeNullTerminatedUnicode(&v40);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( P )
  {
    if ( v42[0] )
      ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x1400373fc  mov     [rsp-8+arg_10], rbx
0x140037401  push    rbp
0x140037402  push    rsi
0x140037403  push    rdi
0x140037404  push    r12
0x140037406  push    r13
0x140037408  push    r14
0x14003740a  push    r15
0x14003740c  lea     rbp, [rsp-27h]
0x140037411  sub     rsp, 0C0h
0x140037418  mov     rax, cs:__security_cookie
0x14003741f  xor     rax, rsp
0x140037422  mov     [rbp+57h+var_38], rax
0x140037426  xor     r13d, r13d
0x140037429  mov     rdi, rcx
0x14003742c  mov     rcx, [rdx+28h]; SourceString
0x140037430  mov     rbx, rdx
0x140037433  mov     [rbp+57h+P], r13
0x140037437  mov     [rbp+57h+var_48], r13b
0x14003743b  mov     [rbp+57h+ListEntry], r13
0x14003743f  mov     [rbp+57h+var_68], r13
0x140037443  mov     [rbp+57h+var_60], r13
0x140037447  mov     [rbp+57h+var_58], r13
0x14003744b  mov     [rbp+57h+var_50], r13
0x14003744f  mov     [rbp+57h+Filter], r13
0x140037453  mov     [rbp+57h+var_70], r13
0x140037457  test    rcx, rcx
0x14003745a  jz      loc_14003767C
0x140037460  xor     r8d, r8d; dwFlags
0x140037463  mov     edx, 7FFFh; cchMax
0x140037468  call    RtlUnicodeStringValidateWorker
0x14003746d  test    eax, eax
0x14003746f  jnz     loc_14003767C
0x140037475  cmp     [rdi+8], r13
0x140037479  jz      loc_14003767C
0x14003747f  cmp     [rbx+30h], r13
0x140037483  jz      loc_14003767C
0x140037489  call    cs:__imp_IoGetCurrentProcess
0x140037490  nop     dword ptr [rax+rax+00h]
0x140037495  mov     r8b, 1
0x140037498  lea     rdx, [rbp+57h+ListEntry]
0x14003749c  mov     rcx, rax
0x14003749f  call    SecGetProcessContextWithAssertions
0x1400374a4  test    eax, eax
0x1400374a6  js      loc_14003767C
0x1400374ac  mov     rcx, gs:188h; Thread
0x1400374b5  lea     r9, [rbp+57h+var_48]
0x1400374b9  mov     rdx, [rbp+57h+ListEntry]
0x1400374bd  lea     r8, [rbp+57h+P]
0x1400374c1  mov     qword ptr [rsp+0F0h+var_D0], r13; __int64
0x1400374c6  call    SecGetEffectiveTokenUser
0x1400374cb  test    eax, eax
0x1400374cd  js      loc_14003767C
0x1400374d3  mov     rcx, [rbx+28h]
0x1400374d7  lea     rdx, [rbp+57h+var_68]
0x1400374db  call    SecUnicodeToNullTerminatedUnicode
0x1400374e0  test    eax, eax
0x1400374e2  js      loc_14003767C
0x1400374e8  mov     rcx, [rdi+8]
0x1400374ec  lea     rdx, [rbp+57h+var_58]
0x1400374f0  call    SecUnicodeToNullTerminatedUnicode
0x1400374f5  test    eax, eax
0x1400374f7  js      loc_14003767C
0x1400374fd  test    byte ptr cs:xmmword_14001B740+8, 40h
0x140037504  mov     rcx, [rbx+30h]
0x140037508  mov     rdx, [rcx+8]
0x14003750c  mov     ecx, [rcx]
0x14003750e  jnz     loc_1400375AC
0x140037514  lea     r8, [rbp+57h+Filter]
0x140037518  call    SecGetSessionsFilterMaskFromMatchEntries
0x14003751d  call    cs:__imp_PsGetCurrentThreadId
0x140037524  nop     dword ptr [rax+rax+00h]
0x140037529  mov     rdx, [rbp+57h+ListEntry]
0x14003752d  mov     r15, rax
0x140037530  mov     rcx, [rbp+57h+P]
0x140037534  mov     rbx, cs:SecData
0x14003753b  mov     r12d, [rdx+20h]
0x14003753f  mov     rdi, [rdx+30h]
0x140037543  mov     rsi, [rcx]
0x140037546  mov     r14, [rdx+28h]
0x14003754a  call    cs:__imp_IoGetCurrentProcess
0x140037551  nop     dword ptr [rax+rax+00h]
0x140037556  mov     rcx, rax
0x140037559  call    PsGetProcessSessionId_0
0x14003755e  lea     edx, [r13+1]
0x140037562  lock xadd [rbx+150h], rdx
0x14003756b  mov     rcx, [rbp+57h+var_50]
0x14003756f  inc     rdx
0x140037572  mov     [rsp+0F0h+var_A0], r13b; char
0x140037577  mov     r9, r14
0x14003757a  mov     qword ptr [rsp+0F0h+var_A8], rdi; char
0x14003757f  mov     r8d, r12d
0x140037582  mov     [rsp+0F0h+var_B0], rcx; wchar_t *
0x140037587  mov     rcx, [rbp+57h+var_60]
0x14003758b  mov     [rsp+0F0h+Str], rcx; Str
0x140037590  mov     rcx, [rbp+57h+Filter]; Filter
0x140037594  mov     dword ptr [rsp+0F0h+var_C0], eax; char
0x140037598  mov     [rsp+0F0h+Sid], rsi; Sid
0x14003759d  mov     dword ptr [rsp+0F0h+var_D0], r15d; char
0x1400375a2  call    EventWriteQueryValue
0x1400375a7  jmp     loc_140037675
0x1400375ac  lea     r8, [rbp+57h+var_70]
0x1400375b0  call    SecGetSessionsFilterMasksAndAsimovNamespaces
0x1400375b5  test    eax, eax
0x1400375b7  js      loc_14003767C
0x1400375bd  mov     r12, [rbp+57h+var_70]
0x1400375c1  jmp     loc_140037668
0x1400375c6  call    cs:__imp_PsGetCurrentThreadId
0x1400375cd  nop     dword ptr [rax+rax+00h]
0x1400375d2  mov     rdx, [rbp+57h+ListEntry]
0x1400375d6  mov     r13, rax
0x1400375d9  mov     rcx, [rbp+57h+P]
0x1400375dd  mov     dil, [r12+8]
0x1400375e2  mov     rbx, cs:SecData
0x1400375e9  mov     eax, [rdx+20h]
0x1400375ec  mov     rsi, [rdx+30h]
0x1400375f0  mov     r14, [rcx]
0x1400375f3  mov     r15, [rdx+28h]
0x1400375f7  mov     r12, [r12]
0x1400375fb  mov     [rbp+57h+var_90], eax
0x1400375fe  call    cs:__imp_IoGetCurrentProcess
0x140037605  nop     dword ptr [rax+rax+00h]
0x14003760a  mov     rcx, rax
0x14003760d  call    PsGetProcessSessionId_0
0x140037612  mov     edx, 1
0x140037617  lock xadd [rbx+150h], rdx
0x140037620  mov     r10, [rbp+57h+var_50]
0x140037624  inc     rdx
0x140037627  mov     r8d, [rbp+57h+var_90]
0x14003762b  mov     r9, r15
0x14003762e  mov     [rsp+0F0h+var_A0], dil; char
0x140037633  mov     rcx, r12; Filter
0x140037636  mov     qword ptr [rsp+0F0h+var_A8], rsi; char
0x14003763b  mov     [rsp+0F0h+var_B0], r10; wchar_t *
0x140037640  mov     r10, [rbp+57h+var_60]
0x140037644  mov     [rsp+0F0h+Str], r10; Str
0x140037649  mov     dword ptr [rsp+0F0h+var_C0], eax; char
0x14003764d  mov     [rsp+0F0h+Sid], r14; Sid
0x140037652  mov     dword ptr [rsp+0F0h+var_D0], r13d; char
0x140037657  call    EventWriteQueryValue
0x14003765c  mov     r12, [rbp+57h+var_88]
0x140037660  xor     r13d, r13d
0x140037663  mov     r12, [r12+10h]
0x140037668  mov     [rbp+57h+var_88], r12
0x14003766c  test    r12, r12
0x14003766f  jnz     loc_1400375C6
0x140037675  mov     ecx, eax
0x140037677  call    SecIncrementEtwCounters
0x14003767c  mov     rcx, [rbp+57h+var_70]
0x140037680  call    SecReleaseSessionsFilterMasksAndAsimovNamespaces
0x140037685  lea     rcx, [rbp+57h+var_68]
0x140037689  call    SecFreeNullTerminatedUnicode
0x14003768e  lea     rcx, [rbp+57h+var_58]
0x140037692  call    SecFreeNullTerminatedUnicode
0x140037697  mov     rcx, [rbp+57h+ListEntry]; ListEntry
0x14003769b  test    rcx, rcx
0x14003769e  jz      short loc_1400376A5
0x1400376a0  call    SecReleaseProcessContext
0x1400376a5  mov     rcx, [rbp+57h+P]; P
0x1400376a9  test    rcx, rcx
0x1400376ac  jz      short loc_1400376C2
0x1400376ae  cmp     [rbp+57h+var_48], r13b
0x1400376b2  jz      short loc_1400376C2
0x1400376b4  xor     edx, edx; Tag
0x1400376b6  call    cs:__imp_ExFreePoolWithTag
0x1400376bd  nop     dword ptr [rax+rax+00h]
0x1400376c2  mov     rcx, [rbp+57h+var_38]
0x1400376c6  xor     rcx, rsp; StackCookie
0x1400376c9  call    __security_check_cookie
0x1400376ce  mov     rbx, [rsp+0F0h+arg_10]
0x1400376d6  add     rsp, 0C0h
0x1400376dd  pop     r15
0x1400376df  pop     r14
0x1400376e1  pop     r13
0x1400376e3  pop     r12
0x1400376e5  pop     rdi
0x1400376e6  pop     rsi
0x1400376e7  pop     rbp
0x1400376e8  retn
```
