# MschapV2UserPropBuffSize

- ea: `0x180001210`
- end: `0x180001256`
- name: `MschapV2UserPropBuffSize`
- size: `70`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180002040`
- `0x180002f20`
- `0x180003200`
- `0x18000b9b4`
- `0x180016ee0`
- `0x18001cbe4`
- `0x180023fd8`

## callees

- `0x180001210`
- `0x180003bd0`

## pseudocode

```c
__int64 __fastcall MschapV2UserPropBuffSize(__int64 a1)
{
  unsigned int v1; // r9d
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 784);
  result = v1 + 788;
  if ( (unsigned int)result < v1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x2Cu, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids, v1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001210  sub     rsp, 28h
0x180001214  mov     r9d, [rcx+310h]
0x18000121b  lea     eax, [r9+314h]
0x180001222  cmp     eax, r9d
0x180001225  jnb     short loc_180001251
0x180001227  mov     rcx, cs:WPP_GLOBAL_Control
0x18000122e  lea     rax, WPP_GLOBAL_Control
0x180001235  cmp     rcx, rax
0x180001238  jz      short loc_18000124F
0x18000123a  mov     rcx, [rcx+10h]
0x18000123e  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x180001245  mov     edx, 2Ch ; ','
0x18000124a  call    WPP_SF_d
0x18000124f  xor     eax, eax
0x180001251  add     rsp, 28h
0x180001255  retn
```
