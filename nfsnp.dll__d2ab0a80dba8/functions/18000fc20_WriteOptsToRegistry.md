# WriteOptsToRegistry

- ea: `0x18000fc20`
- end: `0x18000fdad`
- name: `WriteOptsToRegistry`
- size: `397`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x18000be24`

## callees

- `0x1800016c8`
- `0x18000cf74`
- `0x18000f470`
- `0x18000f64c`
- `0x18000f7b0`
- `0x18000f9f0`
- `0x18000fc20`
- `0x18000fdb4`
- `0x180010310`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000fd1b`
- `msvcrt!wcscat_s` at `0x18000fd1b`
- `msvcrt!wcscpy_s` at `0x18000fc92`
- `msvcrt!wcscpy_s` at `0x18000fc92`

## pseudocode

```c
LSTATUS __fastcall WriteOptsToRegistry(HKEY hKey, __int64 a2)
{
  __int64 v2; // r8
  const wchar_t *v5; // r8
  unsigned __int64 v6; // rcx
  wchar_t *v7; // rdx
  __int64 v8; // rax
  wchar_t Destination[264]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Source[264]; // [rsp+240h] [rbp+140h] BYREF

  v2 = *(_QWORD *)(a2 + 64);
  Source[259] = 0;
  Destination[259] = 0;
  DaBuildRegistryPath(0, L"Persistent\\", v2, Source);
  v5 = *(const wchar_t **)(*(_QWORD *)(a2 + 16) + 8LL);
  if ( v5 )
  {
    wcscpy_s(Destination, 0x104u, v5);
    v6 = -1;
    v7 = Destination;
    v8 = -1;
    do
      ++v8;
    while ( Destination[v8] );
    if ( v8 )
    {
      if ( Destination[v8 - 1] == 92 || Destination[v8 - 1] == 58 )
      {
        v7 = (wchar_t *)(2 * v8 - 2);
        if ( (unsigned __int64)v7 >= 0x208 )
          goto LABEL_15;
        *(wchar_t *)((char *)Destination + (_QWORD)v7) = 0;
      }
      do
        ++v6;
      while ( Destination[v6] );
      if ( Destination[v6 - 1] != 58 )
        goto LABEL_13;
      v6 = 2 * v6 - 2;
      if ( v6 < 0x208 )
      {
        *(wchar_t *)((char *)Destination + v6) = 0;
LABEL_13:
        wcscat_s(Source, 0x104u, Destination);
        goto LABEL_14;
      }
LABEL_15:
      _report_rangecheckfailure(v6, v7, 520);
    }
  }
LABEL_14:
  WriteLoginOpts(hKey, Source, *(_QWORD *)(a2 + 8));
  WriteMountOpts(hKey, Source, *(_QWORD *)a2);
  WriteFileAccessAndCaseOpts(hKey, Source, *(_QWORD *)a2);
  WriteCacheOpts(hKey, Source, (const BYTE *)a2);
  WriteBrowseOpts(*(BYTE **)(a2 + 24));
  return WriteSymLinksOpts(hKey, Source, *(_QWORD *)a2);
}

```

## disassembly

```asm
0x18000fc20  mov     [rsp-8+arg_10], rbx
0x18000fc25  push    rbp
0x18000fc26  push    rsi
0x18000fc27  push    rdi
0x18000fc28  lea     rbp, [rsp-360h]
0x18000fc30  sub     rsp, 460h
0x18000fc37  mov     rax, cs:__security_cookie
0x18000fc3e  xor     rax, rsp
0x18000fc41  mov     [rbp+370h+var_20], rax
0x18000fc48  mov     r8, [rdx+40h]
0x18000fc4c  lea     r9, [rbp+370h+Source]
0x18000fc53  mov     rbx, rdx
0x18000fc56  mov     rdi, rcx
0x18000fc59  xor     esi, esi
0x18000fc5b  lea     rdx, aPersistent_0; "Persistent\\"
0x18000fc62  xor     ecx, ecx
0x18000fc64  mov     [rbp+370h+var_2A], si
0x18000fc6b  mov     [rbp+370h+var_23A], si
0x18000fc72  call    DaBuildRegistryPath
0x18000fc77  mov     rax, [rbx+10h]
0x18000fc7b  mov     r8, [rax+8]; Source
0x18000fc7f  test    r8, r8
0x18000fc82  jz      loc_18000FD21
0x18000fc88  mov     edx, 104h; SizeInWords
0x18000fc8d  lea     rcx, [rsp+470h+Destination]; Destination
0x18000fc92  call    cs:__imp_wcscpy_s
0x18000fc98  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000fc9c  lea     rdx, [rsp+470h+Destination]
0x18000fca1  mov     rax, rcx
0x18000fca4  inc     rax
0x18000fca7  cmp     [rdx+rax*2], si
0x18000fcab  jnz     short loc_18000FCA4
0x18000fcad  test    rax, rax
0x18000fcb0  jz      short loc_18000FD21
0x18000fcb2  cmp     [rsp+rax*2+470h+var_442], 5Ch ; '\'
0x18000fcb8  mov     r8d, 208h
0x18000fcbe  jz      short loc_18000FCC8
0x18000fcc0  cmp     [rsp+rax*2+470h+var_442], 3Ah ; ':'
0x18000fcc6  jnz     short loc_18000FCDE
0x18000fcc8  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18000fcd0  cmp     rdx, r8
0x18000fcd3  jnb     loc_18000FDA7
0x18000fcd9  mov     [rsp+rdx+470h+Destination], si
0x18000fcde  lea     rax, [rsp+470h+Destination]
0x18000fce3  inc     rcx
0x18000fce6  cmp     [rax+rcx*2], si
0x18000fcea  jnz     short loc_18000FCE3
0x18000fcec  cmp     [rsp+rcx*2+470h+var_442], 3Ah ; ':'
0x18000fcf2  jnz     short loc_18000FD0A
0x18000fcf4  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rcx*2]
0x18000fcfc  cmp     rcx, r8
0x18000fcff  jnb     loc_18000FDA7
0x18000fd05  mov     [rsp+rcx+470h+Destination], si
0x18000fd0a  lea     r8, [rsp+470h+Destination]; Source
0x18000fd0f  mov     edx, 104h; SizeInWords
0x18000fd14  lea     rcx, [rbp+370h+Source]; Destination
0x18000fd1b  call    cs:__imp_wcscat_s
0x18000fd21  mov     r8, [rbx+8]
0x18000fd25  lea     rdx, [rbp+370h+Source]; Source
0x18000fd2c  mov     rcx, rdi; hKey
0x18000fd2f  call    WriteLoginOpts
0x18000fd34  mov     r8, [rbx]
0x18000fd37  lea     rdx, [rbp+370h+Source]; Source
0x18000fd3e  mov     rcx, rdi; hKey
0x18000fd41  call    WriteMountOpts
0x18000fd46  mov     r8, [rbx]
0x18000fd49  lea     rdx, [rbp+370h+Source]; Source
0x18000fd50  mov     rcx, rdi; hKey
0x18000fd53  call    WriteFileAccessAndCaseOpts
0x18000fd58  mov     r8, rbx
0x18000fd5b  lea     rdx, [rbp+370h+Source]; Source
0x18000fd62  mov     rcx, rdi; hKey
0x18000fd65  call    WriteCacheOpts
0x18000fd6a  mov     rcx, [rbx+18h]; lpData
0x18000fd6e  call    WriteBrowseOpts
0x18000fd73  mov     r8, [rbx]
0x18000fd76  lea     rdx, [rbp+370h+Source]
0x18000fd7d  mov     rcx, rdi
0x18000fd80  call    WriteSymLinksOpts
0x18000fd85  mov     rcx, [rbp+370h+var_20]
0x18000fd8c  xor     rcx, rsp; StackCookie
0x18000fd8f  call    __security_check_cookie
0x18000fd94  mov     rbx, [rsp+470h+arg_10]
0x18000fd9c  add     rsp, 460h
0x18000fda3  pop     rdi
0x18000fda4  pop     rsi
0x18000fda5  pop     rbp
0x18000fda6  retn
0x18000fda7  call    __report_rangecheckfailure
```
