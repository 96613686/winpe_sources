# GetImagePathInReg

- ea: `0x18000204c`
- end: `0x18000225c`
- name: `GetImagePathInReg`
- size: `528`
- prototype: `__int64 __fastcall(__int64, __int64, BYTE **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001d14`

## callees

- `0x18000204c`
- `0x180002d20`
- `0x180003cf0`
- `0x180004470`
- `0x180006280`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800020c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002115`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800020c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002115`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800021ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800021ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002097`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002097`

## string_xrefs

- `0x1800020c0`: `NgcPopKeyServiceImage`
- `0x18000210e`: `NgcPopKeyServiceImage`
- `0x18000216b`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`
- `0x1800021c1`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`
- `0x18000220f`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`
- `0x18000222d`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`

## pseudocode

```c
__int64 __fastcall GetImagePathInReg(__int64 a1, __int64 a2, BYTE **a3)
{
  BYTE *lpData; // rdi
  unsigned int v5; // eax
  __int64 v6; // rcx
  unsigned int v7; // eax
  int v8; // r8d
  LSTATUS v9; // r8d
  unsigned int v10; // ebx
  __int64 v12; // r9
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  int v14; // [rsp+64h] [rbp+24h]
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  int v16; // [rsp+6Ch] [rbp+2Ch]
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  v16 = HIDWORD(a2);
  v14 = HIDWORD(a1);
  hKey = 0;
  lpData = 0;
  cbData = 0;
  Type = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\Ngc", 0, 0x20019u, &hKey);
  v6 = v5;
  if ( v5 )
  {
    v12 = 96;
LABEL_21:
    DebugTraceError(v6, "lResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c", v12);
LABEL_15:
    v10 = -2146893794;
    goto LABEL_7;
  }
  v7 = RegQueryValueExW(hKey, L"NgcPopKeyServiceImage", 0, &Type, 0, &cbData);
  v6 = v7;
  if ( v7 )
  {
    v12 = 109;
    goto LABEL_21;
  }
  if ( Type == 2 )
  {
    lpData = (BYTE *)MSCryptAlloc(cbData);
    if ( lpData )
    {
      v9 = RegQueryValueExW(hKey, L"NgcPopKeyServiceImage", 0, &Type, lpData, &cbData);
      if ( !v9 )
      {
        v10 = 0;
        *a3 = lpData;
        lpData = 0;
        goto LABEL_7;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)WPP_GLOBAL_Control,
          v9,
          (unsigned int)"lResult",
          v9,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
          137);
      goto LABEL_15;
    }
    v10 = -2146893810;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        v8,
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
        125);
  }
  else
  {
    v10 = -2146893794;
    DebugTraceError(2148073502LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c", 117);
  }
LABEL_7:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( lpData )
    MSCryptFree(lpData);
  return v10;
}

```

## disassembly

```asm
0x18000204c  mov     r11, rsp
0x18000204f  mov     [r11+18h], rbx
0x180002053  mov     [r11+10h], rdx
0x180002057  mov     [r11+8], rcx
0x18000205b  push    rbp
0x18000205c  push    rsi
0x18000205d  push    rdi
0x18000205e  mov     rbp, rsp
0x180002061  sub     rsp, 40h
0x180002065  mov     rsi, r8
0x180002068  mov     [rbp+hKey], 0
0x180002070  xor     edi, edi
0x180002072  lea     rax, [rbp+hKey]
0x180002076  xor     r8d, r8d; ulOptions
0x180002079  mov     [rbp+cbData], edi
0x18000207c  mov     r9d, 20019h; samDesired
0x180002082  mov     [rbp+Type], edi
0x180002085  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x18000208c  mov     [r11-38h], rax
0x180002090  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002097  call    cs:__imp_RegOpenKeyExW
0x18000209d  mov     ecx, eax
0x18000209f  test    eax, eax
0x1800020a1  jnz     loc_180002201
0x1800020a7  mov     rcx, [rbp+hKey]; hKey
0x1800020ab  lea     rax, [rbp+cbData]
0x1800020af  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800020b4  lea     r9, [rbp+Type]; lpType
0x1800020b8  xor     r8d, r8d; lpReserved
0x1800020bb  mov     [rsp+40h+lpData], rdi; lpData
0x1800020c0  lea     rdx, ValueName; "NgcPopKeyServiceImage"
0x1800020c7  call    cs:__imp_RegQueryValueExW
0x1800020cd  mov     ecx, eax
0x1800020cf  test    eax, eax
0x1800020d1  jnz     loc_180002209
0x1800020d7  cmp     [rbp+Type], 2
0x1800020db  jnz     loc_180002227
0x1800020e1  mov     ecx, [rbp+cbData]
0x1800020e4  call    MSCryptAlloc
0x1800020e9  mov     rdi, rax
0x1800020ec  test    rax, rax
0x1800020ef  jz      loc_180002197
0x1800020f5  mov     rcx, [rbp+hKey]; hKey
0x1800020f9  lea     rax, [rbp+cbData]
0x1800020fd  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180002102  lea     r9, [rbp+Type]; lpType
0x180002106  xor     r8d, r8d; lpReserved
0x180002109  mov     [rsp+40h+lpData], rdi; lpData
0x18000210e  lea     rdx, ValueName; "NgcPopKeyServiceImage"
0x180002115  call    cs:__imp_RegQueryValueExW
0x18000211b  mov     r8d, eax
0x18000211e  test    eax, eax
0x180002120  jnz     short loc_18000214E
0x180002122  xor     ebx, ebx
0x180002124  mov     [rsi], rdi
0x180002127  xor     edi, edi
0x180002129  mov     rcx, [rbp+hKey]; hKey
0x18000212d  test    rcx, rcx
0x180002130  jnz     loc_1800021EE
0x180002136  test    rdi, rdi
0x180002139  jnz     loc_18000224F
0x18000213f  mov     eax, ebx
0x180002141  mov     rbx, [rsp+40h+arg_10]
0x180002146  add     rsp, 40h
0x18000214a  pop     rdi
0x18000214b  pop     rsi
0x18000214c  pop     rbp
0x18000214d  retn
0x18000214e  mov     rdx, cs:WPP_GLOBAL_Control
0x180002155  lea     rcx, WPP_GLOBAL_Control
0x18000215c  cmp     rdx, rcx
0x18000215f  jz      short loc_180002190
0x180002161  test    byte ptr [rdx+1Ch], 1
0x180002165  jz      short loc_180002190
0x180002167  mov     rcx, [rdx+10h]
0x18000216b  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002172  mov     [rsp+40h+var_10], 89h
0x18000217a  lea     r9, aLresult; "lResult"
0x180002181  mov     [rsp+40h+lpcbData], rax
0x180002186  mov     dword ptr [rsp+40h+lpData], r8d
0x18000218b  call    WPP_SF_sDsd
0x180002190  mov     ebx, 8009001Eh
0x180002195  jmp     short loc_180002129
0x180002197  mov     ebx, 8009000Eh
0x18000219c  mov     rdx, cs:WPP_GLOBAL_Control
0x1800021a3  lea     rcx, WPP_GLOBAL_Control
0x1800021aa  cmp     rdx, rcx
0x1800021ad  jz      loc_180002129
0x1800021b3  test    byte ptr [rdx+1Ch], 1
0x1800021b7  jz      loc_180002129
0x1800021bd  mov     rcx, [rdx+10h]
0x1800021c1  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800021c8  mov     [rsp+40h+var_10], 7Dh ; '}'
0x1800021d0  lea     r9, aStatus; "Status"
0x1800021d7  mov     [rsp+40h+lpcbData], rax
0x1800021dc  mov     dword ptr [rsp+40h+lpData], 8009000Eh
0x1800021e4  call    WPP_SF_sDsd
0x1800021e9  jmp     loc_180002129
0x1800021ee  call    cs:__imp_RegCloseKey
0x1800021f4  mov     [rbp+hKey], 0
0x1800021fc  jmp     loc_180002136
0x180002201  mov     r9d, 60h ; '`'
0x180002207  jmp     short loc_18000220F
0x180002209  mov     r9d, 6Dh ; 'm'
0x18000220f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002216  lea     rdx, aLresult; "lResult"
0x18000221d  call    DebugTraceError
0x180002222  jmp     loc_180002190
0x180002227  mov     r9d, 75h ; 'u'
0x18000222d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002234  lea     rdx, aStatus; "Status"
0x18000223b  mov     ecx, 8009001Eh
0x180002240  mov     ebx, 8009001Eh
0x180002245  call    DebugTraceError
0x18000224a  jmp     loc_180002129
0x18000224f  mov     rcx, rdi
0x180002252  call    MSCryptFree
0x180002257  jmp     loc_18000213F
```
