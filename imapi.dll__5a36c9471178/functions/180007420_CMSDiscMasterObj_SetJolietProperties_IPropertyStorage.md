# CMSDiscMasterObj::SetJolietProperties(IPropertyStorage *)

- ea: `0x180007420`
- end: `0x180007b86`
- name: `?SetJolietProperties@CMSDiscMasterObj@@UEAAJPEAUIPropertyStorage@@@Z`
- size: `1894`
- prototype: `__int64 __fastcall(CMSDiscMasterObj *__hidden this, struct IPropertyStorage *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180002ac4`
- `0x180007420`
- `0x180007d40`
- `0x180007d80`
- `0x18000c69c`
- `0x1800127ec`
- `0x1800184da`
- `0x180019010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180007ac0`
- `ole32!CoTaskMemFree` at `0x180007ac0`
- `ole32!PropVariantClear` at `0x180007ab1`
- `ole32!PropVariantClear` at `0x180007ab1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800076ac`
- `OLEAUT32!__imp_SysAllocString` at `0x1800076ac`
- `OLEAUT32!__imp_SysFreeString` at `0x18000769e`
- `OLEAUT32!__imp_SysFreeString` at `0x180007822`
- `OLEAUT32!__imp_SysFreeString` at `0x18000769e`
- `OLEAUT32!__imp_SysFreeString` at `0x180007822`

## pseudocode

```c
__int64 __fastcall CMSDiscMasterObj::SetJolietProperties(CMSDiscMasterObj *this, struct IPropertyStorage *a2)
{
  __int64 result; // rax
  int v5; // ebx
  __int64 v6; // rcx
  char v7; // r14
  char v8; // r13
  int v9; // eax
  const OLECHAR *v10; // r15
  OLECHAR *v11; // rcx
  BSTR v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  BSTR v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // [rsp+30h] [rbp-49h] BYREF
  wchar_t *String1[2]; // [rsp+38h] [rbp-41h] BYREF
  int v23; // [rsp+48h] [rbp-31h] BYREF
  const wchar_t *v24; // [rsp+50h] [rbp-29h]
  OLECHAR *psz[2]; // [rsp+68h] [rbp-11h] BYREF
  __int64 v26; // [rsp+78h] [rbp-1h]
  __int128 v27; // [rsp+80h] [rbp+7h] BYREF
  __int64 v28; // [rsp+90h] [rbp+17h]
  int v29; // [rsp+E0h] [rbp+67h] BYREF
  BSTR bstrString; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v31; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      58,
      &WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
      (char *)this - 8);
  v31 = 0;
  v29 = 0;
  *(_OWORD *)String1 = 0;
  v21 = 0;
  result = CMSDiscMasterObj::IsCallLegal((CMSDiscMasterObj *)((char *)this - 8), 0x425u);
  v5 = result;
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)result == 262656 )
      goto LABEL_69;
    if ( !a2 )
    {
      v5 = -2147023116;
      goto LABEL_69;
    }
    if ( !*((_QWORD *)this + 53) )
    {
      v5 = 262656;
      goto LABEL_69;
    }
    v5 = ((__int64 (__fastcall *)(struct IPropertyStorage *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IPropertyStorage,
           &v21);
    if ( v5 >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      if ( (*(int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 53) + 88LL))(*((_QWORD *)this + 53), &v31) >= 0 )
      {
        v6 = v31;
        v26 = 0;
        v28 = 0;
        v7 = 0;
        v8 = 0;
        *(_OWORD *)psz = 0;
        v27 = 0;
        if ( !v31 )
          goto LABEL_61;
        while ( 1 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t **, int *))(*(_QWORD *)v6 + 24LL))(
                 v6,
                 1,
                 String1,
                 &v29);
          if ( v9 < 0 || v9 == 1 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
LABEL_61:
            if ( !*((_BYTE *)this + 442) )
            {
              v19 = 0;
              goto LABEL_65;
            }
            if ( v8 )
            {
              v19 = *((_QWORD *)this + 61);
LABEL_65:
              v20 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 60) + 144LL))(
                      *((_QWORD *)this + 60),
                      v19);
              v5 = v20;
              if ( v20 < 0 )
                v5 = TranslateIMAPI2Error((unsigned int)v20);
            }
            if ( v7 )
              v5 = 262656;
            break;
          }
          if ( !wcscmp_0(String1[0], L"PlaceJolietFSOnDisc") )
          {
            v23 = 0;
            v24 = L"PlaceJolietFSOnDisc";
            v5 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, int *, OLECHAR **))a2->lpVtbl->ReadMultiple)(
                   a2,
                   1,
                   &v23,
                   psz);
            if ( v5 >= 0 )
            {
              *((_BYTE *)this + 441) = LOWORD(psz[1]) != 0;
              goto LABEL_18;
            }
          }
          else if ( !wcscmp_0(String1[0], L"VolumeName") )
          {
            v23 = 0;
            v24 = L"VolumeName";
            v5 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, int *, OLECHAR **))a2->lpVtbl->ReadMultiple)(
                   a2,
                   1,
                   &v23,
                   psz);
            if ( v5 >= 0 )
            {
              v5 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *))(**((_QWORD **)this + 60) + 120LL))(
                     *((_QWORD *)this + 60),
                     psz[1]);
              if ( v5 >= 0 )
              {
                v10 = psz[1];
                v11 = (OLECHAR *)*((_QWORD *)this + 54);
                if ( psz[1] != v11 )
                {
                  SysFreeString(v11);
                  if ( v10 )
                  {
                    v12 = SysAllocString(v10);
                    *((_QWORD *)this + 54) = v12;
                    if ( !v12 )
                      ATL::AtlThrowImpl(-2147024882);
                  }
                  else
                  {
                    *((_QWORD *)this + 54) = 0;
                  }
                }
                *((_BYTE *)this + 440) = 0;
                goto LABEL_18;
              }
              v23 = 0;
              v24 = L"VolumeName";
              LOWORD(v27) = 8;
              *((_QWORD *)&v27 + 1) = *((_QWORD *)this + 54);
              goto LABEL_46;
            }
          }
          else if ( !wcscmp_0(String1[0], L"PlaceBootImageOnDisc") )
          {
            v23 = 0;
            v24 = L"PlaceBootImageOnDisc";
            v5 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, int *, OLECHAR **))a2->lpVtbl->ReadMultiple)(
                   a2,
                   1,
                   &v23,
                   psz);
            if ( v5 >= 0 )
            {
              *((_BYTE *)this + 442) = LOWORD(psz[1]) != 0;
              goto LABEL_18;
            }
          }
          else if ( !wcscmp_0(String1[0], L"BootImageManufacturerIDString") )
          {
            v23 = 0;
            v24 = L"BootImageManufacturerIDString";
            v5 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, int *, OLECHAR **))a2->lpVtbl->ReadMultiple)(
                   a2,
                   1,
                   &v23,
                   psz);
            if ( v5 >= 0 )
            {
              v13 = *((_QWORD *)this + 61);
              bstrString = 0;
              (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v13 + 64LL))(v13, &bstrString);
              v5 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *))(**((_QWORD **)this + 61) + 72LL))(
                     *((_QWORD *)this + 61),
                     psz[1]);
              if ( v5 >= 0 )
              {
                (*(void (__fastcall **)(_QWORD, __int64, int *, OLECHAR **, int))(**((_QWORD **)this + 53) + 32LL))(
                  *((_QWORD *)this + 53),
                  1,
                  &v23,
                  psz,
                  2);
              }
              else
              {
                v23 = 0;
                v24 = L"BootImageManufacturerIDString";
                LOWORD(v27) = 8;
                *((_QWORD *)&v27 + 1) = bstrString;
                ((void (__fastcall *)(struct IPropertyStorage *, __int64, int *, __int128 *, int))a2->lpVtbl->WriteMultiple)(
                  a2,
                  1,
                  &v23,
                  &v27,
                  2);
                v7 = 1;
              }
              SysFreeString(bstrString);
              goto LABEL_57;
            }
          }
          else if ( !wcscmp_0(String1[0], L"BootImagePlatform") )
          {
            v23 = 0;
            v24 = L"BootImagePlatform";
            v5 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, int *, OLECHAR **))a2->lpVtbl->ReadMultiple)(
                   a2,
                   1,
                   &v23,
                   psz);
            if ( v5 >= 0 )
            {
              v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 61) + 88LL))(
                     *((_QWORD *)this + 61),
                     LOBYTE(psz[1]));
              if ( v5 >= 0 )
                goto LABEL_18;
              v14 = *((_QWORD *)this + 61);
              v24 = L"BootImagePlatform";
              LOWORD(v27) = 17;
              v23 = 0;
              (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v14 + 80LL))(v14, (char *)&v27 + 8);
LABEL_46:
              ((void (__fastcall *)(struct IPropertyStorage *, __int64, int *, __int128 *, int))a2->lpVtbl->WriteMultiple)(
                a2,
                1,
                &v23,
                &v27,
                2);
              v7 = 1;
              goto LABEL_57;
            }
          }
          else if ( !wcscmp_0(String1[0], L"BootImageEmulationType") )
          {
            v23 = 0;
            v24 = L"BootImageEmulationType";
            v5 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, int *, OLECHAR **))a2->lpVtbl->ReadMultiple)(
                   a2,
                   1,
                   &v23,
                   psz);
            if ( v5 >= 0 )
            {
              v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 61) + 104LL))(
                     *((_QWORD *)this + 61),
                     LOBYTE(psz[1]));
              if ( v5 < 0 )
              {
                v15 = *((_QWORD *)this + 61);
                v24 = L"BootImageEmulationType";
                LOWORD(v27) = 17;
                v23 = 0;
                (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v15 + 96LL))(v15, (char *)&v27 + 8);
                goto LABEL_46;
              }
LABEL_18:
              (*(void (__fastcall **)(_QWORD, __int64, int *, OLECHAR **, int))(**((_QWORD **)this + 53) + 32LL))(
                *((_QWORD *)this + 53),
                1,
                &v23,
                psz,
                2);
              goto LABEL_57;
            }
          }
          else if ( !wcscmp_0(String1[0], L"BootImage") )
          {
            v23 = 0;
            v24 = L"BootImage";
            v5 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, int *, OLECHAR **))a2->lpVtbl->ReadMultiple)(
                   a2,
                   1,
                   &v23,
                   psz);
            if ( v5 >= 0 )
            {
              v16 = *((_QWORD *)this + 61);
              bstrString = 0;
              (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v16 + 56LL))(v16, &bstrString);
              v17 = bstrString;
              if ( bstrString )
              {
                if ( psz[1] != bstrString )
                {
                  *((_QWORD *)&v27 + 1) = bstrString;
                  LOWORD(v27) = 66;
                  ((void (__fastcall *)(struct IPropertyStorage *, __int64, int *, __int128 *, int))a2->lpVtbl->WriteMultiple)(
                    a2,
                    1,
                    &v23,
                    &v27,
                    2);
                  v7 = 1;
LABEL_54:
                  v17 = bstrString;
                }
                if ( v17 )
                  (*(void (__fastcall **)(BSTR))(*(_QWORD *)v17 + 16LL))(v17);
              }
              else if ( psz[1] )
              {
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 61) + 120LL))(*((_QWORD *)this + 61));
                v18 = *((_QWORD *)this + 53);
                LOWORD(v27) = 66;
                *((OLECHAR **)&v27 + 1) = psz[1];
                (*(void (__fastcall **)(__int64, __int64, int *, __int128 *, int))(*(_QWORD *)v18 + 32LL))(
                  v18,
                  1,
                  &v23,
                  &v27,
                  2);
                v8 = 1;
                goto LABEL_54;
              }
LABEL_57:
              PropVariantClear((PROPVARIANT *)psz);
              goto LABEL_59;
            }
          }
          v7 = 1;
LABEL_59:
          CoTaskMemFree(String1[0]);
          v6 = v31;
        }
      }
    }
LABEL_69:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        59,
        &WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
        (char *)this - 8,
        v5);
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x180007420  mov     [rsp-8+arg_8], rbx
0x180007425  push    rbp
0x180007426  push    rsi
0x180007427  push    rdi
0x180007428  push    r12
0x18000742a  push    r13
0x18000742c  push    r14
0x18000742e  push    r15
0x180007430  lea     rbp, [rsp-27h]
0x180007435  sub     rsp, 0A0h
0x18000743c  mov     rsi, rdx
0x18000743f  mov     rdi, rcx
0x180007442  mov     rcx, cs:WPP_GLOBAL_Control
0x180007449  lea     rax, WPP_GLOBAL_Control
0x180007450  cmp     rcx, rax
0x180007453  jz      short loc_180007474
0x180007455  test    byte ptr [rcx+44h], 1
0x180007459  jz      short loc_180007474
0x18000745b  mov     rcx, [rcx+38h]
0x18000745f  lea     r9, [rdi-8]
0x180007463  mov     edx, 3Ah ; ':'
0x180007468  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x18000746f  call    WPP_SF_q
0x180007474  xor     r15d, r15d
0x180007477  lea     rcx, [rdi-8]; this
0x18000747b  xorps   xmm0, xmm0
0x18000747e  mov     [rbp+57h+arg_18], r15
0x180007482  mov     edx, 425h; unsigned int
0x180007487  mov     [rbp+57h+arg_0], r15d
0x18000748b  movups  xmmword ptr [rbp+57h+String1], xmm0
0x18000748f  mov     [rbp+57h+var_A0], r15
0x180007493  call    ?IsCallLegal@CMSDiscMasterObj@@AEAAJK@Z; CMSDiscMasterObj::IsCallLegal(ulong)
0x180007498  mov     ebx, eax
0x18000749a  test    eax, eax
0x18000749c  js      loc_180007B60
0x1800074a2  mov     eax, 40200h
0x1800074a7  cmp     ebx, eax
0x1800074a9  jz      loc_180007B28
0x1800074af  test    rsi, rsi
0x1800074b2  jnz     short loc_1800074BE
0x1800074b4  mov     ebx, 800706F4h
0x1800074b9  jmp     loc_180007B28
0x1800074be  cmp     [rdi+1A8h], r15
0x1800074c5  jnz     short loc_1800074CE
0x1800074c7  mov     ebx, eax
0x1800074c9  jmp     loc_180007B28
0x1800074ce  mov     rax, [rsi]
0x1800074d1  lea     r8, [rbp+57h+var_A0]
0x1800074d5  lea     rdx, IID_IPropertyStorage
0x1800074dc  mov     rcx, rsi
0x1800074df  mov     rax, [rax]
0x1800074e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074e7  mov     ebx, eax
0x1800074e9  test    eax, eax
0x1800074eb  js      loc_180007B28
0x1800074f1  mov     rcx, [rbp+57h+var_A0]
0x1800074f5  mov     rax, [rcx]
0x1800074f8  mov     rax, [rax+10h]
0x1800074fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007501  mov     rcx, [rdi+1A8h]
0x180007508  lea     rdx, [rbp+57h+arg_18]
0x18000750c  mov     rax, [rcx]
0x18000750f  mov     rax, [rax+58h]
0x180007513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007518  test    eax, eax
0x18000751a  js      loc_180007B28
0x180007520  mov     rcx, [rbp+57h+arg_18]
0x180007524  xor     eax, eax
0x180007526  mov     [rbp+57h+var_58], rax
0x18000752a  xorps   xmm0, xmm0
0x18000752d  mov     [rbp+57h+var_40], rax
0x180007531  xorps   xmm1, xmm1
0x180007534  mov     r14b, r15b
0x180007537  mov     r13b, r15b
0x18000753a  movups  xmmword ptr [rbp+57h+psz], xmm0
0x18000753e  movups  [rbp+57h+var_50], xmm1
0x180007542  test    rcx, rcx
0x180007545  jz      loc_180007ADF
0x18000754b  mov     rax, [rcx]
0x18000754e  lea     r9, [rbp+57h+arg_0]
0x180007552  lea     r8, [rbp+57h+String1]
0x180007556  mov     edx, 1
0x18000755b  mov     rax, [rax+18h]
0x18000755f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007564  test    eax, eax
0x180007566  js      loc_180007ACF
0x18000756c  lea     rcx, aPlacejolietfso; "PlaceJolietFSOnDisc"
0x180007573  cmp     eax, 1
0x180007576  jz      loc_180007ACF
0x18000757c  mov     rdx, rcx; String2
0x18000757f  mov     rcx, [rbp+57h+String1]; String1
0x180007583  call    wcscmp_0
0x180007588  test    eax, eax
0x18000758a  jnz     short loc_1800075FC
0x18000758c  lea     rax, aPlacejolietfso; "PlaceJolietFSOnDisc"
0x180007593  mov     [rbp+57h+var_88], r15d
0x180007597  mov     [rbp+57h+var_80], rax
0x18000759b  lea     r9, [rbp+57h+psz]
0x18000759f  mov     rax, [rsi]
0x1800075a2  lea     r8, [rbp+57h+var_88]
0x1800075a6  mov     edx, 1
0x1800075ab  mov     rcx, rsi
0x1800075ae  mov     rax, [rax+18h]
0x1800075b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075b7  mov     ebx, eax
0x1800075b9  test    eax, eax
0x1800075bb  js      loc_180007AB9
0x1800075c1  cmp     word ptr [rbp+57h+psz+8], r15w
0x1800075c6  setnz   al
0x1800075c9  mov     [rdi+1B9h], al
0x1800075cf  mov     rcx, [rdi+1A8h]
0x1800075d6  lea     r9, [rbp+57h+psz]
0x1800075da  lea     r8, [rbp+57h+var_88]
0x1800075de  mov     [rsp+0D0h+var_B0], 2
0x1800075e6  mov     edx, 1
0x1800075eb  mov     rax, [rcx]
0x1800075ee  mov     rax, [rax+20h]
0x1800075f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075f7  jmp     loc_180007AAD
0x1800075fc  mov     rcx, [rbp+57h+String1]; String1
0x180007600  lea     rdx, aVolumename; "VolumeName"
0x180007607  call    wcscmp_0
0x18000760c  test    eax, eax
0x18000760e  jnz     loc_1800076DF
0x180007614  lea     rax, aVolumename; "VolumeName"
0x18000761b  mov     [rbp+57h+var_88], r15d
0x18000761f  mov     [rbp+57h+var_80], rax
0x180007623  lea     r9, [rbp+57h+psz]
0x180007627  mov     rax, [rsi]
0x18000762a  lea     r8, [rbp+57h+var_88]
0x18000762e  mov     edx, 1
0x180007633  mov     rcx, rsi
0x180007636  mov     rax, [rax+18h]
0x18000763a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000763f  mov     ebx, eax
0x180007641  test    eax, eax
0x180007643  js      loc_180007AB9
0x180007649  mov     rcx, [rdi+1E0h]
0x180007650  mov     rdx, [rbp+57h+psz+8]
0x180007654  mov     rax, [rcx]
0x180007657  mov     rax, [rax+78h]
0x18000765b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007660  mov     ebx, eax
0x180007662  test    eax, eax
0x180007664  jns     short loc_18000768E
0x180007666  lea     rax, aVolumename; "VolumeName"
0x18000766d  mov     [rbp+57h+var_88], r15d
0x180007671  mov     [rbp+57h+var_80], rax
0x180007675  mov     eax, 8
0x18000767a  mov     word ptr [rbp+57h+var_50], ax
0x18000767e  mov     rax, [rdi+1B0h]
0x180007685  mov     qword ptr [rbp+57h+var_50+8], rax
0x180007689  jmp     loc_180007963
0x18000768e  mov     r15, [rbp+57h+psz+8]
0x180007692  mov     rcx, [rdi+1B0h]; bstrString
0x180007699  cmp     r15, rcx
0x18000769c  jz      short loc_1800076D0
0x18000769e  call    cs:__imp_SysFreeString
0x1800076a4  test    r15, r15
0x1800076a7  jz      short loc_1800076C7
0x1800076a9  mov     rcx, r15; psz
0x1800076ac  call    cs:__imp_SysAllocString
0x1800076b2  xor     r15d, r15d
0x1800076b5  mov     [rdi+1B0h], rax
0x1800076bc  test    rax, rax
0x1800076bf  jz      loc_180007B7B
0x1800076c5  jmp     short loc_1800076D3
0x1800076c7  mov     [rdi+1B0h], r15
0x1800076ce  jmp     short loc_1800076D3
0x1800076d0  xor     r15d, r15d
0x1800076d3  mov     [rdi+1B8h], r15b
0x1800076da  jmp     loc_1800075CF
0x1800076df  mov     rcx, [rbp+57h+String1]; String1
0x1800076e3  lea     rdx, aPlacebootimage; "PlaceBootImageOnDisc"
0x1800076ea  call    wcscmp_0
0x1800076ef  test    eax, eax
0x1800076f1  jnz     short loc_18000773B
0x1800076f3  lea     rax, aPlacebootimage; "PlaceBootImageOnDisc"
0x1800076fa  mov     [rbp+57h+var_88], r15d
0x1800076fe  mov     [rbp+57h+var_80], rax
0x180007702  lea     r9, [rbp+57h+psz]
0x180007706  mov     rax, [rsi]
0x180007709  lea     r8, [rbp+57h+var_88]
0x18000770d  mov     edx, 1
0x180007712  mov     rcx, rsi
0x180007715  mov     rax, [rax+18h]
0x180007719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000771e  mov     ebx, eax
0x180007720  test    eax, eax
0x180007722  js      loc_180007AB9
0x180007728  cmp     word ptr [rbp+57h+psz+8], r15w
0x18000772d  setnz   al
0x180007730  mov     [rdi+1BAh], al
0x180007736  jmp     loc_1800075CF
0x18000773b  mov     rcx, [rbp+57h+String1]; String1
0x18000773f  lea     rdx, aBootimagemanuf; "BootImageManufacturerIDString"
0x180007746  call    wcscmp_0
0x18000774b  test    eax, eax
0x18000774d  jnz     loc_18000782D
0x180007753  lea     rax, aBootimagemanuf; "BootImageManufacturerIDString"
0x18000775a  mov     [rbp+57h+var_88], r15d
0x18000775e  mov     [rbp+57h+var_80], rax
0x180007762  lea     r9, [rbp+57h+psz]
0x180007766  mov     rax, [rsi]
0x180007769  lea     r8, [rbp+57h+var_88]
0x18000776d  mov     edx, 1
0x180007772  mov     rcx, rsi
0x180007775  mov     rax, [rax+18h]
0x180007779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000777e  mov     ebx, eax
0x180007780  test    eax, eax
0x180007782  js      loc_180007AB9
0x180007788  mov     rcx, [rdi+1E8h]
0x18000778f  lea     rdx, [rbp+57h+bstrString]
0x180007793  mov     [rbp+57h+bstrString], r15
0x180007797  mov     rax, [rcx]
0x18000779a  mov     rax, [rax+40h]
0x18000779e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077a3  mov     rcx, [rdi+1E8h]
0x1800077aa  mov     rdx, [rbp+57h+psz+8]
0x1800077ae  mov     rax, [rcx]
0x1800077b1  mov     rax, [rax+48h]
0x1800077b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077ba  mov     [rsp+0D0h+var_B0], 2
0x1800077c2  mov     ebx, eax
0x1800077c4  lea     r8, [rbp+57h+var_88]
0x1800077c8  mov     edx, 1
0x1800077cd  test    eax, eax
0x1800077cf  jns     short loc_180007807
0x1800077d1  lea     rax, aBootimagemanuf; "BootImageManufacturerIDString"
0x1800077d8  mov     [rbp+57h+var_88], r15d
0x1800077dc  mov     [rbp+57h+var_80], rax
0x1800077e0  lea     r9, [rbp+57h+var_50]
0x1800077e4  lea     eax, [rdx+7]
0x1800077e7  mov     rcx, rsi
0x1800077ea  mov     word ptr [rbp+57h+var_50], ax
0x1800077ee  mov     rax, [rbp+57h+bstrString]
0x1800077f2  mov     qword ptr [rbp+57h+var_50+8], rax
0x1800077f6  mov     rax, [rsi]
0x1800077f9  mov     rax, [rax+20h]
0x1800077fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007802  mov     r14b, 1
0x180007805  jmp     short loc_18000781E
0x180007807  mov     rcx, [rdi+1A8h]
0x18000780e  lea     r9, [rbp+57h+psz]
0x180007812  mov     rax, [rcx]
0x180007815  mov     rax, [rax+20h]
0x180007819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000781e  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180007822  call    cs:__imp_SysFreeString
0x180007828  jmp     loc_180007AAD
0x18000782d  mov     rcx, [rbp+57h+String1]; String1
0x180007831  lea     rdx, aBootimageplatf; "BootImagePlatform"
0x180007838  call    wcscmp_0
0x18000783d  test    eax, eax
0x18000783f  jnz     loc_1800078C6
0x180007845  lea     rax, aBootimageplatf; "BootImagePlatform"
0x18000784c  mov     [rbp+57h+var_88], r15d
0x180007850  mov     [rbp+57h+var_80], rax
0x180007854  lea     r9, [rbp+57h+psz]
0x180007858  mov     rax, [rsi]
0x18000785b  lea     r8, [rbp+57h+var_88]
0x18000785f  mov     edx, 1
0x180007864  mov     rcx, rsi
0x180007867  mov     rax, [rax+18h]
0x18000786b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007870  mov     ebx, eax
0x180007872  test    eax, eax
0x180007874  js      loc_180007AB9
0x18000787a  mov     rcx, [rdi+1E8h]
0x180007881  movzx   edx, byte ptr [rbp+57h+psz+8]
0x180007885  mov     rax, [rcx]
0x180007888  mov     rax, [rax+58h]
0x18000788c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007891  mov     ebx, eax
0x180007893  test    eax, eax
0x180007895  jns     loc_1800075CF
0x18000789b  mov     rcx, [rdi+1E8h]
0x1800078a2  lea     rax, aBootimageplatf; "BootImagePlatform"
0x1800078a9  mov     [rbp+57h+var_80], rax
0x1800078ad  mov     eax, 11h
0x1800078b2  mov     word ptr [rbp+57h+var_50], ax
0x1800078b6  mov     [rbp+57h+var_88], r15d
0x1800078ba  mov     rax, [rcx]
0x1800078bd  mov     rax, [rax+50h]
0x1800078c1  jmp     loc_18000795A
0x1800078c6  mov     rcx, [rbp+57h+String1]; String1
0x1800078ca  lea     rdx, aBootimageemula; "BootImageEmulationType"
0x1800078d1  call    wcscmp_0
0x1800078d6  test    eax, eax
0x1800078d8  jnz     loc_18000798F
0x1800078de  lea     rax, aBootimageemula; "BootImageEmulationType"
0x1800078e5  mov     [rbp+57h+var_88], r15d
0x1800078e9  mov     [rbp+57h+var_80], rax
0x1800078ed  lea     r9, [rbp+57h+psz]
0x1800078f1  mov     rax, [rsi]
0x1800078f4  lea     r8, [rbp+57h+var_88]
0x1800078f8  mov     edx, 1
0x1800078fd  mov     rcx, rsi
0x180007900  mov     rax, [rax+18h]
  ... truncated ...
```
