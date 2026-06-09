# PxCmCreateVc

- ea: `0x140001f60`
- end: `0x140001f9d`
- name: `PxCmCreateVc`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001b54`
- `0x140001f60`

## pseudocode

```c
__int64 PxCmCreateVc()
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids);
  return 3221225473LL;
}

```

## disassembly

```asm
0x140001f60  sub     rsp, 28h
0x140001f64  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f6b  lea     rax, WPP_GLOBAL_Control
0x140001f72  cmp     rcx, rax
0x140001f75  jz      short loc_140001F92
0x140001f77  cmp     byte ptr [rcx+29h], 1
0x140001f7b  jb      short loc_140001F92
0x140001f7d  mov     rcx, [rcx+18h]
0x140001f81  lea     r8, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids
0x140001f88  mov     edx, 0Ah
0x140001f8d  call    WPP_SF_
0x140001f92  mov     eax, 0C0000001h
0x140001f97  add     rsp, 28h
0x140001f9b  retn
```
