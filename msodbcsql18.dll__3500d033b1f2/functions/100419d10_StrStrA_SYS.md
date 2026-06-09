# StrStrA_SYS

- ea: `0x100419d10`
- end: `0x100419dbf`
- name: `StrStrA_SYS`
- size: `175`
- prototype: `__int64 __fastcall(LPCSTR lpCurrentChar)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100440ee8`
- `0x100442008`

## callees

- `0x100419d10`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x100419d6d`
- `KERNEL32!CompareStringA` at `0x100419d6d`
- `USER32!CharNextExA` at `0x100419d84`
- `USER32!CharNextExA` at `0x100419d84`

## pseudocode

```c
const CHAR *__fastcall StrStrA_SYS(LPCSTR lpCurrentChar, int a2, const CHAR *a3, int a4)
{
  __int64 cchCount2; // rdi
  int v7; // ebp
  const CHAR *v8; // rbx
  int v9; // eax
  int v10; // eax
  LPSTR v11; // rax

  cchCount2 = a4;
  v7 = (int)lpCurrentChar;
  v8 = lpCurrentChar;
  if ( a2 > 1 && a2 >= a4 )
  {
    v9 = a2;
    if ( *lpCurrentChar )
    {
      while ( v9 >= (int)cchCount2 && (unsigned __int64)(cchCount2 + 1) <= 0x8000000 )
      {
        v10 = CompareStringA(0x800u, 0, v8, cchCount2, a3, cchCount2);
        if ( v10 == 2 )
          return v8;
        if ( v10 )
        {
          v11 = CharNextExA(0, v8, 0);
          v8 = v11;
          if ( v11 )
          {
            v9 = a2 + v7 - (_DWORD)v11;
            if ( *v8 )
              continue;
          }
        }
        return 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x100419d10  mov     rax, rsp
0x100419d13  mov     [rax+8], rbx
0x100419d17  mov     [rax+10h], rbp
0x100419d1b  mov     [rax+18h], rsi
0x100419d1f  mov     [rax+20h], rdi
0x100419d23  push    r14
0x100419d25  sub     rsp, 30h
0x100419d29  movsxd  rdi, r9d
0x100419d2c  mov     r14, r8
0x100419d2f  mov     esi, edx
0x100419d31  mov     rbp, rcx
0x100419d34  mov     rbx, rcx
0x100419d37  cmp     edx, 1
0x100419d3a  jle     short loc_100419D9D
0x100419d3c  cmp     edx, edi
0x100419d3e  jl      short loc_100419D9D
0x100419d40  cmp     byte ptr [rcx], 0
0x100419d43  mov     eax, edx
0x100419d45  jz      short loc_100419D9D
0x100419d47  cmp     eax, edi
0x100419d49  jl      short loc_100419D9D
0x100419d4b  lea     rax, [rdi+1]
0x100419d4f  cmp     rax, 8000000h
0x100419d55  ja      short loc_100419D9D
0x100419d57  mov     [rsp+38h+cchCount2], edi; cchCount2
0x100419d5b  mov     r9d, edi; cchCount1
0x100419d5e  mov     r8, rbx; lpString1
0x100419d61  mov     [rsp+38h+lpString2], r14; lpString2
0x100419d66  xor     edx, edx; dwCmpFlags
0x100419d68  mov     ecx, 800h; Locale
0x100419d6d  call    cs:__imp_CompareStringA
0x100419d73  cmp     eax, 2
0x100419d76  jz      short loc_100419DBA
0x100419d78  test    eax, eax
0x100419d7a  jz      short loc_100419D9D
0x100419d7c  xor     ecx, ecx; CodePage
0x100419d7e  xor     r8d, r8d; dwFlags
0x100419d81  mov     rdx, rbx; lpCurrentChar
0x100419d84  call    cs:__imp_CharNextExA
0x100419d8a  mov     rbx, rax
0x100419d8d  test    rax, rax
0x100419d90  jz      short loc_100419D9D
0x100419d92  mov     eax, ebp
0x100419d94  sub     eax, ebx
0x100419d96  add     eax, esi
0x100419d98  cmp     byte ptr [rbx], 0
0x100419d9b  jnz     short loc_100419D47
0x100419d9d  xor     eax, eax
0x100419d9f  mov     rbx, [rsp+38h+arg_0]
0x100419da4  mov     rbp, [rsp+38h+arg_8]
0x100419da9  mov     rsi, [rsp+38h+arg_10]
0x100419dae  mov     rdi, [rsp+38h+arg_18]
0x100419db3  add     rsp, 30h
0x100419db7  pop     r14
0x100419db9  retn
0x100419dba  mov     rax, rbx
0x100419dbd  jmp     short loc_100419D9F
```
