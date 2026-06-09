# DetourUpdateThread

- ea: `0x180078ed0`
- end: `0x180078f7b`
- name: `DetourUpdateThread`
- size: `171`
- prototype: `__int64 __fastcall(HANDLE hThread)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x18001f108`
- `0x180071ab8`

## callees

- `0x18001b22c`
- `0x180076440`
- `0x180078ed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078f26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078f26`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180078f1b`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180078f1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180078ee7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180078ee7`

## pseudocode

```c
__int64 __fastcall DetourUpdateThread(HANDLE hThread)
{
  __int64 result; // rax
  _QWORD *v3; // rbx
  DWORD LastError; // edi

  result = (unsigned int)dword_180108E44;
  if ( !dword_180108E44 )
  {
    if ( hThread == GetCurrentThread() )
      return 0;
    v3 = operator new(0x10u);
    if ( !v3 )
    {
      LastError = 8;
LABEL_8:
      result = LastError;
      dword_180108E44 = LastError;
      qword_180108E48 = 0;
      return result;
    }
    if ( SuspendThread(hThread) == -1 )
    {
      LastError = GetLastError();
      operator delete(v3, 0x10u);
      goto LABEL_8;
    }
    *v3 = qword_180108E50;
    result = 0;
    v3[1] = hThread;
    qword_180108E50 = v3;
  }
  return result;
}

```

## disassembly

```asm
0x180078ed0  push    rdi
0x180078ed2  sub     rsp, 20h
0x180078ed6  mov     eax, cs:dword_180108E44
0x180078edc  mov     rdi, rcx
0x180078edf  test    eax, eax
0x180078ee1  jnz     loc_180078F75
0x180078ee7  call    cs:__imp_GetCurrentThread
0x180078eed  cmp     rdi, rax
0x180078ef0  jnz     short loc_180078EFA
0x180078ef2  xor     eax, eax
0x180078ef4  add     rsp, 20h
0x180078ef8  pop     rdi
0x180078ef9  retn
0x180078efa  mov     ecx, 10h; dwBytes
0x180078eff  mov     [rsp+28h+arg_0], rbx
0x180078f04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180078f09  mov     rbx, rax
0x180078f0c  test    rax, rax
0x180078f0f  jnz     short loc_180078F18
0x180078f11  mov     edi, 8
0x180078f16  jmp     short loc_180078F3B
0x180078f18  mov     rcx, rdi; hThread
0x180078f1b  call    cs:__imp_SuspendThread
0x180078f21  cmp     eax, 0FFFFFFFFh
0x180078f24  jnz     short loc_180078F59
0x180078f26  call    cs:__imp_GetLastError
0x180078f2c  mov     edi, eax
0x180078f2e  mov     edx, 10h; unsigned __int64
0x180078f33  mov     rcx, rbx; void *
0x180078f36  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180078f3b  mov     rbx, [rsp+28h+arg_0]
0x180078f40  mov     eax, edi
0x180078f42  mov     cs:dword_180108E44, edi
0x180078f48  mov     cs:qword_180108E48, 0
0x180078f53  add     rsp, 20h
0x180078f57  pop     rdi
0x180078f58  retn
0x180078f59  mov     rax, cs:qword_180108E50
0x180078f60  mov     [rbx], rax
0x180078f63  xor     eax, eax
0x180078f65  mov     [rbx+8], rdi
0x180078f69  mov     cs:qword_180108E50, rbx
0x180078f70  mov     rbx, [rsp+28h+arg_0]
0x180078f75  add     rsp, 20h
0x180078f79  pop     rdi
0x180078f7a  retn
```
