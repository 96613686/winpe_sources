# CWinTaskHandler::StopWorker(long *)

- ea: `0x180006a20`
- end: `0x180006a89`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180006a20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006a4c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a62`

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
0x180006a20  mov     [rsp+arg_0], rbx
0x180006a25  push    rdi
0x180006a26  sub     rsp, 20h
0x180006a2a  cmp     qword ptr [rcx+28h], 0
0x180006a2f  mov     rdi, rcx
0x180006a32  jnz     short loc_180006A3B
0x180006a34  mov     ebx, 80070057h
0x180006a39  jmp     short loc_180006A77
0x180006a3b  mov     eax, 1
0x180006a40  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006a43  xchg    eax, [rcx+24h]
0x180006a46  mov     rcx, [rcx+28h]; hHandle
0x180006a4a  xor     ebx, ebx
0x180006a4c  call    cs:__imp_WaitForSingleObject
0x180006a52  test    eax, eax
0x180006a54  jz      short loc_180006A77
0x180006a56  cmp     eax, 0FFFFFFFFh
0x180006a59  jz      short loc_180006A62
0x180006a5b  mov     ebx, 80004005h
0x180006a60  jmp     short loc_180006A77
0x180006a62  call    cs:__imp_GetLastError
0x180006a68  mov     ebx, eax
0x180006a6a  test    eax, eax
0x180006a6c  jle     short loc_180006A77
0x180006a6e  movzx   ebx, ax
0x180006a71  or      ebx, 80070000h
0x180006a77  xor     ecx, ecx
0x180006a79  mov     eax, ebx
0x180006a7b  xchg    ecx, [rdi+24h]
0x180006a7e  mov     rbx, [rsp+28h+arg_0]
0x180006a83  add     rsp, 20h
0x180006a87  pop     rdi
0x180006a88  retn
```
