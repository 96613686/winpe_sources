# CHiveUploadTaskHandler::_SetHiveAttributes(ushort const *,ushort const *)

- ea: `0x18001a2c4`
- end: `0x18001a3b4`
- name: `?_SetHiveAttributes@CHiveUploadTaskHandler@@AEAAJPEBG0@Z`
- size: `240`
- prototype: `__int64 __fastcall(CHiveUploadTaskHandler *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009770`

## callees

- `0x180005424`
- `0x18000547c`
- `0x180006a9c`
- `0x1800160d4`
- `0x18001a2c4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001a38a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001a38a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001a360`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001a360`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18001a310`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18001a310`

## string_xrefs

- `0x18001a34a`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`
- `0x18001a375`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CHiveUploadTaskHandler::_SetHiveAttributes(
        CHiveUploadTaskHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int BasicProfileFolderPathAlloc; // eax
  unsigned int LastError; // ebx
  __int64 v7; // rdx
  DWORD FileAttributesW; // eax
  const char *v9; // r9
  __int64 v10; // rdx
  LPCWSTR lpFileName; // [rsp+20h] [rbp-28h] BYREF
  __int64 v13; // [rsp+28h] [rbp-20h]
  __int64 v14; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  lpFileName = 0;
  v13 = 0;
  v14 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpFileName);
  v13 = -1;
  v14 = -1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(5, a2, &lpFileName);
  LastError = BasicProfileFolderPathAlloc;
  if ( BasicProfileFolderPathAlloc < 0 )
  {
    v7 = 518;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      (int)lpFileName);
    goto LABEL_12;
  }
  BasicProfileFolderPathAlloc = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Concat(
                                  &lpFileName,
                                  L"\\ntuser.dat",
                                  11);
  LastError = BasicProfileFolderPathAlloc;
  if ( BasicProfileFolderPathAlloc < 0 )
  {
    v7 = 519;
    goto LABEL_5;
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
  {
    v10 = 522;
  }
  else
  {
    if ( SetFileAttributesW(a3, FileAttributesW) )
    {
      LastError = 0;
      goto LABEL_12;
    }
    v10 = 523;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v10,
                (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
                v9);
LABEL_12:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x18001a2c4  mov     rax, rsp
0x18001a2c7  mov     [rax+8], rbx
0x18001a2cb  push    rdi
0x18001a2cc  sub     rsp, 40h
0x18001a2d0  lea     rcx, [rax-28h]
0x18001a2d4  mov     qword ptr [rax-28h], 0
0x18001a2dc  mov     rdi, r8
0x18001a2df  mov     qword ptr [rax-20h], 0
0x18001a2e7  mov     rbx, rdx
0x18001a2ea  mov     qword ptr [rax-18h], 0
0x18001a2f2  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a2f7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a2fb  lea     r8, [rsp+48h+lpFileName]
0x18001a300  mov     rdx, rbx
0x18001a303  mov     [rsp+48h+var_20], rax
0x18001a308  mov     [rsp+48h+var_18], rax
0x18001a30d  lea     ecx, [rax+6]
0x18001a310  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x18001a316  mov     ebx, eax
0x18001a318  test    eax, eax
0x18001a31a  jns     short loc_18001A323
0x18001a31c  mov     edx, 206h
0x18001a321  jmp     short loc_18001A345
0x18001a323  mov     r8d, 0Bh
0x18001a329  lea     rdx, aNtuserDat; "\\ntuser.dat"
0x18001a330  lea     rcx, [rsp+48h+lpFileName]
0x18001a335  call    ?_Concat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18001a33a  mov     ebx, eax
0x18001a33c  test    eax, eax
0x18001a33e  jns     short loc_18001A35B
0x18001a340  mov     edx, 207h; void *
0x18001a345  mov     rcx, [rsp+48h]; this
0x18001a34a  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x18001a351  mov     r9d, eax; char *
0x18001a354  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a359  jmp     short loc_18001A39D
0x18001a35b  mov     rcx, [rsp+48h+lpFileName]; lpFileName
0x18001a360  call    cs:__imp_GetFileAttributesW
0x18001a366  cmp     eax, 0FFFFFFFFh
0x18001a369  jnz     short loc_18001A385
0x18001a36b  mov     edx, 20Ah; void *
0x18001a370  mov     rcx, [rsp+48h]; this
0x18001a375  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x18001a37c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a381  mov     ebx, eax
0x18001a383  jmp     short loc_18001A39D
0x18001a385  mov     edx, eax; dwFileAttributes
0x18001a387  mov     rcx, rdi; lpFileName
0x18001a38a  call    cs:__imp_SetFileAttributesW
0x18001a390  test    eax, eax
0x18001a392  jnz     short loc_18001A39B
0x18001a394  mov     edx, 20Bh
0x18001a399  jmp     short loc_18001A370
0x18001a39b  xor     ebx, ebx
0x18001a39d  lea     rcx, [rsp+48h+lpFileName]
0x18001a3a2  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a3a7  mov     eax, ebx
0x18001a3a9  mov     rbx, [rsp+48h+arg_0]
0x18001a3ae  add     rsp, 40h
0x18001a3b2  pop     rdi
0x18001a3b3  retn
```
