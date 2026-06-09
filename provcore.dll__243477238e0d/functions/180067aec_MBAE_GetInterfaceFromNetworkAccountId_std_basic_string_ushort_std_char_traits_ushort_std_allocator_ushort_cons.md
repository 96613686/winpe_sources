# MBAE::GetInterfaceFromNetworkAccountId(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_GUID &)

- ea: `0x180067aec`
- end: `0x180067bed`
- name: `?GetInterfaceFromNetworkAccountId@MBAE@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_GUID@@@Z`
- size: `257`
- prototype: `HRESULT __fastcall(const std::wstring *MbaeNetworkAccountId, _GUID *InterfaceGuid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005ffd0`

## callees

- `0x180002790`
- `0x180011844`
- `0x180012770`
- `0x180067aec`
- `0x180067ca0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180067b71`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180067b71`
- `MobileNetworking!GetNetworkInterfaceIdBoundToAccountId` at `0x180067b25`
- `MobileNetworking!GetNetworkInterfaceIdBoundToAccountId` at `0x180067b25`

## pseudocode

```c
__int64 __fastcall MBAE::GetInterfaceFromNetworkAccountId(
        const std::wstring *MbaeNetworkAccountId,
        _GUID *InterfaceGuid)
{
  const wchar_t *v3; // rax
  int NetworkInterfaceIdBoundToAccountId; // eax
  unsigned __int16 v5; // dx
  const _GUID *v6; // r8
  int v7; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v8; // rcx
  HRESULT v9; // eax
  wchar_t szMbnInterfaceId[264]; // [rsp+30h] [rbp-228h] BYREF

  v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&MbaeNetworkAccountId->_Mypair._Myval2);
  NetworkInterfaceIdBoundToAccountId = GetNetworkInterfaceIdBoundToAccountId(v3, 260, szMbnInterfaceId);
  v7 = NetworkInterfaceIdBoundToAccountId;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->Control.Logger,
      0xDu,
      WPP_f06af02949b434cddba45b7b6c1c9557_Traceguids,
      NetworkInterfaceIdBoundToAccountId);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v7 >= 0 )
  {
    v9 = CLSIDFromString(szMbnInterfaceId, InterfaceGuid);
    v7 = v9;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      return (unsigned int)v7;
    if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xEu, WPP_f06af02949b434cddba45b7b6c1c9557_Traceguids, v9);
      v8 = WPP_GLOBAL_Control;
    }
  }
  if ( v8 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v8->ReserveSpace[28] & 8) != 0 )
    WPP_SF_d_guid_(v8->Control.Logger, v5, v6, v7, InterfaceGuid);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180067aec  mov     [rsp+arg_10], rbx
0x180067af1  mov     [rsp+arg_18], rsi
0x180067af6  push    rdi
0x180067af7  sub     rsp, 250h
0x180067afe  mov     rax, cs:__security_cookie
0x180067b05  xor     rax, rsp
0x180067b08  mov     [rsp+258h+var_18], rax
0x180067b10  mov     rdi, InterfaceGuid
0x180067b13  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180067b18  mov     MbaeNetworkAccountId, rax
0x180067b1b  lea     r8, [rsp+258h+szMbnInterfaceId]
0x180067b20  mov     edx, 104h
0x180067b25  call    cs:__imp_GetNetworkInterfaceIdBoundToAccountId
0x180067b2b  mov     ebx, eax
0x180067b2d  mov     MbaeNetworkAccountId, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180067b34  lea     rsi, WPP_GLOBAL_Control
0x180067b3b  cmp     MbaeNetworkAccountId, rsi
0x180067b3e  jz      short loc_180067B65
0x180067b40  test    byte ptr [MbaeNetworkAccountId+1Ch], 10h
0x180067b44  jz      short loc_180067B65
0x180067b46  mov     MbaeNetworkAccountId, [MbaeNetworkAccountId+10h]; Logger
0x180067b4a  lea     r8, WPP_f06af02949b434cddba45b7b6c1c9557_Traceguids; TraceGuid
0x180067b51  mov     edx, 0Dh; id
0x180067b56  mov     r9d, eax; _a1
0x180067b59  call    WPP_SF_d
0x180067b5e  mov     MbaeNetworkAccountId, cs:WPP_GLOBAL_Control
0x180067b65  test    ebx, ebx
0x180067b67  js      short loc_180067BAA
0x180067b69  mov     InterfaceGuid, rdi; pclsid
0x180067b6c  lea     MbaeNetworkAccountId, [rsp+258h+szMbnInterfaceId]; lpsz
0x180067b71  call    cs:__imp_CLSIDFromString
0x180067b77  mov     ebx, eax
0x180067b79  mov     MbaeNetworkAccountId, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180067b80  cmp     MbaeNetworkAccountId, rsi
0x180067b83  jz      short loc_180067BC6
0x180067b85  test    byte ptr [MbaeNetworkAccountId+1Ch], 10h
0x180067b89  jz      short loc_180067BAA
0x180067b8b  mov     MbaeNetworkAccountId, [MbaeNetworkAccountId+10h]; Logger
0x180067b8f  lea     r8, WPP_f06af02949b434cddba45b7b6c1c9557_Traceguids; TraceGuid
0x180067b96  mov     edx, 0Eh; id
0x180067b9b  mov     r9d, eax; _a1
0x180067b9e  call    WPP_SF_d
0x180067ba3  mov     MbaeNetworkAccountId, cs:WPP_GLOBAL_Control
0x180067baa  cmp     MbaeNetworkAccountId, rsi; __annotation("TMF:",
0x180067bad  jz      short loc_180067BC6
0x180067baf  test    byte ptr [MbaeNetworkAccountId+1Ch], 8
0x180067bb3  jz      short loc_180067BC6
0x180067bb5  mov     MbaeNetworkAccountId, [MbaeNetworkAccountId+10h]; Logger
0x180067bb9  mov     r9d, ebx; Logger
0x180067bbc  mov     [rsp+258h+id], rdi; id
0x180067bc1  call    WPP_SF_d_guid_
0x180067bc6  mov     eax, ebx
0x180067bc8  mov     MbaeNetworkAccountId, [rsp+258h+var_18]
0x180067bd0  xor     MbaeNetworkAccountId, rsp; StackCookie
0x180067bd3  call    __security_check_cookie
0x180067bd8  lea     r11, [rsp+258h+var_8]
0x180067be0  mov     rbx, [r11+20h]
0x180067be4  mov     rsi, [r11+28h]
0x180067be8  mov     rsp, r11
0x180067beb  pop     rdi
0x180067bec  retn
```
