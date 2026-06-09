# MupiCreatePrefixEntryForPathFromConfiguration

- ea: `0x140018570`
- end: `0x140018979`
- name: `MupiCreatePrefixEntryForPathFromConfiguration`
- size: `1033`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014d38`

## callees

- `0x1400013e0`
- `0x1400056c0`
- `0x1400059c0`
- `0x140015604`
- `0x140015e2c`
- `0x140017048`
- `0x1400171c4`
- `0x140018570`
- `0x140018980`
- `0x140018a30`
- `0x140018c10`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400185f4`
- `ntoskrnl!ExAllocatePool2` at `0x1400185f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018866`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018866`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001865d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001865d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400187fd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400187fd`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140018745`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140018745`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400186cb`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400187dc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400186cb`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400187dc`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x14001869d`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x14001869d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400187f1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400187f1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140018672`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140018672`

## pseudocode

```c
__int64 __fastcall MupiCreatePrefixEntryForPathFromConfiguration(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rdi
  USHORT Length; // ax
  UNICODE_STRING *p_StringIn; // rbx
  _QWORD *Pool2; // rax
  _QWORD *v7; // rsi
  USHORT v8; // ax
  NTSTATUS v9; // ebx
  int v10; // r12d
  __int64 *v11; // r9
  __int64 v12; // rax
  __int64 v13; // rbx
  int v14; // ecx
  bool v15; // di
  char v16; // r15
  BOOLEAN v17; // al
  bool v18; // zf
  __int64 v19; // r15
  __int64 v20; // r14
  __int64 *v21; // rbx
  int v22; // r12d
  __int64 result; // rax
  int v24; // ecx
  __int64 v25; // rax
  struct _UNICODE_STRING StringOut; // [rsp+30h] [rbp-59h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-49h] BYREF
  UNICODE_STRING StringIn; // [rsp+50h] [rbp-39h] BYREF
  PVOID P[2]; // [rsp+60h] [rbp-29h] BYREF
  __int128 v30; // [rsp+70h] [rbp-19h]
  __int64 v31; // [rsp+80h] [rbp-9h]
  __int128 v32; // [rsp+88h] [rbp-1h] BYREF
  UNICODE_STRING String2; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v34; // [rsp+F0h] [rbp+67h]
  __int64 v36; // [rsp+108h] [rbp+7Fh]

  v3 = a3;
  *a3 = 0;
  StringIn = 0;
  String2 = 0;
  v32 = 0;
  MupiGetPathComponents(a2, &StringIn, &String2, &v32, 0);
  Length = v32;
  if ( (_WORD)v32 )
  {
    p_StringIn = (UNICODE_STRING *)&v32;
  }
  else
  {
    Length = StringIn.Length;
    p_StringIn = &StringIn;
  }
  if ( Length < 2u )
  {
    result = 3221225485LL;
LABEL_30:
    *v3 = 0;
    return result;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(258, Length + 96LL, 1213560141);
  *(_QWORD *)&UnicodeString.Length = Pool2;
  v7 = Pool2;
  if ( !Pool2 )
  {
    result = 3221225495LL;
    goto LABEL_30;
  }
  memset(Pool2, 0, 0x60u);
  *(_DWORD *)v7 = 6320399;
  v7[9] = v7 + 12;
  *((_DWORD *)v7 + 1) = 1;
  v8 = p_StringIn->Length;
  *((_WORD *)v7 + 33) = p_StringIn->Length;
  *((_WORD *)v7 + 32) = v8;
  memmove(v7 + 12, p_StringIn->Buffer, p_StringIn->Length);
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&qword_14000A218, 0);
  v31 = 0;
  *(_OWORD *)P = 0;
  v30 = 0;
  StringOut = 0;
  v9 = RtlDuplicateUnicodeString(0, &StringIn, &StringOut);
  if ( v9 >= 0 )
  {
    MupiUndecorateServerName(&StringOut);
    v9 = RfsServerNameInitialize(&StringOut);
  }
  RtlFreeUnicodeString(&StringOut);
  v10 = (int)P[0];
  if ( v9 < 0 )
    goto LABEL_26;
  v11 = &qword_14000A220;
  if ( (__int64 *)qword_14000A220 == &qword_14000A220 )
    goto LABEL_25;
  v12 = 0;
  v34 = 0;
  v36 = 0;
  *(_QWORD *)&StringOut.Length = 0;
  v13 = qword_14000A220 - 8;
  if ( qword_14000A220 == 8 )
    goto LABEL_25;
  do
  {
    v14 = *(_DWORD *)(v13 + 24);
    v15 = 0;
    if ( v14 == v10 )
    {
      if ( v14 )
      {
        v24 = v14 - 1;
        if ( v24 )
        {
          if ( v24 == 1 )
            v16 = RfspServerNameEqualSockaddr(v13 + 24, P);
          else
            v16 = 0;
        }
        else
        {
          v16 = RfspServerNameEqualDnsName(v13 + 24, P, 0);
          v11 = &qword_14000A220;
        }
      }
      else
      {
        v16 = 1;
      }
      v12 = v34;
    }
    else
    {
      v16 = 0;
    }
    if ( *(_WORD *)(v13 + 64) )
    {
      v17 = RtlEqualUnicodeString((PCUNICODE_STRING)(v13 + 64), &String2, 1u);
      v11 = &qword_14000A220;
      v18 = v17 == 0;
      v12 = v34;
      v15 = !v18;
    }
    if ( v16 )
    {
      if ( v15 )
      {
        v19 = MupiSelectBestMatchingConfigurationEntry(P, *(_QWORD *)&StringOut.Length, v13);
        *(_QWORD *)&StringOut.Length = v19;
        v12 = v34;
      }
      else
      {
        if ( !*(_WORD *)(v13 + 64) )
        {
          v25 = MupiSelectBestMatchingConfigurationEntry(P, v36, v13);
          v19 = *(_QWORD *)&StringOut.Length;
          v20 = v25;
          v36 = v25;
          v12 = v34;
          goto LABEL_17;
        }
        v19 = *(_QWORD *)&StringOut.Length;
      }
    }
    else
    {
      v19 = *(_QWORD *)&StringOut.Length;
      if ( v15 )
      {
        if ( !*(_DWORD *)(v13 + 24) )
          v12 = v13;
        v34 = v12;
      }
    }
    v20 = v36;
LABEL_17:
    v21 = *(__int64 **)(v13 + 8);
    if ( v21 == v11 )
      break;
    v13 = (__int64)(v21 - 1);
  }
  while ( v13 );
  v7 = *(_QWORD **)&UnicodeString.Length;
  if ( v12 )
    MupiApplyUncHardeningConfigurationEntryToPrefixEntry(v12, *(_QWORD *)&UnicodeString.Length);
  if ( v20 )
    MupiApplyUncHardeningConfigurationEntryToPrefixEntry(v20, v7);
  if ( v19 )
    MupiApplyUncHardeningConfigurationEntryToPrefixEntry(v19, v7);
  v3 = a3;
LABEL_25:
  v9 = 0;
LABEL_26:
  v22 = v10 - 1;
  if ( v22 )
  {
    if ( v22 == 1 )
      ExFreePoolWithTag(P[1], 0x5266534Cu);
  }
  else
  {
    UnicodeString.Buffer = (PWSTR)P[1];
    *(_QWORD *)&UnicodeString.Length = 0;
    RtlFreeUnicodeString(&UnicodeString);
  }
  ExReleasePushLockSharedEx(&qword_14000A218, 0);
  KeLeaveCriticalRegion();
  if ( v9 < 0 )
  {
    MupiDereferenceUncHardeningPrefixEntry(v7);
    result = (unsigned int)v9;
    goto LABEL_30;
  }
  result = 0;
  *v3 = v7;
  return result;
}

```

## disassembly

```asm
0x140018570  mov     [rsp-8+arg_10], r8
0x140018575  mov     [rsp-8+arg_0], rcx
0x14001857a  push    rbp
0x14001857b  push    rbx
0x14001857c  push    rdi
0x14001857d  push    r13
0x14001857f  lea     rbp, [rsp-3Fh]
0x140018584  sub     rsp, 0C8h
0x14001858b  xorps   xmm0, xmm0
0x14001858e  lea     r9, [rbp+57h+var_58]
0x140018592  xor     r13d, r13d
0x140018595  mov     rdi, r8
0x140018598  mov     [r8], r13
0x14001859b  mov     rcx, rdx
0x14001859e  xorps   xmm1, xmm1
0x1400185a1  mov     [rsp+0E0h+var_C0], r13
0x1400185a6  lea     r8, [rbp+57h+String2]
0x1400185aa  lea     rdx, [rbp+57h+StringIn]
0x1400185ae  movups  xmmword ptr [rbp+57h+StringIn.Length], xmm0
0x1400185b2  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x1400185b6  movups  [rbp+57h+var_58], xmm0
0x1400185ba  call    MupiGetPathComponents
0x1400185bf  movzx   eax, word ptr [rbp+57h+var_58]
0x1400185c3  test    ax, ax
0x1400185c6  jz      loc_14001883C
0x1400185cc  lea     rbx, [rbp+57h+var_58]
0x1400185d0  mov     [rsp+0E0h+arg_8], rsi
0x1400185d8  cmp     ax, 2
0x1400185dc  jb      loc_140018849
0x1400185e2  movzx   edx, ax
0x1400185e5  mov     ecx, 102h
0x1400185ea  add     rdx, 60h ; '`'
0x1400185ee  mov     r8d, 4855754Dh
0x1400185f4  call    cs:__imp_ExAllocatePool2
0x1400185fb  nop     dword ptr [rax+rax+00h]
0x140018600  mov     qword ptr [rbp+57h+UnicodeString.Length], rax
0x140018604  mov     rsi, rax
0x140018607  test    rax, rax
0x14001860a  jz      loc_140018850
0x140018610  mov     [rsp+0E0h+var_20], r12
0x140018618  xor     edx, edx; Val
0x14001861a  mov     r8d, 60h ; '`'; Size
0x140018620  mov     [rsp+0E0h+var_28], r14
0x140018628  mov     rcx, rax; void *
0x14001862b  call    memset
0x140018630  mov     dword ptr [rsi], 60710Fh
0x140018636  lea     rcx, [rsi+60h]; void *
0x14001863a  mov     [rsi+48h], rcx
0x14001863e  mov     dword ptr [rsi+4], 1
0x140018645  movzx   eax, word ptr [rbx]
0x140018648  mov     [rsi+42h], ax
0x14001864c  mov     [rsi+40h], ax
0x140018650  movzx   r8d, word ptr [rbx]; Size
0x140018654  mov     rdx, [rbx+8]; Src
0x140018658  call    memmove
0x14001865d  call    cs:__imp_KeEnterCriticalRegion
0x140018664  nop     dword ptr [rax+rax+00h]
0x140018669  xor     edx, edx
0x14001866b  lea     rcx, qword_14000A218
0x140018672  call    cs:__imp_ExAcquirePushLockSharedEx
0x140018679  nop     dword ptr [rax+rax+00h]
0x14001867e  xorps   xmm0, xmm0
0x140018681  lea     r8, [rbp+57h+StringOut]; StringOut
0x140018685  xor     eax, eax
0x140018687  lea     rdx, [rbp+57h+StringIn]; StringIn
0x14001868b  xor     ecx, ecx; Flags
0x14001868d  mov     [rbp+57h+var_60], rax
0x140018691  movups  xmmword ptr [rbp+57h+P], xmm0
0x140018695  movups  [rbp+57h+var_70], xmm0
0x140018699  movups  xmmword ptr [rbp+57h+StringOut.Length], xmm0
0x14001869d  call    cs:__imp_RtlDuplicateUnicodeString
0x1400186a4  nop     dword ptr [rax+rax+00h]
0x1400186a9  mov     ebx, eax
0x1400186ab  test    eax, eax
0x1400186ad  js      short loc_1400186C7
0x1400186af  lea     rcx, [rbp+57h+StringOut]
0x1400186b3  call    MupiUndecorateServerName
0x1400186b8  lea     rdx, [rbp+57h+P]
0x1400186bc  lea     rcx, [rbp+57h+StringOut]; StringIn
0x1400186c0  call    RfsServerNameInitialize
0x1400186c5  mov     ebx, eax
0x1400186c7  lea     rcx, [rbp+57h+StringOut]; UnicodeString
0x1400186cb  call    cs:__imp_RtlFreeUnicodeString
0x1400186d2  nop     dword ptr [rax+rax+00h]
0x1400186d7  mov     r12d, dword ptr [rbp+57h+P]
0x1400186db  test    ebx, ebx
0x1400186dd  js      loc_1400187BA
0x1400186e3  mov     rbx, cs:qword_14000A220
0x1400186ea  lea     r9, qword_14000A220
0x1400186f1  cmp     rbx, r9
0x1400186f4  jz      loc_1400187B7
0x1400186fa  mov     [rsp+0E0h+var_30], r15
0x140018702  mov     rax, r13
0x140018705  mov     [rbp+57h+arg_0], rax
0x140018709  mov     [rbp+57h+arg_18], r13
0x14001870d  mov     qword ptr [rbp+57h+StringOut.Length], r13
0x140018711  add     rbx, 0FFFFFFFFFFFFFFF8h
0x140018715  jz      loc_1400187AF
0x14001871b  mov     esi, 1
0x140018720  mov     ecx, [rbx+18h]
0x140018723  xor     dil, dil
0x140018726  cmp     ecx, r12d
0x140018729  jz      loc_140018886
0x14001872f  xor     r15b, r15b
0x140018732  cmp     [rbx+40h], r13w
0x140018737  jbe     short loc_140018765
0x140018739  movzx   r8d, sil; CaseInSensitive
0x14001873d  lea     rdx, [rbp+57h+String2]; String2
0x140018741  lea     rcx, [rbx+40h]; String1
0x140018745  call    cs:__imp_RtlEqualUnicodeString
0x14001874c  nop     dword ptr [rax+rax+00h]
0x140018751  movzx   edi, dil
0x140018755  lea     r9, qword_14000A220
0x14001875c  test    al, al
0x14001875e  mov     rax, [rbp+57h+arg_0]
0x140018762  cmovnz  edi, esi
0x140018765  test    r15b, r15b
0x140018768  jnz     loc_1400188D4
0x14001876e  mov     r15, qword ptr [rbp+57h+StringOut.Length]
0x140018772  test    dil, dil
0x140018775  jnz     loc_140018924
0x14001877b  mov     r14, [rbp+57h+arg_18]
0x14001877f  mov     rbx, [rbx+8]
0x140018783  cmp     rbx, r9
0x140018786  jnz     loc_140018877
0x14001878c  mov     rsi, qword ptr [rbp+57h+UnicodeString.Length]
0x140018790  test    rax, rax
0x140018793  jnz     loc_14001893E
0x140018799  test    r14, r14
0x14001879c  jnz     loc_14001894E
0x1400187a2  test    r15, r15
0x1400187a5  jnz     loc_14001895E
0x1400187ab  mov     rdi, [rbp+57h+arg_10]
0x1400187af  mov     r15, [rsp+0E0h+var_30]
0x1400187b7  mov     ebx, r13d
0x1400187ba  mov     r14, [rsp+0E0h+var_28]
0x1400187c2  sub     r12d, 1
0x1400187c6  jnz     loc_140018857
0x1400187cc  mov     rax, [rbp+57h+P+8]
0x1400187d0  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x1400187d4  mov     [rbp+57h+UnicodeString.Buffer], rax
0x1400187d8  mov     qword ptr [rbp+57h+UnicodeString.Length], r13
0x1400187dc  call    cs:__imp_RtlFreeUnicodeString
0x1400187e3  nop     dword ptr [rax+rax+00h]
0x1400187e8  xor     edx, edx
0x1400187ea  lea     rcx, qword_14000A218
0x1400187f1  call    cs:__imp_ExReleasePushLockSharedEx
0x1400187f8  nop     dword ptr [rax+rax+00h]
0x1400187fd  call    cs:__imp_KeLeaveCriticalRegion
0x140018804  nop     dword ptr [rax+rax+00h]
0x140018809  mov     r12, [rsp+0E0h+var_20]
0x140018811  test    ebx, ebx
0x140018813  jns     loc_14001896E
0x140018819  mov     rcx, rsi
0x14001881c  call    MupiDereferenceUncHardeningPrefixEntry
0x140018821  mov     eax, ebx
0x140018823  mov     [rdi], r13
0x140018826  mov     rsi, [rsp+0E0h+arg_8]
0x14001882e  add     rsp, 0C8h
0x140018835  pop     r13
0x140018837  pop     rdi
0x140018838  pop     rbx
0x140018839  pop     rbp
0x14001883a  retn
0x14001883c  movzx   eax, [rbp+57h+StringIn.Length]
0x140018840  lea     rbx, [rbp+57h+StringIn]
0x140018844  jmp     loc_1400185D0
0x140018849  mov     eax, 0C000000Dh
0x14001884e  jmp     short loc_140018823
0x140018850  mov     eax, 0C0000017h
0x140018855  jmp     short loc_140018823
0x140018857  cmp     r12d, 1
0x14001885b  jnz     short loc_1400187E8
0x14001885d  mov     rcx, [rbp+57h+P+8]; P
0x140018861  mov     edx, 5266534Ch; Tag
0x140018866  call    cs:__imp_ExFreePoolWithTag
0x14001886d  nop     dword ptr [rax+rax+00h]
0x140018872  jmp     loc_1400187E8
0x140018877  add     rbx, 0FFFFFFFFFFFFFFF8h
0x14001887b  jnz     loc_140018720
0x140018881  jmp     loc_14001878C
0x140018886  test    ecx, ecx
0x140018888  jz      short loc_1400188C7
0x14001888a  sub     ecx, esi
0x14001888c  jz      short loc_1400188AA
0x14001888e  cmp     ecx, esi
0x140018890  jz      short loc_140018897
0x140018892  xor     r15b, r15b
0x140018895  jmp     short loc_1400188CB
0x140018897  lea     rdx, [rbp+57h+P]
0x14001889b  lea     rcx, [rbx+18h]
0x14001889f  call    RfspServerNameEqualSockaddr
0x1400188a4  movzx   r15d, al
0x1400188a8  jmp     short loc_1400188CB
0x1400188aa  xor     r8d, r8d
0x1400188ad  lea     rdx, [rbp+57h+P]
0x1400188b1  lea     rcx, [rbx+18h]
0x1400188b5  call    RfspServerNameEqualDnsName
0x1400188ba  movzx   r15d, al
0x1400188be  lea     r9, qword_14000A220
0x1400188c5  jmp     short loc_1400188CB
0x1400188c7  movzx   r15d, sil
0x1400188cb  mov     rax, [rbp+57h+arg_0]
0x1400188cf  jmp     loc_140018732
0x1400188d4  test    dil, dil
0x1400188d7  jz      short loc_1400188F9
0x1400188d9  mov     rdx, qword ptr [rbp+57h+StringOut.Length]
0x1400188dd  lea     rcx, [rbp+57h+P]
0x1400188e1  mov     r8, rbx
0x1400188e4  call    MupiSelectBestMatchingConfigurationEntry
0x1400188e9  mov     r15, rax
0x1400188ec  mov     qword ptr [rbp+57h+StringOut.Length], rax
0x1400188f0  mov     rax, [rbp+57h+arg_0]
0x1400188f4  jmp     loc_14001877B
0x1400188f9  cmp     [rbx+40h], r13w
0x1400188fe  jnz     short loc_140018935
0x140018900  mov     rdx, [rbp+57h+arg_18]
0x140018904  lea     rcx, [rbp+57h+P]
0x140018908  mov     r8, rbx
0x14001890b  call    MupiSelectBestMatchingConfigurationEntry
0x140018910  mov     r15, qword ptr [rbp+57h+StringOut.Length]
0x140018914  mov     r14, rax
0x140018917  mov     [rbp+57h+arg_18], rax
0x14001891b  mov     rax, [rbp+57h+arg_0]
0x14001891f  jmp     loc_14001877F
0x140018924  cmp     [rbx+18h], r13d
0x140018928  cmovz   rax, rbx
0x14001892c  mov     [rbp+57h+arg_0], rax
0x140018930  jmp     loc_14001877B
0x140018935  mov     r15, qword ptr [rbp+57h+StringOut.Length]
0x140018939  jmp     loc_14001877B
0x14001893e  mov     rdx, rsi
0x140018941  mov     rcx, rax
0x140018944  call    MupiApplyUncHardeningConfigurationEntryToPrefixEntry
0x140018949  jmp     loc_140018799
0x14001894e  mov     rdx, rsi
0x140018951  mov     rcx, r14
0x140018954  call    MupiApplyUncHardeningConfigurationEntryToPrefixEntry
0x140018959  jmp     loc_1400187A2
0x14001895e  mov     rdx, rsi
0x140018961  mov     rcx, r15
0x140018964  call    MupiApplyUncHardeningConfigurationEntryToPrefixEntry
0x140018969  jmp     loc_1400187AB
0x14001896e  mov     eax, r13d
0x140018971  mov     [rdi], rsi
0x140018974  jmp     loc_140018826
```
