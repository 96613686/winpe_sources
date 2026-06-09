# ColorProfileGetDeviceCapabilities

- ea: `0x18004cf60`
- end: `0x18004d387`
- name: `ColorProfileGetDeviceCapabilities`
- size: `1063`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config`

## callees

- `0x180016794`
- `0x180016c68`
- `0x18001717c`
- `0x1800173dc`
- `0x180017474`
- `0x180017624`
- `0x180020a24`
- `0x180020f58`
- `0x180022a80`
- `0x1800269d4`
- `0x180027408`
- `0x18002af70`
- `0x18002e5f0`
- `0x18002f2f4`
- `0x18004c830`
- `0x18004c8b4`
- `0x18004cf60`
- `0x180084010`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x18004d084`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x18004d084`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18004d174`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18004d174`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x18004cfd7`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x18004cfd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall ColorProfileGetDeviceCapabilities(__int64 a1, unsigned __int64 a2, int a3, int a4, _DWORD *a5)
{
  DWORD v7; // ebx
  unsigned __int64 v8; // r15
  unsigned int DisplayConfigBufferSizes; // eax
  unsigned int v10; // ebx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  UINT32 v14; // r12d
  int v15; // edx
  UINT32 v16; // ecx
  DISPLAYCONFIG_PATH_INFO *v17; // r14
  unsigned int DeviceInfo; // eax
  unsigned int v19; // ebx
  __int64 ColorManagerForDisplayAsync; // rax
  unsigned int v21; // eax
  int v22; // edi
  unsigned int modeInfoArray; // [rsp+20h] [rbp-2B8h]
  unsigned int modeInfoArraya; // [rsp+20h] [rbp-2B8h]
  _BYTE v25[4]; // [rsp+30h] [rbp-2A8h] BYREF
  UINT32 numModeInfoArrayElements; // [rsp+34h] [rbp-2A4h] BYREF
  UINT32 numPathArrayElements; // [rsp+38h] [rbp-2A0h] BYREF
  __int64 v28; // [rsp+40h] [rbp-298h] BYREF
  __int64 v29; // [rsp+48h] [rbp-290h]
  __int64 v30; // [rsp+50h] [rbp-288h] BYREF
  DISPLAYCONFIG_PATH_INFO *pathArray[2]; // [rsp+58h] [rbp-280h] BYREF
  __int64 v32; // [rsp+68h] [rbp-270h]
  DISPLAYCONFIG_MODE_INFO *v33[2]; // [rsp+70h] [rbp-268h] BYREF
  __int64 v34; // [rsp+80h] [rbp-258h]
  _BYTE v35[8]; // [rsp+88h] [rbp-250h] BYREF
  __int64 v36; // [rsp+90h] [rbp-248h] BYREF
  void *v37; // [rsp+98h] [rbp-240h] BYREF
  int v38; // [rsp+A0h] [rbp-238h] BYREF
  __int128 v39; // [rsp+A8h] [rbp-230h]
  _QWORD v40[4]; // [rsp+B8h] [rbp-220h] BYREF
  __int128 v41; // [rsp+D8h] [rbp-200h]
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+F0h] [rbp-1E8h] BYREF
  unsigned __int16 v43[134]; // [rsp+194h] [rbp-144h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v7 = a2;
  v8 = HIDWORD(a2);
  WinRTActivationWrapper::WinRTActivationWrapper((WinRTActivationWrapper *)v25);
  v28 = 0;
  v29 = 0;
  numPathArrayElements = 0;
  numModeInfoArrayElements = 0;
  DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(2u, &numPathArrayElements, &numModeInfoArrayElements);
  if ( DisplayConfigBufferSizes )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x2B7,
            (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\modernprofman.cxx",
            (const char *)DisplayConfigBufferSizes,
            modeInfoArray);
    WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)v25);
    return v10;
  }
  else if ( numPathArrayElements && numModeInfoArrayElements )
  {
    *(_OWORD *)v33 = 0;
    v34 = 0;
    std::vector<DISPLAYCONFIG_MODE_INFO>::_Construct_n<>(v33, numModeInfoArrayElements);
    *(_OWORD *)pathArray = 0;
    v32 = 0;
    std::vector<DISPLAYCONFIG_PATH_INFO>::_Construct_n<>(pathArray, numPathArrayElements);
    v12 = QueryDisplayConfig(2u, &numPathArrayElements, pathArray[0], &numModeInfoArrayElements, v33[0], 0);
    if ( v12 )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x2C9,
              (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\modernprofman.cxx",
              (const char *)v12,
              modeInfoArraya);
      std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)pathArray);
      std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy((__int64)v33);
      WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)v25);
      return v13;
    }
    else
    {
      v14 = 0;
      v15 = 0;
      v16 = 0;
      if ( !numPathArrayElements )
        goto LABEL_22;
      v17 = pathArray[0];
      do
      {
        if ( pathArray[0][v16].targetInfo.adapterId.LowPart == v7
          && pathArray[0][v16].targetInfo.adapterId.HighPart == (_DWORD)v8
          && pathArray[0][v16].sourceInfo.id == a3 )
        {
          v14 = v16;
          ++v15;
        }
        ++v16;
      }
      while ( v16 < numPathArrayElements );
      if ( v15 == 1 )
      {
        memset_0(&requestPacket.id, 0, 0x194u);
        requestPacket.type = DISPLAYCONFIG_DEVICE_INFO_GET_TARGET_NAME;
        requestPacket.size = 420;
        requestPacket.adapterId.LowPart = v7;
        requestPacket.adapterId.HighPart = v8;
        requestPacket.id = v17[v14].targetInfo.id;
        DeviceInfo = DisplayConfigGetDeviceInfo(&requestPacket);
        if ( DeviceInfo )
        {
          v19 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x2E2,
                  (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\modernprofman.cxx",
                  (const char *)DeviceInfo,
                  modeInfoArraya);
          std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)pathArray);
          std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy((__int64)v33);
          WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)v25);
          return v19;
        }
        else
        {
          v41 = xmmword_18009EC28;
          v40[0] = *(_QWORD *)winrt::hstring::hstring((winrt::hstring *)&v37, v43);
          ColorManagerForDisplayAsync = winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement::GetColorManagerForDisplayAsync(
                                          (const struct winrt::param::hstring *)&v36,
                                          (const struct winrt::guid *)v40);
          winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>,winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::get(
            ColorManagerForDisplayAsync,
            &v30);
          winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(&v36);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v37);
          v38 = 0;
          v39 = 0;
          v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 104LL))(v30, &v28);
          winrt::check_hresult(v35, v21, &v38);
          winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(&v30);
          v22 = a4 - 1;
          if ( v22 )
          {
            if ( v22 == 1 )
            {
              a5[1] = HIDWORD(v28);
              a5[2] = v29;
              a5[3] = WORD2(v29);
              a5[4] = HIWORD(v29);
            }
          }
          else
          {
            a5[1] = v28;
          }
          std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)pathArray);
          std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy((__int64)v33);
          WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)v25);
          return 0;
        }
      }
      else
      {
LABEL_22:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D9,
          (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\modernprofman.cxx",
          (const char *)0x80070057LL,
          modeInfoArraya);
        std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)pathArray);
        std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy((__int64)v33);
        WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)v25);
        return 2147942487LL;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BC,
      (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\modernprofman.cxx",
      (const char *)0x80004004LL,
      modeInfoArray);
    WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)v25);
    return 2147500036LL;
  }
}

```

## disassembly

```asm
0x18004cf60  mov     [rsp+arg_0], rbx
0x18004cf65  mov     [rsp+arg_10], rsi
0x18004cf6a  push    rdi
0x18004cf6b  push    r12
0x18004cf6d  push    r13
0x18004cf6f  push    r14
0x18004cf71  push    r15
0x18004cf73  sub     rsp, 2B0h
0x18004cf7a  mov     rax, cs:__security_cookie
0x18004cf81  xor     rax, rsp
0x18004cf84  mov     [rsp+2D8h+var_38], rax
0x18004cf8c  mov     edi, r9d
0x18004cf8f  mov     r13d, r8d
0x18004cf92  mov     rbx, rdx
0x18004cf95  mov     r15, rdx
0x18004cf98  shr     r15, 20h
0x18004cf9c  mov     rsi, [rsp+2D8h+arg_20]
0x18004cfa4  lea     rcx, [rsp+2D8h+var_2A8]; this
0x18004cfa9  call    ??0WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::WinRTActivationWrapper(void)
0x18004cfae  nop
0x18004cfaf  xor     r14d, r14d
0x18004cfb2  mov     [rsp+2D8h+var_298], r14
0x18004cfb7  mov     [rsp+2D8h+var_290], r14
0x18004cfbc  mov     [rsp+2D8h+numPathArrayElements], r14d
0x18004cfc1  mov     [rsp+2D8h+numModeInfoArrayElements], r14d
0x18004cfc6  lea     r8, [rsp+2D8h+numModeInfoArrayElements]; numModeInfoArrayElements
0x18004cfcb  lea     rdx, [rsp+2D8h+numPathArrayElements]; numPathArrayElements
0x18004cfd0  lea     r12d, [r14+2]
0x18004cfd4  mov     ecx, r12d; flags
0x18004cfd7  call    cs:__imp_GetDisplayConfigBufferSizes
0x18004cfdd  test    eax, eax
0x18004cfdf  jz      short loc_18004D010
0x18004cfe1  mov     rcx, [rsp+2D8h]; this
0x18004cfe9  mov     r9d, eax; char *
0x18004cfec  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\core\\color\\mscms"...
0x18004cff3  mov     edx, 2B7h; void *
0x18004cff8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004cffd  mov     ebx, eax
0x18004cfff  lea     rcx, [rsp+2D8h+var_2A8]; this
0x18004d004  call    ??1WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::~WinRTActivationWrapper(void)
0x18004d009  mov     eax, ebx
0x18004d00b  jmp     loc_18004D359
0x18004d010  cmp     [rsp+2D8h+numPathArrayElements], 1
0x18004d015  jb      loc_18004D325
0x18004d01b  cmp     [rsp+2D8h+numModeInfoArrayElements], 1
0x18004d020  jb      loc_18004D325
0x18004d026  xorps   xmm0, xmm0
0x18004d029  movdqu  xmmword ptr [rsp+2D8h+var_268], xmm0
0x18004d02f  mov     [rsp+2D8h+var_258], r14
0x18004d037  mov     edx, [rsp+2D8h+numModeInfoArrayElements]
0x18004d03b  lea     rcx, [rsp+2D8h+var_268]
0x18004d040  call    ??$_Construct_n@$$V@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_K@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::_Construct_n<>(unsigned __int64)
0x18004d045  nop
0x18004d046  xorps   xmm0, xmm0
0x18004d049  movdqu  xmmword ptr [rsp+2D8h+pathArray], xmm0
0x18004d04f  mov     [rsp+2D8h+var_270], r14
0x18004d054  mov     edx, [rsp+2D8h+numPathArrayElements]
0x18004d058  lea     rcx, [rsp+2D8h+pathArray]
0x18004d05d  call    ??$_Construct_n@$$V@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_K@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::_Construct_n<>(unsigned __int64)
0x18004d062  nop
0x18004d063  mov     rax, [rsp+2D8h+var_268]
0x18004d068  mov     [rsp+2D8h+currentTopologyId], r14; currentTopologyId
0x18004d06d  mov     [rsp+2D8h+modeInfoArray], rax; int
0x18004d072  lea     r9, [rsp+2D8h+numModeInfoArrayElements]; numModeInfoArrayElements
0x18004d077  mov     r8, [rsp+2D8h+pathArray]; pathArray
0x18004d07c  lea     rdx, [rsp+2D8h+numPathArrayElements]; numPathArrayElements
0x18004d081  mov     ecx, r12d; flags
0x18004d084  call    cs:__imp_QueryDisplayConfig
0x18004d08a  test    eax, eax
0x18004d08c  jz      short loc_18004D0D3
0x18004d08e  mov     rcx, [rsp+2D8h]; this
0x18004d096  mov     r9d, eax; char *
0x18004d099  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\core\\color\\mscms"...
0x18004d0a0  mov     edx, 2C9h; void *
0x18004d0a5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004d0aa  mov     ebx, eax
0x18004d0ac  lea     rcx, [rsp+2D8h+pathArray]
0x18004d0b1  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x18004d0b6  nop
0x18004d0b7  lea     rcx, [rsp+2D8h+var_268]
0x18004d0bc  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x18004d0c1  nop
0x18004d0c2  lea     rcx, [rsp+2D8h+var_2A8]; this
0x18004d0c7  call    ??1WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::~WinRTActivationWrapper(void)
0x18004d0cc  mov     eax, ebx
0x18004d0ce  jmp     loc_18004D359
0x18004d0d3  mov     r12d, r14d
0x18004d0d6  mov     edx, r14d
0x18004d0d9  mov     ecx, r14d
0x18004d0dc  mov     r9d, [rsp+2D8h+numPathArrayElements]
0x18004d0e1  test    r9d, r9d
0x18004d0e4  jz      loc_18004D2DF
0x18004d0ea  mov     r14, [rsp+2D8h+pathArray]
0x18004d0ef  mov     eax, ecx
0x18004d0f1  lea     r8, [rax+rax*8]
0x18004d0f5  cmp     [r14+r8*8+14h], ebx
0x18004d0fa  jnz     short loc_18004D10F
0x18004d0fc  cmp     [r14+r8*8+18h], r15d
0x18004d101  jnz     short loc_18004D10F
0x18004d103  cmp     [r14+r8*8+8], r13d
0x18004d108  jnz     short loc_18004D10F
0x18004d10a  mov     r12d, ecx
0x18004d10d  inc     edx
0x18004d10f  inc     ecx
0x18004d111  cmp     ecx, r9d
0x18004d114  jb      short loc_18004D0EF
0x18004d116  cmp     edx, 1
0x18004d119  jnz     loc_18004D2DF
0x18004d11f  xor     edx, edx; Val
0x18004d121  mov     r8d, 194h; Size
0x18004d127  lea     rcx, [rsp+2D8h+requestPacket.id]; void *
0x18004d12f  call    memset_0
0x18004d134  mov     [rsp+2D8h+requestPacket.type], 2
0x18004d13f  mov     [rsp+2D8h+requestPacket.size], 1A4h
0x18004d14a  mov     [rsp+2D8h+requestPacket.adapterId.LowPart], ebx
0x18004d151  mov     [rsp+2D8h+requestPacket.adapterId.HighPart], r15d
0x18004d159  mov     eax, r12d
0x18004d15c  lea     rcx, [rax+rax*8]
0x18004d160  mov     eax, [r14+rcx*8+1Ch]
0x18004d165  mov     [rsp+2D8h+requestPacket.id], eax
0x18004d16c  lea     rcx, [rsp+2D8h+requestPacket]; requestPacket
0x18004d174  call    cs:__imp_DisplayConfigGetDeviceInfo
0x18004d17a  test    eax, eax
0x18004d17c  jz      short loc_18004D1C3
0x18004d17e  mov     rcx, [rsp+2D8h]; this
0x18004d186  mov     r9d, eax; char *
0x18004d189  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\core\\color\\mscms"...
0x18004d190  mov     edx, 2E2h; void *
0x18004d195  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004d19a  mov     ebx, eax
0x18004d19c  lea     rcx, [rsp+2D8h+pathArray]
0x18004d1a1  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x18004d1a6  nop
0x18004d1a7  lea     rcx, [rsp+2D8h+var_268]
0x18004d1ac  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x18004d1b1  nop
0x18004d1b2  lea     rcx, [rsp+2D8h+var_2A8]; this
0x18004d1b7  call    ??1WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::~WinRTActivationWrapper(void)
0x18004d1bc  mov     eax, ebx
0x18004d1be  jmp     loc_18004D359
0x18004d1c3  movups  xmm0, cs:xmmword_18009EC28
0x18004d1ca  movdqu  [rsp+2D8h+var_200], xmm0
0x18004d1d3  lea     rdx, [rsp+2D8h+var_144]; unsigned __int16 *
0x18004d1db  lea     rcx, [rsp+2D8h+var_240]; this
0x18004d1e3  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18004d1e8  nop
0x18004d1e9  mov     rax, [rax]
0x18004d1ec  mov     [rsp+2D8h+var_220], rax
0x18004d1f4  lea     r8, [rsp+2D8h+var_200]
0x18004d1fc  lea     rdx, [rsp+2D8h+var_220]; struct winrt::guid *
0x18004d204  lea     rcx, [rsp+2D8h+var_248]; struct winrt::param::hstring *
0x18004d20c  call    ?GetColorManagerForDisplayAsync@DisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@SA@AEBUhstring@param@6@AEBUguid@6@@Z; winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement::GetColorManagerForDisplayAsync(winrt::param::hstring const &,winrt::guid const &)
0x18004d211  nop
0x18004d212  lea     rdx, [rsp+2D8h+var_288]
0x18004d217  mov     rcx, rax
0x18004d21a  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UDisplayColorManagement@5Display@Graphics@Internal@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>,winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::get(void)
0x18004d21f  nop
0x18004d220  lea     rcx, [rsp+2D8h+var_248]
0x18004d228  call    ??1?$IAsyncOperation@UDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(void)
0x18004d22d  nop
0x18004d22e  lea     rcx, [rsp+2D8h+var_240]
0x18004d236  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18004d23b  mov     rcx, [rsp+2D8h+var_288]
0x18004d240  mov     [rsp+2D8h+var_238], 0
0x18004d24b  xorps   xmm0, xmm0
0x18004d24e  movdqu  [rsp+2D8h+var_230], xmm0
0x18004d257  mov     rax, [rcx]
0x18004d25a  lea     rdx, [rsp+2D8h+var_298]
0x18004d25f  mov     rax, [rax+68h]
0x18004d263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d268  lea     r8, [rsp+2D8h+var_238]
0x18004d270  mov     edx, eax
0x18004d272  lea     rcx, [rsp+2D8h+var_250]
0x18004d27a  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18004d27f  nop
0x18004d280  lea     rcx, [rsp+2D8h+var_288]
0x18004d285  call    ??1?$IAsyncOperation@UDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(void)
0x18004d28a  sub     edi, 1
0x18004d28d  jz      short loc_18004D2B4
0x18004d28f  cmp     edi, 1
0x18004d292  jnz     short loc_18004D2BB
0x18004d294  mov     eax, dword ptr [rsp+2D8h+var_298+4]
0x18004d298  mov     [rsi+4], eax
0x18004d29b  mov     eax, dword ptr [rsp+2D8h+var_290]
0x18004d29f  mov     [rsi+8], eax
0x18004d2a2  movzx   eax, word ptr [rsp+2D8h+var_290+4]
0x18004d2a7  mov     [rsi+0Ch], eax
0x18004d2aa  movzx   eax, word ptr [rsp+2D8h+var_290+6]
0x18004d2af  mov     [rsi+10h], eax
0x18004d2b2  jmp     short loc_18004D2BB
0x18004d2b4  mov     eax, dword ptr [rsp+2D8h+var_298]
0x18004d2b8  mov     [rsi+4], eax
0x18004d2bb  lea     rcx, [rsp+2D8h+pathArray]
0x18004d2c0  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x18004d2c5  nop
0x18004d2c6  lea     rcx, [rsp+2D8h+var_268]
0x18004d2cb  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x18004d2d0  nop
0x18004d2d1  lea     rcx, [rsp+2D8h+var_2A8]; this
0x18004d2d6  call    ??1WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::~WinRTActivationWrapper(void)
0x18004d2db  xor     eax, eax
0x18004d2dd  jmp     short loc_18004D359
0x18004d2df  mov     rcx, [rsp+2D8h]; this
0x18004d2e7  mov     ebx, 80070057h
0x18004d2ec  mov     r9d, ebx; char *
0x18004d2ef  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\core\\color\\mscms"...
0x18004d2f6  mov     edx, 2D9h; void *
0x18004d2fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d300  nop
0x18004d301  lea     rcx, [rsp+2D8h+pathArray]
0x18004d306  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x18004d30b  nop
0x18004d30c  lea     rcx, [rsp+2D8h+var_268]
0x18004d311  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x18004d316  nop
0x18004d317  lea     rcx, [rsp+2D8h+var_2A8]; this
0x18004d31c  call    ??1WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::~WinRTActivationWrapper(void)
0x18004d321  mov     eax, ebx
0x18004d323  jmp     short loc_18004D359
0x18004d325  mov     rcx, [rsp+2D8h]; this
0x18004d32d  mov     ebx, 80004004h
0x18004d332  mov     r9d, ebx; char *
0x18004d335  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\core\\color\\mscms"...
0x18004d33c  mov     edx, 2BCh; void *
0x18004d341  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d346  nop
0x18004d347  lea     rcx, [rsp+2D8h+var_2A8]; this
0x18004d34c  call    ??1WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::~WinRTActivationWrapper(void)
0x18004d351  mov     eax, ebx
0x18004d353  jmp     short loc_18004D359
0x18004d355  mov     eax, [rsp+2D8h+numModeInfoArrayElements]
0x18004d359  mov     rcx, [rsp+2D8h+var_38]
0x18004d361  xor     rcx, rsp; StackCookie
0x18004d364  call    __security_check_cookie
0x18004d369  lea     r11, [rsp+2D8h+var_28]
0x18004d371  mov     rbx, [r11+30h]
0x18004d375  mov     rsi, [r11+40h]
0x18004d379  mov     rsp, r11
0x18004d37c  pop     r15
0x18004d37e  pop     r14
0x18004d380  pop     r13
0x18004d382  pop     r12
0x18004d384  pop     rdi
0x18004d385  retn
```
