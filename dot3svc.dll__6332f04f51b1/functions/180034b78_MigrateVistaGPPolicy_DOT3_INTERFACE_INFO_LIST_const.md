# MigrateVistaGPPolicy(_DOT3_INTERFACE_INFO_LIST const *)

- ea: `0x180034b78`
- end: `0x180034eac`
- name: `?MigrateVistaGPPolicy@@YAJPEBU_DOT3_INTERFACE_INFO_LIST@@@Z`
- size: `820`
- prototype: `__int64 __fastcall(const struct _DOT3_INTERFACE_INFO_LIST *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035348`

## callees

- `0x1800025f0`
- `0x180003114`
- `0x180003be4`
- `0x18000a9c0`
- `0x18000c230`
- `0x180033de4`
- `0x180034080`
- `0x180034b78`
- `0x180038ed4`
- `0x18003cb60`
- `0x18003cff4`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!PathAppendW` at `0x180034ced`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathAppendW` at `0x180034ced`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180034c6d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180034c6d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathAndSubDirW` at `0x180034ca1`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathAndSubDirW` at `0x180034ca1`
- `ext-ms-win-dot3-grouppolicy-l1-1-0!DeserializeLANPolicy` at `0x180034db2`
- `ext-ms-win-dot3-grouppolicy-l1-1-0!DeserializeLANPolicy` at `0x180034db2`

## pseudocode

```c
__int64 __fastcall MigrateVistaGPPolicy(const struct _DOT3_INTERFACE_INFO_LIST *a1)
{
  const unsigned __int16 *v2; // rcx
  unsigned int v3; // ebx
  struct _LIST_ENTRY *v4; // rcx
  int v5; // eax
  const WCHAR *FileNameW; // rdi
  HRESULT v7; // eax
  struct _LIST_ENTRY *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  struct _PM_PROFILE *v11; // rcx
  int v12; // eax
  struct _PM_PROFILE *lpMem; // [rsp+30h] [rbp-D0h] BYREF
  struct tagPolicyMetadata *v15; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+50h] [rbp-B0h]
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v20[2044]; // [rsp+274h] [rbp+174h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 23, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids);
  }
  if ( (unsigned __int8)IsLANGPADeInitPresent() )
  {
    v15 = 0;
    v17 = 0;
    lpMem = 0;
    v16 = 0;
    v5 = RetrievePolicyInfoFromRegistry(v2, &v15);
    v3 = v5;
    if ( v5 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v9 = 27;
        v10 = (unsigned int)v5;
        goto LABEL_29;
      }
    }
    else
    {
      FileNameW = PathFindFileNameW(*((LPCWSTR *)v15 + 2));
      if ( !FileNameW )
      {
        v3 = -2147467261;
LABEL_30:
        v8 = WPP_GLOBAL_Control;
        goto LABEL_31;
      }
      v7 = SHGetFolderPathAndSubDirW(0, 35, 0, 1u, L"Microsoft\\dot3svc\\MigrationData\\Policies", pszPath);
      v3 = v7;
      if ( v7 == 1 )
      {
        v3 = -2147287037;
      }
      else if ( v7 >= 0 )
      {
        if ( !PathAppendW(pszPath, FileNameW) )
        {
          v3 = -2147024774;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
LABEL_39:
            v11 = lpMem;
            if ( lpMem )
            {
              v12 = ApplyGPProfilesToAllTargets(lpMem, a1);
              v3 = v12;
              if ( v12 < 0
                && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control[1].Blink)
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control[1].Flink,
                  29,
                  &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids,
                  (unsigned int)v12);
              }
              v11 = lpMem;
            }
            XsFreeProfile(v11);
            FreePolicyMetadata(&v15);
            goto LABEL_47;
          }
          if ( !BYTE1(WPP_GLOBAL_Control[1].Blink) || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
          {
LABEL_35:
            if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v8[1].Blink) && (BYTE4(v8[1].Blink) & 1) != 0 )
              WPP_SF_d(v8[1].Flink, 28, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids, v3);
            goto LABEL_39;
          }
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 25, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids, 2147942522LL);
        }
        goto LABEL_30;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v9 = 26;
        v10 = v3;
LABEL_29:
        WPP_SF_d(v8[1].Flink, v9, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids, v10);
        goto LABEL_30;
      }
    }
LABEL_31:
    if ( (v3 & 0x80000000) == 0 )
    {
      v19 = 45;
      memset_0(v20, 0, sizeof(v20));
      v3 = DeserializeLANPolicy(pszPath, &v19, &v16, &lpMem, 0);
      if ( (v3 & 0x80000000) == 0 )
      {
        v3 = ApplyGPSettingsToAllTargets((struct _LAN_GP_SETTINGS *)&v16, a1);
        goto LABEL_39;
      }
      v8 = WPP_GLOBAL_Control;
    }
    goto LABEL_35;
  }
  v3 = -2147467263;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v3;
  if ( BYTE1(WPP_GLOBAL_Control[1].Blink) && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 24, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids, 2147500033LL);
LABEL_47:
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v4[1].Blink) >= 4u && (BYTE4(v4[1].Blink) & 1) != 0 )
    WPP_SF_d(v4[1].Flink, 30, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180034b78  mov     [rsp-8+arg_8], rbx
0x180034b7d  mov     [rsp-8+arg_10], rsi
0x180034b82  push    rbp
0x180034b83  push    rdi
0x180034b84  push    r12
0x180034b86  push    r13
0x180034b88  push    r14
0x180034b8a  lea     rbp, [rsp-980h]
0x180034b92  sub     rsp, 0A80h
0x180034b99  mov     rax, cs:__security_cookie
0x180034ba0  xor     rax, rsp
0x180034ba3  mov     [rbp+9A0h+var_30], rax
0x180034baa  mov     rsi, rcx
0x180034bad  mov     rcx, cs:WPP_GLOBAL_Control
0x180034bb4  lea     r12, WPP_GLOBAL_Control
0x180034bbb  lea     r13, WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids
0x180034bc2  mov     r14d, 1
0x180034bc8  cmp     rcx, r12
0x180034bcb  jz      short loc_180034BE9
0x180034bcd  cmp     byte ptr [rcx+19h], 4
0x180034bd1  jb      short loc_180034BE9
0x180034bd3  test    [rcx+1Ch], r14b
0x180034bd7  jz      short loc_180034BE9
0x180034bd9  mov     rcx, [rcx+10h]
0x180034bdd  lea     edx, [r14+16h]
0x180034be1  mov     r8, r13
0x180034be4  call    WPP_SF_
0x180034be9  call    IsLANGPADeInitPresent
0x180034bee  test    al, al
0x180034bf0  jnz     short loc_180034C34
0x180034bf2  mov     ebx, 80004001h
0x180034bf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180034bfe  cmp     rcx, r12
0x180034c01  jz      loc_180034E7F
0x180034c07  cmp     [rcx+19h], r14b
0x180034c0b  jb      loc_180034E5A
0x180034c11  test    [rcx+1Ch], r14b
0x180034c15  jz      loc_180034E5A
0x180034c1b  mov     rcx, [rcx+10h]
0x180034c1f  mov     edx, 18h
0x180034c24  mov     r9d, ebx
0x180034c27  mov     r8, r13
0x180034c2a  call    WPP_SF_d
0x180034c2f  jmp     loc_180034E53
0x180034c34  xor     eax, eax
0x180034c36  mov     [rsp+0AA0h+var_A68], 0
0x180034c3f  xorps   xmm0, xmm0
0x180034c42  mov     [rsp+0AA0h+var_A50], eax
0x180034c46  lea     rdx, [rsp+0AA0h+var_A68]; struct tagPolicyMetadata **
0x180034c4b  mov     [rsp+0AA0h+lpMem], rax
0x180034c50  movups  [rsp+0AA0h+var_A60], xmm0
0x180034c55  call    ?RetrievePolicyInfoFromRegistry@@YAJPEBGPEAPEAUtagPolicyMetadata@@@Z; RetrievePolicyInfoFromRegistry(ushort const *,tagPolicyMetadata * *)
0x180034c5a  mov     ebx, eax
0x180034c5c  test    eax, eax
0x180034c5e  js      loc_180034D3E
0x180034c64  mov     rcx, [rsp+0AA0h+var_A68]
0x180034c69  mov     rcx, [rcx+10h]; pszPath
0x180034c6d  call    cs:__imp_PathFindFileNameW
0x180034c73  mov     rdi, rax
0x180034c76  test    rax, rax
0x180034c79  jz      loc_180034D37
0x180034c7f  xor     r8d, r8d; hToken
0x180034c82  lea     rax, [rsp+0AA0h+var_A40]
0x180034c87  mov     [rsp+0AA0h+pszPath], rax; pszPath
0x180034c8c  mov     r9d, r14d; dwFlags
0x180034c8f  lea     rax, pszSubDir; "Microsoft\\dot3svc\\MigrationData\\Poli"...
0x180034c96  xor     ecx, ecx; hwnd
0x180034c98  mov     [rsp+0AA0h+pszSubDir], rax; pszSubDir
0x180034c9d  lea     edx, [r8+23h]; csidl
0x180034ca1  call    cs:__imp_SHGetFolderPathAndSubDirW
0x180034ca7  mov     ebx, eax
0x180034ca9  cmp     eax, r14d
0x180034cac  jnz     short loc_180034CE1
0x180034cae  mov     ebx, 80030003h
0x180034cb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180034cba  cmp     rcx, r12
0x180034cbd  jz      loc_180034D71
0x180034cc3  cmp     [rcx+19h], r14b
0x180034cc7  jb      loc_180034D71
0x180034ccd  test    [rcx+1Ch], r14b
0x180034cd1  jz      loc_180034D71
0x180034cd7  mov     edx, 1Ah
0x180034cdc  mov     r9d, ebx
0x180034cdf  jmp     short loc_180034D5E
0x180034ce1  test    eax, eax
0x180034ce3  js      short loc_180034CB3
0x180034ce5  mov     rdx, rdi; pszMore
0x180034ce8  lea     rcx, [rsp+0AA0h+var_A40]; pszPath
0x180034ced  call    cs:__imp_PathAppendW
0x180034cf3  test    eax, eax
0x180034cf5  jnz     short loc_180034D6A
0x180034cf7  mov     ebx, 8007007Ah
0x180034cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180034d03  cmp     rcx, r12
0x180034d06  jz      loc_180034DFB
0x180034d0c  cmp     [rcx+19h], r14b
0x180034d10  jb      loc_180034DD6
0x180034d16  test    [rcx+1Ch], r14b
0x180034d1a  jz      loc_180034DD6
0x180034d20  mov     rcx, [rcx+10h]
0x180034d24  lea     edx, [rax+19h]
0x180034d27  mov     r9d, 8007007Ah
0x180034d2d  mov     r8, r13
0x180034d30  call    WPP_SF_d
0x180034d35  jmp     short loc_180034D6A
0x180034d37  mov     ebx, 80004003h
0x180034d3c  jmp     short loc_180034D6A
0x180034d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180034d45  cmp     rcx, r12
0x180034d48  jz      short loc_180034D71
0x180034d4a  cmp     [rcx+19h], r14b
0x180034d4e  jb      short loc_180034D71
0x180034d50  test    [rcx+1Ch], r14b
0x180034d54  jz      short loc_180034D71
0x180034d56  mov     edx, 1Bh
0x180034d5b  mov     r9d, eax
0x180034d5e  mov     rcx, [rcx+10h]
0x180034d62  mov     r8, r13
0x180034d65  call    WPP_SF_d
0x180034d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180034d71  test    ebx, ebx
0x180034d73  js      short loc_180034DD6
0x180034d75  xor     edx, edx; Val
0x180034d77  mov     [rbp+9A0h+var_830], 2Dh ; '-'
0x180034d81  mov     r8d, 7FCh; Size
0x180034d87  lea     rcx, [rbp+9A0h+var_82C]; void *
0x180034d8e  call    memset_0
0x180034d93  lea     r9, [rsp+0AA0h+lpMem]
0x180034d98  mov     [rsp+0AA0h+pszSubDir], 0
0x180034da1  lea     r8, [rsp+0AA0h+var_A60]
0x180034da6  lea     rdx, [rbp+9A0h+var_830]
0x180034dad  lea     rcx, [rsp+0AA0h+var_A40]
0x180034db2  call    cs:__imp_DeserializeLANPolicy
0x180034db8  mov     ebx, eax
0x180034dba  test    eax, eax
0x180034dbc  js      short loc_180034DCF
0x180034dbe  mov     rdx, rsi; struct _DOT3_INTERFACE_INFO_LIST *
0x180034dc1  lea     rcx, [rsp+0AA0h+var_A60]; struct _LAN_GP_SETTINGS *
0x180034dc6  call    ?ApplyGPSettingsToAllTargets@@YAJPEAU_LAN_GP_SETTINGS@@PEBU_DOT3_INTERFACE_INFO_LIST@@@Z; ApplyGPSettingsToAllTargets(_LAN_GP_SETTINGS *,_DOT3_INTERFACE_INFO_LIST const *)
0x180034dcb  mov     ebx, eax
0x180034dcd  jmp     short loc_180034DFB
0x180034dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180034dd6  cmp     rcx, r12
0x180034dd9  jz      short loc_180034DFB
0x180034ddb  cmp     [rcx+19h], r14b
0x180034ddf  jb      short loc_180034DFB
0x180034de1  test    [rcx+1Ch], r14b
0x180034de5  jz      short loc_180034DFB
0x180034de7  mov     rcx, [rcx+10h]
0x180034deb  mov     edx, 1Ch
0x180034df0  mov     r9d, ebx
0x180034df3  mov     r8, r13
0x180034df6  call    WPP_SF_d
0x180034dfb  mov     rcx, [rsp+0AA0h+lpMem]; struct _PM_PROFILE *
0x180034e00  test    rcx, rcx
0x180034e03  jz      short loc_180034E44
0x180034e05  mov     rdx, rsi; struct _DOT3_INTERFACE_INFO_LIST *
0x180034e08  call    ?ApplyGPProfilesToAllTargets@@YAJPEAU_PM_PROFILE@@PEBU_DOT3_INTERFACE_INFO_LIST@@@Z; ApplyGPProfilesToAllTargets(_PM_PROFILE *,_DOT3_INTERFACE_INFO_LIST const *)
0x180034e0d  mov     ebx, eax
0x180034e0f  test    eax, eax
0x180034e11  jns     short loc_180034E3F
0x180034e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e1a  cmp     rcx, r12
0x180034e1d  jz      short loc_180034E3F
0x180034e1f  cmp     [rcx+19h], r14b
0x180034e23  jb      short loc_180034E3F
0x180034e25  test    [rcx+1Ch], r14b
0x180034e29  jz      short loc_180034E3F
0x180034e2b  mov     rcx, [rcx+10h]
0x180034e2f  mov     edx, 1Dh
0x180034e34  mov     r9d, eax
0x180034e37  mov     r8, r13
0x180034e3a  call    WPP_SF_d
0x180034e3f  mov     rcx, [rsp+0AA0h+lpMem]; lpMem
0x180034e44  call    ?XsFreeProfile@@YAXPEAU_PM_PROFILE@@@Z; XsFreeProfile(_PM_PROFILE *)
0x180034e49  lea     rcx, [rsp+0AA0h+var_A68]; struct tagPolicyMetadata **
0x180034e4e  call    ?FreePolicyMetadata@@YAXPEAPEAUtagPolicyMetadata@@@Z; FreePolicyMetadata(tagPolicyMetadata * *)
0x180034e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e5a  cmp     rcx, r12
0x180034e5d  jz      short loc_180034E7F
0x180034e5f  cmp     byte ptr [rcx+19h], 4
0x180034e63  jb      short loc_180034E7F
0x180034e65  test    [rcx+1Ch], r14b
0x180034e69  jz      short loc_180034E7F
0x180034e6b  mov     rcx, [rcx+10h]
0x180034e6f  mov     edx, 1Eh
0x180034e74  mov     r9d, ebx
0x180034e77  mov     r8, r13
0x180034e7a  call    WPP_SF_d
0x180034e7f  mov     eax, ebx
0x180034e81  mov     rcx, [rbp+9A0h+var_30]
0x180034e88  xor     rcx, rsp; StackCookie
0x180034e8b  call    __security_check_cookie
0x180034e90  lea     r11, [rsp+0AA0h+var_20]
0x180034e98  mov     rbx, [r11+38h]
0x180034e9c  mov     rsi, [r11+40h]
0x180034ea0  mov     rsp, r11
0x180034ea3  pop     r14
0x180034ea5  pop     r13
0x180034ea7  pop     r12
0x180034ea9  pop     rdi
0x180034eaa  pop     rbp
0x180034eab  retn
```
