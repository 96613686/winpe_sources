# RasAutodialAddressToNetwork

- ea: `0x18006b110`
- end: `0x18006b424`
- name: `RasAutodialAddressToNetwork`
- size: `788`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006afc`
- `0x18000f31c`
- `0x18004e580`
- `0x18004e984`
- `0x1800661c4`
- `0x18006b110`
- `0x18007e5f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006b2a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006b2a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b3a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b3d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b3a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b3d1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006b3b8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006b3b8`

## pseudocode

```c
__int64 __fastcall RasAutodialAddressToNetwork(__int64 a1, wchar_t *a2, unsigned int *a3)
{
  _QWORD *v6; // rcx
  BYTE *v7; // rsi
  unsigned int v8; // ebx
  __int64 v9; // rdx
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // r14
  unsigned int v14; // r14d
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-8h] BYREF
  int v18; // [rsp+80h] [rbp+40h] BYREF
  BYTE *v19; // [rsp+98h] [rbp+58h] BYREF

  if ( a1 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 681, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, a1);
LABEL_10:
      v6 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 682, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
      goto LABEL_10;
    }
  }
  phkResult = 0;
  v7 = 0;
  hKey = 0;
  v19 = 0;
  v18 = 0;
  if ( !a1 )
  {
    v8 = 87;
    if ( v6 != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v6 + 7) & 0x800) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      {
        WPP_SF_d(v6[2], 683, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x800) != 0 && *((_BYTE *)v6 + 25) >= 6u )
      {
        v9 = 684;
LABEL_58:
        WPP_SF_d(v6[2], v9, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v8);
        return v8;
      }
    }
    return v8;
  }
  v10 = DwOpenUsersRegistry(&hKey, &v18);
  v8 = v10;
  if ( v10 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 685;
LABEL_25:
      WPP_SF_d(v6[2], v11, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v10);
LABEL_47:
      v6 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v10 = RegOpenKeyExW(hKey, L"Software\\Microsoft\\RAS AutoDial", 0, 0x2001Du, &phkResult);
    v8 = v10;
    if ( v10 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 686;
        goto LABEL_25;
      }
    }
    else
    {
      v12 = AutodialAddressToNetwork(phkResult, a1, &v19);
      v8 = v12;
      if ( v12 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          v7 = v19;
          goto LABEL_48;
        }
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 687, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v12);
        v7 = v19;
        goto LABEL_47;
      }
      v7 = v19;
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)&v19[2 * v13] );
      v14 = 2 * v13 + 2;
      if ( !a2 || *a3 < v14 || (v10 = StringCchCopyWrapW(a2), (v8 = v10) == 0) )
      {
        *a3 = v14;
        goto LABEL_47;
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 688;
        goto LABEL_25;
      }
    }
  }
LABEL_48:
  if ( v18 )
  {
    RegCloseKey(hKey);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    GlobalFree(v7);
    v6 = WPP_GLOBAL_Control;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x800) != 0 && *((_BYTE *)v6 + 25) >= 6u )
  {
    v9 = 689;
    goto LABEL_58;
  }
  return v8;
}

```

## disassembly

```asm
0x18006b110  mov     [rsp-38h+arg_8], rbx
0x18006b115  push    rbp
0x18006b116  push    rsi
0x18006b117  push    rdi
0x18006b118  push    r12
0x18006b11a  push    r13
0x18006b11c  push    r14
0x18006b11e  push    r15
0x18006b120  mov     rbp, rsp
0x18006b123  sub     rsp, 40h
0x18006b127  xor     r13d, r13d
0x18006b12a  mov     r15, r8
0x18006b12d  mov     r12, rdx
0x18006b130  mov     r14, rcx
0x18006b133  test    rcx, rcx
0x18006b136  jz      short loc_18006B174
0x18006b138  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b13f  lea     rdi, WPP_GLOBAL_Control
0x18006b146  cmp     rcx, rdi
0x18006b149  jz      short loc_18006B1B2
0x18006b14b  test    dword ptr [rcx+1Ch], 800h
0x18006b152  jz      short loc_18006B1B2
0x18006b154  cmp     byte ptr [rcx+19h], 6
0x18006b158  jb      short loc_18006B1B2
0x18006b15a  mov     rcx, [rcx+10h]
0x18006b15e  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006b165  mov     edx, 2A9h
0x18006b16a  mov     r9, r14
0x18006b16d  call    WPP_SF_S
0x18006b172  jmp     short loc_18006B1AB
0x18006b174  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b17b  lea     rdi, WPP_GLOBAL_Control
0x18006b182  cmp     rcx, rdi
0x18006b185  jz      short loc_18006B1B2
0x18006b187  test    dword ptr [rcx+1Ch], 800h
0x18006b18e  jz      short loc_18006B1B2
0x18006b190  cmp     byte ptr [rcx+19h], 6
0x18006b194  jb      short loc_18006B1B2
0x18006b196  mov     rcx, [rcx+10h]
0x18006b19a  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006b1a1  mov     edx, 2AAh
0x18006b1a6  call    WPP_SF_
0x18006b1ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b1b2  mov     [rbp+var_8], r13
0x18006b1b6  mov     rsi, r13
0x18006b1b9  mov     [rbp+hKey], r13
0x18006b1bd  mov     [rbp+arg_18], r13
0x18006b1c1  mov     [rbp+arg_0], r13d
0x18006b1c5  test    r14, r14
0x18006b1c8  jnz     short loc_18006B22F
0x18006b1ca  lea     ebx, [r14+57h]
0x18006b1ce  cmp     rcx, rdi
0x18006b1d1  jz      loc_18006B40A
0x18006b1d7  test    dword ptr [rcx+1Ch], 800h
0x18006b1de  jz      short loc_18006B205
0x18006b1e0  cmp     byte ptr [rcx+19h], 2
0x18006b1e4  jb      short loc_18006B205
0x18006b1e6  mov     rcx, [rcx+10h]
0x18006b1ea  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006b1f1  mov     edx, 2ABh
0x18006b1f6  mov     r9d, ebx
0x18006b1f9  call    WPP_SF_d
0x18006b1fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b205  cmp     rcx, rdi
0x18006b208  jz      loc_18006B40A
0x18006b20e  test    dword ptr [rcx+1Ch], 800h
0x18006b215  jz      loc_18006B40A
0x18006b21b  cmp     byte ptr [rcx+19h], 6
0x18006b21f  jb      loc_18006B40A
0x18006b225  mov     edx, 2ACh
0x18006b22a  jmp     loc_18006B3F7
0x18006b22f  lea     rdx, [rbp+arg_0]
0x18006b233  lea     rcx, [rbp+hKey]; phkResult
0x18006b237  call    DwOpenUsersRegistry
0x18006b23c  mov     ebx, eax
0x18006b23e  test    eax, eax
0x18006b240  jz      short loc_18006B286
0x18006b242  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b249  cmp     rcx, rdi
0x18006b24c  jz      loc_18006B399
0x18006b252  test    dword ptr [rcx+1Ch], 800h
0x18006b259  jz      loc_18006B399
0x18006b25f  cmp     byte ptr [rcx+19h], 2
0x18006b263  jb      loc_18006B399
0x18006b269  mov     edx, 2ADh
0x18006b26e  mov     rcx, [rcx+10h]
0x18006b272  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006b279  mov     r9d, eax
0x18006b27c  call    WPP_SF_d
0x18006b281  jmp     loc_18006B392
0x18006b286  mov     rcx, [rbp+hKey]; hKey
0x18006b28a  lea     rax, [rbp+var_8]
0x18006b28e  mov     r9d, 2001Dh; samDesired
0x18006b294  mov     [rsp+40h+phkResult], rax; phkResult
0x18006b299  xor     r8d, r8d; ulOptions
0x18006b29c  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\RAS AutoDial"
0x18006b2a3  call    cs:__imp_RegOpenKeyExW
0x18006b2a9  mov     ebx, eax
0x18006b2ab  test    eax, eax
0x18006b2ad  jz      short loc_18006B2DD
0x18006b2af  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b2b6  cmp     rcx, rdi
0x18006b2b9  jz      loc_18006B399
0x18006b2bf  test    dword ptr [rcx+1Ch], 800h
0x18006b2c6  jz      loc_18006B399
0x18006b2cc  cmp     byte ptr [rcx+19h], 2
0x18006b2d0  jb      loc_18006B399
0x18006b2d6  mov     edx, 2AEh
0x18006b2db  jmp     short loc_18006B26E
0x18006b2dd  mov     rcx, [rbp+var_8]; hKey
0x18006b2e1  lea     r8, [rbp+arg_18]
0x18006b2e5  mov     rdx, r14
0x18006b2e8  call    AutodialAddressToNetwork
0x18006b2ed  mov     ebx, eax
0x18006b2ef  test    eax, eax
0x18006b2f1  jz      short loc_18006B332
0x18006b2f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b2fa  cmp     rcx, rdi
0x18006b2fd  jz      short loc_18006B32C
0x18006b2ff  test    dword ptr [rcx+1Ch], 800h
0x18006b306  jz      short loc_18006B32C
0x18006b308  cmp     byte ptr [rcx+19h], 2
0x18006b30c  jb      short loc_18006B32C
0x18006b30e  mov     rcx, [rcx+10h]
0x18006b312  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006b319  mov     edx, 2AFh
0x18006b31e  mov     r9d, eax
0x18006b321  call    WPP_SF_d
0x18006b326  mov     rsi, [rbp+arg_18]
0x18006b32a  jmp     short loc_18006B392
0x18006b32c  mov     rsi, [rbp+arg_18]
0x18006b330  jmp     short loc_18006B399
0x18006b332  mov     rsi, [rbp+arg_18]
0x18006b336  or      r14, 0FFFFFFFFFFFFFFFFh
0x18006b33a  inc     r14
0x18006b33d  cmp     [rsi+r14*2], r13w
0x18006b342  jnz     short loc_18006B33A
0x18006b344  lea     r14d, ds:2[r14*2]
0x18006b34c  test    r12, r12
0x18006b34f  jz      short loc_18006B38F
0x18006b351  cmp     [r15], r14d
0x18006b354  jb      short loc_18006B38F
0x18006b356  mov     edx, [r15]
0x18006b359  mov     r8, rsi
0x18006b35c  mov     rcx, r12; pszDest
0x18006b35f  call    StringCchCopyWrapW
0x18006b364  mov     ebx, eax
0x18006b366  test    eax, eax
0x18006b368  jz      short loc_18006B38F
0x18006b36a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b371  cmp     rcx, rdi
0x18006b374  jz      short loc_18006B399
0x18006b376  test    dword ptr [rcx+1Ch], 800h
0x18006b37d  jz      short loc_18006B399
0x18006b37f  cmp     byte ptr [rcx+19h], 2
0x18006b383  jb      short loc_18006B399
0x18006b385  mov     edx, 2B0h
0x18006b38a  jmp     loc_18006B26E
0x18006b38f  mov     [r15], r14d
0x18006b392  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b399  cmp     [rbp+arg_0], r13d
0x18006b39d  jz      short loc_18006B3B0
0x18006b39f  mov     rcx, [rbp+hKey]; hKey
0x18006b3a3  call    cs:__imp_RegCloseKey
0x18006b3a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b3b0  test    rsi, rsi
0x18006b3b3  jz      short loc_18006B3C5
0x18006b3b5  mov     rcx, rsi; hMem
0x18006b3b8  call    cs:__imp_GlobalFree
0x18006b3be  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b3c5  mov     rax, [rbp+var_8]
0x18006b3c9  test    rax, rax
0x18006b3cc  jz      short loc_18006B3DE
0x18006b3ce  mov     rcx, rax; hKey
0x18006b3d1  call    cs:__imp_RegCloseKey
0x18006b3d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b3de  cmp     rcx, rdi
0x18006b3e1  jz      short loc_18006B40A
0x18006b3e3  test    dword ptr [rcx+1Ch], 800h
0x18006b3ea  jz      short loc_18006B40A
0x18006b3ec  cmp     byte ptr [rcx+19h], 6
0x18006b3f0  jb      short loc_18006B40A
0x18006b3f2  mov     edx, 2B1h
0x18006b3f7  mov     rcx, [rcx+10h]
0x18006b3fb  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006b402  mov     r9d, ebx
0x18006b405  call    WPP_SF_d
0x18006b40a  mov     eax, ebx
0x18006b40c  mov     rbx, [rsp+40h+arg_8]
0x18006b414  add     rsp, 40h
0x18006b418  pop     r15
0x18006b41a  pop     r14
0x18006b41c  pop     r13
0x18006b41e  pop     r12
0x18006b420  pop     rdi
0x18006b421  pop     rsi
0x18006b422  pop     rbp
0x18006b423  retn
```
