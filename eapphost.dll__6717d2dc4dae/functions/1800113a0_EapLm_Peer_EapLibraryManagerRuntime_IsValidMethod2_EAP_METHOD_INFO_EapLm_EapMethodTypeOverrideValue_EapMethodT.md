# EapLm::Peer::EapLibraryManagerRuntime::IsValidMethod2(_EAP_METHOD_INFO &,EapLm::EapMethodTypeOverrideValue::EapMethodTypeOverrideType,RegistryKey const &)

- ea: `0x1800113a0`
- end: `0x180011571`
- name: `?IsValidMethod2@EapLibraryManagerRuntime@Peer@EapLm@@UEAA_NAEAU_EAP_METHOD_INFO@@W4EapMethodTypeOverrideType@EapMethodTypeOverrideValue@3@AEBVRegistryKey@@@Z`
- size: `465`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a90`
- `0x180009844`
- `0x180009b98`
- `0x180009dc4`
- `0x18000a0f4`
- `0x1800109a0`
- `0x180010aa8`
- `0x1800113a0`
- `0x1800118e8`
- `0x180011908`
- `0x1800119d4`
- `0x18001be40`
- `0x18001c0fc`

## string_xrefs

- `0x180011411`: `PeerDllPath`

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
  v21 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v23 = EapLm::BaseEapLibraryManager::ValidateKey(v22, a4, v21);
  v28 = 1;
  if ( v23 == 1 )
  {
    if ( (byte_18004E841 & 2) != 0 )
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
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v31);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v32);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v33);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v30);
  return v28;
}

```

## disassembly

```asm
0x1800113a0  mov     [rsp+arg_0], rbx
0x1800113a5  push    rdi
0x1800113a6  sub     rsp, 0E0h
0x1800113ad  mov     rax, cs:__security_cookie
0x1800113b4  xor     rax, rsp
0x1800113b7  mov     [rsp+0E8h+var_18], rax
0x1800113bf  mov     rdi, r9
0x1800113c2  mov     rbx, rdx
0x1800113c5  call    ?IsValidMethod@BaseEapLibraryManager@EapLm@@MEAA_NAEAU_EAP_METHOD_INFO@@W4EapMethodTypeOverrideType@EapMethodTypeOverrideValue@2@@Z; EapLm::BaseEapLibraryManager::IsValidMethod(_EAP_METHOD_INFO &,EapLm::EapMethodTypeOverrideValue::EapMethodTypeOverrideType)
0x1800113ca  test    al, al
0x1800113cc  jz      loc_18001154E
0x1800113d2  lea     rcx, [rsp+0E8h+var_A8]
0x1800113d7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x1800113dc  nop
0x1800113dd  lea     rcx, [rsp+0E8h+var_48]
0x1800113e5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x1800113ea  nop
0x1800113eb  lea     rcx, [rsp+0E8h+var_68]
0x1800113f3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x1800113f8  nop
0x1800113f9  lea     rcx, [rsp+0E8h+var_88]
0x1800113fe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x180011403  nop
0x180011404  cmp     dword ptr [rbx+0Ch], 0
0x180011408  lea     rcx, aPath; "Path"
0x18001140f  jz      short loc_180011418
0x180011411  lea     rcx, aPeerdllpath; "PeerDllPath"
0x180011418  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18001141d  mov     r8, rax
0x180011420  mov     rdx, rcx
0x180011423  lea     rcx, [rsp+0E8h+var_A8]
0x180011428  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001142d  lea     rcx, [rsp+0E8h+var_A8]
0x180011432  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180011437  mov     r8, rax
0x18001143a  mov     rdx, rdi
0x18001143d  call    ?ValidateKey@BaseEapLibraryManager@EapLm@@IEAA?AW4ResultType@ResultValue@2@AEBVRegistryKey@@PEB_W@Z; EapLm::BaseEapLibraryManager::ValidateKey(RegistryKey const &,wchar_t const *)
0x180011442  mov     edi, 1
0x180011447  cmp     eax, edi
0x180011449  jz      short loc_1800114BD
0x18001144b  test    cs:Microsoft_Windows_EapHostEnableBits, dil
0x180011452  jz      short loc_180011471
0x180011454  mov     eax, [rbx+8]
0x180011457  mov     [rsp+0E8h+var_B8], eax
0x18001145b  mov     eax, [rbx+4]
0x18001145e  mov     [rsp+0E8h+var_C0], eax
0x180011462  mov     eax, [rbx+0Ch]
0x180011465  mov     dword ptr [rsp+0E8h+var_C8], eax
0x180011469  mov     r9b, [rbx]
0x18001146c  call    McTemplateU0suqqq_EtwEventWriteTransfer
0x180011471  lea     rax, WPP_GLOBAL_Control
0x180011478  mov     rcx, cs:WPP_GLOBAL_Control
0x18001147f  cmp     rcx, rax
0x180011482  jz      short loc_1800114B8
0x180011484  test    [rcx+1Ch], dil
0x180011488  jz      short loc_1800114B8
0x18001148a  movzx   r9d, byte ptr [rbx]
0x18001148e  mov     edx, 0Ah
0x180011493  mov     eax, [rbx+8]
0x180011496  mov     [rsp+0E8h+var_B8], eax
0x18001149a  mov     eax, [rbx+4]
0x18001149d  mov     [rsp+0E8h+var_C0], eax
0x1800114a1  mov     eax, [rbx+0Ch]
0x1800114a4  mov     dword ptr [rsp+0E8h+var_C8], eax
0x1800114a8  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x1800114af  mov     rcx, [rcx+10h]
0x1800114b3  call    WPP_SF_dddd
0x1800114b8  xor     dil, dil
0x1800114bb  jmp     short loc_180011518
0x1800114bd  test    cs:byte_18004E841, 2
0x1800114c4  jz      short loc_1800114E9
0x1800114c6  lea     rax, [rsp+0E8h+var_28]
0x1800114ce  mov     [rsp+0E8h+var_C8], rax
0x1800114d3  mov     r9d, edi
0x1800114d6  lea     rdx, PeerRegKeyValidationSuccess
0x1800114dd  lea     rcx, eaphost_Context
0x1800114e4  call    McGenEventWrite_EtwEventWriteTransfer
0x1800114e9  lea     rax, WPP_GLOBAL_Control
0x1800114f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114f7  cmp     rcx, rax
0x1800114fa  jz      short loc_180011518
0x1800114fc  test    byte ptr [rcx+1Ch], 4
0x180011500  jz      short loc_180011518
0x180011502  mov     edx, 0Bh
0x180011507  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x18001150e  mov     rcx, [rcx+10h]
0x180011512  call    WPP_SF_
0x180011517  nop
0x180011518  lea     rcx, [rsp+0E8h+var_88]
0x18001151d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180011522  nop
0x180011523  lea     rcx, [rsp+0E8h+var_68]
0x18001152b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180011530  nop
0x180011531  lea     rcx, [rsp+0E8h+var_48]
0x180011539  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001153e  nop
0x18001153f  lea     rcx, [rsp+0E8h+var_A8]
0x180011544  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180011549  mov     al, dil
0x18001154c  jmp     short loc_180011550
0x18001154e  xor     al, al
0x180011550  mov     rcx, [rsp+0E8h+var_18]
0x180011558  xor     rcx, rsp; StackCookie
0x18001155b  call    __security_check_cookie
0x180011560  mov     rbx, [rsp+0E8h+arg_0]
0x180011568  add     rsp, 0E0h
0x18001156f  pop     rdi
0x180011570  retn
```
