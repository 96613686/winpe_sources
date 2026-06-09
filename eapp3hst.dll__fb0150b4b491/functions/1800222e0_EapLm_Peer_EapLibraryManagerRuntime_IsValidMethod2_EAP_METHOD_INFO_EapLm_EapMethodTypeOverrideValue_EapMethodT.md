# EapLm::Peer::EapLibraryManagerRuntime::IsValidMethod2(_EAP_METHOD_INFO &,EapLm::EapMethodTypeOverrideValue::EapMethodTypeOverrideType,RegistryKey const &)

- ea: `0x1800222e0`
- end: `0x1800224c3`
- name: `?IsValidMethod2@EapLibraryManagerRuntime@Peer@EapLm@@UEAA_NAEAU_EAP_METHOD_INFO@@W4EapMethodTypeOverrideType@EapMethodTypeOverrideValue@3@AEBVRegistryKey@@@Z`
- size: `483`
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
- `0x18001729c`
- `0x18001736c`
- `0x1800222e0`
- `0x18002d6b0`
- `0x18002d96c`

## string_xrefs

- `0x180022351`: `PeerDllPath`
- `0x1800223b0`: `Eap method DLL path name`

## pseudocode

```c
char __fastcall EapLm::Peer::EapLibraryManagerRuntime::IsValidMethod2(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4)
{
  const wchar_t *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  int v11; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  char v15; // di
  _BYTE v17[32]; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v18[32]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v19[32]; // [rsp+80h] [rbp-68h] BYREF
  _BYTE v20[32]; // [rsp+A0h] [rbp-48h] BYREF
  _BYTE v21[16]; // [rsp+C0h] [rbp-28h] BYREF

  if ( !(unsigned __int8)EapLm::BaseEapLibraryManager::IsValidMethod() )
    return 0;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v17);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v20);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v19);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v18);
  v6 = L"Path";
  if ( *((_DWORD *)a2 + 3) )
    v6 = L"PeerDllPath";
  v7 = std::_WChar_traits<wchar_t>::length(v6);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(v17, v8, v7);
  v9 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v17);
  v11 = EapLm::BaseEapLibraryManager::ValidateKey(v10, a4, v9);
  v15 = 1;
  if ( v11 == 1 )
  {
    if ( (byte_18004AF81 & 2) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)PeerRegKeyValidationSuccess,
        v13,
        1,
        (__int64)v21);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids);
  }
  else
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 1) != 0 )
    {
      LOBYTE(v14) = *a2;
      McTemplateU0suqqq_EtwEventWriteTransfer(
        v12,
        (unsigned int)PeerPathNameValidationFailure,
        (unsigned int)"Eap method DLL path name",
        v14,
        *((_DWORD *)a2 + 3),
        *((_DWORD *)a2 + 1),
        *((_DWORD *)a2 + 2));
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids,
        *a2,
        *((_DWORD *)a2 + 3),
        *((_DWORD *)a2 + 1),
        *((_DWORD *)a2 + 2));
    v15 = 0;
  }
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v18);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v19);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v20);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v17);
  return v15;
}

```

## disassembly

```asm
0x1800222e0  mov     [rsp+arg_0], rbx
0x1800222e5  push    rdi
0x1800222e6  sub     rsp, 0E0h
0x1800222ed  mov     rax, cs:__security_cookie
0x1800222f4  xor     rax, rsp
0x1800222f7  mov     [rsp+0E8h+var_18], rax
0x1800222ff  mov     rdi, r9
0x180022302  mov     rbx, rdx
0x180022305  call    ?IsValidMethod@BaseEapLibraryManager@EapLm@@MEAA_NAEAU_EAP_METHOD_INFO@@W4EapMethodTypeOverrideType@EapMethodTypeOverrideValue@2@@Z; EapLm::BaseEapLibraryManager::IsValidMethod(_EAP_METHOD_INFO &,EapLm::EapMethodTypeOverrideValue::EapMethodTypeOverrideType)
0x18002230a  test    al, al
0x18002230c  jz      loc_1800224A0
0x180022312  lea     rcx, [rsp+0E8h+var_A8]
0x180022317  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18002231c  nop
0x18002231d  lea     rcx, [rsp+0E8h+var_48]
0x180022325  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18002232a  nop
0x18002232b  lea     rcx, [rsp+0E8h+var_68]
0x180022333  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x180022338  nop
0x180022339  lea     rcx, [rsp+0E8h+var_88]
0x18002233e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x180022343  nop
0x180022344  cmp     dword ptr [rbx+0Ch], 0
0x180022348  lea     rcx, aPath; "Path"
0x18002234f  jz      short loc_180022358
0x180022351  lea     rcx, aPeerdllpath; "PeerDllPath"
0x180022358  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18002235d  mov     r8, rax
0x180022360  mov     rdx, rcx
0x180022363  lea     rcx, [rsp+0E8h+var_A8]
0x180022368  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18002236d  lea     rcx, [rsp+0E8h+var_A8]
0x180022372  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180022377  mov     r8, rax
0x18002237a  mov     rdx, rdi
0x18002237d  call    ?ValidateKey@BaseEapLibraryManager@EapLm@@IEAA?AW4ResultType@ResultValue@2@AEBVRegistryKey@@PEB_W@Z; EapLm::BaseEapLibraryManager::ValidateKey(RegistryKey const &,wchar_t const *)
0x180022382  mov     edi, 1
0x180022387  cmp     eax, edi
0x180022389  jz      loc_18002240F
0x18002238f  test    cs:Microsoft_Windows_EapHostEnableBits, dil
0x180022396  jz      short loc_1800223C3
0x180022398  mov     eax, [rbx+8]
0x18002239b  mov     [rsp+0E8h+var_B8], eax
0x18002239f  mov     eax, [rbx+4]
0x1800223a2  mov     [rsp+0E8h+var_C0], eax
0x1800223a6  mov     eax, [rbx+0Ch]
0x1800223a9  mov     dword ptr [rsp+0E8h+var_C8], eax
0x1800223ad  mov     r9b, [rbx]
0x1800223b0  lea     r8, aEapMethodDllPa_0; "Eap method DLL path name"
0x1800223b7  lea     rdx, PeerPathNameValidationFailure
0x1800223be  call    McTemplateU0suqqq_EtwEventWriteTransfer
0x1800223c3  lea     rax, WPP_GLOBAL_Control
0x1800223ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223d1  cmp     rcx, rax
0x1800223d4  jz      short loc_18002240A
0x1800223d6  test    [rcx+1Ch], dil
0x1800223da  jz      short loc_18002240A
0x1800223dc  movzx   r9d, byte ptr [rbx]
0x1800223e0  mov     edx, 0Ah
0x1800223e5  mov     eax, [rbx+8]
0x1800223e8  mov     [rsp+0E8h+var_B8], eax
0x1800223ec  mov     eax, [rbx+4]
0x1800223ef  mov     [rsp+0E8h+var_C0], eax
0x1800223f3  mov     eax, [rbx+0Ch]
0x1800223f6  mov     dword ptr [rsp+0E8h+var_C8], eax
0x1800223fa  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x180022401  mov     rcx, [rcx+10h]
0x180022405  call    WPP_SF_dddd
0x18002240a  xor     dil, dil
0x18002240d  jmp     short loc_18002246A
0x18002240f  test    cs:byte_18004AF81, 2
0x180022416  jz      short loc_18002243B
0x180022418  lea     rax, [rsp+0E8h+var_28]
0x180022420  mov     [rsp+0E8h+var_C8], rax
0x180022425  mov     r9d, edi
0x180022428  lea     rdx, PeerRegKeyValidationSuccess
0x18002242f  lea     rcx, eaphost_Context
0x180022436  call    McGenEventWrite_EtwEventWriteTransfer
0x18002243b  lea     rax, WPP_GLOBAL_Control
0x180022442  mov     rcx, cs:WPP_GLOBAL_Control
0x180022449  cmp     rcx, rax
0x18002244c  jz      short loc_18002246A
0x18002244e  test    byte ptr [rcx+1Ch], 4
0x180022452  jz      short loc_18002246A
0x180022454  mov     edx, 0Bh
0x180022459  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x180022460  mov     rcx, [rcx+10h]
0x180022464  call    WPP_SF_
0x180022469  nop
0x18002246a  lea     rcx, [rsp+0E8h+var_88]
0x18002246f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180022474  nop
0x180022475  lea     rcx, [rsp+0E8h+var_68]
0x18002247d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180022482  nop
0x180022483  lea     rcx, [rsp+0E8h+var_48]
0x18002248b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180022490  nop
0x180022491  lea     rcx, [rsp+0E8h+var_A8]
0x180022496  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002249b  mov     al, dil
0x18002249e  jmp     short loc_1800224A2
0x1800224a0  xor     al, al
0x1800224a2  mov     rcx, [rsp+0E8h+var_18]
0x1800224aa  xor     rcx, rsp; StackCookie
0x1800224ad  call    __security_check_cookie
0x1800224b2  mov     rbx, [rsp+0E8h+arg_0]
0x1800224ba  add     rsp, 0E0h
0x1800224c1  pop     rdi
0x1800224c2  retn
```
