# SupplicantSetUserProfile

- ea: `0x180017460`
- end: `0x180017532`
- name: `SupplicantSetUserProfile`
- size: `210`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180007fb0`
- `0x18000a318`
- `0x18001ce44`
- `0x180028cb8`
- `0x180029ea8`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180017460`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!SetBufferAndLength` at `0x1800174be`
- `MobileNetworking!SetBufferAndLength` at `0x1800174be`

## pseudocode

```c
__int64 __fastcall SupplicantSetUserProfile(__int64 a1, unsigned int a2, __int64 a3)
{
  int v6; // ebp
  __int64 result; // rax
  unsigned int v8; // ebx
  _UNKNOWN **v9; // rcx

  v6 = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x28u, (__int64)WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids);
  result = SetBufferAndLength(a1 + 376, a1 + 368, a3, a2);
  v8 = result;
  if ( !(_DWORD)result )
    goto LABEL_8;
  v9 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x29u, (__int64)WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v6);
LABEL_8:
    v9 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
    WPP_SF_D((__int64)v9[7], 0x2Au, (__int64)WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180017460  push    rbx
0x180017462  push    rbp
0x180017463  push    rsi
0x180017464  push    rdi
0x180017465  push    r14
0x180017467  sub     rsp, 30h
0x18001746b  mov     rax, [rcx]
0x18001746e  mov     rdi, r8
0x180017471  mov     esi, edx
0x180017473  mov     rbx, rcx
0x180017476  mov     ebp, [rax+14h]
0x180017479  mov     rcx, cs:WPP_GLOBAL_Control
0x180017480  lea     r14, WPP_GLOBAL_Control
0x180017487  cmp     rcx, r14
0x18001748a  jz      short loc_1800174AA
0x18001748c  test    dword ptr [rcx+44h], 800h
0x180017493  jz      short loc_1800174AA
0x180017495  mov     rcx, [rcx+38h]
0x180017499  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x1800174a0  mov     edx, 28h ; '('
0x1800174a5  call    WPP_SF_
0x1800174aa  lea     rdx, [rbx+170h]
0x1800174b1  mov     r9d, esi
0x1800174b4  lea     rcx, [rbx+178h]
0x1800174bb  mov     r8, rdi
0x1800174be  call    cs:__imp_SetBufferAndLength
0x1800174c4  mov     ebx, eax
0x1800174c6  test    eax, eax
0x1800174c8  jz      short loc_1800174F8
0x1800174ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800174d1  cmp     rcx, r14
0x1800174d4  jz      short loc_180017527
0x1800174d6  test    byte ptr [rcx+44h], 1
0x1800174da  jz      short loc_1800174FF
0x1800174dc  mov     rcx, [rcx+38h]
0x1800174e0  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x1800174e7  mov     edx, 29h ; ')'
0x1800174ec  mov     [rsp+58h+var_38], eax
0x1800174f0  mov     r9d, ebp
0x1800174f3  call    WPP_SF_dd
0x1800174f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800174ff  cmp     rcx, r14
0x180017502  jz      short loc_180017525
0x180017504  test    dword ptr [rcx+44h], 800h
0x18001750b  jz      short loc_180017525
0x18001750d  mov     rcx, [rcx+38h]
0x180017511  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180017518  mov     edx, 2Ah ; '*'
0x18001751d  mov     r9d, ebx
0x180017520  call    WPP_SF_D
0x180017525  mov     eax, ebx
0x180017527  add     rsp, 30h
0x18001752b  pop     r14
0x18001752d  pop     rdi
0x18001752e  pop     rsi
0x18001752f  pop     rbp
0x180017530  pop     rbx
0x180017531  retn
```
