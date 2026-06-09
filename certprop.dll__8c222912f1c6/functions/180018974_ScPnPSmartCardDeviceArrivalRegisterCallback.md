# ScPnPSmartCardDeviceArrivalRegisterCallback

- ea: `0x180018974`
- end: `0x180018b52`
- name: `ScPnPSmartCardDeviceArrivalRegisterCallback`
- size: `478`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000aa00`

## callees

- `0x180004600`
- `0x18000db90`
- `0x180018974`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180018b3f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180018b3f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180018afa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180018afa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018994`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018a1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018994`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018a1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018b1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018b34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018b1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b05`

## pseudocode

```c
__int64 __fastcall ScPnPSmartCardDeviceArrivalRegisterCallback(STRSAFE_LPCWSTR pszSrc)
{
  DWORD LastError; // ebx
  __int64 v3; // rcx
  LPVOID *v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // r8
  wchar_t *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  struct _TP_WORK *ThreadpoolWork; // rax

  LastError = 8;
  v4 = (LPVOID *)HeapAlloc(g_hHeap, 8u, 0x18u);
  if ( !v4 )
  {
    WppTraceIndent(v3, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids, WPP_pszIndent);
    }
    goto LABEL_22;
  }
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( pszSrc[v6] );
  v7 = (wchar_t *)HeapAlloc(g_hHeap, 8u, 2 * v6 + 2);
  *v4 = v7;
  if ( !v7 )
  {
    WppTraceIndent(v8, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids, WPP_pszIndent);
    }
LABEL_21:
    HeapFree(g_hHeap, 0, v4);
LABEL_22:
    if ( *v4 )
      HeapFree(g_hHeap, 0, *v4);
    return LastError;
  }
  do
    ++v5;
  while ( pszSrc[v5] );
  LastError = StringCchCopyW(v7, v5 + 1, pszSrc);
  if ( LastError )
  {
    WppTraceIndent(v9, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
        WPP_pszIndent,
        LastError);
    }
    goto LABEL_21;
  }
  ThreadpoolWork = CreateThreadpoolWork(ScPnPSmartCardDeviceArrival, v4, &g_TpEnvironment);
  if ( ThreadpoolWork )
  {
    SubmitThreadpoolWork(ThreadpoolWork);
    return LastError;
  }
  LastError = GetLastError();
  if ( LastError )
    goto LABEL_21;
  return LastError;
}

```

## disassembly

```asm
0x180018974  push    rbx
0x180018976  push    rbp
0x180018977  push    rsi
0x180018978  push    rdi
0x180018979  push    r14
0x18001897b  sub     rsp, 30h
0x18001897f  mov     ebx, 8
0x180018984  mov     rbp, rcx
0x180018987  mov     rcx, cs:g_hHeap; hHeap
0x18001898e  mov     edx, ebx; dwFlags
0x180018990  lea     r8d, [rbx+10h]; dwBytes
0x180018994  call    cs:__imp_HeapAlloc
0x18001899a  xor     r14d, r14d
0x18001899d  mov     rsi, rax
0x1800189a0  test    rax, rax
0x1800189a3  jnz     short loc_1800189F9
0x1800189a5  lea     edx, [rbx-6]
0x1800189a8  call    WppTraceIndent
0x1800189ad  mov     r10, cs:WPP_GLOBAL_Control
0x1800189b4  lea     rcx, WPP_GLOBAL_Control
0x1800189bb  cmp     r10, rcx
0x1800189be  jz      loc_180018B23
0x1800189c4  test    byte ptr [r10+1Ch], 1
0x1800189c9  jz      loc_180018B23
0x1800189cf  cmp     byte ptr [r10+19h], 2
0x1800189d4  jb      loc_180018B23
0x1800189da  mov     r9, cs:WPP_pszIndent
0x1800189e1  lea     edx, [rbx+3Eh]
0x1800189e4  mov     rcx, [r10+10h]
0x1800189e8  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x1800189ef  call    WPP_SF_s
0x1800189f4  jmp     loc_180018B23
0x1800189f9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800189fd  mov     r8, rdi
0x180018a00  inc     r8
0x180018a03  cmp     [rbp+r8*2+0], r14w
0x180018a09  jnz     short loc_180018A00
0x180018a0b  mov     rcx, cs:g_hHeap; hHeap
0x180018a12  lea     r8, ds:2[r8*2]; dwBytes
0x180018a1a  mov     edx, ebx; dwFlags
0x180018a1c  call    cs:__imp_HeapAlloc
0x180018a22  mov     [rsi], rax
0x180018a25  test    rax, rax
0x180018a28  jnz     short loc_180018A7E
0x180018a2a  lea     edx, [rax+2]
0x180018a2d  call    WppTraceIndent
0x180018a32  mov     rax, cs:WPP_GLOBAL_Control
0x180018a39  lea     rcx, WPP_GLOBAL_Control
0x180018a40  cmp     rax, rcx
0x180018a43  jz      loc_180018B11
0x180018a49  test    byte ptr [rax+1Ch], 1
0x180018a4d  jz      loc_180018B11
0x180018a53  cmp     byte ptr [rax+19h], 2
0x180018a57  jb      loc_180018B11
0x180018a5d  mov     r9, cs:WPP_pszIndent
0x180018a64  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180018a6b  mov     rcx, [rax+10h]
0x180018a6f  mov     edx, 47h ; 'G'
0x180018a74  call    WPP_SF_s
0x180018a79  jmp     loc_180018B11
0x180018a7e  inc     rdi
0x180018a81  cmp     [rbp+rdi*2+0], r14w
0x180018a87  jnz     short loc_180018A7E
0x180018a89  lea     rdx, [rdi+1]; cchDest
0x180018a8d  mov     r8, rbp; pszSrc
0x180018a90  mov     rcx, rax; pszDest
0x180018a93  call    StringCchCopyW
0x180018a98  mov     ebx, eax
0x180018a9a  test    eax, eax
0x180018a9c  jz      short loc_180018AE9
0x180018a9e  mov     edx, 2
0x180018aa3  call    WppTraceIndent
0x180018aa8  mov     rax, cs:WPP_GLOBAL_Control
0x180018aaf  lea     rcx, WPP_GLOBAL_Control
0x180018ab6  cmp     rax, rcx
0x180018ab9  jz      short loc_180018B11
0x180018abb  test    byte ptr [rax+1Ch], 1
0x180018abf  jz      short loc_180018B11
0x180018ac1  cmp     byte ptr [rax+19h], 2
0x180018ac5  jb      short loc_180018B11
0x180018ac7  mov     r9, cs:WPP_pszIndent
0x180018ace  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180018ad5  mov     rcx, [rax+10h]
0x180018ad9  mov     edx, 48h ; 'H'
0x180018ade  mov     [rsp+58h+var_38], ebx
0x180018ae2  call    WPP_SF_sD
0x180018ae7  jmp     short loc_180018B11
0x180018ae9  lea     r8, g_TpEnvironment; pcbe
0x180018af0  mov     rdx, rsi; pv
0x180018af3  lea     rcx, ScPnPSmartCardDeviceArrival; pfnwk
0x180018afa  call    cs:__imp_CreateThreadpoolWork
0x180018b00  test    rax, rax
0x180018b03  jnz     short loc_180018B3C
0x180018b05  call    cs:__imp_GetLastError
0x180018b0b  mov     ebx, eax
0x180018b0d  test    eax, eax
0x180018b0f  jz      short loc_180018B45
0x180018b11  mov     rcx, cs:g_hHeap; hHeap
0x180018b18  mov     r8, rsi; lpMem
0x180018b1b  xor     edx, edx; dwFlags
0x180018b1d  call    cs:__imp_HeapFree
0x180018b23  mov     r8, [rsi]; lpMem
0x180018b26  test    r8, r8
0x180018b29  jz      short loc_180018B45
0x180018b2b  mov     rcx, cs:g_hHeap; hHeap
0x180018b32  xor     edx, edx; dwFlags
0x180018b34  call    cs:__imp_HeapFree
0x180018b3a  jmp     short loc_180018B45
0x180018b3c  mov     rcx, rax; pwk
0x180018b3f  call    cs:__imp_SubmitThreadpoolWork
0x180018b45  mov     eax, ebx
0x180018b47  add     rsp, 30h
0x180018b4b  pop     r14
0x180018b4d  pop     rdi
0x180018b4e  pop     rsi
0x180018b4f  pop     rbp
0x180018b50  pop     rbx
0x180018b51  retn
```
