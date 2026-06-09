# CFileStream::GetName(ushort * *)

- ea: `0x18002e8c0`
- end: `0x18002e944`
- name: `?GetName@CFileStream@@QEAAJPEAPEAG@Z`
- size: `132`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c0a0`
- `0x18002e0d0`

## callees

- `0x18002e8c0`
- `0x18002e94c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e8ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e8ee`

## pseudocode

```c
__int64 __fastcall CFileStream::GetName(CFileStream *this, unsigned __int16 **a2)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  __int64 v5; // rcx
  unsigned __int16 *v7; // rax
  size_t *v8; // r8
  unsigned int v9; // r11d
  const wchar_t *v10; // r9
  size_t v11; // rdx
  size_t v13; // [rsp+20h] [rbp-38h]

  v2 = *((_QWORD *)this + 6);
  v3 = -1;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(v2 + 2 * v5 + 72) );
  v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v5 + 2);
  *a2 = v7;
  if ( v7 )
  {
    v9 = 0;
    v10 = (const wchar_t *)(*((_QWORD *)this + 6) + 72LL);
    do
      ++v3;
    while ( v10[v3] );
    v11 = v3 + 1;
    if ( v3 != -1 )
    {
      if ( v11 > 0x7FFFFFFF )
        *v7 = 0;
      else
        StringCopyWorkerW(v7, v11, v8, v10, v13);
    }
  }
  else
  {
    return (unsigned int)-2147287032;
  }
  return v9;
}

```

## disassembly

```asm
0x18002e8c0  push    rbx
0x18002e8c2  push    rbp
0x18002e8c3  push    rsi
0x18002e8c4  push    rdi
0x18002e8c5  sub     rsp, 38h
0x18002e8c9  mov     rax, [rcx+30h]
0x18002e8cd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e8d1  mov     rdi, rcx
0x18002e8d4  xor     ebp, ebp
0x18002e8d6  mov     rcx, rbx
0x18002e8d9  mov     rsi, rdx
0x18002e8dc  inc     rcx
0x18002e8df  cmp     [rax+rcx*2+48h], bp
0x18002e8e4  jnz     short loc_18002E8DC
0x18002e8e6  lea     rcx, ds:2[rcx*2]; cb
0x18002e8ee  call    cs:__imp_CoTaskMemAlloc
0x18002e8f4  mov     [rsi], rax
0x18002e8f7  test    rax, rax
0x18002e8fa  jz      short loc_18002E93C
0x18002e8fc  mov     r9, [rdi+30h]
0x18002e900  mov     r11d, ebp
0x18002e903  add     r9, 48h ; 'H'; pszSrc
0x18002e907  inc     rbx
0x18002e90a  cmp     [r9+rbx*2], bp
0x18002e90f  jnz     short loc_18002E907
0x18002e911  lea     rdx, [rbx+1]; cchDest
0x18002e915  test    rdx, rdx
0x18002e918  jz      short loc_18002E92B
0x18002e91a  cmp     rdx, 7FFFFFFFh
0x18002e921  ja      short loc_18002E937
0x18002e923  mov     rcx, rax; pszDest
0x18002e926  call    StringCopyWorkerW
0x18002e92b  mov     eax, r11d
0x18002e92e  add     rsp, 38h
0x18002e932  pop     rdi
0x18002e933  pop     rsi
0x18002e934  pop     rbp
0x18002e935  pop     rbx
0x18002e936  retn
0x18002e937  mov     [rax], bp
0x18002e93a  jmp     short loc_18002E92B
0x18002e93c  mov     r11d, 80030008h
0x18002e942  jmp     short loc_18002E92B
```
