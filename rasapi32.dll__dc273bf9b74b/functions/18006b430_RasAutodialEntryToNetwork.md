# RasAutodialEntryToNetwork

- ea: `0x18006b430`
- end: `0x18006b749`
- name: `RasAutodialEntryToNetwork`
- size: `793`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, STRSAFE_LPWSTR pszDest)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006afc`
- `0x18000f31c`
- `0x180010d10`
- `0x18004e580`
- `0x18004e984`
- `0x1800664d8`
- `0x18006b430`
- `0x18007e5f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006b5c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006b5c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b6c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b6f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b6c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b6f6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006b6dd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006b6dd`

## pseudocode

```c
__int64 __fastcall RasAutodialEntryToNetwork(LPCWSTR lpValueName, STRSAFE_LPWSTR pszDest, unsigned int *a3)
{
  BYTE *v6; // rsi
  _QWORD *v7; // rcx
  unsigned int v9; // eax
  unsigned int v10; // edi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // rax
  unsigned int v15; // r14d
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-8h] BYREF
  int v18; // [rsp+80h] [rbp+40h] BYREF
  BYTE *v19; // [rsp+98h] [rbp+58h] BYREF

  if ( lpValueName )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 649, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, lpValueName);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 650, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
  }
  phkResult = 0;
  v6 = 0;
  v19 = 0;
  hKey = 0;
  v18 = 0;
  DebugInit();
  if ( !lpValueName )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 651, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x800) != 0 && *((_BYTE *)v7 + 25) >= 6u )
        WPP_SF_d(v7[2], 652, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
    }
    return 87;
  }
  v9 = DwOpenUsersRegistry(&hKey, &v18);
  v10 = v9;
  if ( v9 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_48;
    }
    v12 = 653;
    goto LABEL_25;
  }
  v9 = RegOpenKeyExW(hKey, L"Software\\Microsoft\\RAS AutoDial", 0, 0x2001Du, &phkResult);
  v10 = v9;
  if ( v9 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_48;
    }
    v12 = 654;
    goto LABEL_25;
  }
  v13 = AutodialEntryToNetwork(phkResult, lpValueName, 0, &v19);
  v10 = v13;
  if ( !v13 )
  {
    v6 = v19;
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)&v19[2 * v14] );
    v15 = 2 * v14 + 2;
    if ( !pszDest || *a3 < v15 )
    {
      *a3 = v15;
      goto LABEL_47;
    }
    v9 = StringCchCopyWrapW(pszDest);
    *a3 = v15;
    v10 = v9;
    if ( !v9 )
    {
LABEL_47:
      v11 = WPP_GLOBAL_Control;
      goto LABEL_48;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_48;
    }
    v12 = 656;
LABEL_25:
    WPP_SF_d(v11[2], v12, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v9);
    goto LABEL_47;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 655, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v13);
    v6 = v19;
    goto LABEL_47;
  }
  v6 = v19;
LABEL_48:
  if ( v18 )
  {
    RegCloseKey(hKey);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    GlobalFree(v6);
    v11 = WPP_GLOBAL_Control;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x800) != 0 && *((_BYTE *)v11 + 25) >= 6u )
    WPP_SF_d(v11[2], 657, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18006b430  mov     [rsp-38h+arg_8], rbx
0x18006b435  push    rbp
0x18006b436  push    rsi
0x18006b437  push    rdi
0x18006b438  push    r12
0x18006b43a  push    r13
0x18006b43c  push    r14
0x18006b43e  push    r15
0x18006b440  mov     rbp, rsp
0x18006b443  sub     rsp, 40h
0x18006b447  xor     r13d, r13d
0x18006b44a  mov     r15, r8
0x18006b44d  mov     r12, rdx
0x18006b450  mov     r14, rcx
0x18006b453  mov     edi, 800h
0x18006b458  test    rcx, rcx
0x18006b45b  jz      short loc_18006B495
0x18006b45d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b464  lea     rbx, WPP_GLOBAL_Control
0x18006b46b  cmp     rcx, rbx
0x18006b46e  jz      short loc_18006B4C8
0x18006b470  test    [rcx+1Ch], edi
0x18006b473  jz      short loc_18006B4C8
0x18006b475  cmp     byte ptr [rcx+19h], 6
0x18006b479  jb      short loc_18006B4C8
0x18006b47b  mov     rcx, [rcx+10h]
0x18006b47f  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006b486  mov     edx, 289h
0x18006b48b  mov     r9, r14
0x18006b48e  call    WPP_SF_S
0x18006b493  jmp     short loc_18006B4C8
0x18006b495  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b49c  lea     rbx, WPP_GLOBAL_Control
0x18006b4a3  cmp     rcx, rbx
0x18006b4a6  jz      short loc_18006B4C8
0x18006b4a8  test    [rcx+1Ch], edi
0x18006b4ab  jz      short loc_18006B4C8
0x18006b4ad  cmp     byte ptr [rcx+19h], 6
0x18006b4b1  jb      short loc_18006B4C8
0x18006b4b3  mov     rcx, [rcx+10h]
0x18006b4b7  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006b4be  mov     edx, 28Ah
0x18006b4c3  call    WPP_SF_
0x18006b4c8  mov     [rbp+var_8], r13
0x18006b4cc  mov     rsi, r13
0x18006b4cf  mov     [rbp+arg_18], r13
0x18006b4d3  mov     [rbp+hKey], r13
0x18006b4d7  mov     [rbp+arg_0], r13d
0x18006b4db  call    DebugInit
0x18006b4e0  test    r14, r14
0x18006b4e3  jnz     short loc_18006B54E
0x18006b4e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b4ec  lea     esi, [r14+57h]
0x18006b4f0  cmp     rcx, rbx
0x18006b4f3  jz      short loc_18006B547
0x18006b4f5  test    [rcx+1Ch], edi
0x18006b4f8  jz      short loc_18006B51F
0x18006b4fa  cmp     byte ptr [rcx+19h], 2
0x18006b4fe  jb      short loc_18006B51F
0x18006b500  mov     rcx, [rcx+10h]
0x18006b504  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006b50b  mov     edx, 28Bh
0x18006b510  mov     r9d, esi
0x18006b513  call    WPP_SF_d
0x18006b518  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b51f  cmp     rcx, rbx
0x18006b522  jz      short loc_18006B547
0x18006b524  test    [rcx+1Ch], edi
0x18006b527  jz      short loc_18006B547
0x18006b529  cmp     byte ptr [rcx+19h], 6
0x18006b52d  jb      short loc_18006B547
0x18006b52f  mov     rcx, [rcx+10h]
0x18006b533  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006b53a  mov     edx, 28Ch
0x18006b53f  mov     r9d, esi
0x18006b542  call    WPP_SF_d
0x18006b547  mov     eax, esi
0x18006b549  jmp     loc_18006B731
0x18006b54e  lea     rdx, [rbp+arg_0]
0x18006b552  lea     rcx, [rbp+hKey]; phkResult
0x18006b556  call    DwOpenUsersRegistry
0x18006b55b  mov     edi, eax
0x18006b55d  test    eax, eax
0x18006b55f  jz      short loc_18006B5A5
0x18006b561  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b568  cmp     rcx, rbx
0x18006b56b  jz      loc_18006B6BE
0x18006b571  test    dword ptr [rcx+1Ch], 800h
0x18006b578  jz      loc_18006B6BE
0x18006b57e  cmp     byte ptr [rcx+19h], 2
0x18006b582  jb      loc_18006B6BE
0x18006b588  mov     edx, 28Dh
0x18006b58d  mov     rcx, [rcx+10h]
0x18006b591  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006b598  mov     r9d, eax
0x18006b59b  call    WPP_SF_d
0x18006b5a0  jmp     loc_18006B6B7
0x18006b5a5  mov     rcx, [rbp+hKey]; hKey
0x18006b5a9  lea     rax, [rbp+var_8]
0x18006b5ad  mov     r9d, 2001Dh; samDesired
0x18006b5b3  mov     [rsp+40h+phkResult], rax; phkResult
0x18006b5b8  xor     r8d, r8d; ulOptions
0x18006b5bb  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\RAS AutoDial"
0x18006b5c2  call    cs:__imp_RegOpenKeyExW
0x18006b5c8  mov     edi, eax
0x18006b5ca  test    eax, eax
0x18006b5cc  jz      short loc_18006B5FC
0x18006b5ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b5d5  cmp     rcx, rbx
0x18006b5d8  jz      loc_18006B6BE
0x18006b5de  test    dword ptr [rcx+1Ch], 800h
0x18006b5e5  jz      loc_18006B6BE
0x18006b5eb  cmp     byte ptr [rcx+19h], 2
0x18006b5ef  jb      loc_18006B6BE
0x18006b5f5  mov     edx, 28Eh
0x18006b5fa  jmp     short loc_18006B58D
0x18006b5fc  mov     rcx, [rbp+var_8]; hKey
0x18006b600  lea     r9, [rbp+arg_18]
0x18006b604  xor     r8d, r8d
0x18006b607  mov     rdx, r14; lpValueName
0x18006b60a  call    AutodialEntryToNetwork
0x18006b60f  mov     edi, eax
0x18006b611  test    eax, eax
0x18006b613  jz      short loc_18006B654
0x18006b615  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b61c  cmp     rcx, rbx
0x18006b61f  jz      short loc_18006B64E
0x18006b621  test    dword ptr [rcx+1Ch], 800h
0x18006b628  jz      short loc_18006B64E
0x18006b62a  cmp     byte ptr [rcx+19h], 2
0x18006b62e  jb      short loc_18006B64E
0x18006b630  mov     rcx, [rcx+10h]
0x18006b634  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006b63b  mov     edx, 28Fh
0x18006b640  mov     r9d, eax
0x18006b643  call    WPP_SF_d
0x18006b648  mov     rsi, [rbp+arg_18]
0x18006b64c  jmp     short loc_18006B6B7
0x18006b64e  mov     rsi, [rbp+arg_18]
0x18006b652  jmp     short loc_18006B6BE
0x18006b654  mov     rsi, [rbp+arg_18]
0x18006b658  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006b65c  inc     rax
0x18006b65f  cmp     [rsi+rax*2], r13w
0x18006b664  jnz     short loc_18006B65C
0x18006b666  lea     r14d, ds:2[rax*2]
0x18006b66e  test    r12, r12
0x18006b671  jz      short loc_18006B6B4
0x18006b673  cmp     [r15], r14d
0x18006b676  jb      short loc_18006B6B4
0x18006b678  mov     edx, [r15]
0x18006b67b  mov     r8, rsi
0x18006b67e  mov     rcx, r12; pszDest
0x18006b681  call    StringCchCopyWrapW
0x18006b686  mov     [r15], r14d
0x18006b689  mov     edi, eax
0x18006b68b  test    eax, eax
0x18006b68d  jz      short loc_18006B6B7
0x18006b68f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b696  cmp     rcx, rbx
0x18006b699  jz      short loc_18006B6BE
0x18006b69b  test    dword ptr [rcx+1Ch], 800h
0x18006b6a2  jz      short loc_18006B6BE
0x18006b6a4  cmp     byte ptr [rcx+19h], 2
0x18006b6a8  jb      short loc_18006B6BE
0x18006b6aa  mov     edx, 290h
0x18006b6af  jmp     loc_18006B58D
0x18006b6b4  mov     [r15], r14d
0x18006b6b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b6be  cmp     [rbp+arg_0], r13d
0x18006b6c2  jz      short loc_18006B6D5
0x18006b6c4  mov     rcx, [rbp+hKey]; hKey
0x18006b6c8  call    cs:__imp_RegCloseKey
0x18006b6ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b6d5  test    rsi, rsi
0x18006b6d8  jz      short loc_18006B6EA
0x18006b6da  mov     rcx, rsi; hMem
0x18006b6dd  call    cs:__imp_GlobalFree
0x18006b6e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b6ea  mov     rax, [rbp+var_8]
0x18006b6ee  test    rax, rax
0x18006b6f1  jz      short loc_18006B703
0x18006b6f3  mov     rcx, rax; hKey
0x18006b6f6  call    cs:__imp_RegCloseKey
0x18006b6fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b703  cmp     rcx, rbx
0x18006b706  jz      short loc_18006B72F
0x18006b708  test    dword ptr [rcx+1Ch], 800h
0x18006b70f  jz      short loc_18006B72F
0x18006b711  cmp     byte ptr [rcx+19h], 6
0x18006b715  jb      short loc_18006B72F
0x18006b717  mov     rcx, [rcx+10h]
0x18006b71b  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006b722  mov     edx, 291h
0x18006b727  mov     r9d, edi
0x18006b72a  call    WPP_SF_d
0x18006b72f  mov     eax, edi
0x18006b731  mov     rbx, [rsp+40h+arg_8]
0x18006b739  add     rsp, 40h
0x18006b73d  pop     r15
0x18006b73f  pop     r14
0x18006b741  pop     r13
0x18006b743  pop     r12
0x18006b745  pop     rdi
0x18006b746  pop     rsi
0x18006b747  pop     rbp
0x18006b748  retn
```
