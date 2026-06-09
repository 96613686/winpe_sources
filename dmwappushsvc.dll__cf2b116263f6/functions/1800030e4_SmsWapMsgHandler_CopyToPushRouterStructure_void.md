# SmsWapMsgHandler::CopyToPushRouterStructure(void)

- ea: `0x1800030e4`
- end: `0x180003601`
- name: `?CopyToPushRouterStructure@SmsWapMsgHandler@@AEAAJXZ`
- size: `1309`
- prototype: `__int64 __fastcall(SmsWapMsgHandler *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180003d3c`

## callees

- `0x180001008`
- `0x180001a70`
- `0x180001aa0`
- `0x18000280c`
- `0x180002b88`
- `0x180002ed8`
- `0x180002f80`
- `0x1800030e4`
- `0x180003c4c`
- `0x180003d10`
- `0x1800040a4`
- `0x1800042dc`
- `0x180004824`
- `0x180004a18`
- `0x180012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180003482`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180003482`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003268`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000335b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003500`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003513`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003268`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000335b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003500`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003513`

## pseudocode

```c
__int64 __fastcall SmsWapMsgHandler::CopyToPushRouterStructure(SmsWapMsgHandler *this)
{
  SmsWapMsgHandler *v1; // rsi
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64, void (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  void (__fastcall ***v4)(_QWORD, _QWORD, _QWORD); // rbx
  void (__fastcall *v5)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v6; // rdi
  void (__fastcall *v7)(__int64, __int64 *); // rbx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // ebx
  int v11; // r8d
  int v12; // r9d
  PCWSTR StringRawBuffer; // rdi
  __int64 v14; // rcx
  __int64 *v15; // rdx
  PCWSTR v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // kr10_8
  _QWORD *v22; // rax
  _QWORD *v23; // rbx
  __int64 v24; // rax
  int v25; // ebx
  __int64 v26; // rax
  const unsigned __int16 *v27; // rax
  _BYTE v29[4]; // [rsp+40h] [rbp-1D8h] BYREF
  int v30; // [rsp+44h] [rbp-1D4h] BYREF
  __int64 v31; // [rsp+48h] [rbp-1D0h] BYREF
  __int64 v32; // [rsp+50h] [rbp-1C8h] BYREF
  __int64 v33; // [rsp+58h] [rbp-1C0h] BYREF
  void (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-1B8h] BYREF
  UINT32 length; // [rsp+68h] [rbp-1B0h] BYREF
  HSTRING v36; // [rsp+70h] [rbp-1A8h] BYREF
  HSTRING string; // [rsp+78h] [rbp-1A0h] BYREF
  unsigned __int16 *v38; // [rsp+80h] [rbp-198h] BYREF
  _BYTE v39[16]; // [rsp+90h] [rbp-188h] BYREF
  _BYTE v40[240]; // [rsp+A0h] [rbp-178h] BYREF
  char *v41; // [rsp+190h] [rbp-88h] BYREF
  __int16 v42; // [rsp+198h] [rbp-80h]
  __int64 v43; // [rsp+1B0h] [rbp-68h] BYREF
  __int16 v44; // [rsp+1B8h] [rbp-60h]
  unsigned __int16 v45[21]; // [rsp+1D0h] [rbp-48h] BYREF

  v1 = this;
  v38 = (unsigned __int16 *)this;
  length = 0;
  v34 = 0;
  v29[0] = 0;
  string = 0;
  v36 = 0;
  v33 = 0;
  v32 = 0;
  v31 = 0;
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v39);
  memset(v45, 0, sizeof(v45));
  v2 = *((_QWORD *)v1 + 1);
  v3 = *(void (__fastcall **)(__int64, void (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v2 + 96LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v34);
  v3(v2, &v34);
  v4 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v34;
  v5 = **v34;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v33);
  v5(v4, &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b, &v33);
  v6 = v33;
  v7 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v31);
  v7(v6, &v31);
  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v31 + 56LL))(v31, v29);
  while ( v29[0] )
  {
    v8 = v31;
    v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v32);
    v10 = v9(v8, &v32);
    if ( v10 < 0 )
      goto LABEL_7;
    v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 48LL))(v32, &string);
    if ( v10 < 0 )
      goto LABEL_7;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !StringRawBuffer )
      goto LABEL_6;
    v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 56LL))(v32, &v36);
    if ( v10 < 0 )
      goto LABEL_7;
    v16 = WindowsGetStringRawBuffer(v36, 0);
    if ( !v16 )
    {
LABEL_6:
      v10 = -2147418113;
LABEL_7:
      v14 = 10;
      goto LABEL_8;
    }
    try
    {
      v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v40, StringRawBuffer);
      v18 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v17, L": ");
      v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, v16);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v19, L"\r\n");
    }
    catch ( ... )
    {
      v30 = -2147024882;
      v10 = -2147024882;
      v1 = (SmsWapMsgHandler *)v38;
      goto LABEL_7;
    }
    v10 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v31 + 64LL))(v31, v29);
    if ( v10 < 0 )
      goto LABEL_7;
  }
  v21 = *(_QWORD *)(std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                      v39,
                      &v41)
                  + 16)
      + 1LL;
  v20 = 2 * v21;
  if ( !is_mul_ok(v21, 2u) )
    v20 = -1;
  *((_QWORD *)v1 + 6) = operator new[](v20, (const struct std::nothrow_t *)&std::nothrow);
  std::wstring::_Tidy_deallocate(&v41);
  if ( !*((_QWORD *)v1 + 6) )
  {
    v10 = -2147024882;
    goto LABEL_7;
  }
  v22 = (_QWORD *)std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                    v39,
                    &v43);
  v23 = v22;
  if ( v22[3] > 7u )
    v23 = (_QWORD *)*v22;
  v24 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
          v39,
          &v41);
  v25 = _o_wcscpy_s(*((_QWORD *)v1 + 6), *(_QWORD *)(v24 + 16) + 1LL, v23);
  std::wstring::_Tidy_deallocate(&v41);
  std::wstring::_Tidy_deallocate(&v43);
  if ( v25 || (v26 = *((_QWORD *)v1 + 6), (*((_QWORD *)v1 + 8) = v26) == 0) )
  {
    v10 = -2147467259;
    goto LABEL_7;
  }
  *((_DWORD *)v1 + 14) = 56;
  *((_QWORD *)v1 + 9) = *((_QWORD *)v1 + 2);
  *((_DWORD *)v1 + 20) = *((_DWORD *)v1 + 6);
  *((_DWORD *)v1 + 21) = 2;
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v1 + 1) + 64LL))(
          *((_QWORD *)v1 + 1),
          (__int64)v1 + 40);
  if ( v10 < 0 )
    goto LABEL_7;
  *((_QWORD *)v1 + 11) = WindowsGetStringRawBuffer(*((HSTRING *)v1 + 5), 0);
  v27 = WindowsGetStringRawBuffer(*((HSTRING *)v1 + 4), &length);
  v10 = StringCchCopyW(v45, 0x15u, v27);
  if ( v10 < 0 )
    goto LABEL_7;
  v10 = IccidStringToBCD((const unsigned __int16 (*)[21])v45, (unsigned __int8 (*)[10])((unsigned __int8 *)v1 + 16));
  if ( v10 < 0 )
    goto LABEL_7;
  *((_QWORD *)v1 + 12) = (char *)v1 + 160;
  v14 = 10;
  *((_DWORD *)v1 + 26) = 10;
LABEL_8:
  if ( (unsigned int)dword_18001C048 > 4 )
  {
    v30 = v10;
    v43 = *((_QWORD *)v1 + 2);
    v44 = *((_WORD *)v1 + 12);
    v41 = (char *)v1 + 160;
    v42 = 10;
    v38 = v45;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(
      10,
      (unsigned int)word_18001627A,
      v11,
      v12,
      (__int64)&v38,
      (__int64)&v41,
      (__int64)&v43,
      (__int64)&v30);
  }
  if ( v10 >= 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
    {
      v15 = PushRouterDmWapPushServiceCopyingMessageIntoPushRouterStructSucceeded;
      goto LABEL_33;
    }
  }
  else if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
  {
    v15 = PushRouterDmWapPushServiceCopyingMessageIntoPushRouterStructFailed;
LABEL_33:
    McTemplateU0zd_EventWriteTransfer(v14, v15, v45, (unsigned int)v10);
  }
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v39);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v33);
  Windows::Internal::String::~String((Windows::Internal::String *)&v36);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v34);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800030e4  mov     [rsp+arg_8], rbx
0x1800030e9  mov     [rsp+arg_10], rsi
0x1800030ee  push    rdi
0x1800030ef  sub     rsp, 210h
0x1800030f6  mov     rax, cs:__security_cookie
0x1800030fd  xor     rax, rsp
0x180003100  mov     [rsp+218h+var_18], rax
0x180003108  mov     rsi, rcx
0x18000310b  mov     [rsp+218h+var_198], rcx
0x180003113  mov     [rsp+218h+length], 0
0x18000311b  mov     [rsp+218h+var_1B8], 0
0x180003124  mov     [rsp+218h+var_1D8], 0
0x180003129  mov     [rsp+218h+string], 0
0x180003132  mov     [rsp+218h+var_1A8], 0
0x18000313b  mov     [rsp+218h+var_1C0], 0
0x180003144  mov     [rsp+218h+var_1C8], 0
0x18000314d  mov     [rsp+218h+var_1D0], 0
0x180003156  lea     rcx, [rsp+218h+var_188]
0x18000315e  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180003163  nop
0x180003164  xorps   xmm0, xmm0
0x180003167  movups  xmmword ptr [rsp+218h+var_48], xmm0
0x18000316f  movups  xmmword ptr [rsp+218h+var_48+10h], xmm0
0x180003177  movups  xmmword ptr [rsp+218h+var_48+1Ah], xmm0
0x18000317f  mov     rdi, [rsi+8]
0x180003183  mov     rax, [rdi]
0x180003186  mov     rbx, [rax+60h]
0x18000318a  lea     rcx, [rsp+218h+var_1B8]
0x18000318f  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x180003194  lea     rdx, [rsp+218h+var_1B8]
0x180003199  mov     rcx, rdi
0x18000319c  mov     rax, rbx
0x18000319f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a4  nop
0x1800031a5  mov     rbx, [rsp+218h+var_1B8]
0x1800031aa  mov     rax, [rbx]
0x1800031ad  mov     rdi, [rax]
0x1800031b0  lea     rcx, [rsp+218h+var_1C0]
0x1800031b5  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x1800031ba  lea     r8, [rsp+218h+var_1C0]
0x1800031bf  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x1800031c6  mov     rcx, rbx
0x1800031c9  mov     rax, rdi
0x1800031cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031d1  nop
0x1800031d2  mov     rdi, [rsp+218h+var_1C0]
0x1800031d7  mov     rax, [rdi]
0x1800031da  mov     rbx, [rax+30h]
0x1800031de  lea     rcx, [rsp+218h+var_1D0]
0x1800031e3  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x1800031e8  lea     rdx, [rsp+218h+var_1D0]
0x1800031ed  mov     rcx, rdi
0x1800031f0  mov     rax, rbx
0x1800031f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031f8  mov     rcx, [rsp+218h+var_1D0]
0x1800031fd  mov     rax, [rcx]
0x180003200  lea     rdx, [rsp+218h+var_1D8]
0x180003205  mov     rax, [rax+38h]
0x180003209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000320e  cmp     [rsp+218h+var_1D8], 0
0x180003213  jz      loc_1800033DD
0x180003219  mov     rdi, [rsp+218h+var_1D0]
0x18000321e  mov     rax, [rdi]
0x180003221  mov     rbx, [rax+30h]
0x180003225  lea     rcx, [rsp+218h+var_1C8]
0x18000322a  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18000322f  lea     rdx, [rsp+218h+var_1C8]
0x180003234  mov     rcx, rdi
0x180003237  mov     rax, rbx
0x18000323a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000323f  mov     ebx, eax
0x180003241  test    eax, eax
0x180003243  js      short loc_18000327F
0x180003245  mov     rcx, [rsp+218h+var_1C8]
0x18000324a  mov     rax, [rcx]
0x18000324d  lea     rdx, [rsp+218h+string]
0x180003252  mov     rax, [rax+30h]
0x180003256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000325b  mov     ebx, eax
0x18000325d  test    eax, eax
0x18000325f  js      short loc_18000327F
0x180003261  xor     edx, edx; length
0x180003263  mov     rcx, [rsp+218h+string]; string
0x180003268  call    cs:__imp_WindowsGetStringRawBuffer
0x18000326e  mov     rdi, rax
0x180003271  test    rax, rax
0x180003274  jnz     loc_180003334
0x18000327a  mov     ebx, 8000FFFFh
0x18000327f  mov     ecx, 0Ah
0x180003284  mov     eax, cs:dword_18001C048
0x18000328a  cmp     eax, 4
0x18000328d  jbe     loc_180003313
0x180003293  mov     [rsp+218h+var_1D4], ebx
0x180003297  mov     rax, [rsi+10h]
0x18000329b  mov     [rsp+218h+var_68], rax
0x1800032a3  movzx   eax, word ptr [rsi+18h]
0x1800032a7  mov     [rsp+218h+var_60], ax
0x1800032af  lea     rax, [rsi+0A0h]
0x1800032b6  mov     [rsp+218h+var_88], rax
0x1800032be  mov     [rsp+218h+var_80], cx
0x1800032c6  lea     rax, [rsp+218h+var_48]
0x1800032ce  mov     [rsp+218h+var_198], rax
0x1800032d6  lea     rax, [rsp+218h+var_1D4]
0x1800032db  mov     [rsp+218h+var_1E0], rax
0x1800032e0  lea     rax, [rsp+218h+var_68]
0x1800032e8  mov     [rsp+218h+var_1E8], rax
0x1800032ed  lea     rax, [rsp+218h+var_88]
0x1800032f5  mov     [rsp+218h+var_1F0], rax
0x1800032fa  lea     rax, [rsp+218h+var_198]
0x180003302  mov     [rsp+218h+var_1F8], rax
0x180003307  lea     rdx, word_18001627A
0x18000330e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperArray@$00@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperArray@$00@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &)
0x180003313  test    ebx, ebx
0x180003315  jns     loc_18000356A
0x18000331b  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x180003322  jz      loc_18000358B
0x180003328  lea     rdx, PushRouterDmWapPushServiceCopyingMessageIntoPushRouterStructFailed
0x18000332f  jmp     loc_18000357A
0x180003334  mov     rcx, [rsp+218h+var_1C8]
0x180003339  mov     rax, [rcx]
0x18000333c  lea     rdx, [rsp+218h+var_1A8]
0x180003341  mov     rax, [rax+38h]
0x180003345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000334a  mov     ebx, eax
0x18000334c  test    eax, eax
0x18000334e  js      loc_18000327F
0x180003354  xor     edx, edx; length
0x180003356  mov     rcx, [rsp+218h+var_1A8]; string
0x18000335b  call    cs:__imp_WindowsGetStringRawBuffer
0x180003361  mov     rbx, rax
0x180003364  test    rax, rax
0x180003367  jz      loc_18000327A
0x18000336d  mov     rdx, rdi
0x180003370  lea     rcx, [rsp+218h+var_178]
0x180003378  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18000337d  lea     rdx, asc_1800142AC; ": "
0x180003384  mov     rcx, rax
0x180003387  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18000338c  mov     rdx, rbx
0x18000338f  mov     rcx, rax
0x180003392  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180003397  lea     rdx, asc_1800142A4; "\r\n"
0x18000339e  mov     rcx, rax
0x1800033a1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800033a6  nop
0x1800033a7  mov     rcx, [rsp+218h+var_1D0]
0x1800033ac  mov     rax, [rcx]
0x1800033af  lea     rdx, [rsp+218h+var_1D8]
0x1800033b4  mov     rax, [rax+40h]
0x1800033b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033bd  mov     ebx, eax
0x1800033bf  test    eax, eax
0x1800033c1  jns     loc_18000320E
0x1800033c7  jmp     loc_18000327F
0x1800033cc  mov     ebx, [rsp+218h+var_1D4]
0x1800033d0  mov     rsi, [rsp+218h+var_198]
0x1800033d8  jmp     loc_18000327F
0x1800033dd  lea     rdx, [rsp+218h+var_88]
0x1800033e5  lea     rcx, [rsp+218h+var_188]
0x1800033ed  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x1800033f2  mov     rcx, [rax+10h]
0x1800033f6  inc     rcx
0x1800033f9  mov     eax, 2
0x1800033fe  mul     rcx
0x180003401  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003408  cmovb   rax, rcx
0x18000340c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003413  mov     rcx, rax; unsigned __int64
0x180003416  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000341b  mov     [rsi+30h], rax
0x18000341f  lea     rcx, [rsp+218h+var_88]
0x180003427  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000342c  cmp     qword ptr [rsi+30h], 0
0x180003431  jnz     short loc_18000343D
0x180003433  mov     ebx, 8007000Eh
0x180003438  jmp     loc_18000327F
0x18000343d  lea     rdx, [rsp+218h+var_68]
0x180003445  lea     rcx, [rsp+218h+var_188]
0x18000344d  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x180003452  mov     rbx, rax
0x180003455  cmp     qword ptr [rax+18h], 7
0x18000345a  jbe     short loc_18000345F
0x18000345c  mov     rbx, [rax]
0x18000345f  lea     rdx, [rsp+218h+var_88]
0x180003467  lea     rcx, [rsp+218h+var_188]
0x18000346f  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x180003474  mov     rdx, [rax+10h]
0x180003478  inc     rdx
0x18000347b  mov     r8, rbx
0x18000347e  mov     rcx, [rsi+30h]
0x180003482  call    cs:__imp__o_wcscpy_s
0x180003488  mov     ebx, eax
0x18000348a  lea     rcx, [rsp+218h+var_88]
0x180003492  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003497  nop
0x180003498  lea     rcx, [rsp+218h+var_68]
0x1800034a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800034a5  test    ebx, ebx
0x1800034a7  jz      short loc_1800034B3
0x1800034a9  mov     ebx, 80004005h
0x1800034ae  jmp     loc_18000327F
0x1800034b3  mov     rax, [rsi+30h]
0x1800034b7  mov     [rsi+40h], rax
0x1800034bb  test    rax, rax
0x1800034be  jz      short loc_1800034A9
0x1800034c0  mov     dword ptr [rsi+38h], 38h ; '8'
0x1800034c7  mov     rax, [rsi+10h]
0x1800034cb  mov     [rsi+48h], rax
0x1800034cf  mov     eax, [rsi+18h]
0x1800034d2  mov     [rsi+50h], eax
0x1800034d5  mov     dword ptr [rsi+54h], 2
0x1800034dc  mov     rcx, [rsi+8]
0x1800034e0  mov     rax, [rcx]
0x1800034e3  lea     rdx, [rsi+28h]
0x1800034e7  mov     rax, [rax+40h]
0x1800034eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034f0  mov     ebx, eax
0x1800034f2  test    eax, eax
0x1800034f4  js      loc_18000327F
0x1800034fa  xor     edx, edx; length
0x1800034fc  mov     rcx, [rsi+28h]; string
0x180003500  call    cs:__imp_WindowsGetStringRawBuffer
0x180003506  mov     [rsi+58h], rax
0x18000350a  lea     rdx, [rsp+218h+length]; length
0x18000350f  mov     rcx, [rsi+20h]; string
0x180003513  call    cs:__imp_WindowsGetStringRawBuffer
0x180003519  mov     r8, rax; unsigned __int16 *
0x18000351c  mov     edx, 15h; unsigned __int64
0x180003521  lea     rcx, [rsp+218h+var_48]; unsigned __int16 *
0x180003529  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000352e  mov     ebx, eax
0x180003530  test    eax, eax
0x180003532  js      loc_18000327F
0x180003538  lea     rdi, [rsi+0A0h]
0x18000353f  mov     rdx, rdi; unsigned __int8 (*)[10]
0x180003542  lea     rcx, [rsp+218h+var_48]; unsigned __int16 (*)[21]
0x18000354a  call    ?IccidStringToBCD@@YAJAEAY0BF@$$CBGAEAY09E@Z; IccidStringToBCD(ushort const (&)[21],uchar (&)[10])
0x18000354f  mov     ebx, eax
0x180003551  test    eax, eax
0x180003553  js      loc_18000327F
0x180003559  mov     [rsi+60h], rdi
0x18000355d  mov     ecx, 0Ah
0x180003562  mov     [rsi+68h], ecx
0x180003565  jmp     loc_180003284
0x18000356a  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x180003571  jz      short loc_18000358B
0x180003573  lea     rdx, PushRouterDmWapPushServiceCopyingMessageIntoPushRouterStructSucceeded
0x18000357a  mov     r9d, ebx
0x18000357d  lea     r8, [rsp+218h+var_48]
0x180003585  call    McTemplateU0zd_EventWriteTransfer
0x18000358a  nop
0x18000358b  lea     rcx, [rsp+218h+var_188]
0x180003593  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x180003598  nop
0x180003599  lea     rcx, [rsp+218h+var_1D0]
0x18000359e  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x1800035a3  nop
0x1800035a4  lea     rcx, [rsp+218h+var_1C8]
0x1800035a9  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x1800035ae  nop
0x1800035af  lea     rcx, [rsp+218h+var_1C0]
0x1800035b4  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x1800035b9  nop
0x1800035ba  lea     rcx, [rsp+218h+var_1A8]; this
0x1800035bf  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800035c4  nop
0x1800035c5  lea     rcx, [rsp+218h+string]; this
0x1800035ca  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800035cf  nop
0x1800035d0  lea     rcx, [rsp+218h+var_1B8]
0x1800035d5  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x1800035da  mov     eax, ebx
0x1800035dc  mov     rcx, [rsp+218h+var_18]
0x1800035e4  xor     rcx, rsp; StackCookie
0x1800035e7  call    __security_check_cookie
0x1800035ec  lea     r11, [rsp+218h+var_8]
0x1800035f4  mov     rbx, [r11+18h]
0x1800035f8  mov     rsi, [r11+20h]
0x1800035fc  mov     rsp, r11
0x1800035ff  pop     rdi
0x180003600  retn
```
