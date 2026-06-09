# write_string_1

- ea: `0x1800406b0`
- end: `0x18004071b`
- name: `write_string_1`
- size: `107`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800407b0`
- `0x1800412f0`
- `0x180042500`

## callees

- `0x180007f00`
- `0x180021a24`
- `0x1800406b0`

## pseudocode

```c
void __fastcall write_string_1(char *a1, int a2, _DWORD *a3)
{
  int v4; // edi

  if ( a2 > 0 )
  {
    v4 = a2;
    while ( putch_nolock(*a1) != -1 )
    {
      if ( ++*a3 == -1 )
        goto LABEL_6;
LABEL_10:
      --v4;
      ++a1;
      if ( v4 <= 0 )
        return;
    }
    *a3 = -1;
LABEL_6:
    if ( *errno() != 42 )
      return;
    if ( putch_nolock(63) == -1 )
      *a3 = -1;
    else
      ++*a3;
    goto LABEL_10;
  }
}

```

## disassembly

```asm
0x1800406b0  test    edx, edx
0x1800406b2  jle     short locret_18004071A
0x1800406b4  mov     [rsp+arg_0], rbx
0x1800406b9  mov     [rsp+arg_8], rsi
0x1800406be  push    rdi
0x1800406bf  sub     rsp, 20h
0x1800406c3  mov     rbx, r8
0x1800406c6  mov     edi, edx
0x1800406c8  mov     rsi, rcx
0x1800406cb  movsx   ecx, byte ptr [rsi]; Ch
0x1800406ce  call    _putch_nolock
0x1800406d3  cmp     eax, 0FFFFFFFFh
0x1800406d6  jnz     short loc_1800406DC
0x1800406d8  mov     [rbx], eax
0x1800406da  jmp     short loc_1800406E3
0x1800406dc  inc     dword ptr [rbx]
0x1800406de  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800406e1  jnz     short loc_180040702
0x1800406e3  call    _errno
0x1800406e8  cmp     dword ptr [rax], 2Ah ; '*'
0x1800406eb  jnz     short loc_18004070B
0x1800406ed  mov     ecx, 3Fh ; '?'; Ch
0x1800406f2  call    _putch_nolock
0x1800406f7  cmp     eax, 0FFFFFFFFh
0x1800406fa  jnz     short loc_180040700
0x1800406fc  mov     [rbx], eax
0x1800406fe  jmp     short loc_180040702
0x180040700  inc     dword ptr [rbx]
0x180040702  dec     edi
0x180040704  inc     rsi
0x180040707  test    edi, edi
0x180040709  jg      short loc_1800406CB
0x18004070b  mov     rbx, [rsp+28h+arg_0]
0x180040710  mov     rsi, [rsp+28h+arg_8]
0x180040715  add     rsp, 20h
0x180040719  pop     rdi
0x18004071a  retn
```
