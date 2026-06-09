# _dynamic_initializer_for__g_writeDumpEventSem__

- ea: `0x140001010`
- end: `0x140001052`
- name: `_dynamic_initializer_for__g_writeDumpEventSem__`
- size: `66`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001010`
- `0x140001a78`
- `0x140003094`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x140001020`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x140001020`

## string_xrefs

- `0x140001036`: `CreateEvent returned a NULL handle.`

## pseudocode

```c
int dynamic_initializer_for__g_writeDumpEventSem__()
{
  unsigned __int16 *v0; // rdx

  g_writeDumpEventSem = CreateEventA(0, 1, 0, 0);
  if ( !g_writeDumpEventSem )
    UtsemWin32Error(L"CreateEvent returned a NULL handle.", v0, 100);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_writeDumpEventSem__);
}

```

## disassembly

```asm
0x140001010  sub     rsp, 28h
0x140001014  xor     r9d, r9d; lpName
0x140001017  xor     r8d, r8d; bInitialState
0x14000101a  xor     ecx, ecx; lpEventAttributes
0x14000101c  lea     edx, [r9+1]; bManualReset
0x140001020  call    cs:__imp_CreateEventA
0x140001026  mov     cs:?g_writeDumpEventSem@@3VCEventSem@@A, rax; CEventSem g_writeDumpEventSem
0x14000102d  test    rax, rax
0x140001030  jnz     short loc_140001042
0x140001032  lea     r8d, [rax+64h]; unsigned int
0x140001036  lea     rcx, aCreateeventRet; "CreateEvent returned a NULL handle."
0x14000103d  call    ?UtsemWin32Error@@YAXPEAG0K@Z; UtsemWin32Error(ushort *,ushort *,ulong)
0x140001042  lea     rcx, _dynamic_atexit_destructor_for__g_writeDumpEventSem__
0x140001049  add     rsp, 28h
0x14000104d  jmp     atexit
```
