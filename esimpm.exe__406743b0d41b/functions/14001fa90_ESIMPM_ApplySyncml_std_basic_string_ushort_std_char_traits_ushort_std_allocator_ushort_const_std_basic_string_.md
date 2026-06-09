# ESIMPM::ApplySyncml(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14001fa90`
- end: `0x140020162`
- name: `?ApplySyncml@ESIMPM@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `1746`
- prototype: `__int64 __fastcall(__int64, char **, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400203ec`

## callees

- `0x140001278`
- `0x140001308`
- `0x140002f60`
- `0x140003b1c`
- `0x14001a9b4`
- `0x14001fa90`
- `0x140020b7c`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001fb37`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001fb37`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001fc9e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001fde9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001fee7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001ffae`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140020014`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140020105`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001fc9e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001fde9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001fee7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001ffae`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140020014`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140020105`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001fb93`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001fbd6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001fc1d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001fc5d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001fb93`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001fbd6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001fc1d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001fc5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140020083`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002008d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400200a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400200bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140020083`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002008d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400200a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400200bb`

## string_xrefs

- `0x140020150`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall ESIMPM::ApplySyncml(__int64 a1, char **a2, __int64 a3, __int64 a4)
{
  _QWORD *v5; // rdi
  HRESULT v6; // eax
  LPVOID v7; // rcx
  LPVOID v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  LPVOID v12; // rcx
  bool v14; // zf
  unsigned __int16 (__fastcall *v15)(LPVOID, __int128 *, __int64); // rax
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned __int16 (__fastcall *v18)(LPVOID, _OWORD *, __int64, _QWORD, _QWORD); // rax
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // r8
  unsigned __int16 (__fastcall *v23)(LPVOID, void **, __int64); // rax
  __int64 v24; // r9
  const void *v25; // r9
  unsigned __int64 v26; // rdx
  char *v27; // rdi
  __int64 v28; // rbx
  unsigned int i; // ebx
  __int64 v30; // r8
  __int64 v31; // r9
  LPVOID v32; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID v34; // [rsp+30h] [rbp-D0h] BYREF
  int v35[2]; // [rsp+38h] [rbp-C8h] BYREF
  const char *v36; // [rsp+40h] [rbp-C0h] BYREF
  char v37; // [rsp+48h] [rbp-B8h]
  __int128 v38; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v39; // [rsp+60h] [rbp-A0h]
  const wchar_t **v40; // [rsp+70h] [rbp-90h]
  void *Src[2]; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL hMem[2]; // [rsp+88h] [rbp-78h]
  HLOCAL v43[2]; // [rsp+98h] [rbp-68h]
  _OWORD v44[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v45; // [rsp+C8h] [rbp-38h]
  const wchar_t *v46; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v47; // [rsp+E0h] [rbp-20h]
  __int64 v48; // [rsp+F0h] [rbp-10h]
  _OWORD v49[3]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v50[2]; // [rsp+130h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v5 = (_QWORD *)a1;
  if ( (unsigned int)dword_140075078 > 5 )
  {
    *(_QWORD *)v35 = "ESIMPM::ApplySyncml";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      a1,
      (__int64)&byte_14006A2C7,
      a3,
      a4,
      (const unsigned __int16 **)v35);
  }
  v34 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  memset(v44, 0, sizeof(v44));
  v45 = 0;
  *(_OWORD *)Src = 0;
  *(_OWORD *)hMem = 0;
  *(_OWORD *)v43 = 0;
  v6 = CoInitializeEx(0, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14D3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v6,
      ppv);
  v37 = 1;
  v34 = 0;
  if ( CoCreateInstance(
         &GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8,
         0,
         1u,
         &GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd,
         &v34) < 0 )
  {
    v7 = v34;
    v34 = 0;
    if ( v7 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
    if ( (CoCreateInstance(
            &GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8,
            0,
            1u,
            &GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd,
            &v34)
        & 0x1FFF0000) == 0x70000 )
    {
      v8 = v34;
      v34 = 0;
      if ( v8 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
      v9 = (unsigned __int16)CoCreateInstance(
                               &GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8,
                               0,
                               1u,
                               &GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd,
                               &v34);
    }
    else
    {
      v12 = v34;
      v34 = 0;
      if ( v12 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
      v9 = CoCreateInstance(
             &GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8,
             0,
             1u,
             &GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd,
             &v34);
    }
    if ( v9 )
    {
      if ( (unsigned int)dword_140075078 > 2 )
      {
        v36 = "ESIMPM::ApplySyncml";
        v35[0] = v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (unsigned int)dword_140075078,
          (__int64)&word_14006A28E,
          v10,
          v11,
          (__int64)v35,
          (const unsigned __int16 **)&v36);
      }
      CoUninitialize();
      if ( v34 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
      return v9;
    }
  }
  LODWORD(v38) = 1;
  *((_QWORD *)&v38 + 1) = L"ProviderId1";
  *((_QWORD *)&v39 + 1) = 0x100000003LL;
  *(_QWORD *)&v39 = L"DisplayedSrc";
  v49[0] = *(_OWORD *)L"DAD70CC2-365B-450D-A8AB-2EB23F4300CC";
  v49[1] = *(_OWORD *)L"-365B-450D-A8AB-2EB23F4300CC";
  v49[2] = *(_OWORD *)L"0D-A8AB-2EB23F4300CC";
  v50[0] = *(_OWORD *)L"2EB23F4300CC";
  *(_OWORD *)((char *)v50 + 10) = *(_OWORD *)L"F4300CC";
  v46 = L"OMADM::AccountID";
  *(_QWORD *)&v47 = v49;
  v40 = &v46;
  if ( (*(int (__fastcall **)(LPVOID, __int128 *, __int64))(*(_QWORD *)v34 + 24LL))(v34, &v38, 40) < 0 )
  {
    v14 = ((*(__int64 (__fastcall **)(LPVOID, __int128 *, __int64))(*(_QWORD *)v34 + 24LL))(v34, &v38, 40) & 0x1FFF0000) == 458752;
    v15 = *(unsigned __int16 (__fastcall **)(LPVOID, __int128 *, __int64))(*(_QWORD *)v34 + 24LL);
    v9 = v14 ? v15(v34, &v38, 40) : ((__int64 (__fastcall *)(LPVOID, __int128 *, __int64))v15)(v34, &v38, 40);
    if ( v9 )
    {
      if ( (unsigned int)dword_140075078 > 2 )
      {
        v36 = "ESIMPM::ApplySyncml";
        v35[0] = v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (unsigned int)dword_140075078,
          (__int64)&word_14006A256,
          v16,
          v17,
          (__int64)v35,
          (const unsigned __int16 **)&v36);
      }
      CoUninitialize();
      if ( v34 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
      return v9;
    }
  }
  DWORD2(v44[0]) = 1;
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  *(_QWORD *)&v44[0] = v5;
  *(_QWORD *)((char *)v44 + 12) = 2;
  DWORD1(v45) = 0;
  if ( (*(int (__fastcall **)(LPVOID, _OWORD *, __int64))(*(_QWORD *)v34 + 32LL))(v34, v44, 48) < 0 )
  {
    v14 = ((*(__int64 (__fastcall **)(LPVOID, _OWORD *, __int64, _QWORD, _QWORD))(*(_QWORD *)v34 + 32LL))(
             v34,
             v44,
             48,
             0,
             0)
         & 0x1FFF0000) == 458752;
    v18 = *(unsigned __int16 (__fastcall **)(LPVOID, _OWORD *, __int64, _QWORD, _QWORD))(*(_QWORD *)v34 + 32LL);
    v9 = v14
       ? v18(v34, v44, 48, 0, 0)
       : ((__int64 (__fastcall *)(LPVOID, _OWORD *, __int64, _QWORD, _QWORD))v18)(v34, v44, 48, 0, 0);
    if ( v9 )
    {
      if ( (unsigned int)dword_140075078 > 2 )
      {
        v36 = "ESIMPM::ApplySyncml";
        v35[0] = v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (unsigned int)dword_140075078,
          (__int64)word_14006A222,
          v19,
          v20,
          (__int64)v35,
          (const unsigned __int16 **)&v36);
      }
      CoUninitialize();
      if ( v34 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
      return v9;
    }
  }
  if ( (*(int (__fastcall **)(LPVOID, void **, __int64))(*(_QWORD *)v34 + 40LL))(v34, Src, 48) < 0 )
  {
    v14 = ((*(__int64 (__fastcall **)(LPVOID, void **, __int64))(*(_QWORD *)v34 + 40LL))(v34, Src, 48) & 0x1FFF0000) == 458752;
    v23 = *(unsigned __int16 (__fastcall **)(LPVOID, void **, __int64))(*(_QWORD *)v34 + 40LL);
    v9 = v14 ? v23(v34, Src, 48) : ((__int64 (__fastcall *)(LPVOID, void **, __int64))v23)(v34, Src, 48);
    if ( v9 )
    {
      if ( (unsigned int)dword_140075078 > 2 )
      {
        v36 = "ESIMPM::ApplySyncml";
        v35[0] = v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (unsigned int)dword_140075078,
          (__int64)byte_14006A1EB,
          v22,
          v24,
          (__int64)v35,
          (const unsigned __int16 **)&v36);
      }
      CoUninitialize();
      if ( v34 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
      return v9;
    }
  }
  v25 = Src[1];
  if ( !Src[1] )
  {
    v9 = 1627;
    if ( (unsigned int)dword_140075078 > 2 )
    {
      v36 = "ESIMPM::ApplySyncml";
      v35[0] = 1627;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v21,
        (__int64)&unk_14006A1B8,
        v22,
        0,
        (__int64)v35,
        (const unsigned __int16 **)&v36);
    }
    CoUninitialize();
    if ( v34 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
    return v9;
  }
  v26 = -1;
  do
    ++v26;
  while ( *((_WORD *)Src[1] + v26) );
  if ( v26 > (unsigned __int64)a2[3] )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      a2,
      v26,
      v22,
      Src[1]);
  }
  else
  {
    if ( (unsigned __int64)a2[3] <= 7 )
      v27 = (char *)a2;
    else
      v27 = *a2;
    a2[2] = (char *)v26;
    v28 = 2 * v26;
    memmove_0(v27, v25, 2 * v26);
    *(_WORD *)&v27[v28] = 0;
  }
  LocalFree(Src[1]);
  LocalFree(hMem[0]);
  for ( i = 0; i < LODWORD(v43[1]); ++i )
    LocalFree(*((HLOCAL *)v43[0] + 2 * i));
  LocalFree(v43[0]);
  v32 = v34;
  v34 = 0;
  if ( v32 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
  if ( (unsigned int)dword_140075078 > 5 )
  {
    v36 = "ESIMPM::ApplySyncml";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)v32,
      (__int64)&word_14006A19E,
      v30,
      v31,
      (const unsigned __int16 **)&v36);
  }
  CoUninitialize();
  if ( v34 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
  return 0;
}

```

## disassembly

```asm
0x14001fa90  mov     [rsp-8+arg_10], rbx
0x14001fa95  mov     [rsp-8+arg_18], rsi
0x14001fa9a  push    rbp
0x14001fa9b  push    rdi
0x14001fa9c  push    r12
0x14001fa9e  push    r14
0x14001faa0  push    r15
0x14001faa2  lea     rbp, [rsp-60h]
0x14001faa7  sub     rsp, 160h
0x14001faae  mov     rax, cs:__security_cookie
0x14001fab5  xor     rax, rsp
0x14001fab8  mov     [rbp+80h+var_30], rax
0x14001fabc  mov     rsi, rdx
0x14001fabf  mov     rdi, rcx
0x14001fac2  xor     r14d, r14d
0x14001fac5  mov     eax, cs:dword_140075078
0x14001facb  lea     r15, aEsimpmApplysyn; "ESIMPM::ApplySyncml"
0x14001fad2  cmp     eax, 5
0x14001fad5  jbe     short loc_14001FAF2
0x14001fad7  mov     qword ptr [rsp+180h+var_148], r15
0x14001fadc  lea     rax, [rsp+180h+var_148]
0x14001fae1  mov     [rsp+180h+ppv], rax; int
0x14001fae6  lea     rdx, byte_14006A2C7
0x14001faed  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14001faf2  mov     [rsp+180h+var_150], r14
0x14001faf7  xorps   xmm0, xmm0
0x14001fafa  xor     eax, eax
0x14001fafc  movups  [rsp+180h+var_130], xmm0
0x14001fb01  movups  [rsp+180h+var_120], xmm0
0x14001fb06  mov     [rsp+180h+var_110], rax
0x14001fb0b  mov     [rbp+80h+var_A8], r14
0x14001fb0f  movups  [rbp+80h+var_A0], xmm0
0x14001fb13  mov     [rbp+80h+var_90], rax
0x14001fb17  xorps   xmm1, xmm1
0x14001fb1a  movups  [rbp+80h+var_D8], xmm1
0x14001fb1e  movups  [rbp+80h+var_C8], xmm1
0x14001fb22  movups  [rbp+80h+var_B8], xmm1
0x14001fb26  movups  xmmword ptr [rsp+180h+Src], xmm0
0x14001fb2b  movups  xmmword ptr [rbp+80h+hMem], xmm0
0x14001fb2f  movups  xmmword ptr [rbp+80h+var_E8], xmm0
0x14001fb33  xor     edx, edx; dwCoInit
0x14001fb35  xor     ecx, ecx; pvReserved
0x14001fb37  call    cs:__imp_CoInitializeEx
0x14001fb3d  mov     rcx, [rbp+88h]; this
0x14001fb44  test    eax, eax
0x14001fb46  js      loc_14002014D
0x14001fb4c  mov     r12d, 1
0x14001fb52  mov     [rsp+180h+var_138], r12b
0x14001fb57  mov     rcx, [rsp+180h+var_150]
0x14001fb5c  mov     [rsp+180h+var_150], r14
0x14001fb61  test    rcx, rcx
0x14001fb64  jz      short loc_14001FB73
0x14001fb66  mov     rax, [rcx]
0x14001fb69  mov     rax, [rax+10h]
0x14001fb6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fb72  nop
0x14001fb73  lea     rax, [rsp+180h+var_150]
0x14001fb78  mov     [rsp+180h+ppv], rax; ppv
0x14001fb7d  lea     rbx, _GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd
0x14001fb84  mov     r9, rbx; riid
0x14001fb87  mov     r8d, r12d; dwClsContext
0x14001fb8a  xor     edx, edx; pUnkOuter
0x14001fb8c  lea     rcx, _GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8; rclsid
0x14001fb93  call    cs:__imp_CoCreateInstance
0x14001fb99  test    eax, eax
0x14001fb9b  jns     loc_14001FCC3
0x14001fba1  mov     rcx, [rsp+180h+var_150]
0x14001fba6  mov     [rsp+180h+var_150], r14
0x14001fbab  test    rcx, rcx
0x14001fbae  jz      short loc_14001FBBD
0x14001fbb0  mov     rax, [rcx]
0x14001fbb3  mov     rax, [rax+10h]
0x14001fbb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fbbc  nop
0x14001fbbd  lea     rax, [rsp+180h+var_150]
0x14001fbc2  mov     [rsp+180h+ppv], rax; ppv
0x14001fbc7  mov     r9, rbx; riid
0x14001fbca  mov     r8d, r12d; dwClsContext
0x14001fbcd  xor     edx, edx; pUnkOuter
0x14001fbcf  lea     rcx, _GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8; rclsid
0x14001fbd6  call    cs:__imp_CoCreateInstance
0x14001fbdc  and     eax, 1FFF0000h
0x14001fbe1  cmp     eax, 70000h
0x14001fbe6  jnz     short loc_14001FC28
0x14001fbe8  mov     rcx, [rsp+180h+var_150]
0x14001fbed  mov     [rsp+180h+var_150], r14
0x14001fbf2  test    rcx, rcx
0x14001fbf5  jz      short loc_14001FC04
0x14001fbf7  mov     rax, [rcx]
0x14001fbfa  mov     rax, [rax+10h]
0x14001fbfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fc03  nop
0x14001fc04  lea     rax, [rsp+180h+var_150]
0x14001fc09  mov     [rsp+180h+ppv], rax; ppv
0x14001fc0e  mov     r9, rbx; riid
0x14001fc11  mov     r8d, r12d; dwClsContext
0x14001fc14  xor     edx, edx; pUnkOuter
0x14001fc16  lea     rcx, _GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8; rclsid
0x14001fc1d  call    cs:__imp_CoCreateInstance
0x14001fc23  movzx   ebx, ax
0x14001fc26  jmp     short loc_14001FC65
0x14001fc28  mov     rcx, [rsp+180h+var_150]
0x14001fc2d  mov     [rsp+180h+var_150], r14
0x14001fc32  test    rcx, rcx
0x14001fc35  jz      short loc_14001FC44
0x14001fc37  mov     rax, [rcx]
0x14001fc3a  mov     rax, [rax+10h]
0x14001fc3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fc43  nop
0x14001fc44  lea     rax, [rsp+180h+var_150]
0x14001fc49  mov     [rsp+180h+ppv], rax; ppv
0x14001fc4e  mov     r9, rbx; riid
0x14001fc51  mov     r8d, r12d; dwClsContext
0x14001fc54  xor     edx, edx; pUnkOuter
0x14001fc56  lea     rcx, _GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8; rclsid
0x14001fc5d  call    cs:__imp_CoCreateInstance
0x14001fc63  mov     ebx, eax
0x14001fc65  test    ebx, ebx
0x14001fc67  jz      short loc_14001FCC3
0x14001fc69  mov     ecx, cs:dword_140075078
0x14001fc6f  cmp     ecx, 2
0x14001fc72  jbe     short loc_14001FC9E
0x14001fc74  mov     [rsp+180h+var_140], r15
0x14001fc79  mov     [rsp+180h+var_148], ebx
0x14001fc7d  lea     rax, [rsp+180h+var_140]
0x14001fc82  mov     [rsp+180h+var_158], rax
0x14001fc87  lea     rax, [rsp+180h+var_148]
0x14001fc8c  mov     [rsp+180h+ppv], rax
0x14001fc91  lea     rdx, word_14006A28E
0x14001fc98  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14001fc9d  nop
0x14001fc9e  call    cs:__imp_CoUninitialize
0x14001fca4  nop
0x14001fca5  mov     rcx, [rsp+180h+var_150]
0x14001fcaa  test    rcx, rcx
0x14001fcad  jz      short loc_14001FCBC
0x14001fcaf  mov     rax, [rcx]
0x14001fcb2  mov     rax, [rax+10h]
0x14001fcb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fcbb  nop
0x14001fcbc  mov     eax, ebx
0x14001fcbe  jmp     loc_140020125
0x14001fcc3  mov     dword ptr [rsp+180h+var_130], r12d
0x14001fcc8  lea     rax, aProviderid1; "ProviderId1"
0x14001fccf  mov     qword ptr [rsp+180h+var_130+8], rax
0x14001fcd4  mov     dword ptr [rsp+180h+var_120+8], 3
0x14001fcdc  lea     rax, aDisplayedsrc; "DisplayedSrc"
0x14001fce3  mov     qword ptr [rsp+180h+var_120], rax
0x14001fce8  movaps  xmm0, xmmword ptr cs:aDad70cc2365b45; "DAD70CC2-365B-450D-A8AB-2EB23F4300CC"
0x14001fcef  movaps  [rbp+80h+var_80], xmm0
0x14001fcf3  movaps  xmm1, xmmword ptr cs:aDad70cc2365b45+10h; "-365B-450D-A8AB-2EB23F4300CC"
0x14001fcfa  movaps  [rbp+80h+var_70], xmm1
0x14001fcfe  movaps  xmm0, xmmword ptr cs:aDad70cc2365b45+20h; "0D-A8AB-2EB23F4300CC"
0x14001fd05  movaps  [rbp+80h+var_60], xmm0
0x14001fd09  movaps  xmm1, xmmword ptr cs:aDad70cc2365b45+30h; "2EB23F4300CC"
0x14001fd10  movaps  xmmword ptr [rbp+80h+var_50], xmm1
0x14001fd14  movups  xmm0, xmmword ptr cs:aDad70cc2365b45+3Ah; "F4300CC"
0x14001fd1b  movups  xmmword ptr [rbp+80h+var_50+0Ah], xmm0
0x14001fd1f  lea     rax, aOmadmAccountid; "OMADM::AccountID"
0x14001fd26  mov     [rbp+80h+var_A8], rax
0x14001fd2a  lea     rax, [rbp+80h+var_80]
0x14001fd2e  mov     qword ptr [rbp+80h+var_A0], rax
0x14001fd32  mov     dword ptr [rsp+180h+var_120+0Ch], r12d
0x14001fd37  lea     rax, [rbp+80h+var_A8]
0x14001fd3b  mov     [rsp+180h+var_110], rax
0x14001fd40  mov     rcx, [rsp+180h+var_150]
0x14001fd45  mov     rax, [rcx]
0x14001fd48  mov     ebx, 28h ; '('
0x14001fd4d  mov     r8d, ebx
0x14001fd50  lea     rdx, [rsp+180h+var_130]
0x14001fd55  mov     rax, [rax+18h]
0x14001fd59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fd5e  test    eax, eax
0x14001fd60  jns     loc_14001FE0C
0x14001fd66  mov     rcx, [rsp+180h+var_150]
0x14001fd6b  mov     rax, [rcx]
0x14001fd6e  mov     r8d, ebx
0x14001fd71  lea     rdx, [rsp+180h+var_130]
0x14001fd76  mov     rax, [rax+18h]
0x14001fd7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fd7f  and     eax, 1FFF0000h
0x14001fd84  mov     rcx, [rsp+180h+var_150]
0x14001fd89  mov     r8d, ebx
0x14001fd8c  lea     rdx, [rsp+180h+var_130]
0x14001fd91  cmp     eax, 70000h
0x14001fd96  mov     rax, [rcx]
0x14001fd99  mov     rax, [rax+18h]
0x14001fd9d  jnz     short loc_14001FDA9
0x14001fd9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fda4  movzx   ebx, ax
0x14001fda7  jmp     short loc_14001FDB0
0x14001fda9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fdae  mov     ebx, eax
0x14001fdb0  test    ebx, ebx
0x14001fdb2  jz      short loc_14001FE0C
0x14001fdb4  mov     ecx, cs:dword_140075078
0x14001fdba  cmp     ecx, 2
0x14001fdbd  jbe     short loc_14001FDE9
0x14001fdbf  mov     [rsp+180h+var_140], r15
0x14001fdc4  mov     [rsp+180h+var_148], ebx
0x14001fdc8  lea     rax, [rsp+180h+var_140]
0x14001fdcd  mov     [rsp+180h+var_158], rax
0x14001fdd2  lea     rax, [rsp+180h+var_148]
0x14001fdd7  mov     [rsp+180h+ppv], rax
0x14001fddc  lea     rdx, word_14006A256
0x14001fde3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14001fde8  nop
0x14001fde9  call    cs:__imp_CoUninitialize
0x14001fdef  nop
0x14001fdf0  mov     rcx, [rsp+180h+var_150]
0x14001fdf5  test    rcx, rcx
0x14001fdf8  jz      short loc_14001FE07
0x14001fdfa  mov     rax, [rcx]
0x14001fdfd  mov     rax, [rax+10h]
0x14001fe01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fe06  nop
0x14001fe07  jmp     loc_14001FCBC
0x14001fe0c  mov     dword ptr [rbp+80h+var_D8+8], r12d
0x14001fe10  cmp     qword ptr [rdi+18h], 7
0x14001fe15  jbe     short loc_14001FE1A
0x14001fe17  mov     rdi, [rdi]
0x14001fe1a  mov     qword ptr [rbp+80h+var_D8], rdi
0x14001fe1e  mov     qword ptr [rbp+80h+var_D8+0Ch], 2
0x14001fe26  mov     dword ptr [rbp+80h+var_B8+4], r14d
0x14001fe2a  mov     rcx, [rsp+180h+var_150]
0x14001fe2f  mov     rax, [rcx]
0x14001fe32  mov     [rsp+180h+ppv], r14
0x14001fe37  xor     r9d, r9d
0x14001fe3a  lea     edi, [r9+30h]
0x14001fe3e  mov     r8d, edi
0x14001fe41  lea     rdx, [rbp+80h+var_D8]
0x14001fe45  mov     rax, [rax+20h]
0x14001fe49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fe4e  test    eax, eax
0x14001fe50  jns     loc_14001FF0A
0x14001fe56  mov     rcx, [rsp+180h+var_150]
0x14001fe5b  mov     rax, [rcx]
0x14001fe5e  mov     [rsp+180h+ppv], r14
0x14001fe63  xor     r9d, r9d
0x14001fe66  mov     r8d, edi
0x14001fe69  lea     rdx, [rbp+80h+var_D8]
0x14001fe6d  mov     rax, [rax+20h]
0x14001fe71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fe76  and     eax, 1FFF0000h
0x14001fe7b  mov     rcx, [rsp+180h+var_150]
0x14001fe80  mov     [rsp+180h+ppv], r14
0x14001fe85  xor     r9d, r9d
0x14001fe88  mov     r8d, edi
0x14001fe8b  lea     rdx, [rbp+80h+var_D8]
0x14001fe8f  cmp     eax, 70000h
0x14001fe94  mov     rax, [rcx]
0x14001fe97  mov     rax, [rax+20h]
0x14001fe9b  jnz     short loc_14001FEA7
0x14001fe9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fea2  movzx   ebx, ax
0x14001fea5  jmp     short loc_14001FEAE
0x14001fea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001feac  mov     ebx, eax
0x14001feae  test    ebx, ebx
0x14001feb0  jz      short loc_14001FF0A
0x14001feb2  mov     ecx, cs:dword_140075078
0x14001feb8  cmp     ecx, 2
0x14001febb  jbe     short loc_14001FEE7
0x14001febd  mov     [rsp+180h+var_140], r15
0x14001fec2  mov     [rsp+180h+var_148], ebx
0x14001fec6  lea     rax, [rsp+180h+var_140]
0x14001fecb  mov     [rsp+180h+var_158], rax
0x14001fed0  lea     rax, [rsp+180h+var_148]
0x14001fed5  mov     [rsp+180h+ppv], rax
0x14001feda  lea     rdx, word_14006A222
0x14001fee1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14001fee6  nop
0x14001fee7  call    cs:__imp_CoUninitialize
0x14001feed  nop
0x14001feee  mov     rcx, [rsp+180h+var_150]
0x14001fef3  test    rcx, rcx
0x14001fef6  jz      short loc_14001FF05
0x14001fef8  mov     rax, [rcx]
0x14001fefb  mov     rax, [rax+10h]
0x14001feff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ff04  nop
0x14001ff05  jmp     loc_14001FCBC
0x14001ff0a  mov     rcx, [rsp+180h+var_150]
0x14001ff0f  mov     rax, [rcx]
0x14001ff12  mov     r8d, edi
0x14001ff15  lea     rdx, [rsp+180h+Src]
0x14001ff1a  mov     rax, [rax+28h]
0x14001ff1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ff23  test    eax, eax
0x14001ff25  jns     loc_14001FFD1
0x14001ff2b  mov     rcx, [rsp+180h+var_150]
0x14001ff30  mov     rax, [rcx]
0x14001ff33  mov     r8d, edi
0x14001ff36  lea     rdx, [rsp+180h+Src]
0x14001ff3b  mov     rax, [rax+28h]
0x14001ff3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ff44  and     eax, 1FFF0000h
0x14001ff49  mov     rcx, [rsp+180h+var_150]
0x14001ff4e  mov     r8d, edi
0x14001ff51  lea     rdx, [rsp+180h+Src]
  ... truncated ...
```
