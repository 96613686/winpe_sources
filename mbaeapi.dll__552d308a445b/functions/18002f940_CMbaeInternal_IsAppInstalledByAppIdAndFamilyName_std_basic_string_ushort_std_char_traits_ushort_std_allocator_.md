# CMbaeInternal::_IsAppInstalledByAppIdAndFamilyName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool &)

- ea: `0x18002f940`
- end: `0x18002fe7b`
- name: `?_IsAppInstalledByAppIdAndFamilyName@CMbaeInternal@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEA_N@Z`
- size: `1339`
- prototype: `__int64 __fastcall(__int64, _QWORD *, const WCHAR *, _BYTE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x18002e300`

## callees

- `0x1800024e0`
- `0x1800028b0`
- `0x180002930`
- `0x180002efc`
- `0x180009474`
- `0x1800143bc`
- `0x18001ae38`
- `0x18002ed18`
- `0x18002ed50`
- `0x18002f940`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x18002f9b3`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x18002faa8`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x18002f9b3`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x18002faa8`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18002fb7d`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18002fbe9`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18002fb7d`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18002fbe9`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x18002fb1f`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x18002fb1f`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18002fb60`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18002fcde`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18002fd2a`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18002fb60`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18002fcde`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18002fd2a`

## string_xrefs

- `0x18002fb29`: `Failed to do OpenPackageInfoByFullName`
- `0x18002fc88`: `CMbaeInternal::_IsAppInstalledByAppIdAndFamilyName`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMbaeInternal::_IsAppInstalledByAppIdAndFamilyName(
        __int64 a1,
        _QWORD *a2,
        const WCHAR *a3,
        _BYTE *a4)
{
  const WCHAR *v5; // rsi
  const WCHAR *v7; // rcx
  unsigned int PackagesByPackageFamily; // eax
  unsigned __int64 v9; // rdi
  void *v10; // rbx
  unsigned __int64 v11; // r14
  void *v12; // rdi
  unsigned int v13; // eax
  unsigned int v14; // esi
  UINT32 i; // r14d
  unsigned int v17; // eax
  unsigned int PackageApplicationIds; // eax
  size_t v19; // r15
  void *v20; // rsi
  void *v21; // rdx
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // eax
  __int64 v25; // r8
  char *v26; // rdx
  char *v27; // rcx
  signed __int64 v28; // rdx
  int v29; // eax
  int v30; // r9d
  int bufferLength; // [rsp+20h] [rbp-A8h]
  unsigned int bufferLengtha; // [rsp+20h] [rbp-A8h]
  WCHAR *buffer; // [rsp+28h] [rbp-A0h]
  WCHAR *buffera; // [rsp+28h] [rbp-A0h]
  UINT32 v35; // [rsp+40h] [rbp-88h] BYREF
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+48h] [rbp-80h] BYREF
  UINT32 count; // [rsp+50h] [rbp-78h] BYREF
  UINT32 v38; // [rsp+54h] [rbp-74h] BYREF
  UINT32 v39; // [rsp+58h] [rbp-70h] BYREF
  void *v40; // [rsp+60h] [rbp-68h]
  void *v41; // [rsp+68h] [rbp-60h]
  const char *v42; // [rsp+88h] [rbp-40h]
  __int64 v43; // [rsp+90h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v5 = a3;
  *a4 = 0;
  count = 0;
  v38 = 0;
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v7 = a3;
  else
    v7 = *(const WCHAR **)a3;
  PackagesByPackageFamily = FindPackagesByPackageFamily(v7, 0x30u, &count, 0, &v38, 0, 0);
  if ( PackagesByPackageFamily )
  {
    if ( PackagesByPackageFamily == 122 )
    {
      packageInfoReference = 0;
      if ( is_mul_ok(count, 2u) )
      {
        v9 = saturated_mul(2LL * count, (unsigned int)((count * (unsigned __int128)2u) >> 64) + 8);
        v10 = operator new[](v9);
        memset_0(v10, 0, v9);
        v40 = v10;
        if ( v10 )
        {
          packageInfoReference = 0;
          if ( is_mul_ok(v38, 2u) )
          {
            v11 = saturated_mul(2LL * v38, 2u);
            v12 = operator new[](v11);
            memset_0(v12, 0, v11);
            v41 = v12;
            if ( v12 )
            {
              if ( *((_QWORD *)v5 + 3) > 7u )
                v5 = *(const WCHAR **)v5;
              v13 = FindPackagesByPackageFamily(v5, 0x30u, &count, (PWSTR *)v10, &v38, (WCHAR *)v12, 0);
              if ( v13 )
              {
                v14 = wil::details::in1diag3::Return_Win32Msg(
                        retaddr,
                        (void *)0x3A3,
                        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
                        (const char *)v13,
                        (unsigned int)"Failed to do FindPackagesByPackageFamily",
                        (const char *)buffera);
                operator delete(v12);
                operator delete(v10);
                return v14;
              }
              else
              {
                for ( i = 0; ; ++i )
                {
                  if ( i >= count )
                    goto LABEL_50;
                  v39 = 0;
                  v35 = 0;
                  packageInfoReference = 0;
                  v17 = OpenPackageInfoByFullName(*((PCWSTR *)v10 + i), 0, &packageInfoReference);
                  if ( v17 )
                  {
                    wil::details::in1diag3::Log_Win32Msg(
                      retaddr,
                      (void *)0x3AF,
                      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
                      (const char *)v17,
                      (unsigned int)"Failed to do OpenPackageInfoByFullName",
                      (const char *)buffera);
                    goto LABEL_19;
                  }
                  PackageApplicationIds = GetPackageApplicationIds(packageInfoReference, &v39, 0, &v35);
                  if ( PackageApplicationIds != 122 )
                  {
                    wil::details::in1diag3::Log_Win32Msg(
                      retaddr,
                      (void *)0x3B5,
                      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
                      (const char *)PackageApplicationIds,
                      (unsigned int)"Failed to do GetPackageApplicationIds",
                      (const char *)buffera);
                    goto LABEL_19;
                  }
                  v19 = v39;
                  if ( !is_mul_ok(v39, 1u) )
                    break;
                  v20 = operator new[](v39);
                  memset_0(v20, 0, v19);
                  if ( !v20 )
                  {
                    wil::details::in1diag3::Log_Win32(retaddr, v21, v22, v23, bufferLengtha);
                    goto LABEL_19;
                  }
                  v24 = GetPackageApplicationIds(packageInfoReference, &v39, (BYTE *)v20, &v35);
                  if ( v24 )
                  {
                    wil::details::in1diag3::Log_Win32Msg(
                      retaddr,
                      (void *)0x3C4,
                      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
                      (const char *)v24,
                      (unsigned int)"Failed to do GetPackageApplicationIds",
                      (const char *)buffera);
                    goto LABEL_27;
                  }
                  if ( v35 )
                  {
                    v25 = 0;
                    while ( 1 )
                    {
                      v26 = a2[3] <= 7u ? (char *)a2 : (char *)*a2;
                      v27 = (char *)*((_QWORD *)v20 + (unsigned int)v25);
                      v28 = v26 - v27;
                      do
                      {
                        v29 = *(unsigned __int16 *)&v27[v28];
                        v30 = *(unsigned __int16 *)v27 - v29;
                        if ( v30 )
                          break;
                        v27 += 2;
                      }
                      while ( v29 );
                      if ( !v30 )
                        break;
                      v25 = (unsigned int)(v25 + 1);
                      if ( (unsigned int)v25 >= v35 )
                        goto LABEL_40;
                    }
                    *a4 = 1;
                  }
LABEL_40:
                  if ( *a4 == 1 )
                  {
                    if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 4) != 0 )
                    {
                      v42 = "CMbaeInternal::_IsAppInstalledByAppIdAndFamilyName";
                      v43 = 51;
                      McGenEventWrite_EventWriteTransfer(&CtlGuid_Context, CMbaeInternal_cpp980, v25, 2);
                    }
LABEL_27:
                    operator delete(v20);
LABEL_19:
                    if ( packageInfoReference )
                      ClosePackageInfo(packageInfoReference);
LABEL_50:
                    operator delete(v12);
                    operator delete(v10);
                    return 0;
                  }
                  operator delete(v20);
                  if ( packageInfoReference )
                    ClosePackageInfo(packageInfoReference);
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x3B9,
                  (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
                  (const char *)0x80070216LL,
                  bufferLengtha);
                if ( packageInfoReference )
                  ClosePackageInfo(packageInfoReference);
                operator delete(v12);
                operator delete(v10);
                return 2147942934LL;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x39E,
                (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
                (const char *)0x8007000ELL,
                bufferLength);
              operator delete(v10);
              return 2147942414LL;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x39C,
              (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
              (const char *)0x80070216LL,
              bufferLength);
            operator delete(v10);
            return 2147942934LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x39A,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
            (const char *)0x8007000ELL,
            bufferLength);
          return 2147942414LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x398,
          (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
          (const char *)0x80070216LL,
          bufferLength);
        return 2147942934LL;
      }
    }
    else
    {
      return wil::details::in1diag3::Return_Win32Msg(
               retaddr,
               (void *)0x3DB,
               (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
               (const char *)PackagesByPackageFamily,
               (unsigned int)"Failed to do FindPackagesByPackageFamily",
               (const char *)buffer);
    }
  }
  else
  {
    *a4 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x18002f940  mov     r11, rsp
0x18002f943  mov     [r11+8], rbx
0x18002f947  mov     [r11+10h], rsi
0x18002f94b  push    rdi
0x18002f94c  push    r12
0x18002f94e  push    r13
0x18002f950  push    r14
0x18002f952  push    r15
0x18002f954  sub     rsp, 0A0h
0x18002f95b  mov     rax, cs:__security_cookie
0x18002f962  xor     rax, rsp
0x18002f965  mov     [rsp+0C8h+var_30], rax
0x18002f96d  mov     r12, r9
0x18002f970  mov     rsi, r8
0x18002f973  mov     r13, rdx
0x18002f976  xor     r15d, r15d
0x18002f979  mov     [r9], r15b
0x18002f97c  mov     [r11-78h], r15d
0x18002f980  mov     [r11-74h], r15d
0x18002f984  cmp     qword ptr [r8+18h], 7
0x18002f989  jbe     short loc_18002F990
0x18002f98b  mov     rcx, [r8]
0x18002f98e  jmp     short loc_18002F993
0x18002f990  mov     rcx, rsi; packageFamilyName
0x18002f993  mov     [rsp+0C8h+packageProperties], r15; packageProperties
0x18002f998  mov     [rsp+0C8h+buffer], r15; char *
0x18002f99d  lea     rax, [rsp+0C8h+var_74]
0x18002f9a2  mov     [rsp+0C8h+bufferLength], rax; int
0x18002f9a7  xor     r9d, r9d; packageFullNames
0x18002f9aa  lea     r8, [rsp+0C8h+count]; count
0x18002f9af  lea     edx, [r9+30h]; packageFilters
0x18002f9b3  call    cs:__imp_FindPackagesByPackageFamily
0x18002f9b9  test    eax, eax
0x18002f9bb  jnz     short loc_18002F9C6
0x18002f9bd  mov     [r12], r15b
0x18002f9c1  jmp     loc_18002FD6E
0x18002f9c6  cmp     eax, 7Ah ; 'z'
0x18002f9c9  jnz     loc_18002FE1F
0x18002f9cf  mov     [rsp+0C8h+packageInfoReference], r15
0x18002f9d4  mov     ecx, [rsp+0C8h+count]
0x18002f9d8  lea     r14d, [rax-78h]
0x18002f9dc  mov     eax, r14d
0x18002f9df  mul     rcx
0x18002f9e2  mov     rcx, rax
0x18002f9e5  test    rdx, rdx
0x18002f9e8  jnz     loc_18002FDFA
0x18002f9ee  lea     eax, [rdx+8]
0x18002f9f1  mul     rcx
0x18002f9f4  mov     rdi, rax
0x18002f9f7  lea     rax, [r14-3]
0x18002f9fb  cmovb   rdi, rax
0x18002f9ff  mov     rcx, rdi; unsigned __int64
0x18002fa02  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002fa07  mov     rbx, rax
0x18002fa0a  mov     r8, rdi; Size
0x18002fa0d  xor     edx, edx; Val
0x18002fa0f  mov     rcx, rax; void *
0x18002fa12  call    memset_0
0x18002fa17  mov     [rsp+0C8h+var_68], rbx
0x18002fa1c  test    rbx, rbx
0x18002fa1f  jz      loc_18002FDD4
0x18002fa25  mov     [rsp+0C8h+packageInfoReference], r15
0x18002fa2a  mov     ecx, [rsp+0C8h+var_74]
0x18002fa2e  mov     eax, r14d
0x18002fa31  mul     rcx
0x18002fa34  mov     rcx, rax
0x18002fa37  test    rdx, rdx
0x18002fa3a  jnz     loc_18002FDA6
0x18002fa40  mov     eax, r14d
0x18002fa43  mul     rcx
0x18002fa46  mov     r14, rax
0x18002fa49  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002fa50  cmovb   r14, rax
0x18002fa54  mov     rcx, r14; unsigned __int64
0x18002fa57  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002fa5c  mov     rdi, rax
0x18002fa5f  mov     r8, r14; Size
0x18002fa62  xor     edx, edx; Val
0x18002fa64  mov     rcx, rax; void *
0x18002fa67  call    memset_0
0x18002fa6c  mov     [rsp+0C8h+var_60], rdi
0x18002fa71  test    rdi, rdi
0x18002fa74  jz      loc_18002FD75
0x18002fa7a  cmp     qword ptr [rsi+18h], 7
0x18002fa7f  jbe     short loc_18002FA84
0x18002fa81  mov     rsi, [rsi]
0x18002fa84  mov     [rsp+0C8h+packageProperties], r15; packageProperties
0x18002fa89  mov     [rsp+0C8h+buffer], rdi; char *
0x18002fa8e  lea     rax, [rsp+0C8h+var_74]
0x18002fa93  mov     [rsp+0C8h+bufferLength], rax; int
0x18002fa98  mov     r9, rbx; packageFullNames
0x18002fa9b  lea     r8, [rsp+0C8h+count]; count
0x18002faa0  mov     edx, 30h ; '0'; packageFilters
0x18002faa5  mov     rcx, rsi; packageFamilyName
0x18002faa8  call    cs:__imp_FindPackagesByPackageFamily
0x18002faae  test    eax, eax
0x18002fab0  jz      short loc_18002FAF4
0x18002fab2  mov     rcx, [rsp+0C8h]; this
0x18002faba  lea     rdx, aFailedToDoFind; "Failed to do FindPackagesByPackageFamil"...
0x18002fac1  mov     [rsp+0C8h+bufferLength], rdx; unsigned int
0x18002fac6  mov     r9d, eax; char *
0x18002fac9  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18002fad0  mov     edx, 3A3h; void *
0x18002fad5  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002fada  mov     esi, eax
0x18002fadc  mov     rcx, rdi; Block
0x18002fadf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fae4  nop
0x18002fae5  mov     rcx, rbx; Block
0x18002fae8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002faed  mov     eax, esi
0x18002faef  jmp     loc_18002FE4D
0x18002faf4  mov     r14d, r15d
0x18002faf7  cmp     r14d, [rsp+0C8h+count]
0x18002fafc  jnb     loc_18002FD53
0x18002fb02  mov     [rsp+0C8h+var_70], r15d
0x18002fb07  mov     [rsp+0C8h+var_88], r15d
0x18002fb0c  mov     [rsp+0C8h+packageInfoReference], r15
0x18002fb11  mov     ecx, r14d
0x18002fb14  lea     r8, [rsp+0C8h+packageInfoReference]; packageInfoReference
0x18002fb19  xor     edx, edx; reserved
0x18002fb1b  mov     rcx, [rbx+rcx*8]; packageFullName
0x18002fb1f  call    cs:__imp_OpenPackageInfoByFullName
0x18002fb25  test    eax, eax
0x18002fb27  jz      short loc_18002FB6B
0x18002fb29  lea     rdx, aFailedToDoOpen; "Failed to do OpenPackageInfoByFullName"
0x18002fb30  mov     [rsp+0C8h+bufferLength], rdx; unsigned int
0x18002fb35  mov     edx, 3AFh; void *
0x18002fb3a  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18002fb41  mov     r9d, eax; char *
0x18002fb44  mov     rcx, [rsp+0C8h]; this
0x18002fb4c  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002fb51  nop
0x18002fb52  mov     rcx, [rsp+0C8h+packageInfoReference]; packageInfoReference
0x18002fb57  test    rcx, rcx
0x18002fb5a  jz      loc_18002FD53
0x18002fb60  call    cs:__imp_ClosePackageInfo
0x18002fb66  jmp     loc_18002FD53
0x18002fb6b  lea     r9, [rsp+0C8h+var_88]; count
0x18002fb70  xor     r8d, r8d; buffer
0x18002fb73  lea     rdx, [rsp+0C8h+var_70]; bufferLength
0x18002fb78  mov     rcx, [rsp+0C8h+packageInfoReference]; packageInfoReference
0x18002fb7d  call    cs:__imp_GetPackageApplicationIds
0x18002fb83  cmp     eax, 7Ah ; 'z'
0x18002fb86  jz      short loc_18002FB9B
0x18002fb88  lea     rdx, aFailedToDoGetp; "Failed to do GetPackageApplicationIds"
0x18002fb8f  mov     [rsp+0C8h+bufferLength], rdx
0x18002fb94  mov     edx, 3B5h
0x18002fb99  jmp     short loc_18002FB3A
0x18002fb9b  mov     ecx, [rsp+0C8h+var_70]
0x18002fb9f  mov     eax, 1
0x18002fba4  mul     rcx
0x18002fba7  mov     r15, rax
0x18002fbaa  test    rdx, rdx
0x18002fbad  jnz     loc_18002FCFE
0x18002fbb3  mov     rcx, rax; unsigned __int64
0x18002fbb6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002fbbb  mov     rsi, rax
0x18002fbbe  mov     r8, r15; Size
0x18002fbc1  xor     edx, edx; Val
0x18002fbc3  mov     rcx, rax; void *
0x18002fbc6  call    memset_0
0x18002fbcb  xor     r15d, r15d
0x18002fbce  test    rsi, rsi
0x18002fbd1  jz      loc_18002FCEC
0x18002fbd7  lea     r9, [rsp+0C8h+var_88]; count
0x18002fbdc  mov     r8, rsi; buffer
0x18002fbdf  lea     rdx, [rsp+0C8h+var_70]; bufferLength
0x18002fbe4  mov     rcx, [rsp+0C8h+packageInfoReference]; packageInfoReference
0x18002fbe9  call    cs:__imp_GetPackageApplicationIds
0x18002fbef  test    eax, eax
0x18002fbf1  jz      short loc_18002FC28
0x18002fbf3  mov     rcx, [rsp+0C8h]; this
0x18002fbfb  lea     rdx, aFailedToDoGetp; "Failed to do GetPackageApplicationIds"
0x18002fc02  mov     [rsp+0C8h+bufferLength], rdx; unsigned int
0x18002fc07  mov     r9d, eax; char *
0x18002fc0a  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18002fc11  mov     edx, 3C4h; void *
0x18002fc16  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002fc1b  mov     rcx, rsi; Block
0x18002fc1e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fc23  jmp     loc_18002FB52
0x18002fc28  mov     r10d, [rsp+0C8h+var_88]
0x18002fc2d  test    r10d, r10d
0x18002fc30  jz      short loc_18002FC78
0x18002fc32  mov     r8d, r15d
0x18002fc35  cmp     qword ptr [r13+18h], 7
0x18002fc3a  jbe     short loc_18002FC42
0x18002fc3c  mov     rdx, [r13+0]
0x18002fc40  jmp     short loc_18002FC45
0x18002fc42  mov     rdx, r13
0x18002fc45  mov     eax, r8d
0x18002fc48  mov     rcx, [rsi+rax*8]
0x18002fc4c  sub     rdx, rcx
0x18002fc4f  movzx   r9d, word ptr [rcx]
0x18002fc53  movzx   eax, word ptr [rcx+rdx]
0x18002fc57  sub     r9d, eax
0x18002fc5a  jnz     short loc_18002FC64
0x18002fc5c  add     rcx, 2
0x18002fc60  test    eax, eax
0x18002fc62  jnz     short loc_18002FC4F
0x18002fc64  test    r9d, r9d
0x18002fc67  jz      short loc_18002FC73
0x18002fc69  inc     r8d
0x18002fc6c  cmp     r8d, r10d
0x18002fc6f  jb      short loc_18002FC35
0x18002fc71  jmp     short loc_18002FC78
0x18002fc73  mov     byte ptr [r12], 1
0x18002fc78  cmp     byte ptr [r12], 1
0x18002fc7d  jnz     short loc_18002FCCB
0x18002fc7f  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 4
0x18002fc86  jz      short loc_18002FC1B
0x18002fc88  lea     rax, aCmbaeinternalI; "CMbaeInternal::_IsAppInstalledByAppIdAn"...
0x18002fc8f  mov     [rsp+0C8h+var_40], rax
0x18002fc97  mov     [rsp+0C8h+var_38], 33h ; '3'
0x18002fca3  lea     rax, [rsp+0C8h+var_50]
0x18002fca8  mov     [rsp+0C8h+bufferLength], rax
0x18002fcad  mov     r9d, 2
0x18002fcb3  lea     rdx, CMbaeInternal_cpp980
0x18002fcba  lea     rcx, CtlGuid_Context
0x18002fcc1  call    McGenEventWrite_EventWriteTransfer
0x18002fcc6  jmp     loc_18002FC1B
0x18002fccb  mov     rcx, rsi; Block
0x18002fcce  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fcd3  nop
0x18002fcd4  mov     rcx, [rsp+0C8h+packageInfoReference]; packageInfoReference
0x18002fcd9  test    rcx, rcx
0x18002fcdc  jz      short loc_18002FCE4
0x18002fcde  call    cs:__imp_ClosePackageInfo
0x18002fce4  inc     r14d
0x18002fce7  jmp     loc_18002FAF7
0x18002fcec  mov     rcx, [rsp+0C8h]; this
0x18002fcf4  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18002fcf9  jmp     loc_18002FB52
0x18002fcfe  mov     rcx, [rsp+0C8h]; this
0x18002fd06  mov     esi, 80070216h
0x18002fd0b  mov     r9d, esi; char *
0x18002fd0e  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18002fd15  mov     edx, 3B9h; void *
0x18002fd1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fd1f  nop
0x18002fd20  mov     rcx, [rsp+0C8h+packageInfoReference]; packageInfoReference
0x18002fd25  test    rcx, rcx
0x18002fd28  jz      short loc_18002FD31
0x18002fd2a  call    cs:__imp_ClosePackageInfo
0x18002fd30  nop
0x18002fd31  test    rdi, rdi
0x18002fd34  jz      short loc_18002FD3F
0x18002fd36  mov     rcx, rdi; Block
0x18002fd39  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fd3e  nop
0x18002fd3f  test    rbx, rbx
0x18002fd42  jz      short loc_18002FD4C
0x18002fd44  mov     rcx, rbx; Block
0x18002fd47  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fd4c  mov     eax, esi
0x18002fd4e  jmp     loc_18002FE4D
0x18002fd53  test    rdi, rdi
0x18002fd56  jz      short loc_18002FD61
0x18002fd58  mov     rcx, rdi; Block
0x18002fd5b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fd60  nop
0x18002fd61  test    rbx, rbx
0x18002fd64  jz      short loc_18002FD6E
0x18002fd66  mov     rcx, rbx; Block
0x18002fd69  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fd6e  xor     eax, eax
0x18002fd70  jmp     loc_18002FE4D
0x18002fd75  mov     rcx, [rsp+0C8h]; this
0x18002fd7d  mov     edi, 8007000Eh
0x18002fd82  mov     r9d, edi; char *
0x18002fd85  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18002fd8c  mov     edx, 39Eh; void *
0x18002fd91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fd96  nop
0x18002fd97  mov     rcx, rbx; Block
0x18002fd9a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fd9f  mov     eax, edi
0x18002fda1  jmp     loc_18002FE4D
0x18002fda6  mov     rcx, [rsp+0C8h]; this
0x18002fdae  mov     esi, 80070216h
0x18002fdb3  mov     r9d, esi; char *
0x18002fdb6  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18002fdbd  mov     edx, 39Ch; void *
0x18002fdc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fdc7  nop
0x18002fdc8  mov     rcx, rbx; Block
0x18002fdcb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fdd0  mov     eax, esi
0x18002fdd2  jmp     short loc_18002FE4D
0x18002fdd4  mov     rcx, [rsp+0C8h]; this
0x18002fddc  mov     edi, 8007000Eh
0x18002fde1  mov     r9d, edi; char *
0x18002fde4  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18002fdeb  mov     edx, 39Ah; void *
0x18002fdf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fdf5  nop
0x18002fdf6  mov     eax, edi
0x18002fdf8  jmp     short loc_18002FE4D
0x18002fdfa  mov     rcx, [rsp+0C8h]; this
  ... truncated ...
```
