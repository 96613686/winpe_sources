# CWinTaskHandler::StopWorker(long *)

- ea: `0x180002640`
- end: `0x1800026a9`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000266c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000266c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002682`

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
0x180002640  mov     [rsp+arg_0], rbx
0x180002645  push    rdi
0x180002646  sub     rsp, 20h
0x18000264a  cmp     qword ptr [rcx+28h], 0
0x18000264f  mov     rdi, rcx
0x180002652  jnz     short loc_18000265B
0x180002654  mov     ebx, 80070057h
0x180002659  jmp     short loc_180002697
0x18000265b  mov     eax, 1
0x180002660  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002663  xchg    eax, [rcx+24h]
0x180002666  mov     rcx, [rcx+28h]; hHandle
0x18000266a  xor     ebx, ebx
0x18000266c  call    cs:__imp_WaitForSingleObject
0x180002672  test    eax, eax
0x180002674  jz      short loc_180002697
0x180002676  cmp     eax, 0FFFFFFFFh
0x180002679  jz      short loc_180002682
0x18000267b  mov     ebx, 80004005h
0x180002680  jmp     short loc_180002697
0x180002682  call    cs:__imp_GetLastError
0x180002688  mov     ebx, eax
0x18000268a  test    eax, eax
0x18000268c  jle     short loc_180002697
0x18000268e  movzx   ebx, ax
0x180002691  or      ebx, 80070000h
0x180002697  xor     ecx, ecx
0x180002699  mov     eax, ebx
0x18000269b  xchg    ecx, [rdi+24h]
0x18000269e  mov     rbx, [rsp+28h+arg_0]
0x1800026a3  add     rsp, 20h
0x1800026a7  pop     rdi
0x1800026a8  retn
```
