# RasGetAutodialParamW

- ea: `0x18006f210`
- end: `0x18006f54e`
- name: `RasGetAutodialParamW`
- size: `830`
- prototype: `DWORD __stdcall(DWORD, LPVOID, LPDWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006f130`

## callees

- `0x18000f31c`
- `0x180010d10`
- `0x18004e580`
- `0x1800668b8`
- `0x18006f210`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006f388`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006f3da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006f388`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006f3da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f3e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f485`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f49c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f3e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f485`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f49c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006f438`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006f438`

## pseudocode

```c
DWORD __stdcall RasGetAutodialParamW(DWORD a1, LPVOID a2, LPDWORD a3)
{
  __int64 v4; // r14
  DWORD v6; // eax
  DWORD v7; // ebx
  _QWORD *v8; // rcx
  unsigned int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // ebx
  __int64 v14; // r9
  _QWORD *v15; // rcx
  HKEY phkResult; // [rsp+30h] [rbp-20h] BYREF
  HKEY v17; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  DWORD Type; // [rsp+98h] [rbp+48h] BYREF

  v4 = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 879, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, a1);
  }
  phkResult = 0;
  v17 = 0;
  Type = 0;
  hKey = 0;
  DebugInit();
  if ( a2 && a3 )
  {
    v6 = AutodialParamSetDefaults((unsigned int)v4, a2, a3);
    v7 = v6;
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 882, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v6);
          v8 = WPP_GLOBAL_Control;
        }
        if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x800) != 0 && *((_BYTE *)v8 + 25) >= 6u )
          WPP_SF_d(v8[2], 883, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v7);
      }
      return v7;
    }
    v10 = DwOpenUsersRegistry(&hKey);
    if ( v10 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      v12 = 884;
    }
    else
    {
      v10 = RegOpenKeyExW(hKey, L"Software\\Microsoft\\RAS AutoDial", 0, 0x20019u, &phkResult);
      if ( v10 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_40;
        }
        v12 = 885;
      }
      else
      {
        v13 = RegOpenKeyExW(phkResult, L"Control", 0, 0x20019u, &v17);
        RegCloseKey(phkResult);
        if ( v13 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_40;
          }
          v12 = 886;
          v14 = v13;
          goto LABEL_38;
        }
        v10 = RegQueryValueExW(v17, (&AutodialParamRegKeys)[2 * v4], 0, &Type, (LPBYTE)a2, a3);
        if ( !v10 )
        {
LABEL_39:
          v11 = WPP_GLOBAL_Control;
LABEL_40:
          if ( v17 )
          {
            RegCloseKey(v17);
            v11 = WPP_GLOBAL_Control;
          }
          if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x800) != 0 && *((_BYTE *)v11 + 25) >= 6u )
            WPP_SF_d(v11[2], 888, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 0);
          return 0;
        }
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_40;
        }
        v12 = 887;
      }
    }
    v14 = v10;
LABEL_38:
    WPP_SF_d(v11[2], v12, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v14);
    goto LABEL_39;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 880, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
      v15 = WPP_GLOBAL_Control;
    }
    if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x800) != 0 && *((_BYTE *)v15 + 25) >= 6u )
      WPP_SF_d(v15[2], 881, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
  }
  return 87;
}

```

## disassembly

```asm
0x18006f210  mov     [rsp-28h+arg_0], rbx
0x18006f215  mov     [rsp-28h+arg_10], rsi
0x18006f21a  push    rbp
0x18006f21b  push    rdi
0x18006f21c  push    r12
0x18006f21e  push    r13
0x18006f220  push    r14
0x18006f222  mov     rbp, rsp
0x18006f225  sub     rsp, 50h
0x18006f229  mov     rdi, r8
0x18006f22c  mov     r14d, ecx
0x18006f22f  mov     rsi, rdx
0x18006f232  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f239  lea     r13, WPP_GLOBAL_Control
0x18006f240  lea     rbx, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006f247  mov     r12d, 800h
0x18006f24d  cmp     rcx, r13
0x18006f250  jz      short loc_18006F272
0x18006f252  test    [rcx+1Ch], r12d
0x18006f256  jz      short loc_18006F272
0x18006f258  cmp     byte ptr [rcx+19h], 6
0x18006f25c  jb      short loc_18006F272
0x18006f25e  mov     rcx, [rcx+10h]
0x18006f262  mov     edx, 36Fh
0x18006f267  mov     r9d, r14d
0x18006f26a  mov     r8, rbx
0x18006f26d  call    WPP_SF_d
0x18006f272  mov     [rbp+var_20], 0
0x18006f27a  mov     [rbp+var_18], 0
0x18006f282  mov     [rbp+Type], 0
0x18006f289  mov     [rbp+hKey], 0
0x18006f291  mov     [rbp+arg_8], 0
0x18006f298  call    DebugInit
0x18006f29d  test    rsi, rsi
0x18006f2a0  jz      loc_18006F4D6
0x18006f2a6  test    rdi, rdi
0x18006f2a9  jz      loc_18006F4D6
0x18006f2af  mov     r8, rdi
0x18006f2b2  mov     rdx, rsi
0x18006f2b5  mov     ecx, r14d
0x18006f2b8  call    AutodialParamSetDefaults
0x18006f2bd  mov     ebx, eax
0x18006f2bf  test    eax, eax
0x18006f2c1  jz      short loc_18006F32A
0x18006f2c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f2ca  cmp     rcx, r13
0x18006f2cd  jz      short loc_18006F323
0x18006f2cf  test    [rcx+1Ch], r12d
0x18006f2d3  jz      short loc_18006F2FA
0x18006f2d5  cmp     byte ptr [rcx+19h], 2
0x18006f2d9  jb      short loc_18006F2FA
0x18006f2db  mov     rcx, [rcx+10h]
0x18006f2df  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006f2e6  mov     edx, 372h
0x18006f2eb  mov     r9d, eax
0x18006f2ee  call    WPP_SF_d
0x18006f2f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f2fa  cmp     rcx, r13
0x18006f2fd  jz      short loc_18006F323
0x18006f2ff  test    [rcx+1Ch], r12d
0x18006f303  jz      short loc_18006F323
0x18006f305  cmp     byte ptr [rcx+19h], 6
0x18006f309  jb      short loc_18006F323
0x18006f30b  mov     rcx, [rcx+10h]
0x18006f30f  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006f316  mov     edx, 373h
0x18006f31b  mov     r9d, ebx
0x18006f31e  call    WPP_SF_d
0x18006f323  mov     eax, ebx
0x18006f325  jmp     loc_18006F535
0x18006f32a  lea     rdx, [rbp+arg_8]
0x18006f32e  lea     rcx, [rbp+hKey]; phkResult
0x18006f332  call    DwOpenUsersRegistry
0x18006f337  test    eax, eax
0x18006f339  jz      short loc_18006F369
0x18006f33b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f342  cmp     rcx, r13
0x18006f345  jz      loc_18006F479
0x18006f34b  test    [rcx+1Ch], r12d
0x18006f34f  jz      loc_18006F479
0x18006f355  cmp     byte ptr [rcx+19h], 2
0x18006f359  jb      loc_18006F479
0x18006f35f  mov     edx, 374h
0x18006f364  jmp     loc_18006F45F
0x18006f369  mov     rcx, [rbp+hKey]; hKey
0x18006f36d  lea     rax, [rbp+var_20]
0x18006f371  mov     ebx, 20019h
0x18006f376  mov     [rsp+50h+phkResult], rax; phkResult
0x18006f37b  mov     r9d, ebx; samDesired
0x18006f37e  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\RAS AutoDial"
0x18006f385  xor     r8d, r8d; ulOptions
0x18006f388  call    cs:__imp_RegOpenKeyExW
0x18006f38e  test    eax, eax
0x18006f390  jz      short loc_18006F3C0
0x18006f392  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f399  cmp     rcx, r13
0x18006f39c  jz      loc_18006F479
0x18006f3a2  test    [rcx+1Ch], r12d
0x18006f3a6  jz      loc_18006F479
0x18006f3ac  cmp     byte ptr [rcx+19h], 2
0x18006f3b0  jb      loc_18006F479
0x18006f3b6  mov     edx, 375h
0x18006f3bb  jmp     loc_18006F45F
0x18006f3c0  mov     rcx, [rbp+var_20]; hKey
0x18006f3c4  lea     rax, [rbp+var_18]
0x18006f3c8  mov     r9d, ebx; samDesired
0x18006f3cb  mov     [rsp+50h+phkResult], rax; phkResult
0x18006f3d0  xor     r8d, r8d; ulOptions
0x18006f3d3  lea     rdx, aControl; "Control"
0x18006f3da  call    cs:__imp_RegOpenKeyExW
0x18006f3e0  mov     rcx, [rbp+var_20]; hKey
0x18006f3e4  mov     ebx, eax
0x18006f3e6  call    cs:__imp_RegCloseKey
0x18006f3ec  test    ebx, ebx
0x18006f3ee  jz      short loc_18006F412
0x18006f3f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f3f7  cmp     rcx, r13
0x18006f3fa  jz      short loc_18006F479
0x18006f3fc  test    [rcx+1Ch], r12d
0x18006f400  jz      short loc_18006F479
0x18006f402  cmp     byte ptr [rcx+19h], 2
0x18006f406  jb      short loc_18006F479
0x18006f408  mov     edx, 376h
0x18006f40d  mov     r9d, ebx
0x18006f410  jmp     short loc_18006F462
0x18006f412  mov     rcx, [rbp+var_18]; hKey
0x18006f416  lea     rax, AutodialParamRegKeys
0x18006f41d  mov     rdx, r14
0x18006f420  mov     [rsp+50h+lpcbData], rdi; lpcbData
0x18006f425  add     rdx, rdx
0x18006f428  mov     [rsp+50h+phkResult], rsi; lpData
0x18006f42d  lea     r9, [rbp+Type]; lpType
0x18006f431  xor     r8d, r8d; lpReserved
0x18006f434  mov     rdx, [rax+rdx*8]; lpValueName
0x18006f438  call    cs:__imp_RegQueryValueExW
0x18006f43e  test    eax, eax
0x18006f440  jz      short loc_18006F472
0x18006f442  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f449  cmp     rcx, r13
0x18006f44c  jz      short loc_18006F479
0x18006f44e  test    [rcx+1Ch], r12d
0x18006f452  jz      short loc_18006F479
0x18006f454  cmp     byte ptr [rcx+19h], 2
0x18006f458  jb      short loc_18006F479
0x18006f45a  mov     edx, 377h
0x18006f45f  mov     r9d, eax
0x18006f462  mov     rcx, [rcx+10h]
0x18006f466  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006f46d  call    WPP_SF_d
0x18006f472  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f479  mov     rax, [rbp+var_18]
0x18006f47d  test    rax, rax
0x18006f480  jz      short loc_18006F492
0x18006f482  mov     rcx, rax; hKey
0x18006f485  call    cs:__imp_RegCloseKey
0x18006f48b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f492  cmp     [rbp+arg_8], 0
0x18006f496  jz      short loc_18006F4A9
0x18006f498  mov     rcx, [rbp+hKey]; hKey
0x18006f49c  call    cs:__imp_RegCloseKey
0x18006f4a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f4a9  cmp     rcx, r13
0x18006f4ac  jz      short loc_18006F4D2
0x18006f4ae  test    [rcx+1Ch], r12d
0x18006f4b2  jz      short loc_18006F4D2
0x18006f4b4  cmp     byte ptr [rcx+19h], 6
0x18006f4b8  jb      short loc_18006F4D2
0x18006f4ba  mov     rcx, [rcx+10h]
0x18006f4be  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006f4c5  mov     edx, 378h
0x18006f4ca  xor     r9d, r9d
0x18006f4cd  call    WPP_SF_d
0x18006f4d2  xor     eax, eax
0x18006f4d4  jmp     short loc_18006F535
0x18006f4d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f4dd  mov     edi, 57h ; 'W'
0x18006f4e2  cmp     rcx, r13
0x18006f4e5  jz      short loc_18006F533
0x18006f4e7  test    [rcx+1Ch], r12d
0x18006f4eb  jz      short loc_18006F50E
0x18006f4ed  cmp     byte ptr [rcx+19h], 2
0x18006f4f1  jb      short loc_18006F50E
0x18006f4f3  mov     rcx, [rcx+10h]
0x18006f4f7  mov     edx, 370h
0x18006f4fc  mov     r9d, edi
0x18006f4ff  mov     r8, rbx
0x18006f502  call    WPP_SF_d
0x18006f507  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f50e  cmp     rcx, r13
0x18006f511  jz      short loc_18006F533
0x18006f513  test    [rcx+1Ch], r12d
0x18006f517  jz      short loc_18006F533
0x18006f519  cmp     byte ptr [rcx+19h], 6
0x18006f51d  jb      short loc_18006F533
0x18006f51f  mov     rcx, [rcx+10h]
0x18006f523  mov     edx, 371h
0x18006f528  mov     r9d, edi
0x18006f52b  mov     r8, rbx
0x18006f52e  call    WPP_SF_d
0x18006f533  mov     eax, edi
0x18006f535  lea     r11, [rsp+50h+var_s0]
0x18006f53a  mov     rbx, [r11+30h]
0x18006f53e  mov     rsi, [r11+40h]
0x18006f542  mov     rsp, r11
0x18006f545  pop     r14
0x18006f547  pop     r13
0x18006f549  pop     r12
0x18006f54b  pop     rdi
0x18006f54c  pop     rbp
0x18006f54d  retn
```
