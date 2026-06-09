# CCtfmonHelper::_SetSessionEvent(ushort const *)

- ea: `0x1800bd464`
- end: `0x1800bd4f2`
- name: `?_SetSessionEvent@CCtfmonHelper@@CA_NPEBG@Z`
- size: `142`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800bd0b0`

## callees

- `0x1800bd464`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800bd484`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800bd498`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800bd484`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800bd498`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800bd4ae`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800bd4bb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800bd4ae`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800bd4bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd4cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd4d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd4cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd4d9`

## pseudocode

```c
bool __fastcall CCtfmonHelper::_SetSessionEvent(const unsigned __int16 *a1)
{
  bool v1; // di
  HANDLE v2; // rsi
  HANDLE v3; // rax
  void *v4; // rbx

  v1 = 0;
  v2 = OpenEventW(2u, 0, L"Global\\{DFFDE213-8CB4-46a9-90EB-3DA843AF66F9}-server");
  v3 = OpenEventW(2u, 0, L"{958DA730-EDB5-43CE-8A56-776CCC5AB7E1}-request");
  v4 = v3;
  if ( v2 )
  {
    if ( v3 && SetEvent(v3) )
      v1 = SetEvent(v2);
    CloseHandle(v2);
  }
  if ( v4 )
    CloseHandle(v4);
  return v1;
}

```

## disassembly

```asm
0x1800bd464  mov     [rsp+arg_0], rbx
0x1800bd469  mov     [rsp+arg_8], rsi
0x1800bd46e  push    rdi
0x1800bd46f  sub     rsp, 20h
0x1800bd473  xor     edx, edx; bInheritHandle
0x1800bd475  lea     r8, aGlobalDffde213; "Global\\{DFFDE213-8CB4-46a9-90EB-3DA843"...
0x1800bd47c  xor     dil, dil
0x1800bd47f  lea     ebx, [rdx+2]
0x1800bd482  mov     ecx, ebx; dwDesiredAccess
0x1800bd484  call    cs:__imp_OpenEventW
0x1800bd48a  lea     r8, a958da730Edb543; "{958DA730-EDB5-43CE-8A56-776CCC5AB7E1}-"...
0x1800bd491  xor     edx, edx; bInheritHandle
0x1800bd493  mov     ecx, ebx; dwDesiredAccess
0x1800bd495  mov     rsi, rax
0x1800bd498  call    cs:__imp_OpenEventW
0x1800bd49e  mov     rbx, rax
0x1800bd4a1  test    rsi, rsi
0x1800bd4a4  jz      short loc_1800BD4D1
0x1800bd4a6  test    rax, rax
0x1800bd4a9  jz      short loc_1800BD4C8
0x1800bd4ab  mov     rcx, rax; hEvent
0x1800bd4ae  call    cs:__imp_SetEvent
0x1800bd4b4  test    eax, eax
0x1800bd4b6  jz      short loc_1800BD4C8
0x1800bd4b8  mov     rcx, rsi; hEvent
0x1800bd4bb  call    cs:__imp_SetEvent
0x1800bd4c1  test    eax, eax
0x1800bd4c3  jz      short loc_1800BD4C8
0x1800bd4c5  mov     dil, 1
0x1800bd4c8  mov     rcx, rsi; hObject
0x1800bd4cb  call    cs:__imp_CloseHandle
0x1800bd4d1  test    rbx, rbx
0x1800bd4d4  jz      short loc_1800BD4DF
0x1800bd4d6  mov     rcx, rbx; hObject
0x1800bd4d9  call    cs:__imp_CloseHandle
0x1800bd4df  mov     rbx, [rsp+28h+arg_0]
0x1800bd4e4  mov     al, dil
0x1800bd4e7  mov     rsi, [rsp+28h+arg_8]
0x1800bd4ec  add     rsp, 20h
0x1800bd4f0  pop     rdi
0x1800bd4f1  retn
```
