# WriteFmtUserTypeStg

- ea: `0x1800304d0`
- end: `0x18003099d`
- name: `WriteFmtUserTypeStg`
- size: `1229`
- prototype: `HRESULT __stdcall(LPSTORAGE pstg, CLIPFORMAT cf, LPOLESTR lpszUserType)`
- caller_count: `9`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180077928`
- `0x18007e9c0`
- `0x18007ed20`
- `0x18008cad4`
- `0x1800a758c`
- `0x1800aa690`
- `0x1800aad58`
- `0x1800aafe0`
- `0x1800c61c0`

## callees

- `0x180008280`
- `0x1800304d0`
- `0x1800309a4`
- `0x180030c08`
- `0x180030c60`
- `0x180042bcc`
- `0x1800451bc`
- `0x180046460`
- `0x180047484`
- `0x180080210`
- `0x1800803e4`
- `0x180080470`
- `0x1800ab474`
- `0x1800ce967`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18003058b`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18003058b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030666`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030666`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x18003056e`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x180030694`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x18003056e`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x180030694`

## pseudocode

```c
HRESULT __stdcall WriteFmtUserTypeStg(LPSTORAGE pstg, CLIPFORMAT cf, LPOLESTR lpszUserType)
{
  unsigned int v3; // esi
  HRESULT v6; // ebx
  const wchar_t *v7; // r8
  unsigned int v9; // esi
  CompObjStmData *p_cod; // r14
  unsigned int m_cBuffer; // eax
  unsigned int v12; // esi
  int *p_Src; // r15
  unsigned int v14; // r14d
  unsigned int v15; // eax
  unsigned int v16; // r14d
  int *v17; // r15
  unsigned int v18; // eax
  int *v19; // r14
  unsigned int v20; // eax
  unsigned int v21; // edi
  bool v22; // zf
  unsigned int v23; // edi
  unsigned int v24; // edi
  unsigned int v25; // edi
  int v26; // [rsp+20h] [rbp-E0h] BYREF
  int Src; // [rsp+24h] [rbp-DCh] BYREF
  wchar_t *szProgID; // [rsp+28h] [rbp-D8h] BYREF
  CompObjStmData cod; // [rsp+30h] [rbp-D0h] BYREF
  _GUID clsid; // [rsp+90h] [rbp-70h] BYREF
  CStmBufWrite StmWrite; // [rsp+A0h] [rbp-60h] BYREF

  v3 = cf;
  memset_0(&cod, 0, sizeof(cod));
  cod.ttClipString = TT_ANSI;
  szProgID = 0;
  clsid = 0;
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
            v9 = 28;
            p_cod = &cod;
LABEL_24:
            m_cBuffer = StmWrite.m_cBuffer;
            while ( v9 )
            {
              v21 = v9;
              if ( m_cBuffer < v9 )
                v21 = m_cBuffer;
              memcpy_0(StmWrite.m_pBuffer, p_cod, v21);
              p_cod = (CompObjStmData *)((char *)p_cod + v21);
              StmWrite.m_pBuffer += v21;
              v9 -= v21;
              v22 = StmWrite.m_cBuffer == v21;
              m_cBuffer = StmWrite.m_cBuffer - v21;
              StmWrite.m_cBuffer -= v21;
              if ( v22 )
              {
                v6 = CStmBufWrite::Flush(&StmWrite);
                if ( v6 < 0 )
                  goto LABEL_16;
                goto LABEL_24;
              }
            }
            v6 = ANSIStrToStm(&StmWrite, cod.m_pszAUserType);
            if ( v6 < 0 )
              goto LABEL_16;
            v12 = 4;
            if ( cod.ttClipString == TT_ANSI )
            {
              v6 = ClipfmtToStm(&StmWrite, cod.m_dwFormatTag, cod.m_ulFormatID, TT_ANSI);
              if ( v6 < 0 )
                goto LABEL_16;
            }
            else
            {
              Src = 0;
              p_Src = &Src;
              v14 = 4;
LABEL_29:
              v15 = StmWrite.m_cBuffer;
              while ( v14 )
              {
                v23 = v14;
                if ( v15 < v14 )
                  v23 = v15;
                memcpy_0(StmWrite.m_pBuffer, p_Src, v23);
                p_Src = (int *)((char *)p_Src + v23);
                StmWrite.m_pBuffer += v23;
                v14 -= v23;
                v22 = StmWrite.m_cBuffer == v23;
                v15 = StmWrite.m_cBuffer - v23;
                StmWrite.m_cBuffer -= v23;
                if ( v22 )
                {
                  v6 = CStmBufWrite::Flush(&StmWrite);
                  if ( v6 < 0 )
                    goto LABEL_16;
                  goto LABEL_29;
                }
              }
            }
            v6 = ANSIStrToStm(&StmWrite, cod.m_pszAProgID);
            if ( v6 < 0 )
              goto LABEL_16;
            v16 = 4;
            v17 = &v26;
LABEL_33:
            v18 = StmWrite.m_cBuffer;
            while ( v16 )
            {
              v24 = v16;
              if ( v18 < v16 )
                v24 = v18;
              memcpy_0(StmWrite.m_pBuffer, v17, v24);
              v17 = (int *)((char *)v17 + v24);
              StmWrite.m_pBuffer += v24;
              v16 -= v24;
              v22 = StmWrite.m_cBuffer == v24;
              v18 = StmWrite.m_cBuffer - v24;
              StmWrite.m_cBuffer -= v24;
              if ( v22 )
              {
                v6 = CStmBufWrite::Flush(&StmWrite);
                if ( v6 < 0 )
                  goto LABEL_16;
                goto LABEL_33;
              }
            }
            v6 = WriteStringStream(&StmWrite, cod.m_pszOUserType);
            if ( v6 < 0 )
              goto LABEL_16;
            if ( cod.ttClipString )
            {
              v26 = 0;
              v19 = &v26;
LABEL_38:
              v20 = StmWrite.m_cBuffer;
              while ( v12 )
              {
                v25 = v12;
                if ( v20 < v12 )
                  v25 = v20;
                memcpy_0(StmWrite.m_pBuffer, v19, v25);
                v19 = (int *)((char *)v19 + v25);
                StmWrite.m_pBuffer += v25;
                v12 -= v25;
                v22 = StmWrite.m_cBuffer == v25;
                v20 = StmWrite.m_cBuffer - v25;
                StmWrite.m_cBuffer -= v25;
                if ( v22 )
                {
                  v6 = CStmBufWrite::Flush(&StmWrite);
                  if ( v6 < 0 )
                    goto LABEL_16;
                  goto LABEL_38;
                }
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
LABEL_16:
          if ( StmWrite.m_pStm )
            ((void (__fastcall *)(IStream *))StmWrite.m_pStm->lpVtbl->Release)(StmWrite.m_pStm);
          if ( v6 == -2147024882 )
            goto $errRtn_16;
LABEL_70:
          v6 = 0;
          goto $errRtn_16;
        }
        cod.m_dwFormatTag = -1;
      }
      cod.m_ulFormatID = v3;
      goto LABEL_14;
    }
  }
$errRtn_16:
  CompObjStmData::~CompObjStmData(&cod);
  return v6;
}

```

## disassembly

```asm
0x1800304d0  mov     [rsp-8+arg_8], rbx
0x1800304d5  mov     [rsp-8+arg_18], rsi
0x1800304da  push    rbp
0x1800304db  push    rdi
0x1800304dc  push    r12
0x1800304de  push    r14
0x1800304e0  push    r15
0x1800304e2  lea     rbp, [rsp-0D0h]
0x1800304ea  sub     rsp, 1D0h
0x1800304f1  mov     rax, cs:__security_cookie
0x1800304f8  xor     rax, rsp
0x1800304fb  mov     [rbp+0F0h+var_30], rax
0x180030502  movzx   esi, dx
0x180030505  mov     r14, szUserType
0x180030508  xor     edx, edx; Val
0x18003050a  mov     rdi, pstg
0x18003050d  lea     pstg, [rsp+1F0h+cod]; void *
0x180030512  lea     r8d, [rdx+58h]; Size
0x180030516  call    memset_0
0x18003051b  xorps   xmm0, xmm0
0x18003051e  mov     r15d, 1
0x180030524  xor     r12d, r12d
0x180030527  mov     [rbp+0F0h+cod.ttClipString], r15d
0x18003052b  mov     pstg, rdi; pv
0x18003052e  mov     [rsp+1F0h+szProgID], r12
0x180030533  movups  xmmword ptr [rbp+0F0h+clsid.Data1], xmm0
0x180030537  call    IsValidInterface
0x18003053c  test    eax, eax
0x18003053e  jz      loc_180030794
0x180030544  lea     rdx, [rsp+1F0h+cod]; pcod
0x180030549  mov     pstg, rdi; pstg
0x18003054c  call    ?ReadCompObjStm@@YAJPEAUIStorage@@PEAVCompObjStmData@@@Z; ReadCompObjStm(IStorage *,CompObjStmData *)
0x180030551  mov     ebx, eax
0x180030553  cmp     eax, 8007000Eh
0x180030558  jz      $errRtn_16
0x18003055e  test    r14, r14
0x180030561  jnz     loc_18003079E
0x180030567  lea     rdx, [rbp+0F0h+clsid]; pclsid
0x18003056b  mov     pstg, rdi; pStg
0x18003056e  call    cs:__imp_ReadClassStg
0x180030575  nop     dword ptr [rax+rax+00h]
0x18003057a  test    eax, eax
0x18003057c  jnz     loc_1800307BA
0x180030582  lea     rdx, [rsp+1F0h+szProgID]; lplpszProgID
0x180030587  lea     pstg, [rbp+0F0h+clsid]; clsid
0x18003058b  call    cs:__imp_ProgIDFromCLSID
0x180030592  nop     dword ptr [rax+rax+00h]
0x180030597  test    eax, eax
0x180030599  jns     loc_1800307CB
0x18003059f  mov     pstg, [rsp+1F0h+szProgID]; pv
0x1800305a4  test    pstg, pstg
0x1800305a7  jnz     loc_180030666
0x1800305ad  mov     eax, 0C000h
0x1800305b2  or      r14d, 0FFFFFFFFh
0x1800305b6  cmp     si, ax
0x1800305b9  jnb     loc_180030659
0x1800305bf  cmp     r12w, si
0x1800305c3  jz      loc_1800307DF
0x1800305c9  mov     [rsp+1F0h+cod.m_dwFormatTag], r14d
0x1800305ce  mov     [rsp+1F0h+cod.m_ulFormatID], esi
0x1800305d2  mov     pstg, rdi; pv
0x1800305d5  mov     [rsp+1F0h+var_1D0], 71B239F4h
0x1800305dd  mov     [rbp+0F0h+StmWrite.m_pStm], r12
0x1800305e1  call    IsValidInterface
0x1800305e6  test    eax, eax
0x1800305e8  jz      loc_180030995
0x1800305ee  mov     rdx, rdi; pstg
0x1800305f1  lea     pstg, [rbp+0F0h+StmWrite]; this
0x1800305f5  call    ?CreateStream@CStmBufWrite@@QEAAJPEAUIStorage@@PEBG@Z; CStmBufWrite::CreateStream(IStorage *,ushort const *)
0x1800305fa  mov     ebx, eax
0x1800305fc  test    eax, eax
0x1800305fe  jns     short loc_180030677
0x180030600  mov     pstg, [rbp+0F0h+StmWrite.m_pStm]
0x180030604  test    pstg, pstg
0x180030607  jz      short loc_180030615
0x180030609  mov     rax, [pstg]
0x18003060c  mov     rax, [rax+10h]
0x180030610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030615  cmp     ebx, 8007000Eh
0x18003061b  jnz     loc_180030995
0x180030621  lea     pstg, [rsp+1F0h+cod]; this
0x180030626  call    ??1CompObjStmData@@QEAA@XZ; CompObjStmData::~CompObjStmData(void)
0x18003062b  mov     eax, ebx
0x18003062d  mov     pstg, [rbp+0F0h+var_30]
0x180030634  xor     pstg, rsp; StackCookie
0x180030637  call    __security_check_cookie
0x18003063c  lea     r11, [rsp+1F0h+var_20]
0x180030644  mov     rbx, [r11+38h]
0x180030648  mov     rsi, [r11+48h]
0x18003064c  mov     rsp, r11
0x18003064f  pop     r15
0x180030651  pop     r14
0x180030653  pop     r12
0x180030655  pop     rdi
0x180030656  pop     rbp
0x180030657  retn
0x180030659  mov     [rsp+1F0h+cod.m_dwFormatTag], 190h
0x180030661  jmp     loc_1800305CE
0x180030666  call    cs:__imp_CoTaskMemFree
0x18003066d  nop     dword ptr [rax+rax+00h]
0x180030672  jmp     loc_1800305AD
0x180030677  lea     rdx, [rsp+1F0h+cod.m_hdr.m_clsClass]; pclsid
0x18003067c  mov     [rsp+1F0h+cod.m_hdr.m_dwFirstDword], 0FFFE0001h
0x180030684  mov     pstg, rdi; pStg
0x180030687  mov     [rsp+1F0h+cod.m_hdr.m_dwOSVer], 0A03h
0x18003068f  mov     [rsp+1F0h+cod.m_hdr.m_unused], r14d
0x180030694  call    cs:__imp_ReadClassStg
0x18003069b  nop     dword ptr [rax+rax+00h]
0x1800306a0  test    eax, eax
0x1800306a2  jnz     loc_1800307E9
0x1800306a8  mov     esi, 1Ch
0x1800306ad  lea     r14, [rsp+1F0h+cod]
0x1800306b2  mov     eax, [rbp+0F0h+StmWrite.m_cBuffer]
0x1800306b8  test    esi, esi
0x1800306ba  jnz     loc_1800307FB
0x1800306c0  mov     rdx, [rsp+1F0h+cod.m_pszAUserType]; str
0x1800306c5  lea     pstg, [rbp+0F0h+StmWrite]; StmWrite
0x1800306c9  call    ?ANSIStrToStm@@YAJAEAVCStmBufWrite@@PEBD@Z; ANSIStrToStm(CStmBufWrite &,char const *)
0x1800306ce  mov     ebx, eax
0x1800306d0  test    eax, eax
0x1800306d2  js      loc_180030600
0x1800306d8  mov     esi, 4
0x1800306dd  cmp     [rbp+0F0h+cod.ttClipString], r15d
0x1800306e1  jz      loc_18003084E
0x1800306e7  mov     [rsp+1F0h+Src], r12d
0x1800306ec  lea     r15, [rsp+1F0h+Src]
0x1800306f1  mov     r14d, esi
0x1800306f4  mov     eax, [rbp+0F0h+StmWrite.m_cBuffer]
0x1800306fa  test    r14d, r14d
0x1800306fd  jnz     loc_180030872
0x180030703  mov     rdx, [rsp+1F0h+cod.m_pszAProgID]; str
0x180030708  lea     pstg, [rbp+0F0h+StmWrite]; StmWrite
0x18003070c  call    ?ANSIStrToStm@@YAJAEAVCStmBufWrite@@PEBD@Z; ANSIStrToStm(CStmBufWrite &,char const *)
0x180030711  mov     ebx, eax
0x180030713  test    eax, eax
0x180030715  js      loc_180030600
0x18003071b  mov     r14d, esi
0x18003071e  lea     r15, [rsp+1F0h+var_1D0]
0x180030723  mov     eax, [rbp+0F0h+StmWrite.m_cBuffer]
0x180030729  test    r14d, r14d
0x18003072c  jnz     loc_1800308C8
0x180030732  mov     rdx, [rsp+1F0h+cod.m_pszOUserType]; psz
0x180030737  lea     pstg, [rbp+0F0h+StmWrite]; StmWrite
0x18003073b  call    WriteStringStream
0x180030740  mov     ebx, eax
0x180030742  test    eax, eax
0x180030744  js      loc_180030600
0x18003074a  cmp     [rbp+0F0h+cod.ttClipString], r12d
0x18003074e  jz      loc_18003091E
0x180030754  mov     [rsp+1F0h+var_1D0], r12d
0x180030759  lea     r14, [rsp+1F0h+var_1D0]
0x18003075e  mov     eax, [rbp+0F0h+StmWrite.m_cBuffer]
0x180030764  test    esi, esi
0x180030766  jnz     loc_180030942
0x18003076c  mov     rdx, [rsp+1F0h+cod.m_pszOProgID]; psz
0x180030771  lea     pstg, [rbp+0F0h+StmWrite]; StmWrite
0x180030775  call    WriteStringStream
0x18003077a  mov     ebx, eax
0x18003077c  test    eax, eax
0x18003077e  js      loc_180030600
0x180030784  lea     pstg, [rbp+0F0h+StmWrite]; this
0x180030788  call    ?Flush@CStmBufWrite@@QEAAJXZ; CStmBufWrite::Flush(void)
0x18003078d  mov     ebx, eax
0x18003078f  jmp     loc_180030600
0x180030794  mov     ebx, 80070057h
0x180030799  jmp     $errRtn_16
0x18003079e  mov     rdx, r14; szUser
0x1800307a1  lea     pstg, [rsp+1F0h+cod]; pcod
0x1800307a6  call    ?PutUNICODEUserType@@YAJPEAVCompObjStmData@@PEAG@Z; PutUNICODEUserType(CompObjStmData *,ushort *)
0x1800307ab  mov     ebx, eax
0x1800307ad  test    eax, eax
0x1800307af  js      $errRtn_16
0x1800307b5  jmp     loc_180030567
0x1800307ba  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800307c1  movdqu  xmmword ptr [rbp+0F0h+clsid.Data1], xmm0
0x1800307c6  jmp     loc_180030582
0x1800307cb  mov     rdx, [rsp+1F0h+szProgID]; szProg
0x1800307d0  lea     pstg, [rsp+1F0h+cod]; pcod
0x1800307d5  call    ?PutUNICODEProgID@@YAJPEAVCompObjStmData@@PEAG@Z; PutUNICODEProgID(CompObjStmData *,ushort *)
0x1800307da  jmp     loc_18003059F
0x1800307df  mov     qword ptr [rsp+1F0h+cod.m_dwFormatTag], r12
0x1800307e4  jmp     loc_1800305D2
0x1800307e9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800307f0  movdqu  xmmword ptr [rsp+1F0h+cod.m_hdr.m_clsClass.Data1], xmm0
0x1800307f6  jmp     loc_1800306A8
0x1800307fb  mov     pstg, [rbp+0F0h+StmWrite.m_pBuffer]; void *
0x180030802  cmp     eax, esi
0x180030804  mov     edi, esi
0x180030806  mov     rdx, r14; Src
0x180030809  cmovb   edi, eax
0x18003080c  mov     r8d, edi; Size
0x18003080f  mov     ebx, edi
0x180030811  call    memcpy_0
0x180030816  mov     eax, [rbp+0F0h+StmWrite.m_cBuffer]
0x18003081c  add     r14, rbx
0x18003081f  add     [rbp+0F0h+StmWrite.m_pBuffer], rbx
0x180030826  sub     esi, edi
0x180030828  sub     eax, edi
0x18003082a  mov     [rbp+0F0h+StmWrite.m_cBuffer], eax
0x180030830  jnz     loc_1800306B8
0x180030836  lea     pstg, [rbp+0F0h+StmWrite]; this
0x18003083a  call    ?Flush@CStmBufWrite@@QEAAJXZ; CStmBufWrite::Flush(void)
0x18003083f  mov     ebx, eax
0x180030841  test    eax, eax
0x180030843  js      loc_180030600
0x180030849  jmp     loc_1800306B2
0x18003084e  mov     r8d, [rsp+1F0h+cod.m_ulFormatID]; ulFormatID
0x180030853  lea     pstg, [rbp+0F0h+StmWrite]; StmWrite
0x180030857  mov     edx, [rsp+1F0h+cod.m_dwFormatTag]; dwFormatTag
0x18003085b  mov     r9d, r15d; ttText
0x18003085e  call    ?ClipfmtToStm@@YAJAEAVCStmBufWrite@@KKW4TXTTYPE@@@Z; ClipfmtToStm(CStmBufWrite &,ulong,ulong,TXTTYPE)
0x180030863  mov     ebx, eax
0x180030865  test    eax, eax
0x180030867  js      loc_180030600
0x18003086d  jmp     loc_180030703
0x180030872  mov     pstg, [rbp+0F0h+StmWrite.m_pBuffer]; void *
0x180030879  cmp     eax, r14d
0x18003087c  mov     edi, r14d
0x18003087f  mov     rdx, r15; Src
0x180030882  cmovb   edi, eax
0x180030885  mov     r8d, edi; Size
0x180030888  mov     ebx, edi
0x18003088a  call    memcpy_0
0x18003088f  mov     eax, [rbp+0F0h+StmWrite.m_cBuffer]
0x180030895  add     r15, rbx
0x180030898  add     [rbp+0F0h+StmWrite.m_pBuffer], rbx
0x18003089f  sub     r14d, edi
0x1800308a2  sub     eax, edi
0x1800308a4  mov     [rbp+0F0h+StmWrite.m_cBuffer], eax
0x1800308aa  jnz     loc_1800306FA
0x1800308b0  lea     pstg, [rbp+0F0h+StmWrite]; this
0x1800308b4  call    ?Flush@CStmBufWrite@@QEAAJXZ; CStmBufWrite::Flush(void)
0x1800308b9  mov     ebx, eax
0x1800308bb  test    eax, eax
0x1800308bd  js      loc_180030600
0x1800308c3  jmp     loc_1800306F4
0x1800308c8  mov     pstg, [rbp+0F0h+StmWrite.m_pBuffer]; void *
0x1800308cf  cmp     eax, r14d
0x1800308d2  mov     edi, r14d
0x1800308d5  mov     rdx, r15; Src
0x1800308d8  cmovb   edi, eax
0x1800308db  mov     r8d, edi; Size
0x1800308de  mov     ebx, edi
0x1800308e0  call    memcpy_0
0x1800308e5  mov     eax, [rbp+0F0h+StmWrite.m_cBuffer]
0x1800308eb  add     r15, rbx
0x1800308ee  add     [rbp+0F0h+StmWrite.m_pBuffer], rbx
0x1800308f5  sub     r14d, edi
0x1800308f8  sub     eax, edi
0x1800308fa  mov     [rbp+0F0h+StmWrite.m_cBuffer], eax
0x180030900  jnz     loc_180030729
0x180030906  lea     pstg, [rbp+0F0h+StmWrite]; this
0x18003090a  call    ?Flush@CStmBufWrite@@QEAAJXZ; CStmBufWrite::Flush(void)
0x18003090f  mov     ebx, eax
0x180030911  test    eax, eax
0x180030913  js      loc_180030600
0x180030919  jmp     loc_180030723
0x18003091e  mov     r8d, [rsp+1F0h+cod.m_ulFormatID]; ulFormatID
0x180030923  lea     pstg, [rbp+0F0h+StmWrite]; StmWrite
0x180030927  mov     edx, [rsp+1F0h+cod.m_dwFormatTag]; dwFormatTag
0x18003092b  xor     r9d, r9d; ttText
0x18003092e  call    ?ClipfmtToStm@@YAJAEAVCStmBufWrite@@KKW4TXTTYPE@@@Z; ClipfmtToStm(CStmBufWrite &,ulong,ulong,TXTTYPE)
0x180030933  mov     ebx, eax
0x180030935  test    eax, eax
0x180030937  js      loc_180030600
0x18003093d  jmp     loc_18003076C
0x180030942  mov     pstg, [rbp+0F0h+StmWrite.m_pBuffer]; void *
0x180030949  cmp     eax, esi
0x18003094b  mov     edi, esi
0x18003094d  mov     rdx, r14; Src
0x180030950  cmovb   edi, eax
0x180030953  mov     r8d, edi; Size
0x180030956  mov     ebx, edi
0x180030958  call    memcpy_0
0x18003095d  mov     eax, [rbp+0F0h+StmWrite.m_cBuffer]
0x180030963  add     r14, rbx
0x180030966  add     [rbp+0F0h+StmWrite.m_pBuffer], rbx
0x18003096d  sub     esi, edi
0x18003096f  sub     eax, edi
0x180030971  mov     [rbp+0F0h+StmWrite.m_cBuffer], eax
0x180030977  jnz     loc_180030764
0x18003097d  lea     pstg, [rbp+0F0h+StmWrite]; this
0x180030981  call    ?Flush@CStmBufWrite@@QEAAJXZ; CStmBufWrite::Flush(void)
0x180030986  mov     ebx, eax
0x180030988  test    eax, eax
0x18003098a  js      loc_180030600
0x180030990  jmp     loc_18003075E
0x180030995  mov     ebx, r12d
0x180030998  jmp     $errRtn_16
```
