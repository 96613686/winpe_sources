# Config::XmlDocument::LoadFileEx(ushort const *)

- ea: `0x14005eac0`
- end: `0x14005ee28`
- name: `?LoadFileEx@XmlDocument@Config@@QEAAPEAVFrsStatus@@PEBG@Z`
- size: `872`
- prototype: `struct FrsStatus *__fastcall(Config::XmlDocument *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x14005e9f8`

## callees

- `0x14002c548`
- `0x14004b510`
- `0x14005c620`
- `0x14005e914`
- `0x14005eac0`
- `0x1400be540`
- `0x1401af7b0`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x14005ecc8`
- `KERNEL32!MultiByteToWideChar` at `0x14005ed19`
- `KERNEL32!MultiByteToWideChar` at `0x14005ecc8`
- `KERNEL32!MultiByteToWideChar` at `0x14005ed19`
- `KERNEL32!ReadFile` at `0x14005ec35`
- `KERNEL32!ReadFile` at `0x14005ec35`
- `KERNEL32!GetFileSizeEx` at `0x14005eb33`
- `KERNEL32!GetFileSizeEx` at `0x14005eb33`
- `KERNEL32!GetLastError` at `0x14005eb51`
- `KERNEL32!GetLastError` at `0x14005ec61`
- `KERNEL32!GetLastError` at `0x14005ed65`
- `KERNEL32!GetLastError` at `0x14005eb51`
- `KERNEL32!GetLastError` at `0x14005ec61`
- `KERNEL32!GetLastError` at `0x14005ed65`
- `KERNEL32!GetCurrentThreadId` at `0x14005eb43`
- `KERNEL32!GetCurrentThreadId` at `0x14005ebb8`
- `KERNEL32!GetCurrentThreadId` at `0x14005ec53`
- `KERNEL32!GetCurrentThreadId` at `0x14005ed57`
- `KERNEL32!GetCurrentThreadId` at `0x14005edb2`
- `KERNEL32!GetCurrentThreadId` at `0x14005eb43`
- `KERNEL32!GetCurrentThreadId` at `0x14005ebb8`
- `KERNEL32!GetCurrentThreadId` at `0x14005ec53`
- `KERNEL32!GetCurrentThreadId` at `0x14005ed57`
- `KERNEL32!GetCurrentThreadId` at `0x14005edb2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14005ecdf`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14005ecdf`
- `OLEAUT32!__imp_SysFreeString` at `0x14005ed3d`
- `OLEAUT32!__imp_SysFreeString` at `0x14005ed3d`

## string_xrefs

- `0x14005eb7a`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x14005eba8`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x14005ec8a`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x14005ed8e`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x14005eddb`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x14005eb6e`: `Config::XmlDocument::LoadFileEx`
- `0x14005eba1`: `Config::XmlDocument::LoadFileEx`
- `0x14005ec7e`: `Config::XmlDocument::LoadFileEx`
- `0x14005ed82`: `Config::XmlDocument::LoadFileEx`
- `0x14005edcf`: `Config::XmlDocument::LoadFileEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct FrsStatus *__fastcall Config::XmlDocument::LoadFileEx(Config::XmlDocument *this, const unsigned __int16 *a2)
{
  __int64 v3; // rdi
  struct FrsStatus *v4; // rsi
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  __int64 v7; // rcx
  DWORD LowPart; // r14d
  DWORD v9; // eax
  __int64 v10; // rcx
  const CHAR *v11; // r12
  CHAR *v12; // r15
  DWORD v13; // ebx
  DWORD v14; // ebx
  DWORD v15; // eax
  UINT v16; // eax
  int cchWideChar; // r15d
  WCHAR *v18; // rax
  unsigned __int16 *v19; // rbx
  int v20; // r14d
  DWORD v21; // ebx
  DWORD v22; // eax
  DWORD v23; // eax
  __int64 v24; // rcx
  _QWORD v26[2]; // [rsp+50h] [rbp-20h] BYREF
  HANDLE hFile; // [rsp+60h] [rbp-10h] BYREF
  int v28; // [rsp+68h] [rbp-8h]
  DWORD NumberOfBytesRead; // [rsp+C0h] [rbp+50h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+C8h] [rbp+58h] BYREF

  hFile = (HANDLE)-1LL;
  v28 = 1;
  v3 = 0;
  FileSize.QuadPart = 0;
  v26[0] = 0;
  v4 = FileUtil::FrsCreateFile(a2, 1u, 0x80u, 7u, 1u, 0x4020u, &hFile);
  if ( v4 )
    goto LABEL_21;
  if ( !GetFileSizeEx(hFile, &FileSize) )
  {
    CurrentThreadId = GetCurrentThreadId();
    LastError = GetLastError();
    v4 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v7,
                               LastError,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                               "Config::XmlDocument::LoadFileEx",
                               587,
                               CurrentThreadId,
                               0);
    if ( v4 )
      goto LABEL_21;
  }
  LowPart = FileSize.LowPart;
  if ( !FileSize.LowPart )
  {
    v9 = GetCurrentThreadId();
    v4 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v10,
                               1392,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                               "Config::XmlDocument::LoadFileEx",
                               592,
                               v9,
                               0);
    if ( v4 )
      goto LABEL_21;
    LowPart = FileSize.LowPart;
  }
  v11 = (const CHAR *)operator_new(LowPart);
  v26[0] = v11;
  v12 = (CHAR *)v11;
  v13 = LowPart;
  NumberOfBytesRead = 0;
  while ( v13 )
  {
    NumberOfBytesRead = 0;
    if ( !ReadFile(hFile, v12, v13, &NumberOfBytesRead, 0) )
    {
      v14 = GetCurrentThreadId();
      v15 = GetLastError();
      v4 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                                 v15,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                                 "Config::XmlDocument::LoadFileEx",
                                 611,
                                 v14,
                                 0);
      if ( v4 )
        goto LABEL_21;
      break;
    }
    v13 -= NumberOfBytesRead;
    v12 += NumberOfBytesRead;
    if ( !NumberOfBytesRead )
      break;
  }
  v16 = MultiByteToWideChar(0xFDE9u, 0, v11, LowPart, 0, 0);
  cchWideChar = v16;
  if ( !v16 )
    goto LABEL_25;
  v18 = SysAllocStringLen(0, v16);
  v19 = v18;
  v26[1] = v18;
  if ( !v18 )
    ATL::AtlThrowImpl(-2147024882);
  v20 = MultiByteToWideChar(0xFDE9u, 0, v11, LowPart, v18, cchWideChar);
  if ( v20 )
    v4 = Config::XmlDocument::Load(this, v19);
  SysFreeString(v19);
  if ( v4 )
    goto LABEL_21;
  if ( !v20 )
  {
LABEL_25:
    v21 = GetCurrentThreadId();
    v22 = GetLastError();
    v4 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                               v22,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                               "Config::XmlDocument::LoadFileEx",
                               657,
                               v21,
                               0);
    if ( v4 )
    {
LABEL_21:
      v23 = GetCurrentThreadId();
      v3 = FrsStatusList::PushNewError(
             v24,
             *((unsigned int *)v4 + 1),
             *((unsigned int *)v4 + 2),
             *(unsigned int *)v4,
             "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
             "Config::XmlDocument::LoadFileEx",
             662,
             v23,
             v4);
    }
  }
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(v26);
  CloseHandleEx(&hFile);
  return (struct FrsStatus *)v3;
}

```

## disassembly

```asm
0x14005eac0  mov     [rsp-38h+arg_0], rbx
0x14005eac5  push    rbp
0x14005eac6  push    rsi
0x14005eac7  push    rdi
0x14005eac8  push    r12
0x14005eaca  push    r13
0x14005eacc  push    r14
0x14005eace  push    r15
0x14005ead0  mov     rbp, rsp
0x14005ead3  sub     rsp, 70h
0x14005ead7  mov     rax, rdx
0x14005eada  mov     r13, rcx
0x14005eadd  or      [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x14005eae2  mov     r15d, 1
0x14005eae8  mov     [rbp+var_8], r15d
0x14005eaec  xor     edi, edi
0x14005eaee  mov     qword ptr [rbp+FileSize], rdi
0x14005eaf2  mov     [rbp+var_20], rdi
0x14005eaf6  lea     rcx, [rbp+hFile]
0x14005eafa  mov     [rsp+70h+var_40], rcx; void **
0x14005eaff  mov     [rsp+70h+cchWideChar], 4020h; unsigned int
0x14005eb07  mov     dword ptr [rsp+70h+lpOverlapped], r15d; unsigned int
0x14005eb0c  lea     r9d, [r15+6]; unsigned int
0x14005eb10  lea     r8d, [r15+7Fh]; unsigned int
0x14005eb14  mov     edx, r15d; unsigned int
0x14005eb17  mov     rcx, rax; unsigned __int16 *
0x14005eb1a  call    ?FrsCreateFile@FileUtil@@SAPEAVFrsStatus@@PEBGKKKKKPEAPEAX@Z; FileUtil::FrsCreateFile(ushort const *,ulong,ulong,ulong,ulong,ulong,void * *)
0x14005eb1f  mov     rsi, rax
0x14005eb22  test    rax, rax
0x14005eb25  jnz     loc_14005EDB2
0x14005eb2b  lea     rdx, [rbp+FileSize]; lpFileSize
0x14005eb2f  mov     rcx, [rbp+hFile]; hFile
0x14005eb33  call    cs:__imp_GetFileSizeEx
0x14005eb3a  nop     dword ptr [rax+rax+00h]
0x14005eb3f  test    eax, eax
0x14005eb41  jnz     short loc_14005EBA1
0x14005eb43  call    cs:__imp_GetCurrentThreadId
0x14005eb4a  nop     dword ptr [rax+rax+00h]
0x14005eb4f  mov     ebx, eax
0x14005eb51  call    cs:__imp_GetLastError
0x14005eb58  nop     dword ptr [rax+rax+00h]
0x14005eb5d  mov     [rsp+70h+var_30], rdi
0x14005eb62  mov     [rsp+70h+var_38], ebx
0x14005eb66  mov     dword ptr [rsp+70h+var_40], 24Bh
0x14005eb6e  lea     rbx, aConfigXmldocum_7; "Config::XmlDocument::LoadFileEx"
0x14005eb75  mov     qword ptr [rsp+70h+cchWideChar], rbx
0x14005eb7a  lea     r12, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x14005eb81  mov     [rsp+70h+lpOverlapped], r12
0x14005eb86  mov     r9d, r15d
0x14005eb89  xor     r8d, r8d
0x14005eb8c  mov     edx, eax
0x14005eb8e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14005eb93  mov     rsi, rax
0x14005eb96  test    rax, rax
0x14005eb99  jnz     loc_14005EDB2
0x14005eb9f  jmp     short loc_14005EBAF
0x14005eba1  lea     rbx, aConfigXmldocum_7; "Config::XmlDocument::LoadFileEx"
0x14005eba8  lea     r12, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x14005ebaf  mov     r14d, dword ptr [rbp+FileSize]
0x14005ebb3  test    r14d, r14d
0x14005ebb6  jnz     short loc_14005EBFF
0x14005ebb8  call    cs:__imp_GetCurrentThreadId
0x14005ebbf  nop     dword ptr [rax+rax+00h]
0x14005ebc4  mov     [rsp+70h+var_30], rdi
0x14005ebc9  mov     [rsp+70h+var_38], eax
0x14005ebcd  mov     dword ptr [rsp+70h+var_40], 250h
0x14005ebd5  mov     qword ptr [rsp+70h+cchWideChar], rbx
0x14005ebda  mov     [rsp+70h+lpOverlapped], r12
0x14005ebdf  mov     r9d, r15d
0x14005ebe2  xor     r8d, r8d
0x14005ebe5  mov     edx, 570h
0x14005ebea  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14005ebef  mov     rsi, rax
0x14005ebf2  test    rax, rax
0x14005ebf5  jnz     loc_14005EDB2
0x14005ebfb  mov     r14d, dword ptr [rbp+FileSize]
0x14005ebff  mov     ecx, r14d; unsigned __int64
0x14005ec02  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x14005ec07  mov     r12, rax
0x14005ec0a  mov     [rbp+var_20], rax
0x14005ec0e  mov     r15, rax
0x14005ec11  mov     ebx, r14d
0x14005ec14  mov     [rbp+NumberOfBytesRead], edi
0x14005ec17  test    ebx, ebx
0x14005ec19  jz      loc_14005ECB2
0x14005ec1f  mov     [rbp+NumberOfBytesRead], edi
0x14005ec22  mov     [rsp+70h+lpOverlapped], rdi; lpOverlapped
0x14005ec27  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x14005ec2b  mov     r8d, ebx; nNumberOfBytesToRead
0x14005ec2e  mov     rdx, r15; lpBuffer
0x14005ec31  mov     rcx, [rbp+hFile]; hFile
0x14005ec35  call    cs:__imp_ReadFile
0x14005ec3c  nop     dword ptr [rax+rax+00h]
0x14005ec41  test    eax, eax
0x14005ec43  jz      short loc_14005EC53
0x14005ec45  mov     ecx, [rbp+NumberOfBytesRead]
0x14005ec48  sub     ebx, ecx
0x14005ec4a  add     r15, rcx
0x14005ec4d  test    ecx, ecx
0x14005ec4f  jnz     short loc_14005EC17
0x14005ec51  jmp     short loc_14005ECB2
0x14005ec53  call    cs:__imp_GetCurrentThreadId
0x14005ec5a  nop     dword ptr [rax+rax+00h]
0x14005ec5f  mov     ebx, eax
0x14005ec61  call    cs:__imp_GetLastError
0x14005ec68  nop     dword ptr [rax+rax+00h]
0x14005ec6d  mov     [rsp+70h+var_30], rdi
0x14005ec72  mov     [rsp+70h+var_38], ebx
0x14005ec76  mov     dword ptr [rsp+70h+var_40], 263h
0x14005ec7e  lea     rcx, aConfigXmldocum_7; "Config::XmlDocument::LoadFileEx"
0x14005ec85  mov     qword ptr [rsp+70h+cchWideChar], rcx
0x14005ec8a  lea     rcx, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x14005ec91  mov     [rsp+70h+lpOverlapped], rcx
0x14005ec96  mov     r9d, 1
0x14005ec9c  xor     r8d, r8d
0x14005ec9f  mov     edx, eax
0x14005eca1  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14005eca6  mov     rsi, rax
0x14005eca9  test    rax, rax
0x14005ecac  jnz     loc_14005EDB2
0x14005ecb2  mov     [rsp+70h+cchWideChar], edi; cchWideChar
0x14005ecb6  mov     [rsp+70h+lpOverlapped], rdi; lpWideCharStr
0x14005ecbb  mov     r9d, r14d; cbMultiByte
0x14005ecbe  mov     r8, r12; lpMultiByteStr
0x14005ecc1  xor     edx, edx; dwFlags
0x14005ecc3  mov     ecx, 0FDE9h; CodePage
0x14005ecc8  call    cs:__imp_MultiByteToWideChar
0x14005eccf  nop     dword ptr [rax+rax+00h]
0x14005ecd4  mov     r15d, eax
0x14005ecd7  test    eax, eax
0x14005ecd9  jz      short loc_14005ED57
0x14005ecdb  mov     edx, eax; ui
0x14005ecdd  xor     ecx, ecx; strIn
0x14005ecdf  call    cs:__imp_SysAllocStringLen
0x14005ece6  nop     dword ptr [rax+rax+00h]
0x14005eceb  mov     rbx, rax
0x14005ecee  mov     [rbp+var_18], rax
0x14005ecf2  test    rax, rax
0x14005ecf5  jnz     short loc_14005ED02
0x14005ecf7  mov     ecx, 8007000Eh; int
0x14005ecfc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14005ed02  mov     [rsp+70h+cchWideChar], r15d; cchWideChar
0x14005ed07  mov     [rsp+70h+lpOverlapped], rbx; lpWideCharStr
0x14005ed0c  mov     r9d, r14d; cbMultiByte
0x14005ed0f  mov     r8, r12; lpMultiByteStr
0x14005ed12  xor     edx, edx; dwFlags
0x14005ed14  mov     ecx, 0FDE9h; CodePage
0x14005ed19  call    cs:__imp_MultiByteToWideChar
0x14005ed20  nop     dword ptr [rax+rax+00h]
0x14005ed25  mov     r14d, eax
0x14005ed28  test    eax, eax
0x14005ed2a  jz      short loc_14005ED3A
0x14005ed2c  mov     rdx, rbx; unsigned __int16 *
0x14005ed2f  mov     rcx, r13; this
0x14005ed32  call    ?Load@XmlDocument@Config@@QEAAPEAVFrsStatus@@QEAG@Z; Config::XmlDocument::Load(ushort * const)
0x14005ed37  mov     rsi, rax
0x14005ed3a  mov     rcx, rbx; bstrString
0x14005ed3d  call    cs:__imp_SysFreeString
0x14005ed44  nop     dword ptr [rax+rax+00h]
0x14005ed49  test    rsi, rsi
0x14005ed4c  jnz     short loc_14005EDB2
0x14005ed4e  test    r14d, r14d
0x14005ed51  jnz     loc_14005EDF9
0x14005ed57  call    cs:__imp_GetCurrentThreadId
0x14005ed5e  nop     dword ptr [rax+rax+00h]
0x14005ed63  mov     ebx, eax
0x14005ed65  call    cs:__imp_GetLastError
0x14005ed6c  nop     dword ptr [rax+rax+00h]
0x14005ed71  mov     [rsp+70h+var_30], rdi
0x14005ed76  mov     [rsp+70h+var_38], ebx
0x14005ed7a  mov     dword ptr [rsp+70h+var_40], 291h
0x14005ed82  lea     rcx, aConfigXmldocum_7; "Config::XmlDocument::LoadFileEx"
0x14005ed89  mov     qword ptr [rsp+70h+cchWideChar], rcx
0x14005ed8e  lea     rcx, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x14005ed95  mov     [rsp+70h+lpOverlapped], rcx
0x14005ed9a  mov     r9d, 1
0x14005eda0  xor     r8d, r8d
0x14005eda3  mov     edx, eax
0x14005eda5  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14005edaa  mov     rsi, rax
0x14005edad  test    rax, rax
0x14005edb0  jz      short loc_14005EDF9
0x14005edb2  call    cs:__imp_GetCurrentThreadId
0x14005edb9  nop     dword ptr [rax+rax+00h]
0x14005edbe  mov     [rsp+70h+var_30], rsi
0x14005edc3  mov     [rsp+70h+var_38], eax
0x14005edc7  mov     dword ptr [rsp+70h+var_40], 296h
0x14005edcf  lea     rax, aConfigXmldocum_7; "Config::XmlDocument::LoadFileEx"
0x14005edd6  mov     qword ptr [rsp+70h+cchWideChar], rax
0x14005eddb  lea     rax, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x14005ede2  mov     [rsp+70h+lpOverlapped], rax
0x14005ede7  mov     r9d, [rsi]
0x14005edea  mov     r8d, [rsi+8]
0x14005edee  mov     edx, [rsi+4]
0x14005edf1  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14005edf6  mov     rdi, rax
0x14005edf9  lea     rcx, [rbp+var_20]
0x14005edfd  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x14005ee02  nop
0x14005ee03  lea     rcx, [rbp+hFile]; void **
0x14005ee07  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x14005ee0c  mov     rax, rdi
0x14005ee0f  mov     rbx, [rsp+70h+arg_0]
0x14005ee17  add     rsp, 70h
0x14005ee1b  pop     r15
0x14005ee1d  pop     r14
0x14005ee1f  pop     r13
0x14005ee21  pop     r12
0x14005ee23  pop     rdi
0x14005ee24  pop     rsi
0x14005ee25  pop     rbp
0x14005ee26  retn
```
