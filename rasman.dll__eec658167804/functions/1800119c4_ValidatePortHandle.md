# ValidatePortHandle

- ea: `0x1800119c4`
- end: `0x180011a3d`
- name: `ValidatePortHandle`
- size: `121`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `56`
- callee_count: `3`
- tags: ``

## callers

- `0x180011860`
- `0x180015da0`
- `0x180015ec0`
- `0x180015ff0`
- `0x180016200`
- `0x180016330`
- `0x180016520`
- `0x180016820`
- `0x180016930`
- `0x180016b10`
- `0x180016c30`
- `0x1800172f0`
- `0x1800175c0`
- `0x1800176f0`
- `0x180017810`
- `0x180017f40`
- `0x1800186d0`
- `0x180018f90`
- `0x1800196d0`
- `0x180019ea0`
- `0x18001a050`
- `0x18001a180`
- `0x18001a290`
- `0x18001a400`
- `0x18001a530`
- `0x18001ab30`
- `0x18001ac40`
- `0x18001adb0`
- `0x18001af00`
- `0x18001b030`
- `0x18001b150`
- `0x18001b260`
- `0x18001b380`
- `0x18001b490`
- `0x18001b5a0`
- `0x18001ba70`
- `0x18001bc30`
- `0x18001be90`
- `0x18001bfb0`
- `0x18001c100`
- `0x18001c340`
- `0x18001c460`
- `0x18001c590`
- `0x18001c6b0`
- `0x18001c7d0`
- `0x18001c8f0`
- `0x18001caf0`
- `0x18001cc10`
- `0x18001cd30`
- `0x18001d3f0`

## callees

- `0x1800119c4`
- `0x180020fd8`
- `0x180021488`

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
0x1800119c4  push    rbx
0x1800119c6  sub     rsp, 20h
0x1800119ca  mov     r9, rcx
0x1800119cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119d4  lea     rbx, WPP_GLOBAL_Control
0x1800119db  cmp     rcx, rbx
0x1800119de  jz      short loc_1800119F1
0x1800119e0  test    byte ptr [rcx+1Ch], 40h
0x1800119e4  jnz     short loc_1800119FC
0x1800119e6  cmp     rcx, rbx
0x1800119e9  jz      short loc_1800119F1
0x1800119eb  test    byte ptr [rcx+1Ch], 40h
0x1800119ef  jnz     short loc_180011A20
0x1800119f1  mov     eax, 1
0x1800119f6  add     rsp, 20h
0x1800119fa  pop     rbx
0x1800119fb  retn
0x1800119fc  cmp     byte ptr [rcx+19h], 6
0x180011a00  jb      short loc_1800119E6
0x180011a02  mov     rcx, [rcx+10h]
0x180011a06  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180011a0d  mov     edx, 0Ah
0x180011a12  call    WPP_SF_q
0x180011a17  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a1e  jmp     short loc_1800119E6
0x180011a20  cmp     byte ptr [rcx+19h], 6
0x180011a24  jb      short loc_1800119F1
0x180011a26  mov     rcx, [rcx+10h]
0x180011a2a  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180011a31  mov     edx, 0Bh
0x180011a36  call    WPP_SF_
0x180011a3b  jmp     short loc_1800119F1
```
