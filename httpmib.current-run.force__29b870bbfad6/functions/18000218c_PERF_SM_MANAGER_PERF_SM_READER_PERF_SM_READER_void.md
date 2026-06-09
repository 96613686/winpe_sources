# PERF_SM_MANAGER::PERF_SM_READER::PERF_SM_READER(void)

- ea: `0x18000218c`
- end: `0x1800021bc`
- name: `??0PERF_SM_READER@PERF_SM_MANAGER@@QEAA@XZ`
- size: `48`
- prototype: `__int64 __fastcall(PERF_SM_MANAGER::PERF_SM_READER *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800027f8`

## pseudocode

```c
PERF_SM_MANAGER::PERF_SM_READER *__fastcall PERF_SM_MANAGER::PERF_SM_READER::PERF_SM_READER(
        PERF_SM_MANAGER::PERF_SM_READER *this)
{
  PERF_SM_MANAGER::PERF_SM_READER *result; // rax

  *(_QWORD *)((char *)this + 28) = 1;
  *(_QWORD *)this = &PERF_SM_MANAGER::PERF_SM_READER::`vftable';
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  result = this;
  *((_QWORD *)this + 1) = 1129467219;
  return result;
}

```

## disassembly

```asm
0x18000218c  lea     rax, ??_7PERF_SM_READER@PERF_SM_MANAGER@@6B@; const PERF_SM_MANAGER::PERF_SM_READER::`vftable'
0x180002193  mov     qword ptr [rcx+1Ch], 1
0x18000219b  mov     [rcx], rax
0x18000219e  xor     eax, eax
0x1800021a0  mov     [rcx+28h], rax
0x1800021a4  mov     [rcx+30h], rax
0x1800021a8  mov     [rcx+38h], rax
0x1800021ac  mov     [rcx+40h], rax
0x1800021b0  mov     rax, rcx
0x1800021b3  mov     qword ptr [rcx+8], 43524D53h
0x1800021bb  retn
```
