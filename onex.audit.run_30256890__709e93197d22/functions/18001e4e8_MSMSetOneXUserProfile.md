# MSMSetOneXUserProfile

- ea: `0x18001e4e8`
- end: `0x18001e657`
- name: `MSMSetOneXUserProfile`
- size: `367`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18001b360`
- `0x1800280d0`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x18001e4e8`
- `0x1800214f0`
- `0x180030010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18001e576`
- `MobileNetworking!ReleaseWriteLock` at `0x18001e576`
- `MobileNetworking!AcquireWriteLock` at `0x18001e5e5`
- `MobileNetworking!AcquireWriteLock` at `0x18001e5e5`

## pseudocode

```c
__int64 __fastcall MSMSetOneXUserProfile(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  unsigned int v4; // edi
  __int64 v6; // r12
  __int64 v8; // r13
  char *v11; // rcx
  int v12; // eax

  v4 = *(_DWORD *)(a1 + 20);
  v6 = *(_QWORD *)(a1 + 192);
  v8 = *(_QWORD *)(a1 + 2368);
  v11 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 62, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
    v11 = (char *)WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)(a1 + 2312) )
  {
    ReleaseWriteLock(a1, a1 + 2896, "MSMSetOneXUserProfile", 630);
    v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, __int64))(a1 + 2312))(v6, v8, a2, a3, a4);
    if ( v12 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 63, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v4, v12);
    AcquireWriteLock(a1, a1 + 2896, "MSMSetOneXUserProfile", 654);
    goto LABEL_13;
  }
  if ( v11 == (char *)&WPP_GLOBAL_Control )
    return 0;
  if ( v11[68] < 0 )
  {
    WPP_SF_d(*((_QWORD *)v11 + 7), 64, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v4);
LABEL_13:
    v11 = (char *)WPP_GLOBAL_Control;
  }
  if ( v11 != (char *)&WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)v11 + 7), 65, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18001e4e8  push    rbx
0x18001e4ea  push    rbp
0x18001e4eb  push    rsi
0x18001e4ec  push    rdi
0x18001e4ed  push    r12
0x18001e4ef  push    r13
0x18001e4f1  push    r14
0x18001e4f3  push    r15
0x18001e4f5  sub     rsp, 38h
0x18001e4f9  mov     edi, [rcx+14h]
0x18001e4fc  mov     rbp, r9
0x18001e4ff  mov     r12, [rcx+0C0h]
0x18001e506  mov     r14d, r8d
0x18001e509  mov     r13, [rcx+940h]
0x18001e510  mov     r15, rdx
0x18001e513  mov     rbx, rcx
0x18001e516  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e51d  lea     rsi, WPP_GLOBAL_Control
0x18001e524  cmp     rcx, rsi
0x18001e527  jz      short loc_18001E54E
0x18001e529  test    dword ptr [rcx+44h], 800h
0x18001e530  jz      short loc_18001E54E
0x18001e532  mov     rcx, [rcx+38h]
0x18001e536  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18001e53d  mov     edx, 3Eh ; '>'
0x18001e542  call    WPP_SF_
0x18001e547  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e54e  cmp     qword ptr [rbx+908h], 0
0x18001e556  jz      loc_18001E5F4
0x18001e55c  lea     rsi, [rbx+0B50h]
0x18001e563  mov     r9d, 276h
0x18001e569  mov     rdx, rsi
0x18001e56c  lea     r8, aMsmsetonexuser; "MSMSetOneXUserProfile"
0x18001e573  mov     rcx, rbx
0x18001e576  call    cs:__imp_ReleaseWriteLock
0x18001e57c  mov     rax, [rbx+908h]
0x18001e583  mov     r9d, r14d
0x18001e586  mov     r8, r15
0x18001e589  mov     [rsp+78h+var_58], rbp
0x18001e58e  mov     rdx, r13
0x18001e591  mov     rcx, r12
0x18001e594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e599  test    eax, eax
0x18001e59b  jz      short loc_18001E5D2
0x18001e59d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5a4  lea     rdx, WPP_GLOBAL_Control
0x18001e5ab  cmp     rcx, rdx
0x18001e5ae  jz      short loc_18001E5D2
0x18001e5b0  test    byte ptr [rcx+44h], 1
0x18001e5b4  jz      short loc_18001E5D2
0x18001e5b6  mov     rcx, [rcx+38h]
0x18001e5ba  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18001e5c1  mov     edx, 3Fh ; '?'
0x18001e5c6  mov     dword ptr [rsp+78h+var_58], eax
0x18001e5ca  mov     r9d, edi
0x18001e5cd  call    WPP_SF_dd
0x18001e5d2  mov     r9d, 28Eh
0x18001e5d8  lea     r8, aMsmsetonexuser; "MSMSetOneXUserProfile"
0x18001e5df  mov     rdx, rsi
0x18001e5e2  mov     rcx, rbx
0x18001e5e5  call    cs:__imp_AcquireWriteLock
0x18001e5eb  lea     rsi, WPP_GLOBAL_Control
0x18001e5f2  jmp     short loc_18001E617
0x18001e5f4  cmp     rcx, rsi
0x18001e5f7  jz      short loc_18001E644
0x18001e5f9  test    byte ptr [rcx+44h], 80h
0x18001e5fd  jz      short loc_18001E61E
0x18001e5ff  mov     rcx, [rcx+38h]
0x18001e603  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18001e60a  mov     edx, 40h ; '@'
0x18001e60f  mov     r9d, edi
0x18001e612  call    WPP_SF_d
0x18001e617  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e61e  cmp     rcx, rsi
0x18001e621  jz      short loc_18001E644
0x18001e623  test    dword ptr [rcx+44h], 800h
0x18001e62a  jz      short loc_18001E644
0x18001e62c  mov     rcx, [rcx+38h]
0x18001e630  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18001e637  mov     edx, 41h ; 'A'
0x18001e63c  xor     r9d, r9d
0x18001e63f  call    WPP_SF_D
0x18001e644  xor     eax, eax
0x18001e646  add     rsp, 38h
0x18001e64a  pop     r15
0x18001e64c  pop     r14
0x18001e64e  pop     r13
0x18001e650  pop     r12
0x18001e652  pop     rdi
0x18001e653  pop     rsi
0x18001e654  pop     rbp
0x18001e655  pop     rbx
0x18001e656  retn
```
