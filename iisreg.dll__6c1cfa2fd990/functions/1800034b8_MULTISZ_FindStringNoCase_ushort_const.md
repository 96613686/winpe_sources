# MULTISZ::FindStringNoCase(ushort const *)

- ea: `0x1800034b8`
- end: `0x180003515`
- name: `?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z`
- size: `93`
- prototype: `int(MULTISZ *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d7c`
- `0x18000200c`

## callees

- `0x1800034b8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800034d8`
- `msvcrt!_wcsicmp` at `0x1800034d8`

## pseudocode

```c
__int64 __fastcall MULTISZ::FindStringNoCase(MULTISZ *this, const unsigned __int16 *a2)
{
  const wchar_t *i; // rbx
  __int64 v4; // rax

  for ( i = (const wchar_t *)*((_QWORD *)this + 4); ; i += v4 + 1 )
  {
    if ( !*i )
      return 0;
    if ( !_wcsicmp(i, a2) )
      break;
    v4 = -1;
    do
      ++v4;
    while ( i[v4] );
  }
  return 1;
}

```

## disassembly

```asm
0x1800034b8  mov     [rsp+arg_0], rbx
0x1800034bd  mov     [rsp+arg_8], rsi
0x1800034c2  push    rdi
0x1800034c3  sub     rsp, 20h
0x1800034c7  mov     rbx, [rcx+20h]
0x1800034cb  mov     rdi, rdx
0x1800034ce  xor     esi, esi
0x1800034d0  jmp     short loc_1800034F7
0x1800034d2  mov     rdx, rdi; String2
0x1800034d5  mov     rcx, rbx; String1
0x1800034d8  call    cs:__imp__wcsicmp
0x1800034de  test    eax, eax
0x1800034e0  jz      short loc_18000350E
0x1800034e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800034e6  inc     rax
0x1800034e9  cmp     [rbx+rax*2], si
0x1800034ed  jnz     short loc_1800034E6
0x1800034ef  lea     rbx, [rbx+rax*2]
0x1800034f3  add     rbx, 2
0x1800034f7  cmp     [rbx], si
0x1800034fa  jnz     short loc_1800034D2
0x1800034fc  xor     eax, eax
0x1800034fe  mov     rbx, [rsp+28h+arg_0]
0x180003503  mov     rsi, [rsp+28h+arg_8]
0x180003508  add     rsp, 20h
0x18000350c  pop     rdi
0x18000350d  retn
0x18000350e  mov     eax, 1
0x180003513  jmp     short loc_1800034FE
```
