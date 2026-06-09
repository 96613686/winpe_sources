# Win32LiveSystemProvider::EnumThreadsUsingNt(ulong *)

- ea: `0x1803fe47c`
- end: `0x1803fe53c`
- name: `?EnumThreadsUsingNt@Win32LiveSystemProvider@@AEAAJPEAK@Z`
- size: `192`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1803fe450`

## callees

- `0x1803fe47c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803fe4fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803fe50b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803fe4fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803fe50b`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1803fe4eb`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1803fe4eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803fe4c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803fe4c2`
- `ntdll!NtGetNextThread` at `0x1803fe4b1`
- `ntdll!NtGetNextThread` at `0x1803fe4b1`

## pseudocode

```c
signed int __fastcall Win32LiveSystemProvider::EnumThreadsUsingNt(Win32LiveSystemProvider *this, unsigned int *a2)
{
  HANDLE *v2; // rsi
  void *v3; // rbx
  int NextThread; // edi
  signed int result; // eax
  DWORD ThreadId; // eax

  v2 = (HANDLE *)((char *)this + 704);
  v3 = (void *)*((_QWORD *)this + 88);
  NextThread = NtGetNextThread(*((_QWORD *)this + 82), v3, 64);
  CloseHandle(v3);
  if ( NextThread >= 0 )
  {
    ThreadId = GetThreadId(*v2);
    if ( ThreadId )
    {
      *a2 = ThreadId;
      return 0;
    }
    else if ( GetLastError() )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
    else
    {
      return -2147467259;
    }
  }
  else
  {
    result = NextThread | 0x10000000;
    if ( NextThread == -2147483622 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1803fe47c  push    rbx
0x1803fe47e  push    rsi
0x1803fe47f  push    rdi
0x1803fe480  push    r14
0x1803fe482  sub     rsp, 38h
0x1803fe486  lea     rsi, [rcx+2C0h]
0x1803fe48d  xor     r9d, r9d
0x1803fe490  mov     rbx, [rsi]
0x1803fe493  mov     r14, rdx
0x1803fe496  mov     rcx, [rcx+290h]
0x1803fe49d  mov     rdx, rbx
0x1803fe4a0  mov     [rsp+58h+var_30], rsi
0x1803fe4a5  lea     r8d, [r9+40h]
0x1803fe4a9  mov     [rsp+58h+var_38], 0
0x1803fe4b1  call    cs:__imp_NtGetNextThread
0x1803fe4b8  nop     dword ptr [rax+rax+00h]
0x1803fe4bd  mov     rcx, rbx; hObject
0x1803fe4c0  mov     edi, eax
0x1803fe4c2  call    cs:__imp_CloseHandle
0x1803fe4c9  nop     dword ptr [rax+rax+00h]
0x1803fe4ce  test    edi, edi
0x1803fe4d0  jns     short loc_1803FE4E8
0x1803fe4d2  mov     eax, edi
0x1803fe4d4  mov     ecx, 1
0x1803fe4d9  bts     eax, 1Ch
0x1803fe4dd  cmp     edi, 8000001Ah
0x1803fe4e3  cmovz   eax, ecx
0x1803fe4e6  jmp     short loc_1803FE531
0x1803fe4e8  mov     rcx, [rsi]; Thread
0x1803fe4eb  call    cs:__imp_GetThreadId
0x1803fe4f2  nop     dword ptr [rax+rax+00h]
0x1803fe4f7  test    eax, eax
0x1803fe4f9  jnz     short loc_1803FE52C
0x1803fe4fb  call    cs:__imp_GetLastError
0x1803fe502  nop     dword ptr [rax+rax+00h]
0x1803fe507  test    eax, eax
0x1803fe509  jz      short loc_1803FE525
0x1803fe50b  call    cs:__imp_GetLastError
0x1803fe512  nop     dword ptr [rax+rax+00h]
0x1803fe517  test    eax, eax
0x1803fe519  jle     short loc_1803FE531
0x1803fe51b  movzx   eax, ax
0x1803fe51e  or      eax, 80070000h
0x1803fe523  jmp     short loc_1803FE531
0x1803fe525  mov     eax, 80004005h
0x1803fe52a  jmp     short loc_1803FE531
0x1803fe52c  mov     [r14], eax
0x1803fe52f  xor     eax, eax
0x1803fe531  add     rsp, 38h
0x1803fe535  pop     r14
0x1803fe537  pop     rdi
0x1803fe538  pop     rsi
0x1803fe539  pop     rbx
0x1803fe53a  retn
```
