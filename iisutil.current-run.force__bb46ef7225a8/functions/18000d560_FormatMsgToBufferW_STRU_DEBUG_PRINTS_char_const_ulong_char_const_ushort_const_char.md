# FormatMsgToBufferW(STRU *,_DEBUG_PRINTS *,char const *,ulong,char const *,ushort const *,char * *)

- ea: `0x18000d560`
- end: `0x18000d769`
- name: `?FormatMsgToBufferW@@YAXPEAVSTRU@@PEAU_DEBUG_PRINTS@@PEBDK2PEBGPEAPEAD@Z`
- size: `521`
- prototype: `void(struct STRU *, struct _DEBUG_PRINTS *, const char *, unsigned int, const char *, const unsigned __int16 *, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f0d0`

## callees

- `0x18000d560`
- `0x18002c476`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000d5da`
- `msvcrt!swprintf_s` at `0x18000d5da`
- `msvcrt!strrchr` at `0x18000d581`
- `msvcrt!strrchr` at `0x18000d581`
- `msvcrt!_vsnwprintf_s` at `0x18000d61b`
- `msvcrt!_vsnwprintf_s` at `0x18000d719`
- `msvcrt!_vsnwprintf_s` at `0x18000d61b`
- `msvcrt!_vsnwprintf_s` at `0x18000d719`
- `msvcrt!wcsnlen` at `0x18000d639`
- `msvcrt!wcsnlen` at `0x18000d639`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d596`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d596`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d6c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d6c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d66e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d6b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d66e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d6b7`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000d682`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000d682`

## pseudocode

```c
void __fastcall FormatMsgToBufferW(
        wchar_t *const *a1,
        struct _DEBUG_PRINTS *a2,
        const char *a3,
        int a4,
        const char *a5,
        wchar_t *Format,
        char **a7)
{
  char *v11; // rax
  const char *v12; // rdi
  DWORD CurrentThreadId; // eax
  int v14; // eax
  __int64 v15; // rsi
  const wchar_t *v16; // rcx
  void *v17; // rdi
  HANDLE ProcessHeap; // rax
  void *v19; // rax
  void *v20; // rdi
  HANDLE v21; // rax
  signed int LastError; // eax
  bool v23; // sf

  v11 = strrchr(a3, 92);
  if ( v11 )
    v12 = v11 + 1;
  else
    v12 = a3;
  CurrentThreadId = GetCurrentThreadId();
  if ( !a2 )
    a2 = (struct _DEBUG_PRINTS *)"??";
  v14 = swprintf_s(
          a1[4],
          (unsigned __int64)*((unsigned int *)a1 + 10) >> 1,
          L"%lu %hs!%hs [%hs @ %d]:",
          CurrentThreadId,
          a2,
          a5,
          v12,
          a4);
  v15 = v14;
  if ( _vsnwprintf_s(
         (wchar_t *const)(*((_QWORD *)a1 + 4) + 2LL * v14),
         (unsigned int)((*((_DWORD *)a1 + 10) >> 1) - v14),
         ((unsigned __int64)*((unsigned int *)a1 + 10) >> 1) - v14 - 1,
         Format,
         *a7) == -1 )
  {
    if ( *((_DWORD *)a1 + 10) < 0x2800u )
    {
      if ( *((_BYTE *)a1 + 44) )
      {
        v17 = (void *)*((_QWORD *)a1 + 4);
        ProcessHeap = GetProcessHeap();
        v19 = HeapReAlloc(ProcessHeap, 0, v17, 0x2800u);
      }
      else
      {
        v21 = GetProcessHeap();
        v19 = HeapAlloc(v21, 0, 0x2800u);
      }
      v20 = v19;
      if ( v19 )
      {
        if ( !*((_BYTE *)a1 + 44) )
        {
          memcpy_0(v19, *((const void **)a1 + 4), *((unsigned int *)a1 + 10));
          *((_BYTE *)a1 + 44) = 1;
        }
        *((_QWORD *)a1 + 4) = v20;
        *((_DWORD *)a1 + 10) = 10240;
      }
      else
      {
        SetLastError(8u);
        LastError = GetLastError();
        v23 = LastError < 0;
        if ( LastError > 0 )
          v23 = 1;
        if ( v23 )
        {
          *a1[4] = 0;
          *((_DWORD *)a1 + 12) = 0;
          return;
        }
      }
    }
    if ( _vsnwprintf_s(
           (wchar_t *const)(*((_QWORD *)a1 + 4) + 2 * v15),
           (unsigned int)((*((_DWORD *)a1 + 10) >> 1) - v15),
           ((unsigned __int64)*((unsigned int *)a1 + 10) >> 1) - v15 - 1,
           Format,
           *a7) == -1 )
      *(_WORD *)(*((_QWORD *)a1 + 4) + 2 * ((unsigned __int64)*((unsigned int *)a1 + 10) >> 1) - 2) = 0;
  }
  v16 = (const wchar_t *)*((_QWORD *)a1 + 4);
  if ( v16 )
    *((_DWORD *)a1 + 12) = wcsnlen(v16, (unsigned __int64)*((unsigned int *)a1 + 10) >> 1);
  else
    *((_DWORD *)a1 + 12) = 0;
}

```

## disassembly

```asm
0x18000d560  push    rbx
0x18000d562  push    rbp
0x18000d563  push    rsi
0x18000d564  push    rdi
0x18000d565  push    r14
0x18000d567  push    r15
0x18000d569  sub     rsp, 48h
0x18000d56d  mov     rbp, rdx
0x18000d570  mov     rbx, rcx
0x18000d573  mov     edx, 5Ch ; '\'; Ch
0x18000d578  mov     rcx, r8; Str
0x18000d57b  mov     r14d, r9d
0x18000d57e  mov     rsi, r8
0x18000d581  call    cs:__imp_strrchr
0x18000d587  mov     rdi, rax
0x18000d58a  test    rax, rax
0x18000d58d  jz      loc_18000D64F
0x18000d593  inc     rdi
0x18000d596  call    cs:__imp_GetCurrentThreadId
0x18000d59c  mov     edx, [rbx+28h]
0x18000d59f  lea     rcx, asc_180030BCC; "??"
0x18000d5a6  mov     [rsp+78h+var_40], r14d
0x18000d5ab  lea     r8, aLuHsHsHsD; "%lu %hs!%hs [%hs @ %d]:"
0x18000d5b2  mov     [rsp+78h+var_48], rdi
0x18000d5b7  test    rbp, rbp
0x18000d5ba  mov     r9d, eax
0x18000d5bd  cmovz   rbp, rcx
0x18000d5c1  mov     rcx, [rsp+78h+arg_20]
0x18000d5c9  mov     [rsp+78h+var_50], rcx
0x18000d5ce  mov     rcx, [rbx+20h]; Buffer
0x18000d5d2  shr     rdx, 1; BufferCount
0x18000d5d5  mov     [rsp+78h+ArgList], rbp
0x18000d5da  call    cs:__imp_swprintf_s
0x18000d5e0  mov     ecx, [rbx+28h]
0x18000d5e3  mov     r15, [rsp+78h+arg_30]
0x18000d5eb  mov     r8d, ecx
0x18000d5ee  mov     rbp, [rsp+78h+Format]
0x18000d5f6  movsxd  rsi, eax
0x18000d5f9  mov     r9, rbp; Format
0x18000d5fc  mov     rax, [rbx+20h]
0x18000d600  shr     ecx, 1
0x18000d602  sub     ecx, esi
0x18000d604  shr     r8, 1
0x18000d607  mov     edx, ecx; BufferCount
0x18000d609  sub     r8, rsi
0x18000d60c  lea     rcx, [rax+rsi*2]; Buffer
0x18000d610  dec     r8; MaxCount
0x18000d613  mov     rax, [r15]
0x18000d616  mov     [rsp+78h+ArgList], rax; ArgList
0x18000d61b  call    cs:__imp__vsnwprintf_s
0x18000d621  cmp     eax, 0FFFFFFFFh
0x18000d624  jz      short loc_18000D657
0x18000d626  mov     rcx, [rbx+20h]; Source
0x18000d62a  test    rcx, rcx
0x18000d62d  jz      loc_18000D757
0x18000d633  mov     edx, [rbx+28h]
0x18000d636  shr     rdx, 1; MaxCount
0x18000d639  call    cs:__imp_wcsnlen
0x18000d63f  mov     [rbx+30h], eax
0x18000d642  add     rsp, 48h
0x18000d646  pop     r15
0x18000d648  pop     r14
0x18000d64a  pop     rdi
0x18000d64b  pop     rsi
0x18000d64c  pop     rbp
0x18000d64d  pop     rbx
0x18000d64e  retn
0x18000d64f  mov     rdi, rsi
0x18000d652  jmp     loc_18000D596
0x18000d657  cmp     dword ptr [rbx+28h], 2800h
0x18000d65e  jnb     loc_18000D6F1
0x18000d664  cmp     byte ptr [rbx+2Ch], 0
0x18000d668  jz      short loc_18000D6B7
0x18000d66a  mov     rdi, [rbx+20h]
0x18000d66e  call    cs:__imp_GetProcessHeap
0x18000d674  mov     r9d, 2800h; dwBytes
0x18000d67a  mov     r8, rdi; lpMem
0x18000d67d  mov     rcx, rax; hHeap
0x18000d680  xor     edx, edx; dwFlags
0x18000d682  call    cs:__imp_HeapReAlloc
0x18000d688  mov     rdi, rax
0x18000d68b  test    rax, rax
0x18000d68e  jz      short loc_18000D6D0
0x18000d690  cmp     byte ptr [rbx+2Ch], 0
0x18000d694  jnz     short loc_18000D6AA
0x18000d696  mov     r8d, [rbx+28h]; Size
0x18000d69a  mov     rcx, rax; void *
0x18000d69d  mov     rdx, [rbx+20h]; Src
0x18000d6a1  call    memcpy_0
0x18000d6a6  mov     byte ptr [rbx+2Ch], 1
0x18000d6aa  mov     [rbx+20h], rdi
0x18000d6ae  mov     dword ptr [rbx+28h], 2800h
0x18000d6b5  jmp     short loc_18000D6F1
0x18000d6b7  call    cs:__imp_GetProcessHeap
0x18000d6bd  xor     edx, edx; dwFlags
0x18000d6bf  mov     r8d, 2800h; dwBytes
0x18000d6c5  mov     rcx, rax; hHeap
0x18000d6c8  call    cs:__imp_HeapAlloc
0x18000d6ce  jmp     short loc_18000D688
0x18000d6d0  mov     ecx, 8; dwErrCode
0x18000d6d5  call    cs:__imp_SetLastError
0x18000d6db  call    cs:__imp_GetLastError
0x18000d6e1  test    eax, eax
0x18000d6e3  jle     short loc_18000D6EF
0x18000d6e5  movzx   eax, ax
0x18000d6e8  or      eax, 80070000h
0x18000d6ed  test    eax, eax
0x18000d6ef  js      short loc_18000D73E
0x18000d6f1  mov     eax, [rbx+28h]
0x18000d6f4  mov     r9, rbp; Format
0x18000d6f7  mov     r8d, eax
0x18000d6fa  shr     eax, 1
0x18000d6fc  sub     eax, esi
0x18000d6fe  shr     r8, 1
0x18000d701  mov     edx, eax; BufferCount
0x18000d703  sub     r8, rsi
0x18000d706  mov     rax, [rbx+20h]
0x18000d70a  dec     r8; MaxCount
0x18000d70d  lea     rcx, [rax+rsi*2]; Buffer
0x18000d711  mov     rax, [r15]
0x18000d714  mov     [rsp+78h+ArgList], rax; ArgList
0x18000d719  call    cs:__imp__vsnwprintf_s
0x18000d71f  cmp     eax, 0FFFFFFFFh
0x18000d722  jnz     loc_18000D626
0x18000d728  mov     edx, [rbx+28h]
0x18000d72b  mov     rcx, [rbx+20h]
0x18000d72f  shr     rdx, 1
0x18000d732  xor     eax, eax
0x18000d734  mov     [rcx+rdx*2-2], ax
0x18000d739  jmp     loc_18000D626
0x18000d73e  mov     rcx, [rbx+20h]
0x18000d742  xor     eax, eax
0x18000d744  mov     [rcx], ax
0x18000d747  mov     [rbx+30h], eax
0x18000d74a  add     rsp, 48h
0x18000d74e  pop     r15
0x18000d750  pop     r14
0x18000d752  pop     rdi
0x18000d753  pop     rsi
0x18000d754  pop     rbp
0x18000d755  pop     rbx
0x18000d756  retn
0x18000d757  xor     eax, eax
0x18000d759  mov     [rbx+30h], eax
0x18000d75c  add     rsp, 48h
0x18000d760  pop     r15
0x18000d762  pop     r14
0x18000d764  pop     rdi
0x18000d765  pop     rsi
0x18000d766  pop     rbp
0x18000d767  pop     rbx
0x18000d768  retn
```
