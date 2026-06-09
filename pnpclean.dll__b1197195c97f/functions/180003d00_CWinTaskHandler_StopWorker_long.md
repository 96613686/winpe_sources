# CWinTaskHandler::StopWorker(long *)

- ea: `0x180003d00`
- end: `0x180003d69`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180003d00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003d42`
- `KERNEL32!GetLastError` at `0x180003d42`
- `KERNEL32!WaitForSingleObject` at `0x180003d2c`
- `KERNEL32!WaitForSingleObject` at `0x180003d2c`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::StopWorker(CWinTaskHandler *this, int *a2)
{
  unsigned int v3; // ebx
  DWORD v4; // eax
  signed int LastError; // eax
  __int64 result; // rax

  if ( *((_QWORD *)this + 5) )
  {
    _InterlockedExchange((volatile __int32 *)this + 9, 1);
    v3 = 0;
    v4 = WaitForSingleObject(*((HANDLE *)this + 5), 0xFFFFFFFF);
    if ( v4 )
    {
      if ( v4 == -1 )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v3 = -2147467259;
      }
    }
  }
  else
  {
    v3 = -2147024809;
  }
  result = v3;
  _InterlockedExchange((volatile __int32 *)this + 9, 0);
  return result;
}

```

## disassembly

```asm
0x180003d00  mov     [rsp+arg_0], rbx
0x180003d05  push    rdi
0x180003d06  sub     rsp, 20h
0x180003d0a  cmp     qword ptr [rcx+28h], 0
0x180003d0f  mov     rdi, rcx
0x180003d12  jnz     short loc_180003D1B
0x180003d14  mov     ebx, 80070057h
0x180003d19  jmp     short loc_180003D57
0x180003d1b  mov     eax, 1
0x180003d20  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003d23  xchg    eax, [rcx+24h]
0x180003d26  mov     rcx, [rcx+28h]; hHandle
0x180003d2a  xor     ebx, ebx
0x180003d2c  call    cs:__imp_WaitForSingleObject
0x180003d32  test    eax, eax
0x180003d34  jz      short loc_180003D57
0x180003d36  cmp     eax, 0FFFFFFFFh
0x180003d39  jz      short loc_180003D42
0x180003d3b  mov     ebx, 80004005h
0x180003d40  jmp     short loc_180003D57
0x180003d42  call    cs:__imp_GetLastError
0x180003d48  mov     ebx, eax
0x180003d4a  test    eax, eax
0x180003d4c  jle     short loc_180003D57
0x180003d4e  movzx   ebx, ax
0x180003d51  or      ebx, 80070000h
0x180003d57  xor     ecx, ecx
0x180003d59  mov     eax, ebx
0x180003d5b  xchg    ecx, [rdi+24h]
0x180003d5e  mov     rbx, [rsp+28h+arg_0]
0x180003d63  add     rsp, 20h
0x180003d67  pop     rdi
0x180003d68  retn
```
