# CDfMutex::Release(void)

- ea: `0x18001b840`
- end: `0x18001b893`
- name: `?Release@CDfMutex@@QEAAXXZ`
- size: `83`
- prototype: `void __fastcall(CDfMutex *__hidden this)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180010710`
- `0x180015f30`
- `0x180019b20`
- `0x18001a510`
- `0x18001b550`
- `0x18001e0f8`
- `0x180024720`
- `0x1800316d0`
- `0x180031770`
- `0x180031d40`
- `0x180036fd0`
- `0x1800375d0`
- `0x180038650`
- `0x18003b588`
- `0x1800405dc`
- `0x18004d7f0`
- `0x18004e170`

## callees

- `0x18001b840`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b849`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b849`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b88b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b88b`

## pseudocode

```c
void __fastcall CDfMutex::Release(HANDLE *this)
{
  DWORD CurrentThreadId; // eax
  _DWORD *v3; // rdx
  bool v4; // zf
  volatile signed __int32 *v5; // rax

  CurrentThreadId = GetCurrentThreadId();
  v3 = *this;
  if ( *((_DWORD *)*this + 2) == CurrentThreadId )
  {
    v4 = v3[1]-- == 1;
    v5 = (volatile signed __int32 *)*this;
    if ( v4 )
    {
      *((_DWORD *)v5 + 2) = 0;
      if ( _InterlockedDecrement((volatile signed __int32 *)*this) >= 0 )
        SetEvent(this[1]);
    }
    else
    {
      _InterlockedDecrement(v5);
    }
  }
}

```

## disassembly

```asm
0x18001b840  push    rbx
0x18001b842  sub     rsp, 20h
0x18001b846  mov     rbx, rcx
0x18001b849  call    cs:__imp_GetCurrentThreadId
0x18001b84f  mov     rdx, [rbx]
0x18001b852  cmp     [rdx+8], eax
0x18001b855  jnz     short loc_18001B878
0x18001b857  sub     dword ptr [rdx+4], 1
0x18001b85b  mov     rax, [rbx]
0x18001b85e  jnz     short loc_18001B87E
0x18001b860  mov     dword ptr [rax+8], 0
0x18001b867  mov     ecx, 0FFFFFFFFh
0x18001b86c  mov     rax, [rbx]
0x18001b86f  lock xadd [rax], ecx
0x18001b873  cmp     ecx, 1
0x18001b876  jns     short loc_18001B887
0x18001b878  add     rsp, 20h
0x18001b87c  pop     rbx
0x18001b87d  retn
0x18001b87e  lock dec dword ptr [rax]
0x18001b881  add     rsp, 20h
0x18001b885  pop     rbx
0x18001b886  retn
0x18001b887  mov     rcx, [rbx+8]; hEvent
0x18001b88b  call    cs:__imp_SetEvent
0x18001b891  jmp     short loc_18001B878
```
