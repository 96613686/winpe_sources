# ATL::CComSafeDeleteCriticalSection::Init(void)

- ea: `0x180004f34`
- end: `0x180004f50`
- name: `?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ`
- size: `28`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800044e4`
- `0x180004620`
- `0x18000474c`
- `0x180004888`
- `0x1800049ac`
- `0x180004ac0`
- `0x180004bf0`
- `0x180006664`

## callees

- `0x180004f0c`
- `0x180004f34`

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
0x180004f34  push    rbx
0x180004f36  sub     rsp, 20h
0x180004f3a  mov     rbx, rcx
0x180004f3d  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004f42  test    eax, eax
0x180004f44  js      short loc_180004F4A
0x180004f46  mov     byte ptr [rbx+28h], 1
0x180004f4a  add     rsp, 20h
0x180004f4e  pop     rbx
0x180004f4f  retn
```
