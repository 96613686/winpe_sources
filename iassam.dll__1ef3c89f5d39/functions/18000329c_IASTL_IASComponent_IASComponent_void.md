# IASTL::IASComponent::~IASComponent(void)

- ea: `0x18000329c`
- end: `0x1800032f6`
- name: `??1IASComponent@IASTL@@QEAA@XZ`
- size: `90`
- prototype: `void __fastcall(IASTL::IASComponent *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ca8`
- `0x180002dd8`
- `0x180002ebc`
- `0x180002f08`
- `0x1800032fc`

## callees

- `0x180003124`
- `0x18000329c`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800032ac`
- `KERNEL32!Sleep` at `0x1800032ac`
- `rtutils!TraceDeregisterW` at `0x1800032d0`
- `rtutils!TraceDeregisterW` at `0x1800032d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall IASTL::IASComponent::~IASComponent(IASTL::IASComponent *this)
{
  while ( _InterlockedExchange(&lLocked, 1) )
    Sleep(5u);
  if ( !--lRefCount )
  {
    TraceDeregisterW(dwTraceID);
    dwTraceID = -1;
  }
  _InterlockedExchange(&lLocked, 0);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((IASTL::IASComponent *)((char *)this + 16));
}

```

## disassembly

```asm
0x18000329c  push    rbx
0x18000329e  sub     rsp, 20h
0x1800032a2  mov     rbx, rcx
0x1800032a5  jmp     short loc_1800032B2
0x1800032a7  mov     ecx, 5; dwMilliseconds
0x1800032ac  call    cs:__imp_Sleep
0x1800032b2  mov     eax, 1
0x1800032b7  xchg    eax, cs:lLocked
0x1800032bd  test    eax, eax
0x1800032bf  jnz     short loc_1800032A7
0x1800032c1  sub     cs:lRefCount, 1
0x1800032c8  jnz     short loc_1800032E0
0x1800032ca  mov     ecx, cs:dwTraceID; dwTraceID
0x1800032d0  call    cs:__imp_TraceDeregisterW
0x1800032d6  mov     cs:dwTraceID, 0FFFFFFFFh
0x1800032e0  xor     eax, eax
0x1800032e2  xchg    eax, cs:lLocked
0x1800032e8  lea     rcx, [rbx+10h]; this
0x1800032ec  add     rsp, 20h
0x1800032f0  pop     rbx
0x1800032f1  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
