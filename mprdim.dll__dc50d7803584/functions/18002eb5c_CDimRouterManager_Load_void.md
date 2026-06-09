# CDimRouterManager::Load(void)

- ea: `0x18002eb5c`
- end: `0x18002ed75`
- name: `?Load@CDimRouterManager@@QEAAKXZ`
- size: `537`
- prototype: `unsigned int __fastcall(CDimRouterManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180011eb0`

## callees

- `0x18000def0`
- `0x18002dccc`
- `0x18002e19c`
- `0x18002eaec`
- `0x18002eb5c`
- `0x18002f140`
- `0x18002f7c8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ed01`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ed0d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ed19`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ed2b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ed37`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ed43`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ed01`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ed0d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ed19`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ed2b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ed37`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ed43`
- `ADVAPI32!RegCloseKey` at `0x18002ed52`
- `ADVAPI32!RegCloseKey` at `0x18002ed52`

## string_xrefs

- `0x18002ec88`: `CDimRouterManager::Load: ProtocolId %d is already installed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDimRouterManager::Load(CDimRouterManager *this)
{
  CDimRouterManager *v1; // rsi
  unsigned int RMStateEvent; // ebx
  __int64 v3; // rcx
  DWORD i; // edi
  unsigned int RouterInfoFromRegistryKey; // eax
  void *v6; // rcx
  unsigned int v8; // [rsp+50h] [rbp-B0h] BYREF
  void *v9; // [rsp+58h] [rbp-A8h] BYREF
  void *v10; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR *v11; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v12; // [rsp+70h] [rbp-90h] BYREF
  DWORD v13; // [rsp+74h] [rbp-8Ch] BYREF
  int v14; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  int v16; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v17[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v1 = g_pCDimRouterManager;
  hKey = 0;
  v12 = 0;
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  RMStateEvent = CDimRouterManager::CreateRMStateEvent(v1);
  if ( !RMStateEvent )
  {
    RMStateEvent = CDimRouterManager::RegOpenRouterManagerKey(&hKey, &v12);
    if ( !RMStateEvent )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= v12 )
          goto LABEL_17;
        v8 = 0;
        v13 = 0;
        v14 = 0;
        v11 = 0;
        v10 = 0;
        v9 = 0;
        RouterInfoFromRegistryKey = CDimRouterManager::GetRouterInfoFromRegistryKey(
                                      v3,
                                      hKey,
                                      i,
                                      (BYTE *)&v8,
                                      (__int64 *)&v11,
                                      &v9,
                                      (LPDWORD)&v14,
                                      &v10,
                                      &v13);
        RMStateEvent = RouterInfoFromRegistryKey;
        if ( RouterInfoFromRegistryKey )
          break;
        if ( CDimRouterManager::IsTransportAvailable(v1, v8) )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
          {
            LOWORD(v16) = 0;
            FormatRRASErrorString(&v16, L"CDimRouterManager::Load: ProtocolId %d is already installed", v8);
            if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceInfo, &v16);
          }
LABEL_13:
          v6 = v9;
          goto LABEL_14;
        }
        RMStateEvent = CDimRouterManager::StartRouter((__int64)v1, v8, (LPCWSTR *)&v11, &v9, v14, &v10, v13);
        v6 = v9;
        if ( RMStateEvent )
          goto LABEL_16;
LABEL_14:
        operator delete[](v6);
        operator delete[](v10);
        operator delete[](v11);
      }
      if ( RouterInfoFromRegistryKey != 50 )
      {
        v6 = v9;
LABEL_16:
        operator delete[](v6);
        operator delete[](v10);
        operator delete[](v11);
        goto LABEL_17;
      }
      goto LABEL_13;
    }
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  return RMStateEvent;
}

```

## disassembly

```asm
0x18002eb5c  push    rbp
0x18002eb5e  push    rbx
0x18002eb5f  push    rsi
0x18002eb60  push    rdi
0x18002eb61  lea     rbp, [rsp-7A8h]
0x18002eb69  sub     rsp, 8A8h
0x18002eb70  mov     rax, cs:__security_cookie
0x18002eb77  xor     rax, rsp
0x18002eb7a  mov     [rbp+7C0h+var_30], rax
0x18002eb81  mov     rsi, cs:?g_pCDimRouterManager@@3PEAVCDimRouterManager@@EA; CDimRouterManager * g_pCDimRouterManager
0x18002eb88  mov     [rbp+7C0h+hKey], 0
0x18002eb90  mov     [rsp+8C0h+var_850], 0
0x18002eb98  xor     eax, eax
0x18002eb9a  mov     [rbp+7C0h+var_830], eax
0x18002eb9d  xor     edx, edx; Val
0x18002eb9f  mov     r8d, 7FCh; Size
0x18002eba5  lea     rcx, [rbp+7C0h+var_82C]; void *
0x18002eba9  call    memset_0
0x18002ebae  mov     rcx, rsi; this
0x18002ebb1  call    ?CreateRMStateEvent@CDimRouterManager@@AEAAKXZ; CDimRouterManager::CreateRMStateEvent(void)
0x18002ebb6  mov     ebx, eax
0x18002ebb8  test    eax, eax
0x18002ebba  jnz     loc_18002ED49
0x18002ebc0  lea     rdx, [rsp+8C0h+var_850]; unsigned int *
0x18002ebc5  lea     rcx, [rbp+7C0h+hKey]; HKEY *
0x18002ebc9  call    ?RegOpenRouterManagerKey@CDimRouterManager@@CAKAEAPEAUHKEY__@@AEAK@Z; CDimRouterManager::RegOpenRouterManagerKey(HKEY__ * &,ulong &)
0x18002ebce  mov     ebx, eax
0x18002ebd0  test    eax, eax
0x18002ebd2  jnz     loc_18002ED49
0x18002ebd8  xor     edi, edi
0x18002ebda  cmp     edi, [rsp+8C0h+var_850]
0x18002ebde  jnb     loc_18002ED49
0x18002ebe4  mov     [rsp+8C0h+var_870], 0
0x18002ebec  mov     [rsp+8C0h+var_84C], 0
0x18002ebf4  mov     [rsp+8C0h+var_848], 0
0x18002ebfc  mov     [rsp+8C0h+var_858], 0
0x18002ec05  mov     [rsp+8C0h+var_860], 0
0x18002ec0e  mov     [rsp+8C0h+var_868], 0
0x18002ec17  lea     rax, [rsp+8C0h+var_84C]
0x18002ec1c  mov     [rsp+8C0h+var_880], rax
0x18002ec21  lea     rax, [rsp+8C0h+var_860]
0x18002ec26  mov     [rsp+8C0h+var_888], rax
0x18002ec2b  lea     rax, [rsp+8C0h+var_848]
0x18002ec30  mov     [rsp+8C0h+var_890], rax
0x18002ec35  lea     rax, [rsp+8C0h+var_868]
0x18002ec3a  mov     [rsp+8C0h+var_898], rax
0x18002ec3f  lea     rax, [rsp+8C0h+var_858]
0x18002ec44  mov     [rsp+8C0h+var_8A0], rax
0x18002ec49  lea     r9, [rsp+8C0h+var_870]
0x18002ec4e  mov     r8d, edi
0x18002ec51  mov     rdx, [rbp+7C0h+hKey]
0x18002ec55  call    ?GetRouterInfoFromRegistryKey@CDimRouterManager@@AEAAKPEAUHKEY__@@KAEAKAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@AEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@4@131@Z; CDimRouterManager::GetRouterInfoFromRegistryKey(HKEY__ *,ulong,ulong &,std::unique_ptr<ushort [0]> &,std::unique_ptr<uchar [0]> &,ulong &,std::unique_ptr<uchar [0]> &,ulong &)
0x18002ec5a  mov     ebx, eax
0x18002ec5c  test    eax, eax
0x18002ec5e  jnz     loc_18002ECF7
0x18002ec64  mov     edx, [rsp+8C0h+var_870]; unsigned int
0x18002ec68  mov     rcx, rsi; this
0x18002ec6b  call    ?IsTransportAvailable@CDimRouterManager@@QEAA_NK@Z; CDimRouterManager::IsTransportAvailable(ulong)
0x18002ec70  test    al, al
0x18002ec72  jz      short loc_18002ECBA
0x18002ec74  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18002ec7b  jz      short loc_18002ECFC
0x18002ec7d  xor     eax, eax
0x18002ec7f  mov     word ptr [rbp+7C0h+var_830], ax
0x18002ec83  mov     r8d, [rsp+8C0h+var_870]
0x18002ec88  lea     rdx, aCdimroutermana_1; "CDimRouterManager::Load: ProtocolId %d "...
0x18002ec8f  lea     rcx, [rbp+7C0h+var_830]
0x18002ec93  call    FormatRRASErrorString
0x18002ec98  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18002ec9f  jz      short loc_18002ECFC
0x18002eca1  lea     r8, [rbp+7C0h+var_830]
0x18002eca5  lea     rdx, RasDimTraceInfo
0x18002ecac  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002ecb3  call    McTemplateU0z_EventWriteTransfer
0x18002ecb8  jmp     short loc_18002ECFC
0x18002ecba  mov     eax, [rsp+8C0h+var_84C]
0x18002ecbe  mov     dword ptr [rsp+8C0h+var_890], eax
0x18002ecc2  lea     rax, [rsp+8C0h+var_860]
0x18002ecc7  mov     [rsp+8C0h+var_898], rax
0x18002eccc  mov     eax, [rsp+8C0h+var_848]
0x18002ecd0  mov     dword ptr [rsp+8C0h+var_8A0], eax
0x18002ecd4  lea     r9, [rsp+8C0h+var_868]
0x18002ecd9  lea     r8, [rsp+8C0h+var_858]
0x18002ecde  mov     edx, [rsp+8C0h+var_870]
0x18002ece2  mov     rcx, rsi
0x18002ece5  call    ?StartRouter@CDimRouterManager@@AEAAKKAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@AEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@3@K1K@Z; CDimRouterManager::StartRouter(ulong,std::unique_ptr<ushort [0]> &,std::unique_ptr<uchar [0]> &,ulong,std::unique_ptr<uchar [0]> &,ulong)
0x18002ecea  mov     ebx, eax
0x18002ecec  mov     rcx, [rsp+8C0h+var_868]
0x18002ecf1  test    eax, eax
0x18002ecf3  jnz     short loc_18002ED2B
0x18002ecf5  jmp     short loc_18002ED01
0x18002ecf7  cmp     eax, 32h ; '2'
0x18002ecfa  jnz     short loc_18002ED26
0x18002ecfc  mov     rcx, [rsp+8C0h+var_868]
0x18002ed01  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002ed07  nop
0x18002ed08  mov     rcx, [rsp+8C0h+var_860]
0x18002ed0d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002ed13  nop
0x18002ed14  mov     rcx, [rsp+8C0h+var_858]
0x18002ed19  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002ed1f  inc     edi
0x18002ed21  jmp     loc_18002EBDA
0x18002ed26  mov     rcx, [rsp+8C0h+var_868]
0x18002ed2b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002ed31  nop
0x18002ed32  mov     rcx, [rsp+8C0h+var_860]
0x18002ed37  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002ed3d  nop
0x18002ed3e  mov     rcx, [rsp+8C0h+var_858]
0x18002ed43  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002ed49  mov     rcx, [rbp+7C0h+hKey]; hKey
0x18002ed4d  test    rcx, rcx
0x18002ed50  jz      short loc_18002ED58
0x18002ed52  call    cs:__imp_RegCloseKey
0x18002ed58  mov     eax, ebx
0x18002ed5a  mov     rcx, [rbp+7C0h+var_30]
0x18002ed61  xor     rcx, rsp; StackCookie
0x18002ed64  call    __security_check_cookie
0x18002ed69  add     rsp, 8A8h
0x18002ed70  pop     rdi
0x18002ed71  pop     rsi
0x18002ed72  pop     rbx
0x18002ed73  pop     rbp
0x18002ed74  retn
```
