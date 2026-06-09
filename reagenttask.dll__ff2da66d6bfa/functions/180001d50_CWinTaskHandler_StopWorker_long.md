# CWinTaskHandler::StopWorker(long *)

- ea: `0x180001d50`
- end: `0x180001dcf`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `127`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180001d50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001d82`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001d82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d9e`

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
0x180001d50  mov     [rsp+arg_0], rbx
0x180001d55  mov     [rsp+arg_8], rsi
0x180001d5a  push    rdi
0x180001d5b  sub     rsp, 20h
0x180001d5f  xor     edi, edi
0x180001d61  mov     rsi, rcx
0x180001d64  cmp     [rcx+28h], rdi
0x180001d68  jnz     short loc_180001D71
0x180001d6a  mov     ebx, 80070057h
0x180001d6f  jmp     short loc_180001DB9
0x180001d71  mov     eax, 1
0x180001d76  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180001d79  xchg    eax, [rcx+24h]
0x180001d7c  mov     rcx, [rcx+28h]; hHandle
0x180001d80  mov     ebx, edi
0x180001d82  call    cs:__imp_WaitForSingleObject
0x180001d89  nop     dword ptr [rax+rax+00h]
0x180001d8e  test    eax, eax
0x180001d90  jz      short loc_180001DB9
0x180001d92  cmp     eax, 0FFFFFFFFh
0x180001d95  jz      short loc_180001D9E
0x180001d97  mov     ebx, 80004005h
0x180001d9c  jmp     short loc_180001DB9
0x180001d9e  call    cs:__imp_GetLastError
0x180001da5  nop     dword ptr [rax+rax+00h]
0x180001daa  mov     ebx, eax
0x180001dac  test    eax, eax
0x180001dae  jle     short loc_180001DB9
0x180001db0  movzx   ebx, ax
0x180001db3  or      ebx, 80070000h
0x180001db9  xchg    edi, [rsi+24h]
0x180001dbc  mov     rsi, [rsp+28h+arg_8]
0x180001dc1  mov     eax, ebx
0x180001dc3  mov     rbx, [rsp+28h+arg_0]
0x180001dc8  add     rsp, 20h
0x180001dcc  pop     rdi
0x180001dcd  retn
```
