# mtx_do_lock

- ea: `0x1801d5f68`
- end: `0x1801d5fde`
- name: `mtx_do_lock`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1801d5f30`

## callees

- `0x1801d5f68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801d5f91`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801d5fa8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801d5f91`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801d5fa8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801d5f75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801d5f75`

## pseudocode

```c
__int64 __fastcall mtx_do_lock(__int64 a1)
{
  DWORD CurrentThreadId; // eax
  DWORD v3; // edi
  int v4; // ecx

  CurrentThreadId = GetCurrentThreadId();
  v3 = CurrentThreadId;
  if ( (*(_DWORD *)a1 & 0xFFFFFEFF) == 1 )
  {
    if ( *(_DWORD *)(a1 + 72) != CurrentThreadId )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
      *(_DWORD *)(a1 + 72) = v3;
    }
    ++*(_DWORD *)(a1 + 76);
  }
  else
  {
    if ( *(_DWORD *)(a1 + 72) != CurrentThreadId )
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
    v4 = *(_DWORD *)(a1 + 76);
    *(_DWORD *)(a1 + 76) = v4 + 1;
    if ( v4 + 1 <= 1 )
    {
      *(_DWORD *)(a1 + 72) = v3;
    }
    else if ( (*(_DWORD *)a1 & 0x100) == 0 )
    {
      *(_DWORD *)(a1 + 76) = v4;
      return 3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1801d5f68  mov     [rsp+arg_0], rbx
0x1801d5f6d  push    rdi
0x1801d5f6e  sub     rsp, 20h
0x1801d5f72  mov     rbx, rcx
0x1801d5f75  call    cs:__imp_GetCurrentThreadId
0x1801d5f7b  mov     edx, [rbx]
0x1801d5f7d  mov     edi, eax
0x1801d5f7f  btr     edx, 8
0x1801d5f83  cmp     edx, 1
0x1801d5f86  jnz     short loc_1801D5F9F
0x1801d5f88  cmp     [rbx+48h], eax
0x1801d5f8b  jz      short loc_1801D5F9A
0x1801d5f8d  lea     rcx, [rbx+10h]; SRWLock
0x1801d5f91  call    cs:__imp_AcquireSRWLockExclusive
0x1801d5f97  mov     [rbx+48h], edi
0x1801d5f9a  inc     dword ptr [rbx+4Ch]
0x1801d5f9d  jmp     short loc_1801D5FD1
0x1801d5f9f  cmp     [rbx+48h], edi
0x1801d5fa2  jz      short loc_1801D5FAE
0x1801d5fa4  lea     rcx, [rbx+10h]; SRWLock
0x1801d5fa8  call    cs:__imp_AcquireSRWLockExclusive
0x1801d5fae  mov     ecx, [rbx+4Ch]
0x1801d5fb1  lea     eax, [rcx+1]
0x1801d5fb4  mov     [rbx+4Ch], eax
0x1801d5fb7  cmp     eax, 1
0x1801d5fba  jle     short loc_1801D5FCE
0x1801d5fbc  test    dword ptr [rbx], 100h
0x1801d5fc2  jnz     short loc_1801D5FD1
0x1801d5fc4  mov     [rbx+4Ch], ecx
0x1801d5fc7  mov     eax, 3
0x1801d5fcc  jmp     short loc_1801D5FD3
0x1801d5fce  mov     [rbx+48h], edi
0x1801d5fd1  xor     eax, eax
0x1801d5fd3  mov     rbx, [rsp+28h+arg_0]
0x1801d5fd8  add     rsp, 20h
0x1801d5fdc  pop     rdi
0x1801d5fdd  retn
```
