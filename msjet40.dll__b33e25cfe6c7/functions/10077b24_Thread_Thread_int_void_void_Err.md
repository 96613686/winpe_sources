# Thread::Thread(int (*)(void *),void *,Err &)

- ea: `0x10077b24`
- end: `0x10077b89`
- name: `??0Thread@@QAE@P6GHPAX@Z0AAVErr@@@Z`
- size: `101`
- prototype: `Thread *__thiscall(Thread *__hidden this, int (__stdcall *)(void *), void *lpParameter, struct Err *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1006134d`

## callees

- `0x100610f0`
- `0x10074be5`
- `0x10077b24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x10077b40`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x10077b40`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x10077b4f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x10077b4f`

## pseudocode

```c
Thread *__thiscall Thread::Thread(Thread *this, int (__stdcall *a2)(void *), void *lpParameter, struct Err *a4)
{
  HANDLE v5; // eax
  struct Err *v6; // ecx
  int v7; // ecx
  DWORD ThreadId; // [esp+8h] [ebp-4h] BYREF

  v5 = CreateThread(0, 0, System::WorkerThread, lpParameter, 4u, &ThreadId);
  *(_DWORD *)this = v5;
  if ( v5 )
  {
    SetThreadPriority(v5, 1);
  }
  else
  {
    System::ErrGetLastError(v6);
    if ( (*(_BYTE *)a4 & 1) == 0 && *((_DWORD *)a4 + 1) == -5500 )
      Err::SetError(a4, -5500, -8400, 0, 0, v7);
  }
  return this;
}

```

## disassembly

```asm
0x10077b24  mov     edi, edi
0x10077b26  push    ebp
0x10077b27  mov     ebp, esp
0x10077b29  push    ecx
0x10077b2a  push    ebx
0x10077b2b  push    edi
0x10077b2c  lea     eax, [ebp+ThreadId]
0x10077b2f  xor     ebx, ebx
0x10077b31  push    eax; lpThreadId
0x10077b32  push    4; dwCreationFlags
0x10077b34  push    [ebp+lpParameter]; lpParameter
0x10077b37  mov     edi, ecx
0x10077b39  push    offset ?WorkerThread@System@@CGHPAX@Z; lpStartAddress
0x10077b3e  push    ebx; dwStackSize
0x10077b3f  push    ebx; lpThreadAttributes
0x10077b40  call    ds:__imp__CreateThread@24; CreateThread(x,x,x,x,x,x)
0x10077b46  mov     [edi], eax
0x10077b48  test    eax, eax
0x10077b4a  jz      short loc_10077B57
0x10077b4c  push    1; nPriority
0x10077b4e  push    eax; hThread
0x10077b4f  call    ds:__imp__SetThreadPriority@8; SetThreadPriority(x,x)
0x10077b55  jmp     short loc_10077B81
0x10077b57  push    esi
0x10077b58  mov     esi, [ebp+arg_8]
0x10077b5b  push    esi
0x10077b5c  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x10077b61  test    byte ptr [esi], 1
0x10077b64  jnz     short loc_10077B80
0x10077b66  mov     eax, 0FFFFEA84h
0x10077b6b  cmp     [esi+4], eax
0x10077b6e  jnz     short loc_10077B80
0x10077b70  push    ecx
0x10077b71  push    ebx
0x10077b72  push    ebx
0x10077b73  push    0FFFFDF30h
0x10077b78  push    eax
0x10077b79  mov     ecx, esi
0x10077b7b  call    ?SetError@Err@@QAEXJJQAG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort * const,ushort * const,ErrAssert)
0x10077b80  pop     esi
0x10077b81  mov     eax, edi
0x10077b83  pop     edi
0x10077b84  pop     ebx
0x10077b85  leave
0x10077b86  retn    0Ch
```
