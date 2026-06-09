# std::_Lockit::~_Lockit(void)

- ea: `0x140002310`
- end: `0x140002327`
- name: `??1_Lockit@std@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(std::_Lockit *__hidden this)`
- caller_count: `16`
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
- `0x140010f70`
- `0x140011224`
- `0x14001257c`
- `0x140013070`
- `0x14001d096`
- `0x14001e763`
- `0x14001e84a`

## callees

- `0x140002d90`

## pseudocode

```c
void __fastcall std::_Lockit::~_Lockit(std::_Lockit *this)
{
  Mtxunlock((LPCRITICAL_SECTION)&qword_14002A9B0[5 * *(int *)this]);
}

```

## disassembly

```asm
0x140002310  movsxd  rax, dword ptr [rcx]
0x140002313  lea     rcx, [rax+rax*4]
0x140002317  lea     rax, qword_14002A9B0
0x14000231e  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x140002322  jmp     _Mtxunlock
```
