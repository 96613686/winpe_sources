# NlReadBinaryLog(ushort *,int,uchar * *,ulong *)

- ea: `0x18003eb40`
- end: `0x18003ee44`
- name: `?NlReadBinaryLog@@YAKPEAGHPEAPEAEPEAK@Z`
- size: `772`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, HLOCAL *, unsigned int *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180016fbc`
- `0x18001c76c`
- `0x180020978`
- `0x180066c98`

## callees

- `0x180003220`
- `0x180007278`
- `0x18000e270`
- `0x18003eb40`
- `0x18008a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003ec73`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003ec73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ecb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ecea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ede6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ecb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ecea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ede6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003edc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003edc9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ed3f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ed3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003edbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003edbb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18003ec01`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18003ec01`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18003ecdd`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18003ecdd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003eca5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003eca5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003eddc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003eddc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003ed67`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003ed67`

## string_xrefs

- `0x18003ec13`: `NlWriteBinaryLog: Unable to GetSystemWindowsDirectoryW (%ld)\n`
- `0x18003ec4d`: `NlWriteBinaryLog: file name length is too long \n`
- `0x18003ecbd`: `%ws: Unable to open. %ld\n`
- `0x18003ed1c`: `NlReadBinaryLog: %ws: size too small: %ld.\n`
- `0x18003ed7f`: `NlReadBinaryLog: %ws: Cannot ReadFile: %ld.\n`
- `0x18003eda7`: `NlReadBinaryLog: %ws: Cannot read entire File: %ld %ld.\n`
- `0x18003edf4`: `Cannot delete %ws (%ld)\n`

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
0x18003eb40  push    rbp
0x18003eb42  push    rbx
0x18003eb43  push    rsi
0x18003eb44  push    rdi
0x18003eb45  push    r12
0x18003eb47  push    r13
0x18003eb49  push    r14
0x18003eb4b  push    r15
0x18003eb4d  sub     rsp, 68h
0x18003eb51  lea     rbp, [rsp+40h]
0x18003eb56  mov     rax, cs:__security_cookie
0x18003eb5d  xor     rax, rbp
0x18003eb60  mov     [rbp+60h+var_50], rax
0x18003eb64  xor     ebx, ebx
0x18003eb66  mov     r13d, edx
0x18003eb69  mov     edx, 20Ah
0x18003eb6e  mov     [rbp+60h+NumberOfBytesRead], ebx
0x18003eb71  cmp     cs:g_ulMaxStackAllocSize, rdx
0x18003eb78  mov     rsi, r9
0x18003eb7b  mov     r14, r8
0x18003eb7e  mov     [r8], rbx
0x18003eb81  lea     edi, [rbx+8]
0x18003eb84  mov     [r9], ebx
0x18003eb87  mov     r15, rcx
0x18003eb8a  mov     r12b, bl
0x18003eb8d  jb      short loc_18003EBCD
0x18003eb8f  mov     rcx, cs:g_ulAdditionalProbeSize
0x18003eb96  add     rcx, 212h
0x18003eb9d  cmp     rcx, rdx
0x18003eba0  jb      short loc_18003EBCD
0x18003eba2  call    VerifyStackAvailable
0x18003eba7  test    eax, eax
0x18003eba9  jz      short loc_18003EBCD
0x18003ebab  mov     eax, [rsp+0A0h+var_A0]
0x18003ebae  mov     eax, 220h
0x18003ebb3  sub     rsp, rax
0x18003ebb6  lea     rbx, [rsp+2C0h+var_280]
0x18003ebbb  mov     eax, [rbx]
0x18003ebbd  test    rbx, rbx
0x18003ebc0  jz      short loc_18003EBCD
0x18003ebc2  mov     dword ptr [rbx], 6B637453h
0x18003ebc8  add     rbx, rdi
0x18003ebcb  jnz     short loc_18003EBF9
0x18003ebcd  mov     rax, cs:g_pfnAllocate
0x18003ebd4  mov     ecx, 212h
0x18003ebd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebde  mov     rbx, rax
0x18003ebe1  test    rax, rax
0x18003ebe4  jz      loc_18003EDCF
0x18003ebea  mov     dword ptr [rax], 70616548h
0x18003ebf0  add     rbx, rdi
0x18003ebf3  jz      loc_18003EDCF
0x18003ebf9  mov     edx, 105h; uSize
0x18003ebfe  mov     rcx, rbx; lpBuffer
0x18003ec01  call    cs:__imp_GetSystemWindowsDirectoryW
0x18003ec07  xor     edx, edx
0x18003ec09  test    eax, eax
0x18003ec0b  jnz     short loc_18003EC2E
0x18003ec0d  call    cs:__imp_GetLastError
0x18003ec13  lea     rdx, aNlwritebinaryl; "NlWriteBinaryLog: Unable to GetSystemWi"...
0x18003ec1a  mov     ecx, 100h; unsigned int
0x18003ec1f  mov     r8d, eax
0x18003ec22  mov     edi, eax
0x18003ec24  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ec29  jmp     loc_18003EDCF
0x18003ec2e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003ec32  inc     rcx
0x18003ec35  cmp     [r15+rcx*2], dx
0x18003ec3a  jnz     short loc_18003EC32
0x18003ec3c  inc     rcx
0x18003ec3f  mov     eax, eax
0x18003ec41  add     rcx, rax
0x18003ec44  cmp     rcx, 104h
0x18003ec4b  jb      short loc_18003EC68
0x18003ec4d  lea     rdx, aNlwritebinaryl_0; "NlWriteBinaryLog: file name length is t"...
0x18003ec54  mov     ecx, 100h; unsigned int
0x18003ec59  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ec5e  mov     edi, 7Bh ; '{'
0x18003ec63  jmp     loc_18003EDCF
0x18003ec68  mov     r8, r15
0x18003ec6b  mov     edx, 105h
0x18003ec70  mov     rcx, rbx
0x18003ec73  call    cs:__imp__o_wcscat_s
0x18003ec79  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x18003ec82  mov     r12d, 1
0x18003ec88  mov     [rsp+2C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003ec90  xor     r9d, r9d; lpSecurityAttributes
0x18003ec93  mov     edx, 80000000h; dwDesiredAccess
0x18003ec98  mov     rcx, rbx; lpFileName
0x18003ec9b  lea     r8d, [r12+2]; dwShareMode
0x18003eca0  mov     [rsp+2C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18003eca5  call    cs:__imp_CreateFileW
0x18003ecab  mov     r15, rax
0x18003ecae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003ecb2  jnz     short loc_18003ECD8
0x18003ecb4  call    cs:__imp_GetLastError
0x18003ecba  mov     r8, rbx
0x18003ecbd  lea     rdx, aWsUnableToOpen; "%ws: Unable to open. %ld\n"
0x18003ecc4  mov     r9d, eax
0x18003ecc7  mov     ecx, 100h; unsigned int
0x18003eccc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ecd1  xor     edi, edi
0x18003ecd3  jmp     loc_18003EDCF
0x18003ecd8  xor     edx, edx; lpFileSizeHigh
0x18003ecda  mov     rcx, r15; hFile
0x18003ecdd  call    cs:__imp_GetFileSize
0x18003ece3  mov     [rsi], eax
0x18003ece5  cmp     eax, 0FFFFFFFFh
0x18003ece8  jnz     short loc_18003ED14
0x18003ecea  call    cs:__imp_GetLastError
0x18003ecf0  mov     r8, rbx
0x18003ecf3  lea     rdx, aWsUnableToGetf; "%ws: Unable to GetFileSize: %ld \n"
0x18003ecfa  mov     r9d, eax
0x18003ecfd  mov     ecx, 100h; unsigned int
0x18003ed02  mov     edi, eax
0x18003ed04  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ed09  mov     dword ptr [rsi], 0
0x18003ed0f  jmp     loc_18003EDC6
0x18003ed14  cmp     eax, r12d
0x18003ed17  jnb     short loc_18003ED3B
0x18003ed19  mov     r9d, eax
0x18003ed1c  lea     rdx, aNlreadbinarylo_1; "NlReadBinaryLog: %ws: size too small: %"...
0x18003ed23  mov     r8, rbx
0x18003ed26  mov     ecx, 100h; unsigned int
0x18003ed2b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ed30  xor     eax, eax
0x18003ed32  mov     [rsi], eax
0x18003ed34  mov     edi, eax
0x18003ed36  jmp     loc_18003EDC6
0x18003ed3b  mov     edx, eax; uBytes
0x18003ed3d  xor     ecx, ecx; uFlags
0x18003ed3f  call    cs:__imp_LocalAlloc
0x18003ed45  xor     ecx, ecx
0x18003ed47  mov     [r14], rax
0x18003ed4a  test    rax, rax
0x18003ed4d  jnz     short loc_18003ED53
0x18003ed4f  mov     [rsi], ecx
0x18003ed51  jmp     short loc_18003EDC6
0x18003ed53  mov     r8d, [rsi]; nNumberOfBytesToRead
0x18003ed56  lea     r9, [rbp+60h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003ed5a  xor     edi, edi
0x18003ed5c  mov     rdx, rax; lpBuffer
0x18003ed5f  mov     rcx, r15; hFile
0x18003ed62  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rdi; lpOverlapped
0x18003ed67  call    cs:__imp_ReadFile
0x18003ed6d  test    eax, eax
0x18003ed6f  jnz     short loc_18003ED95
0x18003ed71  call    cs:__imp_GetLastError
0x18003ed77  cmp     eax, 2
0x18003ed7a  jz      short loc_18003EDB8
0x18003ed7c  mov     r9d, eax
0x18003ed7f  lea     rdx, aNlreadbinarylo; "NlReadBinaryLog: %ws: Cannot ReadFile: "...
0x18003ed86  mov     r8, rbx
0x18003ed89  mov     ecx, 100h; unsigned int
0x18003ed8e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ed93  jmp     short loc_18003EDB8
0x18003ed95  mov     eax, [rsi]
0x18003ed97  mov     r9d, [rbp+60h+NumberOfBytesRead]
0x18003ed9b  cmp     r9d, eax
0x18003ed9e  jz      short loc_18003EDC6
0x18003eda0  mov     r8, rbx
0x18003eda3  mov     [rsp+2C0h+dwCreationDisposition], eax
0x18003eda7  lea     rdx, aNlreadbinarylo_0; "NlReadBinaryLog: %ws: Cannot read entir"...
0x18003edae  mov     ecx, 100h; unsigned int
0x18003edb3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003edb8  mov     rcx, [r14]; hMem
0x18003edbb  call    cs:__imp_LocalFree
0x18003edc1  mov     [rsi], edi
0x18003edc3  mov     [r14], rdi
0x18003edc6  mov     rcx, r15; hObject
0x18003edc9  call    cs:__imp_CloseHandle
0x18003edcf  test    r13d, r13d
0x18003edd2  jz      short loc_18003EE08
0x18003edd4  test    r12b, r12b
0x18003edd7  jz      short loc_18003EE08
0x18003edd9  mov     rcx, rbx; lpFileName
0x18003eddc  call    cs:__imp_DeleteFileW
0x18003ede2  test    eax, eax
0x18003ede4  jnz     short loc_18003EE08
0x18003ede6  call    cs:__imp_GetLastError
0x18003edec  cmp     eax, 2
0x18003edef  jz      short loc_18003EE08
0x18003edf1  mov     r9d, eax
0x18003edf4  lea     rdx, aCannotDeleteWs; "Cannot delete %ws (%ld)\n"
0x18003edfb  mov     r8, rbx
0x18003edfe  mov     ecx, 100h; unsigned int
0x18003ee03  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ee08  test    rbx, rbx
0x18003ee0b  jz      short loc_18003EE25
0x18003ee0d  lea     rcx, [rbx-8]
0x18003ee11  cmp     dword ptr [rcx], 70616548h
0x18003ee17  jnz     short loc_18003EE25
0x18003ee19  mov     rax, cs:g_pfnFree
0x18003ee20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ee25  mov     eax, edi
0x18003ee27  mov     rcx, [rbp+60h+var_50]
0x18003ee2b  xor     rcx, rbp; StackCookie
0x18003ee2e  call    __security_check_cookie
0x18003ee33  lea     rsp, [rbp+28h]
0x18003ee37  pop     r15
0x18003ee39  pop     r14
0x18003ee3b  pop     r13
0x18003ee3d  pop     r12
0x18003ee3f  pop     rdi
0x18003ee40  pop     rsi
0x18003ee41  pop     rbx
0x18003ee42  pop     rbp
0x18003ee43  retn
```
