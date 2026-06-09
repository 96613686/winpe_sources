# CWinTaskHandler::StopWorker(long *)

- ea: `0x1800020c0`
- end: `0x180002129`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800020c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002102`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800020ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800020ec`

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
0x1800020c0  mov     [rsp+arg_0], rbx
0x1800020c5  push    rdi
0x1800020c6  sub     rsp, 20h
0x1800020ca  cmp     qword ptr [rcx+28h], 0
0x1800020cf  mov     rdi, rcx
0x1800020d2  jnz     short loc_1800020DB
0x1800020d4  mov     ebx, 80070057h
0x1800020d9  jmp     short loc_180002117
0x1800020db  mov     eax, 1
0x1800020e0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800020e3  xchg    eax, [rcx+24h]
0x1800020e6  mov     rcx, [rcx+28h]; hHandle
0x1800020ea  xor     ebx, ebx
0x1800020ec  call    cs:__imp_WaitForSingleObject
0x1800020f2  test    eax, eax
0x1800020f4  jz      short loc_180002117
0x1800020f6  cmp     eax, 0FFFFFFFFh
0x1800020f9  jz      short loc_180002102
0x1800020fb  mov     ebx, 80004005h
0x180002100  jmp     short loc_180002117
0x180002102  call    cs:__imp_GetLastError
0x180002108  mov     ebx, eax
0x18000210a  test    eax, eax
0x18000210c  jle     short loc_180002117
0x18000210e  movzx   ebx, ax
0x180002111  or      ebx, 80070000h
0x180002117  xor     ecx, ecx
0x180002119  mov     eax, ebx
0x18000211b  xchg    ecx, [rdi+24h]
0x18000211e  mov     rbx, [rsp+28h+arg_0]
0x180002123  add     rsp, 20h
0x180002127  pop     rdi
0x180002128  retn
```
