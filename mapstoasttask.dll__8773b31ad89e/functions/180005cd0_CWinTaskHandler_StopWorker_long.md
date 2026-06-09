# CWinTaskHandler::StopWorker(long *)

- ea: `0x180005cd0`
- end: `0x180005d39`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180005cd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d12`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005cfc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005cfc`

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
0x180005cd0  mov     [rsp+arg_0], rbx
0x180005cd5  push    rdi
0x180005cd6  sub     rsp, 20h
0x180005cda  cmp     qword ptr [rcx+28h], 0
0x180005cdf  mov     rdi, rcx
0x180005ce2  jnz     short loc_180005CEB
0x180005ce4  mov     ebx, 80070057h
0x180005ce9  jmp     short loc_180005D27
0x180005ceb  mov     eax, 1
0x180005cf0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005cf3  xchg    eax, [rcx+24h]
0x180005cf6  mov     rcx, [rcx+28h]; hHandle
0x180005cfa  xor     ebx, ebx
0x180005cfc  call    cs:__imp_WaitForSingleObject
0x180005d02  test    eax, eax
0x180005d04  jz      short loc_180005D27
0x180005d06  cmp     eax, 0FFFFFFFFh
0x180005d09  jz      short loc_180005D12
0x180005d0b  mov     ebx, 80004005h
0x180005d10  jmp     short loc_180005D27
0x180005d12  call    cs:__imp_GetLastError
0x180005d18  mov     ebx, eax
0x180005d1a  test    eax, eax
0x180005d1c  jle     short loc_180005D27
0x180005d1e  movzx   ebx, ax
0x180005d21  or      ebx, 80070000h
0x180005d27  xor     ecx, ecx
0x180005d29  mov     eax, ebx
0x180005d2b  xchg    ecx, [rdi+24h]
0x180005d2e  mov     rbx, [rsp+28h+arg_0]
0x180005d33  add     rsp, 20h
0x180005d37  pop     rdi
0x180005d38  retn
```
