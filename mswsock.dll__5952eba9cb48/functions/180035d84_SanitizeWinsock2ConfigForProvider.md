# SanitizeWinsock2ConfigForProvider

- ea: `0x180035d84`
- end: `0x180035f43`
- name: `SanitizeWinsock2ConfigForProvider`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180032294`

## callees

- `0x1800327a8`
- `0x1800327f0`
- `0x180033500`
- `0x18003396c`
- `0x180035d84`
- `0x18003ae8c`

## import_xrefs

- `WS2_32!WSCDeinstallProviderEx` at `0x180035e0a`
- `WS2_32!WSCDeinstallProviderEx` at `0x180035eba`
- `WS2_32!WSCDeinstallProviderEx` at `0x180035e0a`
- `WS2_32!WSCDeinstallProviderEx` at `0x180035eba`

## string_xrefs

- `0x180035e25`: `Deinstall failed for the native catalog because provider did not exist; continuing on`
- `0x180035ed5`: `Deinstall failed for the WOW catalog because provider did not exist; continuing on`

## pseudocode

```c
__int64 __fastcall SanitizeWinsock2ConfigForProvider(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // ecx
  unsigned int v7; // eax
  unsigned int v8; // ecx
  unsigned int v9; // eax
  int v11; // [rsp+30h] [rbp-18h] BYREF
  int v12; // [rsp+34h] [rbp-14h]
  __int64 v13; // [rsp+38h] [rbp-10h]
  unsigned int v14; // [rsp+78h] [rbp+30h] BYREF

  v14 = 0;
  if ( *(_DWORD *)a2 != 1297109836 )
  {
    *(_DWORD *)a2 = 1297109836;
    MwcGetProtoArray(0, a2 + 8, a2 + 16, a2 + 20, a3);
    if ( ((*(_DWORD *)(a3 + 4) - 2) & 0xFFFFFFFD) == 0 )
    {
      v11 = *(_DWORD *)a3;
      v13 = *(_QWORD *)(a3 + 8);
      LOBYTE(v6) = 1;
      v12 = 4;
      MwcGetProtoArray(v6, a2 + 24, a2 + 32, a2 + 36, (__int64)&v11);
    }
  }
  if ( (unsigned int)WSCDeinstallProviderEx(a1, &v14, a3) == -1 )
  {
    v7 = v14;
    if ( v14 == 10014 )
    {
      LogMsg(L"Deinstall failed for the native catalog because provider did not exist; continuing on");
    }
    else
    {
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        WPP_SF_d(1025, 49, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, v14);
        v7 = v14;
      }
      LogError(v7, L"Cannot sanitize provider in the native catalog; continuing anyway");
    }
    v8 = 0;
    v14 = 0;
  }
  else
  {
    v8 = 0;
    v14 = 0;
    if ( *(_DWORD *)(a2 + 20) )
    {
      MwcMarkRemovedProtocols(a1, *(_QWORD *)(a2 + 8), *(unsigned int *)(a2 + 16));
      v8 = v14;
    }
  }
  if ( ((*(_DWORD *)(a3 + 4) - 2) & 0xFFFFFFFD) == 0 )
  {
    v11 = *(_DWORD *)a3;
    v13 = *(_QWORD *)(a3 + 8);
    v12 = 4;
    if ( (unsigned int)WSCDeinstallProviderEx(a1, &v14, &v11) == -1 )
    {
      v9 = v14;
      if ( v14 == 10014 )
      {
        LogMsg(L"Deinstall failed for the WOW catalog because provider did not exist; continuing on");
      }
      else
      {
        if ( (xmmword_180063D60 & 2) != 0 )
        {
          WPP_SF_d(1025, 50, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, v14);
          v9 = v14;
        }
        LogError(v9, L"Cannot sanitize provider in the WOW catalog; continuing anyway");
      }
      return 0;
    }
    else
    {
      v8 = 0;
      v14 = 0;
      if ( *(_DWORD *)(a2 + 36) )
      {
        MwcMarkRemovedProtocols(a1, *(_QWORD *)(a2 + 24), *(unsigned int *)(a2 + 32));
        return v14;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180035d84  push    rbp
0x180035d86  push    rbx
0x180035d87  push    rsi
0x180035d88  push    rdi
0x180035d89  mov     rbp, rsp
0x180035d8c  sub     rsp, 48h
0x180035d90  mov     eax, 4D50534Ch
0x180035d95  mov     [rbp+arg_8], 0
0x180035d9c  mov     rdi, r8
0x180035d9f  mov     rbx, rdx
0x180035da2  mov     rsi, rcx
0x180035da5  cmp     [rdx], eax
0x180035da7  jz      short loc_180035E00
0x180035da9  mov     [rdx], eax
0x180035dab  lea     r9, [rdx+14h]
0x180035daf  lea     r8, [rdx+10h]
0x180035db3  mov     [rsp+48h+var_28], rdi
0x180035db8  add     rdx, 8
0x180035dbc  xor     ecx, ecx
0x180035dbe  call    MwcGetProtoArray
0x180035dc3  mov     eax, [rdi+4]
0x180035dc6  sub     eax, 2
0x180035dc9  test    eax, 0FFFFFFFDh
0x180035dce  jnz     short loc_180035E00
0x180035dd0  mov     eax, [rdi]
0x180035dd2  lea     r9, [rbx+24h]
0x180035dd6  mov     [rbp+var_18], eax
0x180035dd9  lea     r8, [rbx+20h]
0x180035ddd  mov     rax, [rdi+8]
0x180035de1  lea     rdx, [rbx+18h]
0x180035de5  mov     [rbp+var_10], rax
0x180035de9  mov     cl, 1
0x180035deb  lea     rax, [rbp+var_18]
0x180035def  mov     [rbp+var_14], 4
0x180035df6  mov     [rsp+48h+var_28], rax
0x180035dfb  call    MwcGetProtoArray
0x180035e00  mov     r8, rdi
0x180035e03  lea     rdx, [rbp+arg_8]
0x180035e07  mov     rcx, rsi
0x180035e0a  call    cs:__imp_WSCDeinstallProviderEx
0x180035e11  nop     dword ptr [rax+rax+00h]
0x180035e16  cmp     eax, 0FFFFFFFFh
0x180035e19  jnz     short loc_180035E6D
0x180035e1b  mov     eax, [rbp+arg_8]
0x180035e1e  cmp     eax, 271Eh
0x180035e23  jnz     short loc_180035E33
0x180035e25  lea     rcx, aDeinstallFaile_0; "Deinstall failed for the native catalog"...
0x180035e2c  call    LogMsg
0x180035e31  jmp     short loc_180035E66
0x180035e33  test    byte ptr cs:xmmword_180063D60, 2
0x180035e3a  jz      short loc_180035E58
0x180035e3c  mov     edx, 31h ; '1'
0x180035e41  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180035e48  mov     ecx, 401h
0x180035e4d  mov     r9d, eax
0x180035e50  call    WPP_SF_d
0x180035e55  mov     eax, [rbp+arg_8]
0x180035e58  lea     rdx, aCannotSanitize_0; "Cannot sanitize provider in the native "...
0x180035e5f  mov     ecx, eax
0x180035e61  call    LogError
0x180035e66  xor     ecx, ecx
0x180035e68  mov     [rbp+arg_8], ecx
0x180035e6b  jmp     short loc_180035E8A
0x180035e6d  xor     ecx, ecx
0x180035e6f  mov     [rbp+arg_8], ecx
0x180035e72  cmp     [rbx+14h], ecx
0x180035e75  jbe     short loc_180035E8A
0x180035e77  mov     r8d, [rbx+10h]
0x180035e7b  mov     rcx, rsi
0x180035e7e  mov     rdx, [rbx+8]
0x180035e82  call    MwcMarkRemovedProtocols
0x180035e87  mov     ecx, [rbp+arg_8]
0x180035e8a  mov     eax, [rdi+4]
0x180035e8d  sub     eax, 2
0x180035e90  test    eax, 0FFFFFFFDh
0x180035e95  jnz     loc_180035F37
0x180035e9b  mov     eax, [rdi]
0x180035e9d  lea     r8, [rbp+var_18]
0x180035ea1  mov     [rbp+var_18], eax
0x180035ea4  lea     rdx, [rbp+arg_8]
0x180035ea8  mov     rax, [rdi+8]
0x180035eac  mov     rcx, rsi
0x180035eaf  mov     [rbp+var_10], rax
0x180035eb3  mov     [rbp+var_14], 4
0x180035eba  call    cs:__imp_WSCDeinstallProviderEx
0x180035ec1  nop     dword ptr [rax+rax+00h]
0x180035ec6  cmp     eax, 0FFFFFFFFh
0x180035ec9  jnz     short loc_180035F1A
0x180035ecb  mov     eax, [rbp+arg_8]
0x180035ece  cmp     eax, 271Eh
0x180035ed3  jnz     short loc_180035EE3
0x180035ed5  lea     rcx, aDeinstallFaile; "Deinstall failed for the WOW catalog be"...
0x180035edc  call    LogMsg
0x180035ee1  jmp     short loc_180035F16
0x180035ee3  test    byte ptr cs:xmmword_180063D60, 2
0x180035eea  jz      short loc_180035F08
0x180035eec  mov     edx, 32h ; '2'
0x180035ef1  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180035ef8  mov     ecx, 401h
0x180035efd  mov     r9d, eax
0x180035f00  call    WPP_SF_d
0x180035f05  mov     eax, [rbp+arg_8]
0x180035f08  lea     rdx, aCannotSanitize; "Cannot sanitize provider in the WOW cat"...
0x180035f0f  mov     ecx, eax
0x180035f11  call    LogError
0x180035f16  xor     ecx, ecx
0x180035f18  jmp     short loc_180035F37
0x180035f1a  xor     ecx, ecx
0x180035f1c  mov     [rbp+arg_8], ecx
0x180035f1f  cmp     [rbx+24h], ecx
0x180035f22  jbe     short loc_180035F37
0x180035f24  mov     r8d, [rbx+20h]
0x180035f28  mov     rcx, rsi
0x180035f2b  mov     rdx, [rbx+18h]
0x180035f2f  call    MwcMarkRemovedProtocols
0x180035f34  mov     ecx, [rbp+arg_8]
0x180035f37  mov     eax, ecx
0x180035f39  add     rsp, 48h
0x180035f3d  pop     rdi
0x180035f3e  pop     rsi
0x180035f3f  pop     rbx
0x180035f40  pop     rbp
0x180035f41  retn
```
