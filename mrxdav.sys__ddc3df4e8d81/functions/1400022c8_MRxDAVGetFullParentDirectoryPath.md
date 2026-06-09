# MRxDAVGetFullParentDirectoryPath

- ea: `0x1400022c8`
- end: `0x14000236b`
- name: `MRxDAVGetFullParentDirectoryPath`
- size: `163`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400130e0`

## callees

- `0x1400022c8`

## pseudocode

```c
__int64 __fastcall MRxDAVGetFullParentDirectoryPath(__int64 a1, __int64 a2)
{
  unsigned __int16 v2; // r9
  __int64 v3; // r10
  unsigned __int16 v4; // cx
  unsigned __int16 v5; // r8
  __int64 v6; // rcx
  __int16 v7; // r8

  v2 = 1;
  v3 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 48LL);
  *(_QWORD *)(a2 + 8) = 0;
  v4 = *(_WORD *)(v3 + 88) >> 1;
  if ( v4 > 1u )
  {
    do
    {
      if ( *(_WORD *)(*(_QWORD *)(v3 + 96) + 2LL * v2) == 92 )
        break;
      ++v2;
    }
    while ( v2 < v4 );
  }
  if ( v2 < v4 )
  {
    v5 = v4 - 1;
    if ( (unsigned __int16)(v4 - 1) > v2 )
    {
      v6 = *(_QWORD *)(v3 + 96);
      do
      {
        if ( *(_WORD *)(v6 + 2LL * v5) == 92 )
          break;
        --v5;
      }
      while ( v5 > v2 );
      if ( v2 < v5 )
      {
        v7 = 2 * (v5 - v2);
        *(_WORD *)(a2 + 2) = v7;
        *(_WORD *)a2 = v7;
        *(_QWORD *)(a2 + 8) = v6 + 2LL * v2;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400022c8  mov     [rsp+arg_0], rbx
0x1400022cd  mov     rax, [rcx+30h]
0x1400022d1  mov     ebx, 1
0x1400022d6  movzx   r9d, bx
0x1400022da  mov     r10, [rax+30h]
0x1400022de  mov     qword ptr [rdx+8], 0
0x1400022e6  movzx   ecx, word ptr [r10+58h]
0x1400022eb  shr     cx, 1
0x1400022ee  movzx   r8d, cx
0x1400022f2  cmp     bx, cx
0x1400022f5  jnb     short loc_140002311
0x1400022f7  mov     r11, [r10+60h]
0x1400022fb  movzx   eax, r9w
0x1400022ff  cmp     word ptr [r11+rax*2], 5Ch ; '\'
0x140002305  jz      short loc_140002311
0x140002307  add     r9w, bx
0x14000230b  cmp     r9w, cx
0x14000230f  jb      short loc_1400022FB
0x140002311  cmp     r9w, r8w
0x140002315  jnb     short loc_140002362
0x140002317  sub     r8w, bx
0x14000231b  cmp     r8w, r9w
0x14000231f  jbe     short loc_140002362
0x140002321  mov     rcx, [r10+60h]
0x140002325  movzx   eax, r8w
0x140002329  cmp     word ptr [rcx+rax*2], 5Ch ; '\'
0x14000232e  jz      short loc_14000233F
0x140002330  mov     eax, 0FFFFh
0x140002335  add     r8w, ax
0x140002339  cmp     r8w, r9w
0x14000233d  ja      short loc_140002325
0x14000233f  cmp     r9w, r8w
0x140002343  jnb     short loc_140002362
0x140002345  movzx   eax, r9w
0x140002349  sub     r8w, r9w
0x14000234d  add     r8w, r8w
0x140002351  mov     [rdx+2], r8w
0x140002356  mov     [rdx], r8w
0x14000235a  lea     rcx, [rcx+rax*2]
0x14000235e  mov     [rdx+8], rcx
0x140002362  mov     rbx, [rsp+arg_0]
0x140002367  xor     eax, eax
0x140002369  retn
```
