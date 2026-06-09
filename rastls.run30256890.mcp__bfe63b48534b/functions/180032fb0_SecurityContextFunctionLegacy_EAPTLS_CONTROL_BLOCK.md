# SecurityContextFunctionLegacy(_EAPTLS_CONTROL_BLOCK *)

- ea: `0x180032fb0`
- end: `0x18003347c`
- name: `?SecurityContextFunctionLegacy@@YAJPEAU_EAPTLS_CONTROL_BLOCK@@@Z`
- size: `1228`
- prototype: `__int64 __fastcall(struct _EAPTLS_CONTROL_BLOCK *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180032f98`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180032fb0`
- `0x180038270`
- `0x180038e4c`
- `0x180038e58`
- `0x180054c64`
- `0x18005df8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033285`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033263`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033263`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033233`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033233`
- `SspiCli!QueryContextAttributesW` at `0x1800333ea`
- `SspiCli!QueryContextAttributesW` at `0x1800333ea`
- `SspiCli!FreeContextBuffer` at `0x180033353`
- `SspiCli!FreeContextBuffer` at `0x180033353`
- `SspiCli!InitializeSecurityContextW` at `0x180033169`
- `SspiCli!InitializeSecurityContextW` at `0x180033169`
- `SspiCli!AcceptSecurityContext` at `0x1800330ed`
- `SspiCli!AcceptSecurityContext` at `0x1800330ed`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v9);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 253, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v12);
      v13 = WPP_GLOBAL_Control;
    }
    if ( EapErrorFromWinError == 590684 )
    {
      if ( v13 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)v13 + 2), 254, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 255, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, LastError);
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
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 256, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v19);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 257, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
0x180032fb0  push    rbp
0x180032fb2  push    rbx
0x180032fb3  push    rsi
0x180032fb4  push    rdi
0x180032fb5  push    r12
0x180032fb7  push    r13
0x180032fb9  push    r14
0x180032fbb  push    r15
0x180032fbd  lea     rbp, [rsp-1Fh]
0x180032fc2  sub     rsp, 0F8h
0x180032fc9  mov     rax, cs:__security_cookie
0x180032fd0  xor     rax, rsp
0x180032fd3  mov     [rbp+57h+var_50], rax
0x180032fd7  xorps   xmm0, xmm0
0x180032fda  xorps   xmm1, xmm1
0x180032fdd  xor     r14d, r14d
0x180032fe0  mov     rbx, rcx
0x180032fe3  movups  xmmword ptr [rbp+57h+pInput.ulVersion], xmm0
0x180032fe7  mov     [rbp+57h+var_D0], r14d
0x180032feb  movups  [rbp+57h+var_90], xmm1
0x180032fef  mov     qword ptr [rbp+57h+var_B8], r14
0x180032ff3  movups  xmmword ptr [rbp+57h+Size], xmm0
0x180032ff7  movups  xmmword ptr [rbp+57h+var_A0.ulVersion], xmm1
0x180032ffb  movups  xmmword ptr [rbp+57h+uBytes], xmm0
0x180032fff  mov     rcx, cs:WPP_GLOBAL_Control
0x180033006  lea     rsi, WPP_GLOBAL_Control
0x18003300d  cmp     rcx, rsi
0x180033010  jz      short loc_180033027
0x180033012  mov     rcx, [rcx+10h]
0x180033016  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18003301d  mov     edx, 0FBh
0x180033022  call    WPP_SF_
0x180033027  mov     r12d, [rbx+4]
0x18003302b  mov     r15d, r14d
0x18003302e  and     r12d, 1
0x180033032  jz      short loc_180033039
0x180033034  cmp     dword ptr [rbx], 1
0x180033037  jmp     short loc_18003303C
0x180033039  cmp     [rbx], r14d
0x18003303c  mov     r9d, [rbx+298h]; fContextReq
0x180033043  lea     r13, [rbx+288h]
0x18003304a  mov     [rbp+57h+var_CC], r9d
0x18003304e  setz    r15b
0x180033052  mov     rax, [rbx+2A0h]
0x180033059  lea     rcx, [rbx+268h]; phCredential
0x180033060  mov     qword ptr [rbp+57h+var_90+8], rax
0x180033064  lea     r8, [rbp+57h+pInput]; pInput
0x180033068  mov     eax, [rbx+2A8h]
0x18003306e  mov     dword ptr [rbp+57h+var_90], eax
0x180033071  lea     rax, [rbp+57h+var_90]
0x180033075  mov     [rbp+57h+pInput.pBuffers], rax
0x180033079  lea     rax, [rbp+57h+uBytes]
0x18003307d  mov     [rbp+57h+var_A0.pBuffers], rax
0x180033081  lea     rax, [rbp+57h+var_B8]
0x180033085  mov     dword ptr [rbp+57h+var_90+4], 2
0x18003308c  mov     [rbp+57h+Size+8], r14
0x180033090  mov     [rbp+57h+Size], 0
0x180033098  mov     [rbp+57h+pInput.cBuffers], 2
0x18003309f  mov     [rbp+57h+pInput.ulVersion], r14d
0x1800330a3  mov     [rbp+57h+uBytes+8], r14
0x1800330a7  mov     dword ptr [rbp+57h+uBytes], r14d
0x1800330ab  mov     dword ptr [rbp+57h+uBytes+4], 2
0x1800330b2  mov     [rbp+57h+var_A0.cBuffers], 1
0x1800330b9  mov     [rbp+57h+var_A0.ulVersion], r14d
0x1800330bd  test    r12d, r12d
0x1800330c0  jz      short loc_180033128
0x1800330c2  mov     [rsp+130h+ptsExpiry], rax; ptsExpiry
0x1800330c7  test    r15d, r15d
0x1800330ca  lea     rax, [rbp+57h+var_D0]
0x1800330ce  mov     rdx, r14
0x1800330d1  mov     [rsp+130h+pfContextAttr], rax; pfContextAttr
0x1800330d6  cmovz   rdx, r13; phContext
0x1800330da  lea     rax, [rbp+57h+var_A0]
0x1800330de  mov     [rsp+130h+pOutput], rax; pOutput
0x1800330e3  mov     [rsp+130h+phNewContext], r13; phNewContext
0x1800330e8  mov     [rsp+130h+TargetDataRep], r14d; TargetDataRep
0x1800330ed  call    cs:__imp_AcceptSecurityContext
0x1800330f4  nop     dword ptr [rax+rax+00h]
0x1800330f9  mov     edi, eax
0x1800330fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180033102  cmp     rcx, rsi
0x180033105  jz      loc_1800331E6
0x18003310b  mov     rcx, [rcx+10h]
0x18003310f  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180033116  mov     edx, 0FCh
0x18003311b  mov     r9d, eax
0x18003311e  call    WPP_SF_d
0x180033123  jmp     loc_1800331E6
0x180033128  mov     [rsp+130h+var_D8], rax; ptsExpiry
0x18003312d  test    r15d, r15d
0x180033130  lea     rax, [rbp+57h+var_D0]
0x180033134  mov     rdx, r13
0x180033137  mov     [rsp+130h+var_E0], rax; pfContextAttr
0x18003313c  cmovnz  r8, r14
0x180033140  lea     rax, [rbp+57h+var_A0]
0x180033144  cmovnz  rdx, r14; phContext
0x180033148  mov     [rsp+130h+var_E8], rax; pOutput
0x18003314d  mov     [rsp+130h+ptsExpiry], r13; phNewContext
0x180033152  mov     dword ptr [rsp+130h+pfContextAttr], r14d; Reserved2
0x180033157  mov     [rsp+130h+pOutput], r8; pInput
0x18003315c  xor     r8d, r8d; pszTargetName
0x18003315f  mov     dword ptr [rsp+130h+phNewContext], r14d; TargetDataRep
0x180033164  mov     [rsp+130h+TargetDataRep], r14d; Reserved1
0x180033169  call    cs:__imp_InitializeSecurityContextW
0x180033170  nop     dword ptr [rax+rax+00h]
0x180033175  mov     edi, eax
0x180033177  mov     rcx, cs:WPP_GLOBAL_Control
0x18003317e  cmp     rcx, rsi
0x180033181  jz      short loc_1800331A2
0x180033183  mov     rcx, [rcx+10h]
0x180033187  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18003318e  mov     edx, 0FDh
0x180033193  mov     r9d, eax
0x180033196  call    WPP_SF_d
0x18003319b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800331a2  cmp     edi, 9035Ch
0x1800331a8  jnz     short loc_1800331CB
0x1800331aa  cmp     rcx, rsi
0x1800331ad  jz      short loc_1800331C4
0x1800331af  mov     rcx, [rcx+10h]
0x1800331b3  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x1800331ba  mov     edx, 0FEh
0x1800331bf  call    WPP_SF_
0x1800331c4  mov     edi, 33Ah
0x1800331c9  jmp     short loc_1800331EA
0x1800331cb  test    edi, edi
0x1800331cd  jns     short loc_1800331EA
0x1800331cf  mov     edx, edi; unsigned int
0x1800331d1  test    r15d, r15d
0x1800331d4  jz      short loc_1800331DA
0x1800331d6  xor     ecx, ecx
0x1800331d8  jmp     short loc_1800331DF
0x1800331da  mov     ecx, 1; int
0x1800331df  call    ?GetEapErrorFromWinError@@YAJHK@Z; GetEapErrorFromWinError(int,ulong)
0x1800331e4  mov     edi, eax
0x1800331e6  test    edi, edi
0x1800331e8  js      short loc_1800331F0
0x1800331ea  and     dword ptr [rbx+4], 0FFFFFFBFh
0x1800331ee  test    edi, edi
0x1800331f0  jz      short loc_18003320F
0x1800331f2  cmp     edi, 90312h
0x1800331f8  jz      short loc_18003320F
0x1800331fa  test    edi, edi
0x1800331fc  jns     loc_1800332F0
0x180033202  test    [rbp+57h+var_D0], 4000h
0x180033209  jz      loc_1800332F0
0x18003320f  mov     esi, dword ptr [rbp+57h+uBytes]
0x180033212  test    esi, esi
0x180033214  jz      loc_1800332E9
0x18003321a  cmp     [rbp+57h+uBytes+8], r14
0x18003321e  jz      loc_1800332E9
0x180033224  cmp     esi, [rbx+2C4h]
0x18003322a  jbe     short loc_180033251
0x18003322c  mov     rcx, [rbx+2B8h]; hMem
0x180033233  call    cs:__imp_LocalFree
0x18003323a  nop     dword ptr [rax+rax+00h]
0x18003323f  mov     [rbx+2B8h], r14
0x180033246  mov     qword ptr [rbx+2C0h], 0
0x180033251  mov     rax, [rbx+2B8h]
0x180033258  test    rax, rax
0x18003325b  jnz     short loc_1800332CA
0x18003325d  mov     rdx, rsi; uBytes
0x180033260  lea     ecx, [rax+40h]; uFlags
0x180033263  call    cs:__imp_LocalAlloc
0x18003326a  nop     dword ptr [rax+rax+00h]
0x18003326f  mov     [rbx+2B8h], rax
0x180033276  test    rax, rax
0x180033279  jnz     short loc_1800332C4
0x18003327b  xor     r14d, r14d
0x18003327e  mov     [rbx+2C0h], r14
0x180033285  call    cs:__imp_GetLastError
0x18003328c  nop     dword ptr [rax+rax+00h]
0x180033291  mov     edi, eax
0x180033293  mov     rcx, cs:WPP_GLOBAL_Control
0x18003329a  lea     rsi, WPP_GLOBAL_Control
0x1800332a1  cmp     rcx, rsi
0x1800332a4  jz      loc_180033331
0x1800332aa  mov     rcx, [rcx+10h]
0x1800332ae  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x1800332b5  mov     edx, 0FFh
0x1800332ba  mov     r9d, eax
0x1800332bd  call    WPP_SF_d
0x1800332c2  jmp     short loc_180033331
0x1800332c4  mov     [rbx+2C4h], esi
0x1800332ca  mov     rdx, [rbp+57h+uBytes+8]; Src
0x1800332ce  mov     r8, rsi; Size
0x1800332d1  mov     rcx, rax; void *
0x1800332d4  call    memcpy_0
0x1800332d9  xor     r14d, r14d
0x1800332dc  mov     [rbx+2C0h], esi
0x1800332e2  mov     [rbx+2C8h], r14
0x1800332e9  lea     rsi, WPP_GLOBAL_Control
0x1800332f0  cmp     dword ptr [rbp+57h+Size+4], 5
0x1800332f4  jnz     short loc_18003332A
0x1800332f6  mov     eax, dword ptr [rbp+57h+Size]
0x1800332f9  mov     edx, [rbx+2A8h]
0x1800332ff  cmp     edx, eax
0x180033301  jb      short loc_18003332A
0x180033303  cmp     [rbx+2ACh], eax
0x180033309  jb      short loc_18003332A
0x18003330b  mov     rcx, [rbx+2A0h]; void *
0x180033312  sub     edx, eax
0x180033314  add     rdx, rcx; Src
0x180033317  mov     r8d, eax; Size
0x18003331a  call    memmove_0
0x18003331f  mov     eax, dword ptr [rbp+57h+Size]
0x180033322  mov     [rbx+2A8h], eax
0x180033328  jmp     short loc_180033331
0x18003332a  mov     [rbx+2A8h], r14d
0x180033331  test    edi, edi
0x180033333  jz      short loc_18003334A
0x180033335  cmp     edi, 90312h
0x18003333b  jz      short loc_18003334A
0x18003333d  test    edi, edi
0x18003333f  jns     short loc_180033387
0x180033341  test    [rbp+57h+var_D0], 4000h
0x180033348  jz      short loc_180033387
0x18003334a  mov     rcx, [rbp+57h+uBytes+8]; pvContextBuffer
0x18003334e  test    rcx, rcx
0x180033351  jz      short loc_180033387
0x180033353  call    cs:__imp_FreeContextBuffer
0x18003335a  nop     dword ptr [rax+rax+00h]
0x18003335f  test    eax, eax
0x180033361  jz      short loc_180033387
0x180033363  mov     rcx, cs:WPP_GLOBAL_Control
0x18003336a  cmp     rcx, rsi
0x18003336d  jz      short loc_180033387
0x18003336f  mov     rcx, [rcx+10h]
0x180033373  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18003337a  mov     edx, 100h
0x18003337f  mov     r9d, eax
0x180033382  call    WPP_SF_d
0x180033387  cmp     dword ptr [rbp+57h+uBytes], r14d
0x18003338b  jnz     short loc_1800333C7
0x18003338d  cmp     edi, 90312h
0x180033393  jnz     short loc_1800333D3
0x180033395  mov     rcx, cs:WPP_GLOBAL_Control
0x18003339c  mov     r9d, [rbp+57h+var_CC]
0x1800333a0  cmp     rcx, rsi
0x1800333a3  jz      loc_180033052
0x1800333a9  mov     rcx, [rcx+10h]
0x1800333ad  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x1800333b4  mov     edx, 101h
0x1800333b9  call    WPP_SF_
0x1800333be  mov     r9d, [rbp+57h+var_CC]
0x1800333c2  jmp     loc_180033052
0x1800333c7  cmp     edi, 90312h
0x1800333cd  jz      loc_180033459
0x1800333d3  xorps   xmm0, xmm0
0x1800333d6  lea     r8, [rbp+57h+pBuffer]; pBuffer
0x1800333da  movups  [rbp+57h+pBuffer], xmm0
0x1800333de  mov     edx, 5Ah ; 'Z'; ulAttribute
0x1800333e3  mov     rcx, r13; phContext
0x1800333e6  movups  [rbp+57h+pBuffer+0Ch], xmm0
0x1800333ea  call    cs:__imp_QueryContextAttributesW
0x1800333f1  nop     dword ptr [rax+rax+00h]
0x1800333f6  test    eax, eax
0x1800333f8  jnz     short loc_180033459
0x1800333fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180033401  cmp     rcx, rsi
0x180033404  jz      short loc_180033459
0x180033406  test    dword ptr [rbx+4], 4000h
0x18003340d  lea     rax, aEaptls_0; "EAPTLS"
0x180033414  mov     rcx, [rcx+10h]
0x180033418  lea     r9, aPeap_0; "PEAP"
0x18003341f  cmovz   r9, rax
0x180033423  mov     eax, [rbp+57h+var_58]
0x180033426  mov     dword ptr [rsp+130h+var_E0], eax
0x18003342a  mov     eax, [rbp+57h+var_5C]
0x18003342d  mov     dword ptr [rsp+130h+var_E8], eax
0x180033431  mov     eax, [rbp+57h+var_60]
0x180033434  mov     dword ptr [rsp+130h+ptsExpiry], eax
0x180033438  mov     eax, dword ptr [rbp+57h+pBuffer+0Ch]
0x18003343b  mov     dword ptr [rsp+130h+pfContextAttr], eax
0x18003343f  mov     eax, dword ptr [rbp+57h+pBuffer+8]
0x180033442  mov     dword ptr [rsp+130h+pOutput], eax
0x180033446  mov     eax, dword ptr [rbp+57h+pBuffer+4]
0x180033449  mov     dword ptr [rsp+130h+phNewContext], eax
0x18003344d  mov     eax, dword ptr [rbp+57h+pBuffer]
0x180033450  mov     [rsp+130h+TargetDataRep], eax
0x180033454  call    WPP_SF_sddddddd
0x180033459  mov     eax, edi
0x18003345b  mov     rcx, [rbp+57h+var_50]
0x18003345f  xor     rcx, rsp; StackCookie
0x180033462  call    __security_check_cookie
0x180033467  add     rsp, 0F8h
0x18003346e  pop     r15
0x180033470  pop     r14
0x180033472  pop     r13
0x180033474  pop     r12
0x180033476  pop     rdi
0x180033477  pop     rsi
0x180033478  pop     rbx
0x180033479  pop     rbp
0x18003347a  retn
```
