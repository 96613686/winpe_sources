# URLMONRequest::GetBindInfo(ulong *,_tagBINDINFO *)

- ea: `0x180053cd4`
- end: `0x1800541c8`
- name: `?GetBindInfo@URLMONRequest@@IEAAJPEAKPEAU_tagBINDINFO@@@Z`
- size: `1268`
- prototype: `HRESULT __fastcall(URLMONRequest *this, unsigned int *grfBINDF, _tagBINDINFO *pbindinfo)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800539c4`
- `0x1801596b0`

## callees

- `0x180015a80`
- `0x180053cd4`
- `0x180054310`
- `0x18005d2c4`
- `0x1800a1b58`
- `0x1800cc6c0`
- `0x1800cd3e4`
- `0x180155910`
- `0x18015a324`
- `0x180189008`
- `0x180189118`
- `0x18018a390`
- `0x18018af54`
- `0x18018b178`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053fb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053fb5`

## pseudocode

```c
__int64 __fastcall URLMONRequest::GetBindInfo(URLMONRequest *this, unsigned int *grfBINDF, _GUID *pbindinfo)
{
  int v6; // r15d
  unsigned int Data1; // ebx
  unsigned __int16 v8; // dx
  unsigned __int16 v9; // cx
  const _GUID *v10; // r8
  const char *v11; // r9
  unsigned __int16 v12; // dx
  unsigned __int16 v13; // cx
  const _GUID *v14; // r8
  const wchar_t *v15; // r10
  const wchar_t *v16; // r10
  const wchar_t *v17; // r10
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // r9
  CachingStreamForExternal *v20; // rbx
  wchar_t *v21; // rax
  HBITMAP__ **p_pstrmRequest; // rbx
  HBITMAP__ *v24; // rcx
  int v25; // eax
  IStream *v26; // rcx
  CachingStreamForExternal *pcs; // [rsp+60h] [rbp-49h] BYREF
  _LARGE_INTEGER liZero; // [rsp+68h] [rbp-41h]
  tagSTATSTG sg; // [rsp+70h] [rbp-39h] BYREF

  if ( (xmmword_1801FAD20 & 8) != 0 )
    WPP_SF_qqDq((unsigned __int16)this, (unsigned __int16)grfBINDF, pbindinfo, this, grfBINDF, *grfBINDF, pbindinfo);
  this->Lock(this);
  if ( !(__int64)g_pfnEntry() )
  {
    v6 = -2147467259;
    goto $CleanUp_35;
  }
  *grfBINDF = 0;
  Data1 = pbindinfo->Data1;
  v6 = 0;
  memset_0(pbindinfo, 0, pbindinfo->Data1);
  pbindinfo->Data1 = Data1;
  if ( !this->_fMta )
  {
    *grfBINDF = 0x100000;
    if ( (xmmword_1801FAD20 & 8) != 0 )
      WPP_SF_(0x403u, 0xC4u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
  }
  if ( this->_fDisableLegacyFeatures )
  {
    if ( (xmmword_1801FAD20 & 8) != 0 )
      WPP_SF_(0x403u, 0xC5u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    *grfBINDF |= 0x20000000u;
    if ( (xmmword_1801FAD20 & 8) != 0 )
      WPP_SF_(0x403u, 0xC6u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    *(_DWORD *)&pbindinfo[3].Data4[4] |= 0x20000000u;
    if ( (xmmword_1801FAD20 & 8) != 0 )
      WPP_SF_(0x403u, 0xC7u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    *(_DWORD *)&pbindinfo[3].Data4[4] |= 0x20000u;
  }
  *(_DWORD *)&pbindinfo[4].Data2 = 0;
  if ( this->_fQueryStringInUtf8 )
    *(_DWORD *)&pbindinfo[4].Data2 = 65001;
  if ( (xmmword_1801FAD20 & 8) != 0 )
  {
    v11 = "UTF8";
    if ( !this->_fQueryStringInUtf8 )
      v11 = "ACP";
    WPP_SF_s(v9, v8, v10, v11);
  }
  if ( this->_fDisableUI )
  {
    if ( (BYTE8(xmmword_1801FAD10) & 8) != 0 )
      WPP_SF_(0x303u, 0xC9u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    *grfBINDF |= 0x1800u;
  }
  if ( this->_dwAuth == 1 )
  {
    if ( (BYTE8(xmmword_1801FAD10) & 8) != 0 )
      WPP_SF_(0x303u, 0xCAu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    *(_DWORD *)&pbindinfo[3].Data4[4] |= 0x10000u;
    pbindinfo[4].Data1 = 0x40000;
  }
  else
  {
    *(_DWORD *)&pbindinfo[3].Data4[4] |= 0x800000u;
  }
  if ( this->_fNoCache )
  {
    if ( (BYTE8(xmmword_1801FAD10) & 8) != 0 )
      WPP_SF_(0x303u, 0xCBu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    *grfBINDF |= 0x30u;
  }
  *(_DWORD *)pbindinfo[2].Data4 = 3;
  if ( !fastcmpi(this->_pwszMethod, L"GET") )
  {
    *(_DWORD *)&pbindinfo[2].Data4[4] = 0;
LABEL_53:
    p_pstrmRequest = (HBITMAP__ **)&this->_pstrmRequest;
    if ( this->_pstrmRequest )
    {
      while ( 1 )
      {
        v24 = *p_pstrmRequest;
        liZero.QuadPart = 0;
        v25 = (*(__int64 (__fastcall **)(HBITMAP__ *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v24 + 40LL))(v24, 0, 0, 0);
        if ( v25 < 0 && (xmmword_1801FAD10 & 8) != 0 )
          WPP_SF_d(0x203u, 0xCDu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v25);
        memset_0(&sg, 0, sizeof(sg));
        v6 = (*(__int64 (__fastcall **)(HBITMAP__ *, tagSTATSTG *, _QWORD))(*(_QWORD *)*p_pstrmRequest + 96LL))(
               *p_pstrmRequest,
               &sg,
               0);
        if ( !v6 )
          break;
        v26 = (IStream *)*p_pstrmRequest;
        pcs = 0;
        v6 = CachingStreamForExternal::NewFromStream(v26, &pcs);
        if ( v6 < 0 )
          goto LABEL_64;
        v12 = (unsigned __int16)pcs;
        if ( !pcs )
          goto LABEL_64;
        assign(&this->_pstrmRequest, pcs);
        if ( pcs )
          pcs->Release(pcs);
      }
      if ( sg.cbSize.QuadPart )
      {
        (*(void (__fastcall **)(HBITMAP__ *))(*(_QWORD *)*p_pstrmRequest + 8LL))(*p_pstrmRequest);
        pbindinfo[1].Data1 = 4;
        *(_QWORD *)pbindinfo[1].Data4 = *p_pstrmRequest;
        *(_DWORD *)pbindinfo[3].Data4 = sg.cbSize.LowPart;
      }
    }
LABEL_64:
    if ( (xmmword_1801FAD20 & 8) != 0 )
      WPP_SF_DDDDdDqD(
        v13,
        v12,
        v14,
        *grfBINDF,
        *(_DWORD *)&pbindinfo[3].Data4[4],
        pbindinfo[4].Data1,
        *(_DWORD *)pbindinfo[2].Data4,
        *(_DWORD *)&pbindinfo[2].Data4[4],
        pbindinfo[1].Data1,
        *(const void **)pbindinfo[1].Data4,
        *(_DWORD *)pbindinfo[3].Data4);
    goto $CleanUp_35;
  }
  if ( !fastcmpi(v15, L"POST") )
  {
    *(_DWORD *)&pbindinfo[2].Data4[4] = 1;
    if ( (BYTE8(xmmword_1801FAD10) & 8) != 0 )
      WPP_SF_(0x303u, 0xCCu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    *grfBINDF |= 0x20u;
    goto LABEL_53;
  }
  if ( !fastcmpi(v16, L"PUT") )
  {
    *(_DWORD *)&pbindinfo[2].Data4[4] = 2;
    goto LABEL_53;
  }
  v18 = xstrlenw(v17, 0x7FFFFFFFu);
  if ( v18 + 1 < v18
    || (pcs = (CachingStreamForExternal *)(v18 + 1), ULongLongMult(v18 + 1, 2u, (unsigned __int64 *)&pcs) < 0)
    || (v20 = pcs, (unsigned __int64)pcs > v19) )
  {
    v6 = -2147024362;
    goto $CleanUp_35;
  }
  v21 = (wchar_t *)CoTaskMemAlloc((SIZE_T)pcs);
  *(_QWORD *)&pbindinfo[3].Data1 = v21;
  if ( !v21 )
  {
    v6 = -2147024882;
    goto $CleanUp_35;
  }
  v6 = StringCbCopyW(v21, (unsigned __int64)v20, this->_pwszMethod);
  if ( v6 >= 0 )
  {
    *(_DWORD *)&pbindinfo[2].Data4[4] = 3;
    goto LABEL_53;
  }
$CleanUp_35:
  this->Unlock(this);
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v6 >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d((((unsigned __int16)(v6 >> 31) + 2) << 9) | 3, 0xCFu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180053cd4  mov     [rsp-8+arg_18], rbx
0x180053cd9  push    rbp
0x180053cda  push    rsi
0x180053cdb  push    rdi
0x180053cdc  push    r12
0x180053cde  push    r13
0x180053ce0  push    r14
0x180053ce2  push    r15
0x180053ce4  lea     rbp, [rsp-27h]
0x180053ce9  sub     rsp, 0D0h
0x180053cf0  mov     rax, cs:__security_cookie
0x180053cf7  xor     rax, rsp
0x180053cfa  mov     [rbp+57h+var_40], rax
0x180053cfe  mov     rdi, pbindinfo
0x180053d01  mov     r14, grfBINDF
0x180053d04  mov     rsi, this
0x180053d07  mov     r13b, 8; __annotation("TMF:",
0x180053d0a  test    byte ptr cs:xmmword_1801FAD20, r13b
0x180053d11  jz      short loc_180053D2B
0x180053d13  mov     eax, [grfBINDF]
0x180053d15  mov     r9, this; _a4
0x180053d18  mov     [rsp+100h+TraceGuid], pbindinfo; TraceGuid
0x180053d1d  mov     [rsp+100h+id], eax; id
0x180053d21  mov     [rsp+100h+LevelKeyword], grfBINDF; LevelKeyword
0x180053d26  call    WPP_SF_qqDq
0x180053d2b  mov     rax, [rsi]
0x180053d2e  mov     this, rsi
0x180053d31  mov     rax, [rax+0F8h]
0x180053d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d3d  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x180053d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d49  xor     r12d, r12d
0x180053d4c  mov     ebx, 2
0x180053d51  test    rax, rax
0x180053d54  jnz     short loc_180053D61
0x180053d56  mov     r15d, 80004005h
0x180053d5c  jmp     $CleanUp_35
0x180053d61  mov     [r14], r12d
0x180053d64  xor     edx, edx; Val
0x180053d66  mov     ebx, [rdi]
0x180053d68  mov     this, rdi; void *
0x180053d6b  mov     r8d, ebx; Size
0x180053d6e  mov     r15d, r12d
0x180053d71  call    memset_0
0x180053d76  mov     [rdi], ebx
0x180053d78  cmp     [rsi+0B0h], r12d
0x180053d7f  jnz     short loc_180053DAC
0x180053d81  mov     dword ptr [r14], 100000h
0x180053d88  test    byte ptr cs:xmmword_1801FAD20, r13b; __annotation("TMF:",
0x180053d8f  lea     rbx, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids
0x180053d96  jz      short loc_180053DB3
0x180053d98  mov     edx, 0C4h; id
0x180053d9d  mov     ecx, 403h; LevelKeyword
0x180053da2  mov     pbindinfo, rbx; TraceGuid
0x180053da5  call    WPP_SF_
0x180053daa  jmp     short loc_180053DB3
0x180053dac  lea     rbx, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids
0x180053db3  cmp     [rsi+0A8h], r12d
0x180053dba  jz      short loc_180053E1C
0x180053dbc  test    byte ptr cs:xmmword_1801FAD20, r13b; __annotation("TMF:",
0x180053dc3  jz      short loc_180053DD7
0x180053dc5  mov     edx, 0C5h; id
0x180053dca  mov     ecx, 403h; LevelKeyword
0x180053dcf  mov     pbindinfo, rbx; TraceGuid
0x180053dd2  call    WPP_SF_
0x180053dd7  bts     dword ptr [r14], 1Dh
0x180053ddc  test    byte ptr cs:xmmword_1801FAD20, r13b; __annotation("TMF:",
0x180053de3  jz      short loc_180053DF7
0x180053de5  mov     edx, 0C6h; id
0x180053dea  mov     ecx, 403h; LevelKeyword
0x180053def  mov     pbindinfo, rbx; TraceGuid
0x180053df2  call    WPP_SF_
0x180053df7  bts     dword ptr [rdi+3Ch], 1Dh
0x180053dfc  test    byte ptr cs:xmmword_1801FAD20, r13b; __annotation("TMF:",
0x180053e03  jz      short loc_180053E17
0x180053e05  mov     edx, 0C7h; id
0x180053e0a  mov     ecx, 403h; LevelKeyword
0x180053e0f  mov     pbindinfo, rbx; TraceGuid
0x180053e12  call    WPP_SF_
0x180053e17  bts     dword ptr [rdi+3Ch], 11h
0x180053e1c  mov     [rdi+44h], r12d
0x180053e20  cmp     [rsi+19Ah], r12b
0x180053e27  jz      short loc_180053E30
0x180053e29  mov     dword ptr [rdi+44h], 0FDE9h
0x180053e30  test    byte ptr cs:xmmword_1801FAD20, r13b; __annotation("TMF:",
0x180053e37  jz      short loc_180053E57
0x180053e39  cmp     [rsi+19Ah], r12b
0x180053e40  lea     rax, TraceGuid; "ACP"
0x180053e47  lea     r9, aUtf8_0; "UTF8"
0x180053e4e  cmovz   r9, rax; TraceGuid
0x180053e52  call    WPP_SF_s
0x180053e57  cmp     [rsi+195h], r12b
0x180053e5e  jz      short loc_180053E82
0x180053e60  test    byte ptr cs:xmmword_1801FAD10+8, r13b; __annotation("TMF:",
0x180053e67  jz      short loc_180053E7B
0x180053e69  mov     edx, 0C9h; id
0x180053e6e  mov     ecx, 303h; LevelKeyword
0x180053e73  mov     pbindinfo, rbx; TraceGuid
0x180053e76  call    WPP_SF_
0x180053e7b  or      dword ptr [r14], 1800h
0x180053e82  cmp     dword ptr [rsi+190h], 1
0x180053e89  jnz     short loc_180053EB4
0x180053e8b  test    byte ptr cs:xmmword_1801FAD10+8, r13b; __annotation("TMF:",
0x180053e92  jz      short loc_180053EA6
0x180053e94  mov     edx, 0CAh; id
0x180053e99  mov     ecx, 303h; LevelKeyword
0x180053e9e  mov     pbindinfo, rbx; TraceGuid
0x180053ea1  call    WPP_SF_
0x180053ea6  bts     dword ptr [rdi+3Ch], 10h
0x180053eab  mov     dword ptr [rdi+40h], 40000h
0x180053eb2  jmp     short loc_180053EB9
0x180053eb4  bts     dword ptr [rdi+3Ch], 17h
0x180053eb9  cmp     [rsi+198h], r12b
0x180053ec0  jz      short loc_180053EE1
0x180053ec2  test    byte ptr cs:xmmword_1801FAD10+8, r13b; __annotation("TMF:",
0x180053ec9  jz      short loc_180053EDD
0x180053ecb  mov     edx, 0CBh; id
0x180053ed0  mov     ecx, 303h; LevelKeyword
0x180053ed5  mov     pbindinfo, rbx; TraceGuid
0x180053ed8  call    WPP_SF_
0x180053edd  or      dword ptr [r14], 30h
0x180053ee1  mov     dword ptr [rdi+28h], 3
0x180053ee8  lea     grfBINDF, aGet_0; "GET"
0x180053eef  mov     r10, [rsi+20h]
0x180053ef3  mov     this, r10; dst
0x180053ef6  call    ?fastcmpi@@YAHPEBG0@Z; fastcmpi(ushort const *,ushort const *)
0x180053efb  test    eax, eax
0x180053efd  jnz     short loc_180053F08
0x180053eff  mov     [rdi+2Ch], r12d
0x180053f03  jmp     loc_18005407E
0x180053f08  lea     grfBINDF, aPost; "POST"
0x180053f0f  mov     this, r10; dst
0x180053f12  call    ?fastcmpi@@YAHPEBG0@Z; fastcmpi(ushort const *,ushort const *)
0x180053f17  test    eax, eax
0x180053f19  jnz     short loc_180053F46
0x180053f1b  mov     dword ptr [rdi+2Ch], 1
0x180053f22  test    byte ptr cs:xmmword_1801FAD10+8, r13b; __annotation("TMF:",
0x180053f29  jz      short loc_180053F3D
0x180053f2b  mov     edx, 0CCh; id
0x180053f30  mov     ecx, 303h; LevelKeyword
0x180053f35  mov     pbindinfo, rbx; TraceGuid
0x180053f38  call    WPP_SF_
0x180053f3d  or      dword ptr [r14], 20h
0x180053f41  jmp     loc_18005407E
0x180053f46  lea     grfBINDF, aPut; "PUT"
0x180053f4d  mov     this, r10; dst
0x180053f50  call    ?fastcmpi@@YAHPEBG0@Z; fastcmpi(ushort const *,ushort const *)
0x180053f55  test    eax, eax
0x180053f57  jnz     short loc_180053F65
0x180053f59  mov     dword ptr [rdi+2Ch], 2
0x180053f60  jmp     loc_18005407E
0x180053f65  mov     r9d, 7FFFFFFFh
0x180053f6b  mov     this, r10; psz
0x180053f6e  mov     edx, r9d; cchMax
0x180053f71  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x180053f76  movsxd  this, eax
0x180053f79  mov     ebx, 2
0x180053f7e  lea     rax, [this+1]
0x180053f82  cmp     rax, this
0x180053f85  jb      loc_1800541BD
0x180053f8b  lea     pbindinfo, [rbp+57h+pcs]; pullResult
0x180053f8f  mov     [rbp+57h+pcs], rax
0x180053f93  mov     edx, ebx; ullMultiplier
0x180053f95  mov     this, rax; ullMultiplicand
0x180053f98  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180053f9d  test    eax, eax
0x180053f9f  js      loc_1800541BD
0x180053fa5  mov     rbx, [rbp+57h+pcs]
0x180053fa9  cmp     rbx, r9
0x180053fac  ja      loc_1800541B8
0x180053fb2  mov     this, rbx; cb
0x180053fb5  call    cs:__imp_CoTaskMemAlloc
0x180053fbc  nop     dword ptr [rax+rax+00h]
0x180053fc1  mov     [rdi+30h], rax
0x180053fc5  test    rax, rax
0x180053fc8  jnz     loc_18005405D
0x180053fce  mov     r15d, 8007000Eh
0x180053fd4  mov     ebx, 2
0x180053fd9  mov     rax, [rsi]
0x180053fdc  mov     this, rsi
0x180053fdf  mov     rax, [rax+100h]
0x180053fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053feb  mov     r9d, r15d; __annotation("TMF:",
0x180053fee  sar     r9d, 1Fh
0x180053ff2  lea     eax, ds:4[r9*2]
0x180053ffa  movsxd  this, eax
0x180053ffd  lea     rax, g_rgFastWppLevelEnabledFlags
0x180054004  test    [rax+this*8], r13b
0x180054008  jz      short loc_180054032
0x18005400a  add     r9w, bx
0x18005400e  lea     pbindinfo, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180054015  movzx   ecx, r9w
0x180054019  mov     eax, 200h
0x18005401e  imul    ecx, eax
0x180054021  mov     edx, 0CFh; id
0x180054026  mov     r9d, r15d; _a1
0x180054029  or      cx, 3; LevelKeyword
0x18005402d  call    WPP_SF_d
0x180054032  mov     eax, r15d
0x180054035  mov     this, [rbp+57h+var_40]
0x180054039  xor     this, rsp; StackCookie
0x18005403c  call    __security_check_cookie
0x180054041  mov     rbx, [rsp+100h+arg_18]
0x180054049  add     rsp, 0D0h
0x180054050  pop     r15
0x180054052  pop     r14
0x180054054  pop     r13
0x180054056  pop     r12
0x180054058  pop     rdi
0x180054059  pop     rsi
0x18005405a  pop     rbp
0x18005405b  retn
0x18005405d  mov     pbindinfo, [rsi+20h]; pszSrc
0x180054061  mov     grfBINDF, rbx; cbDest
0x180054064  mov     this, rax; pszDest
0x180054067  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18005406c  mov     r15d, eax
0x18005406f  test    eax, eax
0x180054071  js      loc_180053FD4
0x180054077  mov     dword ptr [rdi+2Ch], 3
0x18005407e  lea     rbx, [rsi+80h]
0x180054085  cmp     [rbx], r12
0x180054088  jz      loc_18005416B
0x18005408e  mov     this, [rbx]
0x180054091  xor     r9d, r9d
0x180054094  xor     r8d, r8d
0x180054097  mov     qword ptr [rbp+57h+liZero], r12
0x18005409b  mov     grfBINDF, r12
0x18005409e  mov     rax, [this]
0x1800540a1  mov     rax, [rax+28h]
0x1800540a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540aa  test    eax, eax
0x1800540ac  jns     short loc_1800540D0
0x1800540ae  test    byte ptr cs:xmmword_1801FAD10, r13b; __annotation("TMF:",
0x1800540b5  jz      short loc_1800540D0
0x1800540b7  mov     edx, 0CDh; id
0x1800540bc  lea     pbindinfo, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1800540c3  mov     ecx, 203h; LevelKeyword
0x1800540c8  mov     r9d, eax; _a1
0x1800540cb  call    WPP_SF_d
0x1800540d0  xor     edx, edx; Val
0x1800540d2  lea     this, [rbp+57h+sg]; void *
0x1800540d6  lea     r8d, [grfBINDF+50h]; Size
0x1800540da  call    memset_0
0x1800540df  mov     this, [rbx]
0x1800540e2  lea     grfBINDF, [rbp+57h+sg]
0x1800540e6  xor     r8d, r8d
0x1800540e9  mov     rax, [this]
0x1800540ec  mov     rax, [rax+60h]
0x1800540f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540f5  mov     r15d, eax
0x1800540f8  test    eax, eax
0x1800540fa  jz      short loc_180054142
0x1800540fc  mov     this, [rbx]; pStream
0x1800540ff  lea     grfBINDF, [rbp+57h+pcs]; ppNewStream
0x180054103  mov     [rbp+57h+pcs], r12
0x180054107  call    ?NewFromStream@CachingStreamForExternal@@SAJPEAUIStream@@PEAPEAV1@@Z; CachingStreamForExternal::NewFromStream(IStream *,CachingStreamForExternal * *)
0x18005410c  mov     r15d, eax
0x18005410f  test    eax, eax
0x180054111  js      short loc_18005416B
0x180054113  mov     grfBINDF, [rbp+57h+pcs]; pref
0x180054117  test    grfBINDF, grfBINDF
0x18005411a  jz      short loc_18005416B
0x18005411c  mov     this, rbx; ppref
0x18005411f  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180054124  mov     this, [rbp+57h+pcs]
0x180054128  test    this, this
0x18005412b  jz      $setSendBody
0x180054131  mov     rax, [this]
0x180054134  mov     rax, [rax+10h]
0x180054138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005413d  jmp     $setSendBody
0x180054142  cmp     qword ptr [rbp+57h+sg.cbSize], r12
0x180054146  jz      short loc_18005416B
0x180054148  mov     this, [rbx]
0x18005414b  mov     rax, [this]
0x18005414e  mov     rax, [rax+8]
0x180054152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054157  mov     dword ptr [rdi+10h], 4
0x18005415e  mov     rax, [rbx]
0x180054161  mov     [rdi+18h], rax
0x180054165  mov     eax, dword ptr [rbp+57h+sg.cbSize]
0x180054168  mov     [rdi+38h], eax
0x18005416b  test    byte ptr cs:xmmword_1801FAD20, r13b; __annotation("TMF:",
0x180054172  jz      loc_180053FD4
0x180054178  mov     eax, [rdi+38h]
0x18005417b  mov     r9d, [r14]; _a4
0x18005417e  mov     [rsp+100h+var_B0], eax; TraceGuid
0x180054182  mov     rax, [rdi+18h]
0x180054186  mov     [rsp+100h+var_B8], rax; id
0x18005418b  mov     eax, [rdi+10h]
0x18005418e  mov     [rsp+100h+var_C0], eax; LevelKeyword
0x180054192  mov     eax, [rdi+2Ch]
0x180054195  mov     [rsp+100h+_a8], eax; _a8
0x180054199  mov     eax, [rdi+28h]
0x18005419c  mov     dword ptr [rsp+100h+TraceGuid], eax; _a7
0x1800541a0  mov     eax, [rdi+40h]
0x1800541a3  mov     [rsp+100h+id], eax; _a6
0x1800541a7  mov     eax, [rdi+3Ch]
0x1800541aa  mov     dword ptr [rsp+100h+LevelKeyword], eax; _a5
  ... truncated ...
```
