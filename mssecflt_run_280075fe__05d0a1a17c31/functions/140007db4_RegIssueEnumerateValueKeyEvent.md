# RegIssueEnumerateValueKeyEvent

- ea: `0x140007db4`
- end: `0x1400080b3`
- name: `RegIssueEnumerateValueKeyEvent`
- size: `767`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x1400080b4`

## callees

- `0x1400061dc`
- `0x140006684`
- `0x140006854`
- `0x140006b6c`
- `0x140006d3c`
- `0x140007870`
- `0x140007db4`
- `0x14000885c`
- `0x140010080`
- `0x1400108b8`
- `0x140011650`
- `0x14003a4c4`
- `0x14003a5b8`
- `0x14003a768`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140007ee6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140007f8f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140007ee6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140007f8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000807f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000807f`
- `ntoskrnl!IoGetCurrentProcess` at `0x140007e58`
- `ntoskrnl!IoGetCurrentProcess` at `0x140007f13`
- `ntoskrnl!IoGetCurrentProcess` at `0x140007fc7`
- `ntoskrnl!IoGetCurrentProcess` at `0x140007e58`
- `ntoskrnl!IoGetCurrentProcess` at `0x140007f13`
- `ntoskrnl!IoGetCurrentProcess` at `0x140007fc7`

## pseudocode

```c
void __fastcall RegIssueEnumerateValueKeyEvent(const UNICODE_STRING *a1, const UNICODE_STRING *a2, unsigned int *a3)
{
  PEPROCESS CurrentProcess; // rax
  __int64 v7; // r8
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

  P = 0;
  v42[0] = 0;
  ListEntry = 0;
  v38 = 0;
  Str = 0;
  v40 = 0;
  v41 = 0;
  Filter = 0;
  v37 = 0;
  if ( a1 )
  {
    if ( !RtlUnicodeStringValidateWorker(a1, 0x7FFFu, 0) )
    {
      if ( a2 )
      {
        if ( !RtlUnicodeStringValidateWorker(a2, 0x7FFFu, 0) )
        {
          if ( a3 )
          {
            CurrentProcess = IoGetCurrentProcess();
            LOBYTE(v7) = 1;
            if ( (int)SecGetProcessContextWithAssertions(CurrentProcess, &ListEntry, v7) >= 0
              && (int)SecGetEffectiveTokenUser(KeGetCurrentThread(), (__int64)ListEntry, &P, v42, 0) >= 0
              && (int)SecUnicodeToNullTerminatedUnicode(a1, &v38) >= 0
              && (int)SecUnicodeToNullTerminatedUnicode(a2, &v40) >= 0 )
            {
              v8 = *((_QWORD *)a3 + 1);
              v9 = *a3;
              if ( (BYTE8(xmmword_14001B740) & 0x40) != 0 )
              {
                SessionsFilterMasksAndAsimovNamespaces = SecGetSessionsFilterMasksAndAsimovNamespaces(v9, v8, &v37);
                if ( SessionsFilterMasksAndAsimovNamespaces < 0 )
                  goto LABEL_17;
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
                  SessionsFilterMasksAndAsimovNamespaces = EventWriteEnumValueKey(
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
                SessionsFilterMasksAndAsimovNamespaces = EventWriteEnumValueKey(
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
  }
LABEL_17:
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
0x140007db4  mov     [rsp-8+arg_18], rbx
0x140007db9  push    rbp
0x140007dba  push    rsi
0x140007dbb  push    rdi
0x140007dbc  push    r12
0x140007dbe  push    r13
0x140007dc0  push    r14
0x140007dc2  push    r15
0x140007dc4  lea     rbp, [rsp-27h]
0x140007dc9  sub     rsp, 0C0h
0x140007dd0  mov     rax, cs:__security_cookie
0x140007dd7  xor     rax, rsp
0x140007dda  mov     [rbp+57h+var_38], rax
0x140007dde  xor     r13d, r13d
0x140007de1  mov     rbx, r8
0x140007de4  mov     [rbp+57h+P], r13
0x140007de8  mov     rdi, rdx
0x140007deb  mov     [rbp+57h+var_48], r13b
0x140007def  mov     rsi, rcx
0x140007df2  mov     [rbp+57h+ListEntry], r13
0x140007df6  mov     [rbp+57h+var_68], r13
0x140007dfa  mov     [rbp+57h+var_60], r13
0x140007dfe  mov     [rbp+57h+var_58], r13
0x140007e02  mov     [rbp+57h+var_50], r13
0x140007e06  mov     [rbp+57h+Filter], r13
0x140007e0a  mov     [rbp+57h+var_70], r13
0x140007e0e  test    rcx, rcx
0x140007e11  jz      loc_140008045
0x140007e17  mov     r14d, 7FFFh
0x140007e1d  xor     r8d, r8d; dwFlags
0x140007e20  mov     edx, r14d; cchMax
0x140007e23  call    RtlUnicodeStringValidateWorker
0x140007e28  test    eax, eax
0x140007e2a  jnz     loc_140008045
0x140007e30  test    rdi, rdi
0x140007e33  jz      loc_140008045
0x140007e39  xor     r8d, r8d; dwFlags
0x140007e3c  mov     edx, r14d; cchMax
0x140007e3f  mov     rcx, rdi; SourceString
0x140007e42  call    RtlUnicodeStringValidateWorker
0x140007e47  test    eax, eax
0x140007e49  jnz     loc_140008045
0x140007e4f  test    rbx, rbx
0x140007e52  jz      loc_140008045
0x140007e58  call    cs:__imp_IoGetCurrentProcess
0x140007e5f  nop     dword ptr [rax+rax+00h]
0x140007e64  mov     r8b, 1
0x140007e67  lea     rdx, [rbp+57h+ListEntry]
0x140007e6b  mov     rcx, rax
0x140007e6e  call    SecGetProcessContextWithAssertions
0x140007e73  test    eax, eax
0x140007e75  js      loc_140008045
0x140007e7b  mov     rcx, gs:188h; Thread
0x140007e84  lea     r9, [rbp+57h+var_48]
0x140007e88  mov     rdx, [rbp+57h+ListEntry]
0x140007e8c  lea     r8, [rbp+57h+P]
0x140007e90  mov     qword ptr [rsp+0F0h+var_D0], r13; __int64
0x140007e95  call    SecGetEffectiveTokenUser
0x140007e9a  test    eax, eax
0x140007e9c  js      loc_140008045
0x140007ea2  lea     rdx, [rbp+57h+var_68]
0x140007ea6  mov     rcx, rsi
0x140007ea9  call    SecUnicodeToNullTerminatedUnicode
0x140007eae  test    eax, eax
0x140007eb0  js      loc_140008045
0x140007eb6  lea     rdx, [rbp+57h+var_58]
0x140007eba  mov     rcx, rdi
0x140007ebd  call    SecUnicodeToNullTerminatedUnicode
0x140007ec2  test    eax, eax
0x140007ec4  js      loc_140008045
0x140007eca  test    byte ptr cs:xmmword_14001B740+8, 40h
0x140007ed1  mov     rdx, [rbx+8]
0x140007ed5  mov     ecx, [rbx]
0x140007ed7  jnz     loc_140007F75
0x140007edd  lea     r8, [rbp+57h+Filter]
0x140007ee1  call    SecGetSessionsFilterMaskFromMatchEntries
0x140007ee6  call    cs:__imp_PsGetCurrentThreadId
0x140007eed  nop     dword ptr [rax+rax+00h]
0x140007ef2  mov     rdx, [rbp+57h+ListEntry]
0x140007ef6  mov     r15, rax
0x140007ef9  mov     rcx, [rbp+57h+P]
0x140007efd  mov     rbx, cs:SecData
0x140007f04  mov     r12d, [rdx+20h]
0x140007f08  mov     rdi, [rdx+30h]
0x140007f0c  mov     rsi, [rcx]
0x140007f0f  mov     r14, [rdx+28h]
0x140007f13  call    cs:__imp_IoGetCurrentProcess
0x140007f1a  nop     dword ptr [rax+rax+00h]
0x140007f1f  mov     rcx, rax
0x140007f22  call    PsGetProcessSessionId_0
0x140007f27  lea     edx, [r13+1]
0x140007f2b  lock xadd [rbx+150h], rdx
0x140007f34  mov     rcx, [rbp+57h+var_50]
0x140007f38  inc     rdx
0x140007f3b  mov     [rsp+0F0h+var_A0], r13b; char
0x140007f40  mov     r9, r14
0x140007f43  mov     qword ptr [rsp+0F0h+var_A8], rdi; char
0x140007f48  mov     r8d, r12d
0x140007f4b  mov     [rsp+0F0h+var_B0], rcx; wchar_t *
0x140007f50  mov     rcx, [rbp+57h+var_60]
0x140007f54  mov     [rsp+0F0h+Str], rcx; Str
0x140007f59  mov     rcx, [rbp+57h+Filter]; Filter
0x140007f5d  mov     dword ptr [rsp+0F0h+var_C0], eax; char
0x140007f61  mov     [rsp+0F0h+Sid], rsi; Sid
0x140007f66  mov     dword ptr [rsp+0F0h+var_D0], r15d; char
0x140007f6b  call    EventWriteEnumValueKey
0x140007f70  jmp     loc_14000803E
0x140007f75  lea     r8, [rbp+57h+var_70]
0x140007f79  call    SecGetSessionsFilterMasksAndAsimovNamespaces
0x140007f7e  test    eax, eax
0x140007f80  js      loc_140008045
0x140007f86  mov     r12, [rbp+57h+var_70]
0x140007f8a  jmp     loc_140008031
0x140007f8f  call    cs:__imp_PsGetCurrentThreadId
0x140007f96  nop     dword ptr [rax+rax+00h]
0x140007f9b  mov     rdx, [rbp+57h+ListEntry]
0x140007f9f  mov     r13, rax
0x140007fa2  mov     rcx, [rbp+57h+P]
0x140007fa6  mov     dil, [r12+8]
0x140007fab  mov     rbx, cs:SecData
0x140007fb2  mov     eax, [rdx+20h]
0x140007fb5  mov     rsi, [rdx+30h]
0x140007fb9  mov     r14, [rcx]
0x140007fbc  mov     r15, [rdx+28h]
0x140007fc0  mov     r12, [r12]
0x140007fc4  mov     [rbp+57h+var_90], eax
0x140007fc7  call    cs:__imp_IoGetCurrentProcess
0x140007fce  nop     dword ptr [rax+rax+00h]
0x140007fd3  mov     rcx, rax
0x140007fd6  call    PsGetProcessSessionId_0
0x140007fdb  mov     edx, 1
0x140007fe0  lock xadd [rbx+150h], rdx
0x140007fe9  mov     r10, [rbp+57h+var_50]
0x140007fed  inc     rdx
0x140007ff0  mov     r8d, [rbp+57h+var_90]
0x140007ff4  mov     r9, r15
0x140007ff7  mov     [rsp+0F0h+var_A0], dil; char
0x140007ffc  mov     rcx, r12; Filter
0x140007fff  mov     qword ptr [rsp+0F0h+var_A8], rsi; char
0x140008004  mov     [rsp+0F0h+var_B0], r10; wchar_t *
0x140008009  mov     r10, [rbp+57h+var_60]
0x14000800d  mov     [rsp+0F0h+Str], r10; Str
0x140008012  mov     dword ptr [rsp+0F0h+var_C0], eax; char
0x140008016  mov     [rsp+0F0h+Sid], r14; Sid
0x14000801b  mov     dword ptr [rsp+0F0h+var_D0], r13d; char
0x140008020  call    EventWriteEnumValueKey
0x140008025  mov     r12, [rbp+57h+var_88]
0x140008029  xor     r13d, r13d
0x14000802c  mov     r12, [r12+10h]
0x140008031  mov     [rbp+57h+var_88], r12
0x140008035  test    r12, r12
0x140008038  jnz     loc_140007F8F
0x14000803e  mov     ecx, eax
0x140008040  call    SecIncrementEtwCounters
0x140008045  mov     rcx, [rbp+57h+var_70]
0x140008049  call    SecReleaseSessionsFilterMasksAndAsimovNamespaces
0x14000804e  lea     rcx, [rbp+57h+var_68]
0x140008052  call    SecFreeNullTerminatedUnicode
0x140008057  lea     rcx, [rbp+57h+var_58]
0x14000805b  call    SecFreeNullTerminatedUnicode
0x140008060  mov     rcx, [rbp+57h+ListEntry]; ListEntry
0x140008064  test    rcx, rcx
0x140008067  jz      short loc_14000806E
0x140008069  call    SecReleaseProcessContext
0x14000806e  mov     rcx, [rbp+57h+P]; P
0x140008072  test    rcx, rcx
0x140008075  jz      short loc_14000808B
0x140008077  cmp     [rbp+57h+var_48], r13b
0x14000807b  jz      short loc_14000808B
0x14000807d  xor     edx, edx; Tag
0x14000807f  call    cs:__imp_ExFreePoolWithTag
0x140008086  nop     dword ptr [rax+rax+00h]
0x14000808b  mov     rcx, [rbp+57h+var_38]
0x14000808f  xor     rcx, rsp; StackCookie
0x140008092  call    __security_check_cookie
0x140008097  mov     rbx, [rsp+0F0h+arg_18]
0x14000809f  add     rsp, 0C0h
0x1400080a6  pop     r15
0x1400080a8  pop     r14
0x1400080aa  pop     r13
0x1400080ac  pop     r12
0x1400080ae  pop     rdi
0x1400080af  pop     rsi
0x1400080b0  pop     rbp
0x1400080b1  retn
```
