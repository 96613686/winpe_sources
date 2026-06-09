# PpfUnlock

- ea: `0x18001c0a0`
- end: `0x18001c109`
- name: `PpfUnlock`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f5b4`
- `0x180013ef4`
- `0x1800141f4`
- `0x180015ff8`
- `0x180016498`
- `0x18001b140`
- `0x18001b930`
- `0x180052728`
- `0x180053280`

## callees

- `0x18001af5c`
- `0x18001c0a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c0ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c0ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c0d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c0d5`

## string_xrefs

- `0x18001c0c1`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18001c0ea`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`

## pseudocode

```c
void __fastcall PpfUnlock(HANDLE *a1)
{
  const char *v2; // r9
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !ReleaseMutex(*a1) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x59E,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      v2);
  if ( !CloseHandle(*a1) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x59F,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      v3);
  *a1 = 0;
}

```

## disassembly

```asm
0x18001c0a0  push    rbx
0x18001c0a2  sub     rsp, 20h
0x18001c0a6  mov     rbx, rcx
0x18001c0a9  mov     rcx, [rcx]; hMutex
0x18001c0ac  call    cs:__imp_ReleaseMutex
0x18001c0b3  nop     dword ptr [rax+rax+00h]
0x18001c0b8  test    eax, eax
0x18001c0ba  jnz     short loc_18001C0D2
0x18001c0bc  mov     rcx, [rsp+28h]; this
0x18001c0c1  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001c0c8  mov     edx, 59Eh; void *
0x18001c0cd  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18001c0d2  mov     rcx, [rbx]; hObject
0x18001c0d5  call    cs:__imp_CloseHandle
0x18001c0dc  nop     dword ptr [rax+rax+00h]
0x18001c0e1  test    eax, eax
0x18001c0e3  jnz     short loc_18001C0FB
0x18001c0e5  mov     rcx, [rsp+28h]; this
0x18001c0ea  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001c0f1  mov     edx, 59Fh; void *
0x18001c0f6  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18001c0fb  mov     qword ptr [rbx], 0
0x18001c102  add     rsp, 20h
0x18001c106  pop     rbx
0x18001c107  retn
```
