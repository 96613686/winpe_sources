# _Thrd_join

- ea: `0x18031307c`
- end: `0x1803130e1`
- name: `_Thrd_join`
- size: `101`
- prototype: `int __cdecl(_Thrd_t *__struct_ptr, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18011667c`

## callees

- `0x18031307c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1803130c0`
- `KERNEL32!CloseHandle` at `0x1803130c0`
- `KERNEL32!WaitForSingleObjectEx` at `0x180313095`
- `KERNEL32!WaitForSingleObjectEx` at `0x180313095`
- `KERNEL32!GetExitCodeThread` at `0x1803130ad`
- `KERNEL32!GetExitCodeThread` at `0x1803130ad`

## pseudocode

```c
int __cdecl Thrd_join(_Thrd_t *a1, int *a2)
{
  void *Hnd; // rdi
  DWORD ExitCode; // [rsp+30h] [rbp+8h] BYREF

  Hnd = a1->_Hnd;
  if ( WaitForSingleObjectEx(a1->_Hnd, 0xFFFFFFFF, 0) != -1 )
  {
    if ( !a2 )
      return !CloseHandle(Hnd) ? 4 : 0;
    if ( GetExitCodeThread(Hnd, &ExitCode) )
    {
      *a2 = ExitCode;
      return !CloseHandle(Hnd) ? 4 : 0;
    }
  }
  return 4;
}

```

## disassembly

```asm
0x18031307c  mov     [rsp+arg_8], rbx
0x180313081  push    rdi
0x180313082  sub     rsp, 20h
0x180313086  mov     rdi, [rcx]
0x180313089  mov     rbx, rdx
0x18031308c  mov     rcx, rdi; hHandle
0x18031308f  xor     r8d, r8d; bAlertable
0x180313092  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180313095  call    cs:__imp_WaitForSingleObjectEx
0x18031309b  cmp     eax, 0FFFFFFFFh
0x18031309e  jz      short loc_1803130D1
0x1803130a0  test    rbx, rbx
0x1803130a3  jz      short loc_1803130BD
0x1803130a5  lea     rdx, [rsp+28h+ExitCode]; lpExitCode
0x1803130aa  mov     rcx, rdi; hThread
0x1803130ad  call    cs:__imp_GetExitCodeThread
0x1803130b3  test    eax, eax
0x1803130b5  jz      short loc_1803130D1
0x1803130b7  mov     eax, [rsp+28h+ExitCode]
0x1803130bb  mov     [rbx], eax
0x1803130bd  mov     rcx, rdi; hObject
0x1803130c0  call    cs:__imp_CloseHandle
0x1803130c6  neg     eax
0x1803130c8  sbb     eax, eax
0x1803130ca  not     eax
0x1803130cc  and     eax, 4
0x1803130cf  jmp     short loc_1803130D6
0x1803130d1  mov     eax, 4
0x1803130d6  mov     rbx, [rsp+28h+arg_8]
0x1803130db  add     rsp, 20h
0x1803130df  pop     rdi
0x1803130e0  retn
```
