# DusmWlan::UpdateConnectionList(void)

- ea: `0x180038894`
- end: `0x180038b84`
- name: `?UpdateConnectionList@DusmWlan@@AEBAXXZ`
- size: `752`
- prototype: `void __fastcall(DusmWlan *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18003870c`

## callees

- `0x180001234`
- `0x180007c90`
- `0x18000e828`
- `0x180012368`
- `0x180013114`
- `0x180013444`
- `0x18001db50`
- `0x18002f510`
- `0x180036910`
- `0x180036a38`
- `0x180036a80`
- `0x180038894`

## import_xrefs

- `wlanapi!WlanEnumInterfaces` at `0x1800388f8`
- `wlanapi!WlanEnumInterfaces` at `0x1800388f8`
- `wlanapi!WlanFreeMemory` at `0x180038b3d`
- `wlanapi!WlanFreeMemory` at `0x180038b5a`
- `wlanapi!WlanFreeMemory` at `0x180038b3d`
- `wlanapi!WlanFreeMemory` at `0x180038b5a`
- `wlanapi!WlanQueryInterface` at `0x1800389bc`
- `wlanapi!WlanQueryInterface` at `0x1800389bc`

## string_xrefs

- `0x180038908`: `DusmWlan::UpdateConnectionList::WlanEnumInterfaces`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall DusmWlan::UpdateConnectionList(DusmWlan *this)
{
  DWORD v2; // ebx
  __int64 *v3; // rax
  __int64 v4; // rcx
  DWORD v5; // eax
  unsigned int v6; // edi
  __m128i si128; // xmm6
  PVOID v8; // rdx
  unsigned int v9; // eax
  char *v10; // rsi
  __int64 *v11; // rax
  __int64 v12; // rcx
  DWORD v13; // r14d
  __int64 v14; // rdx
  __int64 v15; // rcx
  _DWORD *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // r14
  __int128 *v20; // rcx
  __int64 v21; // rdx
  PVOID v22; // rcx
  PVOID *ppData; // [rsp+30h] [rbp-D8h]
  DWORD v24; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v25; // [rsp+50h] [rbp-B8h] BYREF
  __m128i ppInterfaceList_8; // [rsp+60h] [rbp-A8h]
  _QWORD v27[3]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v28; // [rsp+88h] [rbp-80h]
  __int64 v29; // [rsp+98h] [rbp-70h]
  __int64 v30; // [rsp+A0h] [rbp-68h]
  int v31; // [rsp+A8h] [rbp-60h]
  __int128 v32; // [rsp+B0h] [rbp-58h]
  __int64 v33; // [rsp+C0h] [rbp-48h]
  __int64 v34; // [rsp+C8h] [rbp-40h]
  _BYTE v35[32]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v36[32]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v37[56]; // [rsp+118h] [rbp+10h] BYREF
  __int64 v38; // [rsp+150h] [rbp+48h]
  PVOID pMemory; // [rsp+158h] [rbp+50h] BYREF
  DWORD pdwDataSize; // [rsp+160h] [rbp+58h] BYREF
  PVOID v41; // [rsp+168h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C0h] [rbp+B8h]

  v2 = 0;
  v24 = 0;
  v41 = 0;
  *(_QWORD *)&v25 = &v41;
  *((_QWORD *)&v25 + 1) = 0;
  ppInterfaceList_8.m128i_i8[0] = 1;
  v3 = (__int64 *)*((_QWORD *)this + 5);
  if ( v3 )
    v4 = *v3;
  else
    v4 = -1;
  v5 = WlanEnumInterfaces((HANDLE)v4, 0, (PWLAN_INTERFACE_INFO_LIST *)&v25 + 1);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x164,
    (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmwlan.cpp",
    (const char *)v5,
    (unsigned int)"DusmWlan::UpdateConnectionList::WlanEnumInterfaces",
    (const char *)ppData);
  wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<WLAN_ALL_INTERFACES_INFO_LIST,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<WLAN_ALL_INTERFACES_INFO_LIST,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>((__int64)&v25);
  v6 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v8 = v41;
    v9 = v41 ? *(_DWORD *)v41 : 0;
    if ( v6 >= v9 )
      break;
    v10 = (char *)v41 + 532 * v6;
    pdwDataSize = 0;
    pMemory = 0;
    *(_QWORD *)&v25 = &pMemory;
    *((_QWORD *)&v25 + 1) = 0;
    ppInterfaceList_8.m128i_i8[0] = 1;
    v11 = (__int64 *)*((_QWORD *)this + 5);
    if ( v11 )
      v12 = *v11;
    else
      v12 = -1;
    v13 = WlanQueryInterface(
            (HANDLE)v12,
            (const GUID *)(v10 + 8),
            wlan_intf_opcode_current_connection,
            0,
            &pdwDataSize,
            (PVOID *)&v25 + 1,
            0);
    wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<WLAN_ALL_INTERFACES_INFO_LIST,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<WLAN_ALL_INTERFACES_INFO_LIST,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>((__int64)&v25);
    if ( v13 )
    {
      v16 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v15, v14) + 8);
      if ( *v16 > 5u )
      {
        v24 = v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (int)v16,
          (int)word_180059852,
          v17,
          v18,
          (__int64)&v24);
      }
    }
    v19 = std::wstring::wstring((__int64)v36, (__int64)(v10 + 24));
    if ( pMemory )
    {
      v20 = (__int128 *)std::wstring::wstring((__int64)v35, (__int64)pMemory + 8);
      v2 |= 1u;
    }
    else
    {
      v25 = 0;
      ppInterfaceList_8 = si128;
      LOWORD(v25) = 0;
      v20 = &v25;
      v2 |= 2u;
    }
    v24 = v2;
    *(_OWORD *)&v27[1] = *(_OWORD *)(v10 + 8);
    v28 = 0;
    v28 = *(_OWORD *)v19;
    v29 = *(_QWORD *)(v19 + 16);
    v30 = *(_QWORD *)(v19 + 24);
    *(_QWORD *)(v19 + 24) = 7;
    *(_WORD *)v19 = 0;
    *(_QWORD *)(v19 + 16) = 0;
    v31 = *((_DWORD *)v10 + 134);
    v32 = 0;
    v32 = *v20;
    v33 = *((_QWORD *)v20 + 2);
    v34 = *((_QWORD *)v20 + 3);
    *(_WORD *)v20 = 0;
    *((_QWORD *)v20 + 2) = 0;
    *((_QWORD *)v20 + 3) = 7;
    v38 = 0;
    v38 = std::_Global_new_std::_Func_impl_no_alloc__DusmWlan::UpdateConnectionList_::_4_::_lambda_1__void___DusmWlan::UpdateConnectionList_::_4_::_lambda_1___(&v27[1]);
    DusmAsync::SubmitOrderedWork((__int64)v37);
    std::function<long (void)>::~function<long (void)>((__int64)v37, v21);
    DusmWlan::UpdateConnectionList_::_4_::_lambda_1_::__lambda_1_(&v27[1]);
    if ( (v2 & 2) != 0 )
    {
      v2 &= ~2u;
      std::wstring::_Tidy_deallocate(&v25);
    }
    if ( (v2 & 1) != 0 )
    {
      v2 &= ~1u;
      std::wstring::_Tidy_deallocate(v35);
    }
    std::wstring::_Tidy_deallocate(v36);
    v22 = pMemory;
    pMemory = 0;
    if ( v22 )
      WlanFreeMemory(v22);
    ++v6;
  }
  v41 = 0;
  if ( v8 )
    WlanFreeMemory(v8);
}

```

## disassembly

```asm
0x180038894  mov     rax, rsp
0x180038897  push    rbp
0x180038898  push    rbx
0x180038899  push    rsi
0x18003889a  push    rdi
0x18003889b  push    r14
0x18003889d  push    r15
0x18003889f  lea     rbp, [rax-0B8h]
0x1800388a6  sub     rsp, 188h
0x1800388ad  movaps  xmmword ptr [rax-48h], xmm6
0x1800388b1  mov     rax, cs:__security_cookie
0x1800388b8  xor     rax, rsp
0x1800388bb  mov     qword ptr [rbp+0B0h+var_48], rax
0x1800388bf  mov     r15, rcx
0x1800388c2  xor     ebx, ebx
0x1800388c4  mov     dword ptr [rsp+1B0h+var_170], ebx
0x1800388c8  mov     [rbp+0B0h+var_50], rbx
0x1800388cc  lea     rax, [rbp+0B0h+var_50]
0x1800388d0  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x1800388d5  mov     qword ptr [rsp+1B0h+ppInterfaceList], rbx
0x1800388da  mov     [rsp+1B0h+ppInterfaceList+8], 1
0x1800388df  mov     rax, [rcx+28h]
0x1800388e3  test    rax, rax
0x1800388e6  jz      short loc_1800388ED
0x1800388e8  mov     rcx, [rax]
0x1800388eb  jmp     short loc_1800388F1
0x1800388ed  or      rcx, 0FFFFFFFFFFFFFFFFh; hClientHandle
0x1800388f1  lea     r8, [rsp+1B0h+ppInterfaceList]; ppInterfaceList
0x1800388f6  xor     edx, edx; pReserved
0x1800388f8  call    cs:__imp_WlanEnumInterfaces
0x1800388fe  mov     r9d, eax; char *
0x180038901  mov     rcx, [rbp+0B8h]; this
0x180038908  lea     rax, aDusmwlanUpdate; "DusmWlan::UpdateConnectionList::WlanEnu"...
0x18003890f  mov     [rsp+1B0h+pdwDataSize], rax; unsigned int
0x180038914  lea     r8, aOnecoreuapNetD_11; "onecoreuap\\net\\dusm\\lib\\dusmwlan.cp"...
0x18003891b  mov     edx, 164h; void *
0x180038920  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180038925  nop
0x180038926  lea     rcx, [rsp+1B0h+var_170+8]
0x18003892b  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@UWLAN_ALL_INTERFACES_INFO_LIST@@U?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<WLAN_ALL_INTERFACES_INFO_LIST,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<WLAN_ALL_INTERFACES_INFO_LIST,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x180038930  xor     edi, edi
0x180038932  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18003893a  mov     rdx, [rbp+0B0h+var_50]
0x18003893e  test    rdx, rdx
0x180038941  jz      short loc_180038947
0x180038943  mov     eax, [rdx]
0x180038945  jmp     short loc_180038949
0x180038947  xor     eax, eax
0x180038949  cmp     edi, eax
0x18003894b  jnb     loc_180038B4A
0x180038951  mov     eax, edi
0x180038953  imul    rsi, rax, 214h
0x18003895a  add     rsi, rdx
0x18003895d  mov     [rbp+0B0h+var_58], 0
0x180038964  mov     [rbp+0B0h+pMemory], 0
0x18003896c  lea     rax, [rbp+0B0h+pMemory]
0x180038970  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x180038975  mov     qword ptr [rsp+1B0h+ppInterfaceList], 0
0x18003897e  mov     [rsp+1B0h+ppInterfaceList+8], 1
0x180038983  mov     rax, [r15+28h]
0x180038987  test    rax, rax
0x18003898a  jz      short loc_180038991
0x18003898c  mov     rcx, [rax]
0x18003898f  jmp     short loc_180038995
0x180038991  or      rcx, 0FFFFFFFFFFFFFFFFh; hClientHandle
0x180038995  mov     qword ptr [rsp+30h], 0; pWlanOpcodeValueType
0x18003899e  lea     rax, [rsp+1B0h+ppInterfaceList]
0x1800389a3  mov     [rsp+1B0h+ppData], rax; ppData
0x1800389a8  lea     rax, [rbp+0B0h+var_58]
0x1800389ac  mov     [rsp+1B0h+pdwDataSize], rax; pdwDataSize
0x1800389b1  xor     r9d, r9d; pReserved
0x1800389b4  lea     r8d, [r9+7]; OpCode
0x1800389b8  lea     rdx, [rsi+8]; pInterfaceGuid
0x1800389bc  call    cs:__imp_WlanQueryInterface
0x1800389c2  mov     r14d, eax
0x1800389c5  lea     rcx, [rsp+1B0h+var_170+8]
0x1800389ca  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@UWLAN_ALL_INTERFACES_INFO_LIST@@U?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<WLAN_ALL_INTERFACES_INFO_LIST,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<WLAN_ALL_INTERFACES_INFO_LIST,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x1800389cf  test    r14d, r14d
0x1800389d2  jz      short loc_1800389FF
0x1800389d4  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x1800389d9  mov     rcx, [rax+8]
0x1800389dd  mov     edx, [rcx]
0x1800389df  cmp     edx, 5
0x1800389e2  jbe     short loc_1800389FF
0x1800389e4  mov     dword ptr [rsp+1B0h+var_170], r14d
0x1800389e9  lea     rax, [rsp+1B0h+var_170]
0x1800389ee  mov     [rsp+1B0h+pdwDataSize], rax
0x1800389f3  lea     rdx, word_180059852
0x1800389fa  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800389ff  lea     rdx, [rsi+18h]
0x180038a03  lea     rcx, [rbp+0B0h+var_C0]
0x180038a07  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180038a0c  mov     r14, rax
0x180038a0f  mov     rdx, [rbp+0B0h+pMemory]
0x180038a13  test    rdx, rdx
0x180038a16  jz      short loc_180038A2D
0x180038a18  add     rdx, 8
0x180038a1c  lea     rcx, [rbp+0B0h+var_E0]
0x180038a20  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180038a25  mov     rcx, rax
0x180038a28  or      ebx, 1
0x180038a2b  jmp     short loc_180038A4A
0x180038a2d  xorps   xmm0, xmm0
0x180038a30  movups  [rsp+1B0h+var_170+8], xmm0
0x180038a35  movdqu  xmmword ptr [rsp+1B0h+ppInterfaceList+8], xmm6
0x180038a3b  xor     eax, eax
0x180038a3d  mov     word ptr [rsp+1B0h+var_170+8], ax
0x180038a42  lea     rcx, [rsp+1B0h+var_170+8]
0x180038a47  or      ebx, 2
0x180038a4a  mov     dword ptr [rsp+1B0h+var_170], ebx
0x180038a4e  movups  xmm0, xmmword ptr [rsi+8]
0x180038a52  movdqu  xmmword ptr [rsp+1B0h+var_148+8], xmm0
0x180038a58  xorps   xmm1, xmm1
0x180038a5b  movups  [rbp+0B0h+var_130], xmm1
0x180038a5f  mov     rax, [r14]
0x180038a62  mov     qword ptr [rbp+0B0h+var_130], rax
0x180038a66  mov     rax, [r14+8]
0x180038a6a  mov     qword ptr [rbp+0B0h+var_130+8], rax
0x180038a6e  mov     rax, [r14+10h]
0x180038a72  mov     [rbp+0B0h+var_120], rax
0x180038a76  mov     rax, [r14+18h]
0x180038a7a  mov     [rbp+0B0h+var_118], rax
0x180038a7e  mov     edx, 7
0x180038a83  mov     [r14+18h], rdx
0x180038a87  xor     eax, eax
0x180038a89  mov     [r14], ax
0x180038a8d  mov     [r14+10h], rax
0x180038a91  mov     eax, [rsi+218h]
0x180038a97  mov     [rbp+0B0h+var_110], eax
0x180038a9a  xorps   xmm0, xmm0
0x180038a9d  movups  [rbp+0B0h+var_108], xmm0
0x180038aa1  mov     rax, [rcx]
0x180038aa4  mov     qword ptr [rbp+0B0h+var_108], rax
0x180038aa8  mov     rax, [rcx+8]
0x180038aac  mov     qword ptr [rbp+0B0h+var_108+8], rax
0x180038ab0  mov     rax, [rcx+10h]
0x180038ab4  mov     [rbp+0B0h+var_F8], rax
0x180038ab8  mov     rax, [rcx+18h]
0x180038abc  mov     [rbp+0B0h+var_F0], rax
0x180038ac0  xor     eax, eax
0x180038ac2  mov     [rcx], ax
0x180038ac5  mov     [rcx+10h], rax
0x180038ac9  mov     [rcx+18h], rdx
0x180038acd  mov     [rbp+0B0h+var_68], rax
0x180038ad1  lea     rcx, [rsp+1B0h+var_148+8]
0x180038ad6  call    std___Global_new_std___Func_impl_no_alloc__DusmWlan__UpdateConnectionList____4____lambda_1__void___DusmWlan__UpdateConnectionList____4____lambda_1___
0x180038adb  mov     [rbp+0B0h+var_68], rax
0x180038adf  lea     rcx, [rbp+0B0h+var_A0]
0x180038ae3  call    ?SubmitOrderedWork@DusmAsync@@SAX$$QEAV?$function@$$A6AXXZ@std@@@Z; DusmAsync::SubmitOrderedWork(std::function<void (void)> &&)
0x180038ae8  lea     rcx, [rbp+0B0h+var_A0]
0x180038aec  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180038af1  nop
0x180038af2  lea     rcx, [rsp+1B0h+var_148+8]
0x180038af7  call    _DusmWlan__UpdateConnectionList____4____lambda_1_____lambda_1_
0x180038afc  nop
0x180038afd  test    bl, 2
0x180038b00  jz      short loc_180038B10
0x180038b02  and     ebx, 0FFFFFFFDh
0x180038b05  lea     rcx, [rsp+1B0h+var_170+8]
0x180038b0a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038b0f  nop
0x180038b10  test    bl, 1
0x180038b13  jz      short loc_180038B22
0x180038b15  and     ebx, 0FFFFFFFEh
0x180038b18  lea     rcx, [rbp+0B0h+var_E0]
0x180038b1c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038b21  nop
0x180038b22  lea     rcx, [rbp+0B0h+var_C0]
0x180038b26  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038b2b  nop
0x180038b2c  mov     rcx, [rbp+0B0h+pMemory]; pMemory
0x180038b30  mov     [rbp+0B0h+pMemory], 0
0x180038b38  test    rcx, rcx
0x180038b3b  jz      short loc_180038B43
0x180038b3d  call    cs:__imp_WlanFreeMemory
0x180038b43  inc     edi
0x180038b45  jmp     loc_18003893A
0x180038b4a  mov     [rbp+0B0h+var_50], 0
0x180038b52  test    rdx, rdx
0x180038b55  jz      short loc_180038B60
0x180038b57  mov     rcx, rdx; pMemory
0x180038b5a  call    cs:__imp_WlanFreeMemory
0x180038b60  mov     rcx, qword ptr [rbp+0B0h+var_48]
0x180038b64  xor     rcx, rsp; StackCookie
0x180038b67  call    __security_check_cookie
0x180038b6c  movaps  xmm6, [rsp+1B0h+var_48+8]
0x180038b74  add     rsp, 188h
0x180038b7b  pop     r15
0x180038b7d  pop     r14
0x180038b7f  pop     rdi
0x180038b80  pop     rsi
0x180038b81  pop     rbx
0x180038b82  pop     rbp
0x180038b83  retn
```
