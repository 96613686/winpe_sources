# ValidatePortHandle

- ea: `0x1800121b4`
- end: `0x18001222e`
- name: `ValidatePortHandle`
- size: `122`
- prototype: ``
- caller_count: `56`
- callee_count: `3`
- tags: ``

## callers

- `0x180012050`
- `0x180016740`
- `0x180016860`
- `0x180016990`
- `0x180016ba0`
- `0x180016cd0`
- `0x180016ec0`
- `0x1800171c0`
- `0x1800172d0`
- `0x1800174b0`
- `0x1800175d0`
- `0x180017cb0`
- `0x180017f80`
- `0x1800180b0`
- `0x1800181d0`
- `0x180018920`
- `0x1800190c0`
- `0x180019980`
- `0x18001a0c0`
- `0x18001a890`
- `0x18001aa40`
- `0x18001ab70`
- `0x18001ac80`
- `0x18001adf0`
- `0x18001af20`
- `0x18001b550`
- `0x18001b660`
- `0x18001b7d0`
- `0x18001b920`
- `0x18001ba50`
- `0x18001bb70`
- `0x18001bc80`
- `0x18001bda0`
- `0x18001beb0`
- `0x18001bfc0`
- `0x18001c4a0`
- `0x18001c670`
- `0x18001c8d0`
- `0x18001c9f0`
- `0x18001cb40`
- `0x18001cd80`
- `0x18001cea0`
- `0x18001cfd0`
- `0x18001d0f0`
- `0x18001d210`
- `0x18001d330`
- `0x18001d530`
- `0x18001d650`
- `0x18001d770`
- `0x18001de40`

## callees

- `0x1800121b4`
- `0x180021ae4`
- `0x180021fd4`

## pseudocode

```c
__int64 __fastcall ValidatePortHandle(__int64 a1)
{
  PVOID *v2; // rcx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
      WPP_SF_(v2[2], 11, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  return 1;
}

```

## disassembly

```asm
0x1800121b4  push    rbx
0x1800121b6  sub     rsp, 20h
0x1800121ba  mov     r9, rcx
0x1800121bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121c4  lea     rbx, WPP_GLOBAL_Control
0x1800121cb  cmp     rcx, rbx
0x1800121ce  jz      short loc_1800121E1
0x1800121d0  test    byte ptr [rcx+1Ch], 40h
0x1800121d4  jnz     short loc_1800121ED
0x1800121d6  cmp     rcx, rbx
0x1800121d9  jz      short loc_1800121E1
0x1800121db  test    byte ptr [rcx+1Ch], 40h
0x1800121df  jnz     short loc_180012211
0x1800121e1  mov     eax, 1
0x1800121e6  add     rsp, 20h
0x1800121ea  pop     rbx
0x1800121eb  retn
0x1800121ed  cmp     byte ptr [rcx+19h], 6
0x1800121f1  jb      short loc_1800121D6
0x1800121f3  mov     rcx, [rcx+10h]
0x1800121f7  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800121fe  mov     edx, 0Ah
0x180012203  call    WPP_SF_q
0x180012208  mov     rcx, cs:WPP_GLOBAL_Control
0x18001220f  jmp     short loc_1800121D6
0x180012211  cmp     byte ptr [rcx+19h], 6
0x180012215  jb      short loc_1800121E1
0x180012217  mov     rcx, [rcx+10h]
0x18001221b  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180012222  mov     edx, 0Bh
0x180012227  call    WPP_SF_
0x18001222c  jmp     short loc_1800121E1
```
