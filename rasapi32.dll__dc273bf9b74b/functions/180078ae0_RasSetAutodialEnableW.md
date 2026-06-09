# RasSetAutodialEnableW

- ea: `0x180078ae0`
- end: `0x180078de3`
- name: `RasSetAutodialEnableW`
- size: `771`
- prototype: `DWORD __stdcall(DWORD, BOOL)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800789f0`

## callees

- `0x18000f31c`
- `0x180010d10`
- `0x18004e580`
- `0x180078ae0`
- `0x18007e3a8`
- `0x18007e548`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180078d30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180078d30`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180078c0e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180078c84`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180078c0e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180078c84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180078cc0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180078d7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180078d92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180078cc0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180078d7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180078d92`

## pseudocode

```c
DWORD __stdcall RasSetAutodialEnableW(DWORD a1, BOOL a2)
{
  unsigned int v4; // eax
  DWORD v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // eax
  HRESULT v9; // eax
  __int64 v10; // r9
  DWORD dwDisposition; // [rsp+50h] [rbp-29h] BYREF
  int v13; // [rsp+54h] [rbp-25h]
  BYTE Data[8]; // [rsp+58h] [rbp-21h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-19h] BYREF
  HKEY v16; // [rsp+68h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-9h] BYREF
  wchar_t pszDest[8]; // [rsp+78h] [rbp-1h] BYREF
  __int128 v19; // [rsp+88h] [rbp+Fh]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Dc(*((_QWORD *)WPP_GLOBAL_Control + 2), 810, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, a1, a2);
  }
  phkResult = 0;
  v16 = 0;
  dwDisposition = 0;
  v13 = 0;
  hKey = 0;
  *(_DWORD *)Data = !a2;
  *(_OWORD *)pszDest = 0;
  v19 = 0;
  DebugInit();
  v4 = DwOpenUsersRegistry(&hKey);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 811;
LABEL_32:
      v10 = v4;
      goto LABEL_33;
    }
  }
  else
  {
    v4 = RegCreateKeyExW(hKey, L"Software\\Microsoft\\RAS AutoDial", 0, 0, 0, 0x2001Du, 0, &phkResult, &dwDisposition);
    v5 = v4;
    if ( !v4 )
    {
      v8 = RegCreateKeyExW(phkResult, L"Control\\Locations", 0, 0, 0, 2u, 0, &v16, &dwDisposition);
      v5 = v8;
      if ( v8
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 813, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v8);
      }
      RegCloseKey(phkResult);
      if ( v5 )
        goto LABEL_34;
      v9 = StringCchPrintfW(pszDest, 0x10u, L"%d", a1);
      if ( v9 >= 0 )
      {
        v4 = RegSetValueExW(v16, pszDest, 0, 4u, Data, 4u);
        v5 = v4;
        if ( v4 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v7 = 815;
            goto LABEL_32;
          }
          goto LABEL_35;
        }
      }
      else
      {
        v5 = (unsigned __int16)v9;
        if ( (_WORD)v9 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v7 = 814;
            v10 = (unsigned __int16)v9;
LABEL_33:
            WPP_SF_d(v6[2], v7, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v10);
            goto LABEL_34;
          }
          goto LABEL_35;
        }
      }
LABEL_34:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_35;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 812;
      goto LABEL_32;
    }
  }
LABEL_35:
  if ( v16 )
  {
    RegCloseKey(v16);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v13 )
  {
    RegCloseKey(hKey);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x800) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_d(v6[2], 816, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180078ae0  push    rbp
0x180078ae2  push    rbx
0x180078ae3  push    rdi
0x180078ae4  push    r12
0x180078ae6  push    r14
0x180078ae8  push    r15
0x180078aea  lea     rbp, [rsp-2Fh]
0x180078aef  sub     rsp, 0A8h
0x180078af6  mov     rax, cs:__security_cookie
0x180078afd  xor     rax, rsp
0x180078b00  mov     [rbp+57h+var_38], rax
0x180078b04  mov     ebx, edx
0x180078b06  mov     edi, ecx
0x180078b08  mov     rcx, cs:WPP_GLOBAL_Control
0x180078b0f  lea     r15, WPP_GLOBAL_Control
0x180078b16  lea     r12, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180078b1d  mov     r14d, 800h
0x180078b23  cmp     rcx, r15
0x180078b26  jz      short loc_180078B51
0x180078b28  test    [rcx+1Ch], r14d
0x180078b2c  jz      short loc_180078B51
0x180078b2e  cmp     byte ptr [rcx+19h], 6
0x180078b32  jb      short loc_180078B51
0x180078b34  mov     rcx, [rcx+10h]
0x180078b38  test    edx, edx
0x180078b3a  mov     edx, 32Ah
0x180078b3f  mov     r9d, edi
0x180078b42  setnz   al
0x180078b45  mov     r8, r12
0x180078b48  mov     byte ptr [rsp+0D0h+dwOptions], al
0x180078b4c  call    WPP_SF_Dc
0x180078b51  xor     eax, eax
0x180078b53  mov     [rbp+57h+var_70], 0
0x180078b5b  xorps   xmm0, xmm0
0x180078b5e  mov     [rbp+57h+var_68], 0
0x180078b66  test    ebx, ebx
0x180078b68  mov     [rbp+57h+dwDisposition], 0
0x180078b6f  mov     [rbp+57h+var_7C], 0
0x180078b76  setz    al
0x180078b79  mov     [rbp+57h+hKey], 0
0x180078b81  mov     dword ptr [rbp+57h+Data], eax
0x180078b84  movups  xmmword ptr [rbp+57h+pszDest], xmm0
0x180078b88  movups  [rbp+57h+var_48], xmm0
0x180078b8c  call    DebugInit
0x180078b91  lea     rdx, [rbp+57h+var_7C]
0x180078b95  lea     rcx, [rbp+57h+hKey]; phkResult
0x180078b99  call    DwOpenUsersRegistry
0x180078b9e  mov     ebx, eax
0x180078ba0  test    eax, eax
0x180078ba2  jz      short loc_180078BD2
0x180078ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180078bab  cmp     rcx, r15
0x180078bae  jz      loc_180078D6F
0x180078bb4  test    [rcx+1Ch], r14d
0x180078bb8  jz      loc_180078D6F
0x180078bbe  cmp     byte ptr [rcx+19h], 2
0x180078bc2  jb      loc_180078D6F
0x180078bc8  mov     edx, 32Bh
0x180078bcd  jmp     loc_180078D59
0x180078bd2  mov     rcx, [rbp+57h+hKey]; hKey
0x180078bd6  lea     rax, [rbp+57h+dwDisposition]
0x180078bda  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x180078bdf  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\RAS AutoDial"
0x180078be6  lea     rax, [rbp+57h+var_70]
0x180078bea  xor     r9d, r9d; lpClass
0x180078bed  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180078bf2  xor     r8d, r8d; Reserved
0x180078bf5  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180078bfe  mov     [rsp+0D0h+samDesired], 2001Dh; samDesired
0x180078c06  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x180078c0e  call    cs:__imp_RegCreateKeyExW
0x180078c14  mov     ebx, eax
0x180078c16  test    eax, eax
0x180078c18  jz      short loc_180078C48
0x180078c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180078c21  cmp     rcx, r15
0x180078c24  jz      loc_180078D6F
0x180078c2a  test    [rcx+1Ch], r14d
0x180078c2e  jz      loc_180078D6F
0x180078c34  cmp     byte ptr [rcx+19h], 2
0x180078c38  jb      loc_180078D6F
0x180078c3e  mov     edx, 32Ch
0x180078c43  jmp     loc_180078D59
0x180078c48  mov     rcx, [rbp+57h+var_70]; hKey
0x180078c4c  lea     rax, [rbp+57h+dwDisposition]
0x180078c50  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x180078c55  lea     rdx, aControlLocatio; "Control\\Locations"
0x180078c5c  lea     rax, [rbp+57h+var_68]
0x180078c60  xor     r9d, r9d; lpClass
0x180078c63  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180078c68  xor     r8d, r8d; Reserved
0x180078c6b  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180078c74  mov     [rsp+0D0h+samDesired], 2; samDesired
0x180078c7c  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x180078c84  call    cs:__imp_RegCreateKeyExW
0x180078c8a  mov     ebx, eax
0x180078c8c  test    eax, eax
0x180078c8e  jz      short loc_180078CBC
0x180078c90  mov     rcx, cs:WPP_GLOBAL_Control
0x180078c97  cmp     rcx, r15
0x180078c9a  jz      short loc_180078CBC
0x180078c9c  test    [rcx+1Ch], r14d
0x180078ca0  jz      short loc_180078CBC
0x180078ca2  cmp     byte ptr [rcx+19h], 2
0x180078ca6  jb      short loc_180078CBC
0x180078ca8  mov     rcx, [rcx+10h]
0x180078cac  mov     edx, 32Dh
0x180078cb1  mov     r9d, eax
0x180078cb4  mov     r8, r12
0x180078cb7  call    WPP_SF_d
0x180078cbc  mov     rcx, [rbp+57h+var_70]; hKey
0x180078cc0  call    cs:__imp_RegCloseKey
0x180078cc6  test    ebx, ebx
0x180078cc8  jnz     loc_180078D68
0x180078cce  mov     r9d, edi
0x180078cd1  lea     r8, aD; "%d"
0x180078cd8  lea     edx, [rbx+10h]; cchDest
0x180078cdb  lea     rcx, [rbp+57h+pszDest]; pszDest
0x180078cdf  call    StringCchPrintfW
0x180078ce4  test    eax, eax
0x180078ce6  jns     short loc_180078D11
0x180078ce8  movzx   ebx, ax
0x180078ceb  test    ebx, ebx
0x180078ced  jz      short loc_180078D68
0x180078cef  mov     rcx, cs:WPP_GLOBAL_Control
0x180078cf6  cmp     rcx, r15
0x180078cf9  jz      short loc_180078D6F
0x180078cfb  test    [rcx+1Ch], r14d
0x180078cff  jz      short loc_180078D6F
0x180078d01  cmp     byte ptr [rcx+19h], 2
0x180078d05  jb      short loc_180078D6F
0x180078d07  mov     edx, 32Eh
0x180078d0c  mov     r9d, ebx
0x180078d0f  jmp     short loc_180078D5C
0x180078d11  mov     rcx, [rbp+57h+var_68]; hKey
0x180078d15  lea     rax, [rbp+57h+Data]
0x180078d19  mov     r9d, 4; dwType
0x180078d1f  lea     rdx, [rbp+57h+pszDest]; lpValueName
0x180078d23  mov     [rsp+0D0h+samDesired], r9d; cbData
0x180078d28  xor     r8d, r8d; Reserved
0x180078d2b  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x180078d30  call    cs:__imp_RegSetValueExW
0x180078d36  mov     ebx, eax
0x180078d38  test    eax, eax
0x180078d3a  jz      short loc_180078D68
0x180078d3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180078d43  cmp     rcx, r15
0x180078d46  jz      short loc_180078D6F
0x180078d48  test    [rcx+1Ch], r14d
0x180078d4c  jz      short loc_180078D6F
0x180078d4e  cmp     byte ptr [rcx+19h], 2
0x180078d52  jb      short loc_180078D6F
0x180078d54  mov     edx, 32Fh
0x180078d59  mov     r9d, eax
0x180078d5c  mov     rcx, [rcx+10h]
0x180078d60  mov     r8, r12
0x180078d63  call    WPP_SF_d
0x180078d68  mov     rcx, cs:WPP_GLOBAL_Control
0x180078d6f  mov     rax, [rbp+57h+var_68]
0x180078d73  test    rax, rax
0x180078d76  jz      short loc_180078D88
0x180078d78  mov     rcx, rax; hKey
0x180078d7b  call    cs:__imp_RegCloseKey
0x180078d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180078d88  cmp     [rbp+57h+var_7C], 0
0x180078d8c  jz      short loc_180078D9F
0x180078d8e  mov     rcx, [rbp+57h+hKey]; hKey
0x180078d92  call    cs:__imp_RegCloseKey
0x180078d98  mov     rcx, cs:WPP_GLOBAL_Control
0x180078d9f  cmp     rcx, r15
0x180078da2  jz      short loc_180078DC4
0x180078da4  test    [rcx+1Ch], r14d
0x180078da8  jz      short loc_180078DC4
0x180078daa  cmp     byte ptr [rcx+19h], 6
0x180078dae  jb      short loc_180078DC4
0x180078db0  mov     rcx, [rcx+10h]
0x180078db4  mov     edx, 330h
0x180078db9  mov     r9d, ebx
0x180078dbc  mov     r8, r12
0x180078dbf  call    WPP_SF_d
0x180078dc4  mov     eax, ebx
0x180078dc6  mov     rcx, [rbp+57h+var_38]
0x180078dca  xor     rcx, rsp; StackCookie
0x180078dcd  call    __security_check_cookie
0x180078dd2  add     rsp, 0A8h
0x180078dd9  pop     r15
0x180078ddb  pop     r14
0x180078ddd  pop     r12
0x180078ddf  pop     rdi
0x180078de0  pop     rbx
0x180078de1  pop     rbp
0x180078de2  retn
```
