# GetWlanInterfaceProfileList(std::vector<std::pair<_GUID,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<_GUID,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x180030018`
- end: `0x18003036b`
- name: `?GetWlanInterfaceProfileList@@YAXAEAV?$vector@U?$pair@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$allocator@U?$pair@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@@Z`
- size: `851`
- prototype: `void __fastcall(std::vector<std::pair<_GUID,std::wstring >> *ProfileInterfaceList)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180030380`

## callees

- `0x180002790`
- `0x18000af94`
- `0x180011cfc`
- `0x180012748`
- `0x180012770`
- `0x18001282c`
- `0x180012bc8`
- `0x180017300`
- `0x18002f860`
- `0x180030018`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x1800300a0`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x1800300a0`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x1800300fd`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x1800300fd`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003013e`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180030209`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileList` at `0x1800301bc`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileList` at `0x1800301bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall GetWlanInterfaceProfileList(std::vector<std::pair<_GUID,std::wstring >> *ProfileInterfaceList)
{
  DWORD v2; // eax
  DWORD v3; // eax
  WWAN_INTERFACE_OBJECT *v4; // rbx
  unsigned int v5; // edi
  __m128i si128; // xmm6
  __int64 v7; // rsi
  char *v8; // r15
  DWORD _a2; // eax
  _WLAN_INTERFACE_INFO_LIST *v10; // rdx
  unsigned int i; // ebx
  const wchar_t *v12; // rsi
  _GUID v13; // xmm1
  __int64 v14; // rax
  wchar_t *v15; // r8
  __int64 v16; // rcx
  unsigned __int64 v17; // r9
  unsigned __int64 v18; // r10
  std::pair<_GUID,std::wstring > *Mylast; // rdx
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> v20; // [rsp+38h] [rbp-99h] BYREF
  std::pair<_GUID,std::wstring > v21; // [rsp+50h] [rbp-81h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+80h] [rbp-51h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> v23; // [rsp+98h] [rbp-39h] BYREF
  std::wstring v24; // [rsp+B0h] [rbp-21h] BYREF
  _WLAN_PROFILE_INFO_LIST *pProfileList; // [rsp+D0h] [rbp-1h] BYREF
  _WLAN_INTERFACE_INFO_LIST *pInterfaceList; // [rsp+D8h] [rbp+7h] BYREF
  WWAN_INTERFACE_OBJECT *dwVersion; // [rsp+E0h] [rbp+Fh] BYREF
  unsigned int pdwNegotiatedVersion; // [rsp+E8h] [rbp+17h] BYREF

  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xAu, WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids);
  }
  pProfileList = 0;
  pdwNegotiatedVersion = 0;
  dwVersion = 0;
  v2 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, (PHANDLE)&pProfileList);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xBu, WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids, v2);
    }
  }
  else
  {
    v20.dismissed_ = 0;
    v20.fun_ = (void (__fastcall *)(void *))WlanCloseHandleWrapper;
    v20.p1_ = (WWAN_INTERFACE_OBJECT *const)pProfileList;
    v3 = WlanEnumInterfaces(pProfileList, 0, (PWLAN_INTERFACE_INFO_LIST *)&dwVersion);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xCu, WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids, v3);
      }
    }
    else
    {
      v4 = dwVersion;
      v23.dismissed_ = 0;
      v23.fun_ = (void (__fastcall *)(void *))WlanFreeMemory;
      v23.p1_ = dwVersion;
      if ( dwVersion->size )
      {
        v5 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        do
        {
          v7 = 532LL * v5;
          v8 = (char *)v4 + v7;
          pInterfaceList = 0;
          _a2 = WlanGetProfileList(
                  pProfileList,
                  (const GUID *)((char *)&v4->InterfaceGuid + v7),
                  0,
                  (PWLAN_PROFILE_INFO_LIST *)&pInterfaceList);
          if ( _a2 )
          {
            if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control->Control.Logger,
                0xEu,
                WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids,
                &v4->strInterfaceDescription[(unsigned __int64)v7 / 2],
                _a2);
            }
          }
          else
          {
            v10 = pInterfaceList;
            j.dismissed_ = 0;
            j.fun_ = (void (__fastcall *)(void *))WlanFreeMemory;
            j.p1_ = (WWAN_INTERFACE_OBJECT *const)pInterfaceList;
            for ( i = 0; i < pInterfaceList->dwNumberOfItems; v10 = pInterfaceList )
            {
              v12 = (const wchar_t *)((char *)v10->InterfaceInfo + 516 * i);
              if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
              {
                WPP_SF__guid_S(
                  WPP_GLOBAL_Control->Control.Logger,
                  0xFu,
                  WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids,
                  (const _GUID *)(v8 + 8),
                  v12);
              }
              std::wstring::wstring(&v24, v12);
              v13 = *(_GUID *)(v8 + 8);
              v21.first = v13;
              v21.second._Mypair._Myval2._Bx = 0;
              v15 = *(wchar_t **)v14;
              v21.second._Mypair._Myval2._Bx._Ptr = *(wchar_t **)v14;
              v16 = *(_QWORD *)(v14 + 8);
              *(_QWORD *)&v21.second._Mypair._Myval2._Bx._Alias[8] = v16;
              v17 = *(_QWORD *)(v14 + 16);
              v21.second._Mypair._Myval2._Mysize = v17;
              v18 = *(_QWORD *)(v14 + 24);
              v21.second._Mypair._Myval2._Myres = v18;
              *(_WORD *)v14 = 0;
              *(_QWORD *)(v14 + 16) = 0;
              *(_QWORD *)(v14 + 24) = 7;
              Mylast = ProfileInterfaceList->_Mypair._Myval2._Mylast;
              if ( Mylast == ProfileInterfaceList->_Mypair._Myval2._Myend )
              {
                std::vector<std::pair<_GUID,std::wstring>>::_Emplace_reallocate<std::pair<_GUID,std::wstring>>(
                  ProfileInterfaceList,
                  Mylast,
                  &v21);
              }
              else
              {
                Mylast->first = v13;
                Mylast->second._Mypair._Myval2._Bx._Ptr = v15;
                *(_QWORD *)&Mylast->second._Mypair._Myval2._Bx._Alias[8] = v16;
                Mylast->second._Mypair._Myval2._Mysize = v17;
                Mylast->second._Mypair._Myval2._Myres = v18;
                *(__m128i *)&v21.second._Mypair._Myval2._Mysize = si128;
                v21.second._Mypair._Myval2._Bx._Buf[0] = 0;
                ++ProfileInterfaceList->_Mypair._Myval2._Mylast;
              }
              std::wstring::_Tidy_deallocate(&v21.second);
              std::wstring::_Tidy_deallocate(&v24);
              ++i;
            }
            ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
          }
          ++v5;
          v4 = dwVersion;
        }
        while ( v5 < dwVersion->size );
      }
      else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
             && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xDu, WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids);
      }
      ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&v23);
    }
    ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&v20);
  }
}

```

## disassembly

```asm
0x180030018  mov     rax, rsp
0x18003001b  mov     [rax+10h], rbx
0x18003001f  mov     [rax+18h], rsi
0x180030023  push    rbp
0x180030024  push    rdi
0x180030025  push    r13
0x180030027  push    r14
0x180030029  push    r15
0x18003002b  lea     rbp, [rax-5Fh]
0x18003002f  sub     rsp, 100h
0x180030036  movaps  xmmword ptr [rax-38h], xmm6
0x18003003a  mov     rax, cs:__security_cookie
0x180030041  xor     rax, rsp
0x180030044  mov     [rbp+57h+var_38], rax
0x180030048  mov     r14, ProfileInterfaceList
0x18003004b  lea     r13, WPP_GLOBAL_Control; __annotation("TMF:",
0x180030052  lea     rdi, WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids
0x180030059  mov     ProfileInterfaceList, cs:WPP_GLOBAL_Control
0x180030060  cmp     ProfileInterfaceList, r13
0x180030063  jz      short loc_18003007C
0x180030065  test    byte ptr [ProfileInterfaceList+1Ch], 10h
0x180030069  jz      short loc_18003007C
0x18003006b  mov     edx, 0Ah; id
0x180030070  mov     r8, rdi; TraceGuid
0x180030073  mov     ProfileInterfaceList, [ProfileInterfaceList+10h]; Logger
0x180030077  call    WPP_SF_
0x18003007c  mov     [rbp+57h+pProfileList], 0
0x180030084  mov     [rbp+57h+pdwNegotiatedVersion], 0
0x18003008b  mov     [rbp+57h+dwVersion], 0
0x180030093  lea     r9, [rbp+57h+pProfileList]; phClientHandle
0x180030097  lea     r8, [rbp+57h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18003009b  xor     edx, edx; pReserved
0x18003009d  lea     ecx, [rdx+2]; dwClientVersion
0x1800300a0  call    cs:__imp_WlanOpenHandle
0x1800300a6  test    eax, eax
0x1800300a8  jz      short loc_1800300DD
0x1800300aa  mov     ProfileInterfaceList, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800300b1  cmp     ProfileInterfaceList, r13
0x1800300b4  jz      loc_18003033E
0x1800300ba  test    byte ptr [ProfileInterfaceList+1Ch], 4
0x1800300be  jz      loc_18003033E
0x1800300c4  mov     edx, 0Bh; id
0x1800300c9  mov     r9d, eax; _a1
0x1800300cc  mov     r8, rdi; TraceGuid
0x1800300cf  mov     ProfileInterfaceList, [ProfileInterfaceList+10h]; Logger
0x1800300d3  call    WPP_SF_d
0x1800300d8  jmp     loc_18003033E
0x1800300dd  mov     ProfileInterfaceList, [rbp+57h+pProfileList]; hClientHandle
0x1800300e1  mov     [rsp+120h+var_F0.dismissed_], 0
0x1800300e6  lea     rax, ?WlanCloseHandleWrapper@@YAKPEAX@Z; WlanCloseHandleWrapper(void *)
0x1800300ed  mov     [rsp+120h+var_F0.fun_], rax
0x1800300f2  mov     [rsp+120h+var_F0.p1_], ProfileInterfaceList
0x1800300f7  lea     r8, [rbp+57h+dwVersion]; ppInterfaceList
0x1800300fb  xor     edx, edx; pReserved
0x1800300fd  call    cs:__imp_WlanEnumInterfaces
0x180030103  test    eax, eax
0x180030105  jz      short loc_18003013A
0x180030107  mov     ProfileInterfaceList, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003010e  cmp     ProfileInterfaceList, r13
0x180030111  jz      loc_180030334
0x180030117  test    byte ptr [ProfileInterfaceList+1Ch], 4
0x18003011b  jz      loc_180030334
0x180030121  mov     edx, 0Ch; id
0x180030126  mov     r9d, eax; _a1
0x180030129  mov     r8, rdi; TraceGuid
0x18003012c  mov     ProfileInterfaceList, [ProfileInterfaceList+10h]; Logger
0x180030130  call    WPP_SF_d
0x180030135  jmp     loc_180030334
0x18003013a  mov     rbx, [rbp+57h+dwVersion]
0x18003013e  mov     rax, cs:__imp_WlanFreeMemory
0x180030145  mov     [rbp+57h+var_90.dismissed_], 0
0x180030149  mov     [rbp+57h+var_90.fun_], rax
0x18003014d  mov     [rbp+57h+var_90.p1_], rbx
0x180030151  cmp     dword ptr [rbx], 0
0x180030154  jnz     short loc_180030186
0x180030156  mov     ProfileInterfaceList, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003015d  cmp     ProfileInterfaceList, r13
0x180030160  jz      loc_18003032A
0x180030166  test    byte ptr [ProfileInterfaceList+1Ch], 4
0x18003016a  jz      loc_18003032A
0x180030170  mov     edx, 0Dh; id
0x180030175  mov     r8, rdi; TraceGuid
0x180030178  mov     ProfileInterfaceList, [ProfileInterfaceList+10h]; Logger
0x18003017c  call    WPP_SF_
0x180030181  jmp     loc_18003032A
0x180030186  xor     edi, edi
0x180030188  cmp     [rbx], edi
0x18003018a  jbe     loc_18003032A
0x180030190  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180030198  mov     eax, edi
0x18003019a  imul    rsi, rax, 214h
0x1800301a1  lea     r15, [rsi+rbx]
0x1800301a5  mov     [rbp+57h+pInterfaceList], 0
0x1800301ad  lea     r9, [rbp+57h+pInterfaceList]; ppProfileList
0x1800301b1  xor     r8d, r8d; pReserved
0x1800301b4  lea     rdx, [r15+8]; pInterfaceGuid
0x1800301b8  mov     ProfileInterfaceList, [rbp+57h+pProfileList]; hClientHandle
0x1800301bc  call    cs:__imp_WlanGetProfileList
0x1800301c2  test    eax, eax
0x1800301c4  jz      short loc_180030205
0x1800301c6  mov     ProfileInterfaceList, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800301cd  cmp     ProfileInterfaceList, r13
0x1800301d0  jz      loc_18003031C
0x1800301d6  test    byte ptr [ProfileInterfaceList+1Ch], 8
0x1800301da  jz      loc_18003031C
0x1800301e0  lea     r9, [rbx+18h]
0x1800301e4  add     r9, rsi; _a1
0x1800301e7  mov     edx, 0Eh; id
0x1800301ec  mov     [rsp+120h+_a2], eax; _a2
0x1800301f0  lea     r8, WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids; TraceGuid
0x1800301f7  mov     ProfileInterfaceList, [ProfileInterfaceList+10h]; Logger
0x1800301fb  call    WPP_SF_Sd
0x180030200  jmp     loc_18003031C
0x180030205  mov     rdx, [rbp+57h+pInterfaceList]
0x180030209  mov     rax, cs:__imp_WlanFreeMemory
0x180030210  mov     [rbp+57h+j.dismissed_], 0
0x180030214  mov     [rbp+57h+j.fun_], rax
0x180030218  mov     [rbp+57h+j.p1_], rdx
0x18003021c  xor     ebx, ebx
0x18003021e  cmp     [rdx], ebx
0x180030220  jbe     loc_180030313
0x180030226  mov     eax, ebx
0x180030228  imul    rsi, rax, 204h
0x18003022f  add     rsi, 8
0x180030233  add     rsi, rdx
0x180030236  mov     ProfileInterfaceList, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003023d  cmp     ProfileInterfaceList, r13
0x180030240  jz      short loc_180030266
0x180030242  test    byte ptr [ProfileInterfaceList+1Ch], 8
0x180030246  jz      short loc_180030266
0x180030248  mov     edx, 0Fh; id
0x18003024d  mov     qword ptr [rsp+120h+_a2], rsi; _a2
0x180030252  lea     r9, [r15+8]; _a1
0x180030256  lea     r8, WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids; TraceGuid
0x18003025d  mov     ProfileInterfaceList, [ProfileInterfaceList+10h]; Logger
0x180030261  call    WPP_SF__guid_S
0x180030266  mov     rdx, rsi; _Ptr
0x180030269  lea     ProfileInterfaceList, [rbp+57h+var_78]; this
0x18003026d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180030272  mov     rdx, rax
0x180030275  movups  xmm1, xmmword ptr [r15+8]
0x18003027a  movups  xmmword ptr [rsp+120h+var_D8], xmm1
0x18003027f  xorps   xmm0, xmm0
0x180030282  movups  xmmword ptr [rbp+57h+var_D8+10h], xmm0
0x180030286  mov     r8, [rax]
0x180030289  mov     qword ptr [rbp+57h+var_D8+10h], r8
0x18003028d  mov     ProfileInterfaceList, [rax+8]
0x180030291  mov     qword ptr [rbp+57h+var_D8+18h], ProfileInterfaceList
0x180030295  mov     r9, [rax+10h]
0x180030299  mov     qword ptr [rbp+57h+var_D8+20h], r9
0x18003029d  mov     r10, [rax+18h]
0x1800302a1  mov     qword ptr [rbp+57h+var_D8+28h], r10
0x1800302a5  xor     eax, eax
0x1800302a7  mov     [rdx], ax
0x1800302aa  mov     [rdx+10h], rax
0x1800302ae  mov     qword ptr [rdx+18h], 7
0x1800302b6  mov     rdx, [r14+8]; _Whereptr
0x1800302ba  cmp     rdx, [r14+10h]
0x1800302be  jz      short loc_1800302E4
0x1800302c0  movdqu  xmmword ptr [rdx], xmm1
0x1800302c4  mov     [rdx+10h], r8
0x1800302c8  mov     [rdx+18h], ProfileInterfaceList
0x1800302cc  mov     [rdx+20h], r9
0x1800302d0  mov     [rdx+28h], r10
0x1800302d4  movdqu  xmmword ptr [rbp+57h+var_D8+20h], xmm6
0x1800302d9  mov     word ptr [rbp+57h+var_D8+10h], ax
0x1800302dd  add     qword ptr [r14+8], 30h ; '0'
0x1800302e2  jmp     short loc_1800302F2
0x1800302e4  lea     r8, [rsp+120h+var_D8]; <_Val_0>
0x1800302e9  mov     ProfileInterfaceList, r14; this
0x1800302ec  call    ??$_Emplace_reallocate@U?$pair@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@?$vector@U?$pair@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$allocator@U?$pair@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@AEAAPEAU?$pair@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<_GUID,std::wstring>>::_Emplace_reallocate<std::pair<_GUID,std::wstring>>(std::pair<_GUID,std::wstring> * const,std::pair<_GUID,std::wstring> &&)
0x1800302f1  nop
0x1800302f2  lea     ProfileInterfaceList, [rbp+57h+var_D8+10h]; this
0x1800302f6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800302fb  nop
0x1800302fc  lea     ProfileInterfaceList, [rbp+57h+var_78]; this
0x180030300  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030305  inc     ebx
0x180030307  mov     rdx, [rbp+57h+pInterfaceList]
0x18003030b  cmp     ebx, [rdx]
0x18003030d  jb      loc_180030226
0x180030313  lea     ProfileInterfaceList, [rbp+57h+j]; j
0x180030317  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x18003031c  inc     edi
0x18003031e  mov     rbx, [rbp+57h+dwVersion]
0x180030322  cmp     edi, [rbx]
0x180030324  jb      loc_180030198
0x18003032a  lea     ProfileInterfaceList, [rbp+57h+var_90]; j
0x18003032e  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x180030333  nop
0x180030334  lea     ProfileInterfaceList, [rsp+120h+var_F0]; j
0x180030339  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x18003033e  mov     ProfileInterfaceList, [rbp+57h+var_38]
0x180030342  xor     ProfileInterfaceList, rsp; StackCookie
0x180030345  call    __security_check_cookie
0x18003034a  lea     r11, [rsp+120h+var_20]
0x180030352  mov     rbx, [r11+38h]
0x180030356  mov     rsi, [r11+40h]
0x18003035a  movaps  xmm6, xmmword ptr [r11-10h]
0x18003035f  mov     rsp, r11
0x180030362  pop     r15
0x180030364  pop     r14
0x180030366  pop     r13
0x180030368  pop     rdi
0x180030369  pop     rbp
0x18003036a  retn
```
