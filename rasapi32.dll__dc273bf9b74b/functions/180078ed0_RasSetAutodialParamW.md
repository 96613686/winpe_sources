# RasSetAutodialParamW

- ea: `0x180078ed0`
- end: `0x1800791fc`
- name: `RasSetAutodialParamW`
- size: `812`
- prototype: `DWORD __stdcall(DWORD, LPVOID, DWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180078df0`

## callees

- `0x18000f31c`
- `0x180010d10`
- `0x18004e580`
- `0x180066c20`
- `0x180078ed0`
- `0x18007f140`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180079145`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180079145`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180079060`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800790d6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180079060`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800790d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079116`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079194`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800791ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079116`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079194`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800791ab`

## pseudocode

```c
DWORD __stdcall RasSetAutodialParamW(DWORD a1, LPVOID a2, DWORD a3)
{
  __int64 v4; // rsi
  DWORD v6; // eax
  DWORD v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // eax
  DWORD dwType; // [rsp+50h] [rbp-20h] BYREF
  int v15; // [rsp+54h] [rbp-1Ch]
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  HKEY v17; // [rsp+60h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-8h] BYREF
  DWORD v19; // [rsp+B0h] [rbp+40h] BYREF
  DWORD dwDisposition; // [rsp+B8h] [rbp+48h] BYREF

  v19 = a3;
  v4 = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 868, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, a1, a3);
  }
  phkResult = 0;
  v17 = 0;
  hKey = 0;
  dwType = 0;
  dwDisposition = 0;
  v15 = 0;
  DebugInit();
  v6 = AutodialVerifyParam((unsigned int)v4, a2, &dwType, &v19);
  v7 = v6;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 869, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v6);
        v8 = WPP_GLOBAL_Control;
      }
      if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x800) != 0 && *((_BYTE *)v8 + 25) >= 6u )
      {
        v9 = 870;
LABEL_45:
        WPP_SF_d(v8[2], v9, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v7);
        return v7;
      }
    }
    return v7;
  }
  v10 = DwOpenUsersRegistry(&hKey);
  v7 = v10;
  if ( v10 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 871;
LABEL_35:
      WPP_SF_d(v8[2], v11, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v10);
LABEL_36:
      v8 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v10 = RegCreateKeyExW(hKey, L"Software\\Microsoft\\RAS AutoDial", 0, 0, 0, 0x2001Du, 0, &phkResult, &dwDisposition);
    v7 = v10;
    if ( v10 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 872;
        goto LABEL_35;
      }
    }
    else
    {
      v12 = RegCreateKeyExW(phkResult, L"Control", 0, 0, 0, 2u, 0, &v17, &dwDisposition);
      v7 = v12;
      if ( v12
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 873, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v12);
      }
      RegCloseKey(phkResult);
      if ( v7 )
        goto LABEL_36;
      v10 = RegSetValueExW(v17, (&AutodialParamRegKeys)[2 * v4], 0, dwType, (const BYTE *)a2, a3);
      v7 = v10;
      if ( !v10 )
        goto LABEL_36;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 874;
        goto LABEL_35;
      }
    }
  }
  if ( v17 )
  {
    RegCloseKey(v17);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v15 )
  {
    RegCloseKey(hKey);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x800) != 0 && *((_BYTE *)v8 + 25) >= 6u )
  {
    v9 = 875;
    goto LABEL_45;
  }
  return v7;
}

```

## disassembly

```asm
0x180078ed0  mov     rax, rsp
0x180078ed3  mov     [rax+8], rbx
0x180078ed7  mov     [rax+10h], rsi
0x180078edb  mov     [rax+18h], r8d
0x180078edf  push    rbp
0x180078ee0  push    rdi
0x180078ee1  push    r12
0x180078ee3  push    r13
0x180078ee5  push    r14
0x180078ee7  mov     rbp, rsp
0x180078eea  sub     rsp, 70h
0x180078eee  mov     edi, r8d
0x180078ef1  mov     esi, ecx
0x180078ef3  mov     r14, rdx
0x180078ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x180078efd  lea     r13, WPP_GLOBAL_Control
0x180078f04  mov     r12d, 800h
0x180078f0a  cmp     rcx, r13
0x180078f0d  jz      short loc_180078F37
0x180078f0f  test    [rcx+1Ch], r12d
0x180078f13  jz      short loc_180078F37
0x180078f15  cmp     byte ptr [rcx+19h], 6
0x180078f19  jb      short loc_180078F37
0x180078f1b  mov     rcx, [rcx+10h]
0x180078f1f  mov     edx, 364h
0x180078f24  mov     [rax-78h], r8d
0x180078f28  mov     r9d, esi
0x180078f2b  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180078f32  call    WPP_SF_Dd
0x180078f37  mov     [rbp+var_18], 0
0x180078f3f  mov     [rbp+var_10], 0
0x180078f47  mov     [rbp+hKey], 0
0x180078f4f  mov     [rbp+dwType], 0
0x180078f56  mov     [rbp+dwDisposition], 0
0x180078f5d  mov     [rbp+var_1C], 0
0x180078f64  call    DebugInit
0x180078f69  lea     r9, [rbp+arg_10]
0x180078f6d  mov     rdx, r14
0x180078f70  lea     r8, [rbp+dwType]
0x180078f74  mov     ecx, esi
0x180078f76  call    AutodialVerifyParam
0x180078f7b  mov     ebx, eax
0x180078f7d  test    eax, eax
0x180078f7f  jz      short loc_180078FE3
0x180078f81  mov     rcx, cs:WPP_GLOBAL_Control
0x180078f88  cmp     rcx, r13
0x180078f8b  jz      loc_1800791E1
0x180078f91  test    [rcx+1Ch], r12d
0x180078f95  jz      short loc_180078FBC
0x180078f97  cmp     byte ptr [rcx+19h], 2
0x180078f9b  jb      short loc_180078FBC
0x180078f9d  mov     rcx, [rcx+10h]
0x180078fa1  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180078fa8  mov     edx, 365h
0x180078fad  mov     r9d, eax
0x180078fb0  call    WPP_SF_d
0x180078fb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180078fbc  cmp     rcx, r13
0x180078fbf  jz      loc_1800791E1
0x180078fc5  test    [rcx+1Ch], r12d
0x180078fc9  jz      loc_1800791E1
0x180078fcf  cmp     byte ptr [rcx+19h], 6
0x180078fd3  jb      loc_1800791E1
0x180078fd9  mov     edx, 366h
0x180078fde  jmp     loc_1800791CE
0x180078fe3  lea     rdx, [rbp+var_1C]
0x180078fe7  lea     rcx, [rbp+hKey]; phkResult
0x180078feb  call    DwOpenUsersRegistry
0x180078ff0  mov     ebx, eax
0x180078ff2  test    eax, eax
0x180078ff4  jz      short loc_180079024
0x180078ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x180078ffd  cmp     rcx, r13
0x180079000  jz      loc_180079188
0x180079006  test    [rcx+1Ch], r12d
0x18007900a  jz      loc_180079188
0x180079010  cmp     byte ptr [rcx+19h], 2
0x180079014  jb      loc_180079188
0x18007901a  mov     edx, 367h
0x18007901f  jmp     loc_18007916E
0x180079024  mov     rcx, [rbp+hKey]; hKey
0x180079028  lea     rax, [rbp+dwDisposition]
0x18007902c  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x180079031  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\RAS AutoDial"
0x180079038  lea     rax, [rbp+var_18]
0x18007903c  xor     r9d, r9d; lpClass
0x18007903f  mov     [rsp+70h+phkResult], rax; phkResult
0x180079044  xor     r8d, r8d; Reserved
0x180079047  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180079050  mov     [rsp+70h+samDesired], 2001Dh; samDesired
0x180079058  mov     [rsp+70h+dwOptions], 0; dwOptions
0x180079060  call    cs:__imp_RegCreateKeyExW
0x180079066  mov     ebx, eax
0x180079068  test    eax, eax
0x18007906a  jz      short loc_18007909A
0x18007906c  mov     rcx, cs:WPP_GLOBAL_Control
0x180079073  cmp     rcx, r13
0x180079076  jz      loc_180079188
0x18007907c  test    [rcx+1Ch], r12d
0x180079080  jz      loc_180079188
0x180079086  cmp     byte ptr [rcx+19h], 2
0x18007908a  jb      loc_180079188
0x180079090  mov     edx, 368h
0x180079095  jmp     loc_18007916E
0x18007909a  mov     rcx, [rbp+var_18]; hKey
0x18007909e  lea     rax, [rbp+dwDisposition]
0x1800790a2  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x1800790a7  lea     rdx, aControl; "Control"
0x1800790ae  lea     rax, [rbp+var_10]
0x1800790b2  xor     r9d, r9d; lpClass
0x1800790b5  mov     [rsp+70h+phkResult], rax; phkResult
0x1800790ba  xor     r8d, r8d; Reserved
0x1800790bd  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800790c6  mov     [rsp+70h+samDesired], 2; samDesired
0x1800790ce  mov     [rsp+70h+dwOptions], 0; dwOptions
0x1800790d6  call    cs:__imp_RegCreateKeyExW
0x1800790dc  mov     ebx, eax
0x1800790de  test    eax, eax
0x1800790e0  jz      short loc_180079112
0x1800790e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800790e9  cmp     rcx, r13
0x1800790ec  jz      short loc_180079112
0x1800790ee  test    [rcx+1Ch], r12d
0x1800790f2  jz      short loc_180079112
0x1800790f4  cmp     byte ptr [rcx+19h], 2
0x1800790f8  jb      short loc_180079112
0x1800790fa  mov     rcx, [rcx+10h]
0x1800790fe  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180079105  mov     edx, 369h
0x18007910a  mov     r9d, eax
0x18007910d  call    WPP_SF_d
0x180079112  mov     rcx, [rbp+var_18]; hKey
0x180079116  call    cs:__imp_RegCloseKey
0x18007911c  test    ebx, ebx
0x18007911e  jnz     short loc_180079181
0x180079120  mov     r9d, [rbp+dwType]; dwType
0x180079124  lea     rax, AutodialParamRegKeys
0x18007912b  mov     rcx, [rbp+var_10]; hKey
0x18007912f  mov     rdx, rsi
0x180079132  add     rdx, rdx
0x180079135  mov     [rsp+70h+samDesired], edi; cbData
0x180079139  xor     r8d, r8d; Reserved
0x18007913c  mov     qword ptr [rsp+70h+dwOptions], r14; lpData
0x180079141  mov     rdx, [rax+rdx*8]; lpValueName
0x180079145  call    cs:__imp_RegSetValueExW
0x18007914b  mov     ebx, eax
0x18007914d  test    eax, eax
0x18007914f  jz      short loc_180079181
0x180079151  mov     rcx, cs:WPP_GLOBAL_Control
0x180079158  cmp     rcx, r13
0x18007915b  jz      short loc_180079188
0x18007915d  test    [rcx+1Ch], r12d
0x180079161  jz      short loc_180079188
0x180079163  cmp     byte ptr [rcx+19h], 2
0x180079167  jb      short loc_180079188
0x180079169  mov     edx, 36Ah
0x18007916e  mov     rcx, [rcx+10h]
0x180079172  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180079179  mov     r9d, eax
0x18007917c  call    WPP_SF_d
0x180079181  mov     rcx, cs:WPP_GLOBAL_Control
0x180079188  mov     rax, [rbp+var_10]
0x18007918c  test    rax, rax
0x18007918f  jz      short loc_1800791A1
0x180079191  mov     rcx, rax; hKey
0x180079194  call    cs:__imp_RegCloseKey
0x18007919a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800791a1  cmp     [rbp+var_1C], 0
0x1800791a5  jz      short loc_1800791B8
0x1800791a7  mov     rcx, [rbp+hKey]; hKey
0x1800791ab  call    cs:__imp_RegCloseKey
0x1800791b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800791b8  cmp     rcx, r13
0x1800791bb  jz      short loc_1800791E1
0x1800791bd  test    [rcx+1Ch], r12d
0x1800791c1  jz      short loc_1800791E1
0x1800791c3  cmp     byte ptr [rcx+19h], 6
0x1800791c7  jb      short loc_1800791E1
0x1800791c9  mov     edx, 36Bh
0x1800791ce  mov     rcx, [rcx+10h]
0x1800791d2  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x1800791d9  mov     r9d, ebx
0x1800791dc  call    WPP_SF_d
0x1800791e1  lea     r11, [rsp+70h+var_s0]
0x1800791e6  mov     eax, ebx
0x1800791e8  mov     rbx, [r11+30h]
0x1800791ec  mov     rsi, [r11+38h]
0x1800791f0  mov     rsp, r11
0x1800791f3  pop     r14
0x1800791f5  pop     r13
0x1800791f7  pop     r12
0x1800791f9  pop     rdi
0x1800791fa  pop     rbp
0x1800791fb  retn
```
