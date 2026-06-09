# CWinTaskHandler::StopWorker(long *)

- ea: `0x1800133f0`
- end: `0x180013459`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800133f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180013432`
- `KERNEL32!GetLastError` at `0x180013432`
- `KERNEL32!WaitForSingleObject` at `0x18001341c`
- `KERNEL32!WaitForSingleObject` at `0x18001341c`

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
0x1800133f0  mov     [rsp+arg_0], rbx
0x1800133f5  push    rdi
0x1800133f6  sub     rsp, 20h
0x1800133fa  cmp     qword ptr [rcx+28h], 0
0x1800133ff  mov     rdi, rcx
0x180013402  jnz     short loc_18001340B
0x180013404  mov     ebx, 80070057h
0x180013409  jmp     short loc_180013447
0x18001340b  mov     eax, 1
0x180013410  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180013413  xchg    eax, [rcx+24h]
0x180013416  mov     rcx, [rcx+28h]; hHandle
0x18001341a  xor     ebx, ebx
0x18001341c  call    cs:__imp_WaitForSingleObject
0x180013422  test    eax, eax
0x180013424  jz      short loc_180013447
0x180013426  cmp     eax, 0FFFFFFFFh
0x180013429  jz      short loc_180013432
0x18001342b  mov     ebx, 80004005h
0x180013430  jmp     short loc_180013447
0x180013432  call    cs:__imp_GetLastError
0x180013438  mov     ebx, eax
0x18001343a  test    eax, eax
0x18001343c  jle     short loc_180013447
0x18001343e  movzx   ebx, ax
0x180013441  or      ebx, 80070000h
0x180013447  xor     ecx, ecx
0x180013449  mov     eax, ebx
0x18001344b  xchg    ecx, [rdi+24h]
0x18001344e  mov     rbx, [rsp+28h+arg_0]
0x180013453  add     rsp, 20h
0x180013457  pop     rdi
0x180013458  retn
```
