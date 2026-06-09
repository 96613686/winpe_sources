# ModernColorGetGDILutFromHDC(HDC__ *,_GUID,UINT16Triple (&)[256])

- ea: `0x180015fac`
- end: `0x18001662c`
- name: `?ModernColorGetGDILutFromHDC@@YAJPEAUHDC__@@U_GUID@@AEAY0BAA@UUINT16Triple@@@Z`
- size: `1664`
- prototype: `__int64 __fastcall(HDC, struct _GUID *__struct_ptr, struct UINT16Triple (*)[256])`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024f94`

## callees

- `0x180015704`
- `0x180015fac`
- `0x180016ce0`
- `0x18001717c`
- `0x1800173dc`
- `0x180017474`
- `0x1800174f8`
- `0x180017510`
- `0x180017658`
- `0x1800176ac`
- `0x180017a28`
- `0x1800219ec`
- `0x180022a80`
- `0x180023194`
- `0x180027408`
- `0x18002aea8`
- `0x18002e5f0`
- `0x18002f2f4`
- `0x18002f324`
- `0x18002fa57`
- `0x18002fa75`
- `0x18004b320`
- `0x18004c63c`
- `0x180084010`

## import_xrefs

- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTCloseAdapter` at `0x180016040`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTCloseAdapter` at `0x180016040`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTOpenAdapterFromHdc` at `0x180016001`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTOpenAdapterFromHdc` at `0x180016001`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180015fdb`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180015fdb`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x1800161b2`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x1800161b2`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18001637a`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18001637a`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x18001608b`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x18001608b`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall ModernColorGetGDILutFromHDC(HDC a1, struct _GUID *a2, struct UINT16Triple (*a3)[256])
{
  int v6; // eax
  unsigned int v7; // r8d
  unsigned int v8; // ebx
  int v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  unsigned int DisplayConfigBufferSizes; // eax
  const char *v13; // r9
  __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  const char *v17; // r9
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  __int64 v20; // rax
  UINT32 i; // edx
  UINT32 j; // edx
  __int64 v23; // rbx
  DISPLAYCONFIG_PATH_INFO *v24; // rdi
  _WORD *v25; // rcx
  int v26; // edx
  __int64 v27; // rdx
  __int64 v28; // rbx
  __int64 (__fastcall *v29)(__int64, int *, LPVOID *); // rdi
  int v30; // eax
  __int64 v31; // r8
  __int64 v32; // rdx
  char *v33; // rcx
  unsigned int modeInfoArray; // [rsp+20h] [rbp-2E8h]
  UINT32 numPathArrayElements; // [rsp+30h] [rbp-2D8h] BYREF
  __int64 v37; // [rsp+38h] [rbp-2D0h] BYREF
  UINT32 numModeInfoArrayElements; // [rsp+40h] [rbp-2C8h] BYREF
  DISPLAYCONFIG_MODE_INFO *v39[2]; // [rsp+48h] [rbp-2C0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-2B0h]
  DISPLAYCONFIG_PATH_INFO *pathArray; // [rsp+60h] [rbp-2A8h] BYREF
  char *v42; // [rsp+68h] [rbp-2A0h]
  __int64 v43; // [rsp+70h] [rbp-298h]
  int v44; // [rsp+78h] [rbp-290h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-288h] BYREF
  int v46; // [rsp+88h] [rbp-280h]
  int v47; // [rsp+90h] [rbp-278h] BYREF
  _DWORD *hstring_on_heap; // [rsp+98h] [rbp-270h] BYREF
  int v49; // [rsp+A0h] [rbp-268h] BYREF
  HDC v50; // [rsp+A8h] [rbp-260h] BYREF
  __int128 v51; // [rsp+B0h] [rbp-258h]
  _BYTE v52[24]; // [rsp+C0h] [rbp-248h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+E0h] [rbp-228h] BYREF
  _DWORD *v54; // [rsp+F8h] [rbp-210h] BYREF
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+120h] [rbp-1E8h] BYREF
  _WORD v56[134]; // [rsp+1C4h] [rbp-144h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+0h]

  v44 = RoInitialize(1);
  v51 = 0;
  v50 = a1;
  v6 = D3DKMTOpenAdapterFromHdc(&v50);
  if ( v6 < 0 )
  {
    v8 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0xE5,
           v7,
           (const char *)(unsigned int)v6,
           modeInfoArray);
LABEL_65:
    WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)&v44);
    return v8;
  }
  v47 = v51;
  v9 = D3DKMTCloseAdapter(&v47);
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_NtStatus(retaddr, v10, v11, (const char *)(unsigned int)v9, modeInfoArray);
  numPathArrayElements = 0;
  numModeInfoArrayElements = 0;
  std::vector<DISPLAYCONFIG_PATH_INFO>::vector<DISPLAYCONFIG_PATH_INFO>(&pathArray);
  std::vector<DISPLAYCONFIG_PATH_INFO>::vector<DISPLAYCONFIG_PATH_INFO>(v39);
  DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(0x12u, &numPathArrayElements, &numModeInfoArrayElements);
  if ( DisplayConfigBufferSizes )
  {
    v14 = 240;
LABEL_7:
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v14,
           (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\internalgamma.cxx",
           (const char *)DisplayConfigBufferSizes,
           modeInfoArray);
    std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy((__int64)v39);
    std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)&pathArray);
    goto LABEL_65;
  }
  try
  {
    v15 = 0x8E38E38E38E38E39uLL * ((v42 - (char *)pathArray) >> 3);
    if ( numPathArrayElements >= v15 )
    {
      if ( numPathArrayElements > v15 )
      {
        if ( numPathArrayElements <= 0x8E38E38E38E38E39uLL * ((v43 - (__int64)pathArray) >> 3) )
          v42 = std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(
                  v42,
                  numPathArrayElements - v15);
        else
          std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(
            (const void **)&pathArray,
            numPathArrayElements);
      }
    }
    else
    {
      v42 = (char *)&pathArray[numPathArrayElements];
    }
    v16 = v39[1] - v39[0];
    if ( numModeInfoArrayElements >= v16 )
    {
      if ( numModeInfoArrayElements > v16 )
      {
        if ( numModeInfoArrayElements <= (unsigned __int64)((signed __int64)(v40 - (unsigned __int64)v39[0]) >> 6) )
          v39[1] = (DISPLAYCONFIG_MODE_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(
                                                (char *)v39[1],
                                                numModeInfoArrayElements - v16);
        else
          std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(
            (const void **)v39,
            numModeInfoArrayElements);
      }
    }
    else
    {
      v39[1] = &v39[0][(unsigned __int64)numModeInfoArrayElements];
    }
  }
  catch ( ... )
  {
    LODWORD(v37) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xF8,
                     (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\internalgamma.cxx",
                     v13);
    std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy((__int64)v39);
    std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)&pathArray);
    WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)&v44);
    return (unsigned int)v37;
  }
  DisplayConfigBufferSizes = QueryDisplayConfig(
                               0x12u,
                               &numPathArrayElements,
                               pathArray,
                               &numModeInfoArrayElements,
                               v39[0],
                               0);
  if ( DisplayConfigBufferSizes )
  {
    v14 = 250;
    goto LABEL_7;
  }
  try
  {
    v18 = 0x8E38E38E38E38E39uLL * ((v42 - (char *)pathArray) >> 3);
    if ( numPathArrayElements >= v18 )
    {
      if ( numPathArrayElements > v18 )
      {
        if ( numPathArrayElements <= 0x8E38E38E38E38E39uLL * ((v43 - (__int64)pathArray) >> 3) )
          v42 = std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(
                  v42,
                  numPathArrayElements - v18);
        else
          std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(
            (const void **)&pathArray,
            numPathArrayElements);
      }
    }
    else
    {
      v42 = (char *)&pathArray[numPathArrayElements];
    }
    v19 = v39[1] - v39[0];
    if ( numModeInfoArrayElements >= v19 )
    {
      if ( numModeInfoArrayElements > v19 )
      {
        if ( numModeInfoArrayElements <= (unsigned __int64)((signed __int64)(v40 - (unsigned __int64)v39[0]) >> 6) )
          v39[1] = (DISPLAYCONFIG_MODE_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(
                                                (char *)v39[1],
                                                numModeInfoArrayElements - v19);
        else
          std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(
            (const void **)v39,
            numModeInfoArrayElements);
      }
    }
    else
    {
      v39[1] = &v39[0][(unsigned __int64)numModeInfoArrayElements];
    }
  }
  catch ( ... )
  {
    LODWORD(v37) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x102,
                     (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\internalgamma.cxx",
                     v17);
    std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy((__int64)v39);
    std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)&pathArray);
    v8 = v37;
    goto LABEL_65;
  }
  LODWORD(v20) = 0;
  v37 = 0;
  for ( i = 0; i < numPathArrayElements; ++i )
  {
    if ( *(_QWORD *)&pathArray[i].sourceInfo.adapterId == *(_QWORD *)((char *)&v51 + 4)
      && pathArray[i].sourceInfo.id == HIDWORD(v51) )
    {
      _mm_lfence();
      v20 = *(_QWORD *)&v39[0][(unsigned __int64)*((unsigned __int16 *)&pathArray[i].sourceInfo.1 + 1)].desktopImageInfo.DesktopImageRegion.top;
      v37 = v20;
      break;
    }
  }
  for ( j = 0; j < numPathArrayElements; ++j )
  {
    v23 = j;
    v24 = pathArray;
    if ( *(_QWORD *)&v39[0][(unsigned __int64)*((unsigned __int16 *)&pathArray[j].sourceInfo.1 + 1)].desktopImageInfo.DesktopImageRegion.top == __PAIR64__(HIDWORD(v37), v20) )
    {
      memset_0(&requestPacket.adapterId, 0, 0x19Cu);
      requestPacket.type = DISPLAYCONFIG_DEVICE_INFO_GET_TARGET_NAME;
      requestPacket.size = 420;
      requestPacket.adapterId = v24[v23].targetInfo.adapterId;
      requestPacket.id = v24[v23].targetInfo.id;
      DisplayConfigBufferSizes = DisplayConfigGetDeviceInfo(&requestPacket);
      if ( DisplayConfigBufferSizes )
      {
        v14 = 285;
        goto LABEL_7;
      }
      pv = 0;
      v46 = 0;
      v25 = WINRT_IMPL_CoTaskMemAlloc(0x600u);
      pv = v25;
      if ( !v25 )
      {
        pExceptionObject[2] = 0;
        pExceptionObject[1] = "bad allocation";
        pExceptionObject[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)pExceptionObject;
      }
      v46 = 256;
      v26 = 256;
      do
      {
        *(_DWORD *)v25 = 0;
        v25[2] = 0;
        v25 += 3;
        --v26;
      }
      while ( v26 );
      v27 = -1;
      do
        ++v27;
      while ( v56[v27] );
      hstring_on_heap = winrt::impl::create_hstring_on_heap((winrt::impl *)v56, (winrt::impl *)v27);
      v54 = hstring_on_heap;
      *(struct _GUID *)v52 = *a2;
      GetColorManager(&v37, &v54, v52);
      winrt::handle_type<winrt::impl::hstring_traits>::close((void **)&hstring_on_heap);
      v28 = v37;
      *(_DWORD *)v52 = 0;
      *(_OWORD *)&v52[8] = 0;
      v29 = *(__int64 (__fastcall **)(__int64, int *, LPVOID *))(*(_QWORD *)v37 + 64LL);
      if ( pv )
      {
        CoTaskMemFree_0(pv);
        pv = 0;
        v46 = 0;
      }
      hstring_on_heap = &pv;
      v49 = 0;
      v30 = v29(v28, &v49, &pv);
      if ( v30 < 0 )
        winrt::throw_hresult((unsigned int)v30, v52);
      hstring_on_heap[2] = v49;
      v31 = 0;
      v32 = 0;
      v33 = (char *)pv;
      do
      {
        *(_WORD *)((char *)a3 + v32) = *(_WORD *)&v33[v32];
        *(_WORD *)((char *)a3 + v32 + 2) = *(_WORD *)&v33[v32 + 2];
        *(_WORD *)((char *)a3 + v32 + 4) = *(_WORD *)&v33[v32 + 4];
        ++v31;
        v32 += 6;
      }
      while ( v31 != 256 );
      if ( v37 )
      {
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
        v33 = (char *)pv;
      }
      if ( v33 )
        CoTaskMemFree_0(v33);
      break;
    }
  }
  if ( v39[0] )
  {
    std::_Deallocate<16>(v39[0], (v40 - (unsigned __int64)v39[0]) & 0xFFFFFFFFFFFFFFC0uLL);
    *(_OWORD *)v39 = 0;
    v40 = 0;
  }
  std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)&pathArray);
  WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)&v44);
  return 0;
}

```

## disassembly

```asm
0x180015fac  push    rbx
0x180015fae  push    rsi
0x180015faf  push    rdi
0x180015fb0  push    r14
0x180015fb2  push    r15
0x180015fb4  sub     rsp, 2E0h
0x180015fbb  mov     rax, cs:__security_cookie
0x180015fc2  xor     rax, rsp
0x180015fc5  mov     [rsp+308h+var_38], rax
0x180015fcd  mov     rsi, r8
0x180015fd0  mov     r14, rdx
0x180015fd3  mov     rbx, rcx
0x180015fd6  mov     ecx, 1
0x180015fdb  call    cs:__imp_RoInitialize
0x180015fe1  mov     [rsp+308h+var_290], eax
0x180015fe5  xorps   xmm0, xmm0
0x180015fe8  movdqu  [rsp+308h+var_258], xmm0
0x180015ff1  mov     [rsp+308h+var_260], rbx
0x180015ff9  lea     rcx, [rsp+308h+var_260]
0x180016001  call    cs:__imp_D3DKMTOpenAdapterFromHdc
0x180016007  xor     r15d, r15d
0x18001600a  test    eax, eax
0x18001600c  jns     short loc_18001602A
0x18001600e  mov     rcx, [rsp+308h]; this
0x180016016  mov     r9d, eax; char *
0x180016019  mov     edx, 0E5h; void *
0x18001601e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180016023  mov     ebx, eax
0x180016025  jmp     loc_1800165DB
0x18001602a  mov     eax, dword ptr [rsp+308h+var_258]
0x180016031  mov     [rsp+308h+var_278], eax
0x180016038  lea     rcx, [rsp+308h+var_278]
0x180016040  call    cs:__imp_D3DKMTCloseAdapter
0x180016046  mov     rcx, [rsp+308h]; this
0x18001604e  test    eax, eax
0x180016050  jns     short loc_18001605A
0x180016052  mov     r9d, eax; char *
0x180016055  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18001605a  mov     [rsp+308h+numPathArrayElements], r15d
0x18001605f  mov     [rsp+308h+numModeInfoArrayElements], r15d
0x180016064  lea     rcx, [rsp+308h+pathArray]
0x180016069  call    ??0?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@QEAA@XZ; std::vector<DISPLAYCONFIG_PATH_INFO>::vector<DISPLAYCONFIG_PATH_INFO>(void)
0x18001606e  nop
0x18001606f  lea     rcx, [rsp+308h+var_2C0]
0x180016074  call    ??0?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@QEAA@XZ; std::vector<DISPLAYCONFIG_PATH_INFO>::vector<DISPLAYCONFIG_PATH_INFO>(void)
0x180016079  nop
0x18001607a  lea     r8, [rsp+308h+numModeInfoArrayElements]; numModeInfoArrayElements
0x18001607f  lea     rdx, [rsp+308h+numPathArrayElements]; numPathArrayElements
0x180016084  mov     edi, 12h
0x180016089  mov     ecx, edi; flags
0x18001608b  call    cs:__imp_GetDisplayConfigBufferSizes
0x180016091  test    eax, eax
0x180016093  jz      short loc_1800160CD
0x180016095  mov     edx, 0F0h; void *
0x18001609a  mov     rcx, [rsp+308h]; this
0x1800160a2  mov     r9d, eax; char *
0x1800160a5  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\color\\mscms"...
0x1800160ac  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800160b1  mov     ebx, eax
0x1800160b3  lea     rcx, [rsp+308h+var_2C0]
0x1800160b8  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x1800160bd  nop
0x1800160be  lea     rcx, [rsp+308h+pathArray]
0x1800160c3  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x1800160c8  jmp     loc_1800165DB
0x1800160cd  mov     edx, [rsp+308h+numPathArrayElements]
0x1800160d1  mov     r8, [rsp+308h+pathArray]
0x1800160d6  mov     rcx, [rsp+308h+var_2A0]
0x1800160db  sub     rcx, r8
0x1800160de  sar     rcx, 3
0x1800160e2  mov     rbx, 8E38E38E38E38E39h
0x1800160ec  imul    rcx, rbx
0x1800160f0  cmp     rdx, rcx
0x1800160f3  jnb     short loc_180016104
0x1800160f5  lea     rax, [rdx+rdx*8]
0x1800160f9  lea     rcx, [r8+rax*8]
0x1800160fd  mov     [rsp+308h+var_2A0], rcx
0x180016102  jmp     short loc_180016139
0x180016104  jbe     short loc_180016139
0x180016106  mov     rax, [rsp+308h+var_298]
0x18001610b  sub     rax, r8
0x18001610e  sar     rax, 3
0x180016112  imul    rax, rbx
0x180016116  cmp     rdx, rax
0x180016119  jbe     short loc_180016127
0x18001611b  lea     rcx, [rsp+308h+pathArray]
0x180016120  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180016125  jmp     short loc_180016139
0x180016127  sub     rdx, rcx
0x18001612a  mov     rcx, [rsp+308h+var_2A0]
0x18001612f  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_PATH_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_PATH_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(DISPLAYCONFIG_PATH_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_PATH_INFO> &)
0x180016134  mov     [rsp+308h+var_2A0], rax
0x180016139  mov     edx, [rsp+308h+numModeInfoArrayElements]
0x18001613d  mov     r8, [rsp+308h+var_2C0]
0x180016142  mov     rcx, [rsp+308h+var_2C0+8]
0x180016147  sub     rcx, r8
0x18001614a  sar     rcx, 6
0x18001614e  cmp     rdx, rcx
0x180016151  jnb     short loc_180016161
0x180016153  shl     rdx, 6
0x180016157  add     rdx, r8
0x18001615a  mov     [rsp+308h+var_2C0+8], rdx
0x18001615f  jmp     short loc_180016192
0x180016161  jbe     short loc_180016192
0x180016163  mov     rax, [rsp+308h+var_2B0]
0x180016168  sub     rax, r8
0x18001616b  sar     rax, 6
0x18001616f  cmp     rdx, rax
0x180016172  jbe     short loc_180016180
0x180016174  lea     rcx, [rsp+308h+var_2C0]
0x180016179  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001617e  jmp     short loc_180016192
0x180016180  sub     rdx, rcx
0x180016183  mov     rcx, [rsp+308h+var_2C0+8]
0x180016188  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_MODE_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_MODE_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(DISPLAYCONFIG_MODE_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_MODE_INFO> &)
0x18001618d  mov     [rsp+308h+var_2C0+8], rax
0x180016192  mov     rax, [rsp+308h+var_2C0]
0x180016197  mov     [rsp+308h+currentTopologyId], r15; currentTopologyId
0x18001619c  mov     [rsp+308h+modeInfoArray], rax; modeInfoArray
0x1800161a1  lea     r9, [rsp+308h+numModeInfoArrayElements]; numModeInfoArrayElements
0x1800161a6  mov     r8, [rsp+308h+pathArray]; pathArray
0x1800161ab  lea     rdx, [rsp+308h+numPathArrayElements]; numPathArrayElements
0x1800161b0  mov     ecx, edi; flags
0x1800161b2  call    cs:__imp_QueryDisplayConfig
0x1800161b8  test    eax, eax
0x1800161ba  jz      short loc_1800161C6
0x1800161bc  mov     edx, 0FAh
0x1800161c1  jmp     loc_18001609A
0x1800161c6  mov     edx, [rsp+308h+numPathArrayElements]
0x1800161ca  mov     r8, [rsp+308h+pathArray]
0x1800161cf  mov     rcx, [rsp+308h+var_2A0]
0x1800161d4  sub     rcx, r8
0x1800161d7  sar     rcx, 3
0x1800161db  imul    rcx, rbx
0x1800161df  cmp     rdx, rcx
0x1800161e2  jnb     short loc_1800161F3
0x1800161e4  lea     rax, [rdx+rdx*8]
0x1800161e8  lea     rcx, [r8+rax*8]
0x1800161ec  mov     [rsp+308h+var_2A0], rcx
0x1800161f1  jmp     short loc_180016228
0x1800161f3  jbe     short loc_180016228
0x1800161f5  mov     rax, [rsp+308h+var_298]
0x1800161fa  sub     rax, r8
0x1800161fd  sar     rax, 3
0x180016201  imul    rax, rbx
0x180016205  cmp     rdx, rax
0x180016208  jbe     short loc_180016216
0x18001620a  lea     rcx, [rsp+308h+pathArray]
0x18001620f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180016214  jmp     short loc_180016228
0x180016216  sub     rdx, rcx
0x180016219  mov     rcx, [rsp+308h+var_2A0]
0x18001621e  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_PATH_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_PATH_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(DISPLAYCONFIG_PATH_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_PATH_INFO> &)
0x180016223  mov     [rsp+308h+var_2A0], rax
0x180016228  mov     edx, [rsp+308h+numModeInfoArrayElements]
0x18001622c  mov     r8, [rsp+308h+var_2C0]
0x180016231  mov     rcx, [rsp+308h+var_2C0+8]
0x180016236  sub     rcx, r8
0x180016239  sar     rcx, 6
0x18001623d  cmp     rdx, rcx
0x180016240  jnb     short loc_180016250
0x180016242  shl     rdx, 6
0x180016246  add     rdx, r8
0x180016249  mov     [rsp+308h+var_2C0+8], rdx
0x18001624e  jmp     short loc_180016281
0x180016250  jbe     short loc_180016281
0x180016252  mov     rax, [rsp+308h+var_2B0]
0x180016257  sub     rax, r8
0x18001625a  sar     rax, 6
0x18001625e  cmp     rdx, rax
0x180016261  jbe     short loc_18001626F
0x180016263  lea     rcx, [rsp+308h+var_2C0]
0x180016268  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001626d  jmp     short loc_180016281
0x18001626f  sub     rdx, rcx
0x180016272  mov     rcx, [rsp+308h+var_2C0+8]
0x180016277  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_MODE_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_MODE_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(DISPLAYCONFIG_MODE_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_MODE_INFO> &)
0x18001627c  mov     [rsp+308h+var_2C0+8], rax
0x180016281  mov     rax, r15
0x180016284  mov     [rsp+308h+var_2D0], rax
0x180016289  mov     edx, r15d
0x18001628c  mov     r9d, dword ptr [rsp+308h+var_258+0Ch]
0x180016294  mov     r11, qword ptr [rsp+308h+var_258+8]
0x18001629c  mov     r10d, dword ptr [rsp+308h+var_258+4]
0x1800162a4  cmp     edx, [rsp+308h+numPathArrayElements]
0x1800162a8  jnb     short loc_1800162EE
0x1800162aa  mov     ecx, edx
0x1800162ac  lea     r8, [rcx+rcx*8]
0x1800162b0  mov     rcx, [rsp+308h+pathArray]
0x1800162b5  cmp     [rcx+r8*8+4], r11d
0x1800162ba  jnz     short loc_1800162C9
0x1800162bc  cmp     [rcx+r8*8], r10d
0x1800162c0  jnz     short loc_1800162C9
0x1800162c2  cmp     [rcx+r8*8+8], r9d
0x1800162c7  jz      short loc_1800162CD
0x1800162c9  inc     edx
0x1800162cb  jmp     short loc_1800162A4
0x1800162cd  lfence
0x1800162d0  mov     rax, [rsp+308h+pathArray]
0x1800162d5  movzx   ecx, word ptr [rax+r8*8+0Eh]
0x1800162db  shl     rcx, 6
0x1800162df  mov     rax, [rsp+308h+var_2C0]
0x1800162e4  mov     rax, [rcx+rax+1Ch]
0x1800162e9  mov     [rsp+308h+var_2D0], rax
0x1800162ee  mov     edx, r15d
0x1800162f1  mov     r9d, dword ptr [rsp+308h+var_2D0+4]
0x1800162f6  cmp     edx, [rsp+308h+numPathArrayElements]
0x1800162fa  jnb     loc_180016577
0x180016300  mov     ecx, edx
0x180016302  lea     rbx, [rcx+rcx*8]
0x180016306  mov     rdi, [rsp+308h+pathArray]
0x18001630b  movzx   ecx, word ptr [rdi+rbx*8+0Eh]
0x180016310  shl     rcx, 6
0x180016314  mov     r8, [rsp+308h+var_2C0]
0x180016319  cmp     [rcx+r8+1Ch], eax
0x18001631e  jnz     loc_1800165BB
0x180016324  cmp     [rcx+r8+20h], r9d
0x180016329  jnz     loc_1800165BB
0x18001632f  xor     edx, edx; Val
0x180016331  mov     r8d, 19Ch; Size
0x180016337  lea     rcx, [rsp+308h+requestPacket.adapterId]; void *
0x18001633f  call    memset_0
0x180016344  mov     [rsp+308h+requestPacket.type], 2
0x18001634f  mov     [rsp+308h+requestPacket.size], 1A4h
0x18001635a  mov     rax, [rdi+rbx*8+14h]
0x18001635f  mov     qword ptr [rsp+308h+requestPacket.adapterId.LowPart], rax
0x180016367  mov     eax, [rdi+rbx*8+1Ch]
0x18001636b  mov     [rsp+308h+requestPacket.id], eax
0x180016372  lea     rcx, [rsp+308h+requestPacket]; requestPacket
0x18001637a  call    cs:__imp_DisplayConfigGetDeviceInfo
0x180016380  test    eax, eax
0x180016382  jz      short loc_18001638E
0x180016384  mov     edx, 11Dh
0x180016389  jmp     loc_18001609A
0x18001638e  mov     [rsp+308h+pv], r15
0x180016396  mov     [rsp+308h+var_280], r15d
0x18001639e  mov     ecx, 600h; cb
0x1800163a3  call    WINRT_IMPL_CoTaskMemAlloc
0x1800163a8  mov     rcx, rax
0x1800163ab  mov     [rsp+308h+pv], rax
0x1800163b3  test    rax, rax
0x1800163b6  jnz     short loc_1800163F5
0x1800163b8  xorps   xmm0, xmm0
0x1800163bb  movups  [rsp+308h+var_220], xmm0
0x1800163c3  lea     rax, aBadAllocation; "bad allocation"
0x1800163ca  mov     qword ptr [rsp+308h+var_220], rax
0x1800163d2  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800163d9  mov     [rsp+308h+pExceptionObject], rax
0x1800163e1  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800163e8  lea     rcx, [rsp+308h+pExceptionObject]; pExceptionObject
0x1800163f0  call    _CxxThrowException_0
0x1800163f5  mov     [rsp+308h+var_280], 100h
0x180016400  mov     edx, 100h
0x180016405  mov     [rcx], r15d
0x180016408  mov     [rcx+4], r15w
0x18001640d  lea     rcx, [rcx+6]
0x180016411  add     edx, 0FFFFFFFFh
0x180016414  jnz     short loc_180016405
0x180016416  lea     rax, [rsp+308h+var_144]
0x18001641e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180016422  inc     rdx; winrt::impl *
0x180016425  cmp     [rax+rdx*2], r15w
0x18001642a  jnz     short loc_180016422
0x18001642c  lea     rcx, [rsp+308h+var_144]; this
0x180016434  call    ?create_hstring_on_heap@impl@winrt@@YAPEAUhstring_header@12@PEBGI@Z; winrt::impl::create_hstring_on_heap(ushort const *,uint)
0x180016439  mov     [rsp+308h+var_270], rax
0x180016441  mov     [rsp+308h+var_210], rax
0x180016449  movaps  xmm0, xmmword ptr [r14]
0x18001644d  movdqa  [rsp+308h+var_248], xmm0
0x180016456  lea     r8, [rsp+308h+var_248]
0x18001645e  lea     rdx, [rsp+308h+var_210]
0x180016466  lea     rcx, [rsp+308h+var_2D0]
0x18001646b  call    ?GetColorManager@@YA?AUDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@Uhstring@param@6@U_GUID@@@Z; GetColorManager(winrt::param::hstring,_GUID)
0x180016470  nop
0x180016471  lea     rcx, [rsp+308h+var_270]
0x180016479  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001647e  mov     rbx, [rsp+308h+var_2D0]
0x180016483  mov     dword ptr [rsp+308h+var_248], r15d
0x18001648b  xorps   xmm0, xmm0
0x18001648e  movdqu  [rsp+308h+var_248+8], xmm0
0x180016497  mov     rax, [rbx]
0x18001649a  mov     rdi, [rax+40h]
0x18001649e  mov     rcx, [rsp+308h+pv]; pv
0x1800164a6  test    rcx, rcx
0x1800164a9  jz      short loc_1800164C0
0x1800164ab  call    CoTaskMemFree_0
0x1800164b0  mov     [rsp+308h+pv], r15
0x1800164b8  mov     [rsp+308h+var_280], r15d
0x1800164c0  lea     rax, [rsp+308h+pv]
0x1800164c8  mov     [rsp+308h+var_270], rax
0x1800164d0  mov     [rsp+308h+var_268], r15d
0x1800164d8  lea     r8, [rsp+308h+pv]
0x1800164e0  lea     rdx, [rsp+308h+var_268]
0x1800164e8  mov     rcx, rbx
0x1800164eb  mov     rax, rdi
0x1800164ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164f3  test    eax, eax
0x1800164f5  jns     short loc_180016507
0x1800164f7  lea     rdx, [rsp+308h+var_248]
0x1800164ff  mov     ecx, eax
  ... truncated ...
```
