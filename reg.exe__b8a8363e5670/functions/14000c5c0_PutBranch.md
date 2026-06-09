# PutBranch

- ea: `0x14000c5c0`
- end: `0x14000c9d6`
- name: `PutBranch`
- size: `1046`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000afd4`
- `0x14000c5c0`

## callees

- `0x140001340`
- `0x14000c500`
- `0x14000c5c0`
- `0x14000c9dc`
- `0x14000ca40`
- `0x14000caac`
- `0x14000cadc`
- `0x14000fa80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x14000c872`
- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x14000c872`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14000c656`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14000c656`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000c7ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000c7ad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000c8e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000c8e4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000c77e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000c844`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000c77e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000c844`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c7d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c7d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c97f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c97f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000c8ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000c8ad`

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
  unsigned __int16 *v24; // rbx
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
    v24 = (unsigned __int16 *)LocalAlloc(0x40u, v23 + cbData);
    if ( v24 )
    {
      if ( RegQueryValueExW(hKey, &g_ValueNameBuffer, 0, &Type, (LPBYTE)v24, &cbData) )
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
0x14000c5c0  push    rbp
0x14000c5c2  push    rbx
0x14000c5c3  push    rsi
0x14000c5c4  push    rdi
0x14000c5c5  push    r12
0x14000c5c7  push    r13
0x14000c5c9  push    r14
0x14000c5cb  push    r15
0x14000c5cd  sub     rsp, 78h
0x14000c5d1  lea     rbp, [rsp+40h]
0x14000c5d6  mov     rax, cs:__security_cookie
0x14000c5dd  xor     rax, rbp
0x14000c5e0  mov     [rbp+70h+var_48], rax
0x14000c5e4  mov     r13d, r8d
0x14000c5e7  mov     rsi, rdx
0x14000c5ea  mov     r12, rcx
0x14000c5ed  xor     r14d, r14d
0x14000c5f0  mov     [rbp+70h+hKey], r14
0x14000c5f4  mov     [rbp+70h+cchValueName], r14d
0x14000c5f8  mov     [rbp+70h+cbData], r14d
0x14000c5fc  mov     [rbp+70h+Type], r14d
0x14000c600  mov     r15d, r14d
0x14000c603  lea     ecx, [r14+5Bh]
0x14000c607  call    PutChar
0x14000c60c  mov     rcx, rsi
0x14000c60f  call    PutLiteral
0x14000c614  lea     rcx, asc_14001217C; "]\n"
0x14000c61b  call    PutLiteral
0x14000c620  mov     edi, r14d
0x14000c623  mov     [rbp+70h+cchValueName], 100h
0x14000c62a  lea     rax, [rbp+70h+cbData]
0x14000c62e  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x14000c633  mov     [rsp+0B0h+lpData], r14; lpData
0x14000c638  lea     rax, [rbp+70h+Type]
0x14000c63c  mov     [rsp+0B0h+lpType], rax; lpType
0x14000c641  mov     [rsp+0B0h+lpReserved], r14; lpReserved
0x14000c646  lea     r9, [rbp+70h+cchValueName]; lpcchValueName
0x14000c64a  lea     r8, g_ValueNameBuffer; lpValueName
0x14000c651  mov     edx, edi; dwIndex
0x14000c653  mov     rcx, r12; hKey
0x14000c656  call    cs:__imp_RegEnumValueW
0x14000c65d  nop     dword ptr [rax+rax+00h]
0x14000c662  mov     ebx, eax
0x14000c664  test    eax, eax
0x14000c666  jz      loc_14000C883
0x14000c66c  mov     ecx, 0Ah
0x14000c671  call    PutChar
0x14000c676  cmp     ebx, 103h
0x14000c67c  jz      short loc_14000C688
0x14000c67e  mov     cs:g_FileErrorStringID, 1Eh
0x14000c688  cmp     r15d, 1
0x14000c68c  jnz     short loc_14000C694
0x14000c68e  inc     cs:g_dwTotalKeysSaved
0x14000c694  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000c698  inc     r9
0x14000c69b  cmp     [rsi+r9*2], r14w
0x14000c6a0  jnz     short loc_14000C698
0x14000c6a2  lea     rdx, [r9+100h]
0x14000c6a9  lea     rax, [rdx+rdx]
0x14000c6ad  lea     rcx, [rax+0Fh]
0x14000c6b1  cmp     rcx, rax
0x14000c6b4  ja      short loc_14000C6C0
0x14000c6b6  mov     rcx, 0FFFFFFFFFFFFFF0h
0x14000c6c0  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000c6c4  mov     rax, rcx
0x14000c6c7  call    _alloca_probe
0x14000c6cc  sub     rsp, rcx
0x14000c6cf  lea     rdi, [rsp+0B0h+cbData]
0x14000c6d4  mov     [rbp+70h+var_50], rdi
0x14000c6d8  test    rdx, rdx
0x14000c6db  jz      short loc_14000C6E9
0x14000c6dd  mov     eax, r14d
0x14000c6e0  cmp     rdx, 7FFFFFFFh
0x14000c6e7  jbe     short loc_14000C6EE
0x14000c6e9  mov     eax, 80070057h
0x14000c6ee  test    eax, eax
0x14000c6f0  js      short loc_14000C734
0x14000c6f2  mov     ecx, 7FFFFFFEh
0x14000c6f7  mov     rax, rdi
0x14000c6fa  test    rdx, rdx
0x14000c6fd  jz      short loc_14000C723
0x14000c6ff  test    rcx, rcx
0x14000c702  jz      short loc_14000C723
0x14000c704  movzx   r8d, word ptr [rsi]
0x14000c708  test    r8w, r8w
0x14000c70c  jz      short loc_14000C723
0x14000c70e  mov     [rax], r8w
0x14000c712  add     rax, 2
0x14000c716  add     rsi, 2
0x14000c71a  dec     rcx
0x14000c71d  sub     rdx, 1
0x14000c721  jnz     short loc_14000C6FF
0x14000c723  lea     rcx, [rax-2]
0x14000c727  test    rdx, rdx
0x14000c72a  cmovnz  rcx, rax
0x14000c72e  mov     [rcx], r14w
0x14000c732  jmp     short loc_14000C73D
0x14000c734  test    rdx, rdx
0x14000c737  jz      short loc_14000C73D
0x14000c739  mov     [rdi], r14w
0x14000c73d  mov     word ptr [rdi+r9*2], 5Ch ; '\'
0x14000c744  inc     r9
0x14000c747  lea     rsi, [rdi+r9*2]
0x14000c74b  mov     [rsi], r14w
0x14000c74f  mov     r14d, 1
0x14000c755  mov     [rbp+70h+cchName], 0FFh
0x14000c75c  xor     ebx, ebx
0x14000c75e  mov     [rsp+0B0h+lpcbData], rbx; lpftLastWriteTime
0x14000c763  mov     [rsp+0B0h+lpData], rbx; lpcchClass
0x14000c768  mov     [rsp+0B0h+lpType], rbx; lpClass
0x14000c76d  mov     [rsp+0B0h+lpReserved], rbx; lpReserved
0x14000c772  lea     r9, [rbp+70h+cchName]; lpcchName
0x14000c776  mov     r8, rsi; lpName
0x14000c779  xor     edx, edx; dwIndex
0x14000c77b  mov     rcx, r12; hKey
0x14000c77e  call    cs:__imp_RegEnumKeyExW
0x14000c785  nop     dword ptr [rax+rax+00h]
0x14000c78a  test    eax, eax
0x14000c78c  jnz     loc_14000C858
0x14000c792  mov     ebx, r13d
0x14000c795  or      ebx, 9
0x14000c798  lea     rax, [rbp+70h+hKey]
0x14000c79c  mov     [rsp+0B0h+lpReserved], rax; phkResult
0x14000c7a1  mov     r9d, ebx; samDesired
0x14000c7a4  xor     r8d, r8d; ulOptions
0x14000c7a7  mov     rdx, rsi; lpSubKey
0x14000c7aa  mov     rcx, r12; hKey
0x14000c7ad  call    cs:__imp_RegOpenKeyExW
0x14000c7b4  nop     dword ptr [rax+rax+00h]
0x14000c7b9  xor     ecx, ecx
0x14000c7bb  test    eax, eax
0x14000c7bd  jnz     short loc_14000C80F
0x14000c7bf  mov     cs:g_FileErrorStringID, ecx
0x14000c7c5  mov     r8d, r13d
0x14000c7c8  mov     rdx, rdi
0x14000c7cb  mov     rcx, [rbp+70h+hKey]; hKey
0x14000c7cf  call    PutBranch
0x14000c7d4  mov     rcx, [rbp+70h+hKey]; hKey
0x14000c7d8  call    cs:__imp_RegCloseKey
0x14000c7df  nop     dword ptr [rax+rax+00h]
0x14000c7e4  xor     ecx, ecx
0x14000c7e6  test    r15d, r15d
0x14000c7e9  jnz     short loc_14000C7FD
0x14000c7eb  cmp     cs:g_FileErrorStringID, ecx
0x14000c7f1  jnz     short loc_14000C7FD
0x14000c7f3  inc     cs:g_dwTotalKeysSaved
0x14000c7f9  lea     r15d, [rcx+1]
0x14000c7fd  cmp     cs:g_FileErrorStringID, 322h
0x14000c807  jz      loc_14000C9A5
0x14000c80d  jmp     short loc_14000C819
0x14000c80f  mov     cs:g_FileErrorStringID, 6Eh ; 'n'
0x14000c819  mov     edx, r14d; dwIndex
0x14000c81c  inc     r14d
0x14000c81f  mov     [rbp+70h+cchName], 0FFh
0x14000c826  mov     [rsp+0B0h+lpcbData], rcx; lpftLastWriteTime
0x14000c82b  mov     [rsp+0B0h+lpData], rcx; lpcchClass
0x14000c830  mov     [rsp+0B0h+lpType], rcx; lpClass
0x14000c835  mov     [rsp+0B0h+lpReserved], rcx; lpReserved
0x14000c83a  lea     r9, [rbp+70h+cchName]; lpcchName
0x14000c83e  mov     r8, rsi; lpName
0x14000c841  mov     rcx, r12; hKey
0x14000c844  call    cs:__imp_RegEnumKeyExW
0x14000c84b  nop     dword ptr [rax+rax+00h]
0x14000c850  test    eax, eax
0x14000c852  jz      loc_14000C798
0x14000c858  cmp     eax, 103h
0x14000c85d  jz      loc_14000C9A5
0x14000c863  mov     cs:g_FileErrorStringID, 1Eh
0x14000c86d  jmp     loc_14000C9A5
0x14000c872  call    cs:__imp__o__resetstkoflw
0x14000c879  nop     dword ptr [rax+rax+00h]
0x14000c87e  jmp     loc_14000C9A5
0x14000c883  mov     cs:g_FileErrorStringID, r14d
0x14000c88a  mov     ecx, [rbp+70h+Type]
0x14000c88d  lea     eax, [rcx-1]
0x14000c890  cmp     eax, 1
0x14000c893  jbe     short loc_14000C89D
0x14000c895  cmp     ecx, 7
0x14000c898  mov     rax, r14
0x14000c89b  jnz     short loc_14000C8A2
0x14000c89d  mov     eax, 2
0x14000c8a2  mov     edx, [rbp+70h+cbData]
0x14000c8a5  add     rdx, rax; uBytes
0x14000c8a8  mov     ecx, 40h ; '@'; uFlags
0x14000c8ad  call    cs:__imp_LocalAlloc
0x14000c8b4  nop     dword ptr [rax+rax+00h]
0x14000c8b9  mov     rbx, rax
0x14000c8bc  test    rax, rax
0x14000c8bf  jz      loc_14000C993
0x14000c8c5  lea     rax, [rbp+70h+cbData]
0x14000c8c9  mov     [rsp+0B0h+lpType], rax; lpcbData
0x14000c8ce  mov     [rsp+0B0h+lpReserved], rbx; lpData
0x14000c8d3  lea     r9, [rbp+70h+Type]; lpType
0x14000c8d7  xor     r8d, r8d; lpReserved
0x14000c8da  lea     rdx, g_ValueNameBuffer; lpValueName
0x14000c8e1  mov     rcx, r12; hKey
0x14000c8e4  call    cs:__imp_RegQueryValueExW
0x14000c8eb  nop     dword ptr [rax+rax+00h]
0x14000c8f0  test    eax, eax
0x14000c8f2  jz      short loc_14000C900
0x14000c8f4  mov     cs:g_FileErrorStringID, 322h
0x14000c8fe  jmp     short loc_14000C97C
0x14000c900  cmp     [rbp+70h+cchValueName], r14d
0x14000c904  jz      short loc_14000C914
0x14000c906  lea     rcx, g_ValueNameBuffer
0x14000c90d  call    PutString
0x14000c912  jmp     short loc_14000C91E
0x14000c914  mov     ecx, 40h ; '@'
0x14000c919  call    PutChar
0x14000c91e  mov     ecx, 3Dh ; '='
0x14000c923  call    PutChar
0x14000c928  mov     edx, [rbp+70h+Type]
0x14000c92b  mov     eax, edx
0x14000c92d  sub     eax, 1
0x14000c930  jz      short loc_14000C96A
0x14000c932  sub     eax, 2
0x14000c935  jz      short loc_14000C95C
0x14000c937  cmp     eax, 1
0x14000c93a  jnz     short loc_14000C95C
0x14000c93c  cmp     [rbp+70h+cbData], 4
0x14000c940  jnz     short loc_14000C95C
0x14000c942  lea     rcx, s_DwordPrefix; "dword:"
0x14000c949  call    PutLiteral
0x14000c94e  mov     edx, 1
0x14000c953  mov     ecx, [rbx]
0x14000c955  call    PutDword
0x14000c95a  jmp     short loc_14000C972
0x14000c95c  mov     r8d, [rbp+70h+cbData]
0x14000c960  mov     rcx, rbx
0x14000c963  call    PutBinary
0x14000c968  jmp     short loc_14000C972
0x14000c96a  mov     rcx, rbx
0x14000c96d  call    PutString
0x14000c972  mov     ecx, 0Ah
0x14000c977  call    PutChar
0x14000c97c  mov     rcx, rbx; hMem
0x14000c97f  call    cs:__imp_LocalFree
0x14000c986  nop     dword ptr [rax+rax+00h]
0x14000c98b  mov     eax, cs:g_FileErrorStringID
0x14000c991  jmp     short loc_14000C99E
0x14000c993  mov     eax, 322h
0x14000c998  mov     cs:g_FileErrorStringID, eax
0x14000c99e  cmp     eax, 322h
0x14000c9a3  jnz     short loc_14000C9C3
0x14000c9a5  mov     rcx, [rbp+70h+var_48]
0x14000c9a9  xor     rcx, rbp; StackCookie
0x14000c9ac  call    __security_check_cookie
0x14000c9b1  lea     rsp, [rbp+38h]
0x14000c9b5  pop     r15
0x14000c9b7  pop     r14
0x14000c9b9  pop     r13
0x14000c9bb  pop     r12
0x14000c9bd  pop     rdi
0x14000c9be  pop     rsi
0x14000c9bf  pop     rbx
0x14000c9c0  pop     rbp
0x14000c9c1  retn
0x14000c9c3  inc     edi
0x14000c9c5  test    eax, eax
0x14000c9c7  jnz     loc_14000C623
0x14000c9cd  lea     r15d, [rax+1]
0x14000c9d1  jmp     loc_14000C623
0x14000fb7e  push    rbp
0x14000fb80  sub     rsp, 40h
0x14000fb84  lea     rbp, [rdx+40h]
0x14000fb88  mov     rax, [rcx]
0x14000fb8b  xor     ecx, ecx
0x14000fb8d  cmp     dword ptr [rax], 0C00000FDh
0x14000fb93  setz    cl
0x14000fb96  mov     eax, ecx
0x14000fb98  add     rsp, 40h
0x14000fb9c  pop     rbp
0x14000fb9d  retn
```
