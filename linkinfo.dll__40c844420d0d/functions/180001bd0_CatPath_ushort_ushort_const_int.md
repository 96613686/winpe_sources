# CatPath(ushort *,ushort const *,int)

- ea: `0x180001bd0`
- end: `0x180001c93`
- name: `?CatPath@@YAJPEAGPEBGH@Z`
- size: `195`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800014c0`
- `0x1800019e0`
- `0x1800044f0`
- `0x180004840`
- `0x1800048ec`
- `0x180005110`
- `0x180005240`

## callees

- `0x180001ae0`
- `0x180001bd0`
- `0x1800023d0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180001bf6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180001bf6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180001c6c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180001c6c`

## pseudocode

```c
__int64 __fastcall CatPath(unsigned __int16 *a1, unsigned __int16 *a2)
{
  WCHAR *i; // rbx
  unsigned __int16 v5; // r8
  int v6; // edx
  __int16 v7; // r8
  __int16 v8; // r9

  for ( i = a1; *i; i = CharNextW(i) )
    ;
  CharIsSlash(*a2);
  if ( (unsigned int)CharIsSlash(v5) )
  {
    if ( v6 )
      ++a2;
  }
  else if ( !v6 && v7 && v7 != 58 && v8 && lstrlenW(a1) + 1 < 260 )
  {
    *i++ = 92;
  }
  return StringCchCopyW(i, (int)(260 - (i - a1)), a2);
}

```

## disassembly

```asm
0x180001bd0  push    rbx
0x180001bd2  push    rsi
0x180001bd3  push    rdi
0x180001bd4  push    r14
0x180001bd6  sub     rsp, 28h
0x180001bda  movzx   r8d, word ptr [rcx]
0x180001bde  mov     r14, rdx
0x180001be1  mov     rsi, rcx
0x180001be4  mov     rbx, rcx
0x180001be7  test    r8w, r8w
0x180001beb  jz      short loc_180001C0F
0x180001bed  nop     dword ptr [rax]
0x180001bf0  mov     rcx, rbx; lpsz
0x180001bf3  mov     rdi, rbx
0x180001bf6  call    cs:__imp_CharNextW
0x180001bfd  nop     dword ptr [rax+rax+00h]
0x180001c02  mov     rbx, rax
0x180001c05  cmp     word ptr [rax], 0
0x180001c09  jnz     short loc_180001BF0
0x180001c0b  movzx   r8d, word ptr [rdi]
0x180001c0f  movzx   r9d, word ptr [r14]
0x180001c13  movzx   ecx, r9w; unsigned __int16
0x180001c17  call    ?CharIsSlash@@YAHG@Z; CharIsSlash(ushort)
0x180001c1c  movzx   ecx, r8w; unsigned __int16
0x180001c20  mov     edx, eax
0x180001c22  call    ?CharIsSlash@@YAHG@Z; CharIsSlash(ushort)
0x180001c27  mov     edi, 104h
0x180001c2c  test    eax, eax
0x180001c2e  jnz     short loc_180001C89
0x180001c30  test    edx, edx
0x180001c32  jnz     short loc_180001C47
0x180001c34  test    r8w, r8w
0x180001c38  jz      short loc_180001C47
0x180001c3a  cmp     r8w, 3Ah ; ':'
0x180001c3f  jz      short loc_180001C47
0x180001c41  test    r9w, r9w
0x180001c45  jnz     short loc_180001C69
0x180001c47  mov     rax, rbx
0x180001c4a  mov     r8, r14; unsigned __int16 *
0x180001c4d  sub     rax, rsi
0x180001c50  mov     rcx, rbx; unsigned __int16 *
0x180001c53  sar     rax, 1
0x180001c56  sub     edi, eax
0x180001c58  movsxd  rdx, edi; unsigned __int64
0x180001c5b  add     rsp, 28h
0x180001c5f  pop     r14
0x180001c61  pop     rdi
0x180001c62  pop     rsi
0x180001c63  pop     rbx
0x180001c64  jmp     ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001c69  mov     rcx, rsi; lpString
0x180001c6c  call    cs:__imp_lstrlenW
0x180001c73  nop     dword ptr [rax+rax+00h]
0x180001c78  inc     eax
0x180001c7a  cmp     eax, edi
0x180001c7c  jge     short loc_180001C47
0x180001c7e  mov     word ptr [rbx], 5Ch ; '\'
0x180001c83  add     rbx, 2
0x180001c87  jmp     short loc_180001C47
0x180001c89  test    edx, edx
0x180001c8b  jz      short loc_180001C47
0x180001c8d  add     r14, 2
0x180001c91  jmp     short loc_180001C47
```
