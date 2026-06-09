# ValidateConnectionHandle

- ea: `0x180011f80`
- end: `0x18001203e`
- name: `ValidateConnectionHandle`
- size: `190`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180012050`
- `0x180017e20`
- `0x1800190c0`
- `0x180019470`
- `0x18001b130`
- `0x18001b7d0`
- `0x18001fba0`

## callees

- `0x180011f80`
- `0x180021ae4`
- `0x180021fd4`

## pseudocode

```c
__int64 __fastcall ValidateConnectionHandle(_QWORD *a1)
{
  PVOID *v2; // rcx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xDu, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 || *a1 )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
      WPP_SF_((TRACEHANDLE)v2[2], 0xFu, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    return 1;
  }
  else
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
      WPP_SF_((TRACEHANDLE)v2[2], 0xEu, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    return 0;
  }
}

```

## disassembly

```asm
0x180011f80  mov     [rsp+arg_0], rbx
0x180011f85  push    rdi
0x180011f86  sub     rsp, 20h
0x180011f8a  mov     rbx, rcx
0x180011f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f94  lea     rdi, WPP_GLOBAL_Control
0x180011f9b  cmp     rcx, rdi
0x180011f9e  jz      short loc_180011FA6
0x180011fa0  test    byte ptr [rcx+1Ch], 40h
0x180011fa4  jnz     short loc_180011FC7
0x180011fa6  test    rbx, rbx
0x180011fa9  jnz     short loc_180011FEE
0x180011fab  cmp     rcx, rdi
0x180011fae  jz      short loc_180011FB6
0x180011fb0  test    byte ptr [rcx+1Ch], 40h
0x180011fb4  jnz     short loc_18001201E
0x180011fb6  mov     eax, 1
0x180011fbb  mov     rbx, [rsp+28h+arg_0]
0x180011fc0  add     rsp, 20h
0x180011fc4  pop     rdi
0x180011fc5  retn
0x180011fc7  cmp     byte ptr [rcx+19h], 6
0x180011fcb  jb      short loc_180011FA6
0x180011fcd  mov     rcx, [rcx+10h]
0x180011fd1  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180011fd8  mov     edx, 0Dh
0x180011fdd  mov     r9, rbx
0x180011fe0  call    WPP_SF_q
0x180011fe5  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fec  jmp     short loc_180011FA6
0x180011fee  cmp     qword ptr [rbx], 0
0x180011ff2  jnz     short loc_180011FAB
0x180011ff4  cmp     rcx, rdi
0x180011ff7  jz      short loc_18001201A
0x180011ff9  test    byte ptr [rcx+1Ch], 40h
0x180011ffd  jz      short loc_18001201A
0x180011fff  cmp     byte ptr [rcx+19h], 6
0x180012003  jb      short loc_18001201A
0x180012005  mov     rcx, [rcx+10h]
0x180012009  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180012010  mov     edx, 0Eh
0x180012015  call    WPP_SF_
0x18001201a  xor     eax, eax
0x18001201c  jmp     short loc_180011FBB
0x18001201e  cmp     byte ptr [rcx+19h], 6
0x180012022  jb      short loc_180011FB6
0x180012024  mov     rcx, [rcx+10h]
0x180012028  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001202f  mov     edx, 0Fh
0x180012034  call    WPP_SF_
0x180012039  jmp     loc_180011FB6
```
