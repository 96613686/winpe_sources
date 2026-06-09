# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x18000c968`
- end: `0x18000ca28`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000cb24`
- `0x18000cf30`
- `0x180010210`
- `0x180010bb0`

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
0x18000c968  mov     dword ptr [rcx], 40000h
0x18000c96e  xor     r8d, r8d
0x18000c971  mov     byte ptr [rcx+4], 1
0x18000c975  mov     rax, rcx
0x18000c978  mov     [rcx+8], r8b
0x18000c97c  mov     [rcx+38h], r8w
0x18000c981  mov     [rcx+3Ah], r8b
0x18000c985  lea     edx, [r8+4]
0x18000c989  mov     [rcx+6], dx
0x18000c98d  mov     [rcx+18h], r8
0x18000c991  mov     [rcx+20h], r8
0x18000c995  mov     [rcx+28h], r8
0x18000c999  mov     [rcx+30h], r8
0x18000c99d  mov     [rcx+10h], rdx
0x18000c9a1  mov     dword ptr [rcx+40h], 40000h
0x18000c9a8  mov     byte ptr [rcx+44h], 1
0x18000c9ac  mov     [rcx+46h], dx
0x18000c9b0  mov     byte ptr [rcx+48h], 2
0x18000c9b4  mov     [rcx+58h], r8
0x18000c9b8  mov     [rcx+60h], r8
0x18000c9bc  mov     [rcx+68h], r8
0x18000c9c0  mov     [rcx+70h], r8
0x18000c9c4  mov     qword ptr [rcx+50h], 8
0x18000c9cc  mov     [rcx+78h], r8w
0x18000c9d1  mov     [rcx+7Ah], r8b
0x18000c9d5  mov     dword ptr [rcx+80h], 40000h
0x18000c9df  mov     byte ptr [rcx+84h], 1
0x18000c9e6  mov     [rcx+86h], r8w
0x18000c9ee  mov     byte ptr [rcx+88h], 1
0x18000c9f5  mov     [rcx+98h], r8
0x18000c9fc  mov     [rcx+0A0h], r8
0x18000ca03  mov     [rcx+0A8h], r8
0x18000ca0a  mov     [rcx+0B0h], r8
0x18000ca11  mov     [rcx+90h], r8
0x18000ca18  mov     [rcx+0B8h], r8w
0x18000ca20  mov     [rcx+0BAh], r8b
0x18000ca27  retn
```
