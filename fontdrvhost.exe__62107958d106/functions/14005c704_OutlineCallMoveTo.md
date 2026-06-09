# OutlineCallMoveTo

- ea: `0x14005c704`
- end: `0x14005c74d`
- name: `OutlineCallMoveTo`
- size: `73`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14005c660`
- `0x14005ddc0`
- `0x140061cd0`

## callees

- `0x140041030`
- `0x14005c704`

## pseudocode

```c
_DWORD *__fastcall OutlineCallMoveTo(__int64 a1)
{
  unsigned __int64 v2; // rax
  _DWORD *v3; // rdx
  _DWORD *result; // rax

  v2 = *(_QWORD *)(a1 + 64) + 40LL;
  *(_DWORD *)(a1 + 80) = 0;
  if ( v2 >= *(_QWORD *)(a1 + 72) )
    OutlineGetMemory();
  v3 = *(_DWORD **)(a1 + 64);
  *v3 = 21;
  v3[3] = *(_DWORD *)(a1 + 84);
  v3[4] = *(_DWORD *)(a1 + 88);
  result = v3 + 5;
  *(_QWORD *)(a1 + 64) = v3 + 5;
  return result;
}

```

## disassembly

```asm
0x14005c704  push    rbx
0x14005c706  sub     rsp, 20h
0x14005c70a  mov     rax, [rcx+40h]
0x14005c70e  mov     rbx, rcx
0x14005c711  add     rax, 28h ; '('
0x14005c715  mov     dword ptr [rcx+50h], 0
0x14005c71c  cmp     rax, [rcx+48h]
0x14005c720  jnb     short loc_14005C746
0x14005c722  mov     rdx, [rbx+40h]
0x14005c726  mov     dword ptr [rdx], 15h
0x14005c72c  mov     eax, [rbx+54h]
0x14005c72f  mov     [rdx+0Ch], eax
0x14005c732  mov     eax, [rbx+58h]
0x14005c735  mov     [rdx+10h], eax
0x14005c738  lea     rax, [rdx+14h]
0x14005c73c  mov     [rbx+40h], rax
0x14005c740  add     rsp, 20h
0x14005c744  pop     rbx
0x14005c745  retn
0x14005c746  call    OutlineGetMemory
0x14005c74b  jmp     short loc_14005C722
```
