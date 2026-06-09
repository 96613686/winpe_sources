# Reg_GetValueEx2

- ea: `0x18007e1f0`
- end: `0x18007e51e`
- name: `Reg_GetValueEx2`
- size: `814`
- prototype: ``
- caller_count: `8`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180004d98`
- `0x180005b10`
- `0x180005c1c`
- `0x1800065c0`
- `0x18000702c`
- `0x1800082e4`
- `0x180097bc0`
- `0x18009ecd0`

## callees

- `0x18000723c`
- `0x180007cfc`
- `0x1800087a0`
- `0x180008830`
- `0x180038ea0`
- `0x18007e1f0`
- `0x18008b5f0`
- `0x1800dbfe0`
- `0x1800dc9e0`
- `0x1800de650`
- `0x1800de840`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e479`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e479`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e2cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e2cf`

## pseudocode

```c
__int64 __fastcall Reg_GetValueEx2(HKEY *a1, HKEY a2, const WCHAR *a3, unsigned int a4, int a5, char a6, _QWORD *a7)
{
  __int64 v9; // r14
  __int64 v11; // rax
  __int64 v12; // rdx
  int v13; // ecx
  int v14; // r8d
  unsigned int Value; // ebx
  const WCHAR *v16; // rax
  __int64 v17; // rdx
  const WCHAR *v18; // rax
  const WCHAR *v19; // rax
  __int64 v21; // [rsp+60h] [rbp-31h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-29h] BYREF
  HKEY v23[2]; // [rsp+70h] [rbp-21h] BYREF
  __int64 v24; // [rsp+80h] [rbp-11h]

  v24 = 0;
  *(_OWORD *)v23 = 0;
  LODWORD(v21) = 0;
  hKey = 0;
  v9 = a4;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    v11 = regValueNameForId(a4);
    WPP_SF_qqSdSdDq(v13, v12, v14, (_DWORD)a1, v12, (__int64)a3, v9, v11, a5, a6, (__int64)a7);
  }
  if ( !g_fVelocityDisableInternalExports )
    Reg_Init();
  if ( !regValueNameForId((unsigned int)v9) )
  {
    Value = 87;
    goto LABEL_33;
  }
  if ( a2 )
  {
    if ( a3 )
    {
      Value = RegOpenKeyExW(a2, a3, 0, 1u, &hKey);
      if ( Value )
        goto LABEL_33;
      a2 = hKey;
    }
  }
  else
  {
    Value = 2;
    if ( !a1 )
    {
      Value = Reg_OpenSession(v23);
      if ( Value )
        goto LABEL_33;
      a1 = v23;
    }
    if ( *a1 )
    {
      if ( *((_BYTE *)&RegPropertyTable + 16 * v9 + 12) )
      {
        v16 = (const WCHAR *)regValueNameForId((unsigned int)v9);
        Value = privateRegReadValue(*a1, v16, (__int64)a7, (__int64)&v21);
        if ( !Value )
        {
          if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
            goto LABEL_36;
          v17 = 15;
          goto LABEL_19;
        }
      }
    }
    if ( a1[2] )
    {
      if ( *((_BYTE *)&RegPropertyTable + 16 * v9 + 14) )
      {
        v18 = (const WCHAR *)regValueNameForId((unsigned int)v9);
        Value = privateRegReadValue(a1[2], v18, (__int64)a7, (__int64)&v21);
        if ( !Value )
        {
          if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
            goto LABEL_36;
          v17 = 16;
          goto LABEL_19;
        }
      }
    }
    a2 = a1[1];
    if ( !a2 )
      goto LABEL_36;
  }
  v19 = (const WCHAR *)regValueNameForId((unsigned int)v9);
  Value = privateRegReadValue(a2, v19, (__int64)a7, (__int64)&v21);
  if ( !Value )
  {
    if ( a1 && a2 == a1[1] )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        goto LABEL_36;
      v17 = 17;
    }
    else
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        goto LABEL_36;
      v17 = 18;
    }
LABEL_19:
    WPP_SF_(1035, v17, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids);
    goto LABEL_36;
  }
LABEL_33:
  if ( a5 == 4 )
    *(_DWORD *)a7 = *((_DWORD *)&RegPropertyTable + 4 * v9 + 2);
  else
    *a7 = 0;
LABEL_36:
  if ( a1 == v23 )
    Reg_CloseSession(a1);
  if ( hKey )
    RegCloseKey(hKey);
  if ( !Value )
  {
    if ( a5 == 4 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        return Value;
      WPP_SF_d(1035, 19, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids, *(unsigned int *)a7);
    }
    else if ( a5 == 1 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        return Value;
      WPP_SF_S(1035, 20, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids, *a7);
    }
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 21, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids, Value);
  return Value;
}

```

## disassembly

```asm
0x18007e1f0  push    rbp
0x18007e1f2  push    rbx
0x18007e1f3  push    rsi
0x18007e1f4  push    rdi
0x18007e1f5  push    r12
0x18007e1f7  push    r13
0x18007e1f9  push    r14
0x18007e1fb  push    r15
0x18007e1fd  lea     rbp, [rsp-7]
0x18007e202  sub     rsp, 98h
0x18007e209  mov     rax, cs:__security_cookie
0x18007e210  xor     rax, rsp
0x18007e213  mov     [rbp+3Fh+var_48], rax
0x18007e217  mov     r15, [rbp+3Fh+arg_30]
0x18007e21b  xor     eax, eax
0x18007e21d  xorps   xmm0, xmm0
0x18007e220  mov     [rbp+3Fh+var_50], rax
0x18007e224  movups  xmmword ptr [rbp+3Fh+var_60], xmm0
0x18007e228  mov     dword ptr [rbp+3Fh+var_70], eax
0x18007e22b  mov     rbx, r8
0x18007e22e  mov     [rbp+3Fh+hKey], rax
0x18007e232  mov     rsi, rdx
0x18007e235  mov     r14d, r9d
0x18007e238  mov     rdi, rcx
0x18007e23b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007e242  mov     r13d, dword ptr [rbp+3Fh+arg_28]
0x18007e246  mov     r12d, [rbp+3Fh+arg_20]
0x18007e24a  jz      short loc_18007E27F
0x18007e24c  mov     ecx, r14d
0x18007e24f  call    regValueNameForId
0x18007e254  mov     [rsp+0D0h+var_80], r15
0x18007e259  mov     r9, rdi
0x18007e25c  mov     [rsp+0D0h+var_88], r13d
0x18007e261  mov     [rsp+0D0h+var_90], r12d
0x18007e266  mov     [rsp+0D0h+var_98], rax
0x18007e26b  mov     [rsp+0D0h+var_A0], r14d
0x18007e270  mov     [rsp+0D0h+var_A8], rbx
0x18007e275  mov     [rsp+0D0h+phkResult], rdx
0x18007e27a  call    WPP_SF_qqSdSdDq
0x18007e27f  cmp     cs:g_fVelocityDisableInternalExports, 0
0x18007e286  jnz     short loc_18007E28D
0x18007e288  call    Reg_Init
0x18007e28d  mov     ecx, r14d
0x18007e290  call    regValueNameForId
0x18007e295  lea     rcx, RegPropertyTable
0x18007e29c  test    rax, rax
0x18007e29f  jnz     short loc_18007E2A9
0x18007e2a1  lea     ebx, [rax+57h]
0x18007e2a4  jmp     loc_18007E443
0x18007e2a9  test    rsi, rsi
0x18007e2ac  jz      short loc_18007E2EE
0x18007e2ae  test    rbx, rbx
0x18007e2b1  jz      loc_18007E3E0
0x18007e2b7  lea     rax, [rbp+3Fh+hKey]
0x18007e2bb  mov     r9d, 1; samDesired
0x18007e2c1  xor     r8d, r8d; ulOptions
0x18007e2c4  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18007e2c9  mov     rdx, rbx; lpSubKey
0x18007e2cc  mov     rcx, rsi; hKey
0x18007e2cf  call    cs:__imp_RegOpenKeyExW
0x18007e2d6  nop     dword ptr [rax+rax+00h]
0x18007e2db  mov     ebx, eax
0x18007e2dd  test    eax, eax
0x18007e2df  jnz     loc_18007E43C
0x18007e2e5  mov     rsi, [rbp+3Fh+hKey]
0x18007e2e9  jmp     loc_18007E3E0
0x18007e2ee  mov     ebx, 2
0x18007e2f3  test    rdi, rdi
0x18007e2f6  jnz     short loc_18007E316
0x18007e2f8  lea     rcx, [rbp+3Fh+var_60]; phkResult
0x18007e2fc  call    Reg_OpenSession
0x18007e301  lea     rcx, RegPropertyTable
0x18007e308  mov     ebx, eax
0x18007e30a  test    eax, eax
0x18007e30c  jnz     loc_18007E443
0x18007e312  lea     rdi, [rbp+3Fh+var_60]
0x18007e316  cmp     qword ptr [rdi], 0
0x18007e31a  jz      short loc_18007E37C
0x18007e31c  mov     rax, r14
0x18007e31f  add     rax, rax
0x18007e322  cmp     byte ptr [rcx+rax*8+0Ch], 0
0x18007e327  jz      short loc_18007E37C
0x18007e329  mov     ecx, r14d
0x18007e32c  call    regValueNameForId
0x18007e331  mov     rcx, [rdi]; hKey
0x18007e334  mov     rdx, rax; lpValueName
0x18007e337  lea     rax, [rbp+3Fh+var_70]
0x18007e33b  mov     r9d, r12d
0x18007e33e  mov     [rsp+0D0h+var_A8], rax; __int64
0x18007e343  mov     r8d, r13d
0x18007e346  mov     [rsp+0D0h+phkResult], r15; __int64
0x18007e34b  call    privateRegReadValue
0x18007e350  mov     ebx, eax
0x18007e352  test    eax, eax
0x18007e354  jnz     short loc_18007E37C
0x18007e356  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007e35d  jz      loc_18007E45F
0x18007e363  lea     edx, [rax+0Fh]
0x18007e366  mov     ecx, 40Bh
0x18007e36b  lea     r8, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids
0x18007e372  call    WPP_SF_
0x18007e377  jmp     loc_18007E45F
0x18007e37c  cmp     qword ptr [rdi+10h], 0
0x18007e381  jz      short loc_18007E3D7
0x18007e383  mov     rax, r14
0x18007e386  lea     rcx, RegPropertyTable
0x18007e38d  add     rax, rax
0x18007e390  cmp     byte ptr [rcx+rax*8+0Eh], 0
0x18007e395  jz      short loc_18007E3D7
0x18007e397  mov     ecx, r14d
0x18007e39a  call    regValueNameForId
0x18007e39f  mov     rcx, [rdi+10h]; hKey
0x18007e3a3  mov     rdx, rax; lpValueName
0x18007e3a6  lea     rax, [rbp+3Fh+var_70]
0x18007e3aa  mov     r9d, r12d
0x18007e3ad  mov     [rsp+0D0h+var_A8], rax; __int64
0x18007e3b2  mov     r8d, r13d
0x18007e3b5  mov     [rsp+0D0h+phkResult], r15; __int64
0x18007e3ba  call    privateRegReadValue
0x18007e3bf  mov     ebx, eax
0x18007e3c1  test    eax, eax
0x18007e3c3  jnz     short loc_18007E3D7
0x18007e3c5  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007e3cc  jz      loc_18007E45F
0x18007e3d2  lea     edx, [rax+10h]
0x18007e3d5  jmp     short loc_18007E366
0x18007e3d7  mov     rsi, [rdi+8]
0x18007e3db  test    rsi, rsi
0x18007e3de  jz      short loc_18007E45F
0x18007e3e0  mov     ecx, r14d
0x18007e3e3  call    regValueNameForId
0x18007e3e8  mov     rdx, rax; lpValueName
0x18007e3eb  mov     r9d, r12d
0x18007e3ee  lea     rax, [rbp+3Fh+var_70]
0x18007e3f2  mov     r8d, r13d
0x18007e3f5  mov     [rsp+0D0h+var_A8], rax; __int64
0x18007e3fa  mov     rcx, rsi; hKey
0x18007e3fd  mov     [rsp+0D0h+phkResult], r15; __int64
0x18007e402  call    privateRegReadValue
0x18007e407  mov     ebx, eax
0x18007e409  test    eax, eax
0x18007e40b  jnz     short loc_18007E43C
0x18007e40d  test    rdi, rdi
0x18007e410  jz      short loc_18007E429
0x18007e412  cmp     rsi, [rdi+8]
0x18007e416  jnz     short loc_18007E429
0x18007e418  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007e41f  jz      short loc_18007E45F
0x18007e421  lea     edx, [rax+11h]
0x18007e424  jmp     loc_18007E366
0x18007e429  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007e430  jz      short loc_18007E45F
0x18007e432  mov     edx, 12h
0x18007e437  jmp     loc_18007E366
0x18007e43c  lea     rcx, RegPropertyTable
0x18007e443  cmp     r12d, 4
0x18007e447  jnz     short loc_18007E458
0x18007e449  mov     rax, r14
0x18007e44c  add     rax, rax
0x18007e44f  mov     eax, [rcx+rax*8+8]
0x18007e453  mov     [r15], eax
0x18007e456  jmp     short loc_18007E45F
0x18007e458  mov     qword ptr [r15], 0
0x18007e45f  lea     rax, [rbp+3Fh+var_60]
0x18007e463  cmp     rdi, rax
0x18007e466  jnz     short loc_18007E470
0x18007e468  mov     rcx, rdi
0x18007e46b  call    Reg_CloseSession
0x18007e470  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18007e474  test    rcx, rcx
0x18007e477  jz      short loc_18007E485
0x18007e479  call    cs:__imp_RegCloseKey
0x18007e480  nop     dword ptr [rax+rax+00h]
0x18007e485  test    ebx, ebx
0x18007e487  jnz     short loc_18007E4D9
0x18007e489  cmp     r12d, 4
0x18007e48d  jnz     short loc_18007E4B1
0x18007e48f  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007e496  jz      short loc_18007E4FB
0x18007e498  mov     r9d, [r15]
0x18007e49b  lea     edx, [rbx+13h]
0x18007e49e  mov     ecx, 40Bh
0x18007e4a3  lea     r8, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids
0x18007e4aa  call    WPP_SF_d
0x18007e4af  jmp     short loc_18007E4D9
0x18007e4b1  cmp     r12d, 1
0x18007e4b5  jnz     short loc_18007E4D9
0x18007e4b7  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007e4be  jz      short loc_18007E4FB
0x18007e4c0  mov     r9, [r15]
0x18007e4c3  lea     edx, [r12+13h]
0x18007e4c8  mov     ecx, 40Bh
0x18007e4cd  lea     r8, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids
0x18007e4d4  call    WPP_SF_S
0x18007e4d9  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007e4e0  jz      short loc_18007E4FB
0x18007e4e2  mov     edx, 15h
0x18007e4e7  lea     r8, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids
0x18007e4ee  mov     ecx, 40Bh
0x18007e4f3  mov     r9d, ebx
0x18007e4f6  call    WPP_SF_d
0x18007e4fb  mov     eax, ebx
0x18007e4fd  mov     rcx, [rbp+3Fh+var_48]
0x18007e501  xor     rcx, rsp; StackCookie
0x18007e504  call    __security_check_cookie
0x18007e509  add     rsp, 98h
0x18007e510  pop     r15
0x18007e512  pop     r14
0x18007e514  pop     r13
0x18007e516  pop     r12
0x18007e518  pop     rdi
0x18007e519  pop     rsi
0x18007e51a  pop     rbx
0x18007e51b  pop     rbp
0x18007e51c  retn
```
