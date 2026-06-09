# MupiCreatePrefixEntryForPathFromConfiguration

- ea: `0x140018520`
- end: `0x140018929`
- name: `MupiCreatePrefixEntryForPathFromConfiguration`
- size: `1033`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014ce8`

## callees

- `0x1400013e0`
- `0x1400056c0`
- `0x1400059c0`
- `0x1400155b4`
- `0x140015ddc`
- `0x140016ff8`
- `0x140017174`
- `0x140018520`
- `0x140018930`
- `0x1400189e0`
- `0x140018bc0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400185a4`
- `ntoskrnl!ExAllocatePool2` at `0x1400185a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018816`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018816`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001860d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001860d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400187ad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400187ad`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400186f5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400186f5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001867b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001878c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001867b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001878c`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x14001864d`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x14001864d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400187a1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400187a1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140018622`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140018622`

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
  int v9; // ebx
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
    v9 = RfsServerNameInitialize(&StringOut, (__int64)P);
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
0x140018520  mov     [rsp-8+arg_10], r8
0x140018525  mov     [rsp-8+arg_0], rcx
0x14001852a  push    rbp
0x14001852b  push    rbx
0x14001852c  push    rdi
0x14001852d  push    r13
0x14001852f  lea     rbp, [rsp-3Fh]
0x140018534  sub     rsp, 0C8h
0x14001853b  xorps   xmm0, xmm0
0x14001853e  lea     r9, [rbp+57h+var_58]
0x140018542  xor     r13d, r13d
0x140018545  mov     rdi, r8
0x140018548  mov     [r8], r13
0x14001854b  mov     rcx, rdx
0x14001854e  xorps   xmm1, xmm1
0x140018551  mov     [rsp+0E0h+var_C0], r13
0x140018556  lea     r8, [rbp+57h+String2]
0x14001855a  lea     rdx, [rbp+57h+StringIn]
0x14001855e  movups  xmmword ptr [rbp+57h+StringIn.Length], xmm0
0x140018562  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x140018566  movups  [rbp+57h+var_58], xmm0
0x14001856a  call    MupiGetPathComponents
0x14001856f  movzx   eax, word ptr [rbp+57h+var_58]
0x140018573  test    ax, ax
0x140018576  jz      loc_1400187EC
0x14001857c  lea     rbx, [rbp+57h+var_58]
0x140018580  mov     [rsp+0E0h+arg_8], rsi
0x140018588  cmp     ax, 2
0x14001858c  jb      loc_1400187F9
0x140018592  movzx   edx, ax
0x140018595  mov     ecx, 102h
0x14001859a  add     rdx, 60h ; '`'
0x14001859e  mov     r8d, 4855754Dh
0x1400185a4  call    cs:__imp_ExAllocatePool2
0x1400185ab  nop     dword ptr [rax+rax+00h]
0x1400185b0  mov     qword ptr [rbp+57h+UnicodeString.Length], rax
0x1400185b4  mov     rsi, rax
0x1400185b7  test    rax, rax
0x1400185ba  jz      loc_140018800
0x1400185c0  mov     [rsp+0E0h+var_20], r12
0x1400185c8  xor     edx, edx; Val
0x1400185ca  mov     r8d, 60h ; '`'; Size
0x1400185d0  mov     [rsp+0E0h+var_28], r14
0x1400185d8  mov     rcx, rax; void *
0x1400185db  call    memset
0x1400185e0  mov     dword ptr [rsi], 60710Fh
0x1400185e6  lea     rcx, [rsi+60h]; void *
0x1400185ea  mov     [rsi+48h], rcx
0x1400185ee  mov     dword ptr [rsi+4], 1
0x1400185f5  movzx   eax, word ptr [rbx]
0x1400185f8  mov     [rsi+42h], ax
0x1400185fc  mov     [rsi+40h], ax
0x140018600  movzx   r8d, word ptr [rbx]; Size
0x140018604  mov     rdx, [rbx+8]; Src
0x140018608  call    memmove
0x14001860d  call    cs:__imp_KeEnterCriticalRegion
0x140018614  nop     dword ptr [rax+rax+00h]
0x140018619  xor     edx, edx
0x14001861b  lea     rcx, qword_14000A218
0x140018622  call    cs:__imp_ExAcquirePushLockSharedEx
0x140018629  nop     dword ptr [rax+rax+00h]
0x14001862e  xorps   xmm0, xmm0
0x140018631  lea     r8, [rbp+57h+StringOut]; StringOut
0x140018635  xor     eax, eax
0x140018637  lea     rdx, [rbp+57h+StringIn]; StringIn
0x14001863b  xor     ecx, ecx; Flags
0x14001863d  mov     [rbp+57h+var_60], rax
0x140018641  movups  xmmword ptr [rbp+57h+P], xmm0
0x140018645  movups  [rbp+57h+var_70], xmm0
0x140018649  movups  xmmword ptr [rbp+57h+StringOut.Length], xmm0
0x14001864d  call    cs:__imp_RtlDuplicateUnicodeString
0x140018654  nop     dword ptr [rax+rax+00h]
0x140018659  mov     ebx, eax
0x14001865b  test    eax, eax
0x14001865d  js      short loc_140018677
0x14001865f  lea     rcx, [rbp+57h+StringOut]
0x140018663  call    MupiUndecorateServerName
0x140018668  lea     rdx, [rbp+57h+P]
0x14001866c  lea     rcx, [rbp+57h+StringOut]; StringIn
0x140018670  call    RfsServerNameInitialize
0x140018675  mov     ebx, eax
0x140018677  lea     rcx, [rbp+57h+StringOut]; UnicodeString
0x14001867b  call    cs:__imp_RtlFreeUnicodeString
0x140018682  nop     dword ptr [rax+rax+00h]
0x140018687  mov     r12d, dword ptr [rbp+57h+P]
0x14001868b  test    ebx, ebx
0x14001868d  js      loc_14001876A
0x140018693  mov     rbx, cs:qword_14000A220
0x14001869a  lea     r9, qword_14000A220
0x1400186a1  cmp     rbx, r9
0x1400186a4  jz      loc_140018767
0x1400186aa  mov     [rsp+0E0h+var_30], r15
0x1400186b2  mov     rax, r13
0x1400186b5  mov     [rbp+57h+arg_0], rax
0x1400186b9  mov     [rbp+57h+arg_18], r13
0x1400186bd  mov     qword ptr [rbp+57h+StringOut.Length], r13
0x1400186c1  add     rbx, 0FFFFFFFFFFFFFFF8h
0x1400186c5  jz      loc_14001875F
0x1400186cb  mov     esi, 1
0x1400186d0  mov     ecx, [rbx+18h]
0x1400186d3  xor     dil, dil
0x1400186d6  cmp     ecx, r12d
0x1400186d9  jz      loc_140018836
0x1400186df  xor     r15b, r15b
0x1400186e2  cmp     [rbx+40h], r13w
0x1400186e7  jbe     short loc_140018715
0x1400186e9  movzx   r8d, sil; CaseInSensitive
0x1400186ed  lea     rdx, [rbp+57h+String2]; String2
0x1400186f1  lea     rcx, [rbx+40h]; String1
0x1400186f5  call    cs:__imp_RtlEqualUnicodeString
0x1400186fc  nop     dword ptr [rax+rax+00h]
0x140018701  movzx   edi, dil
0x140018705  lea     r9, qword_14000A220
0x14001870c  test    al, al
0x14001870e  mov     rax, [rbp+57h+arg_0]
0x140018712  cmovnz  edi, esi
0x140018715  test    r15b, r15b
0x140018718  jnz     loc_140018884
0x14001871e  mov     r15, qword ptr [rbp+57h+StringOut.Length]
0x140018722  test    dil, dil
0x140018725  jnz     loc_1400188D4
0x14001872b  mov     r14, [rbp+57h+arg_18]
0x14001872f  mov     rbx, [rbx+8]
0x140018733  cmp     rbx, r9
0x140018736  jnz     loc_140018827
0x14001873c  mov     rsi, qword ptr [rbp+57h+UnicodeString.Length]
0x140018740  test    rax, rax
0x140018743  jnz     loc_1400188EE
0x140018749  test    r14, r14
0x14001874c  jnz     loc_1400188FE
0x140018752  test    r15, r15
0x140018755  jnz     loc_14001890E
0x14001875b  mov     rdi, [rbp+57h+arg_10]
0x14001875f  mov     r15, [rsp+0E0h+var_30]
0x140018767  mov     ebx, r13d
0x14001876a  mov     r14, [rsp+0E0h+var_28]
0x140018772  sub     r12d, 1
0x140018776  jnz     loc_140018807
0x14001877c  mov     rax, [rbp+57h+P+8]
0x140018780  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x140018784  mov     [rbp+57h+UnicodeString.Buffer], rax
0x140018788  mov     qword ptr [rbp+57h+UnicodeString.Length], r13
0x14001878c  call    cs:__imp_RtlFreeUnicodeString
0x140018793  nop     dword ptr [rax+rax+00h]
0x140018798  xor     edx, edx
0x14001879a  lea     rcx, qword_14000A218
0x1400187a1  call    cs:__imp_ExReleasePushLockSharedEx
0x1400187a8  nop     dword ptr [rax+rax+00h]
0x1400187ad  call    cs:__imp_KeLeaveCriticalRegion
0x1400187b4  nop     dword ptr [rax+rax+00h]
0x1400187b9  mov     r12, [rsp+0E0h+var_20]
0x1400187c1  test    ebx, ebx
0x1400187c3  jns     loc_14001891E
0x1400187c9  mov     rcx, rsi
0x1400187cc  call    MupiDereferenceUncHardeningPrefixEntry
0x1400187d1  mov     eax, ebx
0x1400187d3  mov     [rdi], r13
0x1400187d6  mov     rsi, [rsp+0E0h+arg_8]
0x1400187de  add     rsp, 0C8h
0x1400187e5  pop     r13
0x1400187e7  pop     rdi
0x1400187e8  pop     rbx
0x1400187e9  pop     rbp
0x1400187ea  retn
0x1400187ec  movzx   eax, [rbp+57h+StringIn.Length]
0x1400187f0  lea     rbx, [rbp+57h+StringIn]
0x1400187f4  jmp     loc_140018580
0x1400187f9  mov     eax, 0C000000Dh
0x1400187fe  jmp     short loc_1400187D3
0x140018800  mov     eax, 0C0000017h
0x140018805  jmp     short loc_1400187D3
0x140018807  cmp     r12d, 1
0x14001880b  jnz     short loc_140018798
0x14001880d  mov     rcx, [rbp+57h+P+8]; P
0x140018811  mov     edx, 5266534Ch; Tag
0x140018816  call    cs:__imp_ExFreePoolWithTag
0x14001881d  nop     dword ptr [rax+rax+00h]
0x140018822  jmp     loc_140018798
0x140018827  add     rbx, 0FFFFFFFFFFFFFFF8h
0x14001882b  jnz     loc_1400186D0
0x140018831  jmp     loc_14001873C
0x140018836  test    ecx, ecx
0x140018838  jz      short loc_140018877
0x14001883a  sub     ecx, esi
0x14001883c  jz      short loc_14001885A
0x14001883e  cmp     ecx, esi
0x140018840  jz      short loc_140018847
0x140018842  xor     r15b, r15b
0x140018845  jmp     short loc_14001887B
0x140018847  lea     rdx, [rbp+57h+P]
0x14001884b  lea     rcx, [rbx+18h]
0x14001884f  call    RfspServerNameEqualSockaddr
0x140018854  movzx   r15d, al
0x140018858  jmp     short loc_14001887B
0x14001885a  xor     r8d, r8d
0x14001885d  lea     rdx, [rbp+57h+P]
0x140018861  lea     rcx, [rbx+18h]
0x140018865  call    RfspServerNameEqualDnsName
0x14001886a  movzx   r15d, al
0x14001886e  lea     r9, qword_14000A220
0x140018875  jmp     short loc_14001887B
0x140018877  movzx   r15d, sil
0x14001887b  mov     rax, [rbp+57h+arg_0]
0x14001887f  jmp     loc_1400186E2
0x140018884  test    dil, dil
0x140018887  jz      short loc_1400188A9
0x140018889  mov     rdx, qword ptr [rbp+57h+StringOut.Length]
0x14001888d  lea     rcx, [rbp+57h+P]
0x140018891  mov     r8, rbx
0x140018894  call    MupiSelectBestMatchingConfigurationEntry
0x140018899  mov     r15, rax
0x14001889c  mov     qword ptr [rbp+57h+StringOut.Length], rax
0x1400188a0  mov     rax, [rbp+57h+arg_0]
0x1400188a4  jmp     loc_14001872B
0x1400188a9  cmp     [rbx+40h], r13w
0x1400188ae  jnz     short loc_1400188E5
0x1400188b0  mov     rdx, [rbp+57h+arg_18]
0x1400188b4  lea     rcx, [rbp+57h+P]
0x1400188b8  mov     r8, rbx
0x1400188bb  call    MupiSelectBestMatchingConfigurationEntry
0x1400188c0  mov     r15, qword ptr [rbp+57h+StringOut.Length]
0x1400188c4  mov     r14, rax
0x1400188c7  mov     [rbp+57h+arg_18], rax
0x1400188cb  mov     rax, [rbp+57h+arg_0]
0x1400188cf  jmp     loc_14001872F
0x1400188d4  cmp     [rbx+18h], r13d
0x1400188d8  cmovz   rax, rbx
0x1400188dc  mov     [rbp+57h+arg_0], rax
0x1400188e0  jmp     loc_14001872B
0x1400188e5  mov     r15, qword ptr [rbp+57h+StringOut.Length]
0x1400188e9  jmp     loc_14001872B
0x1400188ee  mov     rdx, rsi
0x1400188f1  mov     rcx, rax
0x1400188f4  call    MupiApplyUncHardeningConfigurationEntryToPrefixEntry
0x1400188f9  jmp     loc_140018749
0x1400188fe  mov     rdx, rsi
0x140018901  mov     rcx, r14
0x140018904  call    MupiApplyUncHardeningConfigurationEntryToPrefixEntry
0x140018909  jmp     loc_140018752
0x14001890e  mov     rdx, rsi
0x140018911  mov     rcx, r15
0x140018914  call    MupiApplyUncHardeningConfigurationEntryToPrefixEntry
0x140018919  jmp     loc_14001875B
0x14001891e  mov     eax, r13d
0x140018921  mov     [rdi], rsi
0x140018924  jmp     loc_1400187D6
```
