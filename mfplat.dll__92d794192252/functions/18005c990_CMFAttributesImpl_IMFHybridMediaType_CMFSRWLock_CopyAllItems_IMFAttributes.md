# CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::CopyAllItems(IMFAttributes *)

- ea: `0x18005c990`
- end: `0x18005ca5b`
- name: `?CopyAllItems@?$CMFAttributesImpl@UIMFHybridMediaType@@VCMFSRWLock@@@@UEAAJPEAUIMFAttributes@@@Z`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180148f40`

## callees

- `0x18005c990`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005c9c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005c9c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ca3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ca3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ca45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ca45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c9a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ca17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c9a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ca17`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::CopyAllItems(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  _DWORD *v5; // rdi
  int v6; // r14d
  __int64 i; // rsi

  v3 = a1 + 16;
  v5 = (_DWORD *)(a1 + 28);
  if ( *(_DWORD *)(a1 + 24) == GetCurrentThreadId() )
    ++*v5;
  else
    AcquireSRWLockShared((PSRWLOCK)v3);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 160LL))(a2);
  if ( v6 >= 0 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 44); i = (unsigned int)(i + 1) )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a2 + 144LL))(
             a2,
             *(_QWORD *)(a1 + 32) + 40 * i,
             *(_QWORD *)(a1 + 32) + 40 * i + 16);
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
0x18005c990  push    rbx
0x18005c992  push    rbp
0x18005c993  push    rsi
0x18005c994  push    rdi
0x18005c995  push    r14
0x18005c997  push    r15
0x18005c999  sub     rsp, 28h
0x18005c99d  mov     r15, rdx
0x18005c9a0  lea     rbx, [rcx+10h]
0x18005c9a4  mov     rbp, rcx
0x18005c9a7  call    cs:__imp_GetCurrentThreadId
0x18005c9ad  mov     r8d, [rbx+8]
0x18005c9b1  lea     rdi, [rbx+0Ch]
0x18005c9b5  cmp     r8d, eax
0x18005c9b8  jnz     short loc_18005C9BE
0x18005c9ba  inc     dword ptr [rdi]
0x18005c9bc  jmp     short loc_18005C9C7
0x18005c9be  mov     rcx, rbx; SRWLock
0x18005c9c1  call    cs:__imp_AcquireSRWLockShared
0x18005c9c7  mov     rax, [r15]
0x18005c9ca  mov     rcx, r15
0x18005c9cd  mov     rax, [rax+0A0h]
0x18005c9d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c9d9  mov     r14d, eax
0x18005c9dc  test    eax, eax
0x18005c9de  js      short loc_18005CA17
0x18005c9e0  xor     esi, esi
0x18005c9e2  cmp     [rbp+2Ch], esi
0x18005c9e5  jbe     short loc_18005CA17
0x18005c9e7  mov     rax, [rbp+20h]
0x18005c9eb  lea     rcx, [rsi+rsi*4]
0x18005c9ef  lea     rdx, [rax+rcx*8]
0x18005c9f3  mov     rax, [r15]
0x18005c9f6  lea     r8, [rdx+10h]
0x18005c9fa  mov     rcx, r15
0x18005c9fd  mov     rax, [rax+90h]
0x18005ca04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca09  mov     r14d, eax
0x18005ca0c  test    eax, eax
0x18005ca0e  js      short loc_18005CA17
0x18005ca10  inc     esi
0x18005ca12  cmp     esi, [rbp+2Ch]
0x18005ca15  jb      short loc_18005C9E7
0x18005ca17  call    cs:__imp_GetCurrentThreadId
0x18005ca1d  mov     ecx, [rbx+8]
0x18005ca20  cmp     ecx, eax
0x18005ca22  jnz     short loc_18005CA42
0x18005ca24  mov     eax, [rdi]
0x18005ca26  test    eax, eax
0x18005ca28  jz      short loc_18005CA30
0x18005ca2a  dec     eax
0x18005ca2c  mov     [rdi], eax
0x18005ca2e  jmp     short loc_18005CA4B
0x18005ca30  mov     rcx, rbx; SRWLock
0x18005ca33  mov     dword ptr [rbx+8], 0
0x18005ca3a  call    cs:__imp_ReleaseSRWLockExclusive
0x18005ca40  jmp     short loc_18005CA4B
0x18005ca42  mov     rcx, rbx; SRWLock
0x18005ca45  call    cs:__imp_ReleaseSRWLockShared
0x18005ca4b  mov     eax, r14d
0x18005ca4e  add     rsp, 28h
0x18005ca52  pop     r15
0x18005ca54  pop     r14
0x18005ca56  pop     rdi
0x18005ca57  pop     rsi
0x18005ca58  pop     rbp
0x18005ca59  pop     rbx
0x18005ca5a  retn
```
