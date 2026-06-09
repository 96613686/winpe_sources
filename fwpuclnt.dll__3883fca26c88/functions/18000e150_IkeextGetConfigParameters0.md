# IkeextGetConfigParameters0

- ea: `0x18000e150`
- end: `0x18000e36e`
- name: `IkeextGetConfigParameters0`
- size: `542`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task`

## callees

- `0x1800030a8`
- `0x1800034e0`
- `0x180004540`
- `0x180007e38`
- `0x18000e150`
- `0x180012bd0`
- `0x1800496e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e1d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e1d8`

## string_xrefs

- `0x18000e1f4`: `RegOpenKeyExW`
- `0x18000e18b`: `IkeextGetConfigParameters0`
- `0x18000e1ae`: `SYSTEM\CurrentControlSet\Services\IKEEXT\Parameters`
- `0x18000e20c`: `BfeRegOpenKey`

## pseudocode

```c
__int64 __fastcall IkeextGetConfigParameters0(__int64 a1)
{
  HKEY v2; // rbx
  __int64 DWord; // rdi
  unsigned int v4; // eax
  int v5; // edx
  __int64 v6; // rcx
  int v7; // r9d
  __int64 v8; // rax
  int v9; // edx
  int v10; // r9d
  int v11; // edx
  int v12; // r9d
  int v13; // edx
  int v14; // r9d
  int v15; // edx
  int v16; // r9d
  int v18; // [rsp+30h] [rbp-20h] BYREF
  int v19; // [rsp+34h] [rbp-1Ch] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-18h] BYREF

  v19 = 0;
  v2 = 0;
  if ( a1 )
  {
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 4;
    *(_DWORD *)(a1 + 16) = 0;
    phkResult = 0;
    v18 = 0;
    v4 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\IKEEXT\\Parameters",
           0,
           1u,
           &phkResult);
    if ( v4 == 2 )
    {
      DWord = 0;
    }
    else if ( v4 )
    {
      v8 = WfpReportSysErrorAsWinError(v6, "RegOpenKeyExW", v4);
      DWord = v8;
      if ( v8 )
        WfpReportError(v8, "BfeRegOpenKey");
    }
    else
    {
      v2 = phkResult;
      v18 = 1;
      DWord = BfeRegQueryDWord(
                (_DWORD)phkResult,
                v5,
                (unsigned int)L"EnableDOSProtect",
                v7,
                (__int64)&v19,
                (__int64)&v18);
      if ( !DWord )
      {
        if ( v18 )
          *(_DWORD *)a1 = v19;
        DWord = BfeRegQueryDWord((_DWORD)v2, v9, (unsigned int)L"NLBSFlags", v10, (__int64)&v19, (__int64)&v18);
        if ( !DWord )
        {
          if ( v18 )
            *(_DWORD *)(a1 + 12) = v19;
          DWord = BfeRegQueryDWord((_DWORD)v2, v11, (unsigned int)L"DebugLevel", v12, (__int64)&v19, (__int64)&v18);
          if ( !DWord )
          {
            if ( v18 )
              *(_DWORD *)(a1 + 8) = v19;
            DWord = BfeRegQueryDWord((_DWORD)v2, v13, (unsigned int)L"EnableLogging", v14, (__int64)&v19, (__int64)&v18);
            if ( !DWord )
            {
              if ( v18 )
                *(_DWORD *)(a1 + 4) = v19;
              DWord = BfeRegQueryDWord((_DWORD)v2, v15, (unsigned int)L"IKEFlags", v16, (__int64)&v19, (__int64)&v18);
              if ( !DWord && v18 )
                *(_DWORD *)(a1 + 16) = v19;
            }
          }
        }
      }
    }
  }
  else
  {
    DWord = WfpReportSysErrorAsWinError(0, "IkeextGetConfigParameters0", 2150760476LL);
  }
  BfeRegCloseKey(v2);
  return WfpErrorToFwpErr(DWord);
}

```

## disassembly

```asm
0x18000e150  mov     [rsp-18h+arg_8], rbx
0x18000e155  mov     [rsp-18h+arg_10], rsi
0x18000e15a  push    rbp
0x18000e15b  push    rdi
0x18000e15c  push    r14
0x18000e15e  mov     rbp, rsp
0x18000e161  sub     rsp, 50h
0x18000e165  mov     rax, cs:__security_cookie
0x18000e16c  xor     rax, rsp
0x18000e16f  mov     [rbp+var_10], rax
0x18000e173  xor     r14d, r14d
0x18000e176  mov     rsi, rcx
0x18000e179  mov     [rbp+var_1C], r14d
0x18000e17d  mov     ebx, r14d
0x18000e180  test    rcx, rcx
0x18000e183  jnz     short loc_18000E19F
0x18000e185  mov     r8d, 8032001Ch
0x18000e18b  lea     rdx, aIkeextgetconfi_0; "IkeextGetConfigParameters0"
0x18000e192  call    WfpReportSysErrorAsWinError
0x18000e197  mov     rdi, rax
0x18000e19a  jmp     loc_18000E33C
0x18000e19f  mov     [rcx], r14
0x18000e1a2  lea     rax, [rbp+var_18]
0x18000e1a6  mov     qword ptr [rcx+8], 4
0x18000e1ae  lea     rdx, FWPP_OAKLEY_KEY; "SYSTEM\\CurrentControlSet\\Services\\IK"...
0x18000e1b5  mov     [rcx+10h], r14d
0x18000e1b9  mov     edi, 1
0x18000e1be  mov     r9d, edi; samDesired
0x18000e1c1  mov     [rbp+var_18], r14
0x18000e1c5  xor     r8d, r8d; ulOptions
0x18000e1c8  mov     [rbp+var_20], r14d
0x18000e1cc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e1d3  mov     [rsp+50h+phkResult], rax; phkResult
0x18000e1d8  call    cs:__imp_RegOpenKeyExW
0x18000e1df  nop     dword ptr [rax+rax+00h]
0x18000e1e4  cmp     eax, 2
0x18000e1e7  jz      loc_18000E339
0x18000e1ed  test    eax, eax
0x18000e1ef  jz      short loc_18000E220
0x18000e1f1  mov     r8d, eax
0x18000e1f4  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18000e1fb  call    WfpReportSysErrorAsWinError
0x18000e200  mov     rdi, rax
0x18000e203  test    rax, rax
0x18000e206  jz      loc_18000E33C
0x18000e20c  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x18000e213  mov     rcx, rax
0x18000e216  call    WfpReportError
0x18000e21b  jmp     loc_18000E33C
0x18000e220  mov     rbx, [rbp+var_18]
0x18000e224  lea     rax, [rbp+var_20]
0x18000e228  mov     [rsp+50h+var_28], rax
0x18000e22d  lea     r8, aEnabledosprote; "EnableDOSProtect"
0x18000e234  lea     rax, [rbp+var_1C]
0x18000e238  mov     [rbp+var_20], edi
0x18000e23b  mov     rcx, rbx
0x18000e23e  mov     [rsp+50h+phkResult], rax
0x18000e243  call    BfeRegQueryDWord
0x18000e248  mov     rdi, rax
0x18000e24b  test    rax, rax
0x18000e24e  jnz     loc_18000E33C
0x18000e254  cmp     [rbp+var_20], r14d
0x18000e258  jz      short loc_18000E25F
0x18000e25a  mov     eax, [rbp+var_1C]
0x18000e25d  mov     [rsi], eax
0x18000e25f  lea     rax, [rbp+var_20]
0x18000e263  mov     rcx, rbx
0x18000e266  mov     [rsp+50h+var_28], rax
0x18000e26b  lea     r8, aNlbsflags; "NLBSFlags"
0x18000e272  lea     rax, [rbp+var_1C]
0x18000e276  mov     [rsp+50h+phkResult], rax
0x18000e27b  call    BfeRegQueryDWord
0x18000e280  mov     rdi, rax
0x18000e283  test    rax, rax
0x18000e286  jnz     loc_18000E33C
0x18000e28c  cmp     [rbp+var_20], r14d
0x18000e290  jz      short loc_18000E298
0x18000e292  mov     eax, [rbp+var_1C]
0x18000e295  mov     [rsi+0Ch], eax
0x18000e298  lea     rax, [rbp+var_20]
0x18000e29c  mov     rcx, rbx
0x18000e29f  mov     [rsp+50h+var_28], rax
0x18000e2a4  lea     r8, aDebuglevel; "DebugLevel"
0x18000e2ab  lea     rax, [rbp+var_1C]
0x18000e2af  mov     [rsp+50h+phkResult], rax
0x18000e2b4  call    BfeRegQueryDWord
0x18000e2b9  mov     rdi, rax
0x18000e2bc  test    rax, rax
0x18000e2bf  jnz     short loc_18000E33C
0x18000e2c1  cmp     [rbp+var_20], r14d
0x18000e2c5  jz      short loc_18000E2CD
0x18000e2c7  mov     eax, [rbp+var_1C]
0x18000e2ca  mov     [rsi+8], eax
0x18000e2cd  lea     rax, [rbp+var_20]
0x18000e2d1  mov     rcx, rbx
0x18000e2d4  mov     [rsp+50h+var_28], rax
0x18000e2d9  lea     r8, aEnablelogging; "EnableLogging"
0x18000e2e0  lea     rax, [rbp+var_1C]
0x18000e2e4  mov     [rsp+50h+phkResult], rax
0x18000e2e9  call    BfeRegQueryDWord
0x18000e2ee  mov     rdi, rax
0x18000e2f1  test    rax, rax
0x18000e2f4  jnz     short loc_18000E33C
0x18000e2f6  cmp     [rbp+var_20], r14d
0x18000e2fa  jz      short loc_18000E302
0x18000e2fc  mov     eax, [rbp+var_1C]
0x18000e2ff  mov     [rsi+4], eax
0x18000e302  lea     rax, [rbp+var_20]
0x18000e306  mov     rcx, rbx
0x18000e309  mov     [rsp+50h+var_28], rax
0x18000e30e  lea     r8, aIkeflags; "IKEFlags"
0x18000e315  lea     rax, [rbp+var_1C]
0x18000e319  mov     [rsp+50h+phkResult], rax
0x18000e31e  call    BfeRegQueryDWord
0x18000e323  mov     rdi, rax
0x18000e326  test    rax, rax
0x18000e329  jnz     short loc_18000E33C
0x18000e32b  cmp     [rbp+var_20], r14d
0x18000e32f  jz      short loc_18000E33C
0x18000e331  mov     eax, [rbp+var_1C]
0x18000e334  mov     [rsi+10h], eax
0x18000e337  jmp     short loc_18000E33C
0x18000e339  mov     rdi, r14
0x18000e33c  mov     rcx, rbx
0x18000e33f  call    BfeRegCloseKey
0x18000e344  mov     rcx, rdi
0x18000e347  call    WfpErrorToFwpErr
0x18000e34c  mov     rcx, [rbp+var_10]
0x18000e350  xor     rcx, rsp; StackCookie
0x18000e353  call    __security_check_cookie
0x18000e358  lea     r11, [rsp+50h+var_s0]
0x18000e35d  mov     rbx, [r11+28h]
0x18000e361  mov     rsi, [r11+30h]
0x18000e365  mov     rsp, r11
0x18000e368  pop     r14
0x18000e36a  pop     rdi
0x18000e36b  pop     rbp
0x18000e36c  retn
```
