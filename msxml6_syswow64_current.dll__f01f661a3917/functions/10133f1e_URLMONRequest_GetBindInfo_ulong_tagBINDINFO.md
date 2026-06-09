# URLMONRequest::GetBindInfo(ulong *,_tagBINDINFO *)

- ea: `0x10133f1e`
- end: `0x101343a6`
- name: `?GetBindInfo@URLMONRequest@@IAEJPAKPAU_tagBINDINFO@@@Z`
- size: `1160`
- prototype: `HRESULT __thiscall(URLMONRequest *this, unsigned int *grfBINDF, _tagBINDINFO *pbindinfo)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x101343b0`
- `0x101343d3`

## callees

- `0x1003fba3`
- `0x1004118e`
- `0x1004fc3e`
- `0x10067bc0`
- `0x1006b510`
- `0x1006c354`
- `0x100786f8`
- `0x1012ee4a`
- `0x10133f1e`
- `0x10135946`
- `0x10180006`
- `0x10180060`
- `0x10180c5f`
- `0x1018142e`
- `0x10181506`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x101341d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x101341d8`

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
  if ( (byte_101857A0[0] & 8) != 0 )
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
    if ( (byte_101857A0[0] & 8) != 0 )
      WPP_SF_(0x403u, 0xC4u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
  }
  if ( v6->_fDisableLegacyFeatures )
  {
    if ( (byte_101857A0[0] & 8) != 0 )
      WPP_SF_(0x403u, 0xC5u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    grfBINDF->Data1 |= 0x20000000u;
    if ( (byte_101857A0[0] & 8) != 0 )
      WPP_SF_(0x403u, 0xC6u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    pbindinfo->dwOptions |= 0x20000000u;
    if ( (byte_101857A0[0] & 8) != 0 )
      WPP_SF_(0x403u, 0xC7u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    pbindinfo->dwOptions |= 0x20000u;
  }
  pbindinfo->dwCodePage = 0;
  if ( v6->_fQueryStringInUtf8 )
    pbindinfo->dwCodePage = 65001;
  if ( (byte_101857A0[0] & 8) != 0 )
  {
    v7 = "ACP";
    if ( v6->_fQueryStringInUtf8 )
      v7 = "UTF8";
    WPP_SF_s((unsigned __int16)"UTF8", (unsigned __int16)v7, v18, (const char *)v19);
  }
  if ( v6->_fDisableUI )
  {
    if ( (byte_10185798 & 8) != 0 )
      WPP_SF_(0x303u, 0xC9u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids);
    grfBINDF->Data1 |= 0x1800u;
  }
  if ( v6->_dwAuth == 1 )
  {
    if ( (byte_10185798 & 8) != 0 )
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
    if ( (byte_10185798 & 8) != 0 )
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
        if ( v13 < 0 && (byte_10185790 & 8) != 0 )
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
    if ( (byte_101857A0[0] & 8) != 0 )
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
    if ( (byte_10185798 & 8) != 0 )
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
  if ( (byte_101857A0[16 * ((int)cbCustomVerb >> 31)] & 8) != 0 )
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
0x10133f1e  mov     edi, edi
0x10133f20  push    ebp
0x10133f21  mov     ebp, esp
0x10133f23  and     esp, 0FFFFFFF8h
0x10133f26  sub     esp, 64h
0x10133f29  mov     eax, ___security_cookie
0x10133f2e  xor     eax, esp
0x10133f30  mov     [esp+64h+var_4], eax
0x10133f34  push    ebx
0x10133f35  mov     ebx, [ebp+pbindinfo]
0x10133f38  xor     eax, eax
0x10133f3a  push    esi; TraceGuid
0x10133f3b  push    edi; id
0x10133f3c  mov     edi, [ebp+grfBINDF]
0x10133f3f  mov     esi, this
0x10133f41  mov     [esp+70h+var_58], esi
0x10133f45  mov     [esp+70h+var_60], edi
0x10133f49  mov     [esp+70h+cbCustomVerb], eax
0x10133f4d  test    byte_101857A0, 8; __annotation("TMF:",
0x10133f54  jz      short loc_10133F61
0x10133f56  push    ebx; LevelKeyword
0x10133f57  push    dword ptr [edi]; _a4
0x10133f59  push    edi; _a3
0x10133f5a  push    esi; _a2
0x10133f5b  push    this; _a1
0x10133f5c  call    _WPP_SF_qqDq@28; WPP_SF_qqDq(x,x,x,x,x,x,x)
0x10133f61  mov     eax, [esi]
0x10133f63  mov     esi, [eax+7Ch]
0x10133f66  mov     this, esi; this
0x10133f68  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10133f6e  mov     this, [esp+70h+var_58]
0x10133f72  call    esi
0x10133f74  mov     esi, ?g_pfnEntry@@3P6GPAUTLSDATA@@XZA; TLSDATA * (*g_pfnEntry)(void)
0x10133f7a  mov     this, esi; this
0x10133f7c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10133f82  call    esi ; TLSDATA * (*g_pfnEntry)(void)
0x10133f84  test    eax, eax
0x10133f86  jnz     short loc_10133F95
0x10133f88  mov     [esp+70h+cbCustomVerb], 80004005h
0x10133f90  jmp     CleanUp_466
0x10133f95  mov     dword ptr [edi], 0
0x10133f9b  mov     esi, [ebx]
0x10133f9d  push    esi; Size
0x10133f9e  push    0; Val
0x10133fa0  push    ebx; void *
0x10133fa1  call    _memset
0x10133fa6  mov     [ebx], esi
0x10133fa8  add     esp, 0Ch
0x10133fab  mov     esi, [esp+70h+var_58]
0x10133faf  cmp     dword ptr [esi+64h], 0
0x10133fb3  jnz     short loc_10133FD8
0x10133fb5  mov     dword ptr [edi], 100000h
0x10133fbb  test    byte_101857A0, 8; __annotation("TMF:",
0x10133fc2  jz      short loc_10133FD8
0x10133fc4  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10133fc9  mov     edx, 0C4h; id
0x10133fce  mov     this, 403h; LevelKeyword
0x10133fd3  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x10133fd8  cmp     dword ptr [esi+60h], 0
0x10133fdc  jz      short loc_10134049
0x10133fde  test    byte_101857A0, 8; __annotation("TMF:",
0x10133fe5  jz      short loc_10133FFB
0x10133fe7  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10133fec  mov     edx, 0C5h; id
0x10133ff1  mov     this, 403h; LevelKeyword
0x10133ff6  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x10133ffb  or      dword ptr [edi], 20000000h
0x10134001  test    byte_101857A0, 8; __annotation("TMF:",
0x10134008  jz      short loc_1013401E
0x1013400a  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013400f  mov     edx, 0C6h; id
0x10134014  mov     this, 403h; LevelKeyword
0x10134019  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x1013401e  or      dword ptr [ebx+24h], 20000000h
0x10134025  test    byte_101857A0, 8; __annotation("TMF:",
0x1013402c  jz      short loc_10134042
0x1013402e  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10134033  mov     edx, 0C7h; id
0x10134038  mov     this, 403h; LevelKeyword
0x1013403d  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x10134042  or      dword ptr [ebx+24h], 20000h
0x10134049  mov     dword ptr [ebx+2Ch], 0
0x10134050  cmp     byte ptr [esi+0E6h], 0
0x10134057  jz      short loc_10134060
0x10134059  mov     dword ptr [ebx+2Ch], 0FDE9h
0x10134060  test    byte_101857A0, 8; __annotation("TMF:",
0x10134067  jz      short loc_10134084
0x10134069  cmp     byte ptr [esi+0E6h], 0
0x10134070  mov     this, offset aUtf8_0; "UTF8"
0x10134075  mov     eax, offset aAcp; "ACP"
0x1013407a  cmovnz  eax, this
0x1013407d  push    eax; LevelKeyword
0x1013407e  push    this; _a1
0x1013407f  call    _WPP_SF_s@16; WPP_SF_s(x,x,x,x)
0x10134084  cmp     byte ptr [esi+0E1h], 0
0x1013408b  jz      short loc_101340B0
0x1013408d  test    byte_10185798, 8; __annotation("TMF:",
0x10134094  jz      short loc_101340AA
0x10134096  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013409b  mov     edx, 0C9h; id
0x101340a0  mov     this, 303h; LevelKeyword
0x101340a5  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x101340aa  or      dword ptr [edi], 1800h
0x101340b0  cmp     dword ptr [esi+0DCh], 1
0x101340b7  jnz     short loc_101340E6
0x101340b9  test    byte_10185798, 8; __annotation("TMF:",
0x101340c0  jz      short loc_101340D6
0x101340c2  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101340c7  mov     edx, 0CAh; id
0x101340cc  mov     this, 303h; LevelKeyword
0x101340d1  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x101340d6  or      dword ptr [ebx+24h], 10000h
0x101340dd  mov     dword ptr [ebx+28h], 40000h
0x101340e4  jmp     short loc_101340ED
0x101340e6  or      dword ptr [ebx+24h], 800000h
0x101340ed  cmp     byte ptr [esi+0E4h], 0
0x101340f4  jz      short loc_10134116
0x101340f6  test    byte_10185798, 8; __annotation("TMF:",
0x101340fd  jz      short loc_10134113
0x101340ff  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10134104  mov     edx, 0CBh; id
0x10134109  mov     this, 303h; LevelKeyword
0x1013410e  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x10134113  or      dword ptr [edi], 30h
0x10134116  mov     dword ptr [ebx+14h], 3
0x1013411d  mov     edx, offset aGet; "GET"
0x10134122  mov     this, [esi+18h]; dst
0x10134125  call    ?fastcmpi@@YGHPBG0@Z; fastcmpi(ushort const *,ushort const *)
0x1013412a  test    eax, eax
0x1013412c  jnz     short loc_10134136
0x1013412e  mov     [ebx+18h], eax
0x10134131  jmp     loc_10134213
0x10134136  mov     this, [esi+18h]; dst
0x10134139  mov     edx, offset aPost; "POST"
0x1013413e  call    ?fastcmpi@@YGHPBG0@Z; fastcmpi(ushort const *,ushort const *)
0x10134143  test    eax, eax
0x10134145  jnz     short loc_10134173
0x10134147  mov     dword ptr [ebx+18h], 1
0x1013414e  test    byte_10185798, 8; __annotation("TMF:",
0x10134155  jz      short loc_1013416B
0x10134157  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013415c  mov     edx, 0CCh; id
0x10134161  mov     this, 303h; LevelKeyword
0x10134166  call    _WPP_SF_@12; WPP_SF_(x,x,x)
0x1013416b  or      dword ptr [edi], 20h
0x1013416e  jmp     loc_10134213
0x10134173  mov     this, [esi+18h]; dst
0x10134176  mov     edx, offset aPut; "PUT"
0x1013417b  call    ?fastcmpi@@YGHPBG0@Z; fastcmpi(ushort const *,ushort const *)
0x10134180  test    eax, eax
0x10134182  jnz     short loc_10134190
0x10134184  mov     dword ptr [ebx+18h], 2
0x1013418b  jmp     loc_10134213
0x10134190  mov     this, [esi+18h]; psz
0x10134193  mov     edx, 7FFFFFFFh; cchMax
0x10134198  call    ?xstrlenw@@YGHPBGI@Z; xstrlenw(ushort const *,uint)
0x1013419d  lea     this, [eax+1]
0x101341a0  cmp     this, eax
0x101341a2  jb      loc_10134340
0x101341a8  push    2
0x101341aa  mov     eax, this
0x101341ac  mov     [esp+74h+cbCustomVerb], this
0x101341b0  pop     this
0x101341b1  mul     this
0x101341b3  lea     this, [esp+70h+cbCustomVerb]; puResult
0x101341b7  push    edx
0x101341b8  push    eax; ullOperand
0x101341b9  call    ?ULongLongToUInt@@YGJ_KPAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x101341be  test    eax, eax
0x101341c0  js      loc_10134340
0x101341c6  cmp     [esp+70h+cbCustomVerb], 7FFFFFFFh
0x101341ce  ja      loc_10134340
0x101341d4  push    [esp+70h+cbCustomVerb]; cb
0x101341d8  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x101341de  mov     [ebx+1Ch], eax
0x101341e1  test    eax, eax
0x101341e3  jnz     short loc_101341F2
0x101341e5  mov     [esp+70h+cbCustomVerb], 8007000Eh
0x101341ed  jmp     CleanUp_466
0x101341f2  push    dword ptr [esi+18h]; pszSrc
0x101341f5  mov     edx, [esp+74h+cbCustomVerb]; cbDest
0x101341f9  mov     this, eax; pszDest
0x101341fb  call    ?StringCbCopyW@@YGJPAGIPBG@Z; StringCbCopyW(ushort *,uint,ushort const *)
0x10134200  mov     [esp+70h+cbCustomVerb], eax
0x10134204  test    eax, eax
0x10134206  js      CleanUp_466
0x1013420c  mov     dword ptr [ebx+18h], 3
0x10134213  cmp     dword ptr [esi+48h], 0
0x10134217  lea     eax, [esi+48h]
0x1013421a  mov     [esp+70h+ppref], eax
0x1013421e  jz      loc_10134318
0x10134224  mov     edi, eax
0x10134226  mov     edx, [edi]
0x10134228  xor     this, this
0x1013422a  push    this
0x1013422b  push    this
0x1013422c  push    this
0x1013422d  mov     eax, [edx]
0x1013422f  xor     esi, esi
0x10134231  push    esi
0x10134232  push    edx
0x10134233  mov     edi, [eax+14h]
0x10134236  mov     this, edi; this
0x10134238  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013423e  call    edi
0x10134240  test    eax, eax
0x10134242  jns     short loc_10134262
0x10134244  test    byte_10185790, 8; __annotation("TMF:",
0x1013424b  jz      short loc_10134262
0x1013424d  push    eax; _a1
0x1013424e  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10134253  mov     edx, 0CDh; id
0x10134258  mov     this, 203h; LevelKeyword
0x1013425d  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10134262  push    48h ; 'H'; Size
0x10134264  lea     eax, [esp+74h+sg]
0x10134268  push    0; Val
0x1013426a  push    eax; void *
0x1013426b  call    _memset
0x10134270  mov     edi, [esp+7Ch+ppref]
0x10134274  add     esp, 0Ch
0x10134277  mov     this, [edi]
0x10134279  push    0
0x1013427b  mov     eax, [this]
0x1013427d  mov     esi, [eax+30h]
0x10134280  lea     eax, [esp+74h+sg]
0x10134284  push    eax
0x10134285  push    this
0x10134286  mov     this, esi; this
0x10134288  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013428e  call    esi
0x10134290  mov     this, eax
0x10134292  mov     [esp+70h+cbCustomVerb], this
0x10134296  test    this, this
0x10134298  jz      short loc_101342E5
0x1013429a  mov     this, [edi]; pStream
0x1013429c  lea     edx, [esp+70h+pcs]; ppNewStream
0x101342a0  mov     [esp+70h+pcs], 0
0x101342a8  call    ?NewFromStream@CachingStreamForExternal@@SGJPAUIStream@@PAPAV1@@Z; CachingStreamForExternal::NewFromStream(IStream *,CachingStreamForExternal * *)
0x101342ad  mov     [esp+70h+cbCustomVerb], eax
0x101342b1  test    eax, eax
0x101342b3  js      short loc_10134314
0x101342b5  mov     edx, [esp+70h+pcs]; pref
0x101342b9  test    edx, edx
0x101342bb  jz      short loc_10134314
0x101342bd  mov     this, edi; ppref
0x101342bf  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x101342c4  mov     this, [esp+70h+pcs]
0x101342c8  test    this, this
0x101342ca  jz      setSendBody
0x101342d0  mov     eax, [this]
0x101342d2  push    this
0x101342d3  mov     esi, [eax+8]
0x101342d6  mov     this, esi; this
0x101342d8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101342de  call    esi
0x101342e0  jmp     setSendBody
0x101342e5  mov     eax, dword ptr [esp+70h+sg.cbSize]
0x101342e9  or      eax, dword ptr [esp+70h+sg.cbSize+4]
0x101342ed  jz      short loc_10134314
0x101342ef  mov     eax, [edi]
0x101342f1  push    eax
0x101342f2  mov     this, [eax]
0x101342f4  mov     esi, [this+4]
0x101342f7  mov     this, esi; this
0x101342f9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101342ff  call    esi
0x10134301  mov     dword ptr [ebx+8], 4
0x10134308  mov     eax, [edi]
0x1013430a  mov     [ebx+0Ch], eax
0x1013430d  mov     eax, dword ptr [esp+70h+sg.cbSize]
0x10134311  mov     [ebx+20h], eax
0x10134314  mov     edi, [esp+70h+var_60]
0x10134318  test    byte_101857A0, 8; __annotation("TMF:",
0x1013431f  jz      short CleanUp_466
0x10134321  push    dword ptr [ebx+20h]; LevelKeyword
0x10134324  push    dword ptr [ebx+0Ch]; _a8
0x10134327  push    dword ptr [ebx+8]; _a7
0x1013432a  push    dword ptr [ebx+18h]; _a6
0x1013432d  push    dword ptr [ebx+14h]; _a5
0x10134330  push    dword ptr [ebx+28h]; _a4
0x10134333  push    dword ptr [ebx+24h]; _a3
0x10134336  push    dword ptr [edi]; _a2
0x10134338  push    this; _a1
0x10134339  call    _WPP_SF_DDDDdDqD@44; WPP_SF_DDDDdDqD(x,x,x,x,x,x,x,x,x,x,x)
0x1013433e  jmp     short CleanUp_466
0x10134340  mov     [esp+70h+cbCustomVerb], 80070216h
0x10134348  mov     ebx, [esp+70h+var_58]
0x1013434c  mov     eax, [ebx]
0x1013434e  mov     esi, [eax+80h]
0x10134354  mov     this, esi; this
0x10134356  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013435c  mov     this, ebx
0x1013435e  call    esi
0x10134360  mov     ebx, [esp+70h+cbCustomVerb]; __annotation("TMF:",
0x10134364  mov     this, ebx
0x10134366  sar     this, 1Fh
0x10134369  mov     eax, this
0x1013436b  shl     eax, 4
0x1013436e  test    byte_101857A0[eax], 8
  ... truncated ...
```
