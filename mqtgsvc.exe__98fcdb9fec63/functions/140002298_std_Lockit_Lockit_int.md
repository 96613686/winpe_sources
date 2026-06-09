# std::_Lockit::_Lockit(int)

- ea: `0x140002298`
- end: `0x1400022c5`
- name: `??0_Lockit@std@@QEAA@H@Z`
- size: `45`
- prototype: `std::_Lockit *__fastcall(std::_Lockit *this, char)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x140002330`
- `0x140002444`
- `0x140002570`
- `0x140002780`
- `0x1400027f0`
- `0x140002840`
- `0x14001050c`
- `0x1400105cc`
- `0x14001068c`
- `0x140010aec`
- `0x140011224`
- `0x14001257c`
- `0x140013070`

## callees

- `0x140002d80`

## pseudocode

```c
std::_Lockit *__fastcall std::_Lockit::_Lockit(std::_Lockit *this, char a2)
{
  unsigned int v2; // edx

  v2 = a2 & 3;
  *(_DWORD *)this = v2;
  Mtxlock((LPCRITICAL_SECTION)&qword_14002A9B0[5 * v2]);
  return this;
}

```

## disassembly

```asm
0x140002298  push    rbx
0x14000229a  sub     rsp, 20h
0x14000229e  and     edx, 3
0x1400022a1  mov     rbx, rcx
0x1400022a4  mov     eax, edx
0x1400022a6  mov     [rcx], eax
0x1400022a8  lea     rcx, qword_14002A9B0
0x1400022af  lea     rax, [rdx+rdx*4]
0x1400022b3  lea     rcx, [rcx+rax*8]; lpCriticalSection
0x1400022b7  call    _Mtxlock
0x1400022bc  mov     rax, rbx
0x1400022bf  add     rsp, 20h
0x1400022c3  pop     rbx
0x1400022c4  retn
```
