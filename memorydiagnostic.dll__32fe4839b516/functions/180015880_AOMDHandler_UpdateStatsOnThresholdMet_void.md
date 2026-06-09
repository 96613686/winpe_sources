# AOMDHandler::UpdateStatsOnThresholdMet(void)

- ea: `0x180015880`
- end: `0x1800158c5`
- name: `?UpdateStatsOnThresholdMet@AOMDHandler@@AEAAJXZ`
- size: `69`
- prototype: `__int64 __fastcall(AOMDHandler *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a7e4`

## callees

- `0x180015880`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180015897`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180015897`

## pseudocode

```c
__int64 __fastcall AOMDHandler::UpdateStatsOnThresholdMet(struct _FILETIME *this)
{
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF

  ++this[14].dwLowDateTime;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  this[13] = SystemTimeAsFileTime;
  return 0;
}

```

## disassembly

```asm
0x180015880  push    rbx
0x180015882  sub     rsp, 20h
0x180015886  mov     rbx, rcx
0x180015889  inc     dword ptr [rcx+70h]
0x18001588c  and     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180015892  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180015897  call    cs:__imp_GetSystemTimeAsFileTime
0x18001589e  nop     dword ptr [rax+rax+00h]
0x1800158a3  mov     edx, [rsp+28h+SystemTimeAsFileTime.dwHighDateTime]
0x1800158a7  shl     rdx, 20h
0x1800158ab  mov     eax, [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x1800158af  or      rdx, rax
0x1800158b2  mov     [rbx+68h], rdx
0x1800158b6  xor     eax, eax
0x1800158b8  jmp     short loc_1800158BE
0x1800158ba  mov     eax, [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x1800158be  add     rsp, 20h
0x1800158c2  pop     rbx
0x1800158c3  retn
```
