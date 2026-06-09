# CATUtils::IsProcessInATJob(void *)

- ea: `0x14001c82c`
- end: `0x14001c8a0`
- name: `?IsProcessInATJob@CATUtils@@SAHPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001b674`
- `0x140020938`

## callees

- `0x14001c82c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001c87b`
- `KERNEL32!CloseHandle` at `0x14001c87b`
- `KERNEL32!IsProcessInJob` at `0x14001c870`
- `KERNEL32!IsProcessInJob` at `0x14001c870`
- `KERNEL32!OpenJobObjectW` at `0x14001c851`
- `KERNEL32!OpenJobObjectW` at `0x14001c851`
- `KERNEL32!GetCurrentProcess` at `0x14001c85f`
- `KERNEL32!GetCurrentProcess` at `0x14001c85f`

## string_xrefs

- `0x14001c845`: `WinlogonAccess`

## pseudocode

```c
_BOOL8 __fastcall CATUtils::IsProcessInATJob(void *a1)
{
  BOOL v1; // ebx
  HANDLE v2; // rdi
  HANDLE CurrentProcess; // rax
  WINBOOL Result; // [rsp+30h] [rbp+8h] BYREF
  int v6; // [rsp+34h] [rbp+Ch]

  v6 = HIDWORD(a1);
  v1 = 0;
  Result = 0;
  v2 = OpenJobObjectW(4u, 0, L"WinlogonAccess");
  if ( v2 )
  {
    CurrentProcess = GetCurrentProcess();
    v1 = IsProcessInJob(CurrentProcess, v2, &Result);
    CloseHandle(v2);
  }
  return Result && v1;
}

```

## disassembly

```asm
0x14001c82c  mov     [rsp+arg_8], rbx
0x14001c831  mov     qword ptr [rsp+Result], rcx
0x14001c836  push    rdi
0x14001c837  sub     rsp, 20h
0x14001c83b  xor     ebx, ebx
0x14001c83d  mov     [rsp+28h+Result], 0
0x14001c845  lea     r8, aWinlogonaccess; "WinlogonAccess"
0x14001c84c  xor     edx, edx; bInheritHandle
0x14001c84e  lea     ecx, [rbx+4]; dwDesiredAccess
0x14001c851  call    cs:__imp_OpenJobObjectW
0x14001c857  mov     rdi, rax
0x14001c85a  test    rax, rax
0x14001c85d  jz      short loc_14001C881
0x14001c85f  call    cs:__imp_GetCurrentProcess
0x14001c865  lea     r8, [rsp+28h+Result]; Result
0x14001c86a  mov     rdx, rdi; JobHandle
0x14001c86d  mov     rcx, rax; ProcessHandle
0x14001c870  call    cs:__imp_IsProcessInJob
0x14001c876  mov     rcx, rdi; hObject
0x14001c879  mov     ebx, eax
0x14001c87b  call    cs:__imp_CloseHandle
0x14001c881  cmp     [rsp+28h+Result], 0
0x14001c886  jz      short loc_14001C893
0x14001c888  test    ebx, ebx
0x14001c88a  jz      short loc_14001C893
0x14001c88c  mov     eax, 1
0x14001c891  jmp     short loc_14001C895
0x14001c893  xor     eax, eax
0x14001c895  mov     rbx, [rsp+28h+arg_8]
0x14001c89a  add     rsp, 20h
0x14001c89e  pop     rdi
0x14001c89f  retn
```
