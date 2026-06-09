# LicPackTable::EqualValue(__LicensePack &,__LicensePack &,int,ulong)

- ea: `0x180068a60`
- end: `0x180068e2f`
- name: `?EqualValue@LicPackTable@@UEAAHAEAU__LicensePack@@0HK@Z`
- size: `975`
- prototype: `__int64 __fastcall(LicPackTable *__hidden this, struct __LicensePack *, struct __LicensePack *, int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180068a60`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180068d8d`
- `msvcrt!_wcsicmp` at `0x180068dbb`
- `msvcrt!_wcsicmp` at `0x180068de9`
- `msvcrt!_wcsicmp` at `0x180068d8d`
- `msvcrt!_wcsicmp` at `0x180068dbb`
- `msvcrt!_wcsicmp` at `0x180068de9`
- `KERNEL32!CompareFileTime` at `0x180068cd5`
- `KERNEL32!CompareFileTime` at `0x180068cd5`

## pseudocode

```c
__int64 __fastcall LicPackTable::EqualValue(
        LicPackTable *this,
        struct __LicensePack *a2,
        struct __LicensePack *a3,
        int a4,
        unsigned int a5)
{
  unsigned int v8; // r10d
  unsigned __int16 *v9; // rax
  __int64 v10; // rcx
  int v11; // edx
  int v12; // r8d
  unsigned __int16 *v13; // rax
  int v14; // edx
  int v15; // r8d
  unsigned __int16 *v16; // rax
  int v17; // edx
  int v18; // r8d
  unsigned __int16 *v19; // rax
  int v20; // edx
  int v21; // r8d

  v8 = 1;
  if ( (a5 & 0x10000000) == 0 || (v8 = *(_BYTE *)a2 == *(_BYTE *)a3, a4 == v8) )
  {
    if ( (a5 & 1) == 0 )
      goto LABEL_65;
    v9 = (unsigned __int16 *)((char *)a2 + 1588);
    v10 = a3 - a2;
    do
    {
      v11 = *(unsigned __int16 *)((char *)v9 + v10);
      v12 = *v9 - v11;
      if ( v12 )
        break;
      ++v9;
    }
    while ( v11 );
    v8 = v12 == 0;
    if ( a4 == v8 )
    {
LABEL_65:
      if ( (a5 & 2) == 0 || (v8 = *((_BYTE *)a2 + 2100) == *((_BYTE *)a3 + 2100), a4 == v8) )
      {
        if ( (a5 & 4) == 0 )
          goto LABEL_66;
        v13 = (unsigned __int16 *)((char *)a2 + 2614);
        do
        {
          v14 = *(unsigned __int16 *)((char *)v13 + a3 - a2);
          v15 = *v13 - v14;
          if ( v15 )
            break;
          ++v13;
        }
        while ( v14 );
        v8 = v15 == 0;
        if ( a4 == v8 )
        {
LABEL_66:
          if ( (a5 & 8) == 0 || (v8 = *((_WORD *)a2 + 1563) == *((_WORD *)a3 + 1563), a4 == v8) )
          {
            if ( (a5 & 0x10) == 0 || (v8 = *((_WORD *)a2 + 1564) == *((_WORD *)a3 + 1564), a4 == v8) )
            {
              if ( (a5 & 0x20) == 0 || (v8 = *((_DWORD *)a2 + 783) == *((_DWORD *)a3 + 783), a4 == v8) )
              {
                if ( (a5 & 0x40) == 0 || (v8 = *((_BYTE *)a2 + 3136) == *((_BYTE *)a3 + 3136), a4 == v8) )
                {
                  if ( (a5 & 0x100) == 0 || (v8 = *((_BYTE *)a2 + 3137) == *((_BYTE *)a3 + 3137), a4 == v8) )
                  {
                    if ( (a5 & 0x200) == 0 )
                      goto LABEL_67;
                    v16 = (unsigned __int16 *)((char *)a2 + 3138);
                    do
                    {
                      v17 = *(unsigned __int16 *)((char *)v16 + a3 - a2);
                      v18 = *v16 - v17;
                      if ( v18 )
                        break;
                      ++v16;
                    }
                    while ( v17 );
                    v8 = v18 == 0;
                    if ( a4 == v8 )
                    {
LABEL_67:
                      if ( (a5 & 0x400) == 0 || (v8 = *((_DWORD *)a2 + 913) == *((_DWORD *)a3 + 913), a4 == v8) )
                      {
                        if ( (a5 & 0x800) == 0 || (v8 = *((_DWORD *)a2 + 914) == *((_DWORD *)a3 + 914), a4 == v8) )
                        {
                          if ( (a5 & 0x1000) == 0 )
                            goto LABEL_64;
                          v19 = (unsigned __int16 *)((char *)a2 + 2102);
                          do
                          {
                            v20 = *(unsigned __int16 *)((char *)v19 + a3 - a2);
                            v21 = *v19 - v20;
                            if ( v21 )
                              break;
                            ++v19;
                          }
                          while ( v20 );
                          v8 = v21 == 0;
                          if ( a4 == v8 )
                          {
LABEL_64:
                            if ( (a5 & 0x10000) == 0 || (v8 = *((_DWORD *)a2 + 1) == *((_DWORD *)a3 + 1), a4 == v8) )
                            {
                              if ( (a5 & 0x200000) == 0
                                || (v8 = CompareFileTime((const FILETIME *)a2 + 1, (const FILETIME *)a3 + 1) == 0,
                                    a4 == v8) )
                              {
                                if ( (a5 & 0x400000) == 0 || (v8 = *((_DWORD *)a2 + 4) == *((_DWORD *)a3 + 4), a4 == v8) )
                                {
                                  if ( (a5 & 0x20000) == 0
                                    || (v8 = *((_BYTE *)a2 + 36) == *((_BYTE *)a3 + 36), a4 == v8) )
                                  {
                                    if ( (a5 & 0x100000) == 0
                                      || (v8 = *((_DWORD *)a2 + 8) == *((_DWORD *)a3 + 8), a4 == v8) )
                                    {
                                      if ( (a5 & 0x40000) == 0
                                        || (v8 = *((_DWORD *)a2 + 6) == *((_DWORD *)a3 + 6), a4 == v8) )
                                      {
                                        if ( (a5 & 0x80000) == 0
                                          || (v8 = *((_DWORD *)a2 + 7) <= *((_DWORD *)a3 + 7), a4 == v8) )
                                        {
                                          if ( (a5 & 0x1000000) == 0
                                            || (v8 = _wcsicmp((const wchar_t *)a2 + 26, (const wchar_t *)a3 + 26) == 0,
                                                a4 == v8) )
                                          {
                                            if ( (a5 & 0x2000000) == 0
                                              || (v8 = _wcsicmp((const wchar_t *)a2 + 282, (const wchar_t *)a3 + 282) == 0,
                                                  a4 == v8) )
                                            {
                                              if ( (a5 & 0x4000000) == 0
                                                || (v8 = _wcsicmp((const wchar_t *)a2 + 538, (const wchar_t *)a3 + 538) == 0,
                                                    a4 == v8) )
                                              {
                                                if ( (a5 & 0x8000000) != 0 )
                                                  return *((_DWORD *)a2 + 5) == *((_DWORD *)a3 + 5);
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180068a60  mov     [rsp+arg_0], rbx
0x180068a65  mov     [rsp+arg_8], rbp
0x180068a6a  mov     [rsp+arg_10], rsi
0x180068a6f  push    rdi
0x180068a70  sub     rsp, 20h
0x180068a74  mov     ebx, [rsp+28h+arg_20]
0x180068a78  mov     ebp, r9d
0x180068a7b  mov     rdi, r8
0x180068a7e  mov     rsi, rdx
0x180068a81  mov     r10d, 1
0x180068a87  bt      ebx, 1Ch
0x180068a8b  jnb     short loc_180068AA2
0x180068a8d  mov     al, [r8]
0x180068a90  xor     r10d, r10d
0x180068a93  cmp     [rdx], al
0x180068a95  setz    r10b
0x180068a99  cmp     r9d, r10d
0x180068a9c  jnz     loc_180068E16
0x180068aa2  test    bl, 1
0x180068aa5  jz      short loc_180068AE0
0x180068aa7  lea     rcx, [r8+634h]
0x180068aae  lea     rax, [rdx+634h]
0x180068ab5  sub     rcx, rax
0x180068ab8  movzx   r8d, word ptr [rax]
0x180068abc  movzx   edx, word ptr [rax+rcx]
0x180068ac0  sub     r8d, edx
0x180068ac3  jnz     short loc_180068ACD
0x180068ac5  add     rax, 2
0x180068ac9  test    edx, edx
0x180068acb  jnz     short loc_180068AB8
0x180068acd  xor     r10d, r10d
0x180068ad0  test    r8d, r8d
0x180068ad3  setz    r10b
0x180068ad7  cmp     ebp, r10d
0x180068ada  jnz     loc_180068E16
0x180068ae0  test    bl, 2
0x180068ae3  jz      short loc_180068B01
0x180068ae5  mov     al, [rdi+834h]
0x180068aeb  xor     r10d, r10d
0x180068aee  cmp     [rsi+834h], al
0x180068af4  setz    r10b
0x180068af8  cmp     ebp, r10d
0x180068afb  jnz     loc_180068E16
0x180068b01  test    bl, 4
0x180068b04  jz      short loc_180068B3F
0x180068b06  lea     rcx, [rdi+0A36h]
0x180068b0d  lea     rax, [rsi+0A36h]
0x180068b14  sub     rcx, rax
0x180068b17  movzx   r8d, word ptr [rax]
0x180068b1b  movzx   edx, word ptr [rax+rcx]
0x180068b1f  sub     r8d, edx
0x180068b22  jnz     short loc_180068B2C
0x180068b24  add     rax, 2
0x180068b28  test    edx, edx
0x180068b2a  jnz     short loc_180068B17
0x180068b2c  xor     r10d, r10d
0x180068b2f  test    r8d, r8d
0x180068b32  setz    r10b
0x180068b36  cmp     ebp, r10d
0x180068b39  jnz     loc_180068E16
0x180068b3f  test    bl, 8
0x180068b42  jz      short loc_180068B62
0x180068b44  movzx   eax, word ptr [rdi+0C36h]
0x180068b4b  xor     r10d, r10d
0x180068b4e  cmp     [rsi+0C36h], ax
0x180068b55  setz    r10b
0x180068b59  cmp     ebp, r10d
0x180068b5c  jnz     loc_180068E16
0x180068b62  test    bl, 10h
0x180068b65  jz      short loc_180068B85
0x180068b67  movzx   eax, word ptr [rdi+0C38h]
0x180068b6e  xor     r10d, r10d
0x180068b71  cmp     [rsi+0C38h], ax
0x180068b78  setz    r10b
0x180068b7c  cmp     ebp, r10d
0x180068b7f  jnz     loc_180068E16
0x180068b85  test    bl, 20h
0x180068b88  jz      short loc_180068BA6
0x180068b8a  mov     eax, [rdi+0C3Ch]
0x180068b90  xor     r10d, r10d
0x180068b93  cmp     [rsi+0C3Ch], eax
0x180068b99  setz    r10b
0x180068b9d  cmp     ebp, r10d
0x180068ba0  jnz     loc_180068E16
0x180068ba6  test    bl, 40h
0x180068ba9  jz      short loc_180068BC7
0x180068bab  mov     al, [rdi+0C40h]
0x180068bb1  xor     r10d, r10d
0x180068bb4  cmp     [rsi+0C40h], al
0x180068bba  setz    r10b
0x180068bbe  cmp     ebp, r10d
0x180068bc1  jnz     loc_180068E16
0x180068bc7  bt      ebx, 8
0x180068bcb  jnb     short loc_180068BE9
0x180068bcd  mov     al, [rdi+0C41h]
0x180068bd3  xor     r10d, r10d
0x180068bd6  cmp     [rsi+0C41h], al
0x180068bdc  setz    r10b
0x180068be0  cmp     ebp, r10d
0x180068be3  jnz     loc_180068E16
0x180068be9  bt      ebx, 9
0x180068bed  jnb     short loc_180068C28
0x180068bef  lea     rcx, [rdi+0C42h]
0x180068bf6  lea     rax, [rsi+0C42h]
0x180068bfd  sub     rcx, rax
0x180068c00  movzx   r8d, word ptr [rax]
0x180068c04  movzx   edx, word ptr [rax+rcx]
0x180068c08  sub     r8d, edx
0x180068c0b  jnz     short loc_180068C15
0x180068c0d  add     rax, 2
0x180068c11  test    edx, edx
0x180068c13  jnz     short loc_180068C00
0x180068c15  xor     r10d, r10d
0x180068c18  test    r8d, r8d
0x180068c1b  setz    r10b
0x180068c1f  cmp     ebp, r10d
0x180068c22  jnz     loc_180068E16
0x180068c28  bt      ebx, 0Ah
0x180068c2c  jnb     short loc_180068C4A
0x180068c2e  mov     eax, [rdi+0E44h]
0x180068c34  xor     r10d, r10d
0x180068c37  cmp     [rsi+0E44h], eax
0x180068c3d  setz    r10b
0x180068c41  cmp     ebp, r10d
0x180068c44  jnz     loc_180068E16
0x180068c4a  bt      ebx, 0Bh
0x180068c4e  jnb     short loc_180068C6C
0x180068c50  mov     eax, [rdi+0E48h]
0x180068c56  xor     r10d, r10d
0x180068c59  cmp     [rsi+0E48h], eax
0x180068c5f  setz    r10b
0x180068c63  cmp     ebp, r10d
0x180068c66  jnz     loc_180068E16
0x180068c6c  bt      ebx, 0Ch
0x180068c70  jnb     short loc_180068CAB
0x180068c72  lea     rcx, [rdi+836h]
0x180068c79  lea     rax, [rsi+836h]
0x180068c80  sub     rcx, rax
0x180068c83  movzx   r8d, word ptr [rax]
0x180068c87  movzx   edx, word ptr [rax+rcx]
0x180068c8b  sub     r8d, edx
0x180068c8e  jnz     short loc_180068C98
0x180068c90  add     rax, 2
0x180068c94  test    edx, edx
0x180068c96  jnz     short loc_180068C83
0x180068c98  xor     r10d, r10d
0x180068c9b  test    r8d, r8d
0x180068c9e  setz    r10b
0x180068ca2  cmp     ebp, r10d
0x180068ca5  jnz     loc_180068E16
0x180068cab  bt      ebx, 10h
0x180068caf  jnb     short loc_180068CC7
0x180068cb1  mov     eax, [rdi+4]
0x180068cb4  xor     r10d, r10d
0x180068cb7  cmp     [rsi+4], eax
0x180068cba  setz    r10b
0x180068cbe  cmp     ebp, r10d
0x180068cc1  jnz     loc_180068E16
0x180068cc7  bt      ebx, 15h
0x180068ccb  jnb     short loc_180068CF3
0x180068ccd  lea     rdx, [rdi+8]; lpFileTime2
0x180068cd1  lea     rcx, [rsi+8]; lpFileTime1
0x180068cd5  call    cs:__imp_CompareFileTime
0x180068cdc  nop     dword ptr [rax+rax+00h]
0x180068ce1  xor     r10d, r10d
0x180068ce4  test    eax, eax
0x180068ce6  setz    r10b
0x180068cea  cmp     ebp, r10d
0x180068ced  jnz     loc_180068E16
0x180068cf3  bt      ebx, 16h
0x180068cf7  jnb     short loc_180068D0F
0x180068cf9  mov     eax, [rdi+10h]
0x180068cfc  xor     r10d, r10d
0x180068cff  cmp     [rsi+10h], eax
0x180068d02  setz    r10b
0x180068d06  cmp     ebp, r10d
0x180068d09  jnz     loc_180068E16
0x180068d0f  bt      ebx, 11h
0x180068d13  jnb     short loc_180068D2B
0x180068d15  mov     al, [rdi+24h]
0x180068d18  xor     r10d, r10d
0x180068d1b  cmp     [rsi+24h], al
0x180068d1e  setz    r10b
0x180068d22  cmp     ebp, r10d
0x180068d25  jnz     loc_180068E16
0x180068d2b  bt      ebx, 14h
0x180068d2f  jnb     short loc_180068D47
0x180068d31  mov     eax, [rdi+20h]
0x180068d34  xor     r10d, r10d
0x180068d37  cmp     [rsi+20h], eax
0x180068d3a  setz    r10b
0x180068d3e  cmp     ebp, r10d
0x180068d41  jnz     loc_180068E16
0x180068d47  bt      ebx, 12h
0x180068d4b  jnb     short loc_180068D63
0x180068d4d  mov     eax, [rdi+18h]
0x180068d50  xor     r10d, r10d
0x180068d53  cmp     [rsi+18h], eax
0x180068d56  setz    r10b
0x180068d5a  cmp     ebp, r10d
0x180068d5d  jnz     loc_180068E16
0x180068d63  bt      ebx, 13h
0x180068d67  jnb     short loc_180068D7F
0x180068d69  mov     eax, [rdi+1Ch]
0x180068d6c  xor     r10d, r10d
0x180068d6f  cmp     [rsi+1Ch], eax
0x180068d72  setbe   r10b
0x180068d76  cmp     ebp, r10d
0x180068d79  jnz     loc_180068E16
0x180068d7f  bt      ebx, 18h
0x180068d83  jnb     short loc_180068DA7
0x180068d85  lea     rdx, [rdi+34h]; String2
0x180068d89  lea     rcx, [rsi+34h]; String1
0x180068d8d  call    cs:__imp__wcsicmp
0x180068d94  nop     dword ptr [rax+rax+00h]
0x180068d99  xor     r10d, r10d
0x180068d9c  test    eax, eax
0x180068d9e  setz    r10b
0x180068da2  cmp     ebp, r10d
0x180068da5  jnz     short loc_180068E16
0x180068da7  bt      ebx, 19h
0x180068dab  jnb     short loc_180068DD5
0x180068dad  lea     rdx, [rdi+234h]; String2
0x180068db4  lea     rcx, [rsi+234h]; String1
0x180068dbb  call    cs:__imp__wcsicmp
0x180068dc2  nop     dword ptr [rax+rax+00h]
0x180068dc7  xor     r10d, r10d
0x180068dca  test    eax, eax
0x180068dcc  setz    r10b
0x180068dd0  cmp     ebp, r10d
0x180068dd3  jnz     short loc_180068E16
0x180068dd5  bt      ebx, 1Ah
0x180068dd9  jnb     short loc_180068E03
0x180068ddb  lea     rdx, [rdi+434h]; String2
0x180068de2  lea     rcx, [rsi+434h]; String1
0x180068de9  call    cs:__imp__wcsicmp
0x180068df0  nop     dword ptr [rax+rax+00h]
0x180068df5  xor     r10d, r10d
0x180068df8  test    eax, eax
0x180068dfa  setz    r10b
0x180068dfe  cmp     ebp, r10d
0x180068e01  jnz     short loc_180068E16
0x180068e03  bt      ebx, 1Bh
0x180068e07  jnb     short loc_180068E16
0x180068e09  mov     ecx, [rdi+14h]
0x180068e0c  xor     r10d, r10d
0x180068e0f  cmp     [rsi+14h], ecx
0x180068e12  setz    r10b
0x180068e16  mov     rbx, [rsp+28h+arg_0]
0x180068e1b  mov     eax, r10d
0x180068e1e  mov     rbp, [rsp+28h+arg_8]
0x180068e23  mov     rsi, [rsp+28h+arg_10]
0x180068e28  add     rsp, 20h
0x180068e2c  pop     rdi
0x180068e2d  retn
```
