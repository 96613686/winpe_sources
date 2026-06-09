# NOTIFICATION_THREAD::Start(CONFIG_CACHE *)

- ea: `0x180051354`
- end: `0x18005140c`
- name: `?Start@NOTIFICATION_THREAD@@QEAAJPEAVCONFIG_CACHE@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(NOTIFICATION_THREAD *__hidden this, struct CONFIG_CACHE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004ff30`

## callees

- `0x180051354`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800513d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800513d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800513ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800513ed`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800513c5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800513c5`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180051383`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180051383`

## pseudocode

```c
signed int __fastcall NOTIFICATION_THREAD::Start(NOTIFICATION_THREAD *this, struct CONFIG_CACHE *a2)
{
  signed int result; // eax
  HANDLE IoCompletionPort; // rax
  HANDLE Thread; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx

  if ( !a2 )
    return -2147024809;
  *((_QWORD *)this + 4) = a2;
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 1u);
  *((_QWORD *)this + 6) = IoCompletionPort;
  if ( IoCompletionPort )
  {
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)NOTIFICATION_THREAD::ThreadProc, this, 0, 0);
    *((_QWORD *)this + 5) = Thread;
    if ( Thread )
    {
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      CloseHandle(*((HANDLE *)this + 6));
      result = v7;
      *((_QWORD *)this + 6) = 0;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180051354  mov     [rsp+arg_0], rbx
0x180051359  push    rdi
0x18005135a  sub     rsp, 30h
0x18005135e  mov     rdi, rcx
0x180051361  test    rdx, rdx
0x180051364  jnz     short loc_180051370
0x180051366  mov     eax, 80070057h
0x18005136b  jmp     loc_180051401
0x180051370  mov     [rcx+20h], rdx
0x180051374  mov     r9d, 1; NumberOfConcurrentThreads
0x18005137a  xor     edx, edx; ExistingCompletionPort
0x18005137c  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x180051380  xor     r8d, r8d; CompletionKey
0x180051383  call    cs:__imp_CreateIoCompletionPort
0x180051389  mov     [rdi+30h], rax
0x18005138d  test    rax, rax
0x180051390  jnz     short loc_1800513A6
0x180051392  call    cs:__imp_GetLastError
0x180051398  test    eax, eax
0x18005139a  jle     short loc_180051401
0x18005139c  movzx   eax, ax
0x18005139f  or      eax, 80070000h
0x1800513a4  jmp     short loc_180051401
0x1800513a6  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800513af  lea     r8, ?ThreadProc@NOTIFICATION_THREAD@@CAKPEAX@Z; lpStartAddress
0x1800513b6  mov     r9, rdi; lpParameter
0x1800513b9  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800513c1  xor     edx, edx; dwStackSize
0x1800513c3  xor     ecx, ecx; lpThreadAttributes
0x1800513c5  call    cs:__imp_CreateThread
0x1800513cb  mov     [rdi+28h], rax
0x1800513cf  test    rax, rax
0x1800513d2  jnz     short loc_1800513FF
0x1800513d4  call    cs:__imp_GetLastError
0x1800513da  mov     ebx, eax
0x1800513dc  test    eax, eax
0x1800513de  jle     short loc_1800513E9
0x1800513e0  movzx   ebx, ax
0x1800513e3  or      ebx, 80070000h
0x1800513e9  mov     rcx, [rdi+30h]; hObject
0x1800513ed  call    cs:__imp_CloseHandle
0x1800513f3  mov     eax, ebx
0x1800513f5  mov     qword ptr [rdi+30h], 0
0x1800513fd  jmp     short loc_180051401
0x1800513ff  xor     eax, eax
0x180051401  mov     rbx, [rsp+38h+arg_0]
0x180051406  add     rsp, 30h
0x18005140a  pop     rdi
0x18005140b  retn
```
