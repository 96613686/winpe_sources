# FilterPolicyUpdateCheck

- ea: `0x1800071d0`
- end: `0x1800073ed`
- name: `FilterPolicyUpdateCheck`
- size: `541`
- prototype: `__int64 __fastcall(const WCHAR *, void *, int *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180002f60`

## callees

- `0x1800071d0`
- `0x1800073f4`
- `0x18000d8d0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800072c4`
- `msvcrt!wcscat_s` at `0x1800072c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007290`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007290`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800073bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800073bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000738e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000738e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000739e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000739e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073af`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180007354`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180007354`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800072f1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800072f1`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000735d`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000735d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180007379`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180007379`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180007321`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180007321`
- `USERENV!GetUserProfileDirectoryW` at `0x18000726e`
- `USERENV!GetUserProfileDirectoryW` at `0x1800072ac`
- `USERENV!GetUserProfileDirectoryW` at `0x18000726e`
- `USERENV!GetUserProfileDirectoryW` at `0x1800072ac`

## pseudocode

```c
__int64 __fastcall FilterPolicyUpdateCheck(const WCHAR *a1, void *a2, int *a3, _DWORD *a4)
{
  __int64 v5; // rbx
  int v8; // r15d
  DWORD v9; // eax
  DWORD v10; // r12d
  WCHAR *v11; // rax
  wchar_t *v12; // rdi
  HANDLE FileW; // rax
  DWORD v14; // ecx
  DWORD LastError; // esi
  DWORD cchSize; // [rsp+40h] [rbp-79h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-75h] BYREF
  __int64 Buffer; // [rsp+48h] [rbp-71h] BYREF
  int v20; // [rsp+50h] [rbp-69h]
  wchar_t Source[48]; // [rsp+60h] [rbp-59h] BYREF

  v5 = -1;
  wcscpy(Source, L"\\AppData\\Local\\Microsoft\\DIMS\\crsengs.dat");
  v8 = 1;
  cchSize = 0;
  Buffer = 0;
  v20 = 0;
  NumberOfBytesRead = 0;
  ReadCurrentPolicyFilterOptions(a1);
  GetUserProfileDirectoryW(a2, 0, &cchSize);
  v9 = cchSize;
  if ( !cchSize )
    v9 = 300;
  v10 = v9 + 46;
  cchSize = v9 + 46;
  v11 = (WCHAR *)LocalAlloc(0, 2LL * (v9 + 46));
  v12 = v11;
  if ( !v11 )
    goto LABEL_16;
  if ( !GetUserProfileDirectoryW(a2, v11, &cchSize) )
    goto LABEL_16;
  wcscat_s(v12, v10, Source);
  FileW = CreateFileW(v12, 0xC0000000, 0, 0, 4u, 0, 0);
  v5 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_16;
  if ( ReadFile(FileW, &Buffer, 0xCu, &NumberOfBytesRead, 0)
    && NumberOfBytesRead == 12
    && *(_QWORD *)a4 == Buffer
    && a4[2] == v20 )
  {
    v8 = 0;
    goto LABEL_11;
  }
  SetFilePointer((HANDLE)v5, 0, 0, 0);
  SetEndOfFile((HANDLE)v5);
  if ( !WriteFile((HANDLE)v5, a4, 0xCu, &NumberOfBytesRead, 0) )
  {
LABEL_16:
    LastError = GetLastError();
    if ( v5 == -1 )
      goto LABEL_18;
    goto LABEL_17;
  }
  if ( NumberOfBytesRead != 12 )
  {
    v14 = 112;
    goto LABEL_15;
  }
LABEL_11:
  v14 = 0;
LABEL_15:
  SetLastError(v14);
  LastError = GetLastError();
LABEL_17:
  CloseHandle((HANDLE)v5);
LABEL_18:
  if ( v12 )
    LocalFree(v12);
  if ( a3 )
    *a3 = v8;
  return LastError;
}

```

## disassembly

```asm
0x1800071d0  push    rbp
0x1800071d2  push    rbx
0x1800071d3  push    rsi
0x1800071d4  push    rdi
0x1800071d5  push    r12
0x1800071d7  push    r13
0x1800071d9  push    r14
0x1800071db  push    r15
0x1800071dd  lea     rbp, [rsp-1Fh]
0x1800071e2  sub     rsp, 0D8h
0x1800071e9  mov     rax, cs:__security_cookie
0x1800071f0  xor     rax, rsp
0x1800071f3  mov     [rbp+57h+var_50], rax
0x1800071f7  movaps  xmm1, xmmword ptr cs:aAppdataLocalMi+10h; "\\Local\\Microsoft\\DIMS\\crsettings.da"...
0x1800071fe  xor     eax, eax
0x180007200  movaps  xmm0, xmmword ptr cs:aAppdataLocalMi; "\\AppData\\Local\\Microsoft\\DIMS\\crse"...
0x180007207  mov     r13, rdx
0x18000720a  movaps  [rbp+57h+var_A0], xmm1
0x18000720e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180007212  movaps  xmm1, xmmword ptr cs:aAppdataLocalMi+30h; "\\DIMS\\crsettings.dat"
0x180007219  mov     rdx, r9
0x18000721c  movaps  xmmword ptr [rbp+57h+Source], xmm0
0x180007220  mov     rsi, r9
0x180007223  movaps  xmm0, xmmword ptr cs:aAppdataLocalMi+20h; "icrosoft\\DIMS\\crsettings.dat"
0x18000722a  mov     r14, r8
0x18000722d  movaps  [rbp+57h+var_80], xmm1
0x180007231  lea     r15d, [rbx+2]
0x180007235  movups  xmm1, xmmword ptr cs:aAppdataLocalMi+4Ah; "ngs.dat"
0x18000723c  mov     [rbp+57h+cchSize], 0
0x180007243  movaps  [rbp+57h+var_90], xmm0
0x180007247  movaps  xmm0, xmmword ptr cs:aAppdataLocalMi+40h; "settings.dat"
0x18000724e  movaps  [rbp+57h+var_70], xmm0
0x180007252  movups  [rbp+57h+var_70+0Ah], xmm1
0x180007256  mov     [rbp+57h+Buffer], rax
0x18000725a  mov     [rbp+57h+var_C0], eax
0x18000725d  mov     [rbp+57h+NumberOfBytesRead], eax
0x180007260  call    ReadCurrentPolicyFilterOptions
0x180007265  lea     r8, [rbp+57h+cchSize]; lpcchSize
0x180007269  xor     edx, edx; lpProfileDir
0x18000726b  mov     rcx, r13; hToken
0x18000726e  call    cs:__imp_GetUserProfileDirectoryW
0x180007274  mov     eax, [rbp+57h+cchSize]
0x180007277  test    eax, eax
0x180007279  jnz     short loc_180007280
0x18000727b  mov     eax, 12Ch
0x180007280  add     eax, 2Eh ; '.'
0x180007283  xor     ecx, ecx; uFlags
0x180007285  mov     edx, eax
0x180007287  add     rdx, rdx; uBytes
0x18000728a  mov     r12d, eax
0x18000728d  mov     [rbp+57h+cchSize], eax
0x180007290  call    cs:__imp_LocalAlloc
0x180007296  mov     rdi, rax
0x180007299  test    rax, rax
0x18000729c  jz      loc_18000739E
0x1800072a2  lea     r8, [rbp+57h+cchSize]; lpcchSize
0x1800072a6  mov     rdx, rax; lpProfileDir
0x1800072a9  mov     rcx, r13; hToken
0x1800072ac  call    cs:__imp_GetUserProfileDirectoryW
0x1800072b2  test    eax, eax
0x1800072b4  jz      loc_18000739E
0x1800072ba  mov     edx, r12d; SizeInWords
0x1800072bd  lea     r8, [rbp+57h+Source]; Source
0x1800072c1  mov     rcx, rdi; Destination
0x1800072c4  call    cs:__imp_wcscat_s
0x1800072ca  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x1800072d3  xor     r9d, r9d; lpSecurityAttributes
0x1800072d6  mov     [rsp+110h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800072de  xor     r8d, r8d; dwShareMode
0x1800072e1  mov     edx, 0C0000000h; dwDesiredAccess
0x1800072e6  mov     [rsp+110h+dwCreationDisposition], 4; dwCreationDisposition
0x1800072ee  mov     rcx, rdi; lpFileName
0x1800072f1  call    cs:__imp_CreateFileW
0x1800072f7  mov     rbx, rax
0x1800072fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800072fe  jz      loc_18000739E
0x180007304  mov     r12d, 0Ch
0x18000730a  mov     qword ptr [rsp+110h+dwCreationDisposition], 0; lpOverlapped
0x180007313  mov     r8d, r12d; nNumberOfBytesToRead
0x180007316  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000731a  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18000731e  mov     rcx, rax; hFile
0x180007321  call    cs:__imp_ReadFile
0x180007327  test    eax, eax
0x180007329  jz      short loc_180007349
0x18000732b  cmp     [rbp+57h+NumberOfBytesRead], r12d
0x18000732f  jnz     short loc_180007349
0x180007331  mov     rax, [rsi]
0x180007334  cmp     rax, [rbp+57h+Buffer]
0x180007338  jnz     short loc_180007349
0x18000733a  mov     eax, [rsi+8]
0x18000733d  cmp     eax, [rbp+57h+var_C0]
0x180007340  jnz     short loc_180007349
0x180007342  xor     r15d, r15d
0x180007345  xor     ecx, ecx
0x180007347  jmp     short loc_18000738E
0x180007349  xor     r9d, r9d; dwMoveMethod
0x18000734c  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000734f  xor     edx, edx; lDistanceToMove
0x180007351  mov     rcx, rbx; hFile
0x180007354  call    cs:__imp_SetFilePointer
0x18000735a  mov     rcx, rbx; hFile
0x18000735d  call    cs:__imp_SetEndOfFile
0x180007363  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesWritten
0x180007367  mov     qword ptr [rsp+110h+dwCreationDisposition], 0; lpOverlapped
0x180007370  mov     r8d, r12d; nNumberOfBytesToWrite
0x180007373  mov     rdx, rsi; lpBuffer
0x180007376  mov     rcx, rbx; hFile
0x180007379  call    cs:__imp_WriteFile
0x18000737f  test    eax, eax
0x180007381  jz      short loc_18000739E
0x180007383  cmp     [rbp+57h+NumberOfBytesRead], r12d
0x180007387  jz      short loc_180007345
0x180007389  mov     ecx, 70h ; 'p'; dwErrCode
0x18000738e  call    cs:__imp_SetLastError
0x180007394  call    cs:__imp_GetLastError
0x18000739a  mov     esi, eax
0x18000739c  jmp     short loc_1800073AC
0x18000739e  call    cs:__imp_GetLastError
0x1800073a4  mov     esi, eax
0x1800073a6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800073aa  jz      short loc_1800073B5
0x1800073ac  mov     rcx, rbx; hObject
0x1800073af  call    cs:__imp_CloseHandle
0x1800073b5  test    rdi, rdi
0x1800073b8  jz      short loc_1800073C3
0x1800073ba  mov     rcx, rdi; hMem
0x1800073bd  call    cs:__imp_LocalFree
0x1800073c3  test    r14, r14
0x1800073c6  jz      short loc_1800073CB
0x1800073c8  mov     [r14], r15d
0x1800073cb  mov     eax, esi
0x1800073cd  mov     rcx, [rbp+57h+var_50]
0x1800073d1  xor     rcx, rsp; StackCookie
0x1800073d4  call    __security_check_cookie
0x1800073d9  add     rsp, 0D8h
0x1800073e0  pop     r15
0x1800073e2  pop     r14
0x1800073e4  pop     r13
0x1800073e6  pop     r12
0x1800073e8  pop     rdi
0x1800073e9  pop     rsi
0x1800073ea  pop     rbx
0x1800073eb  pop     rbp
0x1800073ec  retn
```
