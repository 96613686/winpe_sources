# UnreachableServerCache_DllInitialize

- ea: `0x1800512fc`
- end: `0x18005134d`
- name: `UnreachableServerCache_DllInitialize`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180050ed0`

## callees

- `0x1800512fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051339`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051323`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051323`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180051307`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180051307`

## pseudocode

```c
DWORD UnreachableServerCache_DllInitialize()
{
  DWORD result; // eax

  InitializeCriticalSection(&stru_1800ABD68);
  dword_1800ABD9C = 0;
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( !hHandle )
    return GetLastError();
  result = 0;
  dword_1800ABD98 = 0;
  return result;
}

```

## disassembly

```asm
0x1800512fc  sub     rsp, 28h
0x180051300  lea     rcx, stru_1800ABD68; lpCriticalSection
0x180051307  call    cs:__imp_InitializeCriticalSection
0x18005130d  xor     r9d, r9d; lpName
0x180051310  mov     cs:dword_1800ABD9C, 0
0x18005131a  xor     r8d, r8d; bInitialState
0x18005131d  xor     ecx, ecx; lpEventAttributes
0x18005131f  lea     edx, [r9+1]; bManualReset
0x180051323  call    cs:__imp_CreateEventW
0x180051329  mov     cs:hHandle, rax
0x180051330  test    rax, rax
0x180051333  jnz     short loc_180051340
0x180051335  add     rsp, 28h
0x180051339  jmp     cs:__imp_GetLastError
0x180051340  xor     eax, eax
0x180051342  mov     cs:dword_1800ABD98, eax
0x180051348  add     rsp, 28h
0x18005134c  retn
```
