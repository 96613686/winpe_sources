# NptrigHandleTriggerableIo

- ea: `0x14000a460`
- end: `0x14000a4bf`
- name: `NptrigHandleTriggerableIo`
- size: `95`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140001010`
- `0x140008a80`

## callees

- `0x1400017b0`
- `0x140008010`
- `0x14000a460`

## pseudocode

```c
__int64 __fastcall NptrigHandleTriggerableIo(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // eax
  __int64 result; // rax

  v4 = *(_DWORD *)(a1 + 32);
  if ( v4 == 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, a3, a1);
    *(_DWORD *)(a1 + 32) = 1;
LABEL_7:
    result = NptrigFireTrigger((__int64 *)a1, a2, a3, a4);
    if ( (int)result < 0 )
      return result;
    return 0;
  }
  if ( v4 == 1 )
    goto LABEL_7;
  return 0;
}

```

## disassembly

```asm
0x14000a460  push    rbx
0x14000a462  sub     rsp, 20h
0x14000a466  mov     eax, [rcx+20h]
0x14000a469  mov     rbx, rcx
0x14000a46c  cmp     eax, 3
0x14000a46f  jnz     short loc_14000A4A5
0x14000a471  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a478  lea     rax, WPP_GLOBAL_Control
0x14000a47f  cmp     rcx, rax
0x14000a482  jz      short loc_14000A49C
0x14000a484  mov     eax, [rcx+2Ch]
0x14000a487  test    al, 4
0x14000a489  jz      short loc_14000A49C
0x14000a48b  mov     rcx, [rcx+18h]
0x14000a48f  mov     edx, 0Bh
0x14000a494  mov     r9, rbx
0x14000a497  call    WPP_SF_q
0x14000a49c  mov     dword ptr [rbx+20h], 1
0x14000a4a3  jmp     short loc_14000A4AA
0x14000a4a5  cmp     eax, 1
0x14000a4a8  jnz     short loc_14000A4B6
0x14000a4aa  mov     rcx, rbx
0x14000a4ad  call    NptrigFireTrigger
0x14000a4b2  test    eax, eax
0x14000a4b4  js      short loc_14000A4B8
0x14000a4b6  xor     eax, eax
0x14000a4b8  add     rsp, 20h
0x14000a4bc  pop     rbx
0x14000a4bd  retn
```
