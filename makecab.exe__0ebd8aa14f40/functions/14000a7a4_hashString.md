# hashString

- ea: `0x14000a7a4`
- end: `0x14000a7ec`
- name: `hashString`
- size: `72`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a29c`
- `0x14000a564`
- `0x14000a670`

## callees

- `0x14000a7a4`

## import_xrefs

- `msvcrt!toupper` at `0x14000a7b5`
- `msvcrt!toupper` at `0x14000a7c5`
- `msvcrt!toupper` at `0x14000a7b5`
- `msvcrt!toupper` at `0x14000a7c5`

## pseudocode

```c
__int64 __fastcall hashString(unsigned __int8 *a1)
{
  unsigned __int8 *v1; // rbx
  unsigned int i; // edi
  unsigned __int8 v3; // al

  v1 = a1 + 1;
  for ( i = toupper(*a1); ; i = toupper(v3) ^ ((8 * (unsigned __int8)i) | (i >> 8)) )
  {
    v3 = *v1;
    if ( !*v1 )
      break;
    ++v1;
  }
  return i;
}

```

## disassembly

```asm
0x14000a7a4  mov     [rsp+arg_0], rbx
0x14000a7a9  push    rdi
0x14000a7aa  sub     rsp, 20h
0x14000a7ae  lea     rbx, [rcx+1]
0x14000a7b2  movzx   ecx, byte ptr [rcx]; C
0x14000a7b5  call    cs:__imp_toupper
0x14000a7bb  mov     edi, eax
0x14000a7bd  jmp     short loc_14000A7D9
0x14000a7bf  movzx   ecx, al; C
0x14000a7c2  inc     rbx
0x14000a7c5  call    cs:__imp_toupper
0x14000a7cb  movzx   ecx, dil
0x14000a7cf  shl     ecx, 3
0x14000a7d2  shr     edi, 8
0x14000a7d5  or      edi, ecx
0x14000a7d7  xor     edi, eax
0x14000a7d9  mov     al, [rbx]
0x14000a7db  test    al, al
0x14000a7dd  jnz     short loc_14000A7BF
0x14000a7df  mov     rbx, [rsp+28h+arg_0]
0x14000a7e4  mov     eax, edi
0x14000a7e6  add     rsp, 20h
0x14000a7ea  pop     rdi
0x14000a7eb  retn
```
