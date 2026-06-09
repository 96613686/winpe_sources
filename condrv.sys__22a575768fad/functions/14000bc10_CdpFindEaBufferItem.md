# CdpFindEaBufferItem

- ea: `0x14000bc10`
- end: `0x14000bc64`
- name: `CdpFindEaBufferItem`
- size: `84`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400083b0`
- `0x14000b820`
- `0x14000bb80`

## callees

- `0x14000bc10`

## import_xrefs

- `ntoskrnl!_stricmp` at `0x14000bc2c`
- `ntoskrnl!_stricmp` at `0x14000bc2c`

## pseudocode

```c
const char *__fastcall CdpFindEaBufferItem(const char *a1, const char *a2)
{
  const char *v3; // rbx
  __int64 v4; // rax

  v3 = a1;
  if ( !a1 )
    return 0;
  while ( _stricmp(v3 + 8, a2) )
  {
    v4 = *(unsigned int *)v3;
    if ( !(_DWORD)v4 )
      return 0;
    v3 += v4;
  }
  return v3;
}

```

## disassembly

```asm
0x14000bc10  mov     [rsp+arg_0], rbx
0x14000bc15  push    rdi
0x14000bc16  sub     rsp, 20h
0x14000bc1a  mov     rdi, rdx
0x14000bc1d  mov     rbx, rcx
0x14000bc20  test    rcx, rcx
0x14000bc23  jz      short loc_14000BC42
0x14000bc25  lea     rcx, [rbx+8]; Str1
0x14000bc29  mov     rdx, rdi; Str2
0x14000bc2c  call    cs:__imp__stricmp
0x14000bc33  nop     dword ptr [rax+rax+00h]
0x14000bc38  test    eax, eax
0x14000bc3a  jz      short loc_14000BC50
0x14000bc3c  mov     eax, [rbx]
0x14000bc3e  test    eax, eax
0x14000bc40  jnz     short loc_14000BC5F
0x14000bc42  xor     eax, eax
0x14000bc44  mov     rbx, [rsp+28h+arg_0]
0x14000bc49  add     rsp, 20h
0x14000bc4d  pop     rdi
0x14000bc4e  retn
0x14000bc50  mov     rax, rbx
0x14000bc53  mov     rbx, [rsp+28h+arg_0]
0x14000bc58  add     rsp, 20h
0x14000bc5c  pop     rdi
0x14000bc5d  retn
0x14000bc5f  add     rbx, rax
0x14000bc62  jmp     short loc_14000BC25
```
