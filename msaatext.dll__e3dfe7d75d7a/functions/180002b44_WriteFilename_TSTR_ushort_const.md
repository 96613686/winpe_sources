# WriteFilename(TSTR &,ushort const *)

- ea: `0x180002b44`
- end: `0x180002bb2`
- name: `?WriteFilename@@YAXAEAVTSTR@@PEBG@Z`
- size: `110`
- prototype: `void __fastcall(struct TSTR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800026d0`

## callees

- `0x180002b44`
- `0x180003078`

## pseudocode

```c
void __fastcall WriteFilename(struct TSTR *a1, unsigned __int16 *a2)
{
  unsigned __int16 v3; // cx
  const unsigned __int16 *v4; // rax
  const unsigned __int16 *v5; // r9
  const unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // r10
  unsigned __int16 v8; // r8

LABEL_13:
  v5 = 0;
  v7 = a2;
  while ( 1 )
  {
    v8 = *a2;
    if ( !*a2 )
      break;
    if ( v8 == 46 )
      v3 = a2[1];
    else
      v3 = *a2;
    v4 = a2;
    if ( v8 != 46 )
      v4 = v5;
    v5 = v4;
    v6 = a2 + 1;
    if ( v8 != 46 )
      v6 = a2;
    if ( v3 == 92 || *v6 == 58 )
    {
      a2 = (unsigned __int16 *)(v6 + 1);
      goto LABEL_13;
    }
    a2 = (unsigned __int16 *)(v6 + 1);
  }
  std::wstring::append(a1, v7);
}

```

## disassembly

```asm
0x180002b44  push    rbx
0x180002b46  mov     r11, rcx
0x180002b49  xor     ebx, ebx
0x180002b4b  jmp     short loc_180002B86
0x180002b4d  cmp     r8w, 2Eh ; '.'
0x180002b52  jnz     short loc_180002B5A
0x180002b54  movzx   ecx, word ptr [rdx+2]
0x180002b58  jmp     short loc_180002B5E
0x180002b5a  movzx   ecx, r8w
0x180002b5e  mov     rax, rdx
0x180002b61  cmovnz  rax, r9
0x180002b65  mov     r9, rax
0x180002b68  lea     rax, [rdx+2]
0x180002b6c  cmovnz  rax, rdx
0x180002b70  cmp     cx, 5Ch ; '\'
0x180002b74  jz      short loc_180002B82
0x180002b76  cmp     word ptr [rax], 3Ah ; ':'
0x180002b7a  jz      short loc_180002B82
0x180002b7c  lea     rdx, [rax+2]
0x180002b80  jmp     short loc_180002B8C
0x180002b82  lea     rdx, [rax+2]
0x180002b86  mov     r9, rbx
0x180002b89  mov     r10, rdx
0x180002b8c  movzx   r8d, word ptr [rdx]
0x180002b90  test    r8w, r8w
0x180002b94  jnz     short loc_180002B4D
0x180002b96  test    r9, r9
0x180002b99  mov     rcx, r11; Src
0x180002b9c  cmovnz  rdx, r9
0x180002ba0  sub     rdx, r10
0x180002ba3  sar     rdx, 1
0x180002ba6  mov     r8, rdx
0x180002ba9  mov     rdx, r10; void *
0x180002bac  pop     rbx
0x180002bad  jmp     ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
```
