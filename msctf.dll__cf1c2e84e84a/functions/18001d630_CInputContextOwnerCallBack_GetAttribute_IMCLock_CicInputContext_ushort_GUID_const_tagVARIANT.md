# CInputContextOwnerCallBack::GetAttribute(IMCLock &,CicInputContext &,ushort,_GUID const *,tagVARIANT *)

- ea: `0x18001d630`
- end: `0x18001de40`
- name: `?GetAttribute@CInputContextOwnerCallBack@@AEAAJAEAVIMCLock@@AEAVCicInputContext@@GPEBU_GUID@@PEAUtagVARIANT@@@Z`
- size: `2064`
- prototype: `__int64 __fastcall(CInputContextOwnerCallBack *__hidden this, struct IMCLock *, struct CicInputContext *, unsigned __int16, const struct _GUID *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bbd0`

## callees

- `0x180018640`
- `0x18001d630`
- `0x18002a828`
- `0x180039c40`
- `0x180044464`
- `0x18004f1c8`
- `0x180053e2c`
- `0x1800831b8`
- `0x18009eaea`
- `0x18009eb02`
- `0x1800d99a0`
- `0x1800e6ddc`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d9dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ddc8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ddeb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d9dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ddc8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ddeb`
- `USER32!IsWindow` at `0x18001d726`
- `USER32!IsWindow` at `0x18001d726`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ddb6`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ddb6`
- `OLEAUT32!__imp_VariantClear` at `0x18001da55`
- `OLEAUT32!__imp_VariantClear` at `0x18001da55`
- `ext-ms-win-imm-l1-1-0!ImmGetCompositionFontW` at `0x18001d933`
- `ext-ms-win-imm-l1-1-0!ImmGetCompositionFontW` at `0x18001dd9e`
- `ext-ms-win-imm-l1-1-0!ImmGetCompositionFontW` at `0x18001d933`
- `ext-ms-win-imm-l1-1-0!ImmGetCompositionFontW` at `0x18001dd9e`

## pseudocode

```c
__int64 __fastcall CInputContextOwnerCallBack::GetAttribute(
        CInputContextOwnerCallBack *this,
        struct IMCLock *a2,
        struct CicInputContext *a3,
        __int16 a4,
        const struct _GUID *a5,
        struct tagVARIANT *a6)
{
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  HWND *v15; // rax
  HWND v16; // rbx
  struct tagSYSTHREAD *SYSTHREAD; // rax
  __int64 v18; // rcx
  CImeInputScope *v19; // rax
  __int64 result; // rax
  __int64 v21; // rcx
  char v22; // r15
  void (__fastcall **v23)(_QWORD, GUID *, __int64 *); // rax
  LPARAM v24; // rcx
  int v25; // eax
  LONGLONG llVal; // rcx
  int v27; // edi
  HIMC v28; // rcx
  bool v29; // zf
  int v30; // ebx
  int v31; // r13d
  const struct _GUID *p_Buf1; // rax
  int v33; // ebx
  CImeInputScope *v34; // rax
  enum __MIDL___MIDL_itf_inputscope_0000_0000_0001 v35; // edx
  unsigned int (__fastcall ***v36)(_QWORD, GUID *, LPARAM *); // rax
  char *v37; // rsi
  __int64 v38; // rax
  int v39; // ecx
  int v40; // edx
  HIMC v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rdi
  CImeInputScope *v44; // rax
  LPARAM lParam; // [rsp+20h] [rbp-A9h] BYREF
  __int64 v46; // [rsp+28h] [rbp-A1h] BYREF
  unsigned int v47; // [rsp+30h] [rbp-99h] BYREF
  __int64 v48; // [rsp+38h] [rbp-91h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-89h] BYREF
  __int128 Buf1; // [rsp+58h] [rbp-71h] BYREF
  tagLOGFONTW lf; // [rsp+70h] [rbp-59h] BYREF

  v47 = 0;
  a6->vt = 0;
  v10 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_PROP_MODEBIAS.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_PROP_MODEBIAS.Data1 )
    v10 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_PROP_MODEBIAS.Data4;
  if ( v10 )
  {
    v11 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&TSATTRID_Text_Orientation.Data1;
    if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&TSATTRID_Text_Orientation.Data1 )
      v11 = *(_QWORD *)a5->Data4 - *(_QWORD *)TSATTRID_Text_Orientation.Data4;
    if ( !v11 )
    {
      if ( !CBackingStore::GetBackingStoreAttribute(*((struct ITfContext **)this + 8), a5, a6) )
      {
        v41 = (HIMC)*((_QWORD *)a2 + 2);
        LODWORD(lParam) = 0;
        UIComposition::SendMessageToUI(v41, 0x11u, (LPARAM)&lParam);
        v29 = (_DWORD)lParam == 1;
        a6->vt = 3;
        if ( v29 )
          a6->lVal = 0;
        else
          a6->lVal = *(_DWORD *)(*((_QWORD *)a2 + 1) + 44LL);
      }
      return 0;
    }
    v12 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&TSATTRID_Text_VerticalWriting.Data1;
    if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&TSATTRID_Text_VerticalWriting.Data1 )
      v12 = *(_QWORD *)a5->Data4 - *(_QWORD *)TSATTRID_Text_VerticalWriting.Data4;
    if ( v12 )
    {
      v13 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&TSATTRID_Font_FaceName.Data1;
      if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&TSATTRID_Font_FaceName.Data1 )
        v13 = *(_QWORD *)a5->Data4 - *(_QWORD *)TSATTRID_Font_FaceName.Data4;
      if ( !v13 )
      {
        memset_0(&lf, 0, sizeof(lf));
        if ( ImmGetCompositionFontW(*((HIMC *)a2 + 2), &lf) )
        {
          a6->vt = 8;
          v19 = (CImeInputScope *)SysAllocString(lf.lfFaceName);
LABEL_120:
          a6->llVal = (LONGLONG)v19;
        }
        return 0;
      }
      v14 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_PROP_INPUTSCOPE.Data1;
      if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_PROP_INPUTSCOPE.Data1 )
        v14 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_PROP_INPUTSCOPE.Data4;
      if ( v14 )
        return 0;
      v15 = (HWND *)*((_QWORD *)a2 + 1);
      lParam = 0;
      v16 = *v15;
      if ( IsWindow(*v15) )
      {
        SYSTHREAD = GetSYSTHREAD();
        if ( SYSTHREAD )
        {
          v18 = *((_QWORD *)SYSTHREAD + 26);
          if ( v18 )
          {
            v36 = (unsigned int (__fastcall ***)(_QWORD, GUID *, LPARAM *))CPtrMap<HWND__ *,CInputScope>::_Find(
                                                                             v18,
                                                                             v16);
            if ( v36 )
            {
              if ( !(**v36)(v36, &IID_ITfInputScope, &lParam) )
              {
                v19 = (CImeInputScope *)lParam;
                goto LABEL_119;
              }
            }
          }
        }
      }
      switch ( *((_DWORD *)a3 + 46) )
      {
        case 1:
          v44 = (CImeInputScope *)LocalAlloc(0x40u, 0x10u);
          if ( v44 )
          {
            v19 = CImeInputScope::CImeInputScope(v44, IS_FILE_FULLFILEPATH);
            if ( v19 )
              goto LABEL_119;
          }
          break;
        case 4:
          v34 = (CImeInputScope *)LocalAlloc(0x40u, 0x10u);
          if ( v34 )
          {
            v35 = IS_DIGITS;
LABEL_57:
            v19 = CImeInputScope::CImeInputScope(v34, v35);
            if ( v19 )
              goto LABEL_119;
          }
          break;
        case 0x10000:
          v34 = (CImeInputScope *)LocalAlloc(0x40u, 0x10u);
          if ( !v34 )
            return 2147942414LL;
          v35 = IS_URL;
          goto LABEL_57;
        default:
          v19 = (CImeInputScope *)lParam;
          if ( !lParam )
            return 0;
LABEL_119:
          a6->vt = 13;
          goto LABEL_120;
      }
      return 2147942414LL;
    }
    v21 = *((_QWORD *)this + 8);
    v22 = 0;
    *(_QWORD *)&Buf1 = 0;
    if ( (*(int (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v21 + 128LL))(v21, &Buf1) < 0 )
      goto LABEL_44;
    if ( !(_QWORD)Buf1 )
    {
LABEL_47:
      v28 = (HIMC)*((_QWORD *)a2 + 2);
      memset(&lf, 0, sizeof(lf));
      if ( ImmGetCompositionFontW(v28, &lf) )
      {
        v29 = lf.lfFaceName[0] == 64;
        a6->vt = 11;
        a6->lVal = v29;
      }
      return 0;
    }
    v48 = 0;
    v23 = *(void (__fastcall ***)(_QWORD, GUID *, __int64 *))Buf1;
    v46 = 0;
    (*v23)(Buf1, &GUID_7dcf57ac_18ad_438b_824d_979bffb74b7c, &v46);
    v24 = 0;
    lParam = 0;
    if ( v46 )
    {
      if ( (*(int (__fastcall **)(__int64, GUID *, LPARAM *))(*(_QWORD *)v46 + 24LL))(
             v46,
             &GUID_COMPARTMENT_TRANSITORYEXTENSION_PARENT,
             &lParam) < 0 )
      {
LABEL_34:
        v24 = lParam;
        goto LABEL_35;
      }
      v24 = lParam;
      if ( lParam )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        v25 = (*(__int64 (__fastcall **)(LPARAM, VARIANTARG *))(*(_QWORD *)lParam + 32LL))(lParam, &pvarg);
        llVal = pvarg.llVal;
        if ( v25 >= 0 && pvarg.vt == 13 && pvarg.llVal )
        {
          (**(void (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(
            pvarg.llVal,
            &GUID_4c074926_9ddd_4d5e_bdc9_1be08660be14,
            &v48);
          llVal = pvarg.llVal;
        }
        if ( pvarg.vt != 11 )
        {
          if ( pvarg.vt == 13 )
          {
            if ( llVal )
              (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)llVal + 16LL))(llVal);
          }
          else
          {
            switch ( pvarg.vt )
            {
              case 0u:
              case 1u:
              case 2u:
              case 3u:
              case 4u:
              case 5u:
              case 6u:
              case 7u:
              case 0x10u:
              case 0x11u:
              case 0x12u:
              case 0x13u:
              case 0x14u:
              case 0x15u:
              case 0x16u:
              case 0x17u:
                goto LABEL_34;
              default:
                VariantClear(&pvarg);
                break;
            }
          }
        }
        goto LABEL_34;
      }
    }
LABEL_35:
    v27 = -2147467259;
    if ( v48 )
      v27 = 0;
    if ( v24 )
      (*(void (__fastcall **)(LPARAM))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v27 >= 0 )
    {
      ATL::CComQIPtr<ITfDocumentMgr,&__s_GUID const _GUID_aa80e7f4_2021_11d2_93e0_0060b067b86e>::CComQIPtr<ITfDocumentMgr,&__s_GUID const _GUID_aa80e7f4_2021_11d2_93e0_0060b067b86e>(
        &v46,
        v48);
      if ( v46 )
      {
        v42 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 72LL))(v48);
        v43 = v42;
        if ( v42 )
        {
          if ( (*(unsigned __int8 (__fastcall **)(__int64, const struct _GUID *))(*(_QWORD *)v42 + 264LL))(v42, a5) )
            v22 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, struct tagVARIANT *))(*(_QWORD *)v43 + 272LL))(
                    v43,
                    a5,
                    a6);
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
    }
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
LABEL_44:
    if ( (_QWORD)Buf1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)Buf1 + 16LL))(Buf1);
    if ( v22 )
      return 0;
    goto LABEL_47;
  }
  v30 = *((_DWORD *)a3 + 63);
  *((_DWORD *)a3 + 63) = v30 & 0xFFFFFFFE;
  v31 = *((_DWORD *)a3 + 64);
  Buf1 = *(_OWORD *)((char *)a3 + 168);
  if ( (v31 & 1) == 0 )
    return 0;
  if ( *((_DWORD *)a3 + 66) )
  {
    p_Buf1 = &GUID_NULL;
    v33 = 1;
    lParam = (LPARAM)&GUID_NULL;
  }
  else
  {
    v33 = v30 << 31 >> 31;
    if ( !memcmp_0(&Buf1, &GUID_MODEBIAS_NONE, 0x10u) )
    {
      LODWORD(lParam) = 0;
      CanCurrentKeyboardTIPHandleInputModeCompartment((int *)&lParam);
      if ( (_DWORD)lParam )
      {
        result = 0;
        a6->vt = 0;
        return result;
      }
      if ( !memcmp_0(&Buf1, &GUID_MODEBIAS_NONE, 0x10u) )
      {
        v38 = *((_QWORD *)a2 + 1);
        v37 = (char *)a2 + 8;
        v39 = *(_DWORD *)(v38 + 28);
        if ( (v39 & 2) != 0 )
        {
          p_Buf1 = &GUID_MODEBIAS_KATAKANA;
          if ( (v39 & 8) == 0 )
            p_Buf1 = &GUID_MODEBIAS_HALFWIDTHKATAKANA;
          lParam = (LPARAM)p_Buf1;
        }
        else if ( (v39 & 1) != 0 )
        {
          if ( a4 == 1041 )
          {
            p_Buf1 = &GUID_MODEBIAS_HIRAGANA;
            if ( (v39 & 8) == 0 )
              p_Buf1 = &GUID_MODEBIAS_HALFWIDTHALPHANUMERIC;
          }
          else if ( a4 == 1042 )
          {
            p_Buf1 = &GUID_MODEBIAS_FULLWIDTHHANGUL;
            if ( (v39 & 8) == 0 )
              p_Buf1 = &GUID_MODEBIAS_HANGUL;
          }
          else
          {
            p_Buf1 = &GUID_MODEBIAS_CHINESE;
            if ( (a4 & 0x3FF) != 4 )
              p_Buf1 = &GUID_MODEBIAS_HALFWIDTHALPHANUMERIC;
          }
          lParam = (LPARAM)p_Buf1;
        }
        else if ( (v39 & 8) != 0 )
        {
          p_Buf1 = &GUID_MODEBIAS_FULLWIDTHALPHANUMERIC;
          lParam = (LPARAM)&GUID_MODEBIAS_FULLWIDTHALPHANUMERIC;
        }
        else
        {
          p_Buf1 = &GUID_MODEBIAS_HALFWIDTHALPHANUMERIC;
          lParam = (LPARAM)&GUID_MODEBIAS_HALFWIDTHALPHANUMERIC;
        }
      }
      else
      {
        p_Buf1 = 0;
        lParam = 0;
        v37 = (char *)a2 + 8;
      }
      if ( !*((_DWORD *)a3 + 65) )
      {
        v40 = *(_DWORD *)(*(_QWORD *)v37 + 32LL);
        if ( (v40 & 0x10008) != 65544 && (v40 & 0x10) == 0 )
        {
          if ( (v40 & 1) != 0 )
          {
            p_Buf1 = &GUID_MODEBIAS_NAME;
            lParam = (LPARAM)&GUID_MODEBIAS_NAME;
          }
          else
          {
            p_Buf1 = (const struct _GUID *)lParam;
          }
        }
        else
        {
          p_Buf1 = &GUID_MODEBIAS_CONVERSATION;
          lParam = (LPARAM)&GUID_MODEBIAS_CONVERSATION;
        }
      }
    }
    else if ( !memcmp_0(&Buf1, &GUID_MODEBIAS_DEFAULT, 0x10u) )
    {
      p_Buf1 = &GUID_NULL;
      lParam = (LPARAM)&GUID_NULL;
      v33 = 1;
      *(GUID *)((char *)a3 + 168) = GUID_MODEBIAS_NONE;
      *((_DWORD *)a3 + 64) = v31 & 0xFFFFFFFE;
    }
    else
    {
      p_Buf1 = (const struct _GUID *)&Buf1;
      lParam = (LPARAM)&Buf1;
    }
  }
  if ( (unsigned int)GetGUIDATOMFromGUID(*((struct tag_LIBTHREAD **)this + 10), p_Buf1, &v47) )
  {
    if ( memcmp_0((const void *)lParam, &GUID_NULL, 0x10u) || v33 )
    {
      a6->lVal = v47;
      a6->vt = 3;
    }
    return 0;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18001d630  mov     [rsp-8+arg_18], rbx
0x18001d635  push    rbp
0x18001d636  push    rsi
0x18001d637  push    rdi
0x18001d638  push    r12
0x18001d63a  push    r13
0x18001d63c  push    r14
0x18001d63e  push    r15
0x18001d640  lea     rbp, [rsp-17h]
0x18001d645  sub     rsp, 0E0h
0x18001d64c  mov     rax, cs:__security_cookie
0x18001d653  xor     rax, rsp
0x18001d656  mov     [rbp+47h+var_40], rax
0x18001d65a  mov     r14, [rbp+47h+arg_28]
0x18001d65e  xor     r13d, r13d
0x18001d661  mov     rbx, [rbp+47h+arg_20]
0x18001d665  movzx   r12d, r9w
0x18001d669  mov     rdi, r8
0x18001d66c  mov     [rsp+110h+var_E0], r13d
0x18001d671  mov     rsi, rdx
0x18001d674  mov     r15, rcx
0x18001d677  mov     [r14], r13w
0x18001d67b  mov     rax, [rbx]
0x18001d67e  sub     rax, qword ptr cs:GUID_PROP_MODEBIAS.Data1
0x18001d685  jnz     short loc_18001D692
0x18001d687  mov     rax, [rbx+8]
0x18001d68b  sub     rax, qword ptr cs:GUID_PROP_MODEBIAS.Data4
0x18001d692  test    rax, rax
0x18001d695  jz      loc_18001D95B
0x18001d69b  mov     rax, [rbx]
0x18001d69e  sub     rax, qword ptr cs:TSATTRID_Text_Orientation.Data1
0x18001d6a5  jnz     short loc_18001D6B2
0x18001d6a7  mov     rax, [rbx+8]
0x18001d6ab  sub     rax, qword ptr cs:TSATTRID_Text_Orientation.Data4
0x18001d6b2  test    rax, rax
0x18001d6b5  jz      loc_18001DCA2
0x18001d6bb  mov     rax, [rbx]
0x18001d6be  sub     rax, qword ptr cs:TSATTRID_Text_VerticalWriting.Data1
0x18001d6c5  jnz     short loc_18001D6D2
0x18001d6c7  mov     rax, [rbx+8]
0x18001d6cb  sub     rax, qword ptr cs:TSATTRID_Text_VerticalWriting.Data4
0x18001d6d2  test    rax, rax
0x18001d6d5  jz      loc_18001D7A5
0x18001d6db  mov     rax, [rbx]
0x18001d6de  sub     rax, qword ptr cs:TSATTRID_Font_FaceName.Data1
0x18001d6e5  jnz     short loc_18001D6F2
0x18001d6e7  mov     rax, [rbx+8]
0x18001d6eb  sub     rax, qword ptr cs:TSATTRID_Font_FaceName.Data4
0x18001d6f2  test    rax, rax
0x18001d6f5  jz      loc_18001DD85
0x18001d6fb  mov     rax, [rbx]
0x18001d6fe  sub     rax, qword ptr cs:GUID_PROP_INPUTSCOPE.Data1
0x18001d705  jnz     short loc_18001D712
0x18001d707  mov     rax, [rbx+8]
0x18001d70b  sub     rax, qword ptr cs:GUID_PROP_INPUTSCOPE.Data4
0x18001d712  test    rax, rax
0x18001d715  jnz     short loc_18001D77C
0x18001d717  mov     rax, [rdx+8]
0x18001d71b  mov     [rsp+110h+lParam], r13
0x18001d720  mov     rbx, [rax]
0x18001d723  mov     rcx, rbx; hWnd
0x18001d726  call    cs:__imp_IsWindow
0x18001d72c  test    eax, eax
0x18001d72e  jz      short loc_18001D74A
0x18001d730  call    ?GetSYSTHREAD@@YAPEAUtagSYSTHREAD@@XZ; GetSYSTHREAD(void)
0x18001d735  test    rax, rax
0x18001d738  jz      short loc_18001D74A
0x18001d73a  mov     rcx, [rax+0D0h]
0x18001d741  test    rcx, rcx
0x18001d744  jnz     loc_18001DA07
0x18001d74a  mov     ecx, [rdi+0B8h]
0x18001d750  sub     ecx, 1
0x18001d753  jz      loc_18001DDE1
0x18001d759  sub     ecx, 3
0x18001d75c  jz      loc_18001D9D2
0x18001d762  cmp     ecx, 0FFFCh
0x18001d768  jz      loc_18001DDBE
0x18001d76e  mov     rax, [rsp+110h+lParam]
0x18001d773  test    rax, rax
0x18001d776  jnz     loc_18001DE10
0x18001d77c  xor     eax, eax
0x18001d77e  mov     rcx, [rbp+47h+var_40]
0x18001d782  xor     rcx, rsp; StackCookie
0x18001d785  call    __security_check_cookie
0x18001d78a  mov     rbx, [rsp+110h+arg_18]
0x18001d792  add     rsp, 0E0h
0x18001d799  pop     r15
0x18001d79b  pop     r14
0x18001d79d  pop     r13
0x18001d79f  pop     r12
0x18001d7a1  pop     rdi
0x18001d7a2  pop     rsi
0x18001d7a3  pop     rbp
0x18001d7a4  retn
0x18001d7a5  mov     rcx, [rcx+40h]
0x18001d7a9  lea     rdx, [rbp+47h+Buf1]
0x18001d7ad  xor     r15b, r15b
0x18001d7b0  mov     qword ptr [rbp+47h+Buf1], r13
0x18001d7b4  mov     rax, [rcx]
0x18001d7b7  mov     rax, [rax+80h]
0x18001d7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7c3  test    eax, eax
0x18001d7c5  js      loc_18001D8F2
0x18001d7cb  mov     rcx, qword ptr [rbp+47h+Buf1]
0x18001d7cf  test    rcx, rcx
0x18001d7d2  jz      loc_18001D910
0x18001d7d8  mov     [rsp+110h+var_D8], r13
0x18001d7dd  lea     r8, [rsp+110h+var_E8]
0x18001d7e2  mov     rax, [rcx]
0x18001d7e5  lea     rdx, _GUID_7dcf57ac_18ad_438b_824d_979bffb74b7c
0x18001d7ec  mov     [rsp+110h+var_E8], r13
0x18001d7f1  mov     rax, [rax]
0x18001d7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7f9  mov     r9, [rsp+110h+var_E8]
0x18001d7fe  mov     rcx, r13
0x18001d801  mov     [rsp+110h+lParam], rcx
0x18001d806  test    r9, r9
0x18001d809  jz      loc_18001D89C
0x18001d80f  mov     rax, [r9]
0x18001d812  lea     r8, [rsp+110h+lParam]
0x18001d817  lea     rdx, GUID_COMPARTMENT_TRANSITORYEXTENSION_PARENT
0x18001d81e  mov     rcx, r9
0x18001d821  mov     rax, [rax+18h]
0x18001d825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d82a  test    eax, eax
0x18001d82c  js      short loc_18001D897; jumptable 000000018001DD10 cases 0-7,16-23
0x18001d82e  mov     rcx, [rsp+110h+lParam]
0x18001d833  test    rcx, rcx
0x18001d836  jz      short loc_18001D89C
0x18001d838  xor     eax, eax
0x18001d83a  lea     rdx, [rsp+110h+pvarg]
0x18001d83f  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x18001d843  xorps   xmm0, xmm0
0x18001d846  movups  xmmword ptr [rsp+110h+pvarg], xmm0
0x18001d84b  mov     rax, [rcx]
0x18001d84e  mov     rax, [rax+20h]
0x18001d852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d857  mov     rcx, qword ptr [rsp+110h+pvarg+8]
0x18001d85c  test    eax, eax
0x18001d85e  js      short loc_18001D889
0x18001d860  cmp     word ptr [rsp+110h+pvarg], 0Dh
0x18001d866  jnz     short loc_18001D889
0x18001d868  test    rcx, rcx
0x18001d86b  jz      short loc_18001D889
0x18001d86d  mov     rax, [rcx]
0x18001d870  lea     r8, [rsp+110h+var_D8]
0x18001d875  lea     rdx, _GUID_4c074926_9ddd_4d5e_bdc9_1be08660be14
0x18001d87c  mov     rax, [rax]
0x18001d87f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d884  mov     rcx, qword ptr [rsp+110h+pvarg+8]
0x18001d889  movzx   eax, word ptr [rsp+110h+pvarg]
0x18001d88e  cmp     eax, 0Bh
0x18001d891  jnz     loc_18001D9AF
0x18001d897  mov     rcx, [rsp+110h+lParam]; jumptable 000000018001DD10 cases 0-7,16-23
0x18001d89c  cmp     [rsp+110h+var_D8], r13
0x18001d8a1  mov     edi, 80004005h
0x18001d8a6  cmovnz  edi, r13d
0x18001d8aa  test    rcx, rcx
0x18001d8ad  jz      short loc_18001D8BB
0x18001d8af  mov     rax, [rcx]
0x18001d8b2  mov     rax, [rax+10h]
0x18001d8b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8bb  mov     r9, [rsp+110h+var_E8]
0x18001d8c0  test    r9, r9
0x18001d8c3  jz      short loc_18001D8D4
0x18001d8c5  mov     rax, [r9]
0x18001d8c8  mov     rcx, r9
0x18001d8cb  mov     rax, [rax+10h]
0x18001d8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8d4  test    edi, edi
0x18001d8d6  jns     loc_18001DD12
0x18001d8dc  mov     rcx, [rsp+110h+var_D8]
0x18001d8e1  test    rcx, rcx
0x18001d8e4  jz      short loc_18001D8F2
0x18001d8e6  mov     rdx, [rcx]
0x18001d8e9  mov     rax, [rdx+10h]
0x18001d8ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8f2  mov     rcx, qword ptr [rbp+47h+Buf1]
0x18001d8f6  test    rcx, rcx
0x18001d8f9  jz      short loc_18001D907
0x18001d8fb  mov     rax, [rcx]
0x18001d8fe  mov     rax, [rax+10h]
0x18001d902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d907  test    r15b, r15b
0x18001d90a  jnz     loc_18001D77C
0x18001d910  mov     rcx, [rsi+10h]; HIMC
0x18001d914  lea     rdx, [rbp+47h+lf]; lplf
0x18001d918  xorps   xmm0, xmm0
0x18001d91b  movups  xmmword ptr [rbp+47h+lf.lfFaceName+24h], xmm0
0x18001d91f  movups  xmmword ptr [rbp+47h+lf.lfFaceName+30h], xmm0
0x18001d923  movups  xmmword ptr [rbp+47h+lf.lfHeight], xmm0
0x18001d927  movups  xmmword ptr [rbp+47h+lf.lfWeight], xmm0
0x18001d92b  movups  xmmword ptr [rbp+47h+lf.lfFaceName+4], xmm0
0x18001d92f  movups  xmmword ptr [rbp+47h+lf.lfFaceName+14h], xmm0
0x18001d933  call    cs:__imp_ImmGetCompositionFontW
0x18001d939  test    eax, eax
0x18001d93b  jz      loc_18001D77C
0x18001d941  cmp     [rbp+47h+lf.lfFaceName], 40h ; '@'
0x18001d946  mov     eax, r13d
0x18001d949  mov     word ptr [r14], 0Bh
0x18001d94f  setz    al
0x18001d952  mov     [r14+8], eax
0x18001d956  jmp     loc_18001D77C
0x18001d95b  mov     ebx, [r8+0FCh]
0x18001d962  mov     eax, ebx
0x18001d964  and     eax, 0FFFFFFFEh
0x18001d967  mov     [r8+0FCh], eax
0x18001d96e  movups  xmm0, xmmword ptr [r8+0A8h]
0x18001d976  mov     r13d, [r8+100h]
0x18001d97d  movups  [rbp+47h+Buf1], xmm0
0x18001d981  test    r13b, 1
0x18001d985  jz      loc_18001D77C
0x18001d98b  cmp     dword ptr [r8+108h], 0
0x18001d993  jz      loc_18001DA60
0x18001d999  lea     rax, GUID_NULL
0x18001d9a0  mov     ebx, 1
0x18001d9a5  mov     [rsp+110h+lParam], rax
0x18001d9aa  jmp     loc_18001DC72
0x18001d9af  cmp     eax, 0Dh
0x18001d9b2  jnz     loc_18001DA47
0x18001d9b8  test    rcx, rcx
0x18001d9bb  jz      loc_18001D897; jumptable 000000018001DD10 cases 0-7,16-23
0x18001d9c1  mov     rax, [rcx]
0x18001d9c4  mov     rax, [rax+10h]
0x18001d9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9cd  jmp     loc_18001D897; jumptable 000000018001DD10 cases 0-7,16-23
0x18001d9d2  mov     edx, 10h; uBytes
0x18001d9d7  mov     ecx, 40h ; '@'; uFlags
0x18001d9dc  call    cs:__imp_LocalAlloc
0x18001d9e2  test    rax, rax
0x18001d9e5  jz      short loc_18001D9FD
0x18001d9e7  mov     edx, 1Ch; enum __MIDL___MIDL_itf_inputscope_0000_0000_0001
0x18001d9ec  mov     rcx, rax; this
0x18001d9ef  call    ??0CImeInputScope@@QEAA@W4__MIDL___MIDL_itf_inputscope_0000_0000_0001@@@Z; CImeInputScope::CImeInputScope(__MIDL___MIDL_itf_inputscope_0000_0000_0001)
0x18001d9f4  test    rax, rax
0x18001d9f7  jnz     loc_18001DE10
0x18001d9fd  mov     eax, 8007000Eh
0x18001da02  jmp     loc_18001D77E
0x18001da07  mov     rdx, rbx
0x18001da0a  call    ?_Find@?$CPtrMap@PEAUHWND__@@VCInputScope@@@@QEAAPEAVCInputScope@@PEAUHWND__@@@Z; CPtrMap<HWND__ *,CInputScope>::_Find(HWND__ *)
0x18001da0f  mov     r10, rax
0x18001da12  test    rax, rax
0x18001da15  jz      loc_18001D74A
0x18001da1b  mov     rcx, [rax]
0x18001da1e  lea     r8, [rsp+110h+lParam]
0x18001da23  lea     rdx, IID_ITfInputScope
0x18001da2a  mov     rax, [rcx]
0x18001da2d  mov     rcx, r10
0x18001da30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da35  test    eax, eax
0x18001da37  jnz     loc_18001D74A
0x18001da3d  mov     rax, [rsp+110h+lParam]
0x18001da42  jmp     loc_18001DE10
0x18001da47  cmp     eax, 17h; switch 24 cases
0x18001da4a  jbe     loc_18001DCF7
0x18001da50  lea     rcx, [rsp+110h+pvarg]; jumptable 000000018001DD10 default case, cases 8-15
0x18001da55  call    cs:__imp_VariantClear
0x18001da5b  jmp     loc_18001D897; jumptable 000000018001DD10 cases 0-7,16-23
0x18001da60  shl     ebx, 1Fh
0x18001da63  lea     rdx, GUID_MODEBIAS_NONE; Buf2
0x18001da6a  mov     r8d, 10h; Size
0x18001da70  sar     ebx, 1Fh
0x18001da73  lea     rcx, [rbp+47h+Buf1]; Buf1
0x18001da77  call    memcmp_0
0x18001da7c  test    eax, eax
0x18001da7e  jz      loc_18001DB3B
0x18001da84  mov     r8d, 10h; Size
0x18001da8a  lea     rdx, GUID_MODEBIAS_DEFAULT; Buf2
0x18001da91  lea     rcx, [rbp+47h+Buf1]; Buf1
0x18001da95  call    memcmp_0
0x18001da9a  test    eax, eax
0x18001da9c  jz      short loc_18001DB0C
0x18001da9e  lea     rax, [rbp+47h+Buf1]
0x18001daa2  mov     [rsp+110h+lParam], rax
0x18001daa7  jmp     loc_18001DC72
0x18001daac  mov     r8d, 10h; Size
0x18001dab2  lea     rdx, GUID_MODEBIAS_NONE; Buf2
0x18001dab9  lea     rcx, [rbp+47h+Buf1]; Buf1
0x18001dabd  call    memcmp_0
0x18001dac2  test    eax, eax
0x18001dac4  jz      loc_18001DB63
0x18001daca  xor     eax, eax
0x18001dacc  mov     [rsp+110h+lParam], rax
0x18001dad1  add     rsi, 8
0x18001dad5  jmp     loc_18001DC24
0x18001dada  mov     rcx, [rsp+110h+lParam]; Buf1
0x18001dadf  lea     rdx, GUID_NULL; Buf2
0x18001dae6  mov     r8d, 10h; Size
0x18001daec  call    memcmp_0
0x18001daf1  test    eax, eax
0x18001daf3  jz      loc_18001DC95
0x18001daf9  mov     eax, [rsp+110h+var_E0]
0x18001dafd  mov     [r14+8], eax
0x18001db01  mov     word ptr [r14], 3
0x18001db07  jmp     loc_18001D77C
0x18001db0c  movups  xmm0, xmmword ptr cs:GUID_MODEBIAS_NONE.Data1
0x18001db13  lea     rax, GUID_NULL
0x18001db1a  and     r13d, 0FFFFFFFEh
0x18001db1e  mov     [rsp+110h+lParam], rax
0x18001db23  mov     ebx, 1
  ... truncated ...
```
