# SecurityContextFunctionLegacy(_EAPTLS_CONTROL_BLOCK *)

- ea: `0x180030728`
- end: `0x180030bc9`
- name: `?SecurityContextFunctionLegacy@@YAJPEAU_EAPTLS_CONTROL_BLOCK@@@Z`
- size: `1185`
- prototype: `__int64 __fastcall(struct _EAPTLS_CONTROL_BLOCK *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180030710`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180030728`
- `0x180035680`
- `0x18003623c`
- `0x180036248`
- `0x180051ea4`
- `0x18005ab6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800309e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800309e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800309c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800309c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003099f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003099f`
- `SspiCli!QueryContextAttributesW` at `0x180030b3e`
- `SspiCli!QueryContextAttributesW` at `0x180030b3e`
- `SspiCli!FreeContextBuffer` at `0x180030aad`
- `SspiCli!FreeContextBuffer` at `0x180030aad`
- `SspiCli!InitializeSecurityContextW` at `0x1800308db`
- `SspiCli!InitializeSecurityContextW` at `0x1800308db`
- `SspiCli!AcceptSecurityContext` at `0x180030865`
- `SspiCli!AcceptSecurityContext` at `0x180030865`

## pseudocode

```c
__int64 __fastcall SecurityContextFunctionLegacy(struct _EAPTLS_CONTROL_BLOCK *a1)
{
  int v2; // r15d
  int v3; // r12d
  bool v4; // zf
  unsigned int v5; // r9d
  struct _SecHandle *v6; // rcx
  struct _SecBufferDesc *p_pInput; // r8
  struct _SecHandle *v8; // rdx
  unsigned int v9; // eax
  signed int EapErrorFromWinError; // edi
  struct _SecHandle *v11; // rdx
  unsigned int v12; // eax
  struct _EAPTLS_CONTROL_BLOCK *v13; // rcx
  bool v14; // zf
  SIZE_T v15; // rsi
  HLOCAL v16; // rax
  DWORD LastError; // eax
  unsigned int v18; // edx
  unsigned int v19; // eax
  int v20; // edx
  int v21; // r8d
  const char *v22; // r9
  unsigned int pfContextAttr; // [rsp+60h] [rbp-79h] BYREF
  unsigned int v25; // [rsp+64h] [rbp-75h]
  SIZE_T uBytes[2]; // [rsp+68h] [rbp-71h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+78h] [rbp-61h] BYREF
  struct _SecBufferDesc pInput; // [rsp+80h] [rbp-59h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+90h] [rbp-49h] BYREF
  __int128 v30; // [rsp+A0h] [rbp-39h] BYREF
  size_t Size[2]; // [rsp+B0h] [rbp-29h]
  _OWORD pBuffer[2]; // [rsp+C0h] [rbp-19h] BYREF

  pInput = 0;
  pfContextAttr = 0;
  v30 = 0;
  ptsExpiry.QuadPart = 0;
  *(_OWORD *)Size = 0;
  pOutput = 0;
  *(_OWORD *)uBytes = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
  v2 = 0;
  v3 = *((_DWORD *)a1 + 1) & 1;
  if ( v3 )
    v4 = *(_DWORD *)a1 == 1;
  else
    v4 = *(_DWORD *)a1 == 0;
  v5 = *((_DWORD *)a1 + 166);
  v25 = v5;
  LOBYTE(v2) = v4;
  while ( 1 )
  {
    v6 = (struct _SecHandle *)((char *)a1 + 616);
    *((_QWORD *)&v30 + 1) = *((_QWORD *)a1 + 84);
    p_pInput = &pInput;
    LODWORD(v30) = *((_DWORD *)a1 + 170);
    pInput.pBuffers = (PSecBuffer)&v30;
    pOutput.pBuffers = (PSecBuffer)uBytes;
    DWORD1(v30) = 2;
    Size[1] = 0;
    Size[0] = 0;
    pInput.cBuffers = 2;
    pInput.ulVersion = 0;
    uBytes[1] = 0;
    uBytes[0] = 0x200000000LL;
    pOutput.cBuffers = 1;
    pOutput.ulVersion = 0;
    if ( v3 )
    {
      v8 = 0;
      if ( !v2 )
        v8 = (struct _SecHandle *)((char *)a1 + 648);
      v9 = AcceptSecurityContext(
             v6,
             v8,
             &pInput,
             v5,
             0,
             (PCtxtHandle)((char *)a1 + 648),
             &pOutput,
             &pfContextAttr,
             &ptsExpiry);
      EapErrorFromWinError = v9;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v9);
LABEL_22:
      v14 = EapErrorFromWinError == 0;
      if ( EapErrorFromWinError < 0 )
        goto LABEL_24;
      goto LABEL_23;
    }
    v11 = (struct _SecHandle *)((char *)a1 + 648);
    if ( v2 )
    {
      p_pInput = 0;
      v11 = 0;
    }
    v12 = InitializeSecurityContextW(
            v6,
            v11,
            0,
            v5,
            0,
            0,
            p_pInput,
            0,
            (PCtxtHandle)((char *)a1 + 648),
            &pOutput,
            &pfContextAttr,
            &ptsExpiry);
    EapErrorFromWinError = v12;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 253, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v12);
      v13 = WPP_GLOBAL_Control;
    }
    if ( EapErrorFromWinError == 590684 )
    {
      if ( v13 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)v13 + 2), 254, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      EapErrorFromWinError = 826;
    }
    else if ( EapErrorFromWinError < 0 )
    {
      EapErrorFromWinError = GetEapErrorFromWinError(v2 == 0, EapErrorFromWinError);
      goto LABEL_22;
    }
LABEL_23:
    *((_DWORD *)a1 + 1) &= ~0x40u;
    v14 = EapErrorFromWinError == 0;
LABEL_24:
    if ( !v14 && EapErrorFromWinError != 590610 && (EapErrorFromWinError >= 0 || (pfContextAttr & 0x4000) == 0) )
      goto LABEL_38;
    v15 = LODWORD(uBytes[0]);
    if ( !LODWORD(uBytes[0]) || !uBytes[1] )
      goto LABEL_38;
    if ( LODWORD(uBytes[0]) > *((_DWORD *)a1 + 177) )
    {
      LocalFree(*((HLOCAL *)a1 + 87));
      *((_QWORD *)a1 + 87) = 0;
      *((_QWORD *)a1 + 88) = 0;
    }
    v16 = (HLOCAL)*((_QWORD *)a1 + 87);
    if ( v16 )
      goto LABEL_37;
    v16 = LocalAlloc(0x40u, v15);
    *((_QWORD *)a1 + 87) = v16;
    if ( v16 )
    {
      *((_DWORD *)a1 + 177) = v15;
LABEL_37:
      memcpy_0(v16, (const void *)uBytes[1], v15);
      *((_DWORD *)a1 + 176) = v15;
      *((_QWORD *)a1 + 89) = 0;
LABEL_38:
      if ( HIDWORD(Size[0]) == 5
        && (v18 = *((_DWORD *)a1 + 170), v18 >= LODWORD(Size[0]))
        && *((_DWORD *)a1 + 171) >= LODWORD(Size[0]) )
      {
        memmove_0(*((void **)a1 + 84), (const void *)(*((_QWORD *)a1 + 84) + v18 - LODWORD(Size[0])), LODWORD(Size[0]));
        *((_DWORD *)a1 + 170) = Size[0];
      }
      else
      {
        *((_DWORD *)a1 + 170) = 0;
      }
      goto LABEL_43;
    }
    *((_QWORD *)a1 + 88) = 0;
    LastError = GetLastError();
    EapErrorFromWinError = LastError;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 255, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, LastError);
LABEL_43:
    if ( !EapErrorFromWinError
      || EapErrorFromWinError == 590610
      || EapErrorFromWinError < 0 && (pfContextAttr & 0x4000) != 0 )
    {
      if ( uBytes[1] )
      {
        v19 = FreeContextBuffer((PVOID)uBytes[1]);
        if ( v19 )
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 256, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v19);
        }
      }
    }
    if ( LODWORD(uBytes[0]) )
      break;
    if ( EapErrorFromWinError != 590610 )
      goto LABEL_56;
    v5 = v25;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 257, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      v5 = v25;
    }
  }
  if ( EapErrorFromWinError == 590610 )
    return (unsigned int)EapErrorFromWinError;
LABEL_56:
  memset(pBuffer, 0, 28);
  if ( !QueryContextAttributesW((PCtxtHandle)((char *)a1 + 648), 0x5Au, pBuffer)
    && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v22 = "PEAP";
    if ( (*((_DWORD *)a1 + 1) & 0x4000) == 0 )
      v22 = "EAPTLS";
    WPP_SF_sddddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v20,
      v21,
      (_DWORD)v22,
      pBuffer[0],
      SBYTE4(pBuffer[0]),
      SBYTE8(pBuffer[0]),
      SBYTE12(pBuffer[0]),
      pBuffer[1],
      SBYTE4(pBuffer[1]),
      SBYTE8(pBuffer[1]));
  }
  return (unsigned int)EapErrorFromWinError;
}

```

## disassembly

```asm
0x180030728  push    rbp
0x18003072a  push    rbx
0x18003072b  push    rsi
0x18003072c  push    rdi
0x18003072d  push    r12
0x18003072f  push    r13
0x180030731  push    r14
0x180030733  push    r15
0x180030735  lea     rbp, [rsp-1Fh]
0x18003073a  sub     rsp, 0F8h
0x180030741  mov     rax, cs:__security_cookie
0x180030748  xor     rax, rsp
0x18003074b  mov     [rbp+57h+var_50], rax
0x18003074f  xorps   xmm0, xmm0
0x180030752  xorps   xmm1, xmm1
0x180030755  xor     r14d, r14d
0x180030758  mov     rbx, rcx
0x18003075b  movups  xmmword ptr [rbp+57h+pInput.ulVersion], xmm0
0x18003075f  mov     [rbp+57h+var_D0], r14d
0x180030763  movups  [rbp+57h+var_90], xmm1
0x180030767  mov     qword ptr [rbp+57h+var_B8], r14
0x18003076b  movups  xmmword ptr [rbp+57h+Size], xmm0
0x18003076f  movups  xmmword ptr [rbp+57h+var_A0.ulVersion], xmm1
0x180030773  movups  xmmword ptr [rbp+57h+uBytes], xmm0
0x180030777  mov     rcx, cs:WPP_GLOBAL_Control
0x18003077e  lea     rsi, WPP_GLOBAL_Control
0x180030785  cmp     rcx, rsi
0x180030788  jz      short loc_18003079F
0x18003078a  mov     rcx, [rcx+10h]
0x18003078e  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180030795  mov     edx, 0FBh
0x18003079a  call    WPP_SF_
0x18003079f  mov     r12d, [rbx+4]
0x1800307a3  mov     r15d, r14d
0x1800307a6  and     r12d, 1
0x1800307aa  jz      short loc_1800307B1
0x1800307ac  cmp     dword ptr [rbx], 1
0x1800307af  jmp     short loc_1800307B4
0x1800307b1  cmp     [rbx], r14d
0x1800307b4  mov     r9d, [rbx+298h]; fContextReq
0x1800307bb  lea     r13, [rbx+288h]
0x1800307c2  mov     [rbp+57h+var_CC], r9d
0x1800307c6  setz    r15b
0x1800307ca  mov     rax, [rbx+2A0h]
0x1800307d1  lea     rcx, [rbx+268h]; phCredential
0x1800307d8  mov     qword ptr [rbp+57h+var_90+8], rax
0x1800307dc  lea     r8, [rbp+57h+pInput]; pInput
0x1800307e0  mov     eax, [rbx+2A8h]
0x1800307e6  mov     dword ptr [rbp+57h+var_90], eax
0x1800307e9  lea     rax, [rbp+57h+var_90]
0x1800307ed  mov     [rbp+57h+pInput.pBuffers], rax
0x1800307f1  lea     rax, [rbp+57h+uBytes]
0x1800307f5  mov     [rbp+57h+var_A0.pBuffers], rax
0x1800307f9  lea     rax, [rbp+57h+var_B8]
0x1800307fd  mov     dword ptr [rbp+57h+var_90+4], 2
0x180030804  mov     [rbp+57h+Size+8], r14
0x180030808  mov     [rbp+57h+Size], 0
0x180030810  mov     [rbp+57h+pInput.cBuffers], 2
0x180030817  mov     [rbp+57h+pInput.ulVersion], r14d
0x18003081b  mov     [rbp+57h+uBytes+8], r14
0x18003081f  mov     dword ptr [rbp+57h+uBytes], r14d
0x180030823  mov     dword ptr [rbp+57h+uBytes+4], 2
0x18003082a  mov     [rbp+57h+var_A0.cBuffers], 1
0x180030831  mov     [rbp+57h+var_A0.ulVersion], r14d
0x180030835  test    r12d, r12d
0x180030838  jz      short loc_18003089A
0x18003083a  mov     [rsp+130h+ptsExpiry], rax; ptsExpiry
0x18003083f  test    r15d, r15d
0x180030842  lea     rax, [rbp+57h+var_D0]
0x180030846  mov     rdx, r14
0x180030849  mov     [rsp+130h+pfContextAttr], rax; pfContextAttr
0x18003084e  cmovz   rdx, r13; phContext
0x180030852  lea     rax, [rbp+57h+var_A0]
0x180030856  mov     [rsp+130h+pOutput], rax; pOutput
0x18003085b  mov     [rsp+130h+phNewContext], r13; phNewContext
0x180030860  mov     [rsp+130h+TargetDataRep], r14d; TargetDataRep
0x180030865  call    cs:__imp_AcceptSecurityContext
0x18003086b  mov     edi, eax
0x18003086d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030874  cmp     rcx, rsi
0x180030877  jz      loc_180030952
0x18003087d  mov     rcx, [rcx+10h]
0x180030881  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180030888  mov     edx, 0FCh
0x18003088d  mov     r9d, eax
0x180030890  call    WPP_SF_d
0x180030895  jmp     loc_180030952
0x18003089a  mov     [rsp+130h+var_D8], rax; ptsExpiry
0x18003089f  test    r15d, r15d
0x1800308a2  lea     rax, [rbp+57h+var_D0]
0x1800308a6  mov     rdx, r13
0x1800308a9  mov     [rsp+130h+var_E0], rax; pfContextAttr
0x1800308ae  cmovnz  r8, r14
0x1800308b2  lea     rax, [rbp+57h+var_A0]
0x1800308b6  cmovnz  rdx, r14; phContext
0x1800308ba  mov     [rsp+130h+var_E8], rax; pOutput
0x1800308bf  mov     [rsp+130h+ptsExpiry], r13; phNewContext
0x1800308c4  mov     dword ptr [rsp+130h+pfContextAttr], r14d; Reserved2
0x1800308c9  mov     [rsp+130h+pOutput], r8; pInput
0x1800308ce  xor     r8d, r8d; pszTargetName
0x1800308d1  mov     dword ptr [rsp+130h+phNewContext], r14d; TargetDataRep
0x1800308d6  mov     [rsp+130h+TargetDataRep], r14d; Reserved1
0x1800308db  call    cs:__imp_InitializeSecurityContextW
0x1800308e1  mov     edi, eax
0x1800308e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308ea  cmp     rcx, rsi
0x1800308ed  jz      short loc_18003090E
0x1800308ef  mov     rcx, [rcx+10h]
0x1800308f3  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x1800308fa  mov     edx, 0FDh
0x1800308ff  mov     r9d, eax
0x180030902  call    WPP_SF_d
0x180030907  mov     rcx, cs:WPP_GLOBAL_Control
0x18003090e  cmp     edi, 9035Ch
0x180030914  jnz     short loc_180030937
0x180030916  cmp     rcx, rsi
0x180030919  jz      short loc_180030930
0x18003091b  mov     rcx, [rcx+10h]
0x18003091f  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180030926  mov     edx, 0FEh
0x18003092b  call    WPP_SF_
0x180030930  mov     edi, 33Ah
0x180030935  jmp     short loc_180030956
0x180030937  test    edi, edi
0x180030939  jns     short loc_180030956
0x18003093b  mov     edx, edi; unsigned int
0x18003093d  test    r15d, r15d
0x180030940  jz      short loc_180030946
0x180030942  xor     ecx, ecx
0x180030944  jmp     short loc_18003094B
0x180030946  mov     ecx, 1; int
0x18003094b  call    ?GetEapErrorFromWinError@@YAJHK@Z; GetEapErrorFromWinError(int,ulong)
0x180030950  mov     edi, eax
0x180030952  test    edi, edi
0x180030954  js      short loc_18003095C
0x180030956  and     dword ptr [rbx+4], 0FFFFFFBFh
0x18003095a  test    edi, edi
0x18003095c  jz      short loc_18003097B
0x18003095e  cmp     edi, 90312h
0x180030964  jz      short loc_18003097B
0x180030966  test    edi, edi
0x180030968  jns     loc_180030A4A
0x18003096e  test    [rbp+57h+var_D0], 4000h
0x180030975  jz      loc_180030A4A
0x18003097b  mov     esi, dword ptr [rbp+57h+uBytes]
0x18003097e  test    esi, esi
0x180030980  jz      loc_180030A43
0x180030986  cmp     [rbp+57h+uBytes+8], r14
0x18003098a  jz      loc_180030A43
0x180030990  cmp     esi, [rbx+2C4h]
0x180030996  jbe     short loc_1800309B7
0x180030998  mov     rcx, [rbx+2B8h]; hMem
0x18003099f  call    cs:__imp_LocalFree
0x1800309a5  mov     [rbx+2B8h], r14
0x1800309ac  mov     qword ptr [rbx+2C0h], 0
0x1800309b7  mov     rax, [rbx+2B8h]
0x1800309be  test    rax, rax
0x1800309c1  jnz     short loc_180030A24
0x1800309c3  mov     rdx, rsi; uBytes
0x1800309c6  lea     ecx, [rax+40h]; uFlags
0x1800309c9  call    cs:__imp_LocalAlloc
0x1800309cf  mov     [rbx+2B8h], rax
0x1800309d6  test    rax, rax
0x1800309d9  jnz     short loc_180030A1E
0x1800309db  xor     r14d, r14d
0x1800309de  mov     [rbx+2C0h], r14
0x1800309e5  call    cs:__imp_GetLastError
0x1800309eb  mov     edi, eax
0x1800309ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309f4  lea     rsi, WPP_GLOBAL_Control
0x1800309fb  cmp     rcx, rsi
0x1800309fe  jz      loc_180030A8B
0x180030a04  mov     rcx, [rcx+10h]
0x180030a08  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180030a0f  mov     edx, 0FFh
0x180030a14  mov     r9d, eax
0x180030a17  call    WPP_SF_d
0x180030a1c  jmp     short loc_180030A8B
0x180030a1e  mov     [rbx+2C4h], esi
0x180030a24  mov     rdx, [rbp+57h+uBytes+8]; Src
0x180030a28  mov     r8, rsi; Size
0x180030a2b  mov     rcx, rax; void *
0x180030a2e  call    memcpy_0
0x180030a33  xor     r14d, r14d
0x180030a36  mov     [rbx+2C0h], esi
0x180030a3c  mov     [rbx+2C8h], r14
0x180030a43  lea     rsi, WPP_GLOBAL_Control
0x180030a4a  cmp     dword ptr [rbp+57h+Size+4], 5
0x180030a4e  jnz     short loc_180030A84
0x180030a50  mov     eax, dword ptr [rbp+57h+Size]
0x180030a53  mov     edx, [rbx+2A8h]
0x180030a59  cmp     edx, eax
0x180030a5b  jb      short loc_180030A84
0x180030a5d  cmp     [rbx+2ACh], eax
0x180030a63  jb      short loc_180030A84
0x180030a65  mov     rcx, [rbx+2A0h]; void *
0x180030a6c  sub     edx, eax
0x180030a6e  add     rdx, rcx; Src
0x180030a71  mov     r8d, eax; Size
0x180030a74  call    memmove_0
0x180030a79  mov     eax, dword ptr [rbp+57h+Size]
0x180030a7c  mov     [rbx+2A8h], eax
0x180030a82  jmp     short loc_180030A8B
0x180030a84  mov     [rbx+2A8h], r14d
0x180030a8b  test    edi, edi
0x180030a8d  jz      short loc_180030AA4
0x180030a8f  cmp     edi, 90312h
0x180030a95  jz      short loc_180030AA4
0x180030a97  test    edi, edi
0x180030a99  jns     short loc_180030ADB
0x180030a9b  test    [rbp+57h+var_D0], 4000h
0x180030aa2  jz      short loc_180030ADB
0x180030aa4  mov     rcx, [rbp+57h+uBytes+8]; pvContextBuffer
0x180030aa8  test    rcx, rcx
0x180030aab  jz      short loc_180030ADB
0x180030aad  call    cs:__imp_FreeContextBuffer
0x180030ab3  test    eax, eax
0x180030ab5  jz      short loc_180030ADB
0x180030ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x180030abe  cmp     rcx, rsi
0x180030ac1  jz      short loc_180030ADB
0x180030ac3  mov     rcx, [rcx+10h]
0x180030ac7  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180030ace  mov     edx, 100h
0x180030ad3  mov     r9d, eax
0x180030ad6  call    WPP_SF_d
0x180030adb  cmp     dword ptr [rbp+57h+uBytes], r14d
0x180030adf  jnz     short loc_180030B1B
0x180030ae1  cmp     edi, 90312h
0x180030ae7  jnz     short loc_180030B27
0x180030ae9  mov     rcx, cs:WPP_GLOBAL_Control
0x180030af0  mov     r9d, [rbp+57h+var_CC]
0x180030af4  cmp     rcx, rsi
0x180030af7  jz      loc_1800307CA
0x180030afd  mov     rcx, [rcx+10h]
0x180030b01  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180030b08  mov     edx, 101h
0x180030b0d  call    WPP_SF_
0x180030b12  mov     r9d, [rbp+57h+var_CC]
0x180030b16  jmp     loc_1800307CA
0x180030b1b  cmp     edi, 90312h
0x180030b21  jz      loc_180030BA7
0x180030b27  xorps   xmm0, xmm0
0x180030b2a  lea     r8, [rbp+57h+pBuffer]; pBuffer
0x180030b2e  movups  [rbp+57h+pBuffer], xmm0
0x180030b32  mov     edx, 5Ah ; 'Z'; ulAttribute
0x180030b37  mov     rcx, r13; phContext
0x180030b3a  movups  [rbp+57h+pBuffer+0Ch], xmm0
0x180030b3e  call    cs:__imp_QueryContextAttributesW
0x180030b44  test    eax, eax
0x180030b46  jnz     short loc_180030BA7
0x180030b48  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b4f  cmp     rcx, rsi
0x180030b52  jz      short loc_180030BA7
0x180030b54  test    dword ptr [rbx+4], 4000h
0x180030b5b  lea     rax, aEaptls_0; "EAPTLS"
0x180030b62  mov     rcx, [rcx+10h]
0x180030b66  lea     r9, aPeap_0; "PEAP"
0x180030b6d  cmovz   r9, rax
0x180030b71  mov     eax, [rbp+57h+var_58]
0x180030b74  mov     dword ptr [rsp+130h+var_E0], eax
0x180030b78  mov     eax, [rbp+57h+var_5C]
0x180030b7b  mov     dword ptr [rsp+130h+var_E8], eax
0x180030b7f  mov     eax, [rbp+57h+var_60]
0x180030b82  mov     dword ptr [rsp+130h+ptsExpiry], eax
0x180030b86  mov     eax, dword ptr [rbp+57h+pBuffer+0Ch]
0x180030b89  mov     dword ptr [rsp+130h+pfContextAttr], eax
0x180030b8d  mov     eax, dword ptr [rbp+57h+pBuffer+8]
0x180030b90  mov     dword ptr [rsp+130h+pOutput], eax
0x180030b94  mov     eax, dword ptr [rbp+57h+pBuffer+4]
0x180030b97  mov     dword ptr [rsp+130h+phNewContext], eax
0x180030b9b  mov     eax, dword ptr [rbp+57h+pBuffer]
0x180030b9e  mov     [rsp+130h+TargetDataRep], eax
0x180030ba2  call    WPP_SF_sddddddd
0x180030ba7  mov     eax, edi
0x180030ba9  mov     rcx, [rbp+57h+var_50]
0x180030bad  xor     rcx, rsp; StackCookie
0x180030bb0  call    __security_check_cookie
0x180030bb5  add     rsp, 0F8h
0x180030bbc  pop     r15
0x180030bbe  pop     r14
0x180030bc0  pop     r13
0x180030bc2  pop     r12
0x180030bc4  pop     rdi
0x180030bc5  pop     rsi
0x180030bc6  pop     rbx
0x180030bc7  pop     rbp
0x180030bc8  retn
```
