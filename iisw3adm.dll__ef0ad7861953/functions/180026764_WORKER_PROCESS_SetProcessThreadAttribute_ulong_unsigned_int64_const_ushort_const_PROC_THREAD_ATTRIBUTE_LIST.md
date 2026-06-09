# WORKER_PROCESS::SetProcessThreadAttribute(ulong,unsigned __int64 * const,ushort * * const,_PROC_THREAD_ATTRIBUTE_LIST * *)

- ea: `0x180026764`
- end: `0x180026974`
- name: `?SetProcessThreadAttribute@WORKER_PROCESS@@AEAAJKQEA_KQEAPEAGPEAPEAU_PROC_THREAD_ATTRIBUTE_LIST@@@Z`
- size: `528`
- prototype: `__int64 __fastcall(WORKER_PROCESS *__hidden this, unsigned int, unsigned __int64 *const, unsigned __int16 **const, struct _PROC_THREAD_ATTRIBUTE_LIST **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180027008`

## callees

- `0x180026764`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002682c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002682c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026918`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180026905`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180026905`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180026793`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180026856`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180026793`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180026856`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002681e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002681e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800268ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800268ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002680d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800268ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002680d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800268ac`
- `iisutil!PuDbgPrintError` at `0x1800267fa`
- `iisutil!PuDbgPrintError` at `0x1800268a6`
- `iisutil!PuDbgPrintError` at `0x18002695e`
- `iisutil!PuDbgPrintError` at `0x1800267fa`
- `iisutil!PuDbgPrintError` at `0x1800268a6`
- `iisutil!PuDbgPrintError` at `0x18002695e`

## string_xrefs

- `0x1800267f3`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x18002689f`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180026957`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x18002693a`: `Failed UpdateProcThreadAttribute()\n`
- `0x180026946`: `WORKER_PROCESS::SetProcessThreadAttribute`
- `0x1800267d6`: `Failed to InitializeProcThreadAttributeList().\n`
- `0x180026882`: `Failed to InitializeProcThreadAttributeList().\n`
- `0x1800267e2`: `WORKER_PROCESS::InitializeProcThreadAttribList`
- `0x18002688e`: `WORKER_PROCESS::InitializeProcThreadAttribList`

## pseudocode

```c
__int64 __fastcall WORKER_PROCESS::SetProcessThreadAttribute(
        WORKER_PROCESS *this,
        __int64 a2,
        unsigned __int64 *const a3,
        unsigned __int16 **const a4,
        struct _PROC_THREAD_ATTRIBUTE_LIST **a5)
{
  BOOL v7; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST **v8; // rsi
  signed int LastError; // eax
  unsigned int v10; // ebx
  SIZE_T v11; // rbx
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v13; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v14; // rdi
  signed int v15; // eax
  signed int v16; // eax
  HANDLE v17; // rax
  __int64 v18; // rdi
  signed int v19; // eax
  SIZE_T dwBytes; // [rsp+80h] [rbp+8h] BYREF

  dwBytes = 0;
  v7 = InitializeProcThreadAttributeList(0, 1u, 0, &dwBytes);
  v8 = a5;
  if ( !v7 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
          9431,
          "WORKER_PROCESS::InitializeProcThreadAttribList",
          v10,
          "Failed to InitializeProcThreadAttributeList().\n");
      goto LABEL_16;
    }
  }
  v11 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v13 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)HeapAlloc(ProcessHeap, 8u, v11);
  v14 = v13;
  if ( !v13 )
  {
    v15 = GetLastError();
    v10 = v15;
    if ( v15 > 0 )
      v10 = (unsigned __int16)v15 | 0x80070000;
    goto LABEL_16;
  }
  if ( !InitializeProcThreadAttributeList(v13, 1u, 0, &dwBytes) )
  {
    v16 = GetLastError();
    v10 = v16;
    if ( v16 > 0 )
      v10 = (unsigned __int16)v16 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
        9459,
        "WORKER_PROCESS::InitializeProcThreadAttribList",
        v10,
        "Failed to InitializeProcThreadAttributeList().\n");
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v14);
LABEL_16:
    if ( (v10 & 0x80000000) != 0 )
      return v10;
    goto LABEL_19;
  }
  *v8 = v14;
  v10 = 0;
  dwBytes = 0;
LABEL_19:
  v18 = 0;
  while ( UpdateProcThreadAttribute(*v8, 0, a3[v18], a4[v18], 2u, 0, 0) )
  {
    v18 = (unsigned int)(v18 + 1);
    if ( (_DWORD)v18 )
      return v10;
  }
  v19 = GetLastError();
  v10 = v19;
  if ( v19 > 0 )
    v10 = (unsigned __int16)v19 | 0x80070000;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
      4440,
      "WORKER_PROCESS::SetProcessThreadAttribute",
      v10,
      "Failed UpdateProcThreadAttribute()\n");
  return v10;
}

```

## disassembly

```asm
0x180026764  mov     rax, rsp
0x180026767  mov     [rax+8], rcx
0x18002676b  push    rbx
0x18002676c  push    rsi
0x18002676d  push    rdi
0x18002676e  push    r12
0x180026770  push    r14
0x180026772  push    r15
0x180026774  sub     rsp, 48h
0x180026778  mov     r15, r8
0x18002677b  mov     qword ptr [rax+8], 0
0x180026783  xor     r8d, r8d; dwFlags
0x180026786  mov     r14, r9
0x180026789  lea     r9, [rax+8]; lpSize
0x18002678d  xor     ecx, ecx; lpAttributeList
0x18002678f  lea     edx, [r8+1]; dwAttributeCount
0x180026793  call    cs:__imp_InitializeProcThreadAttributeList
0x180026799  mov     rsi, [rsp+78h+arg_20]
0x1800267a1  mov     r12d, 80070000h
0x1800267a7  test    eax, eax
0x1800267a9  jnz     short loc_180026805
0x1800267ab  call    cs:__imp_GetLastError
0x1800267b1  mov     ebx, eax
0x1800267b3  cmp     eax, 7Ah ; 'z'
0x1800267b6  jz      short loc_180026805
0x1800267b8  test    eax, eax
0x1800267ba  jle     short loc_1800267C2
0x1800267bc  movzx   ebx, ax
0x1800267bf  or      ebx, r12d
0x1800267c2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800267c9  jz      loc_1800268C0
0x1800267cf  mov     rcx, cs:g_pDebug
0x1800267d6  lea     rax, aFailedToInitia_7; "Failed to InitializeProcThreadAttribute"...
0x1800267dd  mov     [rsp+78h+lpPreviousValue], rax
0x1800267e2  lea     r9, aWorkerProcessI_0; "WORKER_PROCESS::InitializeProcThreadAtt"...
0x1800267e9  mov     r8d, 24D7h
0x1800267ef  mov     dword ptr [rsp+78h+cbSize], ebx
0x1800267f3  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800267fa  call    cs:__imp_PuDbgPrintError
0x180026800  jmp     loc_1800268C0
0x180026805  mov     rbx, [rsp+78h+dwBytes]
0x18002680d  call    cs:__imp_GetProcessHeap
0x180026813  mov     r8, rbx; dwBytes
0x180026816  mov     edx, 8; dwFlags
0x18002681b  mov     rcx, rax; hHeap
0x18002681e  call    cs:__imp_HeapAlloc
0x180026824  mov     rdi, rax
0x180026827  test    rax, rax
0x18002682a  jnz     short loc_180026844
0x18002682c  call    cs:__imp_GetLastError
0x180026832  mov     ebx, eax
0x180026834  test    eax, eax
0x180026836  jle     loc_1800268C0
0x18002683c  movzx   ebx, ax
0x18002683f  or      ebx, r12d
0x180026842  jmp     short loc_1800268C0
0x180026844  xor     r8d, r8d; dwFlags
0x180026847  lea     r9, [rsp+78h+dwBytes]; lpSize
0x18002684f  mov     rcx, rdi; lpAttributeList
0x180026852  lea     edx, [r8+1]; dwAttributeCount
0x180026856  call    cs:__imp_InitializeProcThreadAttributeList
0x18002685c  test    eax, eax
0x18002685e  jnz     short loc_1800268CA
0x180026860  call    cs:__imp_GetLastError
0x180026866  mov     ebx, eax
0x180026868  test    eax, eax
0x18002686a  jle     short loc_180026872
0x18002686c  movzx   ebx, ax
0x18002686f  or      ebx, r12d
0x180026872  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180026879  jz      short loc_1800268AC
0x18002687b  mov     rcx, cs:g_pDebug
0x180026882  lea     rax, aFailedToInitia_7; "Failed to InitializeProcThreadAttribute"...
0x180026889  mov     [rsp+78h+lpPreviousValue], rax
0x18002688e  lea     r9, aWorkerProcessI_0; "WORKER_PROCESS::InitializeProcThreadAtt"...
0x180026895  mov     r8d, 24F3h
0x18002689b  mov     dword ptr [rsp+78h+cbSize], ebx
0x18002689f  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800268a6  call    cs:__imp_PuDbgPrintError
0x1800268ac  call    cs:__imp_GetProcessHeap
0x1800268b2  mov     r8, rdi; lpMem
0x1800268b5  xor     edx, edx; dwFlags
0x1800268b7  mov     rcx, rax; hHeap
0x1800268ba  call    cs:__imp_HeapFree
0x1800268c0  test    ebx, ebx
0x1800268c2  js      loc_180026964
0x1800268c8  jmp     short loc_1800268DB
0x1800268ca  mov     [rsi], rdi
0x1800268cd  xor     ebx, ebx
0x1800268cf  mov     [rsp+78h+dwBytes], 0
0x1800268db  xor     edi, edi
0x1800268dd  mov     r9, [r14+rdi*8]; lpValue
0x1800268e1  xor     edx, edx; dwFlags
0x1800268e3  mov     r8, [r15+rdi*8]; Attribute
0x1800268e7  mov     rcx, [rsi]; lpAttributeList
0x1800268ea  mov     [rsp+78h+lpReturnSize], 0; lpReturnSize
0x1800268f3  mov     [rsp+78h+lpPreviousValue], 0; lpPreviousValue
0x1800268fc  mov     [rsp+78h+cbSize], 2; cbSize
0x180026905  call    cs:__imp_UpdateProcThreadAttribute
0x18002690b  test    eax, eax
0x18002690d  jz      short loc_180026918
0x18002690f  inc     edi
0x180026911  cmp     edi, 1
0x180026914  jb      short loc_1800268DD
0x180026916  jmp     short loc_180026964
0x180026918  call    cs:__imp_GetLastError
0x18002691e  mov     ebx, eax
0x180026920  test    eax, eax
0x180026922  jle     short loc_18002692A
0x180026924  movzx   ebx, ax
0x180026927  or      ebx, r12d
0x18002692a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180026931  jz      short loc_180026964
0x180026933  mov     rcx, cs:g_pDebug
0x18002693a  lea     rax, aFailedUpdatepr; "Failed UpdateProcThreadAttribute()\n"
0x180026941  mov     [rsp+78h+lpPreviousValue], rax
0x180026946  lea     r9, aWorkerProcessS_7; "WORKER_PROCESS::SetProcessThreadAttribu"...
0x18002694d  mov     r8d, 1158h
0x180026953  mov     dword ptr [rsp+78h+cbSize], ebx
0x180026957  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002695e  call    cs:__imp_PuDbgPrintError
0x180026964  mov     eax, ebx
0x180026966  add     rsp, 48h
0x18002696a  pop     r15
0x18002696c  pop     r14
0x18002696e  pop     r12
0x180026970  pop     rdi
0x180026971  pop     rsi
0x180026972  pop     rbx
0x180026973  retn
```
