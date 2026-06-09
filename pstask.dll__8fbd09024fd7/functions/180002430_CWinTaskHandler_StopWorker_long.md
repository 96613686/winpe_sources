# CWinTaskHandler::StopWorker(long *)

- ea: `0x180002430`
- end: `0x180002499`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002430`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002472`
- `KERNEL32!GetLastError` at `0x180002472`
- `KERNEL32!WaitForSingleObject` at `0x18000245c`
- `KERNEL32!WaitForSingleObject` at `0x18000245c`

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
0x180002430  mov     [rsp+arg_0], rbx
0x180002435  push    rdi
0x180002436  sub     rsp, 20h
0x18000243a  cmp     qword ptr [rcx+28h], 0
0x18000243f  mov     rdi, rcx
0x180002442  jnz     short loc_18000244B
0x180002444  mov     ebx, 80070057h
0x180002449  jmp     short loc_180002487
0x18000244b  mov     eax, 1
0x180002450  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002453  xchg    eax, [rcx+24h]
0x180002456  mov     rcx, [rcx+28h]; hHandle
0x18000245a  xor     ebx, ebx
0x18000245c  call    cs:__imp_WaitForSingleObject
0x180002462  test    eax, eax
0x180002464  jz      short loc_180002487
0x180002466  cmp     eax, 0FFFFFFFFh
0x180002469  jz      short loc_180002472
0x18000246b  mov     ebx, 80004005h
0x180002470  jmp     short loc_180002487
0x180002472  call    cs:__imp_GetLastError
0x180002478  mov     ebx, eax
0x18000247a  test    eax, eax
0x18000247c  jle     short loc_180002487
0x18000247e  movzx   ebx, ax
0x180002481  or      ebx, 80070000h
0x180002487  xor     ecx, ecx
0x180002489  mov     eax, ebx
0x18000248b  xchg    ecx, [rdi+24h]
0x18000248e  mov     rbx, [rsp+28h+arg_0]
0x180002493  add     rsp, 20h
0x180002497  pop     rdi
0x180002498  retn
```
