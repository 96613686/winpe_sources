# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180008430`
- end: `0x180008452`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `31`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007b44`
- `0x18001073c`
- `0x180010af0`
- `0x18001b860`
- `0x18001b9c0`
- `0x180021660`
- `0x1800222b8`
- `0x18002260c`
- `0x180022a48`
- `0x180022ba0`
- `0x180022ff8`
- `0x1800230c0`
- `0x180023250`
- `0x180023400`
- `0x1800234b0`
- `0x180023610`
- `0x1800236a0`
- `0x180023730`
- `0x180024220`
- `0x180024548`
- `0x180024784`
- `0x180024ac0`
- `0x180024ba0`
- `0x180030888`
- `0x1800336e0`
- `0x180033730`
- `0x180033790`
- `0x1800339f5`
- `0x180033a30`
- `0x180034439`
- `0x1800344cb`

## callees

- `0x180008430`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008442`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008442`

## pseudocode

```c
void __fastcall ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
  {
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)a1);
    *(_BYTE *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180008430  push    rbx
0x180008432  sub     rsp, 20h
0x180008436  cmp     byte ptr [rcx+8], 0
0x18000843a  mov     rbx, rcx
0x18000843d  jz      short loc_18000844C
0x18000843f  mov     rcx, [rcx]; lpCriticalSection
0x180008442  call    cs:__imp_LeaveCriticalSection
0x180008448  mov     byte ptr [rbx+8], 0
0x18000844c  add     rsp, 20h
0x180008450  pop     rbx
0x180008451  retn
```
