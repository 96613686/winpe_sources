# I_ReaderListAsyncProcessReader

- ea: `0x18000e888`
- end: `0x18000ec41`
- name: `I_ReaderListAsyncProcessReader`
- size: `953`
- prototype: `__int64 __fastcall(__int64, __int64, int, const void *, SIZE_T dwBytes)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180004900`

## callees

- `0x180004600`
- `0x18000db90`
- `0x18000e888`
- `0x180018b58`
- `0x180018bb4`
- `0x1800243f8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000ebdf`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000ebdf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000eb62`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000eb62`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e8fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e99d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ea2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ea94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e8fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e99d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ea2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ea94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eafa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ebd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eafa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ebd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb6d`

## pseudocode

```c
__int64 __fastcall I_ReaderListAsyncProcessReader(__int64 a1, __int64 a2, int a3, const void *a4, SIZE_T dwBytes)
{
  DWORD LastError; // ebx
  __int64 v9; // rcx
  LPVOID *v10; // r14
  STRSAFE_LPSTR v11; // rcx
  void *v12; // rbp
  __int64 v13; // r8
  wchar_t *v14; // rax
  __int64 v15; // rcx
  STRSAFE_LPSTR v16; // rcx
  __int64 v17; // rdx
  const wchar_t *v18; // r8
  __int64 v19; // rdx
  HANDLE v20; // rcx
  void *v21; // rax
  __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rcx
  void *v25; // rdi
  struct _TP_WORK *ThreadpoolWork; // rax
  __int64 v27; // rcx

  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 208, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  LastError = 8;
  v10 = (LPVOID *)HeapAlloc(hHeap, 8u, 0xF8u);
  if ( !v10 )
  {
    WppTraceIndent(v9, 2);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        209,
        &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent);
    }
    goto LABEL_46;
  }
  v12 = 0;
  if ( !*(_QWORD *)a2 )
  {
    LastError = 87;
LABEL_34:
    if ( *v10 )
      HeapFree(hHeap, 0, *v10);
    HeapFree(hHeap, 0, v10);
    if ( v12 )
      HeapFree(hHeap, 0, v12);
    goto LABEL_46;
  }
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v13) );
  v14 = (wchar_t *)HeapAlloc(hHeap, 8u, 2 * v13 + 2);
  *v10 = v14;
  if ( !v14 )
  {
    WppTraceIndent(v15, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[28] & 1) == 0
      || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
    {
      goto LABEL_34;
    }
    v17 = 210;
    goto LABEL_33;
  }
  v18 = *(const wchar_t **)a2;
  v19 = -1;
  do
    ++v19;
  while ( v18[v19] );
  if ( StringCchCopyW(v14, v19 + 1, v18) < 0 )
  {
    LastError = 122;
    goto LABEL_34;
  }
  v20 = hHeap;
  *((_DWORD *)v10 + 3) = *(_DWORD *)(a2 + 12);
  v21 = HeapAlloc(v20, 8u, (unsigned int)dwBytes);
  v12 = v21;
  if ( !v21 )
  {
    WppTraceIndent(v22, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[28] & 1) == 0
      || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
    {
      goto LABEL_34;
    }
    v17 = 211;
    goto LABEL_33;
  }
  memcpy_0(v21, a4, (unsigned int)dwBytes);
  v23 = HeapAlloc(hHeap, 8u, 0x28u);
  v25 = v23;
  if ( !v23 )
  {
    WppTraceIndent(v24, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[28] & 1) == 0
      || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
    {
      goto LABEL_34;
    }
    v17 = 212;
LABEL_33:
    WPP_SF_s(*((_QWORD *)v16 + 2), v17, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
    goto LABEL_34;
  }
  *v23 = a1;
  v23[1] = v10;
  *((_DWORD *)v23 + 4) = a3;
  v23[3] = v12;
  *((_DWORD *)v23 + 8) = dwBytes;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 384));
  ThreadpoolWork = CreateThreadpoolWork(
                     (PTP_WORK_CALLBACK)I_ReaderListReaderProcessingWorker,
                     v23,
                     (PTP_CALLBACK_ENVIRON)(a1 + 272));
  if ( ThreadpoolWork )
  {
    LastError = 0;
    SubmitThreadpoolWork(ThreadpoolWork);
  }
  else
  {
    LastError = GetLastError();
    WppTraceIndent(v27, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        213,
        (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent,
        LastError);
    }
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 384));
    HeapFree(hHeap, 0, v25);
  }
LABEL_46:
  WppTraceIndent(v11, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      214,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000e888  mov     [rsp+Src], r9
0x18000e88d  push    rbx
0x18000e88e  push    rbp
0x18000e88f  push    rsi
0x18000e890  push    rdi
0x18000e891  push    r12
0x18000e893  push    r13
0x18000e895  push    r14
0x18000e897  push    r15
0x18000e899  sub     rsp, 38h
0x18000e89d  mov     r15, rdx
0x18000e8a0  mov     r13d, r8d
0x18000e8a3  xor     edx, edx
0x18000e8a5  mov     rsi, rcx
0x18000e8a8  call    WppTraceIndent
0x18000e8ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8b4  lea     rax, WPP_GLOBAL_Control
0x18000e8bb  cmp     rcx, rax
0x18000e8be  jz      short loc_18000E8E8
0x18000e8c0  test    byte ptr [rcx+1Ch], 2
0x18000e8c4  jz      short loc_18000E8E8
0x18000e8c6  cmp     byte ptr [rcx+19h], 5
0x18000e8ca  jb      short loc_18000E8E8
0x18000e8cc  mov     r9, cs:WPP_pszIndent
0x18000e8d3  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000e8da  mov     rcx, [rcx+10h]
0x18000e8de  mov     edx, 0D0h
0x18000e8e3  call    WPP_SF_s
0x18000e8e8  mov     rcx, cs:hHeap; hHeap
0x18000e8ef  mov     ebx, 8
0x18000e8f4  mov     edx, ebx; dwFlags
0x18000e8f6  mov     r8d, 0F8h; dwBytes
0x18000e8fc  call    cs:__imp_HeapAlloc
0x18000e902  xor     r12d, r12d
0x18000e905  mov     r14, rax
0x18000e908  test    rax, rax
0x18000e90b  jnz     short loc_18000E961
0x18000e90d  lea     edx, [rbx-6]
0x18000e910  call    WppTraceIndent
0x18000e915  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e91c  lea     r15, WPP_GLOBAL_Control
0x18000e923  cmp     rcx, r15
0x18000e926  jz      loc_18000EBEC
0x18000e92c  test    byte ptr [rcx+1Ch], 1
0x18000e930  jz      loc_18000EBEC
0x18000e936  cmp     byte ptr [rcx+19h], 2
0x18000e93a  jb      loc_18000EBEC
0x18000e940  mov     r9, cs:WPP_pszIndent
0x18000e947  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000e94e  mov     rcx, [rcx+10h]
0x18000e952  mov     edx, 0D1h
0x18000e957  call    WPP_SF_s
0x18000e95c  jmp     loc_18000EBEC
0x18000e961  mov     rax, [r15]
0x18000e964  mov     rbp, r12
0x18000e967  mov     rdi, r12
0x18000e96a  test    rax, rax
0x18000e96d  jnz     short loc_18000E97E
0x18000e96f  lea     ebx, [rax+57h]
0x18000e972  lea     r15, WPP_GLOBAL_Control
0x18000e979  jmp     loc_18000EAE9
0x18000e97e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000e982  inc     r8
0x18000e985  cmp     [rax+r8*2], r12w
0x18000e98a  jnz     short loc_18000E982
0x18000e98c  mov     rcx, cs:hHeap; hHeap
0x18000e993  lea     r8, ds:2[r8*2]; dwBytes
0x18000e99b  mov     edx, ebx; dwFlags
0x18000e99d  call    cs:__imp_HeapAlloc
0x18000e9a3  mov     [r14], rax
0x18000e9a6  test    rax, rax
0x18000e9a9  jnz     short loc_18000E9E8
0x18000e9ab  lea     edx, [rax+2]
0x18000e9ae  call    WppTraceIndent
0x18000e9b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9ba  lea     r15, WPP_GLOBAL_Control
0x18000e9c1  cmp     rcx, r15
0x18000e9c4  jz      loc_18000EAE9
0x18000e9ca  test    byte ptr [rcx+1Ch], 1
0x18000e9ce  jz      loc_18000EAE9
0x18000e9d4  cmp     byte ptr [rcx+19h], 2
0x18000e9d8  jb      loc_18000EAE9
0x18000e9de  mov     edx, 0D2h
0x18000e9e3  jmp     loc_18000EAD2
0x18000e9e8  mov     r8, [r15]; pszSrc
0x18000e9eb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000e9ef  inc     rdx
0x18000e9f2  cmp     [r8+rdx*2], r12w
0x18000e9f7  jnz     short loc_18000E9EF
0x18000e9f9  inc     rdx; cchDest
0x18000e9fc  mov     rcx, rax; pszDest
0x18000e9ff  call    StringCchCopyW
0x18000ea04  test    eax, eax
0x18000ea06  jns     short loc_18000EA12
0x18000ea08  mov     ebx, 7Ah ; 'z'
0x18000ea0d  jmp     loc_18000E972
0x18000ea12  mov     eax, [r15+0Ch]
0x18000ea16  mov     edx, ebx; dwFlags
0x18000ea18  mov     r15d, dword ptr [rsp+78h+dwBytes]
0x18000ea20  mov     rcx, cs:hHeap; hHeap
0x18000ea27  mov     r8d, r15d; dwBytes
0x18000ea2a  mov     [r14+0Ch], eax
0x18000ea2e  call    cs:__imp_HeapAlloc
0x18000ea34  mov     rbp, rax
0x18000ea37  test    rax, rax
0x18000ea3a  jnz     short loc_18000EA72
0x18000ea3c  lea     edx, [rax+2]
0x18000ea3f  call    WppTraceIndent
0x18000ea44  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea4b  lea     r15, WPP_GLOBAL_Control
0x18000ea52  cmp     rcx, r15
0x18000ea55  jz      loc_18000EAE9
0x18000ea5b  test    byte ptr [rcx+1Ch], 1
0x18000ea5f  jz      loc_18000EAE9
0x18000ea65  cmp     byte ptr [rcx+19h], 2
0x18000ea69  jb      short loc_18000EAE9
0x18000ea6b  mov     edx, 0D3h
0x18000ea70  jmp     short loc_18000EAD2
0x18000ea72  mov     rdx, [rsp+78h+Src]; Src
0x18000ea7a  mov     r8, r15; Size
0x18000ea7d  mov     rcx, rbp; void *
0x18000ea80  call    memcpy_0
0x18000ea85  mov     rcx, cs:hHeap; hHeap
0x18000ea8c  mov     r8d, 28h ; '('; dwBytes
0x18000ea92  mov     edx, ebx; dwFlags
0x18000ea94  call    cs:__imp_HeapAlloc
0x18000ea9a  mov     rdi, rax
0x18000ea9d  test    rax, rax
0x18000eaa0  jnz     loc_18000EB37
0x18000eaa6  lea     edx, [rax+2]
0x18000eaa9  call    WppTraceIndent
0x18000eaae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eab5  lea     r15, WPP_GLOBAL_Control
0x18000eabc  cmp     rcx, r15
0x18000eabf  jz      short loc_18000EAE9
0x18000eac1  test    byte ptr [rcx+1Ch], 1
0x18000eac5  jz      short loc_18000EAE9
0x18000eac7  cmp     byte ptr [rcx+19h], 2
0x18000eacb  jb      short loc_18000EAE9
0x18000eacd  mov     edx, 0D4h
0x18000ead2  mov     r9, cs:WPP_pszIndent
0x18000ead9  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000eae0  mov     rcx, [rcx+10h]
0x18000eae4  call    WPP_SF_s
0x18000eae9  mov     r8, [r14]; lpMem
0x18000eaec  test    r8, r8
0x18000eaef  jz      short loc_18000EB00
0x18000eaf1  mov     rcx, cs:hHeap; hHeap
0x18000eaf8  xor     edx, edx; dwFlags
0x18000eafa  call    cs:__imp_HeapFree
0x18000eb00  mov     rcx, cs:hHeap; hHeap
0x18000eb07  mov     r8, r14; lpMem
0x18000eb0a  xor     edx, edx; dwFlags
0x18000eb0c  call    cs:__imp_HeapFree
0x18000eb12  test    rbp, rbp
0x18000eb15  jz      short loc_18000EB29
0x18000eb17  mov     rcx, cs:hHeap; hHeap
0x18000eb1e  mov     r8, rbp; lpMem
0x18000eb21  xor     edx, edx; dwFlags
0x18000eb23  call    cs:__imp_HeapFree
0x18000eb29  test    rdi, rdi
0x18000eb2c  jnz     loc_18000EBC5
0x18000eb32  jmp     loc_18000EBEC
0x18000eb37  mov     [rax], rsi
0x18000eb3a  mov     [rax+8], r14
0x18000eb3e  mov     [rax+10h], r13d
0x18000eb42  mov     [rax+18h], rbp
0x18000eb46  mov     [rax+20h], r15d
0x18000eb4a  lock inc dword ptr [rsi+180h]
0x18000eb51  lea     r8, [rsi+110h]; pcbe
0x18000eb58  mov     rdx, rax; pv
0x18000eb5b  lea     rcx, I_ReaderListReaderProcessingWorker; pfnwk
0x18000eb62  call    cs:__imp_CreateThreadpoolWork
0x18000eb68  test    rax, rax
0x18000eb6b  jnz     short loc_18000EBD9
0x18000eb6d  call    cs:__imp_GetLastError
0x18000eb73  mov     edx, 2
0x18000eb78  mov     ebx, eax
0x18000eb7a  call    WppTraceIndent
0x18000eb7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb86  lea     r15, WPP_GLOBAL_Control
0x18000eb8d  cmp     rcx, r15
0x18000eb90  jz      short loc_18000EBBE
0x18000eb92  test    byte ptr [rcx+1Ch], 1
0x18000eb96  jz      short loc_18000EBBE
0x18000eb98  cmp     byte ptr [rcx+19h], 3
0x18000eb9c  jb      short loc_18000EBBE
0x18000eb9e  mov     r9, cs:WPP_pszIndent
0x18000eba5  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000ebac  mov     rcx, [rcx+10h]
0x18000ebb0  mov     edx, 0D5h
0x18000ebb5  mov     [rsp+78h+var_58], ebx
0x18000ebb9  call    WPP_SF_sD
0x18000ebbe  lock dec dword ptr [rsi+180h]
0x18000ebc5  mov     rcx, cs:hHeap; hHeap
0x18000ebcc  mov     r8, rdi; lpMem
0x18000ebcf  xor     edx, edx; dwFlags
0x18000ebd1  call    cs:__imp_HeapFree
0x18000ebd7  jmp     short loc_18000EBEC
0x18000ebd9  mov     rcx, rax; pwk
0x18000ebdc  mov     ebx, r12d
0x18000ebdf  call    cs:__imp_SubmitThreadpoolWork
0x18000ebe5  lea     r15, WPP_GLOBAL_Control
0x18000ebec  mov     edx, 1
0x18000ebf1  call    WppTraceIndent
0x18000ebf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebfd  cmp     rcx, r15
0x18000ec00  jz      short loc_18000EC2E
0x18000ec02  test    byte ptr [rcx+1Ch], 2
0x18000ec06  jz      short loc_18000EC2E
0x18000ec08  cmp     byte ptr [rcx+19h], 5
0x18000ec0c  jb      short loc_18000EC2E
0x18000ec0e  mov     r9, cs:WPP_pszIndent
0x18000ec15  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000ec1c  mov     rcx, [rcx+10h]
0x18000ec20  mov     edx, 0D6h
0x18000ec25  mov     [rsp+78h+var_58], ebx
0x18000ec29  call    WPP_SF_sD
0x18000ec2e  mov     eax, ebx
0x18000ec30  add     rsp, 38h
0x18000ec34  pop     r15
0x18000ec36  pop     r14
0x18000ec38  pop     r13
0x18000ec3a  pop     r12
0x18000ec3c  pop     rdi
0x18000ec3d  pop     rsi
0x18000ec3e  pop     rbp
0x18000ec3f  pop     rbx
0x18000ec40  retn
```
