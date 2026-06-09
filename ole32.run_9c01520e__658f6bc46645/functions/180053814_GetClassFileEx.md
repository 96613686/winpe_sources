# GetClassFileEx

- ea: `0x180053814`
- end: `0x180053a3f`
- name: `GetClassFileEx`
- size: `555`
- prototype: `HRESULT __fastcall(const wchar_t *lpszFileName, _GUID *pcid, const _GUID *clsidOle1)`
- caller_count: `8`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800511a0`
- `0x18005255c`
- `0x180052760`
- `0x180053800`
- `0x180074ba8`
- `0x18007c62c`
- `0x18009bf30`
- `0x1800a8158`

## callees

- `0x18001d110`
- `0x180046460`
- `0x180053760`
- `0x180053814`
- `0x1800582d4`
- `0x180058400`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x18005394d`
- `ntdll!NtSetInformationFile` at `0x18005394d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800539fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800539fd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180053874`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180053874`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800538b2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800538ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800538b2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800538ea`
- `coml2!__imp_DfGetClass` at `0x18005395f`
- `coml2!__imp_DfGetClass` at `0x18005395f`

## pseudocode

```c
__int64 __fastcall GetClassFileEx(const wchar_t *lpszFileName, _GUID *pcid, const _GUID *clsidOle1)
{
  int v7; // r14d
  unsigned int Class; // ebx
  DWORD dwFlagsAndAttributes; // ebx
  DWORD FileAttributesW; // eax
  HANDLE FileW; // rsi
  __int64 v12; // rax
  __int64 v13; // rax
  const wchar_t *Ext; // rax
  HRESULT ClassExt; // eax
  int v16; // ecx
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-68h] BYREF
  _FILE_BASIC_INFORMATION basicInformation; // [rsp+50h] [rbp-58h] BYREF

  if ( !IsValidPtrOut(pcid, 0x10u) )
    return 2147942487LL;
  v7 = 1;
  if ( !lpszFileName )
    goto LABEL_4;
  dwFlagsAndAttributes = 0;
  FileAttributesW = GetFileAttributesW(lpszFileName);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x400) != 0 )
    dwFlagsAndAttributes = 0x100000;
  FileW = CreateFileW(lpszFileName, 0x80000100, 3u, 0, 3u, dwFlagsAndAttributes, 0);
  if ( FileW == (HANDLE)-1LL
    && (v7 = 0, FileW = CreateFileW(lpszFileName, 0x80000000, 3u, 0, 3u, dwFlagsAndAttributes, 0), FileW == (HANDLE)-1LL) )
  {
LABEL_4:
    Class = -2147221014;
  }
  else
  {
    if ( v7 )
    {
      *(&basicInformation.FileAttributes + 1) = 0;
      basicInformation.FileAttributes = 0;
      *(__m128i *)&basicInformation.CreationTime.LowPart = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      *(_OWORD *)&basicInformation.LastWriteTime.LowPart = *(_OWORD *)&basicInformation.CreationTime.LowPart;
      IoStatusBlock = 0;
      NtSetInformationFile(FileW, &IoStatusBlock, &basicInformation, 0x28u, FileBasicInformation);
    }
    Class = DfGetClass(FileW, pcid);
    if ( Class )
      goto LABEL_16;
    v12 = *(_QWORD *)&pcid->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&pcid->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v12 = *(_QWORD *)pcid->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( !v12 )
    {
LABEL_16:
      v13 = *(_QWORD *)&clsidOle1->Data1 - *(_QWORD *)&GUID_NULL.Data1;
      if ( *(_QWORD *)&clsidOle1->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
        v13 = *(_QWORD *)clsidOle1->Data4 - *(_QWORD *)GUID_NULL.Data4;
      if ( v13 )
      {
        Class = 0;
        *pcid = *clsidOle1;
      }
      else
      {
        Class = wCoGetClassPattern(FileW, pcid);
        if ( Class == -2147221164 )
        {
          Ext = FindExt(lpszFileName);
          if ( Ext )
          {
            ClassExt = wCoGetClassExt(Ext, pcid);
            v16 = 0;
            if ( ClassExt )
              v16 = -2147221018;
            Class = v16;
          }
          else
          {
            Class = -2147221018;
          }
        }
      }
    }
    CloseHandle(FileW);
    if ( !Class )
      return Class;
  }
  *pcid = GUID_NULL;
  return Class;
}

```

## disassembly

```asm
0x180053814  mov     [rsp+arg_10], rbx
0x180053819  push    rbp
0x18005381a  push    rsi
0x18005381b  push    rdi
0x18005381c  push    r14
0x18005381e  push    r15
0x180053820  sub     rsp, 80h
0x180053827  mov     rax, cs:__security_cookie
0x18005382e  xor     rax, rsp
0x180053831  mov     [rsp+0A8h+var_30], rax
0x180053836  mov     rdi, pcid
0x180053839  mov     rbp, lpszFileName
0x18005383c  mov     lpszFileName, rdi; pv
0x18005383f  mov     edx, 10h; cb
0x180053844  mov     r15, clsidOle1
0x180053847  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x18005384c  test    eax, eax
0x18005384e  jnz     short loc_18005385A
0x180053850  mov     eax, 80070057h
0x180053855  jmp     loc_180053A1A
0x18005385a  mov     r14d, 1
0x180053860  test    rbp, rbp
0x180053863  jnz     short loc_18005386F
0x180053865  mov     ebx, 800401EAh
0x18005386a  jmp     loc_180053A0D
0x18005386f  mov     lpszFileName, rbp; lpFileName
0x180053872  xor     ebx, ebx
0x180053874  call    cs:__imp_GetFileAttributesW
0x18005387b  nop     dword ptr [rax+rax+00h]
0x180053880  cmp     eax, 0FFFFFFFFh
0x180053883  jz      short loc_180053891
0x180053885  bt      eax, 0Ah
0x180053889  mov     eax, 100000h
0x18005388e  cmovb   ebx, eax
0x180053891  and     [rsp+0A8h+var_78], 0
0x180053897  xor     r9d, r9d; lpSecurityAttributes
0x18005389a  mov     [rsp+0A8h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18005389e  mov     edx, 80000100h; dwDesiredAccess
0x1800538a3  mov     lpszFileName, rbp; lpFileName
0x1800538a6  mov     [rsp+0A8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800538ae  lea     r8d, [r9+3]; dwShareMode
0x1800538b2  call    cs:__imp_CreateFileW
0x1800538b9  nop     dword ptr [rax+rax+00h]
0x1800538be  mov     rsi, rax
0x1800538c1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800538c5  jnz     short loc_180053903
0x1800538c7  xor     r14d, r14d
0x1800538ca  lea     r8d, [rax+4]; dwShareMode
0x1800538ce  and     [rsp+0A8h+var_78], r14
0x1800538d3  xor     r9d, r9d; lpSecurityAttributes
0x1800538d6  mov     [rsp+0A8h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1800538da  mov     edx, 80000000h; dwDesiredAccess
0x1800538df  mov     lpszFileName, rbp; lpFileName
0x1800538e2  mov     [rsp+0A8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800538ea  call    cs:__imp_CreateFileW
0x1800538f1  nop     dword ptr [rax+rax+00h]
0x1800538f6  mov     rsi, rax
0x1800538f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800538fd  jz      loc_180053865
0x180053903  test    r14d, r14d
0x180053906  jz      short loc_180053959
0x180053908  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180053910  lea     clsidOle1, [rsp+0A8h+basicInformation]; FileInformation
0x180053915  and     dword ptr [rsp+0A8h+basicInformation+24h], 0
0x18005391a  lea     pcid, [rsp+0A8h+IoStatusBlock]; IoStatusBlock
0x18005391f  and     [rsp+0A8h+basicInformation.FileAttributes], 0
0x180053924  movdqa  xmm1, xmm0
0x180053928  movdqu  xmmword ptr [rsp+0A8h+basicInformation.CreationTime], xmm0
0x18005392e  mov     r9d, 28h ; '('; Length
0x180053934  mov     lpszFileName, rsi; FileHandle
0x180053937  movdqu  xmmword ptr [rsp+0A8h+basicInformation.LastWriteTime], xmm0
0x18005393d  mov     [rsp+0A8h+dwCreationDisposition], 4; FileInformationClass
0x180053945  xorps   xmm0, xmm0
0x180053948  movups  xmmword ptr [rsp+0A8h+IoStatusBlock.___u0], xmm0
0x18005394d  call    cs:__imp_NtSetInformationFile
0x180053954  nop     dword ptr [rax+rax+00h]
0x180053959  mov     pcid, rdi
0x18005395c  mov     lpszFileName, rsi
0x18005395f  call    cs:__imp_DfGetClass
0x180053966  nop     dword ptr [rax+rax+00h]
0x18005396b  mov     pcid, qword ptr cs:GUID_NULL.Data4
0x180053972  mov     ebx, eax
0x180053974  mov     lpszFileName, qword ptr cs:GUID_NULL.Data1
0x18005397b  test    eax, eax
0x18005397d  jnz     short loc_180053993
0x18005397f  mov     rax, [rdi]
0x180053982  sub     rax, lpszFileName
0x180053985  jnz     short loc_18005398E
0x180053987  mov     rax, [rdi+8]
0x18005398b  sub     rax, pcid
0x18005398e  test    rax, rax
0x180053991  jnz     short $errRet_29
0x180053993  mov     rax, [r15]
0x180053996  sub     rax, lpszFileName
0x180053999  jnz     short loc_1800539A2
0x18005399b  mov     rax, [r15+8]
0x18005399f  sub     rax, pcid
0x1800539a2  test    rax, rax
0x1800539a5  jz      short loc_1800539B3
0x1800539a7  movups  xmm0, xmmword ptr [r15]
0x1800539ab  xor     ebx, ebx
0x1800539ad  movdqu  xmmword ptr [rdi], xmm0
0x1800539b1  jmp     short $errRet_29
0x1800539b3  mov     pcid, rdi; pclsid
0x1800539b6  mov     lpszFileName, rsi; hfile
0x1800539b9  call    ?wCoGetClassPattern@@YAJPEAXPEAU_GUID@@@Z; wCoGetClassPattern(void *,_GUID *)
0x1800539be  mov     ebx, eax
0x1800539c0  cmp     eax, 80040154h
0x1800539c5  jnz     short $errRet_29
0x1800539c7  mov     lpszFileName, rbp; szPath
0x1800539ca  call    FindExt
0x1800539cf  test    rax, rax
0x1800539d2  jnz     short loc_1800539DB
0x1800539d4  mov     ebx, 800401E6h
0x1800539d9  jmp     short $errRet_29
0x1800539db  mov     pcid, rdi; pclsid
0x1800539de  mov     lpszFileName, rax; pwszExt
0x1800539e1  call    ?wCoGetClassExt@@YAJPEBGPEAU_GUID@@@Z; wCoGetClassExt(ushort const *,_GUID *)
0x1800539e6  xor     ecx, ecx
0x1800539e8  mov     ebx, 800401E6h
0x1800539ed  test    eax, eax
0x1800539ef  cmovnz  ecx, ebx
0x1800539f2  mov     ebx, ecx
0x1800539f4  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800539f8  jz      short loc_180053A09
0x1800539fa  mov     lpszFileName, rsi; hObject
0x1800539fd  call    cs:__imp_CloseHandle
0x180053a04  nop     dword ptr [rax+rax+00h]
0x180053a09  test    ebx, ebx
0x180053a0b  jz      short loc_180053A18
0x180053a0d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180053a14  movdqu  xmmword ptr [rdi], xmm0
0x180053a18  mov     eax, ebx
0x180053a1a  mov     lpszFileName, [rsp+0A8h+var_30]
0x180053a1f  xor     lpszFileName, rsp; StackCookie
0x180053a22  call    __security_check_cookie
0x180053a27  mov     rbx, [rsp+0A8h+arg_10]
0x180053a2f  add     rsp, 80h
0x180053a36  pop     r15
0x180053a38  pop     r14
0x180053a3a  pop     rdi
0x180053a3b  pop     rsi
0x180053a3c  pop     rbp
0x180053a3d  retn
```
