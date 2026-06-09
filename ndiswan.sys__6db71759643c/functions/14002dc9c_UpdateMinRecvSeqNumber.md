# UpdateMinRecvSeqNumber

- ea: `0x14002dc9c`
- end: `0x14002dd73`
- name: `UpdateMinRecvSeqNumber`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14002c9e0`

## callees

- `0x14000a2c0`
- `0x14002dc9c`

## pseudocode

```c
__int64 __fastcall UpdateMinRecvSeqNumber(__int64 a1, unsigned int a2)
{
  __int64 v2; // r14
  _QWORD *v3; // r15
  _QWORD **v4; // rdi
  __int64 v6; // rsi
  __int64 result; // rax
  __int64 v8; // r9
  _QWORD *i; // rcx
  unsigned int v10; // edx

  v2 = a2;
  v3 = (_QWORD *)(a1 + 48);
  v4 = *(_QWORD ***)(a1 + 48);
  v6 = 5LL * a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    result = WPP_SF_d(
               WPP_GLOBAL_Control->AttachedDevice,
               46,
               WPP_52604c4400d53a16edd48a543f00e082_Traceguids,
               *(unsigned int *)(a1 + 40LL * a2 + 240));
  }
  v8 = HIDWORD(v4[v2 + 12]);
  *(_DWORD *)(a1 + 8 * v6 + 240) = v8;
  for ( i = *v4; i != v3; i = (_QWORD *)*i )
  {
    v10 = HIDWORD(i[v2 + 12]);
    if ( v10 != (_DWORD)v8 && ((v10 - (_DWORD)v8) & *(_DWORD *)(a1 + 252)) != 0 )
    {
      *(_DWORD *)(a1 + 8 * v6 + 240) = v10;
      v8 = v10;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    return WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_52604c4400d53a16edd48a543f00e082_Traceguids, v8);
  }
  return result;
}

```

## disassembly

```asm
0x14002dc9c  push    rbx
0x14002dc9e  push    rsi
0x14002dc9f  push    rdi
0x14002dca0  push    r12
0x14002dca2  push    r14
0x14002dca4  push    r15
0x14002dca6  sub     rsp, 28h
0x14002dcaa  mov     r14d, edx
0x14002dcad  lea     r15, [rcx+30h]
0x14002dcb1  mov     rdi, [r15]
0x14002dcb4  mov     rbx, rcx
0x14002dcb7  lea     rsi, [r14+r14*4]
0x14002dcbb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dcc2  lea     r12, WPP_GLOBAL_Control
0x14002dcc9  cmp     rcx, r12
0x14002dccc  jz      short loc_14002DCFA
0x14002dcce  test    dword ptr [rcx+2Ch], 800h
0x14002dcd5  jz      short loc_14002DCFA
0x14002dcd7  cmp     byte ptr [rcx+29h], 4
0x14002dcdb  jb      short loc_14002DCFA
0x14002dcdd  mov     r9d, [rbx+rsi*8+0F0h]
0x14002dce5  lea     r8, WPP_52604c4400d53a16edd48a543f00e082_Traceguids
0x14002dcec  mov     rcx, [rcx+18h]
0x14002dcf0  mov     edx, 2Eh ; '.'
0x14002dcf5  call    WPP_SF_d
0x14002dcfa  mov     r9d, [rdi+r14*8+64h]
0x14002dcff  mov     [rbx+rsi*8+0F0h], r9d
0x14002dd07  mov     rcx, [rdi]
0x14002dd0a  jmp     short loc_14002DD2F
0x14002dd0c  mov     edx, [rcx+r14*8+64h]
0x14002dd11  mov     r8d, edx
0x14002dd14  sub     r8d, r9d
0x14002dd17  jz      short loc_14002DD2C
0x14002dd19  test    [rbx+0FCh], r8d
0x14002dd20  jz      short loc_14002DD2C
0x14002dd22  mov     [rbx+rsi*8+0F0h], edx
0x14002dd29  mov     r9d, edx
0x14002dd2c  mov     rcx, [rcx]
0x14002dd2f  cmp     rcx, r15
0x14002dd32  jnz     short loc_14002DD0C
0x14002dd34  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dd3b  cmp     rcx, r12
0x14002dd3e  jz      short loc_14002DD64
0x14002dd40  test    dword ptr [rcx+2Ch], 800h
0x14002dd47  jz      short loc_14002DD64
0x14002dd49  cmp     byte ptr [rcx+29h], 4
0x14002dd4d  jb      short loc_14002DD64
0x14002dd4f  mov     rcx, [rcx+18h]
0x14002dd53  lea     r8, WPP_52604c4400d53a16edd48a543f00e082_Traceguids
0x14002dd5a  mov     edx, 2Fh ; '/'
0x14002dd5f  call    WPP_SF_d
0x14002dd64  add     rsp, 28h
0x14002dd68  pop     r15
0x14002dd6a  pop     r14
0x14002dd6c  pop     r12
0x14002dd6e  pop     rdi
0x14002dd6f  pop     rsi
0x14002dd70  pop     rbx
0x14002dd71  retn
```
