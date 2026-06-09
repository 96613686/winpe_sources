# ATL::CComSafeDeleteCriticalSection::Init(void)

- ea: `0x18000a970`
- end: `0x18000a98c`
- name: `?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ`
- size: `28`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a0f8`
- `0x18000a220`
- `0x18000bfac`
- `0x18000c224`

## callees

- `0x18000a948`
- `0x18000a970`

## pseudocode

```c
__int64 __fastcall ATL::CComSafeDeleteCriticalSection::Init(struct _RTL_CRITICAL_SECTION *this)
{
  __int64 result; // rax

  result = ATL::CComCriticalSection::Init(this);
  if ( (int)result >= 0 )
    LOBYTE(this[1].DebugInfo) = 1;
  return result;
}

```

## disassembly

```asm
0x18000a970  push    rbx
0x18000a972  sub     rsp, 20h
0x18000a976  mov     rbx, rcx
0x18000a979  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000a97e  test    eax, eax
0x18000a980  js      short loc_18000A986
0x18000a982  mov     byte ptr [rbx+28h], 1
0x18000a986  add     rsp, 20h
0x18000a98a  pop     rbx
0x18000a98b  retn
```
