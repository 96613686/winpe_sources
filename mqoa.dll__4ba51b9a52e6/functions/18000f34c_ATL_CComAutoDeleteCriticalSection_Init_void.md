# ATL::CComAutoDeleteCriticalSection::Init(void)

- ea: `0x18000f34c`
- end: `0x18000f368`
- name: `?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ`
- size: `28`
- prototype: `__int64 __fastcall(ATL::CComAutoDeleteCriticalSection *__hidden this)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000cce4`
- `0x18000cdcc`
- `0x18000ceb4`
- `0x18000d0c0`
- `0x18000d1bc`
- `0x18000d2a4`
- `0x18000d38c`
- `0x18000d474`
- `0x18000d55c`
- `0x18000d644`
- `0x18000d72c`
- `0x18000d814`
- `0x18000d8e4`
- `0x18000d9b4`
- `0x18000db68`
- `0x18000dc4c`
- `0x18000dd00`
- `0x18000ddd0`
- `0x18000de84`
- `0x18000df38`
- `0x18000dfec`
- `0x18000e0a0`
- `0x18000e170`
- `0x18001401c`
- `0x1800140bc`
- `0x18001aa00`
- `0x18001ccdc`
- `0x18001f53c`
- `0x180020a54`
- `0x180025910`

## callees

- `0x18000f34c`
- `0x18000f370`

## pseudocode

```c
__int64 __fastcall ATL::CComAutoDeleteCriticalSection::Init(ATL::CComAutoDeleteCriticalSection *this)
{
  __int64 result; // rax

  result = ATL::CComCriticalSection::Init(this);
  if ( (int)result >= 0 )
    *((_BYTE *)this + 40) = 1;
  return result;
}

```

## disassembly

```asm
0x18000f34c  push    rbx
0x18000f34e  sub     rsp, 20h
0x18000f352  mov     rbx, rcx
0x18000f355  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000f35a  test    eax, eax
0x18000f35c  js      short loc_18000F362
0x18000f35e  mov     byte ptr [rbx+28h], 1
0x18000f362  add     rsp, 20h
0x18000f366  pop     rbx
0x18000f367  retn
```
