# GetProcessToken(ulong,ulong,void * *)

- ea: `0x180025024`
- end: `0x1800250a4`
- name: `?GetProcessToken@@YAJKKPEAPEAX@Z`
- size: `128`
- prototype: `int(unsigned int, unsigned int, void **)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180023d98`
- `0x180024640`
- `0x1800530e0`
- `0x1800623c0`

## callees

- `0x180025024`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002508d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002508d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025054`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025054`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025063`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025063`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002503b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002503b`

## pseudocode

```c
__int64 __fastcall GetProcessToken(__int64 a1, DWORD a2, void **a3)
{
  HANDLE v4; // rax
  void *v5; // rdi
  unsigned int v6; // ebx
  signed int v8; // eax
  signed int LastError; // eax

  v4 = OpenProcess(0x400u, 0, a2);
  v5 = v4;
  if ( v4 )
  {
    if ( OpenProcessToken(v4, 8u, a3) )
    {
      v6 = 0;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(v5);
  }
  else
  {
    v8 = GetLastError();
    v6 = v8;
    if ( v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x180025024  mov     [rsp+arg_0], rbx
0x180025029  push    rdi
0x18002502a  sub     rsp, 20h
0x18002502e  mov     rbx, r8
0x180025031  mov     ecx, 400h; dwDesiredAccess
0x180025036  mov     r8d, edx; dwProcessId
0x180025039  xor     edx, edx; bInheritHandle
0x18002503b  call    cs:__imp_OpenProcess
0x180025041  mov     rdi, rax
0x180025044  test    rax, rax
0x180025047  jz      short loc_180025076
0x180025049  mov     r8, rbx; TokenHandle
0x18002504c  mov     edx, 8; DesiredAccess
0x180025051  mov     rcx, rax; ProcessHandle
0x180025054  call    cs:__imp_OpenProcessToken
0x18002505a  test    eax, eax
0x18002505c  jz      short loc_18002508D
0x18002505e  xor     ebx, ebx
0x180025060  mov     rcx, rdi; hObject
0x180025063  call    cs:__imp_CloseHandle
0x180025069  mov     eax, ebx
0x18002506b  mov     rbx, [rsp+28h+arg_0]
0x180025070  add     rsp, 20h
0x180025074  pop     rdi
0x180025075  retn
0x180025076  call    cs:__imp_GetLastError
0x18002507c  mov     ebx, eax
0x18002507e  test    eax, eax
0x180025080  jle     short loc_180025069
0x180025082  movzx   ebx, ax
0x180025085  or      ebx, 80070000h
0x18002508b  jmp     short loc_180025069
0x18002508d  call    cs:__imp_GetLastError
0x180025093  mov     ebx, eax
0x180025095  test    eax, eax
0x180025097  jle     short loc_180025060
0x180025099  movzx   ebx, ax
0x18002509c  or      ebx, 80070000h
0x1800250a2  jmp     short loc_180025060
```
