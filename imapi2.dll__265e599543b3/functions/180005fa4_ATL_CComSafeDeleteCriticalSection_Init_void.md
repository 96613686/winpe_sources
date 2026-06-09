# ATL::CComSafeDeleteCriticalSection::Init(void)

- ea: `0x180005fa4`
- end: `0x180005fc0`
- name: `?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ`
- size: `28`
- prototype: `__int64 __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `28`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005a30`
- `0x180005b30`
- `0x180005bf8`
- `0x180005dd4`
- `0x180005ea4`
- `0x18000c084`
- `0x18000ed90`
- `0x18000f278`
- `0x180013ad8`
- `0x180016304`
- `0x1800163e0`
- `0x18001649c`
- `0x180017708`
- `0x1800177a0`
- `0x180017838`
- `0x180017910`
- `0x1800179cc`
- `0x180028208`
- `0x180029394`
- `0x18002de28`
- `0x18002df40`
- `0x1800327e8`
- `0x1800378e8`
- `0x180037a04`
- `0x18003cc58`
- `0x18003cd90`
- `0x18003ce6c`
- `0x1800432c0`

## callees

- `0x180005fa4`
- `0x180006144`

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
0x180005fa4  push    rbx
0x180005fa6  sub     rsp, 20h
0x180005faa  mov     rbx, rcx
0x180005fad  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180005fb2  test    eax, eax
0x180005fb4  js      short loc_180005FBA
0x180005fb6  mov     byte ptr [rbx+28h], 1
0x180005fba  add     rsp, 20h
0x180005fbe  pop     rbx
0x180005fbf  retn
```
