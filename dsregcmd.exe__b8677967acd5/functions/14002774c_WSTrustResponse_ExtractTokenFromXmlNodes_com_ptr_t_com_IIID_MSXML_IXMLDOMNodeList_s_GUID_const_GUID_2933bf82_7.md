# WSTrustResponse::ExtractTokenFromXmlNodes(_com_ptr_t<_com_IIID<MSXML::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x14002774c`
- end: `0x140027d79`
- name: `?ExtractTokenFromXmlNodes@WSTrustResponse@@AEBA?AVCSecureString@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1581`
- prototype: `__int64 *__fastcall(__int64, __int64 *, struct IUnknown **, struct IUnknown *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140027534`

## callees

- `0x140001b60`
- `0x1400032ec`
- `0x1400054e8`
- `0x1400061dc`
- `0x14000813c`
- `0x14000be04`
- `0x14000caac`
- `0x14000e6a0`
- `0x140012850`
- `0x140018d0c`
- `0x1400193b4`
- `0x140019a5c`
- `0x140019af4`
- `0x14001c244`
- `0x140026e08`
- `0x14002774c`
- `0x14002c070`
- `0x14002c084`
- `0x14002c3d0`
- `0x14002c3e8`
- `0x140030010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x140027884`
- `OLEAUT32!__imp_SysStringLen` at `0x1400278ef`
- `OLEAUT32!__imp_SysStringLen` at `0x1400278fb`
- `OLEAUT32!__imp_SysStringLen` at `0x140027884`
- `OLEAUT32!__imp_SysStringLen` at `0x1400278ef`
- `OLEAUT32!__imp_SysStringLen` at `0x1400278fb`

## string_xrefs

- `0x140027aa1`: `urn:ietf:params:oauth:token-type:jwt`
- `0x140027990`: `trust:RequestedSecurityToken`
- `0x140027a09`: `trust2005:RequestedSecurityToken`

## pseudocode

```c
__int64 *__fastcall WSTrustResponse::ExtractTokenFromXmlNodes(
        __int64 a1,
        __int64 *a2,
        struct IUnknown **a3,
        struct IUnknown *a4)
{
  const unsigned __int16 **v4; // r15
  int v6; // ebx
  struct IUnknown *v7; // rdi
  int v8; // r12d
  int v9; // eax
  struct IUnknown *v10; // rdi
  int v11; // eax
  struct IUnknown *v12; // rdi
  _bstr_t *v13; // rax
  BSTR *v14; // rsi
  OLECHAR **v15; // r14
  OLECHAR *v16; // rcx
  UINT v17; // eax
  char v18; // si
  UINT v19; // r15d
  UINT v20; // eax
  UINT v21; // ecx
  OLECHAR *v22; // rdx
  BSTR v23; // r8
  bool v24; // cf
  bool v25; // zf
  int v26; // eax
  struct IUnknown *v27; // rsi
  int v28; // ebx
  struct IUnknown *v29; // r14
  int v30; // eax
  struct IUnknown *v31; // rsi
  struct IUnknown **v32; // rax
  int v33; // eax
  struct IUnknown *v34; // rsi
  __int64 **v35; // rax
  __int64 v36; // rdx
  _QWORD *v37; // rdx
  __int64 v38; // rbx
  __int64 v39; // r8
  __int128 *v40; // rdx
  __int64 v41; // r8
  __int64 *v42; // rbx
  __int64 **v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rbx
  __int64 v46; // r8
  struct IUnknown *v48; // [rsp+20h] [rbp-99h] BYREF
  int v49; // [rsp+28h] [rbp-91h]
  struct IUnknown *v50; // [rsp+30h] [rbp-89h] BYREF
  __int64 v51; // [rsp+38h] [rbp-81h] BYREF
  _QWORD v52[2]; // [rsp+40h] [rbp-79h] BYREF
  OLECHAR **v53; // [rsp+50h] [rbp-69h] BYREF
  __int64 *v54; // [rsp+58h] [rbp-61h]
  struct IUnknown *v55; // [rsp+60h] [rbp-59h]
  char v56[8]; // [rsp+68h] [rbp-51h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+70h] [rbp-49h] BYREF
  __int128 v58; // [rsp+80h] [rbp-39h] BYREF
  __int64 v59; // [rsp+90h] [rbp-29h]
  __int64 *v60; // [rsp+98h] [rbp-21h]
  struct IUnknown **v61; // [rsp+A0h] [rbp-19h]
  struct IUnknown *v62; // [rsp+A8h] [rbp-11h]
  __int128 v63; // [rsp+B0h] [rbp-9h] BYREF
  __m128i si128; // [rsp+C0h] [rbp+7h]

  v4 = (const unsigned __int16 **)a4;
  v48 = a4;
  v54 = a2;
  v60 = a2;
  v61 = a3;
  v49 = 0;
  *a2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v6 = 1;
  v49 = 1;
  v7 = *a3;
  if ( !*a3 )
  {
    ArgumentException::ArgumentException((ArgumentException *)pExceptionObject, -894894061);
    throw (ArgumentException *)pExceptionObject;
  }
  v8 = 0;
  while ( 1 )
  {
    LODWORD(v50) = 0;
    v9 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v7->lpVtbl[2].Release)(v7, &v50);
    if ( v9 < 0 )
      _com_issue_errorex(v9, v7, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
    if ( v8 >= (int)v50 )
      break;
    v10 = *a3;
    if ( !*a3 )
      goto LABEL_76;
    v50 = 0;
    v11 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct IUnknown **))v10->lpVtbl[2].AddRef)(
            v10,
            (unsigned int)v8,
            &v50);
    if ( v11 < 0 )
      _com_issue_errorex(v11, v10, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
    v12 = v50;
    v62 = v50;
    v6 |= 2u;
    v49 = v6;
    if ( !v50 )
      _com_issue_error(-2147467261);
    MSXML::IXMLDOMNode::Gettext(v50, &v53);
    v13 = _bstr_t::_bstr_t((_bstr_t *)&v51, *v4);
    v14 = *(BSTR **)v13;
    v15 = v53;
    if ( v53 == *(OLECHAR ***)v13 )
    {
LABEL_15:
      v18 = 1;
      goto LABEL_16;
    }
    if ( !v53 )
    {
      if ( !v14 )
        goto LABEL_15;
      v16 = *v14;
      if ( *v14 )
        goto LABEL_12;
      v17 = 0;
      goto LABEL_14;
    }
    v16 = *v53;
    if ( !v14 )
    {
      if ( !v16 )
        goto LABEL_15;
LABEL_12:
      v17 = SysStringLen(v16);
LABEL_14:
      if ( !v17 )
        goto LABEL_15;
      goto LABEL_33;
    }
    v19 = SysStringLen(v16);
    v20 = SysStringLen(*v14);
    v21 = v19;
    if ( v19 > v20 )
      v21 = v20;
    v22 = *v15;
    v23 = *v14;
    if ( v21 )
    {
      while ( *v22 == *v23 )
      {
        ++v23;
        ++v22;
        if ( !--v21 )
          goto LABEL_29;
      }
      v4 = (const unsigned __int16 **)v48;
    }
    else
    {
LABEL_29:
      v24 = v19 < v20;
      v25 = v19 == v20;
      v4 = (const unsigned __int16 **)v48;
      if ( !v24 && v25 )
        goto LABEL_15;
    }
LABEL_33:
    v18 = 0;
LABEL_16:
    _bstr_t::~_bstr_t((_bstr_t *)&v51);
    if ( v18 )
    {
      if ( !v12 )
        _com_issue_error(-2147467261);
      v48 = 0;
      v26 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v12->lpVtbl[3].Release)(v12, &v48);
      if ( v26 < 0 )
        _com_issue_errorex(v26, v12, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
      v27 = v48;
      v52[0] = v48;
      v28 = v6 | 4;
      v49 = v28;
      if ( !v48 )
        _com_issue_error(-2147467261);
      _bstr_t::_bstr_t((_bstr_t *)&v51, L"trust:RequestedSecurityToken");
      MSXML::IXMLDOMNode::selectSingleNode(v27);
      ((void (__fastcall *)(struct IUnknown *))v27->lpVtbl->Release)(v27);
      v29 = v55;
      if ( !v55 )
      {
        v48 = 0;
        v30 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v12->lpVtbl[3].Release)(v12, &v48);
        if ( v30 < 0 )
          _com_issue_errorex(v30, v12, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
        v31 = v48;
        v28 |= 8u;
        v49 = v28;
        if ( !v48 )
          _com_issue_error(-2147467261);
        _bstr_t::_bstr_t((_bstr_t *)v56, L"trust2005:RequestedSecurityToken");
        v32 = (struct IUnknown **)MSXML::IXMLDOMNode::selectSingleNode(v31);
        if ( *v32 )
        {
          v29 = *v32;
          v55 = *v32;
          *v32 = 0;
        }
        if ( v52[0] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v52[0] + 16LL))(v52[0]);
        ((void (__fastcall *)(struct IUnknown *))v31->lpVtbl->Release)(v31);
        if ( !v29 )
        {
          Exception::Exception((Exception *)pExceptionObject, -894894061);
          throw (Exception *)pExceptionObject;
        }
      }
      v48 = 0;
      v33 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v29->lpVtbl[4].AddRef)(v29, &v48);
      if ( v33 < 0 )
        _com_issue_errorex(v33, v29, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
      v34 = v48;
      pExceptionObject[0] = v48;
      v49 = v28 | 0x10;
      if ( !v48 )
      {
        Exception::Exception((Exception *)v52, -894894061);
        throw (Exception *)v52;
      }
      if ( !wcscmp_0(*v4, L"urn:ietf:params:oauth:token-type:jwt") )
      {
        v58 = 0;
        v59 = 0;
        v35 = (__int64 **)MSXML::IXMLDOMNode::Gettext(v34, v52);
        if ( *v35 )
          v36 = **v35;
        else
          v36 = 0;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v51,
          v36);
        StringUtility::Base64UrlDecode(&v51, &v58);
        v37 = (_QWORD *)(v51 - 24);
        v38 = -1;
        if ( _InterlockedDecrement((volatile signed __int32 *)(v51 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v37 + 8LL))(*v37);
        _bstr_t::~_bstr_t((_bstr_t *)v52);
        v63 = 0;
        si128 = 0;
        if ( (_QWORD)v58 == *((_QWORD *)&v58 + 1) )
        {
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v63) = 0;
        }
        else
        {
          std::wstring::_Construct_from_iter<unsigned char *,unsigned char *,unsigned __int64>(
            &v63,
            v58,
            v39,
            *((_QWORD *)&v58 + 1) - v58);
        }
        if ( si128.m128i_i64[1] <= 7uLL )
        {
          v40 = &v63;
        }
        else
        {
          v40 = (__int128 *)v63;
          if ( !(_QWORD)v63 )
          {
            LODWORD(v38) = 0;
            goto LABEL_61;
          }
        }
        do
          ++v38;
        while ( *((_WORD *)v40 + v38) );
LABEL_61:
        v41 = (unsigned int)v38;
        v42 = v54;
        ATL::CSimpleStringT<unsigned short,0>::Append(v54, (__int64)v40, v41);
        std::wstring::~wstring((char **)&v63);
        std::vector<unsigned char>::~vector<unsigned char>((char **)&v58);
        v12 = v50;
        v34 = v48;
LABEL_70:
        ((void (__fastcall *)(struct IUnknown *))v34->lpVtbl->Release)(v34);
        ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
        _bstr_t::~_bstr_t((_bstr_t *)&v53);
        ((void (__fastcall *)(struct IUnknown *))v12->lpVtbl->Release)(v12);
        goto LABEL_72;
      }
      v43 = (__int64 **)MSXML::IXMLDOMNode::Getxml(v34, v52);
      if ( *v43 )
      {
        v44 = **v43;
        if ( v44 )
        {
          v45 = -1;
          do
            ++v45;
          while ( *(_WORD *)(v44 + 2 * v45) );
          goto LABEL_69;
        }
      }
      else
      {
        v44 = 0;
      }
      LODWORD(v45) = 0;
LABEL_69:
      v46 = (unsigned int)v45;
      v42 = v54;
      ATL::CSimpleStringT<unsigned short,0>::SetString(v54, v44, v46);
      _bstr_t::~_bstr_t((_bstr_t *)v52);
      goto LABEL_70;
    }
    _bstr_t::~_bstr_t((_bstr_t *)&v53);
    if ( v12 )
      ((void (__fastcall *)(struct IUnknown *))v12->lpVtbl->Release)(v12);
    ++v8;
    v7 = *a3;
    if ( !*a3 )
LABEL_76:
      _com_issue_error(-2147467261);
  }
  v42 = v54;
LABEL_72:
  if ( *a3 )
    ((void (__fastcall *)(struct IUnknown *))(*a3)->lpVtbl->Release)(*a3);
  return v42;
}

```

## disassembly

```asm
0x14002774c  mov     [rsp-8+arg_0], rbx
0x140027751  push    rbp
0x140027752  push    rsi
0x140027753  push    rdi
0x140027754  push    r12
0x140027756  push    r13
0x140027758  push    r14
0x14002775a  push    r15
0x14002775c  lea     rbp, [rsp-27h]
0x140027761  sub     rsp, 0E0h
0x140027768  mov     rax, cs:__security_cookie
0x14002776f  xor     rax, rsp
0x140027772  mov     [rbp+57h+var_40], rax
0x140027776  mov     r15, r9
0x140027779  mov     [rsp+110h+var_F0], r9
0x14002777e  mov     r13, r8
0x140027781  mov     rsi, rdx
0x140027784  mov     [rbp+57h+var_B8], rdx
0x140027788  mov     [rbp+57h+var_78], rdx
0x14002778c  mov     [rbp+57h+var_70], r8
0x140027790  mov     [rsp+110h+var_E8], 0
0x140027798  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002779f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400277a6  mov     rax, [rax+18h]
0x1400277aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400277af  add     rax, 18h
0x1400277b3  mov     [rsi], rax
0x1400277b6  mov     ebx, 1
0x1400277bb  mov     [rsp+110h+var_E8], ebx
0x1400277bf  mov     rdi, [r13+0]
0x1400277c3  test    rdi, rdi
0x1400277c6  jz      loc_140027CBA
0x1400277cc  xor     r12d, r12d
0x1400277cf  mov     dword ptr [rsp+110h+var_E0], 0
0x1400277d7  mov     rax, [rdi]
0x1400277da  lea     rdx, [rsp+110h+var_E0]
0x1400277df  mov     rcx, rdi
0x1400277e2  mov     rax, [rax+40h]
0x1400277e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400277eb  test    eax, eax
0x1400277ed  js      loc_140027CA8
0x1400277f3  cmp     r12d, dword ptr [rsp+110h+var_E0]
0x1400277f8  jge     loc_140027C47
0x1400277fe  mov     rdi, [r13+0]
0x140027802  test    rdi, rdi
0x140027805  jz      loc_140027C9D
0x14002780b  mov     [rsp+110h+var_E0], 0
0x140027814  mov     rax, [rdi]
0x140027817  lea     r8, [rsp+110h+var_E0]
0x14002781c  mov     edx, r12d
0x14002781f  mov     rcx, rdi
0x140027822  mov     rax, [rax+38h]
0x140027826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002782b  test    eax, eax
0x14002782d  js      loc_140027C8B
0x140027833  mov     rdi, [rsp+110h+var_E0]
0x140027838  mov     [rbp+57h+var_68], rdi
0x14002783c  or      ebx, 2
0x14002783f  mov     [rsp+110h+var_E8], ebx
0x140027843  test    rdi, rdi
0x140027846  jz      loc_140027D6E
0x14002784c  lea     rdx, [rbp+57h+var_C0]
0x140027850  mov     rcx, rdi
0x140027853  call    ?Gettext@IXMLDOMNode@MSXML@@QEAA?AV_bstr_t@@XZ; MSXML::IXMLDOMNode::Gettext(void)
0x140027858  nop
0x140027859  mov     rdx, [r15]; unsigned __int16 *
0x14002785c  lea     rcx, [rsp+110h+var_D8]; this
0x140027861  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140027866  mov     rsi, [rax]
0x140027869  mov     r14, [rbp+57h+var_C0]
0x14002786d  cmp     r14, rsi
0x140027870  jz      short loc_140027896
0x140027872  test    r14, r14
0x140027875  jnz     short loc_1400278E0
0x140027877  test    rsi, rsi
0x14002787a  jz      short loc_140027896
0x14002787c  mov     rcx, [rsi]; pbstr
0x14002787f  test    rcx, rcx
0x140027882  jz      short loc_14002788C
0x140027884  call    cs:__imp_SysStringLen
0x14002788a  jmp     short loc_14002788E
0x14002788c  xor     eax, eax
0x14002788e  test    eax, eax
0x140027890  jnz     loc_140027942
0x140027896  mov     sil, 1
0x140027899  lea     rcx, [rsp+110h+var_D8]; this
0x14002789e  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1400278a3  test    sil, sil
0x1400278a6  jnz     loc_14002794A
0x1400278ac  lea     rcx, [rbp+57h+var_C0]; this
0x1400278b0  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1400278b5  nop
0x1400278b6  test    rdi, rdi
0x1400278b9  jz      short loc_1400278CB
0x1400278bb  mov     rax, [rdi]
0x1400278be  mov     rcx, rdi
0x1400278c1  mov     rax, [rax+10h]
0x1400278c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400278ca  nop
0x1400278cb  inc     r12d
0x1400278ce  mov     rdi, [r13+0]
0x1400278d2  test    rdi, rdi
0x1400278d5  jz      loc_140027C9D
0x1400278db  jmp     loc_1400277CF
0x1400278e0  mov     rcx, [r14]; pbstr
0x1400278e3  test    rsi, rsi
0x1400278e6  jnz     short loc_1400278EF
0x1400278e8  test    rcx, rcx
0x1400278eb  jz      short loc_140027896
0x1400278ed  jmp     short loc_140027884
0x1400278ef  call    cs:__imp_SysStringLen
0x1400278f5  mov     r15d, eax
0x1400278f8  mov     rcx, [rsi]; pbstr
0x1400278fb  call    cs:__imp_SysStringLen
0x140027901  mov     ecx, r15d
0x140027904  cmp     r15d, eax
0x140027907  cmova   ecx, eax
0x14002790a  mov     rdx, [r14]
0x14002790d  mov     r8, [rsi]
0x140027910  test    ecx, ecx
0x140027912  jz      short loc_14002792B
0x140027914  movzx   r9d, word ptr [rdx]
0x140027918  cmp     r9w, [r8]
0x14002791c  jnz     short loc_14002793D
0x14002791e  add     r8, 2
0x140027922  add     rdx, 2
0x140027926  add     ecx, 0FFFFFFFFh
0x140027929  jnz     short loc_140027914
0x14002792b  cmp     r15d, eax
0x14002792e  mov     r15, [rsp+110h+var_F0]
0x140027933  jb      short loc_140027942
0x140027935  jz      loc_140027896
0x14002793b  jmp     short loc_140027942
0x14002793d  mov     r15, [rsp+110h+var_F0]
0x140027942  xor     sil, sil
0x140027945  jmp     loc_140027899
0x14002794a  xor     r12d, r12d
0x14002794d  test    rdi, rdi
0x140027950  jz      loc_140027D63
0x140027956  mov     [rsp+110h+var_F0], r12
0x14002795b  mov     rax, [rdi]
0x14002795e  lea     rdx, [rsp+110h+var_F0]
0x140027963  mov     rcx, rdi
0x140027966  mov     rax, [rax+58h]
0x14002796a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002796f  test    eax, eax
0x140027971  js      loc_140027CD9
0x140027977  mov     rsi, [rsp+110h+var_F0]
0x14002797c  mov     [rbp+57h+var_D0], rsi
0x140027980  or      ebx, 4
0x140027983  mov     [rsp+110h+var_E8], ebx
0x140027987  test    rsi, rsi
0x14002798a  jz      loc_140027D58
0x140027990  lea     rdx, aTrustRequested; "trust:RequestedSecurityToken"
0x140027997  lea     rcx, [rsp+110h+var_D8]; this
0x14002799c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1400279a1  mov     r8, rax
0x1400279a4  lea     rdx, [rbp+57h+var_B0]
0x1400279a8  mov     rcx, rsi; struct IUnknown *
0x1400279ab  call    ?selectSingleNode@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNode::selectSingleNode(_bstr_t)
0x1400279b0  nop
0x1400279b1  mov     rax, [rsi]
0x1400279b4  mov     rcx, rsi
0x1400279b7  mov     rax, [rax+10h]
0x1400279bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400279c0  nop
0x1400279c1  mov     r14, [rbp+57h+var_B0]
0x1400279c5  test    r14, r14
0x1400279c8  jnz     loc_140027A67
0x1400279ce  mov     [rsp+110h+var_F0], r12
0x1400279d3  mov     rax, [rdi]
0x1400279d6  lea     rdx, [rsp+110h+var_F0]
0x1400279db  mov     rcx, rdi
0x1400279de  mov     rax, [rax+58h]
0x1400279e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400279e7  test    eax, eax
0x1400279e9  js      loc_140027CEB
0x1400279ef  mov     rsi, [rsp+110h+var_F0]
0x1400279f4  mov     [rsp+110h+var_F0], rsi
0x1400279f9  or      ebx, 8
0x1400279fc  mov     [rsp+110h+var_E8], ebx
0x140027a00  test    rsi, rsi
0x140027a03  jz      loc_140027D1C
0x140027a09  lea     rdx, aTrust2005Reque; "trust2005:RequestedSecurityToken"
0x140027a10  lea     rcx, [rbp+57h+var_A8]; this
0x140027a14  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140027a19  mov     r8, rax
0x140027a1c  lea     rdx, [rbp+57h+var_D0]
0x140027a20  mov     rcx, rsi; struct IUnknown *
0x140027a23  call    ?selectSingleNode@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNode::selectSingleNode(_bstr_t)
0x140027a28  nop
0x140027a29  cmp     [rax], r12
0x140027a2c  jz      short loc_140027A38
0x140027a2e  mov     r14, [rax]
0x140027a31  mov     [rbp+57h+var_B0], r14
0x140027a35  mov     [rax], r12
0x140027a38  mov     rcx, [rbp+57h+var_D0]
0x140027a3c  test    rcx, rcx
0x140027a3f  jz      short loc_140027A4E
0x140027a41  mov     rax, [rcx]
0x140027a44  mov     rax, [rax+10h]
0x140027a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027a4d  nop
0x140027a4e  mov     rax, [rsi]
0x140027a51  mov     rcx, rsi
0x140027a54  mov     rax, [rax+10h]
0x140027a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027a5d  nop
0x140027a5e  test    r14, r14
0x140027a61  jz      loc_140027CFD
0x140027a67  mov     [rsp+110h+var_F0], r12
0x140027a6c  mov     rax, [r14]
0x140027a6f  lea     rdx, [rsp+110h+var_F0]
0x140027a74  mov     rcx, r14
0x140027a77  mov     rax, [rax+68h]
0x140027a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027a80  test    eax, eax
0x140027a82  js      loc_140027D27
0x140027a88  mov     rsi, [rsp+110h+var_F0]
0x140027a8d  mov     [rbp+57h+pExceptionObject], rsi
0x140027a91  or      ebx, 10h
0x140027a94  mov     [rsp+110h+var_E8], ebx
0x140027a98  test    rsi, rsi
0x140027a9b  jz      loc_140027D39
0x140027aa1  lea     rdx, aUrnIetfParamsO_0; "urn:ietf:params:oauth:token-type:jwt"
0x140027aa8  mov     rcx, [r15]; String1
0x140027aab  call    wcscmp_0
0x140027ab0  nop
0x140027ab1  test    eax, eax
0x140027ab3  jnz     loc_140027BBE
0x140027ab9  xorps   xmm0, xmm0
0x140027abc  movdqu  [rbp+57h+var_90], xmm0
0x140027ac1  mov     [rbp+57h+var_80], r12
0x140027ac5  lea     rdx, [rbp+57h+var_D0]
0x140027ac9  mov     rcx, rsi
0x140027acc  call    ?Gettext@IXMLDOMNode@MSXML@@QEAA?AV_bstr_t@@XZ; MSXML::IXMLDOMNode::Gettext(void)
0x140027ad1  nop
0x140027ad2  mov     rdx, [rax]
0x140027ad5  test    rdx, rdx
0x140027ad8  jz      short loc_140027ADF
0x140027ada  mov     rdx, [rdx]
0x140027add  jmp     short loc_140027AE2
0x140027adf  mov     rdx, r12
0x140027ae2  lea     rcx, [rsp+110h+var_D8]
0x140027ae7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140027aec  nop
0x140027aed  lea     rdx, [rbp+57h+var_90]
0x140027af1  lea     rcx, [rsp+110h+var_D8]
0x140027af6  call    ?Base64UrlDecode@StringUtility@@SAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; StringUtility::Base64UrlDecode(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::vector<uchar> &)
0x140027afb  nop
0x140027afc  mov     rdx, [rsp+110h+var_D8]
0x140027b01  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140027b05  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140027b09  mov     eax, ebx
0x140027b0b  lock xadd [rdx+10h], eax
0x140027b10  add     eax, ebx
0x140027b12  test    eax, eax
0x140027b14  jg      short loc_140027B26
0x140027b16  mov     rcx, [rdx]
0x140027b19  mov     rax, [rcx]
0x140027b1c  mov     rax, [rax+8]
0x140027b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027b25  nop
0x140027b26  lea     rcx, [rbp+57h+var_D0]; this
0x140027b2a  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x140027b2f  mov     r9, qword ptr [rbp+57h+var_90+8]
0x140027b33  mov     rdx, qword ptr [rbp+57h+var_90]
0x140027b37  xorps   xmm0, xmm0
0x140027b3a  movups  [rbp+57h+var_60], xmm0
0x140027b3e  xorps   xmm1, xmm1
0x140027b41  movdqu  [rbp+57h+var_50], xmm1
0x140027b46  cmp     rdx, r9
0x140027b49  jnz     short loc_140027B5F
0x140027b4b  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140027b53  movdqu  [rbp+57h+var_50], xmm0
0x140027b58  mov     word ptr [rbp+57h+var_60], r12w
0x140027b5d  jmp     short loc_140027B6C
0x140027b5f  sub     r9, rdx
0x140027b62  lea     rcx, [rbp+57h+var_60]
0x140027b66  call    ??$_Construct_from_iter@PEAEPEAE_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXPEAEQEAE_K@Z; std::wstring::_Construct_from_iter<uchar *,uchar *,unsigned __int64>(uchar *,uchar * const,unsigned __int64)
0x140027b6b  nop
0x140027b6c  cmp     qword ptr [rbp+57h+var_50+8], 7
0x140027b71  jbe     short loc_140027B81
0x140027b73  mov     rdx, qword ptr [rbp+57h+var_60]
0x140027b77  test    rdx, rdx
0x140027b7a  jnz     short loc_140027B85
0x140027b7c  mov     ebx, r12d
0x140027b7f  jmp     short loc_140027B8F
0x140027b81  lea     rdx, [rbp+57h+var_60]
0x140027b85  inc     rbx
0x140027b88  cmp     [rdx+rbx*2], r12w
0x140027b8d  jnz     short loc_140027B85
0x140027b8f  mov     r8d, ebx
0x140027b92  mov     rbx, [rbp+57h+var_B8]
0x140027b96  mov     rcx, rbx
0x140027b99  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x140027b9e  nop
0x140027b9f  lea     rcx, [rbp+57h+var_60]
0x140027ba3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140027ba8  nop
  ... truncated ...
```
