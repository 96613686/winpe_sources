# SetVersion3AndLocking

- ea: `0x18000efac`
- end: `0x18000f270`
- name: `SetVersion3AndLocking`
- size: `708`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e454`

## callees

- `0x18000efac`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000f03f`
- `msvcrt!wcscat_s` at `0x18000f03f`
- `msvcrt!wcsncpy_s` at `0x18000f029`
- `msvcrt!wcsncpy_s` at `0x18000f029`
- `ADVAPI32!RegCloseKey` at `0x18000f0dd`
- `ADVAPI32!RegCloseKey` at `0x18000f0dd`
- `ADVAPI32!RegQueryValueExW` at `0x18000f09e`
- `ADVAPI32!RegQueryValueExW` at `0x18000f0d2`
- `ADVAPI32!RegQueryValueExW` at `0x18000f09e`
- `ADVAPI32!RegQueryValueExW` at `0x18000f0d2`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f066`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f066`
- `USER32!LoadStringW` at `0x18000f111`
- `USER32!LoadStringW` at `0x18000f23f`
- `USER32!LoadStringW` at `0x18000f111`
- `USER32!LoadStringW` at `0x18000f23f`

## string_xrefs

- `0x18000f02f`: `\Mount`
- `0x18000f0b3`: `EUCMount`

## pseudocode

```c
HINSTANCE __fastcall SetVersion3AndLocking(__int64 a1, __int64 a2, HINSTANCE *a3)
{
  int v4; // eax
  unsigned int v5; // eax
  UINT v6; // edx
  int v7; // ecx
  UINT v8; // edx
  HINSTANCE v9; // rcx
  HINSTANCE result; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Destination[264]; // [rsp+260h] [rbp+160h] BYREF

  *(_DWORD *)Data = 1;
  *(_DWORD *)v13 = 0;
  cbData = 0;
  hKey = 0;
  memset_0(Destination, 0, 0x208u);
  wcsncpy_s(Destination, 0x104u, L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default", 0x103u);
  wcscat_s(Destination, 0x104u, L"\\Mount");
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, Destination, 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    RegQueryValueExW(hKey, L"Locking", 0, 0, Data, &cbData);
    cbData = 4;
    RegQueryValueExW(hKey, L"EUCMount", 0, 0, v13, &cbData);
    RegCloseKey(hKey);
  }
  v4 = *((_DWORD *)*a3 + 14);
  if ( *(_DWORD *)Data )
  {
    v5 = v4 | 1;
    v6 = 1066;
  }
  else
  {
    v5 = v4 & 0xFFFFFFFE;
    v6 = 1067;
  }
  *((_DWORD *)*a3 + 14) = v5;
  LoadStringW(a3[6], v6, Buffer, 260);
  if ( !*(_DWORD *)v13 )
  {
    *((_DWORD *)*a3 + 14) &= ~0x40u;
    *((_DWORD *)*a3 + 14) &= ~0x2000u;
    *((_DWORD *)*a3 + 14) &= ~0x4000u;
    *((_DWORD *)*a3 + 14) &= ~0x8000u;
    *((_DWORD *)*a3 + 14) &= ~0x10000u;
    *((_DWORD *)*a3 + 14) &= ~0x20000u;
    *((_DWORD *)*a3 + 14) &= ~0x40000u;
    *((_DWORD *)*a3 + 14) &= ~0x80000u;
    if ( (gfCodeModeFlags & 0x10) != 0 )
      goto LABEL_19;
    v9 = a3[6];
    if ( (gfCodeModeFlags & 8) != 0 )
    {
      v8 = 161;
      goto LABEL_33;
    }
    if ( (gfCodeModeFlags & 0x20) != 0 )
    {
      v8 = 163;
      goto LABEL_33;
    }
    v8 = 164;
    if ( (gfCodeModeFlags & 0x40) != 0 )
      goto LABEL_33;
LABEL_32:
    v8 = 160;
    goto LABEL_33;
  }
  v7 = 0x2000;
  if ( *(_DWORD *)v13 == 0x2000 )
  {
    v8 = 158;
LABEL_9:
    *((_DWORD *)*a3 + 14) |= v7;
LABEL_10:
    v9 = a3[6];
LABEL_33:
    LoadStringW(v9, v8, Buffer, 260);
    goto LABEL_34;
  }
  if ( *(_DWORD *)v13 == 64 )
  {
    v8 = 157;
    *((_DWORD *)*a3 + 14) |= 0x40u;
    goto LABEL_10;
  }
  v7 = 0x4000;
  if ( *(_DWORD *)v13 == 0x4000 )
  {
    v8 = 159;
    goto LABEL_9;
  }
  v7 = 0x8000;
  if ( *(_DWORD *)v13 == 0x8000 )
  {
    v8 = 161;
    goto LABEL_9;
  }
  if ( *(_DWORD *)v13 == 0x10000 )
  {
    *((_DWORD *)*a3 + 14) |= 0x10000u;
LABEL_19:
    v8 = 162;
    goto LABEL_10;
  }
  v7 = 0x20000;
  if ( *(_DWORD *)v13 == 0x20000 )
  {
    v8 = 163;
    goto LABEL_9;
  }
  v7 = 0x40000;
  if ( *(_DWORD *)v13 == 0x40000 )
  {
    v8 = 164;
    goto LABEL_9;
  }
  if ( *(_DWORD *)v13 == 0x80000 )
  {
    *((_DWORD *)*a3 + 14) |= 0x80000u;
    v9 = a3[6];
    goto LABEL_32;
  }
LABEL_34:
  result = *a3;
  *((_DWORD *)*a3 + 14) |= 4u;
  return result;
}

```

## disassembly

```asm
0x18000efac  mov     [rsp-8+arg_0], rbx
0x18000efb1  mov     [rsp-8+arg_8], rdi
0x18000efb6  push    rbp
0x18000efb7  lea     rbp, [rsp-380h]
0x18000efbf  sub     rsp, 480h
0x18000efc6  mov     rax, cs:__security_cookie
0x18000efcd  xor     rax, rsp
0x18000efd0  mov     [rbp+380h+var_10], rax
0x18000efd7  mov     rbx, r8
0x18000efda  mov     dword ptr [rsp+480h+Data], 1
0x18000efe2  mov     r8d, 208h; Size
0x18000efe8  mov     dword ptr [rsp+480h+var_448], 0
0x18000eff0  xor     edx, edx; Val
0x18000eff2  mov     [rsp+480h+cbData], 0
0x18000effa  lea     rcx, [rbp+380h+Destination]; void *
0x18000f001  mov     [rsp+480h+hKey], 0
0x18000f00a  call    memset_0
0x18000f00f  mov     r9d, 103h; MaxCount
0x18000f015  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000f01c  lea     rcx, [rbp+380h+Destination]; Destination
0x18000f023  lea     edi, [r9+1]
0x18000f027  mov     edx, edi; SizeInWords
0x18000f029  call    cs:__imp_wcsncpy_s
0x18000f02f  lea     r8, aMount; "\\Mount"
0x18000f036  mov     edx, edi; SizeInWords
0x18000f038  lea     rcx, [rbp+380h+Destination]; Destination
0x18000f03f  call    cs:__imp_wcscat_s
0x18000f045  lea     rax, [rsp+480h+hKey]
0x18000f04a  mov     r9d, 20019h; samDesired
0x18000f050  xor     r8d, r8d; ulOptions
0x18000f053  mov     [rsp+480h+phkResult], rax; phkResult
0x18000f058  lea     rdx, [rbp+380h+Destination]; lpSubKey
0x18000f05f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f066  call    cs:__imp_RegOpenKeyExW
0x18000f06c  test    eax, eax
0x18000f06e  jnz     short loc_18000F0E3
0x18000f070  mov     rcx, [rsp+480h+hKey]; hKey
0x18000f075  lea     rax, [rsp+480h+cbData]
0x18000f07a  mov     [rsp+480h+lpcbData], rax; lpcbData
0x18000f07f  lea     rdx, aLocking; "Locking"
0x18000f086  lea     rax, [rsp+480h+Data]
0x18000f08b  mov     [rsp+480h+cbData], 4
0x18000f093  xor     r9d, r9d; lpType
0x18000f096  mov     [rsp+480h+phkResult], rax; lpData
0x18000f09b  xor     r8d, r8d; lpReserved
0x18000f09e  call    cs:__imp_RegQueryValueExW
0x18000f0a4  mov     rcx, [rsp+480h+hKey]; hKey
0x18000f0a9  lea     rax, [rsp+480h+cbData]
0x18000f0ae  mov     [rsp+480h+lpcbData], rax; lpcbData
0x18000f0b3  lea     rdx, aEucmount; "EUCMount"
0x18000f0ba  lea     rax, [rsp+480h+var_448]
0x18000f0bf  mov     [rsp+480h+cbData], 4
0x18000f0c7  xor     r9d, r9d; lpType
0x18000f0ca  mov     [rsp+480h+phkResult], rax; lpData
0x18000f0cf  xor     r8d, r8d; lpReserved
0x18000f0d2  call    cs:__imp_RegQueryValueExW
0x18000f0d8  mov     rcx, [rsp+480h+hKey]; hKey
0x18000f0dd  call    cs:__imp_RegCloseKey
0x18000f0e3  cmp     dword ptr [rsp+480h+Data], 0
0x18000f0e8  lea     r8, [rsp+480h+Buffer]; lpBuffer
0x18000f0ed  mov     rcx, [rbx]
0x18000f0f0  mov     r9d, edi; cchBufferMax
0x18000f0f3  mov     eax, [rcx+38h]
0x18000f0f6  jz      short loc_18000F102
0x18000f0f8  or      eax, 1
0x18000f0fb  mov     edx, 42Ah
0x18000f100  jmp     short loc_18000F10A
0x18000f102  and     eax, 0FFFFFFFEh
0x18000f105  mov     edx, 42Bh; uID
0x18000f10a  mov     [rcx+38h], eax
0x18000f10d  mov     rcx, [rbx+30h]; hInstance
0x18000f111  call    cs:__imp_LoadStringW
0x18000f117  mov     eax, dword ptr [rsp+480h+var_448]
0x18000f11b  test    eax, eax
0x18000f11d  jz      loc_18000F1C2
0x18000f123  mov     ecx, 2000h
0x18000f128  cmp     eax, ecx
0x18000f12a  jnz     short loc_18000F140
0x18000f12c  mov     edx, 9Eh
0x18000f131  mov     rax, [rbx]
0x18000f134  or      [rax+38h], ecx
0x18000f137  mov     rcx, [rbx+30h]
0x18000f13b  jmp     loc_18000F237
0x18000f140  cmp     eax, 40h ; '@'
0x18000f143  jnz     short loc_18000F153
0x18000f145  mov     rax, [rbx]
0x18000f148  mov     edx, 9Dh
0x18000f14d  or      dword ptr [rax+38h], 40h
0x18000f151  jmp     short loc_18000F137
0x18000f153  mov     ecx, 4000h
0x18000f158  cmp     eax, ecx
0x18000f15a  jnz     short loc_18000F163
0x18000f15c  mov     edx, 9Fh
0x18000f161  jmp     short loc_18000F131
0x18000f163  mov     ecx, 8000h
0x18000f168  cmp     eax, ecx
0x18000f16a  jnz     short loc_18000F173
0x18000f16c  mov     edx, 0A1h
0x18000f171  jmp     short loc_18000F131
0x18000f173  mov     ecx, 10000h
0x18000f178  cmp     eax, ecx
0x18000f17a  jnz     short loc_18000F189
0x18000f17c  mov     rax, [rbx]
0x18000f17f  or      [rax+38h], ecx
0x18000f182  mov     edx, 0A2h
0x18000f187  jmp     short loc_18000F137
0x18000f189  mov     ecx, 20000h
0x18000f18e  cmp     eax, ecx
0x18000f190  jnz     short loc_18000F199
0x18000f192  mov     edx, 0A3h
0x18000f197  jmp     short loc_18000F131
0x18000f199  mov     ecx, 40000h
0x18000f19e  cmp     eax, ecx
0x18000f1a0  jnz     short loc_18000F1A9
0x18000f1a2  mov     edx, 0A4h
0x18000f1a7  jmp     short loc_18000F131
0x18000f1a9  mov     ecx, 80000h
0x18000f1ae  cmp     eax, ecx
0x18000f1b0  jnz     loc_18000F245
0x18000f1b6  mov     rax, [rbx]
0x18000f1b9  or      [rax+38h], ecx
0x18000f1bc  mov     rcx, [rbx+30h]
0x18000f1c0  jmp     short loc_18000F232
0x18000f1c2  mov     rax, [rbx]
0x18000f1c5  and     dword ptr [rax+38h], 0FFFFFFBFh
0x18000f1c9  mov     rax, [rbx]
0x18000f1cc  btr     dword ptr [rax+38h], 0Dh
0x18000f1d1  mov     rax, [rbx]
0x18000f1d4  btr     dword ptr [rax+38h], 0Eh
0x18000f1d9  mov     rax, [rbx]
0x18000f1dc  btr     dword ptr [rax+38h], 0Fh
0x18000f1e1  mov     rax, [rbx]
0x18000f1e4  btr     dword ptr [rax+38h], 10h
0x18000f1e9  mov     rax, [rbx]
0x18000f1ec  btr     dword ptr [rax+38h], 11h
0x18000f1f1  mov     rax, [rbx]
0x18000f1f4  btr     dword ptr [rax+38h], 12h
0x18000f1f9  mov     rax, [rbx]
0x18000f1fc  btr     dword ptr [rax+38h], 13h
0x18000f201  mov     eax, cs:gfCodeModeFlags
0x18000f207  test    al, 10h
0x18000f209  jnz     loc_18000F182
0x18000f20f  mov     rcx, [rbx+30h]; hInstance
0x18000f213  test    al, 8
0x18000f215  jz      short loc_18000F21E
0x18000f217  mov     edx, 0A1h
0x18000f21c  jmp     short loc_18000F237
0x18000f21e  test    al, 20h
0x18000f220  jz      short loc_18000F229
0x18000f222  mov     edx, 0A3h
0x18000f227  jmp     short loc_18000F237
0x18000f229  mov     edx, 0A4h
0x18000f22e  test    al, 40h
0x18000f230  jnz     short loc_18000F237
0x18000f232  mov     edx, 0A0h; uID
0x18000f237  mov     r9d, edi; cchBufferMax
0x18000f23a  lea     r8, [rsp+480h+Buffer]; lpBuffer
0x18000f23f  call    cs:__imp_LoadStringW
0x18000f245  mov     rax, [rbx]
0x18000f248  or      dword ptr [rax+38h], 4
0x18000f24c  mov     rcx, [rbp+380h+var_10]
0x18000f253  xor     rcx, rsp; StackCookie
0x18000f256  call    __security_check_cookie
0x18000f25b  lea     r11, [rsp+480h+var_s0]
0x18000f263  mov     rbx, [r11+10h]
0x18000f267  mov     rdi, [r11+18h]
0x18000f26b  mov     rsp, r11
0x18000f26e  pop     rbp
0x18000f26f  retn
```
