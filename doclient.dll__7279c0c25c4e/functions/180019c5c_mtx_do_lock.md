# mtx_do_lock

- ea: `0x180019c5c`
- end: `0x180019cd2`
- name: `mtx_do_lock`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `233`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c068`
- `0x18000c1ac`
- `0x18000c2bc`
- `0x18000d8f0`
- `0x18000db00`
- `0x18000dd10`
- `0x18000eac4`
- `0x180018814`
- `0x180018ee4`
- `0x1800283f0`
- `0x180029204`
- `0x1800298e4`
- `0x18002b12c`
- `0x18002b430`
- `0x18002b528`
- `0x18002b644`
- `0x18002b73c`
- `0x180030408`
- `0x1800308ac`
- `0x180031fe8`
- `0x180032a40`
- `0x180032b88`
- `0x180032c9c`
- `0x180032dbc`
- `0x180032ed8`
- `0x180033008`
- `0x180033148`
- `0x180033280`
- `0x18003339c`
- `0x1800335c8`
- `0x180033700`
- `0x180033920`
- `0x180036110`
- `0x180040074`
- `0x180043668`
- `0x180046640`
- `0x180046a94`
- `0x180046bb8`
- `0x180047850`
- `0x180047900`
- `0x180047988`
- `0x180047a50`
- `0x180047ec4`
- `0x180047fe0`
- `0x1800497d8`
- `0x180049c10`
- `0x18004ca88`
- `0x18004d5f8`
- `0x18004da80`
- `0x18004dbd0`

## callees

- `0x180019c5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019c85`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019c9c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019c85`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019c9c`

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
0x180019c5c  mov     [rsp+arg_0], rbx
0x180019c61  push    rdi
0x180019c62  sub     rsp, 20h
0x180019c66  mov     rbx, rcx
0x180019c69  call    cs:__imp_GetCurrentThreadId
0x180019c6f  mov     edx, [rbx]
0x180019c71  mov     edi, eax
0x180019c73  btr     edx, 8
0x180019c77  cmp     edx, 1
0x180019c7a  jnz     short loc_180019C93
0x180019c7c  cmp     [rbx+48h], eax
0x180019c7f  jz      short loc_180019C8E
0x180019c81  lea     rcx, [rbx+10h]; SRWLock
0x180019c85  call    cs:__imp_AcquireSRWLockExclusive
0x180019c8b  mov     [rbx+48h], edi
0x180019c8e  inc     dword ptr [rbx+4Ch]
0x180019c91  jmp     short loc_180019CC5
0x180019c93  cmp     [rbx+48h], edi
0x180019c96  jz      short loc_180019CA2
0x180019c98  lea     rcx, [rbx+10h]; SRWLock
0x180019c9c  call    cs:__imp_AcquireSRWLockExclusive
0x180019ca2  mov     ecx, [rbx+4Ch]
0x180019ca5  lea     eax, [rcx+1]
0x180019ca8  mov     [rbx+4Ch], eax
0x180019cab  cmp     eax, 1
0x180019cae  jle     short loc_180019CC2
0x180019cb0  test    dword ptr [rbx], 100h
0x180019cb6  jnz     short loc_180019CC5
0x180019cb8  mov     [rbx+4Ch], ecx
0x180019cbb  mov     eax, 3
0x180019cc0  jmp     short loc_180019CC7
0x180019cc2  mov     [rbx+48h], edi
0x180019cc5  xor     eax, eax
0x180019cc7  mov     rbx, [rsp+28h+arg_0]
0x180019ccc  add     rsp, 20h
0x180019cd0  pop     rdi
0x180019cd1  retn
```
