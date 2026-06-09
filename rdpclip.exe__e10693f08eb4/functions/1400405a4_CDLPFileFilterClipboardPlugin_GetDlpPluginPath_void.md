# CDLPFileFilterClipboardPlugin::GetDlpPluginPath(void)

- ea: `0x1400405a4`
- end: `0x1400407fc`
- name: `?GetDlpPluginPath@CDLPFileFilterClipboardPlugin@@IEAA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@XZ`
- size: `600`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400408fc`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x14000c7cc`
- `0x14000c944`
- `0x140014d8c`
- `0x14002e4b8`
- `0x14004010c`
- `0x1400405a4`
- `0x14006a120`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004060c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004060c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140040664`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140040664`

## string_xrefs

- `0x14004063f`: `InstallLocation`
- `0x1400407c0`: `mpclient.dll`

## pseudocode

```c
__int64 __fastcall CDLPFileFilterClipboardPlugin::GetDlpPluginPath(__int64 a1, __int64 a2)
{
  LSTATUS v3; // eax
  char v4; // di
  LSTATUS v5; // eax
  char v6; // di
  __int64 v7; // r8
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v9; // rax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  _WORD Data[264]; // [rsp+50h] [rbp-B0h] BYREF

  *(_QWORD *)a2 = a2 + 16;
  *(_QWORD *)(a2 + 8) = a2 + 16;
  *(_WORD *)(a2 + 16) = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Defender", 0, 0x20019u, &hKey);
  v4 = v3;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)&WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)L"SOFTWARE\\Microsoft\\Windows Defender",
        v4);
    }
  }
  else
  {
    memset_0(Data, 0, 0x20Au);
    cbData = 522;
    Type = 0;
    v5 = RegQueryValueExW(hKey, L"InstallLocation", 0, &Type, (LPBYTE)Data, &cbData);
    v6 = v5;
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        goto LABEL_14;
      }
    }
    else
    {
      v6 = Type;
      if ( Type == 1 )
      {
        Data[260] = 0;
        v7 = -1;
        do
          ++v7;
        while ( Data[v7] );
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          a2,
          Data,
          v7);
        goto LABEL_19;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
LABEL_14:
        RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (__int64)L"SOFTWARE\\Microsoft\\Windows Defender",
          (__int64)L"InstallLocation",
          v6);
      }
    }
  }
LABEL_19:
  v9 = *(_QWORD *)(a2 + 8);
  if ( *(_QWORD *)a2 != v9 )
  {
    if ( *(_WORD *)(v9 - 2) != 92 && *(_WORD *)(v9 - 2) != 47 )
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
        a2,
        L"\\",
        1);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
      a2,
      L"mpclient.dll",
      12);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return a2;
}

```

## disassembly

```asm
0x1400405a4  push    rbp
0x1400405a6  push    rbx
0x1400405a7  push    rdi
0x1400405a8  push    r12
0x1400405aa  push    r14
0x1400405ac  push    r15
0x1400405ae  lea     rbp, [rsp-178h]
0x1400405b6  sub     rsp, 278h
0x1400405bd  mov     rax, cs:__security_cookie
0x1400405c4  xor     rax, rsp
0x1400405c7  mov     [rbp+1A0h+var_40], rax
0x1400405ce  lea     rcx, [rdx+10h]
0x1400405d2  xor     r14d, r14d
0x1400405d5  mov     [rdx], rcx
0x1400405d8  lea     rax, [rsp+2A0h+hKey]
0x1400405dd  mov     [rdx+8], rcx
0x1400405e1  lea     r15, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows Defender"
0x1400405e8  mov     [rcx], r14w
0x1400405ec  mov     rbx, rdx
0x1400405ef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400405f6  mov     [rsp+2A0h+hKey], r14
0x1400405fb  mov     r9d, 20019h; samDesired
0x140040601  mov     [rsp+2A0h+phkResult], rax; phkResult
0x140040606  xor     r8d, r8d; ulOptions
0x140040609  mov     rdx, r15; lpSubKey
0x14004060c  call    cs:__imp_RegOpenKeyExW
0x140040612  mov     edi, eax
0x140040614  test    eax, eax
0x140040616  jnz     loc_14004073C
0x14004061c  mov     edi, 20Ah
0x140040621  lea     rcx, [rsp+2A0h+Data]; void *
0x140040626  mov     r8d, edi; Size
0x140040629  xor     edx, edx; Val
0x14004062b  call    memset_0
0x140040630  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140040635  lea     rax, [rsp+2A0h+cbData]
0x14004063a  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x14004063f  lea     r12, aInstalllocatio; "InstallLocation"
0x140040646  lea     rax, [rsp+2A0h+Data]
0x14004064b  mov     [rsp+2A0h+cbData], edi
0x14004064f  lea     r9, [rsp+2A0h+Type]; lpType
0x140040654  mov     [rsp+2A0h+phkResult], rax; lpData
0x140040659  xor     r8d, r8d; lpReserved
0x14004065c  mov     [rsp+2A0h+Type], r14d
0x140040661  mov     rdx, r12; lpValueName
0x140040664  call    cs:__imp_RegQueryValueExW
0x14004066a  mov     edi, eax
0x14004066c  test    eax, eax
0x14004066e  jnz     short loc_1400406DD
0x140040670  mov     edi, [rsp+2A0h+Type]
0x140040674  cmp     edi, 1
0x140040677  jnz     short loc_1400406A6
0x140040679  mov     [rbp+1A0h+var_48], r14w
0x140040681  lea     rax, [rsp+2A0h+Data]
0x140040686  or      r8, 0FFFFFFFFFFFFFFFFh
0x14004068a  inc     r8
0x14004068d  cmp     [rax+r8*2], r14w
0x140040692  jnz     short loc_14004068A
0x140040694  lea     rdx, [rsp+2A0h+Data]
0x140040699  mov     rcx, rbx
0x14004069c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1400406a1  jmp     loc_140040788
0x1400406a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400406ad  lea     rax, WPP_GLOBAL_Control
0x1400406b4  cmp     rcx, rax
0x1400406b7  jz      loc_140040788
0x1400406bd  test    byte ptr [rcx+1Ch], 1
0x1400406c1  jz      loc_140040788
0x1400406c7  cmp     byte ptr [rcx+19h], 2
0x1400406cb  jb      loc_140040788
0x1400406d1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400406d6  mov     edx, 15h
0x1400406db  jmp     short loc_140040712
0x1400406dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400406e4  lea     rax, WPP_GLOBAL_Control
0x1400406eb  cmp     rcx, rax
0x1400406ee  jz      loc_140040788
0x1400406f4  test    byte ptr [rcx+1Ch], 1
0x1400406f8  jz      loc_140040788
0x1400406fe  cmp     byte ptr [rcx+19h], 2
0x140040702  jb      loc_140040788
0x140040708  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004070d  mov     edx, 16h
0x140040712  mov     rcx, cs:WPP_GLOBAL_Control
0x140040719  lea     r8, WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids
0x140040720  mov     dword ptr [rsp+2A0h+var_270], edi; char
0x140040724  mov     r9d, eax
0x140040727  mov     [rsp+2A0h+lpcbData], r12; __int64
0x14004072c  mov     [rsp+2A0h+phkResult], r15; __int64
0x140040731  mov     rcx, [rcx+10h]; LoggerHandle
0x140040735  call    WPP_SF_DSSd
0x14004073a  jmp     short loc_140040788
0x14004073c  mov     rcx, cs:WPP_GLOBAL_Control
0x140040743  lea     rax, WPP_GLOBAL_Control
0x14004074a  cmp     rcx, rax
0x14004074d  jz      short loc_140040788
0x14004074f  test    byte ptr [rcx+1Ch], 1
0x140040753  jz      short loc_140040788
0x140040755  cmp     byte ptr [rcx+19h], 2
0x140040759  jb      short loc_140040788
0x14004075b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140040760  mov     rcx, cs:WPP_GLOBAL_Control
0x140040767  lea     r8, WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids
0x14004076e  mov     edx, 17h
0x140040773  mov     dword ptr [rsp+2A0h+lpcbData], edi
0x140040777  mov     r9d, eax
0x14004077a  mov     [rsp+2A0h+phkResult], r15
0x14004077f  mov     rcx, [rcx+10h]
0x140040783  call    WPP_SF_DSD
0x140040788  mov     rax, [rbx+8]
0x14004078c  cmp     [rbx], rax
0x14004078f  jz      short loc_1400407CF
0x140040791  mov     ecx, 5Ch ; '\'
0x140040796  cmp     cx, [rax-2]
0x14004079a  jz      short loc_1400407BA
0x14004079c  mov     ecx, 2Fh ; '/'
0x1400407a1  cmp     cx, [rax-2]
0x1400407a5  jz      short loc_1400407BA
0x1400407a7  lea     r8d, [rcx-2Eh]
0x1400407ab  mov     rcx, rbx
0x1400407ae  lea     rdx, asc_140070908; "\\"
0x1400407b5  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1400407ba  mov     r8d, 0Ch
0x1400407c0  lea     rdx, aMpclientDll; "mpclient.dll"
0x1400407c7  mov     rcx, rbx
0x1400407ca  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1400407cf  lea     rcx, [rsp+2A0h+hKey]
0x1400407d4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400407d9  mov     rax, rbx
0x1400407dc  mov     rcx, [rbp+1A0h+var_40]
0x1400407e3  xor     rcx, rsp; StackCookie
0x1400407e6  call    __security_check_cookie
0x1400407eb  add     rsp, 278h
0x1400407f2  pop     r15
0x1400407f4  pop     r14
0x1400407f6  pop     r12
0x1400407f8  pop     rdi
0x1400407f9  pop     rbx
0x1400407fa  pop     rbp
0x1400407fb  retn
```
