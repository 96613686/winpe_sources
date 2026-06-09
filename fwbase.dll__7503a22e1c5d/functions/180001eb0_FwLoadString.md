# FwLoadString

- ea: `0x180001eb0`
- end: `0x18000206d`
- name: `FwLoadString`
- size: `445`
- prototype: `__int64 __fastcall(UINT uID)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002e70`

## callees

- `0x180001eb0`
- `0x1800024a0`
- `0x1800045f0`
- `0x180004750`
- `0x1800047e0`
- `0x180004840`
- `0x180004870`
- `0x18002f43c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001fbf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001fbf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002026`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002026`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001f6e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001f6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001fe1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001fe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fe7`

## string_xrefs

- `0x180001ee3`: `%SystemRoot%\system32\FirewallAPI.dll`
- `0x180001fd3`: `LoadLibraryExW`

## pseudocode

```c
__int64 __fastcall FwLoadString(UINT uID, _QWORD *a2)
{
  WCHAR *v2; // rdi
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // ebx
  __int64 v9; // rdx
  WCHAR *v10; // rax
  int StringW; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdx
  HMODULE Library; // rax
  DWORD LastError; // eax
  const char *v17; // rdx
  __int64 v18; // r8

  v2 = 0;
  *a2 = 0;
  if ( !hInstance )
  {
    v5 = FwExpandEnvironmentStrings(L"%SystemRoot%\\system32\\FirewallAPI.dll");
    v6 = v5;
    if ( v5 < 0 )
    {
      FwReportReturnError("FwLoadString", (unsigned int)v5);
      goto LABEL_4;
    }
    Library = LoadLibraryExW(0, 0, 2u);
    if ( !Library )
    {
      LastError = GetLastError();
      v17 = "LoadLibraryExW";
LABEL_22:
      v18 = LastError;
LABEL_24:
      v6 = FwReportErrorAsWinError("FwLoadString", v17, v18);
      goto LABEL_4;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hInstance, (signed __int64)Library, 0)
      && !FreeLibrary(Library) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
  }
  v8 = 128;
  do
  {
    FwFree(v2);
    v2 = 0;
    v8 *= 2;
    if ( v8 > 4096 )
    {
      v6 = -2147024362;
LABEL_18:
      v14 = v6;
      goto LABEL_16;
    }
    v10 = (WCHAR *)FwAlloc(2LL * v8, v9);
    v2 = v10;
    if ( !v10 )
    {
      v18 = 8;
      v17 = "FwAlloc";
      goto LABEL_24;
    }
    StringW = LoadStringW(hInstance, uID, v10, v8);
    if ( !StringW )
    {
      SetLastError(0x490u);
      LastError = GetLastError();
      v17 = "LoadStringW";
      goto LABEL_22;
    }
    v12 = StringW + 1;
  }
  while ( v12 == v8 );
  if ( v12 > v8 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v13 = FwStringCopy(v2);
  v6 = v13;
  if ( v13 < 0 )
  {
    v14 = (unsigned int)v13;
LABEL_16:
    FwReportReturnError("FwLoadString", v14);
    goto LABEL_4;
  }
  if ( !*a2 )
  {
    v6 = -2147467261;
    goto LABEL_18;
  }
LABEL_4:
  FwFree(v2);
  FwFree(0);
  if ( (v6 & 0x80000000) != 0 )
    return (unsigned int)FwReportReturnError("FwLoadString", v6);
  return v6;
}

```

## disassembly

```asm
0x180001eb0  push    rbx
0x180001eb2  push    rbp
0x180001eb3  push    rsi
0x180001eb4  push    rdi
0x180001eb5  push    r12
0x180001eb7  push    r14
0x180001eb9  sub     rsp, 28h
0x180001ebd  xor     esi, esi
0x180001ebf  lea     r12, aFwloadstring_0; "FwLoadString"
0x180001ec6  xor     edi, edi
0x180001ec8  mov     [rdx], rsi
0x180001ecb  cmp     cs:hInstance, rsi
0x180001ed2  mov     r14, rdx
0x180001ed5  mov     ebp, ecx
0x180001ed7  mov     [rsp+58h+lpLibFileName], rsi
0x180001edc  jnz     short loc_180001F2F
0x180001ede  lea     rdx, [rsp+58h+lpLibFileName]
0x180001ee3  lea     rcx, aSystemrootSyst; "%SystemRoot%\\system32\\FirewallAPI.dll"
0x180001eea  call    FwExpandEnvironmentStrings
0x180001eef  mov     ebx, eax
0x180001ef1  test    eax, eax
0x180001ef3  jns     loc_180001FB1
0x180001ef9  mov     edx, eax
0x180001efb  mov     rcx, r12
0x180001efe  call    FwReportReturnError
0x180001f03  mov     rsi, [rsp+58h+lpLibFileName]
0x180001f08  mov     rcx, rdi
0x180001f0b  call    FwFree
0x180001f10  mov     rcx, rsi
0x180001f13  call    FwFree
0x180001f18  test    ebx, ebx
0x180001f1a  js      loc_18000205C
0x180001f20  mov     eax, ebx
0x180001f22  add     rsp, 28h
0x180001f26  pop     r14
0x180001f28  pop     r12
0x180001f2a  pop     rdi
0x180001f2b  pop     rsi
0x180001f2c  pop     rbp
0x180001f2d  pop     rbx
0x180001f2e  retn
0x180001f2f  mov     ebx, 80h
0x180001f34  mov     rcx, rdi
0x180001f37  call    FwFree
0x180001f3c  xor     edi, edi
0x180001f3e  add     ebx, ebx
0x180001f40  cmp     ebx, 1000h
0x180001f46  jg      short loc_180001FA8
0x180001f48  movsxd  rcx, ebx
0x180001f4b  add     rcx, rcx
0x180001f4e  call    FwAlloc
0x180001f53  mov     rdi, rax
0x180001f56  test    rax, rax
0x180001f59  jz      loc_180001FF9
0x180001f5f  mov     rcx, cs:hInstance; hInstance
0x180001f66  mov     r9d, ebx; cchBufferMax
0x180001f69  mov     r8, rax; lpBuffer
0x180001f6c  mov     edx, ebp; uID
0x180001f6e  call    cs:__imp_LoadStringW
0x180001f74  test    eax, eax
0x180001f76  jz      short loc_180001FDC
0x180001f78  inc     eax
0x180001f7a  cmp     eax, ebx
0x180001f7c  jz      short loc_180001F34
0x180001f7e  jg      loc_18000203E
0x180001f84  mov     rdx, r14
0x180001f87  mov     rcx, rdi; Src
0x180001f8a  call    FwStringCopy
0x180001f8f  mov     ebx, eax
0x180001f91  test    eax, eax
0x180001f93  jns     loc_180002048
0x180001f99  mov     edx, eax
0x180001f9b  mov     rcx, r12
0x180001f9e  call    FwReportReturnError
0x180001fa3  jmp     loc_180001F08
0x180001fa8  mov     ebx, 80070216h
0x180001fad  mov     edx, ebx
0x180001faf  jmp     short loc_180001F9B
0x180001fb1  mov     rsi, [rsp+58h+lpLibFileName]
0x180001fb6  xor     edx, edx; hFile
0x180001fb8  mov     rcx, rsi; lpLibFileName
0x180001fbb  lea     r8d, [rdx+2]; dwFlags
0x180001fbf  call    cs:__imp_LoadLibraryExW
0x180001fc5  mov     rcx, rax; hLibModule
0x180001fc8  test    rax, rax
0x180001fcb  jnz     short loc_180002015
0x180001fcd  call    cs:__imp_GetLastError
0x180001fd3  lea     rdx, aLoadlibraryexw; "LoadLibraryExW"
0x180001fda  jmp     short loc_180001FF4
0x180001fdc  mov     ecx, 490h; dwErrCode
0x180001fe1  call    cs:__imp_SetLastError
0x180001fe7  call    cs:__imp_GetLastError
0x180001fed  lea     rdx, aLoadstringw; "LoadStringW"
0x180001ff4  mov     r8d, eax
0x180001ff7  jmp     short loc_180002006
0x180001ff9  mov     r8d, 8
0x180001fff  lea     rdx, aFwalloc_0; "FwAlloc"
0x180002006  mov     rcx, r12
0x180002009  call    FwReportErrorAsWinError
0x18000200e  mov     ebx, eax
0x180002010  jmp     loc_180001F08
0x180002015  xor     eax, eax
0x180002017  lock cmpxchg cs:hInstance, rcx
0x180002020  jz      loc_180001F2F
0x180002026  call    cs:__imp_FreeLibrary
0x18000202c  test    eax, eax
0x18000202e  jnz     loc_180001F2F
0x180002034  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "success")
0x180002039  jmp     loc_180001F2F
0x18000203e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "stringLen <= bufferLen")
0x180002043  jmp     loc_180001F84
0x180002048  cmp     qword ptr [r14], 0
0x18000204c  jnz     loc_180001F08
0x180002052  mov     ebx, 80004003h
0x180002057  jmp     loc_180001FAD
0x18000205c  mov     edx, ebx
0x18000205e  mov     rcx, r12
0x180002061  call    FwReportReturnError
0x180002066  mov     ebx, eax
0x180002068  jmp     loc_180001F20
```
