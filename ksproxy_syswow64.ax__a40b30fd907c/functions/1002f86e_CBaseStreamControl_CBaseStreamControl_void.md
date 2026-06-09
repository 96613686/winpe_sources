# CBaseStreamControl::~CBaseStreamControl(void)

- ea: `0x1002f86e`
- end: `0x1002f894`
- name: `??1CBaseStreamControl@@QAE@XZ`
- size: `38`
- prototype: `void __thiscall(CBaseStreamControl *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x100147ad`

## callees

- `0x10006398`
- `0x10033629`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1002f88c`
- `KERNEL32!DeleteCriticalSection` at `0x1002f88c`

## pseudocode

```c
void __thiscall CBaseStreamControl::~CBaseStreamControl(CBaseStreamControl *this)
{
  this->__vftable = (CBaseStreamControl_vtbl *)&CBaseStreamControl::`vftable';
  CBaseStreamControl::SetSyncSource(this, 0);
  CAMEvent::~CAMEvent(&this->m_StreamEvent);
  DeleteCriticalSection(&this->m_CritSec.m_CritSec);
}

```

## disassembly

```asm
0x1002f86e  mov     edi, edi
0x1002f870  push    esi
0x1002f871  mov     esi, ecx
0x1002f873  push    0; struct IReferenceClock *
0x1002f875  mov     dword ptr [esi], offset ??_7CBaseStreamControl@@6B@; const CBaseStreamControl::`vftable'
0x1002f87b  call    ?SetSyncSource@CBaseStreamControl@@QAEXPAUIReferenceClock@@@Z; CBaseStreamControl::SetSyncSource(IReferenceClock *)
0x1002f880  lea     ecx, [esi+4Ch]; this
0x1002f883  call    ??1CAMEvent@@QAE@XZ; CAMEvent::~CAMEvent(void)
0x1002f888  lea     eax, [esi+34h]
0x1002f88b  push    eax; lpCriticalSection
0x1002f88c  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1002f892  pop     esi
0x1002f893  retn
```
