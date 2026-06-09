# CMUtil::~CMUtil(void)

- ea: `0x1800237f8`
- end: `0x180023853`
- name: `??1CMUtil@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180035980`

## callees

- `0x1800043a8`
- `0x1800237f8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180023801`
- `KERNEL32!DeleteCriticalSection` at `0x180023801`

## pseudocode

```c
void __fastcall CMUtil::~CMUtil(struct _RTL_CRITICAL_SECTION *this)
{
  _QWORD *p_Type; // rcx

  DeleteCriticalSection(this);
  p_Type = &this[1].DebugInfo->Type;
  if ( p_Type )
  {
    std::_Deallocate<16>(p_Type, 8 * (((char *)this[1].OwningThread - (char *)p_Type) >> 3));
    this[1].DebugInfo = 0;
    *(_QWORD *)&this[1].LockCount = 0;
    this[1].OwningThread = 0;
  }
}

```

## disassembly

```asm
0x1800237f8  push    rbx
0x1800237fa  sub     rsp, 20h
0x1800237fe  mov     rbx, rcx
0x180023801  call    cs:__imp_DeleteCriticalSection
0x180023807  mov     rcx, [rbx+28h]
0x18002380b  test    rcx, rcx
0x18002380e  jz      short loc_18002384D
0x180023810  mov     rax, [rbx+38h]
0x180023814  mov     rdx, 0F0B7672A07A44C6Bh
0x18002381e  sub     rax, rcx
0x180023821  sar     rax, 3
0x180023825  imul    rax, rdx
0x180023829  imul    rdx, rax, 218h
0x180023830  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180023835  mov     qword ptr [rbx+28h], 0
0x18002383d  mov     qword ptr [rbx+30h], 0
0x180023845  mov     qword ptr [rbx+38h], 0
0x18002384d  add     rsp, 20h
0x180023851  pop     rbx
0x180023852  retn
```
