# NatLookupTicket

- ea: `0x14001e0f8`
- end: `0x14001e1ea`
- name: `NatLookupTicket`
- size: `242`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1400058c0`
- `0x14001d05c`
- `0x14001e4e4`
- `0x14001e874`
- `0x14002665c`

## callees

- `0x14000218c`
- `0x14000fe48`
- `0x14001e0f8`

## pseudocode

```c
_QWORD *__fastcall NatLookupTicket(__int64 a1, unsigned __int64 a2, unsigned __int64 a3, _QWORD *a4)
{
  _QWORD *v8; // rax
  _QWORD *i; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_ii(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x49u,
      (__int64)WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids,
      a2,
      a3);
  }
  v8 = (_QWORD *)(a1 + 168);
  for ( i = *(_QWORD **)(a1 + 168); ; i = (_QWORD *)*i )
  {
    if ( i == v8 )
      goto LABEL_11;
    if ( a2 <= i[2] )
    {
      if ( a2 < i[2] )
        goto LABEL_11;
      if ( a3 <= i[3] )
        break;
    }
  }
  if ( a3 < i[3] )
  {
LABEL_11:
    if ( a4 )
      *a4 = i;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x4Bu,
        (__int64)WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x4Au,
      (__int64)WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids);
  }
  return i;
}

```

## disassembly

```asm
0x14001e0f8  push    rbx
0x14001e0fa  push    rsi
0x14001e0fb  push    rdi
0x14001e0fc  push    r13
0x14001e0fe  push    r14
0x14001e100  sub     rsp, 30h
0x14001e104  mov     r14, r9
0x14001e107  mov     rdi, r8
0x14001e10a  mov     rsi, rdx
0x14001e10d  mov     rbx, rcx
0x14001e110  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e117  lea     r13, WPP_GLOBAL_Control
0x14001e11e  cmp     rcx, r13
0x14001e121  jz      short loc_14001E14D
0x14001e123  mov     eax, [rcx+2Ch]
0x14001e126  test    al, 1
0x14001e128  jz      short loc_14001E14D
0x14001e12a  cmp     byte ptr [rcx+29h], 6
0x14001e12e  jb      short loc_14001E14D
0x14001e130  mov     rcx, [rcx+18h]
0x14001e134  mov     edx, 49h ; 'I'
0x14001e139  mov     [rsp+58h+var_38], r8
0x14001e13e  mov     r9, rsi
0x14001e141  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001e148  call    WPP_SF_ii
0x14001e14d  lea     rax, [rbx+0A8h]
0x14001e154  mov     rbx, [rax]
0x14001e157  jmp     short loc_14001E16A
0x14001e159  cmp     rsi, [rbx+10h]
0x14001e15d  ja      short loc_14001E167
0x14001e15f  jb      short loc_14001E16F
0x14001e161  cmp     rdi, [rbx+18h]
0x14001e165  jbe     short loc_14001E1B4
0x14001e167  mov     rbx, [rbx]
0x14001e16a  cmp     rbx, rax
0x14001e16d  jnz     short loc_14001E159
0x14001e16f  test    r14, r14
0x14001e172  jz      short loc_14001E177
0x14001e174  mov     [r14], rbx
0x14001e177  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e17e  cmp     rcx, r13
0x14001e181  jz      short loc_14001E1A5
0x14001e183  mov     eax, [rcx+2Ch]
0x14001e186  test    al, 1
0x14001e188  jz      short loc_14001E1A5
0x14001e18a  cmp     byte ptr [rcx+29h], 6
0x14001e18e  jb      short loc_14001E1A5
0x14001e190  mov     rcx, [rcx+18h]
0x14001e194  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001e19b  mov     edx, 4Bh ; 'K'
0x14001e1a0  call    WPP_SF_
0x14001e1a5  xor     eax, eax
0x14001e1a7  add     rsp, 30h
0x14001e1ab  pop     r14
0x14001e1ad  pop     r13
0x14001e1af  pop     rdi
0x14001e1b0  pop     rsi
0x14001e1b1  pop     rbx
0x14001e1b2  retn
0x14001e1b4  jb      short loc_14001E16F
0x14001e1b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e1bd  cmp     rcx, r13
0x14001e1c0  jz      short loc_14001E1E5
0x14001e1c2  mov     edx, [rcx+2Ch]
0x14001e1c5  test    dl, 1
0x14001e1c8  jz      short loc_14001E1E5
0x14001e1ca  cmp     byte ptr [rcx+29h], 6
0x14001e1ce  jb      short loc_14001E1E5
0x14001e1d0  mov     rcx, [rcx+18h]
0x14001e1d4  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001e1db  mov     edx, 4Ah ; 'J'
0x14001e1e0  call    WPP_SF_
0x14001e1e5  mov     rax, rbx
0x14001e1e8  jmp     short loc_14001E1A7
```
