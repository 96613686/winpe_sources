# EapLm::Peer::EapLibraryManagerConfig::IsValidMethod2(_EAP_METHOD_INFO &,EapLm::EapMethodTypeOverrideValue::EapMethodTypeOverrideType,RegistryKey const &)

- ea: `0x180016ec0`
- end: `0x180017293`
- name: `?IsValidMethod2@EapLibraryManagerConfig@Peer@EapLm@@UEAA_NAEAU_EAP_METHOD_INFO@@W4EapMethodTypeOverrideType@EapMethodTypeOverrideValue@3@AEBVRegistryKey@@@Z`
- size: `979`
- prototype: `char __fastcall(__int64, unsigned __int8 *, __int64, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x18000bba8`
- `0x18000eb74`
- `0x18000eb94`
- `0x180014ecc`
- `0x180016b4c`
- `0x180016c54`
- `0x180016ec0`
- `0x18001729c`
- `0x18001736c`
- `0x18002d6b0`
- `0x18002d96c`

## string_xrefs

- `0x180016f3e`: `ConfigUIPath`
- `0x180016f59`: `InteractiveUIPath`
- `0x180016f74`: `IdentityPath`
- `0x180016f7d`: `PeerDllPath`
- `0x180016f98`: `PeerConfigUIPath`
- `0x180016fb3`: `PeerInteractiveUIPath`
- `0x180016fce`: `PeerIdentityPath`
- `0x180017027`: `Eap method DLL path`
- `0x18001709f`: `Configuration UI name`
- `0x180017117`: `Interactive UI Path name`
- `0x180017190`: `Identity UI Path name`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall EapLm::Peer::EapLibraryManagerConfig::IsValidMethod2(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  const wchar_t *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  int v23; // ecx
  int v24; // r9d
  char v25; // di
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rcx
  int v30; // ecx
  int v31; // r9d
  __int64 v32; // rax
  __int64 v33; // rcx
  int v34; // ecx
  int v35; // r9d
  __int64 v36; // rax
  __int64 v37; // rcx
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  _BYTE v42[32]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v43[32]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v44[32]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v45[32]; // [rsp+A0h] [rbp+7h] BYREF
  _BYTE v46[16]; // [rsp+C0h] [rbp+27h] BYREF

  if ( (unsigned __int8)EapLm::BaseEapLibraryManager::IsValidMethod() )
  {
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v44);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v43);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v42);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v45);
    if ( *((_DWORD *)a2 + 3) )
    {
      v13 = std::_WChar_traits<wchar_t>::length(L"PeerDllPath");
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(v44, v14, v13);
      v15 = std::_WChar_traits<wchar_t>::length(L"PeerConfigUIPath");
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(v43, v16, v15);
      v17 = std::_WChar_traits<wchar_t>::length(L"PeerInteractiveUIPath");
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(v42, v18, v17);
      v12 = L"PeerIdentityPath";
    }
    else
    {
      v6 = std::_WChar_traits<wchar_t>::length(L"Path");
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(v44, v7, v6);
      v8 = std::_WChar_traits<wchar_t>::length(L"ConfigUIPath");
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(v43, v9, v8);
      v10 = std::_WChar_traits<wchar_t>::length(L"InteractiveUIPath");
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(v42, v11, v10);
      v12 = L"IdentityPath";
    }
    v19 = std::_WChar_traits<wchar_t>::length(v12);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(v45, v20, v19);
    v21 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v44);
    v25 = 1;
    if ( (unsigned int)EapLm::BaseEapLibraryManager::ValidateKey(v22, a4, v21) == 1 )
    {
      v28 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v43);
      if ( (unsigned int)EapLm::BaseEapLibraryManager::ValidateKey(v29, a4, v28) == -1 )
      {
        if ( (Microsoft_Windows_EapHostEnableBits & 1) != 0 )
        {
          LOBYTE(v31) = *a2;
          McTemplateU0suqqq_EtwEventWriteTransfer(
            v30,
            (unsigned int)PeerPathNameValidationFailure,
            (unsigned int)"Configuration UI name",
            v31,
            *((_DWORD *)a2 + 3),
            *((_DWORD *)a2 + 1),
            *((_DWORD *)a2 + 2));
        }
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_30;
        v27 = 11;
      }
      else
      {
        v32 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v42);
        if ( (unsigned int)EapLm::BaseEapLibraryManager::ValidateKey(v33, a4, v32) == -1 )
        {
          if ( (Microsoft_Windows_EapHostEnableBits & 1) != 0 )
          {
            LOBYTE(v35) = *a2;
            McTemplateU0suqqq_EtwEventWriteTransfer(
              v34,
              (unsigned int)PeerPathNameValidationFailure,
              (unsigned int)"Interactive UI Path name",
              v35,
              *((_DWORD *)a2 + 3),
              *((_DWORD *)a2 + 1),
              *((_DWORD *)a2 + 2));
          }
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_30;
          v27 = 12;
        }
        else
        {
          v36 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v45);
          if ( (unsigned int)EapLm::BaseEapLibraryManager::ValidateKey(v37, a4, v36) != -1 )
          {
            if ( (byte_18004AF81 & 2) != 0 )
              McGenEventWrite_EtwEventWriteTransfer(
                (unsigned int)&eaphost_Context,
                (unsigned int)PeerRegKeyValidationSuccess,
                v39,
                1,
                (__int64)v46);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_86bf81f726493138f379a8135b514f35_Traceguids);
            goto LABEL_36;
          }
          if ( (Microsoft_Windows_EapHostEnableBits & 1) != 0 )
          {
            LOBYTE(v40) = *a2;
            McTemplateU0suqqq_EtwEventWriteTransfer(
              v38,
              (unsigned int)PeerPathNameValidationFailure,
              (unsigned int)"Identity UI Path name",
              v40,
              *((_DWORD *)a2 + 3),
              *((_DWORD *)a2 + 1),
              *((_DWORD *)a2 + 2));
          }
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
LABEL_30:
            v25 = 0;
LABEL_36:
            std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v45);
            std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v42);
            std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v43);
            std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v44);
            return v25;
          }
          v27 = 13;
        }
      }
    }
    else
    {
      if ( (Microsoft_Windows_EapHostEnableBits & 1) != 0 )
      {
        LOBYTE(v24) = *a2;
        McTemplateU0suqqq_EtwEventWriteTransfer(
          v23,
          (unsigned int)PeerPathNameValidationFailure,
          (unsigned int)"Eap method DLL path",
          v24,
          *((_DWORD *)a2 + 3),
          *((_DWORD *)a2 + 1),
          *((_DWORD *)a2 + 2));
      }
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_30;
      v27 = 10;
    }
    WPP_SF_dddd(
      v26[2],
      v27,
      WPP_86bf81f726493138f379a8135b514f35_Traceguids,
      *a2,
      *((_DWORD *)a2 + 3),
      *((_DWORD *)a2 + 1),
      *((_DWORD *)a2 + 2));
    goto LABEL_30;
  }
  return 0;
}

```

## disassembly

```asm
0x180016ec0  mov     [rsp-8+arg_0], rbx
0x180016ec5  push    rbp
0x180016ec6  push    rsi
0x180016ec7  push    rdi
0x180016ec8  lea     rbp, [rsp-47h]
0x180016ecd  sub     rsp, 0E0h
0x180016ed4  mov     rax, cs:__security_cookie
0x180016edb  xor     rax, rsp
0x180016ede  mov     [rbp+57h+var_20], rax
0x180016ee2  mov     rsi, r9
0x180016ee5  mov     rbx, rdx
0x180016ee8  call    ?IsValidMethod@BaseEapLibraryManager@EapLm@@MEAA_NAEAU_EAP_METHOD_INFO@@W4EapMethodTypeOverrideType@EapMethodTypeOverrideValue@2@@Z; EapLm::BaseEapLibraryManager::IsValidMethod(_EAP_METHOD_INFO &,EapLm::EapMethodTypeOverrideValue::EapMethodTypeOverrideType)
0x180016eed  test    al, al
0x180016eef  jz      loc_180017272
0x180016ef5  lea     rcx, [rbp+57h+var_70]
0x180016ef9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x180016efe  nop
0x180016eff  lea     rcx, [rbp+57h+var_90]
0x180016f03  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x180016f08  nop
0x180016f09  lea     rcx, [rbp+57h+var_B0]
0x180016f0d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x180016f12  nop
0x180016f13  lea     rcx, [rbp+57h+var_50]
0x180016f17  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x180016f1c  nop
0x180016f1d  cmp     dword ptr [rbx+0Ch], 0
0x180016f21  jnz     short loc_180016F7D
0x180016f23  lea     rcx, aPath; "Path"
0x180016f2a  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180016f2f  mov     r8, rax
0x180016f32  mov     rdx, rcx
0x180016f35  lea     rcx, [rbp+57h+var_70]
0x180016f39  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180016f3e  lea     rcx, aConfiguipath; "ConfigUIPath"
0x180016f45  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180016f4a  mov     r8, rax
0x180016f4d  mov     rdx, rcx
0x180016f50  lea     rcx, [rbp+57h+var_90]
0x180016f54  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180016f59  lea     rcx, aInteractiveuip; "InteractiveUIPath"
0x180016f60  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180016f65  mov     r8, rax
0x180016f68  mov     rdx, rcx
0x180016f6b  lea     rcx, [rbp+57h+var_B0]
0x180016f6f  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180016f74  lea     rcx, aIdentitypath; "IdentityPath"
0x180016f7b  jmp     short loc_180016FD5
0x180016f7d  lea     rcx, aPeerdllpath; "PeerDllPath"
0x180016f84  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180016f89  mov     r8, rax
0x180016f8c  mov     rdx, rcx
0x180016f8f  lea     rcx, [rbp+57h+var_70]
0x180016f93  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180016f98  lea     rcx, aPeerconfiguipa; "PeerConfigUIPath"
0x180016f9f  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180016fa4  mov     r8, rax
0x180016fa7  mov     rdx, rcx
0x180016faa  lea     rcx, [rbp+57h+var_90]
0x180016fae  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180016fb3  lea     rcx, aPeerinteractiv; "PeerInteractiveUIPath"
0x180016fba  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180016fbf  mov     r8, rax
0x180016fc2  mov     rdx, rcx
0x180016fc5  lea     rcx, [rbp+57h+var_B0]
0x180016fc9  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180016fce  lea     rcx, aPeeridentitypa; "PeerIdentityPath"
0x180016fd5  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180016fda  mov     r8, rax
0x180016fdd  mov     rdx, rcx
0x180016fe0  lea     rcx, [rbp+57h+var_50]
0x180016fe4  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180016fe9  lea     rcx, [rbp+57h+var_70]
0x180016fed  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180016ff2  mov     r8, rax
0x180016ff5  mov     rdx, rsi
0x180016ff8  call    ?ValidateKey@BaseEapLibraryManager@EapLm@@IEAA?AW4ResultType@ResultValue@2@AEBVRegistryKey@@PEB_W@Z; EapLm::BaseEapLibraryManager::ValidateKey(RegistryKey const &,wchar_t const *)
0x180016ffd  mov     edi, 1
0x180017002  cmp     eax, edi
0x180017004  jz      short loc_180017065
0x180017006  test    cs:Microsoft_Windows_EapHostEnableBits, dil
0x18001700d  jz      short loc_18001703A
0x18001700f  mov     eax, [rbx+8]
0x180017012  mov     [rsp+0F0h+var_C0], eax
0x180017016  mov     eax, [rbx+4]
0x180017019  mov     [rsp+0F0h+var_C8], eax
0x18001701d  mov     eax, [rbx+0Ch]
0x180017020  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180017024  mov     r9b, [rbx]
0x180017027  lea     r8, aEapMethodDllPa; "Eap method DLL path"
0x18001702e  lea     rdx, PeerPathNameValidationFailure
0x180017035  call    McTemplateU0suqqq_EtwEventWriteTransfer
0x18001703a  lea     rax, WPP_GLOBAL_Control
0x180017041  mov     rcx, cs:WPP_GLOBAL_Control
0x180017048  cmp     rcx, rax
0x18001704b  jz      loc_1800171EA
0x180017051  test    [rcx+1Ch], dil
0x180017055  jz      loc_1800171EA
0x18001705b  mov     edx, 0Ah
0x180017060  jmp     loc_1800171C1
0x180017065  lea     rcx, [rbp+57h+var_90]
0x180017069  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001706e  mov     r8, rax
0x180017071  mov     rdx, rsi
0x180017074  call    ?ValidateKey@BaseEapLibraryManager@EapLm@@IEAA?AW4ResultType@ResultValue@2@AEBVRegistryKey@@PEB_W@Z; EapLm::BaseEapLibraryManager::ValidateKey(RegistryKey const &,wchar_t const *)
0x180017079  cmp     eax, 0FFFFFFFFh
0x18001707c  jnz     short loc_1800170DD
0x18001707e  test    cs:Microsoft_Windows_EapHostEnableBits, dil
0x180017085  jz      short loc_1800170B2
0x180017087  mov     eax, [rbx+8]
0x18001708a  mov     [rsp+0F0h+var_C0], eax
0x18001708e  mov     eax, [rbx+4]
0x180017091  mov     [rsp+0F0h+var_C8], eax
0x180017095  mov     eax, [rbx+0Ch]
0x180017098  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18001709c  mov     r9b, [rbx]
0x18001709f  lea     r8, aConfigurationU; "Configuration UI name"
0x1800170a6  lea     rdx, PeerPathNameValidationFailure
0x1800170ad  call    McTemplateU0suqqq_EtwEventWriteTransfer
0x1800170b2  lea     rax, WPP_GLOBAL_Control
0x1800170b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170c0  cmp     rcx, rax
0x1800170c3  jz      loc_1800171EA
0x1800170c9  test    [rcx+1Ch], dil
0x1800170cd  jz      loc_1800171EA
0x1800170d3  mov     edx, 0Bh
0x1800170d8  jmp     loc_1800171C1
0x1800170dd  lea     rcx, [rbp+57h+var_B0]
0x1800170e1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800170e6  mov     r8, rax
0x1800170e9  mov     rdx, rsi
0x1800170ec  call    ?ValidateKey@BaseEapLibraryManager@EapLm@@IEAA?AW4ResultType@ResultValue@2@AEBVRegistryKey@@PEB_W@Z; EapLm::BaseEapLibraryManager::ValidateKey(RegistryKey const &,wchar_t const *)
0x1800170f1  cmp     eax, 0FFFFFFFFh
0x1800170f4  jnz     short loc_180017152
0x1800170f6  test    cs:Microsoft_Windows_EapHostEnableBits, dil
0x1800170fd  jz      short loc_18001712A
0x1800170ff  mov     eax, [rbx+8]
0x180017102  mov     [rsp+0F0h+var_C0], eax
0x180017106  mov     eax, [rbx+4]
0x180017109  mov     [rsp+0F0h+var_C8], eax
0x18001710d  mov     eax, [rbx+0Ch]
0x180017110  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180017114  mov     r9b, [rbx]
0x180017117  lea     r8, aInteractiveUiP; "Interactive UI Path name"
0x18001711e  lea     rdx, PeerPathNameValidationFailure
0x180017125  call    McTemplateU0suqqq_EtwEventWriteTransfer
0x18001712a  lea     rax, WPP_GLOBAL_Control
0x180017131  mov     rcx, cs:WPP_GLOBAL_Control
0x180017138  cmp     rcx, rax
0x18001713b  jz      loc_1800171EA
0x180017141  test    [rcx+1Ch], dil
0x180017145  jz      loc_1800171EA
0x18001714b  mov     edx, 0Ch
0x180017150  jmp     short loc_1800171C1
0x180017152  lea     rcx, [rbp+57h+var_50]
0x180017156  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001715b  mov     r8, rax
0x18001715e  mov     rdx, rsi
0x180017161  call    ?ValidateKey@BaseEapLibraryManager@EapLm@@IEAA?AW4ResultType@ResultValue@2@AEBVRegistryKey@@PEB_W@Z; EapLm::BaseEapLibraryManager::ValidateKey(RegistryKey const &,wchar_t const *)
0x180017166  cmp     eax, 0FFFFFFFFh
0x180017169  jnz     loc_1800171EF
0x18001716f  test    cs:Microsoft_Windows_EapHostEnableBits, dil
0x180017176  jz      short loc_1800171A3
0x180017178  mov     eax, [rbx+8]
0x18001717b  mov     [rsp+0F0h+var_C0], eax
0x18001717f  mov     eax, [rbx+4]
0x180017182  mov     [rsp+0F0h+var_C8], eax
0x180017186  mov     eax, [rbx+0Ch]
0x180017189  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18001718d  mov     r9b, [rbx]
0x180017190  lea     r8, aIdentityUiPath; "Identity UI Path name"
0x180017197  lea     rdx, PeerPathNameValidationFailure
0x18001719e  call    McTemplateU0suqqq_EtwEventWriteTransfer
0x1800171a3  lea     rax, WPP_GLOBAL_Control
0x1800171aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171b1  cmp     rcx, rax
0x1800171b4  jz      short loc_1800171EA
0x1800171b6  test    [rcx+1Ch], dil
0x1800171ba  jz      short loc_1800171EA
0x1800171bc  mov     edx, 0Dh
0x1800171c1  mov     eax, [rbx+8]
0x1800171c4  mov     [rsp+0F0h+var_C0], eax
0x1800171c8  mov     eax, [rbx+4]
0x1800171cb  mov     [rsp+0F0h+var_C8], eax
0x1800171cf  mov     eax, [rbx+0Ch]
0x1800171d2  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1800171d6  movzx   r9d, byte ptr [rbx]
0x1800171da  lea     r8, WPP_86bf81f726493138f379a8135b514f35_Traceguids
0x1800171e1  mov     rcx, [rcx+10h]
0x1800171e5  call    WPP_SF_dddd
0x1800171ea  xor     dil, dil
0x1800171ed  jmp     short loc_180017246
0x1800171ef  test    cs:byte_18004AF81, 2
0x1800171f6  jz      short loc_180017217
0x1800171f8  lea     rax, [rbp+57h+var_30]
0x1800171fc  mov     [rsp+0F0h+var_D0], rax
0x180017201  mov     r9d, edi
0x180017204  lea     rdx, PeerRegKeyValidationSuccess
0x18001720b  lea     rcx, eaphost_Context
0x180017212  call    McGenEventWrite_EtwEventWriteTransfer
0x180017217  lea     rax, WPP_GLOBAL_Control
0x18001721e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017225  cmp     rcx, rax
0x180017228  jz      short loc_180017246
0x18001722a  test    byte ptr [rcx+1Ch], 4
0x18001722e  jz      short loc_180017246
0x180017230  mov     edx, 0Eh
0x180017235  lea     r8, WPP_86bf81f726493138f379a8135b514f35_Traceguids
0x18001723c  mov     rcx, [rcx+10h]
0x180017240  call    WPP_SF_
0x180017245  nop
0x180017246  lea     rcx, [rbp+57h+var_50]
0x18001724a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001724f  nop
0x180017250  lea     rcx, [rbp+57h+var_B0]
0x180017254  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017259  nop
0x18001725a  lea     rcx, [rbp+57h+var_90]
0x18001725e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180017263  nop
0x180017264  lea     rcx, [rbp+57h+var_70]
0x180017268  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001726d  mov     al, dil
0x180017270  jmp     short loc_180017274
0x180017272  xor     al, al
0x180017274  mov     rcx, [rbp+57h+var_20]
0x180017278  xor     rcx, rsp; StackCookie
0x18001727b  call    __security_check_cookie
0x180017280  mov     rbx, [rsp+0F0h+arg_0]
0x180017288  add     rsp, 0E0h
0x18001728f  pop     rdi
0x180017290  pop     rsi
0x180017291  pop     rbp
0x180017292  retn
```
