# CMFAttributesImpl<IMFAttributes,CMFSRWLock>::CopyAllItems(IMFAttributes *)

- ea: `0x18005fc40`
- end: `0x18005fd0b`
- name: `?CopyAllItems@?$CMFAttributesImpl@UIMFAttributes@@VCMFSRWLock@@@@UEAAJPEAUIMFAttributes@@@Z`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18005fc40`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005fc71`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005fc71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005fcea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005fcea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005fcf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005fcf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fc57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fcc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fc57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fcc7`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CMFSRWLock>::CopyAllItems(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  _DWORD *v5; // rdi
  int v6; // r14d
  __int64 i; // rsi

  v3 = a1 + 8;
  v5 = (_DWORD *)(a1 + 20);
  if ( *(_DWORD *)(a1 + 16) == GetCurrentThreadId() )
    ++*v5;
  else
    AcquireSRWLockShared((PSRWLOCK)v3);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 160LL))(a2);
  if ( v6 >= 0 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 36); i = (unsigned int)(i + 1) )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a2 + 144LL))(
             a2,
             *(_QWORD *)(a1 + 24) + 40 * i,
             *(_QWORD *)(a1 + 24) + 40 * i + 16);
      if ( v6 < 0 )
        break;
    }
  }
  if ( *(_DWORD *)(v3 + 8) == GetCurrentThreadId() )
  {
    if ( *v5 )
    {
      --*v5;
    }
    else
    {
      *(_DWORD *)(v3 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v3);
    }
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)v3);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005fc40  push    rbx
0x18005fc42  push    rbp
0x18005fc43  push    rsi
0x18005fc44  push    rdi
0x18005fc45  push    r14
0x18005fc47  push    r15
0x18005fc49  sub     rsp, 28h
0x18005fc4d  mov     r15, rdx
0x18005fc50  lea     rbx, [rcx+8]
0x18005fc54  mov     rbp, rcx
0x18005fc57  call    cs:__imp_GetCurrentThreadId
0x18005fc5d  mov     r8d, [rbx+8]
0x18005fc61  lea     rdi, [rbx+0Ch]
0x18005fc65  cmp     r8d, eax
0x18005fc68  jnz     short loc_18005FC6E
0x18005fc6a  inc     dword ptr [rdi]
0x18005fc6c  jmp     short loc_18005FC77
0x18005fc6e  mov     rcx, rbx; SRWLock
0x18005fc71  call    cs:__imp_AcquireSRWLockShared
0x18005fc77  mov     rax, [r15]
0x18005fc7a  mov     rcx, r15
0x18005fc7d  mov     rax, [rax+0A0h]
0x18005fc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc89  mov     r14d, eax
0x18005fc8c  test    eax, eax
0x18005fc8e  js      short loc_18005FCC7
0x18005fc90  xor     esi, esi
0x18005fc92  cmp     [rbp+24h], esi
0x18005fc95  jbe     short loc_18005FCC7
0x18005fc97  mov     rax, [rbp+18h]
0x18005fc9b  lea     rcx, [rsi+rsi*4]
0x18005fc9f  lea     rdx, [rax+rcx*8]
0x18005fca3  mov     rax, [r15]
0x18005fca6  lea     r8, [rdx+10h]
0x18005fcaa  mov     rcx, r15
0x18005fcad  mov     rax, [rax+90h]
0x18005fcb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcb9  mov     r14d, eax
0x18005fcbc  test    eax, eax
0x18005fcbe  js      short loc_18005FCC7
0x18005fcc0  inc     esi
0x18005fcc2  cmp     esi, [rbp+24h]
0x18005fcc5  jb      short loc_18005FC97
0x18005fcc7  call    cs:__imp_GetCurrentThreadId
0x18005fccd  mov     ecx, [rbx+8]
0x18005fcd0  cmp     ecx, eax
0x18005fcd2  jnz     short loc_18005FCF2
0x18005fcd4  mov     eax, [rdi]
0x18005fcd6  test    eax, eax
0x18005fcd8  jz      short loc_18005FCE0
0x18005fcda  dec     eax
0x18005fcdc  mov     [rdi], eax
0x18005fcde  jmp     short loc_18005FCFB
0x18005fce0  mov     rcx, rbx; SRWLock
0x18005fce3  mov     dword ptr [rbx+8], 0
0x18005fcea  call    cs:__imp_ReleaseSRWLockExclusive
0x18005fcf0  jmp     short loc_18005FCFB
0x18005fcf2  mov     rcx, rbx; SRWLock
0x18005fcf5  call    cs:__imp_ReleaseSRWLockShared
0x18005fcfb  mov     eax, r14d
0x18005fcfe  add     rsp, 28h
0x18005fd02  pop     r15
0x18005fd04  pop     r14
0x18005fd06  pop     rdi
0x18005fd07  pop     rsi
0x18005fd08  pop     rbp
0x18005fd09  pop     rbx
0x18005fd0a  retn
```
