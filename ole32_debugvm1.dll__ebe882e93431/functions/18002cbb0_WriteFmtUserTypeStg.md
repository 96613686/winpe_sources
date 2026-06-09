# WriteFmtUserTypeStg

- ea: `0x18002cbb0`
- end: `0x18002d0a1`
- name: `WriteFmtUserTypeStg`
- size: `1265`
- prototype: `HRESULT __stdcall(LPSTORAGE pstg, CLIPFORMAT cf, LPOLESTR lpszUserType)`
- caller_count: `9`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180048ef8`
- `0x18004b870`
- `0x18007e524`
- `0x1800845a0`
- `0x1800908d4`
- `0x1800a1474`
- `0x1800a3c28`
- `0x1800a42a0`
- `0x1800bd450`

## callees

- `0x180009de0`
- `0x18002cbb0`
- `0x18002d0a8`
- `0x18002d30c`
- `0x18002d370`
- `0x18003fc8c`
- `0x180052390`
- `0x180053014`
- `0x180085b34`
- `0x180085cfc`
- `0x180085d7c`
- `0x1800a47a8`
- `0x1800c4651`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18002cc66`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18002cc66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd63`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x18002cc4f`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x18002cd8b`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x18002cc4f`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x18002cd8b`

## pseudocode

```c
HRESULT __stdcall WriteFmtUserTypeStg(LPSTORAGE pstg, CLIPFORMAT cf, LPOLESTR lpszUserType)
{
  unsigned int v3; // esi
  HRESULT v6; // ebx
  const wchar_t *v7; // r8
  unsigned int m_cBuffer; // eax
  CompObjStmData *p_cod; // r14
  unsigned int i; // edi
  unsigned int v12; // edi
  unsigned int v13; // eax
  int *p_Src; // r15
  unsigned int j; // esi
  unsigned int v16; // eax
  int *v17; // r15
  unsigned int k; // esi
  unsigned int v19; // eax
  int *v20; // r14
  unsigned int v21; // esi
  bool v22; // zf
  unsigned int v23; // r14d
  unsigned int v24; // r14d
  unsigned int v25; // esi
  int v26; // [rsp+20h] [rbp-E0h] BYREF
  int Src; // [rsp+24h] [rbp-DCh] BYREF
  wchar_t *szProgID; // [rsp+30h] [rbp-D0h] BYREF
  CompObjStmData cod; // [rsp+40h] [rbp-C0h] BYREF
  _GUID clsid; // [rsp+A0h] [rbp-60h] BYREF
  CStmBufWrite StmWrite; // [rsp+B0h] [rbp-50h] BYREF

  v3 = cf;
  memset_0(&cod, 0, sizeof(cod));
  szProgID = 0;
  clsid = 0;
  cod.ttClipString = TT_ANSI;
  if ( !IsValidInterface(pstg) )
  {
    v6 = -2147024809;
    goto $errRtn_16;
  }
  v6 = ReadCompObjStm(pstg, &cod);
  if ( v6 != -2147024882 )
  {
    if ( !lpszUserType || (v6 = PutUNICODEUserType(&cod, lpszUserType), v6 >= 0) )
    {
      if ( ReadClassStg(pstg, &clsid) )
        clsid = GUID_NULL;
      if ( ProgIDFromCLSID(&clsid, &szProgID) >= 0 )
        PutUNICODEProgID(&cod, szProgID);
      if ( szProgID )
        CoTaskMemFree(szProgID);
      if ( (unsigned __int16)v3 >= 0xC000u )
      {
        cod.m_dwFormatTag = 400;
      }
      else
      {
        if ( !(_WORD)v3 )
        {
          *(_QWORD *)&cod.m_dwFormatTag = 0;
          goto LABEL_14;
        }
        cod.m_dwFormatTag = -1;
      }
      cod.m_ulFormatID = v3;
LABEL_14:
      v26 = 1907505652;
      StmWrite.m_pStm = 0;
      if ( !IsValidInterface(pstg) )
        goto LABEL_70;
      v6 = CStmBufWrite::CreateStream(&StmWrite, pstg, v7);
      if ( v6 >= 0 )
      {
        cod.m_hdr.m_dwFirstDword = -131071;
        cod.m_hdr.m_dwOSVer = 2563;
        cod.m_hdr.m_unused = -1;
        if ( ReadClassStg(pstg, &cod.m_hdr.m_clsClass) )
          cod.m_hdr.m_clsClass = GUID_NULL;
        m_cBuffer = StmWrite.m_cBuffer;
        p_cod = &cod;
        for ( i = 28; i; i -= v21 )
        {
          v21 = i;
          if ( m_cBuffer < i )
            v21 = m_cBuffer;
          memcpy_0(StmWrite.m_pBuffer, p_cod, v21);
          StmWrite.m_pBuffer += v21;
          v22 = StmWrite.m_cBuffer == v21;
          m_cBuffer = StmWrite.m_cBuffer - v21;
          StmWrite.m_cBuffer -= v21;
          if ( v22 )
          {
            v6 = CStmBufWrite::Flush(&StmWrite);
            if ( v6 < 0 )
              goto LABEL_16;
            m_cBuffer = StmWrite.m_cBuffer;
          }
          p_cod = (CompObjStmData *)((char *)p_cod + v21);
        }
        v6 = ANSIStrToStm(&StmWrite, cod.m_pszAUserType);
        if ( v6 >= 0 )
        {
          v12 = 4;
          if ( cod.ttClipString == TT_ANSI )
          {
            v6 = ClipfmtToStm(&StmWrite, cod.m_dwFormatTag, cod.m_ulFormatID, TT_ANSI);
            if ( v6 < 0 )
              goto LABEL_16;
          }
          else
          {
            v13 = StmWrite.m_cBuffer;
            p_Src = &Src;
            Src = 0;
            for ( j = 4; j; j -= v23 )
            {
              v23 = j;
              if ( v13 < j )
                v23 = v13;
              memcpy_0(StmWrite.m_pBuffer, p_Src, v23);
              StmWrite.m_pBuffer += v23;
              v22 = StmWrite.m_cBuffer == v23;
              v13 = StmWrite.m_cBuffer - v23;
              StmWrite.m_cBuffer -= v23;
              if ( v22 )
              {
                v6 = CStmBufWrite::Flush(&StmWrite);
                if ( v6 < 0 )
                  goto LABEL_16;
                v13 = StmWrite.m_cBuffer;
              }
              p_Src = (int *)((char *)p_Src + v23);
            }
          }
          v6 = ANSIStrToStm(&StmWrite, cod.m_pszAProgID);
          if ( v6 >= 0 )
          {
            v16 = StmWrite.m_cBuffer;
            v17 = &v26;
            for ( k = 4; k; k -= v24 )
            {
              v24 = k;
              if ( v16 < k )
                v24 = v16;
              memcpy_0(StmWrite.m_pBuffer, v17, v24);
              StmWrite.m_pBuffer += v24;
              v22 = StmWrite.m_cBuffer == v24;
              v16 = StmWrite.m_cBuffer - v24;
              StmWrite.m_cBuffer -= v24;
              if ( v22 )
              {
                v6 = CStmBufWrite::Flush(&StmWrite);
                if ( v6 < 0 )
                  goto LABEL_16;
                v16 = StmWrite.m_cBuffer;
              }
              v17 = (int *)((char *)v17 + v24);
            }
            v6 = WriteStringStream(&StmWrite, cod.m_pszOUserType);
            if ( v6 >= 0 )
            {
              if ( cod.ttClipString )
              {
                v19 = StmWrite.m_cBuffer;
                v20 = &v26;
                v26 = 0;
                while ( v12 )
                {
                  v25 = v12;
                  if ( v19 < v12 )
                    v25 = v19;
                  memcpy_0(StmWrite.m_pBuffer, v20, v25);
                  StmWrite.m_pBuffer += v25;
                  v22 = StmWrite.m_cBuffer == v25;
                  v19 = StmWrite.m_cBuffer - v25;
                  StmWrite.m_cBuffer -= v25;
                  if ( v22 )
                  {
                    v6 = CStmBufWrite::Flush(&StmWrite);
                    if ( v6 < 0 )
                      goto LABEL_16;
                    v19 = StmWrite.m_cBuffer;
                  }
                  v20 = (int *)((char *)v20 + v25);
                  v12 -= v25;
                }
              }
              else
              {
                v6 = ClipfmtToStm(&StmWrite, cod.m_dwFormatTag, cod.m_ulFormatID, TT_UNICODE);
                if ( v6 < 0 )
                  goto LABEL_16;
              }
              v6 = WriteStringStream(&StmWrite, cod.m_pszOProgID);
              if ( v6 >= 0 )
                v6 = CStmBufWrite::Flush(&StmWrite);
            }
          }
        }
      }
LABEL_16:
      if ( StmWrite.m_pStm )
        ((void (__fastcall *)(IStream *))StmWrite.m_pStm->lpVtbl->Release)(StmWrite.m_pStm);
      if ( v6 == -2147024882 )
        goto $errRtn_16;
LABEL_70:
      v6 = 0;
    }
  }
$errRtn_16:
  CoTaskMemFree(cod.m_pszOUserType);
  CoTaskMemFree(cod.m_pszOProgID);
  CoTaskMemFree(cod.m_pszAUserType);
  CoTaskMemFree(cod.m_pszAProgID);
  return v6;
}

```

## disassembly

```asm
0x18002cbb0  mov     [rsp-8+arg_8], rbx
0x18002cbb5  mov     [rsp-8+arg_18], rsi
0x18002cbba  push    rbp
0x18002cbbb  push    rdi
0x18002cbbc  push    r12
0x18002cbbe  push    r14
0x18002cbc0  push    r15
0x18002cbc2  lea     rbp, [rsp-0E0h]
0x18002cbca  sub     rsp, 1E0h
0x18002cbd1  mov     rax, cs:__security_cookie
0x18002cbd8  xor     rax, rsp
0x18002cbdb  mov     [rbp+100h+var_30], rax
0x18002cbe2  movzx   esi, dx
0x18002cbe5  mov     r14, szUserType
0x18002cbe8  xor     edx, edx; Val
0x18002cbea  mov     rdi, pstg
0x18002cbed  lea     pstg, [rsp+200h+cod]; void *
0x18002cbf2  lea     r8d, [rdx+58h]; Size
0x18002cbf6  call    memset_0
0x18002cbfb  xorps   xmm0, xmm0
0x18002cbfe  mov     [rsp+200h+szProgID], 0
0x18002cc07  mov     r12d, 1
0x18002cc0d  mov     pstg, rdi; pv
0x18002cc10  movups  xmmword ptr [rbp+100h+clsid.Data1], xmm0
0x18002cc14  mov     [rbp+100h+cod.ttClipString], r12d
0x18002cc18  call    IsValidInterface
0x18002cc1d  test    eax, eax
0x18002cc1f  jz      loc_18002CE80
0x18002cc25  lea     rdx, [rsp+200h+cod]; pcod
0x18002cc2a  mov     pstg, rdi; pstg
0x18002cc2d  call    ?ReadCompObjStm@@YAJPEAUIStorage@@PEAVCompObjStmData@@@Z; ReadCompObjStm(IStorage *,CompObjStmData *)
0x18002cc32  mov     ebx, eax
0x18002cc34  cmp     eax, 8007000Eh
0x18002cc39  jz      $errRtn_16
0x18002cc3f  test    r14, r14
0x18002cc42  jnz     loc_18002CE8A
0x18002cc48  lea     rdx, [rbp+100h+clsid]; pclsid
0x18002cc4c  mov     pstg, rdi; pStg
0x18002cc4f  call    cs:__imp_ReadClassStg
0x18002cc55  test    eax, eax
0x18002cc57  jnz     loc_18002CEA6
0x18002cc5d  lea     rdx, [rsp+200h+szProgID]; lplpszProgID
0x18002cc62  lea     pstg, [rbp+100h+clsid]; clsid
0x18002cc66  call    cs:__imp_ProgIDFromCLSID
0x18002cc6c  test    eax, eax
0x18002cc6e  jns     loc_18002CEB7
0x18002cc74  mov     pstg, [rsp+200h+szProgID]; pv
0x18002cc79  test    pstg, pstg
0x18002cc7c  jnz     loc_18002CD63
0x18002cc82  mov     eax, 0C000h
0x18002cc87  or      r14d, 0FFFFFFFFh
0x18002cc8b  cmp     si, ax
0x18002cc8e  jnb     loc_18002CD56
0x18002cc94  xor     eax, eax
0x18002cc96  cmp     ax, si
0x18002cc99  jz      loc_18002CECB
0x18002cc9f  mov     [rsp+200h+cod.m_dwFormatTag], r14d
0x18002cca4  mov     [rsp+200h+cod.m_ulFormatID], esi
0x18002cca8  mov     pstg, rdi; pv
0x18002ccab  mov     [rsp+200h+var_1E0], 71B239F4h
0x18002ccb3  mov     [rbp+100h+StmWrite.m_pStm], 0
0x18002ccbb  call    IsValidInterface
0x18002ccc0  test    eax, eax
0x18002ccc2  jz      loc_18002D09A
0x18002ccc8  mov     rdx, rdi; pstg
0x18002cccb  lea     pstg, [rbp+100h+StmWrite]; this
0x18002cccf  call    ?CreateStream@CStmBufWrite@@QEAAJPEAUIStorage@@PEBG@Z; CStmBufWrite::CreateStream(IStorage *,ushort const *)
0x18002ccd4  mov     ebx, eax
0x18002ccd6  test    eax, eax
0x18002ccd8  jns     loc_18002CD6E
0x18002ccde  mov     pstg, [rbp+100h+StmWrite.m_pStm]
0x18002cce2  test    pstg, pstg
0x18002cce5  jz      short loc_18002CCF3
0x18002cce7  mov     rax, [pstg]
0x18002ccea  mov     rax, [rax+10h]
0x18002ccee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccf3  cmp     ebx, 8007000Eh
0x18002ccf9  jnz     loc_18002D09A
0x18002ccff  mov     pstg, [rsp+200h+cod.m_pszOUserType]; pv
0x18002cd04  call    cs:__imp_CoTaskMemFree
0x18002cd0a  mov     pstg, [rsp+200h+cod.m_pszOProgID]; pv
0x18002cd0f  call    cs:__imp_CoTaskMemFree
0x18002cd15  mov     pstg, [rbp+100h+cod.m_pszAUserType]; pv
0x18002cd19  call    cs:__imp_CoTaskMemFree
0x18002cd1f  mov     pstg, [rbp+100h+cod.m_pszAProgID]; pv
0x18002cd23  call    cs:__imp_CoTaskMemFree
0x18002cd29  mov     eax, ebx
0x18002cd2b  mov     pstg, [rbp+100h+var_30]
0x18002cd32  xor     pstg, rsp; StackCookie
0x18002cd35  call    __security_check_cookie
0x18002cd3a  lea     r11, [rsp+200h+var_20]
0x18002cd42  mov     rbx, [r11+38h]
0x18002cd46  mov     rsi, [r11+48h]
0x18002cd4a  mov     rsp, r11
0x18002cd4d  pop     r15
0x18002cd4f  pop     r14
0x18002cd51  pop     r12
0x18002cd53  pop     rdi
0x18002cd54  pop     rbp
0x18002cd55  retn
0x18002cd56  mov     [rsp+200h+cod.m_dwFormatTag], 190h
0x18002cd5e  jmp     loc_18002CCA4
0x18002cd63  call    cs:__imp_CoTaskMemFree
0x18002cd69  jmp     loc_18002CC82
0x18002cd6e  lea     rdx, [rsp+200h+cod.m_hdr.m_clsClass]; pclsid
0x18002cd73  mov     [rsp+200h+cod.m_hdr.m_dwFirstDword], 0FFFE0001h
0x18002cd7b  mov     pstg, rdi; pStg
0x18002cd7e  mov     [rsp+200h+cod.m_hdr.m_dwOSVer], 0A03h
0x18002cd86  mov     [rsp+200h+cod.m_hdr.m_unused], r14d
0x18002cd8b  call    cs:__imp_ReadClassStg
0x18002cd91  test    eax, eax
0x18002cd93  jnz     loc_18002CED5
0x18002cd99  mov     eax, [rbp+100h+StmWrite.m_cBuffer]
0x18002cd9f  lea     r14, [rsp+200h+cod]
0x18002cda4  mov     edi, 1Ch
0x18002cda9  test    edi, edi
0x18002cdab  jnz     loc_18002CEF2
0x18002cdb1  mov     rdx, [rbp+100h+cod.m_pszAUserType]; str
0x18002cdb5  lea     pstg, [rbp+100h+StmWrite]; StmWrite
0x18002cdb9  call    ?ANSIStrToStm@@YAJAEAVCStmBufWrite@@PEBD@Z; ANSIStrToStm(CStmBufWrite &,char const *)
0x18002cdbe  mov     ebx, eax
0x18002cdc0  test    eax, eax
0x18002cdc2  js      loc_18002CCDE
0x18002cdc8  mov     edi, 4
0x18002cdcd  cmp     [rbp+100h+cod.ttClipString], r12d
0x18002cdd1  jz      loc_18002CF48
0x18002cdd7  mov     eax, [rbp+100h+StmWrite.m_cBuffer]
0x18002cddd  lea     r15, [rsp+200h+Src]
0x18002cde2  mov     [rsp+200h+Src], 0
0x18002cdea  mov     esi, edi
0x18002cdec  test    esi, esi
0x18002cdee  jnz     loc_18002CF6C
0x18002cdf4  mov     rdx, [rbp+100h+cod.m_pszAProgID]; str
0x18002cdf8  lea     pstg, [rbp+100h+StmWrite]; StmWrite
0x18002cdfc  call    ?ANSIStrToStm@@YAJAEAVCStmBufWrite@@PEBD@Z; ANSIStrToStm(CStmBufWrite &,char const *)
0x18002ce01  mov     ebx, eax
0x18002ce03  test    eax, eax
0x18002ce05  js      loc_18002CCDE
0x18002ce0b  mov     eax, [rbp+100h+StmWrite.m_cBuffer]
0x18002ce11  lea     r15, [rsp+200h+var_1E0]
0x18002ce16  mov     esi, edi
0x18002ce18  test    esi, esi
0x18002ce1a  jnz     loc_18002CFC6
0x18002ce20  mov     rdx, [rsp+200h+cod.m_pszOUserType]; psz
0x18002ce25  lea     pstg, [rbp+100h+StmWrite]; StmWrite
0x18002ce29  call    WriteStringStream
0x18002ce2e  mov     ebx, eax
0x18002ce30  test    eax, eax
0x18002ce32  js      loc_18002CCDE
0x18002ce38  cmp     [rbp+100h+cod.ttClipString], esi
0x18002ce3b  jz      loc_18002D020
0x18002ce41  mov     eax, [rbp+100h+StmWrite.m_cBuffer]
0x18002ce47  lea     r14, [rsp+200h+var_1E0]
0x18002ce4c  mov     [rsp+200h+var_1E0], esi
0x18002ce50  test    edi, edi
0x18002ce52  jnz     loc_18002D044
0x18002ce58  mov     rdx, [rsp+200h+cod.m_pszOProgID]; psz
0x18002ce5d  lea     pstg, [rbp+100h+StmWrite]; StmWrite
0x18002ce61  call    WriteStringStream
0x18002ce66  mov     ebx, eax
0x18002ce68  test    eax, eax
0x18002ce6a  js      loc_18002CCDE
0x18002ce70  lea     pstg, [rbp+100h+StmWrite]; this
0x18002ce74  call    ?Flush@CStmBufWrite@@QEAAJXZ; CStmBufWrite::Flush(void)
0x18002ce79  mov     ebx, eax
0x18002ce7b  jmp     loc_18002CCDE
0x18002ce80  mov     ebx, 80070057h
0x18002ce85  jmp     $errRtn_16
0x18002ce8a  mov     rdx, r14; szUser
0x18002ce8d  lea     pstg, [rsp+200h+cod]; pcod
0x18002ce92  call    ?PutUNICODEUserType@@YAJPEAVCompObjStmData@@PEAG@Z; PutUNICODEUserType(CompObjStmData *,ushort *)
0x18002ce97  mov     ebx, eax
0x18002ce99  test    eax, eax
0x18002ce9b  js      $errRtn_16
0x18002cea1  jmp     loc_18002CC48
0x18002cea6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002cead  movdqu  xmmword ptr [rbp+100h+clsid.Data1], xmm0
0x18002ceb2  jmp     loc_18002CC5D
0x18002ceb7  mov     rdx, [rsp+200h+szProgID]; szProg
0x18002cebc  lea     pstg, [rsp+200h+cod]; pcod
0x18002cec1  call    ?PutUNICODEProgID@@YAJPEAVCompObjStmData@@PEAG@Z; PutUNICODEProgID(CompObjStmData *,ushort *)
0x18002cec6  jmp     loc_18002CC74
0x18002cecb  mov     qword ptr [rsp+200h+cod.m_dwFormatTag], rax
0x18002ced0  jmp     loc_18002CCA8
0x18002ced5  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18002cedc  mov     qword ptr [rsp+200h+cod.m_hdr.m_clsClass.Data1], rax
0x18002cee1  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18002cee8  mov     qword ptr [rsp+200h+cod.m_hdr.m_clsClass.Data4], rax
0x18002ceed  jmp     loc_18002CD99
0x18002cef2  mov     pstg, [rbp+100h+StmWrite.m_pBuffer]; void *
0x18002cef9  cmp     eax, edi
0x18002cefb  mov     esi, edi
0x18002cefd  mov     rdx, r14; Src
0x18002cf00  cmovb   esi, eax
0x18002cf03  mov     r8d, esi; Size
0x18002cf06  mov     r15d, esi
0x18002cf09  call    memcpy_0
0x18002cf0e  mov     eax, [rbp+100h+StmWrite.m_cBuffer]
0x18002cf14  add     [rbp+100h+StmWrite.m_pBuffer], r15
0x18002cf1b  sub     eax, esi
0x18002cf1d  mov     [rbp+100h+StmWrite.m_cBuffer], eax
0x18002cf23  jnz     short loc_18002CF3E
0x18002cf25  lea     pstg, [rbp+100h+StmWrite]; this
0x18002cf29  call    ?Flush@CStmBufWrite@@QEAAJXZ; CStmBufWrite::Flush(void)
0x18002cf2e  mov     ebx, eax
0x18002cf30  test    eax, eax
0x18002cf32  js      loc_18002CCDE
0x18002cf38  mov     eax, [rbp+100h+StmWrite.m_cBuffer]
0x18002cf3e  add     r14, r15
0x18002cf41  sub     edi, esi
0x18002cf43  jmp     loc_18002CDA9
0x18002cf48  mov     r8d, [rsp+200h+cod.m_ulFormatID]; ulFormatID
0x18002cf4d  lea     pstg, [rbp+100h+StmWrite]; StmWrite
0x18002cf51  mov     edx, [rsp+200h+cod.m_dwFormatTag]; dwFormatTag
0x18002cf55  mov     r9d, r12d; ttText
0x18002cf58  call    ?ClipfmtToStm@@YAJAEAVCStmBufWrite@@KKW4TXTTYPE@@@Z; ClipfmtToStm(CStmBufWrite &,ulong,ulong,TXTTYPE)
0x18002cf5d  mov     ebx, eax
0x18002cf5f  test    eax, eax
0x18002cf61  js      loc_18002CCDE
0x18002cf67  jmp     loc_18002CDF4
0x18002cf6c  mov     pstg, [rbp+100h+StmWrite.m_pBuffer]; void *
0x18002cf73  cmp     eax, esi
0x18002cf75  mov     r14d, esi
0x18002cf78  mov     rdx, r15; Src
0x18002cf7b  cmovb   r14d, eax
0x18002cf7f  mov     r8d, r14d; Size
0x18002cf82  mov     r12d, r14d
0x18002cf85  call    memcpy_0
0x18002cf8a  mov     eax, [rbp+100h+StmWrite.m_cBuffer]
0x18002cf90  add     [rbp+100h+StmWrite.m_pBuffer], r12
0x18002cf97  sub     eax, r14d
0x18002cf9a  mov     [rbp+100h+StmWrite.m_cBuffer], eax
0x18002cfa0  jnz     short loc_18002CFBB
0x18002cfa2  lea     pstg, [rbp+100h+StmWrite]; this
0x18002cfa6  call    ?Flush@CStmBufWrite@@QEAAJXZ; CStmBufWrite::Flush(void)
0x18002cfab  mov     ebx, eax
0x18002cfad  test    eax, eax
0x18002cfaf  js      loc_18002CCDE
0x18002cfb5  mov     eax, [rbp+100h+StmWrite.m_cBuffer]
0x18002cfbb  add     r15, r12
0x18002cfbe  sub     esi, r14d
0x18002cfc1  jmp     loc_18002CDEC
0x18002cfc6  mov     pstg, [rbp+100h+StmWrite.m_pBuffer]; void *
0x18002cfcd  cmp     eax, esi
0x18002cfcf  mov     r14d, esi
0x18002cfd2  mov     rdx, r15; Src
0x18002cfd5  cmovb   r14d, eax
0x18002cfd9  mov     r8d, r14d; Size
0x18002cfdc  mov     r12d, r14d
0x18002cfdf  call    memcpy_0
0x18002cfe4  mov     eax, [rbp+100h+StmWrite.m_cBuffer]
0x18002cfea  add     [rbp+100h+StmWrite.m_pBuffer], r12
0x18002cff1  sub     eax, r14d
0x18002cff4  mov     [rbp+100h+StmWrite.m_cBuffer], eax
0x18002cffa  jnz     short loc_18002D015
0x18002cffc  lea     pstg, [rbp+100h+StmWrite]; this
0x18002d000  call    ?Flush@CStmBufWrite@@QEAAJXZ; CStmBufWrite::Flush(void)
0x18002d005  mov     ebx, eax
0x18002d007  test    eax, eax
0x18002d009  js      loc_18002CCDE
0x18002d00f  mov     eax, [rbp+100h+StmWrite.m_cBuffer]
0x18002d015  add     r15, r12
0x18002d018  sub     esi, r14d
0x18002d01b  jmp     loc_18002CE18
0x18002d020  mov     r8d, [rsp+200h+cod.m_ulFormatID]; ulFormatID
0x18002d025  lea     pstg, [rbp+100h+StmWrite]; StmWrite
0x18002d029  mov     edx, [rsp+200h+cod.m_dwFormatTag]; dwFormatTag
0x18002d02d  xor     r9d, r9d; ttText
0x18002d030  call    ?ClipfmtToStm@@YAJAEAVCStmBufWrite@@KKW4TXTTYPE@@@Z; ClipfmtToStm(CStmBufWrite &,ulong,ulong,TXTTYPE)
0x18002d035  mov     ebx, eax
0x18002d037  test    eax, eax
0x18002d039  js      loc_18002CCDE
0x18002d03f  jmp     loc_18002CE58
0x18002d044  mov     pstg, [rbp+100h+StmWrite.m_pBuffer]; void *
0x18002d04b  cmp     eax, edi
0x18002d04d  mov     esi, edi
0x18002d04f  mov     rdx, r14; Src
0x18002d052  cmovb   esi, eax
0x18002d055  mov     r8d, esi; Size
0x18002d058  mov     r15d, esi
0x18002d05b  call    memcpy_0
0x18002d060  mov     eax, [rbp+100h+StmWrite.m_cBuffer]
0x18002d066  add     [rbp+100h+StmWrite.m_pBuffer], r15
0x18002d06d  sub     eax, esi
0x18002d06f  mov     [rbp+100h+StmWrite.m_cBuffer], eax
0x18002d075  jnz     short loc_18002D090
0x18002d077  lea     pstg, [rbp+100h+StmWrite]; this
0x18002d07b  call    ?Flush@CStmBufWrite@@QEAAJXZ; CStmBufWrite::Flush(void)
0x18002d080  mov     ebx, eax
0x18002d082  test    eax, eax
0x18002d084  js      loc_18002CCDE
0x18002d08a  mov     eax, [rbp+100h+StmWrite.m_cBuffer]
0x18002d090  add     r14, r15
0x18002d093  sub     edi, esi
0x18002d095  jmp     loc_18002CE50
0x18002d09a  xor     ebx, ebx
0x18002d09c  jmp     $errRtn_16
```
