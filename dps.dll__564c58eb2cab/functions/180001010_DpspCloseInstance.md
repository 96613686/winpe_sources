# DpspCloseInstance

- ea: `0x180001010`
- end: `0x1800010ef`
- name: `DpspCloseInstance`
- size: `223`
- prototype: `__int64 __fastcall(__int64, unsigned int, char, unsigned int)`
- caller_count: `22`
- callee_count: `3`
- tags: ``

## callers

- `0x1800013d0`
- `0x180002510`
- `0x180002a08`
- `0x180004864`
- `0x180004de4`
- `0x1800054f0`
- `0x180009b40`
- `0x18000bd28`
- `0x18000bf58`
- `0x18000c0ec`
- `0x18000c21c`
- `0x18000f9fc`
- `0x18000fbb4`
- `0x180011fd4`
- `0x180013908`
- `0x180013a10`
- `0x180013b4c`
- `0x1800145f0`
- `0x1800146b0`
- `0x1800149dc`
- `0x180014df0`
- `0x180015918`

## callees

- `0x180001010`
- `0x180001100`
- `0x180012670`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001037`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001037`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000105c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000105c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800010c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800010c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000109e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000109e`

## pseudocode

```c
__int64 __fastcall DpspCloseInstance(__int64 a1, unsigned int a2, char a3, unsigned int a4)
{
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF

  v11 = a1;
  if ( (a3 & 8) != 0 )
  {
    if ( _interlockedbittestandreset((volatile signed __int32 *)(a1 + 104), 4u) )
    {
      v9 = *(_QWORD *)(a1 + 808);
      if ( v9 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 64));
        --*(_DWORD *)(*(_QWORD *)(a1 + 808) + 44LL);
        v10 = *(_QWORD *)(a1 + 808);
        if ( v10 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 64));
      }
    }
  }
  if ( a1 )
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
  if ( (a3 & 2) != 0 )
  {
    DpspSendClientFeedback(a1, a2, a4);
    if ( (*(_DWORD *)(a1 + 104) & 0x20) != 0 )
      _InterlockedOr((volatile signed __int32 *)(a1 + 104), 4u);
  }
  if ( (a3 & 4) != 0 )
    _InterlockedAnd((volatile signed __int32 *)(a1 + 104), 0xFFFFFBFF);
  if ( a1 )
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 16));
  if ( (a3 & 1) != 0 )
    *(_DWORD *)(a1 + 132) = 0;
  DpspDecrementInstanceReference(&v11);
  return 0;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_0], rcx
0x180001015  push    rbx
0x180001016  push    rbp
0x180001017  push    rsi
0x180001018  push    rdi
0x180001019  sub     rsp, 28h
0x18000101d  mov     esi, r9d
0x180001020  mov     ebx, r8d
0x180001023  mov     ebp, edx
0x180001025  mov     rdi, rcx
0x180001028  test    r8b, 8
0x18000102c  jnz     short loc_180001086
0x18000102e  test    rdi, rdi
0x180001031  jz      short loc_18000103D
0x180001033  lea     rcx, [rdi+10h]; SRWLock
0x180001037  call    cs:__imp_AcquireSRWLockExclusive
0x18000103d  test    bl, 2
0x180001040  jnz     loc_1800010CD
0x180001046  test    bl, 4
0x180001049  jz      short loc_180001053
0x18000104b  lock and dword ptr [rdi+68h], 0FFFFFBFFh
0x180001053  test    rdi, rdi
0x180001056  jz      short loc_180001062
0x180001058  lea     rcx, [rdi+10h]; SRWLock
0x18000105c  call    cs:__imp_ReleaseSRWLockExclusive
0x180001062  test    bl, 1
0x180001065  jz      short loc_180001071
0x180001067  mov     dword ptr [rdi+84h], 0
0x180001071  lea     rcx, [rsp+48h+arg_0]
0x180001076  call    DpspDecrementInstanceReference
0x18000107b  xor     eax, eax
0x18000107d  add     rsp, 28h
0x180001081  pop     rdi
0x180001082  pop     rsi
0x180001083  pop     rbp
0x180001084  pop     rbx
0x180001085  retn
0x180001086  lock btr dword ptr [rcx+68h], 4
0x18000108c  jnb     short loc_18000102E
0x18000108e  mov     rcx, [rcx+328h]
0x180001095  test    rcx, rcx
0x180001098  jz      short loc_18000102E
0x18000109a  add     rcx, 40h ; '@'; lpCriticalSection
0x18000109e  call    cs:__imp_EnterCriticalSection
0x1800010a4  mov     rax, [rdi+328h]
0x1800010ab  dec     dword ptr [rax+2Ch]
0x1800010ae  mov     rcx, [rdi+328h]
0x1800010b5  test    rcx, rcx
0x1800010b8  jz      loc_18000102E
0x1800010be  add     rcx, 40h ; '@'; lpCriticalSection
0x1800010c2  call    cs:__imp_LeaveCriticalSection
0x1800010c8  jmp     loc_18000102E
0x1800010cd  mov     r8d, esi
0x1800010d0  mov     edx, ebp
0x1800010d2  mov     rcx, rdi
0x1800010d5  call    DpspSendClientFeedback
0x1800010da  mov     eax, [rdi+68h]
0x1800010dd  test    al, 20h
0x1800010df  jz      loc_180001046
0x1800010e5  lock or dword ptr [rdi+68h], 4
0x1800010ea  jmp     loc_180001046
```
