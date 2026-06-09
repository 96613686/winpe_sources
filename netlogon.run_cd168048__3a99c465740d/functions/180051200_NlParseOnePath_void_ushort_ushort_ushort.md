# NlParseOnePath(void *,ushort *,ushort *,ushort * *)

- ea: `0x180051200`
- end: `0x1800513f7`
- name: `?NlParseOnePath@@YAKPEAXPEAG1PEAPEAG@Z`
- size: `503`
- prototype: `unsigned int(void *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x180052484`

## callees

- `0x180003250`
- `0x18000dd00`
- `0x18000e910`
- `0x18000f3e4`
- `0x180051200`
- `0x18008d108`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005137c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180051397`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005137c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180051397`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180051327`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180051327`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005135b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005135b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18005134b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18005134b`
- `netutils!NetApiBufferFree` at `0x1800513c9`
- `netutils!NetApiBufferFree` at `0x1800513c9`
- `netutils!NetpwPathCanonicalize` at `0x1800512f8`
- `netutils!NetpwPathCanonicalize` at `0x1800512f8`

## string_xrefs

- `0x1800512bd`: `onecore\ds\netapi\svcdlls\logonsrv\server\parse.cxx`

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
    NlAssertFailed("ValueT != NULL", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\parse.cxx", 0x128u, v9);
  v14 = 0;
  LastError = NetpwPathCanonicalize(v11, v16, 522, 0, &v14, 0);
  if ( !LastError )
  {
    if ( v14 == 8198 )
    {
      _o_wcscpy_s(Buffer, 522, v16);
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
0x180051200  push    rbp
0x180051202  push    rbx
0x180051203  push    rsi
0x180051204  push    rdi
0x180051205  push    r12
0x180051207  push    r14
0x180051209  lea     rbp, [rsp-588h]
0x180051211  sub     rsp, 688h
0x180051218  mov     rax, cs:__security_cookie
0x18005121f  xor     rax, rsp
0x180051222  mov     [rbp+5B0h+var_40], rax
0x180051229  mov     rsi, r8
0x18005122c  mov     rdi, rdx
0x18005122f  mov     rbx, rcx
0x180051232  mov     r12d, 20Ah
0x180051238  mov     r8d, r12d; Size
0x18005123b  lea     rcx, [rsp+6B0h+var_670]; void *
0x180051240  xor     edx, edx; Val
0x180051242  mov     r14, r9
0x180051245  call    memset_0
0x18005124a  lea     r8, [rsp+6B0h+var_678]
0x18005124f  mov     [rsp+6B0h+var_678], 0
0x180051258  mov     rdx, rdi
0x18005125b  mov     [rsp+6B0h+var_680], 0
0x180051263  mov     rcx, rbx
0x180051266  mov     qword ptr [r14], 0
0x18005126d  call    NetpGetConfigValue
0x180051272  mov     ebx, eax
0x180051274  test    eax, eax
0x180051276  jz      short loc_1800512AD
0x180051278  cmp     eax, 863h
0x18005127d  jnz     short loc_180051289
0x18005127f  test    rsi, rsi
0x180051282  jnz     short loc_180051293
0x180051284  mov     [r14], rsi
0x180051287  xor     ebx, ebx
0x180051289  mov     rdi, [rsp+6B0h+var_678]
0x18005128e  jmp     loc_1800513C1
0x180051293  mov     rcx, rsi; Src
0x180051296  call    NetpAllocWStrFromWStr
0x18005129b  mov     rdi, rax
0x18005129e  test    rax, rax
0x1800512a1  jnz     short loc_1800512B2
0x1800512a3  mov     ebx, 8
0x1800512a8  jmp     loc_1800513C1
0x1800512ad  mov     rdi, [rsp+6B0h+var_678]
0x1800512b2  test    rdi, rdi
0x1800512b5  jnz     short loc_1800512D0
0x1800512b7  mov     r8d, 128h; unsigned int
0x1800512bd  lea     rdx, aOnecoreDsNetap_29; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800512c4  lea     rcx, aValuetNull; "ValueT != NULL"
0x1800512cb  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800512d0  lea     rax, [rsp+6B0h+var_680]
0x1800512d5  mov     [rsp+6B0h+var_688], 0
0x1800512dd  xor     r9d, r9d
0x1800512e0  mov     [rsp+6B0h+var_690], rax
0x1800512e5  mov     r8d, r12d
0x1800512e8  mov     [rsp+6B0h+var_680], 0
0x1800512f0  lea     rdx, [rsp+6B0h+var_670]
0x1800512f5  mov     rcx, rdi
0x1800512f8  call    cs:__imp_NetpwPathCanonicalize
0x1800512ff  nop     dword ptr [rax+rax+00h]
0x180051304  mov     ebx, eax
0x180051306  test    eax, eax
0x180051308  jnz     loc_1800513C1
0x18005130e  cmp     [rsp+6B0h+var_680], 2006h
0x180051316  jnz     short loc_180051335
0x180051318  lea     r8, [rsp+6B0h+var_670]
0x18005131d  mov     rdx, r12
0x180051320  lea     rcx, [rbp+5B0h+Buffer]
0x180051327  call    cs:__imp__o_wcscpy_s
0x18005132e  nop     dword ptr [rax+rax+00h]
0x180051333  jmp     short loc_1800513A3
0x180051335  cmp     [rsp+6B0h+var_680], 2000h
0x18005133d  jnz     short loc_1800513BC
0x18005133f  mov     edx, 104h; uSize
0x180051344  lea     rcx, [rbp+5B0h+Buffer]; lpBuffer
0x18005134b  call    cs:__imp_GetSystemWindowsDirectoryW
0x180051352  nop     dword ptr [rax+rax+00h]
0x180051357  test    eax, eax
0x180051359  jnz     short loc_18005136B
0x18005135b  call    cs:__imp_GetLastError
0x180051362  nop     dword ptr [rax+rax+00h]
0x180051367  mov     ebx, eax
0x180051369  jmp     short loc_1800513C1
0x18005136b  lea     r8, SubStr; "\\"
0x180051372  mov     rdx, r12
0x180051375  lea     rcx, [rbp+5B0h+Buffer]
0x18005137c  call    cs:__imp__o_wcscat_s
0x180051383  nop     dword ptr [rax+rax+00h]
0x180051388  lea     r8, [rsp+6B0h+var_670]
0x18005138d  mov     rdx, r12
0x180051390  lea     rcx, [rbp+5B0h+Buffer]
0x180051397  call    cs:__imp__o_wcscat_s
0x18005139e  nop     dword ptr [rax+rax+00h]
0x1800513a3  lea     rcx, [rbp+5B0h+Buffer]; Src
0x1800513aa  call    NetpAllocWStrFromWStr
0x1800513af  mov     [r14], rax
0x1800513b2  test    rax, rax
0x1800513b5  jnz     short loc_1800513C1
0x1800513b7  jmp     loc_1800512A3
0x1800513bc  mov     ebx, 934h
0x1800513c1  test    rdi, rdi
0x1800513c4  jz      short loc_1800513D5
0x1800513c6  mov     rcx, rdi; Buffer
0x1800513c9  call    cs:__imp_NetApiBufferFree
0x1800513d0  nop     dword ptr [rax+rax+00h]
0x1800513d5  mov     eax, ebx
0x1800513d7  mov     rcx, [rbp+5B0h+var_40]
0x1800513de  xor     rcx, rsp; StackCookie
0x1800513e1  call    __security_check_cookie
0x1800513e6  add     rsp, 688h
0x1800513ed  pop     r14
0x1800513ef  pop     r12
0x1800513f1  pop     rdi
0x1800513f2  pop     rsi
0x1800513f3  pop     rbx
0x1800513f4  pop     rbp
0x1800513f5  retn
```
