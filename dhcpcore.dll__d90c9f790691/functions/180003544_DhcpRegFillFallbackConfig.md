# DhcpRegFillFallbackConfig

- ea: `0x180003544`
- end: `0x18000390a`
- name: `DhcpRegFillFallbackConfig`
- size: `966`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003910`
- `0x1800227ac`
- `0x180026ca0`
- `0x180026d54`

## callees

- `0x180003544`
- `0x180003b10`
- `0x1800057f0`
- `0x180006440`
- `0x1800069d0`
- `0x180007190`
- `0x180009038`
- `0x180009108`
- `0x180009580`
- `0x18000a580`
- `0x18000b650`
- `0x18000bba0`
- `0x18001cef0`
- `0x18001d826`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004dd28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800037bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800037bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003735`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003735`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800035c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003712`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800035c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003712`

## string_xrefs

- `0x1800035b5`: `ActiveConfigurations`
- `0x180003706`: `ActiveConfigurations`
- `0x1800035f5`: `OSDATA\Networking\Dhcp\Client4\Configurations\`
- `0x1800035ee`: `System\CurrentControlSet\Services\Dhcp\Configurations\`
- `0x180003643`: `System\CurrentControlSet\Services\Dhcp\Configurations\`
- `0x180003658`: `System\CurrentControlSet\Services\Dhcp\Configurations\`

## pseudocode

```c
__int64 __fastcall DhcpRegFillFallbackConfig(__int64 a1)
{
  LSTATUS v2; // eax
  __int64 v3; // rcx
  __int64 v4; // r9
  unsigned int v5; // r14d
  unsigned int v6; // ebx
  BOOL IsWCOSSystem; // eax
  const wchar_t *v8; // rbx
  const wchar_t *v9; // rdx
  __int64 v10; // rsi
  __int64 v11; // rcx
  __int64 v12; // rcx
  wchar_t *v13; // r15
  const wchar_t *v14; // r12
  BOOL v15; // eax
  __int64 v16; // rcx
  int v17; // r8d
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // rcx
  unsigned int OptionCache; // eax
  __int64 v22; // rcx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v27[112]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v28; // [rsp+B0h] [rbp-50h]
  LPVOID v29[2]; // [rsp+180h] [rbp+80h] BYREF

  phkResult = 0;
  cbData = 0;
  Type = 0;
  memset_0(v27, 0, 0x140u);
  *(_DWORD *)(a1 + 812) = 0;
  v2 = RegQueryValueExW(*(HKEY *)(a1 + 728), L"ActiveConfigurations", 0, &Type, 0, &cbData);
  v4 = Type;
  v5 = 30;
  v6 = v2;
  if ( !v2 )
  {
    if ( Type == 7 )
    {
      IsWCOSSystem = DhcpIsWCOSSystem();
      v8 = L"OSDATA\\Networking\\Dhcp\\Client4\\Configurations\\";
      v9 = L"OSDATA\\Networking\\Dhcp\\Client4\\Configurations\\";
      if ( !IsWCOSSystem )
        v9 = L"System\\CurrentControlSet\\Services\\Dhcp\\Configurations\\";
      v10 = -1;
      v11 = -1;
      do
        ++v11;
      while ( v9[v11] );
      v29[0] = DhcpAlloc(cbData + 2LL + 2 * v11);
      v13 = (wchar_t *)v29[0];
      if ( !v29[0] )
      {
        v6 = 8;
LABEL_17:
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_D(1025, 13, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v6);
        if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
          McTemplateU0q_EtwEventWriteTransfer(v12, ErrorFallbackParamsReadFail, v6);
        v18 = v6;
        goto LABEL_49;
      }
      v14 = L"OSDATA\\Networking\\Dhcp\\Client4\\Configurations\\";
      if ( !DhcpIsWCOSSystem() )
        v14 = L"System\\CurrentControlSet\\Services\\Dhcp\\Configurations\\";
      v15 = DhcpIsWCOSSystem();
      v16 = -1;
      if ( !v15 )
        v8 = L"System\\CurrentControlSet\\Services\\Dhcp\\Configurations\\";
      do
        ++v16;
      while ( v8[v16] );
      v6 = StringCbCopyW(v13, cbData + 2LL + 2 * v16, v14);
      if ( (v6 & 0x80000000) == 0 )
      {
        do
          ++v10;
        while ( v13[v10] );
        RegQueryValueExW(*(HKEY *)(a1 + 728), L"ActiveConfigurations", 0, &Type, (LPBYTE)&v13[v10], &cbData);
        v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v13, 0, 0x2000000u, &phkResult);
        v6 = v19;
        if ( v19 )
        {
          if ( (xmmword_1800616A0 & 2) != 0 )
            WPP_SF_D(1025, 12, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v19);
          if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
            McTemplateU0q_EtwEventWriteTransfer(v20, ErrorRegOpenKeyEx, v6);
          TraceLogErrorv4(a1, v6, 30);
        }
        else
        {
          OptionCache = DhcpRegReadOptionCache(a1 + 712, phkResult, L"Options");
          v6 = OptionCache;
          if ( OptionCache )
          {
            if ( (xmmword_1800616A0 & 2) != 0 )
              WPP_SF_D(1025, 11, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, OptionCache);
            if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
              McTemplateU0q_EtwEventWriteTransfer(v22, ErrorDhcpRegReadOptionCache, v6);
            TraceLogErrorv4(a1, v6, 30);
          }
          else
          {
            *(_DWORD *)(a1 + 812) = 1;
          }
          RegCloseKey(phkResult);
        }
      }
      DhcpPunycodeFree(v29);
      goto LABEL_16;
    }
    v6 = 11;
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
  {
    WPP_SF_Dd(1025, 10, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v6, Type);
    v4 = Type;
  }
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
    McTemplateU0qq_EtwEventWriteTransfer(v3, ErrorRegQueryValueEx, v6, v4);
  InitializeTraceElementFromContext(v27, a1, v6, 30);
  v28 = Type;
  TraceLogEx(v27);
  if ( v6 == 2 )
  {
    v6 = 0;
    goto LABEL_44;
  }
LABEL_16:
  if ( v6 )
    goto LABEL_17;
LABEL_44:
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_(1025, 14, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v12, (unsigned int)ErrorFallbackParamsReadSucceeded, v17, 1, (__int64)v29);
  v18 = 0;
  v5 = 31;
LABEL_49:
  TraceLogErrorv4(a1, v18, v5);
  return v6;
}

```

## disassembly

```asm
0x180003544  push    rbp
0x180003546  push    rbx
0x180003547  push    rsi
0x180003548  push    rdi
0x180003549  push    r12
0x18000354b  push    r13
0x18000354d  push    r14
0x18000354f  push    r15
0x180003551  lea     rbp, [rsp-0A8h]
0x180003559  sub     rsp, 1A8h
0x180003560  mov     rax, cs:__security_cookie
0x180003567  xor     rax, rsp
0x18000356a  mov     [rbp+0E0h+var_50], rax
0x180003571  xor     r13d, r13d
0x180003574  mov     rdi, rcx
0x180003577  lea     rcx, [rsp+1E0h+var_1A0]; void *
0x18000357c  mov     [rsp+1E0h+phkResult], r13
0x180003581  xor     edx, edx; Val
0x180003583  mov     [rsp+1E0h+cbData], r13d
0x180003588  mov     r8d, 140h; Size
0x18000358e  mov     [rsp+1E0h+Type], r13d
0x180003593  call    memset_0
0x180003598  lea     rax, [rsp+1E0h+cbData]
0x18000359d  mov     [rdi+32Ch], r13d
0x1800035a4  mov     rcx, [rdi+2D8h]; hKey
0x1800035ab  lea     r9, [rsp+1E0h+Type]; lpType
0x1800035b0  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x1800035b5  lea     rdx, aActiveconfigur; "ActiveConfigurations"
0x1800035bc  xor     r8d, r8d; lpReserved
0x1800035bf  mov     [rsp+1E0h+lpData], r13; lpData
0x1800035c4  call    cs:__imp_RegQueryValueExW
0x1800035ca  mov     r9d, [rsp+1E0h+Type]
0x1800035cf  lea     r14d, [r13+1Eh]
0x1800035d3  mov     ebx, eax
0x1800035d5  test    eax, eax
0x1800035d7  jnz     loc_180003817
0x1800035dd  cmp     r9d, 7
0x1800035e1  jnz     loc_180003812
0x1800035e7  call    DhcpIsWCOSSystem
0x1800035ec  test    eax, eax
0x1800035ee  lea     rcx, pszSrc; "System\\CurrentControlSet\\Services\\Dh"...
0x1800035f5  lea     rbx, aOsdataNetworki_7; "OSDATA\\Networking\\Dhcp\\Client4\\Conf"...
0x1800035fc  mov     rdx, rbx
0x1800035ff  cmovz   rdx, rcx
0x180003603  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003607  mov     rcx, rsi
0x18000360a  inc     rcx
0x18000360d  cmp     [rdx+rcx*2], r13w
0x180003612  jnz     short loc_18000360A
0x180003614  mov     eax, [rsp+1E0h+cbData]
0x180003618  add     rax, 2
0x18000361c  lea     rcx, [rax+rcx*2]
0x180003620  call    DhcpAlloc
0x180003625  mov     [rbp+0E0h+var_60], rax
0x18000362c  mov     r15, rax
0x18000362f  test    rax, rax
0x180003632  jnz     short loc_180003639
0x180003634  lea     ebx, [rax+8]
0x180003637  jmp     short loc_18000369E
0x180003639  call    DhcpIsWCOSSystem
0x18000363e  test    eax, eax
0x180003640  mov     r12, rbx
0x180003643  lea     rax, pszSrc; "System\\CurrentControlSet\\Services\\Dh"...
0x18000364a  cmovz   r12, rax
0x18000364e  call    DhcpIsWCOSSystem
0x180003653  test    eax, eax
0x180003655  mov     rcx, rsi
0x180003658  lea     rax, pszSrc; "System\\CurrentControlSet\\Services\\Dh"...
0x18000365f  cmovz   rbx, rax
0x180003663  inc     rcx
0x180003666  cmp     [rbx+rcx*2], r13w
0x18000366b  jnz     short loc_180003663
0x18000366d  mov     eax, [rsp+1E0h+cbData]
0x180003671  mov     r8, r12; pszSrc
0x180003674  add     rax, 2
0x180003678  lea     rdx, [rax+rcx*2]; cbDest
0x18000367c  mov     rcx, r15; pszDest
0x18000367f  call    StringCbCopyW
0x180003684  mov     ebx, eax
0x180003686  test    eax, eax
0x180003688  jns     short loc_1800036DF
0x18000368a  lea     rcx, [rbp+0E0h+var_60]
0x180003691  call    DhcpPunycodeFree
0x180003696  test    ebx, ebx
0x180003698  jz      loc_18000388B
0x18000369e  test    byte ptr cs:xmmword_1800616A0, 2
0x1800036a5  jz      short loc_1800036C0
0x1800036a7  mov     edx, 0Dh
0x1800036ac  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x1800036b3  mov     ecx, 401h
0x1800036b8  mov     r9d, ebx
0x1800036bb  call    WPP_SF_D
0x1800036c0  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x1800036c7  jz      short loc_1800036D8
0x1800036c9  mov     r8d, ebx
0x1800036cc  lea     rdx, ErrorFallbackParamsReadFail
0x1800036d3  call    McTemplateU0q_EtwEventWriteTransfer
0x1800036d8  mov     edx, ebx
0x1800036da  jmp     loc_1800038DA
0x1800036df  inc     rsi
0x1800036e2  cmp     [r15+rsi*2], r13w
0x1800036e7  jnz     short loc_1800036DF
0x1800036e9  lea     rcx, [rsp+1E0h+cbData]
0x1800036ee  xor     r8d, r8d; lpReserved
0x1800036f1  mov     [rsp+1E0h+lpcbData], rcx; lpcbData
0x1800036f6  lea     rax, [r15+rsi*2]
0x1800036fa  mov     rcx, [rdi+2D8h]; hKey
0x180003701  lea     r9, [rsp+1E0h+Type]; lpType
0x180003706  lea     rdx, aActiveconfigur; "ActiveConfigurations"
0x18000370d  mov     [rsp+1E0h+lpData], rax; lpData
0x180003712  call    cs:__imp_RegQueryValueExW
0x180003718  lea     rax, [rsp+1E0h+phkResult]
0x18000371d  mov     r9d, 2000000h; samDesired
0x180003723  xor     r8d, r8d; ulOptions
0x180003726  mov     [rsp+1E0h+lpData], rax; phkResult
0x18000372b  mov     rdx, r15; lpSubKey
0x18000372e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003735  call    cs:__imp_RegOpenKeyExW
0x18000373b  mov     ebx, eax
0x18000373d  test    eax, eax
0x18000373f  jnz     loc_1800037C6
0x180003745  mov     rdx, [rsp+1E0h+phkResult]
0x18000374a  lea     rcx, [rdi+2C8h]
0x180003751  lea     r8, aOptions; "Options"
0x180003758  call    DhcpRegReadOptionCache
0x18000375d  mov     ebx, eax
0x18000375f  test    eax, eax
0x180003761  jnz     short loc_18000376F
0x180003763  mov     dword ptr [rdi+32Ch], 1
0x18000376d  jmp     short loc_1800037B6
0x18000376f  test    byte ptr cs:xmmword_1800616A0, 2
0x180003776  jz      short loc_180003791
0x180003778  mov     edx, 0Bh
0x18000377d  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180003784  mov     ecx, 401h
0x180003789  mov     r9d, ebx
0x18000378c  call    WPP_SF_D
0x180003791  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x180003798  jz      short loc_1800037A9
0x18000379a  mov     r8d, ebx
0x18000379d  lea     rdx, ErrorDhcpRegReadOptionCache
0x1800037a4  call    McTemplateU0q_EtwEventWriteTransfer
0x1800037a9  mov     r8d, r14d
0x1800037ac  mov     edx, ebx
0x1800037ae  mov     rcx, rdi
0x1800037b1  call    TraceLogErrorv4
0x1800037b6  mov     rcx, [rsp+1E0h+phkResult]; hKey
0x1800037bb  call    cs:__imp_RegCloseKey
0x1800037c1  jmp     loc_18000368A
0x1800037c6  test    byte ptr cs:xmmword_1800616A0, 2
0x1800037cd  jz      short loc_1800037E8
0x1800037cf  mov     edx, 0Ch
0x1800037d4  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x1800037db  mov     ecx, 401h
0x1800037e0  mov     r9d, ebx
0x1800037e3  call    WPP_SF_D
0x1800037e8  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x1800037ef  jz      short loc_180003800
0x1800037f1  mov     r8d, ebx
0x1800037f4  lea     rdx, ErrorRegOpenKeyEx
0x1800037fb  call    McTemplateU0q_EtwEventWriteTransfer
0x180003800  mov     r8d, r14d
0x180003803  mov     edx, ebx
0x180003805  mov     rcx, rdi
0x180003808  call    TraceLogErrorv4
0x18000380d  jmp     loc_18000368A
0x180003812  mov     ebx, 0Bh
0x180003817  test    byte ptr cs:xmmword_1800616A0, 2
0x18000381e  jz      short loc_180003843
0x180003820  mov     dword ptr [rsp+1E0h+lpData], r9d
0x180003825  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x18000382c  mov     r9d, ebx
0x18000382f  mov     edx, 0Ah
0x180003834  mov     ecx, 401h
0x180003839  call    WPP_SF_Dd
0x18000383e  mov     r9d, [rsp+1E0h+Type]
0x180003843  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x18000384a  jz      short loc_18000385B
0x18000384c  mov     r8d, ebx
0x18000384f  lea     rdx, ErrorRegQueryValueEx
0x180003856  call    McTemplateU0qq_EtwEventWriteTransfer
0x18000385b  mov     r9d, r14d
0x18000385e  lea     rcx, [rsp+1E0h+var_1A0]
0x180003863  mov     r8d, ebx
0x180003866  mov     rdx, rdi
0x180003869  call    InitializeTraceElementFromContext
0x18000386e  mov     eax, [rsp+1E0h+Type]
0x180003872  lea     rcx, [rsp+1E0h+var_1A0]
0x180003877  mov     [rbp+0E0h+var_130], eax
0x18000387a  call    TraceLogEx
0x18000387f  cmp     ebx, 2
0x180003882  jnz     loc_180003696
0x180003888  mov     ebx, r13d
0x18000388b  test    byte ptr cs:xmmword_1800616A0, 2
0x180003892  jz      short loc_1800038AA
0x180003894  mov     edx, 0Eh
0x180003899  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x1800038a0  mov     ecx, 401h
0x1800038a5  call    WPP_SF_
0x1800038aa  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x1800038b1  jz      short loc_1800038D1
0x1800038b3  lea     rax, [rbp+0E0h+var_60]
0x1800038ba  mov     r9d, 1
0x1800038c0  lea     rdx, ErrorFallbackParamsReadSucceeded
0x1800038c7  mov     [rsp+1E0h+lpData], rax
0x1800038cc  call    McGenEventWrite_EtwEventWriteTransfer
0x1800038d1  mov     edx, r13d
0x1800038d4  mov     r14d, 1Fh
0x1800038da  mov     r8d, r14d
0x1800038dd  mov     rcx, rdi
0x1800038e0  call    TraceLogErrorv4
0x1800038e5  mov     eax, ebx
0x1800038e7  mov     rcx, [rbp+0E0h+var_50]
0x1800038ee  xor     rcx, rsp; StackCookie
0x1800038f1  call    __security_check_cookie
0x1800038f6  add     rsp, 1A8h
0x1800038fd  pop     r15
0x1800038ff  pop     r14
0x180003901  pop     r13
0x180003903  pop     r12
0x180003905  pop     rdi
0x180003906  pop     rsi
0x180003907  pop     rbx
0x180003908  pop     rbp
0x180003909  retn
```
