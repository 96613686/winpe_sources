# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000be50`
- end: `0x18000beaa`
- name: `?QueryInterface@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800099d0`
- `0x18000aa18`
- `0x18000be50`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  const struct _GUID *v5; // rdx
  char **v6; // r8
  char *v7; // r9

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( (unsigned int)ATL::InlineIsEqualUnknown(a2) )
  {
    *v6 = v7;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
  }
  else
  {
    return (unsigned int)ATL::AtlInternalQueryInterface(
                           v7 + 16,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`Microsoft::Windows::Performance::CEventTraceRelogger::_GetEntries'::`2'::_entries,
                           v5,
                           v6);
  }
  return v3;
}

```

## disassembly

```asm
0x18000be50  push    rbx
0x18000be52  sub     rsp, 20h
0x18000be56  xor     ebx, ebx
0x18000be58  mov     r9, rcx
0x18000be5b  test    r8, r8
0x18000be5e  jnz     short loc_18000BE67
0x18000be60  mov     eax, 80004003h
0x18000be65  jmp     short loc_18000BEA4
0x18000be67  mov     rcx, rdx; struct _GUID *
0x18000be6a  mov     [r8], rbx
0x18000be6d  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x18000be72  test    eax, eax
0x18000be74  jz      short loc_18000BE8A
0x18000be76  mov     [r8], r9
0x18000be79  mov     rcx, r9
0x18000be7c  mov     rax, [r9]
0x18000be7f  mov     rax, [rax+8]
0x18000be83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be88  jmp     short loc_18000BEA2
0x18000be8a  lea     rcx, [r9+10h]; void *
0x18000be8e  mov     r9, r8; void **
0x18000be91  mov     r8, rdx; struct _GUID *
0x18000be94  lea     rdx, ?_entries@?1??_GetEntries@CEventTraceRelogger@Performance@Windows@Microsoft@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU67@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000be9b  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000bea0  mov     ebx, eax
0x18000bea2  mov     eax, ebx
0x18000bea4  add     rsp, 20h
0x18000bea8  pop     rbx
0x18000bea9  retn
```
