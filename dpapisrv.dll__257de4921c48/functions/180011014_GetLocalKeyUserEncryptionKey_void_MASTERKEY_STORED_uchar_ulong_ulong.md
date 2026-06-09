# GetLocalKeyUserEncryptionKey(void *,MASTERKEY_STORED *,uchar *,ulong *,ulong *)

- ea: `0x180011014`
- end: `0x180011315`
- name: `?GetLocalKeyUserEncryptionKey@@YAHPEAXPEAUMASTERKEY_STORED@@PEAEPEAK3@Z`
- size: `769`
- prototype: `__int64 __fastcall(_DWORD *, struct MASTERKEY_STORED *, unsigned __int8 *, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180019f40`
- `0x18002a794`
- `0x18002ac04`

## callees

- `0x1800029d0`
- `0x1800065b0`
- `0x180007f10`
- `0x180011014`
- `0x1800144a0`
- `0x18001d810`
- `0x18001eb8c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001125a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001125a`
- `bcrypt!BCryptFinishHash` at `0x180011218`
- `bcrypt!BCryptFinishHash` at `0x180011218`
- `bcrypt!BCryptDestroyHash` at `0x18001124a`
- `bcrypt!BCryptDestroyHash` at `0x18001124a`
- `bcrypt!BCryptHashData` at `0x180011196`
- `bcrypt!BCryptHashData` at `0x18001127b`
- `bcrypt!BCryptHashData` at `0x1800112cc`
- `bcrypt!BCryptHashData` at `0x180011196`
- `bcrypt!BCryptHashData` at `0x18001127b`
- `bcrypt!BCryptHashData` at `0x1800112cc`
- `bcrypt!BCryptCreateHash` at `0x180011120`
- `bcrypt!BCryptCreateHash` at `0x180011120`

## string_xrefs

- `0x180011154`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x1800111ac`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x1800111b5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall GetLocalKeyUserEncryptionKey(
        _DWORD *a1,
        struct MASTERKEY_STORED *a2,
        unsigned __int8 *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  int v9; // edi
  unsigned int v10; // ebx
  _DWORD *v11; // rax
  __int64 v12; // r14
  void *BCryptProviderHandle; // rcx
  unsigned int v14; // eax
  NTSTATUS v15; // eax
  NTSTATUS v16; // eax
  __int64 v17; // r9
  unsigned int v18; // eax
  unsigned int v19; // esi
  UCHAR *v20; // rax
  unsigned int v22; // eax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v24; // [rsp+48h] [rbp-38h] BYREF
  PUCHAR pbInput; // [rsp+50h] [rbp-30h] BYREF
  UCHAR v26[24]; // [rsp+58h] [rbp-28h] BYREF

  phHash = 0;
  pbInput = 0;
  v24 = 0;
  if ( a1 )
    v9 = a1[14];
  else
    v9 = 32777;
  *a5 = 0;
  if ( !a4 )
    return 0;
  v10 = 1;
  if ( *((_DWORD *)a2 + 28) )
  {
    v11 = (_DWORD *)*((_QWORD *)a2 + 15);
    if ( v11 )
    {
      v9 = 32777;
      if ( *v11 > 1u )
        v9 = v11[6];
    }
  }
  if ( (unsigned int)CPSGetUserName(a1, (unsigned __int16 **)&pbInput, &v24) )
    return 0;
  v12 = 20;
  if ( v9 == 32782 )
  {
    BCryptProviderHandle = (void *)GetBCryptProviderHandle(0x800Eu);
    if ( !BCryptProviderHandle )
      goto LABEL_34;
    v14 = 64;
    if ( *a4 < 0x40 )
      goto LABEL_34;
  }
  else
  {
    BCryptProviderHandle = (void *)GetBCryptProviderHandle(0x8004u);
    if ( !BCryptProviderHandle || *a4 < 0x14 )
      goto LABEL_34;
    v14 = 20;
  }
  *a4 = v14;
  v15 = BCryptCreateHash(BCryptProviderHandle, &phHash, 0, 0, 0, 0, 0);
  if ( v15 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"ntStatus",
        v15,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
        176);
    goto LABEL_34;
  }
  v16 = BCryptHashData(phHash, pbInput, 2 * v24, 0);
  if ( v16 < 0 )
  {
    v17 = 4536;
LABEL_33:
    DebugTraceError(
      (unsigned int)v16,
      "ntStatus",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
      v17);
LABEL_34:
    v10 = 0;
    goto LABEL_35;
  }
  if ( *(_DWORD *)a2 > 1u && (*((_BYTE *)a2 + 96) & 1) != 0 )
  {
    v18 = CPSGetSystemCredential(a1, 1, v26);
    v19 = v18;
    if ( v18 )
    {
      DebugTraceError(v18, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 4557);
    }
    else
    {
      v16 = BCryptHashData(phHash, v26, 0x14u, 0);
      if ( v16 < 0 )
      {
        v17 = 4565;
        goto LABEL_33;
      }
      v22 = CPSGetSystemCredential(a1, 0, v26);
      v19 = v22;
      if ( v22 )
        DebugTraceError(v22, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 4578);
      v16 = BCryptHashData(phHash, v26, 0x14u, 0);
      if ( v16 < 0 )
      {
        v17 = 4584;
        goto LABEL_33;
      }
    }
    v20 = v26;
    do
    {
      *v20++ = 0;
      --v12;
    }
    while ( v12 );
    if ( v19 )
      v10 = 0;
  }
  v16 = BCryptFinishHash(phHash, a3, *a4, 0);
  if ( v16 < 0 )
  {
    v17 = 4599;
    goto LABEL_33;
  }
LABEL_35:
  if ( phHash )
    BCryptDestroyHash(phHash);
  LocalFree(pbInput);
  return v10;
}

```

## disassembly

```asm
0x180011014  mov     [rsp-38h+arg_8], rbx
0x180011019  push    rbp
0x18001101a  push    rsi
0x18001101b  push    rdi
0x18001101c  push    r12
0x18001101e  push    r13
0x180011020  push    r14
0x180011022  push    r15
0x180011024  mov     rbp, rsp
0x180011027  sub     rsp, 80h
0x18001102e  mov     rax, cs:__security_cookie
0x180011035  xor     rax, rsp
0x180011038  mov     [rbp+var_10], rax
0x18001103c  mov     rax, [rbp+arg_20]
0x180011040  xor     r14d, r14d
0x180011043  mov     r15, rcx
0x180011046  mov     [rbp+phHash], r14
0x18001104a  mov     [rbp+pbInput], r14
0x18001104e  mov     r12, r9
0x180011051  mov     [rbp+var_38], r14d
0x180011055  mov     r13, r8
0x180011058  mov     rsi, rdx
0x18001105b  mov     ecx, 8009h
0x180011060  test    r15, r15
0x180011063  jz      short loc_18001106B
0x180011065  mov     edi, [r15+38h]
0x180011069  jmp     short loc_18001106D
0x18001106b  mov     edi, ecx
0x18001106d  mov     [rax], r14d
0x180011070  test    r12, r12
0x180011073  jz      loc_1800112EB
0x180011079  mov     ebx, 1
0x18001107e  cmp     [rdx+70h], r14d
0x180011082  jz      short loc_180011096
0x180011084  mov     rax, [rdx+78h]
0x180011088  test    rax, rax
0x18001108b  jz      short loc_180011096
0x18001108d  mov     edi, ecx
0x18001108f  cmp     [rax], ebx
0x180011091  jbe     short loc_180011096
0x180011093  mov     edi, [rax+18h]
0x180011096  lea     r8, [rbp+var_38]; unsigned int *
0x18001109a  mov     rcx, r15; void *
0x18001109d  lea     rdx, [rbp+pbInput]; unsigned __int16 **
0x1800110a1  call    ?CPSGetUserName@@YAKPEAXPEAPEAGPEAK@Z; CPSGetUserName(void *,ushort * *,ulong *)
0x1800110a6  test    eax, eax
0x1800110a8  jnz     loc_1800112EB
0x1800110ae  mov     ecx, 800Eh; unsigned int
0x1800110b3  lea     r14d, [rax+14h]
0x1800110b7  xor     r8d, r8d
0x1800110ba  xor     edx, edx
0x1800110bc  cmp     edi, ecx
0x1800110be  jnz     short loc_1800110E0
0x1800110c0  call    GetBCryptProviderHandle
0x1800110c5  mov     rcx, rax
0x1800110c8  test    rax, rax
0x1800110cb  jz      loc_18001123F
0x1800110d1  lea     eax, [r14+2Ch]
0x1800110d5  cmp     [r12], eax
0x1800110d9  jnb     short loc_180011103
0x1800110db  jmp     loc_18001123F
0x1800110e0  mov     ecx, 8004h; unsigned int
0x1800110e5  call    GetBCryptProviderHandle
0x1800110ea  mov     rcx, rax; hAlgorithm
0x1800110ed  test    rax, rax
0x1800110f0  jz      loc_18001123F
0x1800110f6  cmp     [r12], r14d
0x1800110fa  jb      loc_18001123F
0x180011100  mov     eax, r14d
0x180011103  mov     [r12], eax
0x180011107  lea     rdx, [rbp+phHash]; phHash
0x18001110b  xor     eax, eax
0x18001110d  xor     r9d, r9d; cbHashObject
0x180011110  mov     [rsp+80h+dwFlags], eax; dwFlags
0x180011114  xor     r8d, r8d; pbHashObject
0x180011117  mov     [rsp+80h+cbSecret], eax; cbSecret
0x18001111b  mov     [rsp+80h+pbSecret], rax; pbSecret
0x180011120  call    cs:__imp_BCryptCreateHash
0x180011127  nop     dword ptr [rax+rax+00h]
0x18001112c  test    eax, eax
0x18001112e  jns     short loc_180011184
0x180011130  mov     rcx, cs:WPP_GLOBAL_Control
0x180011137  lea     rdx, WPP_GLOBAL_Control
0x18001113e  cmp     rcx, rdx
0x180011141  jz      loc_18001123F
0x180011147  test    [rcx+1Ch], bl
0x18001114a  jz      loc_18001123F
0x180011150  mov     rcx, [rcx+10h]
0x180011154  lea     rdi, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001115b  mov     [rsp+80h+dwFlags], 11B0h
0x180011163  lea     r9, aNtstatus; "ntStatus"
0x18001116a  mov     qword ptr [rsp+80h+cbSecret], rdi
0x18001116f  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180011176  mov     dword ptr [rsp+80h+pbSecret], eax
0x18001117a  call    WPP_SF_sDsd
0x18001117f  jmp     loc_18001123F
0x180011184  mov     r8d, [rbp+var_38]
0x180011188  xor     r9d, r9d; dwFlags
0x18001118b  mov     rdx, [rbp+pbInput]; pbInput
0x18001118f  add     r8d, r8d; cbInput
0x180011192  mov     rcx, [rbp+phHash]; hHash
0x180011196  call    cs:__imp_BCryptHashData
0x18001119d  nop     dword ptr [rax+rax+00h]
0x1800111a2  test    eax, eax
0x1800111a4  jns     short loc_1800111B5
0x1800111a6  mov     r9d, 11B8h
0x1800111ac  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800111b3  jmp     short loc_180011231
0x1800111b5  lea     rdi, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800111bc  cmp     [rsi], ebx
0x1800111be  jbe     short loc_18001120A
0x1800111c0  test    [rsi+60h], bl
0x1800111c3  jz      short loc_18001120A
0x1800111c5  lea     r8, [rbp+var_28]; unsigned __int8 *
0x1800111c9  mov     edx, ebx; int
0x1800111cb  mov     rcx, r15; void *
0x1800111ce  call    ?CPSGetSystemCredential@@YAKPEAXHQEAE@Z; CPSGetSystemCredential(void *,int,uchar * const)
0x1800111d3  mov     esi, eax
0x1800111d5  test    eax, eax
0x1800111d7  jz      loc_18001126D
0x1800111dd  mov     r9d, 11CDh
0x1800111e3  lea     rdx, aDwlasterror; "dwLastError"
0x1800111ea  mov     r8, rdi
0x1800111ed  mov     ecx, eax
0x1800111ef  call    DebugTraceError
0x1800111f4  lea     rax, [rbp+var_28]
0x1800111f8  mov     byte ptr [rax], 0
0x1800111fb  add     rax, rbx
0x1800111fe  sub     r14, rbx
0x180011201  jnz     short loc_1800111F8
0x180011203  xor     eax, eax
0x180011205  test    esi, esi
0x180011207  cmovnz  ebx, eax
0x18001120a  mov     r8d, [r12]; cbOutput
0x18001120e  xor     r9d, r9d; dwFlags
0x180011211  mov     rcx, [rbp+phHash]; hHash
0x180011215  mov     rdx, r13; pbOutput
0x180011218  call    cs:__imp_BCryptFinishHash
0x18001121f  nop     dword ptr [rax+rax+00h]
0x180011224  test    eax, eax
0x180011226  jns     short loc_180011241
0x180011228  mov     r9d, 11F7h
0x18001122e  mov     r8, rdi
0x180011231  lea     rdx, aNtstatus; "ntStatus"
0x180011238  mov     ecx, eax
0x18001123a  call    DebugTraceError
0x18001123f  xor     ebx, ebx
0x180011241  mov     rcx, [rbp+phHash]; hHash
0x180011245  test    rcx, rcx
0x180011248  jz      short loc_180011256
0x18001124a  call    cs:__imp_BCryptDestroyHash
0x180011251  nop     dword ptr [rax+rax+00h]
0x180011256  mov     rcx, [rbp+pbInput]; hMem
0x18001125a  call    cs:__imp_LocalFree
0x180011261  nop     dword ptr [rax+rax+00h]
0x180011266  mov     eax, ebx
0x180011268  jmp     loc_1800112ED
0x18001126d  mov     rcx, [rbp+phHash]; hHash
0x180011271  lea     rdx, [rbp+var_28]; pbInput
0x180011275  xor     r9d, r9d; dwFlags
0x180011278  mov     r8d, r14d; cbInput
0x18001127b  call    cs:__imp_BCryptHashData
0x180011282  nop     dword ptr [rax+rax+00h]
0x180011287  test    eax, eax
0x180011289  jns     short loc_180011293
0x18001128b  mov     r9d, 11D5h
0x180011291  jmp     short loc_18001122E
0x180011293  lea     r8, [rbp+var_28]; unsigned __int8 *
0x180011297  xor     edx, edx; int
0x180011299  mov     rcx, r15; void *
0x18001129c  call    ?CPSGetSystemCredential@@YAKPEAXHQEAE@Z; CPSGetSystemCredential(void *,int,uchar * const)
0x1800112a1  mov     esi, eax
0x1800112a3  test    eax, eax
0x1800112a5  jz      short loc_1800112BE
0x1800112a7  mov     r9d, 11E2h
0x1800112ad  lea     rdx, aDwlasterror; "dwLastError"
0x1800112b4  mov     r8, rdi
0x1800112b7  mov     ecx, eax
0x1800112b9  call    DebugTraceError
0x1800112be  mov     rcx, [rbp+phHash]; hHash
0x1800112c2  lea     rdx, [rbp+var_28]; pbInput
0x1800112c6  xor     r9d, r9d; dwFlags
0x1800112c9  mov     r8d, r14d; cbInput
0x1800112cc  call    cs:__imp_BCryptHashData
0x1800112d3  nop     dword ptr [rax+rax+00h]
0x1800112d8  test    eax, eax
0x1800112da  jns     loc_1800111F4
0x1800112e0  mov     r9d, 11E8h
0x1800112e6  jmp     loc_18001122E
0x1800112eb  xor     eax, eax
0x1800112ed  mov     rcx, [rbp+var_10]
0x1800112f1  xor     rcx, rsp; StackCookie
0x1800112f4  call    __security_check_cookie
0x1800112f9  mov     rbx, [rsp+80h+arg_8]
0x180011301  add     rsp, 80h
0x180011308  pop     r15
0x18001130a  pop     r14
0x18001130c  pop     r13
0x18001130e  pop     r12
0x180011310  pop     rdi
0x180011311  pop     rsi
0x180011312  pop     rbp
0x180011313  retn
```
