# TokenBindingGetKeyTypesServer

- ea: `0x180023750`
- end: `0x1800237a3`
- name: `TokenBindingGetKeyTypesServer`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800049e8`
- `0x180007bd8`
- `0x180023750`

## pseudocode

```c
__int64 __fastcall TokenBindingGetKeyTypesServer(_QWORD *a1)
{
  unsigned int v1; // ebx

  v1 = TBCopyKeyTypes((int *)&unk_180015010, a1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 22, &WPP_0c97cf3ebcf83aea482108bb01090baf_Traceguids);
  return v1;
}

```

## disassembly

```asm
0x180023750  push    rbx
0x180023752  sub     rsp, 20h
0x180023756  mov     rdx, rcx
0x180023759  lea     rcx, unk_180015010
0x180023760  call    TBCopyKeyTypes
0x180023765  mov     ebx, eax
0x180023767  mov     rcx, cs:WPP_GLOBAL_Control
0x18002376e  lea     rax, WPP_GLOBAL_Control
0x180023775  cmp     rcx, rax
0x180023778  jz      short loc_18002379A
0x18002377a  mov     edx, [rcx+2Ch]
0x18002377d  test    dl, 4
0x180023780  jz      short loc_18002379A
0x180023782  mov     rcx, [rcx+18h]
0x180023786  lea     r8, WPP_0c97cf3ebcf83aea482108bb01090baf_Traceguids
0x18002378d  mov     edx, 16h
0x180023792  mov     r9d, ebx
0x180023795  call    WPP_SF_D
0x18002379a  mov     eax, ebx
0x18002379c  add     rsp, 20h
0x1800237a0  pop     rbx
0x1800237a1  retn
```
