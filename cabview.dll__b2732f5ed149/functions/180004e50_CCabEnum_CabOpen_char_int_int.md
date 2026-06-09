# CCabEnum::CabOpen(char *,int,int)

- ea: `0x180004e50`
- end: `0x180005043`
- name: `?CabOpen@CCabEnum@@KA_JPEADHH@Z`
- size: `499`
- prototype: `INT_PTR __cdecl(LPSTR pszFile, int oflag, int pmode)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x180002620`
- `0x180002f40`
- `0x180003adc`
- `0x1800043d4`
- `0x180004e50`
- `0x180005130`
- `0x1800051e0`
- `0x180008544`
- `0x18000990c`
- `0x180011e00`
- `0x18001226c`

## import_xrefs

- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180004fb1`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180004fb1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004ffe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004ffe`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180004ed2`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180004ed2`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180004eb5`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180004eb5`

## pseudocode

```c
INT_PTR __fastcall CCabEnum::CabOpen(const CHAR *pszFile, DWORD oflag, int pmode)
{
  CMemFile *v5; // rax
  CMemFile *v6; // rax
  unsigned int v7; // edx
  CMemFile *v9; // rax
  CMemFile *v10; // rbx
  unsigned int v11; // edx
  WCHAR Buffer[264]; // [rsp+40h] [rbp-648h] BYREF
  WCHAR TempFileName[264]; // [rsp+250h] [rbp-438h] BYREF
  WCHAR pwszDst[264]; // [rsp+460h] [rbp-228h] BYREF

  if ( !pszFile )
    return -1;
  if ( *pszFile == 42 )
  {
    memset_0(Buffer, 0, 0x208u);
    if ( !CCabEnum::s_hSpill )
    {
      GetTempPathW(0x104u, Buffer);
      GetTempFileNameW(Buffer, L"fdi", 0, TempFileName);
      v5 = (CMemFile *)operator new(0x18u);
      if ( !v5 )
      {
LABEL_9:
        CCabEnum::s_hSpill = 0;
        return -1;
      }
      v6 = CMemFile::CMemFile(v5, 0, 0);
      CCabEnum::s_hSpill = v6;
      if ( v6 )
      {
        if ( CMemFile::Create(v6, TempFileName) )
        {
          if ( (unsigned int)CMemFile::Seek(CCabEnum::s_hSpill, *((_DWORD *)pszFile + 1) - 1, 0) != -1 )
          {
            CMemFile::Write(CCabEnum::s_hSpill, TempFileName, 1u);
            return (INT_PTR)CCabEnum::s_hSpill;
          }
          CMemFile::Close(CCabEnum::s_hSpill);
        }
        else if ( CCabEnum::s_hSpill )
        {
          CMemFile::`scalar deleting destructor'(CCabEnum::s_hSpill, v7);
        }
        goto LABEL_9;
      }
    }
  }
  else
  {
    v9 = (CMemFile *)operator new(0x18u);
    if ( v9 )
    {
      v10 = CMemFile::CMemFile(v9, 0, 0);
      if ( v10 )
      {
        SHAnsiToUnicode(pszFile, pwszDst, 260);
        if ( !*((_QWORD *)v10 + 1) && *(_QWORD *)v10 == -1 )
        {
          if ( !(unsigned int)PathIsInvalidW(pwszDst) )
            *(_QWORD *)v10 = CreateFileW(pwszDst, 0x80000000, 1u, 0, 3u, oflag, 0);
          if ( *(_QWORD *)v10 != -1 )
            return (INT_PTR)v10;
        }
        CMemFile::`scalar deleting destructor'(v10, v11);
      }
    }
  }
  return -1;
}

```

## disassembly

```asm
0x180004e50  mov     [rsp+arg_10], rbx
0x180004e55  mov     [rsp+arg_18], rsi
0x180004e5a  push    rdi
0x180004e5b  sub     rsp, 680h
0x180004e62  mov     rax, cs:__security_cookie
0x180004e69  xor     rax, rsp
0x180004e6c  mov     [rsp+688h+var_18], rax
0x180004e74  mov     esi, edx
0x180004e76  mov     rdi, rcx
0x180004e79  test    rcx, rcx
0x180004e7c  jz      loc_18000501A
0x180004e82  cmp     byte ptr [rcx], 2Ah ; '*'
0x180004e85  jnz     loc_180004F78
0x180004e8b  xor     edx, edx; Val
0x180004e8d  lea     rcx, [rsp+688h+Buffer]; void *
0x180004e92  mov     r8d, 208h; Size
0x180004e98  call    memset_0
0x180004e9d  cmp     cs:?s_hSpill@CCabEnum@@0PEAVCMemFile@@EA, 0; CMemFile * CCabEnum::s_hSpill
0x180004ea5  jnz     loc_18000501A
0x180004eab  lea     rdx, [rsp+688h+Buffer]; lpBuffer
0x180004eb0  mov     ecx, 104h; nBufferLength
0x180004eb5  call    cs:__imp_GetTempPathW
0x180004ebb  lea     r9, [rsp+688h+TempFileName]; lpTempFileName
0x180004ec3  xor     r8d, r8d; uUnique
0x180004ec6  lea     rdx, PrefixString; "fdi"
0x180004ecd  lea     rcx, [rsp+688h+Buffer]; lpPathName
0x180004ed2  call    cs:__imp_GetTempFileNameW
0x180004ed8  mov     ecx, 18h; unsigned __int64
0x180004edd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004ee2  test    rax, rax
0x180004ee5  jz      short loc_180004F29
0x180004ee7  xor     r8d, r8d; unsigned int
0x180004eea  xor     edx, edx; void **
0x180004eec  mov     rcx, rax; this
0x180004eef  call    ??0CMemFile@@QEAA@PEAPEAXK@Z; CMemFile::CMemFile(void * *,ulong)
0x180004ef4  mov     cs:?s_hSpill@CCabEnum@@0PEAVCMemFile@@EA, rax; CMemFile * CCabEnum::s_hSpill
0x180004efb  test    rax, rax
0x180004efe  jz      loc_18000501A
0x180004f04  lea     rdx, [rsp+688h+TempFileName]; unsigned __int16 *
0x180004f0c  mov     rcx, rax; this
0x180004f0f  call    ?Create@CMemFile@@QEAAHPEBG@Z; CMemFile::Create(ushort const *)
0x180004f14  mov     rcx, cs:?s_hSpill@CCabEnum@@0PEAVCMemFile@@EA; this
0x180004f1b  test    eax, eax
0x180004f1d  jnz     short loc_180004F39
0x180004f1f  test    rcx, rcx
0x180004f22  jz      short loc_180004F29
0x180004f24  call    ??_GCMemFile@@QEAAPEAXI@Z; CMemFile::`scalar deleting destructor'(uint)
0x180004f29  mov     cs:?s_hSpill@CCabEnum@@0PEAVCMemFile@@EA, 0; CMemFile * CCabEnum::s_hSpill
0x180004f34  jmp     loc_18000501A
0x180004f39  mov     edx, [rdi+4]
0x180004f3c  xor     r8d, r8d; int
0x180004f3f  dec     edx; int
0x180004f41  call    ?Seek@CMemFile@@QEAAJJH@Z; CMemFile::Seek(long,int)
0x180004f46  mov     rcx, cs:?s_hSpill@CCabEnum@@0PEAVCMemFile@@EA; this
0x180004f4d  cmp     eax, 0FFFFFFFFh
0x180004f50  jnz     short loc_180004F59
0x180004f52  call    ?Close@CMemFile@@QEAAPEAXXZ; CMemFile::Close(void)
0x180004f57  jmp     short loc_180004F29
0x180004f59  mov     r8d, 1; unsigned int
0x180004f5f  lea     rdx, [rsp+688h+TempFileName]; void *
0x180004f67  call    ?Write@CMemFile@@QEAAIPEBXI@Z; CMemFile::Write(void const *,uint)
0x180004f6c  mov     rax, cs:?s_hSpill@CCabEnum@@0PEAVCMemFile@@EA; CMemFile * CCabEnum::s_hSpill
0x180004f73  jmp     loc_18000501E
0x180004f78  mov     ecx, 18h; unsigned __int64
0x180004f7d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004f82  test    rax, rax
0x180004f85  jz      loc_18000501A
0x180004f8b  xor     r8d, r8d; unsigned int
0x180004f8e  xor     edx, edx; void **
0x180004f90  mov     rcx, rax; this
0x180004f93  call    ??0CMemFile@@QEAA@PEAPEAXK@Z; CMemFile::CMemFile(void * *,ulong)
0x180004f98  mov     rbx, rax
0x180004f9b  test    rax, rax
0x180004f9e  jz      short loc_18000501A
0x180004fa0  mov     r8d, 104h; cwchBuf
0x180004fa6  lea     rdx, [rsp+688h+pwszDst]; pwszDst
0x180004fae  mov     rcx, rdi; pszSrc
0x180004fb1  call    cs:__imp_SHAnsiToUnicode
0x180004fb7  cmp     qword ptr [rbx+8], 0
0x180004fbc  jnz     short loc_180005012
0x180004fbe  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180004fc2  jnz     short loc_180005012
0x180004fc4  lea     rcx, [rsp+688h+pwszDst]; unsigned __int16 *
0x180004fcc  call    PathIsInvalidW
0x180004fd1  test    eax, eax
0x180004fd3  jnz     short loc_180005007
0x180004fd5  mov     [rsp+688h+hTemplateFile], 0; hTemplateFile
0x180004fde  lea     r8d, [rax+1]; dwShareMode
0x180004fe2  mov     [rsp+688h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180004fe6  lea     rcx, [rsp+688h+pwszDst]; lpFileName
0x180004fee  xor     r9d, r9d; lpSecurityAttributes
0x180004ff1  mov     [rsp+688h+dwCreationDisposition], 3; dwCreationDisposition
0x180004ff9  mov     edx, 80000000h; dwDesiredAccess
0x180004ffe  call    cs:__imp_CreateFileW
0x180005004  mov     [rbx], rax
0x180005007  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18000500b  jz      short loc_180005012
0x18000500d  mov     rax, rbx
0x180005010  jmp     short loc_18000501E
0x180005012  mov     rcx, rbx; this
0x180005015  call    ??_GCMemFile@@QEAAPEAXI@Z; CMemFile::`scalar deleting destructor'(uint)
0x18000501a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000501e  mov     rcx, [rsp+688h+var_18]
0x180005026  xor     rcx, rsp; StackCookie
0x180005029  call    __security_check_cookie
0x18000502e  lea     r11, [rsp+688h+var_8]
0x180005036  mov     rbx, [r11+20h]
0x18000503a  mov     rsi, [r11+28h]
0x18000503e  mov     rsp, r11
0x180005041  pop     rdi
0x180005042  retn
```
