# DwmpReadColorizationParameters

- ea: `0x180001ce0`
- end: `0x180002106`
- name: `DwmpReadColorizationParameters`
- size: `1062`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001c10`

## callees

- `0x180001ce0`
- `0x18000352c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001d77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001dc0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001e19`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001e66`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001ebf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001f09`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001f53`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001d77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001dc0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001e19`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001e66`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001ebf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001f09`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001f53`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001d28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001d28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001faa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001faa`

## pseudocode

```c
__int64 __fastcall DwmpReadColorizationParameters(int *a1)
{
  int v1; // r13d
  LSTATUS v3; // eax
  signed int v4; // ebx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  int v7; // eax
  int v8; // eax
  HKEY v9; // rcx
  LSTATUS v10; // eax
  HKEY v11; // rcx
  LSTATUS v12; // eax
  signed int v13; // ebx
  HKEY v14; // rcx
  int v15; // eax
  int v16; // eax
  bool v17; // sf
  int v18; // eax
  HKEY v19; // rcx
  int v20; // eax
  bool v21; // sf
  int v22; // eax
  HKEY v23; // rcx
  LSTATUS v24; // eax
  bool v25; // zf
  unsigned int phkResult; // [rsp+20h] [rbp-10h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-8h]
  LPDWORD lpcbDataa; // [rsp+28h] [rbp-8h]
  LPDWORD lpcbDatab; // [rsp+28h] [rbp-8h]
  LPDWORD lpcbDatac; // [rsp+28h] [rbp-8h]
  LPDWORD lpcbDatad; // [rsp+28h] [rbp-8h]
  LPDWORD lpcbDatae; // [rsp+28h] [rbp-8h]
  LPDWORD lpcbDataf; // [rsp+28h] [rbp-8h]
  LPDWORD lpcbDatag; // [rsp+28h] [rbp-8h]
  int Data; // [rsp+70h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+50h] BYREF

  v1 = 0;
  hKey = 0;
  if ( !a1 )
  {
    v4 = -2147024809;
    phkResult = 129;
    goto LABEL_42;
  }
  v3 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\DWM", 0, 1u, &hKey);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 < 0 )
  {
    phkResult = 137;
LABEL_42:
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1800192D8, 2u, v4, phkResult, lpcbData);
    goto LABEL_38;
  }
  Data = 0;
  cbData = 4;
  v5 = RegQueryValueExW(hKey, L"ColorizationColor", 0, 0, (LPBYTE)&Data, &cbData);
  v4 = v5;
  if ( v5 > 0 )
    v4 = (unsigned __int16)v5 | 0x80070000;
  if ( v4 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019010, 2u, v4, 0x60u, lpcbDataa);
    phkResult = 152;
    goto LABEL_42;
  }
  v6 = hKey;
  *a1 = Data;
  Data = 0;
  cbData = 4;
  v7 = RegQueryValueExW(v6, L"ColorizationColorBalance", 0, 0, (LPBYTE)&Data, &cbData);
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
  if ( v7 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019010, 2u, v7, 0x60u, lpcbDatab);
    v8 = 27;
  }
  else
  {
    v8 = Data;
  }
  v9 = hKey;
  a1[2] = v8;
  Data = 0;
  cbData = 4;
  v10 = RegQueryValueExW(v9, L"ColorizationAfterglow", 0, 0, (LPBYTE)&Data, &cbData);
  v4 = v10;
  if ( v10 > 0 )
    v4 = (unsigned __int16)v10 | 0x80070000;
  if ( v4 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019010, 2u, v4, 0x60u, lpcbDatac);
    phkResult = 154;
    goto LABEL_42;
  }
  v11 = hKey;
  a1[1] = Data;
  Data = 0;
  cbData = 4;
  v12 = RegQueryValueExW(v11, L"ColorizationAfterglowBalance", 0, 0, (LPBYTE)&Data, &cbData);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( v13 < 0 )
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019010, 2u, v13, 0x60u, lpcbDatad);
  else
    v1 = Data;
  v14 = hKey;
  v15 = 0;
  cbData = 4;
  if ( v13 >= 0 )
    v15 = v1;
  a1[3] = v15;
  Data = 0;
  v16 = RegQueryValueExW(v14, L"ColorizationBlurBalance", 0, 0, (LPBYTE)&Data, &cbData);
  v17 = v16 < 0;
  if ( v16 > 0 )
  {
    v16 = (unsigned __int16)v16 | 0x80070000;
    v17 = v16 < 0;
  }
  if ( v17 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019010, 2u, v16, 0x60u, lpcbDatae);
    v18 = 73;
  }
  else
  {
    v18 = Data;
  }
  v19 = hKey;
  a1[4] = v18;
  Data = 0;
  cbData = 4;
  v20 = RegQueryValueExW(v19, L"EnableWindowColorization", 0, 0, (LPBYTE)&Data, &cbData);
  v21 = v20 < 0;
  if ( v20 > 0 )
  {
    v20 = (unsigned __int16)v20 | 0x80070000;
    v21 = v20 < 0;
  }
  if ( v21 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019010, 2u, v20, 0x60u, lpcbDataf);
    v22 = 1;
  }
  else
  {
    v22 = Data;
  }
  v23 = hKey;
  a1[5] = v22;
  Data = 0;
  cbData = 4;
  v24 = RegQueryValueExW(v23, L"ColorizationGlassAttribute", 0, 0, (LPBYTE)&Data, &cbData);
  v4 = v24;
  if ( v24 > 0 )
    v4 = (unsigned __int16)v24 | 0x80070000;
  if ( v4 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019010, 2u, v4, 0x60u, lpcbDatag);
    phkResult = 158;
    goto LABEL_42;
  }
  v25 = a1[5] == 0;
  a1[6] = Data;
  a1[5] = !v25;
  if ( (unsigned int)a1[2] > 0x64 )
    a1[2] = 27;
  if ( (unsigned int)a1[3] > 0x64 )
    a1[3] = 0;
  if ( (unsigned int)a1[4] > 0x64 )
    a1[4] = 73;
LABEL_38:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001ce0  mov     [rsp-38h+arg_18], rbx
0x180001ce5  push    rbp
0x180001ce6  push    rsi
0x180001ce7  push    rdi
0x180001ce8  push    r12
0x180001cea  push    r13
0x180001cec  push    r14
0x180001cee  push    r15
0x180001cf0  mov     rbp, rsp
0x180001cf3  sub     rsp, 30h
0x180001cf7  xor     r13d, r13d
0x180001cfa  mov     rsi, rcx
0x180001cfd  mov     [rbp+hKey], r13
0x180001d01  test    rcx, rcx
0x180001d04  jz      loc_180001FED
0x180001d0a  lea     rax, [rbp+hKey]
0x180001d0e  xor     r8d, r8d; ulOptions
0x180001d11  lea     r9d, [r13+1]; samDesired
0x180001d15  mov     [rsp+30h+phkResult], rax; phkResult
0x180001d1a  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\DWM"
0x180001d21  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180001d28  call    cs:__imp_RegOpenKeyExW
0x180001d2e  mov     ebx, eax
0x180001d30  mov     r14d, 80070000h
0x180001d36  test    eax, eax
0x180001d38  jle     short loc_180001D40
0x180001d3a  movzx   ebx, ax
0x180001d3d  or      ebx, r14d
0x180001d40  test    ebx, ebx
0x180001d42  js      loc_180001FCA
0x180001d48  mov     rcx, [rbp+hKey]; hKey
0x180001d4c  lea     rax, [rbp+cbData]
0x180001d50  mov     [rsp+30h+lpcbData], rax; void *
0x180001d55  lea     rdx, ValueName; "ColorizationColor"
0x180001d5c  lea     rax, [rbp+Data]
0x180001d60  mov     [rbp+Data], r13d
0x180001d64  mov     edi, 4
0x180001d69  mov     [rsp+30h+phkResult], rax; lpData
0x180001d6e  xor     r9d, r9d; lpType
0x180001d71  mov     [rbp+cbData], edi
0x180001d74  xor     r8d, r8d; lpReserved
0x180001d77  call    cs:__imp_RegQueryValueExW
0x180001d7d  mov     ebx, eax
0x180001d7f  test    eax, eax
0x180001d81  jle     short loc_180001D89
0x180001d83  movzx   ebx, ax
0x180001d86  or      ebx, r14d
0x180001d89  test    ebx, ebx
0x180001d8b  js      loc_1800020B3
0x180001d91  mov     eax, [rbp+Data]
0x180001d94  lea     rdx, aColorizationco_0; "ColorizationColorBalance"
0x180001d9b  mov     rcx, [rbp+hKey]; hKey
0x180001d9f  xor     r9d, r9d; lpType
0x180001da2  mov     [rsi], eax
0x180001da4  xor     r8d, r8d; lpReserved
0x180001da7  lea     rax, [rbp+cbData]
0x180001dab  mov     [rbp+Data], r13d
0x180001daf  mov     [rsp+30h+lpcbData], rax; void *
0x180001db4  lea     rax, [rbp+Data]
0x180001db8  mov     [rsp+30h+phkResult], rax; lpData
0x180001dbd  mov     [rbp+cbData], edi
0x180001dc0  call    cs:__imp_RegQueryValueExW
0x180001dc6  test    eax, eax
0x180001dc8  jle     short loc_180001DD0
0x180001dca  movzx   eax, ax
0x180001dcd  or      eax, r14d
0x180001dd0  lea     r12, qword_180019010
0x180001dd7  mov     r14d, 2
0x180001ddd  lea     r15d, [r14+5Eh]
0x180001de1  test    eax, eax
0x180001de3  js      loc_180001FFC
0x180001de9  mov     eax, [rbp+Data]
0x180001dec  mov     rcx, [rbp+hKey]; hKey
0x180001df0  lea     rdx, aColorizationaf_0; "ColorizationAfterglow"
0x180001df7  mov     [rsi+8], eax
0x180001dfa  xor     r9d, r9d; lpType
0x180001dfd  lea     rax, [rbp+cbData]
0x180001e01  mov     [rbp+Data], r13d
0x180001e05  mov     [rsp+30h+lpcbData], rax; void *
0x180001e0a  xor     r8d, r8d; lpReserved
0x180001e0d  lea     rax, [rbp+Data]
0x180001e11  mov     [rbp+cbData], edi
0x180001e14  mov     [rsp+30h+phkResult], rax; lpData
0x180001e19  call    cs:__imp_RegQueryValueExW
0x180001e1f  mov     ebx, eax
0x180001e21  test    eax, eax
0x180001e23  jle     short loc_180001E2E
0x180001e25  movzx   ebx, ax
0x180001e28  or      ebx, 80070000h
0x180001e2e  test    ebx, ebx
0x180001e30  js      loc_1800020E7
0x180001e36  mov     eax, [rbp+Data]
0x180001e39  lea     rdx, aColorizationaf; "ColorizationAfterglowBalance"
0x180001e40  mov     rcx, [rbp+hKey]; hKey
0x180001e44  xor     r9d, r9d; lpType
0x180001e47  mov     [rsi+4], eax
0x180001e4a  xor     r8d, r8d; lpReserved
0x180001e4d  lea     rax, [rbp+cbData]
0x180001e51  mov     [rbp+Data], r13d
0x180001e55  mov     [rsp+30h+lpcbData], rax; void *
0x180001e5a  lea     rax, [rbp+Data]
0x180001e5e  mov     [rsp+30h+phkResult], rax; lpData
0x180001e63  mov     [rbp+cbData], edi
0x180001e66  call    cs:__imp_RegQueryValueExW
0x180001e6c  mov     ebx, eax
0x180001e6e  test    eax, eax
0x180001e70  jle     short loc_180001E7B
0x180001e72  movzx   ebx, ax
0x180001e75  or      ebx, 80070000h
0x180001e7b  test    ebx, ebx
0x180001e7d  js      loc_18000201B
0x180001e83  mov     r13d, [rbp+Data]
0x180001e87  mov     rcx, [rbp+hKey]; hKey
0x180001e8b  lea     rdx, aColorizationbl; "ColorizationBlurBalance"
0x180001e92  xor     eax, eax
0x180001e94  mov     [rbp+cbData], edi
0x180001e97  test    ebx, ebx
0x180001e99  cmovns  eax, r13d
0x180001e9d  xor     r13d, r13d
0x180001ea0  mov     [rsi+0Ch], eax
0x180001ea3  xor     r9d, r9d; lpType
0x180001ea6  lea     rax, [rbp+cbData]
0x180001eaa  mov     [rbp+Data], r13d
0x180001eae  mov     [rsp+30h+lpcbData], rax; void *
0x180001eb3  xor     r8d, r8d; lpReserved
0x180001eb6  lea     rax, [rbp+Data]
0x180001eba  mov     [rsp+30h+phkResult], rax; lpData
0x180001ebf  call    cs:__imp_RegQueryValueExW
0x180001ec5  test    eax, eax
0x180001ec7  jle     short loc_180001ED3
0x180001ec9  movzx   eax, ax
0x180001ecc  or      eax, 80070000h
0x180001ed1  test    eax, eax
0x180001ed3  js      loc_180002035
0x180001ed9  mov     eax, [rbp+Data]
0x180001edc  mov     rcx, [rbp+hKey]; hKey
0x180001ee0  lea     rdx, aEnablewindowco; "EnableWindowColorization"
0x180001ee7  mov     [rsi+10h], eax
0x180001eea  xor     r9d, r9d; lpType
0x180001eed  lea     rax, [rbp+cbData]
0x180001ef1  mov     [rbp+Data], r13d
0x180001ef5  mov     [rsp+30h+lpcbData], rax; void *
0x180001efa  xor     r8d, r8d; lpReserved
0x180001efd  lea     rax, [rbp+Data]
0x180001f01  mov     [rbp+cbData], edi
0x180001f04  mov     [rsp+30h+phkResult], rax; lpData
0x180001f09  call    cs:__imp_RegQueryValueExW
0x180001f0f  test    eax, eax
0x180001f11  jle     short loc_180001F1D
0x180001f13  movzx   eax, ax
0x180001f16  or      eax, 80070000h
0x180001f1b  test    eax, eax
0x180001f1d  js      loc_180002054
0x180001f23  mov     eax, [rbp+Data]
0x180001f26  mov     rcx, [rbp+hKey]; hKey
0x180001f2a  lea     rdx, aColorizationgl; "ColorizationGlassAttribute"
0x180001f31  mov     [rsi+14h], eax
0x180001f34  xor     r9d, r9d; lpType
0x180001f37  lea     rax, [rbp+cbData]
0x180001f3b  mov     [rbp+Data], r13d
0x180001f3f  mov     [rsp+30h+lpcbData], rax; void *
0x180001f44  xor     r8d, r8d; lpReserved
0x180001f47  lea     rax, [rbp+Data]
0x180001f4b  mov     [rbp+cbData], edi
0x180001f4e  mov     [rsp+30h+phkResult], rax; lpData
0x180001f53  call    cs:__imp_RegQueryValueExW
0x180001f59  mov     ebx, eax
0x180001f5b  test    eax, eax
0x180001f5d  jle     short loc_180001F68
0x180001f5f  movzx   ebx, ax
0x180001f62  or      ebx, 80070000h
0x180001f68  test    ebx, ebx
0x180001f6a  js      loc_180002094
0x180001f70  mov     eax, [rbp+Data]
0x180001f73  cmp     [rsi+14h], r13d
0x180001f77  mov     [rsi+18h], eax
0x180001f7a  mov     eax, r13d
0x180001f7d  setnz   al
0x180001f80  mov     [rsi+14h], eax
0x180001f83  cmp     dword ptr [rsi+8], 64h ; 'd'
0x180001f87  ja      loc_180002073
0x180001f8d  cmp     dword ptr [rsi+0Ch], 64h ; 'd'
0x180001f91  ja      loc_18000207F
0x180001f97  cmp     dword ptr [rsi+10h], 64h ; 'd'
0x180001f9b  ja      loc_180002088
0x180001fa1  mov     rcx, [rbp+hKey]; hKey
0x180001fa5  test    rcx, rcx
0x180001fa8  jz      short loc_180001FB0
0x180001faa  call    cs:__imp_RegCloseKey
0x180001fb0  mov     eax, ebx
0x180001fb2  mov     rbx, [rsp+30h+arg_18]
0x180001fba  add     rsp, 30h
0x180001fbe  pop     r15
0x180001fc0  pop     r14
0x180001fc2  pop     r13
0x180001fc4  pop     r12
0x180001fc6  pop     rdi
0x180001fc7  pop     rsi
0x180001fc8  pop     rbp
0x180001fc9  retn
0x180001fca  mov     dword ptr [rsp+30h+phkResult], 89h; unsigned int
0x180001fd2  mov     r8d, 2; unsigned int
0x180001fd8  lea     ecx, [r8+2]; unsigned int
0x180001fdc  mov     r9d, ebx; int
0x180001fdf  lea     rdx, qword_1800192D8; int *
0x180001fe6  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180001feb  jmp     short loc_180001FA1
0x180001fed  mov     ebx, 80070057h
0x180001ff2  mov     dword ptr [rsp+30h+phkResult], 81h
0x180001ffa  jmp     short loc_180001FD2
0x180001ffc  mov     r9d, eax; int
0x180001fff  mov     dword ptr [rsp+30h+phkResult], r15d; unsigned int
0x180002004  mov     r8d, r14d; unsigned int
0x180002007  mov     rdx, r12; int *
0x18000200a  mov     ecx, edi; unsigned int
0x18000200c  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180002011  mov     eax, 1Bh
0x180002016  jmp     loc_180001DEC
0x18000201b  mov     r9d, ebx; int
0x18000201e  mov     dword ptr [rsp+30h+phkResult], r15d; unsigned int
0x180002023  mov     r8d, r14d; unsigned int
0x180002026  mov     rdx, r12; int *
0x180002029  mov     ecx, edi; unsigned int
0x18000202b  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180002030  jmp     loc_180001E87
0x180002035  mov     r9d, eax; int
0x180002038  mov     dword ptr [rsp+30h+phkResult], r15d; unsigned int
0x18000203d  mov     r8d, r14d; unsigned int
0x180002040  mov     rdx, r12; int *
0x180002043  mov     ecx, edi; unsigned int
0x180002045  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18000204a  mov     eax, 49h ; 'I'
0x18000204f  jmp     loc_180001EDC
0x180002054  mov     r9d, eax; int
0x180002057  mov     dword ptr [rsp+30h+phkResult], r15d; unsigned int
0x18000205c  mov     r8d, r14d; unsigned int
0x18000205f  mov     rdx, r12; int *
0x180002062  mov     ecx, edi; unsigned int
0x180002064  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180002069  mov     eax, 1
0x18000206e  jmp     loc_180001F26
0x180002073  mov     dword ptr [rsi+8], 1Bh
0x18000207a  jmp     loc_180001F8D
0x18000207f  mov     [rsi+0Ch], r13d
0x180002083  jmp     loc_180001F97
0x180002088  mov     dword ptr [rsi+10h], 49h ; 'I'
0x18000208f  jmp     loc_180001FA1
0x180002094  mov     r9d, ebx; int
0x180002097  mov     dword ptr [rsp+30h+phkResult], r15d; unsigned int
0x18000209c  mov     r8d, r14d; unsigned int
0x18000209f  mov     rdx, r12; int *
0x1800020a2  mov     ecx, edi; unsigned int
0x1800020a4  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800020a9  mov     dword ptr [rsp+30h+phkResult], 9Eh
0x1800020b1  jmp     short loc_1800020DD
0x1800020b3  mov     r14d, 2
0x1800020b9  mov     dword ptr [rsp+30h+phkResult], 60h ; '`'; unsigned int
0x1800020c1  mov     r8d, r14d; unsigned int
0x1800020c4  lea     rdx, qword_180019010; int *
0x1800020cb  mov     r9d, ebx; int
0x1800020ce  mov     ecx, edi; unsigned int
0x1800020d0  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800020d5  mov     dword ptr [rsp+30h+phkResult], 98h
0x1800020dd  mov     r8d, r14d
0x1800020e0  mov     ecx, edi
0x1800020e2  jmp     loc_180001FDC
0x1800020e7  mov     r9d, ebx; int
0x1800020ea  mov     dword ptr [rsp+30h+phkResult], r15d; unsigned int
0x1800020ef  mov     r8d, r14d; unsigned int
0x1800020f2  mov     rdx, r12; int *
0x1800020f5  mov     ecx, edi; unsigned int
0x1800020f7  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800020fc  mov     dword ptr [rsp+30h+phkResult], 9Ah
0x180002104  jmp     short loc_1800020DD
```
