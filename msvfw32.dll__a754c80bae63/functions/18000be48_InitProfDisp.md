# InitProfDisp

- ea: `0x18000be48`
- end: `0x18000c135`
- name: `InitProfDisp`
- size: `749`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000bd90`
- `0x18000c13c`

## callees

- `0x1800014b0`
- `0x180001d4a`
- `0x180001fd8`
- `0x180002280`
- `0x18000241c`
- `0x180003f98`
- `0x18000be48`
- `0x18000c300`
- `0x18000d080`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c10c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c10c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c0fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c0fc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000bf40`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000bf53`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000c0d4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000bf40`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000bf53`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000c0d4`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18000bea6`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18000bea6`
- `GDI32!GetDeviceCaps` at `0x18000bebd`
- `GDI32!GetDeviceCaps` at `0x18000becb`
- `GDI32!GetDeviceCaps` at `0x18000bebd`
- `GDI32!GetDeviceCaps` at `0x18000becb`
- `USER32!GetDC` at `0x18000beae`
- `USER32!GetDC` at `0x18000beae`
- `USER32!ReleaseDC` at `0x18000bfb3`
- `USER32!ReleaseDC` at `0x18000bfb3`
- `USER32!GetSystemMetrics` at `0x18000bf71`
- `USER32!GetSystemMetrics` at `0x18000bf7b`
- `USER32!GetSystemMetrics` at `0x18000bf71`
- `USER32!GetSystemMetrics` at `0x18000bf7b`

## pseudocode

```c
int __fastcall InitProfDisp(unsigned int a1)
{
  HDC DC; // r15
  int DeviceCaps; // ebx
  int v4; // r13d
  int BitmapType; // r12d
  const wchar_t *v6; // r8
  size_t v7; // rsi
  int v8; // r13d
  wchar_t *v9; // rdi
  int SystemMetrics; // ebx
  unsigned int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx
  int *v15; // rcx
  int v16; // ebx
  __int64 i; // rdi
  wchar_t *v18; // rsi
  HKEY KeyW; // rax
  int v20; // eax
  __int64 v21; // rcx
  HKEY v22; // rbx
  int v23; // eax
  DWORD nSize[2]; // [rsp+20h] [rbp-E0h]
  DWORD nSizea[2]; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFileName; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpFileNamea; // [rsp+28h] [rbp-D8h]
  __int64 v29; // [rsp+30h] [rbp-D0h]
  _DWORD v30[4]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[80]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ReturnedString[80]; // [rsp+F0h] [rbp-10h] BYREF

  GetPrivateProfileStringW(AppName, KeyName, &Default, ReturnedString, 0x50u, aSystemIni_0);
  DC = GetDC(0);
  DeviceCaps = GetDeviceCaps(DC, 14);
  v4 = GetDeviceCaps(DC, 12);
  BitmapType = GetBitmapType();
  switch ( BitmapType & 0xF )
  {
    case 1:
      goto LABEL_12;
    case 2:
      v6 = a555;
      goto LABEL_11;
    case 3:
    case 4:
      v6 = aBgr;
      goto LABEL_11;
    case 6:
      v6 = a565;
      goto LABEL_11;
  }
  if ( (BitmapType & 0xFu) - 7 > 1 )
  {
LABEL_12:
    pszDest[0] = 0;
    goto LABEL_13;
  }
  v6 = aRgb;
LABEL_11:
  StringCchCopyW(pszDest, 0x50u, v6);
LABEL_13:
  v7 = 80LL - lstrlenW(ReturnedString);
  v8 = DeviceCaps * v4;
  v9 = &ReturnedString[lstrlenW(ReturnedString)];
  SystemMetrics = GetSystemMetrics(1);
  v11 = GetSystemMetrics(0);
  LODWORD(lpFileName) = v8;
  nSize[0] = SystemMetrics;
  StringCchPrintfW(v9, v7, L" %dx%dx%d(%s%u)", v11, *(_QWORD *)nSize, lpFileName, pszDest, BitmapType >> 4);
  ReleaseDC(0, DC);
  mmGetProfileString(v12, ReturnedString, v13, pszDest);
  v16 = 0;
  for ( i = 1; i != 5; ++i )
  {
    v18 = &pszDest[v16];
    KeyW = (HKEY)dword_18001D300;
    if ( *v18 )
    {
      v20 = wcstol(&pszDest[v16], 0, 10);
      v15 = dword_18001D300;
      dword_18001D300[i] = v20;
      if ( *v18 )
      {
        do
        {
          if ( pszDest[v16] == 44 )
            break;
          ++v16;
        }
        while ( pszDest[v16] );
      }
      LODWORD(KeyW) = v16;
      if ( pszDest[v16] )
        ++v16;
    }
    else
    {
      dword_18001D300[i] = -1;
    }
  }
  if ( a1
    || (_DWORD)qword_18001D304 == -1
    || HIDWORD(qword_18001D304) == -1
    || (_DWORD)qword_18001D30C == -1
    || HIDWORD(qword_18001D30C) == -1 )
  {
    TestDibFormats(v15, v14, a1);
    LODWORD(v29) = HIDWORD(qword_18001D30C);
    LODWORD(lpFileNamea) = qword_18001D30C;
    nSizea[0] = HIDWORD(qword_18001D304);
    StringCchPrintfW(pszDest, 0x50u, L"%d,%d,%d,%d", (unsigned int)qword_18001D304, *(_QWORD *)nSizea, lpFileNamea, v29);
    v30[0] = 0;
    KeyW = GetKeyW(v21, v30, 1);
    v22 = KeyW;
    if ( KeyW )
    {
      v23 = lstrlenW(pszDest);
      LODWORD(KeyW) = RegSetValueExW(v22, ReturnedString, 0, 1u, (const BYTE *)pszDest, 2 * v23 + 2);
      if ( v30[0] )
        LODWORD(KeyW) = RegCloseKey(v22);
    }
  }
  return (int)KeyW;
}

```

## disassembly

```asm
0x18000be48  push    rbp
0x18000be4a  push    rbx
0x18000be4b  push    rsi
0x18000be4c  push    rdi
0x18000be4d  push    r12
0x18000be4f  push    r13
0x18000be51  push    r14
0x18000be53  push    r15
0x18000be55  lea     rbp, [rsp-0A8h]
0x18000be5d  sub     rsp, 1A8h
0x18000be64  mov     rax, cs:__security_cookie
0x18000be6b  xor     rax, rsp
0x18000be6e  mov     [rbp+0E0h+var_50], rax
0x18000be75  lea     rax, aSystemIni_0; "system.ini"
0x18000be7c  mov     r14d, ecx
0x18000be7f  mov     [rsp+1E0h+lpFileName], rax; lpFileName
0x18000be84  lea     r9, [rbp+0E0h+ReturnedString]; lpReturnedString
0x18000be88  mov     edi, 50h ; 'P'
0x18000be8d  lea     r8, Default; lpDefault
0x18000be94  lea     rdx, KeyName; "display.drv"
0x18000be9b  mov     [rsp+1E0h+nSize], edi; nSize
0x18000be9f  lea     rcx, AppName; "boot"
0x18000bea6  call    cs:__imp_GetPrivateProfileStringW
0x18000beac  xor     ecx, ecx; hWnd
0x18000beae  call    cs:__imp_GetDC
0x18000beb4  mov     rcx, rax; hdc
0x18000beb7  lea     edx, [rdi-42h]; index
0x18000beba  mov     r15, rax
0x18000bebd  call    cs:__imp_GetDeviceCaps
0x18000bec3  lea     edx, [rdi-44h]; index
0x18000bec6  mov     rcx, r15; hdc
0x18000bec9  mov     ebx, eax
0x18000becb  call    cs:__imp_GetDeviceCaps
0x18000bed1  mov     r13d, eax
0x18000bed4  call    GetBitmapType
0x18000bed9  mov     edx, eax
0x18000bedb  mov     r12d, eax
0x18000bede  and     edx, 0Fh
0x18000bee1  sub     edx, 1
0x18000bee4  jz      short loc_18000BF35
0x18000bee6  sub     edx, 1
0x18000bee9  jz      short loc_18000BF1F
0x18000beeb  sub     edx, 1
0x18000beee  jz      short loc_18000BF16
0x18000bef0  sub     edx, 1
0x18000bef3  jz      short loc_18000BF16
0x18000bef5  sub     edx, 2
0x18000bef8  jz      short loc_18000BF0D
0x18000befa  sub     edx, 1
0x18000befd  jz      short loc_18000BF04
0x18000beff  cmp     edx, 1
0x18000bf02  jnz     short loc_18000BF35
0x18000bf04  lea     r8, aRgb; "RGB "
0x18000bf0b  jmp     short loc_18000BF26
0x18000bf0d  lea     r8, a565; "565 "
0x18000bf14  jmp     short loc_18000BF26
0x18000bf16  lea     r8, aBgr; "BGR "
0x18000bf1d  jmp     short loc_18000BF26
0x18000bf1f  lea     r8, a555; "555 "
0x18000bf26  mov     rdx, rdi; cchDest
0x18000bf29  lea     rcx, [rsp+1E0h+pszDest]; pszDest
0x18000bf2e  call    StringCchCopyW
0x18000bf33  jmp     short loc_18000BF3C
0x18000bf35  xor     eax, eax
0x18000bf37  mov     [rsp+1E0h+pszDest], ax
0x18000bf3c  lea     rcx, [rbp+0E0h+ReturnedString]; lpString
0x18000bf40  call    cs:__imp_lstrlenW
0x18000bf46  movsxd  rcx, eax
0x18000bf49  mov     rsi, rdi
0x18000bf4c  sub     rsi, rcx
0x18000bf4f  lea     rcx, [rbp+0E0h+ReturnedString]; lpString
0x18000bf53  call    cs:__imp_lstrlenW
0x18000bf59  lea     rdi, [rbp+0E0h+ReturnedString]
0x18000bf5d  sar     r12d, 4
0x18000bf61  movsxd  rcx, eax
0x18000bf64  imul    r13d, ebx
0x18000bf68  lea     rdi, [rdi+rcx*2]
0x18000bf6c  mov     ecx, 1; nIndex
0x18000bf71  call    cs:__imp_GetSystemMetrics
0x18000bf77  xor     ecx, ecx; nIndex
0x18000bf79  mov     ebx, eax
0x18000bf7b  call    cs:__imp_GetSystemMetrics
0x18000bf81  mov     [rsp+1E0h+var_1A8], r12d
0x18000bf86  lea     r8, aDxDxDSU; " %dx%dx%d(%s%u)"
0x18000bf8d  mov     r9d, eax
0x18000bf90  mov     rdx, rsi; cchDest
0x18000bf93  lea     rax, [rsp+1E0h+pszDest]
0x18000bf98  mov     rcx, rdi; pszDest
0x18000bf9b  mov     [rsp+1E0h+var_1B0], rax
0x18000bfa0  mov     dword ptr [rsp+1E0h+lpFileName], r13d
0x18000bfa5  mov     [rsp+1E0h+nSize], ebx
0x18000bfa9  call    StringCchPrintfW
0x18000bfae  mov     rdx, r15; hDC
0x18000bfb1  xor     ecx, ecx; hWnd
0x18000bfb3  call    cs:__imp_ReleaseDC
0x18000bfb9  lea     r9, [rsp+1E0h+pszDest]
0x18000bfbe  lea     rdx, [rbp+0E0h+ReturnedString]
0x18000bfc2  call    mmGetProfileString
0x18000bfc7  xor     r15d, r15d
0x18000bfca  mov     ebx, r15d
0x18000bfcd  or      r12d, 0FFFFFFFFh
0x18000bfd1  lea     r13d, [r15+1]
0x18000bfd5  mov     edi, r13d
0x18000bfd8  movsxd  rax, ebx
0x18000bfdb  lea     rsi, [rsp+1E0h+pszDest]
0x18000bfe0  lea     rsi, [rsi+rax*2]
0x18000bfe4  lea     rax, dword_18001D300
0x18000bfeb  cmp     [rsi], r15w
0x18000bfef  jnz     short loc_18000BFF7
0x18000bff1  mov     [rax+rdi*4], r12d
0x18000bff5  jmp     short loc_18000C03C
0x18000bff7  xor     edx, edx; EndPtr
0x18000bff9  mov     rcx, rsi; String
0x18000bffc  lea     r8d, [rdx+0Ah]; Radix
0x18000c000  call    wcstol
0x18000c005  lea     rcx, dword_18001D300
0x18000c00c  mov     [rcx+rdi*4], eax
0x18000c00f  cmp     [rsi], r15w
0x18000c013  jz      short loc_18000C02E
0x18000c015  movsxd  rax, ebx
0x18000c018  cmp     [rsp+rax*2+1E0h+pszDest], 2Ch ; ','
0x18000c01e  jz      short loc_18000C02E
0x18000c020  add     ebx, r13d
0x18000c023  movsxd  rax, ebx
0x18000c026  cmp     [rsp+rax*2+1E0h+pszDest], r15w
0x18000c02c  jnz     short loc_18000C015
0x18000c02e  movsxd  rax, ebx
0x18000c031  cmp     [rsp+rax*2+1E0h+pszDest], r15w
0x18000c037  jz      short loc_18000C03C
0x18000c039  add     ebx, r13d
0x18000c03c  inc     rdi
0x18000c03f  cmp     rdi, 5
0x18000c043  jnz     short loc_18000BFD8
0x18000c045  test    r14d, r14d
0x18000c048  jnz     short loc_18000C072
0x18000c04a  cmp     dword ptr cs:qword_18001D304, r12d
0x18000c051  jz      short loc_18000C072
0x18000c053  cmp     dword ptr cs:qword_18001D304+4, r12d
0x18000c05a  jz      short loc_18000C072
0x18000c05c  cmp     dword ptr cs:qword_18001D30C, r12d
0x18000c063  jz      short loc_18000C072
0x18000c065  cmp     dword ptr cs:qword_18001D30C+4, r12d
0x18000c06c  jnz     loc_18000C112
0x18000c072  mov     r8d, r14d
0x18000c075  call    TestDibFormats
0x18000c07a  mov     eax, dword ptr cs:qword_18001D30C+4
0x18000c080  lea     r8, aDDDD; "%d,%d,%d,%d"
0x18000c087  mov     r9d, dword ptr cs:qword_18001D304
0x18000c08e  lea     rcx, [rsp+1E0h+pszDest]; pszDest
0x18000c093  mov     dword ptr [rsp+1E0h+var_1B0], eax
0x18000c097  mov     edx, 50h ; 'P'; cchDest
0x18000c09c  mov     eax, dword ptr cs:qword_18001D30C
0x18000c0a2  mov     dword ptr [rsp+1E0h+lpFileName], eax
0x18000c0a6  mov     eax, dword ptr cs:qword_18001D304+4
0x18000c0ac  mov     [rsp+1E0h+nSize], eax
0x18000c0b0  call    StringCchPrintfW
0x18000c0b5  mov     r8d, r13d
0x18000c0b8  mov     [rsp+1E0h+var_1A0], r15d
0x18000c0bd  lea     rdx, [rsp+1E0h+var_1A0]
0x18000c0c2  call    GetKeyW
0x18000c0c7  mov     rbx, rax
0x18000c0ca  test    rax, rax
0x18000c0cd  jz      short loc_18000C112
0x18000c0cf  lea     rcx, [rsp+1E0h+pszDest]; lpString
0x18000c0d4  call    cs:__imp_lstrlenW
0x18000c0da  mov     r9d, r13d; dwType
0x18000c0dd  lea     rdx, [rbp+0E0h+ReturnedString]; lpValueName
0x18000c0e1  xor     r8d, r8d; Reserved
0x18000c0e4  mov     rcx, rbx; hKey
0x18000c0e7  lea     eax, ds:2[rax*2]
0x18000c0ee  mov     dword ptr [rsp+1E0h+lpFileName], eax; cbData
0x18000c0f2  lea     rax, [rsp+1E0h+pszDest]
0x18000c0f7  mov     qword ptr [rsp+1E0h+nSize], rax; lpData
0x18000c0fc  call    cs:__imp_RegSetValueExW
0x18000c102  cmp     [rsp+1E0h+var_1A0], r15d
0x18000c107  jz      short loc_18000C112
0x18000c109  mov     rcx, rbx; hKey
0x18000c10c  call    cs:__imp_RegCloseKey
0x18000c112  mov     rcx, [rbp+0E0h+var_50]
0x18000c119  xor     rcx, rsp; StackCookie
0x18000c11c  call    __security_check_cookie
0x18000c121  add     rsp, 1A8h
0x18000c128  pop     r15
0x18000c12a  pop     r14
0x18000c12c  pop     r13
0x18000c12e  pop     r12
0x18000c130  pop     rdi
0x18000c131  pop     rsi
0x18000c132  pop     rbx
0x18000c133  pop     rbp
0x18000c134  retn
```
