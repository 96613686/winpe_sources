# CAppRecorderPlugin::WriteAppCompatLayer(void)

- ea: `0x1800302b8`
- end: `0x180030566`
- name: `?WriteAppCompatLayer@CAppRecorderPlugin@@AEAAJXZ`
- size: `686`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002ecac`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180006b50`
- `0x180009e04`
- `0x180009f00`
- `0x18000a004`
- `0x1800302b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304cf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003048c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003048c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800303b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800303b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003053a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003053a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030408`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030408`

## string_xrefs

- `0x180030384`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`

## pseudocode

```c
__int64 __fastcall CAppRecorderPlugin::WriteAppCompatLayer(CAppRecorderPlugin *this)
{
  int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  HKEY *phkResult; // rax
  HKEY v7; // rcx
  const WCHAR *v8; // r8
  signed int v9; // eax
  signed int LastError; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE *lpData; // [rsp+60h] [rbp-A0h] BYREF
  char *v16; // [rsp+68h] [rbp-98h]
  _WORD v17[8]; // [rsp+70h] [rbp-90h] BYREF
  _WORD pvData[264]; // [rsp+80h] [rbp-80h] BYREF

  hkey = 0;
  lpData = (BYTE *)v17;
  dwDisposition = 0;
  v16 = (char *)v17;
  pcbData = 0;
  v17[0] = 0;
  pvData[0] = 0;
  if ( utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
         (__int64)&lpData,
         L"AppRecorder",
         0xBu) )
  {
    phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
    if ( RegCreateKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
           0,
           0,
           0,
           3u,
           0,
           phkResult,
           &dwDisposition)
      || (v7 = hkey) == 0 )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_28;
      v4 = 47;
    }
    else
    {
      if ( dwDisposition == 2 )
      {
        v8 = (const WCHAR *)*((_QWORD *)this + 1);
        pcbData = 520;
        if ( !RegGetValueW(hkey, 0, v8, 2u, 0, pvData, &pcbData) )
        {
          v2 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                 (__int64)&lpData,
                 (__int64)L"%s %s",
                 pvData,
                 L"AppRecorder");
          if ( v2 < 0 )
          {
            v3 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_28;
            v4 = 48;
            goto LABEL_26;
          }
        }
        v7 = hkey;
      }
      if ( !RegSetValueExW(v7, *((LPCWSTR *)this + 1), 0, 1u, lpData, 2 * ((v16 - (char *)lpData) >> 1)) )
      {
        v2 = 0;
        goto LABEL_28;
      }
      v9 = GetLastError();
      v2 = v9;
      if ( v9 > 0 )
        v2 = (unsigned __int16)v9 | 0x80070000;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_28;
      v4 = 49;
    }
LABEL_26:
    v5 = (unsigned int)v2;
    goto LABEL_27;
  }
  v2 = -2147024882;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v4 = 46;
    v5 = 2147942414LL;
LABEL_27:
    WPP_SF_d(v3[2], v4, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, v5);
  }
LABEL_28:
  if ( lpData != (BYTE *)v17 )
    operator delete(lpData, (const struct std::nothrow_t *)&std::nothrow);
  if ( hkey )
    RegCloseKey(hkey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800302b8  mov     [rsp-8+arg_8], rbx
0x1800302bd  mov     [rsp-8+arg_10], rdi
0x1800302c2  push    rbp
0x1800302c3  lea     rbp, [rsp-1A0h]
0x1800302cb  sub     rsp, 2A0h
0x1800302d2  mov     rax, cs:__security_cookie
0x1800302d9  xor     rax, rsp
0x1800302dc  mov     [rbp+1A0h+var_10], rax
0x1800302e3  lea     rax, [rsp+2A0h+var_230]
0x1800302e8  mov     [rsp+2A0h+hkey], 0
0x1800302f1  mov     [rsp+2A0h+lpData], rax
0x1800302f6  lea     rdx, aApprecorder; "AppRecorder"
0x1800302fd  lea     rax, [rsp+2A0h+var_230]
0x180030302  mov     [rsp+2A0h+dwDisposition], 0
0x18003030a  mov     [rsp+2A0h+var_238], rax
0x18003030f  mov     rdi, rcx
0x180030312  xor     eax, eax
0x180030314  mov     [rsp+2A0h+pcbData], 0
0x18003031c  lea     rcx, [rsp+2A0h+lpData]
0x180030321  mov     [rsp+2A0h+var_230], ax
0x180030326  mov     [rbp+1A0h+pvData], ax
0x18003032a  lea     r8d, [rax+0Bh]
0x18003032e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180030333  test    al, al
0x180030335  jnz     short loc_18003036D
0x180030337  mov     ebx, 8007000Eh
0x18003033c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030343  lea     rax, WPP_GLOBAL_Control
0x18003034a  cmp     rcx, rax
0x18003034d  jz      loc_180030515
0x180030353  test    byte ptr [rcx+1Ch], 1
0x180030357  jz      loc_180030515
0x18003035d  mov     edx, 2Eh ; '.'
0x180030362  mov     r9d, 8007000Eh
0x180030368  jmp     loc_180030505
0x18003036d  lea     rcx, [rsp+2A0h+hkey]
0x180030372  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180030377  lea     rcx, [rsp+2A0h+dwDisposition]
0x18003037c  xor     r9d, r9d; lpClass
0x18003037f  mov     [rsp+2A0h+lpdwDisposition], rcx; lpdwDisposition
0x180030384  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003038b  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180030390  xor     r8d, r8d; Reserved
0x180030393  mov     [rsp+2A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003039c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800303a3  mov     [rsp+2A0h+samDesired], 3; samDesired
0x1800303ab  mov     [rsp+2A0h+dwOptions], 0; dwOptions
0x1800303b3  call    cs:__imp_RegCreateKeyExW
0x1800303b9  test    eax, eax
0x1800303bb  jnz     loc_1800304CF
0x1800303c1  mov     rcx, [rsp+2A0h+hkey]; hkey
0x1800303c6  test    rcx, rcx
0x1800303c9  jz      loc_1800304CF
0x1800303cf  lea     r9d, [rax+2]; dwFlags
0x1800303d3  cmp     [rsp+2A0h+dwDisposition], r9d
0x1800303d8  jnz     loc_180030464
0x1800303de  mov     r8, [rdi+8]; lpValue
0x1800303e2  lea     rax, [rsp+2A0h+pcbData]
0x1800303e7  mov     [rsp+2A0h+lpSecurityAttributes], rax; pcbData
0x1800303ec  xor     edx, edx; lpSubKey
0x1800303ee  lea     rax, [rbp+1A0h+pvData]
0x1800303f2  mov     [rsp+2A0h+pcbData], 208h
0x1800303fa  mov     qword ptr [rsp+2A0h+samDesired], rax; pvData
0x1800303ff  mov     qword ptr [rsp+2A0h+dwOptions], 0; pdwType
0x180030408  call    cs:__imp_RegGetValueW
0x18003040e  test    eax, eax
0x180030410  jnz     short loc_18003045F
0x180030412  lea     r9, aApprecorder; "AppRecorder"
0x180030419  lea     r8, [rbp+1A0h+pvData]
0x18003041d  lea     rdx, aSS_2; "%s %s"
0x180030424  lea     rcx, [rsp+2A0h+lpData]
0x180030429  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003042e  mov     ebx, eax
0x180030430  test    eax, eax
0x180030432  jns     short loc_18003045F
0x180030434  mov     rcx, cs:WPP_GLOBAL_Control
0x18003043b  lea     rax, WPP_GLOBAL_Control
0x180030442  cmp     rcx, rax
0x180030445  jz      loc_180030515
0x18003044b  test    byte ptr [rcx+1Ch], 1
0x18003044f  jz      loc_180030515
0x180030455  mov     edx, 30h ; '0'
0x18003045a  jmp     loc_180030502
0x18003045f  mov     rcx, [rsp+2A0h+hkey]; hKey
0x180030464  mov     r8, [rsp+2A0h+lpData]
0x180030469  mov     r9d, 1; dwType
0x18003046f  mov     rax, [rsp+2A0h+var_238]
0x180030474  mov     rdx, [rdi+8]; lpValueName
0x180030478  sub     rax, r8
0x18003047b  sar     rax, 1
0x18003047e  add     eax, eax
0x180030480  mov     [rsp+2A0h+samDesired], eax; cbData
0x180030484  mov     qword ptr [rsp+2A0h+dwOptions], r8; lpData
0x180030489  xor     r8d, r8d; Reserved
0x18003048c  call    cs:__imp_RegSetValueExW
0x180030492  test    eax, eax
0x180030494  jz      short loc_1800304CB
0x180030496  call    cs:__imp_GetLastError
0x18003049c  mov     ebx, eax
0x18003049e  test    eax, eax
0x1800304a0  jle     short loc_1800304AB
0x1800304a2  movzx   ebx, ax
0x1800304a5  or      ebx, 80070000h
0x1800304ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800304b2  lea     rax, WPP_GLOBAL_Control
0x1800304b9  cmp     rcx, rax
0x1800304bc  jz      short loc_180030515
0x1800304be  test    byte ptr [rcx+1Ch], 1
0x1800304c2  jz      short loc_180030515
0x1800304c4  mov     edx, 31h ; '1'
0x1800304c9  jmp     short loc_180030502
0x1800304cb  xor     ebx, ebx
0x1800304cd  jmp     short loc_180030515
0x1800304cf  call    cs:__imp_GetLastError
0x1800304d5  mov     ebx, eax
0x1800304d7  test    eax, eax
0x1800304d9  jle     short loc_1800304E4
0x1800304db  movzx   ebx, ax
0x1800304de  or      ebx, 80070000h
0x1800304e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800304eb  lea     rax, WPP_GLOBAL_Control
0x1800304f2  cmp     rcx, rax
0x1800304f5  jz      short loc_180030515
0x1800304f7  test    byte ptr [rcx+1Ch], 1
0x1800304fb  jz      short loc_180030515
0x1800304fd  mov     edx, 2Fh ; '/'
0x180030502  mov     r9d, ebx
0x180030505  mov     rcx, [rcx+10h]
0x180030509  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x180030510  call    WPP_SF_d
0x180030515  mov     rcx, [rsp+2A0h+lpData]; void *
0x18003051a  lea     rax, [rsp+2A0h+var_230]
0x18003051f  cmp     rcx, rax
0x180030522  jz      short loc_180030530
0x180030524  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003052b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180030530  mov     rcx, [rsp+2A0h+hkey]; hKey
0x180030535  test    rcx, rcx
0x180030538  jz      short loc_180030540
0x18003053a  call    cs:__imp_RegCloseKey
0x180030540  mov     eax, ebx
0x180030542  mov     rcx, [rbp+1A0h+var_10]
0x180030549  xor     rcx, rsp; StackCookie
0x18003054c  call    __security_check_cookie
0x180030551  lea     r11, [rsp+2A0h+var_s0]
0x180030559  mov     rbx, [r11+18h]
0x18003055d  mov     rdi, [r11+20h]
0x180030561  mov     rsp, r11
0x180030564  pop     rbp
0x180030565  retn
```
