# ATL::CComAggObject<CTaskHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004040`
- end: `0x1800040a3`
- name: `?QueryInterface@?$CComAggObject@VCTaskHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, __int64, char **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800039f4`
- `0x180004040`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CTaskHandler>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 24,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CTaskHandler::_GetEntries'::`2'::_entries,
                           (const struct _GUID *)a2,
                           a3);
  }
  else
  {
    *a3 = a1;
    (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x180004040  push    rbx
0x180004042  sub     rsp, 20h
0x180004046  xor     ebx, ebx
0x180004048  test    r8, r8
0x18000404b  jnz     short loc_180004054
0x18000404d  mov     eax, 80004003h
0x180004052  jmp     short loc_18000409D
0x180004054  mov     [r8], rbx
0x180004057  cmp     [rdx], ebx
0x180004059  jnz     short loc_180004083
0x18000405b  cmp     [rdx+4], ebx
0x18000405e  jnz     short loc_180004083
0x180004060  cmp     dword ptr [rdx+8], 0C0h
0x180004067  jnz     short loc_180004083
0x180004069  cmp     dword ptr [rdx+0Ch], 46000000h
0x180004070  jnz     short loc_180004083
0x180004072  mov     [r8], rcx
0x180004075  mov     rax, [rcx]
0x180004078  mov     rax, [rax+8]
0x18000407c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004081  jmp     short loc_18000409B
0x180004083  mov     r9, r8; void **
0x180004086  add     rcx, 18h; void *
0x18000408a  mov     r8, rdx; struct _GUID *
0x18000408d  lea     rdx, ?_entries@?1??_GetEntries@CTaskHandler@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004094  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180004099  mov     ebx, eax
0x18000409b  mov     eax, ebx
0x18000409d  add     rsp, 20h
0x1800040a1  pop     rbx
0x1800040a2  retn
```
