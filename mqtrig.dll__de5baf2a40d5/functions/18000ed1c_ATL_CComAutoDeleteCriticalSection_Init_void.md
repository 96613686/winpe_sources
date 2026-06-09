# ATL::CComAutoDeleteCriticalSection::Init(void)

- ea: `0x18000ed1c`
- end: `0x18000ed38`
- name: `?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ`
- size: `28`
- prototype: `__int64 __fastcall(ATL::CComAutoDeleteCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dffc`
- `0x18000e0e4`
- `0x18000e2a0`
- `0x18000e388`
- `0x18000e488`
- `0x18000e570`
- `0x18000e690`

## callees

- `0x18000ed1c`
- `0x18000ed40`

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
0x18000ed1c  push    rbx
0x18000ed1e  sub     rsp, 20h
0x18000ed22  mov     rbx, rcx
0x18000ed25  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000ed2a  test    eax, eax
0x18000ed2c  js      short loc_18000ED32
0x18000ed2e  mov     byte ptr [rbx+28h], 1
0x18000ed32  add     rsp, 20h
0x18000ed36  pop     rbx
0x18000ed37  retn
```
