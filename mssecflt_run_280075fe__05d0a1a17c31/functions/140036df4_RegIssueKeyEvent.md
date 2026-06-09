# RegIssueKeyEvent

- ea: `0x140036df4`
- end: `0x140037159`
- name: `RegIssueKeyEvent`
- size: `869`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation`

## callers

- `0x1400389c4`
- `0x140038a48`

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
- `0x140035b7c`
- `0x140035cfc`
- `0x140036df4`
- `0x14003a4c4`
- `0x14003a5b8`
- `0x14003a768`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140036ee5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140036fe4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140036ee5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140036fe4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037125`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037125`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036e68`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036f17`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036f70`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037021`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003707b`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036e68`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036f17`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036f70`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037021`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003707b`

## pseudocode

```c
void __fastcall RegIssueKeyEvent(const UNICODE_STRING *a1, unsigned int *a2, char a3)
{
  char v3; // si
  PEPROCESS CurrentProcess; // rax
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned __int8 CurrentThreadId; // al
  bool v11; // zf
  char v12; // r15
  volatile signed __int64 *v13; // rbx
  int Next; // r12d
  struct _SLIST_ENTRY *v15; // rdi
  __int64 v16; // r14
  void *Sid; // rsi
  PEPROCESS v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  int SessionsFilterMasksAndAsimovNamespaces; // eax
  PEPROCESS v22; // rax
  int ProcessSessionId_0; // eax
  __int64 v24; // rdx
  __int64 i; // r12
  unsigned __int8 v26; // al
  char v27; // r13
  char v28; // di
  volatile signed __int64 *v29; // rbx
  __int64 v30; // r15
  void *v31; // r14
  struct _SLIST_ENTRY *v32; // rsi
  ULONG64 v33; // r12
  PEPROCESS v34; // rax
  int v35; // eax
  __int64 v36; // rdx
  PEPROCESS v37; // rax
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // [rsp+30h] [rbp-49h]
  char v41[4]; // [rsp+30h] [rbp-49h]
  char v42[4]; // [rsp+30h] [rbp-49h]
  __int64 v43; // [rsp+48h] [rbp-31h]
  char v44; // [rsp+48h] [rbp-31h]
  char v45; // [rsp+48h] [rbp-31h]
  int v47; // [rsp+54h] [rbp-25h]
  __int64 v48; // [rsp+58h] [rbp-21h]
  PSLIST_ENTRY ListEntry; // [rsp+60h] [rbp-19h] BYREF
  PVOID P; // [rsp+68h] [rbp-11h] BYREF
  __int64 v51; // [rsp+70h] [rbp-9h] BYREF
  wchar_t *v52; // [rsp+78h] [rbp-1h]
  __int64 v53; // [rsp+80h] [rbp+7h] BYREF
  _BYTE v54[8]; // [rsp+88h] [rbp+Fh] BYREF
  ULONG64 Filter; // [rsp+90h] [rbp+17h] BYREF

  P = 0;
  v3 = a3;
  v54[0] = 0;
  ListEntry = 0;
  v51 = 0;
  v52 = 0;
  Filter = 0;
  v53 = 0;
  if ( !a2 )
    return;
  if ( RtlUnicodeStringValidateWorker(a1, 0x7FFFu, 0) >= 0 )
  {
    CurrentProcess = IoGetCurrentProcess();
    LOBYTE(v7) = 1;
    if ( (int)SecGetProcessContextWithAssertions(CurrentProcess, &ListEntry, v7) >= 0
      && (int)SecGetEffectiveTokenUser(KeGetCurrentThread(), (__int64)ListEntry, &P, v54, 0) >= 0 )
    {
      _mm_lfence();
      if ( (int)SecUnicodeToNullTerminatedUnicode(a1, &v51) >= 0 )
      {
        v8 = *((_QWORD *)a2 + 1);
        v9 = *a2;
        if ( (BYTE8(xmmword_14001B740) & 0x40) == 0 )
        {
          SecGetSessionsFilterMaskFromMatchEntries(v9, v8, &Filter);
          CurrentThreadId = (unsigned __int8)PsGetCurrentThreadId();
          v11 = v3 == 0;
          v12 = CurrentThreadId;
          v13 = (volatile signed __int64 *)SecData;
          Next = (int)ListEntry[2].Next;
          v15 = ListEntry[3].Next;
          v16 = *((_QWORD *)&ListEntry[2].Next + 1);
          Sid = *(void **)P;
          if ( v11 )
          {
            v22 = IoGetCurrentProcess();
            ProcessSessionId_0 = PsGetProcessSessionId_0(v22);
            v24 = _InterlockedIncrement64(v13 + 42);
            v45 = 0;
            *(_DWORD *)v42 = ProcessSessionId_0;
            SessionsFilterMasksAndAsimovNamespaces = EventWriteDeleteKey(
                                                       Filter,
                                                       v24,
                                                       Next,
                                                       v16,
                                                       v12,
                                                       Sid,
                                                       *(_DWORD *)v42,
                                                       v52,
                                                       v15,
                                                       v45);
          }
          else
          {
            v18 = IoGetCurrentProcess();
            v19 = PsGetProcessSessionId_0(v18);
            v20 = _InterlockedIncrement64(v13 + 42);
            v44 = 0;
            *(_DWORD *)v41 = v19;
            SessionsFilterMasksAndAsimovNamespaces = EventWriteCreateKey(
                                                       Filter,
                                                       v20,
                                                       Next,
                                                       v16,
                                                       v12,
                                                       Sid,
                                                       *(_DWORD *)v41,
                                                       v52,
                                                       v15,
                                                       v44);
          }
LABEL_17:
          SecIncrementEtwCounters((unsigned int)SessionsFilterMasksAndAsimovNamespaces);
          goto LABEL_18;
        }
        SessionsFilterMasksAndAsimovNamespaces = SecGetSessionsFilterMasksAndAsimovNamespaces(v9, v8, &v53);
        if ( SessionsFilterMasksAndAsimovNamespaces >= 0 )
        {
          for ( i = v53; ; i = *(_QWORD *)(v48 + 16) )
          {
            v48 = i;
            if ( !i )
              break;
            v26 = (unsigned __int8)PsGetCurrentThreadId();
            v11 = v3 == 0;
            v27 = v26;
            v28 = *(_BYTE *)(i + 8);
            v29 = (volatile signed __int64 *)SecData;
            v30 = *((_QWORD *)&ListEntry[2].Next + 1);
            v31 = *(void **)P;
            v32 = ListEntry[3].Next;
            v33 = *(_QWORD *)i;
            v47 = (int)ListEntry[2].Next;
            if ( v11 )
            {
              v37 = IoGetCurrentProcess();
              v38 = PsGetProcessSessionId_0(v37);
              v39 = _InterlockedIncrement64(v29 + 42);
              LOBYTE(v43) = v28;
              LODWORD(v40) = v38;
              SessionsFilterMasksAndAsimovNamespaces = EventWriteDeleteKey(
                                                         v33,
                                                         v39,
                                                         v47,
                                                         v30,
                                                         v27,
                                                         v31,
                                                         v40,
                                                         v52,
                                                         v32,
                                                         v43);
            }
            else
            {
              v34 = IoGetCurrentProcess();
              v35 = PsGetProcessSessionId_0(v34);
              v36 = _InterlockedIncrement64(v29 + 42);
              LOBYTE(v43) = v28;
              LODWORD(v40) = v35;
              SessionsFilterMasksAndAsimovNamespaces = EventWriteCreateKey(
                                                         v33,
                                                         v36,
                                                         v47,
                                                         v30,
                                                         v27,
                                                         v31,
                                                         v40,
                                                         v52,
                                                         v32,
                                                         v43);
            }
            v3 = a3;
          }
          goto LABEL_17;
        }
      }
    }
  }
LABEL_18:
  SecReleaseSessionsFilterMasksAndAsimovNamespaces(v53);
  SecFreeNullTerminatedUnicode(&v51);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( P )
  {
    if ( v54[0] )
      ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x140036df4  mov     [rsp-8+arg_10], rbx
0x140036df9  push    rbp
0x140036dfa  push    rsi
0x140036dfb  push    rdi
0x140036dfc  push    r12
0x140036dfe  push    r13
0x140036e00  push    r14
0x140036e02  push    r15
0x140036e04  lea     rbp, [rsp-27h]
0x140036e09  sub     rsp, 0A0h
0x140036e10  mov     rax, cs:__security_cookie
0x140036e17  xor     rax, rsp
0x140036e1a  mov     [rbp+57h+var_38], rax
0x140036e1e  xor     r13d, r13d
0x140036e21  mov     [rbp+57h+var_80], r8b
0x140036e25  mov     [rbp+57h+P], r13
0x140036e29  mov     sil, r8b
0x140036e2c  mov     [rbp+57h+var_48], r13b
0x140036e30  mov     rbx, rdx
0x140036e33  mov     [rbp+57h+ListEntry], r13
0x140036e37  mov     rdi, rcx
0x140036e3a  mov     [rbp+57h+var_60], r13
0x140036e3e  mov     [rbp+57h+var_58], r13
0x140036e42  mov     [rbp+57h+Filter], r13
0x140036e46  mov     [rbp+57h+var_50], r13
0x140036e4a  test    rdx, rdx
0x140036e4d  jz      loc_140037131
0x140036e53  xor     r8d, r8d; dwFlags
0x140036e56  mov     edx, 7FFFh; cchMax
0x140036e5b  call    RtlUnicodeStringValidateWorker
0x140036e60  test    eax, eax
0x140036e62  js      loc_1400370F4
0x140036e68  call    cs:__imp_IoGetCurrentProcess
0x140036e6f  nop     dword ptr [rax+rax+00h]
0x140036e74  mov     r8b, 1
0x140036e77  lea     rdx, [rbp+57h+ListEntry]
0x140036e7b  mov     rcx, rax
0x140036e7e  call    SecGetProcessContextWithAssertions
0x140036e83  test    eax, eax
0x140036e85  js      loc_1400370F4
0x140036e8b  mov     rcx, gs:188h; Thread
0x140036e94  lea     r9, [rbp+57h+var_48]
0x140036e98  mov     rdx, [rbp+57h+ListEntry]
0x140036e9c  lea     r8, [rbp+57h+P]
0x140036ea0  mov     qword ptr [rsp+0D0h+var_B0], r13; __int64
0x140036ea5  call    SecGetEffectiveTokenUser
0x140036eaa  test    eax, eax
0x140036eac  js      loc_1400370F4
0x140036eb2  lfence
0x140036eb5  lea     rdx, [rbp+57h+var_60]
0x140036eb9  mov     rcx, rdi
0x140036ebc  call    SecUnicodeToNullTerminatedUnicode
0x140036ec1  test    eax, eax
0x140036ec3  js      loc_1400370F4
0x140036ec9  test    byte ptr cs:xmmword_14001B740+8, 40h
0x140036ed0  mov     rdx, [rbx+8]
0x140036ed4  mov     ecx, [rbx]
0x140036ed6  jnz     loc_140036FCA
0x140036edc  lea     r8, [rbp+57h+Filter]
0x140036ee0  call    SecGetSessionsFilterMaskFromMatchEntries
0x140036ee5  call    cs:__imp_PsGetCurrentThreadId
0x140036eec  nop     dword ptr [rax+rax+00h]
0x140036ef1  mov     rdx, [rbp+57h+ListEntry]
0x140036ef5  test    sil, sil
0x140036ef8  mov     rcx, [rbp+57h+P]
0x140036efc  mov     r15, rax
0x140036eff  mov     rbx, cs:SecData
0x140036f06  mov     r12d, [rdx+20h]
0x140036f0a  mov     rdi, [rdx+30h]
0x140036f0e  mov     r14, [rdx+28h]
0x140036f12  mov     rsi, [rcx]
0x140036f15  jz      short loc_140036F70
0x140036f17  call    cs:__imp_IoGetCurrentProcess
0x140036f1e  nop     dword ptr [rax+rax+00h]
0x140036f23  mov     rcx, rax
0x140036f26  call    PsGetProcessSessionId_0
0x140036f2b  lea     edx, [r13+1]
0x140036f2f  lock xadd [rbx+150h], rdx
0x140036f38  mov     rcx, [rbp+57h+var_58]
0x140036f3c  inc     rdx
0x140036f3f  mov     byte ptr [rsp+0D0h+var_88], r13b; char
0x140036f44  mov     r9, r14
0x140036f47  mov     qword ptr [rsp+0D0h+var_90], rdi; char
0x140036f4c  mov     r8d, r12d
0x140036f4f  mov     [rsp+0D0h+Str], rcx; Str
0x140036f54  mov     rcx, [rbp+57h+Filter]; Filter
0x140036f58  mov     dword ptr [rsp+0D0h+var_A0], eax; char
0x140036f5c  mov     [rsp+0D0h+Sid], rsi; Sid
0x140036f61  mov     dword ptr [rsp+0D0h+var_B0], r15d; char
0x140036f66  call    EventWriteCreateKey
0x140036f6b  jmp     loc_1400370ED
0x140036f70  call    cs:__imp_IoGetCurrentProcess
0x140036f77  nop     dword ptr [rax+rax+00h]
0x140036f7c  mov     rcx, rax
0x140036f7f  call    PsGetProcessSessionId_0
0x140036f84  mov     edx, 1
0x140036f89  lock xadd [rbx+150h], rdx
0x140036f92  mov     rcx, [rbp+57h+var_58]
0x140036f96  inc     rdx
0x140036f99  mov     byte ptr [rsp+0D0h+var_88], r13b; char
0x140036f9e  mov     r9, r14
0x140036fa1  mov     qword ptr [rsp+0D0h+var_90], rdi; char
0x140036fa6  mov     r8d, r12d
0x140036fa9  mov     [rsp+0D0h+Str], rcx; Str
0x140036fae  mov     rcx, [rbp+57h+Filter]; Filter
0x140036fb2  mov     dword ptr [rsp+0D0h+var_A0], eax; char
0x140036fb6  mov     [rsp+0D0h+Sid], rsi; Sid
0x140036fbb  mov     dword ptr [rsp+0D0h+var_B0], r15d; char
0x140036fc0  call    EventWriteDeleteKey
0x140036fc5  jmp     loc_1400370ED
0x140036fca  lea     r8, [rbp+57h+var_50]
0x140036fce  call    SecGetSessionsFilterMasksAndAsimovNamespaces
0x140036fd3  test    eax, eax
0x140036fd5  js      loc_1400370F4
0x140036fdb  mov     r12, [rbp+57h+var_50]
0x140036fdf  jmp     loc_1400370E0
0x140036fe4  call    cs:__imp_PsGetCurrentThreadId
0x140036feb  nop     dword ptr [rax+rax+00h]
0x140036ff0  mov     rdx, [rbp+57h+ListEntry]
0x140036ff4  test    sil, sil
0x140036ff7  mov     rcx, [rbp+57h+P]
0x140036ffb  mov     r13, rax
0x140036ffe  mov     dil, [r12+8]
0x140037003  mov     rbx, cs:SecData
0x14003700a  mov     eax, [rdx+20h]
0x14003700d  mov     r15, [rdx+28h]
0x140037011  mov     r14, [rcx]
0x140037014  mov     rsi, [rdx+30h]
0x140037018  mov     r12, [r12]
0x14003701c  jz      short loc_140037078
0x14003701e  mov     [rbp+57h+var_7C], eax
0x140037021  call    cs:__imp_IoGetCurrentProcess
0x140037028  nop     dword ptr [rax+rax+00h]
0x14003702d  mov     rcx, rax
0x140037030  call    PsGetProcessSessionId_0
0x140037035  mov     edx, 1
0x14003703a  lock xadd [rbx+150h], rdx
0x140037043  mov     r10, [rbp+57h+var_58]
0x140037047  inc     rdx
0x14003704a  mov     r8d, [rbp+57h+var_7C]
0x14003704e  mov     r9, r15
0x140037051  mov     byte ptr [rsp+0D0h+var_88], dil; char
0x140037056  mov     rcx, r12; Filter
0x140037059  mov     qword ptr [rsp+0D0h+var_90], rsi; char
0x14003705e  mov     [rsp+0D0h+Str], r10; Str
0x140037063  mov     dword ptr [rsp+0D0h+var_A0], eax; char
0x140037067  mov     [rsp+0D0h+Sid], r14; Sid
0x14003706c  mov     dword ptr [rsp+0D0h+var_B0], r13d; char
0x140037071  call    EventWriteCreateKey
0x140037076  jmp     short loc_1400370D0
0x140037078  mov     [rbp+57h+var_7C], eax
0x14003707b  call    cs:__imp_IoGetCurrentProcess
0x140037082  nop     dword ptr [rax+rax+00h]
0x140037087  mov     rcx, rax
0x14003708a  call    PsGetProcessSessionId_0
0x14003708f  mov     edx, 1
0x140037094  lock xadd [rbx+150h], rdx
0x14003709d  mov     r10, [rbp+57h+var_58]
0x1400370a1  inc     rdx
0x1400370a4  mov     r8d, [rbp+57h+var_7C]
0x1400370a8  mov     r9, r15
0x1400370ab  mov     byte ptr [rsp+0D0h+var_88], dil; char
0x1400370b0  mov     rcx, r12; Filter
0x1400370b3  mov     qword ptr [rsp+0D0h+var_90], rsi; char
0x1400370b8  mov     [rsp+0D0h+Str], r10; Str
0x1400370bd  mov     dword ptr [rsp+0D0h+var_A0], eax; char
0x1400370c1  mov     [rsp+0D0h+Sid], r14; Sid
0x1400370c6  mov     dword ptr [rsp+0D0h+var_B0], r13d; char
0x1400370cb  call    EventWriteDeleteKey
0x1400370d0  mov     r12, [rbp+57h+var_78]
0x1400370d4  xor     r13d, r13d
0x1400370d7  mov     sil, [rbp+57h+var_80]
0x1400370db  mov     r12, [r12+10h]
0x1400370e0  mov     [rbp+57h+var_78], r12
0x1400370e4  test    r12, r12
0x1400370e7  jnz     loc_140036FE4
0x1400370ed  mov     ecx, eax
0x1400370ef  call    SecIncrementEtwCounters
0x1400370f4  mov     rcx, [rbp+57h+var_50]
0x1400370f8  call    SecReleaseSessionsFilterMasksAndAsimovNamespaces
0x1400370fd  lea     rcx, [rbp+57h+var_60]
0x140037101  call    SecFreeNullTerminatedUnicode
0x140037106  mov     rcx, [rbp+57h+ListEntry]; ListEntry
0x14003710a  test    rcx, rcx
0x14003710d  jz      short loc_140037114
0x14003710f  call    SecReleaseProcessContext
0x140037114  mov     rcx, [rbp+57h+P]; P
0x140037118  test    rcx, rcx
0x14003711b  jz      short loc_140037131
0x14003711d  cmp     [rbp+57h+var_48], r13b
0x140037121  jz      short loc_140037131
0x140037123  xor     edx, edx; Tag
0x140037125  call    cs:__imp_ExFreePoolWithTag
0x14003712c  nop     dword ptr [rax+rax+00h]
0x140037131  mov     rcx, [rbp+57h+var_38]
0x140037135  xor     rcx, rsp; StackCookie
0x140037138  call    __security_check_cookie
0x14003713d  mov     rbx, [rsp+0D0h+arg_10]
0x140037145  add     rsp, 0A0h
0x14003714c  pop     r15
0x14003714e  pop     r14
0x140037150  pop     r13
0x140037152  pop     r12
0x140037154  pop     rdi
0x140037155  pop     rsi
0x140037156  pop     rbp
0x140037157  retn
```
