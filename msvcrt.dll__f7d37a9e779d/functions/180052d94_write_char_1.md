# write_char_1

- ea: `0x180052d94`
- end: `0x180052ddb`
- name: `write_char_1`
- size: `71`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180052de4`
- `0x180052e60`
- `0x180053b40`
- `0x180054e40`

## callees

- `0x18004a800`
- `0x180052d94`

## pseudocode

```c
void __fastcall write_char_1(unsigned __int8 a1, __int64 a2, _DWORD *a3)
{
  int v5; // eax

  if ( (*(_BYTE *)(a2 + 24) & 0x40) == 0 || *(_QWORD *)(a2 + 16) )
  {
    if ( --*(_DWORD *)(a2 + 8) < 0 )
    {
      v5 = flsbuf((char)a1, (FILE *)a2);
    }
    else
    {
      *(_BYTE *)(*(_QWORD *)a2)++ = a1;
      v5 = a1;
    }
    if ( v5 == -1 )
      *a3 = -1;
    else
      ++*a3;
  }
  else
  {
    ++*a3;
  }
}

```

## disassembly

```asm
0x180052d94  push    rbx
0x180052d96  sub     rsp, 20h
0x180052d9a  test    byte ptr [rdx+18h], 40h
0x180052d9e  mov     rbx, r8
0x180052da1  jz      short loc_180052DAF
0x180052da3  cmp     qword ptr [rdx+10h], 0
0x180052da8  jnz     short loc_180052DAF
0x180052daa  inc     dword ptr [r8]
0x180052dad  jmp     short loc_180052DD5
0x180052daf  sub     dword ptr [rdx+8], 1
0x180052db3  js      short loc_180052DC2
0x180052db5  mov     rax, [rdx]
0x180052db8  mov     [rax], cl
0x180052dba  inc     qword ptr [rdx]
0x180052dbd  movzx   eax, cl
0x180052dc0  jmp     short loc_180052DCA
0x180052dc2  movsx   ecx, cl; Ch
0x180052dc5  call    _flsbuf
0x180052dca  cmp     eax, 0FFFFFFFFh
0x180052dcd  jnz     short loc_180052DD3
0x180052dcf  mov     [rbx], eax
0x180052dd1  jmp     short loc_180052DD5
0x180052dd3  inc     dword ptr [rbx]
0x180052dd5  add     rsp, 20h
0x180052dd9  pop     rbx
0x180052dda  retn
```
