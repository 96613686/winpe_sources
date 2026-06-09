# SepReadAndPopulateCapes

- ea: `0x1407cc468`
- end: `0x1407ccbc6`
- name: `SepReadAndPopulateCapes`
- size: `1886`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1406353dc`

## callees

- `0x1403887e8`
- `0x1406355e4`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd6a0`
- `0x1406dd6c0`
- `0x1406f6f80`
- `0x1406f7380`
- `0x1407cc468`
- `0x140911490`
- `0x140a53d14`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x1407cc5b0`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\CentralizedAccessPolicies\CAPEs`
- `0x1407cc851`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\CentralizedAccessPolicies\CAPEs`

## pseudocode

```c
__int64 __fastcall SepReadAndPopulateCapes(HANDLE KeyHandle, int a2, unsigned int *a3, _QWORD *a4)
{
  char *v4; // rsi
  _DWORD *v5; // r15
  ULONG *Pool2; // rdi
  ULONG v8; // r12d
  NTSTATUS v10; // eax
  NTSTATUS v11; // ebx
  char v12; // r12
  unsigned int v13; // ecx
  char *v14; // rax
  ULONG v15; // r14d
  unsigned int v16; // eax
  unsigned int v17; // r13d
  unsigned int v18; // ecx
  NTSTATUS v19; // eax
  ULONG v20; // ebx
  int v21; // r13d
  char *v22; // rax
  char *v23; // r13
  unsigned int v24; // r14d
  ULONG v25; // r12d
  __int64 v26; // r14
  unsigned __int64 v27; // r12
  __int16 v28; // ax
  ULONG v29; // r13d
  __int64 v30; // rcx
  void *v31; // r12
  void *v32; // r12
  void *v33; // rdx
  __int64 v34; // rcx
  char *v35; // r12
  PULONG ResultLength; // [rsp+20h] [rbp-E0h]
  char v38; // [rsp+30h] [rbp-D0h]
  ULONG Length; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE KeyHandlea; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v41; // [rsp+40h] [rbp-C0h]
  unsigned int v42; // [rsp+44h] [rbp-BCh]
  unsigned __int64 v43; // [rsp+48h] [rbp-B8h]
  ULONG v44; // [rsp+50h] [rbp-B0h]
  __int64 v45; // [rsp+58h] [rbp-A8h]
  unsigned int *v46; // [rsp+60h] [rbp-A0h]
  _QWORD *v47; // [rsp+68h] [rbp-98h]
  wchar_t pszDest[344]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE KeyInformation[560]; // [rsp+320h] [rbp+220h] BYREF

  v47 = a4;
  v4 = 0;
  Length = 0;
  v38 = 0;
  v5 = KeyInformation;
  Pool2 = 0;
  KeyHandlea = 0;
  v46 = a3;
  v8 = 560;
  v10 = ZwQueryKey(KeyHandle, KeyFullInformation, KeyInformation, 0x230u, &Length);
  v11 = v10;
  if ( v10 >= 0 )
  {
LABEL_7:
    v42 = v5[5];
    if ( !v42 )
    {
      v13 = 0;
      v14 = 0;
      goto LABEL_58;
    }
    v15 = a2 + 18;
    v44 = a2 + 18;
    Pool2 = (ULONG *)ExAllocatePool2(256, (unsigned int)(a2 + 18), 0x70536553u);
    if ( Pool2 )
    {
      v16 = v42;
      v17 = 56 * v42;
      v18 = 0;
      while ( 1 )
      {
        v41 = v18;
        if ( v18 >= v16 )
          break;
        LODWORD(ResultLength) = v18;
        v11 = RtlStringCbPrintfW(
                pszDest,
                0x157u,
                L"%s\\%d",
                L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa\\CentralizedAccessPolicies\\CAPEs",
                ResultLength);
        if ( v11 < 0 )
          goto LABEL_59;
        v11 = SepRegOpenKey(pszDest, 0x201u, &KeyHandlea);
        if ( v11 < 0 )
          goto LABEL_59;
        v19 = ZwQueryKey(KeyHandlea, KeyFullInformation, v5, v8, &Length);
        v11 = v19;
        if ( v19 < 0 )
        {
          if ( v19 != -2147483643 && v19 != -1073741789 )
            goto LABEL_59;
          v12 = v38;
          if ( v38 )
            ExFreePoolWithTag(v5, 0x70536553u);
          v5 = (_DWORD *)ExAllocatePool2(256, Length, 0x70536553u);
          if ( !v5 )
          {
            v11 = -1073741670;
            goto LABEL_60;
          }
          v8 = Length;
          v38 = 1;
          v11 = ZwQueryKey(KeyHandlea, KeyFullInformation, v5, Length, &Length);
          if ( v11 < 0 )
            goto LABEL_59;
        }
        v20 = v5[10] + 18;
        if ( v20 > v15 )
        {
          Pool2 = (ULONG *)SepRmCapPoolExpand(Pool2, v20);
          if ( !Pool2 )
            goto LABEL_10;
          v15 = v20;
          v44 = v20;
        }
        v11 = ZwQueryValueKey(KeyHandlea, &CapeName, KeyValuePartialInformation, Pool2, v15, &Length);
        if ( v11 < 0 )
          goto LABEL_59;
        v45 = Pool2[2];
        v11 = ZwQueryValueKey(KeyHandlea, &CapePredicate, KeyValuePartialInformation, Pool2, v15, &Length);
        if ( v11 < 0 )
          goto LABEL_59;
        v43 = Pool2[2];
        v11 = ZwQueryValueKey(KeyHandlea, &CapeSD, KeyValuePartialInformation, Pool2, v15, &Length);
        if ( v11 < 0 )
          goto LABEL_59;
        v21 = v45 + v43 + ((v17 + 1) & 0xFFFFFFFE);
        v43 = Pool2[2];
        v11 = ZwQueryValueKey(KeyHandlea, &CapeStagedSD, KeyValuePartialInformation, Pool2, v15, &Length);
        if ( v11 < 0 )
          goto LABEL_59;
        v17 = Pool2[2] + ((((v21 + 7) & 0xFFFFFFF8) + v43 + 7) & 0xFFFFFFF8);
        ZwClose(KeyHandlea);
        v16 = v42;
        v18 = v41 + 1;
        KeyHandlea = 0;
      }
      v22 = (char *)ExAllocatePool2(256, v17, 0x70536553u);
      v4 = v22;
      if ( v22 )
      {
        memset_0(v22, 0, v17);
        v13 = v42;
        v43 = (unsigned __int64)&v4[v17];
        v23 = &v4[56 * v42];
        v24 = 0;
        while ( 1 )
        {
          v41 = v24;
          if ( v24 >= v13 )
            break;
          LODWORD(ResultLength) = v24;
          v11 = RtlStringCbPrintfW(
                  pszDest,
                  0x157u,
                  L"%s\\%d",
                  L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa\\CentralizedAccessPolicies\\CAPEs",
                  ResultLength);
          if ( v11 < 0 )
            goto LABEL_59;
          v11 = SepRegOpenKey(pszDest, 0x201u, &KeyHandlea);
          if ( v11 < 0 )
            goto LABEL_59;
          v25 = v44;
          v11 = ZwQueryValueKey(KeyHandlea, &CapeFlags, KeyValuePartialInformation, Pool2, v44, &Length);
          if ( v11 < 0 )
            goto LABEL_59;
          if ( Pool2[2] != 4 )
          {
            v11 = -1073741811;
            goto LABEL_59;
          }
          v26 = 56LL * v24;
          *(_DWORD *)&v4[v26 + 48] = Pool2[3];
          v11 = ZwQueryValueKey(KeyHandlea, &CapeName, KeyValuePartialInformation, Pool2, v25, &Length);
          if ( v11 < 0 )
            goto LABEL_59;
          v27 = (unsigned __int64)(v23 + 1) & 0xFFFFFFFFFFFFFFFEuLL;
          if ( v27 + Pool2[2] > v43 )
            goto LABEL_55;
          v28 = *((_WORD *)Pool2 + 4);
          *(_WORD *)&v4[v26 + 2] = v28;
          *(_WORD *)&v4[v26] = v28;
          *(_QWORD *)&v4[v26 + 8] = v27;
          memmove((void *)((unsigned __int64)(v23 + 1) & 0xFFFFFFFFFFFFFFFEuLL), Pool2 + 3, Pool2[2]);
          v29 = v44;
          v45 = Pool2[2];
          v11 = ZwQueryValueKey(KeyHandlea, &CapePredicate, KeyValuePartialInformation, Pool2, v44, &Length);
          if ( v11 < 0 )
            goto LABEL_59;
          v30 = Pool2[2];
          v31 = (void *)((unsigned int)v45 + v27);
          if ( (unsigned __int64)v31 + v30 > v43 )
            goto LABEL_55;
          *(_DWORD *)&v4[v26 + 16] = v30;
          if ( Pool2[2] )
          {
            *(_QWORD *)&v4[v26 + 24] = v31;
            memmove(v31, Pool2 + 3, Pool2[2]);
          }
          else
          {
            *(_QWORD *)&v4[v26 + 24] = 0;
          }
          v45 = Pool2[2];
          v11 = ZwQueryValueKey(KeyHandlea, &CapeSD, KeyValuePartialInformation, Pool2, v29, &Length);
          if ( v11 < 0 )
            goto LABEL_59;
          v32 = (void *)(((unsigned __int64)v31 + (unsigned int)v45 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
          if ( (unsigned __int64)v32 + Pool2[2] > v43 )
            goto LABEL_55;
          *(_QWORD *)&v4[v26 + 32] = v32;
          memmove(v32, Pool2 + 3, Pool2[2]);
          v33 = *(void **)&v4[v26 + 32];
          LODWORD(v45) = Pool2[2];
          if ( !SeValidSecurityDescriptor(v45, v33) )
            goto LABEL_52;
          v11 = ZwQueryValueKey(KeyHandlea, &CapeStagedSD, KeyValuePartialInformation, Pool2, v29, &Length);
          if ( v11 < 0 )
            goto LABEL_59;
          v34 = Pool2[2];
          v35 = (char *)(((unsigned __int64)v32 + (unsigned int)v45 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
          if ( (unsigned __int64)&v35[v34] > v43 )
          {
LABEL_55:
            v11 = -1073741789;
            goto LABEL_59;
          }
          if ( (_DWORD)v34 )
          {
            *(_QWORD *)&v4[v26 + 40] = v35;
            memmove(v35, Pool2 + 3, Pool2[2]);
            if ( !SeValidSecurityDescriptor(Pool2[2], *(PSECURITY_DESCRIPTOR *)&v4[v26 + 40]) )
            {
LABEL_52:
              v11 = -1073741703;
              goto LABEL_59;
            }
          }
          else
          {
            *(_QWORD *)&v4[v26 + 40] = 0;
          }
          v23 = &v35[Pool2[2]];
          ZwClose(KeyHandlea);
          v13 = v42;
          v24 = v41 + 1;
          KeyHandlea = 0;
        }
        v14 = v4;
LABEL_58:
        *v47 = v14;
        *v46 = v13;
        if ( v11 >= 0 )
        {
          v12 = v38;
          goto LABEL_65;
        }
        goto LABEL_59;
      }
    }
LABEL_10:
    v11 = -1073741670;
LABEL_59:
    v12 = v38;
    goto LABEL_60;
  }
  if ( v10 != -2147483643 && v10 != -1073741789 )
    goto LABEL_59;
  v5 = (_DWORD *)ExAllocatePool2(256, Length, 0x70536553u);
  if ( v5 )
  {
    v8 = Length;
    v38 = 1;
    v11 = ZwQueryKey(KeyHandle, KeyFullInformation, v5, Length, &Length);
    if ( v11 < 0 )
      goto LABEL_59;
    goto LABEL_7;
  }
  v11 = -1073741670;
  v12 = 0;
LABEL_60:
  if ( KeyHandlea )
    ZwClose(KeyHandlea);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x70536553u);
LABEL_65:
  if ( v12 && v5 )
    ExFreePoolWithTag(v5, 0x70536553u);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x70536553u);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1407cc468  push    rbp
0x1407cc46a  push    rbx
0x1407cc46b  push    rsi
0x1407cc46c  push    rdi
0x1407cc46d  push    r12
0x1407cc46f  push    r13
0x1407cc471  push    r14
0x1407cc473  push    r15
0x1407cc475  lea     rbp, [rsp-468h]
0x1407cc47d  sub     rsp, 568h
0x1407cc484  mov     rax, cs:__security_cookie
0x1407cc48b  xor     rax, rsp
0x1407cc48e  mov     [rbp+4A0h+var_50], rax
0x1407cc495  xor     eax, eax
0x1407cc497  mov     [rsp+5A0h+var_538], r9
0x1407cc49c  mov     esi, eax
0x1407cc49e  mov     [rsp+5A0h+Length], eax
0x1407cc4a2  mov     [rsp+5A0h+var_570], al
0x1407cc4a6  lea     r15, [rbp+4A0h+KeyInformation]
0x1407cc4ad  mov     edi, eax
0x1407cc4af  mov     [rsp+5A0h+KeyHandle], rax
0x1407cc4b4  mov     [rsp+5A0h+var_540], r8
0x1407cc4b9  lea     rax, [rsp+5A0h+Length]
0x1407cc4be  mov     r13d, edx
0x1407cc4c1  mov     [rsp+5A0h+ResultLength], rax; ResultLength
0x1407cc4c6  mov     r12d, 230h
0x1407cc4cc  lea     edx, [rsi+2]; KeyInformationClass
0x1407cc4cf  mov     r9d, r12d; Length
0x1407cc4d2  lea     r8, [rbp+4A0h+KeyInformation]; KeyInformation
0x1407cc4d9  mov     r14, rcx
0x1407cc4dc  call    ZwQueryKey
0x1407cc4e1  mov     ebx, eax
0x1407cc4e3  test    eax, eax
0x1407cc4e5  jns     short loc_1407CC553
0x1407cc4e7  cmp     eax, 80000005h
0x1407cc4ec  jz      short loc_1407CC4F9
0x1407cc4ee  cmp     eax, 0C0000023h
0x1407cc4f3  jnz     loc_1407CCB4A
0x1407cc4f9  mov     edx, [rsp+5A0h+Length]
0x1407cc4fd  mov     ecx, 100h
0x1407cc502  mov     r8d, 70536553h
0x1407cc508  call    ExAllocatePool2
0x1407cc50d  mov     r15, rax
0x1407cc510  test    rax, rax
0x1407cc513  jnz     short loc_1407CC522
0x1407cc515  mov     ebx, 0C000009Ah
0x1407cc51a  mov     r12b, sil
0x1407cc51d  jmp     loc_1407CCB4F
0x1407cc522  mov     r12d, [rsp+5A0h+Length]
0x1407cc527  lea     rax, [rsp+5A0h+Length]
0x1407cc52c  mov     r9d, r12d; Length
0x1407cc52f  mov     [rsp+5A0h+ResultLength], rax; ResultLength
0x1407cc534  mov     r8, r15; KeyInformation
0x1407cc537  mov     [rsp+5A0h+var_570], 1
0x1407cc53c  mov     edx, 2; KeyInformationClass
0x1407cc541  mov     rcx, r14; KeyHandle
0x1407cc544  call    ZwQueryKey
0x1407cc549  mov     ebx, eax
0x1407cc54b  test    eax, eax
0x1407cc54d  js      loc_1407CCB4A
0x1407cc553  mov     eax, [r15+14h]
0x1407cc557  mov     [rsp+5A0h+var_55C], eax
0x1407cc55b  test    eax, eax
0x1407cc55d  jnz     short loc_1407CC568
0x1407cc55f  xor     ecx, ecx
0x1407cc561  xor     eax, eax
0x1407cc563  jmp     loc_1407CCB37
0x1407cc568  lea     r14d, [r13+12h]
0x1407cc56c  mov     ecx, 100h
0x1407cc571  mov     edx, r14d
0x1407cc574  mov     r8d, 70536553h
0x1407cc57a  mov     [rsp+5A0h+var_550], r14d
0x1407cc57f  call    ExAllocatePool2
0x1407cc584  mov     rdi, rax
0x1407cc587  test    rax, rax
0x1407cc58a  jnz     short loc_1407CC596
0x1407cc58c  mov     ebx, 0C000009Ah
0x1407cc591  jmp     loc_1407CCB4A
0x1407cc596  mov     eax, [rsp+5A0h+var_55C]
0x1407cc59a  imul    r13d, eax, 38h ; '8'
0x1407cc59e  xor     ecx, ecx
0x1407cc5a0  mov     [rsp+5A0h+var_560], ecx
0x1407cc5a4  cmp     ecx, eax
0x1407cc5a6  jnb     loc_1407CC7FD
0x1407cc5ac  mov     dword ptr [rsp+5A0h+ResultLength], ecx
0x1407cc5b0  lea     r9, aRegistryMachin_129; "\\Registry\\Machine\\System\\CurrentCon"...
0x1407cc5b7  lea     rcx, [rsp+5A0h+pszDest]; pszDest
0x1407cc5bc  mov     edx, 157h; cbDest
0x1407cc5c1  lea     r8, aSD; "%s\\%d"
0x1407cc5c8  call    RtlStringCbPrintfW
0x1407cc5cd  mov     ebx, eax
0x1407cc5cf  test    eax, eax
0x1407cc5d1  js      loc_1407CCB4A
0x1407cc5d7  lea     r8, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407cc5dc  mov     edx, 201h; DesiredAccess
0x1407cc5e1  lea     rcx, [rsp+5A0h+pszDest]; SourceString
0x1407cc5e6  call    SepRegOpenKey
0x1407cc5eb  mov     ebx, eax
0x1407cc5ed  test    eax, eax
0x1407cc5ef  js      loc_1407CCB4A
0x1407cc5f5  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407cc5fa  lea     rax, [rsp+5A0h+Length]
0x1407cc5ff  mov     r9d, r12d; Length
0x1407cc602  mov     [rsp+5A0h+ResultLength], rax; ResultLength
0x1407cc607  mov     r8, r15; KeyInformation
0x1407cc60a  mov     edx, 2; KeyInformationClass
0x1407cc60f  call    ZwQueryKey
0x1407cc614  mov     ebx, eax
0x1407cc616  test    eax, eax
0x1407cc618  jns     short loc_1407CC696
0x1407cc61a  cmp     eax, 80000005h
0x1407cc61f  jz      short loc_1407CC62C
0x1407cc621  cmp     eax, 0C0000023h
0x1407cc626  jnz     loc_1407CCB4A
0x1407cc62c  mov     r12b, [rsp+5A0h+var_570]
0x1407cc631  test    r12b, r12b
0x1407cc634  jz      short loc_1407CC643
0x1407cc636  mov     edx, 70536553h; Tag
0x1407cc63b  mov     rcx, r15; P
0x1407cc63e  call    ExFreePoolWithTag
0x1407cc643  mov     edx, [rsp+5A0h+Length]
0x1407cc647  mov     ecx, 100h
0x1407cc64c  mov     r8d, 70536553h
0x1407cc652  call    ExAllocatePool2
0x1407cc657  mov     r15, rax
0x1407cc65a  test    rax, rax
0x1407cc65d  jz      loc_1407CC7F3
0x1407cc663  mov     r12d, [rsp+5A0h+Length]
0x1407cc668  lea     rax, [rsp+5A0h+Length]
0x1407cc66d  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407cc672  mov     r9d, r12d; Length
0x1407cc675  mov     r8, r15; KeyInformation
0x1407cc678  mov     [rsp+5A0h+ResultLength], rax; ResultLength
0x1407cc67d  mov     edx, 2; KeyInformationClass
0x1407cc682  mov     [rsp+5A0h+var_570], 1
0x1407cc687  call    ZwQueryKey
0x1407cc68c  mov     ebx, eax
0x1407cc68e  test    eax, eax
0x1407cc690  js      loc_1407CCB4A
0x1407cc696  mov     ebx, [r15+28h]
0x1407cc69a  add     ebx, 12h
0x1407cc69d  cmp     ebx, r14d
0x1407cc6a0  jbe     short loc_1407CC6BF
0x1407cc6a2  mov     edx, ebx
0x1407cc6a4  mov     rcx, rdi
0x1407cc6a7  call    SepRmCapPoolExpand
0x1407cc6ac  mov     rdi, rax
0x1407cc6af  test    rax, rax
0x1407cc6b2  jz      loc_1407CC58C
0x1407cc6b8  mov     r14d, ebx
0x1407cc6bb  mov     [rsp+5A0h+var_550], ebx
0x1407cc6bf  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407cc6c4  lea     rax, [rsp+5A0h+Length]
0x1407cc6c9  mov     [rsp+5A0h+var_578], rax; ResultLength
0x1407cc6ce  lea     rdx, CapeName; ValueName
0x1407cc6d5  mov     r9, rdi; KeyValueInformation
0x1407cc6d8  mov     dword ptr [rsp+5A0h+ResultLength], r14d; Length
0x1407cc6dd  mov     r8d, 2; KeyValueInformationClass
0x1407cc6e3  call    ZwQueryValueKey
0x1407cc6e8  mov     ebx, eax
0x1407cc6ea  test    eax, eax
0x1407cc6ec  js      loc_1407CCB4A
0x1407cc6f2  mov     eax, [rdi+8]
0x1407cc6f5  lea     rcx, [rsp+5A0h+Length]
0x1407cc6fa  mov     [rsp+5A0h+var_578], rcx; ResultLength
0x1407cc6ff  lea     rdx, CapePredicate; ValueName
0x1407cc706  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407cc70b  mov     r9, rdi; KeyValueInformation
0x1407cc70e  mov     r8d, 2; KeyValueInformationClass
0x1407cc714  mov     [rsp+5A0h+var_548], rax
0x1407cc719  mov     dword ptr [rsp+5A0h+ResultLength], r14d; Length
0x1407cc71e  call    ZwQueryValueKey
0x1407cc723  mov     ebx, eax
0x1407cc725  test    eax, eax
0x1407cc727  js      loc_1407CCB4A
0x1407cc72d  mov     eax, [rdi+8]
0x1407cc730  lea     rcx, [rsp+5A0h+Length]
0x1407cc735  mov     [rsp+5A0h+var_578], rcx; ResultLength
0x1407cc73a  lea     rdx, CapeSD; ValueName
0x1407cc741  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407cc746  mov     r9, rdi; KeyValueInformation
0x1407cc749  mov     r8d, 2; KeyValueInformationClass
0x1407cc74f  mov     [rsp+5A0h+var_558], rax
0x1407cc754  mov     dword ptr [rsp+5A0h+ResultLength], r14d; Length
0x1407cc759  call    ZwQueryValueKey
0x1407cc75e  mov     ebx, eax
0x1407cc760  test    eax, eax
0x1407cc762  js      loc_1407CCB4A
0x1407cc768  mov     rcx, [rsp+5A0h+var_548]
0x1407cc76d  lea     rdx, CapeStagedSD; ValueName
0x1407cc774  mov     eax, [rdi+8]
0x1407cc777  inc     r13d
0x1407cc77a  and     r13d, 0FFFFFFFEh
0x1407cc77e  mov     r9, rdi; KeyValueInformation
0x1407cc781  add     r13d, dword ptr [rsp+5A0h+var_558]
0x1407cc786  mov     r8d, 2; KeyValueInformationClass
0x1407cc78c  add     r13d, ecx
0x1407cc78f  mov     [rsp+5A0h+var_558], rax
0x1407cc794  lea     rcx, [rsp+5A0h+Length]
0x1407cc799  mov     [rsp+5A0h+var_578], rcx; ResultLength
0x1407cc79e  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407cc7a3  mov     dword ptr [rsp+5A0h+ResultLength], r14d; Length
0x1407cc7a8  call    ZwQueryValueKey
0x1407cc7ad  mov     ebx, eax
0x1407cc7af  test    eax, eax
0x1407cc7b1  js      loc_1407CCB4A
0x1407cc7b7  mov     rcx, [rsp+5A0h+KeyHandle]; Handle
0x1407cc7bc  lea     eax, [r13+7]
0x1407cc7c0  mov     r13, [rsp+5A0h+var_558]
0x1407cc7c5  mov     edx, 0FFFFFFF8h
0x1407cc7ca  add     r13d, 7
0x1407cc7ce  and     eax, edx
0x1407cc7d0  add     r13d, eax
0x1407cc7d3  and     r13d, edx
0x1407cc7d6  add     r13d, [rdi+8]
0x1407cc7da  call    ZwClose
0x1407cc7df  mov     ecx, [rsp+5A0h+var_560]
0x1407cc7e3  mov     eax, [rsp+5A0h+var_55C]
0x1407cc7e7  inc     ecx
0x1407cc7e9  mov     [rsp+5A0h+KeyHandle], rsi
0x1407cc7ee  jmp     loc_1407CC5A0
0x1407cc7f3  mov     ebx, 0C000009Ah
0x1407cc7f8  jmp     loc_1407CCB4F
0x1407cc7fd  mov     r8d, 70536553h
0x1407cc803  mov     edx, r13d
0x1407cc806  mov     ecx, 100h
0x1407cc80b  mov     r14d, r13d
0x1407cc80e  call    ExAllocatePool2
0x1407cc813  mov     rsi, rax
0x1407cc816  test    rax, rax
0x1407cc819  jz      loc_1407CC58C
0x1407cc81f  mov     r8d, r14d; Size
0x1407cc822  xor     edx, edx; Val
0x1407cc824  mov     rcx, rax; void *
0x1407cc827  call    memset_0
0x1407cc82c  mov     ecx, [rsp+5A0h+var_55C]
0x1407cc830  lea     rax, [r14+rsi]
0x1407cc834  imul    r13, rcx, 38h ; '8'
0x1407cc838  mov     [rsp+5A0h+var_558], rax
0x1407cc83d  add     r13, rsi
0x1407cc840  xor     r14d, r14d
0x1407cc843  mov     [rsp+5A0h+var_560], r14d
0x1407cc848  cmp     r14d, ecx
0x1407cc84b  jnb     loc_1407CCB2A
0x1407cc851  lea     r9, aRegistryMachin_129; "\\Registry\\Machine\\System\\CurrentCon"...
0x1407cc858  mov     dword ptr [rsp+5A0h+ResultLength], r14d
0x1407cc85d  lea     r8, aSD; "%s\\%d"
0x1407cc864  mov     edx, 157h; cbDest
0x1407cc869  lea     rcx, [rsp+5A0h+pszDest]; pszDest
0x1407cc86e  call    RtlStringCbPrintfW
0x1407cc873  mov     ebx, eax
0x1407cc875  test    eax, eax
0x1407cc877  js      loc_1407CCB4A
0x1407cc87d  lea     r8, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407cc882  mov     edx, 201h; DesiredAccess
0x1407cc887  lea     rcx, [rsp+5A0h+pszDest]; SourceString
0x1407cc88c  call    SepRegOpenKey
0x1407cc891  mov     ebx, eax
0x1407cc893  test    eax, eax
0x1407cc895  js      loc_1407CCB4A
0x1407cc89b  mov     r12d, [rsp+5A0h+var_550]
0x1407cc8a0  lea     rax, [rsp+5A0h+Length]
0x1407cc8a5  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407cc8aa  lea     rdx, CapeFlags; ValueName
0x1407cc8b1  mov     [rsp+5A0h+var_578], rax; ResultLength
0x1407cc8b6  mov     r9, rdi; KeyValueInformation
0x1407cc8b9  mov     r8d, 2; KeyValueInformationClass
0x1407cc8bf  mov     dword ptr [rsp+5A0h+ResultLength], r12d; Length
0x1407cc8c4  call    ZwQueryValueKey
0x1407cc8c9  mov     ebx, eax
0x1407cc8cb  test    eax, eax
0x1407cc8cd  js      loc_1407CCB4A
0x1407cc8d3  cmp     dword ptr [rdi+8], 4
0x1407cc8d7  jnz     loc_1407CCB23
0x1407cc8dd  mov     eax, r14d
0x1407cc8e0  lea     rdx, CapeName; ValueName
0x1407cc8e7  imul    r14, rax, 38h ; '8'
0x1407cc8eb  mov     eax, [rdi+0Ch]
0x1407cc8ee  mov     r9, rdi; KeyValueInformation
0x1407cc8f1  mov     r8d, 2; KeyValueInformationClass
0x1407cc8f7  mov     [r14+rsi+30h], eax
0x1407cc8fc  lea     rax, [rsp+5A0h+Length]
0x1407cc901  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407cc906  mov     [rsp+5A0h+var_578], rax; ResultLength
0x1407cc90b  mov     dword ptr [rsp+5A0h+ResultLength], r12d; Length
0x1407cc910  call    ZwQueryValueKey
0x1407cc915  mov     ebx, eax
0x1407cc917  test    eax, eax
0x1407cc919  js      loc_1407CCB4A
0x1407cc91f  mov     eax, [rdi+8]
0x1407cc922  lea     r12, [r13+1]
0x1407cc926  and     r12, 0FFFFFFFFFFFFFFFEh
0x1407cc92a  add     rax, r12
0x1407cc92d  cmp     rax, [rsp+5A0h+var_558]
0x1407cc932  ja      loc_1407CCB1C
0x1407cc938  movzx   eax, word ptr [rdi+8]
0x1407cc93c  lea     rdx, [rdi+0Ch]; Src
0x1407cc940  mov     [r14+rsi+2], ax
0x1407cc946  mov     rcx, r12; void *
0x1407cc949  mov     [r14+rsi], ax
  ... truncated ...
```
