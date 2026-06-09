# DiagExtractCabinet(ushort const *,ushort const *,void (*)(ushort const *,void *),void *)

- ea: `0x1800b98b8`
- end: `0x1800b9b09`
- name: `?DiagExtractCabinet@@YAJPEBG0P6AX0PEAX@Z1@Z`
- size: `593`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, void (*)(const unsigned __int16 *, void *), void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800b9800`
- `0x1801388f0`

## callees

- `0x1800b98b8`
- `0x18013aa70`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b99ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b99ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b999d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b999d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b998c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b9aa1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b9aba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b9ad3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b998c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b9aa1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b9aba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b9ad3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b9aaf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b9ac8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b9ae1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b9aaf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b9ac8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b9ae1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800b99c4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800b99c4`
- `Cabinet!__imp_FDICreate` at `0x1800b9974`
- `Cabinet!__imp_FDICreate` at `0x1800b9974`
- `Cabinet!__imp_FDICopy` at `0x1800b9a75`
- `Cabinet!__imp_FDICopy` at `0x1800b9a75`
- `Cabinet!__imp_FDIDestroy` at `0x1800b9a8d`
- `Cabinet!__imp_FDIDestroy` at `0x1800b9a8d`

## pseudocode

```c
__int64 __fastcall DiagExtractCabinet(
        LPCWSTR lpFileName,
        const unsigned __int16 *a2,
        void (*a3)(const unsigned __int16 *, void *),
        void *a4)
{
  LPSTR v4; // rsi
  LPSTR v5; // r14
  HFDI v9; // r12
  signed int v10; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v12; // rax
  WCHAR *v13; // rdi
  DWORD FullPathNameW; // eax
  signed int LastError; // eax
  int v16; // eax
  HANDLE v17; // rax
  HANDLE v18; // rax
  HANDLE v19; // rax
  LPSTR pszCabinet; // [rsp+50h] [rbp-39h] BYREF
  LPWSTR FilePart; // [rsp+58h] [rbp-31h] BYREF
  LPSTR pszCabPath; // [rsp+60h] [rbp-29h] BYREF
  void *v24; // [rsp+68h] [rbp-21h]
  __int128 pvUser; // [rsp+70h] [rbp-19h] BYREF
  const unsigned __int16 *v26; // [rsp+80h] [rbp-9h]
  ERF perf; // [rsp+88h] [rbp-1h] BYREF

  v24 = a4;
  v4 = 0;
  *(_QWORD *)&perf.erfOper = 0;
  v5 = 0;
  pszCabinet = 0;
  pszCabPath = 0;
  FilePart = 0;
  perf.fError = 0;
  v26 = 0;
  pvUser = 0;
  if ( lpFileName && a2 )
  {
    v9 = FDICreate(
           DiagCabAlloc,
           DiagCabFree,
           (PFNOPEN)DiagCabFDIOpenFile,
           (PFNREAD)DiagCabFDIReadFile,
           (PFNWRITE)DiagCabFDIWriteFile,
           DiagCabFDICloseFile,
           DiagCabFDISeekFile,
           -1,
           &perf);
    if ( !v9 )
      return (unsigned int)-2144337645;
    ProcessHeap = GetProcessHeap();
    v12 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
    v13 = v12;
    if ( v12 )
    {
      FullPathNameW = GetFullPathNameW(lpFileName, 0x400u, v12, &FilePart);
      if ( FullPathNameW )
      {
        if ( FullPathNameW < 0x400 )
        {
          if ( FilePart )
          {
            v10 = DiagDuplicateString(FilePart, &pszCabinet);
            if ( v10 < 0
              || (*FilePart = 0, v16 = DiagDuplicateString(v13, &pszCabPath), v5 = pszCabPath, v10 = v16, v16 < 0) )
            {
              v4 = pszCabinet;
            }
            else
            {
              *((_QWORD *)&pvUser + 1) = v24;
              v26 = a2;
              v4 = pszCabinet;
              *(_QWORD *)&pvUser = a3;
              if ( !FDICopy(v9, pszCabinet, pszCabPath, 0, (PFNFDINOTIFY)DiagCabFdiNotify, 0, &pvUser) )
                v10 = -2144337645;
            }
          }
          else
          {
            v10 = -2147024735;
          }
        }
        else
        {
          v10 = -2147024774;
        }
      }
      else
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v10 = -2147024882;
    }
    FDIDestroy(v9);
  }
  else
  {
    v13 = 0;
    v10 = -2147024809;
  }
  if ( v5 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v5);
  }
  if ( v4 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v4);
  }
  if ( v13 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v13);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800b98b8  push    rbp
0x1800b98ba  push    rbx
0x1800b98bb  push    rsi
0x1800b98bc  push    rdi
0x1800b98bd  push    r12
0x1800b98bf  push    r13
0x1800b98c1  push    r14
0x1800b98c3  push    r15
0x1800b98c5  lea     rbp, [rsp-1Fh]
0x1800b98ca  sub     rsp, 0A8h
0x1800b98d1  mov     rax, cs:__security_cookie
0x1800b98d8  xor     rax, rsp
0x1800b98db  mov     [rbp+57h+var_48], rax
0x1800b98df  xor     eax, eax
0x1800b98e1  mov     [rbp+57h+var_78], r9
0x1800b98e5  xor     esi, esi
0x1800b98e7  mov     qword ptr [rbp+57h+var_58.erfOper], rax
0x1800b98eb  xor     r14d, r14d
0x1800b98ee  mov     [rbp+57h+pszCabinet], rsi
0x1800b98f2  mov     [rbp+57h+pszCabPath], r14
0x1800b98f6  xorps   xmm0, xmm0
0x1800b98f9  mov     [rbp+57h+FilePart], rsi
0x1800b98fd  mov     r13, r8
0x1800b9900  mov     [rbp+57h+var_58.fError], eax
0x1800b9903  mov     r15, rdx
0x1800b9906  mov     [rbp+57h+var_60], rax
0x1800b990a  mov     rbx, rcx
0x1800b990d  movups  [rbp+57h+pvUser], xmm0
0x1800b9911  test    rcx, rcx
0x1800b9914  jz      loc_1800B9A95
0x1800b991a  test    rdx, rdx
0x1800b991d  jz      loc_1800B9A95
0x1800b9923  lea     rax, [rbp+57h+var_58]
0x1800b9927  mov     [rsp+0E0h+perf], rax; perf
0x1800b992c  lea     r9, ?DiagCabFDIReadFile@@YAI_JPEAXI@Z; pfnread
0x1800b9933  mov     [rsp+0E0h+cpuType], 0FFFFFFFFh; cpuType
0x1800b993b  lea     rax, ?DiagCabFDISeekFile@@YAJ_JJH@Z; DiagCabFDISeekFile(__int64,long,int)
0x1800b9942  mov     [rsp+0E0h+pfnseek], rax; pfnseek
0x1800b9947  lea     r8, ?DiagCabFDIOpenFile@@YA_JPEADHH@Z; pfnopen
0x1800b994e  lea     rax, ?DiagCabFDICloseFile@@YAH_J@Z; DiagCabFDICloseFile(__int64)
0x1800b9955  mov     [rsp+0E0h+pfnclose], rax; pfnclose
0x1800b995a  lea     rdx, ?DiagCabFree@@YAXPEAX@Z; pfnfree
0x1800b9961  lea     rax, ?DiagCabFDIWriteFile@@YAI_JPEAXI@Z; DiagCabFDIWriteFile(__int64,void *,uint)
0x1800b9968  lea     rcx, ?DiagCabAlloc@@YAPEAXK@Z; pfnalloc
0x1800b996f  mov     [rsp+0E0h+pfnwrite], rax; pfnwrite
0x1800b9974  call    cs:__imp_FDICreate
0x1800b997a  mov     r12, rax
0x1800b997d  test    rax, rax
0x1800b9980  jnz     short loc_1800B998C
0x1800b9982  mov     ebx, 80300113h
0x1800b9987  jmp     loc_1800B9AE7
0x1800b998c  call    cs:__imp_GetProcessHeap
0x1800b9992  xor     edx, edx; dwFlags
0x1800b9994  mov     r8d, 800h; dwBytes
0x1800b999a  mov     rcx, rax; hHeap
0x1800b999d  call    cs:__imp_HeapAlloc
0x1800b99a3  mov     rdi, rax
0x1800b99a6  test    rax, rax
0x1800b99a9  jnz     short loc_1800B99B5
0x1800b99ab  mov     ebx, 8007000Eh
0x1800b99b0  jmp     loc_1800B9A8A
0x1800b99b5  lea     r9, [rbp+57h+FilePart]; lpFilePart
0x1800b99b9  mov     r8, rdi; lpBuffer
0x1800b99bc  mov     edx, 400h; nBufferLength
0x1800b99c1  mov     rcx, rbx; lpFileName
0x1800b99c4  call    cs:__imp_GetFullPathNameW
0x1800b99ca  test    eax, eax
0x1800b99cc  jnz     short loc_1800B99EC
0x1800b99ce  call    cs:__imp_GetLastError
0x1800b99d4  mov     ebx, eax
0x1800b99d6  test    eax, eax
0x1800b99d8  jle     loc_1800B9A8A
0x1800b99de  movzx   ebx, ax
0x1800b99e1  or      ebx, 80070000h
0x1800b99e7  jmp     loc_1800B9A8A
0x1800b99ec  cmp     eax, 400h
0x1800b99f1  jb      short loc_1800B99FD
0x1800b99f3  mov     ebx, 8007007Ah
0x1800b99f8  jmp     loc_1800B9A8A
0x1800b99fd  mov     rcx, [rbp+57h+FilePart]; lpWideCharStr
0x1800b9a01  test    rcx, rcx
0x1800b9a04  jnz     short loc_1800B9A0D
0x1800b9a06  mov     ebx, 800700A1h
0x1800b9a0b  jmp     short loc_1800B9A8A
0x1800b9a0d  lea     rdx, [rbp+57h+pszCabinet]; char **
0x1800b9a11  call    ?DiagDuplicateString@@YAJPEBGPEAPEAD@Z; DiagDuplicateString(ushort const *,char * *)
0x1800b9a16  mov     ebx, eax
0x1800b9a18  test    eax, eax
0x1800b9a1a  js      short loc_1800B9A86
0x1800b9a1c  mov     rax, [rbp+57h+FilePart]
0x1800b9a20  lea     rdx, [rbp+57h+pszCabPath]; char **
0x1800b9a24  xor     ecx, ecx
0x1800b9a26  mov     [rax], cx
0x1800b9a29  mov     rcx, rdi; lpWideCharStr
0x1800b9a2c  call    ?DiagDuplicateString@@YAJPEBGPEAPEAD@Z; DiagDuplicateString(ushort const *,char * *)
0x1800b9a31  mov     r14, [rbp+57h+pszCabPath]
0x1800b9a35  mov     ebx, eax
0x1800b9a37  test    eax, eax
0x1800b9a39  js      short loc_1800B9A86
0x1800b9a3b  mov     rax, [rbp+57h+var_78]
0x1800b9a3f  xor     r9d, r9d; flags
0x1800b9a42  mov     qword ptr [rbp+57h+pvUser+8], rax
0x1800b9a46  mov     r8, r14; pszCabPath
0x1800b9a49  lea     rax, [rbp+57h+pvUser]
0x1800b9a4d  mov     [rbp+57h+var_60], r15
0x1800b9a51  mov     [rsp+0E0h+pfnseek], rax; pvUser
0x1800b9a56  mov     rcx, r12; hfdi
0x1800b9a59  mov     [rsp+0E0h+pfnclose], rsi; pfnfdid
0x1800b9a5e  lea     rax, ?DiagCabFdiNotify@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; DiagCabFdiNotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x1800b9a65  mov     rsi, [rbp+57h+pszCabinet]
0x1800b9a69  mov     rdx, rsi; pszCabinet
0x1800b9a6c  mov     qword ptr [rbp+57h+pvUser], r13
0x1800b9a70  mov     [rsp+0E0h+pfnwrite], rax; pfnfdin
0x1800b9a75  call    cs:__imp_FDICopy
0x1800b9a7b  test    eax, eax
0x1800b9a7d  jnz     short loc_1800B9A8A
0x1800b9a7f  mov     ebx, 80300113h
0x1800b9a84  jmp     short loc_1800B9A8A
0x1800b9a86  mov     rsi, [rbp+57h+pszCabinet]
0x1800b9a8a  mov     rcx, r12; hfdi
0x1800b9a8d  call    cs:__imp_FDIDestroy
0x1800b9a93  jmp     short loc_1800B9A9C
0x1800b9a95  xor     edi, edi
0x1800b9a97  mov     ebx, 80070057h
0x1800b9a9c  test    r14, r14
0x1800b9a9f  jz      short loc_1800B9AB5
0x1800b9aa1  call    cs:__imp_GetProcessHeap
0x1800b9aa7  mov     r8, r14; lpMem
0x1800b9aaa  xor     edx, edx; dwFlags
0x1800b9aac  mov     rcx, rax; hHeap
0x1800b9aaf  call    cs:__imp_HeapFree
0x1800b9ab5  test    rsi, rsi
0x1800b9ab8  jz      short loc_1800B9ACE
0x1800b9aba  call    cs:__imp_GetProcessHeap
0x1800b9ac0  mov     r8, rsi; lpMem
0x1800b9ac3  xor     edx, edx; dwFlags
0x1800b9ac5  mov     rcx, rax; hHeap
0x1800b9ac8  call    cs:__imp_HeapFree
0x1800b9ace  test    rdi, rdi
0x1800b9ad1  jz      short loc_1800B9AE7
0x1800b9ad3  call    cs:__imp_GetProcessHeap
0x1800b9ad9  mov     r8, rdi; lpMem
0x1800b9adc  xor     edx, edx; dwFlags
0x1800b9ade  mov     rcx, rax; hHeap
0x1800b9ae1  call    cs:__imp_HeapFree
0x1800b9ae7  mov     eax, ebx
0x1800b9ae9  mov     rcx, [rbp+57h+var_48]
0x1800b9aed  xor     rcx, rsp; StackCookie
0x1800b9af0  call    __security_check_cookie
0x1800b9af5  add     rsp, 0A8h
0x1800b9afc  pop     r15
0x1800b9afe  pop     r14
0x1800b9b00  pop     r13
0x1800b9b02  pop     r12
0x1800b9b04  pop     rdi
0x1800b9b05  pop     rsi
0x1800b9b06  pop     rbx
0x1800b9b07  pop     rbp
0x1800b9b08  retn
```
