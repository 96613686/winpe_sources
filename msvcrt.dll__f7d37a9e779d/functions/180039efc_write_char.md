# write_char

- ea: `0x180039efc`
- end: `0x180039f54`
- name: `write_char`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180039390`
- `0x180039f5c`

## callees

- `0x180039efc`
- `0x1800507b0`

## pseudocode

```c
void __fastcall write_char(__int16 a1, FILE *a2, _DWORD *a3)
{
  int flag; // r8d
  bool v5; // sf

  flag = a2->_flag;
  if ( (flag & 0x40) != 0 && !a2->_base )
    goto LABEL_5;
  v5 = a2->_cnt - 2 < 0;
  a2->_cnt -= 2;
  if ( v5 )
  {
    a2->_flag = flag | 0x20;
  }
  else
  {
    *(_WORD *)a2->_ptr = a1;
    a2->_ptr += 2;
    if ( a1 != -1 )
    {
LABEL_5:
      ++*a3;
      return;
    }
  }
  if ( !ferror(a2) )
    goto LABEL_5;
  *a3 = -1;
}

```

## disassembly

```asm
0x180039efc  push    rbx
0x180039efe  sub     rsp, 20h
0x180039f02  mov     rbx, r8
0x180039f05  mov     r8d, [rdx+18h]
0x180039f09  test    r8b, 40h
0x180039f0d  jz      short loc_180039F16
0x180039f0f  cmp     qword ptr [rdx+10h], 0
0x180039f14  jz      short loc_180039F30
0x180039f16  add     dword ptr [rdx+8], 0FFFFFFFEh
0x180039f1a  js      short loc_180039F38
0x180039f1c  mov     rax, [rdx]
0x180039f1f  mov     [rax], cx
0x180039f22  mov     eax, 0FFFFh
0x180039f27  add     qword ptr [rdx], 2
0x180039f2b  cmp     cx, ax
0x180039f2e  jz      short loc_180039F40
0x180039f30  inc     dword ptr [rbx]
0x180039f32  add     rsp, 20h
0x180039f36  pop     rbx
0x180039f37  retn
0x180039f38  or      r8d, 20h
0x180039f3c  mov     [rdx+18h], r8d
0x180039f40  mov     rcx, rdx; Stream
0x180039f43  call    ferror
0x180039f48  test    eax, eax
0x180039f4a  jz      short loc_180039F30
0x180039f4c  mov     dword ptr [rbx], 0FFFFFFFFh
0x180039f52  jmp     short loc_180039F32
```
