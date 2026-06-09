# CGenerateMSI::GenerateMSIFileName(ushort *,ushort * *)

- ea: `0x18002deac`
- end: `0x18002e0c1`
- name: `?GenerateMSIFileName@CGenerateMSI@@AEAAJPEAGPEAPEAG@Z`
- size: `533`
- prototype: `int(CGenerateMSI *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002b820`
- `0x18002c050`
- `0x18002c300`
- `0x18002cc60`
- `0x18002cef0`

## callees

- `0x18000a01c`
- `0x1800136d8`
- `0x18001ec1c`
- `0x18002deac`
- `0x180055550`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002e00f`
- `msvcrt!_wcsnicmp` at `0x18002e00f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dfd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dfd9`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x18002df26`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x18002df26`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18002df2e`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18002df2e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x18002df62`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x18002df62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002dfc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e078`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e08e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002dfc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e078`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e08e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002df4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e043`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002df4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e043`

## pseudocode

```c
__int64 __fastcall CGenerateMSI::GenerateMSIFileName(CGenerateMSI *this, unsigned __int16 *a2, LPVOID *a3)
{
  __int64 v5; // r15
  int v6; // r14d
  __int64 v7; // rbp
  DWORD v8; // ebx
  WCHAR *v9; // rdi
  int i; // r12d
  DWORD LongPathNameW; // eax
  signed int v12; // ebx
  signed int LastError; // eax
  unsigned __int16 *v14; // rax
  wchar_t String1[1032]; // [rsp+20h] [rbp-858h] BYREF

  if ( !a2 || !a3 )
  {
    v12 = -2147467261;
LABEL_32:
    v9 = 0;
    goto LABEL_33;
  }
  *a3 = 0;
  LODWORD(v5) = 0;
  String1[0] = 0;
  v6 = 0;
  v7 = -1;
  while ( 2 )
  {
    if ( v6 >= 2 )
    {
      if ( !_wcsnicmp(String1, &String1[(unsigned int)(v5 + 1)], (unsigned int)v5) )
      {
        if ( 2 * (unsigned __int64)(unsigned int)v5 >= 0x804 )
          _report_rangecheckfailure(2LL * (unsigned int)v5);
        String1[(unsigned int)v5] = 0;
      }
      do
        ++v7;
      while ( String1[v7] );
      v14 = (unsigned __int16 *)CoTaskMemAlloc(2 * v7 + 2);
      *a3 = v14;
      if ( v14 )
      {
        v12 = StringCchCopyW(v14, v7 + 1, String1);
        if ( v12 < 0 )
        {
          CoTaskMemFree(*a3);
          *a3 = 0;
        }
      }
      else
      {
        v12 = -2147024882;
      }
      goto LABEL_32;
    }
    v8 = 0;
    v9 = 0;
    for ( i = 1; ; i = 0 )
    {
      if ( v6 )
        LongPathNameW = GetLongPathNameW(a2, v9, v8);
      else
        LongPathNameW = GetShortPathNameW(a2, v9, v8);
      if ( !LongPathNameW )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_33;
      }
      if ( !i )
        break;
      v8 = LongPathNameW + 1;
      v9 = (WCHAR *)CoTaskMemAlloc(2LL * (LongPathNameW + 1));
      if ( !v9 )
      {
        v12 = -2147024882;
        goto LABEL_33;
      }
    }
    PathStripPathW(v9);
    v12 = StringCchCatW(String1, 0x402u, v9);
    if ( v12 >= 0 )
    {
      if ( v6 )
        goto LABEL_18;
      v5 = -1;
      do
        ++v5;
      while ( String1[v5] );
      v12 = StringCchCatW(String1, 0x402u, L"|");
      if ( v12 >= 0 )
      {
LABEL_18:
        CoTaskMemFree(v9);
        ++v6;
        continue;
      }
    }
    break;
  }
LABEL_33:
  CoTaskMemFree(v9);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002deac  mov     [rsp+arg_0], rbx
0x18002deb1  push    rbp
0x18002deb2  push    rsi
0x18002deb3  push    rdi
0x18002deb4  push    r12
0x18002deb6  push    r13
0x18002deb8  push    r14
0x18002deba  push    r15
0x18002debc  sub     rsp, 840h
0x18002dec3  mov     rax, cs:__security_cookie
0x18002deca  xor     rax, rsp
0x18002decd  mov     [rsp+878h+var_48], rax
0x18002ded5  xor     r12d, r12d
0x18002ded8  mov     rsi, r8
0x18002dedb  mov     r13, rdx
0x18002dede  test    rdx, rdx
0x18002dee1  jz      loc_18002E083
0x18002dee7  test    r8, r8
0x18002deea  jz      loc_18002E083
0x18002def0  mov     [r8], r12
0x18002def3  mov     r15d, r12d
0x18002def6  mov     [rsp+878h+String1], r12w
0x18002defc  mov     r14d, r12d
0x18002deff  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18002df03  cmp     r14d, 2
0x18002df07  jge     loc_18002DFF7
0x18002df0d  xor     eax, eax
0x18002df0f  mov     ebx, r12d
0x18002df12  mov     edi, eax
0x18002df14  lea     r12d, [rax+1]
0x18002df18  mov     r8d, ebx; cchBuffer
0x18002df1b  mov     rdx, rdi; lpszLongPath
0x18002df1e  mov     rcx, r13; lpszShortPath
0x18002df21  test    r14d, r14d
0x18002df24  jnz     short loc_18002DF2E
0x18002df26  call    cs:__imp_GetShortPathNameW
0x18002df2c  jmp     short loc_18002DF34
0x18002df2e  call    cs:__imp_GetLongPathNameW
0x18002df34  mov     ebx, eax
0x18002df36  test    eax, eax
0x18002df38  jz      loc_18002DFD9
0x18002df3e  test    r12d, r12d
0x18002df41  jz      short loc_18002DF5F
0x18002df43  inc     ebx
0x18002df45  mov     ecx, ebx
0x18002df47  add     rcx, rcx; cb
0x18002df4a  call    cs:__imp_CoTaskMemAlloc
0x18002df50  mov     rdi, rax
0x18002df53  xor     eax, eax
0x18002df55  test    rdi, rdi
0x18002df58  jz      short loc_18002DFCF
0x18002df5a  mov     r12d, eax
0x18002df5d  jmp     short loc_18002DF18
0x18002df5f  mov     rcx, rdi; pszPath
0x18002df62  call    cs:__imp_PathStripPathW
0x18002df68  mov     r8, rdi; unsigned __int16 *
0x18002df6b  lea     rcx, [rsp+878h+String1]; unsigned __int16 *
0x18002df70  mov     edx, 402h; unsigned __int64
0x18002df75  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002df7a  xor     r12d, r12d
0x18002df7d  mov     ebx, eax
0x18002df7f  test    eax, eax
0x18002df81  js      loc_18002E08B
0x18002df87  test    r14d, r14d
0x18002df8a  jnz     short loc_18002DFBE
0x18002df8c  lea     rax, [rsp+878h+String1]
0x18002df91  mov     r15, rbp
0x18002df94  inc     r15
0x18002df97  cmp     [rax+r15*2], r12w
0x18002df9c  jnz     short loc_18002DF94
0x18002df9e  lea     r8, asc_18005FAD8; "|"
0x18002dfa5  mov     edx, 402h; unsigned __int64
0x18002dfaa  lea     rcx, [rsp+878h+String1]; unsigned __int16 *
0x18002dfaf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002dfb4  mov     ebx, eax
0x18002dfb6  test    eax, eax
0x18002dfb8  js      loc_18002E08B
0x18002dfbe  mov     rcx, rdi; pv
0x18002dfc1  call    cs:__imp_CoTaskMemFree
0x18002dfc7  inc     r14d
0x18002dfca  jmp     loc_18002DF03
0x18002dfcf  mov     ebx, 8007000Eh
0x18002dfd4  jmp     loc_18002E08B
0x18002dfd9  call    cs:__imp_GetLastError
0x18002dfdf  mov     ebx, eax
0x18002dfe1  test    eax, eax
0x18002dfe3  jle     loc_18002E08B
0x18002dfe9  movzx   ebx, ax
0x18002dfec  or      ebx, 80070000h
0x18002dff2  jmp     loc_18002E08B
0x18002dff7  lea     eax, [r15+1]
0x18002dffb  mov     r8d, r15d; MaxCount
0x18002dffe  lea     rdx, [rsp+878h+String1]
0x18002e003  mov     ebx, r15d
0x18002e006  lea     rdx, [rdx+rax*2]; String2
0x18002e00a  lea     rcx, [rsp+878h+String1]; String1
0x18002e00f  call    cs:__imp__wcsnicmp
0x18002e015  test    eax, eax
0x18002e017  jnz     short loc_18002E02C
0x18002e019  lea     rcx, [rbx+rbx]
0x18002e01d  cmp     rcx, 804h
0x18002e024  jnb     short loc_18002E058
0x18002e026  mov     [rsp+rcx+878h+String1], r12w
0x18002e02c  lea     rax, [rsp+878h+String1]
0x18002e031  inc     rbp
0x18002e034  cmp     [rax+rbp*2], r12w
0x18002e039  jnz     short loc_18002E031
0x18002e03b  lea     rcx, ds:2[rbp*2]; cb
0x18002e043  call    cs:__imp_CoTaskMemAlloc
0x18002e049  mov     [rsi], rax
0x18002e04c  test    rax, rax
0x18002e04f  jnz     short loc_18002E05E
0x18002e051  mov     ebx, 8007000Eh
0x18002e056  jmp     short loc_18002E088
0x18002e058  call    __report_rangecheckfailure
0x18002e05e  lea     r8, [rsp+878h+String1]; unsigned __int16 *
0x18002e063  mov     rcx, rax; unsigned __int16 *
0x18002e066  lea     rdx, [rbp+1]; unsigned __int64
0x18002e06a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e06f  mov     ebx, eax
0x18002e071  test    eax, eax
0x18002e073  jns     short loc_18002E088
0x18002e075  mov     rcx, [rsi]; pv
0x18002e078  call    cs:__imp_CoTaskMemFree
0x18002e07e  mov     [rsi], r12
0x18002e081  jmp     short loc_18002E088
0x18002e083  mov     ebx, 80004003h
0x18002e088  mov     rdi, r12
0x18002e08b  mov     rcx, rdi; pv
0x18002e08e  call    cs:__imp_CoTaskMemFree
0x18002e094  mov     eax, ebx
0x18002e096  mov     rcx, [rsp+878h+var_48]
0x18002e09e  xor     rcx, rsp; StackCookie
0x18002e0a1  call    __security_check_cookie
0x18002e0a6  mov     rbx, [rsp+878h+arg_0]
0x18002e0ae  add     rsp, 840h
0x18002e0b5  pop     r15
0x18002e0b7  pop     r14
0x18002e0b9  pop     r13
0x18002e0bb  pop     r12
0x18002e0bd  pop     rdi
0x18002e0be  pop     rsi
0x18002e0bf  pop     rbp
0x18002e0c0  retn
```
