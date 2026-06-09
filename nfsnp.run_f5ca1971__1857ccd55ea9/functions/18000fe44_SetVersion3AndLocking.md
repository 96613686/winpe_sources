# SetVersion3AndLocking

- ea: `0x18000fe44`
- end: `0x18001013d`
- name: `SetVersion3AndLocking`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f1c8`

## callees

- `0x18000fe44`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000fedd`
- `msvcrt!wcscat_s` at `0x18000fedd`
- `msvcrt!wcsncpy_s` at `0x18000fec1`
- `msvcrt!wcsncpy_s` at `0x18000fec1`
- `ADVAPI32!RegCloseKey` at `0x18000ff97`
- `ADVAPI32!RegCloseKey` at `0x18000ff97`
- `ADVAPI32!RegQueryValueExW` at `0x18000ff4c`
- `ADVAPI32!RegQueryValueExW` at `0x18000ff86`
- `ADVAPI32!RegQueryValueExW` at `0x18000ff4c`
- `ADVAPI32!RegQueryValueExW` at `0x18000ff86`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ff0a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ff0a`
- `USER32!LoadStringW` at `0x18000ffd1`
- `USER32!LoadStringW` at `0x180010105`
- `USER32!LoadStringW` at `0x18000ffd1`
- `USER32!LoadStringW` at `0x180010105`

## string_xrefs

- `0x18000fecd`: `\Mount`
- `0x18000ff67`: `EUCMount`

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
0x18000fe44  mov     [rsp-8+arg_0], rbx
0x18000fe49  mov     [rsp-8+arg_8], rdi
0x18000fe4e  push    rbp
0x18000fe4f  lea     rbp, [rsp-380h]
0x18000fe57  sub     rsp, 480h
0x18000fe5e  mov     rax, cs:__security_cookie
0x18000fe65  xor     rax, rsp
0x18000fe68  mov     [rbp+380h+var_10], rax
0x18000fe6f  mov     rbx, r8
0x18000fe72  mov     dword ptr [rsp+480h+Data], 1
0x18000fe7a  mov     r8d, 208h; Size
0x18000fe80  mov     dword ptr [rsp+480h+var_448], 0
0x18000fe88  xor     edx, edx; Val
0x18000fe8a  mov     [rsp+480h+cbData], 0
0x18000fe92  lea     rcx, [rbp+380h+Destination]; void *
0x18000fe99  mov     [rsp+480h+hKey], 0
0x18000fea2  call    memset_0
0x18000fea7  mov     r9d, 103h; MaxCount
0x18000fead  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000feb4  lea     rcx, [rbp+380h+Destination]; Destination
0x18000febb  lea     edi, [r9+1]
0x18000febf  mov     edx, edi; SizeInWords
0x18000fec1  call    cs:__imp_wcsncpy_s
0x18000fec8  nop     dword ptr [rax+rax+00h]
0x18000fecd  lea     r8, aMount; "\\Mount"
0x18000fed4  mov     edx, edi; SizeInWords
0x18000fed6  lea     rcx, [rbp+380h+Destination]; Destination
0x18000fedd  call    cs:__imp_wcscat_s
0x18000fee4  nop     dword ptr [rax+rax+00h]
0x18000fee9  lea     rax, [rsp+480h+hKey]
0x18000feee  mov     r9d, 20019h; samDesired
0x18000fef4  xor     r8d, r8d; ulOptions
0x18000fef7  mov     [rsp+480h+phkResult], rax; phkResult
0x18000fefc  lea     rdx, [rbp+380h+Destination]; lpSubKey
0x18000ff03  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ff0a  call    cs:__imp_RegOpenKeyExW
0x18000ff11  nop     dword ptr [rax+rax+00h]
0x18000ff16  test    eax, eax
0x18000ff18  jnz     loc_18000FFA3
0x18000ff1e  mov     rcx, [rsp+480h+hKey]; hKey
0x18000ff23  lea     rax, [rsp+480h+cbData]
0x18000ff28  mov     [rsp+480h+lpcbData], rax; lpcbData
0x18000ff2d  lea     rdx, aLocking; "Locking"
0x18000ff34  lea     rax, [rsp+480h+Data]
0x18000ff39  mov     [rsp+480h+cbData], 4
0x18000ff41  xor     r9d, r9d; lpType
0x18000ff44  mov     [rsp+480h+phkResult], rax; lpData
0x18000ff49  xor     r8d, r8d; lpReserved
0x18000ff4c  call    cs:__imp_RegQueryValueExW
0x18000ff53  nop     dword ptr [rax+rax+00h]
0x18000ff58  mov     rcx, [rsp+480h+hKey]; hKey
0x18000ff5d  lea     rax, [rsp+480h+cbData]
0x18000ff62  mov     [rsp+480h+lpcbData], rax; lpcbData
0x18000ff67  lea     rdx, aEucmount; "EUCMount"
0x18000ff6e  lea     rax, [rsp+480h+var_448]
0x18000ff73  mov     [rsp+480h+cbData], 4
0x18000ff7b  xor     r9d, r9d; lpType
0x18000ff7e  mov     [rsp+480h+phkResult], rax; lpData
0x18000ff83  xor     r8d, r8d; lpReserved
0x18000ff86  call    cs:__imp_RegQueryValueExW
0x18000ff8d  nop     dword ptr [rax+rax+00h]
0x18000ff92  mov     rcx, [rsp+480h+hKey]; hKey
0x18000ff97  call    cs:__imp_RegCloseKey
0x18000ff9e  nop     dword ptr [rax+rax+00h]
0x18000ffa3  cmp     dword ptr [rsp+480h+Data], 0
0x18000ffa8  lea     r8, [rsp+480h+Buffer]; lpBuffer
0x18000ffad  mov     rcx, [rbx]
0x18000ffb0  mov     r9d, edi; cchBufferMax
0x18000ffb3  mov     eax, [rcx+38h]
0x18000ffb6  jz      short loc_18000FFC2
0x18000ffb8  or      eax, 1
0x18000ffbb  mov     edx, 42Ah
0x18000ffc0  jmp     short loc_18000FFCA
0x18000ffc2  and     eax, 0FFFFFFFEh
0x18000ffc5  mov     edx, 42Bh; uID
0x18000ffca  mov     [rcx+38h], eax
0x18000ffcd  mov     rcx, [rbx+30h]; hInstance
0x18000ffd1  call    cs:__imp_LoadStringW
0x18000ffd8  nop     dword ptr [rax+rax+00h]
0x18000ffdd  mov     eax, dword ptr [rsp+480h+var_448]
0x18000ffe1  test    eax, eax
0x18000ffe3  jz      loc_180010088
0x18000ffe9  mov     ecx, 2000h
0x18000ffee  cmp     eax, ecx
0x18000fff0  jnz     short loc_180010006
0x18000fff2  mov     edx, 9Eh
0x18000fff7  mov     rax, [rbx]
0x18000fffa  or      [rax+38h], ecx
0x18000fffd  mov     rcx, [rbx+30h]
0x180010001  jmp     loc_1800100FD
0x180010006  cmp     eax, 40h ; '@'
0x180010009  jnz     short loc_180010019
0x18001000b  mov     rax, [rbx]
0x18001000e  mov     edx, 9Dh
0x180010013  or      dword ptr [rax+38h], 40h
0x180010017  jmp     short loc_18000FFFD
0x180010019  mov     ecx, 4000h
0x18001001e  cmp     eax, ecx
0x180010020  jnz     short loc_180010029
0x180010022  mov     edx, 9Fh
0x180010027  jmp     short loc_18000FFF7
0x180010029  mov     ecx, 8000h
0x18001002e  cmp     eax, ecx
0x180010030  jnz     short loc_180010039
0x180010032  mov     edx, 0A1h
0x180010037  jmp     short loc_18000FFF7
0x180010039  mov     ecx, 10000h
0x18001003e  cmp     eax, ecx
0x180010040  jnz     short loc_18001004F
0x180010042  mov     rax, [rbx]
0x180010045  or      [rax+38h], ecx
0x180010048  mov     edx, 0A2h
0x18001004d  jmp     short loc_18000FFFD
0x18001004f  mov     ecx, 20000h
0x180010054  cmp     eax, ecx
0x180010056  jnz     short loc_18001005F
0x180010058  mov     edx, 0A3h
0x18001005d  jmp     short loc_18000FFF7
0x18001005f  mov     ecx, 40000h
0x180010064  cmp     eax, ecx
0x180010066  jnz     short loc_18001006F
0x180010068  mov     edx, 0A4h
0x18001006d  jmp     short loc_18000FFF7
0x18001006f  mov     ecx, 80000h
0x180010074  cmp     eax, ecx
0x180010076  jnz     loc_180010111
0x18001007c  mov     rax, [rbx]
0x18001007f  or      [rax+38h], ecx
0x180010082  mov     rcx, [rbx+30h]
0x180010086  jmp     short loc_1800100F8
0x180010088  mov     rax, [rbx]
0x18001008b  and     dword ptr [rax+38h], 0FFFFFFBFh
0x18001008f  mov     rax, [rbx]
0x180010092  btr     dword ptr [rax+38h], 0Dh
0x180010097  mov     rax, [rbx]
0x18001009a  btr     dword ptr [rax+38h], 0Eh
0x18001009f  mov     rax, [rbx]
0x1800100a2  btr     dword ptr [rax+38h], 0Fh
0x1800100a7  mov     rax, [rbx]
0x1800100aa  btr     dword ptr [rax+38h], 10h
0x1800100af  mov     rax, [rbx]
0x1800100b2  btr     dword ptr [rax+38h], 11h
0x1800100b7  mov     rax, [rbx]
0x1800100ba  btr     dword ptr [rax+38h], 12h
0x1800100bf  mov     rax, [rbx]
0x1800100c2  btr     dword ptr [rax+38h], 13h
0x1800100c7  mov     eax, cs:gfCodeModeFlags
0x1800100cd  test    al, 10h
0x1800100cf  jnz     loc_180010048
0x1800100d5  mov     rcx, [rbx+30h]; hInstance
0x1800100d9  test    al, 8
0x1800100db  jz      short loc_1800100E4
0x1800100dd  mov     edx, 0A1h
0x1800100e2  jmp     short loc_1800100FD
0x1800100e4  test    al, 20h
0x1800100e6  jz      short loc_1800100EF
0x1800100e8  mov     edx, 0A3h
0x1800100ed  jmp     short loc_1800100FD
0x1800100ef  mov     edx, 0A4h
0x1800100f4  test    al, 40h
0x1800100f6  jnz     short loc_1800100FD
0x1800100f8  mov     edx, 0A0h; uID
0x1800100fd  mov     r9d, edi; cchBufferMax
0x180010100  lea     r8, [rsp+480h+Buffer]; lpBuffer
0x180010105  call    cs:__imp_LoadStringW
0x18001010c  nop     dword ptr [rax+rax+00h]
0x180010111  mov     rax, [rbx]
0x180010114  or      dword ptr [rax+38h], 4
0x180010118  mov     rcx, [rbp+380h+var_10]
0x18001011f  xor     rcx, rsp; StackCookie
0x180010122  call    __security_check_cookie
0x180010127  lea     r11, [rsp+480h+var_s0]
0x18001012f  mov     rbx, [r11+10h]
0x180010133  mov     rdi, [r11+18h]
0x180010137  mov     rsp, r11
0x18001013a  pop     rbp
0x18001013b  retn
```
