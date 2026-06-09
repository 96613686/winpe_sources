# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x180007ffc`
- end: `0x1800080bc`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180008284`
- `0x180008ab0`
- `0x18000ae1c`
- `0x18000b8d0`

## pseudocode

```c
wil::details_abi::UsageIndexes *__fastcall wil::details_abi::UsageIndexes::UsageIndexes(
        wil::details_abi::UsageIndexes *this)
{
  wil::details_abi::UsageIndexes *result; // rax

  *(_DWORD *)this = 0x40000;
  *((_BYTE *)this + 4) = 1;
  result = this;
  *((_BYTE *)this + 8) = 0;
  *((_WORD *)this + 28) = 0;
  *((_BYTE *)this + 58) = 0;
  *((_WORD *)this + 3) = 4;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 2) = 4;
  *((_DWORD *)this + 16) = 0x40000;
  *((_BYTE *)this + 68) = 1;
  *((_WORD *)this + 35) = 4;
  *((_BYTE *)this + 72) = 2;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 10) = 8;
  *((_WORD *)this + 60) = 0;
  *((_BYTE *)this + 122) = 0;
  *((_DWORD *)this + 32) = 0x40000;
  *((_BYTE *)this + 132) = 1;
  *((_WORD *)this + 67) = 0;
  *((_BYTE *)this + 136) = 1;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_WORD *)this + 92) = 0;
  *((_BYTE *)this + 186) = 0;
  return result;
}

```

## disassembly

```asm
0x180007ffc  mov     dword ptr [rcx], 40000h
0x180008002  xor     r8d, r8d
0x180008005  mov     byte ptr [rcx+4], 1
0x180008009  mov     rax, rcx
0x18000800c  mov     [rcx+8], r8b
0x180008010  mov     [rcx+38h], r8w
0x180008015  mov     [rcx+3Ah], r8b
0x180008019  lea     edx, [r8+4]
0x18000801d  mov     [rcx+6], dx
0x180008021  mov     [rcx+18h], r8
0x180008025  mov     [rcx+20h], r8
0x180008029  mov     [rcx+28h], r8
0x18000802d  mov     [rcx+30h], r8
0x180008031  mov     [rcx+10h], rdx
0x180008035  mov     dword ptr [rcx+40h], 40000h
0x18000803c  mov     byte ptr [rcx+44h], 1
0x180008040  mov     [rcx+46h], dx
0x180008044  mov     byte ptr [rcx+48h], 2
0x180008048  mov     [rcx+58h], r8
0x18000804c  mov     [rcx+60h], r8
0x180008050  mov     [rcx+68h], r8
0x180008054  mov     [rcx+70h], r8
0x180008058  mov     qword ptr [rcx+50h], 8
0x180008060  mov     [rcx+78h], r8w
0x180008065  mov     [rcx+7Ah], r8b
0x180008069  mov     dword ptr [rcx+80h], 40000h
0x180008073  mov     byte ptr [rcx+84h], 1
0x18000807a  mov     [rcx+86h], r8w
0x180008082  mov     byte ptr [rcx+88h], 1
0x180008089  mov     [rcx+98h], r8
0x180008090  mov     [rcx+0A0h], r8
0x180008097  mov     [rcx+0A8h], r8
0x18000809e  mov     [rcx+0B0h], r8
0x1800080a5  mov     [rcx+90h], r8
0x1800080ac  mov     [rcx+0B8h], r8w
0x1800080b4  mov     [rcx+0BAh], r8b
0x1800080bb  retn
```
