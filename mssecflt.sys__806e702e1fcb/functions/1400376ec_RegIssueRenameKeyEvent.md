# RegIssueRenameKeyEvent

- ea: `0x1400376ec`
- end: `0x140037a04`
- name: `RegIssueRenameKeyEvent`
- size: `792`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x140038cd8`

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
- `0x140036258`
- `0x1400376ec`
- `0x14003a4c4`
- `0x14003a5b8`
- `0x14003a768`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140037831`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400378da`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140037831`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400378da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400379ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400379ca`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003779d`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003785e`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037912`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003779d`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003785e`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037912`

## pseudocode

```c
void __fastcall RegIssueRenameKeyEvent(_QWORD *a1)
{
  const UNICODE_STRING *v2; // rcx
  const UNICODE_STRING *v3; // rcx
  PEPROCESS CurrentProcess; // rax
  __int64 v5; // r8
  unsigned int *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  char v9; // r15
  volatile signed __int64 *v10; // rbx
  struct _SLIST_ENTRY *v11; // rdi
  void *Sid; // rsi
  PEPROCESS v13; // rax
  char v14; // al
  int SessionsFilterMasksAndAsimovNamespaces; // eax
  __int64 i; // r12
  char CurrentThreadId; // r13
  char v18; // di
  volatile signed __int64 *v19; // rbx
  struct _SLIST_ENTRY *Next; // rsi
  void *v21; // r14
  ULONG64 v22; // r12
  PEPROCESS v23; // rax
  char ProcessSessionId_0; // al
  __int64 v25; // [rsp+70h] [rbp-21h]
  PSLIST_ENTRY ListEntry; // [rsp+78h] [rbp-19h] BYREF
  PVOID P; // [rsp+80h] [rbp-11h] BYREF
  __int64 v28; // [rsp+88h] [rbp-9h] BYREF
  __int64 v29; // [rsp+90h] [rbp-1h] BYREF
  wchar_t *Str; // [rsp+98h] [rbp+7h]
  __int64 v31; // [rsp+A0h] [rbp+Fh] BYREF
  wchar_t *v32; // [rsp+A8h] [rbp+17h]
  _BYTE v33[8]; // [rsp+B0h] [rbp+1Fh] BYREF
  ULONG64 Filter; // [rsp+B8h] [rbp+27h] BYREF

  P = 0;
  v33[0] = 0;
  ListEntry = 0;
  v29 = 0;
  Str = 0;
  v31 = 0;
  v32 = 0;
  Filter = 0;
  v28 = 0;
  if ( a1 )
  {
    v2 = (const UNICODE_STRING *)a1[5];
    if ( v2 )
    {
      if ( !RtlUnicodeStringValidateWorker(v2, 0x7FFFu, 0) )
      {
        v3 = (const UNICODE_STRING *)a1[6];
        if ( v3 )
        {
          if ( !RtlUnicodeStringValidateWorker(v3, 0x7FFFu, 0) )
          {
            if ( a1[7] )
            {
              CurrentProcess = IoGetCurrentProcess();
              LOBYTE(v5) = 1;
              if ( (int)SecGetProcessContextWithAssertions(CurrentProcess, &ListEntry, v5) >= 0
                && (int)SecGetEffectiveTokenUser(KeGetCurrentThread(), (__int64)ListEntry, &P, v33, 0) >= 0
                && (int)SecUnicodeToNullTerminatedUnicode(a1[5], &v29) >= 0
                && (int)SecUnicodeToNullTerminatedUnicode(a1[6], &v31) >= 0 )
              {
                v6 = (unsigned int *)a1[7];
                v7 = *((_QWORD *)v6 + 1);
                v8 = *v6;
                if ( (BYTE8(xmmword_14001B740) & 0x40) != 0 )
                {
                  SessionsFilterMasksAndAsimovNamespaces = SecGetSessionsFilterMasksAndAsimovNamespaces(v8, v7, &v28);
                  if ( SessionsFilterMasksAndAsimovNamespaces < 0 )
                    goto LABEL_18;
                  for ( i = v28; ; i = *(_QWORD *)(v25 + 16) )
                  {
                    v25 = i;
                    if ( !i )
                      break;
                    CurrentThreadId = (unsigned __int8)PsGetCurrentThreadId();
                    v18 = *(_BYTE *)(i + 8);
                    v19 = (volatile signed __int64 *)SecData;
                    Next = ListEntry[3].Next;
                    v21 = *(void **)P;
                    v22 = *(_QWORD *)i;
                    v23 = IoGetCurrentProcess();
                    ProcessSessionId_0 = PsGetProcessSessionId_0(v23);
                    _InterlockedExchangeAdd64(v19 + 42, 1u);
                    SessionsFilterMasksAndAsimovNamespaces = EventWriteRenameKey(
                                                               v22,
                                                               CurrentThreadId,
                                                               v21,
                                                               ProcessSessionId_0,
                                                               Str,
                                                               v32,
                                                               (char)Next,
                                                               v18);
                  }
                }
                else
                {
                  SecGetSessionsFilterMaskFromMatchEntries(v8, v7, &Filter);
                  v9 = (unsigned __int8)PsGetCurrentThreadId();
                  v10 = (volatile signed __int64 *)SecData;
                  v11 = ListEntry[3].Next;
                  Sid = *(void **)P;
                  v13 = IoGetCurrentProcess();
                  v14 = PsGetProcessSessionId_0(v13);
                  _InterlockedExchangeAdd64(v10 + 42, 1u);
                  SessionsFilterMasksAndAsimovNamespaces = EventWriteRenameKey(
                                                             Filter,
                                                             v9,
                                                             Sid,
                                                             v14,
                                                             Str,
                                                             v32,
                                                             (char)v11,
                                                             0);
                }
                SecIncrementEtwCounters((unsigned int)SessionsFilterMasksAndAsimovNamespaces);
              }
            }
          }
        }
      }
    }
  }
LABEL_18:
  SecReleaseSessionsFilterMasksAndAsimovNamespaces(v28);
  SecFreeNullTerminatedUnicode(&v29);
  SecFreeNullTerminatedUnicode(&v31);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( P )
  {
    if ( v33[0] )
      ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x1400376ec  mov     rax, rsp
0x1400376ef  mov     [rax+10h], rbx
0x1400376f3  mov     [rax+18h], rsi
0x1400376f7  mov     [rax+20h], rdi
0x1400376fb  push    rbp
0x1400376fc  push    r12
0x1400376fe  push    r13
0x140037700  push    r14
0x140037702  push    r15
0x140037704  lea     rbp, [rax-5Fh]
0x140037708  sub     rsp, 0C0h
0x14003770f  mov     rax, cs:__security_cookie
0x140037716  xor     rax, rsp
0x140037719  mov     [rbp+57h+var_28], rax
0x14003771d  xor     r13d, r13d
0x140037720  mov     rbx, rcx
0x140037723  mov     [rbp+57h+P], r13
0x140037727  mov     [rbp+57h+var_38], r13b
0x14003772b  mov     [rbp+57h+ListEntry], r13
0x14003772f  mov     [rbp+57h+var_58], r13
0x140037733  mov     [rbp+57h+var_50], r13
0x140037737  mov     [rbp+57h+var_48], r13
0x14003773b  mov     [rbp+57h+var_40], r13
0x14003773f  mov     [rbp+57h+Filter], r13
0x140037743  mov     [rbp+57h+var_60], r13
0x140037747  test    rcx, rcx
0x14003774a  jz      loc_140037990
0x140037750  mov     rcx, [rcx+28h]; SourceString
0x140037754  test    rcx, rcx
0x140037757  jz      loc_140037990
0x14003775d  mov     edi, 7FFFh
0x140037762  xor     r8d, r8d; dwFlags
0x140037765  mov     edx, edi; cchMax
0x140037767  call    RtlUnicodeStringValidateWorker
0x14003776c  test    eax, eax
0x14003776e  jnz     loc_140037990
0x140037774  mov     rcx, [rbx+30h]; SourceString
0x140037778  test    rcx, rcx
0x14003777b  jz      loc_140037990
0x140037781  xor     r8d, r8d; dwFlags
0x140037784  mov     edx, edi; cchMax
0x140037786  call    RtlUnicodeStringValidateWorker
0x14003778b  test    eax, eax
0x14003778d  jnz     loc_140037990
0x140037793  cmp     [rbx+38h], r13
0x140037797  jz      loc_140037990
0x14003779d  call    cs:__imp_IoGetCurrentProcess
0x1400377a4  nop     dword ptr [rax+rax+00h]
0x1400377a9  mov     r8b, 1
0x1400377ac  lea     rdx, [rbp+57h+ListEntry]
0x1400377b0  mov     rcx, rax
0x1400377b3  call    SecGetProcessContextWithAssertions
0x1400377b8  test    eax, eax
0x1400377ba  js      loc_140037990
0x1400377c0  mov     rcx, gs:188h; Thread
0x1400377c9  lea     r9, [rbp+57h+var_38]
0x1400377cd  mov     rdx, [rbp+57h+ListEntry]
0x1400377d1  lea     r8, [rbp+57h+P]
0x1400377d5  mov     qword ptr [rsp+0E0h+var_C0], r13; __int64
0x1400377da  call    SecGetEffectiveTokenUser
0x1400377df  test    eax, eax
0x1400377e1  js      loc_140037990
0x1400377e7  mov     rcx, [rbx+28h]
0x1400377eb  lea     rdx, [rbp+57h+var_58]
0x1400377ef  call    SecUnicodeToNullTerminatedUnicode
0x1400377f4  test    eax, eax
0x1400377f6  js      loc_140037990
0x1400377fc  mov     rcx, [rbx+30h]
0x140037800  lea     rdx, [rbp+57h+var_48]
0x140037804  call    SecUnicodeToNullTerminatedUnicode
0x140037809  test    eax, eax
0x14003780b  js      loc_140037990
0x140037811  test    byte ptr cs:xmmword_14001B740+8, 40h
0x140037818  mov     rcx, [rbx+38h]
0x14003781c  mov     rdx, [rcx+8]
0x140037820  mov     ecx, [rcx]
0x140037822  jnz     loc_1400378C0
0x140037828  lea     r8, [rbp+57h+Filter]
0x14003782c  call    SecGetSessionsFilterMaskFromMatchEntries
0x140037831  call    cs:__imp_PsGetCurrentThreadId
0x140037838  nop     dword ptr [rax+rax+00h]
0x14003783d  mov     rdx, [rbp+57h+ListEntry]
0x140037841  mov     r15, rax
0x140037844  mov     rcx, [rbp+57h+P]
0x140037848  mov     rbx, cs:SecData
0x14003784f  mov     r12d, [rdx+20h]
0x140037853  mov     rdi, [rdx+30h]
0x140037857  mov     rsi, [rcx]
0x14003785a  mov     r14, [rdx+28h]
0x14003785e  call    cs:__imp_IoGetCurrentProcess
0x140037865  nop     dword ptr [rax+rax+00h]
0x14003786a  mov     rcx, rax
0x14003786d  call    PsGetProcessSessionId_0
0x140037872  lea     edx, [r13+1]
0x140037876  lock xadd [rbx+150h], rdx
0x14003787f  mov     rcx, [rbp+57h+var_40]
0x140037883  inc     rdx
0x140037886  mov     [rsp+0E0h+var_90], r13b; char
0x14003788b  mov     r9, r14
0x14003788e  mov     qword ptr [rsp+0E0h+var_98], rdi; char
0x140037893  mov     r8d, r12d
0x140037896  mov     [rsp+0E0h+var_A0], rcx; wchar_t *
0x14003789b  mov     rcx, [rbp+57h+var_50]
0x14003789f  mov     [rsp+0E0h+Str], rcx; Str
0x1400378a4  mov     rcx, [rbp+57h+Filter]; Filter
0x1400378a8  mov     dword ptr [rsp+0E0h+var_B0], eax; char
0x1400378ac  mov     [rsp+0E0h+Sid], rsi; Sid
0x1400378b1  mov     dword ptr [rsp+0E0h+var_C0], r15d; char
0x1400378b6  call    EventWriteRenameKey
0x1400378bb  jmp     loc_140037989
0x1400378c0  lea     r8, [rbp+57h+var_60]
0x1400378c4  call    SecGetSessionsFilterMasksAndAsimovNamespaces
0x1400378c9  test    eax, eax
0x1400378cb  js      loc_140037990
0x1400378d1  mov     r12, [rbp+57h+var_60]
0x1400378d5  jmp     loc_14003797C
0x1400378da  call    cs:__imp_PsGetCurrentThreadId
0x1400378e1  nop     dword ptr [rax+rax+00h]
0x1400378e6  mov     rdx, [rbp+57h+ListEntry]
0x1400378ea  mov     r13, rax
0x1400378ed  mov     rcx, [rbp+57h+P]
0x1400378f1  mov     dil, [r12+8]
0x1400378f6  mov     rbx, cs:SecData
0x1400378fd  mov     eax, [rdx+20h]
0x140037900  mov     rsi, [rdx+30h]
0x140037904  mov     r14, [rcx]
0x140037907  mov     r15, [rdx+28h]
0x14003790b  mov     r12, [r12]
0x14003790f  mov     [rbp+57h+var_80], eax
0x140037912  call    cs:__imp_IoGetCurrentProcess
0x140037919  nop     dword ptr [rax+rax+00h]
0x14003791e  mov     rcx, rax
0x140037921  call    PsGetProcessSessionId_0
0x140037926  mov     edx, 1
0x14003792b  lock xadd [rbx+150h], rdx
0x140037934  mov     r10, [rbp+57h+var_40]
0x140037938  inc     rdx
0x14003793b  mov     r8d, [rbp+57h+var_80]
0x14003793f  mov     r9, r15
0x140037942  mov     [rsp+0E0h+var_90], dil; char
0x140037947  mov     rcx, r12; Filter
0x14003794a  mov     qword ptr [rsp+0E0h+var_98], rsi; char
0x14003794f  mov     [rsp+0E0h+var_A0], r10; wchar_t *
0x140037954  mov     r10, [rbp+57h+var_50]
0x140037958  mov     [rsp+0E0h+Str], r10; Str
0x14003795d  mov     dword ptr [rsp+0E0h+var_B0], eax; char
0x140037961  mov     [rsp+0E0h+Sid], r14; Sid
0x140037966  mov     dword ptr [rsp+0E0h+var_C0], r13d; char
0x14003796b  call    EventWriteRenameKey
0x140037970  mov     r12, [rbp+57h+var_78]
0x140037974  xor     r13d, r13d
0x140037977  mov     r12, [r12+10h]
0x14003797c  mov     [rbp+57h+var_78], r12
0x140037980  test    r12, r12
0x140037983  jnz     loc_1400378DA
0x140037989  mov     ecx, eax
0x14003798b  call    SecIncrementEtwCounters
0x140037990  mov     rcx, [rbp+57h+var_60]
0x140037994  call    SecReleaseSessionsFilterMasksAndAsimovNamespaces
0x140037999  lea     rcx, [rbp+57h+var_58]
0x14003799d  call    SecFreeNullTerminatedUnicode
0x1400379a2  lea     rcx, [rbp+57h+var_48]
0x1400379a6  call    SecFreeNullTerminatedUnicode
0x1400379ab  mov     rcx, [rbp+57h+ListEntry]; ListEntry
0x1400379af  test    rcx, rcx
0x1400379b2  jz      short loc_1400379B9
0x1400379b4  call    SecReleaseProcessContext
0x1400379b9  mov     rcx, [rbp+57h+P]; P
0x1400379bd  test    rcx, rcx
0x1400379c0  jz      short loc_1400379D6
0x1400379c2  cmp     [rbp+57h+var_38], r13b
0x1400379c6  jz      short loc_1400379D6
0x1400379c8  xor     edx, edx; Tag
0x1400379ca  call    cs:__imp_ExFreePoolWithTag
0x1400379d1  nop     dword ptr [rax+rax+00h]
0x1400379d6  mov     rcx, [rbp+57h+var_28]
0x1400379da  xor     rcx, rsp; StackCookie
0x1400379dd  call    __security_check_cookie
0x1400379e2  lea     r11, [rsp+0E0h+var_20]
0x1400379ea  mov     rbx, [r11+38h]
0x1400379ee  mov     rsi, [r11+40h]
0x1400379f2  mov     rdi, [r11+48h]
0x1400379f6  mov     rsp, r11
0x1400379f9  pop     r15
0x1400379fb  pop     r14
0x1400379fd  pop     r13
0x1400379ff  pop     r12
0x140037a01  pop     rbp
0x140037a02  retn
```
