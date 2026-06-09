# CJob::_GetTrigger(ushort)

- ea: `0x1800085d8`
- end: `0x180008604`
- name: `?_GetTrigger@CJob@@AEAAPEAU_TASK_TRIGGER@@G@Z`
- size: `44`
- prototype: `struct _TASK_TRIGGER *__fastcall(CJob *__hidden this, unsigned __int16)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000cff4`
- `0x18000d9a0`
- `0x18000db60`
- `0x18000e2ac`

## callees

- `0x1800085d8`

## pseudocode

```c
struct _TASK_TRIGGER *__fastcall CJob::_GetTrigger(CJob *this, __int16 a2)
{
  unsigned __int16 i; // r9
  struct _TASK_TRIGGER *result; // rax

  for ( i = 0; i < *((_WORD *)this + 16); ++i )
  {
    result = (struct _TASK_TRIGGER *)(48LL * i + *((_QWORD *)this + 3));
    if ( result->Reserved1 == a2 )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x1800085d8  xor     r9d, r9d
0x1800085db  cmp     r9w, [rcx+20h]
0x1800085e0  jnb     short loc_180008601
0x1800085e2  movzx   eax, r9w
0x1800085e6  lea     r8, [rax+rax*2]
0x1800085ea  mov     rax, [rcx+18h]
0x1800085ee  shl     r8, 4
0x1800085f2  add     rax, r8
0x1800085f5  cmp     [rax+2], dx
0x1800085f9  jz      short locret_180008603
0x1800085fb  inc     r9w
0x1800085ff  jmp     short loc_1800085DB
0x180008601  xor     eax, eax
0x180008603  retn
```
