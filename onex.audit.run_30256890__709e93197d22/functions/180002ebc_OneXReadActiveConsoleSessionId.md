# OneXReadActiveConsoleSessionId

- ea: `0x180002ebc`
- end: `0x180002f5e`
- name: `OneXReadActiveConsoleSessionId`
- size: `162`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010b0`
- `0x180002470`
- `0x180002a30`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180002ee5`
- `MobileNetworking!ReleaseWriteLock` at `0x180002f2d`
- `MobileNetworking!ReleaseWriteLock` at `0x180002ee5`
- `MobileNetworking!ReleaseWriteLock` at `0x180002f2d`
- `MobileNetworking!AcquireWriteLock` at `0x180002f06`
- `MobileNetworking!AcquireWriteLock` at `0x180002f46`
- `MobileNetworking!AcquireWriteLock` at `0x180002f06`
- `MobileNetworking!AcquireWriteLock` at `0x180002f46`

## string_xrefs

- `0x180002edb`: `OneXReadActiveConsoleSessionId`
- `0x180002ef1`: `OneXReadActiveConsoleSessionId`
- `0x180002f12`: `OneXReadActiveConsoleSessionId`
- `0x180002f39`: `OneXReadActiveConsoleSessionId`

## pseudocode

```c
__int64 __fastcall OneXReadActiveConsoleSessionId(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int v3; // ebx

  v1 = a1 + 2896;
  ReleaseWriteLock(a1, a1 + 2896, "OneXReadActiveConsoleSessionId", 184);
  AcquireWriteLock(g_OneXInfo, qword_18003DD98, "OneXReadActiveConsoleSessionId", 186);
  v3 = dword_18003DE0C;
  ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "OneXReadActiveConsoleSessionId", 188);
  AcquireWriteLock(a1, v1, "OneXReadActiveConsoleSessionId", 190);
  return v3;
}

```

## disassembly

```asm
0x180002ebc  mov     [rsp+arg_0], rbx
0x180002ec1  mov     [rsp+arg_8], rsi
0x180002ec6  push    rdi
0x180002ec7  sub     rsp, 20h
0x180002ecb  lea     rdi, [rcx+0B50h]
0x180002ed2  mov     r9d, 0B8h
0x180002ed8  mov     rdx, rdi
0x180002edb  lea     r8, aOnexreadactive; "OneXReadActiveConsoleSessionId"
0x180002ee2  mov     rsi, rcx
0x180002ee5  call    cs:__imp_ReleaseWriteLock
0x180002eeb  mov     r9d, 0BAh
0x180002ef1  lea     r8, aOnexreadactive; "OneXReadActiveConsoleSessionId"
0x180002ef8  lea     rdx, qword_18003DD98
0x180002eff  lea     rcx, g_OneXInfo
0x180002f06  call    cs:__imp_AcquireWriteLock
0x180002f0c  mov     ebx, cs:dword_18003DE0C
0x180002f12  lea     r8, aOnexreadactive; "OneXReadActiveConsoleSessionId"
0x180002f19  mov     r9d, 0BCh
0x180002f1f  lea     rdx, qword_18003DD98
0x180002f26  lea     rcx, g_OneXInfo
0x180002f2d  call    cs:__imp_ReleaseWriteLock
0x180002f33  mov     r9d, 0BEh
0x180002f39  lea     r8, aOnexreadactive; "OneXReadActiveConsoleSessionId"
0x180002f40  mov     rdx, rdi
0x180002f43  mov     rcx, rsi
0x180002f46  call    cs:__imp_AcquireWriteLock
0x180002f4c  mov     rsi, [rsp+28h+arg_8]
0x180002f51  mov     eax, ebx
0x180002f53  mov     rbx, [rsp+28h+arg_0]
0x180002f58  add     rsp, 20h
0x180002f5c  pop     rdi
0x180002f5d  retn
```
