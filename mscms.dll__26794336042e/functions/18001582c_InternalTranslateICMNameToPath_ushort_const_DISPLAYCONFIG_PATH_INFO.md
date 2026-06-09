# InternalTranslateICMNameToPath(ushort const *,DISPLAYCONFIG_PATH_INFO *)

- ea: `0x18001582c`
- end: `0x180015e73`
- name: `?InternalTranslateICMNameToPath@@YAJPEBGPEAUDISPLAYCONFIG_PATH_INFO@@@Z`
- size: `1607`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct DISPLAYCONFIG_PATH_INFO *)`
- caller_count: `8`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x1800212e0`
- `0x180023428`
- `0x1800258c0`
- `0x180026090`
- `0x180029404`
- `0x180047f20`
- `0x18004a294`
- `0x18004aa0c`

## callees

- `0x18001547c`
- `0x180015724`
- `0x1800157dc`
- `0x18001582c`
- `0x180017474`
- `0x1800174f8`
- `0x180017510`
- `0x1800176ac`
- `0x1800219ec`
- `0x180022044`
- `0x180022a80`
- `0x180023194`
- `0x180027408`
- `0x180028690`
- `0x18002939c`
- `0x18002ac10`
- `0x18002ad24`
- `0x18002aea8`
- `0x18002e5f0`
- `0x18002f2f4`
- `0x18003e874`
- `0x180084010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1800158cc`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x180015c6c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x180015b09`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x180015b09`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!EnumDisplayDevicesW` at `0x180015c05`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!EnumDisplayDevicesW` at `0x180015c05`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180015bc2`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180015bc2`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x1800159c7`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x1800159c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall InternalTranslateICMNameToPath(const unsigned __int16 *a1, struct DISPLAYCONFIG_PATH_INFO *a2)
{
  __int64 v3; // r8
  unsigned __int64 v4; // rdx
  int v5; // eax
  wint_t *v6; // rdi
  __int128 *v7; // rcx
  int v8; // r10d
  wint_t *v9; // r14
  wint_t *v10; // rbx
  __int64 v11; // r8
  __int128 *v12; // rcx
  __int64 v13; // rax
  unsigned int DisplayConfigBufferSizes; // eax
  unsigned int v16; // ebx
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // ebx
  DISPLAYCONFIG_PATH_INFO *v21; // rbx
  char *v22; // rdi
  wchar_t **v23; // r9
  wchar_t **v24; // rdx
  int v25; // r8d
  wchar_t **v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rax
  const wchar_t *v29; // rdx
  const wchar_t *v30; // rcx
  unsigned int modeInfoArray; // [rsp+20h] [rbp-4A8h]
  unsigned int modeInfoArraya; // [rsp+20h] [rbp-4A8h]
  UINT32 numPathArrayElements; // [rsp+30h] [rbp-498h] BYREF
  UINT32 numModeInfoArrayElements; // [rsp+34h] [rbp-494h] BYREF
  DISPLAYCONFIG_MODE_INFO *v35[2]; // [rsp+38h] [rbp-490h] BYREF
  __int64 v36; // [rsp+48h] [rbp-480h]
  DISPLAYCONFIG_PATH_INFO *pathArray; // [rsp+50h] [rbp-478h] BYREF
  char *v38; // [rsp+58h] [rbp-470h]
  __int64 v39; // [rsp+60h] [rbp-468h]
  char v40; // [rsp+68h] [rbp-460h] BYREF
  __int128 v41; // [rsp+70h] [rbp-458h] BYREF
  __int128 v42; // [rsp+80h] [rbp-448h]
  wchar_t *S1[2]; // [rsp+90h] [rbp-438h] BYREF
  size_t N; // [rsp+A0h] [rbp-428h]
  unsigned __int64 v45; // [rsp+A8h] [rbp-420h]
  wchar_t *S2[2]; // [rsp+B0h] [rbp-418h] BYREF
  __int64 v47; // [rsp+C0h] [rbp-408h]
  unsigned __int64 v48; // [rsp+C8h] [rbp-400h]
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+D0h] [rbp-3F8h] BYREF
  WCHAR Device[38]; // [rsp+E4h] [rbp-3E4h] BYREF
  _BYTE v51[32]; // [rsp+130h] [rbp-398h] BYREF
  struct _DISPLAY_DEVICEW DisplayDevice; // [rsp+150h] [rbp-378h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+0h]

  v41 = 0;
  v42 = 0;
  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  std::wstring::_Construct<1,unsigned short const *>(&v41, a1, v3);
  v4 = *((_QWORD *)&v42 + 1);
  v5 = v41;
  if ( *((_QWORD *)&v42 + 1) <= 7u )
  {
    v6 = (wint_t *)&v41;
    v7 = &v41;
  }
  else
  {
    v6 = (wint_t *)v41;
    v7 = (__int128 *)v41;
  }
  v8 = v42;
  v9 = (wint_t *)v7 + v42;
  v10 = (wint_t *)&v41;
  if ( *((_QWORD *)&v42 + 1) > 7u )
    v10 = (wint_t *)v41;
  while ( v10 != v9 )
  {
    *v6++ = towupper(*v10++);
    v4 = *((_QWORD *)&v42 + 1);
    v8 = v42;
    v5 = v41;
  }
  v11 = -1;
  do
    ++v11;
  while ( gszMonitorGUID[v11] );
  v12 = &v41;
  if ( v4 > 7 )
    LODWORD(v12) = v5;
  v13 = std::_Traits_find<std::char_traits<unsigned short>>((_DWORD)v12, v8, v11, (unsigned int)gszMonitorGUID, v11);
  if ( v13 == -1 )
  {
    std::wstring::_Tidy_deallocate(&v41);
    return 2147942487LL;
  }
  else
  {
    std::wstring::substr(&v41, S2, v13);
    numPathArrayElements = 0;
    numModeInfoArrayElements = 0;
    std::vector<DISPLAYCONFIG_PATH_INFO>::vector<DISPLAYCONFIG_PATH_INFO>(&pathArray);
    std::vector<DISPLAYCONFIG_PATH_INFO>::vector<DISPLAYCONFIG_PATH_INFO>(v35);
    if ( a2 )
    {
      DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(0x12u, &numPathArrayElements, &numModeInfoArrayElements);
      if ( DisplayConfigBufferSizes )
      {
        v16 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x359B,
                (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\profman.cxx",
                (const char *)DisplayConfigBufferSizes,
                modeInfoArray);
        std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy((__int64)v35);
        std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)&pathArray);
        std::wstring::_Tidy_deallocate(S2);
        std::wstring::_Tidy_deallocate(&v41);
        return v16;
      }
      else
      {
        v17 = 0x8E38E38E38E38E39uLL * ((v38 - (char *)pathArray) >> 3);
        if ( numPathArrayElements >= v17 )
        {
          if ( numPathArrayElements > v17 )
          {
            if ( numPathArrayElements <= 0x8E38E38E38E38E39uLL * ((v39 - (__int64)pathArray) >> 3) )
              v38 = std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(
                      v38,
                      numPathArrayElements - v17);
            else
              std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(
                (const void **)&pathArray,
                numPathArrayElements);
          }
        }
        else
        {
          v38 = (char *)&pathArray[numPathArrayElements];
        }
        v18 = v35[1] - v35[0];
        if ( numModeInfoArrayElements >= v18 )
        {
          if ( numModeInfoArrayElements > v18 )
          {
            if ( numModeInfoArrayElements <= (unsigned __int64)((signed __int64)(v36 - (unsigned __int64)v35[0]) >> 6) )
              v35[1] = (DISPLAYCONFIG_MODE_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(
                                                    (char *)v35[1],
                                                    numModeInfoArrayElements - v18);
            else
              std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(
                (const void **)v35,
                numModeInfoArrayElements);
          }
        }
        else
        {
          v35[1] = &v35[0][(unsigned __int64)numModeInfoArrayElements];
        }
        v19 = QueryDisplayConfig(0x12u, &numPathArrayElements, pathArray, &numModeInfoArrayElements, v35[0], 0);
        if ( v19 )
        {
          v20 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x35A7,
                  (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\profman.cxx",
                  (const char *)v19,
                  modeInfoArraya);
          std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy((__int64)v35);
          std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)&pathArray);
          std::wstring::_Tidy_deallocate(S2);
          std::wstring::_Tidy_deallocate(&v41);
          return v20;
        }
        else
        {
          v21 = pathArray;
          v22 = v38;
          while ( v21 != (DISPLAYCONFIG_PATH_INFO *)v22 )
          {
            memset_0(&requestPacket, 0, 0x54u);
            requestPacket.type = DISPLAYCONFIG_DEVICE_INFO_GET_SOURCE_NAME;
            requestPacket.size = 84;
            requestPacket.adapterId = v21->targetInfo.adapterId;
            requestPacket.id = v21->sourceInfo.id;
            if ( !DisplayConfigGetDeviceInfo(&requestPacket) )
            {
              memset_0(DisplayDevice.DeviceName, 0, 0x344u);
              DisplayDevice.cb = 840;
              if ( EnumDisplayDevicesW(Device, 0, &DisplayDevice, 0) )
              {
                std::wstring::wstring(S1, DisplayDevice.DeviceID);
                if ( v45 <= 7 )
                {
                  v23 = S1;
                  v24 = S1;
                }
                else
                {
                  LODWORD(v23) = S1[0];
                  LODWORD(v24) = S1[0];
                }
                v25 = (_DWORD)v24 + 2 * N;
                v26 = S1;
                if ( v45 > 7 )
                  LODWORD(v26) = S1[0];
                std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
                  (unsigned int)&v40,
                  (_DWORD)v26,
                  v25,
                  (_DWORD)v23,
                  (__int64)towupper);
                v27 = std::wstring::find(S1, gszMonitorGUID);
                if ( v27 != -1 )
                {
                  v28 = std::wstring::substr(S1, v51, v27);
                  std::wstring::operator=(S1, v28);
                  std::wstring::_Tidy_deallocate(v51);
                  v29 = (const wchar_t *)S2;
                  if ( v48 > 7 )
                    v29 = S2[0];
                  v30 = (const wchar_t *)S1;
                  if ( v45 > 7 )
                    v30 = S1[0];
                  if ( N == v47 && (!N || !wmemcmp(v30, v29, N)) )
                  {
                    *(_OWORD *)&a2->sourceInfo.adapterId.LowPart = *(_OWORD *)&v21->sourceInfo.adapterId.LowPart;
                    *(_OWORD *)&a2->sourceInfo.statusFlags = *(_OWORD *)&v21->sourceInfo.statusFlags;
                    *(_OWORD *)&a2->targetInfo.modeInfoIdx = *(_OWORD *)&v21->targetInfo.modeInfoIdx;
                    *(_OWORD *)&a2->targetInfo.refreshRate.Numerator = *(_OWORD *)&v21->targetInfo.refreshRate.Numerator;
                    *(_QWORD *)&a2->targetInfo.statusFlags = *(_QWORD *)&v21->targetInfo.statusFlags;
                    std::wstring::_Tidy_deallocate(S1);
                    std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy((__int64)v35);
                    std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)&pathArray);
                    std::wstring::_Tidy_deallocate(S2);
                    std::wstring::_Tidy_deallocate(&v41);
                    return 0;
                  }
                }
                std::wstring::_Tidy_deallocate(S1);
              }
            }
            ++v21;
          }
          if ( v35[0] )
          {
            std::_Deallocate<16>(v35[0], (v36 - (unsigned __int64)v35[0]) & 0xFFFFFFFFFFFFFFC0uLL);
            *(_OWORD *)v35 = 0;
            v36 = 0;
          }
          std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)&pathArray);
          if ( v48 > 7 )
            std::_Deallocate<16>(S2[0], 2 * v48 + 2);
          v47 = 0;
          v48 = 7;
          LOWORD(S2[0]) = 0;
          if ( *((_QWORD *)&v42 + 1) > 7u )
            std::_Deallocate<16>((void *)v41, 2LL * *((_QWORD *)&v42 + 1) + 2);
          return 2147942487LL;
        }
      }
    }
    else
    {
      std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy((__int64)v35);
      std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy((__int64)&pathArray);
      std::wstring::_Tidy_deallocate(S2);
      std::wstring::_Tidy_deallocate(&v41);
      return 2147942487LL;
    }
  }
}

```

## disassembly

```asm
0x18001582c  mov     [rsp+arg_10], rbx
0x180015831  mov     [rsp+arg_18], rsi
0x180015836  push    rdi
0x180015837  push    r14
0x180015839  push    r15
0x18001583b  sub     rsp, 4B0h
0x180015842  mov     rax, cs:__security_cookie
0x180015849  xor     rax, rsp
0x18001584c  mov     [rsp+4C8h+var_28], rax
0x180015854  mov     rsi, rdx
0x180015857  xor     r15d, r15d
0x18001585a  xorps   xmm0, xmm0
0x18001585d  movups  [rsp+4C8h+var_458], xmm0
0x180015862  xorps   xmm1, xmm1
0x180015865  movdqu  [rsp+4C8h+var_448], xmm1
0x18001586e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015872  inc     r8
0x180015875  cmp     [rcx+r8*2], r15w
0x18001587a  jnz     short loc_180015872
0x18001587c  mov     rdx, rcx
0x18001587f  lea     rcx, [rsp+4C8h+var_458]
0x180015884  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180015889  nop
0x18001588a  mov     rdx, qword ptr [rsp+4C8h+var_448+8]
0x180015892  mov     rax, qword ptr [rsp+4C8h+var_458]
0x180015897  cmp     rdx, 7
0x18001589b  jbe     short loc_1800158A5
0x18001589d  mov     rdi, rax
0x1800158a0  mov     rcx, rax
0x1800158a3  jmp     short loc_1800158AF
0x1800158a5  lea     rdi, [rsp+4C8h+var_458]
0x1800158aa  lea     rcx, [rsp+4C8h+var_458]
0x1800158af  mov     r10, qword ptr [rsp+4C8h+var_448]
0x1800158b7  lea     r14, [rcx+r10*2]
0x1800158bb  lea     rbx, [rsp+4C8h+var_458]
0x1800158c0  cmova   rbx, rax
0x1800158c4  cmp     rbx, r14
0x1800158c7  jz      short loc_1800158FA
0x1800158c9  movzx   ecx, word ptr [rbx]
0x1800158cc  mov     rax, cs:__imp_towupper
0x1800158d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158d8  mov     [rdi], ax
0x1800158db  add     rbx, 2
0x1800158df  add     rdi, 2
0x1800158e3  mov     rdx, qword ptr [rsp+4C8h+var_448+8]
0x1800158eb  mov     r10, qword ptr [rsp+4C8h+var_448]
0x1800158f3  mov     rax, qword ptr [rsp+4C8h+var_458]
0x1800158f8  jmp     short loc_1800158C4
0x1800158fa  lea     r9, gszMonitorGUID; "{4D36E96E-E325-11CE-BFC1-08002BE10318}"
0x180015901  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015905  inc     r8
0x180015908  cmp     [r9+r8*2], r15w
0x18001590d  jnz     short loc_180015905
0x18001590f  lea     rcx, [rsp+4C8h+var_458]
0x180015914  cmp     rdx, 7
0x180015918  cmova   rcx, rax
0x18001591c  mov     [rsp+4C8h+modeInfoArray], r8; unsigned int
0x180015921  mov     rdx, r10
0x180015924  call    ??$_Traits_find@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x180015929  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001592d  jnz     short loc_180015943
0x18001592f  lea     rcx, [rsp+4C8h+var_458]
0x180015934  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015939  mov     eax, 80070057h
0x18001593e  jmp     loc_180015E49
0x180015943  mov     r8, rax
0x180015946  lea     rdx, [rsp+4C8h+S2]
0x18001594e  lea     rcx, [rsp+4C8h+var_458]
0x180015953  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180015958  nop
0x180015959  mov     [rsp+4C8h+numPathArrayElements], r15d
0x18001595e  mov     [rsp+4C8h+numModeInfoArrayElements], r15d
0x180015963  lea     rcx, [rsp+4C8h+pathArray]
0x180015968  call    ??0?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@QEAA@XZ; std::vector<DISPLAYCONFIG_PATH_INFO>::vector<DISPLAYCONFIG_PATH_INFO>(void)
0x18001596d  nop
0x18001596e  lea     rcx, [rsp+4C8h+var_490]
0x180015973  call    ??0?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@QEAA@XZ; std::vector<DISPLAYCONFIG_PATH_INFO>::vector<DISPLAYCONFIG_PATH_INFO>(void)
0x180015978  nop
0x180015979  test    rsi, rsi
0x18001597c  jnz     short loc_1800159B6
0x18001597e  lea     rcx, [rsp+4C8h+var_490]
0x180015983  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x180015988  nop
0x180015989  lea     rcx, [rsp+4C8h+pathArray]
0x18001598e  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x180015993  nop
0x180015994  lea     rcx, [rsp+4C8h+S2]
0x18001599c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800159a1  nop
0x1800159a2  lea     rcx, [rsp+4C8h+var_458]
0x1800159a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800159ac  mov     eax, 80070057h
0x1800159b1  jmp     loc_180015E49
0x1800159b6  lea     r8, [rsp+4C8h+numModeInfoArrayElements]; numModeInfoArrayElements
0x1800159bb  lea     rdx, [rsp+4C8h+numPathArrayElements]; numPathArrayElements
0x1800159c0  mov     ebx, 12h
0x1800159c5  mov     ecx, ebx; flags
0x1800159c7  call    cs:__imp_GetDisplayConfigBufferSizes
0x1800159cd  test    eax, eax
0x1800159cf  jz      short loc_180015A24
0x1800159d1  mov     rcx, [rsp+4C8h]; this
0x1800159d9  mov     r9d, eax; char *
0x1800159dc  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\core\\color\\mscms"...
0x1800159e3  mov     edx, 359Bh; void *
0x1800159e8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800159ed  mov     ebx, eax
0x1800159ef  lea     rcx, [rsp+4C8h+var_490]
0x1800159f4  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x1800159f9  nop
0x1800159fa  lea     rcx, [rsp+4C8h+pathArray]
0x1800159ff  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x180015a04  nop
0x180015a05  lea     rcx, [rsp+4C8h+S2]
0x180015a0d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015a12  nop
0x180015a13  lea     rcx, [rsp+4C8h+var_458]
0x180015a18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015a1d  mov     eax, ebx
0x180015a1f  jmp     loc_180015E49
0x180015a24  mov     edx, [rsp+4C8h+numPathArrayElements]
0x180015a28  mov     r8, [rsp+4C8h+pathArray]
0x180015a2d  mov     rcx, [rsp+4C8h+var_470]
0x180015a32  sub     rcx, r8
0x180015a35  sar     rcx, 3
0x180015a39  mov     r9, 8E38E38E38E38E39h
0x180015a43  imul    rcx, r9
0x180015a47  cmp     rdx, rcx
0x180015a4a  jnb     short loc_180015A5B
0x180015a4c  lea     rax, [rdx+rdx*8]
0x180015a50  lea     rcx, [r8+rax*8]
0x180015a54  mov     [rsp+4C8h+var_470], rcx
0x180015a59  jmp     short loc_180015A90
0x180015a5b  jbe     short loc_180015A90
0x180015a5d  mov     rax, [rsp+4C8h+var_468]
0x180015a62  sub     rax, r8
0x180015a65  sar     rax, 3
0x180015a69  imul    rax, r9
0x180015a6d  cmp     rdx, rax
0x180015a70  jbe     short loc_180015A7E
0x180015a72  lea     rcx, [rsp+4C8h+pathArray]
0x180015a77  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180015a7c  jmp     short loc_180015A90
0x180015a7e  sub     rdx, rcx
0x180015a81  mov     rcx, [rsp+4C8h+var_470]
0x180015a86  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_PATH_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_PATH_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(DISPLAYCONFIG_PATH_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_PATH_INFO> &)
0x180015a8b  mov     [rsp+4C8h+var_470], rax
0x180015a90  mov     edx, [rsp+4C8h+numModeInfoArrayElements]
0x180015a94  mov     r8, [rsp+4C8h+var_490]
0x180015a99  mov     rcx, [rsp+4C8h+var_490+8]
0x180015a9e  sub     rcx, r8
0x180015aa1  sar     rcx, 6
0x180015aa5  cmp     rdx, rcx
0x180015aa8  jnb     short loc_180015AB8
0x180015aaa  shl     rdx, 6
0x180015aae  add     rdx, r8
0x180015ab1  mov     [rsp+4C8h+var_490+8], rdx
0x180015ab6  jmp     short loc_180015AE9
0x180015ab8  jbe     short loc_180015AE9
0x180015aba  mov     rax, [rsp+4C8h+var_480]
0x180015abf  sub     rax, r8
0x180015ac2  sar     rax, 6
0x180015ac6  cmp     rdx, rax
0x180015ac9  jbe     short loc_180015AD7
0x180015acb  lea     rcx, [rsp+4C8h+var_490]
0x180015ad0  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180015ad5  jmp     short loc_180015AE9
0x180015ad7  sub     rdx, rcx
0x180015ada  mov     rcx, [rsp+4C8h+var_490+8]
0x180015adf  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_MODE_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_MODE_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(DISPLAYCONFIG_MODE_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_MODE_INFO> &)
0x180015ae4  mov     [rsp+4C8h+var_490+8], rax
0x180015ae9  mov     rax, [rsp+4C8h+var_490]
0x180015aee  mov     [rsp+4C8h+currentTopologyId], r15; currentTopologyId
0x180015af3  mov     [rsp+4C8h+modeInfoArray], rax; unsigned int
0x180015af8  lea     r9, [rsp+4C8h+numModeInfoArrayElements]; numModeInfoArrayElements
0x180015afd  mov     r8, [rsp+4C8h+pathArray]; pathArray
0x180015b02  lea     rdx, [rsp+4C8h+numPathArrayElements]; numPathArrayElements
0x180015b07  mov     ecx, ebx; flags
0x180015b09  call    cs:__imp_QueryDisplayConfig
0x180015b0f  test    eax, eax
0x180015b11  jz      short loc_180015B66
0x180015b13  mov     rcx, [rsp+4C8h]; this
0x180015b1b  mov     r9d, eax; char *
0x180015b1e  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\core\\color\\mscms"...
0x180015b25  mov     edx, 35A7h; void *
0x180015b2a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180015b2f  mov     ebx, eax
0x180015b31  lea     rcx, [rsp+4C8h+var_490]
0x180015b36  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x180015b3b  nop
0x180015b3c  lea     rcx, [rsp+4C8h+pathArray]
0x180015b41  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x180015b46  nop
0x180015b47  lea     rcx, [rsp+4C8h+S2]
0x180015b4f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015b54  nop
0x180015b55  lea     rcx, [rsp+4C8h+var_458]
0x180015b5a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015b5f  mov     eax, ebx
0x180015b61  jmp     loc_180015E49
0x180015b66  mov     rbx, [rsp+4C8h+pathArray]
0x180015b6b  mov     rdi, [rsp+4C8h+var_470]
0x180015b70  mov     r14d, 54h ; 'T'
0x180015b76  cmp     rbx, rdi
0x180015b79  jz      loc_180015DAA
0x180015b7f  mov     r8, r14; Size
0x180015b82  xor     edx, edx; Val
0x180015b84  lea     rcx, [rsp+4C8h+requestPacket]; void *
0x180015b8c  call    memset_0
0x180015b91  mov     [rsp+4C8h+requestPacket.type], 1
0x180015b9c  mov     [rsp+4C8h+requestPacket.size], r14d
0x180015ba4  mov     rax, [rbx+14h]
0x180015ba8  mov     qword ptr [rsp+4C8h+requestPacket.adapterId.LowPart], rax
0x180015bb0  mov     eax, [rbx+8]
0x180015bb3  mov     [rsp+4C8h+requestPacket.id], eax
0x180015bba  lea     rcx, [rsp+4C8h+requestPacket]; requestPacket
0x180015bc2  call    cs:__imp_DisplayConfigGetDeviceInfo
0x180015bc8  test    eax, eax
0x180015bca  jnz     loc_180015DA1
0x180015bd0  xor     edx, edx; Val
0x180015bd2  mov     r8d, 344h; Size
0x180015bd8  lea     rcx, [rsp+4C8h+DisplayDevice.DeviceName]; void *
0x180015be0  call    memset_0
0x180015be5  mov     [rsp+4C8h+DisplayDevice.cb], 348h
0x180015bf0  xor     r9d, r9d; dwFlags
0x180015bf3  lea     r8, [rsp+4C8h+DisplayDevice]; lpDisplayDevice
0x180015bfb  xor     edx, edx; iDevNum
0x180015bfd  lea     rcx, [rsp+4C8h+Device]; lpDevice
0x180015c05  call    cs:__imp_EnumDisplayDevicesW
0x180015c0b  test    eax, eax
0x180015c0d  jz      loc_180015DA1
0x180015c13  lea     rdx, [rsp+4C8h+DisplayDevice.DeviceID]
0x180015c1b  lea     rcx, [rsp+4C8h+S1]
0x180015c23  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015c28  nop
0x180015c29  mov     rcx, [rsp+4C8h+S1]
0x180015c31  cmp     [rsp+4C8h+var_420], 7
0x180015c3a  jbe     short loc_180015C44
0x180015c3c  mov     r9, rcx
0x180015c3f  mov     rdx, rcx
0x180015c42  jmp     short loc_180015C54
0x180015c44  lea     r9, [rsp+4C8h+S1]
0x180015c4c  lea     rdx, [rsp+4C8h+S1]
0x180015c54  mov     rax, [rsp+4C8h+N]
0x180015c5c  lea     r8, [rdx+rax*2]
0x180015c60  lea     rdx, [rsp+4C8h+S1]
0x180015c68  cmova   rdx, rcx
0x180015c6c  mov     rax, cs:__imp_towupper
0x180015c73  mov     [rsp+4C8h+modeInfoArray], rax
0x180015c78  lea     rcx, [rsp+4C8h+var_460]
0x180015c7d  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x180015c82  lea     rdx, gszMonitorGUID; "{4D36E96E-E325-11CE-BFC1-08002BE10318}"
0x180015c89  lea     rcx, [rsp+4C8h+S1]
0x180015c91  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180015c96  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015c9a  jz      loc_180015D94
0x180015ca0  mov     r8, rax
0x180015ca3  lea     rdx, [rsp+4C8h+var_398]
0x180015cab  lea     rcx, [rsp+4C8h+S1]
0x180015cb3  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180015cb8  mov     rdx, rax
0x180015cbb  lea     rcx, [rsp+4C8h+S1]
0x180015cc3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180015cc8  lea     rcx, [rsp+4C8h+var_398]
0x180015cd0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015cd5  lea     rdx, [rsp+4C8h+S2]
0x180015cdd  cmp     [rsp+4C8h+var_400], 7
0x180015ce6  cmova   rdx, [rsp+4C8h+S2]; S2
0x180015cef  mov     r8, [rsp+4C8h+N]; N
0x180015cf7  lea     rcx, [rsp+4C8h+S1]
0x180015cff  cmp     [rsp+4C8h+var_420], 7
0x180015d08  cmova   rcx, [rsp+4C8h+S1]; S1
0x180015d11  cmp     r8, [rsp+4C8h+var_408]
0x180015d19  jnz     short loc_180015D94
0x180015d1b  test    r8, r8
0x180015d1e  jz      short loc_180015D29
0x180015d20  call    wmemcmp
0x180015d25  test    eax, eax
0x180015d27  jnz     short loc_180015D94
0x180015d29  movups  xmm0, xmmword ptr [rbx]
0x180015d2c  movaps  xmmword ptr [rsi], xmm0
0x180015d2f  movups  xmm1, xmmword ptr [rbx+10h]
0x180015d33  movaps  xmmword ptr [rsi+10h], xmm1
0x180015d37  movups  xmm0, xmmword ptr [rbx+20h]
0x180015d3b  movaps  xmmword ptr [rsi+20h], xmm0
0x180015d3f  movups  xmm1, xmmword ptr [rbx+30h]
0x180015d43  movaps  xmmword ptr [rsi+30h], xmm1
0x180015d47  movsd   xmm0, qword ptr [rbx+40h]
0x180015d4c  movsd   qword ptr [rsi+40h], xmm0
0x180015d51  lea     rcx, [rsp+4C8h+S1]
0x180015d59  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015d5e  nop
0x180015d5f  lea     rcx, [rsp+4C8h+var_490]
0x180015d64  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x180015d69  nop
0x180015d6a  lea     rcx, [rsp+4C8h+pathArray]
0x180015d6f  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x180015d74  nop
0x180015d75  lea     rcx, [rsp+4C8h+S2]
0x180015d7d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015d82  nop
  ... truncated ...
```
