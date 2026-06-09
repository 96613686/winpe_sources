# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x1800044c0`
- end: `0x180004580`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180004894`
- `0x1800050c0`
- `0x1800088e0`
- `0x180009394`

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
0x1800044c0  mov     dword ptr [rcx], 40000h
0x1800044c6  xor     r8d, r8d
0x1800044c9  mov     byte ptr [rcx+4], 1
0x1800044cd  mov     rax, rcx
0x1800044d0  mov     [rcx+8], r8b
0x1800044d4  mov     [rcx+38h], r8w
0x1800044d9  mov     [rcx+3Ah], r8b
0x1800044dd  lea     edx, [r8+4]
0x1800044e1  mov     [rcx+6], dx
0x1800044e5  mov     [rcx+18h], r8
0x1800044e9  mov     [rcx+20h], r8
0x1800044ed  mov     [rcx+28h], r8
0x1800044f1  mov     [rcx+30h], r8
0x1800044f5  mov     [rcx+10h], rdx
0x1800044f9  mov     dword ptr [rcx+40h], 40000h
0x180004500  mov     byte ptr [rcx+44h], 1
0x180004504  mov     [rcx+46h], dx
0x180004508  mov     byte ptr [rcx+48h], 2
0x18000450c  mov     [rcx+58h], r8
0x180004510  mov     [rcx+60h], r8
0x180004514  mov     [rcx+68h], r8
0x180004518  mov     [rcx+70h], r8
0x18000451c  mov     qword ptr [rcx+50h], 8
0x180004524  mov     [rcx+78h], r8w
0x180004529  mov     [rcx+7Ah], r8b
0x18000452d  mov     dword ptr [rcx+80h], 40000h
0x180004537  mov     byte ptr [rcx+84h], 1
0x18000453e  mov     [rcx+86h], r8w
0x180004546  mov     byte ptr [rcx+88h], 1
0x18000454d  mov     [rcx+98h], r8
0x180004554  mov     [rcx+0A0h], r8
0x18000455b  mov     [rcx+0A8h], r8
0x180004562  mov     [rcx+0B0h], r8
0x180004569  mov     [rcx+90h], r8
0x180004570  mov     [rcx+0B8h], r8w
0x180004578  mov     [rcx+0BAh], r8b
0x18000457f  retn
```
