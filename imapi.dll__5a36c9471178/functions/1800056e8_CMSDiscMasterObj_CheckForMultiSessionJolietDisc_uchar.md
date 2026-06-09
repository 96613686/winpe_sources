# CMSDiscMasterObj::CheckForMultiSessionJolietDisc(uchar *)

- ea: `0x1800056e8`
- end: `0x180005e53`
- name: `?CheckForMultiSessionJolietDisc@CMSDiscMasterObj@@AEAAJPEAE@Z`
- size: `1899`
- prototype: `__int64 __fastcall(CMSDiscMasterObj *__hidden this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000e3f0`

## callees

- `0x180002ac4`
- `0x1800056e8`
- `0x180007bac`
- `0x180007bd4`
- `0x180007c14`
- `0x180007c60`
- `0x18000c330`
- `0x1800127ec`
- `0x180019010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000594a`
- `ole32!CoCreateInstance` at `0x18000594a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800059cc`
- `OLEAUT32!__imp_SysAllocString` at `0x180005cb6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800059cc`
- `OLEAUT32!__imp_SysAllocString` at `0x180005cb6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800059ae`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b32`
- `OLEAUT32!__imp_SysFreeString` at `0x180005cad`
- `OLEAUT32!__imp_SysFreeString` at `0x180005da0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800059ae`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b32`
- `OLEAUT32!__imp_SysFreeString` at `0x180005cad`
- `OLEAUT32!__imp_SysFreeString` at `0x180005da0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180005daf`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180005daf`

## pseudocode

```c
__int64 __fastcall CMSDiscMasterObj::CheckForMultiSessionJolietDisc(CMSDiscMasterObj *this, unsigned __int8 *a2)
{
  char v4; // di
  OLECHAR *v5; // r13
  HRESULT Instance; // ebx
  char v7; // r12
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int v10; // ecx
  _QWORD *v11; // r14
  __int64 *v12; // rax
  bool v13; // zf
  __int64 *v14; // rax
  __int64 *v15; // rax
  __int64 *v16; // rax
  bool v17; // zf
  __int64 *v18; // rax
  __int64 *LastComError; // rax
  int v20; // eax
  const OLECHAR *v21; // rdx
  BSTR v22; // rax
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 result; // rax
  unsigned int v26; // [rsp+40h] [rbp-28h] BYREF
  int v27; // [rsp+44h] [rbp-24h] BYREF
  int v28; // [rsp+48h] [rbp-20h] BYREF
  SAFEARRAY *psa; // [rsp+50h] [rbp-18h] BYREF
  BSTR bstrString[2]; // [rsp+58h] [rbp-10h] BYREF
  int v31; // [rsp+B0h] [rbp+48h] BYREF
  char v32; // [rsp+B8h] [rbp+50h] BYREF
  int v33; // [rsp+C0h] [rbp+58h] BYREF
  int v34; // [rsp+C8h] [rbp+60h] BYREF

  v31 = 0;
  v28 = 0;
  v4 = 0;
  v34 = 0;
  v5 = 0;
  v32 = 0;
  v27 = 0;
  v26 = 0;
  v33 = 0;
  psa = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 64, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids);
  *a2 = 0;
  Instance = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 59) + 96LL))(*((_QWORD *)this + 59));
  if ( Instance < 0 )
  {
    v7 = 0;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_84;
    v9 = 65;
    goto LABEL_8;
  }
  v7 = 1;
  Instance = (*(__int64 (__fastcall **)(_QWORD, int *, int *))(**((_QWORD **)this + 59) + 104LL))(
               *((_QWORD *)this + 59),
               &v28,
               &v34);
  if ( Instance < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_84;
    v9 = 66;
    goto LABEL_8;
  }
  if ( (v34 & 1) != 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_84;
    v9 = 67;
    goto LABEL_8;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, int *, char *, int *, unsigned int *, int *))(**((_QWORD **)this + 59)
                                                                                            + 112LL))(
               *((_QWORD *)this + 59),
               &v31,
               &v32,
               &v27,
               &v26,
               &v33);
  if ( Instance < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_84;
    v9 = 68;
    goto LABEL_8;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 69, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 59) + 136LL))(*((_QWORD *)this + 59));
  v10 = v33;
  if ( (_BYTE)v31 != 1 && v33 )
  {
    v7 = 0;
    if ( *((_BYTE *)this + 450) )
    {
      Instance = -2147220946;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_84;
      v9 = 71;
LABEL_8:
      WPP_SF_(v8[7], v9, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids);
LABEL_84:
      SysFreeString(v5);
      if ( psa )
      {
        SafeArrayDestroy(psa);
        psa = 0;
      }
      v24 = *((_QWORD *)this + 58);
      if ( v24 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        *((_QWORD *)this + 58) = 0;
      }
      if ( v7 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 59) + 136LL))(*((_QWORD *)this + 59));
      return (unsigned int)Instance;
    }
    v11 = (_QWORD *)((char *)this + 464);
    Instance = CoCreateInstance(
                 &GUID_2735412a_7f64_5b0f_8f00_5d77afbe261e,
                 0,
                 0x17u,
                 &GUID_27354153_9f64_5b0f_8f00_5d77afbe261e,
                 (LPVOID *)this + 58);
    if ( Instance >= 0 )
    {
      v5 = SysAllocString(L"IMAPIv1 Shim");
      Instance = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *))(*(_QWORD *)*v11 + 240LL))(*v11, v5);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v11 + 96LL))(*v11, **((_QWORD **)this + 60));
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(_QWORD, SAFEARRAY **))(*(_QWORD *)*v11 + 320LL))(*v11, &psa);
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(_QWORD, SAFEARRAY *))(**((_QWORD **)this + 61) + 448LL))(
                         *((_QWORD *)this + 61),
                         psa);
            if ( Instance >= 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 77, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids);
              }
              Instance = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 61) + 360LL))(
                           *((_QWORD *)this + 61),
                           2);
              if ( Instance >= 0 )
              {
                v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 61) + 120LL))(
                        *((_QWORD *)this + 61),
                        *((_QWORD *)this + 55));
                Instance = v20;
                if ( v20 >= 0 )
                  goto LABEL_78;
                if ( v20 == -1062555388 && *((_BYTE *)this + 448) )
                {
                  v21 = (const OLECHAR *)*((_QWORD *)this + 55);
                  if ( &word_18001BDF8 != v21 )
                  {
                    SysFreeString(*((BSTR *)this + 55));
                    v22 = SysAllocString(&word_18001BDF8);
                    *((_QWORD *)this + 55) = v22;
                    v21 = v22;
                    if ( !v22 )
                      ATL::AtlThrowImpl(-2147024882);
                  }
                  Instance = (*(__int64 (__fastcall **)(_QWORD, const OLECHAR *))(**((_QWORD **)this + 61) + 120LL))(
                               *((_QWORD *)this + 61),
                               v21);
                  if ( Instance >= 0 )
                  {
LABEL_78:
                    *a2 = 1;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
                    {
                      WPP_SF_DD(
                        *((_QWORD *)WPP_GLOBAL_Control + 7),
                        80,
                        &WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
                        v26,
                        v33);
                    }
                    v23 = (unsigned __int8)v31;
                    *((_DWORD *)this + 126) = (unsigned __int8)v31;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
                    {
                      WPP_SF_DD(
                        *((_QWORD *)WPP_GLOBAL_Control + 7),
                        81,
                        &WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
                        v23,
                        v27);
                    }
                    goto LABEL_84;
                  }
                }
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 7),
                    79,
                    &WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
                    (unsigned int)Instance);
                }
                goto LABEL_37;
              }
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                LastComError = (__int64 *)GetLastComError(bstrString);
                WPP_SF_DS(
                  *((_QWORD *)WPP_GLOBAL_Control + 7),
                  78,
                  (unsigned int)&WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
                  Instance,
                  *LastComError);
                v4 = 32;
              }
              v17 = (v4 & 0x20) == 0;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                v18 = (__int64 *)GetLastComError(bstrString);
                WPP_SF_DS(
                  *((_QWORD *)WPP_GLOBAL_Control + 7),
                  76,
                  (unsigned int)&WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
                  Instance,
                  *v18);
                v4 = 16;
              }
              v17 = (v4 & 0x10) == 0;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              v16 = (__int64 *)GetLastComError(bstrString);
              WPP_SF_DS(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                75,
                (unsigned int)&WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
                Instance,
                *v16);
              v4 = 8;
            }
            v17 = (v4 & 8) == 0;
          }
          if ( !v17 )
            SysFreeString(bstrString[0]);
LABEL_37:
          Instance = TranslateIMAPI2Error((unsigned int)Instance);
          goto LABEL_84;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v15 = (__int64 *)GetLastComError(bstrString);
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            74,
            (unsigned int)&WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
            Instance,
            *v15);
          v4 = 4;
        }
        v13 = (v4 & 4) == 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v14 = (__int64 *)GetLastComError(bstrString);
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            73,
            (unsigned int)&WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
            Instance,
            *v14);
          v4 = 2;
        }
        v13 = (v4 & 2) == 0;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v12 = (__int64 *)GetLastComError(bstrString);
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          72,
          (unsigned int)&WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
          Instance,
          *v12);
        v4 = 1;
      }
      v13 = (v4 & 1) == 0;
    }
    if ( !v13 )
      SysFreeString(bstrString[0]);
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      70,
      &WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
      (unsigned __int8)v31,
      v33);
    v10 = v33;
  }
  result = 0;
  if ( !v10 )
    return 2147746332LL;
  return result;
}

```

## disassembly

```asm
0x1800056e8  push    rbp
0x1800056ea  push    rbx
0x1800056eb  push    rsi
0x1800056ec  push    rdi
0x1800056ed  push    r12
0x1800056ef  push    r13
0x1800056f1  push    r14
0x1800056f3  push    r15
0x1800056f5  mov     rbp, rsp
0x1800056f8  sub     rsp, 68h
0x1800056fc  xor     r14d, r14d
0x1800056ff  mov     r15, rdx
0x180005702  mov     [rbp+arg_0], r14d
0x180005706  mov     rsi, rcx
0x180005709  mov     [rbp+var_20], r14d
0x18000570d  mov     edi, r14d
0x180005710  mov     [rbp+arg_18], r14d
0x180005714  mov     r13d, r14d
0x180005717  mov     byte ptr [rbp+arg_0], r14b
0x18000571b  mov     [rbp+arg_8], r14b
0x18000571f  mov     [rbp+var_24], r14d
0x180005723  mov     [rbp+var_28], r14d
0x180005727  mov     [rbp+arg_10], r14d
0x18000572b  mov     [rbp+psa], r14
0x18000572f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005736  lea     rax, WPP_GLOBAL_Control
0x18000573d  cmp     rcx, rax
0x180005740  jz      short loc_18000575C
0x180005742  test    byte ptr [rcx+44h], 1
0x180005746  jz      short loc_18000575C
0x180005748  mov     rcx, [rcx+38h]
0x18000574c  lea     edx, [r14+40h]
0x180005750  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180005757  call    WPP_SF_
0x18000575c  mov     [r15], r14b
0x18000575f  mov     rcx, [rsi+1D8h]
0x180005766  mov     rax, [rcx]
0x180005769  mov     rax, [rax+60h]
0x18000576d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005772  mov     ebx, eax
0x180005774  test    eax, eax
0x180005776  jns     short loc_1800057B6
0x180005778  mov     r12b, r14b
0x18000577b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005782  lea     rax, WPP_GLOBAL_Control
0x180005789  cmp     rcx, rax
0x18000578c  jz      loc_180005D9D
0x180005792  test    byte ptr [rcx+44h], 1
0x180005796  jz      loc_180005D9D
0x18000579c  mov     edx, 41h ; 'A'
0x1800057a1  mov     rcx, [rcx+38h]
0x1800057a5  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x1800057ac  call    WPP_SF_
0x1800057b1  jmp     loc_180005D9D
0x1800057b6  mov     rcx, [rsi+1D8h]
0x1800057bd  lea     r8, [rbp+arg_18]
0x1800057c1  lea     rdx, [rbp+var_20]
0x1800057c5  mov     r12b, 1
0x1800057c8  mov     rax, [rcx]
0x1800057cb  mov     rax, [rax+68h]
0x1800057cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057d4  mov     ebx, eax
0x1800057d6  test    eax, eax
0x1800057d8  jns     short loc_180005802
0x1800057da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057e1  lea     rax, WPP_GLOBAL_Control
0x1800057e8  cmp     rcx, rax
0x1800057eb  jz      loc_180005D9D
0x1800057f1  test    [rcx+44h], r12b
0x1800057f5  jz      loc_180005D9D
0x1800057fb  mov     edx, 42h ; 'B'
0x180005800  jmp     short loc_1800057A1
0x180005802  test    byte ptr [rbp+arg_18], r12b
0x180005806  jz      short loc_180005833
0x180005808  mov     rcx, cs:WPP_GLOBAL_Control
0x18000580f  lea     rax, WPP_GLOBAL_Control
0x180005816  cmp     rcx, rax
0x180005819  jz      loc_180005D9D
0x18000581f  test    [rcx+44h], r12b
0x180005823  jz      loc_180005D9D
0x180005829  mov     edx, 43h ; 'C'
0x18000582e  jmp     loc_1800057A1
0x180005833  mov     rcx, [rsi+1D8h]
0x18000583a  lea     rdx, [rbp+arg_10]
0x18000583e  mov     [rsp+68h+var_40], rdx
0x180005843  lea     r9, [rbp+var_24]
0x180005847  lea     rdx, [rbp+var_28]
0x18000584b  mov     [rsp+68h+ppv], rdx
0x180005850  lea     r8, [rbp+arg_8]
0x180005854  mov     rax, [rcx]
0x180005857  lea     rdx, [rbp+arg_0]
0x18000585b  mov     rax, [rax+70h]
0x18000585f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005864  mov     ebx, eax
0x180005866  test    eax, eax
0x180005868  jns     short loc_180005895
0x18000586a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005871  lea     rax, WPP_GLOBAL_Control
0x180005878  cmp     rcx, rax
0x18000587b  jz      loc_180005D9D
0x180005881  test    [rcx+44h], r12b
0x180005885  jz      loc_180005D9D
0x18000588b  mov     edx, 44h ; 'D'
0x180005890  jmp     loc_1800057A1
0x180005895  mov     rcx, cs:WPP_GLOBAL_Control
0x18000589c  lea     rbx, WPP_GLOBAL_Control
0x1800058a3  cmp     rcx, rbx
0x1800058a6  jz      short loc_1800058C3
0x1800058a8  test    [rcx+44h], r12b
0x1800058ac  jz      short loc_1800058C3
0x1800058ae  mov     rcx, [rcx+38h]
0x1800058b2  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x1800058b9  mov     edx, 45h ; 'E'
0x1800058be  call    WPP_SF_
0x1800058c3  mov     rcx, [rsi+1D8h]
0x1800058ca  mov     rax, [rcx]
0x1800058cd  mov     rax, [rax+88h]
0x1800058d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058d9  mov     ecx, [rbp+arg_10]
0x1800058dc  cmp     byte ptr [rbp+arg_0], r12b
0x1800058e0  jz      loc_180005DF7
0x1800058e6  test    ecx, ecx
0x1800058e8  jz      loc_180005DF7
0x1800058ee  mov     r12b, r14b
0x1800058f1  cmp     [rsi+1C2h], r14b
0x1800058f8  jz      short loc_18000592A
0x1800058fa  mov     ebx, 8004022Eh
0x1800058ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180005906  lea     rax, WPP_GLOBAL_Control
0x18000590d  cmp     rcx, rax
0x180005910  jz      loc_180005D9D
0x180005916  test    byte ptr [rcx+44h], 1
0x18000591a  jz      loc_180005D9D
0x180005920  mov     edx, 47h ; 'G'
0x180005925  jmp     loc_1800057A1
0x18000592a  xor     edx, edx; pUnkOuter
0x18000592c  lea     r14, [rsi+1D0h]
0x180005933  lea     r9, _GUID_27354153_9f64_5b0f_8f00_5d77afbe261e; riid
0x18000593a  mov     [rsp+68h+ppv], r14; ppv
0x18000593f  lea     rcx, _GUID_2735412a_7f64_5b0f_8f00_5d77afbe261e; rclsid
0x180005946  lea     r8d, [rdx+17h]; dwClsContext
0x18000594a  call    cs:__imp_CoCreateInstance
0x180005950  mov     ebx, eax
0x180005952  test    eax, eax
0x180005954  jns     short loc_1800059C5
0x180005956  mov     rcx, cs:WPP_GLOBAL_Control
0x18000595d  lea     rax, WPP_GLOBAL_Control
0x180005964  cmp     rcx, rax
0x180005967  jz      short loc_1800059A4
0x180005969  test    byte ptr [rcx+44h], 1
0x18000596d  jz      short loc_1800059A4
0x18000596f  lea     rcx, [rbp+bstrString]
0x180005973  call    ?GetLastComError@@YA?AVCComBSTR@ATL@@XZ; GetLastComError(void)
0x180005978  mov     edx, 48h ; 'H'
0x18000597d  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180005984  mov     r9d, ebx
0x180005987  mov     rcx, [rax]
0x18000598a  mov     [rsp+68h+ppv], rcx
0x18000598f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005996  mov     rcx, [rcx+38h]
0x18000599a  call    WPP_SF_DS
0x18000599f  mov     edi, 1
0x1800059a4  test    dil, 1
0x1800059a8  jz      short loc_1800059B4
0x1800059aa  mov     rcx, [rbp+bstrString]; bstrString
0x1800059ae  call    cs:__imp_SysFreeString
0x1800059b4  mov     ecx, ebx
0x1800059b6  call    TranslateIMAPI2Error
0x1800059bb  mov     ebx, eax
0x1800059bd  xor     r14d, r14d
0x1800059c0  jmp     loc_180005D9D
0x1800059c5  lea     rcx, psz; "IMAPIv1 Shim"
0x1800059cc  call    cs:__imp_SysAllocString
0x1800059d2  mov     rcx, [r14]
0x1800059d5  mov     r13, rax
0x1800059d8  mov     rdx, [rcx]
0x1800059db  mov     rax, [rdx+0F0h]
0x1800059e2  mov     rdx, r13
0x1800059e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059ea  mov     ebx, eax
0x1800059ec  test    eax, eax
0x1800059ee  jns     short loc_180005A47
0x1800059f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059f7  lea     rax, WPP_GLOBAL_Control
0x1800059fe  cmp     rcx, rax
0x180005a01  jz      short loc_180005A3E
0x180005a03  test    byte ptr [rcx+44h], 1
0x180005a07  jz      short loc_180005A3E
0x180005a09  lea     rcx, [rbp+bstrString]
0x180005a0d  call    ?GetLastComError@@YA?AVCComBSTR@ATL@@XZ; GetLastComError(void)
0x180005a12  mov     edx, 49h ; 'I'
0x180005a17  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180005a1e  mov     r9d, ebx
0x180005a21  mov     rcx, [rax]
0x180005a24  mov     [rsp+68h+ppv], rcx
0x180005a29  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a30  mov     rcx, [rcx+38h]
0x180005a34  call    WPP_SF_DS
0x180005a39  mov     edi, 2
0x180005a3e  test    dil, 2
0x180005a42  jmp     loc_1800059A8
0x180005a47  mov     rcx, [r14]
0x180005a4a  mov     rdx, [rsi+1E0h]
0x180005a51  mov     rax, [rcx]
0x180005a54  mov     rdx, [rdx]
0x180005a57  mov     rax, [rax+60h]
0x180005a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a60  mov     ebx, eax
0x180005a62  test    eax, eax
0x180005a64  jns     short loc_180005ABD
0x180005a66  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a6d  lea     rax, WPP_GLOBAL_Control
0x180005a74  cmp     rcx, rax
0x180005a77  jz      short loc_180005AB4
0x180005a79  test    byte ptr [rcx+44h], 1
0x180005a7d  jz      short loc_180005AB4
0x180005a7f  lea     rcx, [rbp+bstrString]
0x180005a83  call    ?GetLastComError@@YA?AVCComBSTR@ATL@@XZ; GetLastComError(void)
0x180005a88  mov     edx, 4Ah ; 'J'
0x180005a8d  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180005a94  mov     r9d, ebx
0x180005a97  mov     rcx, [rax]
0x180005a9a  mov     [rsp+68h+ppv], rcx
0x180005a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005aa6  mov     rcx, [rcx+38h]
0x180005aaa  call    WPP_SF_DS
0x180005aaf  mov     edi, 4
0x180005ab4  test    dil, 4
0x180005ab8  jmp     loc_1800059A8
0x180005abd  mov     rcx, [r14]
0x180005ac0  lea     rdx, [rbp+psa]
0x180005ac4  mov     rax, [rcx]
0x180005ac7  mov     rax, [rax+140h]
0x180005ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad3  xor     r14d, r14d
0x180005ad6  mov     ebx, eax
0x180005ad8  test    eax, eax
0x180005ada  jns     short loc_180005B46
0x180005adc  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ae3  lea     rax, WPP_GLOBAL_Control
0x180005aea  cmp     rcx, rax
0x180005aed  jz      short loc_180005B28
0x180005aef  test    byte ptr [rcx+44h], 1
0x180005af3  jz      short loc_180005B28
0x180005af5  lea     rcx, [rbp+bstrString]
0x180005af9  call    ?GetLastComError@@YA?AVCComBSTR@ATL@@XZ; GetLastComError(void)
0x180005afe  lea     edx, [r14+4Bh]
0x180005b02  mov     r9d, ebx
0x180005b05  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180005b0c  mov     rcx, [rax]
0x180005b0f  mov     [rsp+68h+ppv], rcx
0x180005b14  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b1b  mov     rcx, [rcx+38h]
0x180005b1f  call    WPP_SF_DS
0x180005b24  lea     edi, [r14+8]
0x180005b28  test    dil, 8
0x180005b2c  jz      short loc_180005B38
0x180005b2e  mov     rcx, [rbp+bstrString]; bstrString
0x180005b32  call    cs:__imp_SysFreeString
0x180005b38  mov     ecx, ebx
0x180005b3a  call    TranslateIMAPI2Error
0x180005b3f  mov     ebx, eax
0x180005b41  jmp     loc_180005D9D
0x180005b46  mov     rcx, [rsi+1E8h]
0x180005b4d  mov     rdx, [rbp+psa]
0x180005b51  mov     rax, [rcx]
0x180005b54  mov     rax, [rax+1C0h]
0x180005b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b60  mov     ebx, eax
0x180005b62  test    eax, eax
0x180005b64  jns     short loc_180005BBD
0x180005b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b6d  lea     rax, WPP_GLOBAL_Control
0x180005b74  cmp     rcx, rax
0x180005b77  jz      short loc_180005BB4
0x180005b79  test    byte ptr [rcx+44h], 1
0x180005b7d  jz      short loc_180005BB4
0x180005b7f  lea     rcx, [rbp+bstrString]
0x180005b83  call    ?GetLastComError@@YA?AVCComBSTR@ATL@@XZ; GetLastComError(void)
0x180005b88  mov     edx, 4Ch ; 'L'
0x180005b8d  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180005b94  mov     r9d, ebx
0x180005b97  mov     rcx, [rax]
0x180005b9a  mov     [rsp+68h+ppv], rcx
0x180005b9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ba6  mov     rcx, [rcx+38h]
0x180005baa  call    WPP_SF_DS
0x180005baf  mov     edi, 10h
0x180005bb4  test    dil, 10h
0x180005bb8  jmp     loc_180005B2C
0x180005bbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bc4  lea     rax, WPP_GLOBAL_Control
0x180005bcb  cmp     rcx, rax
0x180005bce  jz      short loc_180005BEB
0x180005bd0  test    byte ptr [rcx+44h], 1
0x180005bd4  jz      short loc_180005BEB
0x180005bd6  mov     rcx, [rcx+38h]
0x180005bda  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180005be1  mov     edx, 4Dh ; 'M'
0x180005be6  call    WPP_SF_
  ... truncated ...
```
