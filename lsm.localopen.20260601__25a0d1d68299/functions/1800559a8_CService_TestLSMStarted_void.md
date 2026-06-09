# CService::TestLSMStarted(void)

- ea: `0x1800559a8`
- end: `0x180055a10`
- name: `?TestLSMStarted@CService@@IEAAJXZ`
- size: `104`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800492f0`

## callees

- `0x1800559a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800559db`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800559db`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800559c2`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800559c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800559f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800559f6`

## string_xrefs

- `0x1800559b2`: `Global\TermSrvReadyEvent`

## pseudocode

```c
__int64 __fastcall CService::TestLSMStarted(CService *this)
{
  unsigned int v1; // ebx
  HANDLE v2; // rax
  void *v3; // rdi

  v1 = 0;
  v2 = OpenEventW(0x100000u, 0, L"Global\\TermSrvReadyEvent");
  v3 = v2;
  if ( v2 )
  {
    v1 = -2147024713;
    if ( WaitForSingleObject(v2, 0) )
      v1 = 0;
    CloseHandle(v3);
  }
  return v1;
}

```

## disassembly

```asm
0x1800559a8  mov     [rsp+arg_0], rbx
0x1800559ad  push    rdi
0x1800559ae  sub     rsp, 20h
0x1800559b2  lea     r8, aGlobalTermsrvr; "Global\\TermSrvReadyEvent"
0x1800559b9  xor     edx, edx; bInheritHandle
0x1800559bb  mov     ecx, 100000h; dwDesiredAccess
0x1800559c0  xor     ebx, ebx
0x1800559c2  call    cs:__imp_OpenEventW
0x1800559c9  nop     dword ptr [rax+rax+00h]
0x1800559ce  mov     rdi, rax
0x1800559d1  test    rax, rax
0x1800559d4  jz      short loc_180055A02
0x1800559d6  xor     edx, edx; dwMilliseconds
0x1800559d8  mov     rcx, rax; hHandle
0x1800559db  call    cs:__imp_WaitForSingleObject
0x1800559e2  nop     dword ptr [rax+rax+00h]
0x1800559e7  xor     ecx, ecx
0x1800559e9  mov     ebx, 800700B7h
0x1800559ee  test    eax, eax
0x1800559f0  cmovnz  ebx, ecx
0x1800559f3  mov     rcx, rdi; hObject
0x1800559f6  call    cs:__imp_CloseHandle
0x1800559fd  nop     dword ptr [rax+rax+00h]
0x180055a02  mov     eax, ebx
0x180055a04  mov     rbx, [rsp+28h+arg_0]
0x180055a09  add     rsp, 20h
0x180055a0d  pop     rdi
0x180055a0e  retn
```
