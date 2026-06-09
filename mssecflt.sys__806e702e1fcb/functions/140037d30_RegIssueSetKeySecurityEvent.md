# RegIssueSetKeySecurityEvent

- ea: `0x140037d30`
- end: `0x140038161`
- name: `RegIssueSetKeySecurityEvent`
- size: `1073`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400082f8`

## callees

- `0x1400061dc`
- `0x140006684`
- `0x140006854`
- `0x140006b6c`
- `0x140006d3c`
- `0x140007bb0`
- `0x14000885c`
- `0x140010080`
- `0x1400108b8`
- `0x140011610`
- `0x140011650`
- `0x140037d30`
- `0x14003a4c4`
- `0x14003a5b8`
- `0x14003a768`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140037f2b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140037fea`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140037f2b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140037fea`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140037e98`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140037e98`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400380ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038116`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003812d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400380ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038116`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003812d`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037eac`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037f5e`
- `ntoskrnl!IoGetCurrentProcess` at `0x140038029`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037eac`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037f5e`
- `ntoskrnl!IoGetCurrentProcess` at `0x140038029`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037e19`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037e68`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037e19`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037e68`

## pseudocode

```c
void __fastcall RegIssueSetKeySecurityEvent(_QWORD *a1, __int64 a2)
{
  const UNICODE_STRING *v3; // rcx
  __int64 v4; // rsi
  PEPROCESS CurrentProcess; // rax
  __int64 v6; // r8
  unsigned int *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  char v10; // r12
  volatile signed __int64 *v11; // rbx
  int v12; // edi
  struct _SLIST_ENTRY *v13; // rsi
  void *Sid; // r14
  PEPROCESS v15; // rax
  char v16; // al
  int SessionsFilterMasksAndAsimovNamespaces; // eax
  __int64 i; // r13
  unsigned __int8 CurrentThreadId; // al
  char v20; // di
  volatile signed __int64 *v21; // rbx
  struct _SLIST_ENTRY *Next; // r14
  int v23; // esi
  ULONG64 v24; // r13
  void *v25; // r15
  PEPROCESS v26; // rax
  char ProcessSessionId_0; // al
  __int64 v28; // [rsp+78h] [rbp-88h]
  char v29; // [rsp+80h] [rbp-80h]
  PSLIST_ENTRY ListEntry; // [rsp+90h] [rbp-70h] BYREF
  PVOID P; // [rsp+98h] [rbp-68h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-60h] BYREF
  PCWSTR SourceString; // [rsp+A8h] [rbp-58h] BYREF
  PCWSTR v35; // [rsp+B0h] [rbp-50h] BYREF
  UNICODE_STRING String2; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v38; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t *Str; // [rsp+E0h] [rbp-20h]
  __int64 v40; // [rsp+E8h] [rbp-18h] BYREF
  wchar_t *v41; // [rsp+F0h] [rbp-10h]
  __int64 v42; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t *v43; // [rsp+100h] [rbp+0h]
  _BYTE v44[4]; // [rsp+108h] [rbp+8h] BYREF
  int v45; // [rsp+10Ch] [rbp+Ch] BYREF
  int v46; // [rsp+110h] [rbp+10h] BYREF
  ULONG64 Filter; // [rsp+118h] [rbp+18h] BYREF

  P = 0;
  v3 = (const UNICODE_STRING *)a1[5];
  v4 = a2;
  v44[0] = 0;
  ListEntry = 0;
  v38 = 0;
  Str = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  *(_QWORD *)&String2.Length = 0;
  String2.Buffer = 0;
  SourceString = 0;
  v45 = 0;
  v35 = 0;
  v46 = 0;
  Filter = 0;
  v33 = 0;
  if ( v3 && !RtlUnicodeStringValidateWorker(v3, 0x7FFFu, 0) && a1[7] )
  {
    if ( !qword_140020038 )
      goto LABEL_33;
    if ( (int)qword_140020038(a1[6], 1, **(unsigned int **)(v4 + 8), &SourceString, &v45) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
      SecUnicodeToNullTerminatedUnicode(&DestinationString, &v40);
    }
    if ( (int)qword_140020038(*(_QWORD *)(v4 + 16), 1, **(unsigned int **)(v4 + 8), &v35, &v46) >= 0 )
    {
      RtlInitUnicodeString(&String2, v35);
      SecUnicodeToNullTerminatedUnicode(&String2, &v42);
    }
    if ( !DestinationString.Buffer || !String2.Buffer || RtlCompareUnicodeString(&DestinationString, &String2, 1u) )
    {
LABEL_33:
      CurrentProcess = IoGetCurrentProcess();
      LOBYTE(v6) = 1;
      if ( (int)SecGetProcessContextWithAssertions(CurrentProcess, &ListEntry, v6) >= 0
        && (int)SecGetEffectiveTokenUser(KeGetCurrentThread(), (__int64)ListEntry, &P, v44, 0) >= 0
        && (int)SecUnicodeToNullTerminatedUnicode(a1[5], &v38) >= 0 )
      {
        v7 = (unsigned int *)a1[7];
        v8 = *((_QWORD *)v7 + 1);
        v9 = *v7;
        if ( (BYTE8(xmmword_14001B740) & 0x40) != 0 )
        {
          SessionsFilterMasksAndAsimovNamespaces = SecGetSessionsFilterMasksAndAsimovNamespaces(v9, v8, &v33);
          if ( SessionsFilterMasksAndAsimovNamespaces < 0 )
            goto LABEL_22;
          for ( i = v33; ; i = *(_QWORD *)(v28 + 16) )
          {
            v28 = i;
            if ( !i )
              break;
            CurrentThreadId = (unsigned __int8)PsGetCurrentThreadId();
            v20 = *(_BYTE *)(i + 8);
            v21 = (volatile signed __int64 *)SecData;
            Next = ListEntry[3].Next;
            v23 = **(_DWORD **)(v4 + 8);
            v24 = *(_QWORD *)i;
            v29 = CurrentThreadId;
            v25 = *(void **)P;
            v26 = IoGetCurrentProcess();
            ProcessSessionId_0 = PsGetProcessSessionId_0(v26);
            _InterlockedExchangeAdd64(v21 + 42, 1u);
            SessionsFilterMasksAndAsimovNamespaces = EventWriteSetKeySecurity(
                                                       v24,
                                                       v29,
                                                       v25,
                                                       ProcessSessionId_0,
                                                       Str,
                                                       (char)Next,
                                                       v23,
                                                       v41,
                                                       v43,
                                                       v20);
            v4 = a2;
          }
        }
        else
        {
          SecGetSessionsFilterMaskFromMatchEntries(v9, v8, &Filter);
          v10 = (unsigned __int8)PsGetCurrentThreadId();
          v11 = (volatile signed __int64 *)SecData;
          v12 = **(_DWORD **)(v4 + 8);
          v13 = ListEntry[3].Next;
          Sid = *(void **)P;
          v15 = IoGetCurrentProcess();
          v16 = PsGetProcessSessionId_0(v15);
          _InterlockedExchangeAdd64(v11 + 42, 1u);
          SessionsFilterMasksAndAsimovNamespaces = EventWriteSetKeySecurity(
                                                     Filter,
                                                     v10,
                                                     Sid,
                                                     v16,
                                                     Str,
                                                     (char)v13,
                                                     v12,
                                                     v41,
                                                     v43,
                                                     0);
        }
        SecIncrementEtwCounters((unsigned int)SessionsFilterMasksAndAsimovNamespaces);
      }
    }
  }
LABEL_22:
  SecReleaseSessionsFilterMasksAndAsimovNamespaces(v33);
  SecFreeNullTerminatedUnicode(&v38);
  SecFreeNullTerminatedUnicode(&v40);
  SecFreeNullTerminatedUnicode(&v42);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( P && v44[0] )
    ExFreePoolWithTag(P, 0);
  if ( SourceString )
    ExFreePoolWithTag((PVOID)SourceString, 0);
  if ( v35 )
    ExFreePoolWithTag((PVOID)v35, 0);
}

```

## disassembly

```asm
0x140037d30  mov     [rsp-8+arg_10], rbx
0x140037d35  push    rbp
0x140037d36  push    rsi
0x140037d37  push    rdi
0x140037d38  push    r12
0x140037d3a  push    r13
0x140037d3c  push    r14
0x140037d3e  push    r15
0x140037d40  lea     rbp, [rsp-30h]
0x140037d45  sub     rsp, 130h
0x140037d4c  mov     rax, cs:__security_cookie
0x140037d53  xor     rax, rsp
0x140037d56  mov     [rbp+60h+var_40], rax
0x140037d5a  xor     edi, edi
0x140037d5c  mov     [rbp+60h+var_D8], rdx
0x140037d60  mov     rbx, rcx
0x140037d63  mov     [rbp+60h+P], rdi
0x140037d67  mov     rcx, [rcx+28h]; SourceString
0x140037d6b  mov     rsi, rdx
0x140037d6e  mov     [rbp+60h+var_58], dil
0x140037d72  mov     [rbp+60h+ListEntry], rdi
0x140037d76  mov     [rbp+60h+var_88], rdi
0x140037d7a  mov     [rbp+60h+var_80], rdi
0x140037d7e  mov     [rbp+60h+var_78], rdi
0x140037d82  mov     [rbp+60h+var_70], rdi
0x140037d86  mov     [rbp+60h+var_68], rdi
0x140037d8a  mov     [rbp+60h+var_60], rdi
0x140037d8e  mov     qword ptr [rbp+60h+DestinationString.Length], rdi
0x140037d92  mov     [rbp+60h+DestinationString.Buffer], rdi
0x140037d96  mov     qword ptr [rbp+60h+String2.Length], rdi
0x140037d9a  mov     [rbp+60h+String2.Buffer], rdi
0x140037d9e  mov     [rbp+60h+SourceString], rdi
0x140037da2  mov     [rbp+60h+var_54], edi
0x140037da5  mov     [rbp+60h+var_B0], rdi
0x140037da9  mov     [rbp+60h+var_50], edi
0x140037dac  mov     [rbp+60h+Filter], rdi
0x140037db0  mov     [rbp+60h+var_C0], rdi
0x140037db4  test    rcx, rcx
0x140037db7  jz      loc_1400380BC
0x140037dbd  xor     r8d, r8d; dwFlags
0x140037dc0  mov     edx, 7FFFh; cchMax
0x140037dc5  call    RtlUnicodeStringValidateWorker
0x140037dca  test    eax, eax
0x140037dcc  jnz     loc_1400380BC
0x140037dd2  cmp     [rbx+38h], rdi
0x140037dd6  jz      loc_1400380BC
0x140037ddc  mov     rax, cs:qword_140020038
0x140037de3  test    rax, rax
0x140037de6  jz      loc_140037EAC
0x140037dec  mov     r8, [rsi+8]
0x140037df0  lea     rcx, [rbp+60h+var_54]
0x140037df4  mov     qword ptr [rsp+160h+var_140], rcx
0x140037df9  lea     r9, [rbp+60h+SourceString]
0x140037dfd  mov     rcx, [rbx+30h]
0x140037e01  lea     edx, [rdi+1]
0x140037e04  mov     r8d, [r8]
0x140037e07  call    cs:__guard_dispatch_icall_fptr
0x140037e0d  test    eax, eax
0x140037e0f  js      short loc_140037E32
0x140037e11  mov     rdx, [rbp+60h+SourceString]; SourceString
0x140037e15  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x140037e19  call    cs:__imp_RtlInitUnicodeString
0x140037e20  nop     dword ptr [rax+rax+00h]
0x140037e25  lea     rdx, [rbp+60h+var_78]
0x140037e29  lea     rcx, [rbp+60h+DestinationString]
0x140037e2d  call    SecUnicodeToNullTerminatedUnicode
0x140037e32  mov     r8, [rsi+8]
0x140037e36  lea     rcx, [rbp+60h+var_50]
0x140037e3a  mov     rax, cs:qword_140020038
0x140037e41  lea     r9, [rbp+60h+var_B0]
0x140037e45  mov     qword ptr [rsp+160h+var_140], rcx
0x140037e4a  mov     edx, 1
0x140037e4f  mov     rcx, [rsi+10h]
0x140037e53  mov     r8d, [r8]
0x140037e56  call    cs:__guard_dispatch_icall_fptr
0x140037e5c  test    eax, eax
0x140037e5e  js      short loc_140037E81
0x140037e60  mov     rdx, [rbp+60h+var_B0]; SourceString
0x140037e64  lea     rcx, [rbp+60h+String2]; DestinationString
0x140037e68  call    cs:__imp_RtlInitUnicodeString
0x140037e6f  nop     dword ptr [rax+rax+00h]
0x140037e74  lea     rdx, [rbp+60h+var_68]
0x140037e78  lea     rcx, [rbp+60h+String2]
0x140037e7c  call    SecUnicodeToNullTerminatedUnicode
0x140037e81  cmp     [rbp+60h+DestinationString.Buffer], rdi
0x140037e85  jz      short loc_140037EAC
0x140037e87  cmp     [rbp+60h+String2.Buffer], rdi
0x140037e8b  jz      short loc_140037EAC
0x140037e8d  mov     r8b, 1; CaseInSensitive
0x140037e90  lea     rdx, [rbp+60h+String2]; String2
0x140037e94  lea     rcx, [rbp+60h+DestinationString]; String1
0x140037e98  call    cs:__imp_RtlCompareUnicodeString
0x140037e9f  nop     dword ptr [rax+rax+00h]
0x140037ea4  test    eax, eax
0x140037ea6  jz      loc_1400380BC
0x140037eac  call    cs:__imp_IoGetCurrentProcess
0x140037eb3  nop     dword ptr [rax+rax+00h]
0x140037eb8  mov     r8b, 1
0x140037ebb  lea     rdx, [rbp+60h+ListEntry]
0x140037ebf  mov     rcx, rax
0x140037ec2  call    SecGetProcessContextWithAssertions
0x140037ec7  test    eax, eax
0x140037ec9  js      loc_1400380BC
0x140037ecf  mov     rcx, gs:188h; Thread
0x140037ed8  lea     r9, [rbp+60h+var_58]
0x140037edc  mov     rdx, [rbp+60h+ListEntry]
0x140037ee0  lea     r8, [rbp+60h+P]
0x140037ee4  mov     qword ptr [rsp+160h+var_140], rdi; __int64
0x140037ee9  call    SecGetEffectiveTokenUser
0x140037eee  test    eax, eax
0x140037ef0  js      loc_1400380BC
0x140037ef6  mov     rcx, [rbx+28h]
0x140037efa  lea     rdx, [rbp+60h+var_88]
0x140037efe  call    SecUnicodeToNullTerminatedUnicode
0x140037f03  test    eax, eax
0x140037f05  js      loc_1400380BC
0x140037f0b  test    byte ptr cs:xmmword_14001B740+8, 40h
0x140037f12  mov     rcx, [rbx+38h]
0x140037f16  mov     rdx, [rcx+8]
0x140037f1a  mov     ecx, [rcx]
0x140037f1c  jnz     loc_140037FD0
0x140037f22  lea     r8, [rbp+60h+Filter]
0x140037f26  call    SecGetSessionsFilterMaskFromMatchEntries
0x140037f2b  call    cs:__imp_PsGetCurrentThreadId
0x140037f32  nop     dword ptr [rax+rax+00h]
0x140037f37  mov     rcx, [rsi+8]
0x140037f3b  mov     r12, rax
0x140037f3e  mov     rdx, [rbp+60h+ListEntry]
0x140037f42  mov     rbx, cs:SecData
0x140037f49  mov     edi, [rcx]
0x140037f4b  mov     rcx, [rbp+60h+P]
0x140037f4f  mov     r13d, [rdx+20h]
0x140037f53  mov     rsi, [rdx+30h]
0x140037f57  mov     r15, [rdx+28h]
0x140037f5b  mov     r14, [rcx]
0x140037f5e  call    cs:__imp_IoGetCurrentProcess
0x140037f65  nop     dword ptr [rax+rax+00h]
0x140037f6a  mov     rcx, rax
0x140037f6d  call    PsGetProcessSessionId_0
0x140037f72  mov     edx, 1
0x140037f77  lock xadd [rbx+150h], rdx
0x140037f80  mov     rcx, [rbp+60h+var_60]
0x140037f84  inc     rdx
0x140037f87  mov     [rsp+160h+var_100], 0; char
0x140037f8c  mov     r9, r15
0x140037f8f  mov     [rsp+160h+var_108], rcx; wchar_t *
0x140037f94  mov     r8d, r13d
0x140037f97  mov     rcx, [rbp+60h+var_70]
0x140037f9b  mov     [rsp+160h+var_110], rcx; wchar_t *
0x140037fa0  mov     rcx, [rbp+60h+var_80]
0x140037fa4  mov     dword ptr [rsp+160h+var_118], edi; char
0x140037fa8  mov     qword ptr [rsp+160h+var_120], rsi; char
0x140037fad  mov     [rsp+160h+Str], rcx; Str
0x140037fb2  mov     rcx, [rbp+60h+Filter]; Filter
0x140037fb6  mov     dword ptr [rsp+160h+var_130], eax; char
0x140037fba  mov     [rsp+160h+Sid], r14; Sid
0x140037fbf  mov     dword ptr [rsp+160h+var_140], r12d; char
0x140037fc4  call    EventWriteSetKeySecurity
0x140037fc9  xor     edi, edi
0x140037fcb  jmp     loc_1400380B5
0x140037fd0  lea     r8, [rbp+60h+var_C0]
0x140037fd4  call    SecGetSessionsFilterMasksAndAsimovNamespaces
0x140037fd9  test    eax, eax
0x140037fdb  js      loc_1400380BC
0x140037fe1  mov     r13, [rbp+60h+var_C0]
0x140037fe5  jmp     loc_1400380A7
0x140037fea  call    cs:__imp_PsGetCurrentThreadId
0x140037ff1  nop     dword ptr [rax+rax+00h]
0x140037ff6  mov     rdx, [rbp+60h+ListEntry]
0x140037ffa  mov     rcx, [rsi+8]
0x140037ffe  mov     dil, [r13+8]
0x140038002  mov     rbx, cs:SecData
0x140038009  mov     r14, [rdx+30h]
0x14003800d  mov     esi, [rcx]
0x14003800f  mov     rcx, [rbp+60h+P]
0x140038013  mov     r12, [rdx+28h]
0x140038017  mov     r13, [r13+0]
0x14003801b  mov     qword ptr [rbp+60h+var_E0], rax
0x14003801f  mov     eax, [rdx+20h]
0x140038022  mov     r15, [rcx]
0x140038025  mov     [rsp+160h+var_F0], eax
0x140038029  call    cs:__imp_IoGetCurrentProcess
0x140038030  nop     dword ptr [rax+rax+00h]
0x140038035  mov     rcx, rax
0x140038038  call    PsGetProcessSessionId_0
0x14003803d  mov     edx, 1
0x140038042  lock xadd [rbx+150h], rdx
0x14003804b  mov     r10, [rbp+60h+var_60]
0x14003804f  inc     rdx
0x140038052  mov     r8d, [rsp+160h+var_F0]
0x140038057  mov     r9, r12
0x14003805a  mov     [rsp+160h+var_100], dil; char
0x14003805f  mov     rcx, r13; Filter
0x140038062  mov     [rsp+160h+var_108], r10; wchar_t *
0x140038067  mov     r10, [rbp+60h+var_70]
0x14003806b  mov     [rsp+160h+var_110], r10; wchar_t *
0x140038070  mov     r10, [rbp+60h+var_80]
0x140038074  mov     dword ptr [rsp+160h+var_118], esi; char
0x140038078  mov     qword ptr [rsp+160h+var_120], r14; char
0x14003807d  mov     [rsp+160h+Str], r10; Str
0x140038082  mov     dword ptr [rsp+160h+var_130], eax; char
0x140038086  mov     rax, qword ptr [rbp+60h+var_E0]
0x14003808a  mov     [rsp+160h+Sid], r15; Sid
0x14003808f  mov     dword ptr [rsp+160h+var_140], eax; char
0x140038093  call    EventWriteSetKeySecurity
0x140038098  mov     r13, [rsp+160h+var_E8]
0x14003809d  xor     edi, edi
0x14003809f  mov     rsi, [rbp+60h+var_D8]
0x1400380a3  mov     r13, [r13+10h]
0x1400380a7  mov     [rsp+160h+var_E8], r13
0x1400380ac  test    r13, r13
0x1400380af  jnz     loc_140037FEA
0x1400380b5  mov     ecx, eax
0x1400380b7  call    SecIncrementEtwCounters
0x1400380bc  mov     rcx, [rbp+60h+var_C0]
0x1400380c0  call    SecReleaseSessionsFilterMasksAndAsimovNamespaces
0x1400380c5  lea     rcx, [rbp+60h+var_88]
0x1400380c9  call    SecFreeNullTerminatedUnicode
0x1400380ce  lea     rcx, [rbp+60h+var_78]
0x1400380d2  call    SecFreeNullTerminatedUnicode
0x1400380d7  lea     rcx, [rbp+60h+var_68]
0x1400380db  call    SecFreeNullTerminatedUnicode
0x1400380e0  mov     rcx, [rbp+60h+ListEntry]; ListEntry
0x1400380e4  test    rcx, rcx
0x1400380e7  jz      short loc_1400380EE
0x1400380e9  call    SecReleaseProcessContext
0x1400380ee  mov     rcx, [rbp+60h+P]; P
0x1400380f2  test    rcx, rcx
0x1400380f5  jz      short loc_14003810B
0x1400380f7  cmp     [rbp+60h+var_58], dil
0x1400380fb  jz      short loc_14003810B
0x1400380fd  xor     edx, edx; Tag
0x1400380ff  call    cs:__imp_ExFreePoolWithTag
0x140038106  nop     dword ptr [rax+rax+00h]
0x14003810b  mov     rcx, [rbp+60h+SourceString]; P
0x14003810f  test    rcx, rcx
0x140038112  jz      short loc_140038122
0x140038114  xor     edx, edx; Tag
0x140038116  call    cs:__imp_ExFreePoolWithTag
0x14003811d  nop     dword ptr [rax+rax+00h]
0x140038122  mov     rcx, [rbp+60h+var_B0]; P
0x140038126  test    rcx, rcx
0x140038129  jz      short loc_140038139
0x14003812b  xor     edx, edx; Tag
0x14003812d  call    cs:__imp_ExFreePoolWithTag
0x140038134  nop     dword ptr [rax+rax+00h]
0x140038139  mov     rcx, [rbp+60h+var_40]
0x14003813d  xor     rcx, rsp; StackCookie
0x140038140  call    __security_check_cookie
0x140038145  mov     rbx, [rsp+160h+arg_10]
0x14003814d  add     rsp, 130h
0x140038154  pop     r15
0x140038156  pop     r14
0x140038158  pop     r13
0x14003815a  pop     r12
0x14003815c  pop     rdi
0x14003815d  pop     rsi
0x14003815e  pop     rbp
0x14003815f  retn
```
