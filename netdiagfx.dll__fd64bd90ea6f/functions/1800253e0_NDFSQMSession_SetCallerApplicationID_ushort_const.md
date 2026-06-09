# NDFSQMSession::SetCallerApplicationID(ushort const *)

- ea: `0x1800253e0`
- end: `0x18002540c`
- name: `?SetCallerApplicationID@NDFSQMSession@@UEAAJPEBG@Z`
- size: `44`
- prototype: `int(NDFSQMSession *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `ntdll!WinSqmSetString` at `0x1800253fe`
- `ntdll!WinSqmSetString` at `0x1800253fe`
- `SHLWAPI!PathFindFileNameW` at `0x1800253ec`
- `SHLWAPI!PathFindFileNameW` at `0x1800253ec`

## pseudocode

```c
__int64 __fastcall NDFSQMSession::SetCallerApplicationID(NDFSQMSession *this, const unsigned __int16 *a2)
{
  LPWSTR FileNameW; // rax

  FileNameW = PathFindFileNameW(a2);
  WinSqmSetString(*((_QWORD *)this + 1), 7120, FileNameW);
  return 0;
}

```

## disassembly

```asm
0x1800253e0  push    rbx
0x1800253e2  sub     rsp, 20h
0x1800253e6  mov     rbx, rcx
0x1800253e9  mov     rcx, rdx; pszPath
0x1800253ec  call    cs:__imp_PathFindFileNameW
0x1800253f2  mov     rcx, [rbx+8]
0x1800253f6  mov     edx, 1BD0h
0x1800253fb  mov     r8, rax
0x1800253fe  call    cs:__imp_WinSqmSetString
0x180025404  xor     eax, eax
0x180025406  add     rsp, 20h
0x18002540a  pop     rbx
0x18002540b  retn
```
