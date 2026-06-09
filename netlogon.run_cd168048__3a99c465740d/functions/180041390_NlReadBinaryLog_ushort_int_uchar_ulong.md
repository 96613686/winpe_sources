# NlReadBinaryLog(ushort *,int,uchar * *,ulong *)

- ea: `0x180041390`
- end: `0x1800416ec`
- name: `?NlReadBinaryLog@@YAKPEAGHPEAPEAEPEAK@Z`
- size: `860`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, unsigned __int8 **, unsigned int *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180017a44`
- `0x18001d6a4`
- `0x1800218bc`
- `0x18006b978`

## callees

- `0x180003340`
- `0x180007518`
- `0x18000e910`
- `0x180041390`
- `0x180091010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800414cf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800414cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004151c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004155e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800415fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004151c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004155e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800415fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041687`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004165e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004165e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800415b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800415b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004164a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004164a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180041451`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180041451`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18004154b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18004154b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041507`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041507`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180041677`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180041677`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800415ea`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800415ea`

## string_xrefs

- `0x18004146f`: `NlWriteBinaryLog: Unable to GetSystemWindowsDirectoryW (%ld)\n`
- `0x1800414a9`: `NlWriteBinaryLog: file name length is too long \n`
- `0x18004152b`: `%ws: Unable to open. %ld\n`
- `0x180041596`: `NlReadBinaryLog: %ws: size too small: %ld.\n`
- `0x18004160e`: `NlReadBinaryLog: %ws: Cannot ReadFile: %ld.\n`
- `0x180041636`: `NlReadBinaryLog: %ws: Cannot read entire File: %ld %ld.\n`
- `0x18004169b`: `Cannot delete %ws (%ld)\n`

## pseudocode

```c
__int64 __fastcall NlReadBinaryLog(unsigned __int16 *a1, int a2, HLOCAL *a3, unsigned int *a4)
{
  bool v5; // cf
  __int64 LastError; // rdi
  char v10; // r12
  void *v11; // rsp
  WCHAR *v12; // rbx
  WCHAR *v13; // rax
  UINT SystemWindowsDirectoryW; // eax
  __int64 v15; // rcx
  HANDLE FileW; // rax
  void *v17; // r15
  DWORD v18; // eax
  DWORD FileSize; // eax
  unsigned __int8 *v20; // rax
  DWORD v21; // eax
  DWORD v22; // eax
  __int64 v24; // [rsp-20h] [rbp-260h] BYREF
  DWORD dwCreationDisposition[2]; // [rsp+0h] [rbp-240h]
  int v26; // [rsp+20h] [rbp-220h]
  _BYTE v27[472]; // [rsp+28h] [rbp-218h] BYREF
  DWORD NumberOfBytesRead; // [rsp+240h] [rbp+0h] BYREF

  NumberOfBytesRead = 0;
  v5 = (unsigned __int64)g_ulMaxStackAllocSize < 0x20A;
  *a3 = 0;
  LODWORD(LastError) = 8;
  *a4 = 0;
  v10 = 0;
  if ( !v5
    && (unsigned __int64)(g_ulAdditionalProbeSize + 530) >= 0x20A
    && (unsigned int)VerifyStackAvailable()
    && (v11 = alloca(544), &v24 != (__int64 *)-64LL)
    && (v26 = 1801679955, (v12 = (WCHAR *)v27) != 0)
    || (v13 = (WCHAR *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(530), (v12 = v13) != 0)
    && (*(_DWORD *)v13 = 1885431112, v12 = v13 + 4, v13 != (WCHAR *)-8LL) )
  {
    SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(v12, 0x105u);
    if ( !SystemWindowsDirectoryW )
    {
      LastError = GetLastError();
      NlPrintRoutine(0x100u, L"NlWriteBinaryLog: Unable to GetSystemWindowsDirectoryW (%ld)\n", LastError);
      goto LABEL_29;
    }
    v15 = -1;
    do
      ++v15;
    while ( a1[v15] );
    if ( (unsigned __int64)SystemWindowsDirectoryW + v15 + 1 >= 0x104 )
    {
      NlPrintRoutine(0x100u, L"NlWriteBinaryLog: file name length is too long \n");
      LODWORD(LastError) = 123;
      goto LABEL_29;
    }
    _o_wcscat_s(v12, 261, a1);
    v10 = 1;
    FileW = CreateFileW(v12, 0x80000000, 3u, 0, 3u, 0x80u, 0);
    v17 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v18 = GetLastError();
      NlPrintRoutine(0x100u, L"%ws: Unable to open. %ld\n", v12, v18);
      LODWORD(LastError) = 0;
      goto LABEL_29;
    }
    FileSize = GetFileSize(FileW, 0);
    *a4 = FileSize;
    if ( FileSize == -1 )
    {
      LastError = GetLastError();
      NlPrintRoutine(0x100u, L"%ws: Unable to GetFileSize: %ld \n", v12, LastError);
      *a4 = 0;
    }
    else if ( FileSize )
    {
      v20 = (unsigned __int8 *)LocalAlloc(0, FileSize);
      *a3 = v20;
      if ( v20 )
      {
        LODWORD(LastError) = 0;
        if ( ReadFile(v17, v20, *a4, &NumberOfBytesRead, 0) )
        {
          if ( NumberOfBytesRead == *a4 )
            goto LABEL_28;
          dwCreationDisposition[0] = *a4;
          NlPrintRoutine(0x100u, L"NlReadBinaryLog: %ws: Cannot read entire File: %ld %ld.\n", v12);
        }
        else
        {
          v21 = GetLastError();
          if ( v21 != 2 )
            NlPrintRoutine(0x100u, L"NlReadBinaryLog: %ws: Cannot ReadFile: %ld.\n", v12, v21);
        }
        LocalFree(*a3);
        *a4 = 0;
        *a3 = 0;
        goto LABEL_28;
      }
      *a4 = 0;
    }
    else
    {
      NlPrintRoutine(0x100u, L"NlReadBinaryLog: %ws: size too small: %ld.\n", v12, 0);
      *a4 = 0;
      LODWORD(LastError) = 0;
    }
LABEL_28:
    CloseHandle(v17);
  }
LABEL_29:
  if ( a2 )
  {
    if ( v10 )
    {
      if ( !DeleteFileW(v12) )
      {
        v22 = GetLastError();
        if ( v22 != 2 )
          NlPrintRoutine(0x100u, L"Cannot delete %ws (%ld)\n", v12, v22);
      }
    }
  }
  if ( v12 && *((_DWORD *)v12 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180041390  push    rbp
0x180041392  push    rbx
0x180041393  push    rsi
0x180041394  push    rdi
0x180041395  push    r12
0x180041397  push    r13
0x180041399  push    r14
0x18004139b  push    r15
0x18004139d  sub     rsp, 68h
0x1800413a1  lea     rbp, [rsp+40h]
0x1800413a6  mov     rax, cs:__security_cookie
0x1800413ad  xor     rax, rbp
0x1800413b0  mov     [rbp+60h+var_50], rax
0x1800413b4  xor     ebx, ebx
0x1800413b6  mov     r13d, edx
0x1800413b9  mov     edx, 20Ah
0x1800413be  mov     [rbp+60h+NumberOfBytesRead], ebx
0x1800413c1  cmp     cs:g_ulMaxStackAllocSize, rdx
0x1800413c8  mov     rsi, r9
0x1800413cb  mov     r14, r8
0x1800413ce  mov     [r8], rbx
0x1800413d1  lea     edi, [rbx+8]
0x1800413d4  mov     [r9], ebx
0x1800413d7  mov     r15, rcx
0x1800413da  mov     r12b, bl
0x1800413dd  jb      short loc_18004141D
0x1800413df  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800413e6  add     rcx, 212h
0x1800413ed  cmp     rcx, rdx
0x1800413f0  jb      short loc_18004141D
0x1800413f2  call    VerifyStackAvailable
0x1800413f7  test    eax, eax
0x1800413f9  jz      short loc_18004141D
0x1800413fb  mov     eax, [rsp+0A0h+var_A0]
0x1800413fe  mov     eax, 220h
0x180041403  sub     rsp, rax
0x180041406  lea     rbx, [rsp+2C0h+var_280]
0x18004140b  mov     eax, [rbx]
0x18004140d  test    rbx, rbx
0x180041410  jz      short loc_18004141D
0x180041412  mov     dword ptr [rbx], 6B637453h
0x180041418  add     rbx, rdi
0x18004141b  jnz     short loc_180041449
0x18004141d  mov     rax, cs:g_pfnAllocate
0x180041424  mov     ecx, 212h
0x180041429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004142e  mov     rbx, rax
0x180041431  test    rax, rax
0x180041434  jz      loc_18004166A
0x18004143a  mov     dword ptr [rax], 70616548h
0x180041440  add     rbx, rdi
0x180041443  jz      loc_18004166A
0x180041449  mov     edx, 105h; uSize
0x18004144e  mov     rcx, rbx; lpBuffer
0x180041451  call    cs:__imp_GetSystemWindowsDirectoryW
0x180041458  nop     dword ptr [rax+rax+00h]
0x18004145d  xor     edx, edx
0x18004145f  test    eax, eax
0x180041461  jnz     short loc_18004148A
0x180041463  call    cs:__imp_GetLastError
0x18004146a  nop     dword ptr [rax+rax+00h]
0x18004146f  lea     rdx, aNlwritebinaryl; "NlWriteBinaryLog: Unable to GetSystemWi"...
0x180041476  mov     ecx, 100h; unsigned int
0x18004147b  mov     r8d, eax
0x18004147e  mov     edi, eax
0x180041480  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180041485  jmp     loc_18004166A
0x18004148a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004148e  inc     rcx
0x180041491  cmp     [r15+rcx*2], dx
0x180041496  jnz     short loc_18004148E
0x180041498  inc     rcx
0x18004149b  mov     eax, eax
0x18004149d  add     rcx, rax
0x1800414a0  cmp     rcx, 104h
0x1800414a7  jb      short loc_1800414C4
0x1800414a9  lea     rdx, aNlwritebinaryl_0; "NlWriteBinaryLog: file name length is t"...
0x1800414b0  mov     ecx, 100h; unsigned int
0x1800414b5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800414ba  mov     edi, 7Bh ; '{'
0x1800414bf  jmp     loc_18004166A
0x1800414c4  mov     r8, r15
0x1800414c7  mov     edx, 105h
0x1800414cc  mov     rcx, rbx
0x1800414cf  call    cs:__imp__o_wcscat_s
0x1800414d6  nop     dword ptr [rax+rax+00h]
0x1800414db  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x1800414e4  mov     r12d, 1
0x1800414ea  mov     [rsp+2C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800414f2  xor     r9d, r9d; lpSecurityAttributes
0x1800414f5  mov     edx, 80000000h; dwDesiredAccess
0x1800414fa  mov     rcx, rbx; lpFileName
0x1800414fd  lea     r8d, [r12+2]; dwShareMode
0x180041502  mov     [rsp+2C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180041507  call    cs:__imp_CreateFileW
0x18004150e  nop     dword ptr [rax+rax+00h]
0x180041513  mov     r15, rax
0x180041516  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004151a  jnz     short loc_180041546
0x18004151c  call    cs:__imp_GetLastError
0x180041523  nop     dword ptr [rax+rax+00h]
0x180041528  mov     r8, rbx
0x18004152b  lea     rdx, aWsUnableToOpen; "%ws: Unable to open. %ld\n"
0x180041532  mov     r9d, eax
0x180041535  mov     ecx, 100h; unsigned int
0x18004153a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004153f  xor     edi, edi
0x180041541  jmp     loc_18004166A
0x180041546  xor     edx, edx; lpFileSizeHigh
0x180041548  mov     rcx, r15; hFile
0x18004154b  call    cs:__imp_GetFileSize
0x180041552  nop     dword ptr [rax+rax+00h]
0x180041557  mov     [rsi], eax
0x180041559  cmp     eax, 0FFFFFFFFh
0x18004155c  jnz     short loc_18004158E
0x18004155e  call    cs:__imp_GetLastError
0x180041565  nop     dword ptr [rax+rax+00h]
0x18004156a  mov     r8, rbx
0x18004156d  lea     rdx, aWsUnableToGetf; "%ws: Unable to GetFileSize: %ld \n"
0x180041574  mov     r9d, eax
0x180041577  mov     ecx, 100h; unsigned int
0x18004157c  mov     edi, eax
0x18004157e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180041583  mov     dword ptr [rsi], 0
0x180041589  jmp     loc_18004165B
0x18004158e  cmp     eax, r12d
0x180041591  jnb     short loc_1800415B5
0x180041593  mov     r9d, eax
0x180041596  lea     rdx, aNlreadbinarylo_1; "NlReadBinaryLog: %ws: size too small: %"...
0x18004159d  mov     r8, rbx
0x1800415a0  mov     ecx, 100h; unsigned int
0x1800415a5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800415aa  xor     eax, eax
0x1800415ac  mov     [rsi], eax
0x1800415ae  mov     edi, eax
0x1800415b0  jmp     loc_18004165B
0x1800415b5  mov     edx, eax; uBytes
0x1800415b7  xor     ecx, ecx; uFlags
0x1800415b9  call    cs:__imp_LocalAlloc
0x1800415c0  nop     dword ptr [rax+rax+00h]
0x1800415c5  xor     ecx, ecx
0x1800415c7  mov     [r14], rax
0x1800415ca  test    rax, rax
0x1800415cd  jnz     short loc_1800415D6
0x1800415cf  mov     [rsi], ecx
0x1800415d1  jmp     loc_18004165B
0x1800415d6  mov     r8d, [rsi]; nNumberOfBytesToRead
0x1800415d9  lea     r9, [rbp+60h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800415dd  xor     edi, edi
0x1800415df  mov     rdx, rax; lpBuffer
0x1800415e2  mov     rcx, r15; hFile
0x1800415e5  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rdi; lpOverlapped
0x1800415ea  call    cs:__imp_ReadFile
0x1800415f1  nop     dword ptr [rax+rax+00h]
0x1800415f6  test    eax, eax
0x1800415f8  jnz     short loc_180041624
0x1800415fa  call    cs:__imp_GetLastError
0x180041601  nop     dword ptr [rax+rax+00h]
0x180041606  cmp     eax, 2
0x180041609  jz      short loc_180041647
0x18004160b  mov     r9d, eax
0x18004160e  lea     rdx, aNlreadbinarylo; "NlReadBinaryLog: %ws: Cannot ReadFile: "...
0x180041615  mov     r8, rbx
0x180041618  mov     ecx, 100h; unsigned int
0x18004161d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180041622  jmp     short loc_180041647
0x180041624  mov     eax, [rsi]
0x180041626  mov     r9d, [rbp+60h+NumberOfBytesRead]
0x18004162a  cmp     r9d, eax
0x18004162d  jz      short loc_18004165B
0x18004162f  mov     r8, rbx
0x180041632  mov     [rsp+2C0h+dwCreationDisposition], eax
0x180041636  lea     rdx, aNlreadbinarylo_0; "NlReadBinaryLog: %ws: Cannot read entir"...
0x18004163d  mov     ecx, 100h; unsigned int
0x180041642  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180041647  mov     rcx, [r14]; hMem
0x18004164a  call    cs:__imp_LocalFree
0x180041651  nop     dword ptr [rax+rax+00h]
0x180041656  mov     [rsi], edi
0x180041658  mov     [r14], rdi
0x18004165b  mov     rcx, r15; hObject
0x18004165e  call    cs:__imp_CloseHandle
0x180041665  nop     dword ptr [rax+rax+00h]
0x18004166a  test    r13d, r13d
0x18004166d  jz      short loc_1800416AF
0x18004166f  test    r12b, r12b
0x180041672  jz      short loc_1800416AF
0x180041674  mov     rcx, rbx; lpFileName
0x180041677  call    cs:__imp_DeleteFileW
0x18004167e  nop     dword ptr [rax+rax+00h]
0x180041683  test    eax, eax
0x180041685  jnz     short loc_1800416AF
0x180041687  call    cs:__imp_GetLastError
0x18004168e  nop     dword ptr [rax+rax+00h]
0x180041693  cmp     eax, 2
0x180041696  jz      short loc_1800416AF
0x180041698  mov     r9d, eax
0x18004169b  lea     rdx, aCannotDeleteWs; "Cannot delete %ws (%ld)\n"
0x1800416a2  mov     r8, rbx
0x1800416a5  mov     ecx, 100h; unsigned int
0x1800416aa  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800416af  test    rbx, rbx
0x1800416b2  jz      short loc_1800416CC
0x1800416b4  lea     rcx, [rbx-8]
0x1800416b8  cmp     dword ptr [rcx], 70616548h
0x1800416be  jnz     short loc_1800416CC
0x1800416c0  mov     rax, cs:g_pfnFree
0x1800416c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416cc  mov     eax, edi
0x1800416ce  mov     rcx, [rbp+60h+var_50]
0x1800416d2  xor     rcx, rbp; StackCookie
0x1800416d5  call    __security_check_cookie
0x1800416da  lea     rsp, [rbp+28h]
0x1800416de  pop     r15
0x1800416e0  pop     r14
0x1800416e2  pop     r13
0x1800416e4  pop     r12
0x1800416e6  pop     rdi
0x1800416e7  pop     rsi
0x1800416e8  pop     rbx
0x1800416e9  pop     rbp
0x1800416ea  retn
```
