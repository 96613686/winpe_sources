# TokenBindingGetKeyTypesServer

- ea: `0x180023700`
- end: `0x180023753`
- name: `TokenBindingGetKeyTypesServer`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800049e8`
- `0x180007bd8`
- `0x180023700`

## pseudocode

```c
__int64 __fastcall TokenBindingGetKeyTypesServer(_QWORD *a1)
{
  unsigned int v1; // ebx

  v1 = TBCopyKeyTypes((int *)&qword_180015010, a1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 22, WPP_0c97cf3ebcf83aea482108bb01090baf_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x180023700  push    rbx
0x180023702  sub     rsp, 20h
0x180023706  mov     rdx, rcx
0x180023709  lea     rcx, qword_180015010
0x180023710  call    TBCopyKeyTypes
0x180023715  mov     ebx, eax
0x180023717  mov     rcx, cs:WPP_GLOBAL_Control
0x18002371e  lea     rax, WPP_GLOBAL_Control
0x180023725  cmp     rcx, rax
0x180023728  jz      short loc_18002374A
0x18002372a  mov     edx, [rcx+2Ch]
0x18002372d  test    dl, 4
0x180023730  jz      short loc_18002374A
0x180023732  mov     rcx, [rcx+18h]
0x180023736  lea     r8, WPP_0c97cf3ebcf83aea482108bb01090baf_Traceguids
0x18002373d  mov     edx, 16h
0x180023742  mov     r9d, ebx
0x180023745  call    WPP_SF_D
0x18002374a  mov     eax, ebx
0x18002374c  add     rsp, 20h
0x180023750  pop     rbx
0x180023751  retn
```
