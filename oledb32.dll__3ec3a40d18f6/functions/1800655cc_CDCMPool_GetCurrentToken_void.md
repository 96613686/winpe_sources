# CDCMPool::GetCurrentToken(void * *)

- ea: `0x1800655cc`
- end: `0x180065668`
- name: `?GetCurrentToken@CDCMPool@@QEAAJPEAPEAX@Z`
- size: `156`
- prototype: `__int64 __fastcall(CDCMPool *__hidden this, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180064720`
- `0x180065d04`

## callees

- `0x180013870`
- `0x1800655cc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180065607`
- `KERNEL32!GetLastError` at `0x180065607`
- `KERNEL32!GetCurrentProcess` at `0x180065614`
- `KERNEL32!GetCurrentProcess` at `0x180065614`
- `KERNEL32!GetCurrentThread` at `0x1800655e8`
- `KERNEL32!GetCurrentThread` at `0x1800655e8`
- `ADVAPI32!OpenProcessToken` at `0x180065625`
- `ADVAPI32!OpenProcessToken` at `0x180065625`
- `ADVAPI32!OpenThreadToken` at `0x1800655fd`
- `ADVAPI32!OpenThreadToken` at `0x1800655fd`

## string_xrefs

- `0x180065643`: `<CDCMPool::GetCurrentToken|OLEDB|ERR> `

## pseudocode

```c
__int64 __fastcall CDCMPool::GetCurrentToken(CDCMPool *this, void **a2)
{
  unsigned int v2; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  TokenHandle = 0;
  *a2 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
    || GetLastError() == 1008
    && (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 8u, &TokenHandle)) )
  {
    *a2 = TokenHandle;
  }
  else
  {
    v2 = -2147467259;
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(-2147467259, L"<CDCMPool::GetCurrentToken|OLEDB|ERR> ", 0x6E3u);
  }
  return v2;
}

```

## disassembly

```asm
0x1800655cc  mov     [rsp+arg_8], rbx
0x1800655d1  mov     [rsp+TokenHandle], rcx
0x1800655d6  push    rdi
0x1800655d7  sub     rsp, 20h
0x1800655db  xor     ebx, ebx
0x1800655dd  mov     rdi, rdx
0x1800655e0  mov     [rsp+28h+TokenHandle], rbx
0x1800655e5  mov     [rdx], rbx
0x1800655e8  call    cs:__imp_GetCurrentThread
0x1800655ee  mov     rcx, rax; ThreadHandle
0x1800655f1  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800655f6  lea     edx, [rbx+8]; DesiredAccess
0x1800655f9  lea     r8d, [rbx+1]; OpenAsSelf
0x1800655fd  call    cs:__imp_OpenThreadToken
0x180065603  test    eax, eax
0x180065605  jnz     short loc_180065653
0x180065607  call    cs:__imp_GetLastError
0x18006560d  cmp     eax, 3F0h
0x180065612  jnz     short loc_18006562F
0x180065614  call    cs:__imp_GetCurrentProcess
0x18006561a  mov     rcx, rax; ProcessHandle
0x18006561d  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180065622  lea     edx, [rbx+8]; DesiredAccess
0x180065625  call    cs:__imp_OpenProcessToken
0x18006562b  test    eax, eax
0x18006562d  jnz     short loc_180065653
0x18006562f  test    byte ptr cs:_bidGblFlags, 2
0x180065636  mov     ebx, 80004005h
0x18006563b  jz      short loc_18006565B
0x18006563d  mov     r8d, 6E3h; unsigned int
0x180065643  lea     rdx, aCdcmpoolGetcur; "<CDCMPool::GetCurrentToken|OLEDB|ERR> "
0x18006564a  mov     ecx, ebx; int
0x18006564c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180065651  jmp     short loc_18006565B
0x180065653  mov     rcx, [rsp+28h+TokenHandle]
0x180065658  mov     [rdi], rcx
0x18006565b  mov     eax, ebx
0x18006565d  mov     rbx, [rsp+28h+arg_8]
0x180065662  add     rsp, 20h
0x180065666  pop     rdi
0x180065667  retn
```
