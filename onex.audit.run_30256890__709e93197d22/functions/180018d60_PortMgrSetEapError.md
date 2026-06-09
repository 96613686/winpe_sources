# PortMgrSetEapError

- ea: `0x180018d60`
- end: `0x180018e49`
- name: `PortMgrSetEapError`
- size: `233`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x180015f90`
- `0x18001ba00`
- `0x18001d654`
- `0x180022960`
- `0x1800230c0`
- `0x180026194`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180018d60`
- `0x1800214f0`
- `0x180021c50`
- `0x180022104`

## pseudocode

```c
__int64 __fastcall PortMgrSetEapError(__int64 a1, __int64 a2)
{
  int v2; // ebp
  unsigned int v5; // ebx
  _UNKNOWN **v6; // rcx
  __int64 result; // rax

  v2 = *(_DWORD *)(a1 + 20);
  v5 = 0;
  v6 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x42u, (__int64)WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
    v6 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)(a1 + 104) )
  {
    FreeEapError(*(_QWORD *)(a1 + 104));
    *(_QWORD *)(a1 + 104) = 0;
    v6 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( !a2 )
    goto LABEL_12;
  result = DuplicateEapError(a2, (_QWORD *)(a1 + 104));
  v5 = result;
  if ( !(_DWORD)result )
    goto LABEL_11;
  v6 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x43u, (__int64)WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v2);
LABEL_11:
    v6 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
LABEL_12:
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 17) & 0x800) != 0 )
    WPP_SF_D((__int64)v6[7], 0x44u, (__int64)WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180018d60  push    rbx
0x180018d62  push    rbp
0x180018d63  push    rsi
0x180018d64  push    rdi
0x180018d65  push    r14
0x180018d67  sub     rsp, 30h
0x180018d6b  mov     ebp, [rcx+14h]
0x180018d6e  mov     rsi, rdx
0x180018d71  mov     rdi, rcx
0x180018d74  xor     ebx, ebx
0x180018d76  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d7d  lea     r14, WPP_GLOBAL_Control
0x180018d84  cmp     rcx, r14
0x180018d87  jz      short loc_180018DAE
0x180018d89  test    dword ptr [rcx+44h], 800h
0x180018d90  jz      short loc_180018DAE
0x180018d92  mov     rcx, [rcx+38h]
0x180018d96  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180018d9d  mov     edx, 42h ; 'B'
0x180018da2  call    WPP_SF_
0x180018da7  mov     rcx, cs:WPP_GLOBAL_Control
0x180018dae  mov     rax, [rdi+68h]
0x180018db2  test    rax, rax
0x180018db5  jz      short loc_180018DCA
0x180018db7  mov     rcx, rax
0x180018dba  call    FreeEapError
0x180018dbf  mov     [rdi+68h], rbx
0x180018dc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180018dca  test    rsi, rsi
0x180018dcd  jz      short loc_180018E16
0x180018dcf  lea     rdx, [rdi+68h]
0x180018dd3  mov     rcx, rsi
0x180018dd6  call    DuplicateEapError
0x180018ddb  mov     ebx, eax
0x180018ddd  test    eax, eax
0x180018ddf  jz      short loc_180018E0F
0x180018de1  mov     rcx, cs:WPP_GLOBAL_Control
0x180018de8  cmp     rcx, r14
0x180018deb  jz      short loc_180018E3E
0x180018ded  test    byte ptr [rcx+44h], 1
0x180018df1  jz      short loc_180018E16
0x180018df3  mov     rcx, [rcx+38h]
0x180018df7  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180018dfe  mov     edx, 43h ; 'C'
0x180018e03  mov     [rsp+58h+var_38], eax
0x180018e07  mov     r9d, ebp
0x180018e0a  call    WPP_SF_dd
0x180018e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e16  cmp     rcx, r14
0x180018e19  jz      short loc_180018E3C
0x180018e1b  test    dword ptr [rcx+44h], 800h
0x180018e22  jz      short loc_180018E3C
0x180018e24  mov     rcx, [rcx+38h]
0x180018e28  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180018e2f  mov     edx, 44h ; 'D'
0x180018e34  mov     r9d, ebx
0x180018e37  call    WPP_SF_D
0x180018e3c  mov     eax, ebx
0x180018e3e  add     rsp, 30h
0x180018e42  pop     r14
0x180018e44  pop     rdi
0x180018e45  pop     rsi
0x180018e46  pop     rbp
0x180018e47  pop     rbx
0x180018e48  retn
```
