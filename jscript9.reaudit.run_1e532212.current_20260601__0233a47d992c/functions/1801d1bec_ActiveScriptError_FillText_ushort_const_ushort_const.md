# ActiveScriptError::FillText(ushort const * &,ushort const *)

- ea: `0x1801d1bec`
- end: `0x1801d1c66`
- name: `?FillText@ActiveScriptError@@CAJAEAPEBGPEBG@Z`
- size: `122`
- prototype: `static int(const unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1801d0bf4`
- `0x1801d0dd8`
- `0x1801d136c`
- `0x1801d1428`
- `0x1801d17a4`
- `0x1801d1a9c`
- `0x1801d20b0`

## callees

- `0x1801d1bec`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1801d1c4e`
- `msvcrt!wcscpy_s` at `0x1801d1c4e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1801d1c2b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1801d1c2b`

## pseudocode

```c
__int64 __fastcall ActiveScriptError::FillText(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  __int64 v3; // rax
  rsize_t v4; // rdi
  unsigned __int16 *v5; // rax

  if ( a2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a2[v3] );
    v4 = v3 + 1;
    v5 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v3 + 1));
    *a1 = v5;
    if ( !v5 )
      return 2147942414LL;
    wcscpy_s(v5, v4, a2);
  }
  else
  {
    *a1 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1801d1bec  mov     rax, rsp
0x1801d1bef  mov     [rax+18h], rbx
0x1801d1bf3  mov     [rax+20h], rsi
0x1801d1bf7  mov     [rax+10h], rdx
0x1801d1bfb  mov     [rax+8], rcx
0x1801d1bff  push    rdi
0x1801d1c00  sub     rsp, 20h
0x1801d1c04  xor     esi, esi
0x1801d1c06  mov     rbx, rdx
0x1801d1c09  test    rdx, rdx
0x1801d1c0c  jnz     short loc_1801D1C16
0x1801d1c0e  mov     rax, rcx
0x1801d1c11  mov     [rcx], rsi
0x1801d1c14  jmp     short loc_1801D1C54
0x1801d1c16  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801d1c1a  inc     rax
0x1801d1c1d  cmp     [rbx+rax*2], si
0x1801d1c21  jnz     short loc_1801D1C1A
0x1801d1c23  lea     rdi, [rax+1]
0x1801d1c27  lea     rcx, [rdi+rdi]; cb
0x1801d1c2b  call    cs:__imp_CoTaskMemAlloc
0x1801d1c31  mov     rcx, [rsp+28h+arg_0]
0x1801d1c36  mov     [rcx], rax
0x1801d1c39  test    rax, rax
0x1801d1c3c  jnz     short loc_1801D1C45
0x1801d1c3e  mov     eax, 8007000Eh
0x1801d1c43  jmp     short loc_1801D1C56
0x1801d1c45  mov     r8, rbx; Source
0x1801d1c48  mov     rdx, rdi; SizeInWords
0x1801d1c4b  mov     rcx, rax; Destination
0x1801d1c4e  call    cs:__imp_wcscpy_s
0x1801d1c54  xor     eax, eax
0x1801d1c56  mov     rbx, [rsp+28h+arg_10]
0x1801d1c5b  mov     rsi, [rsp+28h+arg_18]
0x1801d1c60  add     rsp, 20h
0x1801d1c64  pop     rdi
0x1801d1c65  retn
```
