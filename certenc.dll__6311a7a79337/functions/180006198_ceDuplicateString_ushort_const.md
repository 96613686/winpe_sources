# ceDuplicateString(ushort const *)

- ea: `0x180006198`
- end: `0x18000622d`
- name: `?ceDuplicateString@@YAPEAGPEBG@Z`
- size: `149`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800032e0`
- `0x180003fa0`
- `0x1800081f0`

## callees

- `0x180006198`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800061c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800061c2`

## pseudocode

```c
unsigned __int16 *__fastcall ceDuplicateString(const unsigned __int16 *a1)
{
  __int64 v1; // rbx
  const unsigned __int16 *v2; // rdi
  unsigned __int64 v3; // rbx
  _WORD *v4; // rax
  _WORD *v5; // rdx
  __int64 v6; // rcx
  _WORD *v7; // rcx

  v1 = -1;
  v2 = a1;
  do
    ++v1;
  while ( a1[v1] );
  v3 = v1 + 1;
  v4 = LocalAlloc(0, 2 * v3);
  v5 = v4;
  if ( v4 && v3 )
  {
    if ( v3 <= 0x7FFFFFFF )
    {
      v6 = 2147483646;
      do
      {
        if ( !v6 )
          break;
        if ( !*v2 )
          break;
        *v4++ = *v2++;
        --v6;
        --v3;
      }
      while ( v3 );
      v7 = v4 - 1;
      if ( v3 )
        v7 = v4;
      *v7 = 0;
    }
    else
    {
      *v4 = 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180006198  mov     [rsp+arg_0], rbx
0x18000619d  mov     [rsp+arg_8], rsi
0x1800061a2  push    rdi
0x1800061a3  sub     rsp, 20h
0x1800061a7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800061ab  mov     rdi, rcx
0x1800061ae  xor     esi, esi
0x1800061b0  inc     rbx
0x1800061b3  cmp     [rcx+rbx*2], si
0x1800061b7  jnz     short loc_1800061B0
0x1800061b9  inc     rbx
0x1800061bc  xor     ecx, ecx; uFlags
0x1800061be  lea     rdx, [rbx+rbx]; uBytes
0x1800061c2  call    cs:__imp_LocalAlloc
0x1800061c8  mov     rdx, rax
0x1800061cb  test    rax, rax
0x1800061ce  jz      short loc_18000621A
0x1800061d0  test    rbx, rbx
0x1800061d3  jz      short loc_18000621A
0x1800061d5  cmp     rbx, 7FFFFFFFh
0x1800061dc  jbe     short loc_1800061E3
0x1800061de  mov     [rax], si
0x1800061e1  jmp     short loc_18000621A
0x1800061e3  mov     ecx, 7FFFFFFEh
0x1800061e8  test    rcx, rcx
0x1800061eb  jz      short loc_18000620C
0x1800061ed  movzx   r8d, word ptr [rdi]
0x1800061f1  test    r8w, r8w
0x1800061f5  jz      short loc_18000620C
0x1800061f7  mov     [rax], r8w
0x1800061fb  add     rdi, 2
0x1800061ff  add     rax, 2
0x180006203  dec     rcx
0x180006206  sub     rbx, 1
0x18000620a  jnz     short loc_1800061E8
0x18000620c  test    rbx, rbx
0x18000620f  lea     rcx, [rax-2]
0x180006213  cmovnz  rcx, rax
0x180006217  mov     [rcx], si
0x18000621a  mov     rbx, [rsp+28h+arg_0]
0x18000621f  mov     rax, rdx
0x180006222  mov     rsi, [rsp+28h+arg_8]
0x180006227  add     rsp, 20h
0x18000622b  pop     rdi
0x18000622c  retn
```
