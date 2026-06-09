# DSUtils::GetFinalPathFromHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x18001a330`
- end: `0x18001a492`
- name: `?GetFinalPathFromHandle@DSUtils@@YAJPEAXPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800125c4`
- `0x180019bf0`
- `0x180019e70`
- `0x18001ab08`

## callees

- `0x180003478`
- `0x180006e2c`
- `0x180006e54`
- `0x18000be3c`
- `0x18001a330`
- `0x18001b30a`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a434`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18001a386`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18001a42a`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18001a386`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18001a42a`

## pseudocode

```c
__int64 __fastcall DSUtils::GetFinalPathFromHandle(HANDLE hFile, __int64 a2)
{
  signed int v4; // edi
  DWORD FinalPathNameByHandleW; // eax
  unsigned __int64 v6; // rsi
  signed int LastError; // eax
  __int64 v8; // rcx
  unsigned __int64 v9; // rax
  WCHAR *v10; // rax
  WCHAR *v11; // rbx
  signed int v12; // eax
  WCHAR szFilePath[264]; // [rsp+30h] [rbp-248h] BYREF

  v4 = 0;
  memset_0(szFilePath, 0, 0x208u);
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, szFilePath, 0x104u, 0);
  v6 = FinalPathNameByHandleW;
  if ( FinalPathNameByHandleW )
    goto LABEL_5;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_5:
    if ( (unsigned int)v6 > 0x104 )
    {
      v9 = 2 * v6;
      if ( !is_mul_ok(v6, 2u) )
        v9 = -1;
      v10 = (WCHAR *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
      v11 = v10;
      if ( v10 )
      {
        if ( GetFinalPathNameByHandleW(hFile, v10, v6, 0) )
          goto LABEL_24;
        v12 = GetLastError();
        v4 = v12;
        if ( v12 > 0 )
          v4 = (unsigned __int16)v12 | 0x80070000;
        if ( v4 >= 0 )
        {
LABEL_24:
          if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                   a2,
                                   v11) )
            v4 = -2147024882;
        }
        Common::GlobalHeap::Free(v11);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      v8 = -1;
      do
        ++v8;
      while ( szFilePath[v8] );
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               a2,
                               szFilePath,
                               v8) )
        return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001a330  mov     [rsp+arg_10], rbx
0x18001a335  push    rbp
0x18001a336  push    rsi
0x18001a337  push    rdi
0x18001a338  push    r14
0x18001a33a  push    r15
0x18001a33c  sub     rsp, 250h
0x18001a343  mov     rax, cs:__security_cookie
0x18001a34a  xor     rax, rsp
0x18001a34d  mov     [rsp+278h+var_38], rax
0x18001a355  mov     rbp, rdx
0x18001a358  mov     r14, rcx
0x18001a35b  xor     r15d, r15d
0x18001a35e  mov     edi, r15d
0x18001a361  xor     edx, edx; Val
0x18001a363  mov     r8d, 208h; Size
0x18001a369  lea     rcx, [rsp+278h+szFilePath]; void *
0x18001a36e  call    memset_0
0x18001a373  xor     r9d, r9d; dwFlags
0x18001a376  mov     ebx, 104h
0x18001a37b  mov     r8d, ebx; cchFilePath
0x18001a37e  lea     rdx, [rsp+278h+szFilePath]; lpszFilePath
0x18001a383  mov     rcx, r14; hFile
0x18001a386  call    cs:__imp_GetFinalPathNameByHandleW
0x18001a38c  mov     esi, eax
0x18001a38e  test    eax, eax
0x18001a390  jnz     short loc_18001A3AF
0x18001a392  call    cs:__imp_GetLastError
0x18001a398  mov     edi, eax
0x18001a39a  test    eax, eax
0x18001a39c  jle     short loc_18001A3A7
0x18001a39e  movzx   edi, ax
0x18001a3a1  or      edi, 80070000h
0x18001a3a7  test    edi, edi
0x18001a3a9  js      loc_18001A469
0x18001a3af  cmp     esi, ebx
0x18001a3b1  ja      short loc_18001A3E8
0x18001a3b3  lea     rax, [rsp+278h+szFilePath]
0x18001a3b8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001a3bc  inc     rcx
0x18001a3bf  cmp     [rax+rcx*2], r15w
0x18001a3c4  jnz     short loc_18001A3BC
0x18001a3c6  mov     r8, rcx
0x18001a3c9  lea     rdx, [rsp+278h+szFilePath]
0x18001a3ce  mov     rcx, rbp
0x18001a3d1  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18001a3d6  test    al, al
0x18001a3d8  jnz     loc_18001A469
0x18001a3de  mov     edi, 8007000Eh
0x18001a3e3  jmp     loc_18001A469
0x18001a3e8  mov     eax, 2
0x18001a3ed  mul     rsi
0x18001a3f0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001a3f7  cmovb   rax, rcx
0x18001a3fb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a402  mov     rcx, rax; unsigned __int64
0x18001a405  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001a40a  mov     rbx, rax
0x18001a40d  mov     [rsp+278h+var_258], rax
0x18001a412  test    rax, rax
0x18001a415  jnz     short loc_18001A41E
0x18001a417  mov     edi, 8007000Eh
0x18001a41c  jmp     short loc_18001A469
0x18001a41e  xor     r9d, r9d; dwFlags
0x18001a421  mov     r8d, esi; cchFilePath
0x18001a424  mov     rdx, rbx; lpszFilePath
0x18001a427  mov     rcx, r14; hFile
0x18001a42a  call    cs:__imp_GetFinalPathNameByHandleW
0x18001a430  test    eax, eax
0x18001a432  jnz     short loc_18001A44D
0x18001a434  call    cs:__imp_GetLastError
0x18001a43a  mov     edi, eax
0x18001a43c  test    eax, eax
0x18001a43e  jle     short loc_18001A449
0x18001a440  movzx   edi, ax
0x18001a443  or      edi, 80070000h
0x18001a449  test    edi, edi
0x18001a44b  js      short loc_18001A461
0x18001a44d  mov     rdx, rbx
0x18001a450  mov     rcx, rbp
0x18001a453  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18001a458  test    al, al
0x18001a45a  jnz     short loc_18001A461
0x18001a45c  mov     edi, 8007000Eh
0x18001a461  mov     rcx, rbx; P
0x18001a464  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18001a469  mov     eax, edi
0x18001a46b  mov     rcx, [rsp+278h+var_38]
0x18001a473  xor     rcx, rsp; StackCookie
0x18001a476  call    __security_check_cookie
0x18001a47b  mov     rbx, [rsp+278h+arg_10]
0x18001a483  add     rsp, 250h
0x18001a48a  pop     r15
0x18001a48c  pop     r14
0x18001a48e  pop     rdi
0x18001a48f  pop     rsi
0x18001a490  pop     rbp
0x18001a491  retn
```
