# mtx_do_lock

- ea: `0x18002ae04`
- end: `0x18002ae7a`
- name: `mtx_do_lock`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ace0`

## callees

- `0x18002ae04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ae2d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ae44`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ae2d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ae44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ae11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ae11`

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
0x18002ae04  mov     [rsp+arg_0], rbx
0x18002ae09  push    rdi
0x18002ae0a  sub     rsp, 20h
0x18002ae0e  mov     rbx, rcx
0x18002ae11  call    cs:__imp_GetCurrentThreadId
0x18002ae17  mov     edx, [rbx]
0x18002ae19  mov     edi, eax
0x18002ae1b  btr     edx, 8
0x18002ae1f  cmp     edx, 1
0x18002ae22  jnz     short loc_18002AE3B
0x18002ae24  cmp     [rbx+48h], eax
0x18002ae27  jz      short loc_18002AE36
0x18002ae29  lea     rcx, [rbx+10h]; SRWLock
0x18002ae2d  call    cs:__imp_AcquireSRWLockExclusive
0x18002ae33  mov     [rbx+48h], edi
0x18002ae36  inc     dword ptr [rbx+4Ch]
0x18002ae39  jmp     short loc_18002AE6D
0x18002ae3b  cmp     [rbx+48h], edi
0x18002ae3e  jz      short loc_18002AE4A
0x18002ae40  lea     rcx, [rbx+10h]; SRWLock
0x18002ae44  call    cs:__imp_AcquireSRWLockExclusive
0x18002ae4a  mov     ecx, [rbx+4Ch]
0x18002ae4d  lea     eax, [rcx+1]
0x18002ae50  mov     [rbx+4Ch], eax
0x18002ae53  cmp     eax, 1
0x18002ae56  jle     short loc_18002AE6A
0x18002ae58  test    dword ptr [rbx], 100h
0x18002ae5e  jnz     short loc_18002AE6D
0x18002ae60  mov     [rbx+4Ch], ecx
0x18002ae63  mov     eax, 3
0x18002ae68  jmp     short loc_18002AE6F
0x18002ae6a  mov     [rbx+48h], edi
0x18002ae6d  xor     eax, eax
0x18002ae6f  mov     rbx, [rsp+28h+arg_0]
0x18002ae74  add     rsp, 20h
0x18002ae78  pop     rdi
0x18002ae79  retn
```
