# RegIssueQueryKeyInfoEvent

- ea: `0x14003715c`
- end: `0x1400373fb`
- name: `RegIssueQueryKeyInfoEvent`
- size: `671`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x140038b54`

## callees

- `0x1400061dc`
- `0x140006684`
- `0x140006754`
- `0x140006b6c`
- `0x140006d3c`
- `0x140007a30`
- `0x14000885c`
- `0x140010080`
- `0x1400108b8`
- `0x140011650`
- `0x14003715c`
- `0x14003a4c4`
- `0x14003a5b8`
- `0x14003a768`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140037249`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400372e9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140037249`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400372e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400373c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400373c7`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400371d2`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037276`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037321`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400371d2`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037276`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037321`

## pseudocode

```c
void __fastcall RegIssueQueryKeyInfoEvent(const UNICODE_STRING *a1, unsigned int *a2)
{
  PEPROCESS CurrentProcess; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  char v7; // r15
  volatile signed __int64 *v8; // rbx
  int v9; // r12d
  struct _SLIST_ENTRY *v10; // rdi
  void *Sid; // rsi
  __int64 v12; // r14
  PEPROCESS v13; // rax
  int v14; // eax
  __int64 v15; // rdx
  int SessionsFilterMasksAndAsimovNamespaces; // eax
  __int64 i; // r12
  char CurrentThreadId; // r13
  char v19; // di
  volatile signed __int64 *v20; // rbx
  struct _SLIST_ENTRY *Next; // rsi
  void *v22; // r14
  __int64 v23; // r15
  ULONG64 v24; // r12
  PEPROCESS v25; // rax
  int ProcessSessionId_0; // eax
  __int64 v27; // rdx
  __int64 v28; // [rsp+30h] [rbp-49h]
  char v29[4]; // [rsp+30h] [rbp-49h]
  __int64 v30; // [rsp+48h] [rbp-31h]
  char v31; // [rsp+48h] [rbp-31h]
  int v32; // [rsp+50h] [rbp-29h]
  __int64 v33; // [rsp+58h] [rbp-21h]
  PSLIST_ENTRY ListEntry; // [rsp+60h] [rbp-19h] BYREF
  PVOID P; // [rsp+68h] [rbp-11h] BYREF
  __int64 v36; // [rsp+70h] [rbp-9h] BYREF
  __int64 v37; // [rsp+78h] [rbp-1h] BYREF
  wchar_t *v38; // [rsp+80h] [rbp+7h]
  _BYTE v39[8]; // [rsp+88h] [rbp+Fh] BYREF
  ULONG64 Filter; // [rsp+90h] [rbp+17h] BYREF

  P = 0;
  v39[0] = 0;
  ListEntry = 0;
  v37 = 0;
  v38 = 0;
  Filter = 0;
  v36 = 0;
  if ( a1 )
  {
    if ( !RtlUnicodeStringValidateWorker(a1, 0x7FFFu, 0) )
    {
      if ( a2 )
      {
        CurrentProcess = IoGetCurrentProcess();
        if ( (int)SecGetProcessContextByObject(CurrentProcess, &ListEntry) >= 0
          && (int)SecGetEffectiveTokenUser(KeGetCurrentThread(), (__int64)ListEntry, &P, v39, 0) >= 0
          && (int)SecUnicodeToNullTerminatedUnicode(a1, &v37) >= 0 )
        {
          v5 = *((_QWORD *)a2 + 1);
          v6 = *a2;
          if ( (BYTE8(xmmword_14001B740) & 0x40) != 0 )
          {
            SessionsFilterMasksAndAsimovNamespaces = SecGetSessionsFilterMasksAndAsimovNamespaces(v6, v5, &v36);
            if ( SessionsFilterMasksAndAsimovNamespaces < 0 )
              goto LABEL_14;
            for ( i = v36; ; i = *(_QWORD *)(v33 + 16) )
            {
              v33 = i;
              if ( !i )
                break;
              CurrentThreadId = (unsigned __int8)PsGetCurrentThreadId();
              v19 = *(_BYTE *)(i + 8);
              v20 = (volatile signed __int64 *)SecData;
              Next = ListEntry[3].Next;
              v22 = *(void **)P;
              v23 = *((_QWORD *)&ListEntry[2].Next + 1);
              v24 = *(_QWORD *)i;
              v32 = (int)ListEntry[2].Next;
              v25 = IoGetCurrentProcess();
              ProcessSessionId_0 = PsGetProcessSessionId_0(v25);
              v27 = _InterlockedIncrement64(v20 + 42);
              LOBYTE(v30) = v19;
              LODWORD(v28) = ProcessSessionId_0;
              SessionsFilterMasksAndAsimovNamespaces = EventWriteQueryKeyInfo(
                                                         v24,
                                                         v27,
                                                         v32,
                                                         v23,
                                                         CurrentThreadId,
                                                         v22,
                                                         v28,
                                                         v38,
                                                         Next,
                                                         v30);
            }
          }
          else
          {
            SecGetSessionsFilterMaskFromMatchEntries(v6, v5, &Filter);
            v7 = (unsigned __int8)PsGetCurrentThreadId();
            v8 = (volatile signed __int64 *)SecData;
            v9 = (int)ListEntry[2].Next;
            v10 = ListEntry[3].Next;
            Sid = *(void **)P;
            v12 = *((_QWORD *)&ListEntry[2].Next + 1);
            v13 = IoGetCurrentProcess();
            v14 = PsGetProcessSessionId_0(v13);
            v15 = _InterlockedIncrement64(v8 + 42);
            v31 = 0;
            *(_DWORD *)v29 = v14;
            SessionsFilterMasksAndAsimovNamespaces = EventWriteQueryKeyInfo(
                                                       Filter,
                                                       v15,
                                                       v9,
                                                       v12,
                                                       v7,
                                                       Sid,
                                                       *(_DWORD *)v29,
                                                       v38,
                                                       v10,
                                                       v31);
          }
          SecIncrementEtwCounters((unsigned int)SessionsFilterMasksAndAsimovNamespaces);
        }
      }
    }
  }
LABEL_14:
  SecReleaseSessionsFilterMasksAndAsimovNamespaces(v36);
  SecFreeNullTerminatedUnicode(&v37);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( P )
  {
    if ( v39[0] )
      ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x14003715c  mov     [rsp-8+arg_10], rbx
0x140037161  push    rbp
0x140037162  push    rsi
0x140037163  push    rdi
0x140037164  push    r12
0x140037166  push    r13
0x140037168  push    r14
0x14003716a  push    r15
0x14003716c  lea     rbp, [rsp-27h]
0x140037171  sub     rsp, 0A0h
0x140037178  mov     rax, cs:__security_cookie
0x14003717f  xor     rax, rsp
0x140037182  mov     [rbp+57h+var_38], rax
0x140037186  xor     r13d, r13d
0x140037189  mov     rbx, rdx
0x14003718c  mov     [rbp+57h+P], r13
0x140037190  mov     rdi, rcx
0x140037193  mov     [rbp+57h+var_48], r13b
0x140037197  mov     [rbp+57h+ListEntry], r13
0x14003719b  mov     [rbp+57h+var_58], r13
0x14003719f  mov     [rbp+57h+var_50], r13
0x1400371a3  mov     [rbp+57h+Filter], r13
0x1400371a7  mov     [rbp+57h+var_60], r13
0x1400371ab  test    rcx, rcx
0x1400371ae  jz      loc_140037396
0x1400371b4  xor     r8d, r8d; dwFlags
0x1400371b7  mov     edx, 7FFFh; cchMax
0x1400371bc  call    RtlUnicodeStringValidateWorker
0x1400371c1  test    eax, eax
0x1400371c3  jnz     loc_140037396
0x1400371c9  test    rbx, rbx
0x1400371cc  jz      loc_140037396
0x1400371d2  call    cs:__imp_IoGetCurrentProcess
0x1400371d9  nop     dword ptr [rax+rax+00h]
0x1400371de  mov     rcx, rax
0x1400371e1  lea     rdx, [rbp+57h+ListEntry]
0x1400371e5  call    SecGetProcessContextByObject
0x1400371ea  test    eax, eax
0x1400371ec  js      loc_140037396
0x1400371f2  mov     rcx, gs:188h; Thread
0x1400371fb  lea     r9, [rbp+57h+var_48]
0x1400371ff  mov     rdx, [rbp+57h+ListEntry]
0x140037203  lea     r8, [rbp+57h+P]
0x140037207  mov     qword ptr [rsp+0D0h+var_B0], r13; __int64
0x14003720c  call    SecGetEffectiveTokenUser
0x140037211  test    eax, eax
0x140037213  js      loc_140037396
0x140037219  lea     rdx, [rbp+57h+var_58]
0x14003721d  mov     rcx, rdi
0x140037220  call    SecUnicodeToNullTerminatedUnicode
0x140037225  test    eax, eax
0x140037227  js      loc_140037396
0x14003722d  test    byte ptr cs:xmmword_14001B740+8, 40h
0x140037234  mov     rdx, [rbx+8]
0x140037238  mov     ecx, [rbx]
0x14003723a  jnz     loc_1400372CF
0x140037240  lea     r8, [rbp+57h+Filter]
0x140037244  call    SecGetSessionsFilterMaskFromMatchEntries
0x140037249  call    cs:__imp_PsGetCurrentThreadId
0x140037250  nop     dword ptr [rax+rax+00h]
0x140037255  mov     rdx, [rbp+57h+ListEntry]
0x140037259  mov     r15, rax
0x14003725c  mov     rcx, [rbp+57h+P]
0x140037260  mov     rbx, cs:SecData
0x140037267  mov     r12d, [rdx+20h]
0x14003726b  mov     rdi, [rdx+30h]
0x14003726f  mov     rsi, [rcx]
0x140037272  mov     r14, [rdx+28h]
0x140037276  call    cs:__imp_IoGetCurrentProcess
0x14003727d  nop     dword ptr [rax+rax+00h]
0x140037282  mov     rcx, rax
0x140037285  call    PsGetProcessSessionId_0
0x14003728a  lea     edx, [r13+1]
0x14003728e  lock xadd [rbx+150h], rdx
0x140037297  mov     rcx, [rbp+57h+var_50]
0x14003729b  inc     rdx
0x14003729e  mov     byte ptr [rsp+0D0h+var_88], r13b; char
0x1400372a3  mov     r9, r14
0x1400372a6  mov     qword ptr [rsp+0D0h+var_90], rdi; char
0x1400372ab  mov     r8d, r12d
0x1400372ae  mov     [rsp+0D0h+Str], rcx; Str
0x1400372b3  mov     rcx, [rbp+57h+Filter]; Filter
0x1400372b7  mov     dword ptr [rsp+0D0h+var_A0], eax; char
0x1400372bb  mov     [rsp+0D0h+Sid], rsi; Sid
0x1400372c0  mov     dword ptr [rsp+0D0h+var_B0], r15d; char
0x1400372c5  call    EventWriteQueryKeyInfo
0x1400372ca  jmp     loc_14003738F
0x1400372cf  lea     r8, [rbp+57h+var_60]
0x1400372d3  call    SecGetSessionsFilterMasksAndAsimovNamespaces
0x1400372d8  test    eax, eax
0x1400372da  js      loc_140037396
0x1400372e0  mov     r12, [rbp+57h+var_60]
0x1400372e4  jmp     loc_140037382
0x1400372e9  call    cs:__imp_PsGetCurrentThreadId
0x1400372f0  nop     dword ptr [rax+rax+00h]
0x1400372f5  mov     rdx, [rbp+57h+ListEntry]
0x1400372f9  mov     r13, rax
0x1400372fc  mov     rcx, [rbp+57h+P]
0x140037300  mov     dil, [r12+8]
0x140037305  mov     rbx, cs:SecData
0x14003730c  mov     eax, [rdx+20h]
0x14003730f  mov     rsi, [rdx+30h]
0x140037313  mov     r14, [rcx]
0x140037316  mov     r15, [rdx+28h]
0x14003731a  mov     r12, [r12]
0x14003731e  mov     [rbp+57h+var_80], eax
0x140037321  call    cs:__imp_IoGetCurrentProcess
0x140037328  nop     dword ptr [rax+rax+00h]
0x14003732d  mov     rcx, rax
0x140037330  call    PsGetProcessSessionId_0
0x140037335  mov     edx, 1
0x14003733a  lock xadd [rbx+150h], rdx
0x140037343  mov     r10, [rbp+57h+var_50]
0x140037347  inc     rdx
0x14003734a  mov     r8d, [rbp+57h+var_80]
0x14003734e  mov     r9, r15
0x140037351  mov     byte ptr [rsp+0D0h+var_88], dil; char
0x140037356  mov     rcx, r12; Filter
0x140037359  mov     qword ptr [rsp+0D0h+var_90], rsi; char
0x14003735e  mov     [rsp+0D0h+Str], r10; Str
0x140037363  mov     dword ptr [rsp+0D0h+var_A0], eax; char
0x140037367  mov     [rsp+0D0h+Sid], r14; Sid
0x14003736c  mov     dword ptr [rsp+0D0h+var_B0], r13d; char
0x140037371  call    EventWriteQueryKeyInfo
0x140037376  mov     r12, [rbp+57h+var_78]
0x14003737a  xor     r13d, r13d
0x14003737d  mov     r12, [r12+10h]
0x140037382  mov     [rbp+57h+var_78], r12
0x140037386  test    r12, r12
0x140037389  jnz     loc_1400372E9
0x14003738f  mov     ecx, eax
0x140037391  call    SecIncrementEtwCounters
0x140037396  mov     rcx, [rbp+57h+var_60]
0x14003739a  call    SecReleaseSessionsFilterMasksAndAsimovNamespaces
0x14003739f  lea     rcx, [rbp+57h+var_58]
0x1400373a3  call    SecFreeNullTerminatedUnicode
0x1400373a8  mov     rcx, [rbp+57h+ListEntry]; ListEntry
0x1400373ac  test    rcx, rcx
0x1400373af  jz      short loc_1400373B6
0x1400373b1  call    SecReleaseProcessContext
0x1400373b6  mov     rcx, [rbp+57h+P]; P
0x1400373ba  test    rcx, rcx
0x1400373bd  jz      short loc_1400373D3
0x1400373bf  cmp     [rbp+57h+var_48], r13b
0x1400373c3  jz      short loc_1400373D3
0x1400373c5  xor     edx, edx; Tag
0x1400373c7  call    cs:__imp_ExFreePoolWithTag
0x1400373ce  nop     dword ptr [rax+rax+00h]
0x1400373d3  mov     rcx, [rbp+57h+var_38]
0x1400373d7  xor     rcx, rsp; StackCookie
0x1400373da  call    __security_check_cookie
0x1400373df  mov     rbx, [rsp+0D0h+arg_10]
0x1400373e7  add     rsp, 0A0h
0x1400373ee  pop     r15
0x1400373f0  pop     r14
0x1400373f2  pop     r13
0x1400373f4  pop     r12
0x1400373f6  pop     rdi
0x1400373f7  pop     rsi
0x1400373f8  pop     rbp
0x1400373f9  retn
```
