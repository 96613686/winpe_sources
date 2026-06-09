# NtWin32LiveSystemProvider::DupSame(unsigned __int64,void * *)

- ea: `0x180023398`
- end: `0x180023437`
- name: `?DupSame@NtWin32LiveSystemProvider@@AEAAJ_KPEAPEAX@Z`
- size: `159`
- prototype: `int(NtWin32LiveSystemProvider *__hidden this, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180023920`
- `0x180023dc0`

## callees

- `0x180023398`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023411`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800233b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800233b1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800233fd`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800233fd`

## pseudocode

```c
int __fastcall NtWin32LiveSystemProvider::DupSame(NtWin32LiveSystemProvider *this, void *a2, void **a3)
{
  __int64 (__fastcall *v3)(void *, void *, HANDLE, void **, _DWORD, _DWORD, int); // rdi
  HANDLE CurrentProcess; // rax
  void *v8; // rcx
  int v9; // edx
  int result; // eax

  v3 = (__int64 (__fastcall *)(void *, void *, HANDLE, void **, _DWORD, _DWORD, int))*((_QWORD *)this + 104);
  CurrentProcess = GetCurrentProcess();
  v8 = (void *)*((_QWORD *)this + 82);
  if ( v3 )
  {
    v9 = v3(v8, a2, CurrentProcess, a3, 0, 0, 2);
    result = 0;
    if ( v9 < 0 )
      return v9 | 0x10000000;
  }
  else if ( DuplicateHandle(v8, a2, CurrentProcess, a3, 0, 0, 2u) )
  {
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
  return result;
}

```

## disassembly

```asm
0x180023398  push    rbx
0x18002339a  push    rbp
0x18002339b  push    rsi
0x18002339c  push    rdi
0x18002339d  sub     rsp, 48h
0x1800233a1  mov     rdi, [rcx+340h]
0x1800233a8  mov     rsi, r8
0x1800233ab  mov     rbp, rdx
0x1800233ae  mov     rbx, rcx
0x1800233b1  call    cs:__imp_GetCurrentProcess
0x1800233b7  mov     rcx, [rbx+290h]; hSourceProcessHandle
0x1800233be  mov     r8, rax; hTargetProcessHandle
0x1800233c1  mov     [rsp+68h+dwOptions], 2; dwOptions
0x1800233c9  mov     r9, rsi; lpTargetHandle
0x1800233cc  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x1800233d4  mov     rdx, rbp; hSourceHandle
0x1800233d7  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x1800233df  test    rdi, rdi
0x1800233e2  jz      short loc_1800233FD
0x1800233e4  mov     rax, rdi
0x1800233e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233ec  mov     ecx, eax
0x1800233ee  mov     edx, eax
0x1800233f0  bts     ecx, 1Ch
0x1800233f4  xor     eax, eax
0x1800233f6  test    edx, edx
0x1800233f8  cmovs   eax, ecx
0x1800233fb  jmp     short loc_18002342E
0x1800233fd  call    cs:__imp_DuplicateHandle
0x180023403  test    eax, eax
0x180023405  jnz     short loc_18002342C
0x180023407  call    cs:__imp_GetLastError
0x18002340d  test    eax, eax
0x18002340f  jz      short loc_180023425
0x180023411  call    cs:__imp_GetLastError
0x180023417  test    eax, eax
0x180023419  jle     short loc_18002342E
0x18002341b  movzx   eax, ax
0x18002341e  or      eax, 80070000h
0x180023423  jmp     short loc_18002342E
0x180023425  mov     eax, 80004005h
0x18002342a  jmp     short loc_18002342E
0x18002342c  xor     eax, eax
0x18002342e  add     rsp, 48h
0x180023432  pop     rdi
0x180023433  pop     rsi
0x180023434  pop     rbp
0x180023435  pop     rbx
0x180023436  retn
```
