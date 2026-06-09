# FwRemoveRangesFromPortList(_tag_FW_PORTS *)

- ea: `0x18002ce58`
- end: `0x18002cee9`
- name: `?FwRemoveRangesFromPortList@@YAXPEAU_tag_FW_PORTS@@@Z`
- size: `145`
- prototype: `void __fastcall(struct _tag_FW_PORTS *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010d70`

## callees

- `0x180017d1c`
- `0x18002ce58`

## pseudocode

```c
void __fastcall FwRemoveRangesFromPortList(struct _tag_FW_PORTS *a1)
{
  unsigned int v2; // r8d
  __int64 v3; // rcx
  unsigned int v4; // r9d
  __int16 v5; // r10
  __int64 v6; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 300, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  v2 = 0;
  if ( a1 )
  {
    if ( *((_DWORD *)a1 + 2) )
    {
      v3 = *((_QWORD *)a1 + 2);
      if ( v3 )
      {
        v4 = 0;
        do
        {
          v5 = *(_WORD *)(v3 + 4LL * v2);
          if ( v5 == *(_WORD *)(v3 + 4LL * v2 + 2) )
          {
            v6 = v4++;
            *(_WORD *)(v3 + 4 * v6 + 2) = v5;
            *(_WORD *)(*((_QWORD *)a1 + 2) + 4 * v6) = *(_WORD *)(*((_QWORD *)a1 + 2) + 4 * v6 + 2);
            v3 = *((_QWORD *)a1 + 2);
          }
          ++v2;
        }
        while ( v2 < *((_DWORD *)a1 + 2) );
        *((_DWORD *)a1 + 2) = v4;
      }
    }
  }
}

```

## disassembly

```asm
0x18002ce58  push    rbx
0x18002ce5a  sub     rsp, 20h
0x18002ce5e  mov     rbx, rcx
0x18002ce61  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce68  lea     rax, WPP_GLOBAL_Control
0x18002ce6f  cmp     rcx, rax
0x18002ce72  jz      short loc_18002CE8F
0x18002ce74  test    byte ptr [rcx+1Ch], 8
0x18002ce78  jz      short loc_18002CE8F
0x18002ce7a  mov     rcx, [rcx+10h]
0x18002ce7e  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18002ce85  mov     edx, 12Ch
0x18002ce8a  call    WPP_SF_
0x18002ce8f  xor     r8d, r8d
0x18002ce92  test    rbx, rbx
0x18002ce95  jz      short loc_18002CEE3
0x18002ce97  cmp     [rbx+8], r8d
0x18002ce9b  jbe     short loc_18002CEE3
0x18002ce9d  mov     rcx, [rbx+10h]
0x18002cea1  test    rcx, rcx
0x18002cea4  jz      short loc_18002CEE3
0x18002cea6  mov     r9d, r8d
0x18002cea9  mov     eax, r8d
0x18002ceac  movzx   r10d, word ptr [rcx+rax*4]
0x18002ceb1  cmp     r10w, [rcx+rax*4+2]
0x18002ceb7  jnz     short loc_18002CED6
0x18002ceb9  mov     edx, r9d
0x18002cebc  inc     r9d
0x18002cebf  mov     [rcx+rdx*4+2], r10w
0x18002cec5  mov     rcx, [rbx+10h]
0x18002cec9  movzx   eax, word ptr [rcx+rdx*4+2]
0x18002cece  mov     [rcx+rdx*4], ax
0x18002ced2  mov     rcx, [rbx+10h]
0x18002ced6  inc     r8d
0x18002ced9  cmp     r8d, [rbx+8]
0x18002cedd  jb      short loc_18002CEA9
0x18002cedf  mov     [rbx+8], r9d
0x18002cee3  add     rsp, 20h
0x18002cee7  pop     rbx
0x18002cee8  retn
```
