# EapLm::Peer::EapLibraryManagerRuntime::IsValidMethod2(_EAP_METHOD_INFO &,EapLm::EapMethodTypeOverrideValue::EapMethodTypeOverrideType,RegistryKey const &)

- ea: `0x180011ae0`
- end: `0x180011cb2`
- name: `?IsValidMethod2@EapLibraryManagerRuntime@Peer@EapLm@@UEAA_NAEAU_EAP_METHOD_INFO@@W4EapMethodTypeOverrideType@EapMethodTypeOverrideValue@3@AEBVRegistryKey@@@Z`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002af0`
- `0x180009c40`
- `0x180009fe4`
- `0x18000a21c`
- `0x18000a588`
- `0x18001110c`
- `0x180011218`
- `0x180011ae0`
- `0x18001204c`
- `0x18001206c`
- `0x180012140`
- `0x18001c870`
- `0x18001cb34`

## string_xrefs

- `0x180011b51`: `PeerDllPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall EapLm::Peer::EapLibraryManagerRuntime::IsValidMethod2(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  const wchar_t *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  int v23; // eax
  int v24; // edx
  int v25; // ecx
  __int64 v26; // r8
  int v27; // r9d
  char v28; // di
  _BYTE v30[32]; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v31[32]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v32[32]; // [rsp+80h] [rbp-68h] BYREF
  _BYTE v33[32]; // [rsp+A0h] [rbp-48h] BYREF
  _BYTE v34[16]; // [rsp+C0h] [rbp-28h] BYREF

  if ( !(unsigned __int8)EapLm::BaseEapLibraryManager::IsValidMethod() )
    return 0;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v30,
    v6,
    v7,
    v8);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v33,
    v9,
    v10,
    v11);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v32,
    v12,
    v13,
    v14);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v31,
    v15,
    v16,
    v17);
  v18 = L"Path";
  if ( *((_DWORD *)a2 + 3) )
    v18 = L"PeerDllPath";
  v19 = std::_WChar_traits<wchar_t>::length(v18);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(v30, v20, v19);
  v21 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v30);
  v23 = EapLm::BaseEapLibraryManager::ValidateKey(v22, a4, v21);
  v28 = 1;
  if ( v23 == 1 )
  {
    if ( (byte_18004F981 & 2) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        &eaphost_Context,
        (__int64)PeerRegKeyValidationSuccess,
        v26,
        1,
        (__int64)v34);
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids);
    }
  }
  else
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 1) != 0 )
    {
      LOBYTE(v27) = *a2;
      McTemplateU0suqqq_EtwEventWriteTransfer(
        v25,
        v24,
        v26,
        v27,
        *((_DWORD *)a2 + 3),
        *((_DWORD *)a2 + 1),
        *((_DWORD *)a2 + 2));
    }
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_dddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids,
        *a2,
        *((_DWORD *)a2 + 3),
        *((_DWORD *)a2 + 1),
        *((_DWORD *)a2 + 2));
    }
    v28 = 0;
  }
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v31);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v32);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v33);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v30);
  return v28;
}

```

## disassembly

```asm
0x180011ae0  mov     [rsp+arg_0], rbx
0x180011ae5  push    rdi
0x180011ae6  sub     rsp, 0E0h
0x180011aed  mov     rax, cs:__security_cookie
0x180011af4  xor     rax, rsp
0x180011af7  mov     [rsp+0E8h+var_18], rax
0x180011aff  mov     rdi, r9
0x180011b02  mov     rbx, rdx
0x180011b05  call    ?IsValidMethod@BaseEapLibraryManager@EapLm@@MEAA_NAEAU_EAP_METHOD_INFO@@W4EapMethodTypeOverrideType@EapMethodTypeOverrideValue@2@@Z; EapLm::BaseEapLibraryManager::IsValidMethod(_EAP_METHOD_INFO &,EapLm::EapMethodTypeOverrideValue::EapMethodTypeOverrideType)
0x180011b0a  test    al, al
0x180011b0c  jz      loc_180011C8E
0x180011b12  lea     rcx, [rsp+0E8h+var_A8]
0x180011b17  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x180011b1c  nop
0x180011b1d  lea     rcx, [rsp+0E8h+var_48]
0x180011b25  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x180011b2a  nop
0x180011b2b  lea     rcx, [rsp+0E8h+var_68]
0x180011b33  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x180011b38  nop
0x180011b39  lea     rcx, [rsp+0E8h+var_88]
0x180011b3e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x180011b43  nop
0x180011b44  cmp     dword ptr [rbx+0Ch], 0
0x180011b48  lea     rcx, aPath; "Path"
0x180011b4f  jz      short loc_180011B58
0x180011b51  lea     rcx, aPeerdllpath; "PeerDllPath"
0x180011b58  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180011b5d  mov     r8, rax
0x180011b60  mov     rdx, rcx
0x180011b63  lea     rcx, [rsp+0E8h+var_A8]
0x180011b68  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180011b6d  lea     rcx, [rsp+0E8h+var_A8]
0x180011b72  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180011b77  mov     r8, rax
0x180011b7a  mov     rdx, rdi
0x180011b7d  call    ?ValidateKey@BaseEapLibraryManager@EapLm@@IEAA?AW4ResultType@ResultValue@2@AEBVRegistryKey@@PEB_W@Z; EapLm::BaseEapLibraryManager::ValidateKey(RegistryKey const &,wchar_t const *)
0x180011b82  mov     edi, 1
0x180011b87  cmp     eax, edi
0x180011b89  jz      short loc_180011BFD
0x180011b8b  test    cs:Microsoft_Windows_EapHostEnableBits, dil
0x180011b92  jz      short loc_180011BB1
0x180011b94  mov     eax, [rbx+8]
0x180011b97  mov     [rsp+0E8h+var_B8], eax
0x180011b9b  mov     eax, [rbx+4]
0x180011b9e  mov     [rsp+0E8h+var_C0], eax
0x180011ba2  mov     eax, [rbx+0Ch]
0x180011ba5  mov     dword ptr [rsp+0E8h+var_C8], eax
0x180011ba9  mov     r9b, [rbx]
0x180011bac  call    McTemplateU0suqqq_EtwEventWriteTransfer
0x180011bb1  lea     rax, WPP_GLOBAL_Control
0x180011bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bbf  cmp     rcx, rax
0x180011bc2  jz      short loc_180011BF8
0x180011bc4  test    [rcx+1Ch], dil
0x180011bc8  jz      short loc_180011BF8
0x180011bca  movzx   r9d, byte ptr [rbx]
0x180011bce  mov     edx, 0Ah
0x180011bd3  mov     eax, [rbx+8]
0x180011bd6  mov     [rsp+0E8h+var_B8], eax
0x180011bda  mov     eax, [rbx+4]
0x180011bdd  mov     [rsp+0E8h+var_C0], eax
0x180011be1  mov     eax, [rbx+0Ch]
0x180011be4  mov     dword ptr [rsp+0E8h+var_C8], eax
0x180011be8  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x180011bef  mov     rcx, [rcx+10h]
0x180011bf3  call    WPP_SF_dddd
0x180011bf8  xor     dil, dil
0x180011bfb  jmp     short loc_180011C58
0x180011bfd  test    cs:byte_18004F981, 2
0x180011c04  jz      short loc_180011C29
0x180011c06  lea     rax, [rsp+0E8h+var_28]
0x180011c0e  mov     [rsp+0E8h+var_C8], rax
0x180011c13  mov     r9d, edi
0x180011c16  lea     rdx, PeerRegKeyValidationSuccess
0x180011c1d  lea     rcx, eaphost_Context
0x180011c24  call    McGenEventWrite_EtwEventWriteTransfer
0x180011c29  lea     rax, WPP_GLOBAL_Control
0x180011c30  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c37  cmp     rcx, rax
0x180011c3a  jz      short loc_180011C58
0x180011c3c  test    byte ptr [rcx+1Ch], 4
0x180011c40  jz      short loc_180011C58
0x180011c42  mov     edx, 0Bh
0x180011c47  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x180011c4e  mov     rcx, [rcx+10h]
0x180011c52  call    WPP_SF_
0x180011c57  nop
0x180011c58  lea     rcx, [rsp+0E8h+var_88]
0x180011c5d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180011c62  nop
0x180011c63  lea     rcx, [rsp+0E8h+var_68]
0x180011c6b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180011c70  nop
0x180011c71  lea     rcx, [rsp+0E8h+var_48]
0x180011c79  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180011c7e  nop
0x180011c7f  lea     rcx, [rsp+0E8h+var_A8]
0x180011c84  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180011c89  mov     al, dil
0x180011c8c  jmp     short loc_180011C90
0x180011c8e  xor     al, al
0x180011c90  mov     rcx, [rsp+0E8h+var_18]
0x180011c98  xor     rcx, rsp; StackCookie
0x180011c9b  call    __security_check_cookie
0x180011ca0  mov     rbx, [rsp+0E8h+arg_0]
0x180011ca8  add     rsp, 0E0h
0x180011caf  pop     rdi
0x180011cb0  retn
```
