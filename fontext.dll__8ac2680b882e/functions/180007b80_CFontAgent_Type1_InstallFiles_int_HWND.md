# CFontAgent_Type1::InstallFiles(int,HWND__ *)

- ea: `0x180007b80`
- end: `0x180007cc0`
- name: `?InstallFiles@CFontAgent_Type1@@UEAAJHPEAUHWND__@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(CFontAgent_Type1 *__hidden this, int, HWND)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update`

## callees

- `0x180006624`
- `0x180007b80`
- `0x180008374`
- `0x1800087d0`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007c4e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007c5c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007c4e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007c5c`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180007c0a`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180007c34`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180007c0a`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180007c34`

## pseudocode

```c
__int64 __fastcall CFontAgent_Type1::InstallFiles(CFontAgent_Type1 *this, int a2, HWND a3)
{
  unsigned int v5; // r9d
  int Error; // ebx
  unsigned int v7; // r11d
  unsigned int v9; // [rsp+28h] [rbp-440h]
  WCHAR NewFileName[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR FileName[264]; // [rsp+240h] [rbp-228h] BYREF

  memset_0(NewFileName, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  Error = CFontAgent_Type1::_PrepareDestinationFilePaths(this, a2, NewFileName, v5, FileName, v9);
  if ( Error >= 0 )
  {
    if ( (CopyFileW((LPCWSTR)this + 420, NewFileName, 1) || (Error = ResultFromLastError(), Error >= 0))
      && (CopyFileW((LPCWSTR)this + 680, FileName, 1) || (Error = ResultFromLastError(), Error >= 0)) )
    {
      Error = StringCchCopyW((unsigned __int16 *)this + 420, 0x104u, NewFileName);
      if ( Error >= 0 )
        return (unsigned int)StringCchCopyW((unsigned __int16 *)this + 680, v7, FileName);
    }
    else
    {
      DeleteFileW(NewFileName);
      DeleteFileW(FileName);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180007b80  mov     [rsp+arg_10], rbx
0x180007b85  mov     [rsp+arg_18], rsi
0x180007b8a  push    rdi
0x180007b8b  sub     rsp, 460h
0x180007b92  mov     rax, cs:__security_cookie
0x180007b99  xor     rax, rsp
0x180007b9c  mov     [rsp+468h+var_18], rax
0x180007ba4  mov     ebx, edx
0x180007ba6  mov     rdi, rcx
0x180007ba9  mov     esi, 208h
0x180007bae  lea     rcx, [rsp+468h+NewFileName]; void *
0x180007bb3  mov     r8d, esi; Size
0x180007bb6  xor     edx, edx; Val
0x180007bb8  call    memset_0
0x180007bbd  mov     r8d, esi; Size
0x180007bc0  lea     rcx, [rsp+468h+FileName]; void *
0x180007bc8  xor     edx, edx; Val
0x180007bca  call    memset_0
0x180007bcf  lea     rax, [rsp+468h+FileName]
0x180007bd7  mov     edx, ebx; int
0x180007bd9  lea     r8, [rsp+468h+NewFileName]; unsigned __int16 *
0x180007bde  mov     [rsp+468h+var_448], rax; unsigned __int16 *
0x180007be3  mov     rcx, rdi; this
0x180007be6  call    ?_PrepareDestinationFilePaths@CFontAgent_Type1@@IEAAJHPEAGI0I@Z; CFontAgent_Type1::_PrepareDestinationFilePaths(int,ushort *,uint,ushort *,uint)
0x180007beb  mov     ebx, eax
0x180007bed  test    eax, eax
0x180007bef  js      loc_180007C99
0x180007bf5  lea     rsi, [rdi+348h]
0x180007bfc  mov     r8d, 1; bFailIfExists
0x180007c02  mov     rcx, rsi; lpExistingFileName
0x180007c05  lea     rdx, [rsp+468h+NewFileName]; lpNewFileName
0x180007c0a  call    cs:__imp_CopyFileW
0x180007c10  test    eax, eax
0x180007c12  jnz     short loc_180007C1F
0x180007c14  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180007c19  mov     ebx, eax
0x180007c1b  test    eax, eax
0x180007c1d  js      short loc_180007C49
0x180007c1f  mov     r8d, 1; bFailIfExists
0x180007c25  lea     rdx, [rsp+468h+FileName]; lpNewFileName
0x180007c2d  lea     rcx, [rdi+550h]; lpExistingFileName
0x180007c34  call    cs:__imp_CopyFileW
0x180007c3a  test    eax, eax
0x180007c3c  jnz     short loc_180007C64
0x180007c3e  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180007c43  mov     ebx, eax
0x180007c45  test    eax, eax
0x180007c47  jns     short loc_180007C64
0x180007c49  lea     rcx, [rsp+468h+NewFileName]; lpFileName
0x180007c4e  call    cs:__imp_DeleteFileW
0x180007c54  lea     rcx, [rsp+468h+FileName]; lpFileName
0x180007c5c  call    cs:__imp_DeleteFileW
0x180007c62  jmp     short loc_180007C99
0x180007c64  mov     r11d, 104h
0x180007c6a  lea     r8, [rsp+468h+NewFileName]; unsigned __int16 *
0x180007c6f  mov     edx, r11d; unsigned __int64
0x180007c72  mov     rcx, rsi; unsigned __int16 *
0x180007c75  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007c7a  mov     ebx, eax
0x180007c7c  test    eax, eax
0x180007c7e  js      short loc_180007C99
0x180007c80  lea     r8, [rsp+468h+FileName]; unsigned __int16 *
0x180007c88  mov     edx, r11d; unsigned __int64
0x180007c8b  lea     rcx, [rdi+550h]; unsigned __int16 *
0x180007c92  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007c97  mov     ebx, eax
0x180007c99  mov     eax, ebx
0x180007c9b  mov     rcx, [rsp+468h+var_18]
0x180007ca3  xor     rcx, rsp; StackCookie
0x180007ca6  call    __security_check_cookie
0x180007cab  lea     r11, [rsp+468h+var_8]
0x180007cb3  mov     rbx, [r11+20h]
0x180007cb7  mov     rsi, [r11+28h]
0x180007cbb  mov     rsp, r11
0x180007cbe  pop     rdi
0x180007cbf  retn
```
