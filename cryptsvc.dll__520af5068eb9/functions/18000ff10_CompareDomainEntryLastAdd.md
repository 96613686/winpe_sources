# _CompareDomainEntryLastAdd

- ea: `0x18000ff10`
- end: `0x18000ffa2`
- name: `_CompareDomainEntryLastAdd`
- size: `146`
- prototype: `LONG __fastcall(__int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ff10`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000ff44`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000ff64`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000ff8f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000ff44`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000ff64`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000ff8f`

## pseudocode

```c
LONG __fastcall CompareDomainEntryLastAdd(__int64 *a1, __int64 *a2)
{
  __int64 v2; // rsi
  __int64 v3; // rdi
  __int64 v4; // rbp
  __int64 v5; // rbx
  FILETIME FileTime2; // [rsp+40h] [rbp+8h] BYREF
  FILETIME FileTime1; // [rsp+48h] [rbp+10h] BYREF

  v2 = *a1;
  v3 = 0;
  v4 = *a2;
  v5 = 0;
  FileTime2 = 0;
  FileTime1 = 0;
  do
  {
    if ( CompareFileTime((const FILETIME *)(v5 + v2 + 24), &FileTime2) > 0 )
      FileTime2 = *(FILETIME *)(v5 + v2 + 24);
    if ( CompareFileTime((const FILETIME *)(v5 + v4 + 24), &FileTime1) > 0 )
      FileTime1 = *(FILETIME *)(v5 + v4 + 24);
    ++v3;
    v5 += 48;
  }
  while ( v3 != 3 );
  return CompareFileTime(&FileTime1, &FileTime2);
}

```

## disassembly

```asm
0x18000ff10  mov     [rsp+arg_10], rbx
0x18000ff15  push    rbp
0x18000ff16  push    rsi
0x18000ff17  push    rdi
0x18000ff18  sub     rsp, 20h
0x18000ff1c  mov     rsi, [rcx]
0x18000ff1f  xor     edi, edi
0x18000ff21  mov     rbp, [rdx]
0x18000ff24  xor     ebx, ebx
0x18000ff26  mov     qword ptr [rsp+38h+FileTime2.dwLowDateTime], 0
0x18000ff2f  mov     qword ptr [rsp+38h+FileTime1.dwLowDateTime], 0
0x18000ff38  lea     rcx, [rsi+18h]
0x18000ff3c  add     rcx, rbx; lpFileTime1
0x18000ff3f  lea     rdx, [rsp+38h+FileTime2]; lpFileTime2
0x18000ff44  call    cs:__imp_CompareFileTime
0x18000ff4a  test    eax, eax
0x18000ff4c  jle     short loc_18000FF58
0x18000ff4e  mov     rax, [rbx+rsi+18h]
0x18000ff53  mov     qword ptr [rsp+38h+FileTime2.dwLowDateTime], rax
0x18000ff58  lea     rcx, [rbp+18h]
0x18000ff5c  add     rcx, rbx; lpFileTime1
0x18000ff5f  lea     rdx, [rsp+38h+FileTime1]; lpFileTime2
0x18000ff64  call    cs:__imp_CompareFileTime
0x18000ff6a  test    eax, eax
0x18000ff6c  jle     short loc_18000FF78
0x18000ff6e  mov     rax, [rbx+rbp+18h]
0x18000ff73  mov     qword ptr [rsp+38h+FileTime1.dwLowDateTime], rax
0x18000ff78  inc     rdi
0x18000ff7b  add     rbx, 30h ; '0'
0x18000ff7f  cmp     rdi, 3
0x18000ff83  jnz     short loc_18000FF38
0x18000ff85  lea     rdx, [rsp+38h+FileTime2]; lpFileTime2
0x18000ff8a  lea     rcx, [rsp+38h+FileTime1]; lpFileTime1
0x18000ff8f  call    cs:__imp_CompareFileTime
0x18000ff95  mov     rbx, [rsp+38h+arg_10]
0x18000ff9a  add     rsp, 20h
0x18000ff9e  pop     rdi
0x18000ff9f  pop     rsi
0x18000ffa0  pop     rbp
0x18000ffa1  retn
```
