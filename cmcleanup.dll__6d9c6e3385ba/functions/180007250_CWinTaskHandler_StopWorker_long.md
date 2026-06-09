# CWinTaskHandler::StopWorker(long *)

- ea: `0x180007250`
- end: `0x1800072b9`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180007250`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000727c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000727c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007292`

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
0x180007250  mov     [rsp+arg_0], rbx
0x180007255  push    rdi
0x180007256  sub     rsp, 20h
0x18000725a  cmp     qword ptr [rcx+28h], 0
0x18000725f  mov     rdi, rcx
0x180007262  jnz     short loc_18000726B
0x180007264  mov     ebx, 80070057h
0x180007269  jmp     short loc_1800072A7
0x18000726b  mov     eax, 1
0x180007270  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007273  xchg    eax, [rcx+24h]
0x180007276  mov     rcx, [rcx+28h]; hHandle
0x18000727a  xor     ebx, ebx
0x18000727c  call    cs:__imp_WaitForSingleObject
0x180007282  test    eax, eax
0x180007284  jz      short loc_1800072A7
0x180007286  cmp     eax, 0FFFFFFFFh
0x180007289  jz      short loc_180007292
0x18000728b  mov     ebx, 80004005h
0x180007290  jmp     short loc_1800072A7
0x180007292  call    cs:__imp_GetLastError
0x180007298  mov     ebx, eax
0x18000729a  test    eax, eax
0x18000729c  jle     short loc_1800072A7
0x18000729e  movzx   ebx, ax
0x1800072a1  or      ebx, 80070000h
0x1800072a7  xor     ecx, ecx
0x1800072a9  mov     eax, ebx
0x1800072ab  xchg    ecx, [rdi+24h]
0x1800072ae  mov     rbx, [rsp+28h+arg_0]
0x1800072b3  add     rsp, 20h
0x1800072b7  pop     rdi
0x1800072b8  retn
```
