# RemoveFileIdTableNode

- ea: `0x14001de14`
- end: `0x14001debf`
- name: `RemoveFileIdTableNode`
- size: `171`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14001af8c`
- `0x14001d3cc`
- `0x140024bc0`

## callees

- `0x14001d4d0`
- `0x14001de14`
- `0x14001fda4`

## pseudocode

```c
__int64 __fastcall RemoveFileIdTableNode(__int64 a1)
{
  _QWORD *v2; // rdx
  __int64 v3; // r8
  __int64 result; // rax
  __int64 v5; // rcx
  _QWORD *v6; // rax
  __int64 v7; // rax
  _QWORD *v8; // rcx

  v2 = (_QWORD *)(a1 + 192);
  if ( (*(_WORD *)(a1 + 30) & 0x200) == 0 )
  {
    v7 = *v2;
    if ( *(_QWORD **)(*v2 + 8LL) == v2 )
    {
      v8 = *(_QWORD **)(a1 + 200);
      if ( (_QWORD *)*v8 == v2 )
      {
        *v8 = v7;
        *(_QWORD *)(v7 + 8) = v8;
        goto LABEL_4;
      }
    }
    goto LABEL_8;
  }
  v3 = *v2;
  if ( (_QWORD *)*v2 != v2 )
  {
    *(_WORD *)(v3 - 162) |= 0x200u;
    v5 = *v2;
    if ( *(_QWORD **)(*v2 + 8LL) == v2 )
    {
      v6 = (_QWORD *)v2[1];
      if ( (_QWORD *)*v6 == v2 )
      {
        *v6 = v5;
        *(_QWORD *)(v5 + 8) = v6;
        LuafvReplaceElementTable(&Root, a1 + 144, v3 - 48);
        goto LABEL_4;
      }
    }
LABEL_8:
    __fastfail(3u);
  }
  LuafvDeleteElementTable(&Root, (PRTL_SPLAY_LINKS)(a1 + 144));
  *(_WORD *)(a1 + 30) &= ~0x200u;
LABEL_4:
  result = 65519;
  *(_WORD *)(a1 + 30) &= ~0x10u;
  return result;
}

```

## disassembly

```asm
0x14001de14  push    rbx
0x14001de16  sub     rsp, 20h
0x14001de1a  mov     rbx, rcx
0x14001de1d  lea     rdx, [rcx+0C0h]
0x14001de24  mov     ecx, 200h
0x14001de29  test    [rbx+1Eh], cx
0x14001de2d  jz      short loc_14001DEA4
0x14001de2f  mov     r8, [rdx]
0x14001de32  cmp     r8, rdx
0x14001de35  jnz     short loc_14001DE63
0x14001de37  lea     rdx, [rbx+90h]; Links
0x14001de3e  lea     rcx, Root; Root
0x14001de45  call    LuafvDeleteElementTable
0x14001de4a  mov     eax, 0FDFFh
0x14001de4f  and     [rbx+1Eh], ax
0x14001de53  mov     eax, 0FFEFh
0x14001de58  and     [rbx+1Eh], ax
0x14001de5c  add     rsp, 20h
0x14001de60  pop     rbx
0x14001de61  retn
0x14001de63  or      [r8-0A2h], cx
0x14001de6b  mov     rcx, [rdx]
0x14001de6e  cmp     [rcx+8], rdx
0x14001de72  jnz     short loc_14001DE9D
0x14001de74  mov     rax, [rdx+8]
0x14001de78  cmp     [rax], rdx
0x14001de7b  jnz     short loc_14001DE9D
0x14001de7d  mov     [rax], rcx
0x14001de80  lea     rdx, [rbx+90h]
0x14001de87  mov     [rcx+8], rax
0x14001de8b  add     r8, 0FFFFFFFFFFFFFFD0h
0x14001de8f  lea     rcx, Root
0x14001de96  call    LuafvReplaceElementTable
0x14001de9b  jmp     short loc_14001DE53
0x14001de9d  mov     ecx, 3
0x14001dea2  int     29h; Win8: RtlFailFast(ecx)
0x14001dea4  mov     rax, [rdx]
0x14001dea7  cmp     [rax+8], rdx
0x14001deab  jnz     short loc_14001DE9D
0x14001dead  mov     rcx, [rdx+8]
0x14001deb1  cmp     [rcx], rdx
0x14001deb4  jnz     short loc_14001DE9D
0x14001deb6  mov     [rcx], rax
0x14001deb9  mov     [rax+8], rcx
0x14001debd  jmp     short loc_14001DE53
```
