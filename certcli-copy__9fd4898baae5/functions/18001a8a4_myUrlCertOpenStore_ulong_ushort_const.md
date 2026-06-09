# myUrlCertOpenStore(ulong,ushort const *)

- ea: `0x18001a8a4`
- end: `0x18001a9ab`
- name: `?myUrlCertOpenStore@@YAPEAXKPEBG@Z`
- size: `263`
- prototype: `void *__fastcall(unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018d44`

## callees

- `0x18001a8a4`
- `0x180021438`
- `0x1800217d4`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a990`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a990`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a8f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a8f6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a97e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a97e`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001a8e1`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001a90f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001a8e1`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001a90f`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18001a971`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18001a971`

## string_xrefs

- `0x18001a8b3`: `cryptnet.dll`

## pseudocode

```c
void *__fastcall myUrlCertOpenStore(__int64 a1, unsigned __int16 *a2)
{
  HINSTANCE System32Library; // rax
  HMODULE v4; // rdi
  DWORD v5; // ebx
  FARPROC ProcAddress; // rax
  void *result; // rax
  void *v8; // [rsp+70h] [rbp+18h] BYREF

  v8 = 0;
  System32Library = myLoadSystem32LibraryEx(L"cryptnet.dll", a2);
  v4 = System32Library;
  if ( System32Library )
  {
    ProcAddress = GetProcAddress(System32Library, "CryptRetrieveObjectByUrlW");
    if ( ProcAddress )
    {
      if ( ((unsigned int (__fastcall *)(unsigned __int16 *, __int64, __int64, __int64, void **, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(
             a2,
             5,
             5,
             120000,
             &v8,
             0,
             0,
             0,
             0) )
      {
        v5 = 0;
      }
      else
      {
        v5 = myHLastError();
        CSPrintErrorLineFileData(a2, 0x225701A3u, v5);
      }
    }
    else
    {
      v5 = myHLastError();
      CSPrintErrorLineFile(0x224801A3u, v5);
    }
    FreeLibrary(v4);
  }
  else
  {
    v5 = myHLastError();
    CSPrintErrorLineFile(0x223F01A3u, v5);
  }
  result = v8;
  if ( !v8 )
  {
    SetLastError(v5);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18001a8a4  mov     [rsp+arg_0], rbx
0x18001a8a9  mov     [rsp+arg_8], rsi
0x18001a8ae  push    rdi
0x18001a8af  sub     rsp, 50h
0x18001a8b3  lea     rcx, aCryptnetDll; "cryptnet.dll"
0x18001a8ba  mov     [rsp+58h+arg_10], 0
0x18001a8c3  mov     rsi, rdx
0x18001a8c6  call    ?myLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; myLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x18001a8cb  mov     rdi, rax
0x18001a8ce  test    rax, rax
0x18001a8d1  jnz     short loc_18001A8EC
0x18001a8d3  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001a8d8  mov     edx, eax
0x18001a8da  mov     ecx, 223F01A3h
0x18001a8df  mov     ebx, eax
0x18001a8e1  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001a8e7  jmp     loc_18001A984
0x18001a8ec  lea     rdx, aCryptretrieveo; "CryptRetrieveObjectByUrlW"
0x18001a8f3  mov     rcx, rdi; hModule
0x18001a8f6  call    cs:__imp_GetProcAddress
0x18001a8fc  test    rax, rax
0x18001a8ff  jnz     short loc_18001A917
0x18001a901  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001a906  mov     edx, eax
0x18001a908  mov     ecx, 224801A3h
0x18001a90d  mov     ebx, eax
0x18001a90f  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001a915  jmp     short loc_18001A97B
0x18001a917  mov     [rsp+58h+var_18], 0
0x18001a920  lea     rcx, [rsp+58h+arg_10]
0x18001a925  mov     [rsp+58h+var_20], 0
0x18001a92e  mov     edx, 5
0x18001a933  mov     [rsp+58h+var_28], 0
0x18001a93c  mov     r9d, 1D4C0h
0x18001a942  mov     [rsp+58h+var_30], 0
0x18001a94b  mov     r8d, edx
0x18001a94e  mov     [rsp+58h+var_38], rcx
0x18001a953  mov     rcx, rsi
0x18001a956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a95b  test    eax, eax
0x18001a95d  jnz     short loc_18001A979
0x18001a95f  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001a964  mov     r8d, eax
0x18001a967  mov     edx, 225701A3h
0x18001a96c  mov     rcx, rsi
0x18001a96f  mov     ebx, eax
0x18001a971  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18001a977  jmp     short loc_18001A97B
0x18001a979  xor     ebx, ebx
0x18001a97b  mov     rcx, rdi; hLibModule
0x18001a97e  call    cs:__imp_FreeLibrary
0x18001a984  mov     rax, [rsp+58h+arg_10]
0x18001a989  test    rax, rax
0x18001a98c  jnz     short loc_18001A99B
0x18001a98e  mov     ecx, ebx; dwErrCode
0x18001a990  call    cs:__imp_SetLastError
0x18001a996  mov     rax, [rsp+58h+arg_10]
0x18001a99b  mov     rbx, [rsp+58h+arg_0]
0x18001a9a0  mov     rsi, [rsp+58h+arg_8]
0x18001a9a5  add     rsp, 50h
0x18001a9a9  pop     rdi
0x18001a9aa  retn
```
