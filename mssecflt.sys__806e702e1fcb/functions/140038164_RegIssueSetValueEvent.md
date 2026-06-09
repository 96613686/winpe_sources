# RegIssueSetValueEvent

- ea: `0x140038164`
- end: `0x1400389c1`
- name: `RegIssueSetValueEvent`
- size: `2141`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x140038d5c`

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
- `0x1400365d8`
- `0x140038164`
- `0x14003a4c4`
- `0x14003a5b8`
- `0x14003a768`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400382b7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140038320`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400383ff`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003860b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140038790`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400388b6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400382b7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140038320`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400383ff`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003860b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140038790`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400388b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003872c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003872c`
- `ntoskrnl!RtlLengthSid` at `0x1400384e8`
- `ntoskrnl!RtlLengthSid` at `0x1400384e8`
- `ntoskrnl!IoGetCurrentProcess` at `0x140038213`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400382e4`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003834d`
- `ntoskrnl!IoGetCurrentProcess` at `0x140038437`
- `ntoskrnl!IoGetCurrentProcess` at `0x140038647`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400387cc`
- `ntoskrnl!IoGetCurrentProcess` at `0x140038904`
- `ntoskrnl!IoGetCurrentProcess` at `0x140038213`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400382e4`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003834d`
- `ntoskrnl!IoGetCurrentProcess` at `0x140038437`
- `ntoskrnl!IoGetCurrentProcess` at `0x140038647`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400387cc`
- `ntoskrnl!IoGetCurrentProcess` at `0x140038904`

## pseudocode

```c
void __fastcall RegIssueSetValueEvent(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v3; // r13
  const UNICODE_STRING *v4; // rcx
  PEPROCESS CurrentProcess; // rax
  __int64 v6; // r8
  unsigned int *v7; // rcx
  char v8; // r15
  volatile signed __int64 *v9; // rbx
  struct _SLIST_ENTRY *v10; // rdi
  PSID Sid; // rsi
  PEPROCESS v12; // rax
  char v13; // cl
  volatile signed __int64 *v14; // rbx
  PEPROCESS v15; // rax
  int SessionsFilterMasksAndAsimovNamespaces; // eax
  __int64 i; // r12
  char CurrentThreadId; // r13
  char v19; // di
  volatile signed __int64 *v20; // rbx
  struct _SLIST_ENTRY *Next; // rsi
  PSID v22; // r14
  ULONG64 v23; // r12
  PEPROCESS v24; // rax
  char ProcessSessionId_0; // al
  unsigned __int16 v26; // ax
  unsigned __int16 v27; // cx
  unsigned __int16 v28; // ax
  __int64 v29; // r8
  unsigned int v30; // edx
  unsigned int *v31; // r10
  int *v32; // r15
  unsigned int v33; // eax
  unsigned int v34; // r10d
  unsigned int v35; // ecx
  unsigned int v36; // edi
  int v37; // r9d
  unsigned int v38; // eax
  unsigned int v39; // edx
  unsigned int v40; // r9d
  unsigned int v41; // edx
  unsigned int v42; // ecx
  __int64 v43; // rax
  unsigned __int8 v44; // al
  __int64 v45; // rsi
  int v46; // r14d
  int v47; // r15d
  struct _SLIST_ENTRY *v48; // rdi
  PSID v49; // r12
  volatile signed __int64 *v50; // rbx
  PEPROCESS v51; // rax
  char v52; // cl
  __int64 v53; // rax
  unsigned __int8 v54; // al
  __int64 v55; // rsi
  int v56; // r14d
  int v57; // r15d
  struct _SLIST_ENTRY *v58; // rdi
  PSID v59; // r12
  volatile signed __int64 *v60; // rbx
  PEPROCESS v61; // rax
  char v62; // cl
  ULONG64 j; // rdi
  __int64 v64; // rax
  __int64 v65; // rcx
  unsigned __int8 v66; // al
  __int64 v67; // r14
  int v68; // r12d
  char v69; // di
  struct _SLIST_ENTRY *v70; // rsi
  int v71; // r15d
  PSID v72; // r13
  volatile signed __int64 *v73; // rbx
  PEPROCESS v74; // rax
  char v75; // al
  char v76; // [rsp+90h] [rbp-90h]
  char v77[4]; // [rsp+A0h] [rbp-80h]
  char v78[4]; // [rsp+A0h] [rbp-80h]
  char v79[4]; // [rsp+A0h] [rbp-80h]
  char v80[4]; // [rsp+A4h] [rbp-7Ch]
  char v81[4]; // [rsp+A4h] [rbp-7Ch]
  char v82[4]; // [rsp+A4h] [rbp-7Ch]
  unsigned int v83; // [rsp+A8h] [rbp-78h]
  unsigned int v84; // [rsp+ACh] [rbp-74h]
  __int64 v85; // [rsp+B8h] [rbp-68h]
  __int64 v86; // [rsp+B8h] [rbp-68h]
  __int64 v87; // [rsp+B8h] [rbp-68h]
  ULONG64 *v88; // [rsp+B8h] [rbp-68h]
  char v89[8]; // [rsp+C0h] [rbp-60h]
  char v90; // [rsp+C0h] [rbp-60h]
  char v91; // [rsp+C0h] [rbp-60h]
  __int64 v92; // [rsp+C8h] [rbp-58h]
  char v93; // [rsp+D0h] [rbp-50h]
  ULONG64 v94; // [rsp+E0h] [rbp-40h]
  PSLIST_ENTRY ListEntry; // [rsp+F8h] [rbp-28h] BYREF
  PVOID P; // [rsp+100h] [rbp-20h] BYREF
  __int64 v99; // [rsp+108h] [rbp-18h] BYREF
  wchar_t *Str; // [rsp+110h] [rbp-10h]
  __int64 v101; // [rsp+118h] [rbp-8h] BYREF
  wchar_t *v102; // [rsp+120h] [rbp+0h]
  ULONG64 v103; // [rsp+128h] [rbp+8h] BYREF
  char v104[8]; // [rsp+130h] [rbp+10h] BYREF
  ULONG64 Filter; // [rsp+138h] [rbp+18h] BYREF

  v2 = a2;
  P = 0;
  v3 = a1;
  v104[0] = 0;
  ListEntry = 0;
  v99 = 0;
  Str = 0;
  v101 = 0;
  v102 = 0;
  Filter = 0;
  v103 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v4 = *(const UNICODE_STRING **)(a2 + 40);
      if ( v4 )
      {
        if ( v4->Length )
        {
          if ( !RtlUnicodeStringValidateWorker(v4, 0x7FFFu, 0) )
          {
            if ( *(_QWORD *)(v3 + 8) )
            {
              if ( *(_QWORD *)(v2 + 72) )
              {
                CurrentProcess = IoGetCurrentProcess();
                LOBYTE(v6) = 1;
                if ( (int)SecGetProcessContextWithAssertions(CurrentProcess, &ListEntry, v6) >= 0
                  && (int)SecGetEffectiveTokenUser(KeGetCurrentThread(), (__int64)ListEntry, &P, v104, 0) >= 0
                  && (int)SecUnicodeToNullTerminatedUnicode(*(_QWORD *)(v2 + 40), &v99) >= 0
                  && (int)SecUnicodeToNullTerminatedUnicode(*(_QWORD *)(v3 + 8), &v101) >= 0 )
                {
                  if ( !*(_BYTE *)(v2 + 80) )
                    SecGetSessionsFilterMaskFromMatchEntries(
                      **(unsigned int **)(v2 + 72),
                      *(_QWORD *)(*(_QWORD *)(v2 + 72) + 8LL),
                      &Filter);
                  v7 = *(unsigned int **)(v2 + 72);
                  if ( !*((_BYTE *)v7 + 16) )
                  {
                    if ( (BYTE8(xmmword_14001B740) & 0x40) != 0 )
                    {
                      if ( *(_BYTE *)(v2 + 80) != 1 )
                      {
                        SessionsFilterMasksAndAsimovNamespaces = SecGetSessionsFilterMasksAndAsimovNamespaces(
                                                                   *v7,
                                                                   *((_QWORD *)v7 + 1),
                                                                   &v103);
                        if ( SessionsFilterMasksAndAsimovNamespaces < 0 )
                          goto LABEL_57;
                        for ( i = v103; ; i = *(_QWORD *)(v85 + 16) )
                        {
                          v85 = i;
                          if ( !i )
                            break;
                          CurrentThreadId = (unsigned __int8)PsGetCurrentThreadId();
                          v19 = *(_BYTE *)(i + 8);
                          v20 = (volatile signed __int64 *)SecData;
                          Next = ListEntry[3].Next;
                          v22 = *(PSID *)P;
                          v23 = *(_QWORD *)i;
                          v24 = IoGetCurrentProcess();
                          ProcessSessionId_0 = PsGetProcessSessionId_0(v24);
                          _InterlockedExchangeAdd64(v20 + 42, 1u);
                          SessionsFilterMasksAndAsimovNamespaces = EventWriteSetValue(
                                                                     v23,
                                                                     CurrentThreadId,
                                                                     v22,
                                                                     ProcessSessionId_0,
                                                                     Str,
                                                                     v102,
                                                                     0,
                                                                     0,
                                                                     0,
                                                                     0,
                                                                     0,
                                                                     0,
                                                                     0,
                                                                     0,
                                                                     (char)Next,
                                                                     v19);
                        }
                        goto LABEL_56;
                      }
                      v8 = (unsigned __int8)PsGetCurrentThreadId();
                      v14 = (volatile signed __int64 *)SecData;
                      v10 = ListEntry[3].Next;
                      Sid = *(PSID *)P;
                      v15 = IoGetCurrentProcess();
                      v13 = PsGetProcessSessionId_0(v15);
                      _InterlockedExchangeAdd64(v14 + 42, 1u);
                      v76 = -1;
                    }
                    else
                    {
                      v8 = (unsigned __int8)PsGetCurrentThreadId();
                      v9 = (volatile signed __int64 *)SecData;
                      v10 = ListEntry[3].Next;
                      Sid = *(PSID *)P;
                      v12 = IoGetCurrentProcess();
                      v13 = PsGetProcessSessionId_0(v12);
                      _InterlockedIncrement64(v9 + 42);
                      v76 = 0;
                    }
                    SessionsFilterMasksAndAsimovNamespaces = EventWriteSetValue(
                                                               Filter,
                                                               v8,
                                                               Sid,
                                                               v13,
                                                               Str,
                                                               v102,
                                                               0,
                                                               0,
                                                               0,
                                                               0,
                                                               0,
                                                               0,
                                                               0,
                                                               0,
                                                               (char)v10,
                                                               v76);
LABEL_56:
                    SecIncrementEtwCounters((unsigned int)SessionsFilterMasksAndAsimovNamespaces);
                    goto LABEL_57;
                  }
                  v26 = RtlLengthSid(*(PSID *)P) + 132;
                  if ( v26 >= 0x84u )
                  {
                    v27 = v99 + v26 + 2;
                    if ( v27 >= v26 )
                    {
                      v28 = v101 + v27 + 2;
                      if ( v28 >= v27 && v28 <= 0xC000u )
                      {
                        v29 = *(_QWORD *)(v2 + 56);
                        v30 = (-16384 - v28) & 0xFFF8;
                        v31 = (unsigned int *)(v29 + 8);
                        if ( !v29 )
                        {
                          v32 = (int *)(v3 + 32);
                          v83 = 0;
                          v33 = *(_DWORD *)(v3 + 32);
                          *(_QWORD *)v89 = v3 + 32;
                          if ( v33 >= v30 )
                            v33 = v30;
                          v84 = v33;
                          goto LABEL_49;
                        }
                        v34 = *v31;
                        v35 = 8 * (v30 >> 4);
                        v36 = v35;
                        if ( v34 > v35 )
                          v37 = 8 * (v30 >> 4);
                        else
                          v37 = *(unsigned __int16 *)(v29 + 8);
                        v32 = (int *)(v3 + 32);
                        v83 = v37;
                        v38 = *(_DWORD *)(v3 + 32);
                        *(_QWORD *)v89 = v3 + 32;
                        if ( v38 <= v35 )
                          v35 = *(_DWORD *)(v3 + 32);
                        v84 = v35;
                        if ( v34 <= v36 )
                        {
                          v31 = (unsigned int *)(v29 + 8);
                          if ( v38 <= v36 )
                          {
LABEL_49:
                            if ( (BYTE8(xmmword_14001B740) & 0x40) == 0 )
                            {
                              v43 = v29 + 12;
                              if ( !v29 )
                                v43 = 0;
                              v86 = v43;
                              if ( v29 )
                              {
                                *(_DWORD *)v77 = *(_DWORD *)(v29 + 4);
                                *(_DWORD *)v80 = *v31;
                              }
                              else
                              {
                                v77[0] = 0;
                                v80[0] = 0;
                              }
                              v44 = (unsigned __int8)PsGetCurrentThreadId();
                              v45 = *(_QWORD *)(v3 + 24);
                              v46 = *(_DWORD *)(v3 + 32);
                              v47 = *(_DWORD *)(v3 + 20);
                              v48 = ListEntry[3].Next;
                              v49 = *(PSID *)P;
                              v50 = (volatile signed __int64 *)SecData;
                              v90 = v44;
                              v51 = IoGetCurrentProcess();
                              v52 = PsGetProcessSessionId_0(v51);
                              _InterlockedIncrement64(v50 + 42);
                              SessionsFilterMasksAndAsimovNamespaces = EventWriteSetValue(
                                                                         Filter,
                                                                         v90,
                                                                         v49,
                                                                         v52,
                                                                         Str,
                                                                         v102,
                                                                         v77[0],
                                                                         v80[0],
                                                                         v83,
                                                                         v86,
                                                                         v47,
                                                                         v46,
                                                                         v84,
                                                                         v45,
                                                                         (char)v48,
                                                                         0);
                              goto LABEL_56;
                            }
                            if ( *(_BYTE *)(v2 + 80) == 1 )
                            {
                              v53 = v29 + 12;
                              if ( !v29 )
                                v53 = 0;
                              v87 = v53;
                              if ( v29 )
                              {
                                *(_DWORD *)v81 = *(_DWORD *)(v29 + 4);
                                *(_DWORD *)v78 = *v31;
                              }
                              else
                              {
                                v81[0] = 0;
                                v78[0] = 0;
                              }
                              v54 = (unsigned __int8)PsGetCurrentThreadId();
                              v55 = *(_QWORD *)(v3 + 24);
                              v56 = *(_DWORD *)(v3 + 32);
                              v57 = *(_DWORD *)(v3 + 20);
                              v58 = ListEntry[3].Next;
                              v59 = *(PSID *)P;
                              v60 = (volatile signed __int64 *)SecData;
                              v91 = v54;
                              v61 = IoGetCurrentProcess();
                              v62 = PsGetProcessSessionId_0(v61);
                              _InterlockedIncrement64(v60 + 42);
                              SessionsFilterMasksAndAsimovNamespaces = EventWriteSetValue(
                                                                         0,
                                                                         v91,
                                                                         v59,
                                                                         v62,
                                                                         Str,
                                                                         v102,
                                                                         v81[0],
                                                                         v78[0],
                                                                         v83,
                                                                         v87,
                                                                         v57,
                                                                         v56,
                                                                         v84,
                                                                         v55,
                                                                         (char)v58,
                                                                         255);
                              goto LABEL_56;
                            }
                            SessionsFilterMasksAndAsimovNamespaces = SecGetSessionsFilterMasksAndAsimovNamespaces(
                                                                       **(unsigned int **)(v2 + 72),
                                                                       *(_QWORD *)(*(_QWORD *)(v2 + 72) + 8LL),
                                                                       &v103);
                            if ( SessionsFilterMasksAndAsimovNamespaces >= 0 )
                            {
                              for ( j = v103; ; j = v88[2] )
                              {
                                v88 = (ULONG64 *)j;
                                if ( !j )
                                  break;
                                v64 = *(_QWORD *)(v2 + 56);
                                v65 = v64 + 12;
                                if ( !v64 )
                                  v65 = 0;
                                v92 = v65;
                                if ( v64 )
                                {
                                  *(_DWORD *)v79 = *(_DWORD *)(v64 + 8);
                                  *(_DWORD *)v82 = *(_DWORD *)(v64 + 4);
                                }
                                else
                                {
                                  v82[0] = 0;
                                  v79[0] = 0;
                                }
                                v66 = (unsigned __int8)PsGetCurrentThreadId();
                                v67 = *(_QWORD *)(v3 + 24);
                                v68 = *(_DWORD *)(v3 + 20);
                                v69 = *(_BYTE *)(j + 8);
                                v70 = ListEntry[3].Next;
                                v71 = *v32;
                                v72 = *(PSID *)P;
                                v73 = (volatile signed __int64 *)SecData;
                                v93 = v66;
                                v94 = *v88;
                                v74 = IoGetCurrentProcess();
                                v75 = PsGetProcessSessionId_0(v74);
                                _InterlockedExchangeAdd64(v73 + 42, 1u);
                                SessionsFilterMasksAndAsimovNamespaces = EventWriteSetValue(
                                                                           v94,
                                                                           v93,
                                                                           v72,
                                                                           v75,
                                                                           Str,
                                                                           v102,
                                                                           v82[0],
                                                                           v79[0],
                                                                           v83,
                                                                           v92,
                                                                           v68,
                                                                           v71,
                                                                           v84,
                                                                           v67,
                                                                           (char)v70,
                                                                           v69);
                                v2 = a2;
                                v3 = a1;
                                v32 = *(int **)v89;
                              }
                              goto LABEL_56;
                            }
                            goto LABEL_57;
                          }
                          v41 = v30 - v37;
                          v42 = *(_DWORD *)(v3 + 32);
                          if ( v38 >= v41 )
                            v42 = v41;
                          v84 = v42 & 0xFFFFFFF8;
                        }
                        else
                        {
                          if ( v38 <= v36 )
                          {
                            v39 = v30 - v35;
                            v40 = v34;
                            if ( v34 >= v39 )
                              v40 = v39;
                            v83 = v40 & 0xFFFFFFF8;
                          }
                          v31 = (unsigned int *)(v29 + 8);
                        }
                        *(_QWORD *)v89 = v3 + 32;
                        goto LABEL_49;
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
  }
LABEL_57:
  SecReleaseSessionsFilterMasksAndAsimovNamespaces(v103);
  SecFreeNullTerminatedUnicode(&v99);
  SecFreeNullTerminatedUnicode(&v101);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( P )
  {
    if ( v104[0] )
      ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x140038164  mov     [rsp-8+arg_10], rbx
0x140038169  push    rbp
0x14003816a  push    rsi
0x14003816b  push    rdi
0x14003816c  push    r12
0x14003816e  push    r13
0x140038170  push    r14
0x140038172  push    r15
0x140038174  lea     rbp, [rsp-30h]
0x140038179  sub     rsp, 150h
0x140038180  mov     rax, cs:__security_cookie
0x140038187  xor     rax, rsp
0x14003818a  mov     [rbp+60h+var_40], rax
0x14003818e  xor     edi, edi
0x140038190  mov     [rbp+60h+var_98], rdx
0x140038194  mov     [rbp+60h+var_90], rcx
0x140038198  mov     rbx, rdx
0x14003819b  mov     [rbp+60h+P], rdi
0x14003819f  mov     r13, rcx
0x1400381a2  mov     [rbp+60h+var_50], dil
0x1400381a6  mov     [rbp+60h+ListEntry], rdi
0x1400381aa  mov     [rbp+60h+var_78], rdi
0x1400381ae  mov     [rbp+60h+var_70], rdi
0x1400381b2  mov     [rbp+60h+var_68], rdi
0x1400381b6  mov     [rbp+60h+var_60], rdi
0x1400381ba  mov     [rbp+60h+Filter], rdi
0x1400381be  mov     [rbp+60h+var_58], rdi
0x1400381c2  test    rcx, rcx
0x1400381c5  jz      loc_1400386F2
0x1400381cb  test    rdx, rdx
0x1400381ce  jz      loc_1400386F2
0x1400381d4  mov     rcx, [rdx+28h]; SourceString
0x1400381d8  test    rcx, rcx
0x1400381db  jz      loc_1400386F2
0x1400381e1  cmp     di, [rcx]
0x1400381e4  jz      loc_1400386F2
0x1400381ea  xor     r8d, r8d; dwFlags
0x1400381ed  mov     edx, 7FFFh; cchMax
0x1400381f2  call    RtlUnicodeStringValidateWorker
0x1400381f7  test    eax, eax
0x1400381f9  jnz     loc_1400386F2
0x1400381ff  cmp     [r13+8], rdi
0x140038203  jz      loc_1400386F2
0x140038209  cmp     [rbx+48h], rdi
0x14003820d  jz      loc_1400386F2
0x140038213  call    cs:__imp_IoGetCurrentProcess
0x14003821a  nop     dword ptr [rax+rax+00h]
0x14003821f  mov     r8b, 1
0x140038222  lea     rdx, [rbp+60h+ListEntry]
0x140038226  mov     rcx, rax
0x140038229  call    SecGetProcessContextWithAssertions
0x14003822e  test    eax, eax
0x140038230  js      loc_1400386F2
0x140038236  mov     rcx, gs:188h; Thread
0x14003823f  lea     r9, [rbp+60h+var_50]
0x140038243  mov     rdx, [rbp+60h+ListEntry]
0x140038247  lea     r8, [rbp+60h+P]
0x14003824b  mov     qword ptr [rsp+180h+var_160], rdi; __int64
0x140038250  call    SecGetEffectiveTokenUser
0x140038255  test    eax, eax
0x140038257  js      loc_1400386F2
0x14003825d  mov     rcx, [rbx+28h]
0x140038261  lea     rdx, [rbp+60h+var_78]
0x140038265  call    SecUnicodeToNullTerminatedUnicode
0x14003826a  test    eax, eax
0x14003826c  js      loc_1400386F2
0x140038272  mov     rcx, [r13+8]
0x140038276  lea     rdx, [rbp+60h+var_68]
0x14003827a  call    SecUnicodeToNullTerminatedUnicode
0x14003827f  test    eax, eax
0x140038281  js      loc_1400386F2
0x140038287  cmp     [rbx+50h], dil
0x14003828b  jnz     short loc_1400382A0
0x14003828d  mov     rcx, [rbx+48h]
0x140038291  lea     r8, [rbp+60h+Filter]
0x140038295  mov     rdx, [rcx+8]
0x140038299  mov     ecx, [rcx]
0x14003829b  call    SecGetSessionsFilterMaskFromMatchEntries
0x1400382a0  mov     rcx, [rbx+48h]
0x1400382a4  cmp     [rcx+10h], dil
0x1400382a8  jnz     loc_1400384E1
0x1400382ae  test    byte ptr cs:xmmword_14001B740+8, 40h
0x1400382b5  jnz     short loc_140038316
0x1400382b7  call    cs:__imp_PsGetCurrentThreadId
0x1400382be  nop     dword ptr [rax+rax+00h]
0x1400382c3  mov     rdx, [rbp+60h+ListEntry]
0x1400382c7  mov     r15, rax
0x1400382ca  mov     rcx, [rbp+60h+P]
0x1400382ce  mov     rbx, cs:SecData
0x1400382d5  mov     r12d, [rdx+20h]
0x1400382d9  mov     rdi, [rdx+30h]
0x1400382dd  mov     rsi, [rcx]
0x1400382e0  mov     r14, [rdx+28h]
0x1400382e4  call    cs:__imp_IoGetCurrentProcess
0x1400382eb  nop     dword ptr [rax+rax+00h]
0x1400382f0  mov     rcx, rax
0x1400382f3  call    PsGetProcessSessionId_0
0x1400382f8  mov     ecx, eax
0x1400382fa  mov     edx, 1
0x1400382ff  lock xadd [rbx+150h], rdx
0x140038308  inc     rdx
0x14003830b  xor     eax, eax
0x14003830d  mov     [rsp+180h+var_F0], al
0x140038314  jmp     short loc_14003837C
0x140038316  cmp     byte ptr [rbx+50h], 1
0x14003831a  jnz     loc_1400383DF
0x140038320  call    cs:__imp_PsGetCurrentThreadId
0x140038327  nop     dword ptr [rax+rax+00h]
0x14003832c  mov     rdx, [rbp+60h+ListEntry]
0x140038330  mov     r15, rax
0x140038333  mov     rcx, [rbp+60h+P]
0x140038337  mov     rbx, cs:SecData
0x14003833e  mov     r12d, [rdx+20h]
0x140038342  mov     rdi, [rdx+30h]
0x140038346  mov     rsi, [rcx]
0x140038349  mov     r14, [rdx+28h]
0x14003834d  call    cs:__imp_IoGetCurrentProcess
0x140038354  nop     dword ptr [rax+rax+00h]
0x140038359  mov     rcx, rax
0x14003835c  call    PsGetProcessSessionId_0
0x140038361  mov     ecx, eax
0x140038363  mov     edx, 1
0x140038368  lock xadd [rbx+150h], rdx
0x140038371  inc     rdx
0x140038374  mov     [rsp+180h+var_F0], 0FFh; char
0x14003837c  mov     rax, [rbp+60h+var_60]
0x140038380  mov     r9, r14
0x140038383  mov     qword ptr [rsp+180h+var_F8], rdi; char
0x14003838b  mov     r8d, r12d
0x14003838e  xor     edi, edi
0x140038390  mov     [rsp+180h+var_100], rdi; __int64
0x140038398  mov     [rsp+180h+var_108], edi; int
0x14003839c  mov     dword ptr [rsp+180h+var_110], edi; char
0x1400383a0  mov     dword ptr [rsp+180h+var_118], edi; char
0x1400383a4  mov     [rsp+180h+var_120], rdi; __int64
0x1400383a9  mov     [rsp+180h+var_128], edi; int
0x1400383ad  mov     dword ptr [rsp+180h+var_130], edi; char
0x1400383b1  mov     dword ptr [rsp+180h+var_138], edi; char
0x1400383b5  mov     [rsp+180h+var_140], rax; wchar_t *
0x1400383ba  mov     rax, [rbp+60h+var_70]
0x1400383be  mov     [rsp+180h+Str], rax; Str
0x1400383c3  mov     dword ptr [rsp+180h+var_150], ecx; char
0x1400383c7  mov     rcx, [rbp+60h+Filter]; Filter
0x1400383cb  mov     [rsp+180h+Sid], rsi; Sid
0x1400383d0  mov     dword ptr [rsp+180h+var_160], r15d; char
0x1400383d5  call    EventWriteSetValue
0x1400383da  jmp     loc_1400386EB
0x1400383df  mov     rdx, [rcx+8]
0x1400383e3  lea     r8, [rbp+60h+var_58]
0x1400383e7  mov     ecx, [rcx]
0x1400383e9  call    SecGetSessionsFilterMasksAndAsimovNamespaces
0x1400383ee  test    eax, eax
0x1400383f0  js      loc_1400386F2
0x1400383f6  mov     r12, [rbp+60h+var_58]
0x1400383fa  jmp     loc_1400384CF
0x1400383ff  call    cs:__imp_PsGetCurrentThreadId
0x140038406  nop     dword ptr [rax+rax+00h]
0x14003840b  mov     rdx, [rbp+60h+ListEntry]
0x14003840f  mov     r13, rax
0x140038412  mov     rcx, [rbp+60h+P]
0x140038416  mov     dil, [r12+8]
0x14003841b  mov     rbx, cs:SecData
0x140038422  mov     eax, [rdx+20h]
0x140038425  mov     rsi, [rdx+30h]
0x140038429  mov     r14, [rcx]
0x14003842c  mov     r15, [rdx+28h]
0x140038430  mov     r12, [r12]
0x140038434  mov     dword ptr [rbp+60h+var_E0], eax
0x140038437  call    cs:__imp_IoGetCurrentProcess
0x14003843e  nop     dword ptr [rax+rax+00h]
0x140038443  mov     rcx, rax
0x140038446  call    PsGetProcessSessionId_0
0x14003844b  mov     r10d, eax
0x14003844e  mov     edx, 1
0x140038453  lock xadd [rbx+150h], rdx
0x14003845c  mov     rax, [rbp+60h+var_60]
0x140038460  inc     rdx
0x140038463  mov     r8d, dword ptr [rbp+60h+var_E0]
0x140038467  mov     r9, r15
0x14003846a  mov     [rsp+180h+var_F0], dil; char
0x140038472  mov     rcx, r12; Filter
0x140038475  mov     qword ptr [rsp+180h+var_F8], rsi; char
0x14003847d  xor     edi, edi
0x14003847f  mov     [rsp+180h+var_100], rdi; __int64
0x140038487  mov     [rsp+180h+var_108], edi; int
0x14003848b  mov     dword ptr [rsp+180h+var_110], edi; char
0x14003848f  mov     dword ptr [rsp+180h+var_118], edi; char
0x140038493  mov     [rsp+180h+var_120], rdi; __int64
0x140038498  mov     [rsp+180h+var_128], edi; int
0x14003849c  mov     dword ptr [rsp+180h+var_130], edi; char
0x1400384a0  mov     dword ptr [rsp+180h+var_138], edi; char
0x1400384a4  mov     [rsp+180h+var_140], rax; wchar_t *
0x1400384a9  mov     rax, [rbp+60h+var_70]
0x1400384ad  mov     [rsp+180h+Str], rax; Str
0x1400384b2  mov     dword ptr [rsp+180h+var_150], r10d; char
0x1400384b7  mov     [rsp+180h+Sid], r14; Sid
0x1400384bc  mov     dword ptr [rsp+180h+var_160], r13d; char
0x1400384c1  call    EventWriteSetValue
0x1400384c6  mov     r12, [rbp+60h+var_C8]
0x1400384ca  mov     r12, [r12+10h]
0x1400384cf  mov     [rbp+60h+var_C8], r12
0x1400384d3  test    r12, r12
0x1400384d6  jnz     loc_1400383FF
0x1400384dc  jmp     loc_1400386EB
0x1400384e1  mov     rcx, [rbp+60h+P]
0x1400384e5  mov     rcx, [rcx]; Sid
0x1400384e8  call    cs:__imp_RtlLengthSid
0x1400384ef  nop     dword ptr [rax+rax+00h]
0x1400384f4  mov     ecx, 84h
0x1400384f9  add     ax, cx
0x1400384fc  cmp     ax, cx
0x1400384ff  jb      loc_1400386F2
0x140038505  lea     ecx, [rax+2]
0x140038508  add     cx, word ptr [rbp+60h+var_78]
0x14003850c  cmp     cx, ax
0x14003850f  jb      loc_1400386F2
0x140038515  lea     eax, [rcx+2]
0x140038518  add     ax, word ptr [rbp+60h+var_68]
0x14003851c  cmp     ax, cx
0x14003851f  jb      loc_1400386F2
0x140038525  mov     ecx, 0C000h
0x14003852a  cmp     cx, ax
0x14003852d  jb      loc_1400386F2
0x140038533  mov     r8, [rbx+38h]
0x140038537  sub     cx, ax
0x14003853a  movzx   edx, cx
0x14003853d  and     edx, 0FFF8h
0x140038543  lea     r10, [r8+8]
0x140038547  test    r8, r8
0x14003854a  jnz     short loc_140038564
0x14003854c  lea     r15, [r13+20h]
0x140038550  mov     [rbp+60h+var_D8], edi
0x140038553  mov     eax, [r15]
0x140038556  cmp     eax, edx
0x140038558  mov     qword ptr [rbp+60h+var_C0], r15
0x14003855c  cmovnb  eax, edx
0x14003855f  mov     [rbp+60h+var_D4], eax
0x140038562  jmp     short loc_1400385D8
0x140038564  mov     ecx, edx
0x140038566  mov     r11, r10
0x140038569  mov     r10d, [r10]
0x14003856c  shr     ecx, 4
0x14003856f  shl     ecx, 3
0x140038572  mov     edi, ecx
0x140038574  cmp     r10d, ecx
0x140038577  ja      short loc_14003857F
0x140038579  movzx   r9d, word ptr [r11]
0x14003857d  jmp     short loc_140038582
0x14003857f  mov     r9d, ecx
0x140038582  lea     r15, [r13+20h]
0x140038586  mov     [rbp+60h+var_D8], r9d
0x14003858a  mov     eax, [r15]
0x14003858d  cmp     eax, ecx
0x14003858f  mov     qword ptr [rbp+60h+var_C0], r15
0x140038593  cmovbe  ecx, eax
0x140038596  mov     [rbp+60h+var_D4], ecx
0x140038599  cmp     r10d, edi
0x14003859c  jbe     short loc_1400385BB
0x14003859e  cmp     eax, edi
0x1400385a0  ja      short loc_1400385B6
0x1400385a2  sub     edx, ecx
0x1400385a4  mov     r9d, r10d
0x1400385a7  cmp     r10d, edx
0x1400385aa  cmovnb  r9d, edx
0x1400385ae  and     r9d, 0FFFFFFF8h
0x1400385b2  mov     [rbp+60h+var_D8], r9d
0x1400385b6  mov     r10, r11
0x1400385b9  jmp     short loc_1400385D2
0x1400385bb  mov     r10, r11
0x1400385be  cmp     eax, edi
0x1400385c0  jbe     short loc_1400385D6
0x1400385c2  sub     edx, r9d
0x1400385c5  mov     ecx, eax
0x1400385c7  cmp     eax, edx
0x1400385c9  cmovnb  ecx, edx
0x1400385cc  and     ecx, 0FFFFFFF8h
0x1400385cf  mov     [rbp+60h+var_D4], ecx
0x1400385d2  mov     qword ptr [rbp+60h+var_C0], r15
0x1400385d6  xor     edi, edi
0x1400385d8  test    byte ptr cs:xmmword_14001B740+8, 40h
0x1400385df  jnz     loc_140038760
0x1400385e5  test    r8, r8
0x1400385e8  lea     rax, [r8+0Ch]
0x1400385ec  cmovz   rax, rdi
0x1400385f0  mov     [rbp+60h+var_C8], rax
0x1400385f4  jz      short loc_140038605
0x1400385f6  mov     eax, [r8+4]
0x1400385fa  mov     dword ptr [rbp+60h+var_E0], eax
0x1400385fd  mov     eax, [r10]
0x140038600  mov     dword ptr [rbp+60h+var_DC], eax
0x140038603  jmp     short loc_14003860B
0x140038605  mov     dword ptr [rbp+60h+var_E0], edi
0x140038608  mov     dword ptr [rbp+60h+var_DC], edi
0x14003860b  call    cs:__imp_PsGetCurrentThreadId
0x140038612  nop     dword ptr [rax+rax+00h]
0x140038617  mov     rdx, [rbp+60h+ListEntry]
0x14003861b  mov     rcx, [rbp+60h+P]
0x14003861f  mov     rsi, [r13+18h]
0x140038623  mov     r14d, [r13+20h]
0x140038627  mov     r15d, [r13+14h]
  ... truncated ...
```
