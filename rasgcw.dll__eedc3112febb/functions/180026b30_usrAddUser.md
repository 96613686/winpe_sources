# usrAddUser

- ea: `0x180026b30`
- end: `0x180026ca8`
- name: `usrAddUser`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180023bac`

## callees

- `0x180021438`
- `0x180021c04`
- `0x180026710`
- `0x180026b30`
- `0x180026e14`
- `0x180027874`
- `0x18002bf2c`
- `0x18002c1b0`

## import_xrefs

- `msvcrt!qsort` at `0x180026c5b`
- `msvcrt!qsort` at `0x180026c5b`

## string_xrefs

- `0x180026c0d`: `usrAddUser: StringCchCopyExW 0x%08x`

## pseudocode

```c
__int64 __fastcall usrAddUser(__int64 a1, const WCHAR *a2, __int64 *a3)
{
  unsigned int v6; // edi
  int v7; // eax
  unsigned int v8; // edx
  __int64 result; // rax
  __int64 v10; // rdi
  __int64 v11; // rsi
  wchar_t *v12; // rax
  STRSAFE_LPWSTR *v13; // r9
  HRESULT v14; // eax
  unsigned __int16 v15; // si
  __int64 v16; // rdx
  _BYTE *v17; // rax
  size_t *v18; // [rsp+20h] [rbp-48h]

  if ( !a1 || !a2 )
    return 87;
  v6 = 0;
  if ( *(_DWORD *)(a1 + 8) )
  {
    while ( 1 )
    {
      v7 = CompareStringWrapW(*(PCNZWCH *)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL * v6) + 8LL), a2);
      if ( !v7 )
        return 183;
      if ( v7 <= 0 && ++v6 < *(_DWORD *)(a1 + 8) )
        continue;
      goto LABEL_7;
    }
  }
  else
  {
LABEL_7:
    v8 = *(_DWORD *)(a1 + 12);
    if ( *(_DWORD *)(a1 + 8) + 1 < v8 || (result = usrResizeCache(a1, v8 + 50), !(_DWORD)result) )
    {
      v10 = RassrvAlloc(800, 1);
      if ( !v10 )
        return 8;
      v11 = -1;
      do
        ++v11;
      while ( a2[v11] );
      v12 = (wchar_t *)RassrvAlloc((unsigned int)(2 * v11 + 2), 0);
      *(_QWORD *)(v10 + 8) = v12;
      if ( v12 )
      {
        v14 = StringCchCopyExW(v12, (unsigned int)(v11 + 1), a2, v13, v18, 0x900u);
        v15 = v14;
        if ( v14 >= 0 )
        {
          usrEnableDialin(v10, 1);
          *(_BYTE *)(v10 + 797) |= 9u;
          *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL * (unsigned int)(*(_DWORD *)(a1 + 8))++) = v10;
          qsort(*(void **)(a1 + 40), *(unsigned int *)(a1 + 8), 8u, usrCompareUsers);
          if ( a3 )
            *a3 = v10;
          v16 = 514;
          v17 = (_BYTE *)(v10 + 24);
          do
          {
            *v17++ = 0;
            --v16;
          }
          while ( v16 );
          EncryptMemoryInPlace((LPVOID)(v10 + 24), 0x200u);
          return 0;
        }
        else
        {
          DbgOutputTrace("usrAddUser: StringCchCopyExW 0x%08x", v14);
          return v15;
        }
      }
      else
      {
        return 8;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180026b30  push    rbx
0x180026b32  push    rbp
0x180026b33  push    rsi
0x180026b34  push    rdi
0x180026b35  push    r14
0x180026b37  push    r15
0x180026b39  sub     rsp, 38h
0x180026b3d  xor     r15d, r15d
0x180026b40  mov     r14, r8
0x180026b43  mov     rbp, rdx
0x180026b46  mov     rbx, rcx
0x180026b49  test    rcx, rcx
0x180026b4c  jz      loc_180026C96
0x180026b52  test    rdx, rdx
0x180026b55  jz      loc_180026C96
0x180026b5b  mov     edi, r15d
0x180026b5e  cmp     [rcx+8], r15d
0x180026b62  jbe     short loc_180026B8B
0x180026b64  mov     rax, [rbx+28h]
0x180026b68  mov     rdx, rbp; lpString2
0x180026b6b  mov     ecx, edi
0x180026b6d  mov     rcx, [rax+rcx*8]
0x180026b71  mov     rcx, [rcx+8]; lpString1
0x180026b75  call    CompareStringWrapW
0x180026b7a  test    eax, eax
0x180026b7c  jz      loc_180026C1E
0x180026b82  jg      short loc_180026B8B
0x180026b84  inc     edi
0x180026b86  cmp     edi, [rbx+8]
0x180026b89  jb      short loc_180026B64
0x180026b8b  mov     eax, [rbx+8]
0x180026b8e  mov     edx, [rbx+0Ch]
0x180026b91  inc     eax
0x180026b93  cmp     eax, edx
0x180026b95  jb      short loc_180026BAA
0x180026b97  add     edx, 32h ; '2'
0x180026b9a  mov     rcx, rbx
0x180026b9d  call    usrResizeCache
0x180026ba2  test    eax, eax
0x180026ba4  jnz     loc_180026C9B
0x180026baa  mov     edx, 1
0x180026baf  mov     ecx, 320h
0x180026bb4  call    RassrvAlloc
0x180026bb9  mov     rdi, rax
0x180026bbc  test    rax, rax
0x180026bbf  jz      loc_180026C8F
0x180026bc5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180026bc9  inc     rsi
0x180026bcc  cmp     [rbp+rsi*2+0], r15w
0x180026bd2  jnz     short loc_180026BC9
0x180026bd4  lea     ecx, ds:2[rsi*2]
0x180026bdb  xor     edx, edx
0x180026bdd  call    RassrvAlloc
0x180026be2  mov     [rdi+8], rax
0x180026be6  test    rax, rax
0x180026be9  jz      loc_180026C8F
0x180026bef  lea     edx, [rsi+1]; cchDest
0x180026bf2  mov     [rsp+68h+dwFlags], 900h; dwFlags
0x180026bfa  mov     r8, rbp; pszSrc
0x180026bfd  mov     rcx, rax; pszDest
0x180026c00  call    StringCchCopyExW
0x180026c05  mov     esi, eax
0x180026c07  test    eax, eax
0x180026c09  jns     short loc_180026C25
0x180026c0b  mov     edx, eax
0x180026c0d  lea     rcx, aUsradduserStri; "usrAddUser: StringCchCopyExW 0x%08x"
0x180026c14  call    DbgOutputTrace
0x180026c19  movzx   eax, si
0x180026c1c  jmp     short loc_180026C9B
0x180026c1e  mov     eax, 0B7h
0x180026c23  jmp     short loc_180026C9B
0x180026c25  mov     edx, 1
0x180026c2a  mov     rcx, rdi
0x180026c2d  call    usrEnableDialin
0x180026c32  or      byte ptr [rdi+31Dh], 9
0x180026c39  lea     r9, usrCompareUsers; CompareFunction
0x180026c40  mov     ecx, [rbx+8]
0x180026c43  mov     r8d, 8; SizeOfElements
0x180026c49  mov     rax, [rbx+28h]
0x180026c4d  mov     [rax+rcx*8], rdi
0x180026c51  inc     dword ptr [rbx+8]
0x180026c54  mov     edx, [rbx+8]; NumOfElements
0x180026c57  mov     rcx, [rbx+28h]; Base
0x180026c5b  call    cs:__imp_qsort
0x180026c61  test    r14, r14
0x180026c64  jz      short loc_180026C69
0x180026c66  mov     [r14], rdi
0x180026c69  lea     rcx, [rdi+18h]; pDataIn
0x180026c6d  mov     edx, 202h
0x180026c72  mov     rax, rcx
0x180026c75  mov     [rax], r15b
0x180026c78  inc     rax
0x180026c7b  sub     rdx, 1
0x180026c7f  jnz     short loc_180026C75
0x180026c81  mov     edx, 200h; cbDataIn
0x180026c86  call    EncryptMemoryInPlace
0x180026c8b  xor     eax, eax
0x180026c8d  jmp     short loc_180026C9B
0x180026c8f  mov     eax, 8
0x180026c94  jmp     short loc_180026C9B
0x180026c96  mov     eax, 57h ; 'W'
0x180026c9b  add     rsp, 38h
0x180026c9f  pop     r15
0x180026ca1  pop     r14
0x180026ca3  pop     rdi
0x180026ca4  pop     rsi
0x180026ca5  pop     rbp
0x180026ca6  pop     rbx
0x180026ca7  retn
```
