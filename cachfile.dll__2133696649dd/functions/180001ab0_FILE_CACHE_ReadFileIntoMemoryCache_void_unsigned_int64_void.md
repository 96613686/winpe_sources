# FILE_CACHE::ReadFileIntoMemoryCache(void *,unsigned __int64,void * *)

- ea: `0x180001ab0`
- end: `0x180001cb2`
- name: `?ReadFileIntoMemoryCache@FILE_CACHE@@QEAAJPEAX_KPEAPEAX@Z`
- size: `514`
- prototype: `__int64 __fastcall(FILE_CACHE *this, void *, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001630`

## callees

- `0x180001ab0`
- `0x180001cc0`
- `0x180002550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001b23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001b23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001aec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001aec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001beb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001beb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001c9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001c9c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001b3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001b3d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180001ba4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180001ba4`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180001be1`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180001be1`

## pseudocode

```c
__int64 __fastcall FILE_CACHE::ReadFileIntoMemoryCache(FILE_CACHE *this, void *a2, unsigned __int64 a3, void **a4)
{
  char *v4; // rbp
  struct _RTL_CRITICAL_SECTION *v8; // rcx
  unsigned __int64 v9; // r8
  FILE_CACHE *v10; // rcx
  char *v11; // rax
  void *v12; // r12
  char *v13; // rdi
  char *i; // r15
  unsigned int v15; // ebx
  DWORD v16; // r8d
  signed int LastError; // eax
  signed int v18; // eax
  FILE_CACHE *v20; // rcx
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-58h] BYREF
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp+8h] BYREF
  int v23; // [rsp+94h] [rbp+Ch]
  void **v24; // [rsp+A8h] [rbp+20h]

  v24 = a4;
  v23 = HIDWORD(this);
  v4 = (char *)g_pFileCache;
  NumberOfBytesRead = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pFileCache + 72));
  v8 = (struct _RTL_CRITICAL_SECTION *)(v4 + 72);
  v9 = a3 + *((_QWORD *)v4 + 15);
  if ( v9 > *((_QWORD *)v4 + 14) )
  {
    LeaveCriticalSection(v8);
    return 2147942408LL;
  }
  else
  {
    ++*((_DWORD *)v4 + 36);
    *((_QWORD *)v4 + 15) = v9;
    LeaveCriticalSection(v8);
    FILE_CACHE::IncrementCacheSizePerfCounters(v10, a3);
    v11 = (char *)HeapAlloc(*((HANDLE *)v4 + 16), 0, a3);
    v12 = v11;
    if ( v11 )
    {
      v13 = 0;
      *a4 = v11;
      for ( i = v11; ; i += NumberOfBytesRead )
      {
        v15 = 0;
        if ( (unsigned __int64)v13 >= a3 )
          break;
        Overlapped.Pointer = v13;
        v16 = a3 - (_DWORD)v13;
        if ( a3 - (unsigned __int64)v13 > 0x10000000 )
          v16 = 0x10000000;
        NumberOfBytesRead = v16;
        if ( !ReadFile(a2, i, v16, &NumberOfBytesRead, &Overlapped) )
        {
          LastError = GetLastError();
          v15 = LastError;
          if ( LastError > 0 )
            v15 = (unsigned __int16)LastError | 0x80070000;
          if ( v15 != -2147023899 )
            goto LABEL_14;
          if ( !GetOverlappedResult(a2, &Overlapped, &NumberOfBytesRead, 1) )
          {
            v18 = GetLastError();
            v15 = v18;
            if ( v18 > 0 )
              v15 = (unsigned __int16)v18 | 0x80070000;
LABEL_14:
            if ( (v15 & 0x80000000) != 0 )
              goto LABEL_19;
            return v15;
          }
        }
        v13 += NumberOfBytesRead;
      }
    }
    else
    {
      v15 = -2147024888;
LABEL_19:
      *v24 = 0;
      EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 72));
      --*((_DWORD *)v4 + 36);
      *((_QWORD *)v4 + 15) -= a3;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 72));
      FILE_CACHE::DecrementCacheSizePerfCounters(v20, a3);
      if ( v12 )
        HeapFree(*((HANDLE *)v4 + 16), 0, v12);
    }
    return v15;
  }
}

```

## disassembly

```asm
0x180001ab0  mov     rax, rsp
0x180001ab3  mov     [rax+20h], r9
0x180001ab7  mov     [rax+8], rcx
0x180001abb  push    rbx
0x180001abc  push    rbp
0x180001abd  push    rsi
0x180001abe  push    r13
0x180001ac0  push    r14
0x180001ac2  sub     rsp, 60h
0x180001ac6  mov     rbp, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x180001acd  xorps   xmm0, xmm0
0x180001ad0  mov     rbx, r9
0x180001ad3  mov     dword ptr [rax+8], 0
0x180001ada  mov     rsi, r8
0x180001add  mov     r14, rdx
0x180001ae0  movups  xmmword ptr [rax-58h], xmm0
0x180001ae4  lea     rcx, [rbp+48h]; lpCriticalSection
0x180001ae8  movups  xmmword ptr [rax-48h], xmm0
0x180001aec  call    cs:__imp_EnterCriticalSection
0x180001af2  mov     r8, [rbp+78h]
0x180001af6  lea     rcx, [rbp+48h]; lpCriticalSection
0x180001afa  add     r8, rsi
0x180001afd  cmp     r8, [rbp+70h]
0x180001b01  ja      loc_180001C36
0x180001b07  inc     dword ptr [rbp+90h]
0x180001b0d  mov     [rsp+88h+arg_8], rdi
0x180001b15  mov     [rsp+88h+var_30], r12
0x180001b1a  mov     [rsp+88h+var_38], r15
0x180001b1f  mov     [rbp+78h], r8
0x180001b23  call    cs:__imp_LeaveCriticalSection
0x180001b29  mov     rdx, rsi; unsigned __int64
0x180001b2c  call    ?IncrementCacheSizePerfCounters@FILE_CACHE@@AEAAX_K@Z; FILE_CACHE::IncrementCacheSizePerfCounters(unsigned __int64)
0x180001b31  mov     rcx, [rbp+80h]; hHeap
0x180001b38  mov     r8, rsi; dwBytes
0x180001b3b  xor     edx, edx; dwFlags
0x180001b3d  call    cs:__imp_HeapAlloc
0x180001b43  mov     r12, rax
0x180001b46  test    rax, rax
0x180001b49  jz      loc_180001C4D
0x180001b4f  xor     edi, edi
0x180001b51  mov     [rbx], rax
0x180001b54  mov     r15, rax
0x180001b57  xor     ebx, ebx
0x180001b59  cmp     rdi, rsi
0x180001b5c  jnb     loc_180001C04
0x180001b62  mov     rax, rdi
0x180001b65  mov     dword ptr [rsp+88h+Overlapped.10h], edi
0x180001b69  shr     rax, 20h
0x180001b6d  mov     r8, rsi
0x180001b70  sub     r8, rdi; nNumberOfBytesToRead
0x180001b73  mov     dword ptr [rsp+88h+Overlapped.10h+4], eax
0x180001b77  cmp     r8, 10000000h
0x180001b7e  ja      loc_180001CA7
0x180001b84  lea     rax, [rsp+88h+Overlapped]
0x180001b89  mov     [rsp+88h+NumberOfBytesRead], r8d
0x180001b91  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180001b99  mov     [rsp+88h+lpOverlapped], rax; lpOverlapped
0x180001b9e  mov     rdx, r15; lpBuffer
0x180001ba1  mov     rcx, r14; hFile
0x180001ba4  call    cs:__imp_ReadFile
0x180001baa  test    eax, eax
0x180001bac  jnz     short loc_180001C24
0x180001bae  call    cs:__imp_GetLastError
0x180001bb4  mov     ebx, eax
0x180001bb6  test    eax, eax
0x180001bb8  jle     short loc_180001BC3
0x180001bba  movzx   ebx, ax
0x180001bbd  or      ebx, 80070000h
0x180001bc3  cmp     ebx, 800703E5h
0x180001bc9  jnz     short loc_180001C00
0x180001bcb  mov     r9d, 1; bWait
0x180001bd1  lea     r8, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x180001bd9  lea     rdx, [rsp+88h+Overlapped]; lpOverlapped
0x180001bde  mov     rcx, r14; hFile
0x180001be1  call    cs:__imp_GetOverlappedResult
0x180001be7  test    eax, eax
0x180001be9  jnz     short loc_180001C24
0x180001beb  call    cs:__imp_GetLastError
0x180001bf1  mov     ebx, eax
0x180001bf3  test    eax, eax
0x180001bf5  jle     short loc_180001C00
0x180001bf7  movzx   ebx, ax
0x180001bfa  or      ebx, 80070000h
0x180001c00  test    ebx, ebx
0x180001c02  js      short loc_180001C52
0x180001c04  mov     r15, [rsp+88h+var_38]
0x180001c09  mov     eax, ebx
0x180001c0b  mov     r12, [rsp+88h+var_30]
0x180001c10  mov     rdi, [rsp+88h+arg_8]
0x180001c18  add     rsp, 60h
0x180001c1c  pop     r14
0x180001c1e  pop     r13
0x180001c20  pop     rsi
0x180001c21  pop     rbp
0x180001c22  pop     rbx
0x180001c23  retn
0x180001c24  mov     eax, [rsp+88h+NumberOfBytesRead]
0x180001c2b  add     rdi, rax
0x180001c2e  add     r15, rax
0x180001c31  jmp     loc_180001B57
0x180001c36  call    cs:__imp_LeaveCriticalSection
0x180001c3c  mov     eax, 80070008h
0x180001c41  add     rsp, 60h
0x180001c45  pop     r14
0x180001c47  pop     r13
0x180001c49  pop     rsi
0x180001c4a  pop     rbp
0x180001c4b  pop     rbx
0x180001c4c  retn
0x180001c4d  mov     ebx, 80070008h
0x180001c52  mov     rax, [rsp+88h+arg_18]
0x180001c5a  lea     rcx, [rbp+48h]; lpCriticalSection
0x180001c5e  mov     qword ptr [rax], 0
0x180001c65  call    cs:__imp_EnterCriticalSection
0x180001c6b  dec     dword ptr [rbp+90h]
0x180001c71  lea     rcx, [rbp+48h]; lpCriticalSection
0x180001c75  sub     [rbp+78h], rsi
0x180001c79  call    cs:__imp_LeaveCriticalSection
0x180001c7f  mov     rdx, rsi; unsigned __int64
0x180001c82  call    ?DecrementCacheSizePerfCounters@FILE_CACHE@@AEAAX_K@Z; FILE_CACHE::DecrementCacheSizePerfCounters(unsigned __int64)
0x180001c87  test    r12, r12
0x180001c8a  jz      loc_180001C04
0x180001c90  mov     rcx, [rbp+80h]; hHeap
0x180001c97  mov     r8, r12; lpMem
0x180001c9a  xor     edx, edx; dwFlags
0x180001c9c  call    cs:__imp_HeapFree
0x180001ca2  jmp     loc_180001C04
0x180001ca7  mov     r8d, 10000000h
0x180001cad  jmp     loc_180001B84
```
