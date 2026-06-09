# OneXCreateDefaultProfile

- ea: `0x18002c3b0`
- end: `0x18002c446`
- name: `OneXCreateDefaultProfile`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005440`
- `0x1800214f0`
- `0x18002c3b0`
- `0x18002c450`

## pseudocode

```c
__int64 __fastcall OneXCreateDefaultProfile(int a1, signed int a2, _DWORD *a3, _QWORD *a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
  v8 = OneXCreateDefaultProfileWithEapMethodId(a1, 25, a2, a3, a4);
  v9 = v8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v8);
  return v9;
}

```

## disassembly

```asm
0x18002c3b0  push    rbx
0x18002c3b2  push    rbp
0x18002c3b3  push    rsi
0x18002c3b4  push    rdi
0x18002c3b5  push    r15
0x18002c3b7  sub     rsp, 30h
0x18002c3bb  mov     rbx, r9
0x18002c3be  mov     rdi, r8
0x18002c3c1  mov     esi, edx
0x18002c3c3  mov     ebp, ecx
0x18002c3c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c3cc  lea     r15, WPP_GLOBAL_Control
0x18002c3d3  cmp     rcx, r15
0x18002c3d6  jz      short loc_18002C3F6
0x18002c3d8  test    dword ptr [rcx+44h], 800h
0x18002c3df  jz      short loc_18002C3F6
0x18002c3e1  mov     rcx, [rcx+38h]
0x18002c3e5  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18002c3ec  mov     edx, 1Bh
0x18002c3f1  call    WPP_SF_
0x18002c3f6  mov     r9, rdi
0x18002c3f9  mov     [rsp+58h+var_38], rbx
0x18002c3fe  mov     r8d, esi
0x18002c401  mov     dl, 19h
0x18002c403  mov     ecx, ebp
0x18002c405  call    OneXCreateDefaultProfileWithEapMethodId
0x18002c40a  mov     ebx, eax
0x18002c40c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c413  cmp     rcx, r15
0x18002c416  jz      short loc_18002C439
0x18002c418  test    dword ptr [rcx+44h], 800h
0x18002c41f  jz      short loc_18002C439
0x18002c421  mov     rcx, [rcx+38h]
0x18002c425  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18002c42c  mov     edx, 1Ch
0x18002c431  mov     r9d, eax
0x18002c434  call    WPP_SF_D
0x18002c439  mov     eax, ebx
0x18002c43b  add     rsp, 30h
0x18002c43f  pop     r15
0x18002c441  pop     rdi
0x18002c442  pop     rsi
0x18002c443  pop     rbp
0x18002c444  pop     rbx
0x18002c445  retn
```
