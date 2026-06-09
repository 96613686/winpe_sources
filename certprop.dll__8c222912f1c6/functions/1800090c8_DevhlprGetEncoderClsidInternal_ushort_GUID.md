# DevhlprGetEncoderClsidInternal(ushort *,_GUID *)

- ea: `0x1800090c8`
- end: `0x1800092f1`
- name: `?DevhlprGetEncoderClsidInternal@@YA?AV?$scoped_error@Utag@hresult_error@@@errorlib@@PEAGPEAU_GUID@@@Z`
- size: `553`
- prototype: `int *__fastcall(int *, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800075d0`

## callees

- `0x1800066d8`
- `0x180006700`
- `0x180008554`
- `0x1800085c4`
- `0x1800090c8`
- `0x1800092f8`
- `0x180010c58`
- `0x180013fac`
- `0x180015894`
- `0x180016a66`
- `0x18001e074`
- `0x1800243e0`

## import_xrefs

- `gdiplus!GdipGetImageEncoders` at `0x180009201`
- `gdiplus!GdipGetImageEncoders` at `0x180009201`
- `gdiplus!GdipGetImageEncodersSize` at `0x180009113`
- `gdiplus!GdipGetImageEncodersSize` at `0x180009113`

## pseudocode

```c
int *__fastcall DevhlprGetEncoderClsidInternal(int *a1, __int64 a2, _OWORD *a3)
{
  unsigned int ImageEncodersSize; // eax
  int v6; // esi
  unsigned int v7; // edx
  unsigned int v8; // edx
  char *v9; // r14
  char *v10; // rax
  size_t v11; // rdi
  unsigned int ImageEncoders; // eax
  int v13; // edi
  unsigned int v14; // edx
  __int64 v15; // r14
  unsigned int i; // esi
  __int64 v17; // r15
  int v19; // [rsp+20h] [rbp-30h] BYREF
  int v20; // [rsp+24h] [rbp-2Ch]
  int v21; // [rsp+30h] [rbp-20h] BYREF
  int v22; // [rsp+34h] [rbp-1Ch]
  __int64 v23; // [rsp+38h] [rbp-18h] BYREF
  void *v24; // [rsp+40h] [rbp-10h]
  __int64 v25; // [rsp+48h] [rbp-8h]
  unsigned int v26; // [rsp+88h] [rbp+38h] BYREF
  int v27; // [rsp+8Ch] [rbp+3Ch]
  unsigned int v28; // [rsp+98h] [rbp+48h] BYREF

  v27 = HIDWORD(a2);
  v28 = 0;
  v26 = 0;
  v21 = 0;
  v22 = 1;
  ImageEncodersSize = GdipGetImageEncodersSize(&v28, &v26);
  v6 = HRESULT_FROM_GDIPLUS(ImageEncodersSize);
  v19 = v6;
  v20 = 2;
  if ( v6 < 0 )
    errorlib::error_received<errorlib::scoped_error<hresult_error::tag>>();
  errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>((unsigned int *)&v19);
  v21 = v6;
  v19 = 0;
  v20 = 1;
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v19, v7);
  v22 = 3;
  if ( v6 < 0 )
  {
    *a1 = v6;
    a1[1] = 2;
    v22 = 5;
    errorlib::scoped_error<hresult_error::tag>::report(a1, 3);
    goto LABEL_25;
  }
  if ( !v26 )
  {
    v19 = -2147024882;
    errorlib::scoped_error<hresult_error::tag>::make_initiated<unsigned long>(a1, &v19);
    goto LABEL_25;
  }
  std::vector<unsigned char>::vector<unsigned char>(&v23);
  v9 = (char *)v24;
  if ( (char *)v26 < (char *)v24 - v23 )
  {
    v10 = (char *)(v26 + v23);
LABEL_13:
    v24 = v10;
    goto LABEL_14;
  }
  if ( (char *)v26 > (char *)v24 - v23 )
  {
    if ( v26 <= (unsigned __int64)(v25 - v23) )
    {
      v11 = v26 - ((unsigned __int64)v24 - v23);
      memset_0(v24, 0, v11);
      v10 = &v9[v11];
      goto LABEL_13;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v23, v26);
  }
LABEL_14:
  ImageEncoders = GdipGetImageEncoders(v28, v26, v23);
  v13 = HRESULT_FROM_GDIPLUS(ImageEncoders);
  v19 = v13;
  v20 = 2;
  if ( v13 < 0 )
    errorlib::error_received<errorlib::scoped_error<hresult_error::tag>>();
  errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>((unsigned int *)&v19);
  v21 = v13;
  v19 = v6;
  v20 = 3;
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v19, v14);
  v22 = 3;
  if ( v13 >= 0 )
  {
    v15 = v23;
    for ( i = 0; i < v28; ++i )
    {
      v17 = 104LL * i;
      if ( !wcscmp_0(*(const wchar_t **)(v17 + v15 + 64), L"image/bmp") )
      {
        *a3 = *(_OWORD *)(v17 + v15);
        *a1 = v13;
        a1[1] = 2;
        std::vector<unsigned char>::_Tidy((__int64)&v23);
        return a1;
      }
    }
    v19 = -2147023728;
    errorlib::scoped_error<hresult_error::tag>::make_initiated<unsigned long>(a1, &v19);
  }
  else
  {
    *a1 = v13;
    a1[1] = 2;
    v22 = 5;
    errorlib::scoped_error<hresult_error::tag>::report(a1, 3);
  }
  std::vector<unsigned char>::_Tidy((__int64)&v23);
LABEL_25:
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v21, v8);
  return a1;
}

```

## disassembly

```asm
0x1800090c8  mov     [rsp-28h+arg_0], rbx
0x1800090cd  mov     [rsp-28h+arg_10], rsi
0x1800090d2  mov     [rsp-28h+arg_8], rdx
0x1800090d7  push    rbp
0x1800090d8  push    rdi
0x1800090d9  push    r12
0x1800090db  push    r14
0x1800090dd  push    r15
0x1800090df  mov     rbp, rsp
0x1800090e2  sub     rsp, 50h
0x1800090e6  mov     r12, r8
0x1800090e9  mov     rbx, rcx
0x1800090ec  mov     [rbp+arg_18], 0
0x1800090f3  mov     dword ptr [rbp+arg_8], 0
0x1800090fa  mov     [rbp+var_20], 0
0x180009101  mov     r14d, 1
0x180009107  mov     [rbp+var_1C], r14d
0x18000910b  lea     rdx, [rbp+arg_8]
0x18000910f  lea     rcx, [rbp+arg_18]
0x180009113  call    cs:__imp_GdipGetImageEncodersSize
0x180009119  mov     ecx, eax
0x18000911b  call    ?HRESULT_FROM_GDIPLUS@@YAJW4Status@Gdiplus@@@Z; HRESULT_FROM_GDIPLUS(Gdiplus::Status)
0x180009120  mov     esi, eax
0x180009122  mov     [rbp+var_30], eax
0x180009125  lea     edi, [r14+1]
0x180009129  mov     [rbp+var_2C], edi
0x18000912c  test    eax, eax
0x18000912e  jns     short loc_180009135
0x180009130  call    ??$error_received@V?$scoped_error@Utag@hresult_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@hresult_error@@@0@AEBUtag@hresult_error@@@Z; errorlib::error_received<errorlib::scoped_error<hresult_error::tag>>(errorlib::scoped_error<hresult_error::tag> const &,hresult_error::tag const &)
0x180009135  lea     rcx, [rbp+var_30]
0x180009139  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@hresult_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(errorlib::scoped_error<hresult_error::tag> &)
0x18000913e  mov     [rbp+var_20], esi
0x180009141  mov     [rbp+var_30], 0
0x180009148  mov     [rbp+var_2C], r14d
0x18000914c  lea     rcx, [rbp+var_30]
0x180009150  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180009155  mov     r15d, 3
0x18000915b  mov     [rbp+var_1C], r15d
0x18000915f  test    esi, esi
0x180009161  jns     short loc_18000917F
0x180009163  mov     [rbx], esi
0x180009165  mov     [rbx+4], edi
0x180009168  mov     [rbp+var_1C], 5
0x18000916f  mov     edx, r15d
0x180009172  mov     rcx, rbx
0x180009175  call    ?report@?$scoped_error@Utag@hresult_error@@@errorlib@@AEAAXW4type@ErrorSource@2@@Z; errorlib::scoped_error<hresult_error::tag>::report(errorlib::ErrorSource::type)
0x18000917a  jmp     loc_1800092CC
0x18000917f  cmp     dword ptr [rbp+arg_8], 0
0x180009183  jnz     short loc_18000919D
0x180009185  mov     [rbp+var_30], 8007000Eh
0x18000918c  lea     rdx, [rbp+var_30]
0x180009190  mov     rcx, rbx
0x180009193  call    ??$make_initiated@K@?$scoped_error@Utag@hresult_error@@@errorlib@@SA?AV01@$$QEAK@Z; errorlib::scoped_error<hresult_error::tag>::make_initiated<ulong>(ulong &&)
0x180009198  jmp     loc_1800092CC
0x18000919d  lea     rcx, [rbp+var_18]
0x1800091a1  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::vector<uchar>(void)
0x1800091a6  nop
0x1800091a7  mov     edi, dword ptr [rbp+arg_8]
0x1800091aa  mov     rdx, [rbp+var_18]
0x1800091ae  mov     r14, [rbp+var_10]
0x1800091b2  mov     rcx, r14
0x1800091b5  sub     rcx, rdx
0x1800091b8  cmp     rdi, rcx
0x1800091bb  jnb     short loc_1800091C3
0x1800091bd  lea     rax, [rdi+rdx]
0x1800091c1  jmp     short loc_1800091F3
0x1800091c3  jbe     short loc_1800091F7
0x1800091c5  mov     rax, [rbp+var_8]
0x1800091c9  sub     rax, rdx
0x1800091cc  cmp     rdi, rax
0x1800091cf  jbe     short loc_1800091DF
0x1800091d1  mov     rdx, rdi
0x1800091d4  lea     rcx, [rbp+var_18]
0x1800091d8  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800091dd  jmp     short loc_1800091F7
0x1800091df  sub     rdi, rcx
0x1800091e2  mov     r8, rdi; Size
0x1800091e5  xor     edx, edx; Val
0x1800091e7  mov     rcx, r14; void *
0x1800091ea  call    memset_0
0x1800091ef  lea     rax, [rdi+r14]
0x1800091f3  mov     [rbp+var_10], rax
0x1800091f7  mov     r8, [rbp+var_18]
0x1800091fb  mov     edx, dword ptr [rbp+arg_8]
0x1800091fe  mov     ecx, [rbp+arg_18]
0x180009201  call    cs:__imp_GdipGetImageEncoders
0x180009207  mov     ecx, eax
0x180009209  call    ?HRESULT_FROM_GDIPLUS@@YAJW4Status@Gdiplus@@@Z; HRESULT_FROM_GDIPLUS(Gdiplus::Status)
0x18000920e  mov     edi, eax
0x180009210  mov     [rbp+var_30], eax
0x180009213  mov     r14d, 2
0x180009219  mov     [rbp+var_2C], r14d
0x18000921d  test    eax, eax
0x18000921f  jns     short loc_180009226
0x180009221  call    ??$error_received@V?$scoped_error@Utag@hresult_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@hresult_error@@@0@AEBUtag@hresult_error@@@Z; errorlib::error_received<errorlib::scoped_error<hresult_error::tag>>(errorlib::scoped_error<hresult_error::tag> const &,hresult_error::tag const &)
0x180009226  lea     rcx, [rbp+var_30]
0x18000922a  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@hresult_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(errorlib::scoped_error<hresult_error::tag> &)
0x18000922f  mov     [rbp+var_20], edi
0x180009232  mov     [rbp+var_30], esi
0x180009235  mov     [rbp+var_2C], r15d
0x180009239  lea     rcx, [rbp+var_30]
0x18000923d  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180009242  mov     [rbp+var_1C], r15d
0x180009246  test    edi, edi
0x180009248  jns     short loc_180009264
0x18000924a  mov     [rbx], edi
0x18000924c  mov     [rbx+4], r14d
0x180009250  mov     [rbp+var_1C], 5
0x180009257  mov     edx, r15d
0x18000925a  mov     rcx, rbx
0x18000925d  call    ?report@?$scoped_error@Utag@hresult_error@@@errorlib@@AEAAXW4type@ErrorSource@2@@Z; errorlib::scoped_error<hresult_error::tag>::report(errorlib::ErrorSource::type)
0x180009262  jmp     short loc_1800092C2
0x180009264  mov     r14, [rbp+var_18]
0x180009268  xor     esi, esi
0x18000926a  cmp     esi, [rbp+arg_18]
0x18000926d  jnb     short loc_1800092AE
0x18000926f  mov     eax, esi
0x180009271  imul    r15, rax, 68h ; 'h'
0x180009275  lea     rdx, aImageBmp; "image/bmp"
0x18000927c  mov     rcx, [r15+r14+40h]; String1
0x180009281  call    wcscmp_0
0x180009286  test    eax, eax
0x180009288  jz      short loc_18000928E
0x18000928a  inc     esi
0x18000928c  jmp     short loc_18000926A
0x18000928e  movups  xmm0, xmmword ptr [r15+r14]
0x180009293  movdqu  xmmword ptr [r12], xmm0
0x180009299  mov     [rbx], edi
0x18000929b  mov     dword ptr [rbx+4], 2
0x1800092a2  lea     rcx, [rbp+var_18]
0x1800092a6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800092ab  nop
0x1800092ac  jmp     short loc_1800092D5
0x1800092ae  mov     [rbp+var_30], 80070490h
0x1800092b5  lea     rdx, [rbp+var_30]
0x1800092b9  mov     rcx, rbx
0x1800092bc  call    ??$make_initiated@K@?$scoped_error@Utag@hresult_error@@@errorlib@@SA?AV01@$$QEAK@Z; errorlib::scoped_error<hresult_error::tag>::make_initiated<ulong>(ulong &&)
0x1800092c1  nop
0x1800092c2  lea     rcx, [rbp+var_18]
0x1800092c6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800092cb  nop
0x1800092cc  lea     rcx, [rbp+var_20]
0x1800092d0  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1800092d5  mov     rax, rbx
0x1800092d8  lea     r11, [rsp+50h+var_s0]
0x1800092dd  mov     rbx, [r11+30h]
0x1800092e1  mov     rsi, [r11+40h]
0x1800092e5  mov     rsp, r11
0x1800092e8  pop     r15
0x1800092ea  pop     r14
0x1800092ec  pop     r12
0x1800092ee  pop     rdi
0x1800092ef  pop     rbp
0x1800092f0  retn
```
