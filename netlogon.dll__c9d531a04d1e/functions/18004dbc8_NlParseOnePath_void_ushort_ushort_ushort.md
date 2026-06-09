# NlParseOnePath(void *,ushort *,ushort *,ushort * *)

- ea: `0x18004dbc8`
- end: `0x18004dd94`
- name: `?NlParseOnePath@@YAKPEAXPEAG1PEAPEAG@Z`
- size: `460`
- prototype: `unsigned int(void *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x18004ed98`

## callees

- `0x180003170`
- `0x18000d710`
- `0x18000e270`
- `0x18000ed34`
- `0x18004dbc8`
- `0x180086d1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004dd2c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004dd41`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004dd2c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004dd41`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004dce9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004dce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dd11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dd11`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18004dd07`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18004dd07`
- `netutils!NetApiBufferFree` at `0x18004dd6d`
- `netutils!NetApiBufferFree` at `0x18004dd6d`
- `netutils!NetpwPathCanonicalize` at `0x18004dcc0`
- `netutils!NetpwPathCanonicalize` at `0x18004dcc0`

## string_xrefs

- `0x18004dc85`: `onecore\ds\netapi\svcdlls\logonsrv\server\parse.cxx`

## pseudocode

```c
__int64 __fastcall NlParseOnePath(void *a1, unsigned __int16 *a2, unsigned __int16 *a3, unsigned __int16 **a4)
{
  DWORD ConfigValue; // eax
  char *v9; // r9
  DWORD LastError; // ebx
  void *v11; // rdi
  unsigned __int16 *v12; // rax
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v15; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v16[528]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[528]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(v16, 0, 0x20Au);
  v15 = 0;
  v14 = 0;
  *a4 = 0;
  ConfigValue = NetpGetConfigValue(a1, a2, &v15);
  LastError = ConfigValue;
  if ( ConfigValue )
  {
    if ( ConfigValue != 2147 )
    {
LABEL_5:
      v11 = v15;
      goto LABEL_21;
    }
    if ( !a3 )
    {
      *a4 = 0;
      LastError = 0;
      goto LABEL_5;
    }
    v11 = (void *)NetpAllocWStrFromWStr(a3);
    if ( !v11 )
      goto LABEL_7;
  }
  else
  {
    v11 = v15;
  }
  if ( !v11 )
    NlAssertFailed("ValueT != NULL", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\parse.cxx", 296, v9);
  v14 = 0;
  LastError = NetpwPathCanonicalize(v11, v16, 522, 0, &v14, 0);
  if ( !LastError )
  {
    if ( v14 == 8198 )
    {
      _o_wcscpy_s(Buffer, 522);
    }
    else
    {
      if ( v14 != 0x2000 )
      {
        LastError = 2356;
        goto LABEL_21;
      }
      if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
      {
        LastError = GetLastError();
        goto LABEL_21;
      }
      _o_wcscat_s(Buffer, 522, L"\\");
      _o_wcscat_s(Buffer, 522, v16);
    }
    v12 = (unsigned __int16 *)NetpAllocWStrFromWStr(Buffer);
    *a4 = v12;
    if ( !v12 )
LABEL_7:
      LastError = 8;
  }
LABEL_21:
  if ( v11 )
    NetApiBufferFree(v11);
  return LastError;
}

```

## disassembly

```asm
0x18004dbc8  push    rbp
0x18004dbca  push    rbx
0x18004dbcb  push    rsi
0x18004dbcc  push    rdi
0x18004dbcd  push    r12
0x18004dbcf  push    r14
0x18004dbd1  lea     rbp, [rsp-588h]
0x18004dbd9  sub     rsp, 688h
0x18004dbe0  mov     rax, cs:__security_cookie
0x18004dbe7  xor     rax, rsp
0x18004dbea  mov     [rbp+5B0h+var_40], rax
0x18004dbf1  mov     rsi, r8
0x18004dbf4  mov     rdi, rdx
0x18004dbf7  mov     rbx, rcx
0x18004dbfa  mov     r12d, 20Ah
0x18004dc00  mov     r8d, r12d; Size
0x18004dc03  lea     rcx, [rsp+6B0h+var_670]; void *
0x18004dc08  xor     edx, edx; Val
0x18004dc0a  mov     r14, r9
0x18004dc0d  call    memset_0
0x18004dc12  lea     r8, [rsp+6B0h+var_678]
0x18004dc17  mov     [rsp+6B0h+var_678], 0
0x18004dc20  mov     rdx, rdi
0x18004dc23  mov     [rsp+6B0h+var_680], 0
0x18004dc2b  mov     rcx, rbx
0x18004dc2e  mov     qword ptr [r14], 0
0x18004dc35  call    NetpGetConfigValue
0x18004dc3a  mov     ebx, eax
0x18004dc3c  test    eax, eax
0x18004dc3e  jz      short loc_18004DC75
0x18004dc40  cmp     eax, 863h
0x18004dc45  jnz     short loc_18004DC51
0x18004dc47  test    rsi, rsi
0x18004dc4a  jnz     short loc_18004DC5B
0x18004dc4c  mov     [r14], rsi
0x18004dc4f  xor     ebx, ebx
0x18004dc51  mov     rdi, [rsp+6B0h+var_678]
0x18004dc56  jmp     loc_18004DD65
0x18004dc5b  mov     rcx, rsi; Src
0x18004dc5e  call    NetpAllocWStrFromWStr
0x18004dc63  mov     rdi, rax
0x18004dc66  test    rax, rax
0x18004dc69  jnz     short loc_18004DC7A
0x18004dc6b  mov     ebx, 8
0x18004dc70  jmp     loc_18004DD65
0x18004dc75  mov     rdi, [rsp+6B0h+var_678]
0x18004dc7a  test    rdi, rdi
0x18004dc7d  jnz     short loc_18004DC98
0x18004dc7f  mov     r8d, 128h; unsigned int
0x18004dc85  lea     rdx, aOnecoreDsNetap_29; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18004dc8c  lea     rcx, aValuetNull; "ValueT != NULL"
0x18004dc93  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18004dc98  lea     rax, [rsp+6B0h+var_680]
0x18004dc9d  mov     [rsp+6B0h+var_688], 0
0x18004dca5  xor     r9d, r9d
0x18004dca8  mov     [rsp+6B0h+var_690], rax
0x18004dcad  mov     r8d, r12d
0x18004dcb0  mov     [rsp+6B0h+var_680], 0
0x18004dcb8  lea     rdx, [rsp+6B0h+var_670]
0x18004dcbd  mov     rcx, rdi
0x18004dcc0  call    cs:__imp_NetpwPathCanonicalize
0x18004dcc6  mov     ebx, eax
0x18004dcc8  test    eax, eax
0x18004dcca  jnz     loc_18004DD65
0x18004dcd0  cmp     [rsp+6B0h+var_680], 2006h
0x18004dcd8  jnz     short loc_18004DCF1
0x18004dcda  lea     r8, [rsp+6B0h+var_670]
0x18004dcdf  mov     rdx, r12
0x18004dce2  lea     rcx, [rbp+5B0h+Buffer]
0x18004dce9  call    cs:__imp__o_wcscpy_s
0x18004dcef  jmp     short loc_18004DD47
0x18004dcf1  cmp     [rsp+6B0h+var_680], 2000h
0x18004dcf9  jnz     short loc_18004DD60
0x18004dcfb  mov     edx, 104h; uSize
0x18004dd00  lea     rcx, [rbp+5B0h+Buffer]; lpBuffer
0x18004dd07  call    cs:__imp_GetSystemWindowsDirectoryW
0x18004dd0d  test    eax, eax
0x18004dd0f  jnz     short loc_18004DD1B
0x18004dd11  call    cs:__imp_GetLastError
0x18004dd17  mov     ebx, eax
0x18004dd19  jmp     short loc_18004DD65
0x18004dd1b  lea     r8, SubStr; "\\"
0x18004dd22  mov     rdx, r12
0x18004dd25  lea     rcx, [rbp+5B0h+Buffer]
0x18004dd2c  call    cs:__imp__o_wcscat_s
0x18004dd32  lea     r8, [rsp+6B0h+var_670]
0x18004dd37  mov     rdx, r12
0x18004dd3a  lea     rcx, [rbp+5B0h+Buffer]
0x18004dd41  call    cs:__imp__o_wcscat_s
0x18004dd47  lea     rcx, [rbp+5B0h+Buffer]; Src
0x18004dd4e  call    NetpAllocWStrFromWStr
0x18004dd53  mov     [r14], rax
0x18004dd56  test    rax, rax
0x18004dd59  jnz     short loc_18004DD65
0x18004dd5b  jmp     loc_18004DC6B
0x18004dd60  mov     ebx, 934h
0x18004dd65  test    rdi, rdi
0x18004dd68  jz      short loc_18004DD73
0x18004dd6a  mov     rcx, rdi; Buffer
0x18004dd6d  call    cs:__imp_NetApiBufferFree
0x18004dd73  mov     eax, ebx
0x18004dd75  mov     rcx, [rbp+5B0h+var_40]
0x18004dd7c  xor     rcx, rsp; StackCookie
0x18004dd7f  call    __security_check_cookie
0x18004dd84  add     rsp, 688h
0x18004dd8b  pop     r14
0x18004dd8d  pop     r12
0x18004dd8f  pop     rdi
0x18004dd90  pop     rsi
0x18004dd91  pop     rbx
0x18004dd92  pop     rbp
0x18004dd93  retn
```
