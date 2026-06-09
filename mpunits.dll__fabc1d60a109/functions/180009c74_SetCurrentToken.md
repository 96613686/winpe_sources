# SetCurrentToken

- ea: `0x180009c74`
- end: `0x180009d1b`
- name: `SetCurrentToken`
- size: `167`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180009740`
- `0x1800098b0`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x180009c74`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180009ca4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180009ca4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009c7f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cc4`

## string_xrefs

- `0x180009c96`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall SetCurrentToken(HANDLE Token)
{
  DWORD LastError; // ebx
  HMODULE ModuleHandleA; // rax
  signed int v3; // eax

  if ( SetThreadToken(0, Token) )
    return 0;
  LastError = GetLastError();
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_FormatString_FormatMessage(ModuleHandleA, 2024, LastError);
  v3 = GetLastError();
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  MI_ReportErrorDetails_ForCustomError(v3, (int)L"HRESULT", 0, 0);
  return 2;
}

```

## disassembly

```asm
0x180009c74  push    rbx
0x180009c76  sub     rsp, 40h
0x180009c7a  mov     rdx, rcx; Token
0x180009c7d  xor     ecx, ecx; Thread
0x180009c7f  call    cs:__imp_SetThreadToken
0x180009c85  test    eax, eax
0x180009c87  jnz     loc_180009D13
0x180009c8d  call    cs:__imp_GetLastError
0x180009c93  xorps   xmm0, xmm0
0x180009c96  lea     rcx, ModuleName; "mpunits.dll"
0x180009c9d  movups  [rsp+48h+var_18], xmm0
0x180009ca2  mov     ebx, eax
0x180009ca4  call    cs:__imp_GetModuleHandleA
0x180009caa  mov     r8d, ebx
0x180009cad  mov     edx, 7E8h
0x180009cb2  mov     rcx, rax
0x180009cb5  call    _Intlstr_FormatString_FormatMessage
0x180009cba  mov     qword ptr [rsp+48h+var_18], rax
0x180009cbf  mov     byte ptr [rsp+48h+var_18+8], 1
0x180009cc4  call    cs:__imp_GetLastError
0x180009cca  test    eax, eax
0x180009ccc  jle     short loc_180009CD6
0x180009cce  movzx   eax, ax
0x180009cd1  or      eax, 80070000h
0x180009cd6  movaps  xmm0, [rsp+48h+var_18]
0x180009cdb  lea     r9, [rsp+48h+var_18]
0x180009ce0  mov     [rsp+48h+var_20], 0; __int64
0x180009ce9  lea     rdx, aHresult; "HRESULT"
0x180009cf0  mov     r8d, 12h
0x180009cf6  movdqa  [rsp+48h+var_18], xmm0
0x180009cfc  mov     ecx, eax; int
0x180009cfe  mov     [rsp+48h+var_28], 0; __int64
0x180009d07  call    MI_ReportErrorDetails_ForCustomError
0x180009d0c  mov     eax, 2
0x180009d11  jmp     short loc_180009D15
0x180009d13  xor     eax, eax
0x180009d15  add     rsp, 40h
0x180009d19  pop     rbx
0x180009d1a  retn
```
