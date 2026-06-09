# LoadModule

- ea: `0x180041d80`
- end: `0x18004221a`
- name: `LoadModule`
- size: `1178`
- prototype: `DWORD __stdcall(LPCSTR lpModuleName, LPVOID lpParameterBlock)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting`

## callees

- `0x18000ccf0`
- `0x180041d80`
- `0x180082721`
- `0x180082751`
- `0x18008275d`
- `0x180084010`

## import_xrefs

- `ntdll!RtlDetermineDosPathNameType_U` at `0x180042107`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x180042107`
- `ntdll!RtlInitAnsiStringEx` at `0x18004208a`
- `ntdll!RtlInitAnsiStringEx` at `0x18004208a`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800420ce`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800420ce`
- `ntdll!NtClose` at `0x180042008`
- `ntdll!NtClose` at `0x18004201c`
- `ntdll!NtClose` at `0x180042008`
- `ntdll!NtClose` at `0x18004201c`
- `ntdll!RtlFreeUnicodeString` at `0x18004211d`
- `ntdll!RtlFreeUnicodeString` at `0x18004211d`
- `ntdll!RtlSetLastWin32Error` at `0x180041e43`
- `ntdll!RtlSetLastWin32Error` at `0x180041e43`
- `ntdll!RtlFreeHeap` at `0x180041fae`
- `ntdll!RtlFreeHeap` at `0x180041fd1`
- `ntdll!RtlFreeHeap` at `0x180083175`
- `ntdll!RtlFreeHeap` at `0x18008319a`
- `ntdll!RtlFreeHeap` at `0x180041fae`
- `ntdll!RtlFreeHeap` at `0x180041fd1`
- `ntdll!RtlFreeHeap` at `0x180083175`
- `ntdll!RtlFreeHeap` at `0x18008319a`
- `ntdll!RtlAllocateHeap` at `0x180041e25`
- `ntdll!RtlAllocateHeap` at `0x180041ef2`
- `ntdll!RtlAllocateHeap` at `0x180041e25`
- `ntdll!RtlAllocateHeap` at `0x180041ef2`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180041e04`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180041ecf`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180041e04`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180041ecf`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessA` at `0x180041f85`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessA` at `0x180041f85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004216e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004216e`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180042159`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180042159`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x180041e70`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x180041e70`

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
          local_unwind_1(v27, &loc_1800421DE);
          return 2;
        }
        else
        {
          FileA = CreateFileA(lpModuleName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
          if ( FileA == (HANDLE)-1LL )
          {
            LastErrorValue = NtCurrentTeb()->LastErrorValue;
            v34 = LastErrorValue;
            local_unwind_1(v27, &loc_1800421BE);
            return LastErrorValue;
          }
          else
          {
            CloseHandle(FileA);
            v33 = 2;
            local_unwind_1(v27, &loc_180042191);
            return 2;
          }
        }
      }
      else
      {
        v32 = 2;
        local_unwind_1(v27, &loc_1800420F5);
        return 2;
      }
    }
    else
    {
      v31 = 2;
      local_unwind_1(v27, &loc_1800420B1);
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
0x180041d80  mov     [rsp+arg_0], rbx
0x180041d85  mov     [rsp+arg_10], rsi
0x180041d8a  push    rdi
0x180041d8b  push    r12
0x180041d8d  push    r13
0x180041d8f  push    r14
0x180041d91  push    r15
0x180041d93  sub     rsp, 130h
0x180041d9a  mov     [rsp+158h+var_108], rsp
0x180041d9f  mov     r15, rdx
0x180041da2  mov     r12, rcx
0x180041da5  xor     eax, eax
0x180041da7  mov     dword ptr [rsp+158h+StartupInfo+4], eax
0x180041dae  xor     edx, edx; Val
0x180041db0  lea     r8d, [rax+64h]; Size
0x180041db4  lea     rcx, [rsp+158h+StartupInfo]; void *
0x180041dbc  call    memset_0
0x180041dc1  xorps   xmm0, xmm0
0x180041dc4  xor     eax, eax
0x180041dc6  movups  xmmword ptr [rsp+158h+ProcessInformation.hProcess], xmm0
0x180041dce  mov     qword ptr [rsp+158h+ProcessInformation.dwProcessId], rax
0x180041dd6  xor     r13d, r13d
0x180041dd9  cmp     [r15+18h], r13d
0x180041ddd  jnz     loc_1800421F0
0x180041de3  mov     rax, [r15+10h]
0x180041de7  lea     edi, [r13+2]
0x180041deb  cmp     [rax], di
0x180041dee  jnz     loc_1800421F0
0x180041df4  mov     ebx, r13d
0x180041df7  mov     esi, r13d
0x180041dfa  mov     [rsp+158h+var_F8], r13
0x180041dff  mov     [rsp+158h+var_100], r13
0x180041e04  call    cs:__imp_KernelBaseGetGlobalData
0x180041e0b  nop     dword ptr [rax+rax+00h]
0x180041e10  mov     rcx, gs:60h
0x180041e19  mov     r8d, 104h; Size
0x180041e1f  mov     edx, [rax]; Flags
0x180041e21  mov     rcx, [rcx+30h]; HeapHandle
0x180041e25  call    cs:__imp_RtlAllocateHeap
0x180041e2c  nop     dword ptr [rax+rax+00h]
0x180041e31  mov     r14, rax
0x180041e34  mov     [rsp+158h+var_100], rax
0x180041e39  test    rax, rax
0x180041e3c  jnz     short loc_180041E54
0x180041e3e  mov     ecx, 8; LastError
0x180041e43  call    cs:__imp_RtlSetLastWin32Error
0x180041e4a  nop     dword ptr [rax+rax+00h]
0x180041e4f  jmp     loc_180041F97
0x180041e54  mov     [rsp+158h+lpFilePart], r13; lpFilePart
0x180041e59  mov     [rsp+158h+lpBuffer], r14; lpBuffer
0x180041e5e  mov     r9d, 104h; nBufferLength
0x180041e64  lea     r8, Extension; ".exe"
0x180041e6b  mov     rdx, r12; lpFileName
0x180041e6e  xor     ecx, ecx; lpPath
0x180041e70  call    cs:__imp_SearchPathA
0x180041e77  nop     dword ptr [rax+rax+00h]
0x180041e7c  mov     r13d, eax
0x180041e7f  lea     eax, [r13-1]
0x180041e83  cmp     eax, 102h
0x180041e88  ja      loc_180042069
0x180041e8e  mov     esi, 68h ; 'h'
0x180041e93  mov     r8d, esi; Size
0x180041e96  xor     edx, edx; Val
0x180041e98  lea     rcx, [rsp+158h+StartupInfo]; void *
0x180041ea0  call    memset_0
0x180041ea5  mov     [rsp+158h+StartupInfo.cb], esi
0x180041eac  mov     [rsp+158h+StartupInfo.dwFlags], 1
0x180041eb7  mov     rax, [r15+10h]
0x180041ebb  movzx   ecx, word ptr [rax+2]
0x180041ebf  mov     [rsp+158h+StartupInfo.wShowWindow], cx
0x180041ec7  mov     rax, [r15+8]
0x180041ecb  movzx   r12d, byte ptr [rax]
0x180041ecf  call    cs:__imp_KernelBaseGetGlobalData
0x180041ed6  nop     dword ptr [rax+rax+00h]
0x180041edb  lea     r8d, [r12+2]
0x180041ee0  add     r8d, r13d; Size
0x180041ee3  mov     rcx, gs:60h
0x180041eec  mov     edx, [rax]; Flags
0x180041eee  mov     rcx, [rcx+30h]; HeapHandle
0x180041ef2  call    cs:__imp_RtlAllocateHeap
0x180041ef9  nop     dword ptr [rax+rax+00h]
0x180041efe  mov     rsi, rax
0x180041f01  mov     [rsp+158h+var_F8], rax
0x180041f06  test    rax, rax
0x180041f09  jz      loc_180041E3E
0x180041f0f  mov     r8d, r13d; Size
0x180041f12  mov     rdx, r14; Src
0x180041f15  mov     rcx, rax; void *
0x180041f18  call    memcpy_0
0x180041f1d  mov     byte ptr [r13+rsi+0], 20h ; ' '
0x180041f23  mov     r8d, r12d; Size
0x180041f26  mov     rdx, [r15+8]
0x180041f2a  inc     rdx; Src
0x180041f2d  lea     ecx, [r13+1]
0x180041f31  add     rcx, rsi; void *
0x180041f34  call    memcpy_0
0x180041f39  lea     eax, [r12+1]
0x180041f3e  add     eax, r13d
0x180041f41  xor     r13d, r13d
0x180041f44  mov     [rax+rsi], r13b
0x180041f48  lea     rax, [rsp+158h+ProcessInformation]
0x180041f50  mov     [rsp+158h+lpProcessInformation], rax; lpProcessInformation
0x180041f55  lea     rax, [rsp+158h+StartupInfo]
0x180041f5d  mov     [rsp+158h+lpStartupInfo], rax; lpStartupInfo
0x180041f62  mov     [rsp+158h+lpCurrentDirectory], r13; lpCurrentDirectory
0x180041f67  mov     rax, [r15]
0x180041f6a  mov     [rsp+158h+lpEnvironment], rax; lpEnvironment
0x180041f6f  mov     dword ptr [rsp+158h+lpFilePart], r13d; dwCreationFlags
0x180041f74  mov     dword ptr [rsp+158h+lpBuffer], r13d; bInheritHandles
0x180041f79  xor     r9d, r9d; lpThreadAttributes
0x180041f7c  xor     r8d, r8d; lpProcessAttributes
0x180041f7f  mov     rdx, rsi; lpCommandLine
0x180041f82  mov     rcx, r14; lpApplicationName
0x180041f85  call    cs:__imp_CreateProcessA
0x180041f8c  nop     dword ptr [rax+rax+00h]
0x180041f91  mov     ebx, eax
0x180041f93  mov     [rsp+158h+var_F0], eax
0x180041f97  test    r14, r14
0x180041f9a  jz      short loc_180041FBA
0x180041f9c  mov     rcx, gs:60h
0x180041fa5  mov     r8, r14; P
0x180041fa8  xor     edx, edx; Flags
0x180041faa  mov     rcx, [rcx+30h]; HeapHandle
0x180041fae  call    cs:__imp_RtlFreeHeap
0x180041fb5  nop     dword ptr [rax+rax+00h]
0x180041fba  test    rsi, rsi
0x180041fbd  jz      short loc_180041FDE
0x180041fbf  mov     rcx, gs:60h
0x180041fc8  mov     r8, rsi; P
0x180041fcb  xor     edx, edx; Flags
0x180041fcd  mov     rcx, [rcx+30h]; HeapHandle
0x180041fd1  call    cs:__imp_RtlFreeHeap
0x180041fd8  nop     dword ptr [rax+rax+00h]
0x180041fdd  nop
0x180041fde  test    ebx, ebx
0x180041fe0  jz      short loc_180042032
0x180041fe2  mov     rax, cs:UserWaitForInputIdleRoutine
0x180041fe9  test    rax, rax
0x180041fec  jz      short loc_180042000
0x180041fee  mov     edx, 7530h
0x180041ff3  mov     rcx, [rsp+158h+ProcessInformation.hProcess]
0x180041ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042000  mov     rcx, [rsp+158h+ProcessInformation.hProcess]; Handle
0x180042008  call    cs:__imp_NtClose
0x18004200f  nop     dword ptr [rax+rax+00h]
0x180042014  mov     rcx, [rsp+158h+ProcessInformation.hThread]; Handle
0x18004201c  call    cs:__imp_NtClose
0x180042023  nop     dword ptr [rax+rax+00h]
0x180042028  mov     eax, 21h ; '!'
0x18004202d  jmp     loc_1800421FC
0x180042032  mov     eax, gs:68h
0x18004203a  sub     eax, edi
0x18004203c  jz      short loc_180042062
0x18004203e  sub     eax, 1
0x180042041  jz      short loc_180042058
0x180042043  cmp     eax, 0BEh
0x180042048  jnz     loc_1800421FA
0x18004204e  mov     eax, 0Bh
0x180042053  jmp     loc_1800421FC
0x180042058  mov     eax, 3
0x18004205d  jmp     loc_1800421FC
0x180042062  mov     eax, edi
0x180042064  jmp     loc_1800421FC
0x180042069  xorps   xmm0, xmm0
0x18004206c  movups  xmmword ptr [rsp+158h+UnicodeString.Length], xmm0
0x180042074  xorps   xmm1, xmm1
0x180042077  movups  xmmword ptr [rsp+158h+DestinationString.Length], xmm1
0x18004207f  mov     rdx, r12; SourceString
0x180042082  lea     rcx, [rsp+158h+DestinationString]; DestinationString
0x18004208a  call    cs:__imp_RtlInitAnsiStringEx
0x180042091  nop     dword ptr [rax+rax+00h]
0x180042096  test    eax, eax
0x180042098  jns     short loc_1800420BB
0x18004209a  mov     [rsp+158h+var_EC], edi
0x18004209e  lea     rdx, loc_1800420B1
0x1800420a5  mov     rcx, [rsp+158h+var_108]
0x1800420aa  call    _local_unwind_1
0x1800420af  nop
0x1800420b0  nop
0x1800420b1  mov     eax, 2
0x1800420b6  jmp     loc_1800421FC
0x1800420bb  mov     r8b, 1; AllocateDestinationString
0x1800420be  lea     rdx, [rsp+158h+DestinationString]; SourceString
0x1800420c6  lea     rcx, [rsp+158h+UnicodeString]; DestinationString
0x1800420ce  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1800420d5  nop     dword ptr [rax+rax+00h]
0x1800420da  test    eax, eax
0x1800420dc  jns     short loc_1800420FF
0x1800420de  mov     [rsp+158h+var_E8], edi
0x1800420e2  lea     rdx, loc_1800420F5
0x1800420e9  mov     rcx, [rsp+158h+var_108]
0x1800420ee  call    _local_unwind_1
0x1800420f3  nop
0x1800420f4  nop
0x1800420f5  mov     eax, 2
0x1800420fa  jmp     loc_1800421FC
0x1800420ff  mov     rcx, [rsp+158h+UnicodeString.Buffer]; Path
0x180042107  call    cs:__imp_RtlDetermineDosPathNameType_U
0x18004210e  nop     dword ptr [rax+rax+00h]
0x180042113  mov     ebx, eax
0x180042115  lea     rcx, [rsp+158h+UnicodeString]; UnicodeString
0x18004211d  call    cs:__imp_RtlFreeUnicodeString
0x180042124  nop     dword ptr [rax+rax+00h]
0x180042129  cmp     ebx, 5
0x18004212c  jz      loc_1800421C7
0x180042132  mov     [rsp+158h+lpEnvironment], 0; hTemplateFile
0x18004213b  mov     dword ptr [rsp+158h+lpFilePart], 80h; dwFlagsAndAttributes
0x180042143  mov     r8d, 3; dwShareMode
0x180042149  mov     dword ptr [rsp+158h+lpBuffer], r8d; dwCreationDisposition
0x18004214e  xor     r9d, r9d; lpSecurityAttributes
0x180042151  mov     edx, 80000000h; dwDesiredAccess
0x180042156  mov     rcx, r12; lpFileName
0x180042159  call    cs:__imp_CreateFileA
0x180042160  nop     dword ptr [rax+rax+00h]
0x180042165  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180042169  jz      short loc_180042198
0x18004216b  mov     rcx, rax; hObject
0x18004216e  call    cs:__imp_CloseHandle
0x180042175  nop     dword ptr [rax+rax+00h]
0x18004217a  mov     [rsp+158h+var_E4], edi
0x18004217e  lea     rdx, loc_180042191
0x180042185  mov     rcx, [rsp+158h+var_108]
0x18004218a  call    _local_unwind_1
0x18004218f  nop
0x180042190  nop
0x180042191  mov     eax, 2
0x180042196  jmp     short loc_1800421FC
0x180042198  mov     eax, gs:68h
0x1800421a0  mov     [rsp+158h+arg_8], eax
0x1800421a7  mov     [rsp+158h+var_E0], eax
0x1800421ab  lea     rdx, loc_1800421BE
0x1800421b2  mov     rcx, [rsp+158h+var_108]
0x1800421b7  call    _local_unwind_1
0x1800421bc  nop
0x1800421bd  nop
0x1800421be  mov     eax, [rsp+158h+arg_8]
0x1800421c5  jmp     short loc_1800421FC
0x1800421c7  mov     [rsp+158h+var_DC], edi
0x1800421cb  lea     rdx, loc_1800421DE
0x1800421d2  mov     rcx, [rsp+158h+var_108]
0x1800421d7  call    _local_unwind_1
0x1800421dc  nop
0x1800421dd  nop
0x1800421de  mov     eax, 2
0x1800421e3  jmp     short loc_1800421FC
0x1800421e5  mov     ecx, eax
0x1800421e7  call    BaseSetLastNTError
0x1800421ec  xor     eax, eax
0x1800421ee  jmp     short loc_1800421FC
0x1800421f0  mov     ecx, 0C000000Dh
0x1800421f5  call    BaseSetLastNTError
0x1800421fa  xor     eax, eax
0x1800421fc  lea     r11, [rsp+158h+var_28]
0x180042204  mov     rbx, [r11+30h]
0x180042208  mov     rsi, [r11+40h]
0x18004220c  mov     rsp, r11
0x18004220f  pop     r15
0x180042211  pop     r14
0x180042213  pop     r13
0x180042215  pop     r12
0x180042217  pop     rdi
0x180042218  retn
0x180083154  push    rbp
0x180083156  sub     rsp, 50h
0x18008315a  mov     rbp, rdx
0x18008315d  mov     r8, [rbp+58h]; P
0x180083161  test    r8, r8
0x180083164  jz      short loc_180083182
0x180083166  mov     rcx, gs:60h
0x18008316f  xor     edx, edx; Flags
0x180083171  mov     rcx, [rcx+30h]; HeapHandle
0x180083175  call    cs:__imp_RtlFreeHeap
0x18008317c  nop     dword ptr [rax+rax+00h]
0x180083181  nop
0x180083182  mov     r8, [rbp+60h]; P
0x180083186  test    r8, r8
0x180083189  jz      short loc_1800831A7
0x18008318b  mov     rcx, gs:60h
0x180083194  xor     edx, edx; Flags
0x180083196  mov     rcx, [rcx+30h]; HeapHandle
0x18008319a  call    cs:__imp_RtlFreeHeap
0x1800831a1  nop     dword ptr [rax+rax+00h]
0x1800831a6  nop
0x1800831a7  add     rsp, 50h
0x1800831ab  pop     rbp
0x1800831ac  retn
0x1800831ae  push    rbp
0x1800831b0  sub     rsp, 50h
0x1800831b4  mov     rbp, rdx
0x1800831b7  mov     rax, [rcx]
0x1800831ba  xor     ecx, ecx
0x1800831bc  cmp     dword ptr [rax], 0C00000FDh
0x1800831c2  setnz   cl
0x1800831c5  mov     eax, ecx
0x1800831c7  add     rsp, 50h
0x1800831cb  pop     rbp
0x1800831cc  retn
```
