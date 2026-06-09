# CWinTaskHandler::StopWorker(long *)

- ea: `0x18000c2e0`
- end: `0x18000c349`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000c2e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c322`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c30c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c30c`

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
0x18000c2e0  mov     [rsp+arg_0], rbx
0x18000c2e5  push    rdi
0x18000c2e6  sub     rsp, 20h
0x18000c2ea  cmp     qword ptr [rcx+28h], 0
0x18000c2ef  mov     rdi, rcx
0x18000c2f2  jnz     short loc_18000C2FB
0x18000c2f4  mov     ebx, 80070057h
0x18000c2f9  jmp     short loc_18000C337
0x18000c2fb  mov     eax, 1
0x18000c300  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000c303  xchg    eax, [rcx+24h]
0x18000c306  mov     rcx, [rcx+28h]; hHandle
0x18000c30a  xor     ebx, ebx
0x18000c30c  call    cs:__imp_WaitForSingleObject
0x18000c312  test    eax, eax
0x18000c314  jz      short loc_18000C337
0x18000c316  cmp     eax, 0FFFFFFFFh
0x18000c319  jz      short loc_18000C322
0x18000c31b  mov     ebx, 80004005h
0x18000c320  jmp     short loc_18000C337
0x18000c322  call    cs:__imp_GetLastError
0x18000c328  mov     ebx, eax
0x18000c32a  test    eax, eax
0x18000c32c  jle     short loc_18000C337
0x18000c32e  movzx   ebx, ax
0x18000c331  or      ebx, 80070000h
0x18000c337  xor     ecx, ecx
0x18000c339  mov     eax, ebx
0x18000c33b  xchg    ecx, [rdi+24h]
0x18000c33e  mov     rbx, [rsp+28h+arg_0]
0x18000c343  add     rsp, 20h
0x18000c347  pop     rdi
0x18000c348  retn
```
