# CEnergyTaskHandler::PurgeOldFiles(ushort const *,ulong,ushort const *)

- ea: `0x18000200c`
- end: `0x180002295`
- name: `?PurgeOldFiles@CEnergyTaskHandler@@AEAAJPEBGK0@Z`
- size: `649`
- prototype: `__int64 __fastcall(CEnergyTaskHandler *this, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002c8c`

## callees

- `0x18000200c`
- `0x180003a86`
- `0x180003ac0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000221a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000221a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000223b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000223b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800020e9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800020e9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000217d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000217d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002208`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000210b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000210b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002282`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000212e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000212e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800020cd`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800021f5`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800020cd`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800021f5`

## pseudocode

```c
__int64 __fastcall CEnergyTaskHandler::PurgeOldFiles(
        CEnergyTaskHandler *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  __int64 v4; // r14
  WCHAR *v7; // r9
  __int64 v8; // rax
  const unsigned __int16 *v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // rcx
  signed int v12; // ebx
  HANDLE FirstFileW; // rsi
  signed int LastError; // eax
  unsigned __int64 v15; // rcx
  __int64 v16; // rcx
  WCHAR *v17; // rax
  const unsigned __int16 *v18; // r8
  __int64 v19; // rdx
  WCHAR *v20; // rcx
  signed int v21; // eax
  signed int v22; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-E0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPath[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR FileName[264]; // [rsp+490h] [rbp+390h] BYREF

  v4 = a3;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v7 = pszPath;
  SystemTimeAsFileTime = 0;
  v8 = 2147483646;
  v9 = a2;
  v10 = 260;
  do
  {
    if ( !v8 )
      break;
    if ( !*v9 )
      break;
    *v7++ = *v9++;
    --v8;
    --v10;
  }
  while ( v10 );
  v11 = v7 - 1;
  v12 = v10 == 0 ? 0x8007007A : 0;
  if ( v10 )
    v11 = v7;
  *v11 = 0;
  if ( v10 )
  {
    v12 = PathCchAppend(pszPath, 0x104u, a4);
    if ( v12 >= 0 )
    {
      FirstFileW = FindFirstFileW(pszPath, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        if ( GetLastError() == 2 )
        {
          return 0;
        }
        else
        {
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
        }
      }
      else
      {
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v15 = SystemTimeAsFileTime.dwLowDateTime
            + ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32)
            - 864000000000LL * v4;
        SystemTimeAsFileTime.dwLowDateTime -= 711573504 * v4;
        SystemTimeAsFileTime.dwHighDateTime = HIDWORD(v15);
        do
        {
          if ( (FindFileData.dwFileAttributes & 0x10) == 0
            && CompareFileTime(&FindFileData.ftCreationTime, &SystemTimeAsFileTime) == -1 )
          {
            v16 = 2147483646;
            v17 = FileName;
            v18 = a2;
            v19 = 260;
            do
            {
              if ( !v16 )
                break;
              if ( !*v18 )
                break;
              *v17++ = *v18++;
              --v16;
              --v19;
            }
            while ( v19 );
            v20 = v17 - 1;
            if ( v19 )
              v20 = v17;
            *v20 = 0;
            v12 = v19 == 0 ? 0x8007007A : 0;
            if ( !v19 )
              goto LABEL_29;
            v12 = PathCchAppend(FileName, 0x104u, FindFileData.cFileName);
            if ( v12 < 0 )
              goto LABEL_29;
            if ( !DeleteFileW(FileName) )
            {
              v21 = GetLastError();
              v12 = v21;
              goto LABEL_34;
            }
          }
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        v21 = GetLastError();
        v12 = v21;
        if ( v21 == 18 )
        {
          v12 = 0;
          goto LABEL_29;
        }
LABEL_34:
        if ( v21 > 0 )
          v12 = (unsigned __int16)v21 | 0x80070000;
LABEL_29:
        if ( !FindClose(FirstFileW) )
        {
          v22 = GetLastError();
          v12 = v22;
          if ( v22 > 0 )
            return (unsigned __int16)v22 | 0x80070000;
        }
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000200c  mov     [rsp-8+arg_0], rbx
0x180002011  push    rbp
0x180002012  push    rsi
0x180002013  push    rdi
0x180002014  push    r12
0x180002016  push    r13
0x180002018  push    r14
0x18000201a  push    r15
0x18000201c  lea     rbp, [rsp-5B0h]
0x180002024  sub     rsp, 6B0h
0x18000202b  mov     rax, cs:__security_cookie
0x180002032  xor     rax, rsp
0x180002035  mov     [rbp+5E0h+var_40], rax
0x18000203c  mov     r14d, r8d
0x18000203f  lea     rcx, [rsp+6E0h+FindFileData]; void *
0x180002044  mov     r15, rdx
0x180002047  mov     r8d, 250h; Size
0x18000204d  xor     edx, edx; Val
0x18000204f  mov     rdi, r9
0x180002052  call    memset_0
0x180002057  xor     r12d, r12d
0x18000205a  lea     r9, [rbp+5E0h+pszPath]
0x180002061  mov     r13d, 104h
0x180002067  mov     qword ptr [rsp+6E0h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18000206c  mov     eax, 7FFFFFFEh
0x180002071  mov     rcx, r15
0x180002074  mov     edx, r13d
0x180002077  test    rax, rax
0x18000207a  jz      short loc_18000209B
0x18000207c  movzx   r8d, word ptr [rcx]
0x180002080  test    r8w, r8w
0x180002084  jz      short loc_18000209B
0x180002086  mov     [r9], r8w
0x18000208a  add     rcx, 2
0x18000208e  add     r9, 2
0x180002092  dec     rax
0x180002095  sub     rdx, 1
0x180002099  jnz     short loc_180002077
0x18000209b  mov     rax, rdx
0x18000209e  lea     rcx, [r9-2]
0x1800020a2  neg     rax
0x1800020a5  sbb     ebx, ebx
0x1800020a7  not     ebx
0x1800020a9  and     ebx, 8007007Ah
0x1800020af  test    rdx, rdx
0x1800020b2  cmovnz  rcx, r9
0x1800020b6  mov     [rcx], r12w
0x1800020ba  jz      loc_180002256
0x1800020c0  mov     r8, rdi; pszMore
0x1800020c3  lea     rcx, [rbp+5E0h+pszPath]; pszPath
0x1800020ca  mov     rdx, r13; cchPath
0x1800020cd  call    cs:__imp_PathCchAppend
0x1800020d3  mov     ebx, eax
0x1800020d5  test    eax, eax
0x1800020d7  js      loc_180002256
0x1800020dd  lea     rdx, [rsp+6E0h+FindFileData]; lpFindFileData
0x1800020e2  lea     rcx, [rbp+5E0h+pszPath]; lpFileName
0x1800020e9  call    cs:__imp_FindFirstFileW
0x1800020ef  mov     rsi, rax
0x1800020f2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800020f6  jnz     short loc_180002129
0x1800020f8  call    cs:__imp_GetLastError
0x1800020fe  cmp     eax, 2
0x180002101  jnz     short loc_18000210B
0x180002103  mov     ebx, r12d
0x180002106  jmp     loc_180002256
0x18000210b  call    cs:__imp_GetLastError
0x180002111  mov     ebx, eax
0x180002113  test    eax, eax
0x180002115  jle     loc_180002256
0x18000211b  movzx   ebx, ax
0x18000211e  or      ebx, 80070000h
0x180002124  jmp     loc_180002256
0x180002129  lea     rcx, [rsp+6E0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000212e  call    cs:__imp_GetSystemTimeAsFileTime
0x180002134  mov     rcx, 0C92A69C000h
0x18000213e  mov     rax, r14
0x180002141  imul    rax, rcx
0x180002145  mov     ecx, [rsp+6E0h+SystemTimeAsFileTime.dwHighDateTime]
0x180002149  shl     rcx, 20h
0x18000214d  sub     rcx, rax
0x180002150  mov     eax, [rsp+6E0h+SystemTimeAsFileTime.dwLowDateTime]
0x180002154  add     rcx, rax
0x180002157  mov     [rsp+6E0h+SystemTimeAsFileTime.dwLowDateTime], ecx
0x18000215b  shr     rcx, 20h
0x18000215f  mov     [rsp+6E0h+SystemTimeAsFileTime.dwHighDateTime], ecx
0x180002163  test    byte ptr [rsp+6E0h+FindFileData.dwFileAttributes], 10h
0x180002168  mov     edi, 80070000h
0x18000216d  jnz     loc_180002212
0x180002173  lea     rdx, [rsp+6E0h+SystemTimeAsFileTime]; lpFileTime2
0x180002178  lea     rcx, [rsp+6E0h+FindFileData.ftCreationTime]; lpFileTime1
0x18000217d  call    cs:__imp_CompareFileTime
0x180002183  cmp     eax, 0FFFFFFFFh
0x180002186  jnz     loc_180002212
0x18000218c  mov     ecx, 7FFFFFFEh
0x180002191  lea     rax, [rbp+5E0h+FileName]
0x180002198  mov     r8, r15
0x18000219b  mov     rdx, r13
0x18000219e  test    rcx, rcx
0x1800021a1  jz      short loc_1800021C2
0x1800021a3  movzx   r9d, word ptr [r8]
0x1800021a7  test    r9w, r9w
0x1800021ab  jz      short loc_1800021C2
0x1800021ad  mov     [rax], r9w
0x1800021b1  add     r8, 2
0x1800021b5  add     rax, 2
0x1800021b9  dec     rcx
0x1800021bc  sub     rdx, 1
0x1800021c0  jnz     short loc_18000219E
0x1800021c2  test    rdx, rdx
0x1800021c5  lea     rcx, [rax-2]
0x1800021c9  cmovnz  rcx, rax
0x1800021cd  mov     rax, rdx
0x1800021d0  neg     rax
0x1800021d3  sbb     ebx, ebx
0x1800021d5  not     ebx
0x1800021d7  mov     [rcx], r12w
0x1800021db  and     ebx, 8007007Ah
0x1800021e1  test    rdx, rdx
0x1800021e4  jz      short loc_180002238
0x1800021e6  lea     r8, [rsp+6E0h+FindFileData.cFileName]; pszMore
0x1800021eb  mov     rdx, r13; cchPath
0x1800021ee  lea     rcx, [rbp+5E0h+FileName]; pszPath
0x1800021f5  call    cs:__imp_PathCchAppend
0x1800021fb  mov     ebx, eax
0x1800021fd  test    eax, eax
0x1800021ff  js      short loc_180002238
0x180002201  lea     rcx, [rbp+5E0h+FileName]; lpFileName
0x180002208  call    cs:__imp_DeleteFileW
0x18000220e  test    eax, eax
0x180002210  jz      short loc_180002282
0x180002212  lea     rdx, [rsp+6E0h+FindFileData]; lpFindFileData
0x180002217  mov     rcx, rsi; hFindFile
0x18000221a  call    cs:__imp_FindNextFileW
0x180002220  test    eax, eax
0x180002222  jnz     loc_180002163
0x180002228  call    cs:__imp_GetLastError
0x18000222e  mov     ebx, eax
0x180002230  cmp     eax, 12h
0x180002233  jnz     short loc_18000228A
0x180002235  mov     ebx, r12d
0x180002238  mov     rcx, rsi; hFindFile
0x18000223b  call    cs:__imp_FindClose
0x180002241  test    eax, eax
0x180002243  jnz     short loc_180002256
0x180002245  call    cs:__imp_GetLastError
0x18000224b  mov     ebx, eax
0x18000224d  test    eax, eax
0x18000224f  jle     short loc_180002256
0x180002251  movzx   ebx, ax
0x180002254  or      ebx, edi
0x180002256  mov     eax, ebx
0x180002258  mov     rcx, [rbp+5E0h+var_40]
0x18000225f  xor     rcx, rsp; StackCookie
0x180002262  call    __security_check_cookie
0x180002267  mov     rbx, [rsp+6E0h+arg_0]
0x18000226f  add     rsp, 6B0h
0x180002276  pop     r15
0x180002278  pop     r14
0x18000227a  pop     r13
0x18000227c  pop     r12
0x18000227e  pop     rdi
0x18000227f  pop     rsi
0x180002280  pop     rbp
0x180002281  retn
0x180002282  call    cs:__imp_GetLastError
0x180002288  mov     ebx, eax
0x18000228a  test    eax, eax
0x18000228c  jle     short loc_180002238
0x18000228e  movzx   ebx, ax
0x180002291  or      ebx, edi
0x180002293  jmp     short loc_180002238
```
