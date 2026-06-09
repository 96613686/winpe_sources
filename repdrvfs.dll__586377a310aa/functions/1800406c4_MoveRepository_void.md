# MoveRepository(void)

- ea: `0x1800406c4`
- end: `0x1800407e0`
- name: `?MoveRepository@@YAJXZ`
- size: `284`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800411c0`

## callees

- `0x1800012b8`
- `0x1800216c8`
- `0x18003a550`
- `0x1800406c4`
- `0x180044420`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180040771`
- `wbemcomn!GetMemLogObject` at `0x180040771`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004077c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004077c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180040726`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180040726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040758`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18004074e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18004074e`

## pseudocode

```c
__int64 MoveRepository(void)
{
  int RepositoryDirectory; // edi
  int i; // ebx
  signed int LastError; // eax
  unsigned int v3; // ebx
  CMemoryLog *MemLogObject; // rax
  __int64 v6; // [rsp+20h] [rbp-448h]
  WCHAR FileName[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+240h] [rbp-228h] BYREF

  RepositoryDirectory = GetRepositoryDirectory(ExistingFileName);
  if ( RepositoryDirectory < 0 )
    return (unsigned int)RepositoryDirectory;
  for ( i = 1; i < 999; ++i )
  {
    LODWORD(v6) = i;
    StringCchPrintfW(FileName, 0x105u, L"%s.%03i", ExistingFileName, v6);
    if ( GetFileAttributesW(FileName) == -1 )
      break;
  }
  if ( MoveFileExW(ExistingFileName, FileName, 2u) )
    return (unsigned int)RepositoryDirectory;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( (v3 & 0x80000000) != 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v3);
  }
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x1800406c4  mov     [rsp+arg_0], rbx
0x1800406c9  push    rdi
0x1800406ca  sub     rsp, 460h
0x1800406d1  mov     rax, cs:__security_cookie
0x1800406d8  xor     rax, rsp
0x1800406db  mov     [rsp+468h+var_18], rax
0x1800406e3  lea     rcx, [rsp+468h+ExistingFileName]; lpDst
0x1800406eb  call    ?GetRepositoryDirectory@@YAJQEAG@Z; GetRepositoryDirectory(ushort * const)
0x1800406f0  mov     edi, eax
0x1800406f2  test    eax, eax
0x1800406f4  js      loc_1800407BD
0x1800406fa  mov     ebx, 1
0x1800406ff  lea     r9, [rsp+468h+ExistingFileName]
0x180040707  mov     [rsp+468h+var_448], ebx
0x18004070b  lea     r8, aS03i; "%s.%03i"
0x180040712  mov     edx, 105h; unsigned __int64
0x180040717  lea     rcx, [rsp+468h+FileName]; unsigned __int16 *
0x18004071c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040721  lea     rcx, [rsp+468h+FileName]; lpFileName
0x180040726  call    cs:__imp_GetFileAttributesW
0x18004072c  cmp     eax, 0FFFFFFFFh
0x18004072f  jz      short loc_18004073B
0x180040731  inc     ebx
0x180040733  cmp     ebx, 3E7h
0x180040739  jl      short loc_1800406FF
0x18004073b  mov     r8d, 2; dwFlags
0x180040741  lea     rdx, [rsp+468h+FileName]; lpNewFileName
0x180040746  lea     rcx, [rsp+468h+ExistingFileName]; lpExistingFileName
0x18004074e  call    cs:__imp_MoveFileExW
0x180040754  test    eax, eax
0x180040756  jnz     short loc_1800407BD
0x180040758  call    cs:__imp_GetLastError
0x18004075e  mov     ebx, eax
0x180040760  test    eax, eax
0x180040762  jle     short loc_18004076D
0x180040764  movzx   ebx, ax
0x180040767  or      ebx, 80070000h
0x18004076d  test    ebx, ebx
0x18004076f  jns     short loc_180040782
0x180040771  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180040777  mov     rcx, rax
0x18004077a  mov     edx, ebx
0x18004077c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180040782  mov     rcx, cs:WPP_GLOBAL_Control
0x180040789  lea     rax, WPP_GLOBAL_Control
0x180040790  cmp     rcx, rax
0x180040793  jz      short loc_1800407B9
0x180040795  test    byte ptr [rcx+1Ch], 1
0x180040799  jz      short loc_1800407B9
0x18004079b  cmp     byte ptr [rcx+19h], 2
0x18004079f  jb      short loc_1800407B9
0x1800407a1  mov     rcx, [rcx+10h]
0x1800407a5  lea     r8, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids
0x1800407ac  mov     edx, 3Eh ; '>'
0x1800407b1  mov     r9d, ebx
0x1800407b4  call    WPP_SF_d
0x1800407b9  mov     eax, ebx
0x1800407bb  jmp     short loc_1800407BF
0x1800407bd  mov     eax, edi
0x1800407bf  mov     rcx, [rsp+468h+var_18]
0x1800407c7  xor     rcx, rsp; StackCookie
0x1800407ca  call    __security_check_cookie
0x1800407cf  mov     rbx, [rsp+468h+arg_0]
0x1800407d7  add     rsp, 460h
0x1800407de  pop     rdi
0x1800407df  retn
```
