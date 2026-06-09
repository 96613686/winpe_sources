# SepReadAndPopulateCapes

- ea: `0x1407c95e8`
- end: `0x1407c9d46`
- name: `SepReadAndPopulateCapes`
- size: `1886`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14062f85c`

## callees

- `0x1403f4ae8`
- `0x14062fa64`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406dab50`
- `0x1406dab70`
- `0x1406f4480`
- `0x1406f4880`
- `0x1407c95e8`
- `0x1408dc6b0`
- `0x140a4c4e4`
- `0x140bae410`
- `0x140bae8e0`

## string_xrefs

- `0x1407c9730`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\CentralizedAccessPolicies\CAPEs`
- `0x1407c99d1`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\CentralizedAccessPolicies\CAPEs`

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
    Pool2 = (ULONG *)ExAllocatePool2(256, (unsigned int)(a2 + 18), 1884513619);
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
          v5 = (_DWORD *)ExAllocatePool2(256, Length, 1884513619);
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
        v11 = ZwQueryValueKey(
                KeyHandlea,
                (PUNICODE_STRING)&ExpPlatformBinaryLock.WaitBlockFill11[160],
                KeyValuePartialInformation,
                Pool2,
                v15,
                &Length);
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
      v22 = (char *)ExAllocatePool2(256, v17, 1884513619);
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
          v11 = ZwQueryValueKey(
                  KeyHandlea,
                  (PUNICODE_STRING)&ExpPlatformBinaryLock.WaitBlockFill11[160],
                  KeyValuePartialInformation,
                  Pool2,
                  v25,
                  &Length);
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
  v5 = (_DWORD *)ExAllocatePool2(256, Length, 1884513619);
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
0x1407c95e8  push    rbp
0x1407c95ea  push    rbx
0x1407c95eb  push    rsi
0x1407c95ec  push    rdi
0x1407c95ed  push    r12
0x1407c95ef  push    r13
0x1407c95f1  push    r14
0x1407c95f3  push    r15
0x1407c95f5  lea     rbp, [rsp-468h]
0x1407c95fd  sub     rsp, 568h
0x1407c9604  mov     rax, cs:__security_cookie
0x1407c960b  xor     rax, rsp
0x1407c960e  mov     [rbp+4A0h+var_50], rax
0x1407c9615  xor     eax, eax
0x1407c9617  mov     [rsp+5A0h+var_538], r9
0x1407c961c  mov     esi, eax
0x1407c961e  mov     [rsp+5A0h+Length], eax
0x1407c9622  mov     [rsp+5A0h+var_570], al
0x1407c9626  lea     r15, [rbp+4A0h+KeyInformation]
0x1407c962d  mov     edi, eax
0x1407c962f  mov     [rsp+5A0h+KeyHandle], rax
0x1407c9634  mov     [rsp+5A0h+var_540], r8
0x1407c9639  lea     rax, [rsp+5A0h+Length]
0x1407c963e  mov     r13d, edx
0x1407c9641  mov     [rsp+5A0h+ResultLength], rax; ResultLength
0x1407c9646  mov     r12d, 230h
0x1407c964c  lea     edx, [rsi+2]; KeyInformationClass
0x1407c964f  mov     r9d, r12d; Length
0x1407c9652  lea     r8, [rbp+4A0h+KeyInformation]; KeyInformation
0x1407c9659  mov     r14, rcx
0x1407c965c  call    ZwQueryKey
0x1407c9661  mov     ebx, eax
0x1407c9663  test    eax, eax
0x1407c9665  jns     short loc_1407C96D3
0x1407c9667  cmp     eax, 80000005h
0x1407c966c  jz      short loc_1407C9679
0x1407c966e  cmp     eax, 0C0000023h
0x1407c9673  jnz     loc_1407C9CCA
0x1407c9679  mov     edx, [rsp+5A0h+Length]
0x1407c967d  mov     ecx, 100h
0x1407c9682  mov     r8d, 70536553h
0x1407c9688  call    ExAllocatePool2
0x1407c968d  mov     r15, rax
0x1407c9690  test    rax, rax
0x1407c9693  jnz     short loc_1407C96A2
0x1407c9695  mov     ebx, 0C000009Ah
0x1407c969a  mov     r12b, sil
0x1407c969d  jmp     loc_1407C9CCF
0x1407c96a2  mov     r12d, [rsp+5A0h+Length]
0x1407c96a7  lea     rax, [rsp+5A0h+Length]
0x1407c96ac  mov     r9d, r12d; Length
0x1407c96af  mov     [rsp+5A0h+ResultLength], rax; ResultLength
0x1407c96b4  mov     r8, r15; KeyInformation
0x1407c96b7  mov     [rsp+5A0h+var_570], 1
0x1407c96bc  mov     edx, 2; KeyInformationClass
0x1407c96c1  mov     rcx, r14; KeyHandle
0x1407c96c4  call    ZwQueryKey
0x1407c96c9  mov     ebx, eax
0x1407c96cb  test    eax, eax
0x1407c96cd  js      loc_1407C9CCA
0x1407c96d3  mov     eax, [r15+14h]
0x1407c96d7  mov     [rsp+5A0h+var_55C], eax
0x1407c96db  test    eax, eax
0x1407c96dd  jnz     short loc_1407C96E8
0x1407c96df  xor     ecx, ecx
0x1407c96e1  xor     eax, eax
0x1407c96e3  jmp     loc_1407C9CB7
0x1407c96e8  lea     r14d, [r13+12h]
0x1407c96ec  mov     ecx, 100h
0x1407c96f1  mov     edx, r14d
0x1407c96f4  mov     r8d, 70536553h
0x1407c96fa  mov     [rsp+5A0h+var_550], r14d
0x1407c96ff  call    ExAllocatePool2
0x1407c9704  mov     rdi, rax
0x1407c9707  test    rax, rax
0x1407c970a  jnz     short loc_1407C9716
0x1407c970c  mov     ebx, 0C000009Ah
0x1407c9711  jmp     loc_1407C9CCA
0x1407c9716  mov     eax, [rsp+5A0h+var_55C]
0x1407c971a  imul    r13d, eax, 38h ; '8'
0x1407c971e  xor     ecx, ecx
0x1407c9720  mov     [rsp+5A0h+var_560], ecx
0x1407c9724  cmp     ecx, eax
0x1407c9726  jnb     loc_1407C997D
0x1407c972c  mov     dword ptr [rsp+5A0h+ResultLength], ecx
0x1407c9730  lea     r9, aRegistryMachin_129; "\\Registry\\Machine\\System\\CurrentCon"...
0x1407c9737  lea     rcx, [rsp+5A0h+pszDest]; pszDest
0x1407c973c  mov     edx, 157h; cbDest
0x1407c9741  lea     r8, aSD; "%s\\%d"
0x1407c9748  call    RtlStringCbPrintfW
0x1407c974d  mov     ebx, eax
0x1407c974f  test    eax, eax
0x1407c9751  js      loc_1407C9CCA
0x1407c9757  lea     r8, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407c975c  mov     edx, 201h; DesiredAccess
0x1407c9761  lea     rcx, [rsp+5A0h+pszDest]; SourceString
0x1407c9766  call    SepRegOpenKey
0x1407c976b  mov     ebx, eax
0x1407c976d  test    eax, eax
0x1407c976f  js      loc_1407C9CCA
0x1407c9775  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407c977a  lea     rax, [rsp+5A0h+Length]
0x1407c977f  mov     r9d, r12d; Length
0x1407c9782  mov     [rsp+5A0h+ResultLength], rax; ResultLength
0x1407c9787  mov     r8, r15; KeyInformation
0x1407c978a  mov     edx, 2; KeyInformationClass
0x1407c978f  call    ZwQueryKey
0x1407c9794  mov     ebx, eax
0x1407c9796  test    eax, eax
0x1407c9798  jns     short loc_1407C9816
0x1407c979a  cmp     eax, 80000005h
0x1407c979f  jz      short loc_1407C97AC
0x1407c97a1  cmp     eax, 0C0000023h
0x1407c97a6  jnz     loc_1407C9CCA
0x1407c97ac  mov     r12b, [rsp+5A0h+var_570]
0x1407c97b1  test    r12b, r12b
0x1407c97b4  jz      short loc_1407C97C3
0x1407c97b6  mov     edx, 70536553h; Tag
0x1407c97bb  mov     rcx, r15; P
0x1407c97be  call    ExFreePoolWithTag
0x1407c97c3  mov     edx, [rsp+5A0h+Length]
0x1407c97c7  mov     ecx, 100h
0x1407c97cc  mov     r8d, 70536553h
0x1407c97d2  call    ExAllocatePool2
0x1407c97d7  mov     r15, rax
0x1407c97da  test    rax, rax
0x1407c97dd  jz      loc_1407C9973
0x1407c97e3  mov     r12d, [rsp+5A0h+Length]
0x1407c97e8  lea     rax, [rsp+5A0h+Length]
0x1407c97ed  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407c97f2  mov     r9d, r12d; Length
0x1407c97f5  mov     r8, r15; KeyInformation
0x1407c97f8  mov     [rsp+5A0h+ResultLength], rax; ResultLength
0x1407c97fd  mov     edx, 2; KeyInformationClass
0x1407c9802  mov     [rsp+5A0h+var_570], 1
0x1407c9807  call    ZwQueryKey
0x1407c980c  mov     ebx, eax
0x1407c980e  test    eax, eax
0x1407c9810  js      loc_1407C9CCA
0x1407c9816  mov     ebx, [r15+28h]
0x1407c981a  add     ebx, 12h
0x1407c981d  cmp     ebx, r14d
0x1407c9820  jbe     short loc_1407C983F
0x1407c9822  mov     edx, ebx
0x1407c9824  mov     rcx, rdi
0x1407c9827  call    SepRmCapPoolExpand
0x1407c982c  mov     rdi, rax
0x1407c982f  test    rax, rax
0x1407c9832  jz      loc_1407C970C
0x1407c9838  mov     r14d, ebx
0x1407c983b  mov     [rsp+5A0h+var_550], ebx
0x1407c983f  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407c9844  lea     rax, [rsp+5A0h+Length]
0x1407c9849  mov     [rsp+5A0h+var_578], rax; ResultLength
0x1407c984e  lea     rdx, ExpPlatformBinaryLock.___u33+0A0h; ValueName
0x1407c9855  mov     r9, rdi; KeyValueInformation
0x1407c9858  mov     dword ptr [rsp+5A0h+ResultLength], r14d; Length
0x1407c985d  mov     r8d, 2; KeyValueInformationClass
0x1407c9863  call    ZwQueryValueKey
0x1407c9868  mov     ebx, eax
0x1407c986a  test    eax, eax
0x1407c986c  js      loc_1407C9CCA
0x1407c9872  mov     eax, [rdi+8]
0x1407c9875  lea     rcx, [rsp+5A0h+Length]
0x1407c987a  mov     [rsp+5A0h+var_578], rcx; ResultLength
0x1407c987f  lea     rdx, CapePredicate; ValueName
0x1407c9886  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407c988b  mov     r9, rdi; KeyValueInformation
0x1407c988e  mov     r8d, 2; KeyValueInformationClass
0x1407c9894  mov     [rsp+5A0h+var_548], rax
0x1407c9899  mov     dword ptr [rsp+5A0h+ResultLength], r14d; Length
0x1407c989e  call    ZwQueryValueKey
0x1407c98a3  mov     ebx, eax
0x1407c98a5  test    eax, eax
0x1407c98a7  js      loc_1407C9CCA
0x1407c98ad  mov     eax, [rdi+8]
0x1407c98b0  lea     rcx, [rsp+5A0h+Length]
0x1407c98b5  mov     [rsp+5A0h+var_578], rcx; ResultLength
0x1407c98ba  lea     rdx, CapeSD; ValueName
0x1407c98c1  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407c98c6  mov     r9, rdi; KeyValueInformation
0x1407c98c9  mov     r8d, 2; KeyValueInformationClass
0x1407c98cf  mov     [rsp+5A0h+var_558], rax
0x1407c98d4  mov     dword ptr [rsp+5A0h+ResultLength], r14d; Length
0x1407c98d9  call    ZwQueryValueKey
0x1407c98de  mov     ebx, eax
0x1407c98e0  test    eax, eax
0x1407c98e2  js      loc_1407C9CCA
0x1407c98e8  mov     rcx, [rsp+5A0h+var_548]
0x1407c98ed  lea     rdx, CapeStagedSD; ValueName
0x1407c98f4  mov     eax, [rdi+8]
0x1407c98f7  inc     r13d
0x1407c98fa  and     r13d, 0FFFFFFFEh
0x1407c98fe  mov     r9, rdi; KeyValueInformation
0x1407c9901  add     r13d, dword ptr [rsp+5A0h+var_558]
0x1407c9906  mov     r8d, 2; KeyValueInformationClass
0x1407c990c  add     r13d, ecx
0x1407c990f  mov     [rsp+5A0h+var_558], rax
0x1407c9914  lea     rcx, [rsp+5A0h+Length]
0x1407c9919  mov     [rsp+5A0h+var_578], rcx; ResultLength
0x1407c991e  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407c9923  mov     dword ptr [rsp+5A0h+ResultLength], r14d; Length
0x1407c9928  call    ZwQueryValueKey
0x1407c992d  mov     ebx, eax
0x1407c992f  test    eax, eax
0x1407c9931  js      loc_1407C9CCA
0x1407c9937  mov     rcx, [rsp+5A0h+KeyHandle]; Handle
0x1407c993c  lea     eax, [r13+7]
0x1407c9940  mov     r13, [rsp+5A0h+var_558]
0x1407c9945  mov     edx, 0FFFFFFF8h
0x1407c994a  add     r13d, 7
0x1407c994e  and     eax, edx
0x1407c9950  add     r13d, eax
0x1407c9953  and     r13d, edx
0x1407c9956  add     r13d, [rdi+8]
0x1407c995a  call    ZwClose
0x1407c995f  mov     ecx, [rsp+5A0h+var_560]
0x1407c9963  mov     eax, [rsp+5A0h+var_55C]
0x1407c9967  inc     ecx
0x1407c9969  mov     [rsp+5A0h+KeyHandle], rsi
0x1407c996e  jmp     loc_1407C9720
0x1407c9973  mov     ebx, 0C000009Ah
0x1407c9978  jmp     loc_1407C9CCF
0x1407c997d  mov     r8d, 70536553h
0x1407c9983  mov     edx, r13d
0x1407c9986  mov     ecx, 100h
0x1407c998b  mov     r14d, r13d
0x1407c998e  call    ExAllocatePool2
0x1407c9993  mov     rsi, rax
0x1407c9996  test    rax, rax
0x1407c9999  jz      loc_1407C970C
0x1407c999f  mov     r8d, r14d; Size
0x1407c99a2  xor     edx, edx; Val
0x1407c99a4  mov     rcx, rax; void *
0x1407c99a7  call    memset_0
0x1407c99ac  mov     ecx, [rsp+5A0h+var_55C]
0x1407c99b0  lea     rax, [r14+rsi]
0x1407c99b4  imul    r13, rcx, 38h ; '8'
0x1407c99b8  mov     [rsp+5A0h+var_558], rax
0x1407c99bd  add     r13, rsi
0x1407c99c0  xor     r14d, r14d
0x1407c99c3  mov     [rsp+5A0h+var_560], r14d
0x1407c99c8  cmp     r14d, ecx
0x1407c99cb  jnb     loc_1407C9CAA
0x1407c99d1  lea     r9, aRegistryMachin_129; "\\Registry\\Machine\\System\\CurrentCon"...
0x1407c99d8  mov     dword ptr [rsp+5A0h+ResultLength], r14d
0x1407c99dd  lea     r8, aSD; "%s\\%d"
0x1407c99e4  mov     edx, 157h; cbDest
0x1407c99e9  lea     rcx, [rsp+5A0h+pszDest]; pszDest
0x1407c99ee  call    RtlStringCbPrintfW
0x1407c99f3  mov     ebx, eax
0x1407c99f5  test    eax, eax
0x1407c99f7  js      loc_1407C9CCA
0x1407c99fd  lea     r8, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407c9a02  mov     edx, 201h; DesiredAccess
0x1407c9a07  lea     rcx, [rsp+5A0h+pszDest]; SourceString
0x1407c9a0c  call    SepRegOpenKey
0x1407c9a11  mov     ebx, eax
0x1407c9a13  test    eax, eax
0x1407c9a15  js      loc_1407C9CCA
0x1407c9a1b  mov     r12d, [rsp+5A0h+var_550]
0x1407c9a20  lea     rax, [rsp+5A0h+Length]
0x1407c9a25  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407c9a2a  lea     rdx, CapeFlags; ValueName
0x1407c9a31  mov     [rsp+5A0h+var_578], rax; ResultLength
0x1407c9a36  mov     r9, rdi; KeyValueInformation
0x1407c9a39  mov     r8d, 2; KeyValueInformationClass
0x1407c9a3f  mov     dword ptr [rsp+5A0h+ResultLength], r12d; Length
0x1407c9a44  call    ZwQueryValueKey
0x1407c9a49  mov     ebx, eax
0x1407c9a4b  test    eax, eax
0x1407c9a4d  js      loc_1407C9CCA
0x1407c9a53  cmp     dword ptr [rdi+8], 4
0x1407c9a57  jnz     loc_1407C9CA3
0x1407c9a5d  mov     eax, r14d
0x1407c9a60  lea     rdx, ExpPlatformBinaryLock.___u33+0A0h; ValueName
0x1407c9a67  imul    r14, rax, 38h ; '8'
0x1407c9a6b  mov     eax, [rdi+0Ch]
0x1407c9a6e  mov     r9, rdi; KeyValueInformation
0x1407c9a71  mov     r8d, 2; KeyValueInformationClass
0x1407c9a77  mov     [r14+rsi+30h], eax
0x1407c9a7c  lea     rax, [rsp+5A0h+Length]
0x1407c9a81  mov     rcx, [rsp+5A0h+KeyHandle]; KeyHandle
0x1407c9a86  mov     [rsp+5A0h+var_578], rax; ResultLength
0x1407c9a8b  mov     dword ptr [rsp+5A0h+ResultLength], r12d; Length
0x1407c9a90  call    ZwQueryValueKey
0x1407c9a95  mov     ebx, eax
0x1407c9a97  test    eax, eax
0x1407c9a99  js      loc_1407C9CCA
0x1407c9a9f  mov     eax, [rdi+8]
0x1407c9aa2  lea     r12, [r13+1]
0x1407c9aa6  and     r12, 0FFFFFFFFFFFFFFFEh
0x1407c9aaa  add     rax, r12
0x1407c9aad  cmp     rax, [rsp+5A0h+var_558]
0x1407c9ab2  ja      loc_1407C9C9C
0x1407c9ab8  movzx   eax, word ptr [rdi+8]
0x1407c9abc  lea     rdx, [rdi+0Ch]; Src
0x1407c9ac0  mov     [r14+rsi+2], ax
0x1407c9ac6  mov     rcx, r12; void *
0x1407c9ac9  mov     [r14+rsi], ax
  ... truncated ...
```
