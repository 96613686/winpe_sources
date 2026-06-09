# ATL::CComSafeDeleteCriticalSection::Init(void)

- ea: `0x180002d44`
- end: `0x180002d60`
- name: `?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ`
- size: `28`
- prototype: `__int64 __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002504`
- `0x180004220`
- `0x180006988`
- `0x180009b78`
- `0x180009c6c`
- `0x180009d90`
- `0x180009e88`
- `0x180009f90`
- `0x18000b7bc`
- `0x18000ba34`

## callees

- `0x180002d1c`
- `0x180002d44`

## pseudocode

```c
__int64 __fastcall ATL::CComSafeDeleteCriticalSection::Init(ATL::CComSafeDeleteCriticalSection *this)
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
0x180002d44  push    rbx
0x180002d46  sub     rsp, 20h
0x180002d4a  mov     rbx, rcx
0x180002d4d  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180002d52  test    eax, eax
0x180002d54  js      short loc_180002D5A
0x180002d56  mov     byte ptr [rbx+28h], 1
0x180002d5a  add     rsp, 20h
0x180002d5e  pop     rbx
0x180002d5f  retn
```
