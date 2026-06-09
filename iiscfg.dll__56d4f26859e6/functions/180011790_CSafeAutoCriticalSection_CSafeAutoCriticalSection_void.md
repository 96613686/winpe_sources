# CSafeAutoCriticalSection::~CSafeAutoCriticalSection(void)

- ea: `0x180011790`
- end: `0x1800117ab`
- name: `??1CSafeAutoCriticalSection@@QEAA@XZ`
- size: `27`
- prototype: `void __fastcall(CSafeAutoCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002ef60`
- `0x18002efc0`
- `0x18002f030`
- `0x18002f050`
- `0x18002f070`

## callees

- `0x180011790`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800117a0`
- `KERNEL32!DeleteCriticalSection` at `0x1800117a0`

## pseudocode

```c
void __fastcall CSafeAutoCriticalSection::~CSafeAutoCriticalSection(CSafeAutoCriticalSection *this)
{
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 10, 0, 1) == 1 )
    DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x180011790  sub     rsp, 28h
0x180011794  xor     edx, edx
0x180011796  lea     eax, [rdx+1]
0x180011799  lock cmpxchg [rcx+28h], edx
0x18001179e  jnz     short loc_1800117A6
0x1800117a0  call    cs:__imp_DeleteCriticalSection
0x1800117a6  add     rsp, 28h
0x1800117aa  retn
```
