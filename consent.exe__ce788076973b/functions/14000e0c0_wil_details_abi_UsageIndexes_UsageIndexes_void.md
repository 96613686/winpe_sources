# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x14000e0c0`
- end: `0x14000e1d8`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `280`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d7c0`
- `0x14000e028`
- `0x140016968`
- `0x140016d2c`

## callees

- `0x140008fe0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::UsageIndexes::UsageIndexes(wil::details_abi::UsageIndexes *this)
{
  unsigned __int64 Size; // rax
  __int64 v2; // r8
  __int64 v3; // r10
  __int16 v4; // r9
  unsigned __int64 v5; // rax
  __int64 v6; // r8
  __int64 result; // rax
  __int64 v8; // r10
  __int16 v9; // [rsp+20h] [rbp-20h] BYREF
  char v10; // [rsp+22h] [rbp-1Eh]
  int v11; // [rsp+24h] [rbp-1Ch]
  __int16 v12; // [rsp+28h] [rbp-18h]
  __int128 v13; // [rsp+30h] [rbp-10h]

  *(_DWORD *)this = 0x40000;
  *((_BYTE *)this + 4) = 1;
  *((_BYTE *)this + 8) = 0;
  v10 = 0;
  v11 = 0;
  *((_WORD *)this + 3) = 4;
  v9 = 4;
  v12 = 0;
  v13 = 0;
  Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v9);
  *(_QWORD *)(v2 + 16) = Size;
  *(_QWORD *)(v2 + 24) = v3;
  *(_QWORD *)(v2 + 32) = v3;
  *(_QWORD *)(v2 + 40) = v3;
  *(_QWORD *)(v2 + 48) = v3;
  *(_WORD *)(v2 + 56) = v3;
  *(_BYTE *)(v2 + 58) = v3;
  *(_DWORD *)(v2 + 64) = 0x40000;
  *(_BYTE *)(v2 + 68) = 1;
  *(_WORD *)(v2 + 70) = v4;
  *(_BYTE *)(v2 + 72) = 2;
  v9 = v4;
  v10 = 2;
  v11 = v3;
  v12 = v3;
  v13 = 0;
  v5 = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v9);
  *(_QWORD *)(v6 + 80) = v5;
  result = v6;
  *(_QWORD *)(v6 + 88) = v8;
  *(_QWORD *)(v6 + 96) = v8;
  *(_QWORD *)(v6 + 104) = v8;
  *(_QWORD *)(v6 + 112) = v8;
  *(_WORD *)(v6 + 120) = v8;
  *(_BYTE *)(v6 + 122) = v8;
  *(_DWORD *)(v6 + 128) = 0x40000;
  *(_BYTE *)(v6 + 132) = 1;
  *(_WORD *)(v6 + 134) = v8;
  *(_BYTE *)(v6 + 136) = 1;
  *(_QWORD *)(v6 + 144) = v8;
  *(_QWORD *)(v6 + 152) = v8;
  *(_QWORD *)(v6 + 160) = v8;
  *(_QWORD *)(v6 + 168) = v8;
  *(_QWORD *)(v6 + 176) = v8;
  *(_WORD *)(v6 + 184) = v8;
  *(_BYTE *)(v6 + 186) = v8;
  return result;
}

```

## disassembly

```asm
0x14000e0c0  push    rbp
0x14000e0c2  mov     rbp, rsp
0x14000e0c5  sub     rsp, 40h
0x14000e0c9  xor     r10d, r10d
0x14000e0cc  mov     dword ptr [rcx], 40000h
0x14000e0d2  mov     r8, rcx
0x14000e0d5  mov     byte ptr [rcx+4], 1
0x14000e0d9  mov     [rcx+8], r10b
0x14000e0dd  xorps   xmm0, xmm0
0x14000e0e0  mov     [rbp+var_1E], r10b
0x14000e0e4  lea     r9d, [r10+4]
0x14000e0e8  mov     [rbp+var_1C], r10d
0x14000e0ec  mov     [rcx+6], r9w
0x14000e0f1  lea     rcx, [rbp+var_20]; this
0x14000e0f5  mov     [rbp+var_20], r9w
0x14000e0fa  mov     [rbp+var_18], r10w
0x14000e0ff  movdqu  [rbp+var_10], xmm0
0x14000e104  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x14000e109  mov     [r8+10h], rax
0x14000e10d  lea     rcx, [rbp+var_20]; this
0x14000e111  mov     [r8+18h], r10
0x14000e115  mov     [r8+20h], r10
0x14000e119  mov     [r8+28h], r10
0x14000e11d  mov     [r8+30h], r10
0x14000e121  mov     [r8+38h], r10w
0x14000e126  mov     [r8+3Ah], r10b
0x14000e12a  mov     dword ptr [r8+40h], 40000h
0x14000e132  mov     byte ptr [r8+44h], 1
0x14000e137  mov     [r8+46h], r9w
0x14000e13c  mov     byte ptr [r8+48h], 2
0x14000e141  mov     [rbp+var_20], r9w
0x14000e146  mov     [rbp+var_1E], 2
0x14000e14a  mov     [rbp+var_1C], r10d
0x14000e14e  mov     [rbp+var_18], r10w
0x14000e153  movdqu  [rbp+var_10], xmm0
0x14000e158  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x14000e15d  mov     [r8+50h], rax
0x14000e161  mov     rax, r8
0x14000e164  mov     [r8+58h], r10
0x14000e168  mov     [r8+60h], r10
0x14000e16c  mov     [r8+68h], r10
0x14000e170  mov     [r8+70h], r10
0x14000e174  mov     [r8+78h], r10w
0x14000e179  mov     [r8+7Ah], r10b
0x14000e17d  mov     dword ptr [r8+80h], 40000h
0x14000e188  mov     byte ptr [r8+84h], 1
0x14000e190  mov     [r8+86h], r10w
0x14000e198  mov     byte ptr [r8+88h], 1
0x14000e1a0  mov     [r8+90h], r10
0x14000e1a7  mov     [r8+98h], r10
0x14000e1ae  mov     [r8+0A0h], r10
0x14000e1b5  mov     [r8+0A8h], r10
0x14000e1bc  mov     [r8+0B0h], r10
0x14000e1c3  mov     [r8+0B8h], r10w
0x14000e1cb  mov     [r8+0BAh], r10b
0x14000e1d2  add     rsp, 40h
0x14000e1d6  pop     rbp
0x14000e1d7  retn
```
