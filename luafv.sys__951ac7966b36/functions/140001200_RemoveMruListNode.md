# RemoveMruListNode

- ea: `0x140001200`
- end: `0x140001235`
- name: `RemoveMruListNode`
- size: `53`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c420`
- `0x14001d3cc`
- `0x14001d930`

## callees

- `0x140001200`

## pseudocode

```c
__int64 __fastcall RemoveMruListNode(__int64 a1)
{
  __int64 *v1; // rcx
  __int64 result; // rax
  __int64 **v3; // rdx

  v1 = (__int64 *)(a1 + 208);
  result = *v1;
  if ( *v1 )
  {
    if ( *(__int64 **)(result + 8) != v1 || (v3 = (__int64 **)v1[1], *v3 != v1) )
      __fastfail(3u);
    *v3 = (__int64 *)result;
    *(_QWORD *)(result + 8) = v3;
    *v1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140001200  add     rcx, 0D0h
0x140001207  mov     rax, [rcx]
0x14000120a  test    rax, rax
0x14000120d  jz      short locret_14000122C
0x14000120f  cmp     [rax+8], rcx
0x140001213  jnz     short loc_14000122E
0x140001215  mov     rdx, [rcx+8]
0x140001219  cmp     [rdx], rcx
0x14000121c  jnz     short loc_14000122E
0x14000121e  mov     [rdx], rax
0x140001221  mov     [rax+8], rdx
0x140001225  mov     qword ptr [rcx], 0
0x14000122c  retn
0x14000122e  mov     ecx, 3
0x140001233  int     29h; Win8: RtlFailFast(ecx)
```
