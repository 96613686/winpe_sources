# DfscCredCreateExplicitCredentials

- ea: `0x1400221cc`
- end: `0x14002261a`
- name: `DfscCredCreateExplicitCredentials`
- size: `1102`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int16, const void **, __int64, int, char *AuthIdentityByteArray, unsigned int AuthIdentityLength, int, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140029160`

## callees

- `0x1400025a0`
- `0x140006080`
- `0x140006380`
- `0x1400221cc`
- `0x140022620`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14002221a`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14002222c`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14002221a`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14002222c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002257c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022592`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400225b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400225cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002257c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022592`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400225b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400225cb`
- `ntoskrnl!ExAllocatePool2` at `0x1400222d0`
- `ntoskrnl!ExAllocatePool2` at `0x140022331`
- `ntoskrnl!ExAllocatePool2` at `0x1400224a2`
- `ntoskrnl!ExAllocatePool2` at `0x1400222d0`
- `ntoskrnl!ExAllocatePool2` at `0x140022331`
- `ntoskrnl!ExAllocatePool2` at `0x1400224a2`
- `ksecdd!SspiEncodeStringsAsAuthIdentity` at `0x140022390`
- `ksecdd!SspiEncodeStringsAsAuthIdentity` at `0x140022390`
- `ksecdd!SspiLocalFree` at `0x1400225fa`
- `ksecdd!SspiLocalFree` at `0x1400225fa`
- `ksecdd!SspiFreeAuthIdentity` at `0x1400225e4`
- `ksecdd!SspiFreeAuthIdentity` at `0x1400225e4`
- `ksecdd!SspiMarshalAuthIdentity` at `0x140022405`
- `ksecdd!SspiMarshalAuthIdentity` at `0x140022405`
- `ksecdd!MapSecurityError` at `0x1400223a0`
- `ksecdd!MapSecurityError` at `0x140022415`
- `ksecdd!MapSecurityError` at `0x1400223a0`
- `ksecdd!MapSecurityError` at `0x140022415`

## pseudocode

```c
__int64 __fastcall DfscCredCreateExplicitCredentials(
        unsigned __int16 *a1,
        __int16 a2,
        const void **a3,
        __int64 a4,
        int a5,
        char *AuthIdentityByteArray,
        unsigned int AuthIdentityLength,
        int a8,
        unsigned int a9,
        _QWORD *a10)
{
  void *v10; // r14
  __int16 v11; // r13
  unsigned int v15; // ebx
  unsigned int v16; // esi
  __int64 *v17; // rdx
  void *v18; // r15
  void *Pool2; // rax
  __int64 v20; // rax
  void *v21; // rax
  const WCHAR *v22; // rdx
  SECURITY_STATUS v23; // edi
  NTSTATUS v24; // eax
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  int v27; // eax
  unsigned int v28; // eax
  unsigned int v30; // r12d
  char *v31; // rax
  char *v32; // rdi
  unsigned int v33; // eax
  __int16 v34; // ax
  int v35; // eax
  _QWORD *v36; // rax
  struct _UNICODE_STRING v37; // xmm0
  unsigned int v38; // [rsp+30h] [rbp-38h]
  int v39; // [rsp+34h] [rbp-34h]
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE ppAuthIdentity; // [rsp+38h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-28h] BYREF
  struct _UNICODE_STRING v42; // [rsp+50h] [rbp-18h] BYREF

  v10 = 0;
  v11 = a2;
  ppAuthIdentity = 0;
  v39 = 0;
  *a10 = 0;
  DestinationString = 0;
  v42 = 0;
  RtlInitUnicodeStringEx(&DestinationString, 0);
  RtlInitUnicodeStringEx(&v42, 0);
  v15 = DfscCreateNameFromUnicodeString(&DestinationString, a4, 2017683012);
  if ( v15 )
    goto LABEL_46;
  v16 = a9;
  if ( a8 != 1 )
  {
    v38 = 0;
    goto LABEL_8;
  }
  v17 = &ExplicitNullCredentials;
  v38 = (a9 >> 2) & 1;
  if ( *a1 )
    v17 = (__int64 *)a1;
  v15 = DfscCreateNameFromUnicodeString(&v42, v17, 2017683012);
  if ( !v15 )
  {
    v11 = a2;
LABEL_8:
    v18 = 0;
    if ( !AuthIdentityByteArray && a1[1] )
    {
      Pool2 = (void *)ExAllocatePool2(258, *a1 + 2LL, 2017683012);
      v18 = Pool2;
      if ( !Pool2 )
      {
        v15 = -1073741670;
LABEL_46:
        if ( DestinationString.Buffer )
        {
          ExFreePoolWithTag(DestinationString.Buffer, 0);
          DestinationString.Buffer = 0;
        }
        if ( v42.Buffer )
        {
          ExFreePoolWithTag(v42.Buffer, 0);
          v42.Buffer = 0;
        }
        goto LABEL_50;
      }
      memset(Pool2, 0, *a1 + 2LL);
      memmove(v18, *((const void **)a1 + 1), *a1);
      v20 = *(unsigned __int16 *)a3;
      if ( (_WORD)v20 || (v16 & 2) != 0 )
      {
        v21 = (void *)ExAllocatePool2(258, v20 + 2, 2017683012);
        v10 = v21;
        if ( !v21 )
        {
          v15 = -1073741670;
LABEL_42:
          ExFreePoolWithTag(v18, 0);
LABEL_43:
          if ( v10 )
            ExFreePoolWithTag(v10, 0);
          goto LABEL_45;
        }
        memset(v21, 0, *(unsigned __int16 *)a3 + 2LL);
        memmove(v10, a3[1], *(unsigned __int16 *)a3);
      }
      v22 = 0;
      if ( !v11 )
        v22 = &pszDomainName;
      v23 = SspiEncodeStringsAsAuthIdentity((PCWSTR)v18, v22, (PCWSTR)v10, &ppAuthIdentity);
      v24 = MapSecurityError(v23);
      v15 = v24;
      if ( v24 < 0 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
        {
          goto LABEL_42;
        }
        v26 = 10;
        goto LABEL_23;
      }
      v23 = SspiMarshalAuthIdentity(ppAuthIdentity, &AuthIdentityLength, &AuthIdentityByteArray);
      v24 = MapSecurityError(v23);
      v15 = v24;
      if ( v24 < 0 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
        {
          goto LABEL_42;
        }
        v26 = 11;
LABEL_23:
        WPP_SF_dd(v25->AttachedDevice, v26, WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids, (unsigned int)v24, v23);
        goto LABEL_42;
      }
      v39 = 1;
    }
    v27 = AuthIdentityLength + 45;
    if ( (v16 & 2) != 0 || *(_WORD *)a3 )
      v27 = AuthIdentityLength + 70;
    v28 = (v27 + 1) & 0xFFFFFFFE;
    if ( v28 > 0xFFFF )
      return 3221225485LL;
    v30 = v28 + AuthIdentityLength + 88;
    v31 = (char *)ExAllocatePool2(66, v30, 2017683012);
    v32 = v31;
    if ( v31 )
    {
      memset(v31, 0, v30);
      *(_WORD *)v32 = -32508;
      *((_WORD *)v32 + 1) = v30;
      v33 = 0;
      *((_DWORD *)v32 + 1) = 1;
      if ( AuthIdentityByteArray )
      {
        memmove(v32 + 88, "AuthIdentity", 0xDu);
        v32[85] = 12;
        v34 = AuthIdentityLength;
        if ( AuthIdentityLength )
        {
          memmove(v32 + 101, AuthIdentityByteArray, AuthIdentityLength);
          v34 = AuthIdentityLength;
        }
        *((_WORD *)v32 + 43) = v34;
        v35 = AuthIdentityLength + 24;
        v32[84] = 0;
        v33 = v35 & 0xFFFFFFFC;
      }
      *((_DWORD *)v32 + 20) = 0;
      *((_DWORD *)v32 + 18) = v33;
      *((_DWORD *)v32 + 10) = a8;
      *((_DWORD *)v32 + 11) = v38;
      *((_DWORD *)v32 + 12) = a5;
      v36 = a10;
      *((_QWORD *)v32 + 3) = 0;
      *((_DWORD *)v32 + 13) = (v16 >> 4) & 1;
      v37 = DestinationString;
      *v36 = v32;
      *(struct _UNICODE_STRING *)(v32 + 8) = v37;
      *(struct _UNICODE_STRING *)(v32 + 56) = v42;
    }
    else
    {
      v15 = -1073741670;
    }
    if ( !v18 )
      goto LABEL_43;
    goto LABEL_42;
  }
LABEL_45:
  if ( v15 )
    goto LABEL_46;
LABEL_50:
  if ( ppAuthIdentity )
    SspiFreeAuthIdentity(ppAuthIdentity);
  if ( v39 )
    SspiLocalFree(AuthIdentityByteArray);
  return v15;
}

```

## disassembly

```asm
0x1400221cc  mov     [rsp-40h+arg_8], dx
0x1400221d1  push    rbp
0x1400221d2  push    rbx
0x1400221d3  push    rsi
0x1400221d4  push    rdi
0x1400221d5  push    r12
0x1400221d7  push    r13
0x1400221d9  push    r14
0x1400221db  push    r15
0x1400221dd  mov     rbp, rsp
0x1400221e0  sub     rsp, 68h
0x1400221e4  mov     rax, [rbp+arg_48]
0x1400221eb  xor     r14d, r14d
0x1400221ee  movzx   r13d, dx
0x1400221f2  mov     [rbp+ppAuthIdentity], r14
0x1400221f6  mov     rdi, rcx
0x1400221f9  mov     [rbp+var_34], r14d
0x1400221fd  xorps   xmm0, xmm0
0x140022200  lea     rcx, [rbp+DestinationString]; DestinationString
0x140022204  xorps   xmm1, xmm1
0x140022207  mov     [rax], r14
0x14002220a  xor     edx, edx; SourceString
0x14002220c  mov     rbx, r9
0x14002220f  mov     r12, r8
0x140022212  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140022216  movups  xmmword ptr [rbp+var_18.Length], xmm1
0x14002221a  call    cs:__imp_RtlInitUnicodeStringEx
0x140022221  nop     dword ptr [rax+rax+00h]
0x140022226  xor     edx, edx; SourceString
0x140022228  lea     rcx, [rbp+var_18]; DestinationString
0x14002222c  call    cs:__imp_RtlInitUnicodeStringEx
0x140022233  nop     dword ptr [rax+rax+00h]
0x140022238  mov     r15d, 78436644h
0x14002223e  lea     rcx, [rbp+DestinationString]
0x140022242  mov     r8d, r15d
0x140022245  mov     rdx, rbx
0x140022248  call    DfscCreateNameFromUnicodeString
0x14002224d  mov     ebx, eax
0x14002224f  test    eax, eax
0x140022251  jnz     loc_1400225A5
0x140022257  cmp     [rbp+arg_38], 1
0x14002225e  mov     esi, [rbp+arg_40]
0x140022264  jnz     short loc_1400222A1
0x140022266  mov     r13d, esi
0x140022269  lea     rdx, ExplicitNullCredentials
0x140022270  shr     r13d, 2
0x140022274  lea     rcx, [rbp+var_18]
0x140022278  and     r13d, 1
0x14002227c  mov     r8d, r15d
0x14002227f  cmp     [rdi], r14w
0x140022283  mov     [rbp+var_38], r13d
0x140022287  cmovnz  rdx, rdi
0x14002228b  call    DfscCreateNameFromUnicodeString
0x140022290  mov     ebx, eax
0x140022292  test    eax, eax
0x140022294  jnz     loc_1400225A1
0x14002229a  movzx   r13d, [rbp+arg_8]
0x14002229f  jmp     short loc_1400222A5
0x1400222a1  mov     [rbp+var_38], r14d
0x1400222a5  xor     eax, eax
0x1400222a7  mov     r15, r14
0x1400222aa  cmp     [rbp+AuthIdentityByteArray], rax
0x1400222ae  jnz     loc_14002245B
0x1400222b4  cmp     [rdi+2], ax
0x1400222b8  jz      loc_14002245B
0x1400222be  movzx   edx, word ptr [rdi]
0x1400222c1  mov     ecx, 102h
0x1400222c6  add     rdx, 2
0x1400222ca  mov     r8d, 78436644h
0x1400222d0  call    cs:__imp_ExAllocatePool2
0x1400222d7  nop     dword ptr [rax+rax+00h]
0x1400222dc  xor     ebx, ebx
0x1400222de  mov     r15, rax
0x1400222e1  test    rax, rax
0x1400222e4  jnz     short loc_1400222F0
0x1400222e6  mov     ebx, 0C000009Ah
0x1400222eb  jmp     loc_1400225A5
0x1400222f0  movzx   r8d, word ptr [rdi]
0x1400222f4  xor     edx, edx; Val
0x1400222f6  add     r8, 2; Size
0x1400222fa  mov     rcx, r15; void *
0x1400222fd  call    memset
0x140022302  movzx   r8d, word ptr [rdi]; Size
0x140022306  mov     rcx, r15; void *
0x140022309  mov     rdx, [rdi+8]; Src
0x14002230d  call    memmove
0x140022312  movzx   eax, word ptr [r12]
0x140022317  test    ax, ax
0x14002231a  jnz     short loc_140022322
0x14002231c  test    sil, 2
0x140022320  jz      short loc_140022374
0x140022322  lea     rdx, [rax+2]
0x140022326  mov     ecx, 102h
0x14002232b  mov     r8d, 78436644h
0x140022331  call    cs:__imp_ExAllocatePool2
0x140022338  nop     dword ptr [rax+rax+00h]
0x14002233d  mov     r14, rax
0x140022340  test    rax, rax
0x140022343  jnz     short loc_14002234F
0x140022345  mov     ebx, 0C000009Ah
0x14002234a  jmp     loc_140022577
0x14002234f  movzx   r8d, word ptr [r12]
0x140022354  xor     edx, edx; Val
0x140022356  add     r8, 2; Size
0x14002235a  mov     rcx, r14; void *
0x14002235d  call    memset
0x140022362  movzx   r8d, word ptr [r12]; Size
0x140022367  mov     rcx, r14; void *
0x14002236a  mov     rdx, [r12+8]; Src
0x14002236f  call    memmove
0x140022374  lea     rax, pszDomainName
0x14002237b  test    r13w, r13w
0x14002237f  mov     rdx, rbx
0x140022382  lea     r9, [rbp+ppAuthIdentity]; ppAuthIdentity
0x140022386  cmovz   rdx, rax; pszDomainName
0x14002238a  mov     r8, r14; pszPackedCredentialsString
0x14002238d  mov     rcx, r15; pszUserName
0x140022390  call    cs:__imp_SspiEncodeStringsAsAuthIdentity
0x140022397  nop     dword ptr [rax+rax+00h]
0x14002239c  mov     ecx, eax; SecStatus
0x14002239e  mov     edi, eax
0x1400223a0  call    cs:__imp_MapSecurityError
0x1400223a7  nop     dword ptr [rax+rax+00h]
0x1400223ac  xor     r13d, r13d
0x1400223af  mov     ebx, eax
0x1400223b1  test    eax, eax
0x1400223b3  jns     short loc_1400223F9
0x1400223b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400223bc  lea     rdx, WPP_GLOBAL_Control
0x1400223c3  cmp     rcx, rdx
0x1400223c6  jz      loc_140022577
0x1400223cc  test    dword ptr [rcx+2Ch], 100h
0x1400223d3  jz      loc_140022577
0x1400223d9  lea     edx, [r13+0Ah]
0x1400223dd  mov     rcx, [rcx+18h]
0x1400223e1  lea     r8, WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids
0x1400223e8  mov     r9d, eax
0x1400223eb  mov     [rsp+68h+var_48], edi
0x1400223ef  call    WPP_SF_dd
0x1400223f4  jmp     loc_140022577
0x1400223f9  mov     rcx, [rbp+ppAuthIdentity]; AuthIdentity
0x1400223fd  lea     r8, [rbp+AuthIdentityByteArray]; AuthIdentityByteArray
0x140022401  lea     rdx, [rbp+AuthIdentityLength]; AuthIdentityLength
0x140022405  call    cs:__imp_SspiMarshalAuthIdentity
0x14002240c  nop     dword ptr [rax+rax+00h]
0x140022411  mov     ecx, eax; SecStatus
0x140022413  mov     edi, eax
0x140022415  call    cs:__imp_MapSecurityError
0x14002241c  nop     dword ptr [rax+rax+00h]
0x140022421  mov     ebx, eax
0x140022423  test    eax, eax
0x140022425  jns     short loc_140022452
0x140022427  mov     rcx, cs:WPP_GLOBAL_Control
0x14002242e  lea     rdx, WPP_GLOBAL_Control
0x140022435  cmp     rcx, rdx
0x140022438  jz      loc_140022577
0x14002243e  test    dword ptr [rcx+2Ch], 100h
0x140022445  jz      loc_140022577
0x14002244b  mov     edx, 0Bh
0x140022450  jmp     short loc_1400223DD
0x140022452  mov     [rbp+var_34], 1
0x140022459  jmp     short loc_14002245E
0x14002245b  xor     r13d, r13d
0x14002245e  mov     ecx, [rbp+AuthIdentityLength]
0x140022461  lea     eax, [rcx+2Dh]
0x140022464  test    sil, 2
0x140022468  jnz     short loc_140022471
0x14002246a  cmp     [r12], r13w
0x14002246f  jz      short loc_140022474
0x140022471  add     eax, 19h
0x140022474  inc     eax
0x140022476  and     eax, 0FFFFFFFEh
0x140022479  cmp     eax, 0FFFFh
0x14002247e  jbe     short loc_14002248A
0x140022480  mov     eax, 0C000000Dh
0x140022485  jmp     loc_140022608
0x14002248a  lea     r12d, [rcx+58h]
0x14002248e  mov     r8d, 78436644h
0x140022494  add     r12d, eax
0x140022497  mov     ecx, 42h ; 'B'
0x14002249c  mov     edx, r12d
0x14002249f  mov     r13d, r12d
0x1400224a2  call    cs:__imp_ExAllocatePool2
0x1400224a9  nop     dword ptr [rax+rax+00h]
0x1400224ae  mov     rdi, rax
0x1400224b1  test    rax, rax
0x1400224b4  jnz     short loc_1400224C0
0x1400224b6  mov     ebx, 0C000009Ah
0x1400224bb  jmp     loc_140022572
0x1400224c0  mov     r8, r13; Size
0x1400224c3  xor     edx, edx; Val
0x1400224c5  mov     rcx, rdi; void *
0x1400224c8  call    memset
0x1400224cd  xor     r13d, r13d
0x1400224d0  mov     word ptr [rdi], 8104h
0x1400224d5  mov     [rdi+2], r12w
0x1400224da  mov     eax, r13d
0x1400224dd  mov     dword ptr [rdi+4], 1
0x1400224e4  cmp     [rbp+AuthIdentityByteArray], r13
0x1400224e8  jz      short loc_14002252D
0x1400224ea  lea     rcx, [rdi+58h]; void *
0x1400224ee  lea     r8d, [r13+0Dh]; Size
0x1400224f2  lea     rdx, Src; "AuthIdentity"
0x1400224f9  call    memmove
0x1400224fe  mov     byte ptr [rdi+55h], 0Ch
0x140022502  mov     eax, [rbp+AuthIdentityLength]
0x140022505  test    eax, eax
0x140022507  jz      short loc_14002251C
0x140022509  mov     rdx, [rbp+AuthIdentityByteArray]; Src
0x14002250d  lea     rcx, [rdi+65h]; void *
0x140022511  mov     r8d, eax; Size
0x140022514  call    memmove
0x140022519  mov     eax, [rbp+AuthIdentityLength]
0x14002251c  mov     [rdi+56h], ax
0x140022520  mov     eax, [rbp+AuthIdentityLength]
0x140022523  add     eax, 18h
0x140022526  mov     [rdi+54h], r13b
0x14002252a  and     eax, 0FFFFFFFCh
0x14002252d  mov     [rdi+50h], r13d
0x140022531  mov     [rdi+48h], eax
0x140022534  mov     eax, [rbp+arg_38]
0x14002253a  mov     [rdi+28h], eax
0x14002253d  mov     eax, [rbp+var_38]
0x140022540  mov     [rdi+2Ch], eax
0x140022543  mov     eax, [rbp+arg_20]
0x140022546  mov     [rdi+30h], eax
0x140022549  mov     rax, [rbp+arg_48]
0x140022550  mov     [rdi+18h], r13
0x140022554  shr     esi, 4
0x140022557  and     esi, 1
0x14002255a  mov     [rdi+34h], esi
0x14002255d  movups  xmm0, xmmword ptr [rbp+DestinationString.Length]
0x140022561  mov     [rax], rdi
0x140022564  movdqu  xmmword ptr [rdi+8], xmm0
0x140022569  movups  xmm1, xmmword ptr [rbp+var_18.Length]
0x14002256d  movdqu  xmmword ptr [rdi+38h], xmm1
0x140022572  test    r15, r15
0x140022575  jz      short loc_140022588
0x140022577  xor     edx, edx; Tag
0x140022579  mov     rcx, r15; P
0x14002257c  call    cs:__imp_ExFreePoolWithTag
0x140022583  nop     dword ptr [rax+rax+00h]
0x140022588  test    r14, r14
0x14002258b  jz      short loc_14002259E
0x14002258d  xor     edx, edx; Tag
0x14002258f  mov     rcx, r14; P
0x140022592  call    cs:__imp_ExFreePoolWithTag
0x140022599  nop     dword ptr [rax+rax+00h]
0x14002259e  xor     r14d, r14d
0x1400225a1  test    ebx, ebx
0x1400225a3  jz      short loc_1400225DB
0x1400225a5  mov     rcx, [rbp+DestinationString.Buffer]; P
0x1400225a9  test    rcx, rcx
0x1400225ac  jz      short loc_1400225C0
0x1400225ae  xor     edx, edx; Tag
0x1400225b0  call    cs:__imp_ExFreePoolWithTag
0x1400225b7  nop     dword ptr [rax+rax+00h]
0x1400225bc  mov     [rbp+DestinationString.Buffer], r14
0x1400225c0  mov     rcx, [rbp+var_18.Buffer]; P
0x1400225c4  test    rcx, rcx
0x1400225c7  jz      short loc_1400225DB
0x1400225c9  xor     edx, edx; Tag
0x1400225cb  call    cs:__imp_ExFreePoolWithTag
0x1400225d2  nop     dword ptr [rax+rax+00h]
0x1400225d7  mov     [rbp+var_18.Buffer], r14
0x1400225db  mov     rcx, [rbp+ppAuthIdentity]; AuthData
0x1400225df  test    rcx, rcx
0x1400225e2  jz      short loc_1400225F0
0x1400225e4  call    cs:__imp_SspiFreeAuthIdentity
0x1400225eb  nop     dword ptr [rax+rax+00h]
0x1400225f0  cmp     [rbp+var_34], r14d
0x1400225f4  jz      short loc_140022606
0x1400225f6  mov     rcx, [rbp+AuthIdentityByteArray]; DataBuffer
0x1400225fa  call    cs:__imp_SspiLocalFree
0x140022601  nop     dword ptr [rax+rax+00h]
0x140022606  mov     eax, ebx
0x140022608  add     rsp, 68h
0x14002260c  pop     r15
0x14002260e  pop     r14
0x140022610  pop     r13
0x140022612  pop     r12
0x140022614  pop     rdi
0x140022615  pop     rsi
0x140022616  pop     rbx
0x140022617  pop     rbp
0x140022618  retn
```
