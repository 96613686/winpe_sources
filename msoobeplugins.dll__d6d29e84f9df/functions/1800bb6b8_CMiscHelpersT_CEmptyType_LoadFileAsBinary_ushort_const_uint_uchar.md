# CMiscHelpersT<CEmptyType>::LoadFileAsBinary(ushort const *,uint *,uchar * *)

- ea: `0x1800bb6b8`
- end: `0x1800bb80e`
- name: `?LoadFileAsBinary@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAIPEAPEAE@Z`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800bb324`

## callees

- `0x180003df0`
- `0x1800ba518`
- `0x1800ba648`
- `0x1800bb6b8`
- `0x1800bb814`
- `0x1800bbbec`
- `0x1800bbc4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb756`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bb734`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bb734`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800bb7b8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800bb7b8`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800bb774`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800bb774`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::LoadFileAsBinary(const WCHAR *a1, DWORD *a2, _QWORD *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rbx
  HANDLE FileW; // rbx
  DWORD LastError; // eax
  DWORD FileSize; // eax
  DWORD v10; // edi
  void *v11; // r15
  void *v13; // [rsp+40h] [rbp-10h] BYREF
  __int64 v14; // [rsp+48h] [rbp-8h] BYREF
  DWORD FileSizeHigh; // [rsp+80h] [rbp+30h] BYREF
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+48h] BYREF

  v13 = 0;
  v14 = -1;
  NumberOfBytesRead = 0;
  FileSizeHigh = 0;
  if ( !a1 || !a2 || !a3 )
    goto LABEL_2;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  SH<void *,SH_FILENT>::Reset(&v14);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v14 = -1;
LABEL_8:
    LastError = GetLastError();
    v6 = (unsigned int)SErrorConverter::C_LR2HR(LastError);
    v5 = v6;
    goto LABEL_3;
  }
  v14 = (__int64)FileW;
  FileSize = GetFileSize(FileW, &FileSizeHigh);
  v10 = FileSize;
  if ( FileSize == -1 )
    goto LABEL_8;
  if ( !FileSizeHigh )
  {
    v11 = operator new(FileSize);
    SP<unsigned char,SP_CPP_ARRAY<unsigned char>>::Reset(&v13);
    v13 = v11;
    if ( !ReadFile(FileW, v11, v10, &NumberOfBytesRead, 0) )
      goto LABEL_8;
    if ( NumberOfBytesRead == v10 )
    {
      LODWORD(v6) = 0;
      *a2 = v10;
      v13 = 0;
      *a3 = v11;
      goto LABEL_15;
    }
    LODWORD(v6) = -2147418113;
    v5 = 2147549183LL;
  }
  else
  {
LABEL_2:
    v5 = 2147942487LL;
    LODWORD(v6) = -2147024809;
  }
LABEL_3:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
LABEL_15:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  SP<unsigned char,SP_CPP_ARRAY<unsigned char>>::Reset(&v13);
  SH<void *,SH_FILENT>::Reset(&v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800bb6b8  mov     [rsp-28h+arg_8], rbx
0x1800bb6bd  push    rbp
0x1800bb6be  push    rsi
0x1800bb6bf  push    rdi
0x1800bb6c0  push    r14
0x1800bb6c2  push    r15
0x1800bb6c4  mov     rbp, rsp
0x1800bb6c7  sub     rsp, 50h
0x1800bb6cb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800bb6cf  mov     [rbp+var_10], 0
0x1800bb6d7  mov     [rbp+var_8], rdi
0x1800bb6db  mov     rsi, r8
0x1800bb6de  mov     [rbp+NumberOfBytesRead], 0
0x1800bb6e5  mov     r14, rdx
0x1800bb6e8  mov     [rbp+FileSizeHigh], 0
0x1800bb6ef  test    rcx, rcx
0x1800bb6f2  jnz     short loc_1800BB705
0x1800bb6f4  mov     ecx, 80070057h
0x1800bb6f9  mov     ebx, ecx
0x1800bb6fb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800bb700  jmp     loc_1800BB7DF
0x1800bb705  test    r14, r14
0x1800bb708  jz      short loc_1800BB6F4
0x1800bb70a  test    rsi, rsi
0x1800bb70d  jz      short loc_1800BB6F4
0x1800bb70f  xor     r9d, r9d; lpSecurityAttributes
0x1800bb712  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x1800bb71b  mov     [rsp+50h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800bb723  mov     edx, 80000000h; dwDesiredAccess
0x1800bb728  mov     [rsp+50h+dwCreationDisposition], 3; dwCreationDisposition
0x1800bb730  lea     r8d, [r9+1]; dwShareMode
0x1800bb734  call    cs:__imp_CreateFileW
0x1800bb73a  lea     rcx, [rbp+var_8]
0x1800bb73e  mov     rbx, rax
0x1800bb741  call    ?Reset@?$SH@PEAXVSH_FILENT@@@@QEAAXXZ; SH<void *,SH_FILENT>::Reset(void)
0x1800bb746  lea     rax, [rbx+1]
0x1800bb74a  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800bb750  jnz     short loc_1800BB769
0x1800bb752  mov     [rbp+var_8], rdi
0x1800bb756  call    cs:__imp_GetLastError
0x1800bb75c  mov     ecx, eax; unsigned int
0x1800bb75e  call    ?C_LR2HR@SErrorConverter@@SAJK@Z; SErrorConverter::C_LR2HR(ulong)
0x1800bb763  mov     ebx, eax
0x1800bb765  mov     ecx, eax
0x1800bb767  jmp     short loc_1800BB6FB
0x1800bb769  lea     rdx, [rbp+FileSizeHigh]; lpFileSizeHigh
0x1800bb76d  mov     [rbp+var_8], rbx
0x1800bb771  mov     rcx, rbx; hFile
0x1800bb774  call    cs:__imp_GetFileSize
0x1800bb77a  mov     edi, eax
0x1800bb77c  cmp     eax, 0FFFFFFFFh
0x1800bb77f  jz      short loc_1800BB756
0x1800bb781  cmp     [rbp+FileSizeHigh], 0
0x1800bb785  jnz     loc_1800BB6F4
0x1800bb78b  mov     ecx, edi; Size
0x1800bb78d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bb792  lea     rcx, [rbp+var_10]
0x1800bb796  mov     r15, rax
0x1800bb799  call    ?Reset@?$SP@EV?$SP_CPP_ARRAY@E@@@@QEAAXXZ; SP<uchar,SP_CPP_ARRAY<uchar>>::Reset(void)
0x1800bb79e  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800bb7a2  mov     [rbp+var_10], r15
0x1800bb7a6  mov     r8d, edi; nNumberOfBytesToRead
0x1800bb7a9  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x1800bb7b2  mov     rdx, r15; lpBuffer
0x1800bb7b5  mov     rcx, rbx; hFile
0x1800bb7b8  call    cs:__imp_ReadFile
0x1800bb7be  test    eax, eax
0x1800bb7c0  jz      short loc_1800BB756
0x1800bb7c2  cmp     [rbp+NumberOfBytesRead], edi
0x1800bb7c5  jz      short loc_1800BB7D3
0x1800bb7c7  mov     ebx, 8000FFFFh
0x1800bb7cc  mov     ecx, ebx
0x1800bb7ce  jmp     loc_1800BB6FB
0x1800bb7d3  xor     ebx, ebx
0x1800bb7d5  mov     [r14], edi
0x1800bb7d8  mov     [rbp+var_10], rbx
0x1800bb7dc  mov     [rsi], r15
0x1800bb7df  mov     ecx, ebx
0x1800bb7e1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800bb7e6  lea     rcx, [rbp+var_10]
0x1800bb7ea  call    ?Reset@?$SP@EV?$SP_CPP_ARRAY@E@@@@QEAAXXZ; SP<uchar,SP_CPP_ARRAY<uchar>>::Reset(void)
0x1800bb7ef  lea     rcx, [rbp+var_8]
0x1800bb7f3  call    ?Reset@?$SH@PEAXVSH_FILENT@@@@QEAAXXZ; SH<void *,SH_FILENT>::Reset(void)
0x1800bb7f8  mov     eax, ebx
0x1800bb7fa  mov     rbx, [rsp+50h+arg_8]
0x1800bb802  add     rsp, 50h
0x1800bb806  pop     r15
0x1800bb808  pop     r14
0x1800bb80a  pop     rdi
0x1800bb80b  pop     rsi
0x1800bb80c  pop     rbp
0x1800bb80d  retn
```
