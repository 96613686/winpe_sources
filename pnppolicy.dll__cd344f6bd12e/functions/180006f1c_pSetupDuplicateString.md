# pSetupDuplicateString

- ea: `0x180006f1c`
- end: `0x180006faa`
- name: `pSetupDuplicateString`
- size: `142`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000355c`
- `0x18000729c`
- `0x1800079f0`
- `0x180009e08`

## callees

- `0x1800034e8`
- `0x180006f1c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180006f8e`
- `KERNEL32!HeapFree` at `0x180006f8e`
- `KERNEL32!HeapAlloc` at `0x180006f63`
- `KERNEL32!HeapAlloc` at `0x180006f63`

## pseudocode

```c
wchar_t *__fastcall pSetupDuplicateString(STRSAFE_LPCWSTR pszSrc)
{
  __int64 v3; // rax
  __int64 v4; // rax
  unsigned int v5; // edi
  unsigned __int64 v6; // rax
  wchar_t *v7; // rax
  wchar_t *v8; // r11

  if ( !pszSrc )
    return 0;
  v3 = -1;
  do
    ++v3;
  while ( pszSrc[v3] );
  v4 = (unsigned int)(v3 + 1);
  v5 = v4;
  v6 = 2 * v4;
  if ( v6 <= 0xFFFFFFFF )
  {
    v7 = (wchar_t *)HeapAlloc(hHeap, 0, (unsigned int)v6);
    v8 = v7;
    if ( !v7 || StringCchCopyW(v7, v5, pszSrc) >= 0 )
      return v8;
    HeapFree(hHeap, 0, v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180006f1c  mov     [rsp+arg_0], rbx
0x180006f21  mov     [rsp+arg_8], rsi
0x180006f26  push    rdi
0x180006f27  sub     rsp, 20h
0x180006f2b  xor     esi, esi
0x180006f2d  mov     rbx, rcx
0x180006f30  test    rcx, rcx
0x180006f33  jnz     short loc_180006F39
0x180006f35  xor     eax, eax
0x180006f37  jmp     short loc_180006F9A
0x180006f39  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006f3d  inc     rax
0x180006f40  cmp     [rcx+rax*2], si
0x180006f44  jnz     short loc_180006F3D
0x180006f46  inc     eax
0x180006f48  mov     ecx, 0FFFFFFFFh
0x180006f4d  mov     edi, eax
0x180006f4f  add     rax, rax
0x180006f52  cmp     rax, rcx
0x180006f55  ja      short loc_180006F94
0x180006f57  mov     rcx, cs:hHeap; hHeap
0x180006f5e  xor     edx, edx; dwFlags
0x180006f60  mov     r8d, eax; dwBytes
0x180006f63  call    cs:__imp_HeapAlloc
0x180006f69  mov     r11, rax
0x180006f6c  test    rax, rax
0x180006f6f  jz      short loc_180006F97
0x180006f71  mov     r8, rbx; pszSrc
0x180006f74  mov     edx, edi; cchDest
0x180006f76  mov     rcx, rax; pszDest
0x180006f79  call    StringCchCopyW
0x180006f7e  test    eax, eax
0x180006f80  jns     short loc_180006F97
0x180006f82  mov     rcx, cs:hHeap; hHeap
0x180006f89  mov     r8, r11; lpMem
0x180006f8c  xor     edx, edx; dwFlags
0x180006f8e  call    cs:__imp_HeapFree
0x180006f94  mov     r11, rsi
0x180006f97  mov     rax, r11
0x180006f9a  mov     rbx, [rsp+28h+arg_0]
0x180006f9f  mov     rsi, [rsp+28h+arg_8]
0x180006fa4  add     rsp, 20h
0x180006fa8  pop     rdi
0x180006fa9  retn
```
