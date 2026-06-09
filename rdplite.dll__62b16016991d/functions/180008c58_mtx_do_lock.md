# mtx_do_lock

- ea: `0x180008c58`
- end: `0x180008cce`
- name: `mtx_do_lock`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800081d0`

## callees

- `0x180008c58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c98`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008c65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008c65`

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
0x180008c58  mov     [rsp+arg_0], rbx
0x180008c5d  push    rdi
0x180008c5e  sub     rsp, 20h
0x180008c62  mov     rbx, rcx
0x180008c65  call    cs:__imp_GetCurrentThreadId
0x180008c6b  mov     edx, [rbx]
0x180008c6d  mov     edi, eax
0x180008c6f  btr     edx, 8
0x180008c73  cmp     edx, 1
0x180008c76  jnz     short loc_180008C8F
0x180008c78  cmp     [rbx+48h], eax
0x180008c7b  jz      short loc_180008C8A
0x180008c7d  lea     rcx, [rbx+10h]; SRWLock
0x180008c81  call    cs:__imp_AcquireSRWLockExclusive
0x180008c87  mov     [rbx+48h], edi
0x180008c8a  inc     dword ptr [rbx+4Ch]
0x180008c8d  jmp     short loc_180008CC1
0x180008c8f  cmp     [rbx+48h], edi
0x180008c92  jz      short loc_180008C9E
0x180008c94  lea     rcx, [rbx+10h]; SRWLock
0x180008c98  call    cs:__imp_AcquireSRWLockExclusive
0x180008c9e  mov     ecx, [rbx+4Ch]
0x180008ca1  lea     eax, [rcx+1]
0x180008ca4  mov     [rbx+4Ch], eax
0x180008ca7  cmp     eax, 1
0x180008caa  jle     short loc_180008CBE
0x180008cac  test    dword ptr [rbx], 100h
0x180008cb2  jnz     short loc_180008CC1
0x180008cb4  mov     [rbx+4Ch], ecx
0x180008cb7  mov     eax, 3
0x180008cbc  jmp     short loc_180008CC3
0x180008cbe  mov     [rbx+48h], edi
0x180008cc1  xor     eax, eax
0x180008cc3  mov     rbx, [rsp+28h+arg_0]
0x180008cc8  add     rsp, 20h
0x180008ccc  pop     rdi
0x180008ccd  retn
```
