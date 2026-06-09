# IsAnyStringInList

- ea: `0x18000859c`
- end: `0x1800086b6`
- name: `IsAnyStringInList`
- size: `282`
- prototype: `__int64 __fastcall(LPCWCH lpString1, LPCWCH lpString2)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800086bc`
- `0x1800087c4`
- `0x18000892c`
- `0x180008bc0`

## callees

- `0x18000859c`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800085e3`
- `KERNEL32!CompareStringOrdinal` at `0x180008611`
- `KERNEL32!CompareStringOrdinal` at `0x1800085e3`
- `KERNEL32!CompareStringOrdinal` at `0x180008611`

## pseudocode

```c
__int64 __fastcall IsAnyStringInList(LPCWCH lpString1, LPCWCH lpString2, const WCHAR **a3)
{
  const WCHAR *v5; // rbx
  unsigned int v6; // ebp
  LPCWCH v7; // rsi
  __int64 v8; // rdx
  _WORD *v9; // rax
  __int64 v10; // rdx
  const WCHAR *v11; // rax

  v5 = lpString1;
  v6 = 0;
  if ( *lpString1 )
  {
    while ( CompareStringOrdinal(v5, -1, L"*", -1, 1) != 2 )
    {
      v7 = lpString2;
      if ( *lpString2 )
      {
        while ( CompareStringOrdinal(v5, -1, v7, -1, 1) != 2 )
        {
          v8 = 0x7FFFFFFF;
          v9 = v7;
          do
          {
            if ( !*v9 )
              break;
            ++v9;
            --v8;
          }
          while ( v8 );
          if ( v8 )
          {
            v7 += ((0x7FFFFFFF - v8) & -(__int64)(v8 != 0)) + 1;
            if ( *v7 )
              continue;
          }
          goto LABEL_10;
        }
        break;
      }
LABEL_10:
      v10 = 0x7FFFFFFF;
      v11 = v5;
      do
      {
        if ( !*v11 )
          break;
        ++v11;
        --v10;
      }
      while ( v10 );
      if ( v10 )
      {
        v5 += ((0x7FFFFFFF - v10) & -(__int64)(v10 != 0)) + 1;
        if ( *v5 )
          continue;
      }
      return v6;
    }
    if ( a3 )
      *a3 = v5;
    return 1;
  }
  return v6;
}

```

## disassembly

```asm
0x18000859c  push    rbx
0x18000859e  push    rbp
0x18000859f  push    rsi
0x1800085a0  push    rdi
0x1800085a1  push    r13
0x1800085a3  push    r14
0x1800085a5  push    r15
0x1800085a7  sub     rsp, 30h
0x1800085ab  xor     r15d, r15d
0x1800085ae  mov     rdi, r8
0x1800085b1  mov     r14, rdx
0x1800085b4  mov     rbx, rcx
0x1800085b7  mov     ebp, r15d
0x1800085ba  cmp     [rcx], r15w
0x1800085be  jz      loc_1800086A5
0x1800085c4  mov     r13d, 7FFFFFFFh
0x1800085ca  or      r9d, 0FFFFFFFFh; cchCount2
0x1800085ce  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x1800085d6  or      edx, r9d; cchCount1
0x1800085d9  lea     r8, asc_18000D9D0; "*"
0x1800085e0  mov     rcx, rbx; lpString1
0x1800085e3  call    cs:__imp_CompareStringOrdinal
0x1800085e9  cmp     eax, 2
0x1800085ec  jz      loc_180008698
0x1800085f2  mov     rsi, r14
0x1800085f5  cmp     [r14], r15w
0x1800085f9  jz      short loc_180008657
0x1800085fb  or      eax, 0FFFFFFFFh
0x1800085fe  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180008606  mov     r9d, eax; cchCount2
0x180008609  mov     edx, eax; cchCount1
0x18000860b  mov     r8, rsi; lpString2
0x18000860e  mov     rcx, rbx; lpString1
0x180008611  call    cs:__imp_CompareStringOrdinal
0x180008617  cmp     eax, 2
0x18000861a  jz      short loc_180008698
0x18000861c  mov     rdx, r13
0x18000861f  mov     rax, rsi
0x180008622  cmp     [rax], r15w
0x180008626  jz      short loc_180008632
0x180008628  add     rax, 2
0x18000862c  sub     rdx, 1
0x180008630  jnz     short loc_180008622
0x180008632  mov     rcx, r13
0x180008635  mov     rax, rdx
0x180008638  sub     rcx, rdx
0x18000863b  neg     rax
0x18000863e  sbb     r8, r8
0x180008641  and     r8, rcx
0x180008644  test    rdx, rdx
0x180008647  jz      short loc_180008657
0x180008649  lea     rsi, [rsi+r8*2]
0x18000864d  add     rsi, 2
0x180008651  cmp     [rsi], r15w
0x180008655  jnz     short loc_1800085FB
0x180008657  mov     rdx, r13
0x18000865a  mov     rax, rbx
0x18000865d  cmp     [rax], r15w
0x180008661  jz      short loc_18000866D
0x180008663  add     rax, 2
0x180008667  sub     rdx, 1
0x18000866b  jnz     short loc_18000865D
0x18000866d  mov     rcx, r13
0x180008670  mov     rax, rdx
0x180008673  sub     rcx, rdx
0x180008676  neg     rax
0x180008679  sbb     r8, r8
0x18000867c  and     r8, rcx
0x18000867f  test    rdx, rdx
0x180008682  jz      short loc_1800086A5
0x180008684  lea     rbx, [rbx+r8*2]
0x180008688  add     rbx, 2
0x18000868c  cmp     [rbx], r15w
0x180008690  jnz     loc_1800085CA
0x180008696  jmp     short loc_1800086A5
0x180008698  test    rdi, rdi
0x18000869b  jz      short loc_1800086A0
0x18000869d  mov     [rdi], rbx
0x1800086a0  mov     ebp, 1
0x1800086a5  mov     eax, ebp
0x1800086a7  add     rsp, 30h
0x1800086ab  pop     r15
0x1800086ad  pop     r14
0x1800086af  pop     r13
0x1800086b1  pop     rdi
0x1800086b2  pop     rsi
0x1800086b3  pop     rbp
0x1800086b4  pop     rbx
0x1800086b5  retn
```
