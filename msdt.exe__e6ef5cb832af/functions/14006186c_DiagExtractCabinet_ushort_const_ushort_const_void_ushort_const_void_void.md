# DiagExtractCabinet(ushort const *,ushort const *,void (*)(ushort const *,void *),void *)

- ea: `0x14006186c`
- end: `0x140061b0e`
- name: `?DiagExtractCabinet@@YAJPEBG0P6AX0PEAX@Z1@Z`
- size: `674`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, void (*)(const unsigned __int16 *, void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140052f10`

## callees

- `0x140061724`
- `0x14006186c`
- `0x140061c90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140061998`
- `KERNEL32!GetLastError` at `0x140061998`
- `KERNEL32!HeapAlloc` at `0x14006195b`
- `KERNEL32!HeapAlloc` at `0x14006195b`
- `KERNEL32!HeapFree` at `0x140061a8d`
- `KERNEL32!HeapFree` at `0x140061ab2`
- `KERNEL32!HeapFree` at `0x140061ad7`
- `KERNEL32!HeapFree` at `0x140061a8d`
- `KERNEL32!HeapFree` at `0x140061ab2`
- `KERNEL32!HeapFree` at `0x140061ad7`
- `KERNEL32!GetProcessHeap` at `0x140061944`
- `KERNEL32!GetProcessHeap` at `0x140061a79`
- `KERNEL32!GetProcessHeap` at `0x140061a9e`
- `KERNEL32!GetProcessHeap` at `0x140061ac3`
- `KERNEL32!GetProcessHeap` at `0x140061944`
- `KERNEL32!GetProcessHeap` at `0x140061a79`
- `KERNEL32!GetProcessHeap` at `0x140061a9e`
- `KERNEL32!GetProcessHeap` at `0x140061ac3`
- `KERNEL32!GetFullPathNameW` at `0x140061988`
- `KERNEL32!GetFullPathNameW` at `0x140061988`
- `Cabinet!__imp_FDICreate` at `0x140061926`
- `Cabinet!__imp_FDICreate` at `0x140061926`
- `Cabinet!__imp_FDICopy` at `0x140061a41`
- `Cabinet!__imp_FDICopy` at `0x140061a41`
- `Cabinet!__imp_FDIDestroy` at `0x140061a5f`
- `Cabinet!__imp_FDIDestroy` at `0x140061a5f`

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
  HFDI v8; // r12
  signed int v9; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // rax
  WCHAR *v12; // rdi
  DWORD FullPathNameW; // eax
  signed int LastError; // eax
  int v15; // eax
  HANDLE v16; // rax
  HANDLE v17; // rax
  HANDLE v18; // rax
  LPSTR pszCabinet; // [rsp+50h] [rbp-19h] BYREF
  LPWSTR FilePart; // [rsp+58h] [rbp-11h] BYREF
  LPSTR pszCabPath; // [rsp+60h] [rbp-9h] BYREF
  __int128 pvUser; // [rsp+68h] [rbp-1h] BYREF
  const unsigned __int16 *v24; // [rsp+78h] [rbp+Fh]
  ERF perf; // [rsp+80h] [rbp+17h] BYREF

  v4 = 0;
  v5 = 0;
  pszCabinet = 0;
  pszCabPath = 0;
  FilePart = 0;
  *(_QWORD *)&perf.erfOper = 0;
  perf.fError = 0;
  v24 = 0;
  pvUser = 0;
  if ( lpFileName && a2 )
  {
    v8 = FDICreate(
           DiagCabAlloc,
           DiagCabFree,
           DiagCabFDIOpenFile,
           DiagCabFDIReadFile,
           DiagCabFDIWriteFile,
           DiagCabFDICloseFile,
           DiagCabFDISeekFile,
           -1,
           &perf);
    if ( !v8 )
      return (unsigned int)-2144337645;
    ProcessHeap = GetProcessHeap();
    v11 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
    v12 = v11;
    if ( v11 )
    {
      FullPathNameW = GetFullPathNameW(lpFileName, 0x400u, v11, &FilePart);
      if ( FullPathNameW )
      {
        if ( FullPathNameW < 0x400 )
        {
          if ( FilePart )
          {
            v9 = DiagDuplicateString(FilePart, &pszCabinet);
            if ( v9 < 0
              || (*FilePart = 0, v15 = DiagDuplicateString(v12, &pszCabPath), v5 = pszCabPath, v9 = v15, v15 < 0) )
            {
              v4 = pszCabinet;
            }
            else
            {
              pvUser = 0u;
              v4 = pszCabinet;
              v24 = a2;
              if ( !FDICopy(v8, pszCabinet, pszCabPath, 0, DiagCabFdiNotify, 0, &pvUser) )
                v9 = -2144337645;
            }
          }
          else
          {
            v9 = -2147024735;
          }
        }
        else
        {
          v9 = -2147024774;
        }
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v9 = -2147024882;
    }
    FDIDestroy(v8);
  }
  else
  {
    v12 = 0;
    v9 = -2147024809;
  }
  if ( v5 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v5);
  }
  if ( v4 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v4);
  }
  if ( v12 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v12);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14006186c  mov     [rsp-8+arg_10], rbx
0x140061871  mov     [rsp-8+arg_18], rsi
0x140061876  push    rbp
0x140061877  push    rdi
0x140061878  push    r12
0x14006187a  push    r14
0x14006187c  push    r15
0x14006187e  lea     rbp, [rsp-37h]
0x140061883  sub     rsp, 0A0h
0x14006188a  mov     rax, cs:__security_cookie
0x140061891  xor     rax, rsp
0x140061894  mov     [rbp+57h+var_30], rax
0x140061898  xor     eax, eax
0x14006189a  xor     esi, esi
0x14006189c  xor     r14d, r14d
0x14006189f  mov     [rbp+57h+pszCabinet], rsi
0x1400618a3  mov     [rbp+57h+pszCabPath], r14
0x1400618a7  xorps   xmm0, xmm0
0x1400618aa  mov     [rbp+57h+FilePart], rsi
0x1400618ae  mov     r15, rdx
0x1400618b1  mov     qword ptr [rbp+57h+var_40.erfOper], rax
0x1400618b5  mov     rbx, rcx
0x1400618b8  mov     [rbp+57h+var_40.fError], eax
0x1400618bb  mov     [rbp+57h+var_48], rax
0x1400618bf  movups  [rbp+57h+pvUser], xmm0
0x1400618c3  test    rcx, rcx
0x1400618c6  jz      loc_140061A6D
0x1400618cc  test    rdx, rdx
0x1400618cf  jz      loc_140061A6D
0x1400618d5  lea     rax, [rbp+57h+var_40]
0x1400618d9  mov     [rsp+0C0h+perf], rax; perf
0x1400618de  lea     r9, ?DiagCabFDIReadFile@@YAI_JPEAXI@Z; pfnread
0x1400618e5  mov     [rsp+0C0h+cpuType], 0FFFFFFFFh; cpuType
0x1400618ed  lea     rax, ?DiagCabFDISeekFile@@YAJ_JJH@Z; DiagCabFDISeekFile(__int64,long,int)
0x1400618f4  mov     [rsp+0C0h+pfnseek], rax; pfnseek
0x1400618f9  lea     r8, ?DiagCabFDIOpenFile@@YA_JPEADHH@Z; pfnopen
0x140061900  lea     rax, ?DiagCabFDICloseFile@@YAH_J@Z; DiagCabFDICloseFile(__int64)
0x140061907  mov     [rsp+0C0h+pfnclose], rax; pfnclose
0x14006190c  lea     rdx, ?DiagCabFree@@YAXPEAX@Z; pfnfree
0x140061913  lea     rax, ?DiagCabFDIWriteFile@@YAI_JPEAXI@Z; DiagCabFDIWriteFile(__int64,void *,uint)
0x14006191a  lea     rcx, ?DiagCabAlloc@@YAPEAXK@Z; pfnalloc
0x140061921  mov     [rsp+0C0h+pfnwrite], rax; pfnwrite
0x140061926  call    cs:__imp_FDICreate
0x14006192d  nop     dword ptr [rax+rax+00h]
0x140061932  mov     r12, rax
0x140061935  test    rax, rax
0x140061938  jnz     short loc_140061944
0x14006193a  mov     ebx, 80300113h
0x14006193f  jmp     loc_140061AE3
0x140061944  call    cs:__imp_GetProcessHeap
0x14006194b  nop     dword ptr [rax+rax+00h]
0x140061950  xor     edx, edx; dwFlags
0x140061952  mov     r8d, 800h; dwBytes
0x140061958  mov     rcx, rax; hHeap
0x14006195b  call    cs:__imp_HeapAlloc
0x140061962  nop     dword ptr [rax+rax+00h]
0x140061967  mov     rdi, rax
0x14006196a  test    rax, rax
0x14006196d  jnz     short loc_140061979
0x14006196f  mov     ebx, 8007000Eh
0x140061974  jmp     loc_140061A5C
0x140061979  lea     r9, [rbp+57h+FilePart]; lpFilePart
0x14006197d  mov     r8, rdi; lpBuffer
0x140061980  mov     edx, 400h; nBufferLength
0x140061985  mov     rcx, rbx; lpFileName
0x140061988  call    cs:__imp_GetFullPathNameW
0x14006198f  nop     dword ptr [rax+rax+00h]
0x140061994  test    eax, eax
0x140061996  jnz     short loc_1400619BC
0x140061998  call    cs:__imp_GetLastError
0x14006199f  nop     dword ptr [rax+rax+00h]
0x1400619a4  mov     ebx, eax
0x1400619a6  test    eax, eax
0x1400619a8  jle     loc_140061A5C
0x1400619ae  movzx   ebx, ax
0x1400619b1  or      ebx, 80070000h
0x1400619b7  jmp     loc_140061A5C
0x1400619bc  cmp     eax, 400h
0x1400619c1  jb      short loc_1400619CD
0x1400619c3  mov     ebx, 8007007Ah
0x1400619c8  jmp     loc_140061A5C
0x1400619cd  mov     rcx, [rbp+57h+FilePart]; lpWideCharStr
0x1400619d1  test    rcx, rcx
0x1400619d4  jnz     short loc_1400619DD
0x1400619d6  mov     ebx, 800700A1h
0x1400619db  jmp     short loc_140061A5C
0x1400619dd  lea     rdx, [rbp+57h+pszCabinet]; char **
0x1400619e1  call    ?DiagDuplicateString@@YAJPEBGPEAPEAD@Z; DiagDuplicateString(ushort const *,char * *)
0x1400619e6  mov     ebx, eax
0x1400619e8  test    eax, eax
0x1400619ea  js      short loc_140061A58
0x1400619ec  mov     rax, [rbp+57h+FilePart]
0x1400619f0  lea     rdx, [rbp+57h+pszCabPath]; char **
0x1400619f4  xor     ecx, ecx
0x1400619f6  mov     [rax], cx
0x1400619f9  mov     rcx, rdi; lpWideCharStr
0x1400619fc  call    ?DiagDuplicateString@@YAJPEBGPEAPEAD@Z; DiagDuplicateString(ushort const *,char * *)
0x140061a01  mov     r14, [rbp+57h+pszCabPath]
0x140061a05  mov     ebx, eax
0x140061a07  test    eax, eax
0x140061a09  js      short loc_140061A58
0x140061a0b  lea     rax, [rbp+57h+pvUser]
0x140061a0f  mov     qword ptr [rbp+57h+pvUser], rsi
0x140061a13  mov     [rsp+0C0h+pfnseek], rax; pvUser
0x140061a18  xor     r9d, r9d; flags
0x140061a1b  mov     [rsp+0C0h+pfnclose], rsi; pfnfdid
0x140061a20  lea     rax, ?DiagCabFdiNotify@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; DiagCabFdiNotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x140061a27  mov     qword ptr [rbp+57h+pvUser+8], rsi
0x140061a2b  mov     r8, r14; pszCabPath
0x140061a2e  mov     rsi, [rbp+57h+pszCabinet]
0x140061a32  mov     rcx, r12; hfdi
0x140061a35  mov     rdx, rsi; pszCabinet
0x140061a38  mov     [rbp+57h+var_48], r15
0x140061a3c  mov     [rsp+0C0h+pfnwrite], rax; pfnfdin
0x140061a41  call    cs:__imp_FDICopy
0x140061a48  nop     dword ptr [rax+rax+00h]
0x140061a4d  test    eax, eax
0x140061a4f  jnz     short loc_140061A5C
0x140061a51  mov     ebx, 80300113h
0x140061a56  jmp     short loc_140061A5C
0x140061a58  mov     rsi, [rbp+57h+pszCabinet]
0x140061a5c  mov     rcx, r12; hfdi
0x140061a5f  call    cs:__imp_FDIDestroy
0x140061a66  nop     dword ptr [rax+rax+00h]
0x140061a6b  jmp     short loc_140061A74
0x140061a6d  xor     edi, edi
0x140061a6f  mov     ebx, 80070057h
0x140061a74  test    r14, r14
0x140061a77  jz      short loc_140061A99
0x140061a79  call    cs:__imp_GetProcessHeap
0x140061a80  nop     dword ptr [rax+rax+00h]
0x140061a85  mov     r8, r14; lpMem
0x140061a88  xor     edx, edx; dwFlags
0x140061a8a  mov     rcx, rax; hHeap
0x140061a8d  call    cs:__imp_HeapFree
0x140061a94  nop     dword ptr [rax+rax+00h]
0x140061a99  test    rsi, rsi
0x140061a9c  jz      short loc_140061ABE
0x140061a9e  call    cs:__imp_GetProcessHeap
0x140061aa5  nop     dword ptr [rax+rax+00h]
0x140061aaa  mov     r8, rsi; lpMem
0x140061aad  xor     edx, edx; dwFlags
0x140061aaf  mov     rcx, rax; hHeap
0x140061ab2  call    cs:__imp_HeapFree
0x140061ab9  nop     dword ptr [rax+rax+00h]
0x140061abe  test    rdi, rdi
0x140061ac1  jz      short loc_140061AE3
0x140061ac3  call    cs:__imp_GetProcessHeap
0x140061aca  nop     dword ptr [rax+rax+00h]
0x140061acf  mov     r8, rdi; lpMem
0x140061ad2  xor     edx, edx; dwFlags
0x140061ad4  mov     rcx, rax; hHeap
0x140061ad7  call    cs:__imp_HeapFree
0x140061ade  nop     dword ptr [rax+rax+00h]
0x140061ae3  mov     eax, ebx
0x140061ae5  mov     rcx, [rbp+57h+var_30]
0x140061ae9  xor     rcx, rsp; StackCookie
0x140061aec  call    __security_check_cookie
0x140061af1  lea     r11, [rsp+0C0h+var_20]
0x140061af9  mov     rbx, [r11+40h]
0x140061afd  mov     rsi, [r11+48h]
0x140061b01  mov     rsp, r11
0x140061b04  pop     r15
0x140061b06  pop     r14
0x140061b08  pop     r12
0x140061b0a  pop     rdi
0x140061b0b  pop     rbp
0x140061b0c  retn
```
