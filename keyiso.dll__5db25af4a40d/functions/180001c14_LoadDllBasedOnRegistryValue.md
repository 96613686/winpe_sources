# LoadDllBasedOnRegistryValue

- ea: `0x180001c14`
- end: `0x180001d0e`
- name: `LoadDllBasedOnRegistryValue`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64, HMODULE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b62c`

## callees

- `0x180001c14`
- `0x180001d14`
- `0x180003cf0`
- `0x180004470`
- `0x180006280`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001c93`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001c93`

## string_xrefs

- `0x180001c3a`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`
- `0x180001c72`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`
- `0x180001cc0`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`

## pseudocode

```c
__int64 __fastcall LoadDllBasedOnRegistryValue(__int64 a1, __int64 a2, HMODULE *a3)
{
  unsigned int v4; // ebx
  int DllPath; // eax
  HMODULE Library; // rax
  int v7; // edx
  int v8; // r8d
  LPCWSTR lpLibFileName; // [rsp+58h] [rbp+10h] BYREF

  lpLibFileName = 0;
  if ( a3 )
  {
    DllPath = GetDllPath(a1, a2, &lpLibFileName);
    v4 = DllPath;
    if ( DllPath >= 0 )
    {
      Library = LoadLibraryExW(lpLibFileName, 0, 0);
      if ( Library )
      {
        *a3 = Library;
        v4 = 0;
      }
      else
      {
        v4 = -2146893794;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v7,
            v8,
            (unsigned int)"Status",
            30,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
            234);
      }
    }
    else
    {
      DebugTraceError(
        (unsigned int)DllPath,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
        225);
    }
    if ( lpLibFileName )
      MSCryptFree(lpLibFileName);
  }
  else
  {
    v4 = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c", 218);
  }
  return v4;
}

```

## disassembly

```asm
0x180001c14  mov     [rsp+arg_0], rbx
0x180001c19  mov     [rsp+lpLibFileName], rdx
0x180001c1e  push    rsi
0x180001c1f  sub     rsp, 40h
0x180001c23  mov     [rsp+48h+lpLibFileName], 0
0x180001c2c  mov     rsi, r8
0x180001c2f  test    r8, r8
0x180001c32  jnz     short loc_180001C5C
0x180001c34  mov     r9d, 0DAh
0x180001c3a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001c41  lea     rdx, aStatus; "Status"
0x180001c48  mov     ecx, 80090027h
0x180001c4d  mov     ebx, 80090027h
0x180001c52  call    DebugTraceError
0x180001c57  jmp     loc_180001D01
0x180001c5c  lea     r8, [rsp+48h+lpLibFileName]
0x180001c61  call    GetDllPath
0x180001c66  mov     ebx, eax
0x180001c68  test    eax, eax
0x180001c6a  jns     short loc_180001C89
0x180001c6c  mov     r9d, 0E1h
0x180001c72  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001c79  lea     rdx, aStatus; "Status"
0x180001c80  mov     ecx, eax
0x180001c82  call    DebugTraceError
0x180001c87  jmp     short loc_180001CEF
0x180001c89  mov     rcx, [rsp+48h+lpLibFileName]; lpLibFileName
0x180001c8e  xor     r8d, r8d; dwFlags
0x180001c91  xor     edx, edx; hFile
0x180001c93  call    cs:__imp_LoadLibraryExW
0x180001c99  test    rax, rax
0x180001c9c  jnz     short loc_180001CEA
0x180001c9e  mov     ebx, 8009001Eh
0x180001ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x180001caa  lea     rax, WPP_GLOBAL_Control
0x180001cb1  cmp     rcx, rax
0x180001cb4  jz      short loc_180001CEF
0x180001cb6  test    byte ptr [rcx+1Ch], 1
0x180001cba  jz      short loc_180001CEF
0x180001cbc  mov     rcx, [rcx+10h]
0x180001cc0  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001cc7  mov     [rsp+48h+var_18], 0EAh
0x180001ccf  lea     r9, aStatus; "Status"
0x180001cd6  mov     [rsp+48h+var_20], rax
0x180001cdb  mov     [rsp+48h+var_28], 8009001Eh
0x180001ce3  call    WPP_SF_sDsd
0x180001ce8  jmp     short loc_180001CEF
0x180001cea  mov     [rsi], rax
0x180001ced  xor     ebx, ebx
0x180001cef  cmp     [rsp+48h+lpLibFileName], 0
0x180001cf5  jz      short loc_180001D01
0x180001cf7  mov     rcx, [rsp+48h+lpLibFileName]
0x180001cfc  call    MSCryptFree
0x180001d01  mov     eax, ebx
0x180001d03  mov     rbx, [rsp+48h+arg_0]
0x180001d08  add     rsp, 40h
0x180001d0c  pop     rsi
0x180001d0d  retn
```
