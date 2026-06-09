# SymSetSearchPathW

- ea: `0x18000dac0`
- end: `0x18000dd8a`
- name: `SymSetSearchPathW`
- size: `714`
- prototype: `BOOL __stdcall(HANDLE hProcess, PCWSTR SearchPathA)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18000d670`
- `0x1801a84d0`

## callees

- `0x1800089f0`
- `0x180008a38`
- `0x180008ad0`
- `0x18000aeec`
- `0x18000dac0`
- `0x18000ddcc`
- `0x18000dfac`
- `0x180012ed4`
- `0x180021374`
- `0x1800273fc`
- `0x180027430`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000dc0b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000dc0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dbef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dbef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd5d`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000dbae`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000dbc7`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000dc86`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000dce3`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000dbae`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000dbc7`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000dc86`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000dce3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000db44`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000db82`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000db44`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000db82`

## string_xrefs

- `0x18000dbc0`: `_NT_ALT_SYMBOL_PATH`
- `0x18000dcdc`: `_NT_ALT_SYMBOL_PATH`
- `0x18000dba7`: `_NT_SYMBOL_PATH`
- `0x18000dc7f`: `_NT_SYMBOL_PATH`
- `0x18000dd44`: `Symbol Search Path: %s\n`
- `0x18000dc9e`: `_NT_SYMBOL_PATH: %s\n`
- `0x18000dcfb`: `_NT_ALT_SYMBOL_PATH: %s\n`

## pseudocode

```c
BOOL __stdcall SymSetSearchPathW(HANDLE hProcess, PCWSTR SearchPathA)
{
  struct _PROCESS_ENTRY *ProcessEntry; // rax
  struct _PROCESS_ENTRY *v5; // rdi
  void *v7; // rcx
  DWORD v8; // eax
  DWORD v9; // ebx
  WCHAR *v10; // rax
  __int64 v11; // rax
  DWORD v12; // ebx
  unsigned int v13; // ebx
  wchar_t *v14; // rax
  __int64 v15; // rdx
  const wchar_t *v16; // rcx
  const wchar_t *v17; // r8
  wchar_t *v18; // r9
  WCHAR Dst[1040]; // [rsp+40h] [rbp-848h] BYREF

  memset_0(Dst, 0, sizeof(Dst));
  ProcessEntry = FindProcessEntry(hProcess);
  v5 = ProcessEntry;
  if ( !ProcessEntry )
  {
    SetLastError(6u);
    return 0;
  }
  v7 = (void *)*((_QWORD *)ProcessEntry + 8);
  if ( v7 )
  {
    FreeIt(v7);
    *((_QWORD *)v5 + 8) = 0;
  }
  if ( !SearchPathA )
  {
    v11 = 3;
    if ( (dword_1802AF9CC & 0x1000) == 0 )
    {
      v12 = GetEnvironmentVariableW(L"_NT_SYMBOL_PATH", 0, 0) + 3;
      v11 = v12 + GetEnvironmentVariableW(L"_NT_ALT_SYMBOL_PATH", 0, 0);
    }
    v13 = 2 * v11;
    v14 = (wchar_t *)pMemAlloc(2 * v11 + 2);
    v18 = v14;
    *((_QWORD *)v5 + 8) = v14;
    if ( !v14 )
    {
      SetLastError(8u);
      return 0;
    }
    if ( v13 )
    {
      v15 = v13;
      v17 = L".";
      v16 = L".";
      do
      {
        if ( !*v16++ )
          break;
        --v15;
      }
      while ( v15 );
      if ( v15 )
      {
        wcscpy_s(v18, v13, L".");
LABEL_22:
        if ( (dword_1802AF9CC & 0x1000) == 0 )
        {
          if ( GetEnvironmentVariableW(L"_NT_SYMBOL_PATH", Dst, 0x410u) )
          {
            if ( (unsigned int)spew() )
              _pwprint(v5, L"_NT_SYMBOL_PATH: %s\n", Dst);
            wcscat_s_ex(*((unsigned __int16 **)v5 + 8), v13, L";");
            wcscat_s_ex(*((unsigned __int16 **)v5 + 8), v13, Dst);
          }
          if ( GetEnvironmentVariableW(L"_NT_ALT_SYMBOL_PATH", Dst, 0x410u) )
          {
            if ( (unsigned int)spew() )
              _pwprint(v5, L"_NT_ALT_SYMBOL_PATH: %s\n", Dst);
            wcscat_s_ex(*((unsigned __int16 **)v5 + 8), v13, L";");
            wcscat_s_ex(*((unsigned __int16 **)v5 + 8), v13, Dst);
          }
        }
        goto LABEL_31;
      }
      *v18 = 0;
    }
    else
    {
      *v14 = 0;
    }
    *(_DWORD *)_o__errno(v16, v15, v17, v18) = 34;
    goto LABEL_22;
  }
  v8 = ExpandEnvironmentStringsW(SearchPathA, Dst, 0x410u);
  v9 = v8;
  if ( v8 >= 0x410 )
  {
    v10 = (WCHAR *)pMemAlloc(2LL * v8);
    *((_QWORD *)v5 + 8) = v10;
    ExpandEnvironmentStringsW(SearchPathA, v10, v9);
  }
  else
  {
    *((_QWORD *)v5 + 8) = StringDup(Dst);
  }
LABEL_31:
  PrepSearchPath(*((unsigned __int16 **)v5 + 8));
  if ( (unsigned int)spew() )
    _pwprint(v5, L"Symbol Search Path: %s\n", *((_QWORD *)v5 + 8));
  return 1;
}

```

## disassembly

```asm
0x18000dac0  mov     [rsp+arg_10], rbx
0x18000dac5  push    rdi
0x18000dac6  push    r14
0x18000dac8  push    r15
0x18000daca  sub     rsp, 870h
0x18000dad1  mov     rax, cs:__security_cookie
0x18000dad8  xor     rax, rsp
0x18000dadb  mov     [rsp+888h+var_28], rax
0x18000dae3  mov     r14, rdx
0x18000dae6  mov     rbx, rcx
0x18000dae9  xor     edx, edx; Val
0x18000daeb  mov     r8d, 820h; Size
0x18000daf1  lea     rcx, [rsp+888h+Dst]; void *
0x18000daf6  call    memset_0
0x18000dafb  nop
0x18000dafc  mov     rcx, rbx; void *
0x18000daff  call    ?FindProcessEntry@@YAPEAU_PROCESS_ENTRY@@PEAX@Z; FindProcessEntry(void *)
0x18000db04  mov     rdi, rax
0x18000db07  xor     r15d, r15d
0x18000db0a  test    rax, rax
0x18000db0d  jnz     short loc_18000DB1F
0x18000db0f  lea     ecx, [rax+6]; dwErrCode
0x18000db12  call    cs:__imp_SetLastError
0x18000db18  xor     eax, eax
0x18000db1a  jmp     loc_18000DD65
0x18000db1f  mov     rcx, [rax+40h]; lpMem
0x18000db23  test    rcx, rcx
0x18000db26  jz      short loc_18000DB31
0x18000db28  call    ?FreeIt@@YAXPEAX@Z; FreeIt(void *)
0x18000db2d  mov     [rdi+40h], r15
0x18000db31  test    r14, r14
0x18000db34  jz      short loc_18000DB8D
0x18000db36  mov     r8d, 410h; nSize
0x18000db3c  lea     rdx, [rsp+888h+Dst]; lpDst
0x18000db41  mov     rcx, r14; lpSrc
0x18000db44  call    cs:__imp_ExpandEnvironmentStringsW
0x18000db4a  mov     ebx, eax
0x18000db4c  mov     [rsp+888h+var_868], ebx
0x18000db50  cmp     eax, 410h
0x18000db55  jnb     short loc_18000DB6A
0x18000db57  lea     rcx, [rsp+888h+Dst]; Source
0x18000db5c  call    ?StringDup@@YAPEAGPEBG@Z; StringDup(ushort const *)
0x18000db61  mov     [rdi+40h], rax
0x18000db65  jmp     loc_18000DD2E
0x18000db6a  mov     rcx, rbx
0x18000db6d  add     rcx, rcx; dwBytes
0x18000db70  call    pMemAlloc
0x18000db75  mov     [rdi+40h], rax
0x18000db79  mov     r8d, ebx; nSize
0x18000db7c  mov     rdx, rax; lpDst
0x18000db7f  mov     rcx, r14; lpSrc
0x18000db82  call    cs:__imp_ExpandEnvironmentStringsW
0x18000db88  jmp     loc_18000DD2E
0x18000db8d  mov     eax, 3
0x18000db92  mov     [rsp+888h+var_868], eax
0x18000db96  test    cs:dword_1802AF9CC, 1000h
0x18000dba0  jnz     short loc_18000DBD3
0x18000dba2  xor     r8d, r8d; nSize
0x18000dba5  xor     edx, edx; lpBuffer
0x18000dba7  lea     rcx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x18000dbae  call    cs:__imp_GetEnvironmentVariableW
0x18000dbb4  lea     ebx, [rax+3]
0x18000dbb7  mov     [rsp+888h+var_868], ebx
0x18000dbbb  xor     r8d, r8d; nSize
0x18000dbbe  xor     edx, edx; lpBuffer
0x18000dbc0  lea     rcx, aNtAltSymbolPat; "_NT_ALT_SYMBOL_PATH"
0x18000dbc7  call    cs:__imp_GetEnvironmentVariableW
0x18000dbcd  add     eax, ebx
0x18000dbcf  mov     [rsp+888h+var_868], eax
0x18000dbd3  lea     rbx, [rax+rax]
0x18000dbd7  lea     rcx, [rbx+2]; dwBytes
0x18000dbdb  call    pMemAlloc
0x18000dbe0  mov     r9, rax
0x18000dbe3  mov     [rdi+40h], rax
0x18000dbe7  test    rax, rax
0x18000dbea  jnz     short loc_18000DBFC
0x18000dbec  lea     ecx, [rax+8]; dwErrCode
0x18000dbef  call    cs:__imp_SetLastError
0x18000dbf5  xor     eax, eax
0x18000dbf7  jmp     loc_18000DD65
0x18000dbfc  mov     ebx, ebx
0x18000dbfe  mov     [rsp+888h+var_868], ebx
0x18000dc02  test    rbx, rbx
0x18000dc05  jnz     short loc_18000DC19
0x18000dc07  mov     [rax], r15w
0x18000dc0b  call    cs:__imp__o__errno
0x18000dc11  mov     dword ptr [rax], 22h ; '"'
0x18000dc17  jmp     short loc_18000DC64
0x18000dc19  mov     rdx, rbx
0x18000dc1c  mov     [rsp+888h+var_858], rbx
0x18000dc21  lea     r8, asc_18022ACFC; "."
0x18000dc28  mov     rcx, r8
0x18000dc2b  mov     [rsp+888h+var_860], rcx
0x18000dc30  movzx   eax, word ptr [rcx]
0x18000dc33  add     rcx, 2
0x18000dc37  mov     [rsp+888h+var_860], rcx
0x18000dc3c  test    ax, ax
0x18000dc3f  jz      short loc_18000DC4E
0x18000dc41  sub     rdx, 1
0x18000dc45  mov     [rsp+888h+var_858], rdx
0x18000dc4a  jz      short loc_18000DC4E
0x18000dc4c  jmp     short loc_18000DC30
0x18000dc4e  test    rdx, rdx
0x18000dc51  jnz     short loc_18000DC59
0x18000dc53  mov     [r9], r15w
0x18000dc57  jmp     short loc_18000DC0B
0x18000dc59  mov     rdx, rbx; SizeInWords
0x18000dc5c  mov     rcx, r9; Destination
0x18000dc5f  call    wcscpy_s
0x18000dc64  test    cs:dword_1802AF9CC, 1000h
0x18000dc6e  jnz     loc_18000DD2E
0x18000dc74  mov     r8d, 410h; nSize
0x18000dc7a  lea     rdx, [rsp+888h+Dst]; lpBuffer
0x18000dc7f  lea     rcx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x18000dc86  call    cs:__imp_GetEnvironmentVariableW
0x18000dc8c  test    eax, eax
0x18000dc8e  jz      short loc_18000DCD1
0x18000dc90  call    ?spew@@YAHXZ; spew(void)
0x18000dc95  test    eax, eax
0x18000dc97  jz      short loc_18000DCAD
0x18000dc99  lea     r8, [rsp+888h+Dst]
0x18000dc9e  lea     rdx, aNtSymbolPathS; "_NT_SYMBOL_PATH: %s\n"
0x18000dca5  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x18000dca8  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18000dcad  lea     r8, asc_180253C24; ";"
0x18000dcb4  mov     rdx, rbx; unsigned __int64
0x18000dcb7  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18000dcbb  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x18000dcc0  lea     r8, [rsp+888h+Dst]; unsigned __int16 *
0x18000dcc5  mov     rdx, rbx; unsigned __int64
0x18000dcc8  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18000dccc  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x18000dcd1  mov     r8d, 410h; nSize
0x18000dcd7  lea     rdx, [rsp+888h+Dst]; lpBuffer
0x18000dcdc  lea     rcx, aNtAltSymbolPat; "_NT_ALT_SYMBOL_PATH"
0x18000dce3  call    cs:__imp_GetEnvironmentVariableW
0x18000dce9  test    eax, eax
0x18000dceb  jz      short loc_18000DD2E
0x18000dced  call    ?spew@@YAHXZ; spew(void)
0x18000dcf2  test    eax, eax
0x18000dcf4  jz      short loc_18000DD0A
0x18000dcf6  lea     r8, [rsp+888h+Dst]
0x18000dcfb  lea     rdx, aNtAltSymbolPat_0; "_NT_ALT_SYMBOL_PATH: %s\n"
0x18000dd02  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x18000dd05  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18000dd0a  lea     r8, asc_180253C24; ";"
0x18000dd11  mov     rdx, rbx; unsigned __int64
0x18000dd14  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18000dd18  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x18000dd1d  lea     r8, [rsp+888h+Dst]; unsigned __int16 *
0x18000dd22  mov     rdx, rbx; unsigned __int64
0x18000dd25  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18000dd29  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x18000dd2e  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18000dd32  call    ?PrepSearchPath@@YAXPEAG@Z; PrepSearchPath(ushort *)
0x18000dd37  call    ?spew@@YAHXZ; spew(void)
0x18000dd3c  test    eax, eax
0x18000dd3e  jz      short loc_18000DD54
0x18000dd40  mov     r8, [rdi+40h]
0x18000dd44  lea     rdx, aSymbolSearchPa_0; "Symbol Search Path: %s\n"
0x18000dd4b  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x18000dd4e  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18000dd53  nop
0x18000dd54  mov     eax, 1
0x18000dd59  jmp     short loc_18000DD65
0x18000dd5b  mov     ecx, eax; dwErrCode
0x18000dd5d  call    cs:__imp_SetLastError
0x18000dd63  xor     eax, eax
0x18000dd65  mov     rcx, [rsp+888h+var_28]
0x18000dd6d  xor     rcx, rsp; StackCookie
0x18000dd70  call    __security_check_cookie
0x18000dd75  mov     rbx, [rsp+888h+arg_10]
0x18000dd7d  add     rsp, 870h
0x18000dd84  pop     r15
0x18000dd86  pop     r14
0x18000dd88  pop     rdi
0x18000dd89  retn
```
