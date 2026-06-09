# NptrigTakeRequestRef

- ea: `0x140001860`
- end: `0x1400018a7`
- name: `NptrigTakeRequestRef`
- size: `71`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009b00`

## callees

- `0x140001220`
- `0x140001860`

## pseudocode

```c
__int64 __fastcall NptrigTakeRequestRef(__int64 a1)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 112));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    return WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_GLOBAL_Control, a1, result);
  return result;
}

```

## disassembly

```asm
0x140001860  sub     rsp, 38h
0x140001864  mov     eax, 1
0x140001869  lock xadd [rcx+70h], eax
0x14000186e  inc     eax
0x140001870  mov     r8, cs:WPP_GLOBAL_Control
0x140001877  lea     rdx, WPP_GLOBAL_Control
0x14000187e  cmp     r8, rdx
0x140001881  jz      short loc_1400018A1
0x140001883  mov     edx, [r8+2Ch]
0x140001887  test    dl, 4
0x14000188a  jz      short loc_1400018A1
0x14000188c  mov     r9, rcx
0x14000188f  mov     [rsp+38h+var_18], eax
0x140001893  mov     rcx, [r8+18h]
0x140001897  mov     edx, 24h ; '$'
0x14000189c  call    WPP_SF_qd
0x1400018a1  add     rsp, 38h
0x1400018a5  retn
```
