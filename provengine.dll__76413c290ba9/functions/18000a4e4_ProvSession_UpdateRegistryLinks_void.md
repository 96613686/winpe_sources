# ProvSession::UpdateRegistryLinks(void)

- ea: `0x18000a4e4`
- end: `0x18000a7eb`
- name: `?UpdateRegistryLinks@ProvSession@@AEAAJXZ`
- size: `775`
- prototype: `__int64 __fastcall(ProvSession *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180009924`

## callees

- `0x1800010c8`
- `0x180009348`
- `0x1800098dc`
- `0x180009900`
- `0x18000a4e4`
- `0x180033218`
- `0x180033354`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a6c1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a72a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a788`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a7bf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a6c1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a72a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a788`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a7bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a67e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a67e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a6ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a718`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a741`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a6ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a718`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a741`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a56a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a56a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ProvSession::UpdateRegistryLinks(HKEY *this)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  const BYTE **v5; // rbx
  const BYTE *v6; // r8
  LSTATUS v7; // eax
  unsigned int v8; // edi
  const WCHAR *v9; // rdx
  unsigned int v10; // eax
  const BYTE **v11; // rdi
  const BYTE *v12; // r8
  LSTATUS v13; // eax
  unsigned int v14; // r14d
  int v15; // eax
  int lpcSubKeys; // [rsp+20h] [rbp-69h]
  DWORD cSubKeys; // [rsp+60h] [rbp-29h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-21h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int64 v20; // [rsp+88h] [rbp-1h]
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+90h] [rbp+7h] BYREF
  HKEY *p_phkResult; // [rsp+B0h] [rbp+27h]
  __int64 v23; // [rsp+B8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  cSubKeys = 0;
  v2 = RegQueryInfoKeyW(this[11], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( (v3 & 0x80000000) != 0 )
  {
    if ( (unsigned int)dword_18005A000 > 3 )
    {
      LODWORD(phkResult) = v3;
      p_phkResult = &phkResult;
      v23 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18005A000, (unsigned __int8 *)byte_18004E211, 0, 0, 3u, &v21);
    }
    return v3;
  }
  v5 = (const BYTE **)(this + 3);
  if ( cSubKeys == 1 )
  {
    v6 = (unsigned __int64)this[6] < 8 ? (const BYTE *)(this + 3) : *v5;
    v7 = RegSetSzValue(this[11], L"FirstSession", v6);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x148,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
        (const char *)(unsigned int)v7,
        lpcSubKeys);
      return v8;
    }
  }
  v20 = 7;
  lpSubKey[2] = 0;
  LOWORD(lpSubKey[0]) = 0;
  if ( (int)RegGetSzValue(this[11], L"LastSession", lpSubKey) < 0 )
  {
    v11 = (const BYTE **)(this + 3);
  }
  else
  {
    phkResult = 0;
    v9 = (const WCHAR *)lpSubKey;
    if ( v20 >= 8 )
      v9 = lpSubKey[0];
    v10 = RegOpenKeyExW(this[11], v9, 0, 0xFu, &phkResult);
    if ( v10 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x159,
             (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
             (const char *)v10,
             lpcSubKeys);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( v20 >= 8 )
        operator delete((void *)lpSubKey[0]);
      return v3;
    }
    v11 = (const BYTE **)(this + 3);
    if ( (unsigned __int64)this[6] < 8 )
      v12 = (const BYTE *)(this + 3);
    else
      v12 = *v11;
    v13 = RegSetSzValue(phkResult, L"NextSession", v12);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
        (const char *)(unsigned int)v13,
        lpcSubKeys);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( v20 >= 8 )
        operator delete((void *)lpSubKey[0]);
      return v14;
    }
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  if ( cSubKeys <= 0xA )
  {
    v5 = v11;
  }
  else
  {
    v15 = ProvSession::PurgeOldestSession(this);
    v8 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
        (const char *)(unsigned int)v15,
        lpcSubKeys);
      if ( v20 >= 8 )
        operator delete((void *)lpSubKey[0]);
      return v8;
    }
  }
  if ( (unsigned __int64)v5[3] >= 8 )
    v5 = (const BYTE **)*v5;
  RegSetSzValue(this[11], L"LastSession", (const BYTE *)v5);
  if ( v20 >= 8 )
    operator delete((void *)lpSubKey[0]);
  return 0;
}

```

## disassembly

```asm
0x18000a4e4  mov     [rsp-8+arg_8], rbx
0x18000a4e9  mov     [rsp-8+arg_10], rsi
0x18000a4ee  push    rbp
0x18000a4ef  push    rdi
0x18000a4f0  push    r14
0x18000a4f2  lea     rbp, [rsp-47h]
0x18000a4f7  sub     rsp, 0D0h
0x18000a4fe  mov     rax, cs:__security_cookie
0x18000a505  xor     rax, rsp
0x18000a508  mov     [rbp+57h+var_20], rax
0x18000a50c  mov     rsi, rcx
0x18000a50f  mov     [rbp+57h+cSubKeys], 0
0x18000a516  mov     [rsp+0E0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000a51f  mov     [rsp+0E0h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18000a528  mov     [rsp+0E0h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18000a531  mov     [rsp+0E0h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18000a53a  mov     [rsp+0E0h+lpcValues], 0; lpcValues
0x18000a543  mov     [rsp+0E0h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18000a54c  mov     [rsp+0E0h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18000a555  lea     rax, [rbp+57h+cSubKeys]
0x18000a559  mov     [rsp+0E0h+lpcSubKeys], rax; int
0x18000a55e  xor     r9d, r9d; lpReserved
0x18000a561  xor     r8d, r8d; lpcchClass
0x18000a564  xor     edx, edx; lpClass
0x18000a566  mov     rcx, [rcx+58h]; hKey
0x18000a56a  call    cs:__imp_RegQueryInfoKeyW
0x18000a570  mov     ebx, eax
0x18000a572  test    eax, eax
0x18000a574  jle     short loc_18000A57F
0x18000a576  movzx   ebx, ax
0x18000a579  or      ebx, 80070000h
0x18000a57f  test    ebx, ebx
0x18000a581  jns     short loc_18000A5D2
0x18000a583  mov     eax, cs:dword_18005A000
0x18000a589  cmp     eax, 3
0x18000a58c  jbe     short loc_18000A5CB
0x18000a58e  mov     dword ptr [rbp+57h+phkResult], ebx
0x18000a591  lea     rax, [rbp+57h+phkResult]
0x18000a595  mov     [rbp+57h+var_30], rax
0x18000a599  mov     [rbp+57h+var_28], 4
0x18000a5a1  lea     rax, [rbp+57h+var_50]
0x18000a5a5  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax
0x18000a5aa  mov     dword ptr [rsp+0E0h+lpcSubKeys], 3
0x18000a5b2  xor     r9d, r9d
0x18000a5b5  xor     r8d, r8d
0x18000a5b8  lea     rdx, byte_18004E211
0x18000a5bf  lea     rcx, dword_18005A000
0x18000a5c6  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a5cb  mov     eax, ebx
0x18000a5cd  jmp     loc_18000A7C7
0x18000a5d2  lea     rbx, [rsi+18h]
0x18000a5d6  cmp     [rbp+57h+cSubKeys], 1
0x18000a5da  jnz     short loc_18000A620
0x18000a5dc  cmp     qword ptr [rbx+18h], 8
0x18000a5e1  jb      short loc_18000A5E8
0x18000a5e3  mov     r8, [rbx]
0x18000a5e6  jmp     short loc_18000A5EB
0x18000a5e8  mov     r8, rbx; unsigned __int16 *
0x18000a5eb  lea     rdx, aFirstsession; "FirstSession"
0x18000a5f2  mov     rcx, [rsi+58h]; HKEY
0x18000a5f6  call    ?RegSetSzValue@@YAJPEAUHKEY__@@PEBG1@Z; RegSetSzValue(HKEY__ *,ushort const *,ushort const *)
0x18000a5fb  mov     edi, eax
0x18000a5fd  test    eax, eax
0x18000a5ff  jns     short loc_18000A620
0x18000a601  mov     rcx, [rbp+5Fh]; this
0x18000a605  mov     r9d, eax; char *
0x18000a608  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000a60f  mov     edx, 148h; void *
0x18000a614  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a619  mov     eax, edi
0x18000a61b  jmp     loc_18000A7C7
0x18000a620  mov     [rbp+57h+var_58], 7
0x18000a628  mov     [rbp+57h+var_60], 0
0x18000a630  xor     eax, eax
0x18000a632  mov     word ptr [rbp+57h+lpSubKey], ax
0x18000a636  lea     r8, [rbp+57h+lpSubKey]; void *
0x18000a63a  lea     rdx, aLastsession; "LastSession"
0x18000a641  mov     rcx, [rsi+58h]; hKey
0x18000a645  call    ?RegGetSzValue@@YAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegGetSzValue(HKEY__ *,ushort const *,std::wstring &)
0x18000a64a  test    eax, eax
0x18000a64c  js      loc_18000A749
0x18000a652  mov     [rbp+57h+phkResult], 0
0x18000a65a  lea     rdx, [rbp+57h+lpSubKey]
0x18000a65e  cmp     [rbp+57h+var_58], 8
0x18000a663  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18000a668  lea     rax, [rbp+57h+phkResult]
0x18000a66c  mov     [rsp+0E0h+lpcSubKeys], rax; int
0x18000a671  mov     r9d, 0Fh; samDesired
0x18000a677  xor     r8d, r8d; ulOptions
0x18000a67a  mov     rcx, [rsi+58h]; hKey
0x18000a67e  call    cs:__imp_RegOpenKeyExW
0x18000a684  test    eax, eax
0x18000a686  jz      short loc_18000A6CC
0x18000a688  mov     rcx, [rbp+5Fh]; this
0x18000a68c  mov     r9d, eax; char *
0x18000a68f  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000a696  mov     edx, 159h; void *
0x18000a69b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000a6a0  mov     ebx, eax
0x18000a6a2  mov     rcx, [rbp+57h+phkResult]; hKey
0x18000a6a6  test    rcx, rcx
0x18000a6a9  jz      short loc_18000A6B2
0x18000a6ab  call    cs:__imp_RegCloseKey
0x18000a6b1  nop
0x18000a6b2  cmp     [rbp+57h+var_58], 8
0x18000a6b7  jb      loc_18000A5CB
0x18000a6bd  mov     rcx, [rbp+57h+lpSubKey]
0x18000a6c1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a6c7  jmp     loc_18000A5CB
0x18000a6cc  lea     rdi, [rsi+18h]
0x18000a6d0  cmp     qword ptr [rdi+18h], 8
0x18000a6d5  jb      short loc_18000A6DC
0x18000a6d7  mov     r8, [rdi]
0x18000a6da  jmp     short loc_18000A6DF
0x18000a6dc  mov     r8, rdi; unsigned __int16 *
0x18000a6df  lea     rdx, aNextsession; "NextSession"
0x18000a6e6  mov     rcx, [rbp+57h+phkResult]; HKEY
0x18000a6ea  call    ?RegSetSzValue@@YAJPEAUHKEY__@@PEBG1@Z; RegSetSzValue(HKEY__ *,ushort const *,ushort const *)
0x18000a6ef  mov     r14d, eax
0x18000a6f2  test    eax, eax
0x18000a6f4  jns     short loc_18000A738
0x18000a6f6  mov     rcx, [rbp+5Fh]; this
0x18000a6fa  mov     r9d, eax; char *
0x18000a6fd  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000a704  mov     edx, 15Bh; void *
0x18000a709  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a70e  nop
0x18000a70f  mov     rcx, [rbp+57h+phkResult]; hKey
0x18000a713  test    rcx, rcx
0x18000a716  jz      short loc_18000A71F
0x18000a718  call    cs:__imp_RegCloseKey
0x18000a71e  nop
0x18000a71f  cmp     [rbp+57h+var_58], 8
0x18000a724  jb      short loc_18000A730
0x18000a726  mov     rcx, [rbp+57h+lpSubKey]
0x18000a72a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a730  mov     eax, r14d
0x18000a733  jmp     loc_18000A7C7
0x18000a738  mov     rcx, [rbp+57h+phkResult]; hKey
0x18000a73c  test    rcx, rcx
0x18000a73f  jz      short loc_18000A74C
0x18000a741  call    cs:__imp_RegCloseKey
0x18000a747  jmp     short loc_18000A74C
0x18000a749  mov     rdi, rbx
0x18000a74c  cmp     [rbp+57h+cSubKeys], 0Ah
0x18000a750  jbe     short loc_18000A793
0x18000a752  mov     rcx, rsi; this
0x18000a755  call    ?PurgeOldestSession@ProvSession@@AEAAJXZ; ProvSession::PurgeOldestSession(void)
0x18000a75a  mov     edi, eax
0x18000a75c  test    eax, eax
0x18000a75e  jns     short loc_18000A796
0x18000a760  mov     rcx, [rbp+5Fh]; this
0x18000a764  mov     r9d, eax; char *
0x18000a767  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000a76e  mov     edx, 161h; void *
0x18000a773  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a778  nop
0x18000a779  cmp     [rbp+57h+var_58], 8
0x18000a77e  jb      loc_18000A619
0x18000a784  mov     rcx, [rbp+57h+lpSubKey]
0x18000a788  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a78e  jmp     loc_18000A619
0x18000a793  mov     rbx, rdi
0x18000a796  cmp     qword ptr [rbx+18h], 8
0x18000a79b  jb      short loc_18000A7A0
0x18000a79d  mov     rbx, [rbx]
0x18000a7a0  mov     r8, rbx; unsigned __int16 *
0x18000a7a3  lea     rdx, aLastsession; "LastSession"
0x18000a7aa  mov     rcx, [rsi+58h]; HKEY
0x18000a7ae  call    ?RegSetSzValue@@YAJPEAUHKEY__@@PEBG1@Z; RegSetSzValue(HKEY__ *,ushort const *,ushort const *)
0x18000a7b3  nop
0x18000a7b4  cmp     [rbp+57h+var_58], 8
0x18000a7b9  jb      short loc_18000A7C5
0x18000a7bb  mov     rcx, [rbp+57h+lpSubKey]
0x18000a7bf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a7c5  xor     eax, eax
0x18000a7c7  mov     rcx, [rbp+57h+var_20]
0x18000a7cb  xor     rcx, rsp; StackCookie
0x18000a7ce  call    __security_check_cookie
0x18000a7d3  lea     r11, [rsp+0E0h+var_10]
0x18000a7db  mov     rbx, [r11+28h]
0x18000a7df  mov     rsi, [r11+30h]
0x18000a7e3  mov     rsp, r11
0x18000a7e6  pop     r14
0x18000a7e8  pop     rdi
0x18000a7e9  pop     rbp
0x18000a7ea  retn
```
