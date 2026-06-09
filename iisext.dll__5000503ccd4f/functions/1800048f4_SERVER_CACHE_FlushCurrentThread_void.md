# SERVER_CACHE::FlushCurrentThread(void)

- ea: `0x1800048f4`
- end: `0x18000499a`
- name: `?FlushCurrentThread@SERVER_CACHE@@SAXXZ`
- size: `166`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001a2c`

## callees

- `0x180001048`
- `0x18000487c`
- `0x1800048f4`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000490c`
- `KERNEL32!EnterCriticalSection` at `0x18000490c`
- `KERNEL32!LeaveCriticalSection` at `0x18000495e`
- `KERNEL32!LeaveCriticalSection` at `0x18000495e`
- `KERNEL32!GetCurrentThreadId` at `0x18000491c`
- `KERNEL32!GetCurrentThreadId` at `0x18000491c`

## pseudocode

```c
void SERVER_CACHE::FlushCurrentThread(void)
{
  struct _RTL_CRITICAL_SECTION *v0; // rbx
  DWORD CurrentThreadId; // eax
  SERVER_CACHE *v2; // rdi
  DWORD v3; // ebp
  int v4; // ecx
  int v5; // edx
  __int64 v6; // r8
  __int64 v7; // rax
  SERVER_CACHE_ITEM *v8; // rsi
  __int64 v9; // rax

  v0 = g_pGlobalLock;
  if ( g_pGlobalLock )
  {
    EnterCriticalSection(g_pGlobalLock);
    if ( SERVER_CACHE::sm_pServerCache )
    {
      CurrentThreadId = GetCurrentThreadId();
      v2 = SERVER_CACHE::sm_pServerCache;
      v3 = CurrentThreadId;
      *((_DWORD *)SERVER_CACHE::sm_pServerCache + 4) = 0;
      while ( 1 )
      {
        v4 = *((_DWORD *)v2 + 4);
        v5 = *((_DWORD *)v2 + 2);
        if ( v4 >= v5 )
          break;
        v6 = *(_QWORD *)v2;
        while ( 1 )
        {
          v7 = v4++;
          v8 = *(SERVER_CACHE_ITEM **)(v6 + 8 * v7);
          *((_DWORD *)v2 + 4) = v4;
          if ( v8 )
            break;
          if ( v4 >= v5 )
            goto LABEL_8;
        }
        if ( v3 == *((_DWORD *)v8 + 30) )
        {
          v9 = *(int *)v8;
          if ( (int)v9 >= 0 && (int)v9 < v5 )
          {
            --*((_DWORD *)v2 + 3);
            *(_QWORD *)(v6 + 8 * v9) = 0;
          }
          SERVER_CACHE_ITEM::~SERVER_CACHE_ITEM(v8);
          operator delete(v8);
        }
      }
LABEL_8:
      *((_DWORD *)v2 + 4) = 0;
    }
    LeaveCriticalSection(v0);
  }
}

```

## disassembly

```asm
0x1800048f4  push    rbx
0x1800048f6  push    rbp
0x1800048f7  push    rsi
0x1800048f8  push    rdi
0x1800048f9  sub     rsp, 28h
0x1800048fd  mov     rbx, cs:?g_pGlobalLock@@3PEAVWIN32_CRITSEC@@EA; WIN32_CRITSEC * g_pGlobalLock
0x180004904  test    rbx, rbx
0x180004907  jz      short loc_180004964
0x180004909  mov     rcx, rbx; lpCriticalSection
0x18000490c  call    cs:__imp_EnterCriticalSection
0x180004912  cmp     cs:?sm_pServerCache@SERVER_CACHE@@1PEAV1@EA, 0; SERVER_CACHE * SERVER_CACHE::sm_pServerCache
0x18000491a  jz      short loc_18000495B
0x18000491c  call    cs:__imp_GetCurrentThreadId
0x180004922  mov     rdi, cs:?sm_pServerCache@SERVER_CACHE@@1PEAV1@EA; SERVER_CACHE * SERVER_CACHE::sm_pServerCache
0x180004929  mov     ebp, eax
0x18000492b  mov     dword ptr [rdi+10h], 0
0x180004932  mov     ecx, [rdi+10h]
0x180004935  mov     edx, [rdi+8]
0x180004938  cmp     ecx, edx
0x18000493a  jge     short loc_180004954
0x18000493c  mov     r8, [rdi]
0x18000493f  movsxd  rax, ecx
0x180004942  inc     ecx
0x180004944  mov     rsi, [r8+rax*8]
0x180004948  mov     [rdi+10h], ecx
0x18000494b  test    rsi, rsi
0x18000494e  jnz     short loc_18000496D
0x180004950  cmp     ecx, edx
0x180004952  jl      short loc_18000493F
0x180004954  mov     dword ptr [rdi+10h], 0
0x18000495b  mov     rcx, rbx; lpCriticalSection
0x18000495e  call    cs:__imp_LeaveCriticalSection
0x180004964  add     rsp, 28h
0x180004968  pop     rdi
0x180004969  pop     rsi
0x18000496a  pop     rbp
0x18000496b  pop     rbx
0x18000496c  retn
0x18000496d  cmp     ebp, [rsi+78h]
0x180004970  jnz     short loc_180004932
0x180004972  movsxd  rax, dword ptr [rsi]
0x180004975  test    eax, eax
0x180004977  js      short loc_180004988
0x180004979  cmp     eax, edx
0x18000497b  jge     short loc_180004988
0x18000497d  dec     dword ptr [rdi+0Ch]
0x180004980  mov     qword ptr [r8+rax*8], 0
0x180004988  mov     rcx, rsi; this
0x18000498b  call    ??1SERVER_CACHE_ITEM@@QEAA@XZ; SERVER_CACHE_ITEM::~SERVER_CACHE_ITEM(void)
0x180004990  mov     rcx, rsi; Block
0x180004993  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004998  jmp     short loc_180004932
```
