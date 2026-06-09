# NatLookupAddressPoolEntry

- ea: `0x140013ccc`
- end: `0x140013dc3`
- name: `NatLookupAddressPoolEntry`
- size: `247`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140011e00`
- `0x14001308c`
- `0x140013550`
- `0x140013dcc`

## callees

- `0x14000218c`
- `0x140002200`
- `0x140013ccc`

## pseudocode

```c
_QWORD *__fastcall NatLookupAddressPoolEntry(_QWORD *a1, unsigned int a2, unsigned int a3, _QWORD *a4)
{
  __int64 v5; // rsi
  __int64 v6; // rbp
  _QWORD *v8; // rax
  unsigned __int64 v9; // rcx

  v5 = a3;
  v6 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_dd(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x58u,
      (__int64)WPP_96cec5cc952234920ba0014d840adb44_Traceguids,
      a2,
      a3);
  }
  if ( a1 )
  {
    v9 = v5 | (v6 << 32);
    while ( 1 )
    {
      v8 = a1;
      if ( v9 >= a1[5] )
      {
        if ( v9 <= a1[5] )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
          {
            WPP_SF_(
              (__int64)WPP_GLOBAL_Control->AttachedDevice,
              0x59u,
              (__int64)WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
          }
          return a1;
        }
        a1 = (_QWORD *)a1[2];
      }
      else
      {
        a1 = (_QWORD *)a1[1];
      }
      if ( !a1 )
        goto LABEL_13;
    }
  }
  v8 = 0;
LABEL_13:
  if ( a4 )
    *a4 = v8;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x5Au,
      (__int64)WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140013ccc  push    rbx
0x140013cce  push    rbp
0x140013ccf  push    rsi
0x140013cd0  push    rdi
0x140013cd1  push    r13
0x140013cd3  sub     rsp, 30h
0x140013cd7  mov     rdi, r9
0x140013cda  mov     esi, r8d
0x140013cdd  mov     ebp, edx
0x140013cdf  mov     rbx, rcx
0x140013ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x140013ce9  lea     r13, WPP_GLOBAL_Control
0x140013cf0  cmp     rcx, r13
0x140013cf3  jz      short loc_140013D1E
0x140013cf5  mov     eax, [rcx+2Ch]
0x140013cf8  test    al, 1
0x140013cfa  jz      short loc_140013D1E
0x140013cfc  cmp     byte ptr [rcx+29h], 6
0x140013d00  jb      short loc_140013D1E
0x140013d02  mov     rcx, [rcx+18h]
0x140013d06  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140013d0d  mov     edx, 58h ; 'X'
0x140013d12  mov     [rsp+58h+var_38], esi
0x140013d16  mov     r9d, ebp
0x140013d19  call    WPP_SF_dd
0x140013d1e  test    rbx, rbx
0x140013d21  jnz     short loc_140013D27
0x140013d23  xor     eax, eax
0x140013d25  jmp     short loc_140013D4B
0x140013d27  mov     rcx, rbp
0x140013d2a  shl     rcx, 20h
0x140013d2e  or      rcx, rsi
0x140013d31  mov     rax, rbx
0x140013d34  cmp     rcx, [rbx+28h]
0x140013d38  jnb     short loc_140013D40
0x140013d3a  mov     rbx, [rbx+8]
0x140013d3e  jmp     short loc_140013D46
0x140013d40  jbe     short loc_140013D85
0x140013d42  mov     rbx, [rbx+10h]
0x140013d46  test    rbx, rbx
0x140013d49  jnz     short loc_140013D31
0x140013d4b  test    rdi, rdi
0x140013d4e  jz      short loc_140013D53
0x140013d50  mov     [rdi], rax
0x140013d53  mov     rcx, cs:WPP_GLOBAL_Control
0x140013d5a  cmp     rcx, r13
0x140013d5d  jz      short loc_140013D81
0x140013d5f  mov     eax, [rcx+2Ch]
0x140013d62  test    al, 1
0x140013d64  jz      short loc_140013D81
0x140013d66  cmp     byte ptr [rcx+29h], 6
0x140013d6a  jb      short loc_140013D81
0x140013d6c  mov     rcx, [rcx+18h]
0x140013d70  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140013d77  mov     edx, 5Ah ; 'Z'
0x140013d7c  call    WPP_SF_
0x140013d81  xor     eax, eax
0x140013d83  jmp     short loc_140013DB7
0x140013d85  mov     rcx, cs:WPP_GLOBAL_Control
0x140013d8c  cmp     rcx, r13
0x140013d8f  jz      short loc_140013DB4
0x140013d91  mov     edx, [rcx+2Ch]
0x140013d94  test    dl, 1
0x140013d97  jz      short loc_140013DB4
0x140013d99  cmp     byte ptr [rcx+29h], 6
0x140013d9d  jb      short loc_140013DB4
0x140013d9f  mov     rcx, [rcx+18h]
0x140013da3  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140013daa  mov     edx, 59h ; 'Y'
0x140013daf  call    WPP_SF_
0x140013db4  mov     rax, rbx
0x140013db7  add     rsp, 30h
0x140013dbb  pop     r13
0x140013dbd  pop     rdi
0x140013dbe  pop     rsi
0x140013dbf  pop     rbp
0x140013dc0  pop     rbx
0x140013dc1  retn
```
