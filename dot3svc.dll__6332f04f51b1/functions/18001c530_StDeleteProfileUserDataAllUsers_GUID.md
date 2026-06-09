# StDeleteProfileUserDataAllUsers(_GUID *)

- ea: `0x18001c530`
- end: `0x18001c777`
- name: `?StDeleteProfileUserDataAllUsers@@YAKPEAU_GUID@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d638`
- `0x18000e6a8`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001c530`
- `0x18001e620`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001c61f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001c61f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001c5d8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001c6a8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001c5d8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001c6a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c657`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c657`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001c644`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001c644`

## pseudocode

```c
__int64 __fastcall StDeleteProfileUserDataAllUsers(GUID *rguid)
{
  unsigned int RegKeyPath; // ebx
  DWORD i; // edi
  unsigned int v4; // eax
  DWORD v5; // ecx
  __int64 v6; // rcx
  unsigned int v7; // eax
  struct _LIST_ENTRY *v8; // rcx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  PSID Sid; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  cchName = 0;
  Sid = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 43, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
  }
  RegKeyPath = StpGetRegKeyPath(rguid, 0, 1, SubKey, 0x104u);
  if ( RegKeyPath )
  {
LABEL_22:
    v8 = WPP_GLOBAL_Control;
  }
  else
  {
    RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
    for ( i = 0; ; ++i )
    {
      cchName = 260;
      v4 = RegEnumKeyExW(HKEY_USERS, i, SubKey, &cchName, 0, 0, 0, 0);
      RegKeyPath = v4;
      if ( v4 == 259 )
      {
        RegKeyPath = 0;
        goto LABEL_22;
      }
      if ( v4 )
        break;
      if ( ConvertStringSidToSidW(SubKey, &Sid) )
      {
        LocalFree(Sid);
        v5 = cchName;
        SubKey[cchName] = RegKeyPath + 92;
        v6 = v5 + 1;
        cchName = v6;
        RegKeyPath = StpGetRegKeyPath(rguid, 0, 0, &SubKey[v6], 260 - v6);
        if ( RegKeyPath )
          goto LABEL_22;
        v7 = RegDeleteTreeW(HKEY_USERS, SubKey);
        if ( (v7 & 0xFFFFFFFD) != 0
          && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control[1].Blink)
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 45, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, v7);
        }
      }
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return RegKeyPath;
    if ( BYTE1(WPP_GLOBAL_Control[1].Blink) && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 44, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, v4);
      goto LABEL_22;
    }
  }
  if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v8[1].Blink) >= 4u && (BYTE4(v8[1].Blink) & 1) != 0 )
    WPP_SF_d(v8[1].Flink, 46, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, RegKeyPath);
  return RegKeyPath;
}

```

## disassembly

```asm
0x18001c530  mov     [rsp-8+arg_8], rbx
0x18001c535  mov     [rsp-8+arg_10], rsi
0x18001c53a  push    rbp
0x18001c53b  push    rdi
0x18001c53c  push    r12
0x18001c53e  lea     rbp, [rsp-170h]
0x18001c546  sub     rsp, 270h
0x18001c54d  mov     rax, cs:__security_cookie
0x18001c554  xor     rax, rsp
0x18001c557  mov     [rbp+180h+var_20], rax
0x18001c55e  mov     rsi, rcx
0x18001c561  mov     [rsp+280h+cchName], 0
0x18001c569  mov     [rsp+280h+Sid], 0
0x18001c572  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c579  lea     r12, WPP_GLOBAL_Control
0x18001c580  cmp     rcx, r12
0x18001c583  jz      short loc_18001C5A6
0x18001c585  cmp     byte ptr [rcx+19h], 4
0x18001c589  jb      short loc_18001C5A6
0x18001c58b  test    byte ptr [rcx+1Ch], 1
0x18001c58f  jz      short loc_18001C5A6
0x18001c591  mov     rcx, [rcx+10h]
0x18001c595  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001c59c  mov     edx, 2Bh ; '+'
0x18001c5a1  call    WPP_SF_
0x18001c5a6  xor     edx, edx; GUID *
0x18001c5a8  mov     [rsp+280h+lpReserved], 104h; unsigned __int64
0x18001c5b1  lea     r9, [rsp+280h+SubKey]; unsigned __int16 *
0x18001c5b6  mov     rcx, rsi; rguid
0x18001c5b9  lea     r8d, [rdx+1]; int
0x18001c5bd  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@0HPEAG_K@Z; StpGetRegKeyPath(_GUID const *,_GUID const *,int,ushort *,unsigned __int64)
0x18001c5c2  mov     ebx, eax
0x18001c5c4  test    eax, eax
0x18001c5c6  jnz     loc_18001C71E
0x18001c5cc  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x18001c5d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c5d8  call    cs:__imp_RegDeleteTreeW
0x18001c5de  xor     edi, edi
0x18001c5e0  mov     [rsp+280h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18001c5e9  lea     r9, [rsp+280h+cchName]; lpcchName
0x18001c5ee  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x18001c5f7  lea     r8, [rsp+280h+SubKey]; lpName
0x18001c5fc  mov     [rsp+280h+lpClass], 0; lpClass
0x18001c605  mov     edx, edi; dwIndex
0x18001c607  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001c60e  mov     [rsp+280h+lpReserved], 0; lpReserved
0x18001c617  mov     [rsp+280h+cchName], 104h
0x18001c61f  call    cs:__imp_RegEnumKeyExW
0x18001c625  mov     ebx, eax
0x18001c627  cmp     eax, 103h
0x18001c62c  jz      loc_18001C71C
0x18001c632  test    eax, eax
0x18001c634  jnz     loc_18001C6EA
0x18001c63a  lea     rdx, [rsp+280h+Sid]; Sid
0x18001c63f  lea     rcx, [rsp+280h+SubKey]; StringSid
0x18001c644  call    cs:__imp_ConvertStringSidToSidW
0x18001c64a  test    eax, eax
0x18001c64c  jz      loc_18001C6E3
0x18001c652  mov     rcx, [rsp+280h+Sid]; hMem
0x18001c657  call    cs:__imp_LocalFree
0x18001c65d  mov     ecx, [rsp+280h+cchName]
0x18001c661  lea     edx, [rbx+5Ch]
0x18001c664  mov     eax, 104h
0x18001c669  lea     r9, [rsp+280h+SubKey]
0x18001c66e  xor     r8d, r8d; int
0x18001c671  mov     [rsp+rcx*2+280h+SubKey], dx
0x18001c676  inc     ecx
0x18001c678  sub     rax, rcx
0x18001c67b  mov     [rsp+280h+cchName], ecx
0x18001c67f  xor     edx, edx; GUID *
0x18001c681  mov     [rsp+280h+lpReserved], rax; unsigned __int64
0x18001c686  lea     r9, [r9+rcx*2]; unsigned __int16 *
0x18001c68a  mov     rcx, rsi; rguid
0x18001c68d  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@0HPEAG_K@Z; StpGetRegKeyPath(_GUID const *,_GUID const *,int,ushort *,unsigned __int64)
0x18001c692  mov     ebx, eax
0x18001c694  test    eax, eax
0x18001c696  jnz     loc_18001C71E
0x18001c69c  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x18001c6a1  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001c6a8  call    cs:__imp_RegDeleteTreeW
0x18001c6ae  test    eax, 0FFFFFFFDh
0x18001c6b3  jz      short loc_18001C6E3
0x18001c6b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c6bc  cmp     rcx, r12
0x18001c6bf  jz      short loc_18001C6E3
0x18001c6c1  cmp     byte ptr [rcx+19h], 1
0x18001c6c5  jb      short loc_18001C6E3
0x18001c6c7  test    byte ptr [rcx+1Ch], 1
0x18001c6cb  jz      short loc_18001C6E3
0x18001c6cd  mov     rcx, [rcx+10h]
0x18001c6d1  lea     edx, [rbx+2Dh]
0x18001c6d4  mov     r9d, eax
0x18001c6d7  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001c6de  call    WPP_SF_d
0x18001c6e3  inc     edi
0x18001c6e5  jmp     loc_18001C5E0
0x18001c6ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c6f1  cmp     rcx, r12
0x18001c6f4  jz      short loc_18001C74E
0x18001c6f6  cmp     byte ptr [rcx+19h], 1
0x18001c6fa  jb      short loc_18001C725
0x18001c6fc  test    byte ptr [rcx+1Ch], 1
0x18001c700  jz      short loc_18001C725
0x18001c702  mov     rcx, [rcx+10h]
0x18001c706  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001c70d  mov     edx, 2Ch ; ','
0x18001c712  mov     r9d, eax
0x18001c715  call    WPP_SF_d
0x18001c71a  jmp     short loc_18001C71E
0x18001c71c  xor     ebx, ebx
0x18001c71e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c725  cmp     rcx, r12
0x18001c728  jz      short loc_18001C74E
0x18001c72a  cmp     byte ptr [rcx+19h], 4
0x18001c72e  jb      short loc_18001C74E
0x18001c730  test    byte ptr [rcx+1Ch], 1
0x18001c734  jz      short loc_18001C74E
0x18001c736  mov     rcx, [rcx+10h]
0x18001c73a  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001c741  mov     edx, 2Eh ; '.'
0x18001c746  mov     r9d, ebx
0x18001c749  call    WPP_SF_d
0x18001c74e  mov     eax, ebx
0x18001c750  mov     rcx, [rbp+180h+var_20]
0x18001c757  xor     rcx, rsp; StackCookie
0x18001c75a  call    __security_check_cookie
0x18001c75f  lea     r11, [rsp+280h+var_10]
0x18001c767  mov     rbx, [r11+28h]
0x18001c76b  mov     rsi, [r11+30h]
0x18001c76f  mov     rsp, r11
0x18001c772  pop     r12
0x18001c774  pop     rdi
0x18001c775  pop     rbp
0x18001c776  retn
```
