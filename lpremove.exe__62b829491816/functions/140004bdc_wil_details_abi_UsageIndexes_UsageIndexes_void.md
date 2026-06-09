# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x140004bdc`
- end: `0x140004c9c`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400052b4`
- `0x1400060b8`
- `0x140009790`
- `0x14000a2a0`

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
0x140004bdc  mov     dword ptr [rcx], 40000h
0x140004be2  xor     r8d, r8d
0x140004be5  mov     byte ptr [rcx+4], 1
0x140004be9  mov     rax, rcx
0x140004bec  mov     [rcx+8], r8b
0x140004bf0  mov     [rcx+38h], r8w
0x140004bf5  mov     [rcx+3Ah], r8b
0x140004bf9  lea     edx, [r8+4]
0x140004bfd  mov     [rcx+6], dx
0x140004c01  mov     [rcx+18h], r8
0x140004c05  mov     [rcx+20h], r8
0x140004c09  mov     [rcx+28h], r8
0x140004c0d  mov     [rcx+30h], r8
0x140004c11  mov     [rcx+10h], rdx
0x140004c15  mov     dword ptr [rcx+40h], 40000h
0x140004c1c  mov     byte ptr [rcx+44h], 1
0x140004c20  mov     [rcx+46h], dx
0x140004c24  mov     byte ptr [rcx+48h], 2
0x140004c28  mov     [rcx+58h], r8
0x140004c2c  mov     [rcx+60h], r8
0x140004c30  mov     [rcx+68h], r8
0x140004c34  mov     [rcx+70h], r8
0x140004c38  mov     qword ptr [rcx+50h], 8
0x140004c40  mov     [rcx+78h], r8w
0x140004c45  mov     [rcx+7Ah], r8b
0x140004c49  mov     dword ptr [rcx+80h], 40000h
0x140004c53  mov     byte ptr [rcx+84h], 1
0x140004c5a  mov     [rcx+86h], r8w
0x140004c62  mov     byte ptr [rcx+88h], 1
0x140004c69  mov     [rcx+98h], r8
0x140004c70  mov     [rcx+0A0h], r8
0x140004c77  mov     [rcx+0A8h], r8
0x140004c7e  mov     [rcx+0B0h], r8
0x140004c85  mov     [rcx+90h], r8
0x140004c8c  mov     [rcx+0B8h], r8w
0x140004c94  mov     [rcx+0BAh], r8b
0x140004c9b  retn
```
