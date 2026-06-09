# FMyDeriveBCryptKey(void *,void *,uint,uint,ulong,uchar *,ulong,uchar * *,ulong *,void * *)

- ea: `0x18000c8c0`
- end: `0x18000ce81`
- name: `?FMyDeriveBCryptKey@@YAKPEAX0IIKPEAEKPEAPEAEPEAKPEAPEAX@Z`
- size: `1473`
- prototype: `__int64 __fastcall(BCRYPT_HANDLE hObject, BCRYPT_HASH_HANDLE hHash, unsigned int, __int64, unsigned int, unsigned __int8 *, size_t Size, unsigned __int8 **, unsigned int *, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014c80`
- `0x180016370`

## callees

- `0x180007f10`
- `0x18000c8c0`
- `0x180013f2c`
- `0x18001d810`
- `0x18001e1b4`
- `0x18001eb8c`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdf8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdf8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cd83`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cd83`
- `bcrypt!BCryptGenRandom` at `0x18000cdca`
- `bcrypt!BCryptGenRandom` at `0x18000cdca`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000ca4b`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000ca4b`
- `bcrypt!BCryptDestroyKey` at `0x18000ce70`
- `bcrypt!BCryptDestroyKey` at `0x18000ce70`
- `bcrypt!BCryptGetProperty` at `0x18000c986`
- `bcrypt!BCryptGetProperty` at `0x18000cb0b`
- `bcrypt!BCryptGetProperty` at `0x18000c986`
- `bcrypt!BCryptGetProperty` at `0x18000cb0b`
- `bcrypt!BCryptDeriveKeyCapi` at `0x18000c9e1`
- `bcrypt!BCryptDeriveKeyCapi` at `0x18000c9e1`

## string_xrefs

- `0x18000cc27`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\capiprim.cpp`
- `0x18000cc92`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\capiprim.cpp`
- `0x18000cceb`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\capiprim.cpp`
- `0x18000cd2a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\capiprim.cpp`
- `0x18000cd9c`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\capiprim.cpp`
- `0x18000cde2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\capiprim.cpp`
- `0x18000ce31`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\capiprim.cpp`

## pseudocode

```c
__int64 __fastcall FMyDeriveBCryptKey(
        BCRYPT_HANDLE hObject,
        BCRYPT_HASH_HANDLE hHash,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        unsigned __int8 *a6,
        size_t Size,
        unsigned __int8 **a8,
        unsigned int *a9,
        void **a10)
{
  unsigned int v13; // edi
  int v14; // edx
  unsigned int v15; // ebx
  ULONG v16; // ebx
  NTSTATUS v17; // eax
  UCHAR *v18; // rsi
  int v19; // r12d
  unsigned __int8 **v20; // r15
  NTSTATUS v21; // edx
  __int64 v23; // rcx
  ULONG v24; // r15d
  UCHAR *v25; // rax
  NTSTATUS v26; // eax
  UCHAR *v27; // rdx
  _DWORD *v28; // rax
  char v29; // [rsp+30h] [rbp-A9h]
  ULONG pcbResult; // [rsp+40h] [rbp-99h] BYREF
  unsigned int v31; // [rsp+44h] [rbp-95h]
  UCHAR v32[8]; // [rsp+48h] [rbp-91h] BYREF
  unsigned __int8 **v33; // [rsp+50h] [rbp-89h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-81h] BYREF
  unsigned int *v35; // [rsp+60h] [rbp-79h]
  void *Src; // [rsp+68h] [rbp-71h]
  UCHAR pbOutput[8]; // [rsp+70h] [rbp-69h] BYREF
  int v38; // [rsp+78h] [rbp-61h]
  UCHAR pbDerivedKey[80]; // [rsp+80h] [rbp-59h] BYREF

  Src = a6;
  v33 = a8;
  v13 = 13;
  v31 = a3;
  v35 = a9;
  memset_0(pbDerivedKey, 0, 0x4Bu);
  phKey = 0;
  v15 = HIWORD(a5);
  if ( HIWORD(a5) )
  {
    if ( (a5 & 0x70000) != 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        return v13;
      v29 = 63;
      goto LABEL_51;
    }
  }
  else
  {
    v15 = -1;
  }
  *(_QWORD *)pbOutput = 0;
  v38 = 0;
  *(_DWORD *)v32 = 0;
  pcbResult = 0;
  if ( BCryptGetProperty(hObject, L"KeyLengths", pbOutput, 0xCu, &pcbResult, 0) < 0 || pcbResult < 0xC )
  {
    if ( BCryptGetProperty(hObject, L"HashDigestLength", v32, 4u, &pcbResult, 0) < 0 || pcbResult < 4 )
      goto LABEL_27;
    if ( v15 == -1 )
    {
      v15 = 8 * *(_DWORD *)v32;
      goto LABEL_8;
    }
    if ( 8 * *(_DWORD *)v32 != v15 )
      goto LABEL_27;
  }
  else
  {
    if ( v15 != -1 )
    {
      if ( *(_DWORD *)pbOutput <= v15 && *(_DWORD *)&pbOutput[4] >= v15 )
        goto LABEL_8;
LABEL_27:
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_42dd8ab1efa135ad49ce01560d99f2ca_Traceguids, a3);
      goto LABEL_22;
    }
    v15 = *(_DWORD *)&pbOutput[4];
    if ( a3 == 26625 && *(_DWORD *)&pbOutput[4] > 0x80u )
      v15 = 128;
  }
LABEL_8:
  v16 = v15 >> 3;
  if ( v16 > 0x4B )
  {
    DebugTraceError(2148073504LL, "NTE_FAIL", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\capiprim.cpp", 339);
    goto LABEL_22;
  }
  v17 = BCryptDeriveKeyCapi(hHash, hObject, pbDerivedKey, v16, 0);
  if ( v17 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"ntStatus",
        v17,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\capiprim.cpp",
        90);
    goto LABEL_22;
  }
  v18 = 0;
  v19 = 0;
  if ( (a5 & 4) == 0 )
    goto LABEL_69;
  v14 = (int)Src;
  if ( Src && (_DWORD)Size )
  {
    v24 = v16 + Size;
    if ( v16 + (unsigned int)Size > 0x4B )
    {
      v13 = 87;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (_DWORD)Src,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          87,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\capiprim.cpp",
          101);
      goto LABEL_22;
    }
    if ( v31 != 26625 && v31 != 26114 )
      goto LABEL_69;
    memcpy_0(&pbDerivedKey[v16], Src, (unsigned int)Size);
LABEL_68:
    v16 = v24;
LABEL_69:
    v20 = v33;
    goto LABEL_14;
  }
  v20 = v33;
  if ( !v33 || !v35 )
    goto LABEL_14;
  if ( v31 != 26625 && v31 != 26114 )
  {
    *v35 = 0;
    *v20 = 0;
LABEL_14:
    v21 = BCryptGenerateSymmetricKey(hObject, &phKey, 0, 0, pbDerivedKey, v16, 0);
    if ( v21 >= 0 )
    {
      if ( v18 )
      {
        v28 = v35;
        *v20 = v18;
        *v28 = v19;
      }
      v13 = 0;
      *a10 = phKey;
      phKey = 0;
      goto LABEL_22;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v21,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"ntStatus",
        v21,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\capiprim.cpp",
        169);
    if ( !v18 )
      goto LABEL_22;
    goto LABEL_66;
  }
  v24 = v16 + 11;
  if ( v16 + 11 <= 0x4B )
  {
    v19 = 11;
    v25 = (UCHAR *)LocalAlloc(0, 0xBu);
    v18 = v25;
    if ( !v25 )
    {
      v13 = 14;
      DebugTraceError(14, "dwRet", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\capiprim.cpp", 385);
      goto LABEL_22;
    }
    v26 = BCryptGenRandom(0, v25, 0xBu, 2u);
    if ( v26 < 0 )
    {
      DebugTraceError(
        (unsigned int)v26,
        "ntStatus",
        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\capiprim.cpp",
        395);
LABEL_66:
      LocalFree(v18);
      goto LABEL_22;
    }
    v27 = &pbDerivedKey[v16];
    *(_QWORD *)v27 = *(_QWORD *)v18;
    *(_DWORD *)(v27 + 7) = *(_DWORD *)(v18 + 7);
    goto LABEL_68;
  }
  v23 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v29 = 119;
LABEL_51:
    WPP_SF_sDsd(
      *(_QWORD *)(v23 + 16),
      v14,
      (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
      (unsigned int)"NTE_FAIL",
      32,
      (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\capiprim.cpp",
      v29);
  }
LABEL_22:
  if ( phKey )
    BCryptDestroyKey(phKey);
  return v13;
}

```

## disassembly

```asm
0x18000c8c0  mov     [rsp-8+arg_18], rbx
0x18000c8c5  push    rbp
0x18000c8c6  push    rsi
0x18000c8c7  push    rdi
0x18000c8c8  push    r12
0x18000c8ca  push    r13
0x18000c8cc  push    r14
0x18000c8ce  push    r15
0x18000c8d0  lea     rbp, [rsp-7]
0x18000c8d5  sub     rsp, 0E0h
0x18000c8dc  mov     rax, cs:__security_cookie
0x18000c8e3  xor     rax, rsp
0x18000c8e6  mov     [rbp+37h+var_40], rax
0x18000c8ea  mov     rax, [rbp+37h+arg_28]
0x18000c8ee  mov     r12d, r8d
0x18000c8f1  mov     r13, [rbp+37h+arg_48]
0x18000c8f8  mov     rsi, rdx
0x18000c8fb  mov     [rbp+37h+Src], rax
0x18000c8ff  mov     r14, rcx
0x18000c902  mov     rax, [rbp+37h+arg_38]
0x18000c906  lea     rcx, [rbp+37h+pbDerivedKey]; void *
0x18000c90a  mov     [rsp+110h+var_C0], rax
0x18000c90f  xor     edx, edx; Val
0x18000c911  mov     rax, [rbp+37h+arg_40]
0x18000c918  mov     edi, 0Dh
0x18000c91d  mov     [rsp+110h+var_CC], r8d
0x18000c922  mov     r8d, 4Bh ; 'K'; Size
0x18000c928  mov     [rbp+37h+var_B0], rax
0x18000c92c  call    memset_0
0x18000c931  mov     r15d, [rbp+37h+arg_20]
0x18000c935  xor     ecx, ecx
0x18000c937  mov     ebx, r15d
0x18000c93a  mov     [rsp+110h+phKey], rcx
0x18000c93f  shr     ebx, 10h
0x18000c942  test    ebx, ebx
0x18000c944  jz      loc_18000CADA
0x18000c94a  test    bl, 7
0x18000c94d  jnz     loc_18000CB5D
0x18000c953  xor     eax, eax
0x18000c955  mov     [rsp+110h+dwFlags], ecx; dwFlags
0x18000c959  mov     qword ptr [rbp+37h+pbOutput], rax
0x18000c95d  lea     r8, [rbp+37h+pbOutput]; pbOutput
0x18000c961  mov     [rbp+37h+var_98], eax
0x18000c964  lea     rdx, aKeylengths; "KeyLengths"
0x18000c96b  lea     rax, [rsp+110h+var_D0]
0x18000c970  mov     dword ptr [rsp+110h+var_C8], ecx
0x18000c974  mov     [rsp+110h+var_D0], ecx
0x18000c978  mov     r9d, 0Ch; cbOutput
0x18000c97e  mov     rcx, r14; hObject
0x18000c981  mov     [rsp+110h+pcbResult], rax; pcbResult
0x18000c986  call    cs:__imp_BCryptGetProperty
0x18000c98d  nop     dword ptr [rax+rax+00h]
0x18000c992  test    eax, eax
0x18000c994  js      loc_18000CAE4
0x18000c99a  cmp     [rsp+110h+var_D0], 0Ch
0x18000c99f  jb      loc_18000CAE4
0x18000c9a5  cmp     ebx, 0FFFFFFFFh
0x18000c9a8  jz      loc_18000CBC1
0x18000c9ae  cmp     dword ptr [rbp+37h+pbOutput], ebx
0x18000c9b1  ja      loc_18000CB1F
0x18000c9b7  cmp     dword ptr [rbp+37h+pbOutput+4], ebx
0x18000c9ba  jb      loc_18000CB1F
0x18000c9c0  shr     ebx, 3
0x18000c9c3  cmp     ebx, 4Bh ; 'K'
0x18000c9c6  ja      loc_18000CD24
0x18000c9cc  mov     r9d, ebx; cbDerivedKey
0x18000c9cf  mov     dword ptr [rsp+110h+pcbResult], 0; dwFlags
0x18000c9d7  lea     r8, [rbp+37h+pbDerivedKey]; pbDerivedKey
0x18000c9db  mov     rdx, r14; hTargetAlg
0x18000c9de  mov     rcx, rsi; hHash
0x18000c9e1  call    cs:__imp_BCryptDeriveKeyCapi
0x18000c9e8  nop     dword ptr [rax+rax+00h]
0x18000c9ed  mov     ecx, eax
0x18000c9ef  test    eax, eax
0x18000c9f1  js      loc_18000CC06
0x18000c9f7  xor     esi, esi
0x18000c9f9  xor     r12d, r12d
0x18000c9fc  test    r15b, 4
0x18000ca00  jz      loc_18000CE23
0x18000ca06  mov     rdx, [rbp+37h+Src]; Src
0x18000ca0a  test    rdx, rdx
0x18000ca0d  jz      short loc_18000CA1A
0x18000ca0f  mov     eax, dword ptr [rbp+37h+Size]
0x18000ca12  test    eax, eax
0x18000ca14  jnz     loc_18000CCAF
0x18000ca1a  mov     r15, [rsp+110h+var_C0]
0x18000ca1f  test    r15, r15
0x18000ca22  jnz     loc_18000CB8B
0x18000ca28  mov     dword ptr [rsp+110h+var_E0], 0; dwFlags
0x18000ca30  lea     rax, [rbp+37h+pbDerivedKey]
0x18000ca34  mov     [rsp+110h+dwFlags], ebx; cbSecret
0x18000ca38  lea     rdx, [rsp+110h+phKey]; phKey
0x18000ca3d  xor     r9d, r9d; cbKeyObject
0x18000ca40  mov     [rsp+110h+pcbResult], rax; pbSecret
0x18000ca45  xor     r8d, r8d; pbKeyObject
0x18000ca48  mov     rcx, r14; hAlgorithm
0x18000ca4b  call    cs:__imp_BCryptGenerateSymmetricKey
0x18000ca52  nop     dword ptr [rax+rax+00h]
0x18000ca57  mov     edx, eax
0x18000ca59  test    eax, eax
0x18000ca5b  js      short loc_18000CA7C
0x18000ca5d  test    rsi, rsi
0x18000ca60  jnz     loc_18000CE61
0x18000ca66  mov     rax, [rsp+110h+phKey]
0x18000ca6b  xor     edi, edi
0x18000ca6d  mov     [r13+0], rax
0x18000ca71  mov     [rsp+110h+phKey], 0
0x18000ca7a  jmp     short loc_18000CAA2
0x18000ca7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca83  lea     rax, WPP_GLOBAL_Control
0x18000ca8a  cmp     rcx, rax
0x18000ca8d  jz      short loc_18000CA99
0x18000ca8f  test    byte ptr [rcx+1Ch], 1
0x18000ca93  jnz     loc_18000CE2D
0x18000ca99  test    rsi, rsi
0x18000ca9c  jnz     loc_18000CDF5
0x18000caa2  mov     rcx, [rsp+110h+phKey]; hKey
0x18000caa7  test    rcx, rcx
0x18000caaa  jnz     loc_18000CE70
0x18000cab0  mov     eax, edi
0x18000cab2  mov     rcx, [rbp+37h+var_40]
0x18000cab6  xor     rcx, rsp; StackCookie
0x18000cab9  call    __security_check_cookie
0x18000cabe  mov     rbx, [rsp+110h+arg_18]
0x18000cac6  add     rsp, 0E0h
0x18000cacd  pop     r15
0x18000cacf  pop     r14
0x18000cad1  pop     r13
0x18000cad3  pop     r12
0x18000cad5  pop     rdi
0x18000cad6  pop     rsi
0x18000cad7  pop     rbp
0x18000cad8  retn
0x18000cada  mov     ebx, 0FFFFFFFFh
0x18000cadf  jmp     loc_18000C953
0x18000cae4  lea     rax, [rsp+110h+var_D0]
0x18000cae9  mov     [rsp+110h+dwFlags], 0; dwFlags
0x18000caf1  mov     r9d, 4; cbOutput
0x18000caf7  mov     [rsp+110h+pcbResult], rax; pcbResult
0x18000cafc  lea     r8, [rsp+110h+var_C8]; pbOutput
0x18000cb01  mov     rcx, r14; hObject
0x18000cb04  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000cb0b  call    cs:__imp_BCryptGetProperty
0x18000cb12  nop     dword ptr [rax+rax+00h]
0x18000cb17  test    eax, eax
0x18000cb19  jns     loc_18000CBE0
0x18000cb1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb26  lea     rax, WPP_GLOBAL_Control
0x18000cb2d  cmp     rcx, rax
0x18000cb30  jz      loc_18000CAA2
0x18000cb36  test    byte ptr [rcx+1Ch], 1
0x18000cb3a  jz      loc_18000CAA2
0x18000cb40  mov     rcx, [rcx+10h]
0x18000cb44  lea     r8, WPP_42dd8ab1efa135ad49ce01560d99f2ca_Traceguids
0x18000cb4b  mov     edx, 0Bh
0x18000cb50  mov     r9d, r12d
0x18000cb53  call    WPP_SF_d
0x18000cb58  jmp     loc_18000CAA2
0x18000cb5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb64  lea     rax, WPP_GLOBAL_Control
0x18000cb6b  cmp     rcx, rax
0x18000cb6e  jz      loc_18000CAB0
0x18000cb74  test    byte ptr [rcx+1Ch], 1
0x18000cb78  jz      loc_18000CAB0
0x18000cb7e  mov     dword ptr [rsp+110h+var_E0], 13Fh
0x18000cb86  jmp     loc_18000CC92
0x18000cb8b  mov     rax, [rbp+37h+var_B0]
0x18000cb8f  test    rax, rax
0x18000cb92  jz      loc_18000CA28
0x18000cb98  mov     r9d, [rsp+110h+var_CC]
0x18000cb9d  cmp     r9d, 6801h
0x18000cba4  jz      loc_18000CC5B
0x18000cbaa  cmp     r9d, 6602h
0x18000cbb1  jz      loc_18000CC5B
0x18000cbb7  mov     [rax], esi
0x18000cbb9  mov     [r15], rsi
0x18000cbbc  jmp     loc_18000CA28
0x18000cbc1  mov     ebx, dword ptr [rbp+37h+pbOutput+4]
0x18000cbc4  cmp     r12d, 6801h
0x18000cbcb  jnz     loc_18000C9C0
0x18000cbd1  mov     eax, 80h
0x18000cbd6  cmp     ebx, eax
0x18000cbd8  cmova   ebx, eax
0x18000cbdb  jmp     loc_18000C9C0
0x18000cbe0  cmp     [rsp+110h+var_D0], 4
0x18000cbe5  jb      loc_18000CB1F
0x18000cbeb  mov     eax, dword ptr [rsp+110h+var_C8]
0x18000cbef  lea     eax, ds:0[rax*8]
0x18000cbf6  cmp     ebx, 0FFFFFFFFh
0x18000cbf9  jnz     loc_18000CD17
0x18000cbff  mov     ebx, eax
0x18000cc01  jmp     loc_18000C9C0
0x18000cc06  mov     rdx, cs:WPP_GLOBAL_Control
0x18000cc0d  lea     rax, WPP_GLOBAL_Control
0x18000cc14  cmp     rdx, rax
0x18000cc17  jz      loc_18000CAA2
0x18000cc1d  test    byte ptr [rdx+1Ch], 1
0x18000cc21  jz      loc_18000CAA2
0x18000cc27  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000cc2e  mov     dword ptr [rsp+110h+var_E0], 15Ah
0x18000cc36  mov     qword ptr [rsp+110h+dwFlags], rax
0x18000cc3b  lea     r9, aNtstatus; "ntStatus"
0x18000cc42  mov     dword ptr [rsp+110h+pcbResult], ecx
0x18000cc46  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000cc4d  mov     rcx, [rdx+10h]
0x18000cc51  call    WPP_SF_sDsd
0x18000cc56  jmp     loc_18000CAA2
0x18000cc5b  lea     r15d, [rbx+0Bh]
0x18000cc5f  cmp     r15d, 4Bh ; 'K'
0x18000cc63  jbe     loc_18000CD78
0x18000cc69  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc70  lea     rax, WPP_GLOBAL_Control
0x18000cc77  cmp     rcx, rax
0x18000cc7a  jz      loc_18000CAA2
0x18000cc80  test    byte ptr [rcx+1Ch], 1
0x18000cc84  jz      loc_18000CAA2
0x18000cc8a  mov     dword ptr [rsp+110h+var_E0], 177h
0x18000cc92  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000cc99  mov     qword ptr [rsp+110h+dwFlags], rax
0x18000cc9e  lea     r9, aNteFail; "NTE_FAIL"
0x18000cca5  mov     dword ptr [rsp+110h+pcbResult], 80090020h
0x18000ccad  jmp     short loc_18000CD02
0x18000ccaf  lea     r15d, [rbx+rax]
0x18000ccb3  cmp     r15d, 4Bh ; 'K'
0x18000ccb7  jbe     loc_18000CD47
0x18000ccbd  mov     edi, 57h ; 'W'
0x18000ccc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccc9  lea     rax, WPP_GLOBAL_Control
0x18000ccd0  cmp     rcx, rax
0x18000ccd3  jz      loc_18000CAA2
0x18000ccd9  test    byte ptr [rcx+1Ch], 1
0x18000ccdd  jz      loc_18000CAA2
0x18000cce3  mov     dword ptr [rsp+110h+var_E0], 165h
0x18000cceb  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000ccf2  mov     qword ptr [rsp+110h+dwFlags], rax
0x18000ccf7  lea     r9, aDwret; "dwRet"
0x18000ccfe  mov     dword ptr [rsp+110h+pcbResult], edi
0x18000cd02  mov     rcx, [rcx+10h]
0x18000cd06  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000cd0d  call    WPP_SF_sDsd
0x18000cd12  jmp     loc_18000CAA2
0x18000cd17  cmp     eax, ebx
0x18000cd19  jnz     loc_18000CB1F
0x18000cd1f  jmp     loc_18000C9C0
0x18000cd24  mov     r9d, 153h
0x18000cd2a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000cd31  lea     rdx, aNteFail; "NTE_FAIL"
0x18000cd38  mov     ecx, 80090020h
0x18000cd3d  call    DebugTraceError
0x18000cd42  jmp     loc_18000CAA2
0x18000cd47  mov     r9d, [rsp+110h+var_CC]
0x18000cd4c  cmp     r9d, 6801h
0x18000cd53  jz      short loc_18000CD62
0x18000cd55  cmp     r9d, 6602h
0x18000cd5c  jnz     loc_18000CE23
0x18000cd62  mov     r8, rax; Size
0x18000cd65  lea     rcx, [rbp+37h+pbDerivedKey]
0x18000cd69  mov     eax, ebx
0x18000cd6b  add     rcx, rax; void *
0x18000cd6e  call    memcpy_0
0x18000cd73  jmp     loc_18000CE20
0x18000cd78  mov     r12d, 0Bh
0x18000cd7e  xor     ecx, ecx; uFlags
0x18000cd80  mov     edx, r12d; uBytes
0x18000cd83  call    cs:__imp_LocalAlloc
0x18000cd8a  nop     dword ptr [rax+rax+00h]
0x18000cd8f  mov     rsi, rax
0x18000cd92  test    rax, rax
0x18000cd95  jnz     short loc_18000CDBC
0x18000cd97  mov     edi, 0Eh
0x18000cd9c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000cda3  mov     ecx, edi
0x18000cda5  lea     rdx, aDwret; "dwRet"
0x18000cdac  mov     r9d, 181h
0x18000cdb2  call    DebugTraceError
0x18000cdb7  jmp     loc_18000CAA2
0x18000cdbc  mov     r9d, 2; dwFlags
0x18000cdc2  mov     r8d, r12d; cbBuffer
0x18000cdc5  mov     rdx, rsi; pbBuffer
0x18000cdc8  xor     ecx, ecx; hAlgorithm
0x18000cdca  call    cs:__imp_BCryptGenRandom
0x18000cdd1  nop     dword ptr [rax+rax+00h]
0x18000cdd6  mov     ecx, eax
0x18000cdd8  test    eax, eax
0x18000cdda  jns     short loc_18000CE09
0x18000cddc  mov     r9d, 18Bh
0x18000cde2  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000cde9  lea     rdx, aNtstatus; "ntStatus"
0x18000cdf0  call    DebugTraceError
0x18000cdf5  mov     rcx, rsi; hMem
0x18000cdf8  call    cs:__imp_LocalFree
0x18000cdff  nop     dword ptr [rax+rax+00h]
0x18000ce04  jmp     loc_18000CAA2
0x18000ce09  movsd   xmm0, qword ptr [rsi]
0x18000ce0d  lea     rdx, [rbp+37h+pbDerivedKey]
0x18000ce11  mov     eax, ebx
0x18000ce13  add     rdx, rax
0x18000ce16  movsd   qword ptr [rdx], xmm0
0x18000ce1a  mov     eax, [rsi+7]
0x18000ce1d  mov     [rdx+7], eax
  ... truncated ...
```
