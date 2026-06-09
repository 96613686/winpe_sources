# ContextCacheCreate

- ea: `0x180082c98`
- end: `0x180082e2a`
- name: `ContextCacheCreate`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800834bc`

## callees

- `0x180014a60`
- `0x180082c98`
- `0x180082e30`
- `0x180083a68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082db8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082db8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180082cdf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180082d5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180082cdf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180082d5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082cca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082d4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082cca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082d4e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180082da6`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180082da6`
- `KERNEL32!CreateIoCompletionPort` at `0x180082d8b`
- `KERNEL32!CreateIoCompletionPort` at `0x180082d8b`

## pseudocode

```c
__int64 __fastcall ContextCacheCreate(__int64 a1, __int64 a2, const wchar_t *a3, _QWORD *a4)
{
  HANDLE ProcessHeap; // rax
  DWORD LastError; // edi
  _QWORD *v10; // rax
  _QWORD *v11; // rsi
  const wchar_t *v13; // rax
  __int64 v14; // rcx
  HRESULT v15; // ebp
  __int64 v16; // r8
  size_t v17; // r15
  SIZE_T v18; // rbx
  HANDLE v19; // rax
  wchar_t *v20; // rax
  HANDLE IoCompletionPort; // rax
  HANDLE MutexW; // rax
  __int64 v23; // rdx
  __int64 v24; // r8

  if ( a1 && a2 )
  {
    ProcessHeap = GetProcessHeap();
    LastError = 8;
    v10 = HeapAlloc(ProcessHeap, 8u, 0xC8u);
    v11 = v10;
    if ( !v10 )
      return LastError;
    *v10 = a1;
    v10[1] = a2;
    if ( a3 )
    {
      v13 = a3;
      v14 = 0x7FFFFFFF;
      do
      {
        if ( !*v13 )
          break;
        ++v13;
        --v14;
      }
      while ( v14 );
      v15 = v14 == 0 ? 0x80070057 : 0;
      v16 = (0x7FFFFFFF - v14) & -(__int64)(v14 != 0);
      if ( v14 )
      {
        v17 = v16 + 1;
        v18 = 2 * (v16 + 1);
        v19 = GetProcessHeap();
        v20 = (wchar_t *)HeapAlloc(v19, 0, v18);
        v11[15] = v20;
        if ( v20 )
        {
          v15 = StringCchCopyW(v20, v17, a3);
          if ( v15 >= 0 )
          {
            if ( (IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0),
                  (v11[4] = IoCompletionPort) != 0)
              && (LastError = 0, MutexW = CreateMutexW(0, 1, 0), (v11[16] = MutexW) != 0)
              || (LastError = GetLastError()) == 0 )
            {
              *a4 = v11;
              goto LABEL_18;
            }
          }
        }
      }
    }
    else
    {
      v15 = -2147024809;
    }
    ContextCacheDelete(v11);
LABEL_18:
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      WPP_SF_qdD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, v24, v11, LastError, v15);
    }
    return LastError;
  }
  return 50;
}

```

## disassembly

```asm
0x180082c98  push    rbx
0x180082c9a  push    rbp
0x180082c9b  push    rsi
0x180082c9c  push    rdi
0x180082c9d  push    r12
0x180082c9f  push    r13
0x180082ca1  push    r14
0x180082ca3  push    r15
0x180082ca5  sub     rsp, 38h
0x180082ca9  xor     r13d, r13d
0x180082cac  mov     r12, r9
0x180082caf  mov     r14, r8
0x180082cb2  mov     rbx, rdx
0x180082cb5  mov     rbp, rcx
0x180082cb8  test    rcx, rcx
0x180082cbb  jz      loc_180082E14
0x180082cc1  test    rdx, rdx
0x180082cc4  jz      loc_180082E14
0x180082cca  call    cs:__imp_GetProcessHeap
0x180082cd0  lea     edi, [r13+8]
0x180082cd4  mov     r8d, 0C8h; dwBytes
0x180082cda  mov     rcx, rax; hHeap
0x180082cdd  mov     edx, edi; dwFlags
0x180082cdf  call    cs:__imp_HeapAlloc
0x180082ce5  mov     rsi, rax
0x180082ce8  test    rax, rax
0x180082ceb  jnz     short loc_180082CF4
0x180082ced  mov     eax, edi
0x180082cef  jmp     loc_180082E19
0x180082cf4  mov     [rax], rbp
0x180082cf7  mov     [rax+8], rbx
0x180082cfb  test    r14, r14
0x180082cfe  jz      loc_180082DCA
0x180082d04  mov     edx, 7FFFFFFFh
0x180082d09  mov     rax, r14
0x180082d0c  mov     ecx, edx
0x180082d0e  cmp     [rax], r13w
0x180082d12  jz      short loc_180082D1E
0x180082d14  add     rax, 2
0x180082d18  sub     rcx, 1
0x180082d1c  jnz     short loc_180082D0E
0x180082d1e  mov     rax, rcx
0x180082d21  neg     rax
0x180082d24  mov     rax, rcx
0x180082d27  sbb     ebp, ebp
0x180082d29  sub     rdx, rcx
0x180082d2c  not     ebp
0x180082d2e  and     ebp, 80070057h
0x180082d34  neg     rax
0x180082d37  sbb     r8, r8
0x180082d3a  and     r8, rdx
0x180082d3d  test    rcx, rcx
0x180082d40  jz      loc_180082DCF
0x180082d46  lea     r15, [r8+1]
0x180082d4a  lea     rbx, [r15+r15]
0x180082d4e  call    cs:__imp_GetProcessHeap
0x180082d54  mov     r8, rbx; dwBytes
0x180082d57  xor     edx, edx; dwFlags
0x180082d59  mov     rcx, rax; hHeap
0x180082d5c  call    cs:__imp_HeapAlloc
0x180082d62  mov     [rsi+78h], rax
0x180082d66  test    rax, rax
0x180082d69  jz      short loc_180082DCF
0x180082d6b  mov     r8, r14; pszSrc
0x180082d6e  mov     rdx, r15; cchDest
0x180082d71  mov     rcx, rax; pszDest
0x180082d74  call    StringCchCopyW
0x180082d79  mov     ebp, eax
0x180082d7b  test    eax, eax
0x180082d7d  js      short loc_180082DCF
0x180082d7f  xor     r9d, r9d; NumberOfConcurrentThreads
0x180082d82  xor     r8d, r8d; CompletionKey
0x180082d85  xor     edx, edx; ExistingCompletionPort
0x180082d87  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x180082d8b  call    cs:__imp_CreateIoCompletionPort
0x180082d91  mov     [rsi+20h], rax
0x180082d95  test    rax, rax
0x180082d98  jz      short loc_180082DB8
0x180082d9a  xor     r8d, r8d; lpName
0x180082d9d  xor     ecx, ecx; lpMutexAttributes
0x180082d9f  mov     edi, r13d
0x180082da2  lea     edx, [r8+1]; bInitialOwner
0x180082da6  call    cs:__imp_CreateMutexW
0x180082dac  mov     [rsi+80h], rax
0x180082db3  test    rax, rax
0x180082db6  jnz     short loc_180082DC4
0x180082db8  call    cs:__imp_GetLastError
0x180082dbe  mov     edi, eax
0x180082dc0  test    eax, eax
0x180082dc2  jnz     short loc_180082DCF
0x180082dc4  mov     [r12], rsi
0x180082dc8  jmp     short loc_180082DD7
0x180082dca  mov     ebp, 80070057h
0x180082dcf  mov     rcx, rsi; lpMem
0x180082dd2  call    ContextCacheDelete
0x180082dd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180082dde  lea     rax, WPP_GLOBAL_Control
0x180082de5  cmp     rcx, rax
0x180082de8  jz      loc_180082CED
0x180082dee  test    dword ptr [rcx+1Ch], 10000000h
0x180082df5  jz      loc_180082CED
0x180082dfb  mov     rcx, [rcx+10h]
0x180082dff  mov     r9, rsi
0x180082e02  mov     [rsp+78h+var_50], ebp
0x180082e06  mov     [rsp+78h+var_58], edi
0x180082e0a  call    WPP_SF_qdD
0x180082e0f  jmp     loc_180082CED
0x180082e14  mov     eax, 32h ; '2'
0x180082e19  add     rsp, 38h
0x180082e1d  pop     r15
0x180082e1f  pop     r14
0x180082e21  pop     r13
0x180082e23  pop     r12
0x180082e25  pop     rdi
0x180082e26  pop     rsi
0x180082e27  pop     rbp
0x180082e28  pop     rbx
0x180082e29  retn
```
