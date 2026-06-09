# CControlLogic::GMReset(void)

- ea: `0x180004000`
- end: `0x1800040cd`
- name: `?GMReset@CControlLogic@@AEAAXXZ`
- size: `205`
- prototype: `void __fastcall(CControlLogic *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fb0`
- `0x180005630`

## callees

- `0x180004000`

## pseudocode

```c
void __fastcall CControlLogic::GMReset(CControlLogic *this)
{
  int v1; // r8d
  __int64 v2; // rdx
  __int64 v3; // rax

  v1 = 0;
  v2 = 0;
  do
  {
    *((_WORD *)this + v2 + 1756) = 0;
    *((_DWORD *)this + v2 + 887) = 0;
    v3 = 6 * v2;
    *((_BYTE *)this + v2 + 4460) = 0;
    ++v2;
    *(_QWORD *)((char *)this + 8 * v3 + 3612) = 0;
    *(_QWORD *)((char *)this + 8 * v3 + 3620) = 0;
    *(_QWORD *)((char *)this + 8 * v3 + 3628) = 0;
    *(_QWORD *)((char *)this + 8 * v3 + 3636) = 0;
    *(_QWORD *)((char *)this + 8 * v3 + 3644) = 0;
    *(_QWORD *)((char *)this + 8 * v3 + 3652) = 0;
    LOBYTE(v3) = *((_BYTE *)qword_180016870 + 4 * v2 - 4);
    *((_WORD *)this + v2 + 1651) = 0x3FFF;
    *((_DWORD *)this + v2 + 1094) = 0;
    *((_BYTE *)this + v2 + 4443) = v3;
    *((_DWORD *)this + v2 + 1118) = 0;
    *((_DWORD *)this + v2 + 859) = -2147483632 - v1++;
    *((_BYTE *)this + v2 + 3335) = 0;
    *((_BYTE *)this + v2 + 3351) = 0;
  }
  while ( v1 < 16 );
  *((_BYTE *)this + 4460) = 1;
  *((_DWORD *)this + 886) = 0;
  *((_QWORD *)this + 438) = 0;
}

```

## disassembly

```asm
0x180004000  xor     r9d, r9d
0x180004003  lea     r11, qword_180016870
0x18000400a  mov     r8d, r9d
0x18000400d  mov     edx, r9d
0x180004010  mov     [rcx+rdx*2+0DB8h], r9w
0x180004019  lea     rax, [rdx+rdx*2]
0x18000401d  mov     [rcx+rdx*4+0DDCh], r9d
0x180004025  add     rax, rax
0x180004028  mov     [rdx+rcx+116Ch], r9b
0x180004030  lea     rdx, [rdx+1]
0x180004034  mov     [rcx+rax*8+0E1Ch], r9
0x18000403c  mov     [rcx+rax*8+0E24h], r9
0x180004044  mov     [rcx+rax*8+0E2Ch], r9
0x18000404c  mov     [rcx+rax*8+0E34h], r9
0x180004054  mov     [rcx+rax*8+0E3Ch], r9
0x18000405c  mov     [rcx+rax*8+0E44h], r9
0x180004064  movzx   eax, byte ptr [r11+rdx*4-4]
0x18000406a  mov     word ptr [rcx+rdx*2+0CE6h], 3FFFh
0x180004074  mov     [rcx+rdx*4+1118h], r9d
0x18000407c  mov     [rdx+rcx+115Bh], al
0x180004083  mov     eax, 80000010h
0x180004088  sub     eax, r8d
0x18000408b  mov     [rcx+rdx*4+1178h], r9d
0x180004093  mov     [rcx+rdx*4+0D6Ch], eax
0x18000409a  inc     r8d
0x18000409d  mov     [rdx+rcx+0D07h], r9b
0x1800040a5  mov     [rdx+rcx+0D17h], r9b
0x1800040ad  cmp     r8d, 10h
0x1800040b1  jl      loc_180004010
0x1800040b7  mov     byte ptr [rcx+116Ch], 1
0x1800040be  mov     [rcx+0DD8h], r9d
0x1800040c5  mov     [rcx+0DB0h], r9
0x1800040cc  retn
```
