# DiagCreateCabContext(ushort const *,ushort const *,_DIAG_CAB_CONTEXT * *)

- ea: `0x18013a568`
- end: `0x18013a7e4`
- name: `?DiagCreateCabContext@@YAJPEBG0PEAPEAU_DIAG_CAB_CONTEXT@@@Z`
- size: `636`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, struct _DIAG_CAB_CONTEXT **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18013a7ec`

## callees

- `0x180015f98`
- `0x18013a568`
- `0x18013aa34`
- `0x18013ae9a`
- `0x18013aee0`

## import_xrefs

- `msvcrt!time` at `0x18013a5a5`
- `msvcrt!time` at `0x18013a5a5`
- `msvcrt!srand` at `0x18013a5ae`
- `msvcrt!srand` at `0x18013a5ae`
- `msvcrt!rand` at `0x18013a5fd`
- `msvcrt!rand` at `0x18013a5fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a6a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a6ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a6a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a6ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013a5c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013a627`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013a5c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013a627`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a5b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a616`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a7a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a5b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a616`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a7a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18013a7b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18013a7b2`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18013a696`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18013a6fd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18013a696`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18013a6fd`
- `Cabinet!__imp_FCICreate` at `0x18013a782`
- `Cabinet!__imp_FCICreate` at `0x18013a782`

## pseudocode

```c
__int64 __fastcall DiagCreateCabContext(const unsigned __int16 *a1, const unsigned __int16 *a2, ERF **a3)
{
  unsigned int v6; // eax
  HANDLE ProcessHeap; // rax
  ERF *pv; // rdi
  signed int v9; // ebx
  HANDLE v10; // rax
  unsigned __int16 *v11; // rax
  WCHAR *v12; // rsi
  signed int LastError; // eax
  HFCI v14; // rax
  HANDLE v15; // rax
  CCAB lpMultiByteStr; // [rsp+70h] [rbp-368h] BYREF

  memset_0(&lpMultiByteStr, 0, sizeof(lpMultiByteStr));
  v6 = time(0);
  srand(v6);
  ProcessHeap = GetProcessHeap();
  pv = (ERF *)HeapAlloc(ProcessHeap, 8u, 0x30u);
  if ( pv )
  {
    memset_0(&lpMultiByteStr.cbReserveCFHeader, 0, 0x31Cu);
    lpMultiByteStr.cb = 0x7FFFFFFF;
    lpMultiByteStr.cbFolderThresh = 0x7FFFFFFF;
    lpMultiByteStr.setID = rand();
    lpMultiByteStr.iDisk = 1;
    v10 = GetProcessHeap();
    v11 = (unsigned __int16 *)HeapAlloc(v10, 0, 0x208u);
    v12 = v11;
    if ( !v11 )
    {
      v9 = -2147024882;
      goto LABEL_16;
    }
    v9 = StringCchPrintfW(v11, 0x104u, L"%s\\", a1);
    if ( v9 >= 0 )
    {
      if ( WideCharToMultiByte(0xFDE9u, 0, v12, -1, lpMultiByteStr.szCabPath, 256, 0, 0)
        && WideCharToMultiByte(0xFDE9u, 0, a2, -1, lpMultiByteStr.szCab, 256, 0, 0) )
      {
        v14 = FCICreate(
                pv,
                HDataCollector::Cycle,
                DiagCabAlloc,
                DiagCabFree,
                DiagCabOpenFile,
                DiagCabReadFile,
                DiagCabWriteFile,
                DiagCabCloseFile,
                DiagCabSeekFile,
                DiagCabDeleteFile,
                (PFNFCIGETTEMPFILE)DiagCabGetTempFileName,
                &lpMultiByteStr,
                pv);
        *(_QWORD *)&pv[1].erfType = v14;
        if ( !v14 )
        {
          v9 = -2144337645;
          goto LABEL_15;
        }
        pv[3].erfType = 50;
        *a3 = pv;
        goto LABEL_14;
      }
      if ( !GetLastError() )
      {
LABEL_14:
        v9 = 0;
        goto LABEL_15;
      }
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
LABEL_15:
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v12);
    if ( v9 >= 0 )
      return (unsigned int)v9;
LABEL_16:
    DiagDestroyCabContext((struct _DIAG_CAB_CONTEXT *)pv);
    return (unsigned int)v9;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x18013a568  push    rbx
0x18013a56a  push    rbp
0x18013a56b  push    rsi
0x18013a56c  push    rdi
0x18013a56d  push    r14
0x18013a56f  sub     rsp, 3B0h
0x18013a576  mov     rax, cs:__security_cookie
0x18013a57d  xor     rax, rsp
0x18013a580  mov     [rsp+3D8h+var_38], rax
0x18013a588  mov     r14, r8
0x18013a58b  mov     rbp, rdx
0x18013a58e  mov     rbx, rcx
0x18013a591  xor     edx, edx; Val
0x18013a593  mov     r8d, 324h; Size
0x18013a599  lea     rcx, [rsp+3D8h+var_368]; void *
0x18013a59e  call    memset_0
0x18013a5a3  xor     ecx, ecx; Time
0x18013a5a5  call    cs:__imp_time
0x18013a5ab  mov     rcx, rax; Seed
0x18013a5ae  call    cs:__imp_srand
0x18013a5b4  call    cs:__imp_GetProcessHeap
0x18013a5ba  mov     edx, 8; dwFlags
0x18013a5bf  mov     rcx, rax; hHeap
0x18013a5c2  lea     r8d, [rdx+28h]; dwBytes
0x18013a5c6  call    cs:__imp_HeapAlloc
0x18013a5cc  mov     rdi, rax
0x18013a5cf  test    rax, rax
0x18013a5d2  jnz     short loc_18013A5DE
0x18013a5d4  mov     ebx, 8007000Eh
0x18013a5d9  jmp     loc_18013A7C4
0x18013a5de  xor     edx, edx; Val
0x18013a5e0  lea     rcx, [rsp+3D8h+var_368.cbReserveCFHeader]; void *
0x18013a5e5  mov     r8d, 31Ch; Size
0x18013a5eb  call    memset_0
0x18013a5f0  mov     eax, 7FFFFFFFh
0x18013a5f5  mov     [rsp+3D8h+var_368.cb], eax
0x18013a5f9  mov     [rsp+3D8h+var_368.cbFolderThresh], eax
0x18013a5fd  call    cs:__imp_rand
0x18013a603  mov     [rsp+3D8h+var_368.setID], ax
0x18013a60b  mov     [rsp+3D8h+var_368.iDisk], 1
0x18013a616  call    cs:__imp_GetProcessHeap
0x18013a61c  xor     edx, edx; dwFlags
0x18013a61e  mov     r8d, 208h; dwBytes
0x18013a624  mov     rcx, rax; hHeap
0x18013a627  call    cs:__imp_HeapAlloc
0x18013a62d  mov     rsi, rax
0x18013a630  test    rax, rax
0x18013a633  jnz     short loc_18013A63F
0x18013a635  mov     ebx, 8007000Eh
0x18013a63a  jmp     loc_18013A7BC
0x18013a63f  mov     r9, rbx
0x18013a642  lea     r8, aS_0; "%s\\"
0x18013a649  mov     edx, 104h; unsigned __int64
0x18013a64e  mov     rcx, rsi; unsigned __int16 *
0x18013a651  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18013a656  mov     ebx, eax
0x18013a658  test    eax, eax
0x18013a65a  js      loc_18013A7A4
0x18013a660  mov     [rsp+3D8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18013a669  lea     rax, [rsp+3D8h+var_368.szCabPath]
0x18013a671  mov     [rsp+3D8h+lpDefaultChar], 0; lpDefaultChar
0x18013a67a  mov     ebx, 100h
0x18013a67f  mov     [rsp+3D8h+cbMultiByte], ebx; cbMultiByte
0x18013a683  or      r9d, 0FFFFFFFFh; cchWideChar
0x18013a687  mov     r8, rsi; lpWideCharStr
0x18013a68a  mov     [rsp+3D8h+lpMultiByteStr], rax; lpMultiByteStr
0x18013a68f  xor     edx, edx; dwFlags
0x18013a691  mov     ecx, 0FDE9h; CodePage
0x18013a696  call    cs:__imp_WideCharToMultiByte
0x18013a69c  test    eax, eax
0x18013a69e  jnz     short loc_18013A6CC
0x18013a6a0  call    cs:__imp_GetLastError
0x18013a6a6  test    eax, eax
0x18013a6a8  jz      loc_18013A7A2
0x18013a6ae  call    cs:__imp_GetLastError
0x18013a6b4  mov     ebx, eax
0x18013a6b6  test    eax, eax
0x18013a6b8  jle     loc_18013A7A4
0x18013a6be  movzx   ebx, ax
0x18013a6c1  or      ebx, 80070000h
0x18013a6c7  jmp     loc_18013A7A4
0x18013a6cc  mov     [rsp+3D8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18013a6d5  lea     rax, [rsp+3D8h+var_368.szCab]
0x18013a6dd  mov     [rsp+3D8h+lpDefaultChar], 0; lpDefaultChar
0x18013a6e6  or      r9d, 0FFFFFFFFh; cchWideChar
0x18013a6ea  mov     [rsp+3D8h+cbMultiByte], ebx; cbMultiByte
0x18013a6ee  mov     r8, rbp; lpWideCharStr
0x18013a6f1  xor     edx, edx; dwFlags
0x18013a6f3  mov     [rsp+3D8h+lpMultiByteStr], rax; lpMultiByteStr
0x18013a6f8  mov     ecx, 0FDE9h; CodePage
0x18013a6fd  call    cs:__imp_WideCharToMultiByte
0x18013a703  test    eax, eax
0x18013a705  jz      short loc_18013A6A0
0x18013a707  mov     [rsp+3D8h+pv], rdi; pv
0x18013a70c  lea     rax, [rsp+3D8h+var_368]
0x18013a711  mov     [rsp+3D8h+pccab], rax; pccab
0x18013a716  lea     r9, ?DiagCabFree@@YAXPEAX@Z; pfnf
0x18013a71d  lea     rax, ?DiagCabGetTempFileName@@YAHPEADHPEAX@Z; DiagCabGetTempFileName(char *,int,void *)
0x18013a724  mov     rcx, rdi; perf
0x18013a727  mov     [rsp+3D8h+pfnfcigtf], rax; pfnfcigtf
0x18013a72c  lea     r8, ?DiagCabAlloc@@YAPEAXK@Z; pfna
0x18013a733  lea     rax, ?DiagCabDeleteFile@@YAHPEADPEAHPEAX@Z; DiagCabDeleteFile(char *,int *,void *)
0x18013a73a  mov     [rsp+3D8h+pfndelete], rax; pfndelete
0x18013a73f  lea     rdx, ?Cycle@HDataCollector@@UEAAJXZ; pfnfcifp
0x18013a746  lea     rax, ?DiagCabSeekFile@@YAJ_JJHPEAHPEAX@Z; DiagCabSeekFile(__int64,long,int,int *,void *)
0x18013a74d  mov     [rsp+3D8h+pfnseek], rax; pfnseek
0x18013a752  lea     rax, ?DiagCabCloseFile@@YAH_JPEAHPEAX@Z; DiagCabCloseFile(__int64,int *,void *)
0x18013a759  mov     [rsp+3D8h+lpUsedDefaultChar], rax; pfnclose
0x18013a75e  lea     rax, ?DiagCabWriteFile@@YAI_JPEAXIPEAH1@Z; DiagCabWriteFile(__int64,void *,uint,int *,void *)
0x18013a765  mov     [rsp+3D8h+lpDefaultChar], rax; pfnwrite
0x18013a76a  lea     rax, ?DiagCabReadFile@@YAI_JPEAXIPEAH1@Z; DiagCabReadFile(__int64,void *,uint,int *,void *)
0x18013a771  mov     qword ptr [rsp+3D8h+cbMultiByte], rax; pfnread
0x18013a776  lea     rax, ?DiagCabOpenFile@@YA_JPEADHHPEAHPEAX@Z; DiagCabOpenFile(char *,int,int,int *,void *)
0x18013a77d  mov     [rsp+3D8h+lpMultiByteStr], rax; pfnopen
0x18013a782  call    cs:__imp_FCICreate
0x18013a788  mov     [rdi+10h], rax
0x18013a78c  test    rax, rax
0x18013a78f  jnz     short loc_18013A798
0x18013a791  mov     ebx, 80300113h
0x18013a796  jmp     short loc_18013A7A4
0x18013a798  mov     dword ptr [rdi+28h], 32h ; '2'
0x18013a79f  mov     [r14], rdi
0x18013a7a2  xor     ebx, ebx
0x18013a7a4  call    cs:__imp_GetProcessHeap
0x18013a7aa  mov     r8, rsi; lpMem
0x18013a7ad  xor     edx, edx; dwFlags
0x18013a7af  mov     rcx, rax; hHeap
0x18013a7b2  call    cs:__imp_HeapFree
0x18013a7b8  test    ebx, ebx
0x18013a7ba  jns     short loc_18013A7C4
0x18013a7bc  mov     rcx, rdi; lpMem
0x18013a7bf  call    ?DiagDestroyCabContext@@YAJPEAU_DIAG_CAB_CONTEXT@@@Z; DiagDestroyCabContext(_DIAG_CAB_CONTEXT *)
0x18013a7c4  mov     eax, ebx
0x18013a7c6  mov     rcx, [rsp+3D8h+var_38]
0x18013a7ce  xor     rcx, rsp; StackCookie
0x18013a7d1  call    __security_check_cookie
0x18013a7d6  add     rsp, 3B0h
0x18013a7dd  pop     r14
0x18013a7df  pop     rdi
0x18013a7e0  pop     rsi
0x18013a7e1  pop     rbp
0x18013a7e2  pop     rbx
0x18013a7e3  retn
```
