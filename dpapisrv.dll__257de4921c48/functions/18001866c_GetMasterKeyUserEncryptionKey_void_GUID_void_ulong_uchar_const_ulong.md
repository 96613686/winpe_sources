# GetMasterKeyUserEncryptionKey(void *,_GUID *,void *,ulong,uchar * const,ulong *)

- ea: `0x18001866c`
- end: `0x180018a0e`
- name: `?GetMasterKeyUserEncryptionKey@@YAHPEAXPEAU_GUID@@0KQEAEPEAK@Z`
- size: `930`
- prototype: `__int64 __fastcall(_DWORD *, struct _GUID *, void *, unsigned int, unsigned __int8 *const pbOutput, unsigned int *)`
- caller_count: `5`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e9c0`
- `0x1800180cc`
- `0x180019f40`
- `0x18002d8f0`
- `0x18002ea4c`

## callees

- `0x180005880`
- `0x1800065b0`
- `0x180007f10`
- `0x18000a5d0`
- `0x18000e3f0`
- `0x18000e470`
- `0x180011710`
- `0x180012544`
- `0x1800144a0`
- `0x18001467c`
- `0x18001866c`
- `0x18001d810`
- `0x180029ed4`
- `0x18002f664`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800187ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800189d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800187ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800189d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001898f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001898f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001881d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001881d`

## string_xrefs

- `0x1800187dd`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x1800188cd`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x1800188fd`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall GetMasterKeyUserEncryptionKey(
        _DWORD *a1,
        struct _GUID *a2,
        void *a3,
        unsigned int a4,
        unsigned __int8 *const pbOutput,
        unsigned int *a6)
{
  unsigned int v9; // r15d
  char v10; // r9
  void *v11; // rcx
  _DWORD *v12; // rcx
  int v13; // esi
  unsigned int v14; // edi
  __int64 v15; // r9
  const char *v16; // rdx
  DWORD v17; // ebx
  __int64 v19; // rbx
  __int64 v20; // rax
  SIZE_T v21; // rsi
  unsigned __int8 *v22; // rax
  unsigned __int8 *v23; // rdi
  unsigned int v24; // eax
  unsigned int *v25; // rsi
  DWORD v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  unsigned int v29; // eax
  bool v30; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v31; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v32; // [rsp+48h] [rbp-B8h] BYREF
  int v33; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v34; // [rsp+50h] [rbp-B0h]
  unsigned int *v35; // [rsp+58h] [rbp-A8h]
  PUCHAR pbInput; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v37[32]; // [rsp+68h] [rbp-98h] BYREF
  bool *v38; // [rsp+88h] [rbp-78h]
  __int64 v39; // [rsp+90h] [rbp-70h]
  _WORD Src[264]; // [rsp+A0h] [rbp-60h] BYREF

  v35 = a6;
  v33 = 0;
  v32 = 0;
  pbInput = 0;
  v31 = 0;
  v34 = a4;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF__guid_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 104, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, a2);
  *a6 = 0;
  v9 = 1;
  if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
  {
    v39 = 1;
    v30 = (v10 & 1) == 0;
    v38 = &v30;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_18004C260,
      (unsigned int)byte_180044E83,
      0,
      0,
      3,
      (__int64)v37);
  }
  CPSOverrideToLocalSystem(a1, 0, &v33);
  CPSQueryWellKnownAccount(v11, &v32);
  v13 = v33;
  v14 = v32;
  if ( v33 || v32 )
  {
    v29 = CPSGetSystemCredential(v12, v33, pbOutput);
    v17 = v29;
    if ( v29 )
      DebugTraceError(v29, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 4280);
    if ( a2 )
      *a2 = 0;
    if ( v17 )
      goto LABEL_45;
    if ( v13 || ((v14 - 90) & 0xFFFFFFF6) != 0 || v14 == 98 )
    {
      v25 = v35;
LABEL_42:
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF__guid_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v27, v28, a2, *v25);
      return v9;
    }
    v17 = CPSGetUserName(a1, (unsigned __int16 **)&pbInput, &v31);
    if ( !v17 )
    {
      v23 = pbInput;
      DeriveWithHMAC_SHA1(pbOutput, 0x14u, pbInput, 2 * v31, pbOutput);
      v25 = v35;
      goto LABEL_37;
    }
    v15 = 4312;
LABEL_22:
    v16 = "dwLastError";
    goto LABEL_12;
  }
  if ( a3 )
  {
    if ( !(unsigned int)GetTextualSid(a3, Src, 261) )
    {
      v15 = 4229;
      v16 = "ERROR_INVALID_PARAMETER";
      v17 = 87;
LABEL_12:
      DebugTraceError(v17, v16, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v15);
      SetLastError(v17);
      return 0;
    }
    v19 = -1;
    v20 = -1;
    do
      ++v20;
    while ( Src[v20] );
    v21 = 2LL * (unsigned int)(v20 + 1);
    v22 = (unsigned __int8 *)LocalAlloc(0, v21);
    v23 = v22;
    if ( !v22 )
    {
      v15 = 4237;
      v16 = "ERROR_NOT_ENOUGH_MEMORY";
      v17 = 8;
      goto LABEL_12;
    }
    memcpy_0(v22, Src, v21);
    do
      ++v19;
    while ( *(_WORD *)&v23[2 * v19] );
    v24 = v19 + 1;
    goto LABEL_24;
  }
  v17 = CPSGetUserName(v12, (unsigned __int16 **)&pbInput, &v31);
  if ( v17 )
  {
    v15 = 4258;
    goto LABEL_22;
  }
  v23 = pbInput;
  v24 = v31;
LABEL_24:
  v25 = v35;
  v26 = CPSGetDerivedCredential(a1, a2, v34, v23, 2 * v24, pbOutput, v35);
  v17 = v26;
  if ( v26 )
    DebugTraceError(v26, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 4342);
LABEL_37:
  if ( v23 )
    LocalFree(v23);
  if ( !v17 )
    goto LABEL_42;
LABEL_45:
  SetLastError(v17);
  return 0;
}

```

## disassembly

```asm
0x18001866c  push    rbp
0x18001866e  push    rbx
0x18001866f  push    rsi
0x180018670  push    rdi
0x180018671  push    r12
0x180018673  push    r13
0x180018675  push    r14
0x180018677  push    r15
0x180018679  lea     rbp, [rsp-1C8h]
0x180018681  sub     rsp, 2C8h
0x180018688  mov     rax, cs:__security_cookie
0x18001868f  xor     rax, rsp
0x180018692  mov     [rbp+200h+var_50], rax
0x180018699  mov     rdi, [rbp+200h+arg_28]
0x1800186a0  xor     r10d, r10d
0x1800186a3  mov     r13, [rbp+200h+arg_20]
0x1800186aa  mov     rbx, r8
0x1800186ad  mov     [rsp+300h+var_2A8], rdi
0x1800186b2  mov     r12, rdx
0x1800186b5  mov     [rsp+300h+var_2B4], r10d
0x1800186ba  mov     r14, rcx
0x1800186bd  mov     [rsp+300h+var_2B8], r10d
0x1800186c2  mov     [rsp+300h+pbInput], r10
0x1800186c7  mov     [rsp+300h+var_2BC], r10d
0x1800186cc  mov     [rsp+300h+var_2B0], r9d
0x1800186d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186d8  lea     rax, WPP_GLOBAL_Control
0x1800186df  cmp     rcx, rax
0x1800186e2  jz      short loc_180018709
0x1800186e4  test    byte ptr [rcx+1Ch], 4
0x1800186e8  jz      short loc_180018709
0x1800186ea  mov     rcx, [rcx+10h]
0x1800186ee  lea     edx, [r10+68h]
0x1800186f2  mov     r9, r12
0x1800186f5  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x1800186fc  call    WPP_SF__guid_
0x180018701  mov     r9d, [rsp+300h+var_2B0]
0x180018706  xor     r10d, r10d
0x180018709  mov     [rdi], r10d
0x18001870c  mov     r15d, 1
0x180018712  mov     eax, cs:dword_18004C260
0x180018718  cmp     eax, 5
0x18001871b  jbe     short loc_18001877B
0x18001871d  mov     rdx, 400000000000h
0x180018727  lea     rcx, dword_18004C260
0x18001872e  call    _tlgKeywordOn
0x180018733  test    al, al
0x180018735  jz      short loc_18001877B
0x180018737  mov     al, r9b
0x18001873a  mov     [rbp+200h+var_270], r15
0x18001873e  not     al
0x180018740  lea     rdx, byte_180044E83
0x180018747  and     al, r15b
0x18001874a  lea     rcx, dword_18004C260
0x180018751  mov     [rsp+300h+var_2C0], al
0x180018755  xor     r9d, r9d
0x180018758  lea     rax, [rsp+300h+var_2C0]
0x18001875d  xor     r8d, r8d
0x180018760  mov     [rbp+200h+var_278], rax
0x180018764  lea     rax, [rsp+300h+var_298]
0x180018769  mov     [rsp+300h+var_2D8], rax
0x18001876e  mov     dword ptr [rsp+300h+pbOutput], 3
0x180018776  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18001877b  lea     r8, [rsp+300h+var_2B4]; int *
0x180018780  xor     edx, edx; int *
0x180018782  mov     rcx, r14; void *
0x180018785  call    ?CPSOverrideToLocalSystem@@YAKPEAXPEAH1@Z; CPSOverrideToLocalSystem(void *,int *,int *)
0x18001878a  lea     rdx, [rsp+300h+var_2B8]; unsigned int *
0x18001878f  call    ?CPSQueryWellKnownAccount@@YAKPEAXPEAK@Z; CPSQueryWellKnownAccount(void *,ulong *)
0x180018794  mov     esi, [rsp+300h+var_2B4]
0x180018798  mov     edi, [rsp+300h+var_2B8]
0x18001879c  test    esi, esi
0x18001879e  jnz     loc_1800188E7
0x1800187a4  test    edi, edi
0x1800187a6  jnz     loc_1800188E7
0x1800187ac  test    rbx, rbx
0x1800187af  jz      loc_180018862
0x1800187b5  mov     r8d, 105h
0x1800187bb  lea     rdx, [rbp+200h+Src]
0x1800187bf  mov     rcx, rbx
0x1800187c2  call    GetTextualSid
0x1800187c7  xor     ecx, ecx; uFlags
0x1800187c9  test    eax, eax
0x1800187cb  jnz     short loc_180018800
0x1800187cd  mov     r9d, 1085h
0x1800187d3  lea     rdx, aErrorInvalidPa; "ERROR_INVALID_PARAMETER"
0x1800187da  lea     ebx, [rdi+57h]
0x1800187dd  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800187e4  mov     ecx, ebx
0x1800187e6  call    DebugTraceError
0x1800187eb  mov     ecx, ebx; dwErrCode
0x1800187ed  call    cs:__imp_SetLastError
0x1800187f4  nop     dword ptr [rax+rax+00h]
0x1800187f9  xor     eax, eax
0x1800187fb  jmp     loc_1800189EA
0x180018800  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180018804  lea     rdx, [rbp+200h+Src]
0x180018808  mov     rax, rbx
0x18001880b  inc     rax
0x18001880e  cmp     [rdx+rax*2], cx
0x180018812  jnz     short loc_18001880B
0x180018814  lea     esi, [rax+1]
0x180018817  add     rsi, rsi
0x18001881a  mov     rdx, rsi; uBytes
0x18001881d  call    cs:__imp_LocalAlloc
0x180018824  nop     dword ptr [rax+rax+00h]
0x180018829  mov     rdi, rax
0x18001882c  test    rax, rax
0x18001882f  jnz     short loc_180018843
0x180018831  mov     r9d, 108Dh
0x180018837  lea     rdx, aErrorNotEnough; "ERROR_NOT_ENOUGH_MEMORY"
0x18001883e  lea     ebx, [rax+8]
0x180018841  jmp     short loc_1800187DD
0x180018843  mov     r8, rsi; Size
0x180018846  lea     rdx, [rbp+200h+Src]; Src
0x18001884a  mov     rcx, rdi; void *
0x18001884d  call    memcpy_0
0x180018852  xor     eax, eax
0x180018854  inc     rbx
0x180018857  cmp     [rdi+rbx*2], ax
0x18001885b  jnz     short loc_180018854
0x18001885d  lea     eax, [rbx+1]
0x180018860  jmp     short loc_180018892
0x180018862  lea     r8, [rsp+300h+var_2BC]; unsigned int *
0x180018867  lea     rdx, [rsp+300h+pbInput]; unsigned __int16 **
0x18001886c  call    ?CPSGetUserName@@YAKPEAXPEAPEAGPEAK@Z; CPSGetUserName(void *,ushort * *,ulong *)
0x180018871  mov     ebx, eax
0x180018873  test    eax, eax
0x180018875  jz      short loc_180018889
0x180018877  mov     r9d, 10A2h
0x18001887d  lea     rdx, aDwlasterror; "dwLastError"
0x180018884  jmp     loc_1800187DD
0x180018889  mov     rdi, [rsp+300h+pbInput]
0x18001888e  mov     eax, [rsp+300h+var_2BC]
0x180018892  mov     rsi, [rsp+300h+var_2A8]
0x180018897  add     eax, eax
0x180018899  mov     r8d, [rsp+300h+var_2B0]; unsigned int
0x18001889e  mov     r9, rdi; unsigned __int8 *
0x1800188a1  mov     [rsp+300h+var_2D0], rsi; unsigned int *
0x1800188a6  mov     rdx, r12; struct _GUID *
0x1800188a9  mov     [rsp+300h+var_2D8], r13; unsigned __int8 *
0x1800188ae  mov     rcx, r14; void *
0x1800188b1  mov     dword ptr [rsp+300h+pbOutput], eax; ULONG
0x1800188b5  call    ?CPSGetDerivedCredential@@YAKPEAXPEAU_GUID@@KPEAEKQEAEPEAK@Z; CPSGetDerivedCredential(void *,_GUID *,ulong,uchar *,ulong,uchar * const,ulong *)
0x1800188ba  xor     r14d, r14d
0x1800188bd  mov     ebx, eax
0x1800188bf  test    eax, eax
0x1800188c1  jz      loc_180018987
0x1800188c7  mov     r9d, 10F6h
0x1800188cd  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800188d4  lea     rdx, aDwlasterror; "dwLastError"
0x1800188db  mov     ecx, eax
0x1800188dd  call    DebugTraceError
0x1800188e2  jmp     loc_180018987
0x1800188e7  mov     r8, r13; unsigned __int8 *
0x1800188ea  mov     edx, esi; int
0x1800188ec  call    ?CPSGetSystemCredential@@YAKPEAXHQEAE@Z; CPSGetSystemCredential(void *,int,uchar * const)
0x1800188f1  mov     ebx, eax
0x1800188f3  test    eax, eax
0x1800188f5  jz      short loc_180018912
0x1800188f7  mov     r9d, 10B8h
0x1800188fd  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180018904  lea     rdx, aDwlasterror; "dwLastError"
0x18001890b  mov     ecx, eax
0x18001890d  call    DebugTraceError
0x180018912  test    r12, r12
0x180018915  jz      short loc_18001891F
0x180018917  xorps   xmm0, xmm0
0x18001891a  movups  xmmword ptr [r12], xmm0
0x18001891f  test    ebx, ebx
0x180018921  jnz     loc_1800189D3
0x180018927  test    esi, esi
0x180018929  jnz     short loc_1800189A1
0x18001892b  lea     eax, [rdi-5Ah]
0x18001892e  test    eax, 0FFFFFFF6h
0x180018933  jnz     short loc_1800189A1
0x180018935  cmp     edi, 62h ; 'b'
0x180018938  jz      short loc_1800189A1
0x18001893a  lea     r8, [rsp+300h+var_2BC]; unsigned int *
0x18001893f  mov     rcx, r14; void *
0x180018942  lea     rdx, [rsp+300h+pbInput]; unsigned __int16 **
0x180018947  call    ?CPSGetUserName@@YAKPEAXPEAPEAGPEAK@Z; CPSGetUserName(void *,ushort * *,ulong *)
0x18001894c  xor     r14d, r14d
0x18001894f  mov     ebx, eax
0x180018951  test    eax, eax
0x180018953  jz      short loc_180018960
0x180018955  mov     r9d, 10D8h
0x18001895b  jmp     loc_18001887D
0x180018960  mov     r9d, [rsp+300h+var_2BC]
0x180018965  mov     edx, 14h; Size
0x18001896a  mov     rdi, [rsp+300h+pbInput]
0x18001896f  add     r9d, r9d; cbInput
0x180018972  mov     r8, rdi; pbInput
0x180018975  mov     [rsp+300h+pbOutput], r13; pbOutput
0x18001897a  mov     rcx, r13; Src
0x18001897d  call    DeriveWithHMAC_SHA1
0x180018982  mov     rsi, [rsp+300h+var_2A8]
0x180018987  test    rdi, rdi
0x18001898a  jz      short loc_18001899B
0x18001898c  mov     rcx, rdi; hMem
0x18001898f  call    cs:__imp_LocalFree
0x180018996  nop     dword ptr [rax+rax+00h]
0x18001899b  test    ebx, ebx
0x18001899d  jnz     short loc_1800189D6
0x18001899f  jmp     short loc_1800189A6
0x1800189a1  mov     rsi, [rsp+300h+var_2A8]
0x1800189a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189ad  lea     rax, WPP_GLOBAL_Control
0x1800189b4  cmp     rcx, rax
0x1800189b7  jz      short loc_1800189E7
0x1800189b9  test    byte ptr [rcx+1Ch], 4
0x1800189bd  jz      short loc_1800189E7
0x1800189bf  mov     eax, [rsi]
0x1800189c1  mov     r9, r12
0x1800189c4  mov     rcx, [rcx+10h]
0x1800189c8  mov     dword ptr [rsp+300h+pbOutput], eax
0x1800189cc  call    WPP_SF__guid_D
0x1800189d1  jmp     short loc_1800189E7
0x1800189d3  xor     r14d, r14d
0x1800189d6  mov     ecx, ebx; dwErrCode
0x1800189d8  call    cs:__imp_SetLastError
0x1800189df  nop     dword ptr [rax+rax+00h]
0x1800189e4  mov     r15d, r14d
0x1800189e7  mov     eax, r15d
0x1800189ea  mov     rcx, [rbp+200h+var_50]
0x1800189f1  xor     rcx, rsp; StackCookie
0x1800189f4  call    __security_check_cookie
0x1800189f9  add     rsp, 2C8h
0x180018a00  pop     r15
0x180018a02  pop     r14
0x180018a04  pop     r13
0x180018a06  pop     r12
0x180018a08  pop     rdi
0x180018a09  pop     rsi
0x180018a0a  pop     rbx
0x180018a0b  pop     rbp
0x180018a0c  retn
```
