# DeleteExtractedFiles

- ea: `0x180015900`
- end: `0x1800159a2`
- name: `DeleteExtractedFiles`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180014904`
- `0x180014dc0`
- `0x180015900`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x18001594d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x18001594d`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18001595c`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18001595c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015965`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015972`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015965`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015972`

## pseudocode

```c
void __fastcall DeleteExtractedFiles(__int64 a1)
{
  __int64 v1; // rbx
  void *v3; // rcx
  CHAR FileName[272]; // [rsp+20h] [rbp-128h] BYREF

  v1 = *(_QWORD *)(a1 + 16);
  while ( v1 )
  {
    if ( !*(_DWORD *)(v1 + 16) && (unsigned int)catDirAndFile(FileName) && SetFileAttributesA(FileName, 0x80u) )
      DeleteFileA(FileName);
    CoTaskMemFree(*(LPVOID *)v1);
    v3 = (void *)v1;
    v1 = *(_QWORD *)(v1 + 8);
    CoTaskMemFree(v3);
  }
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180015900  mov     [rsp+arg_8], rbx
0x180015905  push    rdi
0x180015906  sub     rsp, 140h
0x18001590d  mov     rax, cs:__security_cookie
0x180015914  xor     rax, rsp
0x180015917  mov     [rsp+148h+var_18], rax
0x18001591f  mov     rbx, [rcx+10h]
0x180015923  mov     rdi, rcx
0x180015926  jmp     short loc_180015978
0x180015928  cmp     dword ptr [rbx+10h], 0
0x18001592c  jnz     short loc_180015962
0x18001592e  mov     r9, [rbx]
0x180015931  lea     r8, [rdi+20h]
0x180015935  lea     rcx, [rsp+148h+FileName]; pszDest
0x18001593a  call    catDirAndFile
0x18001593f  test    eax, eax
0x180015941  jz      short loc_180015962
0x180015943  mov     edx, 80h; dwFileAttributes
0x180015948  lea     rcx, [rsp+148h+FileName]; lpFileName
0x18001594d  call    cs:__imp_SetFileAttributesA
0x180015953  test    eax, eax
0x180015955  jz      short loc_180015962
0x180015957  lea     rcx, [rsp+148h+FileName]; lpFileName
0x18001595c  call    cs:__imp_DeleteFileA
0x180015962  mov     rcx, [rbx]; pv
0x180015965  call    cs:__imp_CoTaskMemFree
0x18001596b  mov     rcx, rbx; pv
0x18001596e  mov     rbx, [rbx+8]
0x180015972  call    cs:__imp_CoTaskMemFree
0x180015978  test    rbx, rbx
0x18001597b  jnz     short loc_180015928
0x18001597d  mov     [rdi+10h], rbx
0x180015981  mov     rcx, [rsp+148h+var_18]
0x180015989  xor     rcx, rsp; StackCookie
0x18001598c  call    __security_check_cookie
0x180015991  mov     rbx, [rsp+148h+arg_8]
0x180015999  add     rsp, 140h
0x1800159a0  pop     rdi
0x1800159a1  retn
```
