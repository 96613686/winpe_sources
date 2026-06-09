# LoadModule

- ea: `0x18003e530`
- end: `0x18003e963`
- name: `LoadModule`
- size: `1075`
- prototype: `DWORD __stdcall(LPCSTR lpModuleName, LPVOID lpParameterBlock)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting`

## callees

- `0x18000f920`
- `0x18003e530`
- `0x18007a7a1`
- `0x18007a7d1`
- `0x18007a7dd`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlDetermineDosPathNameType_U` at `0x18003e869`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x18003e869`
- `ntdll!RtlInitAnsiStringEx` at `0x18003e7f8`
- `ntdll!RtlInitAnsiStringEx` at `0x18003e7f8`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003e836`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003e836`
- `ntdll!NtClose` at `0x18003e782`
- `ntdll!NtClose` at `0x18003e790`
- `ntdll!NtClose` at `0x18003e782`
- `ntdll!NtClose` at `0x18003e790`
- `ntdll!RtlFreeUnicodeString` at `0x18003e879`
- `ntdll!RtlFreeUnicodeString` at `0x18003e879`
- `ntdll!RtlSetLastWin32Error` at `0x18003e5e7`
- `ntdll!RtlSetLastWin32Error` at `0x18003e5e7`
- `ntdll!RtlFreeHeap` at `0x18003e734`
- `ntdll!RtlFreeHeap` at `0x18003e751`
- `ntdll!RtlFreeHeap` at `0x18007b10b`
- `ntdll!RtlFreeHeap` at `0x18007b12a`
- `ntdll!RtlFreeHeap` at `0x18003e734`
- `ntdll!RtlFreeHeap` at `0x18003e751`
- `ntdll!RtlFreeHeap` at `0x18007b10b`
- `ntdll!RtlFreeHeap` at `0x18007b12a`
- `ntdll!RtlAllocateHeap` at `0x18003e5cf`
- `ntdll!RtlAllocateHeap` at `0x18003e684`
- `ntdll!RtlAllocateHeap` at `0x18003e5cf`
- `ntdll!RtlAllocateHeap` at `0x18003e684`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003e5b4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003e667`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003e5b4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003e667`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessA` at `0x18003e711`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessA` at `0x18003e711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e8be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e8be`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18003e8af`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18003e8af`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x18003e60e`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x18003e60e`

## pseudocode

```c
DWORD __stdcall LoadModule(LPCSTR lpModuleName, LPVOID lpParameterBlock)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  BOOL v8; // ebx
  CHAR *v9; // rsi
  ULONG *GlobalData; // rax
  CHAR *lpBuffer; // rax
  CHAR *v12; // r14
  DWORD v13; // eax
  __int64 v14; // r13
  unsigned int v15; // r12d
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  ULONG *v19; // rax
  CHAR *Heap; // rax
  ULONG v22; // eax
  ULONG v23; // eax
  RTL_PATH_TYPE v24; // ebx
  HANDLE FileA; // rax
  __int64 v26; // [rsp+0h] [rbp-158h] BYREF
  __int64 *v27; // [rsp+50h] [rbp-108h]
  CHAR *v28; // [rsp+58h] [rbp-100h]
  CHAR *v29; // [rsp+60h] [rbp-F8h]
  BOOL v30; // [rsp+68h] [rbp-F0h]
  int v31; // [rsp+6Ch] [rbp-ECh]
  int v32; // [rsp+70h] [rbp-E8h]
  int v33; // [rsp+74h] [rbp-E4h]
  ULONG v34; // [rsp+78h] [rbp-E0h]
  int v35; // [rsp+7Ch] [rbp-DCh]
  struct _UNICODE_STRING UnicodeString; // [rsp+80h] [rbp-D8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-C8h] BYREF
  struct _STRING DestinationString; // [rsp+A8h] [rbp-B0h] BYREF
  struct _STARTUPINFOA StartupInfo; // [rsp+C0h] [rbp-98h] BYREF
  ULONG LastErrorValue; // [rsp+168h] [rbp+10h]

  v27 = &v26;
  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo, 0, 0x64u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( *((_DWORD *)lpParameterBlock + 6) || **((_WORD **)lpParameterBlock + 2) != 2 )
  {
    BaseSetLastNTError(3221225485LL);
    return 0;
  }
  v8 = 0;
  v9 = 0;
  v29 = 0;
  v28 = 0;
  GlobalData = (ULONG *)KernelBaseGetGlobalData(v5, v4, v6, v7);
  lpBuffer = (CHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, 0x104u);
  v12 = lpBuffer;
  v28 = lpBuffer;
  if ( !lpBuffer )
    goto LABEL_4;
  v13 = SearchPathA(0, lpModuleName, ".exe", 0x104u, lpBuffer, 0);
  v14 = v13;
  if ( v13 - 1 > 0x102 )
  {
    UnicodeString = 0;
    DestinationString = 0;
    if ( RtlInitAnsiStringEx(&DestinationString, lpModuleName) >= 0 )
    {
      if ( RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u) >= 0 )
      {
        v24 = RtlDetermineDosPathNameType_U(UnicodeString.Buffer);
        RtlFreeUnicodeString(&UnicodeString);
        if ( v24 == RtlPathTypeRelative )
        {
          v35 = 2;
          local_unwind_1(v27, &loc_18003E928);
          return 2;
        }
        else
        {
          FileA = CreateFileA(lpModuleName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
          if ( FileA == (HANDLE)-1LL )
          {
            LastErrorValue = NtCurrentTeb()->LastErrorValue;
            v34 = LastErrorValue;
            local_unwind_1(v27, &loc_18003E908);
            return LastErrorValue;
          }
          else
          {
            CloseHandle(FileA);
            v33 = 2;
            local_unwind_1(v27, &loc_18003E8DB);
            return 2;
          }
        }
      }
      else
      {
        v32 = 2;
        local_unwind_1(v27, &loc_18003E857);
        return 2;
      }
    }
    else
    {
      v31 = 2;
      local_unwind_1(v27, &loc_18003E819);
      return 2;
    }
  }
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.dwFlags = 1;
  StartupInfo.wShowWindow = *(_WORD *)(*((_QWORD *)lpParameterBlock + 2) + 2LL);
  v15 = **((unsigned __int8 **)lpParameterBlock + 1);
  v19 = (ULONG *)KernelBaseGetGlobalData(StartupInfo.wShowWindow, v16, v17, v18);
  Heap = (CHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *v19, (unsigned int)v14 + v15 + 2);
  v9 = Heap;
  v29 = Heap;
  if ( Heap )
  {
    memcpy_0(Heap, v12, (unsigned int)v14);
    v9[v14] = 32;
    memcpy_0(&v9[(unsigned int)(v14 + 1)], (const void *)(*((_QWORD *)lpParameterBlock + 1) + 1LL), v15);
    v9[(unsigned int)v14 + 1 + v15] = 0;
    v8 = CreateProcessA(v12, v9, 0, 0, 0, 0, *(LPVOID *)lpParameterBlock, 0, &StartupInfo, &ProcessInformation);
    v30 = v8;
  }
  else
  {
LABEL_4:
    RtlSetLastWin32Error(8u);
  }
  if ( v12 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  if ( v9 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  if ( !v8 )
  {
    v22 = NtCurrentTeb()->LastErrorValue - 2;
    if ( !v22 )
      return 2;
    v23 = v22 - 1;
    if ( !v23 )
      return 3;
    if ( v23 == 190 )
      return 11;
    return 0;
  }
  if ( UserWaitForInputIdleRoutine )
    UserWaitForInputIdleRoutine(ProcessInformation.hProcess, 30000);
  NtClose(ProcessInformation.hProcess);
  NtClose(ProcessInformation.hThread);
  return 33;
}

```

## disassembly

```asm
0x18003e530  mov     [rsp+arg_0], rbx
0x18003e535  mov     [rsp+arg_10], rsi
0x18003e53a  push    rdi
0x18003e53b  push    r12
0x18003e53d  push    r13
0x18003e53f  push    r14
0x18003e541  push    r15
0x18003e543  sub     rsp, 130h
0x18003e54a  mov     [rsp+158h+var_108], rsp
0x18003e54f  mov     r15, rdx
0x18003e552  mov     r12, rcx
0x18003e555  xor     eax, eax
0x18003e557  mov     dword ptr [rsp+158h+StartupInfo+4], eax
0x18003e55e  xor     edx, edx; Val
0x18003e560  lea     r8d, [rax+64h]; Size
0x18003e564  lea     rcx, [rsp+158h+StartupInfo]; void *
0x18003e56c  call    memset_0
0x18003e571  xorps   xmm0, xmm0
0x18003e574  xor     eax, eax
0x18003e576  movups  xmmword ptr [rsp+158h+ProcessInformation.hProcess], xmm0
0x18003e57e  mov     qword ptr [rsp+158h+ProcessInformation.dwProcessId], rax
0x18003e586  xor     r13d, r13d
0x18003e589  cmp     [r15+18h], r13d
0x18003e58d  jnz     loc_18003E93A
0x18003e593  mov     rax, [r15+10h]
0x18003e597  lea     edi, [r13+2]
0x18003e59b  cmp     [rax], di
0x18003e59e  jnz     loc_18003E93A
0x18003e5a4  mov     ebx, r13d
0x18003e5a7  mov     esi, r13d
0x18003e5aa  mov     [rsp+158h+var_F8], r13
0x18003e5af  mov     [rsp+158h+var_100], r13
0x18003e5b4  call    cs:__imp_KernelBaseGetGlobalData
0x18003e5ba  mov     rcx, gs:60h
0x18003e5c3  mov     r8d, 104h; Size
0x18003e5c9  mov     edx, [rax]; Flags
0x18003e5cb  mov     rcx, [rcx+30h]; HeapHandle
0x18003e5cf  call    cs:__imp_RtlAllocateHeap
0x18003e5d5  mov     r14, rax
0x18003e5d8  mov     [rsp+158h+var_100], rax
0x18003e5dd  test    rax, rax
0x18003e5e0  jnz     short loc_18003E5F2
0x18003e5e2  mov     ecx, 8; LastError
0x18003e5e7  call    cs:__imp_RtlSetLastWin32Error
0x18003e5ed  jmp     loc_18003E71D
0x18003e5f2  mov     [rsp+158h+lpFilePart], r13; lpFilePart
0x18003e5f7  mov     [rsp+158h+lpBuffer], r14; lpBuffer
0x18003e5fc  mov     r9d, 104h; nBufferLength
0x18003e602  lea     r8, Extension; ".exe"
0x18003e609  mov     rdx, r12; lpFileName
0x18003e60c  xor     ecx, ecx; lpPath
0x18003e60e  call    cs:__imp_SearchPathA
0x18003e614  mov     r13d, eax
0x18003e617  lea     eax, [r13-1]
0x18003e61b  cmp     eax, 102h
0x18003e620  ja      loc_18003E7D7
0x18003e626  mov     esi, 68h ; 'h'
0x18003e62b  mov     r8d, esi; Size
0x18003e62e  xor     edx, edx; Val
0x18003e630  lea     rcx, [rsp+158h+StartupInfo]; void *
0x18003e638  call    memset_0
0x18003e63d  mov     [rsp+158h+StartupInfo.cb], esi
0x18003e644  mov     [rsp+158h+StartupInfo.dwFlags], 1
0x18003e64f  mov     rax, [r15+10h]
0x18003e653  movzx   ecx, word ptr [rax+2]
0x18003e657  mov     [rsp+158h+StartupInfo.wShowWindow], cx
0x18003e65f  mov     rax, [r15+8]
0x18003e663  movzx   r12d, byte ptr [rax]
0x18003e667  call    cs:__imp_KernelBaseGetGlobalData
0x18003e66d  lea     r8d, [r12+2]
0x18003e672  add     r8d, r13d; Size
0x18003e675  mov     rcx, gs:60h
0x18003e67e  mov     edx, [rax]; Flags
0x18003e680  mov     rcx, [rcx+30h]; HeapHandle
0x18003e684  call    cs:__imp_RtlAllocateHeap
0x18003e68a  mov     rsi, rax
0x18003e68d  mov     [rsp+158h+var_F8], rax
0x18003e692  test    rax, rax
0x18003e695  jz      loc_18003E5E2
0x18003e69b  mov     r8d, r13d; Size
0x18003e69e  mov     rdx, r14; Src
0x18003e6a1  mov     rcx, rax; void *
0x18003e6a4  call    memcpy_0
0x18003e6a9  mov     byte ptr [r13+rsi+0], 20h ; ' '
0x18003e6af  mov     r8d, r12d; Size
0x18003e6b2  mov     rdx, [r15+8]
0x18003e6b6  inc     rdx; Src
0x18003e6b9  lea     ecx, [r13+1]
0x18003e6bd  add     rcx, rsi; void *
0x18003e6c0  call    memcpy_0
0x18003e6c5  lea     eax, [r12+1]
0x18003e6ca  add     eax, r13d
0x18003e6cd  xor     r13d, r13d
0x18003e6d0  mov     [rax+rsi], r13b
0x18003e6d4  lea     rax, [rsp+158h+ProcessInformation]
0x18003e6dc  mov     [rsp+158h+lpProcessInformation], rax; lpProcessInformation
0x18003e6e1  lea     rax, [rsp+158h+StartupInfo]
0x18003e6e9  mov     [rsp+158h+lpStartupInfo], rax; lpStartupInfo
0x18003e6ee  mov     [rsp+158h+lpCurrentDirectory], r13; lpCurrentDirectory
0x18003e6f3  mov     rax, [r15]
0x18003e6f6  mov     [rsp+158h+lpEnvironment], rax; lpEnvironment
0x18003e6fb  mov     dword ptr [rsp+158h+lpFilePart], r13d; dwCreationFlags
0x18003e700  mov     dword ptr [rsp+158h+lpBuffer], r13d; bInheritHandles
0x18003e705  xor     r9d, r9d; lpThreadAttributes
0x18003e708  xor     r8d, r8d; lpProcessAttributes
0x18003e70b  mov     rdx, rsi; lpCommandLine
0x18003e70e  mov     rcx, r14; lpApplicationName
0x18003e711  call    cs:__imp_CreateProcessA
0x18003e717  mov     ebx, eax
0x18003e719  mov     [rsp+158h+var_F0], eax
0x18003e71d  test    r14, r14
0x18003e720  jz      short loc_18003E73A
0x18003e722  mov     rcx, gs:60h
0x18003e72b  mov     r8, r14; P
0x18003e72e  xor     edx, edx; Flags
0x18003e730  mov     rcx, [rcx+30h]; HeapHandle
0x18003e734  call    cs:__imp_RtlFreeHeap
0x18003e73a  test    rsi, rsi
0x18003e73d  jz      short loc_18003E758
0x18003e73f  mov     rcx, gs:60h
0x18003e748  mov     r8, rsi; P
0x18003e74b  xor     edx, edx; Flags
0x18003e74d  mov     rcx, [rcx+30h]; HeapHandle
0x18003e751  call    cs:__imp_RtlFreeHeap
0x18003e757  nop
0x18003e758  test    ebx, ebx
0x18003e75a  jz      short loc_18003E7A0
0x18003e75c  mov     rax, cs:UserWaitForInputIdleRoutine
0x18003e763  test    rax, rax
0x18003e766  jz      short loc_18003E77A
0x18003e768  mov     edx, 7530h
0x18003e76d  mov     rcx, [rsp+158h+ProcessInformation.hProcess]
0x18003e775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e77a  mov     rcx, [rsp+158h+ProcessInformation.hProcess]; Handle
0x18003e782  call    cs:__imp_NtClose
0x18003e788  mov     rcx, [rsp+158h+ProcessInformation.hThread]; Handle
0x18003e790  call    cs:__imp_NtClose
0x18003e796  mov     eax, 21h ; '!'
0x18003e79b  jmp     loc_18003E946
0x18003e7a0  mov     eax, gs:68h
0x18003e7a8  sub     eax, edi
0x18003e7aa  jz      short loc_18003E7D0
0x18003e7ac  sub     eax, 1
0x18003e7af  jz      short loc_18003E7C6
0x18003e7b1  cmp     eax, 0BEh
0x18003e7b6  jnz     loc_18003E944
0x18003e7bc  mov     eax, 0Bh
0x18003e7c1  jmp     loc_18003E946
0x18003e7c6  mov     eax, 3
0x18003e7cb  jmp     loc_18003E946
0x18003e7d0  mov     eax, edi
0x18003e7d2  jmp     loc_18003E946
0x18003e7d7  xorps   xmm0, xmm0
0x18003e7da  movups  xmmword ptr [rsp+158h+UnicodeString.Length], xmm0
0x18003e7e2  xorps   xmm1, xmm1
0x18003e7e5  movups  xmmword ptr [rsp+158h+DestinationString.Length], xmm1
0x18003e7ed  mov     rdx, r12; SourceString
0x18003e7f0  lea     rcx, [rsp+158h+DestinationString]; DestinationString
0x18003e7f8  call    cs:__imp_RtlInitAnsiStringEx
0x18003e7fe  test    eax, eax
0x18003e800  jns     short loc_18003E823
0x18003e802  mov     [rsp+158h+var_EC], edi
0x18003e806  lea     rdx, loc_18003E819
0x18003e80d  mov     rcx, [rsp+158h+var_108]
0x18003e812  call    _local_unwind_1
0x18003e817  nop
0x18003e818  nop
0x18003e819  mov     eax, 2
0x18003e81e  jmp     loc_18003E946
0x18003e823  mov     r8b, 1; AllocateDestinationString
0x18003e826  lea     rdx, [rsp+158h+DestinationString]; SourceString
0x18003e82e  lea     rcx, [rsp+158h+UnicodeString]; DestinationString
0x18003e836  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18003e83c  test    eax, eax
0x18003e83e  jns     short loc_18003E861
0x18003e840  mov     [rsp+158h+var_E8], edi
0x18003e844  lea     rdx, loc_18003E857
0x18003e84b  mov     rcx, [rsp+158h+var_108]
0x18003e850  call    _local_unwind_1
0x18003e855  nop
0x18003e856  nop
0x18003e857  mov     eax, 2
0x18003e85c  jmp     loc_18003E946
0x18003e861  mov     rcx, [rsp+158h+UnicodeString.Buffer]; Path
0x18003e869  call    cs:__imp_RtlDetermineDosPathNameType_U
0x18003e86f  mov     ebx, eax
0x18003e871  lea     rcx, [rsp+158h+UnicodeString]; UnicodeString
0x18003e879  call    cs:__imp_RtlFreeUnicodeString
0x18003e87f  cmp     ebx, 5
0x18003e882  jz      loc_18003E911
0x18003e888  mov     [rsp+158h+lpEnvironment], 0; hTemplateFile
0x18003e891  mov     dword ptr [rsp+158h+lpFilePart], 80h; dwFlagsAndAttributes
0x18003e899  mov     r8d, 3; dwShareMode
0x18003e89f  mov     dword ptr [rsp+158h+lpBuffer], r8d; dwCreationDisposition
0x18003e8a4  xor     r9d, r9d; lpSecurityAttributes
0x18003e8a7  mov     edx, 80000000h; dwDesiredAccess
0x18003e8ac  mov     rcx, r12; lpFileName
0x18003e8af  call    cs:__imp_CreateFileA
0x18003e8b5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003e8b9  jz      short loc_18003E8E2
0x18003e8bb  mov     rcx, rax; hObject
0x18003e8be  call    cs:__imp_CloseHandle
0x18003e8c4  mov     [rsp+158h+var_E4], edi
0x18003e8c8  lea     rdx, loc_18003E8DB
0x18003e8cf  mov     rcx, [rsp+158h+var_108]
0x18003e8d4  call    _local_unwind_1
0x18003e8d9  nop
0x18003e8da  nop
0x18003e8db  mov     eax, 2
0x18003e8e0  jmp     short loc_18003E946
0x18003e8e2  mov     eax, gs:68h
0x18003e8ea  mov     [rsp+158h+arg_8], eax
0x18003e8f1  mov     [rsp+158h+var_E0], eax
0x18003e8f5  lea     rdx, loc_18003E908
0x18003e8fc  mov     rcx, [rsp+158h+var_108]
0x18003e901  call    _local_unwind_1
0x18003e906  nop
0x18003e907  nop
0x18003e908  mov     eax, [rsp+158h+arg_8]
0x18003e90f  jmp     short loc_18003E946
0x18003e911  mov     [rsp+158h+var_DC], edi
0x18003e915  lea     rdx, loc_18003E928
0x18003e91c  mov     rcx, [rsp+158h+var_108]
0x18003e921  call    _local_unwind_1
0x18003e926  nop
0x18003e927  nop
0x18003e928  mov     eax, 2
0x18003e92d  jmp     short loc_18003E946
0x18003e92f  mov     ecx, eax
0x18003e931  call    BaseSetLastNTError
0x18003e936  xor     eax, eax
0x18003e938  jmp     short loc_18003E946
0x18003e93a  mov     ecx, 0C000000Dh
0x18003e93f  call    BaseSetLastNTError
0x18003e944  xor     eax, eax
0x18003e946  lea     r11, [rsp+158h+var_28]
0x18003e94e  mov     rbx, [r11+30h]
0x18003e952  mov     rsi, [r11+40h]
0x18003e956  mov     rsp, r11
0x18003e959  pop     r15
0x18003e95b  pop     r14
0x18003e95d  pop     r13
0x18003e95f  pop     r12
0x18003e961  pop     rdi
0x18003e962  retn
0x18007b0ea  push    rbp
0x18007b0ec  sub     rsp, 50h
0x18007b0f0  mov     rbp, rdx
0x18007b0f3  mov     r8, [rbp+58h]; P
0x18007b0f7  test    r8, r8
0x18007b0fa  jz      short loc_18007B112
0x18007b0fc  mov     rcx, gs:60h
0x18007b105  xor     edx, edx; Flags
0x18007b107  mov     rcx, [rcx+30h]; HeapHandle
0x18007b10b  call    cs:__imp_RtlFreeHeap
0x18007b111  nop
0x18007b112  mov     r8, [rbp+60h]; P
0x18007b116  test    r8, r8
0x18007b119  jz      short loc_18007B131
0x18007b11b  mov     rcx, gs:60h
0x18007b124  xor     edx, edx; Flags
0x18007b126  mov     rcx, [rcx+30h]; HeapHandle
0x18007b12a  call    cs:__imp_RtlFreeHeap
0x18007b130  nop
0x18007b131  add     rsp, 50h
0x18007b135  pop     rbp
0x18007b136  retn
0x18007b138  push    rbp
0x18007b13a  sub     rsp, 50h
0x18007b13e  mov     rbp, rdx
0x18007b141  mov     rax, [rcx]
0x18007b144  xor     ecx, ecx
0x18007b146  cmp     dword ptr [rax], 0C00000FDh
0x18007b14c  setnz   cl
0x18007b14f  mov     eax, ecx
0x18007b151  add     rsp, 50h
0x18007b155  pop     rbp
0x18007b156  retn
```
