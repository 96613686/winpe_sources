# CFDRPlugin::WriteFDRLayer(void)

- ea: `0x180036764`
- end: `0x180036a56`
- name: `?WriteFDRLayer@CFDRPlugin@@AEAAJXZ`
- size: `754`
- prototype: `__int64 __fastcall(CFDRPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035224`

## callees

- `0x1800028b4`
- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x18000a004`
- `0x180011d94`
- `0x1800121e4`
- `0x180016414`
- `0x180036764`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003699b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003699b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036822`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036822`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036a36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036a36`

## string_xrefs

- `0x1800367fb`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`

## pseudocode

```c
__int64 __fastcall CFDRPlugin::WriteFDRLayer(CFDRPlugin *this)
{
  HKEY *phkResult; // rax
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  void *v8; // rax
  _WORD *v9; // rdx
  __int64 v10; // r8
  const BYTE *v11; // rcx
  __int64 v12; // rax
  BYTE *lpData[2]; // [rsp+50h] [rbp-49h] BYREF
  _WORD v15[8]; // [rsp+60h] [rbp-39h] BYREF
  _WORD v16[2]; // [rsp+70h] [rbp-29h] BYREF
  int v17; // [rsp+74h] [rbp-25h]
  void *v18; // [rsp+78h] [rbp-21h]
  __m128i si128; // [rsp+80h] [rbp-19h]
  void *v20; // [rsp+90h] [rbp-9h]
  _WORD *v21; // [rsp+98h] [rbp-1h]
  _WORD v22[8]; // [rsp+A0h] [rbp+7h] BYREF
  void *v23; // [rsp+B0h] [rbp+17h]
  _WORD *v24; // [rsp+B8h] [rbp+1Fh]
  _WORD v25[8]; // [rsp+C0h] [rbp+27h] BYREF
  void *v26; // [rsp+D0h] [rbp+37h]
  DWORD dwDisposition; // [rsp+108h] [rbp+6Fh] BYREF
  HKEY hKey; // [rsp+110h] [rbp+77h] BYREF

  v20 = v22;
  hKey = 0;
  v21 = v22;
  dwDisposition = 0;
  v23 = v25;
  v16[0] = 0;
  v24 = v25;
  v17 = 0;
  lpData[0] = (BYTE *)v15;
  lpData[1] = (BYTE *)v15;
  v18 = (void *)-1LL;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v22[0] = 0;
  v25[0] = 0;
  v26 = 0;
  v15[0] = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
         0,
         0,
         0,
         3u,
         0,
         phkResult,
         &dwDisposition) )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v4 = 30;
LABEL_5:
    WPP_SF_(v3[2], v4, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
LABEL_6:
    v5 = -2147467259;
    goto LABEL_35;
  }
  v5 = CRegSetting::Initialize(v16, 1, &unk_18004FE4C, *((_QWORD *)this + 1), 0);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 31;
LABEL_11:
      WPP_SF_d(v6[2], v7, &WPP_928a4490cd403d1d5470036a68085293_Traceguids, (unsigned int)v5);
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  if ( CRegSetting::Load((CRegSetting *)v16, hKey, 0) < 0 )
    goto LABEL_27;
  v8 = v26;
  if ( LOBYTE(v16[0]) )
    v8 = v18;
  if ( !v8 )
  {
LABEL_27:
    v11 = (const BYTE *)L"FDR";
LABEL_28:
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)&v11[2 * v12] );
    if ( RegSetValueExW(hKey, *((LPCWSTR *)this + 1), 0, 1u, v11, 2 * v12 + 2) )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_6;
      v4 = 33;
      goto LABEL_5;
    }
    v5 = 0;
    goto LABEL_35;
  }
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                          lpData,
                          L"FDR ") )
  {
    v9 = v26;
    if ( LOBYTE(v16[0]) )
      v9 = v18;
    if ( v9 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v9[v10] );
    }
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                            lpData,
                            v9) )
    {
      v11 = lpData[0];
      goto LABEL_28;
    }
  }
  v5 = -2147024882;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 32;
    goto LABEL_11;
  }
LABEL_35:
  if ( (_WORD *)lpData[0] != v15 )
    operator delete(lpData[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v23 != v25 )
    operator delete(v23, (const struct std::nothrow_t *)&std::nothrow);
  if ( v20 != v22 )
    operator delete(v20, (const struct std::nothrow_t *)&std::nothrow);
  if ( v18 != (void *)-1LL )
  {
    si128.m128i_i64[0] = (__int64)v18;
    operator delete(v18, (const struct std::nothrow_t *)&std::nothrow);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180036764  mov     [rsp-8+arg_0], rbx
0x180036769  mov     [rsp-8+arg_18], rsi
0x18003676e  push    rbp
0x18003676f  push    rdi
0x180036770  push    r14
0x180036772  lea     rbp, [rsp-47h]
0x180036777  sub     rsp, 0E0h
0x18003677e  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180036786  lea     rax, [rbp+57h+var_50]
0x18003678a  xor     esi, esi
0x18003678c  mov     [rbp+57h+var_60], rax
0x180036790  lea     rax, [rbp+57h+var_50]
0x180036794  mov     [rbp+57h+hKey], rsi
0x180036798  mov     [rbp+57h+var_58], rax
0x18003679c  mov     rdi, rcx
0x18003679f  lea     rax, [rbp+57h+var_30]
0x1800367a3  mov     [rbp+57h+dwDisposition], esi
0x1800367a6  mov     [rbp+57h+var_40], rax
0x1800367aa  lea     rcx, [rbp+57h+hKey]
0x1800367ae  lea     rax, [rbp+57h+var_30]
0x1800367b2  mov     [rbp+57h+var_80], si
0x1800367b6  mov     [rbp+57h+var_38], rax
0x1800367ba  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800367be  lea     rax, [rbp+57h+var_90]
0x1800367c2  mov     [rbp+57h+var_7C], esi
0x1800367c5  mov     [rbp+57h+lpData], rax
0x1800367c9  lea     rax, [rbp+57h+var_90]
0x1800367cd  mov     [rbp+57h+var_98], rax
0x1800367d1  mov     [rbp+57h+var_78], r14
0x1800367d5  movdqa  [rbp+57h+var_70], xmm0
0x1800367da  mov     [rbp+57h+var_50], si
0x1800367de  mov     [rbp+57h+var_30], si
0x1800367e2  mov     [rbp+57h+var_20], rsi
0x1800367e6  mov     [rbp+57h+var_90], si
0x1800367ea  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800367ef  lea     rcx, [rbp+57h+dwDisposition]
0x1800367f3  xor     r9d, r9d; lpClass
0x1800367f6  mov     [rsp+0F0h+lpdwDisposition], rcx; lpdwDisposition
0x1800367fb  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x180036802  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180036807  xor     r8d, r8d; Reserved
0x18003680a  mov     [rsp+0F0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18003680f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180036816  mov     [rsp+0F0h+samDesired], 3; samDesired
0x18003681e  mov     [rsp+0F0h+dwOptions], esi; dwOptions
0x180036822  call    cs:__imp_RegCreateKeyExW
0x180036828  test    eax, eax
0x18003682a  jz      short loc_180036862
0x18003682c  mov     rcx, cs:WPP_GLOBAL_Control
0x180036833  lea     rax, WPP_GLOBAL_Control
0x18003683a  cmp     rcx, rax
0x18003683d  jz      short loc_180036858
0x18003683f  test    byte ptr [rcx+1Ch], 1
0x180036843  jz      short loc_180036858
0x180036845  lea     edx, [rsi+1Eh]
0x180036848  mov     rcx, [rcx+10h]
0x18003684c  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x180036853  call    WPP_SF_
0x180036858  mov     ebx, 80004005h
0x18003685d  jmp     loc_1800369D2
0x180036862  mov     r9, [rdi+8]
0x180036866  lea     r8, unk_18004FE4C
0x18003686d  mov     edx, 1
0x180036872  mov     qword ptr [rsp+0F0h+dwOptions], rsi
0x180036877  lea     rcx, [rbp+57h+var_80]
0x18003687b  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x180036880  mov     ebx, eax
0x180036882  test    eax, eax
0x180036884  jns     short loc_1800368C4
0x180036886  mov     rcx, cs:WPP_GLOBAL_Control
0x18003688d  lea     rax, WPP_GLOBAL_Control
0x180036894  cmp     rcx, rax
0x180036897  jz      loc_1800369D2
0x18003689d  test    byte ptr [rcx+1Ch], 1
0x1800368a1  jz      loc_1800369D2
0x1800368a7  mov     edx, 1Fh
0x1800368ac  mov     rcx, [rcx+10h]
0x1800368b0  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x1800368b7  mov     r9d, ebx
0x1800368ba  call    WPP_SF_d
0x1800368bf  jmp     loc_1800369D2
0x1800368c4  mov     rdx, [rbp+57h+hKey]; HKEY
0x1800368c8  lea     rcx, [rbp+57h+var_80]; this
0x1800368cc  xor     r8d, r8d; unsigned int
0x1800368cf  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x1800368d4  test    eax, eax
0x1800368d6  js      loc_180036967
0x1800368dc  cmp     byte ptr [rbp+57h+var_80], sil
0x1800368e0  mov     rax, [rbp+57h+var_20]
0x1800368e4  cmovnz  rax, [rbp+57h+var_78]
0x1800368e9  test    rax, rax
0x1800368ec  jz      short loc_180036967
0x1800368ee  mov     r8d, 4
0x1800368f4  lea     rdx, aFdr_0; "FDR "
0x1800368fb  lea     rcx, [rbp+57h+lpData]
0x1800368ff  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180036904  test    al, al
0x180036906  jz      short loc_18003693F
0x180036908  cmp     byte ptr [rbp+57h+var_80], sil
0x18003690c  mov     rdx, [rbp+57h+var_20]
0x180036910  cmovnz  rdx, [rbp+57h+var_78]
0x180036915  test    rdx, rdx
0x180036918  jz      short loc_180036929
0x18003691a  mov     r8, r14
0x18003691d  inc     r8
0x180036920  cmp     [rdx+r8*2], si
0x180036925  jnz     short loc_18003691D
0x180036927  jmp     short loc_18003692C
0x180036929  mov     r8, rsi
0x18003692c  lea     rcx, [rbp+57h+lpData]
0x180036930  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180036935  test    al, al
0x180036937  jz      short loc_18003693F
0x180036939  mov     rcx, [rbp+57h+lpData]
0x18003693d  jmp     short loc_18003696E
0x18003693f  mov     ebx, 8007000Eh
0x180036944  mov     rcx, cs:WPP_GLOBAL_Control
0x18003694b  lea     rax, WPP_GLOBAL_Control
0x180036952  cmp     rcx, rax
0x180036955  jz      short loc_1800369D2
0x180036957  test    byte ptr [rcx+1Ch], 1
0x18003695b  jz      short loc_1800369D2
0x18003695d  mov     edx, 20h ; ' '
0x180036962  jmp     loc_1800368AC
0x180036967  lea     rcx, aFdr; "FDR"
0x18003696e  mov     rax, r14
0x180036971  inc     rax
0x180036974  cmp     [rcx+rax*2], si
0x180036978  jnz     short loc_180036971
0x18003697a  mov     rdx, [rdi+8]; lpValueName
0x18003697e  lea     eax, ds:2[rax*2]
0x180036985  mov     [rsp+0F0h+samDesired], eax; cbData
0x180036989  mov     r9d, 1; dwType
0x18003698f  mov     qword ptr [rsp+0F0h+dwOptions], rcx; lpData
0x180036994  xor     r8d, r8d; Reserved
0x180036997  mov     rcx, [rbp+57h+hKey]; hKey
0x18003699b  call    cs:__imp_RegSetValueExW
0x1800369a1  test    eax, eax
0x1800369a3  jz      short loc_1800369D0
0x1800369a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800369ac  lea     rax, WPP_GLOBAL_Control
0x1800369b3  cmp     rcx, rax
0x1800369b6  jz      loc_180036858
0x1800369bc  test    byte ptr [rcx+1Ch], 1
0x1800369c0  jz      loc_180036858
0x1800369c6  mov     edx, 21h ; '!'
0x1800369cb  jmp     loc_180036848
0x1800369d0  mov     ebx, esi
0x1800369d2  mov     rcx, [rbp+57h+lpData]; void *
0x1800369d6  lea     rax, [rbp+57h+var_90]
0x1800369da  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800369e1  cmp     rcx, rax
0x1800369e4  jz      short loc_1800369EE
0x1800369e6  mov     rdx, rdi; struct std::nothrow_t *
0x1800369e9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800369ee  mov     rcx, [rbp+57h+var_40]; void *
0x1800369f2  lea     rax, [rbp+57h+var_30]
0x1800369f6  cmp     rcx, rax
0x1800369f9  jz      short loc_180036A03
0x1800369fb  mov     rdx, rdi; struct std::nothrow_t *
0x1800369fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036a03  mov     rcx, [rbp+57h+var_60]; void *
0x180036a07  lea     rax, [rbp+57h+var_50]
0x180036a0b  cmp     rcx, rax
0x180036a0e  jz      short loc_180036A18
0x180036a10  mov     rdx, rdi; struct std::nothrow_t *
0x180036a13  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036a18  mov     rcx, [rbp+57h+var_78]; void *
0x180036a1c  cmp     rcx, r14
0x180036a1f  jz      short loc_180036A2D
0x180036a21  mov     rdx, rdi; struct std::nothrow_t *
0x180036a24  mov     qword ptr [rbp+57h+var_70], rcx
0x180036a28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036a2d  mov     rcx, [rbp+57h+hKey]; hKey
0x180036a31  test    rcx, rcx
0x180036a34  jz      short loc_180036A3C
0x180036a36  call    cs:__imp_RegCloseKey
0x180036a3c  lea     r11, [rsp+0F0h+var_10]
0x180036a44  mov     eax, ebx
0x180036a46  mov     rbx, [r11+20h]
0x180036a4a  mov     rsi, [r11+38h]
0x180036a4e  mov     rsp, r11
0x180036a51  pop     r14
0x180036a53  pop     rdi
0x180036a54  pop     rbp
0x180036a55  retn
```
