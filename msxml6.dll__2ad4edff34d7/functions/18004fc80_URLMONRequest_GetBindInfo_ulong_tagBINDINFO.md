# URLMONRequest::GetBindInfo(ulong *,_tagBINDINFO *)

- ea: `0x18004fc80`
- end: `0x18005016d`
- name: `?GetBindInfo@URLMONRequest@@IEAAJPEAKPEAU_tagBINDINFO@@@Z`
- size: `1261`
- prototype: `__int64 __fastcall(URLMONRequest *this, unsigned int *grfBINDF, _GUID *pbindinfo)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004f974`
- `0x180156020`

## callees

- `0x180009490`
- `0x18004fc80`
- `0x1800502b0`
- `0x18005ac64`
- `0x1800a0c90`
- `0x1800cada0`
- `0x1800cba94`
- `0x1801524f0`
- `0x180156c74`
- `0x180185008`
- `0x180185118`
- `0x180186378`
- `0x180186f1c`
- `0x180187140`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ff61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ff61`

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
  IStream **p_pstrmRequest; // rbx
  IStream *v24; // rcx
  int v25; // eax
  IStream *v26; // rcx
  CachingStreamForExternal *pcs; // [rsp+60h] [rbp-49h] BYREF
  _LARGE_INTEGER liZero; // [rsp+68h] [rbp-41h]
  tagSTATSTG sg; // [rsp+70h] [rbp-39h] BYREF

  if ( (xmmword_1801F6C20 & 8) != 0 )
    WPP_SF_qqDq((unsigned __int16)this, (unsigned __int16)grfBINDF, pbindinfo, this, grfBINDF, *grfBINDF, pbindinfo);
  this->Lock(this);
  if ( !(__int64)g_pfnEntry() )
  {
    v6 = -2147467259;
    goto $CleanUp_32;
  }
  *grfBINDF = 0;
  Data1 = pbindinfo->Data1;
  v6 = 0;
  memset_0(pbindinfo, 0, pbindinfo->Data1);
  pbindinfo->Data1 = Data1;
  if ( !this->_fMta )
  {
    *grfBINDF = 0x100000;
    if ( (xmmword_1801F6C20 & 8) != 0 )
      WPP_SF_(0x403u, 0xC4u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
  }
  if ( this->_fDisableLegacyFeatures )
  {
    if ( (xmmword_1801F6C20 & 8) != 0 )
      WPP_SF_(0x403u, 0xC5u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    *grfBINDF |= 0x20000000u;
    if ( (xmmword_1801F6C20 & 8) != 0 )
      WPP_SF_(0x403u, 0xC6u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    *(_DWORD *)&pbindinfo[3].Data4[4] |= 0x20000000u;
    if ( (xmmword_1801F6C20 & 8) != 0 )
      WPP_SF_(0x403u, 0xC7u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    *(_DWORD *)&pbindinfo[3].Data4[4] |= 0x20000u;
  }
  *(_DWORD *)&pbindinfo[4].Data2 = 0;
  if ( this->_fQueryStringInUtf8 )
    *(_DWORD *)&pbindinfo[4].Data2 = 65001;
  if ( (xmmword_1801F6C20 & 8) != 0 )
  {
    v11 = "UTF8";
    if ( !this->_fQueryStringInUtf8 )
      v11 = "ACP";
    WPP_SF_s(v9, v8, v10, v11);
  }
  if ( this->_fDisableUI )
  {
    if ( (BYTE8(xmmword_1801F6C10) & 8) != 0 )
      WPP_SF_(0x303u, 0xC9u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    *grfBINDF |= 0x1800u;
  }
  if ( this->_dwAuth == 1 )
  {
    if ( (BYTE8(xmmword_1801F6C10) & 8) != 0 )
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
    if ( (BYTE8(xmmword_1801F6C10) & 8) != 0 )
      WPP_SF_(0x303u, 0xCBu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    *grfBINDF |= 0x30u;
  }
  *(_DWORD *)pbindinfo[2].Data4 = 3;
  if ( !fastcmpi(this->_pwszMethod, L"GET") )
  {
    *(_DWORD *)&pbindinfo[2].Data4[4] = 0;
LABEL_53:
    p_pstrmRequest = &this->_pstrmRequest;
    if ( this->_pstrmRequest )
    {
      while ( 1 )
      {
        v24 = *p_pstrmRequest;
        liZero.QuadPart = 0;
        v25 = ((__int64 (__fastcall *)(IStream *, _QWORD, _QWORD, _QWORD))v24->Seek)(v24, 0, 0, 0);
        if ( v25 < 0 && (xmmword_1801F6C10 & 8) != 0 )
          WPP_SF_d(0x203u, 0xCDu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v25);
        memset_0(&sg, 0, sizeof(sg));
        v6 = (*p_pstrmRequest)->Stat(*p_pstrmRequest, &sg, 0);
        if ( !v6 )
          break;
        v26 = *p_pstrmRequest;
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
        (*p_pstrmRequest)->AddRef(*p_pstrmRequest);
        pbindinfo[1].Data1 = 4;
        *(_QWORD *)pbindinfo[1].Data4 = *p_pstrmRequest;
        *(_DWORD *)pbindinfo[3].Data4 = sg.cbSize.LowPart;
      }
    }
LABEL_64:
    if ( (xmmword_1801F6C20 & 8) != 0 )
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
    goto $CleanUp_32;
  }
  if ( !fastcmpi(v15, L"POST") )
  {
    *(_DWORD *)&pbindinfo[2].Data4[4] = 1;
    if ( (BYTE8(xmmword_1801F6C10) & 8) != 0 )
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
    goto $CleanUp_32;
  }
  v21 = (wchar_t *)CoTaskMemAlloc((SIZE_T)pcs);
  *(_QWORD *)&pbindinfo[3].Data1 = v21;
  if ( !v21 )
  {
    v6 = -2147024882;
    goto $CleanUp_32;
  }
  v6 = StringCbCopyW(v21, (unsigned __int64)v20, this->_pwszMethod);
  if ( v6 >= 0 )
  {
    *(_DWORD *)&pbindinfo[2].Data4[4] = 3;
    goto LABEL_53;
  }
$CleanUp_32:
  this->Unlock(this);
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v6 >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d((((unsigned __int16)(v6 >> 31) + 2) << 9) | 3, 0xCFu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004fc80  mov     [rsp-8+arg_18], rbx
0x18004fc85  push    rbp
0x18004fc86  push    rsi
0x18004fc87  push    rdi
0x18004fc88  push    r12
0x18004fc8a  push    r13
0x18004fc8c  push    r14
0x18004fc8e  push    r15
0x18004fc90  lea     rbp, [rsp-27h]
0x18004fc95  sub     rsp, 0D0h
0x18004fc9c  mov     rax, cs:__security_cookie
0x18004fca3  xor     rax, rsp
0x18004fca6  mov     [rbp+57h+var_40], rax
0x18004fcaa  mov     rdi, pbindinfo
0x18004fcad  mov     r14, grfBINDF
0x18004fcb0  mov     rsi, this
0x18004fcb3  mov     r13b, 8; __annotation("TMF:",
0x18004fcb6  test    byte ptr cs:xmmword_1801F6C20, r13b
0x18004fcbd  jz      short loc_18004FCD7
0x18004fcbf  mov     eax, [grfBINDF]
0x18004fcc1  mov     r9, this; _a4
0x18004fcc4  mov     [rsp+100h+TraceGuid], pbindinfo; TraceGuid
0x18004fcc9  mov     [rsp+100h+id], eax; id
0x18004fccd  mov     [rsp+100h+LevelKeyword], grfBINDF; LevelKeyword
0x18004fcd2  call    WPP_SF_qqDq
0x18004fcd7  mov     rax, [rsi]
0x18004fcda  mov     this, rsi
0x18004fcdd  mov     rax, [rax+0F8h]
0x18004fce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fce9  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x18004fcf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fcf5  xor     r12d, r12d
0x18004fcf8  mov     ebx, 2
0x18004fcfd  test    rax, rax
0x18004fd00  jnz     short loc_18004FD0D
0x18004fd02  mov     r15d, 80004005h
0x18004fd08  jmp     $CleanUp_32
0x18004fd0d  mov     [r14], r12d
0x18004fd10  xor     edx, edx; Val
0x18004fd12  mov     ebx, [rdi]
0x18004fd14  mov     this, rdi; void *
0x18004fd17  mov     r8d, ebx; Size
0x18004fd1a  mov     r15d, r12d
0x18004fd1d  call    memset_0
0x18004fd22  mov     [rdi], ebx
0x18004fd24  cmp     [rsi+0B0h], r12d
0x18004fd2b  jnz     short loc_18004FD58
0x18004fd2d  mov     dword ptr [r14], 100000h
0x18004fd34  test    byte ptr cs:xmmword_1801F6C20, r13b; __annotation("TMF:",
0x18004fd3b  lea     rbx, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids
0x18004fd42  jz      short loc_18004FD5F
0x18004fd44  mov     edx, 0C4h; id
0x18004fd49  mov     ecx, 403h; LevelKeyword
0x18004fd4e  mov     pbindinfo, rbx; TraceGuid
0x18004fd51  call    WPP_SF_
0x18004fd56  jmp     short loc_18004FD5F
0x18004fd58  lea     rbx, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids
0x18004fd5f  cmp     [rsi+0A8h], r12d
0x18004fd66  jz      short loc_18004FDC8
0x18004fd68  test    byte ptr cs:xmmword_1801F6C20, r13b; __annotation("TMF:",
0x18004fd6f  jz      short loc_18004FD83
0x18004fd71  mov     edx, 0C5h; id
0x18004fd76  mov     ecx, 403h; LevelKeyword
0x18004fd7b  mov     pbindinfo, rbx; TraceGuid
0x18004fd7e  call    WPP_SF_
0x18004fd83  bts     dword ptr [r14], 1Dh
0x18004fd88  test    byte ptr cs:xmmword_1801F6C20, r13b; __annotation("TMF:",
0x18004fd8f  jz      short loc_18004FDA3
0x18004fd91  mov     edx, 0C6h; id
0x18004fd96  mov     ecx, 403h; LevelKeyword
0x18004fd9b  mov     pbindinfo, rbx; TraceGuid
0x18004fd9e  call    WPP_SF_
0x18004fda3  bts     dword ptr [rdi+3Ch], 1Dh
0x18004fda8  test    byte ptr cs:xmmword_1801F6C20, r13b; __annotation("TMF:",
0x18004fdaf  jz      short loc_18004FDC3
0x18004fdb1  mov     edx, 0C7h; id
0x18004fdb6  mov     ecx, 403h; LevelKeyword
0x18004fdbb  mov     pbindinfo, rbx; TraceGuid
0x18004fdbe  call    WPP_SF_
0x18004fdc3  bts     dword ptr [rdi+3Ch], 11h
0x18004fdc8  mov     [rdi+44h], r12d
0x18004fdcc  cmp     [rsi+19Ah], r12b
0x18004fdd3  jz      short loc_18004FDDC
0x18004fdd5  mov     dword ptr [rdi+44h], 0FDE9h
0x18004fddc  test    byte ptr cs:xmmword_1801F6C20, r13b; __annotation("TMF:",
0x18004fde3  jz      short loc_18004FE03
0x18004fde5  cmp     [rsi+19Ah], r12b
0x18004fdec  lea     rax, TraceGuid; "ACP"
0x18004fdf3  lea     r9, aUtf8_0; "UTF8"
0x18004fdfa  cmovz   r9, rax; TraceGuid
0x18004fdfe  call    WPP_SF_s
0x18004fe03  cmp     [rsi+195h], r12b
0x18004fe0a  jz      short loc_18004FE2E
0x18004fe0c  test    byte ptr cs:xmmword_1801F6C10+8, r13b; __annotation("TMF:",
0x18004fe13  jz      short loc_18004FE27
0x18004fe15  mov     edx, 0C9h; id
0x18004fe1a  mov     ecx, 303h; LevelKeyword
0x18004fe1f  mov     pbindinfo, rbx; TraceGuid
0x18004fe22  call    WPP_SF_
0x18004fe27  or      dword ptr [r14], 1800h
0x18004fe2e  cmp     dword ptr [rsi+190h], 1
0x18004fe35  jnz     short loc_18004FE60
0x18004fe37  test    byte ptr cs:xmmword_1801F6C10+8, r13b; __annotation("TMF:",
0x18004fe3e  jz      short loc_18004FE52
0x18004fe40  mov     edx, 0CAh; id
0x18004fe45  mov     ecx, 303h; LevelKeyword
0x18004fe4a  mov     pbindinfo, rbx; TraceGuid
0x18004fe4d  call    WPP_SF_
0x18004fe52  bts     dword ptr [rdi+3Ch], 10h
0x18004fe57  mov     dword ptr [rdi+40h], 40000h
0x18004fe5e  jmp     short loc_18004FE65
0x18004fe60  bts     dword ptr [rdi+3Ch], 17h
0x18004fe65  cmp     [rsi+198h], r12b
0x18004fe6c  jz      short loc_18004FE8D
0x18004fe6e  test    byte ptr cs:xmmword_1801F6C10+8, r13b; __annotation("TMF:",
0x18004fe75  jz      short loc_18004FE89
0x18004fe77  mov     edx, 0CBh; id
0x18004fe7c  mov     ecx, 303h; LevelKeyword
0x18004fe81  mov     pbindinfo, rbx; TraceGuid
0x18004fe84  call    WPP_SF_
0x18004fe89  or      dword ptr [r14], 30h
0x18004fe8d  mov     dword ptr [rdi+28h], 3
0x18004fe94  lea     grfBINDF, aGet_0; "GET"
0x18004fe9b  mov     r10, [rsi+20h]
0x18004fe9f  mov     this, r10; dst
0x18004fea2  call    ?fastcmpi@@YAHPEBG0@Z; fastcmpi(ushort const *,ushort const *)
0x18004fea7  test    eax, eax
0x18004fea9  jnz     short loc_18004FEB4
0x18004feab  mov     [rdi+2Ch], r12d
0x18004feaf  jmp     loc_180050023
0x18004feb4  lea     grfBINDF, aPost; "POST"
0x18004febb  mov     this, r10; dst
0x18004febe  call    ?fastcmpi@@YAHPEBG0@Z; fastcmpi(ushort const *,ushort const *)
0x18004fec3  test    eax, eax
0x18004fec5  jnz     short loc_18004FEF2
0x18004fec7  mov     dword ptr [rdi+2Ch], 1
0x18004fece  test    byte ptr cs:xmmword_1801F6C10+8, r13b; __annotation("TMF:",
0x18004fed5  jz      short loc_18004FEE9
0x18004fed7  mov     edx, 0CCh; id
0x18004fedc  mov     ecx, 303h; LevelKeyword
0x18004fee1  mov     pbindinfo, rbx; TraceGuid
0x18004fee4  call    WPP_SF_
0x18004fee9  or      dword ptr [r14], 20h
0x18004feed  jmp     loc_180050023
0x18004fef2  lea     grfBINDF, aPut; "PUT"
0x18004fef9  mov     this, r10; dst
0x18004fefc  call    ?fastcmpi@@YAHPEBG0@Z; fastcmpi(ushort const *,ushort const *)
0x18004ff01  test    eax, eax
0x18004ff03  jnz     short loc_18004FF11
0x18004ff05  mov     dword ptr [rdi+2Ch], 2
0x18004ff0c  jmp     loc_180050023
0x18004ff11  mov     r9d, 7FFFFFFFh
0x18004ff17  mov     this, r10; psz
0x18004ff1a  mov     edx, r9d; cchMax
0x18004ff1d  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x18004ff22  movsxd  this, eax
0x18004ff25  mov     ebx, 2
0x18004ff2a  lea     rax, [this+1]
0x18004ff2e  cmp     rax, this
0x18004ff31  jb      loc_180050162
0x18004ff37  lea     pbindinfo, [rbp+57h+pcs]; pullResult
0x18004ff3b  mov     [rbp+57h+pcs], rax
0x18004ff3f  mov     edx, ebx; ullMultiplier
0x18004ff41  mov     this, rax; ullMultiplicand
0x18004ff44  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004ff49  test    eax, eax
0x18004ff4b  js      loc_180050162
0x18004ff51  mov     rbx, [rbp+57h+pcs]
0x18004ff55  cmp     rbx, r9
0x18004ff58  ja      loc_18005015D
0x18004ff5e  mov     this, rbx; cb
0x18004ff61  call    cs:__imp_CoTaskMemAlloc
0x18004ff67  mov     [rdi+30h], rax
0x18004ff6b  test    rax, rax
0x18004ff6e  jnz     loc_180050002
0x18004ff74  mov     r15d, 8007000Eh
0x18004ff7a  mov     ebx, 2
0x18004ff7f  mov     rax, [rsi]
0x18004ff82  mov     this, rsi
0x18004ff85  mov     rax, [rax+100h]
0x18004ff8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff91  mov     r9d, r15d; __annotation("TMF:",
0x18004ff94  sar     r9d, 1Fh
0x18004ff98  lea     eax, ds:4[r9*2]
0x18004ffa0  movsxd  this, eax
0x18004ffa3  lea     rax, g_rgFastWppLevelEnabledFlags
0x18004ffaa  test    [rax+this*8], r13b
0x18004ffae  jz      short loc_18004FFD8
0x18004ffb0  add     r9w, bx
0x18004ffb4  lea     pbindinfo, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18004ffbb  movzx   ecx, r9w
0x18004ffbf  mov     eax, 200h
0x18004ffc4  imul    ecx, eax
0x18004ffc7  mov     edx, 0CFh; id
0x18004ffcc  mov     r9d, r15d; _a1
0x18004ffcf  or      cx, 3; LevelKeyword
0x18004ffd3  call    WPP_SF_d
0x18004ffd8  mov     eax, r15d
0x18004ffdb  mov     this, [rbp+57h+var_40]
0x18004ffdf  xor     this, rsp; StackCookie
0x18004ffe2  call    __security_check_cookie
0x18004ffe7  mov     rbx, [rsp+100h+arg_18]
0x18004ffef  add     rsp, 0D0h
0x18004fff6  pop     r15
0x18004fff8  pop     r14
0x18004fffa  pop     r13
0x18004fffc  pop     r12
0x18004fffe  pop     rdi
0x18004ffff  pop     rsi
0x180050000  pop     rbp
0x180050001  retn
0x180050002  mov     pbindinfo, [rsi+20h]; pszSrc
0x180050006  mov     grfBINDF, rbx; cbDest
0x180050009  mov     this, rax; pszDest
0x18005000c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180050011  mov     r15d, eax
0x180050014  test    eax, eax
0x180050016  js      loc_18004FF7A
0x18005001c  mov     dword ptr [rdi+2Ch], 3
0x180050023  lea     rbx, [rsi+80h]
0x18005002a  cmp     [rbx], r12
0x18005002d  jz      loc_180050110
0x180050033  mov     this, [rbx]
0x180050036  xor     r9d, r9d
0x180050039  xor     r8d, r8d
0x18005003c  mov     qword ptr [rbp+57h+liZero], r12
0x180050040  mov     grfBINDF, r12
0x180050043  mov     rax, [this]
0x180050046  mov     rax, [rax+28h]
0x18005004a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005004f  test    eax, eax
0x180050051  jns     short loc_180050075
0x180050053  test    byte ptr cs:xmmword_1801F6C10, r13b; __annotation("TMF:",
0x18005005a  jz      short loc_180050075
0x18005005c  mov     edx, 0CDh; id
0x180050061  lea     pbindinfo, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180050068  mov     ecx, 203h; LevelKeyword
0x18005006d  mov     r9d, eax; _a1
0x180050070  call    WPP_SF_d
0x180050075  xor     edx, edx; Val
0x180050077  lea     this, [rbp+57h+sg]; void *
0x18005007b  lea     r8d, [grfBINDF+50h]; Size
0x18005007f  call    memset_0
0x180050084  mov     this, [rbx]
0x180050087  lea     grfBINDF, [rbp+57h+sg]
0x18005008b  xor     r8d, r8d
0x18005008e  mov     rax, [this]
0x180050091  mov     rax, [rax+60h]
0x180050095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005009a  mov     r15d, eax
0x18005009d  test    eax, eax
0x18005009f  jz      short loc_1800500E7
0x1800500a1  mov     this, [rbx]; pStream
0x1800500a4  lea     grfBINDF, [rbp+57h+pcs]; ppNewStream
0x1800500a8  mov     [rbp+57h+pcs], r12
0x1800500ac  call    ?NewFromStream@CachingStreamForExternal@@SAJPEAUIStream@@PEAPEAV1@@Z; CachingStreamForExternal::NewFromStream(IStream *,CachingStreamForExternal * *)
0x1800500b1  mov     r15d, eax
0x1800500b4  test    eax, eax
0x1800500b6  js      short loc_180050110
0x1800500b8  mov     grfBINDF, [rbp+57h+pcs]; pref
0x1800500bc  test    grfBINDF, grfBINDF
0x1800500bf  jz      short loc_180050110
0x1800500c1  mov     this, rbx; ppref
0x1800500c4  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800500c9  mov     this, [rbp+57h+pcs]
0x1800500cd  test    this, this
0x1800500d0  jz      $setSendBody
0x1800500d6  mov     rax, [this]
0x1800500d9  mov     rax, [rax+10h]
0x1800500dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500e2  jmp     $setSendBody
0x1800500e7  cmp     qword ptr [rbp+57h+sg.cbSize], r12
0x1800500eb  jz      short loc_180050110
0x1800500ed  mov     this, [rbx]
0x1800500f0  mov     rax, [this]
0x1800500f3  mov     rax, [rax+8]
0x1800500f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500fc  mov     dword ptr [rdi+10h], 4
0x180050103  mov     rax, [rbx]
0x180050106  mov     [rdi+18h], rax
0x18005010a  mov     eax, dword ptr [rbp+57h+sg.cbSize]
0x18005010d  mov     [rdi+38h], eax
0x180050110  test    byte ptr cs:xmmword_1801F6C20, r13b; __annotation("TMF:",
0x180050117  jz      loc_18004FF7A
0x18005011d  mov     eax, [rdi+38h]
0x180050120  mov     r9d, [r14]; _a4
0x180050123  mov     [rsp+100h+var_B0], eax; TraceGuid
0x180050127  mov     rax, [rdi+18h]
0x18005012b  mov     [rsp+100h+var_B8], rax; id
0x180050130  mov     eax, [rdi+10h]
0x180050133  mov     [rsp+100h+var_C0], eax; LevelKeyword
0x180050137  mov     eax, [rdi+2Ch]
0x18005013a  mov     [rsp+100h+_a8], eax; _a8
0x18005013e  mov     eax, [rdi+28h]
0x180050141  mov     dword ptr [rsp+100h+TraceGuid], eax; _a7
0x180050145  mov     eax, [rdi+40h]
0x180050148  mov     [rsp+100h+id], eax; _a6
0x18005014c  mov     eax, [rdi+3Ch]
0x18005014f  mov     dword ptr [rsp+100h+LevelKeyword], eax; _a5
0x180050153  call    WPP_SF_DDDDdDqD
  ... truncated ...
```
