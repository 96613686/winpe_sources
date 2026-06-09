# RtdspFindEndpoint

- ea: `0x140009830`
- end: `0x140009883`
- name: `RtdspFindEndpoint`
- size: `83`
- prototype: `_QWORD *__fastcall(_QWORD **, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140009340`
- `0x140009410`

## callees

- `0x140009830`

## pseudocode

```c
_QWORD *__fastcall RtdspFindEndpoint(_QWORD **a1, __int64 a2)
{
  _QWORD *i; // r9
  unsigned __int16 *v6; // rax
  __int64 v7; // r8
  int v8; // ecx
  int v9; // edx

  for ( i = *a1; ; i = (_QWORD *)*i )
  {
    if ( i == a1 )
      return 0;
    v6 = (unsigned __int16 *)*(i - 2);
    v7 = a2 - (_QWORD)v6;
    do
    {
      v8 = *(unsigned __int16 *)((char *)v6 + v7);
      v9 = *v6 - v8;
      if ( v9 )
        break;
      ++v6;
    }
    while ( v8 );
    if ( !v9 )
      break;
  }
  return i - 5;
}

```

## disassembly

```asm
0x140009830  sub     rsp, 8
0x140009834  mov     r9, [rcx]
0x140009837  mov     r11, rdx
0x14000983a  mov     r10, rcx
0x14000983d  mov     [rsp+8+var_8], rbx
0x140009841  cmp     r9, r10
0x140009844  jnz     short loc_140009852
0x140009846  xor     eax, eax
0x140009848  mov     rbx, [rsp+8+var_8]
0x14000984c  add     rsp, 8
0x140009850  retn
0x140009852  mov     rax, [r9-10h]
0x140009856  mov     r8, r11
0x140009859  sub     r8, rax
0x14000985c  nop     dword ptr [rax+00h]
0x140009860  movzx   edx, word ptr [rax]
0x140009863  movzx   ecx, word ptr [rax+r8]
0x140009868  sub     edx, ecx
0x14000986a  jnz     short loc_140009874
0x14000986c  add     rax, 2
0x140009870  test    ecx, ecx
0x140009872  jnz     short loc_140009860
0x140009874  test    edx, edx
0x140009876  jz      short loc_14000987D
0x140009878  mov     r9, [r9]
0x14000987b  jmp     short loc_140009841
0x14000987d  lea     rax, [r9-28h]
0x140009881  jmp     short loc_140009848
```
