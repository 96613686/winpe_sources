# RemoveFileIdTableNode

- ea: `0x14001ddc4`
- end: `0x14001de6f`
- name: `RemoveFileIdTableNode`
- size: `171`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14001af3c`
- `0x14001d37c`
- `0x140024b70`

## callees

- `0x14001d480`
- `0x14001ddc4`
- `0x14001fd54`

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
0x14001ddc4  push    rbx
0x14001ddc6  sub     rsp, 20h
0x14001ddca  mov     rbx, rcx
0x14001ddcd  lea     rdx, [rcx+0C0h]
0x14001ddd4  mov     ecx, 200h
0x14001ddd9  test    [rbx+1Eh], cx
0x14001dddd  jz      short loc_14001DE54
0x14001dddf  mov     r8, [rdx]
0x14001dde2  cmp     r8, rdx
0x14001dde5  jnz     short loc_14001DE13
0x14001dde7  lea     rdx, [rbx+90h]; Links
0x14001ddee  lea     rcx, Root; Root
0x14001ddf5  call    LuafvDeleteElementTable
0x14001ddfa  mov     eax, 0FDFFh
0x14001ddff  and     [rbx+1Eh], ax
0x14001de03  mov     eax, 0FFEFh
0x14001de08  and     [rbx+1Eh], ax
0x14001de0c  add     rsp, 20h
0x14001de10  pop     rbx
0x14001de11  retn
0x14001de13  or      [r8-0A2h], cx
0x14001de1b  mov     rcx, [rdx]
0x14001de1e  cmp     [rcx+8], rdx
0x14001de22  jnz     short loc_14001DE4D
0x14001de24  mov     rax, [rdx+8]
0x14001de28  cmp     [rax], rdx
0x14001de2b  jnz     short loc_14001DE4D
0x14001de2d  mov     [rax], rcx
0x14001de30  lea     rdx, [rbx+90h]
0x14001de37  mov     [rcx+8], rax
0x14001de3b  add     r8, 0FFFFFFFFFFFFFFD0h
0x14001de3f  lea     rcx, Root
0x14001de46  call    LuafvReplaceElementTable
0x14001de4b  jmp     short loc_14001DE03
0x14001de4d  mov     ecx, 3
0x14001de52  int     29h; Win8: RtlFailFast(ecx)
0x14001de54  mov     rax, [rdx]
0x14001de57  cmp     [rax+8], rdx
0x14001de5b  jnz     short loc_14001DE4D
0x14001de5d  mov     rcx, [rdx+8]
0x14001de61  cmp     [rcx], rdx
0x14001de64  jnz     short loc_14001DE4D
0x14001de66  mov     [rcx], rax
0x14001de69  mov     [rax+8], rcx
0x14001de6d  jmp     short loc_14001DE03
```
