# PxCoSendNetBufferListsComplete

- ea: `0x140003820`
- end: `0x140003858`
- name: `PxCoSendNetBufferListsComplete`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001b54`
- `0x140003820`

## pseudocode

```c
PDEVICE_OBJECT *PxCoSendNetBufferListsComplete()
{
  PDEVICE_OBJECT *result; // rax

  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    return (PDEVICE_OBJECT *)WPP_SF_(
                               WPP_GLOBAL_Control->AttachedDevice,
                               49,
                               WPP_55e376f2a9f936ee4a212904c2347983_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140003820  sub     rsp, 28h
0x140003824  mov     rcx, cs:WPP_GLOBAL_Control
0x14000382b  lea     rax, WPP_GLOBAL_Control
0x140003832  cmp     rcx, rax
0x140003835  jz      short loc_140003852
0x140003837  cmp     byte ptr [rcx+29h], 4
0x14000383b  jb      short loc_140003852
0x14000383d  mov     rcx, [rcx+18h]
0x140003841  lea     r8, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids
0x140003848  mov     edx, 31h ; '1'
0x14000384d  call    WPP_SF_
0x140003852  add     rsp, 28h
0x140003856  retn
```
