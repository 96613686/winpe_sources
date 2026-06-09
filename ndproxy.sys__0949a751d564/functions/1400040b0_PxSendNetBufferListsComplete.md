# PxSendNetBufferListsComplete

- ea: `0x1400040b0`
- end: `0x1400040e8`
- name: `PxSendNetBufferListsComplete`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001b54`
- `0x1400040b0`

## pseudocode

```c
PDEVICE_OBJECT *PxSendNetBufferListsComplete()
{
  PDEVICE_OBJECT *result; // rax

  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    return (PDEVICE_OBJECT *)WPP_SF_(
                               WPP_GLOBAL_Control->AttachedDevice,
                               47,
                               WPP_55e376f2a9f936ee4a212904c2347983_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1400040b0  sub     rsp, 28h
0x1400040b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400040bb  lea     rax, WPP_GLOBAL_Control
0x1400040c2  cmp     rcx, rax
0x1400040c5  jz      short loc_1400040E2
0x1400040c7  cmp     byte ptr [rcx+29h], 4
0x1400040cb  jb      short loc_1400040E2
0x1400040cd  mov     rcx, [rcx+18h]
0x1400040d1  lea     r8, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids
0x1400040d8  mov     edx, 2Fh ; '/'
0x1400040dd  call    WPP_SF_
0x1400040e2  add     rsp, 28h
0x1400040e6  retn
```
