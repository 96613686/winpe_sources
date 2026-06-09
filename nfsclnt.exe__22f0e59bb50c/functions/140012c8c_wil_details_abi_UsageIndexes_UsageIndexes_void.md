# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x140012c8c`
- end: `0x140012d4c`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140012f14`
- `0x140013740`
- `0x140015aac`
- `0x140016560`

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
0x140012c8c  mov     dword ptr [rcx], 40000h
0x140012c92  xor     r8d, r8d
0x140012c95  mov     byte ptr [rcx+4], 1
0x140012c99  mov     rax, rcx
0x140012c9c  mov     [rcx+8], r8b
0x140012ca0  mov     [rcx+38h], r8w
0x140012ca5  mov     [rcx+3Ah], r8b
0x140012ca9  lea     edx, [r8+4]
0x140012cad  mov     [rcx+6], dx
0x140012cb1  mov     [rcx+18h], r8
0x140012cb5  mov     [rcx+20h], r8
0x140012cb9  mov     [rcx+28h], r8
0x140012cbd  mov     [rcx+30h], r8
0x140012cc1  mov     [rcx+10h], rdx
0x140012cc5  mov     dword ptr [rcx+40h], 40000h
0x140012ccc  mov     byte ptr [rcx+44h], 1
0x140012cd0  mov     [rcx+46h], dx
0x140012cd4  mov     byte ptr [rcx+48h], 2
0x140012cd8  mov     [rcx+58h], r8
0x140012cdc  mov     [rcx+60h], r8
0x140012ce0  mov     [rcx+68h], r8
0x140012ce4  mov     [rcx+70h], r8
0x140012ce8  mov     qword ptr [rcx+50h], 8
0x140012cf0  mov     [rcx+78h], r8w
0x140012cf5  mov     [rcx+7Ah], r8b
0x140012cf9  mov     dword ptr [rcx+80h], 40000h
0x140012d03  mov     byte ptr [rcx+84h], 1
0x140012d0a  mov     [rcx+86h], r8w
0x140012d12  mov     byte ptr [rcx+88h], 1
0x140012d19  mov     [rcx+98h], r8
0x140012d20  mov     [rcx+0A0h], r8
0x140012d27  mov     [rcx+0A8h], r8
0x140012d2e  mov     [rcx+0B0h], r8
0x140012d35  mov     [rcx+90h], r8
0x140012d3c  mov     [rcx+0B8h], r8w
0x140012d44  mov     [rcx+0BAh], r8b
0x140012d4b  retn
```
