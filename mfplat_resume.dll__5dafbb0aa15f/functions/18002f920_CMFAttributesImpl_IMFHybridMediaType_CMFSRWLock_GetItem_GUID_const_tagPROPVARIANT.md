# CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::GetItem(_GUID const &,tagPROPVARIANT *)

- ea: `0x18002f920`
- end: `0x18002fab8`
- name: `?GetItem@?$CMFAttributesImpl@UIMFHybridMediaType@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1801495f0`

## callees

- `0x18002f920`
- `0x18002fac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002f94a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002f94a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002f9e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002f9e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f938`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f9d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f938`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f9d5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002f9cd`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002f9cd`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::GetItem(
        CMFSRWLock *a1,
        unsigned int *a2,
        PROPVARIANT *a3)
{
  CMFSRWLock *v4; // rdi
  int m_dwRecursionCount; // r10d
  unsigned int v8; // ebp
  char *Ptr; // rsi
  int v10; // r9d
  __int64 v11; // r8
  char *v12; // rdx
  unsigned int v13; // ebx
  __int64 v14; // rax
  const PROPVARIANT *v15; // rdx
  int j; // r11d
  __int64 v18; // rax
  int i; // r8d
  __int64 v20; // rax
  int k; // r8d
  __int64 v22; // rax

  v4 = a1 + 1;
  if ( a1[1].m_OwningThreadId == GetCurrentThreadId() )
    ++v4->m_dwRecursionCount;
  else
    AcquireSRWLockShared(&v4->m_SRWLock);
  m_dwRecursionCount = a1[2].m_dwRecursionCount;
  if ( !m_dwRecursionCount )
    goto LABEL_9;
  v8 = *a2;
  if ( m_dwRecursionCount < 4 )
  {
    for ( i = 0; i < m_dwRecursionCount; ++i )
    {
      v12 = (char *)a1[2].m_SRWLock.Ptr + 40 * i;
      if ( *(_DWORD *)v12 == v8 )
      {
        v20 = *(_QWORD *)a2 - *(_QWORD *)v12;
        if ( *(_QWORD *)a2 == *(_QWORD *)v12 )
          v20 = *((_QWORD *)a2 + 1) - *((_QWORD *)v12 + 1);
        if ( !v20 )
          goto LABEL_16;
      }
      else if ( *(_DWORD *)v12 > v8 )
      {
        goto LABEL_9;
      }
    }
    goto LABEL_9;
  }
  Ptr = (char *)a1[2].m_SRWLock.Ptr;
  v10 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v11 = (v10 + m_dwRecursionCount) / 2;
      v12 = &Ptr[40 * v11];
      if ( v8 >= *(_DWORD *)v12 )
        break;
      if ( (_DWORD)v11 == v10 )
        goto LABEL_9;
      m_dwRecursionCount = (v10 + m_dwRecursionCount) / 2;
    }
    if ( v8 <= *(_DWORD *)v12 )
      break;
    v10 = v11 + 1;
    if ( (_DWORD)v11 + 1 == m_dwRecursionCount )
      goto LABEL_9;
  }
  v14 = *(_QWORD *)a2 - *(_QWORD *)v12;
  if ( *(_QWORD *)a2 == *(_QWORD *)v12 )
    v14 = *((_QWORD *)a2 + 1) - *((_QWORD *)v12 + 1);
  if ( v14 )
  {
    if ( (int)v11 > v10 )
    {
      for ( j = v11 - 1; j >= v10; --j )
      {
        v12 = &Ptr[40 * j];
        if ( v8 != *(_DWORD *)v12 )
          break;
        v18 = *(_QWORD *)a2 - *(_QWORD *)v12;
        if ( *(_QWORD *)a2 == *(_QWORD *)v12 )
          v18 = *((_QWORD *)a2 + 1) - *((_QWORD *)v12 + 1);
        if ( !v18 )
          goto LABEL_16;
      }
    }
    for ( k = v11 + 1; k < m_dwRecursionCount; ++k )
    {
      v12 = &Ptr[40 * k];
      if ( v8 != *(_DWORD *)v12 )
        break;
      v22 = *(_QWORD *)a2 - *(_QWORD *)v12;
      if ( *(_QWORD *)a2 == *(_QWORD *)v12 )
        v22 = *((_QWORD *)a2 + 1) - *((_QWORD *)v12 + 1);
      if ( !v22 )
        goto LABEL_16;
    }
    goto LABEL_9;
  }
LABEL_16:
  v15 = (const PROPVARIANT *)(v12 + 16);
  if ( !v15 )
  {
LABEL_9:
    v13 = -1072875802;
    goto LABEL_19;
  }
  v13 = 0;
  if ( a3 )
    v13 = PropVariantCopy(a3, v15);
LABEL_19:
  if ( v4->m_OwningThreadId == GetCurrentThreadId() )
    CMFSRWLock::UnlockExclusive(v4);
  else
    ReleaseSRWLockShared(&v4->m_SRWLock);
  return v13;
}

```

## disassembly

```asm
0x18002f920  push    rbx
0x18002f922  push    rbp
0x18002f923  push    rsi
0x18002f924  push    rdi
0x18002f925  push    r14
0x18002f927  sub     rsp, 20h
0x18002f92b  mov     r14, r8
0x18002f92e  lea     rdi, [rcx+10h]
0x18002f932  mov     rbx, rdx
0x18002f935  mov     rsi, rcx
0x18002f938  call    cs:__imp_GetCurrentThreadId
0x18002f93e  mov     r9d, [rdi+8]
0x18002f942  cmp     r9d, eax
0x18002f945  jz      short loc_18002F9A3
0x18002f947  mov     rcx, rdi; SRWLock
0x18002f94a  call    cs:__imp_AcquireSRWLockShared
0x18002f950  mov     r10d, [rsi+2Ch]
0x18002f954  test    r10d, r10d
0x18002f957  jz      short loc_18002F992
0x18002f959  mov     ebp, [rbx]
0x18002f95b  cmp     r10d, 4
0x18002f95f  jl      loc_18002FA36
0x18002f965  mov     rsi, [rsi+20h]
0x18002f969  xor     r9d, r9d
0x18002f96c  lea     eax, [r9+r10]
0x18002f970  mov     ecx, 2
0x18002f975  cdq
0x18002f976  idiv    ecx
0x18002f978  movsxd  r8, eax
0x18002f97b  lea     rdx, [r8+r8*4]
0x18002f97f  lea     rdx, [rsi+rdx*8]
0x18002f983  cmp     ebp, [rdx]
0x18002f985  jb      short loc_18002F999
0x18002f987  jbe     short loc_18002F9A8
0x18002f989  lea     r9d, [r8+1]
0x18002f98d  cmp     r9d, r10d
0x18002f990  jnz     short loc_18002F96C
0x18002f992  mov     ebx, 0C00D36E6h
0x18002f997  jmp     short loc_18002F9D5
0x18002f999  cmp     r8d, r9d
0x18002f99c  jz      short loc_18002F992
0x18002f99e  mov     r10d, r8d
0x18002f9a1  jmp     short loc_18002F96C
0x18002f9a3  inc     dword ptr [rdi+0Ch]
0x18002f9a6  jmp     short loc_18002F950
0x18002f9a8  mov     rax, [rbx]
0x18002f9ab  sub     rax, [rdx]
0x18002f9ae  jnz     short loc_18002F9B8
0x18002f9b0  mov     rax, [rbx+8]
0x18002f9b4  sub     rax, [rdx+8]
0x18002f9b8  test    rax, rax
0x18002f9bb  jnz     short loc_18002F9FF
0x18002f9bd  add     rdx, 10h; pvarSrc
0x18002f9c1  jz      short loc_18002F992
0x18002f9c3  xor     ebx, ebx
0x18002f9c5  test    r14, r14
0x18002f9c8  jz      short loc_18002F9D5
0x18002f9ca  mov     rcx, r14; pvarDest
0x18002f9cd  call    cs:__imp_PropVariantCopy
0x18002f9d3  mov     ebx, eax
0x18002f9d5  call    cs:__imp_GetCurrentThreadId
0x18002f9db  mov     edx, [rdi+8]
0x18002f9de  mov     rcx, rdi; this
0x18002f9e1  cmp     edx, eax
0x18002f9e3  jz      short loc_18002F9F8
0x18002f9e5  call    cs:__imp_ReleaseSRWLockShared
0x18002f9eb  mov     eax, ebx
0x18002f9ed  add     rsp, 20h
0x18002f9f1  pop     r14
0x18002f9f3  pop     rdi
0x18002f9f4  pop     rsi
0x18002f9f5  pop     rbp
0x18002f9f6  pop     rbx
0x18002f9f7  retn
0x18002f9f8  call    ?UnlockExclusive@CMFSRWLock@@QEAAXXZ; CMFSRWLock::UnlockExclusive(void)
0x18002f9fd  jmp     short loc_18002F9EB
0x18002f9ff  cmp     r8d, r9d
0x18002fa02  jle     short loc_18002FA7B
0x18002fa04  lea     r11d, [r8-1]
0x18002fa08  cmp     r11d, r9d
0x18002fa0b  jl      short loc_18002FA7B
0x18002fa0d  movsxd  rax, r11d
0x18002fa10  lea     rcx, [rax+rax*4]
0x18002fa14  lea     rdx, [rsi+rcx*8]
0x18002fa18  cmp     ebp, [rdx]
0x18002fa1a  jnz     short loc_18002FA7B
0x18002fa1c  mov     rax, [rbx]
0x18002fa1f  sub     rax, [rdx]
0x18002fa22  jnz     short loc_18002FA2C
0x18002fa24  mov     rax, [rbx+8]
0x18002fa28  sub     rax, [rdx+8]
0x18002fa2c  test    rax, rax
0x18002fa2f  jz      short loc_18002F9BD
0x18002fa31  dec     r11d
0x18002fa34  jmp     short loc_18002FA08
0x18002fa36  xor     r8d, r8d
0x18002fa39  cmp     r8d, r10d
0x18002fa3c  jge     loc_18002F992
0x18002fa42  movsxd  rax, r8d
0x18002fa45  lea     rcx, [rax+rax*4]
0x18002fa49  mov     rax, [rsi+20h]
0x18002fa4d  lea     rdx, [rax+rcx*8]
0x18002fa51  cmp     [rdx], ebp
0x18002fa53  jz      short loc_18002FA60
0x18002fa55  ja      loc_18002F992
0x18002fa5b  inc     r8d
0x18002fa5e  jmp     short loc_18002FA39
0x18002fa60  mov     rax, [rbx]
0x18002fa63  sub     rax, [rdx]
0x18002fa66  jnz     short loc_18002FA70
0x18002fa68  mov     rax, [rbx+8]
0x18002fa6c  sub     rax, [rdx+8]
0x18002fa70  test    rax, rax
0x18002fa73  jz      loc_18002F9BD
0x18002fa79  jmp     short loc_18002FA5B
0x18002fa7b  inc     r8d
0x18002fa7e  cmp     r8d, r10d
0x18002fa81  jge     loc_18002F992
0x18002fa87  movsxd  rax, r8d
0x18002fa8a  lea     rcx, [rax+rax*4]
0x18002fa8e  lea     rdx, [rsi+rcx*8]
0x18002fa92  cmp     ebp, [rdx]
0x18002fa94  jnz     loc_18002F992
0x18002fa9a  mov     rax, [rbx]
0x18002fa9d  sub     rax, [rdx]
0x18002faa0  jnz     short loc_18002FAAA
0x18002faa2  mov     rax, [rbx+8]
0x18002faa6  sub     rax, [rdx+8]
0x18002faaa  test    rax, rax
0x18002faad  jz      loc_18002F9BD
0x18002fab3  inc     r8d
0x18002fab6  jmp     short loc_18002FA7E
```
