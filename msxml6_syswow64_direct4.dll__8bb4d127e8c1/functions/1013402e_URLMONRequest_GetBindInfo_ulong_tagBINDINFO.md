# URLMONRequest::GetBindInfo(ulong *,_tagBINDINFO *)

- ea: `0x1013402e`
- end: `0x101344b6`
- name: `?GetBindInfo@URLMONRequest@@IAEJPAKPAU_tagBINDINFO@@@Z`
- size: `1160`
- prototype: `HRESULT __thiscall(URLMONRequest *this, unsigned int *grfBINDF, _tagBINDINFO *pbindinfo)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x101344c0`
- `0x101344e3`

## callees

- `0x1003fb13`
- `0x100410fe`
- `0x1004fbae`
- `0x10067b20`
- `0x1006b470`
- `0x1006c2c4`
- `0x10078738`
- `0x1012ef5a`
- `0x1013402e`
- `0x10135a56`
- `0x10180006`
- `0x10180060`
- `0x10180c5f`
- `0x1018142e`
- `0x10181506`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x101342e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x101342e8`

## pseudocode

```c
unsigned int __thiscall URLMONRequest::GetBindInfo(URLMONRequest *this, _GUID *grfBINDF, _tagBINDINFO *pbindinfo)
{
  _GUID *v3; // edi
  unsigned int cbSize; // esi
  URLMONRequest *v6; // esi
  const char *v7; // eax
  unsigned __int16 v8; // cx
  unsigned int v9; // eax
  wchar_t *v10; // eax
  bool v11; // zf
  IUnknown **p_pstrmRequest; // edi
  int v13; // eax
  unsigned int v14; // eax
  IStream *v15; // ecx
  unsigned int v16; // ebx
  const _GUID *v18; // [esp+14h] [ebp-70h]
  const void *v19; // [esp+18h] [ebp-6Ch]
  unsigned int cbCustomVerb; // [esp+20h] [ebp-64h] BYREF
  _GUID *v21; // [esp+24h] [ebp-60h]
  CachingStreamForExternal *pcs; // [esp+28h] [ebp-5Ch] BYREF
  URLMONRequest *v23; // [esp+2Ch] [ebp-58h]
  IUnknown **ppref; // [esp+30h] [ebp-54h]
  tagSTATSTG sg; // [esp+34h] [ebp-50h] BYREF

  v3 = grfBINDF;
  v23 = this;
  v21 = grfBINDF;
  cbCustomVerb = 0;
  if ( (byte_10185760[0] & 8) != 0 )
    WPP_SF_qqDq(
      (unsigned __int16)this,
      (unsigned __int16)this,
      grfBINDF,
      (const void *)grfBINDF->Data1,
      pbindinfo,
      (unsigned int)v18,
      v19);
  this->Lock(v23);
  if ( !((struct TLSDATA *(__stdcall *)())g_pfnEntry)() )
  {
    cbCustomVerb = -2147467259;
    goto CleanUp_466;
  }
  grfBINDF->Data1 = 0;
  cbSize = pbindinfo->cbSize;
  memset(pbindinfo, 0, pbindinfo->cbSize);
  pbindinfo->cbSize = cbSize;
  v6 = v23;
  if ( !v23->_fMta )
  {
    grfBINDF->Data1 = 0x100000;
    if ( (byte_10185760[0] & 8) != 0 )
      WPP_SF_(0x403u, 0xC4u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
  }
  if ( v6->_fDisableLegacyFeatures )
  {
    if ( (byte_10185760[0] & 8) != 0 )
      WPP_SF_(0x403u, 0xC5u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    grfBINDF->Data1 |= 0x20000000u;
    if ( (byte_10185760[0] & 8) != 0 )
      WPP_SF_(0x403u, 0xC6u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    pbindinfo->dwOptions |= 0x20000000u;
    if ( (byte_10185760[0] & 8) != 0 )
      WPP_SF_(0x403u, 0xC7u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    pbindinfo->dwOptions |= 0x20000u;
  }
  pbindinfo->dwCodePage = 0;
  if ( v6->_fQueryStringInUtf8 )
    pbindinfo->dwCodePage = 65001;
  if ( (byte_10185760[0] & 8) != 0 )
  {
    v7 = "ACP";
    if ( v6->_fQueryStringInUtf8 )
      v7 = "UTF8";
    WPP_SF_s((unsigned __int16)"UTF8", (unsigned __int16)v7, v18, (const char *)v19);
  }
  if ( v6->_fDisableUI )
  {
    if ( (byte_10185758 & 8) != 0 )
      WPP_SF_(0x303u, 0xC9u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    grfBINDF->Data1 |= 0x1800u;
  }
  if ( v6->_dwAuth == 1 )
  {
    if ( (byte_10185758 & 8) != 0 )
      WPP_SF_(0x303u, 0xCAu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    pbindinfo->dwOptions |= 0x10000u;
    pbindinfo->dwOptionsFlags = 0x40000;
  }
  else
  {
    pbindinfo->dwOptions |= 0x800000u;
  }
  if ( v6->_fNoCache )
  {
    if ( (byte_10185758 & 8) != 0 )
      WPP_SF_(0x303u, 0xCBu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    grfBINDF->Data1 |= 0x30u;
  }
  pbindinfo->grfBindInfoF = 3;
  if ( !fastcmpi(v6->_pwszMethod, L"GET") )
  {
    pbindinfo->dwBindVerb = 0;
LABEL_50:
    v11 = v6->_pstrmRequest == 0;
    ppref = &v6->_pstrmRequest;
    if ( !v11 )
    {
      p_pstrmRequest = &v6->_pstrmRequest;
      while ( 1 )
      {
        v13 = ((int (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IUnknown *, _DWORD, _DWORD, _DWORD, _DWORD))(*p_pstrmRequest)->__vftable[1].Release)(
                (*p_pstrmRequest)->__vftable[1].Release,
                *p_pstrmRequest,
                0,
                0,
                0,
                0);
        if ( v13 < 0 && (byte_10185750 & 8) != 0 )
          WPP_SF_q(0x203u, 0xCDu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v13);
        memset(&sg, 0, sizeof(sg));
        p_pstrmRequest = ppref;
        v14 = ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IUnknown *, tagSTATSTG *, _DWORD))(*ppref)->__vftable[4].QueryInterface)(
                (*ppref)->__vftable[4].QueryInterface,
                *ppref,
                &sg,
                0);
        v8 = v14;
        cbCustomVerb = v14;
        if ( !v14 )
          break;
        v15 = (IStream *)*p_pstrmRequest;
        pcs = 0;
        cbCustomVerb = CachingStreamForExternal::NewFromStream(v15, &pcs);
        if ( (cbCustomVerb & 0x80000000) != 0 || !pcs )
          goto LABEL_62;
        assign(p_pstrmRequest, pcs);
        if ( pcs )
          ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), CachingStreamForExternal *))pcs->Release)(
            pcs->Release,
            pcs);
      }
      if ( sg.cbSize.QuadPart )
      {
        ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IUnknown *))(*p_pstrmRequest)->AddRef)(
          (*p_pstrmRequest)->AddRef,
          *p_pstrmRequest);
        pbindinfo->stgmedData.tymed = 4;
        pbindinfo->stgmedData.hBitmap = (HBITMAP__ *)*p_pstrmRequest;
        pbindinfo->cbstgmedData = sg.cbSize.LowPart;
      }
LABEL_62:
      v3 = v21;
    }
    if ( (byte_10185760[0] & 8) != 0 )
      WPP_SF_DDDDdDqD(
        v8,
        v3->Data1,
        (const _GUID *)pbindinfo->dwOptions,
        pbindinfo->dwOptionsFlags,
        pbindinfo->grfBindInfoF,
        pbindinfo->dwBindVerb,
        pbindinfo->stgmedData.tymed,
        (int)pbindinfo->stgmedData.hBitmap,
        pbindinfo->cbstgmedData,
        v18,
        (unsigned int)v19);
    goto CleanUp_466;
  }
  if ( !fastcmpi(v6->_pwszMethod, L"POST") )
  {
    pbindinfo->dwBindVerb = 1;
    if ( (byte_10185758 & 8) != 0 )
      WPP_SF_(0x303u, 0xCCu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    grfBINDF->Data1 |= 0x20u;
    goto LABEL_50;
  }
  if ( !fastcmpi(v6->_pwszMethod, L"PUT") )
  {
    pbindinfo->dwBindVerb = 2;
    goto LABEL_50;
  }
  v9 = xstrlenw(v6->_pwszMethod, 0x7FFFFFFFu);
  if ( v9 + 1 < v9
    || (cbCustomVerb = v9 + 1, ULongLongToUInt(2LL * (v9 + 1), &cbCustomVerb) < 0)
    || cbCustomVerb > 0x7FFFFFFF )
  {
    cbCustomVerb = -2147024362;
    goto CleanUp_466;
  }
  v10 = (wchar_t *)CoTaskMemAlloc(cbCustomVerb);
  pbindinfo->szCustomVerb = v10;
  if ( !v10 )
  {
    cbCustomVerb = -2147024882;
    goto CleanUp_466;
  }
  cbCustomVerb = StringCbCopyW(v10, cbCustomVerb, v6->_pwszMethod);
  if ( (cbCustomVerb & 0x80000000) == 0 )
  {
    pbindinfo->dwBindVerb = 3;
    goto LABEL_50;
  }
CleanUp_466:
  v23->Unlock(v23);
  v16 = cbCustomVerb;
  if ( (byte_10185760[16 * ((int)cbCustomVerb >> 31)] & 8) != 0 )
    WPP_SF_q(
      (((unsigned __int16)((int)cbCustomVerb >> 31) + 2) << 9) | 3,
      0xCFu,
      WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids,
      cbCustomVerb);
  return v16;
}

```

## disassembly

```asm
0x1013402e  mov     edi, edi
0x10134030  push    ebp
0x10134031  mov     ebp, esp
0x10134033  and     esp, 0FFFFFFF8h
0x10134036  sub     esp, 64h
0x10134039  mov     eax, ___security_cookie
0x1013403e  xor     eax, esp
0x10134040  mov     [esp+64h+var_4], eax
0x10134044  push    ebx
0x10134045  mov     ebx, [ebp+pbindinfo]
0x10134048  xor     eax, eax
0x1013404a  push    esi; TraceGuid
0x1013404b  push    edi; id
0x1013404c  mov     edi, [ebp+grfBINDF]
0x1013404f  mov     esi, this
0x10134051  mov     [esp+70h+var_58], esi
0x10134055  mov     [esp+70h+var_60], edi
0x10134059  mov     [esp+70h+cbCustomVerb], eax
0x1013405d  test    byte_10185760, 8; __annotation("TMF:",
0x10134064  jz      short loc_10134071
0x10134066  push    ebx; LevelKeyword
0x10134067  push    dword ptr [edi]; _a4
0x10134069  push    edi; _a3
0x1013406a  push    esi; _a2
0x1013406b  push    this; _a1
0x1013406c  call    _WPP_SF_qqDq@28; WPP_SF_qqDq(x,x,x,x,x,x,x)
0x10134071  mov     eax, [esi]
0x10134073  mov     esi, [eax+7Ch]
0x10134076  mov     this, esi; this
0x10134078  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013407e  mov     this, [esp+70h+var_58]
0x10134082  call    esi
0x10134084  mov     esi, ?g_pfnEntry@@3P6GPAUTLSDATA@@XZA; TLSDATA * (*g_pfnEntry)(void)
0x1013408a  mov     this, esi; this
0x1013408c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10134092  call    esi ; TLSDATA * (*g_pfnEntry)(void)
0x10134094  test    eax, eax
0x10134096  jnz     short loc_101340A5
0x10134098  mov     [esp+70h+cbCustomVerb], 80004005h
0x101340a0  jmp     CleanUp_466
0x101340a5  mov     dword ptr [edi], 0
0x101340ab  mov     esi, [ebx]
0x101340ad  push    esi; Size
0x101340ae  push    0; Val
0x101340b0  push    ebx; void *
0x101340b1  call    _memset
0x101340b6  mov     [ebx], esi
0x101340b8  add     esp, 0Ch
0x101340bb  mov     esi, [esp+70h+var_58]
0x101340bf  cmp     dword ptr [esi+64h], 0
0x101340c3  jnz     short loc_101340E8
0x101340c5  mov     dword ptr [edi], 100000h
0x101340cb  test    byte_10185760, 8; __annotation("TMF:",
0x101340d2  jz      short loc_101340E8
0x101340d4  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101340d9  mov     edx, 0C4h; id
0x101340de  mov     this, 403h; LevelKeyword
0x101340e3  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x101340e8  cmp     dword ptr [esi+60h], 0
0x101340ec  jz      short loc_10134159
0x101340ee  test    byte_10185760, 8; __annotation("TMF:",
0x101340f5  jz      short loc_1013410B
0x101340f7  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101340fc  mov     edx, 0C5h; id
0x10134101  mov     this, 403h; LevelKeyword
0x10134106  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x1013410b  or      dword ptr [edi], 20000000h
0x10134111  test    byte_10185760, 8; __annotation("TMF:",
0x10134118  jz      short loc_1013412E
0x1013411a  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013411f  mov     edx, 0C6h; id
0x10134124  mov     this, 403h; LevelKeyword
0x10134129  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x1013412e  or      dword ptr [ebx+24h], 20000000h
0x10134135  test    byte_10185760, 8; __annotation("TMF:",
0x1013413c  jz      short loc_10134152
0x1013413e  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10134143  mov     edx, 0C7h; id
0x10134148  mov     this, 403h; LevelKeyword
0x1013414d  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x10134152  or      dword ptr [ebx+24h], 20000h
0x10134159  mov     dword ptr [ebx+2Ch], 0
0x10134160  cmp     byte ptr [esi+0E6h], 0
0x10134167  jz      short loc_10134170
0x10134169  mov     dword ptr [ebx+2Ch], 0FDE9h
0x10134170  test    byte_10185760, 8; __annotation("TMF:",
0x10134177  jz      short loc_10134194
0x10134179  cmp     byte ptr [esi+0E6h], 0
0x10134180  mov     this, offset aUtf8_0; "UTF8"
0x10134185  mov     eax, offset aAcp; "ACP"
0x1013418a  cmovnz  eax, this
0x1013418d  push    eax; LevelKeyword
0x1013418e  push    this; _a1
0x1013418f  call    _WPP_SF_s@16; WPP_SF_s(x,x,x,x)
0x10134194  cmp     byte ptr [esi+0E1h], 0
0x1013419b  jz      short loc_101341C0
0x1013419d  test    byte_10185758, 8; __annotation("TMF:",
0x101341a4  jz      short loc_101341BA
0x101341a6  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101341ab  mov     edx, 0C9h; id
0x101341b0  mov     this, 303h; LevelKeyword
0x101341b5  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x101341ba  or      dword ptr [edi], 1800h
0x101341c0  cmp     dword ptr [esi+0DCh], 1
0x101341c7  jnz     short loc_101341F6
0x101341c9  test    byte_10185758, 8; __annotation("TMF:",
0x101341d0  jz      short loc_101341E6
0x101341d2  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101341d7  mov     edx, 0CAh; id
0x101341dc  mov     this, 303h; LevelKeyword
0x101341e1  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x101341e6  or      dword ptr [ebx+24h], 10000h
0x101341ed  mov     dword ptr [ebx+28h], 40000h
0x101341f4  jmp     short loc_101341FD
0x101341f6  or      dword ptr [ebx+24h], 800000h
0x101341fd  cmp     byte ptr [esi+0E4h], 0
0x10134204  jz      short loc_10134226
0x10134206  test    byte_10185758, 8; __annotation("TMF:",
0x1013420d  jz      short loc_10134223
0x1013420f  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10134214  mov     edx, 0CBh; id
0x10134219  mov     this, 303h; LevelKeyword
0x1013421e  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x10134223  or      dword ptr [edi], 30h
0x10134226  mov     dword ptr [ebx+14h], 3
0x1013422d  mov     edx, offset aGet; "GET"
0x10134232  mov     this, [esi+18h]; dst
0x10134235  call    ?fastcmpi@@YGHPBG0@Z; fastcmpi(ushort const *,ushort const *)
0x1013423a  test    eax, eax
0x1013423c  jnz     short loc_10134246
0x1013423e  mov     [ebx+18h], eax
0x10134241  jmp     loc_10134323
0x10134246  mov     this, [esi+18h]; dst
0x10134249  mov     edx, offset aPost; "POST"
0x1013424e  call    ?fastcmpi@@YGHPBG0@Z; fastcmpi(ushort const *,ushort const *)
0x10134253  test    eax, eax
0x10134255  jnz     short loc_10134283
0x10134257  mov     dword ptr [ebx+18h], 1
0x1013425e  test    byte_10185758, 8; __annotation("TMF:",
0x10134265  jz      short loc_1013427B
0x10134267  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013426c  mov     edx, 0CCh; id
0x10134271  mov     this, 303h; LevelKeyword
0x10134276  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x1013427b  or      dword ptr [edi], 20h
0x1013427e  jmp     loc_10134323
0x10134283  mov     this, [esi+18h]; dst
0x10134286  mov     edx, offset aPut; "PUT"
0x1013428b  call    ?fastcmpi@@YGHPBG0@Z; fastcmpi(ushort const *,ushort const *)
0x10134290  test    eax, eax
0x10134292  jnz     short loc_101342A0
0x10134294  mov     dword ptr [ebx+18h], 2
0x1013429b  jmp     loc_10134323
0x101342a0  mov     this, [esi+18h]; psz
0x101342a3  mov     edx, 7FFFFFFFh; cchMax
0x101342a8  call    ?xstrlenw@@YGHPBGI@Z; xstrlenw(ushort const *,uint)
0x101342ad  lea     this, [eax+1]
0x101342b0  cmp     this, eax
0x101342b2  jb      loc_10134450
0x101342b8  push    2
0x101342ba  mov     eax, this
0x101342bc  mov     [esp+74h+cbCustomVerb], this
0x101342c0  pop     this
0x101342c1  mul     this
0x101342c3  lea     this, [esp+70h+cbCustomVerb]; puResult
0x101342c7  push    edx
0x101342c8  push    eax; ullOperand
0x101342c9  call    ?ULongLongToUInt@@YGJ_KPAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x101342ce  test    eax, eax
0x101342d0  js      loc_10134450
0x101342d6  cmp     [esp+70h+cbCustomVerb], 7FFFFFFFh
0x101342de  ja      loc_10134450
0x101342e4  push    [esp+70h+cbCustomVerb]; cb
0x101342e8  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x101342ee  mov     [ebx+1Ch], eax
0x101342f1  test    eax, eax
0x101342f3  jnz     short loc_10134302
0x101342f5  mov     [esp+70h+cbCustomVerb], 8007000Eh
0x101342fd  jmp     CleanUp_466
0x10134302  push    dword ptr [esi+18h]; pszSrc
0x10134305  mov     edx, [esp+74h+cbCustomVerb]; cbDest
0x10134309  mov     this, eax; pszDest
0x1013430b  call    ?StringCbCopyW@@YGJPAGIPBG@Z; StringCbCopyW(ushort *,uint,ushort const *)
0x10134310  mov     [esp+70h+cbCustomVerb], eax
0x10134314  test    eax, eax
0x10134316  js      CleanUp_466
0x1013431c  mov     dword ptr [ebx+18h], 3
0x10134323  cmp     dword ptr [esi+48h], 0
0x10134327  lea     eax, [esi+48h]
0x1013432a  mov     [esp+70h+ppref], eax
0x1013432e  jz      loc_10134428
0x10134334  mov     edi, eax
0x10134336  mov     edx, [edi]
0x10134338  xor     this, this
0x1013433a  push    this
0x1013433b  push    this
0x1013433c  push    this
0x1013433d  mov     eax, [edx]
0x1013433f  xor     esi, esi
0x10134341  push    esi
0x10134342  push    edx
0x10134343  mov     edi, [eax+14h]
0x10134346  mov     this, edi; this
0x10134348  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013434e  call    edi
0x10134350  test    eax, eax
0x10134352  jns     short loc_10134372
0x10134354  test    byte_10185750, 8; __annotation("TMF:",
0x1013435b  jz      short loc_10134372
0x1013435d  push    eax; _a1
0x1013435e  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10134363  mov     edx, 0CDh; id
0x10134368  mov     this, 203h; LevelKeyword
0x1013436d  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10134372  push    48h ; 'H'; Size
0x10134374  lea     eax, [esp+74h+sg]
0x10134378  push    0; Val
0x1013437a  push    eax; void *
0x1013437b  call    _memset
0x10134380  mov     edi, [esp+7Ch+ppref]
0x10134384  add     esp, 0Ch
0x10134387  mov     this, [edi]
0x10134389  push    0
0x1013438b  mov     eax, [this]
0x1013438d  mov     esi, [eax+30h]
0x10134390  lea     eax, [esp+74h+sg]
0x10134394  push    eax
0x10134395  push    this
0x10134396  mov     this, esi; this
0x10134398  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013439e  call    esi
0x101343a0  mov     this, eax
0x101343a2  mov     [esp+70h+cbCustomVerb], this
0x101343a6  test    this, this
0x101343a8  jz      short loc_101343F5
0x101343aa  mov     this, [edi]; pStream
0x101343ac  lea     edx, [esp+70h+pcs]; ppNewStream
0x101343b0  mov     [esp+70h+pcs], 0
0x101343b8  call    ?NewFromStream@CachingStreamForExternal@@SGJPAUIStream@@PAPAV1@@Z; CachingStreamForExternal::NewFromStream(IStream *,CachingStreamForExternal * *)
0x101343bd  mov     [esp+70h+cbCustomVerb], eax
0x101343c1  test    eax, eax
0x101343c3  js      short loc_10134424
0x101343c5  mov     edx, [esp+70h+pcs]; pref
0x101343c9  test    edx, edx
0x101343cb  jz      short loc_10134424
0x101343cd  mov     this, edi; ppref
0x101343cf  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x101343d4  mov     this, [esp+70h+pcs]
0x101343d8  test    this, this
0x101343da  jz      setSendBody
0x101343e0  mov     eax, [this]
0x101343e2  push    this
0x101343e3  mov     esi, [eax+8]
0x101343e6  mov     this, esi; this
0x101343e8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101343ee  call    esi
0x101343f0  jmp     setSendBody
0x101343f5  mov     eax, dword ptr [esp+70h+sg.cbSize]
0x101343f9  or      eax, dword ptr [esp+70h+sg.cbSize+4]
0x101343fd  jz      short loc_10134424
0x101343ff  mov     eax, [edi]
0x10134401  push    eax
0x10134402  mov     this, [eax]
0x10134404  mov     esi, [this+4]
0x10134407  mov     this, esi; this
0x10134409  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013440f  call    esi
0x10134411  mov     dword ptr [ebx+8], 4
0x10134418  mov     eax, [edi]
0x1013441a  mov     [ebx+0Ch], eax
0x1013441d  mov     eax, dword ptr [esp+70h+sg.cbSize]
0x10134421  mov     [ebx+20h], eax
0x10134424  mov     edi, [esp+70h+var_60]
0x10134428  test    byte_10185760, 8; __annotation("TMF:",
0x1013442f  jz      short CleanUp_466
0x10134431  push    dword ptr [ebx+20h]; LevelKeyword
0x10134434  push    dword ptr [ebx+0Ch]; _a8
0x10134437  push    dword ptr [ebx+8]; _a7
0x1013443a  push    dword ptr [ebx+18h]; _a6
0x1013443d  push    dword ptr [ebx+14h]; _a5
0x10134440  push    dword ptr [ebx+28h]; _a4
0x10134443  push    dword ptr [ebx+24h]; _a3
0x10134446  push    dword ptr [edi]; _a2
0x10134448  push    this; _a1
0x10134449  call    _WPP_SF_DDDDdDqD@44; WPP_SF_DDDDdDqD(x,x,x,x,x,x,x,x,x,x,x)
0x1013444e  jmp     short CleanUp_466
0x10134450  mov     [esp+70h+cbCustomVerb], 80070216h
0x10134458  mov     ebx, [esp+70h+var_58]
0x1013445c  mov     eax, [ebx]
0x1013445e  mov     esi, [eax+80h]
0x10134464  mov     this, esi; this
0x10134466  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013446c  mov     this, ebx
0x1013446e  call    esi
0x10134470  mov     ebx, [esp+70h+cbCustomVerb]; __annotation("TMF:",
0x10134474  mov     this, ebx
0x10134476  sar     this, 1Fh
0x10134479  mov     eax, this
0x1013447b  shl     eax, 4
0x1013447e  test    byte_10185760[eax], 8
  ... truncated ...
```
