# PregenGetEvent(void * *)

- ea: `0x18001c268`
- end: `0x18001c2f0`
- name: `?PregenGetEvent@@YAJPEAPEAX@Z`
- size: `136`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001c508`

## callees

- `0x18000b0dc`
- `0x18001c268`
- `0x18001c984`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001c27f`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001c27f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c29c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c29c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2c5`

## string_xrefs

- `0x18001c2af`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001c2d4`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 __fastcall PregenGetEvent(void **a1)
{
  HANDLE v2; // rax
  HANDLE EventW; // rax
  const char *v4; // r9
  DWORD LastError; // eax
  unsigned int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = OpenEventW(0x100000u, 0, L"Global\\NgcKeyStaging");
  *a1 = v2;
  if ( !v2 )
  {
    EventW = CreateEventW(0, 1, 0, L"Global\\NgcKeyStaging");
    *a1 = EventW;
    if ( !EventW )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x211,
               (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
               v4);
    LastError = GetLastError();
    if ( LastError )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x215,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)LastError,
        v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18001c268  push    rbx; unsigned int
0x18001c26a  sub     rsp, 20h
0x18001c26e  mov     rbx, rcx
0x18001c271  lea     r8, Name; "Global\\NgcKeyStaging"
0x18001c278  mov     ecx, 100000h; dwDesiredAccess
0x18001c27d  xor     edx, edx; bInheritHandle
0x18001c27f  call    cs:__imp_OpenEventW
0x18001c285  mov     [rbx], rax
0x18001c288  test    rax, rax
0x18001c28b  jnz     short loc_18001C2E8
0x18001c28d  lea     r9, Name; "Global\\NgcKeyStaging"
0x18001c294  xor     r8d, r8d; bInitialState
0x18001c297  lea     edx, [rax+1]; bManualReset
0x18001c29a  xor     ecx, ecx; lpEventAttributes
0x18001c29c  call    cs:__imp_CreateEventW
0x18001c2a2  mov     [rbx], rax
0x18001c2a5  test    rax, rax
0x18001c2a8  jnz     short loc_18001C2C5
0x18001c2aa  mov     rcx, [rsp+28h]; this
0x18001c2af  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c2b6  mov     edx, 211h; void *
0x18001c2bb  add     rsp, 20h
0x18001c2bf  pop     rbx
0x18001c2c0  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c2c5  call    cs:__imp_GetLastError
0x18001c2cb  test    eax, eax
0x18001c2cd  jz      short loc_18001C2E8
0x18001c2cf  mov     rcx, [rsp+28h]; this
0x18001c2d4  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c2db  mov     r9d, eax; char *
0x18001c2de  mov     edx, 215h; void *
0x18001c2e3  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18001c2e8  xor     eax, eax
0x18001c2ea  add     rsp, 20h
0x18001c2ee  pop     rbx
0x18001c2ef  retn
```
