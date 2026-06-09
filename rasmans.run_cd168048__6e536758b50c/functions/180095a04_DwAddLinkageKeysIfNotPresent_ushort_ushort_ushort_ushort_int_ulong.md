# DwAddLinkageKeysIfNotPresent(ushort *,ushort *,ushort *,ushort *,int *,ulong)

- ea: `0x180095a04`
- end: `0x180095bd5`
- name: `?DwAddLinkageKeysIfNotPresent@@YAKPEAG000PEAHK@Z`
- size: `465`
- prototype: `unsigned int(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int *, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180095354`
- `0x1800956ac`
- `0x180095efc`
- `0x1800960f8`

## callees

- `0x18000eae0`
- `0x180056178`
- `0x180095a04`
- `0x180097938`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095a54`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095a54`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180095b8a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180095b8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095ba1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095ba1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095bb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095bb5`

## pseudocode

```c
__int64 __fastcall DwAddLinkageKeysIfNotPresent(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int *a5,
        unsigned int a6)
{
  BYTE *v8; // rbx
  unsigned int v9; // esi
  unsigned int v10; // r8d
  unsigned int v11; // eax
  unsigned __int64 v12; // r11
  int v13; // r14d
  STRSAFE_LPWSTR v14; // rdi
  __int64 v15; // r9
  unsigned __int64 v16; // rax
  char *v17; // rcx
  unsigned __int16 *v18; // rax
  signed __int64 v19; // rcx
  int v20; // edx
  int v21; // r8d
  size_t v22; // r11
  BYTE *v23; // rax
  bool v24; // zf
  _WORD *v25; // rcx
  unsigned int v27; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v28; // [rsp+44h] [rbp-24h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-20h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+50h] [rbp-18h] BYREF

  hKey = 0;
  v28 = 0;
  v8 = 0;
  *a5 = 0;
  pszDest = 0;
  v27 = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0xF003Fu, &hKey);
  if ( !v9 )
  {
    v11 = RegQueryValueWithAllocW(hKey, a3, v10, (unsigned __int8 **)&pszDest, &v27, &v28, a6);
    v8 = (BYTE *)pszDest;
    v9 = v11;
    if ( !v11 )
    {
      v12 = v27;
      v13 = 2;
      v14 = pszDest;
      if ( *pszDest )
      {
        while ( 1 )
        {
          v15 = -1;
          do
            ++v15;
          while ( v14[v15] );
          v16 = -1;
          do
            ++v16;
          while ( a4[v16] );
          if ( (unsigned int)v15 >= v16 )
          {
            v17 = (char *)&v14[v16];
            if ( *(_WORD *)v17 == 123 )
            {
              v18 = a1;
              v19 = v17 - (char *)a1;
              do
              {
                v20 = *(unsigned __int16 *)((char *)v18 + v19);
                v21 = *v18 - v20;
                if ( v21 )
                  break;
                ++v18;
              }
              while ( v20 );
              if ( !v21 )
                break;
            }
          }
          v14 += (unsigned int)v15 + 1;
          v12 = (unsigned int)(-2 - 2 * v15 + v12);
          if ( !*v14 )
            goto LABEL_17;
        }
        *a5 = 1;
      }
LABEL_17:
      if ( !*a5 )
      {
        StringCchCopyW(v14, v12 >> 1, a4);
        StringCchCatW(v14, v22, a1);
        v23 = v8;
        while ( 1 )
        {
          v24 = *(_WORD *)v23 == 0;
          v25 = v23 + 2;
          v23 += 2;
          if ( v24 && !*v25 )
            break;
          ++v13;
        }
        v9 = RegSetValueExW(hKey, a3, 0, 7u, v8, 2 * v13);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v8 )
    LocalFree(v8);
  return v9;
}

```

## disassembly

```asm
0x180095a04  mov     [rsp-40h+pszSrc], rcx
0x180095a09  push    rbp
0x180095a0a  push    rbx
0x180095a0b  push    rsi
0x180095a0c  push    rdi
0x180095a0d  push    r12
0x180095a0f  push    r13
0x180095a11  push    r14
0x180095a13  push    r15
0x180095a15  mov     rbp, rsp
0x180095a18  sub     rsp, 68h
0x180095a1c  mov     r15, [rbp+arg_20]
0x180095a20  lea     rax, [rbp+hKey]
0x180095a24  xor     edi, edi
0x180095a26  mov     [rsp+68h+phkResult], rax; phkResult
0x180095a2b  mov     r13, r9
0x180095a2e  mov     [rbp+hKey], rdi
0x180095a32  mov     r12, r8
0x180095a35  mov     [rbp+var_24], edi
0x180095a38  mov     ebx, edi
0x180095a3a  mov     [r15], edi
0x180095a3d  mov     r9d, 0F003Fh; samDesired
0x180095a43  mov     [rbp+pszDest], rbx
0x180095a47  xor     r8d, r8d; ulOptions
0x180095a4a  mov     [rbp+var_28], edi
0x180095a4d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180095a54  call    cs:__imp_RegOpenKeyExW
0x180095a5b  nop     dword ptr [rax+rax+00h]
0x180095a60  mov     esi, eax
0x180095a62  test    eax, eax
0x180095a64  jnz     loc_180095B98
0x180095a6a  mov     eax, [rbp+arg_28]
0x180095a6d  lea     r9, [rbp+pszDest]; unsigned __int8 **
0x180095a71  mov     rcx, [rbp+hKey]; hKey
0x180095a75  mov     rdx, r12; lpValueName
0x180095a78  mov     [rsp+68h+var_38], eax; unsigned int
0x180095a7c  lea     rax, [rbp+var_24]
0x180095a80  mov     qword ptr [rsp+68h+cbData], rax; unsigned int *
0x180095a85  lea     rax, [rbp+var_28]
0x180095a89  mov     [rsp+68h+phkResult], rax; unsigned int *
0x180095a8e  call    ?RegQueryValueWithAllocW@@YAKPEAUHKEY__@@PEAGKPEAPEAEPEAK3K@Z; RegQueryValueWithAllocW(HKEY__ *,ushort *,ulong,uchar * *,ulong *,ulong *,ulong)
0x180095a93  mov     rbx, [rbp+pszDest]
0x180095a97  mov     esi, eax
0x180095a99  test    eax, eax
0x180095a9b  jnz     loc_180095B98
0x180095aa1  mov     r11d, [rbp+var_28]
0x180095aa5  lea     r14d, [rax+2]
0x180095aa9  xor     ecx, ecx
0x180095aab  mov     rdi, rbx
0x180095aae  cmp     [rbx], cx
0x180095ab1  jz      short loc_180095B2D
0x180095ab3  or      r9, 0FFFFFFFFFFFFFFFFh
0x180095ab7  inc     r9
0x180095aba  cmp     [rdi+r9*2], cx
0x180095abf  jnz     short loc_180095AB7
0x180095ac1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180095ac5  inc     rax
0x180095ac8  cmp     [r13+rax*2+0], cx
0x180095ace  jnz     short loc_180095AC5
0x180095ad0  mov     r10d, r9d
0x180095ad3  cmp     r10, rax
0x180095ad6  jb      short loc_180095B08
0x180095ad8  lea     rcx, [rdi+rax*2]
0x180095adc  mov     eax, 7Bh ; '{'
0x180095ae1  cmp     ax, [rcx]
0x180095ae4  jnz     short loc_180095B08
0x180095ae6  mov     rax, [rbp+pszSrc]
0x180095aea  sub     rcx, rax
0x180095aed  movzx   r8d, word ptr [rax]
0x180095af1  movzx   edx, word ptr [rax+rcx]
0x180095af5  sub     r8d, edx
0x180095af8  jnz     short loc_180095B01
0x180095afa  add     rax, r14
0x180095afd  test    edx, edx
0x180095aff  jnz     short loc_180095AED
0x180095b01  xor     ecx, ecx
0x180095b03  test    r8d, r8d
0x180095b06  jz      short loc_180095B26
0x180095b08  mov     ecx, 0FFFFFFFEh
0x180095b0d  lea     rdi, [rdi+r10*2]
0x180095b11  lea     eax, [r9+r9]
0x180095b15  add     rdi, r14
0x180095b18  sub     ecx, eax
0x180095b1a  add     r11d, ecx
0x180095b1d  xor     ecx, ecx
0x180095b1f  cmp     [rdi], cx
0x180095b22  jnz     short loc_180095AB3
0x180095b24  jmp     short loc_180095B2D
0x180095b26  mov     dword ptr [r15], 1
0x180095b2d  cmp     [r15], ecx
0x180095b30  jnz     short loc_180095B98
0x180095b32  shr     r11, 1
0x180095b35  mov     r8, r13; pszSrc
0x180095b38  mov     rdx, r11; cchDest
0x180095b3b  mov     rcx, rdi; pszDest
0x180095b3e  call    StringCchCopyW
0x180095b43  mov     r8, [rbp+pszSrc]; pszSrc
0x180095b47  mov     rdx, r11; cchDest
0x180095b4a  mov     rcx, rdi; pszDest
0x180095b4d  call    StringCchCatW
0x180095b52  mov     rax, rbx
0x180095b55  xor     edi, edi
0x180095b57  cmp     [rax], di
0x180095b5a  lea     rcx, [rax+2]
0x180095b5e  mov     rax, rcx
0x180095b61  jnz     short loc_180095B68
0x180095b63  cmp     [rcx], di
0x180095b66  jz      short loc_180095B6D
0x180095b68  inc     r14d
0x180095b6b  jmp     short loc_180095B57
0x180095b6d  mov     rcx, [rbp+hKey]; hKey
0x180095b71  lea     eax, [r14+r14]
0x180095b75  mov     [rsp+68h+cbData], eax; cbData
0x180095b79  mov     r9d, 7; dwType
0x180095b7f  xor     r8d, r8d; Reserved
0x180095b82  mov     [rsp+68h+phkResult], rbx; lpData
0x180095b87  mov     rdx, r12; lpValueName
0x180095b8a  call    cs:__imp_RegSetValueExW
0x180095b91  nop     dword ptr [rax+rax+00h]
0x180095b96  mov     esi, eax
0x180095b98  mov     rcx, [rbp+hKey]; hKey
0x180095b9c  test    rcx, rcx
0x180095b9f  jz      short loc_180095BAD
0x180095ba1  call    cs:__imp_RegCloseKey
0x180095ba8  nop     dword ptr [rax+rax+00h]
0x180095bad  test    rbx, rbx
0x180095bb0  jz      short loc_180095BC1
0x180095bb2  mov     rcx, rbx; hMem
0x180095bb5  call    cs:__imp_LocalFree
0x180095bbc  nop     dword ptr [rax+rax+00h]
0x180095bc1  mov     eax, esi
0x180095bc3  add     rsp, 68h
0x180095bc7  pop     r15
0x180095bc9  pop     r14
0x180095bcb  pop     r13
0x180095bcd  pop     r12
0x180095bcf  pop     rdi
0x180095bd0  pop     rsi
0x180095bd1  pop     rbx
0x180095bd2  pop     rbp
0x180095bd3  retn
```
