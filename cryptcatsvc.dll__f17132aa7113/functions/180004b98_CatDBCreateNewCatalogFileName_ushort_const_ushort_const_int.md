# _CatDBCreateNewCatalogFileName(ushort const *,ushort const *,int *)

- ea: `0x180004b98`
- end: `0x180004d2a`
- name: `?_CatDBCreateNewCatalogFileName@@YAPEAGPEBG0PEAH@Z`
- size: `402`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180017a04`

## callees

- `0x1800015b0`
- `0x180003d48`
- `0x180004b98`
- `0x180005640`
- `0x18000a59c`
- `0x18000be40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004cd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004cd4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004c08`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004cc0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004c08`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004cc0`

## pseudocode

```c
unsigned __int16 *__fastcall _CatDBCreateNewCatalogFileName(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int *a3)
{
  const WCHAR *v5; // rax
  unsigned int v6; // edx
  unsigned __int16 *v7; // rcx
  WCHAR *v8; // rbx
  unsigned int v9; // r8d
  HANDLE FileW; // rbp
  DWORD LastError; // eax
  int v12; // ebp
  unsigned int v13; // esi
  const WCHAR *v14; // rax
  HANDLE v15; // rax
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-B0h]
  unsigned __int16 v18[56]; // [rsp+40h] [rbp-98h] BYREF

  if ( a2 )
  {
    v5 = _CATDBConstructWSTRPath(a1, a2);
    v8 = (WCHAR *)v5;
    if ( v5 )
    {
      FileW = CreateFileW(v5, 0xC0000000, 0, 0, 3u, 0x80u, 0);
      LastError = GetLastError();
      if ( FileW == (HANDLE)-1LL && (LastError - 2 <= 1 || LastError == 53) )
      {
        *a3 = 0;
      }
      else
      {
        *a3 = 1;
        if ( FileW != (HANDLE)-1LL )
          CloseHandle(FileW);
      }
    }
    else
    {
      v9 = 1202;
LABEL_18:
      ErrLog_LogError(v7, v6, v9, 0, 0, dwFlagsAndAttributes);
      return 0;
    }
  }
  else
  {
    v8 = 0;
    *a3 = 0;
    v12 = 0;
    v13 = 1;
    while ( !v12 && v13 )
    {
      StringCchPrintfW(v18, 0x38u, L"%X.CAT", v13);
      v14 = _CATDBConstructWSTRPath(a1, v18);
      v8 = (WCHAR *)v14;
      if ( !v14 )
      {
        v9 = 1256;
        goto LABEL_18;
      }
      v15 = CreateFileW(v14, 0xC0000000, 0, 0, 3u, 0x80u, 0);
      if ( v15 == (HANDLE)-1LL )
      {
        v12 = 1;
      }
      else
      {
        CloseHandle(v15);
        _CatDBFree(v8);
        v8 = 0;
        ++v13;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180004b98  mov     [rsp+arg_18], rbx
0x180004b9d  push    rbp
0x180004b9e  push    rsi
0x180004b9f  push    r14
0x180004ba1  sub     rsp, 0C0h
0x180004ba8  mov     rax, cs:__security_cookie
0x180004baf  xor     rax, rsp
0x180004bb2  mov     [rsp+0D8h+var_28], rax
0x180004bba  mov     rsi, r8
0x180004bbd  mov     r14, rcx
0x180004bc0  test    rdx, rdx
0x180004bc3  jz      loc_180004C53
0x180004bc9  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x180004bce  mov     rbx, rax
0x180004bd1  test    rax, rax
0x180004bd4  jnz     short loc_180004BE1
0x180004bd6  mov     r8d, 4B2h
0x180004bdc  jmp     loc_180004CF1
0x180004be1  mov     [rsp+0D8h+hTemplateFile], 0; hTemplateFile
0x180004bea  xor     r9d, r9d; lpSecurityAttributes
0x180004bed  mov     [rsp+0D8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180004bf5  xor     r8d, r8d; dwShareMode
0x180004bf8  mov     edx, 0C0000000h; dwDesiredAccess
0x180004bfd  mov     [rsp+0D8h+dwCreationDisposition], 3; dwCreationDisposition
0x180004c05  mov     rcx, rax; lpFileName
0x180004c08  call    cs:__imp_CreateFileW
0x180004c0e  mov     rbp, rax
0x180004c11  call    cs:__imp_GetLastError
0x180004c17  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180004c1b  jnz     short loc_180004C35
0x180004c1d  lea     ecx, [rax-2]
0x180004c20  cmp     ecx, 1
0x180004c23  jbe     short loc_180004C2A
0x180004c25  cmp     eax, 35h ; '5'
0x180004c28  jnz     short loc_180004C35
0x180004c2a  mov     dword ptr [rsi], 0
0x180004c30  jmp     loc_180004D03
0x180004c35  mov     dword ptr [rsi], 1
0x180004c3b  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180004c3f  jz      loc_180004D03
0x180004c45  mov     rcx, rbp; hObject
0x180004c48  call    cs:__imp_CloseHandle
0x180004c4e  jmp     loc_180004D03
0x180004c53  xor     ebx, ebx
0x180004c55  mov     [r8], ebx
0x180004c58  xor     ebp, ebp
0x180004c5a  lea     esi, [rbx+1]
0x180004c5d  test    ebp, ebp
0x180004c5f  jnz     loc_180004D03
0x180004c65  test    esi, esi
0x180004c67  jz      loc_180004D03
0x180004c6d  mov     r9d, esi
0x180004c70  lea     r8, aXCat; "%X.CAT"
0x180004c77  lea     edx, [rbp+38h]; unsigned __int64
0x180004c7a  lea     rcx, [rsp+0D8h+var_98]; unsigned __int16 *
0x180004c7f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004c84  lea     rdx, [rsp+0D8h+var_98]; unsigned __int16 *
0x180004c89  mov     rcx, r14; unsigned __int16 *
0x180004c8c  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x180004c91  mov     rbx, rax
0x180004c94  test    rax, rax
0x180004c97  jz      short loc_180004CEB
0x180004c99  mov     [rsp+0D8h+hTemplateFile], 0; hTemplateFile
0x180004ca2  xor     r9d, r9d; lpSecurityAttributes
0x180004ca5  mov     [rsp+0D8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180004cad  xor     r8d, r8d; dwShareMode
0x180004cb0  mov     edx, 0C0000000h; dwDesiredAccess
0x180004cb5  mov     [rsp+0D8h+dwCreationDisposition], 3; dwCreationDisposition
0x180004cbd  mov     rcx, rax; lpFileName
0x180004cc0  call    cs:__imp_CreateFileW
0x180004cc6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004cca  jnz     short loc_180004CD1
0x180004ccc  lea     ebp, [rax+2]
0x180004ccf  jmp     short loc_180004C5D
0x180004cd1  mov     rcx, rax; hObject
0x180004cd4  call    cs:__imp_CloseHandle
0x180004cda  mov     rcx, rbx; void *
0x180004cdd  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x180004ce2  xor     ebx, ebx
0x180004ce4  inc     esi
0x180004ce6  jmp     loc_180004C5D
0x180004ceb  mov     r8d, 4E8h; unsigned int
0x180004cf1  xor     r9d, r9d; unsigned int
0x180004cf4  mov     [rsp+0D8h+dwCreationDisposition], 0; int
0x180004cfc  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180004d01  xor     ebx, ebx
0x180004d03  mov     rax, rbx
0x180004d06  mov     rcx, [rsp+0D8h+var_28]
0x180004d0e  xor     rcx, rsp; StackCookie
0x180004d11  call    __security_check_cookie
0x180004d16  mov     rbx, [rsp+0D8h+arg_18]
0x180004d1e  add     rsp, 0C0h
0x180004d25  pop     r14
0x180004d27  pop     rsi
0x180004d28  pop     rbp
0x180004d29  retn
```
