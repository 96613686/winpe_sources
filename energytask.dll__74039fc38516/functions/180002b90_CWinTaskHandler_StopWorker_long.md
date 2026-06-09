# CWinTaskHandler::StopWorker(long *)

- ea: `0x180002b90`
- end: `0x180002bf9`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002b90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002bbc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002bbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bd2`

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
0x180002b90  mov     [rsp+arg_0], rbx
0x180002b95  push    rdi
0x180002b96  sub     rsp, 20h
0x180002b9a  cmp     qword ptr [rcx+28h], 0
0x180002b9f  mov     rdi, rcx
0x180002ba2  jnz     short loc_180002BAB
0x180002ba4  mov     ebx, 80070057h
0x180002ba9  jmp     short loc_180002BE7
0x180002bab  mov     eax, 1
0x180002bb0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002bb3  xchg    eax, [rcx+24h]
0x180002bb6  mov     rcx, [rcx+28h]; hHandle
0x180002bba  xor     ebx, ebx
0x180002bbc  call    cs:__imp_WaitForSingleObject
0x180002bc2  test    eax, eax
0x180002bc4  jz      short loc_180002BE7
0x180002bc6  cmp     eax, 0FFFFFFFFh
0x180002bc9  jz      short loc_180002BD2
0x180002bcb  mov     ebx, 80004005h
0x180002bd0  jmp     short loc_180002BE7
0x180002bd2  call    cs:__imp_GetLastError
0x180002bd8  mov     ebx, eax
0x180002bda  test    eax, eax
0x180002bdc  jle     short loc_180002BE7
0x180002bde  movzx   ebx, ax
0x180002be1  or      ebx, 80070000h
0x180002be7  xor     ecx, ecx
0x180002be9  mov     eax, ebx
0x180002beb  xchg    ecx, [rdi+24h]
0x180002bee  mov     rbx, [rsp+28h+arg_0]
0x180002bf3  add     rsp, 20h
0x180002bf7  pop     rdi
0x180002bf8  retn
```
