# PxCmDeleteVc

- ea: `0x1400020b0`
- end: `0x1400020ed`
- name: `PxCmDeleteVc`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001b54`
- `0x1400020b0`

## pseudocode

```c
__int64 PxCmDeleteVc()
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids);
  return 3221225473LL;
}

```

## disassembly

```asm
0x1400020b0  sub     rsp, 28h
0x1400020b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400020bb  lea     rax, WPP_GLOBAL_Control
0x1400020c2  cmp     rcx, rax
0x1400020c5  jz      short loc_1400020E2
0x1400020c7  cmp     byte ptr [rcx+29h], 1
0x1400020cb  jb      short loc_1400020E2
0x1400020cd  mov     rcx, [rcx+18h]
0x1400020d1  lea     r8, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids
0x1400020d8  mov     edx, 0Bh
0x1400020dd  call    WPP_SF_
0x1400020e2  mov     eax, 0C0000001h
0x1400020e7  add     rsp, 28h
0x1400020eb  retn
```
