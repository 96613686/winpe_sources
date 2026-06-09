# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x1400038d8`
- end: `0x140003998`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140003bcc`
- `0x140004680`
- `0x1400074a4`
- `0x140007f30`

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
0x1400038d8  mov     dword ptr [rcx], 40000h
0x1400038de  xor     r8d, r8d
0x1400038e1  mov     byte ptr [rcx+4], 1
0x1400038e5  mov     rax, rcx
0x1400038e8  mov     [rcx+8], r8b
0x1400038ec  mov     [rcx+38h], r8w
0x1400038f1  mov     [rcx+3Ah], r8b
0x1400038f5  lea     edx, [r8+4]
0x1400038f9  mov     [rcx+6], dx
0x1400038fd  mov     [rcx+18h], r8
0x140003901  mov     [rcx+20h], r8
0x140003905  mov     [rcx+28h], r8
0x140003909  mov     [rcx+30h], r8
0x14000390d  mov     [rcx+10h], rdx
0x140003911  mov     dword ptr [rcx+40h], 40000h
0x140003918  mov     byte ptr [rcx+44h], 1
0x14000391c  mov     [rcx+46h], dx
0x140003920  mov     byte ptr [rcx+48h], 2
0x140003924  mov     [rcx+58h], r8
0x140003928  mov     [rcx+60h], r8
0x14000392c  mov     [rcx+68h], r8
0x140003930  mov     [rcx+70h], r8
0x140003934  mov     qword ptr [rcx+50h], 8
0x14000393c  mov     [rcx+78h], r8w
0x140003941  mov     [rcx+7Ah], r8b
0x140003945  mov     dword ptr [rcx+80h], 40000h
0x14000394f  mov     byte ptr [rcx+84h], 1
0x140003956  mov     [rcx+86h], r8w
0x14000395e  mov     byte ptr [rcx+88h], 1
0x140003965  mov     [rcx+98h], r8
0x14000396c  mov     [rcx+0A0h], r8
0x140003973  mov     [rcx+0A8h], r8
0x14000397a  mov     [rcx+0B0h], r8
0x140003981  mov     [rcx+90h], r8
0x140003988  mov     [rcx+0B8h], r8w
0x140003990  mov     [rcx+0BAh], r8b
0x140003997  retn
```
