# PutBranch

- ea: `0x14000be00`
- end: `0x14000c1df`
- name: `PutBranch`
- size: `991`
- prototype: `LSTATUS __fastcall(HKEY hKey, _WORD *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000a934`
- `0x14000be00`

## callees

- `0x140001340`
- `0x14000bd44`
- `0x14000be00`
- `0x14000c1e8`
- `0x14000c24c`
- `0x14000c2b8`
- `0x14000c2e8`
- `0x14000edd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x14000c094`
- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x14000c094`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14000be96`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14000be96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000bfe1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000bfe1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000c0fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000c0fa`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000bfb8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000c06c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000bfb8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000c06c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c006`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c006`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c18f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c18f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000c0c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000c0c9`

## pseudocode

```c
LSTATUS __fastcall PutBranch(HKEY hKey, _WORD *a2, int a3)
{
  int v6; // r15d
  DWORD i; // edi
  LSTATUS v8; // ebx
  __int64 v9; // r9
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  int v15; // eax
  __int64 v16; // rcx
  DWORD *p_cbData; // rax
  DWORD *v18; // rcx
  WCHAR *v19; // rsi
  int v20; // r14d
  LSTATUS result; // eax
  DWORD v22; // edx
  __int64 v23; // rax
  BYTE *v24; // rbx
  DWORD cbData; // [rsp+40h] [rbp+0h] BYREF
  DWORD Type; // [rsp+44h] [rbp+4h] BYREF
  DWORD cchName; // [rsp+48h] [rbp+8h] BYREF
  DWORD cchValueName; // [rsp+50h] [rbp+10h] BYREF
  HKEY hKeya[2]; // [rsp+58h] [rbp+18h] BYREF

  hKeya[0] = 0;
  cchValueName = 0;
  cbData = 0;
  Type = 0;
  v6 = 0;
  PutChar(91);
  PutLiteral(a2);
  PutLiteral(L"]\n");
  for ( i = 0; ; ++i )
  {
    cchValueName = 256;
    v8 = RegEnumValueW(hKey, i, &g_ValueNameBuffer, &cchValueName, 0, &Type, 0, &cbData);
    if ( v8 )
      break;
    g_FileErrorStringID = 0;
    if ( Type - 1 <= 1 || (v23 = 0, Type == 7) )
      v23 = 2;
    v24 = (BYTE *)LocalAlloc(0x40u, v23 + cbData);
    if ( v24 )
    {
      if ( RegQueryValueExW(hKey, &g_ValueNameBuffer, 0, &Type, v24, &cbData) )
      {
        g_FileErrorStringID = 802;
      }
      else
      {
        if ( cchValueName )
          PutString(&g_ValueNameBuffer);
        else
          PutChar(64);
        PutChar(61);
        if ( Type == 1 )
        {
          PutString(v24);
        }
        else if ( Type == 4 && cbData == 4 )
        {
          PutLiteral(L"dword:");
          PutDword(*(unsigned int *)v24, 1);
        }
        else
        {
          PutBinary(v24, Type, cbData);
        }
        PutChar(10);
      }
      LocalFree(v24);
      result = g_FileErrorStringID;
    }
    else
    {
      result = 802;
      g_FileErrorStringID = 802;
    }
    if ( result == 802 )
      return result;
    if ( !result )
      v6 = 1;
  }
  PutChar(10);
  if ( v8 != 259 )
    g_FileErrorStringID = 30;
  if ( v6 == 1 )
    ++g_dwTotalKeysSaved;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  v10 = v9 + 256;
  v11 = 2 * (v9 + 256) + 15;
  if ( v11 <= 2 * (v9 + 256) )
    v11 = 0xFFFFFFFFFFFFFF0LL;
  v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
  v13 = alloca(v12);
  v14 = alloca(v12);
  hKeya[1] = (HKEY)&cbData;
  if ( v9 == -256 || (v15 = 0, v10 > 0x7FFFFFFF) )
    v15 = -2147024809;
  if ( v15 < 0 )
  {
    if ( v9 != -256 )
      LOWORD(cbData) = 0;
  }
  else
  {
    v16 = 2147483646;
    p_cbData = &cbData;
    if ( v9 != -256 )
    {
      do
      {
        if ( !v16 )
          break;
        if ( !*a2 )
          break;
        *(_WORD *)p_cbData = *a2;
        p_cbData = (DWORD *)((char *)p_cbData + 2);
        ++a2;
        --v16;
        --v10;
      }
      while ( v10 );
    }
    v18 = (DWORD *)((char *)p_cbData - 2);
    if ( v10 )
      v18 = p_cbData;
    *(_WORD *)v18 = 0;
  }
  *((_WORD *)&cbData + v9) = 92;
  v19 = (WCHAR *)&cbData + v9 + 1;
  *v19 = 0;
  v20 = 1;
  cchName = 255;
  for ( result = RegEnumKeyExW(hKey, 0, v19, &cchName, 0, 0, 0, 0);
        !result;
        result = RegEnumKeyExW(hKey, v22, v19, &cchName, 0, 0, 0, 0) )
  {
    if ( RegOpenKeyExW(hKey, v19, 0, a3 | 9, hKeya) )
    {
      g_FileErrorStringID = 110;
    }
    else
    {
      g_FileErrorStringID = 0;
      PutBranch(hKeya[0]);
      result = RegCloseKey(hKeya[0]);
      if ( !v6 && !g_FileErrorStringID )
      {
        ++g_dwTotalKeysSaved;
        v6 = 1;
      }
      if ( g_FileErrorStringID == 802 )
        return result;
    }
    v22 = v20++;
    cchName = 255;
  }
  if ( result != 259 )
    g_FileErrorStringID = 30;
  return result;
}

```

## disassembly

```asm
0x14000be00  push    rbp
0x14000be02  push    rbx
0x14000be03  push    rsi
0x14000be04  push    rdi
0x14000be05  push    r12
0x14000be07  push    r13
0x14000be09  push    r14
0x14000be0b  push    r15
0x14000be0d  sub     rsp, 78h
0x14000be11  lea     rbp, [rsp+40h]
0x14000be16  mov     rax, cs:__security_cookie
0x14000be1d  xor     rax, rbp
0x14000be20  mov     [rbp+70h+var_48], rax
0x14000be24  mov     r13d, r8d
0x14000be27  mov     rsi, rdx
0x14000be2a  mov     r12, rcx
0x14000be2d  xor     r14d, r14d
0x14000be30  mov     [rbp+70h+hKey], r14
0x14000be34  mov     [rbp+70h+cchValueName], r14d
0x14000be38  mov     [rbp+70h+cbData], r14d
0x14000be3c  mov     [rbp+70h+Type], r14d
0x14000be40  mov     r15d, r14d
0x14000be43  lea     ecx, [r14+5Bh]
0x14000be47  call    PutChar
0x14000be4c  mov     rcx, rsi
0x14000be4f  call    PutLiteral
0x14000be54  lea     rcx, asc_14001117C; "]\n"
0x14000be5b  call    PutLiteral
0x14000be60  mov     edi, r14d
0x14000be63  mov     [rbp+70h+cchValueName], 100h
0x14000be6a  lea     rax, [rbp+70h+cbData]
0x14000be6e  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x14000be73  mov     [rsp+0B0h+lpData], r14; lpData
0x14000be78  lea     rax, [rbp+70h+Type]
0x14000be7c  mov     [rsp+0B0h+lpType], rax; lpType
0x14000be81  mov     [rsp+0B0h+lpReserved], r14; lpReserved
0x14000be86  lea     r9, [rbp+70h+cchValueName]; lpcchValueName
0x14000be8a  lea     r8, g_ValueNameBuffer; lpValueName
0x14000be91  mov     edx, edi; dwIndex
0x14000be93  mov     rcx, r12; hKey
0x14000be96  call    cs:__imp_RegEnumValueW
0x14000be9c  mov     ebx, eax
0x14000be9e  test    eax, eax
0x14000bea0  jz      loc_14000C09F
0x14000bea6  mov     ecx, 0Ah
0x14000beab  call    PutChar
0x14000beb0  cmp     ebx, 103h
0x14000beb6  jz      short loc_14000BEC2
0x14000beb8  mov     cs:g_FileErrorStringID, 1Eh
0x14000bec2  cmp     r15d, 1
0x14000bec6  jnz     short loc_14000BECE
0x14000bec8  inc     cs:g_dwTotalKeysSaved
0x14000bece  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000bed2  inc     r9
0x14000bed5  cmp     [rsi+r9*2], r14w
0x14000beda  jnz     short loc_14000BED2
0x14000bedc  lea     rdx, [r9+100h]
0x14000bee3  lea     rax, [rdx+rdx]
0x14000bee7  lea     rcx, [rax+0Fh]
0x14000beeb  cmp     rcx, rax
0x14000beee  ja      short loc_14000BEFA
0x14000bef0  mov     rcx, 0FFFFFFFFFFFFFF0h
0x14000befa  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000befe  mov     rax, rcx
0x14000bf01  call    _alloca_probe
0x14000bf06  sub     rsp, rcx
0x14000bf09  lea     rdi, [rsp+0B0h+cbData]
0x14000bf0e  mov     [rbp+70h+var_50], rdi
0x14000bf12  test    rdx, rdx
0x14000bf15  jz      short loc_14000BF23
0x14000bf17  mov     eax, r14d
0x14000bf1a  cmp     rdx, 7FFFFFFFh
0x14000bf21  jbe     short loc_14000BF28
0x14000bf23  mov     eax, 80070057h
0x14000bf28  test    eax, eax
0x14000bf2a  js      short loc_14000BF6E
0x14000bf2c  mov     ecx, 7FFFFFFEh
0x14000bf31  mov     rax, rdi
0x14000bf34  test    rdx, rdx
0x14000bf37  jz      short loc_14000BF5D
0x14000bf39  test    rcx, rcx
0x14000bf3c  jz      short loc_14000BF5D
0x14000bf3e  movzx   r8d, word ptr [rsi]
0x14000bf42  test    r8w, r8w
0x14000bf46  jz      short loc_14000BF5D
0x14000bf48  mov     [rax], r8w
0x14000bf4c  add     rax, 2
0x14000bf50  add     rsi, 2
0x14000bf54  dec     rcx
0x14000bf57  sub     rdx, 1
0x14000bf5b  jnz     short loc_14000BF39
0x14000bf5d  lea     rcx, [rax-2]
0x14000bf61  test    rdx, rdx
0x14000bf64  cmovnz  rcx, rax
0x14000bf68  mov     [rcx], r14w
0x14000bf6c  jmp     short loc_14000BF77
0x14000bf6e  test    rdx, rdx
0x14000bf71  jz      short loc_14000BF77
0x14000bf73  mov     [rdi], r14w
0x14000bf77  mov     word ptr [rdi+r9*2], 5Ch ; '\'
0x14000bf7e  inc     r9
0x14000bf81  lea     rsi, [rdi+r9*2]
0x14000bf85  mov     [rsi], r14w
0x14000bf89  mov     r14d, 1
0x14000bf8f  mov     [rbp+70h+cchName], 0FFh
0x14000bf96  xor     ebx, ebx
0x14000bf98  mov     [rsp+0B0h+lpcbData], rbx; lpftLastWriteTime
0x14000bf9d  mov     [rsp+0B0h+lpData], rbx; lpcchClass
0x14000bfa2  mov     [rsp+0B0h+lpType], rbx; lpClass
0x14000bfa7  mov     [rsp+0B0h+lpReserved], rbx; lpReserved
0x14000bfac  lea     r9, [rbp+70h+cchName]; lpcchName
0x14000bfb0  mov     r8, rsi; lpName
0x14000bfb3  xor     edx, edx; dwIndex
0x14000bfb5  mov     rcx, r12; hKey
0x14000bfb8  call    cs:__imp_RegEnumKeyExW
0x14000bfbe  test    eax, eax
0x14000bfc0  jnz     loc_14000C07A
0x14000bfc6  mov     ebx, r13d
0x14000bfc9  or      ebx, 9
0x14000bfcc  lea     rax, [rbp+70h+hKey]
0x14000bfd0  mov     [rsp+0B0h+lpReserved], rax; phkResult
0x14000bfd5  mov     r9d, ebx; samDesired
0x14000bfd8  xor     r8d, r8d; ulOptions
0x14000bfdb  mov     rdx, rsi; lpSubKey
0x14000bfde  mov     rcx, r12; hKey
0x14000bfe1  call    cs:__imp_RegOpenKeyExW
0x14000bfe7  xor     ecx, ecx
0x14000bfe9  test    eax, eax
0x14000bfeb  jnz     short loc_14000C037
0x14000bfed  mov     cs:g_FileErrorStringID, ecx
0x14000bff3  mov     r8d, r13d
0x14000bff6  mov     rdx, rdi
0x14000bff9  mov     rcx, [rbp+70h+hKey]; hKey
0x14000bffd  call    PutBranch
0x14000c002  mov     rcx, [rbp+70h+hKey]; hKey
0x14000c006  call    cs:__imp_RegCloseKey
0x14000c00c  xor     ecx, ecx
0x14000c00e  test    r15d, r15d
0x14000c011  jnz     short loc_14000C025
0x14000c013  cmp     cs:g_FileErrorStringID, ecx
0x14000c019  jnz     short loc_14000C025
0x14000c01b  inc     cs:g_dwTotalKeysSaved
0x14000c021  lea     r15d, [rcx+1]
0x14000c025  cmp     cs:g_FileErrorStringID, 322h
0x14000c02f  jz      loc_14000C1AF
0x14000c035  jmp     short loc_14000C041
0x14000c037  mov     cs:g_FileErrorStringID, 6Eh ; 'n'
0x14000c041  mov     edx, r14d; dwIndex
0x14000c044  inc     r14d
0x14000c047  mov     [rbp+70h+cchName], 0FFh
0x14000c04e  mov     [rsp+0B0h+lpcbData], rcx; lpftLastWriteTime
0x14000c053  mov     [rsp+0B0h+lpData], rcx; lpcchClass
0x14000c058  mov     [rsp+0B0h+lpType], rcx; lpClass
0x14000c05d  mov     [rsp+0B0h+lpReserved], rcx; lpReserved
0x14000c062  lea     r9, [rbp+70h+cchName]; lpcchName
0x14000c066  mov     r8, rsi; lpName
0x14000c069  mov     rcx, r12; hKey
0x14000c06c  call    cs:__imp_RegEnumKeyExW
0x14000c072  test    eax, eax
0x14000c074  jz      loc_14000BFCC
0x14000c07a  cmp     eax, 103h
0x14000c07f  jz      loc_14000C1AF
0x14000c085  mov     cs:g_FileErrorStringID, 1Eh
0x14000c08f  jmp     loc_14000C1AF
0x14000c094  call    cs:__imp__o__resetstkoflw
0x14000c09a  jmp     loc_14000C1AF
0x14000c09f  mov     cs:g_FileErrorStringID, r14d
0x14000c0a6  mov     ecx, [rbp+70h+Type]
0x14000c0a9  lea     eax, [rcx-1]
0x14000c0ac  cmp     eax, 1
0x14000c0af  jbe     short loc_14000C0B9
0x14000c0b1  cmp     ecx, 7
0x14000c0b4  mov     rax, r14
0x14000c0b7  jnz     short loc_14000C0BE
0x14000c0b9  mov     eax, 2
0x14000c0be  mov     edx, [rbp+70h+cbData]
0x14000c0c1  add     rdx, rax; uBytes
0x14000c0c4  mov     ecx, 40h ; '@'; uFlags
0x14000c0c9  call    cs:__imp_LocalAlloc
0x14000c0cf  mov     rbx, rax
0x14000c0d2  test    rax, rax
0x14000c0d5  jz      loc_14000C19D
0x14000c0db  lea     rax, [rbp+70h+cbData]
0x14000c0df  mov     [rsp+0B0h+lpType], rax; lpcbData
0x14000c0e4  mov     [rsp+0B0h+lpReserved], rbx; lpData
0x14000c0e9  lea     r9, [rbp+70h+Type]; lpType
0x14000c0ed  xor     r8d, r8d; lpReserved
0x14000c0f0  lea     rdx, g_ValueNameBuffer; lpValueName
0x14000c0f7  mov     rcx, r12; hKey
0x14000c0fa  call    cs:__imp_RegQueryValueExW
0x14000c100  test    eax, eax
0x14000c102  jz      short loc_14000C110
0x14000c104  mov     cs:g_FileErrorStringID, 322h
0x14000c10e  jmp     short loc_14000C18C
0x14000c110  cmp     [rbp+70h+cchValueName], r14d
0x14000c114  jz      short loc_14000C124
0x14000c116  lea     rcx, g_ValueNameBuffer
0x14000c11d  call    PutString
0x14000c122  jmp     short loc_14000C12E
0x14000c124  mov     ecx, 40h ; '@'
0x14000c129  call    PutChar
0x14000c12e  mov     ecx, 3Dh ; '='
0x14000c133  call    PutChar
0x14000c138  mov     edx, [rbp+70h+Type]
0x14000c13b  mov     eax, edx
0x14000c13d  sub     eax, 1
0x14000c140  jz      short loc_14000C17A
0x14000c142  sub     eax, 2
0x14000c145  jz      short loc_14000C16C
0x14000c147  cmp     eax, 1
0x14000c14a  jnz     short loc_14000C16C
0x14000c14c  cmp     [rbp+70h+cbData], 4
0x14000c150  jnz     short loc_14000C16C
0x14000c152  lea     rcx, s_DwordPrefix; "dword:"
0x14000c159  call    PutLiteral
0x14000c15e  mov     edx, 1
0x14000c163  mov     ecx, [rbx]
0x14000c165  call    PutDword
0x14000c16a  jmp     short loc_14000C182
0x14000c16c  mov     r8d, [rbp+70h+cbData]
0x14000c170  mov     rcx, rbx
0x14000c173  call    PutBinary
0x14000c178  jmp     short loc_14000C182
0x14000c17a  mov     rcx, rbx
0x14000c17d  call    PutString
0x14000c182  mov     ecx, 0Ah
0x14000c187  call    PutChar
0x14000c18c  mov     rcx, rbx; hMem
0x14000c18f  call    cs:__imp_LocalFree
0x14000c195  mov     eax, cs:g_FileErrorStringID
0x14000c19b  jmp     short loc_14000C1A8
0x14000c19d  mov     eax, 322h
0x14000c1a2  mov     cs:g_FileErrorStringID, eax
0x14000c1a8  cmp     eax, 322h
0x14000c1ad  jnz     short loc_14000C1CC
0x14000c1af  mov     rcx, [rbp+70h+var_48]
0x14000c1b3  xor     rcx, rbp; StackCookie
0x14000c1b6  call    __security_check_cookie
0x14000c1bb  lea     rsp, [rbp+38h]
0x14000c1bf  pop     r15
0x14000c1c1  pop     r14
0x14000c1c3  pop     r13
0x14000c1c5  pop     r12
0x14000c1c7  pop     rdi
0x14000c1c8  pop     rsi
0x14000c1c9  pop     rbx
0x14000c1ca  pop     rbp
0x14000c1cb  retn
0x14000c1cc  inc     edi
0x14000c1ce  test    eax, eax
0x14000c1d0  jnz     loc_14000BE63
0x14000c1d6  lea     r15d, [rax+1]
0x14000c1da  jmp     loc_14000BE63
0x14000eece  push    rbp
0x14000eed0  sub     rsp, 40h
0x14000eed4  lea     rbp, [rdx+40h]
0x14000eed8  mov     rax, [rcx]
0x14000eedb  xor     ecx, ecx
0x14000eedd  cmp     dword ptr [rax], 0C00000FDh
0x14000eee3  setz    cl
0x14000eee6  mov     eax, ecx
0x14000eee8  add     rsp, 40h
0x14000eeec  pop     rbp
0x14000eeed  retn
```
