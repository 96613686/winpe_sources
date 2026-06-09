# OROpenHiveInternal

- ea: `0x140023544`
- end: `0x140023751`
- name: `OROpenHiveInternal`
- size: `525`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140022834`
- `0x140023480`
- `0x1400234a0`

## callees

- `0x1400029c6`
- `0x1400029d2`
- `0x1400234b0`
- `0x140023544`
- `0x1400271d4`
- `0x140027b04`
- `0x140028dd0`
- `0x140028e10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400236dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400236dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400236ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400236ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400235e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400236be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400235e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400236be`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1400235d6`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1400235d6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140023655`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140023655`

## string_xrefs

- `0x1400236a1`: `ntdll.dll`
- `0x1400236d2`: `RtlValidRelativeSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall OROpenHiveInternal(HANDLE hFile, __int64 a2, __int64 a3, __int64 a4)
{
  void *v4; // rsi
  char v5; // r14
  HANDLE v8; // rdi
  DWORD LastError; // ebx
  DWORD LowPart; // ebx
  void *v11; // rax
  HMODULE ModuleHandleW; // rax
  void *Block; // [rsp+70h] [rbp+40h] BYREF
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+50h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+88h] [rbp+58h] BYREF

  Block = hFile;
  v4 = 0;
  NumberOfBytesRead = 0;
  v5 = 0;
  FileSize.QuadPart = 0;
  *(_QWORD *)a4 = 0;
  v8 = hFile;
  if ( !hFile && !a2 )
  {
    LastError = 87;
    goto LABEL_27;
  }
  LastError = ORStart();
  if ( !LastError )
  {
    if ( !v8 )
    {
      LastError = ORCreateFile(a2, LastError + 1, LastError + 3, 1, &Block);
      if ( LastError )
      {
        v8 = Block;
        goto LABEL_27;
      }
      v5 = 1;
      v8 = Block;
    }
    if ( GetFileSizeEx(v8, &FileSize) || (LastError = GetLastError()) == 0 )
    {
      LowPart = FileSize.LowPart;
      if ( FileSize.LowPart <= 0x1000 || FileSize.HighPart )
      {
        LastError = 1009;
        goto LABEL_27;
      }
      v11 = o__aligned_malloc_0(FileSize.LowPart, 0x10u);
      Block = v11;
      v4 = v11;
      if ( !v11 )
      {
        LastError = 8;
        goto LABEL_27;
      }
      if ( ReadFile(v8, v11, LowPart, &NumberOfBytesRead, 0) || (LastError = GetLastError()) == 0 )
      {
        LastError = ValidateHiveAndRecoverFromLog(&Block, &FileSize, a2, v8);
        if ( !LastError )
        {
          if ( v5 )
            ORCloseFile(v8);
          v8 = 0;
          v5 = 0;
          ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
          if ( ModuleHandleW )
          {
            ORValidRelativeSecurityDescriptor = (__int64)GetProcAddress(
                                                           ModuleHandleW,
                                                           "RtlValidRelativeSecurityDescriptor");
            if ( ORValidRelativeSecurityDescriptor )
            {
              v4 = 0;
              LastError = OROpenHiveFromMemoryInternal(Block);
              if ( !LastError )
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a4 + 16LL) + 128LL) = 0;
              goto LABEL_27;
            }
          }
          LastError = GetLastError();
        }
        v4 = Block;
      }
    }
  }
LABEL_27:
  if ( v4 )
    aligned_free(v4);
  if ( v5 )
    ORCloseFile(v8);
  return LastError;
}

```

## disassembly

```asm
0x140023544  mov     [rsp-38h+NumberOfBytesRead], r8d
0x140023549  mov     [rsp-38h+Block], rcx
0x14002354e  push    rbp
0x14002354f  push    rbx
0x140023550  push    rsi
0x140023551  push    rdi
0x140023552  push    r12
0x140023554  push    r14
0x140023556  push    r15
0x140023558  mov     rbp, rsp
0x14002355b  sub     rsp, 30h
0x14002355f  xor     esi, esi
0x140023561  mov     [rbp+NumberOfBytesRead], 0
0x140023568  xor     r14b, r14b
0x14002356b  mov     qword ptr [rbp+FileSize], 0
0x140023573  mov     [r9], rsi
0x140023576  mov     r12, r9
0x140023579  mov     r15, rdx
0x14002357c  mov     rdi, rcx
0x14002357f  test    rcx, rcx
0x140023582  jnz     short loc_140023591
0x140023584  test    rdx, rdx
0x140023587  jnz     short loc_140023591
0x140023589  lea     ebx, [rdx+57h]
0x14002358c  jmp     loc_140023725
0x140023591  call    ORStart
0x140023596  mov     ebx, eax
0x140023598  test    eax, eax
0x14002359a  jnz     loc_140023725
0x1400235a0  test    rdi, rdi
0x1400235a3  jnz     short loc_1400235CF
0x1400235a5  lea     edi, [rbx+1]
0x1400235a8  mov     rcx, r15
0x1400235ab  lea     rax, [rbp+Block]
0x1400235af  mov     r9d, edi
0x1400235b2  mov     edx, edi
0x1400235b4  mov     [rsp+30h+lpOverlapped], rax
0x1400235b9  lea     r8d, [rbx+3]
0x1400235bd  call    ORCreateFile
0x1400235c2  mov     ebx, eax
0x1400235c4  test    eax, eax
0x1400235c6  jnz     short loc_140023636
0x1400235c8  mov     r14b, dil
0x1400235cb  mov     rdi, [rbp+Block]
0x1400235cf  lea     rdx, [rbp+FileSize]; lpFileSize
0x1400235d3  mov     rcx, rdi; hFile
0x1400235d6  call    cs:__imp_GetFileSizeEx
0x1400235dd  nop     dword ptr [rax+rax+00h]
0x1400235e2  test    eax, eax
0x1400235e4  jnz     short loc_1400235FC
0x1400235e6  call    cs:__imp_GetLastError
0x1400235ed  nop     dword ptr [rax+rax+00h]
0x1400235f2  mov     ebx, eax
0x1400235f4  test    eax, eax
0x1400235f6  jnz     loc_140023725
0x1400235fc  mov     rbx, qword ptr [rbp+FileSize]
0x140023600  cmp     ebx, 1000h
0x140023606  jbe     loc_140023720
0x14002360c  cmp     dword ptr [rbp+FileSize+4], esi
0x14002360f  jnz     loc_140023720
0x140023615  mov     edx, 10h; Alignment
0x14002361a  mov     rcx, rbx; Size
0x14002361d  call    _o__aligned_malloc_0
0x140023622  mov     [rbp+Block], rax
0x140023626  mov     rsi, rax
0x140023629  test    rax, rax
0x14002362c  jnz     short loc_14002363F
0x14002362e  lea     ebx, [rax+8]
0x140023631  jmp     loc_140023725
0x140023636  mov     rdi, [rbp+Block]
0x14002363a  jmp     loc_140023725
0x14002363f  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x140023643  mov     [rsp+30h+lpOverlapped], 0; lpOverlapped
0x14002364c  mov     r8d, ebx; nNumberOfBytesToRead
0x14002364f  mov     rdx, rax; lpBuffer
0x140023652  mov     rcx, rdi; hFile
0x140023655  call    cs:__imp_ReadFile
0x14002365c  nop     dword ptr [rax+rax+00h]
0x140023661  test    eax, eax
0x140023663  jnz     short loc_14002367B
0x140023665  call    cs:__imp_GetLastError
0x14002366c  nop     dword ptr [rax+rax+00h]
0x140023671  mov     ebx, eax
0x140023673  test    eax, eax
0x140023675  jnz     loc_140023725
0x14002367b  mov     r9, rdi
0x14002367e  lea     rdx, [rbp+FileSize]
0x140023682  mov     r8, r15
0x140023685  lea     rcx, [rbp+Block]
0x140023689  call    ValidateHiveAndRecoverFromLog
0x14002368e  mov     ebx, eax
0x140023690  test    eax, eax
0x140023692  jnz     short loc_1400236CC
0x140023694  test    r14b, r14b
0x140023697  jz      short loc_1400236A1
0x140023699  mov     rcx, rdi
0x14002369c  call    ORCloseFile
0x1400236a1  lea     rcx, ModuleName; "ntdll.dll"
0x1400236a8  xor     edi, edi
0x1400236aa  xor     r14b, r14b
0x1400236ad  call    cs:__imp_GetModuleHandleW
0x1400236b4  nop     dword ptr [rax+rax+00h]
0x1400236b9  test    rax, rax
0x1400236bc  jnz     short loc_1400236D2
0x1400236be  call    cs:__imp_GetLastError
0x1400236c5  nop     dword ptr [rax+rax+00h]
0x1400236ca  mov     ebx, eax
0x1400236cc  mov     rsi, [rbp+Block]
0x1400236d0  jmp     short loc_140023725
0x1400236d2  lea     rdx, aRtlvalidrelati; "RtlValidRelativeSecurityDescriptor"
0x1400236d9  mov     rcx, rax; hModule
0x1400236dc  call    cs:__imp_GetProcAddress
0x1400236e3  nop     dword ptr [rax+rax+00h]
0x1400236e8  mov     cs:ORValidRelativeSecurityDescriptor, rax
0x1400236ef  test    rax, rax
0x1400236f2  jz      short loc_1400236BE
0x1400236f4  mov     rdx, qword ptr [rbp+FileSize]
0x1400236f8  mov     r9, r12
0x1400236fb  mov     rcx, [rbp+Block]; Block
0x1400236ff  mov     r8, r15
0x140023702  call    OROpenHiveFromMemoryInternal
0x140023707  xor     esi, esi
0x140023709  mov     ebx, eax
0x14002370b  test    eax, eax
0x14002370d  jnz     short loc_140023725
0x14002370f  mov     rax, [r12]
0x140023713  mov     rcx, [rax+10h]
0x140023717  mov     [rcx+80h], rsi
0x14002371e  jmp     short loc_140023725
0x140023720  mov     ebx, 3F1h
0x140023725  test    rsi, rsi
0x140023728  jz      short loc_140023732
0x14002372a  mov     rcx, rsi; Block
0x14002372d  call    _aligned_free
0x140023732  test    r14b, r14b
0x140023735  jz      short loc_14002373F
0x140023737  mov     rcx, rdi
0x14002373a  call    ORCloseFile
0x14002373f  mov     eax, ebx
0x140023741  add     rsp, 30h
0x140023745  pop     r15
0x140023747  pop     r14
0x140023749  pop     r12
0x14002374b  pop     rdi
0x14002374c  pop     rsi
0x14002374d  pop     rbx
0x14002374e  pop     rbp
0x14002374f  retn
```
