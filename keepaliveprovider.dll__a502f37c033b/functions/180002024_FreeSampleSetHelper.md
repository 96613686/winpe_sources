# FreeSampleSetHelper

- ea: `0x180002024`
- end: `0x1800020a5`
- name: `FreeSampleSetHelper`
- size: `129`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002cc0`
- `0x1800030a4`

## callees

- `0x180001e20`
- `0x180002024`
- `0x1800020ac`

## pseudocode

```c
__int64 __fastcall FreeSampleSetHelper(__int64 a1)
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
  }
  result = FreeSampleSetHelperTemplate(a1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180002024  mov     [rsp+arg_0], rbx
0x180002029  push    rdi
0x18000202a  sub     rsp, 20h
0x18000202e  mov     rbx, rcx
0x180002031  mov     rcx, cs:WPP_GLOBAL_Control
0x180002038  lea     rdi, WPP_GLOBAL_Control
0x18000203f  cmp     rcx, rdi
0x180002042  jz      short loc_180002065
0x180002044  test    byte ptr [rcx+1Ch], 1
0x180002048  jz      short loc_180002065
0x18000204a  cmp     byte ptr [rcx+19h], 6
0x18000204e  jb      short loc_180002065
0x180002050  mov     rcx, [rcx+10h]
0x180002054  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x18000205b  mov     edx, 0Ah
0x180002060  call    WPP_SF_
0x180002065  mov     rcx, rbx
0x180002068  call    FreeSampleSetHelperTemplate
0x18000206d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002074  cmp     rcx, rdi
0x180002077  jz      short loc_18000209A
0x180002079  test    byte ptr [rcx+1Ch], 1
0x18000207d  jz      short loc_18000209A
0x18000207f  cmp     byte ptr [rcx+19h], 6
0x180002083  jb      short loc_18000209A
0x180002085  mov     rcx, [rcx+10h]
0x180002089  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x180002090  mov     edx, 0Bh
0x180002095  call    WPP_SF_
0x18000209a  mov     rbx, [rsp+28h+arg_0]
0x18000209f  add     rsp, 20h
0x1800020a3  pop     rdi
0x1800020a4  retn
```
