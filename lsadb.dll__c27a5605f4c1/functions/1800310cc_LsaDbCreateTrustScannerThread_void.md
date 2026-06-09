# LsaDbCreateTrustScannerThread(void)

- ea: `0x1800310cc`
- end: `0x1800311f2`
- name: `?LsaDbCreateTrustScannerThread@@YAJXZ`
- size: `294`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800304a0`

## callees

- `0x18000fd40`
- `0x1800310cc`
- `0x180032958`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003115b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003115b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800310f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800310f7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800311d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800311d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031169`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800311df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800311df`

## pseudocode

```c
__int64 LsaDbCreateTrustScannerThread(void)
{
  HANDLE v0; // rdi
  DWORD v1; // eax
  HMODULE v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // r8
  DWORD LastError; // eax
  _QWORD *v6; // rcx
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF
  LPVOID lpParameter; // [rsp+48h] [rbp+10h] BYREF

  ThreadId = 0;
  lpParameter = 0;
  if ( GetModuleHandleExW(4u, (LPCWSTR)TrustScannerThreadProc, (HMODULE *)&lpParameter) )
  {
    v3 = 0;
    v0 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)TrustScannerThreadProc, lpParameter, 0, &ThreadId);
    if ( v0 )
    {
      v6 = WPP_GLOBAL_Control;
    }
    else
    {
      LastError = GetLastError();
      v6 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids, LastError);
        v6 = WPP_GLOBAL_Control;
      }
      v3 = -1073741801;
    }
    if ( (*((_BYTE *)v6 + 28) & 0x10) != 0 )
      WPP_SF_Dd(v6[2], 71, v4, ThreadId, ThreadId);
    v2 = 0;
    lpParameter = 0;
  }
  else
  {
    v0 = 0;
    v1 = GetLastError();
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids, v1);
    v2 = (HMODULE)lpParameter;
    v3 = -1073741801;
  }
  if ( v2 )
    FreeLibrary(v2);
  if ( v0 )
    CloseHandle(v0);
  return v3;
}

```

## disassembly

```asm
0x1800310cc  mov     rax, rsp
0x1800310cf  mov     [rax+18h], rbx
0x1800310d3  push    rdi
0x1800310d4  sub     rsp, 30h
0x1800310d8  lea     r8, [rax+10h]; phModule
0x1800310dc  mov     dword ptr [rax+8], 0
0x1800310e3  lea     rdx, ?TrustScannerThreadProc@@YAKPEAX@Z; lpModuleName
0x1800310ea  mov     qword ptr [rax+10h], 0
0x1800310f2  mov     ecx, 4; dwFlags
0x1800310f7  call    cs:__imp_GetModuleHandleExW
0x1800310fd  test    eax, eax
0x1800310ff  jnz     short loc_18003113B
0x180031101  xor     edi, edi
0x180031103  call    cs:__imp_GetLastError
0x180031109  mov     rcx, cs:WPP_GLOBAL_Control
0x180031110  test    byte ptr [rcx+1Ch], 10h
0x180031114  jz      short loc_18003112C
0x180031116  mov     rcx, [rcx+10h]
0x18003111a  lea     edx, [rdi+45h]
0x18003111d  mov     r9d, eax
0x180031120  lea     r8, WPP_844d483327f83d00fc717282eb3891a9_Traceguids
0x180031127  call    WPP_SF_d
0x18003112c  mov     rcx, [rsp+38h+lpParameter]
0x180031131  mov     ebx, 0C0000017h
0x180031136  jmp     loc_1800311CC
0x18003113b  mov     r9, [rsp+38h+lpParameter]; lpParameter
0x180031140  lea     rax, [rsp+38h+ThreadId]
0x180031145  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18003114a  lea     r8, ?TrustScannerThreadProc@@YAKPEAX@Z; lpStartAddress
0x180031151  xor     ebx, ebx
0x180031153  xor     edx, edx; dwStackSize
0x180031155  xor     ecx, ecx; lpThreadAttributes
0x180031157  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x18003115b  call    cs:__imp_CreateThread
0x180031161  mov     rdi, rax
0x180031164  test    rax, rax
0x180031167  jnz     short loc_1800311A0
0x180031169  call    cs:__imp_GetLastError
0x18003116f  mov     rcx, cs:WPP_GLOBAL_Control
0x180031176  test    byte ptr [rcx+1Ch], 10h
0x18003117a  jz      short loc_180031199
0x18003117c  mov     rcx, [rcx+10h]
0x180031180  lea     edx, [rbx+46h]
0x180031183  mov     r9d, eax
0x180031186  lea     r8, WPP_844d483327f83d00fc717282eb3891a9_Traceguids
0x18003118d  call    WPP_SF_d
0x180031192  mov     rcx, cs:WPP_GLOBAL_Control
0x180031199  mov     ebx, 0C0000017h
0x18003119e  jmp     short loc_1800311A7
0x1800311a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800311a7  test    byte ptr [rcx+1Ch], 10h
0x1800311ab  jz      short loc_1800311C5
0x1800311ad  mov     r9d, [rsp+38h+ThreadId]
0x1800311b2  mov     edx, 47h ; 'G'
0x1800311b7  mov     rcx, [rcx+10h]
0x1800311bb  mov     [rsp+38h+dwCreationFlags], r9d
0x1800311c0  call    WPP_SF_Dd
0x1800311c5  xor     ecx, ecx; hLibModule
0x1800311c7  mov     [rsp+38h+lpParameter], rcx
0x1800311cc  test    rcx, rcx
0x1800311cf  jz      short loc_1800311D7
0x1800311d1  call    cs:__imp_FreeLibrary
0x1800311d7  test    rdi, rdi
0x1800311da  jz      short loc_1800311E5
0x1800311dc  mov     rcx, rdi; hObject
0x1800311df  call    cs:__imp_CloseHandle
0x1800311e5  mov     eax, ebx
0x1800311e7  mov     rbx, [rsp+38h+arg_10]
0x1800311ec  add     rsp, 30h
0x1800311f0  pop     rdi
0x1800311f1  retn
```
