# OUTPUT_CACHE::CacheFlushByHitCount(OUTPUT_ENTRY *,void *)

- ea: `0x1800081f0`
- end: `0x1800082fd`
- name: `?CacheFlushByHitCount@OUTPUT_CACHE@@CA?AW4LK_PREDICATE@@PEAVOUTPUT_ENTRY@@PEAX@Z`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800064bc`
- `0x1800064fc`
- `0x1800081f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008239`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000825f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008239`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000825f`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180008217`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180008217`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180008270`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180008270`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180008283`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180008283`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800082a6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800082a6`

## pseudocode

```c
__int64 __fastcall OUTPUT_CACHE::CacheFlushByHitCount(__int64 a1, unsigned int a2)
{
  CReaderWriterLock3 *v2; // rbp
  BOOL v5; // r15d
  int v6; // r14d
  __int64 v7; // rdi
  int v8; // ebx
  DWORD v9; // edi
  __int64 v10; // rdi
  int v11; // ebx
  DWORD v12; // edi
  int v13; // eax
  unsigned int v14; // ecx

  v2 = (CReaderWriterLock3 *)(a1 + 816);
  v5 = 0;
  v6 = 0;
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(a1 + 816));
  v7 = *(_QWORD *)(a1 + 824);
  if ( v7 )
  {
    v8 = *(_DWORD *)(v7 + 588);
    v9 = *(_DWORD *)(v7 + 592);
    v5 = GetTickCount() - v8 > v9;
  }
  v10 = *(_QWORD *)(a1 + 832);
  if ( v10 )
  {
    v11 = *(_DWORD *)(v10 + 588);
    v12 = *(_DWORD *)(v10 + 592);
    if ( GetTickCount() - v11 > v12 )
      v6 = 1;
  }
  CReaderWriterLock3::ReadUnlock(v2);
  if ( v5 || v6 )
  {
    CReaderWriterLock3::WriteLock(v2);
    if ( v5 )
      OUTPUT_ENTRY::ClearIdentityResponseEntry((OUTPUT_ENTRY *)a1);
    if ( v6 )
      OUTPUT_ENTRY::ClearAlternateResponseEntry((OUTPUT_ENTRY *)a1);
    CReaderWriterLock3::WriteUnlock(v2);
  }
  v13 = *(_DWORD *)(a1 + 812);
  *(_DWORD *)(a1 + 812) = 0;
  if ( v13 )
    return 2;
  v14 = *(_DWORD *)(a1 + 808);
  *(_DWORD *)(a1 + 808) = v14 >> 1;
  if ( v14 )
    return (unsigned int)(v14 < a2) + 2;
  else
    return 3;
}

```

## disassembly

```asm
0x1800081f0  push    rbx
0x1800081f2  push    rbp
0x1800081f3  push    rsi
0x1800081f4  push    rdi
0x1800081f5  push    r12
0x1800081f7  push    r13
0x1800081f9  push    r14
0x1800081fb  push    r15
0x1800081fd  sub     rsp, 28h
0x180008201  lea     rbp, [rcx+330h]
0x180008208  mov     rsi, rcx
0x18000820b  mov     rcx, rbp
0x18000820e  mov     r12, rdx
0x180008211  xor     r15d, r15d
0x180008214  xor     r14d, r14d
0x180008217  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000821d  mov     rdi, [rsi+338h]
0x180008224  lea     r13d, [r15+1]
0x180008228  test    rdi, rdi
0x18000822b  jz      short loc_180008247
0x18000822d  mov     ebx, [rdi+24Ch]
0x180008233  mov     edi, [rdi+250h]
0x180008239  call    cs:__imp_GetTickCount
0x18000823f  sub     eax, ebx
0x180008241  cmp     eax, edi
0x180008243  cmova   r15d, r13d
0x180008247  mov     rdi, [rsi+340h]
0x18000824e  test    rdi, rdi
0x180008251  jz      short loc_18000826D
0x180008253  mov     ebx, [rdi+24Ch]
0x180008259  mov     edi, [rdi+250h]
0x18000825f  call    cs:__imp_GetTickCount
0x180008265  sub     eax, ebx
0x180008267  cmp     eax, edi
0x180008269  cmova   r14d, r13d
0x18000826d  mov     rcx, rbp
0x180008270  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180008276  test    r15d, r15d
0x180008279  jnz     short loc_180008280
0x18000827b  test    r14d, r14d
0x18000827e  jz      short loc_1800082AC
0x180008280  mov     rcx, rbp
0x180008283  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180008289  test    r15d, r15d
0x18000828c  jz      short loc_180008296
0x18000828e  mov     rcx, rsi; this
0x180008291  call    ?ClearIdentityResponseEntry@OUTPUT_ENTRY@@QEAAXXZ; OUTPUT_ENTRY::ClearIdentityResponseEntry(void)
0x180008296  test    r14d, r14d
0x180008299  jz      short loc_1800082A3
0x18000829b  mov     rcx, rsi; this
0x18000829e  call    ?ClearAlternateResponseEntry@OUTPUT_ENTRY@@QEAAXXZ; OUTPUT_ENTRY::ClearAlternateResponseEntry(void)
0x1800082a3  mov     rcx, rbp
0x1800082a6  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800082ac  mov     eax, [rsi+32Ch]
0x1800082b2  mov     dword ptr [rsi+32Ch], 0
0x1800082bc  test    eax, eax
0x1800082be  jnz     short loc_1800082E7
0x1800082c0  mov     ecx, [rsi+328h]
0x1800082c6  mov     eax, ecx
0x1800082c8  shr     eax, 1
0x1800082ca  mov     [rsi+328h], eax
0x1800082d0  test    ecx, ecx
0x1800082d2  jz      short loc_1800082E0
0x1800082d4  cmp     ecx, r12d
0x1800082d7  sbb     eax, eax
0x1800082d9  neg     eax
0x1800082db  add     eax, 2
0x1800082de  jmp     short loc_1800082EC
0x1800082e0  mov     eax, 3
0x1800082e5  jmp     short loc_1800082EC
0x1800082e7  mov     eax, 2
0x1800082ec  add     rsp, 28h
0x1800082f0  pop     r15
0x1800082f2  pop     r14
0x1800082f4  pop     r13
0x1800082f6  pop     r12
0x1800082f8  pop     rdi
0x1800082f9  pop     rsi
0x1800082fa  pop     rbp
0x1800082fb  pop     rbx
0x1800082fc  retn
```
