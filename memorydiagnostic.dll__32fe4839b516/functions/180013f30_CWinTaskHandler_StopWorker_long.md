# CWinTaskHandler::StopWorker(long *)

- ea: `0x180013f30`
- end: `0x180013faf`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `127`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180013f30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180013f7e`
- `KERNEL32!GetLastError` at `0x180013f7e`
- `KERNEL32!WaitForSingleObject` at `0x180013f62`
- `KERNEL32!WaitForSingleObject` at `0x180013f62`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::StopWorker(CWinTaskHandler *this, int *a2)
{
  unsigned int v3; // ebx
  DWORD v4; // eax
  signed int LastError; // eax

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
  _InterlockedExchange((volatile __int32 *)this + 9, 0);
  return v3;
}

```

## disassembly

```asm
0x180013f30  mov     [rsp+arg_0], rbx
0x180013f35  mov     [rsp+arg_8], rsi
0x180013f3a  push    rdi
0x180013f3b  sub     rsp, 20h
0x180013f3f  xor     edi, edi
0x180013f41  mov     rsi, rcx
0x180013f44  cmp     [rcx+28h], rdi
0x180013f48  jnz     short loc_180013F51
0x180013f4a  mov     ebx, 80070057h
0x180013f4f  jmp     short loc_180013F99
0x180013f51  mov     eax, 1
0x180013f56  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180013f59  xchg    eax, [rcx+24h]
0x180013f5c  mov     rcx, [rcx+28h]; hHandle
0x180013f60  mov     ebx, edi
0x180013f62  call    cs:__imp_WaitForSingleObject
0x180013f69  nop     dword ptr [rax+rax+00h]
0x180013f6e  test    eax, eax
0x180013f70  jz      short loc_180013F99
0x180013f72  cmp     eax, 0FFFFFFFFh
0x180013f75  jz      short loc_180013F7E
0x180013f77  mov     ebx, 80004005h
0x180013f7c  jmp     short loc_180013F99
0x180013f7e  call    cs:__imp_GetLastError
0x180013f85  nop     dword ptr [rax+rax+00h]
0x180013f8a  mov     ebx, eax
0x180013f8c  test    eax, eax
0x180013f8e  jle     short loc_180013F99
0x180013f90  movzx   ebx, ax
0x180013f93  or      ebx, 80070000h
0x180013f99  xchg    edi, [rsi+24h]
0x180013f9c  mov     rsi, [rsp+28h+arg_8]
0x180013fa1  mov     eax, ebx
0x180013fa3  mov     rbx, [rsp+28h+arg_0]
0x180013fa8  add     rsp, 20h
0x180013fac  pop     rdi
0x180013fad  retn
```
