# CDefaultChainEngineMgr::GetTokenId(void *,_CRYPTOAPI_BLOB *)

- ea: `0x180068f74`
- end: `0x18006937d`
- name: `?GetTokenId@CDefaultChainEngineMgr@@AEAAHPEAXPEAU_CRYPTOAPI_BLOB@@@Z`
- size: `1033`
- prototype: `int(CDefaultChainEngineMgr *__hidden this, void *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180068cf0`

## callees

- `0x180028d60`
- `0x18002a7d8`
- `0x180046e10`
- `0x18005d484`
- `0x180068c94`
- `0x180068f74`
- `0x1800bec20`
- `0x180115040`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006915a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006915a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180069344`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180069372`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180069344`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180069372`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180068fd7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180069007`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800690ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800691cb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180069270`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180068fd7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180069007`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800690ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800691cb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180069270`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006911a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006931d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006911a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006931d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800690bf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180069281`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800690bf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180069281`

## pseudocode

```c
__int64 __fastcall CDefaultChainEngineMgr::GetTokenId(
        CDefaultChainEngineMgr *this,
        void *a2,
        struct _CRYPTOAPI_BLOB *a3)
{
  int v3; // r15d
  DWORD *v6; // rbx
  DWORD *v7; // rdi
  unsigned int v8; // r12d
  __int64 v9; // rdx
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  void *v14; // rsp
  void *v15; // rsp
  DWORD LengthSid; // esi
  SIZE_T v17; // rcx
  BYTE *v18; // rax
  BYTE *v19; // r14
  BYTE *v20; // r14
  BYTE *v21; // rax
  DWORD LastError; // esi
  __int64 v24; // rdx
  unsigned __int64 v25; // rsi
  unsigned __int64 v26; // rcx
  __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  void *v29; // rsp
  void *v30; // rsp
  DWORD *v31; // rax
  DWORD *v32; // rax
  _BYTE v33[32]; // [rsp+0h] [rbp-30h] BYREF
  int v34; // [rsp+30h] [rbp+0h] BYREF
  DWORD TokenInformationLength; // [rsp+34h] [rbp+4h] BYREF
  DWORD v36; // [rsp+38h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+3Ch] [rbp+Ch] BYREF
  int TokenInformation; // [rsp+40h] [rbp+10h] BYREF
  DWORD nDestinationSidLength; // [rsp+48h] [rbp+18h]

  v3 = 0;
  a3->cbData = 0;
  a3->pbData = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  v36 = 0;
  ReturnLength = 4;
  v6 = 0;
  v7 = 0;
  if ( !GetTokenInformation(a2, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
    goto LABEL_24;
  if ( ReturnLength != 4 )
    goto LABEL_24;
  v8 = 1;
  GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength);
  if ( !TokenInformationLength )
    goto LABEL_24;
  v10 = TokenInformationLength;
  if ( TokenInformationLength > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_55;
  v11 = TokenInformationLength + g_ulAdditionalProbeSize + 8;
  if ( v11 < TokenInformationLength || !(unsigned int)VerifyStackAvailable(v11, v9) )
    goto LABEL_55;
  v12 = v10 + 23;
  if ( v10 + 23 <= v10 + 8 )
    v12 = 0xFFFFFFFFFFFFFF0LL;
  v13 = v12 & 0xFFFFFFFFFFFFFFF0uLL;
  v14 = alloca(v13);
  v15 = alloca(v13);
  v6 = (DWORD *)&v34;
  if ( v33 == (_BYTE *)-48LL || (v34 = 1801679955, (v6 = &v36) == 0) )
  {
LABEL_55:
    if ( v10 + 8 >= v10 )
    {
      v31 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      v6 = v31;
      if ( v31 )
      {
        *v31 = 1885431112;
        v6 = v31 + 2;
      }
    }
  }
  if ( !v6 )
    goto LABEL_50;
  if ( !GetTokenInformation(a2, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
    goto LABEL_24;
  nDestinationSidLength = GetLengthSid(*(PSID *)v6);
  if ( !nDestinationSidLength )
    goto LABEL_24;
  LOBYTE(v34) = 0;
  if ( (unsigned int)I_CryptIsAppContainerToken(a2) )
  {
    GetTokenInformation(a2, TokenAppContainerSid, 0, 0, &v36);
    if ( !v36 )
      goto LABEL_24;
    v25 = v36;
    if ( v36 > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_56;
    v26 = v36 + g_ulAdditionalProbeSize + 8;
    if ( v26 < v36 || !(unsigned int)VerifyStackAvailable(v26, v24) )
      goto LABEL_56;
    v27 = v25 + 23;
    if ( v25 + 23 <= v25 + 8 )
      v27 = 0xFFFFFFFFFFFFFF0LL;
    v28 = v27 & 0xFFFFFFFFFFFFFFF0uLL;
    v29 = alloca(v28);
    v30 = alloca(v28);
    v7 = (DWORD *)&v34;
    if ( v33 == (_BYTE *)-48LL || (v34 = 1801679955, (v7 = &v36) == 0) )
    {
LABEL_56:
      if ( v25 + 8 >= v25 )
      {
        v32 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        v7 = v32;
        if ( v32 )
        {
          *v32 = 1885431112;
          v7 = v32 + 2;
        }
      }
    }
    if ( !v7 )
      goto LABEL_50;
    if ( !GetTokenInformation(a2, TokenAppContainerSid, v7, v36, &v36) )
      goto LABEL_24;
    LengthSid = GetLengthSid(*(PSID *)v7);
    if ( !LengthSid )
      goto LABEL_24;
    v3 = 1;
    if ( (unsigned int)I_CryptHasAppContainerUserCertCapability(a2) )
      LOBYTE(v34) = 1;
  }
  else
  {
    LengthSid = 0;
  }
  v17 = v3 + LengthSid + nDestinationSidLength + 4;
  a3->cbData = v17;
  v18 = (BYTE *)PkiZeroAlloc(v17);
  a3->pbData = v18;
  if ( !v18 )
  {
LABEL_50:
    SetLastError(0x8007000E);
    goto LABEL_24;
  }
  v19 = v18 + 4;
  *(_DWORD *)v18 = TokenInformation;
  if ( !CopySid(nDestinationSidLength, v18 + 4, *(PSID *)v6) )
    goto LABEL_24;
  v20 = &v19[nDestinationSidLength];
  if ( !LengthSid )
  {
    v21 = v20;
    goto LABEL_20;
  }
  if ( !CopySid(LengthSid, v20, *(PSID *)v7) )
  {
LABEL_24:
    LastError = GetLastError();
    PkiDefaultCryptFree(a3->pbData);
    a3->cbData = 0;
    a3->pbData = 0;
    v8 = 0;
    if ( !v6 )
      goto LABEL_25;
    goto LABEL_22;
  }
  v21 = &v20[LengthSid];
LABEL_20:
  LastError = 0;
  if ( v3 )
    *v21 = v34;
LABEL_22:
  if ( *(v6 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
LABEL_25:
  if ( v7 && *(v7 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( !v8 )
    SetLastError(LastError);
  return v8;
}

```

## disassembly

```asm
0x180068f74  push    rbp
0x180068f76  push    rbx
0x180068f77  push    rsi
0x180068f78  push    rdi
0x180068f79  push    r12
0x180068f7b  push    r13
0x180068f7d  push    r14
0x180068f7f  push    r15
0x180068f81  sub     rsp, 68h
0x180068f85  lea     rbp, [rsp+30h]
0x180068f8a  mov     rax, cs:__security_cookie
0x180068f91  xor     rax, rbp
0x180068f94  mov     [rbp+70h+var_48], rax
0x180068f98  xor     r15d, r15d
0x180068f9b  lea     rax, [rbp+70h+var_64]
0x180068f9f  mov     r14, rdx
0x180068fa2  mov     [r8], r15d
0x180068fa5  mov     r13, r8
0x180068fa8  mov     [r8+8], r15
0x180068fac  lea     r8, [rbp+70h+TokenInformation]; TokenInformation
0x180068fb0  mov     [rbp+70h+TokenInformation], r15d
0x180068fb4  lea     esi, [r15+4]
0x180068fb8  mov     [rbp+70h+TokenInformationLength], r15d
0x180068fbc  mov     r9d, esi; TokenInformationLength
0x180068fbf  mov     [rbp+70h+var_68], r15d
0x180068fc3  lea     edx, [rsi+8]; TokenInformationClass
0x180068fc6  mov     [rbp+70h+var_64], esi
0x180068fc9  mov     rcx, r14; TokenHandle
0x180068fcc  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x180068fd1  mov     ebx, r15d
0x180068fd4  mov     edi, r15d
0x180068fd7  call    cs:__imp_GetTokenInformation
0x180068fdd  test    eax, eax
0x180068fdf  jz      loc_18006915A
0x180068fe5  cmp     [rbp+70h+var_64], esi
0x180068fe8  jnz     loc_18006915A
0x180068fee  lea     rax, [rbp+70h+TokenInformationLength]
0x180068ff2  xor     r9d, r9d; TokenInformationLength
0x180068ff5  lea     r12d, [r15+1]
0x180068ff9  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x180068ffe  mov     edx, r12d; TokenInformationClass
0x180069001  xor     r8d, r8d; TokenInformation
0x180069004  mov     rcx, r14; TokenHandle
0x180069007  call    cs:__imp_GetTokenInformation
0x18006900d  mov     eax, [rbp+70h+TokenInformationLength]
0x180069010  test    eax, eax
0x180069012  jz      loc_18006915A
0x180069018  cmp     rax, cs:g_ulMaxStackAllocSize
0x18006901f  mov     esi, eax
0x180069021  ja      loc_1800692AD
0x180069027  mov     rcx, cs:g_ulAdditionalProbeSize
0x18006902e  add     rcx, 8
0x180069032  add     rcx, rax
0x180069035  cmp     rcx, rax
0x180069038  jb      loc_1800692AD
0x18006903e  call    VerifyStackAvailable
0x180069043  test    eax, eax
0x180069045  jz      loc_1800692AD
0x18006904b  lea     rax, [rsi+8]
0x18006904f  lea     rcx, [rax+0Fh]
0x180069053  cmp     rcx, rax
0x180069056  ja      short loc_180069062
0x180069058  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180069062  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180069066  mov     rax, rcx
0x180069069  call    _alloca_probe
0x18006906e  sub     rsp, rcx
0x180069071  lea     rbx, [rsp+0A0h+var_70]
0x180069076  test    rbx, rbx
0x180069079  jz      loc_1800692AD
0x18006907f  mov     dword ptr [rbx], 6B637453h
0x180069085  add     rbx, 8
0x180069089  jz      loc_1800692AD
0x18006908f  test    rbx, rbx
0x180069092  jz      loc_18006933F
0x180069098  mov     r9d, [rbp+70h+TokenInformationLength]; TokenInformationLength
0x18006909c  lea     rax, [rbp+70h+TokenInformationLength]
0x1800690a0  mov     r8, rbx; TokenInformation
0x1800690a3  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x1800690a8  mov     edx, r12d; TokenInformationClass
0x1800690ab  mov     rcx, r14; TokenHandle
0x1800690ae  call    cs:__imp_GetTokenInformation
0x1800690b4  test    eax, eax
0x1800690b6  jz      loc_18006915A
0x1800690bc  mov     rcx, [rbx]; pSid
0x1800690bf  call    cs:__imp_GetLengthSid
0x1800690c5  mov     [rbp+70h+nDestinationSidLength], eax
0x1800690c8  test    eax, eax
0x1800690ca  jz      loc_18006915A
0x1800690d0  mov     rcx, r14
0x1800690d3  mov     byte ptr [rbp+70h+var_70], r15b
0x1800690d7  call    I_CryptIsAppContainerToken
0x1800690dc  test    eax, eax
0x1800690de  jnz     loc_1800691B5
0x1800690e4  xor     esi, esi
0x1800690e6  mov     ecx, [rbp+70h+nDestinationSidLength]
0x1800690e9  lea     eax, [r15+rsi]
0x1800690ed  add     ecx, 4
0x1800690f0  add     ecx, eax; uBytes
0x1800690f2  mov     [r13+0], ecx
0x1800690f6  call    PkiZeroAlloc
0x1800690fb  mov     [r13+8], rax
0x1800690ff  test    rax, rax
0x180069102  jz      loc_18006933F
0x180069108  mov     ecx, [rbp+70h+TokenInformation]
0x18006910b  lea     r14, [rax+4]
0x18006910f  mov     [rax], ecx
0x180069111  mov     rdx, r14; pDestinationSid
0x180069114  mov     r8, [rbx]; pSourceSid
0x180069117  mov     ecx, [rbp+70h+nDestinationSidLength]; nDestinationSidLength
0x18006911a  call    cs:__imp_CopySid
0x180069120  test    eax, eax
0x180069122  jz      short loc_18006915A
0x180069124  mov     eax, [rbp+70h+nDestinationSidLength]
0x180069127  add     r14, rax
0x18006912a  test    esi, esi
0x18006912c  jnz     loc_180069315
0x180069132  mov     rax, r14
0x180069135  xor     esi, esi
0x180069137  test    r15d, r15d
0x18006913a  jnz     loc_180069335
0x180069140  lea     rcx, [rbx-8]
0x180069144  cmp     dword ptr [rcx], 70616548h
0x18006914a  jnz     short loc_180069183
0x18006914c  mov     rax, cs:g_pfnFree
0x180069153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069158  jmp     short loc_180069183
0x18006915a  call    cs:__imp_GetLastError
0x180069160  mov     rcx, [r13+8]; hMem
0x180069164  mov     esi, eax
0x180069166  call    PkiDefaultCryptFree
0x18006916b  mov     dword ptr [r13+0], 0
0x180069173  mov     qword ptr [r13+8], 0
0x18006917b  xor     r12d, r12d
0x18006917e  test    rbx, rbx
0x180069181  jnz     short loc_180069140
0x180069183  test    rdi, rdi
0x180069186  jnz     loc_18006934F
0x18006918c  test    r12d, r12d
0x18006918f  jz      loc_180069370
0x180069195  mov     eax, r12d
0x180069198  mov     rcx, [rbp+70h+var_48]
0x18006919c  xor     rcx, rbp; StackCookie
0x18006919f  call    __security_check_cookie
0x1800691a4  lea     rsp, [rbp+38h]
0x1800691a8  pop     r15
0x1800691aa  pop     r14
0x1800691ac  pop     r13
0x1800691ae  pop     r12
0x1800691b0  pop     rdi
0x1800691b1  pop     rsi
0x1800691b2  pop     rbx
0x1800691b3  pop     rbp
0x1800691b4  retn
0x1800691b5  xor     r9d, r9d; TokenInformationLength
0x1800691b8  lea     rax, [rbp+70h+var_68]
0x1800691bc  xor     r8d, r8d; TokenInformation
0x1800691bf  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x1800691c4  mov     rcx, r14; TokenHandle
0x1800691c7  lea     edx, [r9+1Fh]; TokenInformationClass
0x1800691cb  call    cs:__imp_GetTokenInformation
0x1800691d1  mov     eax, [rbp+70h+var_68]
0x1800691d4  test    eax, eax
0x1800691d6  jz      short loc_18006915A
0x1800691d8  cmp     rax, cs:g_ulMaxStackAllocSize
0x1800691df  mov     esi, eax
0x1800691e1  ja      loc_1800692E1
0x1800691e7  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800691ee  add     rcx, 8
0x1800691f2  add     rcx, rax
0x1800691f5  cmp     rcx, rax
0x1800691f8  jb      loc_1800692E1
0x1800691fe  call    VerifyStackAvailable
0x180069203  test    eax, eax
0x180069205  jz      loc_1800692E1
0x18006920b  lea     rax, [rsi+8]
0x18006920f  lea     rcx, [rax+0Fh]
0x180069213  cmp     rcx, rax
0x180069216  ja      short loc_180069222
0x180069218  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180069222  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180069226  mov     rax, rcx
0x180069229  call    _alloca_probe
0x18006922e  sub     rsp, rcx
0x180069231  lea     rdi, [rsp+0A0h+var_70]
0x180069236  test    rdi, rdi
0x180069239  jz      loc_1800692E1
0x18006923f  mov     dword ptr [rdi], 6B637453h
0x180069245  add     rdi, 8
0x180069249  jz      loc_1800692E1
0x18006924f  test    rdi, rdi
0x180069252  jz      loc_18006933F
0x180069258  mov     r9d, [rbp+70h+var_68]; TokenInformationLength
0x18006925c  lea     rax, [rbp+70h+var_68]
0x180069260  mov     r8, rdi; TokenInformation
0x180069263  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x180069268  mov     edx, 1Fh; TokenInformationClass
0x18006926d  mov     rcx, r14; TokenHandle
0x180069270  call    cs:__imp_GetTokenInformation
0x180069276  test    eax, eax
0x180069278  jz      loc_18006915A
0x18006927e  mov     rcx, [rdi]; pSid
0x180069281  call    cs:__imp_GetLengthSid
0x180069287  mov     esi, eax
0x180069289  test    eax, eax
0x18006928b  jz      loc_18006915A
0x180069291  mov     rcx, r14
0x180069294  mov     r15d, r12d
0x180069297  call    I_CryptHasAppContainerUserCertCapability
0x18006929c  test    eax, eax
0x18006929e  jz      loc_1800690E6
0x1800692a4  mov     byte ptr [rbp+70h+var_70], r12b
0x1800692a8  jmp     loc_1800690E6
0x1800692ad  lea     rcx, [rsi+8]
0x1800692b1  cmp     rcx, rsi
0x1800692b4  jb      loc_18006908F
0x1800692ba  mov     rax, cs:g_pfnAllocate
0x1800692c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800692c6  mov     rbx, rax
0x1800692c9  test    rax, rax
0x1800692cc  jz      loc_18006908F
0x1800692d2  mov     dword ptr [rax], 70616548h
0x1800692d8  add     rbx, 8
0x1800692dc  jmp     loc_18006908F
0x1800692e1  lea     rcx, [rsi+8]
0x1800692e5  cmp     rcx, rsi
0x1800692e8  jb      loc_18006924F
0x1800692ee  mov     rax, cs:g_pfnAllocate
0x1800692f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800692fa  mov     rdi, rax
0x1800692fd  test    rax, rax
0x180069300  jz      loc_18006924F
0x180069306  mov     dword ptr [rax], 70616548h
0x18006930c  add     rdi, 8
0x180069310  jmp     loc_18006924F
0x180069315  mov     r8, [rdi]; pSourceSid
0x180069318  mov     rdx, r14; pDestinationSid
0x18006931b  mov     ecx, esi; nDestinationSidLength
0x18006931d  call    cs:__imp_CopySid
0x180069323  test    eax, eax
0x180069325  jz      loc_18006915A
0x18006932b  mov     eax, esi
0x18006932d  add     rax, r14
0x180069330  jmp     loc_180069135
0x180069335  mov     cl, byte ptr [rbp+70h+var_70]
0x180069338  mov     [rax], cl
0x18006933a  jmp     loc_180069140
0x18006933f  mov     ecx, 8007000Eh; dwErrCode
0x180069344  call    cs:__imp_SetLastError
0x18006934a  jmp     loc_18006915A
0x18006934f  lea     rcx, [rdi-8]
0x180069353  cmp     dword ptr [rcx], 70616548h
0x180069359  jnz     loc_18006918C
0x18006935f  mov     rax, cs:g_pfnFree
0x180069366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006936b  jmp     loc_18006918C
0x180069370  mov     ecx, esi; dwErrCode
0x180069372  call    cs:__imp_SetLastError
0x180069378  jmp     loc_180069195
```
