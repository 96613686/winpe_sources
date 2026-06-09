# CLocalDumpSettings::LoadSettingsFromSubKey(wchar_t const *)

- ea: `0x18001b5b4`
- end: `0x18001b7c6`
- name: `?LoadSettingsFromSubKey@CLocalDumpSettings@@AEAAJPEB_W@Z`
- size: `530`
- prototype: `__int64 __fastcall(CLocalDumpSettings *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001a3a4`

## callees

- `0x1800028b4`
- `0x18000760c`
- `0x180009f00`
- `0x18000a004`
- `0x18000a074`
- `0x18000bc54`
- `0x18000e524`
- `0x18001b5b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b7b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b7b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b63c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b63c`

## pseudocode

```c
__int64 __fastcall CLocalDumpSettings::LoadSettingsFromSubKey(CLocalDumpSettings *this, const wchar_t *a2)
{
  HKEY *v4; // rax
  LSTATUS v5; // eax
  signed int String; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned int DWORD; // eax
  unsigned int v10; // r9d
  HKEY v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // r9d
  HKEY v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // r9d
  HKEY v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // r9d
  bool *phkResult; // [rsp+20h] [rbp-48h]
  bool *phkResulta; // [rsp+20h] [rbp-48h]
  bool *phkResultb; // [rsp+20h] [rbp-48h]
  bool *phkResultc; // [rsp+20h] [rbp-48h]
  bool *phkResultd; // [rsp+20h] [rbp-48h]
  bool v26; // [rsp+28h] [rbp-40h]
  bool v27; // [rsp+28h] [rbp-40h]
  bool v28; // [rsp+28h] [rbp-40h]
  bool v29; // [rsp+28h] [rbp-40h]
  bool v30; // [rsp+28h] [rbp-40h]
  DWORD v31; // [rsp+30h] [rbp-38h]
  void *v32[2]; // [rsp+40h] [rbp-28h] BYREF
  _WORD v33[12]; // [rsp+50h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp+48h] BYREF

  hKey = 0;
  v32[0] = v33;
  v32[1] = v33;
  v33[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_bb2f0e3f91823ea90d6fa399a905fc71_Traceguids, a2);
  v4 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\LocalDumps",
         0,
         0x101u,
         v4);
  String = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      String = (unsigned __int16)v5 | 0x80070000;
    if ( String >= 0 )
      String = -2147467259;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 12;
LABEL_12:
      WPP_SF_d(v7[2], v8, WPP_bb2f0e3f91823ea90d6fa399a905fc71_Traceguids, (unsigned int)String);
    }
  }
  else
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v32, (char *)this + 8);
    String = UtilRegGetString(hKey, a2, L"DumpFolder", (__int64)this + 8, 1, v31);
    if ( String >= 0 )
    {
      DWORD = UtilRegGetDWORD(hKey, a2, L"DumpCount", *((_DWORD *)this + 10), phkResult, v26);
      v10 = *((_DWORD *)this + 11);
      v11 = hKey;
      *((_DWORD *)this + 10) = DWORD;
      v12 = UtilRegGetDWORD(v11, a2, L"DumpType", v10, phkResulta, v27);
      v13 = *((_DWORD *)this + 12);
      v14 = hKey;
      *((_DWORD *)this + 11) = v12;
      v15 = UtilRegGetDWORD(v14, a2, L"CustomDumpFlags", v13, phkResultb, v28);
      v16 = *((_DWORD *)this + 13);
      v17 = hKey;
      *((_DWORD *)this + 12) = v15;
      v18 = UtilRegGetDWORD(v17, a2, L"SuppressOnDebugger", v16, phkResultc, v29);
      v19 = *((_DWORD *)this + 14);
      *((_DWORD *)this + 13) = v18 != 0;
      String = 0;
      *((_DWORD *)this + 14) = UtilRegGetDWORD(hKey, a2, L"DeveloperAppOnly", v19, phkResultd, v30) != 0;
    }
    else
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=((char *)this + 8, v32);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 13;
        goto LABEL_12;
      }
    }
  }
  if ( v32[0] != v33 )
    operator delete(v32[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18001b5b4  push    rbp
0x18001b5b6  push    rbx
0x18001b5b7  push    rsi
0x18001b5b8  push    rdi
0x18001b5b9  push    r12
0x18001b5bb  push    r14
0x18001b5bd  mov     rbp, rsp
0x18001b5c0  sub     rsp, 68h
0x18001b5c4  lea     rax, [rbp+var_18]
0x18001b5c8  mov     [rbp+hKey], 0
0x18001b5d0  mov     [rbp+var_28], rax
0x18001b5d4  mov     rsi, rdx
0x18001b5d7  lea     rax, [rbp+var_18]
0x18001b5db  mov     r14, rcx
0x18001b5de  mov     [rbp+var_20], rax
0x18001b5e2  xor     eax, eax
0x18001b5e4  mov     [rbp+var_18], ax
0x18001b5e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5ef  lea     r12, WPP_GLOBAL_Control
0x18001b5f6  cmp     rcx, r12
0x18001b5f9  jz      short loc_18001B617
0x18001b5fb  test    byte ptr [rcx+1Ch], 4
0x18001b5ff  jz      short loc_18001B617
0x18001b601  mov     rcx, [rcx+10h]
0x18001b605  lea     edx, [rax+0Bh]
0x18001b608  mov     r9, rsi
0x18001b60b  lea     r8, WPP_bb2f0e3f91823ea90d6fa399a905fc71_Traceguids
0x18001b612  call    WPP_SF_S
0x18001b617  lea     rcx, [rbp+hKey]
0x18001b61b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18001b620  mov     r9d, 101h; samDesired
0x18001b626  mov     [rsp+68h+phkResult], rax; phkResult
0x18001b62b  xor     r8d, r8d; ulOptions
0x18001b62e  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\Windows E"...
0x18001b635  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b63c  call    cs:__imp_RegOpenKeyExW
0x18001b642  mov     ebx, eax
0x18001b644  test    eax, eax
0x18001b646  jz      short loc_18001B694
0x18001b648  jle     short loc_18001B653
0x18001b64a  movzx   ebx, ax
0x18001b64d  or      ebx, 80070000h
0x18001b653  test    ebx, ebx
0x18001b655  mov     eax, 80004005h
0x18001b65a  cmovns  ebx, eax
0x18001b65d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b664  cmp     rcx, r12
0x18001b667  jz      loc_18001B78F
0x18001b66d  test    byte ptr [rcx+1Ch], 1
0x18001b671  jz      loc_18001B78F
0x18001b677  mov     edx, 0Ch
0x18001b67c  mov     rcx, [rcx+10h]
0x18001b680  lea     r8, WPP_bb2f0e3f91823ea90d6fa399a905fc71_Traceguids
0x18001b687  mov     r9d, ebx
0x18001b68a  call    WPP_SF_d
0x18001b68f  jmp     loc_18001B78F
0x18001b694  lea     rdi, [r14+8]
0x18001b698  mov     rdx, rdi
0x18001b69b  lea     rcx, [rbp+var_28]
0x18001b69f  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18001b6a4  mov     r9, [rbp+var_28]
0x18001b6a8  lea     r8, aDumpfolder; "DumpFolder"
0x18001b6af  mov     rcx, [rbp+hKey]; hKey
0x18001b6b3  mov     rdx, rsi; lpSubKey
0x18001b6b6  mov     [rsp+68h+var_40], 1; bool
0x18001b6bb  mov     [rsp+68h+phkResult], rdi; bool *
0x18001b6c0  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x18001b6c5  mov     ebx, eax
0x18001b6c7  test    eax, eax
0x18001b6c9  jns     short loc_18001B6F8
0x18001b6cb  lea     rdx, [rbp+var_28]
0x18001b6cf  mov     rcx, rdi
0x18001b6d2  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18001b6d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6de  cmp     rcx, r12
0x18001b6e1  jz      loc_18001B78F
0x18001b6e7  test    byte ptr [rcx+1Ch], 1
0x18001b6eb  jz      loc_18001B78F
0x18001b6f1  mov     edx, 0Dh
0x18001b6f6  jmp     short loc_18001B67C
0x18001b6f8  mov     r9d, [r14+28h]; unsigned int
0x18001b6fc  lea     r8, aDumpcount; "DumpCount"
0x18001b703  mov     rcx, [rbp+hKey]; hKey
0x18001b707  mov     rdx, rsi; lpSubKey
0x18001b70a  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18001b70f  mov     r9d, [r14+2Ch]; unsigned int
0x18001b713  lea     r8, aDumptype; "DumpType"
0x18001b71a  mov     rcx, [rbp+hKey]; hKey
0x18001b71e  mov     rdx, rsi; lpSubKey
0x18001b721  mov     [r14+28h], eax
0x18001b725  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18001b72a  mov     r9d, [r14+30h]; unsigned int
0x18001b72e  lea     r8, aCustomdumpflag; "CustomDumpFlags"
0x18001b735  mov     rcx, [rbp+hKey]; hKey
0x18001b739  mov     rdx, rsi; lpSubKey
0x18001b73c  mov     [r14+2Ch], eax
0x18001b740  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18001b745  mov     r9d, [r14+34h]; unsigned int
0x18001b749  lea     r8, aSuppressondebu; "SuppressOnDebugger"
0x18001b750  mov     rcx, [rbp+hKey]; hKey
0x18001b754  mov     rdx, rsi; lpSubKey
0x18001b757  mov     [r14+30h], eax
0x18001b75b  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18001b760  mov     r9d, [r14+38h]; unsigned int
0x18001b764  lea     r8, aDeveloperappon; "DeveloperAppOnly"
0x18001b76b  xor     ecx, ecx
0x18001b76d  mov     rdx, rsi; lpSubKey
0x18001b770  test    eax, eax
0x18001b772  setnz   cl
0x18001b775  mov     [r14+34h], ecx
0x18001b779  mov     rcx, [rbp+hKey]; hKey
0x18001b77d  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18001b782  xor     ecx, ecx
0x18001b784  test    eax, eax
0x18001b786  setnz   cl
0x18001b789  xor     ebx, ebx
0x18001b78b  mov     [r14+38h], ecx
0x18001b78f  mov     rcx, [rbp+var_28]; void *
0x18001b793  lea     rax, [rbp+var_18]
0x18001b797  cmp     rcx, rax
0x18001b79a  jz      short loc_18001B7A8
0x18001b79c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b7a3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b7a8  mov     rcx, [rbp+hKey]; hKey
0x18001b7ac  test    rcx, rcx
0x18001b7af  jz      short loc_18001B7B7
0x18001b7b1  call    cs:__imp_RegCloseKey
0x18001b7b7  mov     eax, ebx
0x18001b7b9  add     rsp, 68h
0x18001b7bd  pop     r14
0x18001b7bf  pop     r12
0x18001b7c1  pop     rdi
0x18001b7c2  pop     rsi
0x18001b7c3  pop     rbx
0x18001b7c4  pop     rbp
0x18001b7c5  retn
```
