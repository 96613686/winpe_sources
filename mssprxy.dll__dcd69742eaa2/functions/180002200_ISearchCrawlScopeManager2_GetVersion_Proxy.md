# ISearchCrawlScopeManager2_GetVersion_Proxy

- ea: `0x180002200`
- end: `0x180002291`
- name: `ISearchCrawlScopeManager2_GetVersion_Proxy`
- size: `145`
- prototype: `HRESULT __stdcall(ISearchCrawlScopeManager2 *This, int **plVersion, HANDLE *phFileMapping)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002200`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18000221c`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18000221c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000225d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000225d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000222e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000222e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002268`

## pseudocode

```c
HRESULT __stdcall ISearchCrawlScopeManager2_GetVersion_Proxy(
        ISearchCrawlScopeManager2 *This,
        int **plVersion,
        HANDLE *phFileMapping)
{
  HANDLE v5; // rdi
  HRESULT v6; // ebx
  signed int v7; // eax
  int *v8; // rax
  signed int LastError; // eax

  v5 = OpenFileMappingW(4u, 0, L"Global\\SearchCrawlScopeVersion");
  if ( v5 )
  {
    v6 = 0;
LABEL_6:
    v8 = (int *)MapViewOfFile(v5, 4u, 0, 0, 4u);
    if ( v8 )
    {
      *plVersion = v8;
      *phFileMapping = v5;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    return v6;
  }
  v7 = GetLastError();
  v6 = v7;
  if ( v7 > 0 )
    v6 = (unsigned __int16)v7 | 0x80070000;
  if ( v6 >= 0 )
    goto LABEL_6;
  return v6;
}

```

## disassembly

```asm
0x180002200  push    rbx
0x180002202  push    rsi
0x180002203  push    rdi
0x180002204  push    r14
0x180002206  sub     rsp, 38h
0x18000220a  mov     r14, rdx
0x18000220d  mov     rsi, r8
0x180002210  xor     edx, edx; bInheritHandle
0x180002212  lea     r8, Name; "Global\\SearchCrawlScopeVersion"
0x180002219  lea     ecx, [rdx+4]; dwDesiredAccess
0x18000221c  call    cs:__imp_OpenFileMappingW
0x180002222  mov     rdi, rax
0x180002225  test    rax, rax
0x180002228  jz      short loc_18000222E
0x18000222a  xor     ebx, ebx
0x18000222c  jmp     short loc_180002247
0x18000222e  call    cs:__imp_GetLastError
0x180002234  mov     ebx, eax
0x180002236  test    eax, eax
0x180002238  jle     short loc_180002243
0x18000223a  movzx   ebx, ax
0x18000223d  or      ebx, 80070000h
0x180002243  test    ebx, ebx
0x180002245  js      short loc_180002285
0x180002247  xor     r9d, r9d; dwFileOffsetLow
0x18000224a  mov     [rsp+58h+dwNumberOfBytesToMap], 4; dwNumberOfBytesToMap
0x180002253  xor     r8d, r8d; dwFileOffsetHigh
0x180002256  mov     rcx, rdi; hFileMappingObject
0x180002259  lea     edx, [r9+4]; dwDesiredAccess
0x18000225d  call    cs:__imp_MapViewOfFile
0x180002263  test    rax, rax
0x180002266  jnz     short loc_18000227F
0x180002268  call    cs:__imp_GetLastError
0x18000226e  mov     ebx, eax
0x180002270  test    eax, eax
0x180002272  jle     short loc_180002285
0x180002274  movzx   ebx, ax
0x180002277  or      ebx, 80070000h
0x18000227d  jmp     short loc_180002285
0x18000227f  mov     [r14], rax
0x180002282  mov     [rsi], rdi
0x180002285  mov     eax, ebx
0x180002287  add     rsp, 38h
0x18000228b  pop     r14
0x18000228d  pop     rdi
0x18000228e  pop     rsi
0x18000228f  pop     rbx
0x180002290  retn
```
