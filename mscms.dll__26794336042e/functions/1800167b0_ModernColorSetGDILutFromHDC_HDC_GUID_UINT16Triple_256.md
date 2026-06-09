# ModernColorSetGDILutFromHDC(HDC__ *,_GUID,UINT16Triple (&)[256])

- ea: `0x1800167b0`
- end: `0x180016c2d`
- name: `?ModernColorSetGDILutFromHDC@@YAJPEAUHDC__@@U_GUID@@AEAY0BAA@UUINT16Triple@@@Z`
- size: `1149`
- prototype: `int(HDC, struct _GUID *__struct_ptr, struct UINT16Triple (*)[256])`
- caller_count: `3`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x180025100`
- `0x18002a9d0`
- `0x18004c6c0`

## callees

- `0x1800167b0`
- `0x18001717c`
- `0x1800171c8`
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
- `0x1800269d4`
- `0x180027408`
- `0x18002aea8`
- `0x18002e5f0`
- `0x18002f2f4`

## import_xrefs

- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTOpenAdapterFromHdc` at `0x180016803`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTOpenAdapterFromHdc` at `0x180016803`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800167e3`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800167e3`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x180016956`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x180016956`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180016a5c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180016a5c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x18001685d`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x18001685d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ModernColorSetGDILutFromHDC(HDC a1, struct _GUID *a2, struct UINT16Triple (*a3)[256])
{
  int v6; // eax
  unsigned int v7; // r8d
  unsigned int v8; // ebx
  unsigned int DisplayConfigBufferSizes; // eax
  __int64 v10; // rdx
  const char *v11; // r9
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  struct winrt::impl::hstring_header *v14; // rbx
  UINT32 v15; // r8d
  UINT32 v16; // edx
  DISPLAYCONFIG_MODE_INFO *i; // rcx
  UINT32 v18; // esi
  int v19; // r15d
  DISPLAYCONFIG_PATH_INFO *v20; // r14
  unsigned __int64 v21; // rax
  __int64 v23; // rdx
  int v24; // eax
  const char *v25; // r9
  unsigned int v26; // edi
  unsigned int modeInfoArray; // [rsp+20h] [rbp-278h]
  UINT32 numPathArrayElements; // [rsp+30h] [rbp-268h] BYREF
  int v29; // [rsp+34h] [rbp-264h] BYREF
  DISPLAYCONFIG_MODE_INFO *v30[2]; // [rsp+38h] [rbp-260h] BYREF
  __int64 v31; // [rsp+48h] [rbp-250h]
  struct winrt::impl::hstring_header *hstring_on_heap; // [rsp+50h] [rbp-248h] BYREF
  UINT32 numModeInfoArrayElements; // [rsp+58h] [rbp-240h] BYREF
  DISPLAYCONFIG_PATH_INFO *pathArray; // [rsp+60h] [rbp-238h] BYREF
  char *v35; // [rsp+68h] [rbp-230h]
  __int64 v36; // [rsp+70h] [rbp-228h]
  HDC v37; // [rsp+78h] [rbp-220h] BYREF
  __int128 v38; // [rsp+80h] [rbp-218h]
  struct _GUID v39; // [rsp+90h] [rbp-208h] BYREF
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+A0h] [rbp-1F8h] BYREF
  _WORD v41[134]; // [rsp+144h] [rbp-154h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v29 = RoInitialize(1);
  v38 = 0;
  v37 = a1;
  v6 = D3DKMTOpenAdapterFromHdc(&v37);
  if ( v6 < 0 )
  {
    v8 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0xA7,
           v7,
           (const char *)(unsigned int)v6,
           modeInfoArray);
LABEL_33:
    WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)&v29);
    return v8;
  }
  numPathArrayElements = 0;
  numModeInfoArrayElements = 0;
  std::vector<DISPLAYCONFIG_PATH_INFO>::vector<DISPLAYCONFIG_PATH_INFO>(&pathArray);
  std::vector<DISPLAYCONFIG_PATH_INFO>::vector<DISPLAYCONFIG_PATH_INFO>(v30);
  DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(0x12u, &numPathArrayElements, &numModeInfoArrayElements);
  if ( DisplayConfigBufferSizes )
  {
    v10 = 174;
LABEL_30:
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v10,
           (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\internalgamma.cxx",
           (const char *)DisplayConfigBufferSizes,
           modeInfoArray);
    if ( v30[0] )
    {
      std::_Deallocate<16>(v30[0], (v31 - (unsigned __int64)v30[0]) & 0xFFFFFFFFFFFFFFC0uLL);
      *(_OWORD *)v30 = 0;
      v31 = 0;
    }
    std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)&pathArray);
    goto LABEL_33;
  }
  try
  {
    v11 = (const char *)0x8E38E38E38E38E39LL;
    v12 = 0x8E38E38E38E38E39uLL * ((v35 - (char *)pathArray) >> 3);
    if ( numPathArrayElements >= v12 )
    {
      if ( numPathArrayElements > v12 )
      {
        if ( numPathArrayElements <= 0x8E38E38E38E38E39uLL * ((v36 - (__int64)pathArray) >> 3) )
          v35 = std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(
                  v35,
                  numPathArrayElements - v12);
        else
          std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(
            (const void **)&pathArray,
            numPathArrayElements);
      }
    }
    else
    {
      v35 = (char *)&pathArray[numPathArrayElements];
    }
    v13 = v30[1] - v30[0];
    if ( numModeInfoArrayElements >= v13 )
    {
      if ( numModeInfoArrayElements > v13 )
      {
        if ( numModeInfoArrayElements <= (unsigned __int64)((signed __int64)(v31 - (unsigned __int64)v30[0]) >> 6) )
          v30[1] = (DISPLAYCONFIG_MODE_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(
                                                (char *)v30[1],
                                                numModeInfoArrayElements - v13);
        else
          std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(
            (const void **)v30,
            numModeInfoArrayElements);
      }
    }
    else
    {
      v30[1] = &v30[0][(unsigned __int64)numModeInfoArrayElements];
    }
  }
  catch ( ... )
  {
    LODWORD(hstring_on_heap) = wil::details::in1diag3::Return_CaughtException(
                                 retaddr,
                                 (void *)0xB5,
                                 (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\internalgamma.cxx",
                                 v11);
    goto LABEL_46;
  }
  DisplayConfigBufferSizes = QueryDisplayConfig(
                               0x12u,
                               &numPathArrayElements,
                               pathArray,
                               &numModeInfoArrayElements,
                               v30[0],
                               0);
  if ( DisplayConfigBufferSizes )
  {
    v10 = 183;
    goto LABEL_30;
  }
  LODWORD(v14) = 0;
  hstring_on_heap = 0;
  v15 = 0;
  v16 = numPathArrayElements;
  for ( i = v30[0]; v15 < numPathArrayElements; ++v15 )
  {
    if ( *(_QWORD *)&pathArray[v15].sourceInfo.adapterId == *(_QWORD *)((char *)&v38 + 4)
      && pathArray[v15].sourceInfo.id == HIDWORD(v38) )
    {
      v14 = *(struct winrt::impl::hstring_header **)&v30[0][(unsigned __int64)*((unsigned __int16 *)&pathArray[v15].sourceInfo.1
                                                                              + 1)].desktopImageInfo.DesktopImageRegion.top;
      hstring_on_heap = v14;
    }
  }
  v18 = 0;
  v19 = HIDWORD(hstring_on_heap);
  while ( v18 < v16 )
  {
    v20 = pathArray;
    v21 = (unsigned __int64)*((unsigned __int16 *)&pathArray[v18].sourceInfo.1 + 1) << 6;
    if ( *(UINT32 *)((char *)&i->targetMode.targetVideoSignalInfo.hSyncFreq.Denominator + v21) == (_DWORD)v14
      && *(UINT32 *)((char *)&i->targetMode.targetVideoSignalInfo.vSyncFreq.Numerator + v21) == v19 )
    {
      memset_0(&requestPacket.adapterId, 0, 0x19Cu);
      requestPacket.type = DISPLAYCONFIG_DEVICE_INFO_GET_TARGET_NAME;
      requestPacket.size = 420;
      requestPacket.adapterId = v20[v18].targetInfo.adapterId;
      requestPacket.id = v20[v18].targetInfo.id;
      DisplayConfigBufferSizes = DisplayConfigGetDeviceInfo(&requestPacket);
      if ( DisplayConfigBufferSizes )
      {
        v10 = 209;
        goto LABEL_30;
      }
      v23 = -1;
      do
        ++v23;
      while ( v41[v23] );
      try
      {
        hstring_on_heap = winrt::impl::create_hstring_on_heap((winrt::impl *)v41, (winrt::impl *)v23);
        v39 = *a2;
        v24 = ModernColorSetGDILut((HSTRING)hstring_on_heap, &v39, a3);
      }
      catch ( ... )
      {
        LODWORD(hstring_on_heap) = wil::details::in1diag3::Return_CaughtException(
                                     retaddr,
                                     (void *)0xD8,
                                     (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\internalgamma.cxx",
                                     v25);
LABEL_46:
        std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy((__int64)v30);
        std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)&pathArray);
        WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)&v29);
        return (unsigned int)hstring_on_heap;
      }
      v26 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD6,
          (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\internalgamma.cxx",
          (const char *)(unsigned int)v24,
          modeInfoArray);
        winrt::handle_type<winrt::impl::hstring_traits>::close((void **)&hstring_on_heap);
        if ( v30[0] )
        {
          std::_Deallocate<16>(v30[0], (v31 - (unsigned __int64)v30[0]) & 0xFFFFFFFFFFFFFFC0uLL);
          *(_OWORD *)v30 = 0;
          v31 = 0;
        }
        std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)&pathArray);
        WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)&v29);
        return v26;
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close((void **)&hstring_on_heap);
      v16 = numPathArrayElements;
      i = v30[0];
    }
    ++v18;
  }
  if ( i )
  {
    std::_Deallocate<16>(i, (v31 - (_QWORD)i) & 0xFFFFFFFFFFFFFFC0uLL);
    *(_OWORD *)v30 = 0;
    v31 = 0;
  }
  std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)&pathArray);
  WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)&v29);
  return 0;
}

```

## disassembly

```asm
0x1800167b0  push    rbx
0x1800167b2  push    rsi
0x1800167b3  push    rdi
0x1800167b4  push    r12
0x1800167b6  push    r13
0x1800167b8  push    r14
0x1800167ba  push    r15
0x1800167bc  sub     rsp, 260h
0x1800167c3  mov     rax, cs:__security_cookie
0x1800167ca  xor     rax, rsp
0x1800167cd  mov     [rsp+298h+var_48], rax
0x1800167d5  mov     r13, r8
0x1800167d8  mov     r12, rdx
0x1800167db  mov     rbx, rcx
0x1800167de  mov     ecx, 1
0x1800167e3  call    cs:__imp_RoInitialize
0x1800167e9  mov     [rsp+298h+var_264], eax
0x1800167ed  xorps   xmm0, xmm0
0x1800167f0  movdqu  [rsp+298h+var_218], xmm0
0x1800167f9  mov     [rsp+298h+var_220], rbx
0x1800167fe  lea     rcx, [rsp+298h+var_220]
0x180016803  call    cs:__imp_D3DKMTOpenAdapterFromHdc
0x180016809  xor     r14d, r14d
0x18001680c  test    eax, eax
0x18001680e  jns     short loc_18001682C
0x180016810  mov     rcx, [rsp+298h]; this
0x180016818  mov     r9d, eax; char *
0x18001681b  mov     edx, 0A7h; void *
0x180016820  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180016825  mov     ebx, eax
0x180016827  jmp     loc_180016ABB
0x18001682c  mov     [rsp+298h+numPathArrayElements], r14d
0x180016831  mov     [rsp+298h+numModeInfoArrayElements], r14d
0x180016836  lea     rcx, [rsp+298h+pathArray]
0x18001683b  call    ??0?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@QEAA@XZ; std::vector<DISPLAYCONFIG_PATH_INFO>::vector<DISPLAYCONFIG_PATH_INFO>(void)
0x180016840  nop
0x180016841  lea     rcx, [rsp+298h+var_260]
0x180016846  call    ??0?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@QEAA@XZ; std::vector<DISPLAYCONFIG_PATH_INFO>::vector<DISPLAYCONFIG_PATH_INFO>(void)
0x18001684b  nop
0x18001684c  lea     r8, [rsp+298h+numModeInfoArrayElements]; numModeInfoArrayElements
0x180016851  lea     rdx, [rsp+298h+numPathArrayElements]; numPathArrayElements
0x180016856  mov     ebx, 12h
0x18001685b  mov     ecx, ebx; flags
0x18001685d  call    cs:__imp_GetDisplayConfigBufferSizes
0x180016863  test    eax, eax
0x180016865  jz      short loc_180016871
0x180016867  mov     edx, 0AEh
0x18001686c  jmp     loc_180016A6E
0x180016871  mov     edx, [rsp+298h+numPathArrayElements]
0x180016875  mov     r8, [rsp+298h+pathArray]
0x18001687a  mov     rcx, [rsp+298h+var_230]
0x18001687f  sub     rcx, r8
0x180016882  sar     rcx, 3
0x180016886  mov     r9, 8E38E38E38E38E39h
0x180016890  imul    rcx, r9
0x180016894  cmp     rdx, rcx
0x180016897  jnb     short loc_1800168A8
0x180016899  lea     rax, [rdx+rdx*8]
0x18001689d  lea     rcx, [r8+rax*8]
0x1800168a1  mov     [rsp+298h+var_230], rcx
0x1800168a6  jmp     short loc_1800168DD
0x1800168a8  jbe     short loc_1800168DD
0x1800168aa  mov     rax, [rsp+298h+var_228]
0x1800168af  sub     rax, r8
0x1800168b2  sar     rax, 3
0x1800168b6  imul    rax, r9
0x1800168ba  cmp     rdx, rax
0x1800168bd  jbe     short loc_1800168CB
0x1800168bf  lea     rcx, [rsp+298h+pathArray]
0x1800168c4  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800168c9  jmp     short loc_1800168DD
0x1800168cb  sub     rdx, rcx
0x1800168ce  mov     rcx, [rsp+298h+var_230]
0x1800168d3  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_PATH_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_PATH_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(DISPLAYCONFIG_PATH_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_PATH_INFO> &)
0x1800168d8  mov     [rsp+298h+var_230], rax
0x1800168dd  mov     edx, [rsp+298h+numModeInfoArrayElements]
0x1800168e1  mov     r8, [rsp+298h+var_260]
0x1800168e6  mov     rcx, [rsp+298h+var_260+8]
0x1800168eb  sub     rcx, r8
0x1800168ee  sar     rcx, 6
0x1800168f2  cmp     rdx, rcx
0x1800168f5  jnb     short loc_180016905
0x1800168f7  shl     rdx, 6
0x1800168fb  add     rdx, r8
0x1800168fe  mov     [rsp+298h+var_260+8], rdx
0x180016903  jmp     short loc_180016936
0x180016905  jbe     short loc_180016936
0x180016907  mov     rax, [rsp+298h+var_250]
0x18001690c  sub     rax, r8
0x18001690f  sar     rax, 6
0x180016913  cmp     rdx, rax
0x180016916  jbe     short loc_180016924
0x180016918  lea     rcx, [rsp+298h+var_260]
0x18001691d  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180016922  jmp     short loc_180016936
0x180016924  sub     rdx, rcx
0x180016927  mov     rcx, [rsp+298h+var_260+8]
0x18001692c  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_MODE_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_MODE_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(DISPLAYCONFIG_MODE_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_MODE_INFO> &)
0x180016931  mov     [rsp+298h+var_260+8], rax
0x180016936  mov     rax, [rsp+298h+var_260]
0x18001693b  mov     [rsp+298h+currentTopologyId], r14; currentTopologyId
0x180016940  mov     [rsp+298h+modeInfoArray], rax; int
0x180016945  lea     r9, [rsp+298h+numModeInfoArrayElements]; numModeInfoArrayElements
0x18001694a  mov     r8, [rsp+298h+pathArray]; pathArray
0x18001694f  lea     rdx, [rsp+298h+numPathArrayElements]; numPathArrayElements
0x180016954  mov     ecx, ebx; flags
0x180016956  call    cs:__imp_QueryDisplayConfig
0x18001695c  test    eax, eax
0x18001695e  jz      short loc_18001696A
0x180016960  mov     edx, 0B7h
0x180016965  jmp     loc_180016A6E
0x18001696a  mov     rbx, r14
0x18001696d  mov     [rsp+298h+var_248], rbx
0x180016972  mov     r8d, r14d
0x180016975  mov     edx, [rsp+298h+numPathArrayElements]
0x180016979  mov     rcx, [rsp+298h+var_260]
0x18001697e  test    edx, edx
0x180016980  jz      short loc_1800169D6
0x180016982  mov     r10d, dword ptr [rsp+298h+var_218+0Ch]
0x18001698a  mov     rdi, qword ptr [rsp+298h+var_218+8]
0x180016992  mov     r11d, dword ptr [rsp+298h+var_218+4]
0x18001699a  mov     eax, r8d
0x18001699d  lea     r9, [rax+rax*8]
0x1800169a1  mov     rax, [rsp+298h+pathArray]
0x1800169a6  cmp     [rax+r9*8+4], edi
0x1800169ab  jnz     short loc_1800169CE
0x1800169ad  cmp     [rax+r9*8], r11d
0x1800169b1  jnz     short loc_1800169CE
0x1800169b3  cmp     [rax+r9*8+8], r10d
0x1800169b8  jnz     short loc_1800169CE
0x1800169ba  movzx   ebx, word ptr [rax+r9*8+0Eh]
0x1800169c0  shl     rbx, 6
0x1800169c4  mov     rbx, [rbx+rcx+1Ch]
0x1800169c9  mov     [rsp+298h+var_248], rbx
0x1800169ce  inc     r8d
0x1800169d1  cmp     r8d, edx
0x1800169d4  jb      short loc_18001699A
0x1800169d6  mov     esi, r14d
0x1800169d9  mov     r15d, dword ptr [rsp+298h+var_248+4]
0x1800169de  cmp     esi, edx
0x1800169e0  jnb     loc_180016BA9
0x1800169e6  mov     eax, esi
0x1800169e8  lea     rdi, [rax+rax*8]
0x1800169ec  mov     r14, [rsp+298h+pathArray]
0x1800169f1  movzx   eax, word ptr [r14+rdi*8+0Eh]
0x1800169f7  shl     rax, 6
0x1800169fb  cmp     [rax+rcx+1Ch], ebx
0x1800169ff  jnz     loc_180016B9F
0x180016a05  cmp     [rax+rcx+20h], r15d
0x180016a0a  jnz     loc_180016B9F
0x180016a10  xor     edx, edx; Val
0x180016a12  mov     r8d, 19Ch; Size
0x180016a18  lea     rcx, [rsp+298h+requestPacket.adapterId]; void *
0x180016a20  call    memset_0
0x180016a25  mov     [rsp+298h+requestPacket.type], 2
0x180016a30  mov     [rsp+298h+requestPacket.size], 1A4h
0x180016a3b  mov     rax, [r14+rdi*8+14h]
0x180016a40  mov     qword ptr [rsp+298h+requestPacket.adapterId.LowPart], rax
0x180016a48  mov     eax, [r14+rdi*8+1Ch]
0x180016a4d  mov     [rsp+298h+requestPacket.id], eax
0x180016a54  lea     rcx, [rsp+298h+requestPacket]; requestPacket
0x180016a5c  call    cs:__imp_DisplayConfigGetDeviceInfo
0x180016a62  xor     r14d, r14d
0x180016a65  test    eax, eax
0x180016a67  jz      short loc_180016ACC
0x180016a69  mov     edx, 0D1h; void *
0x180016a6e  mov     r9d, eax; char *
0x180016a71  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\color\\mscms"...
0x180016a78  mov     rcx, [rsp+298h]; this
0x180016a80  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180016a85  mov     ebx, eax
0x180016a87  mov     rcx, [rsp+298h+var_260]
0x180016a8c  test    rcx, rcx
0x180016a8f  jz      short loc_180016AB0
0x180016a91  mov     rdx, [rsp+298h+var_250]
0x180016a96  sub     rdx, rcx
0x180016a99  and     rdx, 0FFFFFFFFFFFFFFC0h
0x180016a9d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180016aa2  xorps   xmm0, xmm0
0x180016aa5  movdqu  xmmword ptr [rsp+298h+var_260], xmm0
0x180016aab  mov     [rsp+298h+var_250], r14
0x180016ab0  lea     rcx, [rsp+298h+pathArray]
0x180016ab5  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x180016aba  nop
0x180016abb  lea     rcx, [rsp+298h+var_264]; this
0x180016ac0  call    ??1WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::~WinRTActivationWrapper(void)
0x180016ac5  mov     eax, ebx
0x180016ac7  jmp     loc_180016C0A
0x180016acc  lea     rax, [rsp+298h+var_154]
0x180016ad4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180016ad8  inc     rdx; winrt::impl *
0x180016adb  cmp     [rax+rdx*2], r14w
0x180016ae0  jnz     short loc_180016AD8
0x180016ae2  lea     rcx, [rsp+298h+var_154]; this
0x180016aea  call    ?create_hstring_on_heap@impl@winrt@@YAPEAUhstring_header@12@PEBGI@Z; winrt::impl::create_hstring_on_heap(ushort const *,uint)
0x180016aef  mov     [rsp+298h+var_248], rax
0x180016af4  movaps  xmm0, xmmword ptr [r12]
0x180016af9  movdqa  xmmword ptr [rsp+298h+var_208.Data1], xmm0
0x180016b02  mov     r8, r13; struct UINT16Triple (*)[256]
0x180016b05  lea     rdx, [rsp+298h+var_208]; struct _GUID
0x180016b0d  mov     rcx, rax; HSTRING
0x180016b10  call    ?ModernColorSetGDILut@@YAJPEAUHSTRING__@@U_GUID@@AEAY0BAA@UUINT16Triple@@@Z; ModernColorSetGDILut(HSTRING__ *,_GUID,UINT16Triple (&)[256])
0x180016b15  mov     edi, eax
0x180016b17  test    eax, eax
0x180016b19  jns     short loc_180016B88
0x180016b1b  mov     rcx, [rsp+298h]; this
0x180016b23  mov     r9d, eax; char *
0x180016b26  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\color\\mscms"...
0x180016b2d  mov     edx, 0D6h; void *
0x180016b32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b37  nop
0x180016b38  lea     rcx, [rsp+298h+var_248]
0x180016b3d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180016b42  nop
0x180016b43  mov     rcx, [rsp+298h+var_260]
0x180016b48  test    rcx, rcx
0x180016b4b  jz      short loc_180016B6C
0x180016b4d  mov     rdx, [rsp+298h+var_250]
0x180016b52  sub     rdx, rcx
0x180016b55  and     rdx, 0FFFFFFFFFFFFFFC0h
0x180016b59  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180016b5e  xorps   xmm0, xmm0
0x180016b61  movdqu  xmmword ptr [rsp+298h+var_260], xmm0
0x180016b67  mov     [rsp+298h+var_250], r14
0x180016b6c  lea     rcx, [rsp+298h+pathArray]
0x180016b71  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x180016b76  nop
0x180016b77  lea     rcx, [rsp+298h+var_264]; this
0x180016b7c  call    ??1WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::~WinRTActivationWrapper(void)
0x180016b81  mov     eax, edi
0x180016b83  jmp     loc_180016C0A
0x180016b88  lea     rcx, [rsp+298h+var_248]
0x180016b8d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180016b92  mov     edx, [rsp+298h+numPathArrayElements]
0x180016b96  mov     rcx, [rsp+298h+var_260]
0x180016b9b  jmp     short loc_180016BA2
0x180016b9d  jmp     short loc_180016BE6
0x180016b9f  xor     r14d, r14d
0x180016ba2  inc     esi
0x180016ba4  jmp     loc_1800169DE
0x180016ba9  test    rcx, rcx
0x180016bac  jz      short loc_180016BCD
0x180016bae  mov     rdx, [rsp+298h+var_250]
0x180016bb3  sub     rdx, rcx
0x180016bb6  and     rdx, 0FFFFFFFFFFFFFFC0h
0x180016bba  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180016bbf  xorps   xmm0, xmm0
0x180016bc2  movdqu  xmmword ptr [rsp+298h+var_260], xmm0
0x180016bc8  mov     [rsp+298h+var_250], r14
0x180016bcd  lea     rcx, [rsp+298h+pathArray]
0x180016bd2  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x180016bd7  nop
0x180016bd8  lea     rcx, [rsp+298h+var_264]; this
0x180016bdd  call    ??1WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::~WinRTActivationWrapper(void)
0x180016be2  xor     eax, eax
0x180016be4  jmp     short loc_180016C0A
0x180016be6  lea     rcx, [rsp+298h+var_260]
0x180016beb  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x180016bf0  nop
0x180016bf1  lea     rcx, [rsp+298h+pathArray]
0x180016bf6  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x180016bfb  nop
0x180016bfc  lea     rcx, [rsp+298h+var_264]; this
0x180016c01  call    ??1WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::~WinRTActivationWrapper(void)
0x180016c06  mov     eax, dword ptr [rsp+298h+var_248]
0x180016c0a  mov     rcx, [rsp+298h+var_48]
0x180016c12  xor     rcx, rsp; StackCookie
0x180016c15  call    __security_check_cookie
0x180016c1a  add     rsp, 260h
0x180016c21  pop     r15
0x180016c23  pop     r14
0x180016c25  pop     r13
0x180016c27  pop     r12
0x180016c29  pop     rdi
0x180016c2a  pop     rsi
0x180016c2b  pop     rbx
0x180016c2c  retn
```
