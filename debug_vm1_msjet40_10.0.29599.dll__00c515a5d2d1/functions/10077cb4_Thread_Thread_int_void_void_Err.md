# Thread::Thread(int (*)(void *),void *,Err &)

- ea: `0x10077cb4`
- end: `0x10077d19`
- name: `??0Thread@@QAE@P6GHPAX@Z0AAVErr@@@Z`
- size: `101`
- prototype: `Thread *__thiscall(Thread *__hidden this, int (__stdcall *)(void *), void *lpParameter, struct Err *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x100614e1`

## callees

- `0x10061284`
- `0x10074d75`
- `0x10077cb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x10077cd0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x10077cd0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x10077cdf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x10077cdf`

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
0x10077cb4  mov     edi, edi
0x10077cb6  push    ebp
0x10077cb7  mov     ebp, esp
0x10077cb9  push    ecx
0x10077cba  push    ebx
0x10077cbb  push    edi
0x10077cbc  lea     eax, [ebp+ThreadId]
0x10077cbf  xor     ebx, ebx
0x10077cc1  push    eax; lpThreadId
0x10077cc2  push    4; dwCreationFlags
0x10077cc4  push    [ebp+lpParameter]; lpParameter
0x10077cc7  mov     edi, ecx
0x10077cc9  push    offset ?WorkerThread@System@@CGHPAX@Z; lpStartAddress
0x10077cce  push    ebx; dwStackSize
0x10077ccf  push    ebx; lpThreadAttributes
0x10077cd0  call    ds:__imp__CreateThread@24; CreateThread(x,x,x,x,x,x)
0x10077cd6  mov     [edi], eax
0x10077cd8  test    eax, eax
0x10077cda  jz      short loc_10077CE7
0x10077cdc  push    1; nPriority
0x10077cde  push    eax; hThread
0x10077cdf  call    ds:__imp__SetThreadPriority@8; SetThreadPriority(x,x)
0x10077ce5  jmp     short loc_10077D11
0x10077ce7  push    esi
0x10077ce8  mov     esi, [ebp+arg_8]
0x10077ceb  push    esi
0x10077cec  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x10077cf1  test    byte ptr [esi], 1
0x10077cf4  jnz     short loc_10077D10
0x10077cf6  mov     eax, 0FFFFEA84h
0x10077cfb  cmp     [esi+4], eax
0x10077cfe  jnz     short loc_10077D10
0x10077d00  push    ecx
0x10077d01  push    ebx
0x10077d02  push    ebx
0x10077d03  push    0FFFFDF30h
0x10077d08  push    eax
0x10077d09  mov     ecx, esi
0x10077d0b  call    ?SetError@Err@@QAEXJJQAG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort * const,ushort * const,ErrAssert)
0x10077d10  pop     esi
0x10077d11  mov     eax, edi
0x10077d13  pop     edi
0x10077d14  pop     ebx
0x10077d15  leave
0x10077d16  retn    0Ch
```
