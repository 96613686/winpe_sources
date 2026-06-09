# MSMUpdateOneXAuthParams

- ea: `0x180028b14`
- end: `0x180028c45`
- name: `MSMUpdateOneXAuthParams`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180029238`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x1800214f0`
- `0x180028b14`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall MSMUpdateOneXAuthParams(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v3; // edi
  __int64 v5; // r14
  __int64 v7; // r15
  char *v9; // rcx
  int v10; // eax

  v3 = *(_DWORD *)(a1 + 20);
  v5 = *(_QWORD *)(a1 + 192);
  v7 = *(_QWORD *)(a1 + 2368);
  v9 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 82, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
    v9 = (char *)WPP_GLOBAL_Control;
  }
  if ( !*(_QWORD *)(a1 + 2352) )
  {
    if ( v9 == (char *)&WPP_GLOBAL_Control )
      return 0;
    if ( v9[68] >= 0 )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)v9 + 7), 85, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v3);
    goto LABEL_15;
  }
  if ( v9 != (char *)&WPP_GLOBAL_Control && v9[68] < 0 )
    WPP_SF_d(*((_QWORD *)v9 + 7), 83, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v3);
  v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(a1 + 2352))(v5, v7, a2, a3);
  if ( !v10 )
  {
LABEL_15:
    v9 = (char *)WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  v9 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 84, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v3, v10);
    goto LABEL_15;
  }
LABEL_16:
  if ( v9 != (char *)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)v9 + 7), 86, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180028b14  push    rbx
0x180028b16  push    rbp
0x180028b17  push    rsi
0x180028b18  push    rdi
0x180028b19  push    r12
0x180028b1b  push    r13
0x180028b1d  push    r14
0x180028b1f  push    r15
0x180028b21  sub     rsp, 38h
0x180028b25  mov     edi, [rcx+14h]
0x180028b28  mov     rsi, r8
0x180028b2b  mov     r14, [rcx+0C0h]
0x180028b32  mov     ebp, edx
0x180028b34  mov     r15, [rcx+940h]
0x180028b3b  mov     rbx, rcx
0x180028b3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b45  lea     r12, WPP_GLOBAL_Control
0x180028b4c  lea     r13, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180028b53  cmp     rcx, r12
0x180028b56  jz      short loc_180028B79
0x180028b58  test    dword ptr [rcx+44h], 800h
0x180028b5f  jz      short loc_180028B79
0x180028b61  mov     rcx, [rcx+38h]
0x180028b65  mov     edx, 52h ; 'R'
0x180028b6a  mov     r8, r13
0x180028b6d  call    WPP_SF_
0x180028b72  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b79  cmp     qword ptr [rbx+930h], 0
0x180028b81  jz      short loc_180028BEA
0x180028b83  cmp     rcx, r12
0x180028b86  jz      short loc_180028BA2
0x180028b88  test    byte ptr [rcx+44h], 80h
0x180028b8c  jz      short loc_180028BA2
0x180028b8e  mov     rcx, [rcx+38h]
0x180028b92  mov     edx, 53h ; 'S'
0x180028b97  mov     r9d, edi
0x180028b9a  mov     r8, r13
0x180028b9d  call    WPP_SF_d
0x180028ba2  mov     rax, [rbx+930h]
0x180028ba9  mov     r9, rsi
0x180028bac  mov     r8d, ebp
0x180028baf  mov     rdx, r15
0x180028bb2  mov     rcx, r14
0x180028bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bba  test    eax, eax
0x180028bbc  jz      short loc_180028C09
0x180028bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180028bc5  cmp     rcx, r12
0x180028bc8  jz      short loc_180028C32
0x180028bca  test    byte ptr [rcx+44h], 1
0x180028bce  jz      short loc_180028C10
0x180028bd0  mov     rcx, [rcx+38h]
0x180028bd4  mov     edx, 54h ; 'T'
0x180028bd9  mov     r9d, edi
0x180028bdc  mov     [rsp+78h+var_58], eax
0x180028be0  mov     r8, r13
0x180028be3  call    WPP_SF_dd
0x180028be8  jmp     short loc_180028C09
0x180028bea  cmp     rcx, r12
0x180028bed  jz      short loc_180028C32
0x180028bef  test    byte ptr [rcx+44h], 80h
0x180028bf3  jz      short loc_180028C10
0x180028bf5  mov     rcx, [rcx+38h]
0x180028bf9  mov     edx, 55h ; 'U'
0x180028bfe  mov     r9d, edi
0x180028c01  mov     r8, r13
0x180028c04  call    WPP_SF_d
0x180028c09  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c10  cmp     rcx, r12
0x180028c13  jz      short loc_180028C32
0x180028c15  test    dword ptr [rcx+44h], 800h
0x180028c1c  jz      short loc_180028C32
0x180028c1e  mov     rcx, [rcx+38h]
0x180028c22  mov     edx, 56h ; 'V'
0x180028c27  xor     r9d, r9d
0x180028c2a  mov     r8, r13
0x180028c2d  call    WPP_SF_D
0x180028c32  xor     eax, eax
0x180028c34  add     rsp, 38h
0x180028c38  pop     r15
0x180028c3a  pop     r14
0x180028c3c  pop     r13
0x180028c3e  pop     r12
0x180028c40  pop     rdi
0x180028c41  pop     rsi
0x180028c42  pop     rbp
0x180028c43  pop     rbx
0x180028c44  retn
```
