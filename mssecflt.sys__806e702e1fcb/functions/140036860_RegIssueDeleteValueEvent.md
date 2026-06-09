# RegIssueDeleteValueEvent

- ea: `0x140036860`
- end: `0x140036df3`
- name: `RegIssueDeleteValueEvent`
- size: `1427`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x140038acc`

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
- `0x140035e7c`
- `0x140036860`
- `0x14003a4c4`
- `0x14003a5b8`
- `0x14003a768`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140036a19`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140036afe`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140036bf8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140036cbc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140036a19`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140036afe`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140036bf8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140036cbc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036dbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036dbf`
- `ntoskrnl!RtlLengthSid` at `0x1400369aa`
- `ntoskrnl!RtlLengthSid` at `0x1400369aa`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036904`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036a59`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036b51`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036c25`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036cf4`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036904`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036a59`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036b51`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036c25`
- `ntoskrnl!IoGetCurrentProcess` at `0x140036cf4`

## pseudocode

```c
void __fastcall RegIssueDeleteValueEvent(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  const UNICODE_STRING *v4; // rcx
  PEPROCESS CurrentProcess; // rax
  __int64 v6; // r8
  unsigned int *v7; // rcx
  unsigned __int16 v8; // ax
  unsigned __int16 v9; // cx
  unsigned __int16 v10; // ax
  unsigned int v11; // eax
  unsigned __int8 v12; // al
  __int64 v13; // rcx
  volatile signed __int64 *v14; // rbx
  int v15; // r14d
  __int64 v16; // rdi
  int v17; // r15d
  struct _SLIST_ENTRY *v18; // rsi
  PSID Sid; // r12
  PEPROCESS v20; // rax
  char v21; // al
  int SessionsFilterMasksAndAsimovNamespaces; // eax
  ULONG64 j; // rdi
  unsigned __int8 v24; // al
  __int64 v25; // rcx
  char v26; // si
  volatile signed __int64 *v27; // rbx
  int v28; // r15d
  __int64 v29; // rdi
  int v30; // r12d
  struct _SLIST_ENTRY *v31; // r14
  PSID v32; // r13
  PEPROCESS v33; // rax
  char v34; // al
  char v35; // r15
  volatile signed __int64 *v36; // rbx
  struct _SLIST_ENTRY *v37; // rdi
  PSID v38; // rsi
  PEPROCESS v39; // rax
  char v40; // al
  ULONG64 i; // r12
  char CurrentThreadId; // r13
  char v43; // di
  volatile signed __int64 *v44; // rbx
  struct _SLIST_ENTRY *Next; // rsi
  PSID v46; // r14
  ULONG64 v47; // r12
  PEPROCESS v48; // rax
  char ProcessSessionId_0; // al
  char v50; // [rsp+88h] [rbp-78h]
  ULONG64 *v51; // [rsp+88h] [rbp-78h]
  char v52[8]; // [rsp+88h] [rbp-78h]
  int v53; // [rsp+90h] [rbp-70h]
  char v54; // [rsp+98h] [rbp-68h]
  ULONG64 v55; // [rsp+A8h] [rbp-58h]
  PSLIST_ENTRY ListEntry; // [rsp+B8h] [rbp-48h] BYREF
  PVOID P; // [rsp+C0h] [rbp-40h] BYREF
  ULONG64 v59; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v60; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t *Str; // [rsp+D8h] [rbp-28h]
  __int64 v62; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t *v63; // [rsp+E8h] [rbp-18h]
  char v64[8]; // [rsp+F0h] [rbp-10h] BYREF
  ULONG64 Filter; // [rsp+F8h] [rbp-8h] BYREF

  P = 0;
  v2 = a2;
  v64[0] = 0;
  ListEntry = 0;
  v60 = 0;
  Str = 0;
  v62 = 0;
  v63 = 0;
  Filter = 0;
  v59 = 0;
  if ( a2 )
  {
    v4 = *(const UNICODE_STRING **)(a2 + 40);
    if ( v4 )
    {
      if ( v4->Length )
      {
        if ( !RtlUnicodeStringValidateWorker(v4, 0x7FFFu, 0) )
        {
          if ( *(_QWORD *)(a1 + 8) )
          {
            if ( *(_QWORD *)(v2 + 56) )
            {
              CurrentProcess = IoGetCurrentProcess();
              LOBYTE(v6) = 1;
              if ( (int)SecGetProcessContextWithAssertions(CurrentProcess, &ListEntry, v6) >= 0
                && (int)SecGetEffectiveTokenUser(KeGetCurrentThread(), (__int64)ListEntry, &P, v64, 0) >= 0
                && (int)SecUnicodeToNullTerminatedUnicode(*(_QWORD *)(v2 + 40), &v60) >= 0
                && (int)SecUnicodeToNullTerminatedUnicode(*(_QWORD *)(a1 + 8), &v62) >= 0 )
              {
                SecGetSessionsFilterMaskFromMatchEntries(
                  **(unsigned int **)(v2 + 56),
                  *(_QWORD *)(*(_QWORD *)(v2 + 56) + 8LL),
                  &Filter);
                v7 = *(unsigned int **)(v2 + 56);
                if ( !*((_BYTE *)v7 + 16) || !*(_QWORD *)(v2 + 48) )
                {
                  if ( (BYTE8(xmmword_14001B740) & 0x40) != 0 )
                  {
                    SessionsFilterMasksAndAsimovNamespaces = SecGetSessionsFilterMasksAndAsimovNamespaces(
                                                               *v7,
                                                               *((_QWORD *)v7 + 1),
                                                               &v59);
                    if ( SessionsFilterMasksAndAsimovNamespaces < 0 )
                      goto LABEL_33;
                    for ( i = v59; ; i = *(_QWORD *)(*(_QWORD *)v52 + 16LL) )
                    {
                      *(_QWORD *)v52 = i;
                      if ( !i )
                        break;
                      CurrentThreadId = (unsigned __int8)PsGetCurrentThreadId();
                      v43 = *(_BYTE *)(i + 8);
                      v44 = (volatile signed __int64 *)SecData;
                      Next = ListEntry[3].Next;
                      v46 = *(PSID *)P;
                      v47 = *(_QWORD *)i;
                      v48 = IoGetCurrentProcess();
                      ProcessSessionId_0 = PsGetProcessSessionId_0(v48);
                      _InterlockedExchangeAdd64(v44 + 42, 1u);
                      SessionsFilterMasksAndAsimovNamespaces = EventWriteDeleteValue(
                                                                 v47,
                                                                 CurrentThreadId,
                                                                 v46,
                                                                 ProcessSessionId_0,
                                                                 Str,
                                                                 v63,
                                                                 0,
                                                                 0,
                                                                 0,
                                                                 0,
                                                                 (char)Next,
                                                                 v43);
                    }
                  }
                  else
                  {
                    v35 = (unsigned __int8)PsGetCurrentThreadId();
                    v36 = (volatile signed __int64 *)SecData;
                    v37 = ListEntry[3].Next;
                    v38 = *(PSID *)P;
                    v39 = IoGetCurrentProcess();
                    v40 = PsGetProcessSessionId_0(v39);
                    _InterlockedExchangeAdd64(v36 + 42, 1u);
                    SessionsFilterMasksAndAsimovNamespaces = EventWriteDeleteValue(
                                                               Filter,
                                                               v35,
                                                               v38,
                                                               v40,
                                                               Str,
                                                               v63,
                                                               0,
                                                               0,
                                                               0,
                                                               0,
                                                               (char)v37,
                                                               0);
                  }
                  goto LABEL_32;
                }
                v8 = RtlLengthSid(*(PSID *)P) + 120;
                if ( v8 >= 0x78u )
                {
                  v9 = v60 + v8 + 2;
                  if ( v9 >= v8 )
                  {
                    v10 = v62 + v9 + 2;
                    if ( v10 >= v9 && v10 <= 0xC000u )
                    {
                      v11 = (-16384 - v10) & 0xFFF8;
                      if ( v11 >= *(_DWORD *)(*(_QWORD *)(v2 + 48) + 8LL) )
                        v11 = *(_DWORD *)(*(_QWORD *)(v2 + 48) + 8LL);
                      v53 = v11;
                      if ( (BYTE8(xmmword_14001B740) & 0x40) != 0 )
                      {
                        SessionsFilterMasksAndAsimovNamespaces = SecGetSessionsFilterMasksAndAsimovNamespaces(
                                                                   **(unsigned int **)(v2 + 56),
                                                                   *(_QWORD *)(*(_QWORD *)(v2 + 56) + 8LL),
                                                                   &v59);
                        if ( SessionsFilterMasksAndAsimovNamespaces < 0 )
                          goto LABEL_33;
                        for ( j = v59; ; j = v51[2] )
                        {
                          v51 = (ULONG64 *)j;
                          if ( !j )
                            break;
                          v24 = (unsigned __int8)PsGetCurrentThreadId();
                          v25 = *(_QWORD *)(v2 + 48);
                          v26 = *(_BYTE *)(j + 8);
                          v27 = (volatile signed __int64 *)SecData;
                          v28 = *(_DWORD *)(v25 + 8);
                          v29 = v25 + 12;
                          v30 = *(_DWORD *)(v25 + 4);
                          v31 = ListEntry[3].Next;
                          v54 = v24;
                          v32 = *(PSID *)P;
                          v55 = *v51;
                          v33 = IoGetCurrentProcess();
                          v34 = PsGetProcessSessionId_0(v33);
                          _InterlockedExchangeAdd64(v27 + 42, 1u);
                          SessionsFilterMasksAndAsimovNamespaces = EventWriteDeleteValue(
                                                                     v55,
                                                                     v54,
                                                                     v32,
                                                                     v34,
                                                                     Str,
                                                                     v63,
                                                                     v30,
                                                                     v28,
                                                                     v53,
                                                                     v29,
                                                                     (char)v31,
                                                                     v26);
                          v2 = a2;
                        }
                      }
                      else
                      {
                        v12 = (unsigned __int8)PsGetCurrentThreadId();
                        v13 = *(_QWORD *)(v2 + 48);
                        v14 = (volatile signed __int64 *)SecData;
                        v50 = v12;
                        v15 = *(_DWORD *)(v13 + 8);
                        v16 = v13 + 12;
                        v17 = *(_DWORD *)(v13 + 4);
                        v18 = ListEntry[3].Next;
                        Sid = *(PSID *)P;
                        v20 = IoGetCurrentProcess();
                        v21 = PsGetProcessSessionId_0(v20);
                        _InterlockedExchangeAdd64(v14 + 42, 1u);
                        SessionsFilterMasksAndAsimovNamespaces = EventWriteDeleteValue(
                                                                   Filter,
                                                                   v50,
                                                                   Sid,
                                                                   v21,
                                                                   Str,
                                                                   v63,
                                                                   v17,
                                                                   v15,
                                                                   v53,
                                                                   v16,
                                                                   (char)v18,
                                                                   0);
                      }
LABEL_32:
                      SecIncrementEtwCounters((unsigned int)SessionsFilterMasksAndAsimovNamespaces);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_33:
  SecReleaseSessionsFilterMasksAndAsimovNamespaces(v59);
  SecFreeNullTerminatedUnicode(&v60);
  SecFreeNullTerminatedUnicode(&v62);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( P )
  {
    if ( v64[0] )
      ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x140036860  mov     [rsp-8+arg_10], rbx
0x140036865  push    rbp
0x140036866  push    rsi
0x140036867  push    rdi
0x140036868  push    r12
0x14003686a  push    r13
0x14003686c  push    r14
0x14003686e  push    r15
0x140036870  lea     rbp, [rsp-10h]
0x140036875  sub     rsp, 110h
0x14003687c  mov     rax, cs:__security_cookie
0x140036883  xor     rax, rsp
0x140036886  mov     [rbp+40h+var_40], rax
0x14003688a  xor     r13d, r13d
0x14003688d  mov     [rbp+40h+var_90], rdx
0x140036891  mov     [rbp+40h+P], r13
0x140036895  mov     rbx, rdx
0x140036898  mov     [rbp+40h+var_50], r13b
0x14003689c  mov     rdi, rcx
0x14003689f  mov     [rbp+40h+ListEntry], r13
0x1400368a3  mov     [rbp+40h+var_70], r13
0x1400368a7  mov     [rbp+40h+var_68], r13
0x1400368ab  mov     [rbp+40h+var_60], r13
0x1400368af  mov     [rbp+40h+var_58], r13
0x1400368b3  mov     [rbp+40h+Filter], r13
0x1400368b7  mov     [rbp+40h+var_78], r13
0x1400368bb  test    rdx, rdx
0x1400368be  jz      loc_140036D85
0x1400368c4  mov     rcx, [rdx+28h]; SourceString
0x1400368c8  test    rcx, rcx
0x1400368cb  jz      loc_140036D85
0x1400368d1  cmp     r13w, [rcx]
0x1400368d5  jz      loc_140036D85
0x1400368db  xor     r8d, r8d; dwFlags
0x1400368de  mov     edx, 7FFFh; cchMax
0x1400368e3  call    RtlUnicodeStringValidateWorker
0x1400368e8  test    eax, eax
0x1400368ea  jnz     loc_140036D85
0x1400368f0  cmp     [rdi+8], r13
0x1400368f4  jz      loc_140036D85
0x1400368fa  cmp     [rbx+38h], r13
0x1400368fe  jz      loc_140036D85
0x140036904  call    cs:__imp_IoGetCurrentProcess
0x14003690b  nop     dword ptr [rax+rax+00h]
0x140036910  mov     r8b, 1
0x140036913  lea     rdx, [rbp+40h+ListEntry]
0x140036917  mov     rcx, rax
0x14003691a  call    SecGetProcessContextWithAssertions
0x14003691f  test    eax, eax
0x140036921  js      loc_140036D85
0x140036927  mov     rcx, gs:188h; Thread
0x140036930  lea     r9, [rbp+40h+var_50]
0x140036934  mov     rdx, [rbp+40h+ListEntry]
0x140036938  lea     r8, [rbp+40h+P]
0x14003693c  mov     qword ptr [rsp+140h+var_120], r13; __int64
0x140036941  call    SecGetEffectiveTokenUser
0x140036946  test    eax, eax
0x140036948  js      loc_140036D85
0x14003694e  mov     rcx, [rbx+28h]
0x140036952  lea     rdx, [rbp+40h+var_70]
0x140036956  call    SecUnicodeToNullTerminatedUnicode
0x14003695b  test    eax, eax
0x14003695d  js      loc_140036D85
0x140036963  mov     rcx, [rdi+8]
0x140036967  lea     rdx, [rbp+40h+var_60]
0x14003696b  call    SecUnicodeToNullTerminatedUnicode
0x140036970  test    eax, eax
0x140036972  js      loc_140036D85
0x140036978  mov     rcx, [rbx+38h]
0x14003697c  lea     r8, [rbp+40h+Filter]
0x140036980  mov     rdx, [rcx+8]
0x140036984  mov     ecx, [rcx]
0x140036986  call    SecGetSessionsFilterMaskFromMatchEntries
0x14003698b  mov     rcx, [rbx+38h]
0x14003698f  cmp     [rcx+10h], r13b
0x140036993  jz      loc_140036BEB
0x140036999  cmp     [rbx+30h], r13
0x14003699d  jz      loc_140036BEB
0x1400369a3  mov     rcx, [rbp+40h+P]
0x1400369a7  mov     rcx, [rcx]; Sid
0x1400369aa  call    cs:__imp_RtlLengthSid
0x1400369b1  nop     dword ptr [rax+rax+00h]
0x1400369b6  add     ax, 78h ; 'x'
0x1400369ba  cmp     ax, 78h ; 'x'
0x1400369be  jb      loc_140036D85
0x1400369c4  lea     ecx, [rax+2]
0x1400369c7  add     cx, word ptr [rbp+40h+var_70]
0x1400369cb  cmp     cx, ax
0x1400369ce  jb      loc_140036D85
0x1400369d4  lea     eax, [rcx+2]
0x1400369d7  add     ax, word ptr [rbp+40h+var_60]
0x1400369db  cmp     ax, cx
0x1400369de  jb      loc_140036D85
0x1400369e4  mov     edx, 0C000h
0x1400369e9  cmp     dx, ax
0x1400369ec  jb      loc_140036D85
0x1400369f2  sub     dx, ax
0x1400369f5  mov     rax, [rbx+30h]
0x1400369f9  mov     ecx, [rax+8]
0x1400369fc  movzx   eax, dx
0x1400369ff  and     eax, 0FFF8h
0x140036a04  cmp     eax, ecx
0x140036a06  cmovnb  eax, ecx
0x140036a09  test    byte ptr cs:xmmword_14001B740+8, 40h
0x140036a10  mov     [rbp+40h+var_B0], eax
0x140036a13  jnz     loc_140036ADA
0x140036a19  call    cs:__imp_PsGetCurrentThreadId
0x140036a20  nop     dword ptr [rax+rax+00h]
0x140036a25  mov     rcx, [rbx+30h]
0x140036a29  mov     rdx, [rbp+40h+ListEntry]
0x140036a2d  mov     rbx, cs:SecData
0x140036a34  mov     qword ptr [rbp+40h+var_B8], rax
0x140036a38  mov     r14d, [rcx+8]
0x140036a3c  lea     rdi, [rcx+0Ch]
0x140036a40  mov     r15d, [rcx+4]
0x140036a44  mov     rcx, [rbp+40h+P]
0x140036a48  mov     eax, [rdx+20h]
0x140036a4b  mov     rsi, [rdx+30h]
0x140036a4f  mov     r13, [rdx+28h]
0x140036a53  mov     r12, [rcx]
0x140036a56  mov     [rbp+40h+var_C0], eax
0x140036a59  call    cs:__imp_IoGetCurrentProcess
0x140036a60  nop     dword ptr [rax+rax+00h]
0x140036a65  mov     rcx, rax
0x140036a68  call    PsGetProcessSessionId_0
0x140036a6d  mov     edx, 1
0x140036a72  lock xadd [rbx+150h], rdx
0x140036a7b  mov     r8d, [rbp+40h+var_C0]
0x140036a7f  xor     ecx, ecx
0x140036a81  mov     [rsp+140h+var_D0], cl; char
0x140036a85  inc     rdx
0x140036a88  mov     ecx, [rbp+40h+var_B0]
0x140036a8b  mov     r9, r13
0x140036a8e  mov     qword ptr [rsp+140h+var_D8], rsi; char
0x140036a93  mov     [rsp+140h+var_E0], rdi; __int64
0x140036a98  mov     [rsp+140h+var_E8], ecx; int
0x140036a9c  mov     rcx, [rbp+40h+var_58]
0x140036aa0  mov     dword ptr [rsp+140h+var_F0], r14d; char
0x140036aa5  mov     dword ptr [rsp+140h+var_F8], r15d; char
0x140036aaa  mov     [rsp+140h+var_100], rcx; wchar_t *
0x140036aaf  mov     rcx, [rbp+40h+var_68]
0x140036ab3  mov     [rsp+140h+Str], rcx; Str
0x140036ab8  mov     rcx, [rbp+40h+Filter]; Filter
0x140036abc  mov     dword ptr [rsp+140h+var_110], eax; char
0x140036ac0  mov     rax, qword ptr [rbp+40h+var_B8]
0x140036ac4  mov     [rsp+140h+Sid], r12; Sid
0x140036ac9  mov     dword ptr [rsp+140h+var_120], eax; char
0x140036acd  call    EventWriteDeleteValue
0x140036ad2  xor     r13d, r13d
0x140036ad5  jmp     loc_140036D7E
0x140036ada  mov     rcx, [rbx+38h]
0x140036ade  lea     r8, [rbp+40h+var_78]
0x140036ae2  mov     rdx, [rcx+8]
0x140036ae6  mov     ecx, [rcx]
0x140036ae8  call    SecGetSessionsFilterMasksAndAsimovNamespaces
0x140036aed  test    eax, eax
0x140036aef  js      loc_140036D85
0x140036af5  mov     rdi, [rbp+40h+var_78]
0x140036af9  jmp     loc_140036BD9
0x140036afe  call    cs:__imp_PsGetCurrentThreadId
0x140036b05  nop     dword ptr [rax+rax+00h]
0x140036b0a  mov     rcx, [rbx+30h]
0x140036b0e  mov     rdx, [rbp+40h+ListEntry]
0x140036b12  mov     sil, [rdi+8]
0x140036b16  mov     rbx, cs:SecData
0x140036b1d  mov     r15d, [rcx+8]
0x140036b21  lea     rdi, [rcx+0Ch]
0x140036b25  mov     r12d, [rcx+4]
0x140036b29  mov     rcx, [rbp+40h+P]
0x140036b2d  mov     r14, [rdx+30h]
0x140036b31  mov     qword ptr [rbp+40h+var_A8], rax
0x140036b35  mov     eax, [rdx+20h]
0x140036b38  mov     r13, [rcx]
0x140036b3b  mov     [rbp+40h+var_C0], eax
0x140036b3e  mov     rax, [rdx+28h]
0x140036b42  mov     [rbp+40h+var_A0], rax
0x140036b46  mov     rax, qword ptr [rbp+40h+var_B8]
0x140036b4a  mov     rax, [rax]
0x140036b4d  mov     [rbp+40h+var_98], rax
0x140036b51  call    cs:__imp_IoGetCurrentProcess
0x140036b58  nop     dword ptr [rax+rax+00h]
0x140036b5d  mov     rcx, rax
0x140036b60  call    PsGetProcessSessionId_0
0x140036b65  mov     edx, 1
0x140036b6a  lock xadd [rbx+150h], rdx
0x140036b73  mov     r10, [rbp+40h+var_58]
0x140036b77  inc     rdx
0x140036b7a  mov     ecx, [rbp+40h+var_B0]
0x140036b7d  mov     r9, [rbp+40h+var_A0]
0x140036b81  mov     r8d, [rbp+40h+var_C0]
0x140036b85  mov     [rsp+140h+var_D0], sil; char
0x140036b8a  mov     qword ptr [rsp+140h+var_D8], r14; char
0x140036b8f  mov     [rsp+140h+var_E0], rdi; __int64
0x140036b94  mov     [rsp+140h+var_E8], ecx; int
0x140036b98  mov     rcx, [rbp+40h+var_98]; Filter
0x140036b9c  mov     dword ptr [rsp+140h+var_F0], r15d; char
0x140036ba1  mov     dword ptr [rsp+140h+var_F8], r12d; char
0x140036ba6  mov     [rsp+140h+var_100], r10; wchar_t *
0x140036bab  mov     r10, [rbp+40h+var_68]
0x140036baf  mov     [rsp+140h+Str], r10; Str
0x140036bb4  mov     dword ptr [rsp+140h+var_110], eax; char
0x140036bb8  mov     rax, qword ptr [rbp+40h+var_A8]
0x140036bbc  mov     [rsp+140h+Sid], r13; Sid
0x140036bc1  mov     dword ptr [rsp+140h+var_120], eax; char
0x140036bc5  call    EventWriteDeleteValue
0x140036bca  mov     rdi, qword ptr [rbp+40h+var_B8]
0x140036bce  xor     r13d, r13d
0x140036bd1  mov     rbx, [rbp+40h+var_90]
0x140036bd5  mov     rdi, [rdi+10h]
0x140036bd9  mov     qword ptr [rbp+40h+var_B8], rdi
0x140036bdd  test    rdi, rdi
0x140036be0  jnz     loc_140036AFE
0x140036be6  jmp     loc_140036D7E
0x140036beb  test    byte ptr cs:xmmword_14001B740+8, 40h
0x140036bf2  jnz     loc_140036C9C
0x140036bf8  call    cs:__imp_PsGetCurrentThreadId
0x140036bff  nop     dword ptr [rax+rax+00h]
0x140036c04  mov     rdx, [rbp+40h+ListEntry]
0x140036c08  mov     r15, rax
0x140036c0b  mov     rcx, [rbp+40h+P]
0x140036c0f  mov     rbx, cs:SecData
0x140036c16  mov     r12d, [rdx+20h]
0x140036c1a  mov     rdi, [rdx+30h]
0x140036c1e  mov     rsi, [rcx]
0x140036c21  mov     r14, [rdx+28h]
0x140036c25  call    cs:__imp_IoGetCurrentProcess
0x140036c2c  nop     dword ptr [rax+rax+00h]
0x140036c31  mov     rcx, rax
0x140036c34  call    PsGetProcessSessionId_0
0x140036c39  mov     edx, 1
0x140036c3e  lock xadd [rbx+150h], rdx
0x140036c47  mov     rcx, [rbp+40h+var_58]
0x140036c4b  inc     rdx
0x140036c4e  mov     [rsp+140h+var_D0], r13b; char
0x140036c53  mov     r9, r14
0x140036c56  mov     qword ptr [rsp+140h+var_D8], rdi; char
0x140036c5b  mov     r8d, r12d
0x140036c5e  mov     [rsp+140h+var_E0], r13; __int64
0x140036c63  mov     [rsp+140h+var_E8], r13d; int
0x140036c68  mov     dword ptr [rsp+140h+var_F0], r13d; char
0x140036c6d  mov     dword ptr [rsp+140h+var_F8], r13d; char
0x140036c72  mov     [rsp+140h+var_100], rcx; wchar_t *
0x140036c77  mov     rcx, [rbp+40h+var_68]
0x140036c7b  mov     [rsp+140h+Str], rcx; Str
0x140036c80  mov     rcx, [rbp+40h+Filter]; Filter
0x140036c84  mov     dword ptr [rsp+140h+var_110], eax; char
0x140036c88  mov     [rsp+140h+Sid], rsi; Sid
0x140036c8d  mov     dword ptr [rsp+140h+var_120], r15d; char
0x140036c92  call    EventWriteDeleteValue
0x140036c97  jmp     loc_140036D7E
0x140036c9c  mov     rdx, [rcx+8]
0x140036ca0  lea     r8, [rbp+40h+var_78]
0x140036ca4  mov     ecx, [rcx]
0x140036ca6  call    SecGetSessionsFilterMasksAndAsimovNamespaces
0x140036cab  test    eax, eax
0x140036cad  js      loc_140036D85
0x140036cb3  mov     r12, [rbp+40h+var_78]
0x140036cb7  jmp     loc_140036D71
0x140036cbc  call    cs:__imp_PsGetCurrentThreadId
0x140036cc3  nop     dword ptr [rax+rax+00h]
0x140036cc8  mov     rdx, [rbp+40h+ListEntry]
0x140036ccc  mov     r13, rax
0x140036ccf  mov     rcx, [rbp+40h+P]
0x140036cd3  mov     dil, [r12+8]
0x140036cd8  mov     rbx, cs:SecData
0x140036cdf  mov     eax, [rdx+20h]
0x140036ce2  mov     rsi, [rdx+30h]
0x140036ce6  mov     r14, [rcx]
0x140036ce9  mov     r15, [rdx+28h]
0x140036ced  mov     r12, [r12]
0x140036cf1  mov     [rbp+40h+var_C0], eax
0x140036cf4  call    cs:__imp_IoGetCurrentProcess
0x140036cfb  nop     dword ptr [rax+rax+00h]
0x140036d00  mov     rcx, rax
0x140036d03  call    PsGetProcessSessionId_0
0x140036d08  mov     edx, 1
0x140036d0d  lock xadd [rbx+150h], rdx
0x140036d16  mov     r10, [rbp+40h+var_58]
0x140036d1a  xor     ecx, ecx
0x140036d1c  mov     r8d, [rbp+40h+var_C0]
0x140036d20  inc     rdx
0x140036d23  mov     [rsp+140h+var_D0], dil; char
0x140036d28  mov     r9, r15
0x140036d2b  mov     qword ptr [rsp+140h+var_D8], rsi; char
0x140036d30  mov     [rsp+140h+var_E0], rcx; __int64
0x140036d35  mov     [rsp+140h+var_E8], ecx; int
0x140036d39  mov     dword ptr [rsp+140h+var_F0], ecx; char
0x140036d3d  mov     dword ptr [rsp+140h+var_F8], ecx; char
0x140036d41  mov     rcx, r12; Filter
0x140036d44  mov     [rsp+140h+var_100], r10; wchar_t *
0x140036d49  mov     r10, [rbp+40h+var_68]
0x140036d4d  mov     [rsp+140h+Str], r10; Str
0x140036d52  mov     dword ptr [rsp+140h+var_110], eax; char
0x140036d56  mov     [rsp+140h+Sid], r14; Sid
0x140036d5b  mov     dword ptr [rsp+140h+var_120], r13d; char
0x140036d60  call    EventWriteDeleteValue
0x140036d65  mov     r12, qword ptr [rbp+40h+var_B8]
0x140036d69  xor     r13d, r13d
0x140036d6c  mov     r12, [r12+10h]
0x140036d71  mov     qword ptr [rbp+40h+var_B8], r12
  ... truncated ...
```
