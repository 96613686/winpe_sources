# FormatMsgToBufferW(STRU *,_DEBUG_PRINTS *,char const *,ulong,char const *,ushort const *,char * *)

- ea: `0x18000e650`
- end: `0x18000e8a4`
- name: `?FormatMsgToBufferW@@YAXPEAVSTRU@@PEAU_DEBUG_PRINTS@@PEBDK2PEBGPEAPEAD@Z`
- size: `596`
- prototype: `void __fastcall(wchar_t *const *, struct _DEBUG_PRINTS *, const char *, int, const char *, wchar_t *Format, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180020340`

## callees

- `0x18000e650`
- `0x18002e516`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000e6d6`
- `msvcrt!swprintf_s` at `0x18000e6d6`
- `msvcrt!strrchr` at `0x18000e671`
- `msvcrt!strrchr` at `0x18000e671`
- `msvcrt!_vsnwprintf_s` at `0x18000e71d`
- `msvcrt!_vsnwprintf_s` at `0x18000e84c`
- `msvcrt!_vsnwprintf_s` at `0x18000e71d`
- `msvcrt!_vsnwprintf_s` at `0x18000e84c`
- `msvcrt!wcsnlen` at `0x18000e741`
- `msvcrt!wcsnlen` at `0x18000e741`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e808`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e68c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e68c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e7e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e7e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e77d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e77d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7d2`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000e797`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000e797`

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
0x18000e650  push    rbx
0x18000e652  push    rbp
0x18000e653  push    rsi
0x18000e654  push    rdi
0x18000e655  push    r14
0x18000e657  push    r15
0x18000e659  sub     rsp, 48h
0x18000e65d  mov     rbp, rdx
0x18000e660  mov     rbx, rcx
0x18000e663  mov     edx, 5Ch ; '\'; Ch
0x18000e668  mov     rcx, r8; Str
0x18000e66b  mov     r14d, r9d
0x18000e66e  mov     rsi, r8
0x18000e671  call    cs:__imp_strrchr
0x18000e678  nop     dword ptr [rax+rax+00h]
0x18000e67d  mov     rdi, rax
0x18000e680  test    rax, rax
0x18000e683  jz      loc_18000E75E
0x18000e689  inc     rdi
0x18000e68c  call    cs:__imp_GetCurrentThreadId
0x18000e693  nop     dword ptr [rax+rax+00h]
0x18000e698  mov     edx, [rbx+28h]
0x18000e69b  lea     rcx, asc_180032BDC; "??"
0x18000e6a2  mov     [rsp+78h+var_40], r14d
0x18000e6a7  lea     r8, aLuHsHsHsD; "%lu %hs!%hs [%hs @ %d]:"
0x18000e6ae  mov     [rsp+78h+var_48], rdi
0x18000e6b3  test    rbp, rbp
0x18000e6b6  mov     r9d, eax
0x18000e6b9  cmovz   rbp, rcx
0x18000e6bd  mov     rcx, [rsp+78h+arg_20]
0x18000e6c5  mov     [rsp+78h+var_50], rcx
0x18000e6ca  mov     rcx, [rbx+20h]; Buffer
0x18000e6ce  shr     rdx, 1; BufferCount
0x18000e6d1  mov     [rsp+78h+ArgList], rbp
0x18000e6d6  call    cs:__imp_swprintf_s
0x18000e6dd  nop     dword ptr [rax+rax+00h]
0x18000e6e2  mov     ecx, [rbx+28h]
0x18000e6e5  mov     r15, [rsp+78h+arg_30]
0x18000e6ed  mov     r8d, ecx
0x18000e6f0  mov     rbp, [rsp+78h+Format]
0x18000e6f8  movsxd  rsi, eax
0x18000e6fb  mov     r9, rbp; Format
0x18000e6fe  mov     rax, [rbx+20h]
0x18000e702  shr     ecx, 1
0x18000e704  sub     ecx, esi
0x18000e706  shr     r8, 1
0x18000e709  mov     edx, ecx; BufferCount
0x18000e70b  sub     r8, rsi
0x18000e70e  lea     rcx, [rax+rsi*2]; Buffer
0x18000e712  dec     r8; MaxCount
0x18000e715  mov     rax, [r15]
0x18000e718  mov     [rsp+78h+ArgList], rax; ArgList
0x18000e71d  call    cs:__imp__vsnwprintf_s
0x18000e724  nop     dword ptr [rax+rax+00h]
0x18000e729  cmp     eax, 0FFFFFFFFh
0x18000e72c  jz      short loc_18000E766
0x18000e72e  mov     rcx, [rbx+20h]; Source
0x18000e732  test    rcx, rcx
0x18000e735  jz      loc_18000E891
0x18000e73b  mov     edx, [rbx+28h]
0x18000e73e  shr     rdx, 1; MaxCount
0x18000e741  call    cs:__imp_wcsnlen
0x18000e748  nop     dword ptr [rax+rax+00h]
0x18000e74d  mov     [rbx+30h], eax
0x18000e750  add     rsp, 48h
0x18000e754  pop     r15
0x18000e756  pop     r14
0x18000e758  pop     rdi
0x18000e759  pop     rsi
0x18000e75a  pop     rbp
0x18000e75b  pop     rbx
0x18000e75c  retn
0x18000e75e  mov     rdi, rsi
0x18000e761  jmp     loc_18000E68C
0x18000e766  cmp     dword ptr [rbx+28h], 2800h
0x18000e76d  jnb     loc_18000E824
0x18000e773  cmp     byte ptr [rbx+2Ch], 0
0x18000e777  jz      short loc_18000E7D2
0x18000e779  mov     rdi, [rbx+20h]
0x18000e77d  call    cs:__imp_GetProcessHeap
0x18000e784  nop     dword ptr [rax+rax+00h]
0x18000e789  mov     r9d, 2800h; dwBytes
0x18000e78f  mov     r8, rdi; lpMem
0x18000e792  mov     rcx, rax; hHeap
0x18000e795  xor     edx, edx; dwFlags
0x18000e797  call    cs:__imp_HeapReAlloc
0x18000e79e  nop     dword ptr [rax+rax+00h]
0x18000e7a3  mov     rdi, rax
0x18000e7a6  test    rax, rax
0x18000e7a9  jz      short loc_18000E7F7
0x18000e7ab  cmp     byte ptr [rbx+2Ch], 0
0x18000e7af  jnz     short loc_18000E7C5
0x18000e7b1  mov     r8d, [rbx+28h]; Size
0x18000e7b5  mov     rcx, rax; void *
0x18000e7b8  mov     rdx, [rbx+20h]; Src
0x18000e7bc  call    memcpy_0
0x18000e7c1  mov     byte ptr [rbx+2Ch], 1
0x18000e7c5  mov     [rbx+20h], rdi
0x18000e7c9  mov     dword ptr [rbx+28h], 2800h
0x18000e7d0  jmp     short loc_18000E824
0x18000e7d2  call    cs:__imp_GetProcessHeap
0x18000e7d9  nop     dword ptr [rax+rax+00h]
0x18000e7de  xor     edx, edx; dwFlags
0x18000e7e0  mov     r8d, 2800h; dwBytes
0x18000e7e6  mov     rcx, rax; hHeap
0x18000e7e9  call    cs:__imp_HeapAlloc
0x18000e7f0  nop     dword ptr [rax+rax+00h]
0x18000e7f5  jmp     short loc_18000E7A3
0x18000e7f7  mov     ecx, 8; dwErrCode
0x18000e7fc  call    cs:__imp_SetLastError
0x18000e803  nop     dword ptr [rax+rax+00h]
0x18000e808  call    cs:__imp_GetLastError
0x18000e80f  nop     dword ptr [rax+rax+00h]
0x18000e814  test    eax, eax
0x18000e816  jle     short loc_18000E822
0x18000e818  movzx   eax, ax
0x18000e81b  or      eax, 80070000h
0x18000e820  test    eax, eax
0x18000e822  js      short loc_18000E877
0x18000e824  mov     eax, [rbx+28h]
0x18000e827  mov     r9, rbp; Format
0x18000e82a  mov     r8d, eax
0x18000e82d  shr     eax, 1
0x18000e82f  sub     eax, esi
0x18000e831  shr     r8, 1
0x18000e834  mov     edx, eax; BufferCount
0x18000e836  sub     r8, rsi
0x18000e839  mov     rax, [rbx+20h]
0x18000e83d  dec     r8; MaxCount
0x18000e840  lea     rcx, [rax+rsi*2]; Buffer
0x18000e844  mov     rax, [r15]
0x18000e847  mov     [rsp+78h+ArgList], rax; ArgList
0x18000e84c  call    cs:__imp__vsnwprintf_s
0x18000e853  nop     dword ptr [rax+rax+00h]
0x18000e858  cmp     eax, 0FFFFFFFFh
0x18000e85b  jnz     loc_18000E72E
0x18000e861  mov     edx, [rbx+28h]
0x18000e864  mov     rcx, [rbx+20h]
0x18000e868  shr     rdx, 1
0x18000e86b  xor     eax, eax
0x18000e86d  mov     [rcx+rdx*2-2], ax
0x18000e872  jmp     loc_18000E72E
0x18000e877  mov     rcx, [rbx+20h]
0x18000e87b  xor     eax, eax
0x18000e87d  mov     [rcx], ax
0x18000e880  mov     [rbx+30h], eax
0x18000e883  add     rsp, 48h
0x18000e887  pop     r15
0x18000e889  pop     r14
0x18000e88b  pop     rdi
0x18000e88c  pop     rsi
0x18000e88d  pop     rbp
0x18000e88e  pop     rbx
0x18000e88f  retn
0x18000e891  xor     eax, eax
0x18000e893  mov     [rbx+30h], eax
0x18000e896  add     rsp, 48h
0x18000e89a  pop     r15
0x18000e89c  pop     r14
0x18000e89e  pop     rdi
0x18000e89f  pop     rsi
0x18000e8a0  pop     rbp
0x18000e8a1  pop     rbx
0x18000e8a2  retn
```
