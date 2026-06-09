# AOMDHandler::UpdateStatsOnThresholdMet(void)

- ea: `0x180014a4c`
- end: `0x180014a8e`
- name: `?UpdateStatsOnThresholdMet@AOMDHandler@@AEAAJXZ`
- size: `66`
- prototype: `__int64 __fastcall(struct _FILETIME *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a6d4`

## callees

- `0x180014a4c`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180014a66`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180014a66`

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
0x180014a4c  push    rbx
0x180014a4e  sub     rsp, 20h
0x180014a52  mov     rbx, rcx
0x180014a55  inc     dword ptr [rcx+70h]
0x180014a58  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180014a61  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014a66  call    cs:__imp_GetSystemTimeAsFileTime
0x180014a6c  mov     edx, [rsp+28h+SystemTimeAsFileTime.dwHighDateTime]
0x180014a70  shl     rdx, 20h
0x180014a74  mov     eax, [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x180014a78  or      rdx, rax
0x180014a7b  mov     [rbx+68h], rdx
0x180014a7f  xor     eax, eax
0x180014a81  jmp     short loc_180014A87
0x180014a83  mov     eax, [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x180014a87  add     rsp, 20h
0x180014a8b  pop     rbx
0x180014a8c  retn
```
