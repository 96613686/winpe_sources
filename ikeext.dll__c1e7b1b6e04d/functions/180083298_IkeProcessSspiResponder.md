# IkeProcessSspiResponder

- ea: `0x180083298`
- end: `0x1800839b4`
- name: `IkeProcessSspiResponder`
- size: `1820`
- prototype: `__int64 __fastcall(int, struct _SecBuffer *, unsigned int *, _DWORD *)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x1800825a4`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x180008388`
- `0x180019e40`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x18004d15c`
- `0x180050850`
- `0x18005bc40`
- `0x18005bce4`
- `0x18006dec8`
- `0x18007c950`
- `0x18007d46c`
- `0x1800823e8`
- `0x180083298`
- `0x180084c50`
- `0x180117fa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008379f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008379f`
- `SspiCli!AcceptSecurityContext` at `0x18008368d`
- `SspiCli!AcceptSecurityContext` at `0x18008368d`

## string_xrefs

- `0x180083468`: `Received NULL SSPI token`
- `0x180083641`: `ASC intoken:`
- `0x180083907`: `ASC outtoken:`

## pseudocode

```c
__int64 __fastcall IkeProcessSspiResponder(int a1, struct _SecBuffer *a2, unsigned int *a3, _DWORD *a4)
{
  struct _SecBuffer *v4; // rbx
  SIZE_T cbBuffer; // rcx
  __int64 SecBuffer; // r12
  unsigned __int64 v9; // rcx
  struct _SecHandle *v10; // r13
  struct _SecBuffer *v11; // rdx
  int v12; // esi
  __int64 v13; // r12
  __int64 v14; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v16; // rcx
  int TlsMmLuid; // eax
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // r8d
  int v21; // r9d
  char *v22; // rdx
  const char *v23; // rcx
  unsigned int v24; // r13d
  __int64 v25; // rdi
  __int64 v26; // rbx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rdi
  __int64 v33; // rbx
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rax
  int v38; // r8d
  int v39; // r9d
  int *v40; // rbx
  __int64 v41; // rcx
  int v42; // edi
  __int64 v43; // rsi
  __int64 v44; // rbx
  __int64 v45; // rcx
  int v46; // eax
  __int64 v47; // rcx
  __int64 v48; // rax
  int v49; // r8d
  int v50; // r9d
  __int64 v51; // rcx
  DWORD LastError; // r12d
  _QWORD *v53; // rdi
  __int64 v54; // rdi
  __int64 v55; // rbx
  __int64 v56; // rcx
  int v57; // eax
  __int64 v58; // rdi
  __int64 v59; // rbx
  __int64 v60; // rcx
  int v61; // eax
  __int64 v62; // rcx
  __int64 v63; // rax
  int v64; // r8d
  int v65; // r9d
  _DWORD *v66; // rax
  struct _SecBufferDesc pOutput; // [rsp+58h] [rbp-A8h] BYREF
  size_t Size[2]; // [rsp+68h] [rbp-98h] BYREF
  struct _SecBufferDesc pInput; // [rsp+78h] [rbp-88h] BYREF
  __int64 v72; // [rsp+88h] [rbp-78h] BYREF
  struct _SecBuffer *v73; // [rsp+90h] [rbp-70h] BYREF
  __int64 v74; // [rsp+98h] [rbp-68h] BYREF
  __int128 v75; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v76[32]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v77; // [rsp+D0h] [rbp-30h]
  __int64 v78; // [rsp+D8h] [rbp-28h]
  _BYTE v79[16]; // [rsp+E0h] [rbp-20h] BYREF
  const char *v80; // [rsp+F0h] [rbp-10h]
  __int64 v81; // [rsp+F8h] [rbp-8h]
  __int64 *v82; // [rsp+100h] [rbp+0h]
  __int64 v83; // [rsp+108h] [rbp+8h]
  __int64 *v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]

  v73 = a2;
  v4 = a2;
  pInput = 0;
  pOutput = 0;
  v75 = 0;
  *(_OWORD *)Size = 0;
  TraceLogHelper("IkeProcessSspiResponder", 1);
  pInput.cBuffers = 1;
  pInput.ulVersion = 0;
  pOutput.ulVersion = 0;
  pOutput.cBuffers = 1;
  if ( *((_QWORD *)a3 + 12) )
  {
    cbBuffer = v4->cbBuffer;
    pInput.pBuffers = (PSecBuffer)Size;
    pOutput.pBuffers = (PSecBuffer)&v75;
    SecBuffer = IkeAllocateSecBuffer(cbBuffer);
    if ( SecBuffer )
      goto LABEL_65;
    memcpy_0((void *)Size[1], v4->pvBuffer, LODWORD(Size[0]));
    SecBuffer = IkeAllocateSecBuffer(*a3);
    if ( SecBuffer )
      goto LABEL_65;
    v9 = (unsigned int)-**((_DWORD **)a3 + 12);
    v10 = (struct _SecHandle *)((unsigned __int64)(a3 + 6) & -(__int64)(**((_DWORD **)a3 + 12) != 0));
  }
  else
  {
    v11 = (struct _SecBuffer *)*((_QWORD *)a3 + 13);
    pInput.pBuffers = v4;
    pOutput.pBuffers = v11;
    if ( v11->cbBuffer )
    {
      SecBuffer = 0;
      v10 = (struct _SecHandle *)(a3 + 6);
    }
    else
    {
      SecBuffer = IkeAllocateSecBuffer(*a3);
      if ( SecBuffer )
        goto LABEL_65;
      v10 = 0;
    }
    v9 = *((_QWORD *)a3 + 13);
    *(_DWORD *)v9 = *a3;
  }
  v12 = ~(unsigned __int8)(a3[18] >> 22) & 2 | 0x8010;
  if ( !v4->cbBuffer )
  {
    v13 = 25;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v9);
      TlsMmLuid = IkeGetTlsMmLuid(v16);
      WPP_SF_iS(v14, 25, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, TlsMmLuid, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
      goto LABEL_18;
    v72 = IkeGetTlsMmLuid(v9);
    v77 = &v72;
    v78 = 8;
    v19 = IkeGetTlsPeerAddr(v18);
    tlgCreate1Sz_wchar_t(v79, v19);
    v22 = &byte_180155AC7;
    v23 = "Received NULL SSPI token";
LABEL_17:
    v80 = v23;
    v81 = v13;
    tlgWriteTransfer_EtwEventWriteTransfer((unsigned int)&dword_180173278, (_DWORD)v22, v20, v21, 5, (__int64)v76);
LABEL_18:
    v24 = -2146893048;
    goto LABEL_44;
  }
  if ( (a3[18] & 0x200) != 0 )
  {
    v13 = 26;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v25 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v26 = IkeGetTlsPeerAddr(v9);
      v28 = IkeGetTlsMmLuid(v27);
      WPP_SF_iS(v25, 26, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v28, v26);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
      goto LABEL_18;
    v72 = IkeGetTlsMmLuid(v9);
    v77 = &v72;
    v78 = 8;
    v30 = IkeGetTlsPeerAddr(v29);
    tlgCreate1Sz_wchar_t(v79, v30);
    v22 = byte_1801559DD;
    v23 = "SSPI fatal error occurred";
    goto LABEL_17;
  }
  if ( *((_QWORD *)a3 + 13) )
  {
    v72 = 0;
    SecBuffer = IkeGetImpersonationHandle(a1, (_DWORD)a3, 0, 0, (__int64)&v72);
  }
  v31 = *((_QWORD *)a3 + 13);
  if ( v31 )
    ++*(_DWORD *)(v31 + 80);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v32 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v33 = IkeGetTlsPeerAddr(v9);
    v35 = IkeGetTlsMmLuid(v34);
    WPP_SF_iSL(v32, 27, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v35, v33, v12);
    v4 = v73;
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v72 = IkeGetTlsMmLuid(v9);
    v77 = &v72;
    v78 = 8;
    v37 = IkeGetTlsPeerAddr(v36);
    tlgCreate1Sz_wchar_t(v79, v37);
    LODWORD(v73) = v12;
    v80 = (const char *)&v73;
    v81 = 4;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)&byte_18015599F,
      v38,
      v39,
      5,
      (__int64)v76);
  }
  IkeDumpSspiToken(v4->pvBuffer, "ASC intoken:", v4->cbBuffer);
  v40 = (int *)(a3 + 10);
  v24 = AcceptSecurityContext(
          (PCredHandle)(a3 + 2),
          v10,
          &pInput,
          v12,
          0x10u,
          (PCtxtHandle)(a3 + 6),
          &pOutput,
          a3 + 10,
          (PTimeStamp)a3 + 6);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v42 = *v40;
    v43 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v44 = IkeGetTlsPeerAddr(v41);
    v46 = IkeGetTlsMmLuid(v45);
    WPP_SF_iSDD(v43, 28, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v46, v44, v24, v42);
    v40 = (int *)(a3 + 10);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v74 = IkeGetTlsMmLuid(v41);
    v77 = &v74;
    v78 = 8;
    v48 = IkeGetTlsPeerAddr(v47);
    tlgCreate1Sz_wchar_t(v79, v48);
    v81 = 11;
    v82 = (__int64 *)&v73;
    LODWORD(v72) = *v40;
    v84 = &v72;
    v80 = "ASC failed";
    LODWORD(v73) = v24;
    v83 = 4;
    v85 = 4;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)word_180155A6A,
      v49,
      v50,
      7,
      (__int64)v76);
  }
  if ( !v24 || v24 == 590610 )
    goto LABEL_57;
LABEL_44:
  LastError = GetLastError();
  v53 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v54 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v55 = IkeGetTlsPeerAddr(v51);
      v57 = IkeGetTlsMmLuid(v56);
      WPP_SF_iSL(v54, 29, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v57, v55, LastError);
      v53 = WPP_GLOBAL_Control;
    }
    if ( v53 != &WPP_GLOBAL_Control && *((_BYTE *)v53 + 25) >= 2u && (*((_BYTE *)v53 + 28) & 0x10) != 0 )
    {
      v58 = v53[2];
      v59 = IkeGetTlsPeerAddr(v51);
      v61 = IkeGetTlsMmLuid(v60);
      WPP_SF_iSL(v58, 30, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v61, v59, v24);
    }
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v74 = IkeGetTlsMmLuid(v51);
    v78 = 8;
    v77 = &v74;
    v63 = IkeGetTlsPeerAddr(v62);
    tlgCreate1Sz_wchar_t(v79, v63);
    v81 = 11;
    v80 = "ASC failed";
    LODWORD(v72) = LastError;
    v82 = &v72;
    v83 = 4;
    v84 = (__int64 *)&v73;
    LODWORD(v73) = v24;
    v85 = 4;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)byte_180155A1D,
      v64,
      v65,
      7,
      (__int64)v76);
  }
  SecBuffer = SetSspiError(a3, v24, 1);
  if ( !SecBuffer )
  {
    v66 = (_DWORD *)*((_QWORD *)a3 + 13);
    if ( v66 )
      *v66 = 0;
LABEL_57:
    IkeDumpSspiToken(pOutput.pBuffers->pvBuffer, "ASC outtoken:", pOutput.pBuffers->cbBuffer);
    if ( !v24 && ((a3[18] & 0x800000) != 0 || (a3[10] & 2) != 0 || (unsigned int)IkeIsSslAuth(a3[22])) )
      *a4 = 1;
    if ( *((_QWORD *)a3 + 12) )
      IkeProcessOakASCResponse(Size, &v75);
    a3[18] |= 1u;
  }
LABEL_65:
  WfpMemFree((LPCVOID *)&Size[1]);
  WfpMemFree((LPCVOID *)&v75 + 1);
  TraceLogHelper("IkeProcessSspiResponder", 0);
  return IkeReturnError(SecBuffer, "IkeProcessSspiResponder");
}

```

## disassembly

```asm
0x180083298  push    rbp
0x18008329a  push    rbx
0x18008329b  push    rsi
0x18008329c  push    rdi
0x18008329d  push    r12
0x18008329f  push    r13
0x1800832a1  push    r14
0x1800832a3  push    r15
0x1800832a5  lea     rbp, [rsp-38h]
0x1800832aa  sub     rsp, 138h
0x1800832b1  mov     rax, cs:__security_cookie
0x1800832b8  xor     rax, rsp
0x1800832bb  mov     [rbp+70h+var_50], rax
0x1800832bf  xorps   xmm0, xmm0
0x1800832c2  mov     [rbp+70h+var_E0], rdx
0x1800832c6  xorps   xmm1, xmm1
0x1800832c9  mov     [rsp+170h+var_120], r9
0x1800832ce  mov     rbx, rdx
0x1800832d1  mov     rdi, rcx
0x1800832d4  mov     esi, 1
0x1800832d9  lea     rcx, aIkeprocesssspi_2; "IkeProcessSspiResponder"
0x1800832e0  mov     edx, esi
0x1800832e2  mov     r14, r8
0x1800832e5  movups  xmmword ptr [rsp+170h+pInput.ulVersion], xmm0
0x1800832ea  movups  xmmword ptr [rsp+170h+var_118.ulVersion], xmm1
0x1800832ef  movups  [rbp+70h+var_D0], xmm0
0x1800832f3  movups  xmmword ptr [rsp+170h+Size], xmm1
0x1800832f8  call    TraceLogHelper
0x1800832fd  xor     r15d, r15d
0x180083300  mov     [rsp+170h+pInput.cBuffers], esi
0x180083304  mov     [rsp+170h+pInput.ulVersion], r15d
0x180083309  mov     [rsp+170h+var_118.ulVersion], r15d
0x18008330e  mov     [rsp+170h+var_118.cBuffers], esi
0x180083312  cmp     [r14+60h], r15
0x180083316  jz      short loc_180083381
0x180083318  mov     ecx, [rbx]; dwBytes
0x18008331a  lea     rax, [rsp+170h+Size]
0x18008331f  mov     [rbp+70h+pInput.pBuffers], rax
0x180083323  lea     rdx, [rsp+170h+Size]
0x180083328  lea     rax, [rbp+70h+var_D0]
0x18008332c  mov     [rsp+170h+var_118.pBuffers], rax
0x180083331  call    IkeAllocateSecBuffer
0x180083336  mov     r12, rax
0x180083339  test    rax, rax
0x18008333c  jnz     loc_180083964
0x180083342  mov     r8d, dword ptr [rsp+170h+Size]; Size
0x180083347  mov     rdx, [rbx+8]; Src
0x18008334b  mov     rcx, [rsp+170h+Size+8]; void *
0x180083350  call    memcpy_0
0x180083355  mov     ecx, [r14]; dwBytes
0x180083358  lea     rdx, [rbp+70h+var_D0]
0x18008335c  call    IkeAllocateSecBuffer
0x180083361  mov     r12, rax
0x180083364  test    rax, rax
0x180083367  jnz     loc_180083964
0x18008336d  mov     rax, [r14+60h]
0x180083371  mov     ecx, [rax]
0x180083373  lea     rax, [r14+18h]
0x180083377  neg     ecx
0x180083379  sbb     r13, r13
0x18008337c  and     r13, rax
0x18008337f  jmp     short loc_1800833BC
0x180083381  mov     rdx, [r14+68h]
0x180083385  mov     [rbp+70h+pInput.pBuffers], rbx
0x180083389  mov     [rsp+170h+var_118.pBuffers], rdx
0x18008338e  cmp     [rdx], r15d
0x180083391  jnz     short loc_1800833AC
0x180083393  mov     ecx, [r14]; dwBytes
0x180083396  call    IkeAllocateSecBuffer
0x18008339b  mov     r12, rax
0x18008339e  test    rax, rax
0x1800833a1  jnz     loc_180083964
0x1800833a7  mov     r13, r15
0x1800833aa  jmp     short loc_1800833B3
0x1800833ac  mov     r12, r15
0x1800833af  lea     r13, [r14+18h]
0x1800833b3  mov     rcx, [r14+68h]
0x1800833b7  mov     eax, [r14]
0x1800833ba  mov     [rcx], eax
0x1800833bc  mov     esi, [r14+48h]
0x1800833c0  shr     esi, 16h
0x1800833c3  not     esi
0x1800833c5  and     esi, 2
0x1800833c8  or      esi, 8010h
0x1800833ce  cmp     [rbx], r15d
0x1800833d1  jnz     loc_18008349F
0x1800833d7  mov     rdi, cs:WPP_GLOBAL_Control
0x1800833de  lea     rsi, WPP_GLOBAL_Control
0x1800833e5  mov     r12d, 19h
0x1800833eb  lea     r15d, [r12-15h]
0x1800833f0  cmp     rdi, rsi
0x1800833f3  jz      short loc_18008342C
0x1800833f5  cmp     [rdi+19h], r15b
0x1800833f9  jb      short loc_18008342C
0x1800833fb  test    byte ptr [rdi+1Ch], 10h
0x1800833ff  jz      short loc_18008342C
0x180083401  mov     rdi, [rdi+10h]
0x180083405  call    IkeGetTlsPeerAddr
0x18008340a  mov     rbx, rax
0x18008340d  call    IkeGetTlsMmLuid
0x180083412  mov     r9, rax
0x180083415  mov     qword ptr [rsp+170h+TargetDataRep], rbx
0x18008341a  mov     edx, r12d
0x18008341d  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180083424  mov     rcx, rdi
0x180083427  call    WPP_SF_iS
0x18008342c  mov     eax, cs:dword_180173278
0x180083432  cmp     eax, r15d
0x180083435  jbe     short loc_180083494
0x180083437  call    IkeGetTlsMmLuid
0x18008343c  mov     [rbp+70h+var_E8], rax
0x180083440  lea     rax, [rbp+70h+var_E8]
0x180083444  mov     [rbp+70h+var_A0], rax
0x180083448  mov     [rbp+70h+var_98], 8
0x180083450  call    IkeGetTlsPeerAddr
0x180083455  mov     rdx, rax
0x180083458  lea     rcx, [rbp+70h+var_90]
0x18008345c  call    _tlgCreate1Sz_wchar_t
0x180083461  lea     rdx, byte_180155AC7
0x180083468  lea     rcx, aReceivedNullSs; "Received NULL SSPI token"
0x18008346f  lea     rax, [rbp+70h+var_C0]
0x180083473  mov     [rbp+70h+var_80], rcx
0x180083477  mov     [rsp+170h+phNewContext], rax
0x18008347c  lea     rcx, dword_180173278
0x180083483  mov     [rsp+170h+TargetDataRep], 5
0x18008348b  mov     [rbp+70h+var_78], r12
0x18008348f  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180083494  mov     r13d, 80090308h
0x18008349a  jmp     loc_18008379F
0x18008349f  test    dword ptr [r14+48h], 200h
0x1800834a7  jz      loc_18008354A
0x1800834ad  mov     rdi, cs:WPP_GLOBAL_Control
0x1800834b4  lea     rsi, WPP_GLOBAL_Control
0x1800834bb  mov     r12d, 1Ah
0x1800834c1  lea     r15d, [r12-16h]
0x1800834c6  cmp     rdi, rsi
0x1800834c9  jz      short loc_180083502
0x1800834cb  cmp     [rdi+19h], r15b
0x1800834cf  jb      short loc_180083502
0x1800834d1  test    byte ptr [rdi+1Ch], 10h
0x1800834d5  jz      short loc_180083502
0x1800834d7  mov     rdi, [rdi+10h]
0x1800834db  call    IkeGetTlsPeerAddr
0x1800834e0  mov     rbx, rax
0x1800834e3  call    IkeGetTlsMmLuid
0x1800834e8  mov     r9, rax
0x1800834eb  mov     qword ptr [rsp+170h+TargetDataRep], rbx
0x1800834f0  mov     edx, r12d
0x1800834f3  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x1800834fa  mov     rcx, rdi
0x1800834fd  call    WPP_SF_iS
0x180083502  mov     eax, cs:dword_180173278
0x180083508  cmp     eax, r15d
0x18008350b  jbe     short loc_180083494
0x18008350d  call    IkeGetTlsMmLuid
0x180083512  mov     [rbp+70h+var_E8], rax
0x180083516  lea     rax, [rbp+70h+var_E8]
0x18008351a  mov     [rbp+70h+var_A0], rax
0x18008351e  mov     [rbp+70h+var_98], 8
0x180083526  call    IkeGetTlsPeerAddr
0x18008352b  mov     rdx, rax
0x18008352e  lea     rcx, [rbp+70h+var_90]
0x180083532  call    _tlgCreate1Sz_wchar_t
0x180083537  lea     rdx, byte_1801559DD
0x18008353e  lea     rcx, aSspiFatalError; "SSPI fatal error occurred"
0x180083545  jmp     loc_18008346F
0x18008354a  cmp     [r14+68h], r15
0x18008354e  jz      short loc_180083571
0x180083550  lea     rax, [rbp+70h+var_E8]
0x180083554  mov     [rbp+70h+var_E8], r15
0x180083558  xor     r9d, r9d
0x18008355b  mov     qword ptr [rsp+170h+TargetDataRep], rax
0x180083560  xor     r8d, r8d
0x180083563  mov     rdx, r14
0x180083566  mov     rcx, rdi
0x180083569  call    IkeGetImpersonationHandle
0x18008356e  mov     r12, rax
0x180083571  mov     rax, [r14+68h]
0x180083575  test    rax, rax
0x180083578  jz      short loc_18008357D
0x18008357a  inc     dword ptr [rax+50h]
0x18008357d  mov     rdi, cs:WPP_GLOBAL_Control
0x180083584  lea     rax, WPP_GLOBAL_Control
0x18008358b  mov     r15d, 4
0x180083591  cmp     rdi, rax
0x180083594  jz      short loc_1800835D6
0x180083596  cmp     [rdi+19h], r15b
0x18008359a  jb      short loc_1800835D6
0x18008359c  test    byte ptr [rdi+1Ch], 10h
0x1800835a0  jz      short loc_1800835D6
0x1800835a2  mov     rdi, [rdi+10h]
0x1800835a6  call    IkeGetTlsPeerAddr
0x1800835ab  mov     rbx, rax
0x1800835ae  call    IkeGetTlsMmLuid
0x1800835b3  mov     r9, rax
0x1800835b6  mov     dword ptr [rsp+170h+phNewContext], esi
0x1800835ba  lea     edx, [r15+17h]
0x1800835be  mov     qword ptr [rsp+170h+TargetDataRep], rbx
0x1800835c3  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x1800835ca  mov     rcx, rdi
0x1800835cd  call    WPP_SF_iSL
0x1800835d2  mov     rbx, [rbp+70h+var_E0]
0x1800835d6  mov     eax, cs:dword_180173278
0x1800835dc  cmp     eax, r15d
0x1800835df  jbe     short loc_18008363E
0x1800835e1  call    IkeGetTlsMmLuid
0x1800835e6  mov     [rbp+70h+var_E8], rax
0x1800835ea  lea     rax, [rbp+70h+var_E8]
0x1800835ee  mov     [rbp+70h+var_A0], rax
0x1800835f2  mov     [rbp+70h+var_98], 8
0x1800835fa  call    IkeGetTlsPeerAddr
0x1800835ff  mov     rdx, rax
0x180083602  lea     rcx, [rbp+70h+var_90]
0x180083606  call    _tlgCreate1Sz_wchar_t
0x18008360b  lea     rax, [rbp+70h+var_E0]
0x18008360f  mov     dword ptr [rbp+70h+var_E0], esi
0x180083612  mov     [rbp+70h+var_80], rax
0x180083616  lea     rdx, byte_18015599F
0x18008361d  lea     rax, [rbp+70h+var_C0]
0x180083621  mov     [rbp+70h+var_78], r15
0x180083625  mov     [rsp+170h+phNewContext], rax
0x18008362a  lea     rcx, dword_180173278
0x180083631  mov     [rsp+170h+TargetDataRep], 5
0x180083639  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18008363e  mov     r8d, [rbx]
0x180083641  lea     rdx, aAscIntoken; "ASC intoken:"
0x180083648  mov     rcx, [rbx+8]
0x18008364c  call    IkeDumpSspiToken
0x180083651  lea     rax, [r14+30h]
0x180083655  mov     r9d, esi; fContextReq
0x180083658  mov     [rsp+170h+ptsExpiry], rax; ptsExpiry
0x18008365d  lea     rdx, [r14+18h]
0x180083661  lea     rax, [rsp+170h+var_118]
0x180083666  lea     rbx, [r14+28h]
0x18008366a  mov     [rsp+170h+pfContextAttr], rbx; pfContextAttr
0x18008366f  lea     rcx, [r14+8]; phCredential
0x180083673  mov     [rsp+170h+pOutput], rax; pOutput
0x180083678  lea     r8, [rsp+170h+pInput]; pInput
0x18008367d  mov     [rsp+170h+phNewContext], rdx; phNewContext
0x180083682  mov     rdx, r13; phContext
0x180083685  mov     [rsp+170h+TargetDataRep], 10h; TargetDataRep
0x18008368d  call    cs:__imp_AcceptSecurityContext
0x180083693  mov     r13d, eax
0x180083696  mov     rax, cs:WPP_GLOBAL_Control
0x18008369d  lea     rsi, WPP_GLOBAL_Control
0x1800836a4  cmp     rax, rsi
0x1800836a7  jz      short loc_1800836F8
0x1800836a9  cmp     [rax+19h], r15b
0x1800836ad  jb      short loc_1800836F8
0x1800836af  test    byte ptr [rax+1Ch], 10h
0x1800836b3  jz      short loc_1800836F8
0x1800836b5  mov     edi, [rbx]
0x1800836b7  mov     rsi, [rax+10h]
0x1800836bb  call    IkeGetTlsPeerAddr
0x1800836c0  mov     rbx, rax
0x1800836c3  call    IkeGetTlsMmLuid
0x1800836c8  mov     dword ptr [rsp+170h+pOutput], edi
0x1800836cc  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x1800836d3  mov     r9, rax
0x1800836d6  mov     dword ptr [rsp+170h+phNewContext], r13d
0x1800836db  mov     edx, 1Ch
0x1800836e0  mov     qword ptr [rsp+170h+TargetDataRep], rbx
0x1800836e5  mov     rcx, rsi
0x1800836e8  call    WPP_SF_iSDD
0x1800836ed  lea     rsi, WPP_GLOBAL_Control
0x1800836f4  lea     rbx, [r14+28h]
0x1800836f8  mov     eax, cs:dword_180173278
0x1800836fe  cmp     eax, r15d
0x180083701  jbe     loc_180083789
0x180083707  call    IkeGetTlsMmLuid
0x18008370c  mov     [rbp+70h+var_D8], rax
0x180083710  lea     rax, [rbp+70h+var_D8]
0x180083714  mov     [rbp+70h+var_A0], rax
0x180083718  mov     [rbp+70h+var_98], 8
0x180083720  call    IkeGetTlsPeerAddr
0x180083725  mov     rdx, rax
0x180083728  lea     rcx, [rbp+70h+var_90]
0x18008372c  call    _tlgCreate1Sz_wchar_t
0x180083731  lea     rax, [rbp+70h+var_E0]
0x180083735  mov     [rbp+70h+var_78], 0Bh
0x18008373d  mov     [rbp+70h+var_70], rax
0x180083741  lea     rcx, aAscFailed; "ASC failed"
0x180083748  mov     eax, [rbx]
0x18008374a  lea     rdx, word_180155A6A
0x180083751  mov     dword ptr [rbp+70h+var_E8], eax
0x180083754  lea     rax, [rbp+70h+var_E8]
0x180083758  mov     [rbp+70h+var_60], rax
0x18008375c  lea     rax, [rbp+70h+var_C0]
0x180083760  mov     [rbp+70h+var_80], rcx
0x180083764  lea     rcx, dword_180173278
0x18008376b  mov     [rsp+170h+phNewContext], rax
0x180083770  mov     [rsp+170h+TargetDataRep], 7
0x180083778  mov     dword ptr [rbp+70h+var_E0], r13d
0x18008377c  mov     [rbp+70h+var_68], r15
0x180083780  mov     [rbp+70h+var_58], r15
0x180083784  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180083789  test    r13d, r13d
0x18008378c  jz      loc_180083902
0x180083792  cmp     r13d, 90312h
0x180083799  jz      loc_180083902
  ... truncated ...
```
