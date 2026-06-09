# DrDeallocateForSrvOpen

- ea: `0x1400178d0`
- end: `0x14001790d`
- name: `DrDeallocateForSrvOpen`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000324c`
- `0x1400178d0`

## pseudocode

```c
__int64 DrDeallocateForSrvOpen()
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
  return 3221225474LL;
}

```

## disassembly

```asm
0x1400178d0  sub     rsp, 28h
0x1400178d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400178db  lea     rax, WPP_GLOBAL_Control
0x1400178e2  cmp     rcx, rax
0x1400178e5  jz      short loc_140017902
0x1400178e7  cmp     byte ptr [rcx+29h], 4
0x1400178eb  jb      short loc_140017902
0x1400178ed  mov     rcx, [rcx+18h]
0x1400178f1  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x1400178f8  mov     edx, 55h ; 'U'
0x1400178fd  call    WPP_SF_
0x140017902  mov     eax, 0C0000002h
0x140017907  add     rsp, 28h
0x14001790b  retn
```
