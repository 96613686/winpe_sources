# CAutoVerifierPlugin::DisableAutoverifier(void)

- ea: `0x18002b3a0`
- end: `0x18002b4be`
- name: `?DisableAutoverifier@CAutoVerifierPlugin@@AEAAJXZ`
- size: `286`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002d040`

## callees

- `0x1800028b4`
- `0x180006b50`
- `0x180009ed8`
- `0x180009f00`
- `0x18002b3a0`
- `0x18002b9cc`
- `0x18002ce14`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002b45c`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002b45c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAutoVerifierPlugin::DisableAutoverifier(CAutoVerifierPlugin *this)
{
  CAutoVerifierPlugin *v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  LPCWSTR lpSubKey[2]; // [rsp+20h] [rbp-28h] BYREF
  _WORD v7[12]; // [rsp+30h] [rbp-18h] BYREF

  lpSubKey[0] = v7;
  lpSubKey[1] = v7;
  v7[0] = 0;
  CAutoVerifierPlugin::EnableHKCULookupForIFEO(this, 0);
  if ( (int)CAutoVerifierPlugin::SetAutoverifierEnabledFlag(v2, 0) < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
  }
  v3 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         lpSubKey,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\%s",
         *((_QWORD *)this + 93));
  v4 = v3;
  if ( v3 >= 0 )
  {
    if ( RegDeleteKeyW(HKEY_CURRENT_USER, lpSubKey[0]) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
      v4 = -2147467259;
    }
    else
    {
      v4 = 0;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      66,
      &WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids,
      (unsigned int)v3);
  }
  if ( lpSubKey[0] != v7 )
    operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
  return v4;
}

```

## disassembly

```asm
0x18002b3a0  mov     r11, rsp
0x18002b3a3  mov     [r11+8], rbx
0x18002b3a7  push    rsi
0x18002b3a8  sub     rsp, 40h
0x18002b3ac  mov     rbx, rcx
0x18002b3af  lea     rax, [r11-18h]
0x18002b3b3  mov     [r11-28h], rax
0x18002b3b7  lea     rax, [r11-18h]
0x18002b3bb  mov     [r11-20h], rax
0x18002b3bf  xor     eax, eax
0x18002b3c1  mov     [rsp+48h+var_18], ax
0x18002b3c6  xor     edx, edx; int
0x18002b3c8  call    ?EnableHKCULookupForIFEO@CAutoVerifierPlugin@@AEAAJH@Z; CAutoVerifierPlugin::EnableHKCULookupForIFEO(int)
0x18002b3cd  xor     edx, edx; unsigned int
0x18002b3cf  call    ?SetAutoverifierEnabledFlag@CAutoVerifierPlugin@@AEAAJK@Z; CAutoVerifierPlugin::SetAutoverifierEnabledFlag(ulong)
0x18002b3d4  lea     rsi, WPP_GLOBAL_Control
0x18002b3db  test    eax, eax
0x18002b3dd  jns     short loc_18002B406
0x18002b3df  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3e6  cmp     rcx, rsi
0x18002b3e9  jz      short loc_18002B406
0x18002b3eb  test    byte ptr [rcx+1Ch], 1
0x18002b3ef  jz      short loc_18002B406
0x18002b3f1  mov     edx, 41h ; 'A'
0x18002b3f6  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002b3fd  mov     rcx, [rcx+10h]
0x18002b401  call    WPP_SF_
0x18002b406  mov     r8, [rbx+2E8h]
0x18002b40d  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002b414  lea     rcx, [rsp+48h+lpSubKey]
0x18002b419  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18002b41e  mov     ebx, eax
0x18002b420  test    eax, eax
0x18002b422  jns     short loc_18002B450
0x18002b424  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b42b  cmp     rcx, rsi
0x18002b42e  jz      short loc_18002B496
0x18002b430  test    byte ptr [rcx+1Ch], 1
0x18002b434  jz      short loc_18002B496
0x18002b436  mov     edx, 42h ; 'B'
0x18002b43b  mov     r9d, eax
0x18002b43e  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002b445  mov     rcx, [rcx+10h]
0x18002b449  call    WPP_SF_d
0x18002b44e  jmp     short loc_18002B496
0x18002b450  mov     rdx, [rsp+48h+lpSubKey]; lpSubKey
0x18002b455  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002b45c  call    cs:__imp_RegDeleteKeyW
0x18002b462  test    eax, eax
0x18002b464  jz      short loc_18002B494
0x18002b466  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b46d  cmp     rcx, rsi
0x18002b470  jz      short loc_18002B48D
0x18002b472  test    byte ptr [rcx+1Ch], 1
0x18002b476  jz      short loc_18002B48D
0x18002b478  mov     edx, 43h ; 'C'
0x18002b47d  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002b484  mov     rcx, [rcx+10h]
0x18002b488  call    WPP_SF_
0x18002b48d  mov     ebx, 80004005h
0x18002b492  jmp     short loc_18002B496
0x18002b494  xor     ebx, ebx
0x18002b496  lea     rax, [rsp+48h+var_18]
0x18002b49b  mov     rcx, [rsp+48h+lpSubKey]; void *
0x18002b4a0  cmp     rcx, rax
0x18002b4a3  jz      short loc_18002B4B1
0x18002b4a5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b4ac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b4b1  mov     eax, ebx
0x18002b4b3  mov     rbx, [rsp+48h+arg_0]
0x18002b4b8  add     rsp, 40h
0x18002b4bc  pop     rsi
0x18002b4bd  retn
```
