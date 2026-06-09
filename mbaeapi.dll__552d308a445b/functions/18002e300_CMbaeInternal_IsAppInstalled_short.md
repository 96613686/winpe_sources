# CMbaeInternal::IsAppInstalled(short *)

- ea: `0x18002e300`
- end: `0x18002e602`
- name: `?IsAppInstalled@CMbaeInternal@@UEAAJPEAF@Z`
- size: `770`
- prototype: `__int64 __fastcall(CMbaeInternal *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800024e0`
- `0x180009474`
- `0x1800143bc`
- `0x180016134`
- `0x1800163ec`
- `0x1800171b8`
- `0x18002ba40`
- `0x18002e300`
- `0x18002f0e4`
- `0x18002f1e0`
- `0x18002f288`
- `0x18002f940`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x18002e574`
- `ntdll!WinSqmIncrementDWORD` at `0x18002e574`

## string_xrefs

- `0x18002e38c`: `CMbaeInternal::IsAppInstalled`

## pseudocode

```c
__int64 __fastcall CMbaeInternal::IsAppInstalled(CMbaeInternal *this, __int16 *a2)
{
  int v4; // eax
  int v5; // ecx
  unsigned int v6; // edi
  int AppId; // eax
  int AppPackageFamilyName; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rbx
  int AppInstallDelta; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  const wchar_t *v16; // rax
  unsigned int v17; // ecx
  __int64 v18; // rdx
  const wchar_t *v19; // rax
  unsigned int v20; // ecx
  int v21; // [rsp+20h] [rbp-69h]
  unsigned __int8 v22[8]; // [rsp+30h] [rbp-59h] BYREF
  int v23; // [rsp+38h] [rbp-51h] BYREF
  __int128 v24; // [rsp+40h] [rbp-49h] BYREF
  __m128i si128; // [rsp+50h] [rbp-39h]
  _OWORD v26[2]; // [rsp+60h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+80h] [rbp-9h] BYREF
  const char *v28; // [rsp+90h] [rbp+7h]
  __int64 v29; // [rsp+98h] [rbp+Fh]
  int *v30; // [rsp+A0h] [rbp+17h]
  __int64 v31; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v4 = CMbaeInternal::_CheckAndInitOutParam<short>();
  v6 = v4;
  if ( v4 >= 0 )
  {
    v23 = 0;
    if ( !*((_QWORD *)this + 3) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x102,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
        (const char *)0x8007139FLL,
        v21);
      return 2147947423LL;
    }
    if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
      McTemplateU0szz_EventWriteTransfer(
        v5,
        (unsigned int)CMbaeInternal_cpp260,
        (unsigned int)"CMbaeInternal::IsAppInstalled",
        *((_QWORD *)this + 4),
        *((_QWORD *)this + 5));
    v22[0] = 0;
    v24 = 0;
    LOWORD(v24) = 0;
    v26[0] = 0;
    LOWORD(v26[0]) = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v26[1] = si128;
    AppId = CMbaeInternal::_GetAppId((__int64)this, (__int64)&v24);
    if ( AppId < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x10A,
        (int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
        (const char *)(unsigned int)AppId);
    AppPackageFamilyName = CMbaeInternal::_GetAppPackageFamilyName((__int64)this, (__int64)v26);
    if ( AppPackageFamilyName < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x10B,
        (int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
        (const char *)(unsigned int)AppPackageFamilyName);
    v12 = -1;
    if ( (int)CMbaeInternal::_IsAppInstalledByAppIdAndFamilyName(v10, &v24, (const WCHAR *)v26, v22) >= 0 && v22[0] )
      *a2 = -1;
    AppInstallDelta = CMbaeInternal::_GetAppInstallDelta(v11, (__int64)&v24, v22[0], &v23);
    v6 = AppInstallDelta;
    if ( AppInstallDelta < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x111,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
        (const char *)(unsigned int)AppInstallDelta,
        v21);
LABEL_42:
      std::wstring::~wstring((char **)v26);
      std::wstring::~wstring((char **)&v24);
      return v6;
    }
    v15 = 2;
    if ( v23 == 1 )
    {
      if ( (Microsoft_Windows_Mobile_Broadband_Experience_Api_InternalEnableBits & 2) == 0 )
      {
LABEL_26:
        v18 = 9621;
LABEL_38:
        WinSqmIncrementDWORD(0, v18, 1, v15);
        goto LABEL_39;
      }
      if ( si128.m128i_i64[1] <= 7uLL )
      {
        v16 = (const wchar_t *)&v24;
      }
      else
      {
        v16 = (const wchar_t *)v24;
        if ( !(_QWORD)v24 )
        {
          v17 = 10;
LABEL_24:
          v16 = L"NULL";
LABEL_25:
          v28 = (const char *)v16;
          v29 = v17;
          McGenEventWrite_EventWriteTransfer(
            &MBAE_Api_Internal_Context,
            (const EVENT_DESCRIPTOR *)DetectedAppInstalled,
            v14,
            2u,
            &v27);
          goto LABEL_26;
        }
      }
      do
        ++v12;
      while ( v16[v12] );
      v17 = 2 * v12 + 2;
      if ( v16 )
        goto LABEL_25;
      goto LABEL_24;
    }
    if ( v23 != 2 )
    {
LABEL_39:
      if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
      {
        v23 = v22[0];
        v28 = "CMbaeInternal::IsAppInstalled";
        v30 = &v23;
        v29 = 30;
        v31 = 4;
        McGenEventWrite_EventWriteTransfer(
          &CtlGuid_Context,
          (const EVENT_DESCRIPTOR *)CMbaeInternal_cpp290,
          v14,
          3u,
          &v27);
      }
      v6 = 0;
      goto LABEL_42;
    }
    if ( (Microsoft_Windows_Mobile_Broadband_Experience_Api_InternalEnableBits & 2) == 0 )
    {
LABEL_37:
      v18 = 9567;
      goto LABEL_38;
    }
    if ( si128.m128i_i64[1] <= 7uLL )
    {
      v19 = (const wchar_t *)&v24;
    }
    else
    {
      v19 = (const wchar_t *)v24;
      if ( !(_QWORD)v24 )
      {
        v20 = 10;
LABEL_35:
        v19 = L"NULL";
LABEL_36:
        v28 = (const char *)v19;
        v29 = v20;
        McGenEventWrite_EventWriteTransfer(
          &MBAE_Api_Internal_Context,
          (const EVENT_DESCRIPTOR *)DetectedAppUninstalled,
          v14,
          2u,
          &v27);
        goto LABEL_37;
      }
    }
    do
      ++v12;
    while ( v19[v12] );
    v20 = 2 * v12 + 2;
    if ( v19 )
      goto LABEL_36;
    goto LABEL_35;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xFE,
    (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
    (const char *)(unsigned int)v4,
    v21);
  return v6;
}

```

## disassembly

```asm
0x18002e300  mov     [rsp-8+arg_10], rbx
0x18002e305  push    rbp
0x18002e306  push    rsi
0x18002e307  push    rdi
0x18002e308  push    r13
0x18002e30a  push    r15
0x18002e30c  lea     rbp, [rsp-37h]
0x18002e311  sub     rsp, 0C0h
0x18002e318  mov     rax, cs:__security_cookie
0x18002e31f  xor     rax, rsp
0x18002e322  mov     [rbp+57h+var_30], rax
0x18002e326  mov     rsi, rdx
0x18002e329  mov     rbx, rcx
0x18002e32c  call    ??$_CheckAndInitOutParam@F@CMbaeInternal@@AEAAJPEAF@Z; CMbaeInternal::_CheckAndInitOutParam<short>(short *)
0x18002e331  xor     r15d, r15d
0x18002e334  mov     edi, eax
0x18002e336  test    eax, eax
0x18002e338  jns     short loc_18002E357
0x18002e33a  mov     rcx, [rbp+5Fh]; this
0x18002e33e  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18002e345  mov     r9d, eax; char *
0x18002e348  mov     edx, 0FEh; void *
0x18002e34d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e352  jmp     loc_18002E5DD
0x18002e357  mov     [rbp+57h+var_A8], r15d
0x18002e35b  cmp     [rbx+18h], r15
0x18002e35f  jnz     short loc_18002E385
0x18002e361  mov     rcx, [rbp+5Fh]; this
0x18002e365  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18002e36c  mov     ebx, 8007139Fh
0x18002e371  mov     edx, 102h; void *
0x18002e376  mov     r9d, ebx; char *
0x18002e379  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e37e  mov     eax, ebx
0x18002e380  jmp     loc_18002E5DF
0x18002e385  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x18002e38c  lea     r13, aCmbaeinternalI_0; "CMbaeInternal::IsAppInstalled"
0x18002e393  jz      short loc_18002E3B1
0x18002e395  mov     rax, [rbx+28h]
0x18002e399  lea     rdx, CMbaeInternal_cpp260
0x18002e3a0  mov     r9, [rbx+20h]
0x18002e3a4  mov     r8, r13
0x18002e3a7  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18002e3ac  call    McTemplateU0szz_EventWriteTransfer
0x18002e3b1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002e3b9  lea     rdx, [rbp+57h+var_A0]
0x18002e3bd  xorps   xmm0, xmm0
0x18002e3c0  mov     [rbp+57h+var_B0], r15b
0x18002e3c4  movups  [rbp+57h+var_A0], xmm0
0x18002e3c8  mov     rcx, rbx
0x18002e3cb  mov     word ptr [rbp+57h+var_A0], r15w
0x18002e3d0  movups  [rbp+57h+var_80], xmm0
0x18002e3d4  mov     word ptr [rbp+57h+var_80], r15w
0x18002e3d9  movdqu  [rbp+57h+var_90], xmm1
0x18002e3de  movdqu  [rbp+57h+var_70], xmm1
0x18002e3e3  call    ?_GetAppId@CMbaeInternal@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CMbaeInternal::_GetAppId(std::wstring &)
0x18002e3e8  test    eax, eax
0x18002e3ea  jns     short loc_18002E404
0x18002e3ec  mov     rcx, [rbp+5Fh]; this
0x18002e3f0  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18002e3f7  mov     r9d, eax; char *
0x18002e3fa  mov     edx, 10Ah; void *
0x18002e3ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002e404  lea     rdx, [rbp+57h+var_80]
0x18002e408  mov     rcx, rbx
0x18002e40b  call    ?_GetAppPackageFamilyName@CMbaeInternal@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CMbaeInternal::_GetAppPackageFamilyName(std::wstring &)
0x18002e410  test    eax, eax
0x18002e412  jns     short loc_18002E42C
0x18002e414  mov     rcx, [rbp+5Fh]; this
0x18002e418  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18002e41f  mov     r9d, eax; char *
0x18002e422  mov     edx, 10Bh; void *
0x18002e427  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002e42c  lea     r9, [rbp+57h+var_B0]
0x18002e430  lea     r8, [rbp+57h+var_80]
0x18002e434  lea     rdx, [rbp+57h+var_A0]
0x18002e438  call    ?_IsAppInstalledByAppIdAndFamilyName@CMbaeInternal@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEA_N@Z; CMbaeInternal::_IsAppInstalledByAppIdAndFamilyName(std::wstring const &,std::wstring const &,bool &)
0x18002e43d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e441  test    eax, eax
0x18002e443  js      short loc_18002E44E
0x18002e445  cmp     [rbp+57h+var_B0], r15b
0x18002e449  jz      short loc_18002E44E
0x18002e44b  mov     [rsi], bx
0x18002e44e  mov     r8b, [rbp+57h+var_B0]
0x18002e452  lea     r9, [rbp+57h+var_A8]
0x18002e456  lea     rdx, [rbp+57h+var_A0]
0x18002e45a  call    ?_GetAppInstallDelta@CMbaeInternal@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NPEAW4APPINSTALL_DELTA@1@@Z; CMbaeInternal::_GetAppInstallDelta(std::wstring const &,bool,CMbaeInternal::APPINSTALL_DELTA *)
0x18002e45f  mov     edi, eax
0x18002e461  test    eax, eax
0x18002e463  jns     short loc_18002E482
0x18002e465  mov     rcx, [rbp+5Fh]; this
0x18002e469  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18002e470  mov     r9d, eax; char *
0x18002e473  mov     edx, 111h; void *
0x18002e478  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e47d  jmp     loc_18002E5CB
0x18002e482  cmp     [rbp+57h+var_A8], 1
0x18002e486  mov     r9d, 2
0x18002e48c  jnz     short loc_18002E4FB
0x18002e48e  test    cs:Microsoft_Windows_Mobile_Broadband_Experience_Api_InternalEnableBits, r9b
0x18002e495  jz      short loc_18002E4F4
0x18002e497  cmp     qword ptr [rbp+57h+var_90+8], 7
0x18002e49c  jbe     short loc_18002E4AC
0x18002e49e  mov     rax, qword ptr [rbp+57h+var_A0]
0x18002e4a2  test    rax, rax
0x18002e4a5  jnz     short loc_18002E4B0
0x18002e4a7  lea     ecx, [rax+0Ah]
0x18002e4aa  jmp     short loc_18002E4C6
0x18002e4ac  lea     rax, [rbp+57h+var_A0]
0x18002e4b0  inc     rbx
0x18002e4b3  cmp     [rax+rbx*2], r15w
0x18002e4b8  jnz     short loc_18002E4B0
0x18002e4ba  lea     ecx, ds:2[rbx*2]
0x18002e4c1  test    rax, rax
0x18002e4c4  jnz     short loc_18002E4CD
0x18002e4c6  lea     rax, aNull_0; "NULL"
0x18002e4cd  mov     [rbp+57h+var_50], rax
0x18002e4d1  lea     rdx, DetectedAppInstalled
0x18002e4d8  lea     rax, [rbp+57h+var_60]
0x18002e4dc  mov     dword ptr [rbp+57h+var_48], ecx
0x18002e4df  lea     rcx, MBAE_Api_Internal_Context
0x18002e4e6  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18002e4eb  mov     dword ptr [rbp+57h+var_48+4], r15d
0x18002e4ef  call    McGenEventWrite_EventWriteTransfer
0x18002e4f4  mov     edx, 2595h
0x18002e4f9  jmp     short loc_18002E56C
0x18002e4fb  cmp     [rbp+57h+var_A8], r9d
0x18002e4ff  jnz     short loc_18002E57A
0x18002e501  test    cs:Microsoft_Windows_Mobile_Broadband_Experience_Api_InternalEnableBits, r9b
0x18002e508  jz      short loc_18002E567
0x18002e50a  cmp     qword ptr [rbp+57h+var_90+8], 7
0x18002e50f  jbe     short loc_18002E51F
0x18002e511  mov     rax, qword ptr [rbp+57h+var_A0]
0x18002e515  test    rax, rax
0x18002e518  jnz     short loc_18002E523
0x18002e51a  lea     ecx, [rax+0Ah]
0x18002e51d  jmp     short loc_18002E539
0x18002e51f  lea     rax, [rbp+57h+var_A0]
0x18002e523  inc     rbx
0x18002e526  cmp     [rax+rbx*2], r15w
0x18002e52b  jnz     short loc_18002E523
0x18002e52d  lea     ecx, ds:2[rbx*2]
0x18002e534  test    rax, rax
0x18002e537  jnz     short loc_18002E540
0x18002e539  lea     rax, aNull_0; "NULL"
0x18002e540  mov     [rbp+57h+var_50], rax
0x18002e544  lea     rdx, DetectedAppUninstalled
0x18002e54b  lea     rax, [rbp+57h+var_60]
0x18002e54f  mov     dword ptr [rbp+57h+var_48], ecx
0x18002e552  lea     rcx, MBAE_Api_Internal_Context
0x18002e559  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18002e55e  mov     dword ptr [rbp+57h+var_48+4], r15d
0x18002e562  call    McGenEventWrite_EventWriteTransfer
0x18002e567  mov     edx, 255Fh
0x18002e56c  mov     r8d, 1
0x18002e572  xor     ecx, ecx
0x18002e574  call    cs:__imp_WinSqmIncrementDWORD
0x18002e57a  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x18002e581  jz      short loc_18002E5C8
0x18002e583  movzx   eax, [rbp+57h+var_B0]
0x18002e587  lea     rdx, CMbaeInternal_cpp290
0x18002e58e  mov     [rbp+57h+var_A8], eax
0x18002e591  lea     rcx, CtlGuid_Context
0x18002e598  lea     rax, [rbp+57h+var_A8]
0x18002e59c  mov     [rbp+57h+var_50], r13
0x18002e5a0  mov     [rbp+57h+var_40], rax
0x18002e5a4  mov     r9d, 3
0x18002e5aa  lea     rax, [rbp+57h+var_60]
0x18002e5ae  mov     [rbp+57h+var_48], 1Eh
0x18002e5b6  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18002e5bb  mov     [rbp+57h+var_38], 4
0x18002e5c3  call    McGenEventWrite_EventWriteTransfer
0x18002e5c8  mov     edi, r15d
0x18002e5cb  lea     rcx, [rbp+57h+var_80]
0x18002e5cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e5d4  lea     rcx, [rbp+57h+var_A0]
0x18002e5d8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e5dd  mov     eax, edi
0x18002e5df  mov     rcx, [rbp+57h+var_30]
0x18002e5e3  xor     rcx, rsp; StackCookie
0x18002e5e6  call    __security_check_cookie
0x18002e5eb  mov     rbx, [rsp+0E0h+arg_10]
0x18002e5f3  add     rsp, 0C0h
0x18002e5fa  pop     r15
0x18002e5fc  pop     r13
0x18002e5fe  pop     rdi
0x18002e5ff  pop     rsi
0x18002e600  pop     rbp
0x18002e601  retn
```
