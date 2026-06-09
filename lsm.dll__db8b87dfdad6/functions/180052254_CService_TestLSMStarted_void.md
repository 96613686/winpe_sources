# CService::TestLSMStarted(void)

- ea: `0x180052254`
- end: `0x1800522a9`
- name: `?TestLSMStarted@CService@@IEAAJXZ`
- size: `85`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180045fd4`

## callees

- `0x180052254`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180052281`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180052281`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18005226e`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18005226e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052296`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052296`

## string_xrefs

- `0x18005225e`: `Global\TermSrvReadyEvent`

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
0x180052254  mov     [rsp+arg_0], rbx
0x180052259  push    rdi
0x18005225a  sub     rsp, 20h
0x18005225e  lea     r8, aGlobalTermsrvr; "Global\\TermSrvReadyEvent"
0x180052265  xor     edx, edx; bInheritHandle
0x180052267  mov     ecx, 100000h; dwDesiredAccess
0x18005226c  xor     ebx, ebx
0x18005226e  call    cs:__imp_OpenEventW
0x180052274  mov     rdi, rax
0x180052277  test    rax, rax
0x18005227a  jz      short loc_18005229C
0x18005227c  xor     edx, edx; dwMilliseconds
0x18005227e  mov     rcx, rax; hHandle
0x180052281  call    cs:__imp_WaitForSingleObject
0x180052287  xor     ecx, ecx
0x180052289  mov     ebx, 800700B7h
0x18005228e  test    eax, eax
0x180052290  cmovnz  ebx, ecx
0x180052293  mov     rcx, rdi; hObject
0x180052296  call    cs:__imp_CloseHandle
0x18005229c  mov     eax, ebx
0x18005229e  mov     rbx, [rsp+28h+arg_0]
0x1800522a3  add     rsp, 20h
0x1800522a7  pop     rdi
0x1800522a8  retn
```
