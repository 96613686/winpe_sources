# PersistNFAObject

- ea: `0x1800378f0`
- end: `0x180037ed8`
- name: `PersistNFAObject`
- size: `1512`
- prototype: `__int64 __fastcall(HKEY, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180038908`

## callees

- `0x180006f00`
- `0x180006f60`
- `0x18000e510`
- `0x1800378f0`
- `0x18004d052`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037ebc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037ebc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180037b63`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180037b63`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800379d5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037a45`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037ab3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037b21`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037ba0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037bfc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037c5c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037cca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037d38`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037e1d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037e76`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800379d5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037a45`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037ab3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037b21`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037ba0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037bfc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037c5c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037cca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037d38`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037e1d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037e76`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003793c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003793c`

## pseudocode

```c
__int64 __fastcall PersistNFAObject(HKEY a1, __int64 a2)
{
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  const BYTE *lpData; // rcx
  __int64 v10; // rsi
  __int64 v11; // rax
  const BYTE *v12; // rcx
  __int64 v13; // rax
  const BYTE *v14; // rcx
  __int64 v15; // rax
  const BYTE *v16; // rcx
  __int64 v17; // rax
  const BYTE *v18; // rcx
  const BYTE *v19; // rcx
  __int64 v20; // rax
  const BYTE *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  BYTE *v25; // rax
  BYTE *v26; // r14
  _WORD *v27; // rdx
  __int64 v28; // r8
  DWORD v30; // [rsp+88h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+40h] BYREF

  v3 = *(const WCHAR **)a2;
  hKey = 0;
  v30 = 0;
  v4 = RegCreateKeyExW(a1, v3, 0, 0, 0, 0xF003Fu, 0, &hKey, &v30);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = 34;
LABEL_86:
      v8 = v4;
      goto LABEL_87;
    }
    goto LABEL_88;
  }
  if ( !hKey )
  {
    v5 = 1359;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return v5;
    v7 = 35;
    goto LABEL_9;
  }
  v4 = RegSetValueExW(hKey, L"className", 0, 1u, L"ipsecNFA", 0x12u);
  v5 = v4;
  if ( !v4 )
  {
    lpData = *(const BYTE **)a2;
    v10 = -1;
    if ( *(_QWORD *)a2 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&lpData[2 * v11] );
      v4 = RegSetValueExW(hKey, L"name", 0, 1u, lpData, 2 * v11 + 2);
      v5 = v4;
      if ( v4 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v7 = 37;
          goto LABEL_86;
        }
        goto LABEL_88;
      }
    }
    v12 = *(const BYTE **)(a2 + 8);
    if ( v12 )
    {
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)&v12[2 * v13] );
      v4 = RegSetValueExW(hKey, L"ipsecName", 0, 1u, v12, 2 * v13 + 2);
      v5 = v4;
      if ( v4 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v7 = 38;
          goto LABEL_86;
        }
        goto LABEL_88;
      }
    }
    v14 = *(const BYTE **)(a2 + 80);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)&v14[2 * v15] );
      v4 = RegSetValueExW(hKey, L"description", 0, 1u, v14, 2 * v15 + 2);
      v5 = v4;
      if ( v4 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v7 = 39;
          goto LABEL_86;
        }
        goto LABEL_88;
      }
    }
    else
    {
      RegDeleteValueW(hKey, L"description");
    }
    v16 = *(const BYTE **)(a2 + 16);
    if ( v16 )
    {
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)&v16[2 * v17] );
      v4 = RegSetValueExW(hKey, L"ipsecID", 0, 1u, v16, 2 * v17 + 2);
      v5 = v4;
      if ( v4 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v7 = 40;
          goto LABEL_86;
        }
        goto LABEL_88;
      }
    }
    v4 = RegSetValueExW(hKey, L"ipsecDataType", 0, 4u, (const BYTE *)(a2 + 24), 4u);
    v5 = v4;
    if ( v4 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 41;
        goto LABEL_86;
      }
      goto LABEL_88;
    }
    v18 = *(const BYTE **)(a2 + 32);
    if ( v18 )
    {
      v4 = RegSetValueExW(hKey, L"ipsecData", 0, 3u, v18, *(_DWORD *)(a2 + 40));
      v5 = v4;
      if ( v4 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v7 = 42;
          goto LABEL_86;
        }
        goto LABEL_88;
      }
    }
    v19 = *(const BYTE **)(a2 + 48);
    if ( v19 )
    {
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&v19[2 * v20] );
      v4 = RegSetValueExW(hKey, L"ipsecOwnersReference", 0, 1u, v19, 2 * v20 + 2);
      v5 = v4;
      if ( v4 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v7 = 43;
          goto LABEL_86;
        }
        goto LABEL_88;
      }
    }
    v21 = *(const BYTE **)(a2 + 64);
    if ( v21 )
    {
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)&v21[2 * v22] );
      v4 = RegSetValueExW(hKey, L"ipsecNegotiationPolicyReference", 0, 1u, v21, 2 * v22 + 2);
      v5 = v4;
      if ( v4 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v7 = 44;
          goto LABEL_86;
        }
        goto LABEL_88;
      }
    }
    v23 = *(_QWORD *)(a2 + 56);
    if ( v23 )
    {
      v24 = -1;
      do
        ++v24;
      while ( *(_WORD *)(v23 + 2 * v24) );
      v25 = (BYTE *)IpsecAllocMem(2 * v24 + 4);
      v26 = v25;
      if ( !v25 )
      {
        v5 = 14;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_88;
        v7 = 45;
LABEL_9:
        v8 = v5;
LABEL_87:
        WPP_SF_d(v6[2], v7, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v8);
        goto LABEL_88;
      }
      v27 = *(_WORD **)(a2 + 56);
      v28 = -1;
      do
        ++v28;
      while ( v27[v28] );
      memcpy_0(v25, v27, 2 * v28 + 2);
      do
        ++v10;
      while ( *(_WORD *)(*(_QWORD *)(a2 + 56) + 2 * v10) );
      v4 = RegSetValueExW(hKey, L"ipsecFilterReference", 0, 7u, v26, 2 * v10 + 4);
      v5 = v4;
      if ( v4 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v7 = 46;
          goto LABEL_86;
        }
        goto LABEL_88;
      }
      IpsecFreeMem(v26);
    }
    v4 = RegSetValueExW(hKey, L"whenChanged", 0, 4u, (const BYTE *)(a2 + 72), 4u);
    v5 = v4;
    if ( v4 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 47;
        goto LABEL_86;
      }
    }
    goto LABEL_88;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v7 = 36;
    goto LABEL_86;
  }
LABEL_88:
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x1800378f0  mov     r11, rsp
0x1800378f3  mov     [r11+8], rbx
0x1800378f7  push    rbp
0x1800378f8  push    rsi
0x1800378f9  push    rdi
0x1800378fa  push    r14
0x1800378fc  push    r15
0x1800378fe  mov     rbp, rsp
0x180037901  sub     rsp, 50h
0x180037905  xor     r15d, r15d
0x180037908  lea     rax, [rbp+arg_8]
0x18003790c  mov     [r11-38h], rax
0x180037910  mov     rdi, rdx
0x180037913  mov     rdx, [rdx]; lpSubKey
0x180037916  lea     rax, [rbp+hKey]
0x18003791a  mov     [r11-40h], rax
0x18003791e  xor     r9d, r9d; lpClass
0x180037921  mov     [r11-48h], r15
0x180037925  xor     r8d, r8d; Reserved
0x180037928  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x180037930  mov     [r11-58h], r15d
0x180037934  mov     [rbp+hKey], r15
0x180037938  mov     [rbp+arg_8], r15d
0x18003793c  call    cs:__imp_RegCreateKeyExW
0x180037942  mov     ebx, eax
0x180037944  test    eax, eax
0x180037946  jz      short loc_180037972
0x180037948  mov     rcx, cs:WPP_GLOBAL_Control
0x18003794f  lea     rdx, WPP_GLOBAL_Control
0x180037956  cmp     rcx, rdx
0x180037959  jz      loc_180037EB3
0x18003795f  test    byte ptr [rcx+1Ch], 10h
0x180037963  jz      loc_180037EB3
0x180037969  lea     edx, [r15+22h]
0x18003796d  jmp     loc_180037EA0
0x180037972  mov     rcx, [rbp+hKey]; hKey
0x180037976  test    rcx, rcx
0x180037979  jnz     short loc_1800379AE
0x18003797b  mov     ebx, 54Fh
0x180037980  mov     rcx, cs:WPP_GLOBAL_Control
0x180037987  lea     rdx, WPP_GLOBAL_Control
0x18003798e  cmp     rcx, rdx
0x180037991  jz      loc_180037EC2
0x180037997  test    byte ptr [rcx+1Ch], 10h
0x18003799b  jz      loc_180037EC2
0x1800379a1  mov     edx, 23h ; '#'
0x1800379a6  mov     r9d, ebx
0x1800379a9  jmp     loc_180037EA3
0x1800379ae  lea     rax, aIpsecnfa; "ipsecNFA"
0x1800379b5  mov     [rsp+50h+samDesired], 12h; cbData
0x1800379bd  mov     r14d, 1
0x1800379c3  mov     [rsp+50h+lpData], rax; lpData
0x1800379c8  mov     r9d, r14d; dwType
0x1800379cb  lea     rdx, aClassname; "className"
0x1800379d2  xor     r8d, r8d; Reserved
0x1800379d5  call    cs:__imp_RegSetValueExW
0x1800379db  mov     ebx, eax
0x1800379dd  test    eax, eax
0x1800379df  jz      short loc_180037A0B
0x1800379e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800379e8  lea     rdx, WPP_GLOBAL_Control
0x1800379ef  cmp     rcx, rdx
0x1800379f2  jz      loc_180037EB3
0x1800379f8  test    byte ptr [rcx+1Ch], 10h
0x1800379fc  jz      loc_180037EB3
0x180037a02  lea     edx, [r14+23h]
0x180037a06  jmp     loc_180037EA0
0x180037a0b  mov     rcx, [rdi]
0x180037a0e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180037a12  test    rcx, rcx
0x180037a15  jz      short loc_180037A7C
0x180037a17  mov     rax, rsi
0x180037a1a  inc     rax
0x180037a1d  cmp     [rcx+rax*2], r15w
0x180037a22  jnz     short loc_180037A1A
0x180037a24  lea     eax, ds:2[rax*2]
0x180037a2b  mov     r9d, r14d; dwType
0x180037a2e  mov     [rsp+50h+samDesired], eax; cbData
0x180037a32  lea     rdx, aName; "name"
0x180037a39  mov     [rsp+50h+lpData], rcx; lpData
0x180037a3e  xor     r8d, r8d; Reserved
0x180037a41  mov     rcx, [rbp+hKey]; hKey
0x180037a45  call    cs:__imp_RegSetValueExW
0x180037a4b  mov     ebx, eax
0x180037a4d  test    eax, eax
0x180037a4f  jz      short loc_180037A7C
0x180037a51  mov     rcx, cs:WPP_GLOBAL_Control
0x180037a58  lea     rdx, WPP_GLOBAL_Control
0x180037a5f  cmp     rcx, rdx
0x180037a62  jz      loc_180037EB3
0x180037a68  test    byte ptr [rcx+1Ch], 10h
0x180037a6c  jz      loc_180037EB3
0x180037a72  mov     edx, 25h ; '%'
0x180037a77  jmp     loc_180037EA0
0x180037a7c  mov     rcx, [rdi+8]
0x180037a80  test    rcx, rcx
0x180037a83  jz      short loc_180037AEA
0x180037a85  mov     rax, rsi
0x180037a88  inc     rax
0x180037a8b  cmp     [rcx+rax*2], r15w
0x180037a90  jnz     short loc_180037A88
0x180037a92  lea     eax, ds:2[rax*2]
0x180037a99  mov     r9d, r14d; dwType
0x180037a9c  mov     [rsp+50h+samDesired], eax; cbData
0x180037aa0  lea     rdx, aIpsecname_0; "ipsecName"
0x180037aa7  mov     [rsp+50h+lpData], rcx; lpData
0x180037aac  xor     r8d, r8d; Reserved
0x180037aaf  mov     rcx, [rbp+hKey]; hKey
0x180037ab3  call    cs:__imp_RegSetValueExW
0x180037ab9  mov     ebx, eax
0x180037abb  test    eax, eax
0x180037abd  jz      short loc_180037AEA
0x180037abf  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ac6  lea     rdx, WPP_GLOBAL_Control
0x180037acd  cmp     rcx, rdx
0x180037ad0  jz      loc_180037EB3
0x180037ad6  test    byte ptr [rcx+1Ch], 10h
0x180037ada  jz      loc_180037EB3
0x180037ae0  mov     edx, 26h ; '&'
0x180037ae5  jmp     loc_180037EA0
0x180037aea  mov     rcx, [rdi+50h]
0x180037aee  test    rcx, rcx
0x180037af1  jz      short loc_180037B58
0x180037af3  mov     rax, rsi
0x180037af6  inc     rax
0x180037af9  cmp     [rcx+rax*2], r15w
0x180037afe  jnz     short loc_180037AF6
0x180037b00  lea     eax, ds:2[rax*2]
0x180037b07  mov     r9d, r14d; dwType
0x180037b0a  mov     [rsp+50h+samDesired], eax; cbData
0x180037b0e  lea     rdx, aDescription_0; "description"
0x180037b15  mov     [rsp+50h+lpData], rcx; lpData
0x180037b1a  xor     r8d, r8d; Reserved
0x180037b1d  mov     rcx, [rbp+hKey]; hKey
0x180037b21  call    cs:__imp_RegSetValueExW
0x180037b27  mov     ebx, eax
0x180037b29  test    eax, eax
0x180037b2b  jz      short loc_180037B69
0x180037b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180037b34  lea     rdx, WPP_GLOBAL_Control
0x180037b3b  cmp     rcx, rdx
0x180037b3e  jz      loc_180037EB3
0x180037b44  test    byte ptr [rcx+1Ch], 10h
0x180037b48  jz      loc_180037EB3
0x180037b4e  mov     edx, 27h ; '''
0x180037b53  jmp     loc_180037EA0
0x180037b58  mov     rcx, [rbp+hKey]; hKey
0x180037b5c  lea     rdx, aDescription_0; "description"
0x180037b63  call    cs:__imp_RegDeleteValueW
0x180037b69  mov     rcx, [rdi+10h]
0x180037b6d  test    rcx, rcx
0x180037b70  jz      short loc_180037BD7
0x180037b72  mov     rax, rsi
0x180037b75  inc     rax
0x180037b78  cmp     [rcx+rax*2], r15w
0x180037b7d  jnz     short loc_180037B75
0x180037b7f  lea     eax, ds:2[rax*2]
0x180037b86  mov     r9d, r14d; dwType
0x180037b89  mov     [rsp+50h+samDesired], eax; cbData
0x180037b8d  lea     rdx, aIpsecid_0; "ipsecID"
0x180037b94  mov     [rsp+50h+lpData], rcx; lpData
0x180037b99  xor     r8d, r8d; Reserved
0x180037b9c  mov     rcx, [rbp+hKey]; hKey
0x180037ba0  call    cs:__imp_RegSetValueExW
0x180037ba6  mov     ebx, eax
0x180037ba8  test    eax, eax
0x180037baa  jz      short loc_180037BD7
0x180037bac  mov     rcx, cs:WPP_GLOBAL_Control
0x180037bb3  lea     rdx, WPP_GLOBAL_Control
0x180037bba  cmp     rcx, rdx
0x180037bbd  jz      loc_180037EB3
0x180037bc3  test    byte ptr [rcx+1Ch], 10h
0x180037bc7  jz      loc_180037EB3
0x180037bcd  mov     edx, 28h ; '('
0x180037bd2  jmp     loc_180037EA0
0x180037bd7  mov     rcx, [rbp+hKey]; hKey
0x180037bdb  lea     rax, [rdi+18h]
0x180037bdf  mov     [rsp+50h+samDesired], 4; cbData
0x180037be7  lea     rdx, aIpsecdatatype_0; "ipsecDataType"
0x180037bee  mov     r9d, 4; dwType
0x180037bf4  mov     [rsp+50h+lpData], rax; lpData
0x180037bf9  xor     r8d, r8d; Reserved
0x180037bfc  call    cs:__imp_RegSetValueExW
0x180037c02  mov     ebx, eax
0x180037c04  test    eax, eax
0x180037c06  jz      short loc_180037C33
0x180037c08  mov     rcx, cs:WPP_GLOBAL_Control
0x180037c0f  lea     rdx, WPP_GLOBAL_Control
0x180037c16  cmp     rcx, rdx
0x180037c19  jz      loc_180037EB3
0x180037c1f  test    byte ptr [rcx+1Ch], 10h
0x180037c23  jz      loc_180037EB3
0x180037c29  mov     edx, 29h ; ')'
0x180037c2e  jmp     loc_180037EA0
0x180037c33  mov     rcx, [rdi+20h]
0x180037c37  test    rcx, rcx
0x180037c3a  jz      short loc_180037C93
0x180037c3c  mov     eax, [rdi+28h]
0x180037c3f  lea     rdx, aIpsecdata_0; "ipsecData"
0x180037c46  mov     [rsp+50h+samDesired], eax; cbData
0x180037c4a  mov     r9d, 3; dwType
0x180037c50  mov     [rsp+50h+lpData], rcx; lpData
0x180037c55  xor     r8d, r8d; Reserved
0x180037c58  mov     rcx, [rbp+hKey]; hKey
0x180037c5c  call    cs:__imp_RegSetValueExW
0x180037c62  mov     ebx, eax
0x180037c64  test    eax, eax
0x180037c66  jz      short loc_180037C93
0x180037c68  mov     rcx, cs:WPP_GLOBAL_Control
0x180037c6f  lea     rdx, WPP_GLOBAL_Control
0x180037c76  cmp     rcx, rdx
0x180037c79  jz      loc_180037EB3
0x180037c7f  test    byte ptr [rcx+1Ch], 10h
0x180037c83  jz      loc_180037EB3
0x180037c89  mov     edx, 2Ah ; '*'
0x180037c8e  jmp     loc_180037EA0
0x180037c93  mov     rcx, [rdi+30h]
0x180037c97  test    rcx, rcx
0x180037c9a  jz      short loc_180037D01
0x180037c9c  mov     rax, rsi
0x180037c9f  inc     rax
0x180037ca2  cmp     [rcx+rax*2], r15w
0x180037ca7  jnz     short loc_180037C9F
0x180037ca9  lea     eax, ds:2[rax*2]
0x180037cb0  mov     r9d, r14d; dwType
0x180037cb3  mov     [rsp+50h+samDesired], eax; cbData
0x180037cb7  lea     rdx, aIpsecownersref_0; "ipsecOwnersReference"
0x180037cbe  mov     [rsp+50h+lpData], rcx; lpData
0x180037cc3  xor     r8d, r8d; Reserved
0x180037cc6  mov     rcx, [rbp+hKey]; hKey
0x180037cca  call    cs:__imp_RegSetValueExW
0x180037cd0  mov     ebx, eax
0x180037cd2  test    eax, eax
0x180037cd4  jz      short loc_180037D01
0x180037cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180037cdd  lea     rdx, WPP_GLOBAL_Control
0x180037ce4  cmp     rcx, rdx
0x180037ce7  jz      loc_180037EB3
0x180037ced  test    byte ptr [rcx+1Ch], 10h
0x180037cf1  jz      loc_180037EB3
0x180037cf7  mov     edx, 2Bh ; '+'
0x180037cfc  jmp     loc_180037EA0
0x180037d01  mov     rcx, [rdi+40h]
0x180037d05  test    rcx, rcx
0x180037d08  jz      short loc_180037D6F
0x180037d0a  mov     rax, rsi
0x180037d0d  inc     rax
0x180037d10  cmp     [rcx+rax*2], r15w
0x180037d15  jnz     short loc_180037D0D
0x180037d17  lea     eax, ds:2[rax*2]
0x180037d1e  mov     r9d, r14d; dwType
0x180037d21  mov     [rsp+50h+samDesired], eax; cbData
0x180037d25  lea     rdx, aIpsecnegotiati_2; "ipsecNegotiationPolicyReference"
0x180037d2c  mov     [rsp+50h+lpData], rcx; lpData
0x180037d31  xor     r8d, r8d; Reserved
0x180037d34  mov     rcx, [rbp+hKey]; hKey
0x180037d38  call    cs:__imp_RegSetValueExW
0x180037d3e  mov     ebx, eax
0x180037d40  test    eax, eax
0x180037d42  jz      short loc_180037D6F
0x180037d44  mov     rcx, cs:WPP_GLOBAL_Control
0x180037d4b  lea     rdx, WPP_GLOBAL_Control
0x180037d52  cmp     rcx, rdx
0x180037d55  jz      loc_180037EB3
0x180037d5b  test    byte ptr [rcx+1Ch], 10h
0x180037d5f  jz      loc_180037EB3
0x180037d65  mov     edx, 2Ch ; ','
0x180037d6a  jmp     loc_180037EA0
0x180037d6f  mov     rax, [rdi+38h]
0x180037d73  test    rax, rax
0x180037d76  jz      loc_180037E51
0x180037d7c  mov     rcx, rsi
0x180037d7f  inc     rcx
0x180037d82  cmp     [rax+rcx*2], r15w
0x180037d87  jnz     short loc_180037D7F
0x180037d89  lea     rcx, ds:4[rcx*2]
0x180037d91  call    IpsecAllocMem
0x180037d96  mov     r14, rax
0x180037d99  test    rax, rax
0x180037d9c  jnz     short loc_180037DCA
0x180037d9e  lea     ebx, [rax+0Eh]
0x180037da1  mov     rcx, cs:WPP_GLOBAL_Control
0x180037da8  lea     rdx, WPP_GLOBAL_Control
0x180037daf  cmp     rcx, rdx
0x180037db2  jz      loc_180037EB3
0x180037db8  test    byte ptr [rcx+1Ch], 10h
0x180037dbc  jz      loc_180037EB3
0x180037dc2  lea     edx, [rax+2Dh]
0x180037dc5  jmp     loc_1800379A6
0x180037dca  mov     rdx, [rdi+38h]; Src
0x180037dce  mov     r8, rsi
0x180037dd1  inc     r8
0x180037dd4  cmp     [rdx+r8*2], r15w
0x180037dd9  jnz     short loc_180037DD1
0x180037ddb  lea     r8, ds:2[r8*2]; Size
0x180037de3  mov     rcx, r14; void *
0x180037de6  call    memcpy_0
0x180037deb  mov     rax, [rdi+38h]
0x180037def  inc     rsi
0x180037df2  cmp     [rax+rsi*2], r15w
  ... truncated ...
```
