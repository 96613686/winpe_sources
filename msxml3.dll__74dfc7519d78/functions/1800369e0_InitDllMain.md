# InitDllMain

- ea: `0x1800369e0`
- end: `0x180036c76`
- name: `InitDllMain`
- size: `662`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x18002cf6c`
- `0x1800353d0`
- `0x1800369e0`
- `0x180036c7c`
- `0x180037ec4`
- `0x1800476c8`
- `0x180051d14`
- `0x180058c3c`
- `0x18005fe28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036b23`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036b23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036c02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036c1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036c57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036c6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036c02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036c1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036c57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036c6b`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180036c3c`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180036c3c`

## pseudocode

```c
BOOL __stdcall InitDllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  DWORD v4; // edx
  DWORD v5; // edx
  _BOOL8 v6; // rax
  int v7; // eax
  int v8; // r15d
  unsigned int v9; // edx
  TLSDATA *v10; // rcx
  LPVOID *v11; // rsi
  int v12; // edi
  void **v13; // rbx
  LPVOID *v14; // r14
  int v15; // ebp

  if ( fdwReason )
  {
    v4 = fdwReason - 1;
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( v5 )
      {
        if ( v5 != 1 )
          goto LABEL_6;
        if ( (unsigned int)DllMainCRTStartup(hinstDLL, 3u) )
        {
          DeleteTlsData();
          _InterlockedDecrement(&g_lThreadAttachedCount);
          goto LABEL_6;
        }
      }
      else if ( (unsigned int)DllMainCRTStartup(hinstDLL, 2u) )
      {
        _InterlockedAdd(&g_lThreadAttachedCount, 1u);
LABEL_6:
        LODWORD(v6) = 1;
        return v6;
      }
    }
    else if ( (unsigned int)Memory_init() )
    {
      if ( (unsigned int)DllMainCRTStartup(hinstDLL, 1u) )
      {
        if ( (unsigned int)Runtime_init(hinstDLL) )
        {
          g_nProcessAttachStatus = 4;
          goto LABEL_6;
        }
        g_nProcessAttachStatus = 3;
      }
      else
      {
        g_nProcessAttachStatus = 2;
      }
    }
    else
    {
      g_nProcessAttachStatus = 1;
    }
    LODWORD(v6) = 0;
    return v6;
  }
  if ( lpReserved )
  {
    g_fProcessShutdown = 1;
    goto LABEL_6;
  }
  v7 = g_nProcessAttachStatus;
  v8 = 1;
  if ( g_nProcessAttachStatus >= 3 )
  {
    Runtime_exit();
    v7 = g_nProcessAttachStatus;
  }
  if ( v7 >= 2 )
  {
    v8 = DllMainCRTStartup(hinstDLL, 0);
    v7 = g_nProcessAttachStatus;
  }
  if ( v7 >= 1 )
  {
    TlsClear();
    MpHeapExit();
    v13 = (void **)&level1;
    v12 = 0x10000;
    do
    {
      v11 = (LPVOID *)*v13;
      --v12;
      if ( *v13 )
      {
        *v13 = 0;
        v14 = v11 + 1;
        v15 = 0x8000;
        do
        {
          --v15;
          if ( *v14 )
            HeapFree(g_hProcessHeap, 0, *v14);
          ++v14;
        }
        while ( v15 );
        HeapFree(g_hProcessHeap, 0, v11);
      }
      ++v13;
    }
    while ( v12 );
    while ( 1 )
    {
      v10 = g_ptlsdata;
      if ( !g_ptlsdata )
        break;
      g_ptlsdata = (TLSDATA *)*((_QWORD *)g_ptlsdata + 5);
      TLSDATA::`scalar deleting destructor'(v10, v9);
    }
    if ( g_ptlsdataExtra )
    {
      TLSDATA::`scalar deleting destructor'(g_ptlsdataExtra, v9);
      g_ptlsdataExtra = 0;
    }
    if ( g_dwTlsIndex != -1 )
    {
      TlsFree(g_dwTlsIndex);
      g_dwTlsIndex = -1;
    }
    if ( lpMem )
      HeapFree(g_hProcessHeap, 0, lpMem);
    if ( qword_180170120 )
      HeapFree(g_hProcessHeap, 0, qword_180170120);
    qword_180170120 = 0;
    lpMem = 0;
    if ( failure_tracing::_fInitialized )
      DeleteCriticalSection(&failure_tracing::_cs);
  }
  return v8 != 0;
}

```

## disassembly

```asm
0x1800369e0  push    rbx
0x1800369e2  push    rbp
0x1800369e3  push    rsi
0x1800369e4  push    rdi
0x1800369e5  push    r13
0x1800369e7  push    r14
0x1800369e9  push    r15
0x1800369eb  sub     rsp, 20h
0x1800369ef  mov     rsi, r8
0x1800369f2  mov     rdi, rcx
0x1800369f5  mov     ebx, 1
0x1800369fa  test    edx, edx
0x1800369fc  jz      short loc_180036A56
0x1800369fe  sub     edx, ebx
0x180036a00  jz      loc_180036B4A
0x180036a06  sub     edx, ebx
0x180036a08  jnz     short loc_180036A32
0x180036a0a  lea     edx, [rbx+1]; fdwReason
0x180036a0d  call    _DllMainCRTStartup
0x180036a12  test    eax, eax
0x180036a14  jz      loc_180036B65
0x180036a1a  lock add cs:?g_lThreadAttachedCount@@3JA, ebx; long g_lThreadAttachedCount
0x180036a21  mov     eax, ebx
0x180036a23  add     rsp, 20h
0x180036a27  pop     r15
0x180036a29  pop     r14
0x180036a2b  pop     r13
0x180036a2d  pop     rdi
0x180036a2e  pop     rsi
0x180036a2f  pop     rbp
0x180036a30  pop     rbx
0x180036a31  retn
0x180036a32  cmp     edx, ebx
0x180036a34  jnz     short loc_180036A21
0x180036a36  mov     edx, 3; fdwReason
0x180036a3b  call    _DllMainCRTStartup
0x180036a40  test    eax, eax
0x180036a42  jz      loc_180036B65
0x180036a48  call    ?DeleteTlsData@@YAXXZ; DeleteTlsData(void)
0x180036a4d  lock dec cs:?g_lThreadAttachedCount@@3JA; long g_lThreadAttachedCount
0x180036a54  jmp     short loc_180036A21
0x180036a56  test    rsi, rsi
0x180036a59  jnz     loc_180036BA4
0x180036a5f  mov     eax, cs:?g_nProcessAttachStatus@@3JA; long g_nProcessAttachStatus
0x180036a65  mov     r15d, ebx
0x180036a68  cmp     eax, 3
0x180036a6b  jge     loc_180036BAF
0x180036a71  cmp     eax, 2
0x180036a74  jl      short loc_180036A8C
0x180036a76  xor     r8d, r8d
0x180036a79  xor     edx, edx; fdwReason
0x180036a7b  mov     rcx, rdi; hinstDLL
0x180036a7e  call    _DllMainCRTStartup
0x180036a83  mov     r15d, eax
0x180036a86  mov     eax, cs:?g_nProcessAttachStatus@@3JA; long g_nProcessAttachStatus
0x180036a8c  cmp     eax, ebx
0x180036a8e  jge     loc_180036BBF
0x180036a94  xor     eax, eax
0x180036a96  test    r15d, r15d
0x180036a99  setnz   al
0x180036a9c  jmp     short loc_180036A23
0x180036a9e  mov     rax, [rcx+28h]
0x180036aa2  mov     cs:?g_ptlsdata@@3PEAUTLSDATA@@EA, rax; TLSDATA * g_ptlsdata
0x180036aa9  call    ??_GTLSDATA@@QEAAPEAXI@Z; TLSDATA::`scalar deleting destructor'(uint)
0x180036aae  mov     rcx, cs:?g_ptlsdata@@3PEAUTLSDATA@@EA; this
0x180036ab5  test    rcx, rcx
0x180036ab8  jnz     short loc_180036A9E
0x180036aba  mov     rcx, cs:?g_ptlsdataExtra@@3PEAUTLSDATA@@EA; this
0x180036ac1  test    rcx, rcx
0x180036ac4  jnz     loc_180036C27
0x180036aca  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180036ad0  cmp     ecx, r13d
0x180036ad3  jnz     loc_180036C3C
0x180036ad9  mov     r8, cs:lpMem; lpMem
0x180036ae0  test    r8, r8
0x180036ae3  jnz     loc_180036C4E
0x180036ae9  mov     r8, cs:qword_180170120; lpMem
0x180036af0  test    r8, r8
0x180036af3  jnz     loc_180036C62
0x180036af9  cmp     cs:?_fInitialized@failure_tracing@@1_NA, 0; bool failure_tracing::_fInitialized
0x180036b00  mov     cs:qword_180170120, 0
0x180036b0b  mov     cs:lpMem, 0
0x180036b16  jz      loc_180036A94
0x180036b1c  lea     rcx, ?_cs@failure_tracing@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180036b23  call    cs:__imp_DeleteCriticalSection
0x180036b29  jmp     loc_180036A94
0x180036b2e  mov     rsi, [rbx]
0x180036b31  add     edi, r13d
0x180036b34  test    rsi, rsi
0x180036b37  jnz     loc_180036BDE
0x180036b3d  add     rbx, 8
0x180036b41  test    edi, edi
0x180036b43  jnz     short loc_180036B2E
0x180036b45  jmp     loc_180036AAE
0x180036b4a  call    Memory_init
0x180036b4f  test    eax, eax
0x180036b51  jnz     short loc_180036B6C
0x180036b53  mov     cs:?g_nProcessAttachStatus@@3JA, ebx; long g_nProcessAttachStatus
0x180036b59  jmp     short loc_180036B65
0x180036b5b  mov     cs:?g_nProcessAttachStatus@@3JA, 3; long g_nProcessAttachStatus
0x180036b65  xor     eax, eax
0x180036b67  jmp     loc_180036A23
0x180036b6c  mov     r8, rsi
0x180036b6f  mov     edx, ebx; fdwReason
0x180036b71  mov     rcx, rdi; hinstDLL
0x180036b74  call    _DllMainCRTStartup
0x180036b79  test    eax, eax
0x180036b7b  jnz     short loc_180036B89
0x180036b7d  mov     cs:?g_nProcessAttachStatus@@3JA, 2; long g_nProcessAttachStatus
0x180036b87  jmp     short loc_180036B65
0x180036b89  mov     rcx, rdi
0x180036b8c  call    Runtime_init
0x180036b91  test    eax, eax
0x180036b93  jz      short loc_180036B5B
0x180036b95  mov     cs:?g_nProcessAttachStatus@@3JA, 4; long g_nProcessAttachStatus
0x180036b9f  jmp     loc_180036A21
0x180036ba4  mov     cs:?g_fProcessShutdown@@3HA, ebx; int g_fProcessShutdown
0x180036baa  jmp     loc_180036A21
0x180036baf  call    Runtime_exit
0x180036bb4  mov     eax, cs:?g_nProcessAttachStatus@@3JA; long g_nProcessAttachStatus
0x180036bba  jmp     loc_180036A71
0x180036bbf  call    ?TlsClear@@YAXXZ; TlsClear(void)
0x180036bc4  call    ?MpHeapExit@@YAXXZ; MpHeapExit(void)
0x180036bc9  or      r13d, 0FFFFFFFFh
0x180036bcd  lea     rbx, ?level1@@3PAPEAULEVEL2@@A; LEVEL2 * near * level1
0x180036bd4  mov     edi, 10000h
0x180036bd9  jmp     loc_180036B2E
0x180036bde  mov     qword ptr [rbx], 0
0x180036be5  lea     r14, [rsi+8]
0x180036be9  mov     ebp, 8000h
0x180036bee  mov     r8, [r14]; lpMem
0x180036bf1  add     ebp, r13d
0x180036bf4  test    r8, r8
0x180036bf7  jz      short loc_180036C08
0x180036bf9  mov     rcx, cs:g_hProcessHeap; hHeap
0x180036c00  xor     edx, edx; dwFlags
0x180036c02  call    cs:__imp_HeapFree
0x180036c08  add     r14, 8
0x180036c0c  test    ebp, ebp
0x180036c0e  jnz     short loc_180036BEE
0x180036c10  mov     rcx, cs:g_hProcessHeap; hHeap
0x180036c17  mov     r8, rsi; lpMem
0x180036c1a  xor     edx, edx; dwFlags
0x180036c1c  call    cs:__imp_HeapFree
0x180036c22  jmp     loc_180036B3D
0x180036c27  call    ??_GTLSDATA@@QEAAPEAXI@Z; TLSDATA::`scalar deleting destructor'(uint)
0x180036c2c  mov     cs:?g_ptlsdataExtra@@3PEAUTLSDATA@@EA, 0; TLSDATA * g_ptlsdataExtra
0x180036c37  jmp     loc_180036ACA
0x180036c3c  call    cs:__imp_TlsFree
0x180036c42  mov     cs:?g_dwTlsIndex@@3KA, r13d; ulong g_dwTlsIndex
0x180036c49  jmp     loc_180036AD9
0x180036c4e  mov     rcx, cs:g_hProcessHeap; hHeap
0x180036c55  xor     edx, edx; dwFlags
0x180036c57  call    cs:__imp_HeapFree
0x180036c5d  jmp     loc_180036AE9
0x180036c62  mov     rcx, cs:g_hProcessHeap; hHeap
0x180036c69  xor     edx, edx; dwFlags
0x180036c6b  call    cs:__imp_HeapFree
0x180036c71  jmp     loc_180036AF9
```
