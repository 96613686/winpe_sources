# CTimeX86::~CTimeX86(void)

- ea: `0x18000a084`
- end: `0x18000a0bc`
- name: `??1CTimeX86@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(CTimeX86 *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002a0f0`

## callees

- `0x18000a084`
- `0x18000a6d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a0b5`

## pseudocode

```c
void __fastcall CTimeX86::~CTimeX86(CTimeX86 *this, unsigned __int64 a2)
{
  void *v3; // rcx

  v3 = (void *)*((_QWORD *)this + 74);
  if ( v3 )
  {
    operator delete(v3, a2);
    *((_QWORD *)this + 74) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 11344));
}

```

## disassembly

```asm
0x18000a084  push    rbx
0x18000a086  sub     rsp, 20h
0x18000a08a  mov     rbx, rcx
0x18000a08d  mov     rcx, [rcx+250h]; void *
0x18000a094  test    rcx, rcx
0x18000a097  jz      short loc_18000A0A9
0x18000a099  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a09e  mov     qword ptr [rbx+250h], 0
0x18000a0a9  lea     rcx, [rbx+2C50h]
0x18000a0b0  add     rsp, 20h
0x18000a0b4  pop     rbx
0x18000a0b5  jmp     cs:__imp_DeleteCriticalSection
```
