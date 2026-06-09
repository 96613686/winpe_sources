# CFveApi::AttemptUserAutoUnlock(void)

- ea: `0x1800ceb48`
- end: `0x1800cefa1`
- name: `?AttemptUserAutoUnlock@CFveApi@@IEAAJXZ`
- size: `1113`
- prototype: `__int64 __fastcall(CFveApi *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ce2cc`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180037f50`
- `0x180079538`
- `0x1800ceb48`
- `0x1800cf934`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cef0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180128241`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cef0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180128241`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800cec9f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800cec9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cebfe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cebfe`

## pseudocode

```c
__int64 __fastcall CFveApi::AttemptUserAutoUnlock(CFveApi *this)
{
  DWORD v2; // r14d
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  LSTATUS v7; // eax
  CFveApi *v8; // rcx
  int v9; // eax
  CFveApi *v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  struct _FVE_AUTH_INFORMATION *v15; // [rsp+48h] [rbp-290h] BYREF
  unsigned __int64 v16; // [rsp+50h] [rbp-288h] BYREF
  unsigned __int64 v17; // [rsp+58h] [rbp-280h] BYREF
  DWORD v18; // [rsp+60h] [rbp-278h]
  HKEY hKey; // [rsp+68h] [rbp-270h] BYREF
  void *lpMem; // [rsp+70h] [rbp-268h] BYREF
  DWORD cchName; // [rsp+78h] [rbp-260h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-258h] BYREF

  memset_0(Name, 0, 0x208u);
  lpMem = 0;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  v2 = 0;
  cchName = 260;
  hKey = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_82fbf6316f983a090a97009b222379cf_Traceguids);
  v3 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\FveAutoUnlock",
         0,
         0x2000000u,
         &hKey);
  v4 = v3;
  if ( v3 == 2 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v6 = 78;
LABEL_53:
      WPP_SF_(v5[2], v6, WPP_82fbf6316f983a090a97009b222379cf_Traceguids);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_54:
    v4 = 0;
    goto LABEL_55;
  }
  if ( !v3 )
  {
    while ( 1 )
    {
      cchName = 260;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_82fbf6316f983a090a97009b222379cf_Traceguids);
      v7 = RegEnumKeyExW(hKey, v2, Name, &cchName, 0, 0, 0, 0);
      v4 = v7;
      if ( v7 == 259 )
        break;
      if ( v7 )
      {
        if ( v7 > 0 )
          v4 = (unsigned __int16)v7 | 0x80070000;
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v12 = 81;
          v13 = v4;
          goto LABEL_48;
        }
        goto LABEL_55;
      }
      v8 = (CFveApi *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_82fbf6316f983a090a97009b222379cf_Traceguids);
      v9 = CFveApi::DecryptRegKey(v8, hKey, Name, L"element", &lpMem, &v16);
      v4 = v9;
      if ( v9 < 0 )
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v12 = 83;
LABEL_42:
          v13 = (unsigned int)v9;
LABEL_48:
          WPP_SF_d(v5[2], v12, WPP_82fbf6316f983a090a97009b222379cf_Traceguids, v13);
          goto LABEL_49;
        }
        goto LABEL_55;
      }
      v10 = (CFveApi *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_82fbf6316f983a090a97009b222379cf_Traceguids);
      v9 = CFveApi::DecryptRegKey(v10, hKey, Name, L"info", (void **)&v15, &v17);
      v4 = v9;
      if ( v9 < 0 )
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v12 = 85;
          goto LABEL_42;
        }
        goto LABEL_55;
      }
      *((_QWORD *)v15 + 2) = &lpMem;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_82fbf6316f983a090a97009b222379cf_Traceguids);
      v11 = CFveApiBase::UnlockVolume(this, v15, 0, 0, 0);
      v4 = v11;
      if ( v11 >= 0 )
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_82fbf6316f983a090a97009b222379cf_Traceguids);
          goto LABEL_49;
        }
        goto LABEL_55;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          88,
          WPP_82fbf6316f983a090a97009b222379cf_Traceguids,
          (unsigned int)v11);
      CFveApiBase::ZeroFree(lpMem, v16);
      lpMem = 0;
      CFveApiBase::ZeroFree(v15, v17);
      v15 = 0;
      v18 = ++v2;
    }
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v6 = 80;
      goto LABEL_53;
    }
    goto LABEL_54;
  }
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
LABEL_49:
  v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_55:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( lpMem )
  {
    CFveApiBase::ZeroFree(lpMem, v16);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 )
  {
    CFveApiBase::ZeroFree(v15, v17);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 )
    WPP_SF_d(v5[2], 89, WPP_82fbf6316f983a090a97009b222379cf_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800ceb48  push    rbx
0x1800ceb4a  push    rdi
0x1800ceb4b  push    r12
0x1800ceb4d  push    r13
0x1800ceb4f  push    r14
0x1800ceb51  push    r15
0x1800ceb53  sub     rsp, 2A8h
0x1800ceb5a  mov     rax, cs:__security_cookie
0x1800ceb61  xor     rax, rsp
0x1800ceb64  mov     [rsp+2D8h+var_48], rax
0x1800ceb6c  mov     r15, rcx
0x1800ceb6f  xor     edx, edx; Val
0x1800ceb71  mov     r8d, 208h; Size
0x1800ceb77  lea     rcx, [rsp+2D8h+Name]; void *
0x1800ceb7f  call    memset_0
0x1800ceb84  xor     r12d, r12d
0x1800ceb87  mov     [rsp+2D8h+lpMem], r12
0x1800ceb8c  mov     [rsp+2D8h+var_288], r12
0x1800ceb91  mov     [rsp+2D8h+var_290], r12
0x1800ceb96  mov     [rsp+2D8h+var_280], r12
0x1800ceb9b  mov     r14d, r12d
0x1800ceb9e  mov     [rsp+2D8h+cchName], 104h
0x1800ceba6  mov     [rsp+2D8h+hKey], r12
0x1800cebab  lea     r13, WPP_GLOBAL_Control
0x1800cebb2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cebb9  lea     rdi, WPP_82fbf6316f983a090a97009b222379cf_Traceguids
0x1800cebc0  cmp     rcx, r13
0x1800cebc3  jz      short loc_1800CEBDD
0x1800cebc5  test    byte ptr [rcx+1Ch], 20h
0x1800cebc9  jz      short loc_1800CEBDD
0x1800cebcb  lea     edx, [r12+4Dh]
0x1800cebd0  mov     r8, rdi
0x1800cebd3  mov     rcx, [rcx+10h]
0x1800cebd7  call    WPP_SF_
0x1800cebdc  nop
0x1800cebdd  lea     rax, [rsp+2D8h+hKey]
0x1800cebe2  mov     [rsp+2D8h+phkResult], rax; phkResult
0x1800cebe7  mov     r9d, 2000000h; samDesired
0x1800cebed  xor     r8d, r8d; ulOptions
0x1800cebf0  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800cebf7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800cebfe  call    cs:__imp_RegOpenKeyExW
0x1800cec05  nop     dword ptr [rax+rax+00h]
0x1800cec0a  mov     ebx, eax
0x1800cec0c  cmp     eax, 2
0x1800cec0f  jnz     short loc_1800CEC33
0x1800cec11  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cec18  cmp     rcx, r13
0x1800cec1b  jz      loc_1800CEEFA
0x1800cec21  test    byte ptr [rcx+1Ch], 8
0x1800cec25  jz      loc_1800CEEFA
0x1800cec2b  lea     edx, [rax+4Ch]
0x1800cec2e  jmp     loc_1800CEEE7
0x1800cec33  test    eax, eax
0x1800cec35  jz      short loc_1800CEC4B
0x1800cec37  jle     short loc_1800CEC42
0x1800cec39  movzx   ebx, ax
0x1800cec3c  or      ebx, 80070000h
0x1800cec42  mov     [rsp+2D8h+var_298], ebx
0x1800cec46  jmp     loc_1800CEEC7
0x1800cec4b  mov     [rsp+2D8h+cchName], 104h
0x1800cec53  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cec5a  cmp     rcx, r13
0x1800cec5d  jz      short loc_1800CEC76
0x1800cec5f  test    byte ptr [rcx+1Ch], 8
0x1800cec63  jz      short loc_1800CEC76
0x1800cec65  mov     edx, 4Fh ; 'O'
0x1800cec6a  mov     r8, rdi
0x1800cec6d  mov     rcx, [rcx+10h]
0x1800cec71  call    WPP_SF_
0x1800cec76  mov     [rsp+2D8h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800cec7b  mov     [rsp+2D8h+lpcchClass], r12; lpcchClass
0x1800cec80  mov     [rsp+2D8h+lpClass], r12; lpClass
0x1800cec85  mov     [rsp+2D8h+phkResult], r12; lpReserved
0x1800cec8a  lea     r9, [rsp+2D8h+cchName]; lpcchName
0x1800cec8f  lea     r8, [rsp+2D8h+Name]; lpName
0x1800cec97  mov     edx, r14d; dwIndex
0x1800cec9a  mov     rcx, [rsp+2D8h+hKey]; hKey
0x1800cec9f  call    cs:__imp_RegEnumKeyExW
0x1800ceca6  nop     dword ptr [rax+rax+00h]
0x1800cecab  mov     ebx, eax
0x1800cecad  cmp     eax, 103h
0x1800cecb2  jz      loc_1800CEED0
0x1800cecb8  test    eax, eax
0x1800cecba  jnz     loc_1800CEE92
0x1800cecc0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cecc7  cmp     rcx, r13
0x1800cecca  jz      short loc_1800CECE1
0x1800ceccc  test    byte ptr [rcx+1Ch], 8
0x1800cecd0  jz      short loc_1800CECE1
0x1800cecd2  lea     edx, [rax+52h]
0x1800cecd5  mov     r8, rdi
0x1800cecd8  mov     rcx, [rcx+10h]
0x1800cecdc  call    WPP_SF_
0x1800cece1  lea     rax, [rsp+2D8h+var_288]
0x1800cece6  mov     [rsp+2D8h+lpClass], rax; unsigned __int64 *
0x1800ceceb  lea     rax, [rsp+2D8h+lpMem]
0x1800cecf0  mov     [rsp+2D8h+phkResult], rax; void **
0x1800cecf5  lea     r9, aElement; "element"
0x1800cecfc  lea     r8, [rsp+2D8h+Name]; unsigned __int16 *
0x1800ced04  mov     rdx, [rsp+2D8h+hKey]; HKEY
0x1800ced09  call    ?DecryptRegKey@CFveApi@@QEAAJPEAUHKEY__@@PEBG1PEAPEAXPEA_K@Z; CFveApi::DecryptRegKey(HKEY__ *,ushort const *,ushort const *,void * *,unsigned __int64 *)
0x1800ced0e  mov     ebx, eax
0x1800ced10  mov     [rsp+2D8h+var_298], eax
0x1800ced14  test    eax, eax
0x1800ced16  js      loc_1800CEE76
0x1800ced1c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ced23  cmp     rcx, r13
0x1800ced26  jz      short loc_1800CED3F
0x1800ced28  test    byte ptr [rcx+1Ch], 8
0x1800ced2c  jz      short loc_1800CED3F
0x1800ced2e  mov     edx, 54h ; 'T'
0x1800ced33  mov     r8, rdi
0x1800ced36  mov     rcx, [rcx+10h]
0x1800ced3a  call    WPP_SF_
0x1800ced3f  lea     rax, [rsp+2D8h+var_280]
0x1800ced44  mov     [rsp+2D8h+lpClass], rax; unsigned __int64 *
0x1800ced49  lea     rax, [rsp+2D8h+var_290]
0x1800ced4e  mov     [rsp+2D8h+phkResult], rax; void **
0x1800ced53  lea     r9, aInfo; "info"
0x1800ced5a  lea     r8, [rsp+2D8h+Name]; unsigned __int16 *
0x1800ced62  mov     rdx, [rsp+2D8h+hKey]; HKEY
0x1800ced67  call    ?DecryptRegKey@CFveApi@@QEAAJPEAUHKEY__@@PEBG1PEAPEAXPEA_K@Z; CFveApi::DecryptRegKey(HKEY__ *,ushort const *,ushort const *,void * *,unsigned __int64 *)
0x1800ced6c  mov     ebx, eax
0x1800ced6e  mov     [rsp+2D8h+var_298], eax
0x1800ced72  test    eax, eax
0x1800ced74  js      loc_1800CEE55
0x1800ced7a  lea     rcx, [rsp+2D8h+lpMem]
0x1800ced7f  mov     rax, [rsp+2D8h+var_290]
0x1800ced84  mov     [rax+10h], rcx
0x1800ced88  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ced8f  cmp     rcx, r13
0x1800ced92  jz      short loc_1800CEDAB
0x1800ced94  test    byte ptr [rcx+1Ch], 8
0x1800ced98  jz      short loc_1800CEDAB
0x1800ced9a  mov     edx, 56h ; 'V'
0x1800ced9f  mov     r8, rdi
0x1800ceda2  mov     rcx, [rcx+10h]
0x1800ceda6  call    WPP_SF_
0x1800cedab  mov     [rsp+2D8h+phkResult], r12; bool *
0x1800cedb0  xor     r9d, r9d; void (*)(const void *)
0x1800cedb3  xor     r8d, r8d; bool
0x1800cedb6  mov     rdx, [rsp+2D8h+var_290]; struct _FVE_AUTH_INFORMATION *
0x1800cedbb  mov     rcx, r15; this
0x1800cedbe  call    ?UnlockVolume@CFveApiBase@@QEAAJPEBU_FVE_AUTH_INFORMATION@@_NP6AXPEBX@ZPEA_N@Z; CFveApiBase::UnlockVolume(_FVE_AUTH_INFORMATION const *,bool,void (*)(void const *),bool *)
0x1800cedc3  mov     ebx, eax
0x1800cedc5  mov     [rsp+2D8h+var_298], eax
0x1800cedc9  test    eax, eax
0x1800cedcb  jns     short loc_1800CEE28
0x1800cedcd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cedd4  cmp     rcx, r13
0x1800cedd7  jz      short loc_1800CEDF3
0x1800cedd9  test    byte ptr [rcx+1Ch], 4
0x1800ceddd  jz      short loc_1800CEDF3
0x1800ceddf  mov     edx, 58h ; 'X'
0x1800cede4  mov     r9d, eax
0x1800cede7  mov     r8, rdi
0x1800cedea  mov     rcx, [rcx+10h]
0x1800cedee  call    WPP_SF_d
0x1800cedf3  mov     rdx, [rsp+2D8h+var_288]; unsigned __int64
0x1800cedf8  mov     rcx, [rsp+2D8h+lpMem]; lpMem
0x1800cedfd  call    ?ZeroFree@CFveApiBase@@SAJPEAX_K@Z; CFveApiBase::ZeroFree(void *,unsigned __int64)
0x1800cee02  mov     [rsp+2D8h+lpMem], r12
0x1800cee07  mov     rdx, [rsp+2D8h+var_280]; unsigned __int64
0x1800cee0c  mov     rcx, [rsp+2D8h+var_290]; lpMem
0x1800cee11  call    ?ZeroFree@CFveApiBase@@SAJPEAX_K@Z; CFveApiBase::ZeroFree(void *,unsigned __int64)
0x1800cee16  mov     [rsp+2D8h+var_290], r12
0x1800cee1b  inc     r14d
0x1800cee1e  mov     [rsp+2D8h+var_278], r14d
0x1800cee23  jmp     loc_1800CEC4B
0x1800cee28  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cee2f  cmp     rcx, r13
0x1800cee32  jz      loc_1800CEF01
0x1800cee38  test    byte ptr [rcx+1Ch], 8
0x1800cee3c  jz      loc_1800CEF01
0x1800cee42  mov     edx, 57h ; 'W'
0x1800cee47  mov     r8, rdi
0x1800cee4a  mov     rcx, [rcx+10h]
0x1800cee4e  call    WPP_SF_
0x1800cee53  jmp     short loc_1800CEEC7
0x1800cee55  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cee5c  cmp     rcx, r13
0x1800cee5f  jz      loc_1800CEF01
0x1800cee65  test    byte ptr [rcx+1Ch], 4
0x1800cee69  jz      loc_1800CEF01
0x1800cee6f  mov     edx, 55h ; 'U'
0x1800cee74  jmp     short loc_1800CEE8D
0x1800cee76  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cee7d  cmp     rcx, r13
0x1800cee80  jz      short loc_1800CEF01
0x1800cee82  test    byte ptr [rcx+1Ch], 4
0x1800cee86  jz      short loc_1800CEF01
0x1800cee88  mov     edx, 53h ; 'S'
0x1800cee8d  mov     r9d, eax
0x1800cee90  jmp     short loc_1800CEEBB
0x1800cee92  jle     short loc_1800CEE9D
0x1800cee94  movzx   ebx, ax
0x1800cee97  or      ebx, 80070000h
0x1800cee9d  mov     [rsp+2D8h+var_298], ebx
0x1800ceea1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ceea8  cmp     rcx, r13
0x1800ceeab  jz      short loc_1800CEF01
0x1800ceead  test    byte ptr [rcx+1Ch], 4
0x1800ceeb1  jz      short loc_1800CEF01
0x1800ceeb3  mov     edx, 51h ; 'Q'
0x1800ceeb8  mov     r9d, ebx
0x1800ceebb  mov     r8, rdi
0x1800ceebe  mov     rcx, [rcx+10h]
0x1800ceec2  call    WPP_SF_d
0x1800ceec7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ceece  jmp     short loc_1800CEF01
0x1800ceed0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ceed7  cmp     rcx, r13
0x1800ceeda  jz      short loc_1800CEEFA
0x1800ceedc  test    byte ptr [rcx+1Ch], 8
0x1800ceee0  jz      short loc_1800CEEFA
0x1800ceee2  mov     edx, 50h ; 'P'
0x1800ceee7  mov     r8, rdi
0x1800ceeea  mov     rcx, [rcx+10h]
0x1800ceeee  call    WPP_SF_
0x1800ceef3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ceefa  mov     ebx, r12d
0x1800ceefd  mov     [rsp+2D8h+var_298], ebx
0x1800cef01  mov     rax, [rsp+2D8h+hKey]
0x1800cef06  test    rax, rax
0x1800cef09  jz      short loc_1800CEF21
0x1800cef0b  mov     rcx, rax; hKey
0x1800cef0e  call    cs:__imp_RegCloseKey
0x1800cef15  nop     dword ptr [rax+rax+00h]
0x1800cef1a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cef21  mov     rax, [rsp+2D8h+lpMem]
0x1800cef26  test    rax, rax
0x1800cef29  jz      short loc_1800CEF3F
0x1800cef2b  mov     rdx, [rsp+2D8h+var_288]; unsigned __int64
0x1800cef30  mov     rcx, rax; lpMem
0x1800cef33  call    ?ZeroFree@CFveApiBase@@SAJPEAX_K@Z; CFveApiBase::ZeroFree(void *,unsigned __int64)
0x1800cef38  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cef3f  mov     rax, [rsp+2D8h+var_290]
0x1800cef44  test    rax, rax
0x1800cef47  jz      short loc_1800CEF5D
0x1800cef49  mov     rdx, [rsp+2D8h+var_280]; unsigned __int64
0x1800cef4e  mov     rcx, rax; lpMem
0x1800cef51  call    ?ZeroFree@CFveApiBase@@SAJPEAX_K@Z; CFveApiBase::ZeroFree(void *,unsigned __int64)
0x1800cef56  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cef5d  cmp     rcx, r13
0x1800cef60  jz      short loc_1800CEF7C
0x1800cef62  test    byte ptr [rcx+1Ch], 20h
0x1800cef66  jz      short loc_1800CEF7C
0x1800cef68  mov     edx, 59h ; 'Y'
0x1800cef6d  mov     r9d, ebx
0x1800cef70  mov     r8, rdi
0x1800cef73  mov     rcx, [rcx+10h]
0x1800cef77  call    WPP_SF_d
0x1800cef7c  mov     eax, ebx
0x1800cef7e  mov     rcx, [rsp+2D8h+var_48]
0x1800cef86  xor     rcx, rsp; StackCookie
0x1800cef89  call    __security_check_cookie
0x1800cef8e  add     rsp, 2A8h
0x1800cef95  pop     r15
0x1800cef97  pop     r14
0x1800cef99  pop     r13
0x1800cef9b  pop     r12
0x1800cef9d  pop     rdi
0x1800cef9e  pop     rbx
0x1800cef9f  retn
0x18012822f  push    rbp
0x180128231  sub     rsp, 40h
0x180128235  mov     rbp, rdx
0x180128238  mov     rcx, [rbp+68h]; hKey
0x18012823c  test    rcx, rcx
0x18012823f  jz      short loc_18012824E
0x180128241  call    cs:__imp_RegCloseKey
0x180128248  nop     dword ptr [rax+rax+00h]
0x18012824d  nop
0x18012824e  mov     rcx, [rbp+70h]; lpMem
0x180128252  test    rcx, rcx
0x180128255  jz      short loc_180128261
0x180128257  mov     rdx, [rbp+50h]; unsigned __int64
0x18012825b  call    ?ZeroFree@CFveApiBase@@SAJPEAX_K@Z; CFveApiBase::ZeroFree(void *,unsigned __int64)
0x180128260  nop
0x180128261  mov     rcx, [rbp+48h]; lpMem
0x180128265  test    rcx, rcx
0x180128268  jz      short loc_180128274
0x18012826a  mov     rdx, [rbp+58h]; unsigned __int64
0x18012826e  call    ?ZeroFree@CFveApiBase@@SAJPEAX_K@Z; CFveApiBase::ZeroFree(void *,unsigned __int64)
0x180128273  nop
0x180128274  add     rsp, 40h
0x180128278  pop     rbp
0x180128279  retn
```
