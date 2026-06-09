# GetClassFileEx

- ea: `0x180061754`
- end: `0x18006194c`
- name: `GetClassFileEx`
- size: `504`
- prototype: `HRESULT __fastcall(const wchar_t *lpszFileName, _GUID *pcid, const _GUID *clsidOle1)`
- caller_count: `8`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800486bc`
- `0x18005f2c0`
- `0x18006055c`
- `0x180060740`
- `0x180061740`
- `0x18007bafc`
- `0x180082a58`
- `0x180099e50`

## callees

- `0x18001c1d0`
- `0x180052390`
- `0x1800616d0`
- `0x180061754`
- `0x180065834`
- `0x180065954`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x18006186b`
- `ntdll!NtSetInformationFile` at `0x18006186b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061910`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061910`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800617ae`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800617ae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800617e9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061817`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800617e9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061817`
- `coml2!__imp_DfGetClass` at `0x180061877`
- `coml2!__imp_DfGetClass` at `0x180061877`

## pseudocode

```c
__int64 __fastcall GetClassFileEx(const wchar_t *lpszFileName, _GUID *pcid, const _GUID *clsidOle1)
{
  unsigned int Class; // edi
  DWORD dwFlagsAndAttributes; // ebx
  DWORD FileAttributesW; // eax
  HANDLE FileW; // rax
  HANDLE v11; // rsi
  __int64 v12; // rax
  __int64 v13; // rax
  const wchar_t *Ext; // rax
  int v15; // ebx
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-68h] BYREF
  _FILE_BASIC_INFORMATION basicInformation; // [rsp+50h] [rbp-58h] BYREF

  if ( !IsValidPtrOut(pcid, 0x10u) )
    return 2147942487LL;
  if ( !lpszFileName )
    goto LABEL_4;
  dwFlagsAndAttributes = 0;
  FileAttributesW = GetFileAttributesW(lpszFileName);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x400) != 0 )
    dwFlagsAndAttributes = 0x100000;
  FileW = CreateFileW(lpszFileName, 0x80000100, 3u, 0, 3u, dwFlagsAndAttributes, 0);
  v11 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    *(__m128i *)&basicInformation.CreationTime.LowPart = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    *(_OWORD *)&basicInformation.LastWriteTime.LowPart = *(_OWORD *)&basicInformation.CreationTime.LowPart;
    *(_QWORD *)&basicInformation.FileAttributes = 0;
    IoStatusBlock = 0;
    NtSetInformationFile(FileW, &IoStatusBlock, &basicInformation, 0x28u, FileBasicInformation);
    goto LABEL_12;
  }
  v11 = CreateFileW(lpszFileName, 0x80000000, 3u, 0, 3u, dwFlagsAndAttributes, 0);
  if ( v11 != (HANDLE)-1LL )
  {
LABEL_12:
    Class = DfGetClass(v11, pcid);
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
        Class = wCoGetClassPattern(v11, pcid);
        if ( Class == -2147221164 )
        {
          Ext = FindExt(lpszFileName);
          if ( Ext )
          {
            v15 = 0;
            if ( wCoGetClassExt(Ext, pcid) )
              v15 = -2147221018;
            Class = v15;
          }
          else
          {
            Class = -2147221018;
          }
        }
      }
    }
    if ( v11 != (HANDLE)-1LL )
      CloseHandle(v11);
    if ( !Class )
      return Class;
    goto LABEL_29;
  }
LABEL_4:
  Class = -2147221014;
LABEL_29:
  *pcid = GUID_NULL;
  return Class;
}

```

## disassembly

```asm
0x180061754  mov     [rsp+arg_10], rbx
0x180061759  push    rbp
0x18006175a  push    rsi
0x18006175b  push    rdi
0x18006175c  push    r14
0x18006175e  push    r15
0x180061760  sub     rsp, 80h
0x180061767  mov     rax, cs:__security_cookie
0x18006176e  xor     rax, rsp
0x180061771  mov     [rsp+0A8h+var_30], rax
0x180061776  mov     r14, pcid
0x180061779  mov     rbp, lpszFileName
0x18006177c  mov     lpszFileName, r14; pv
0x18006177f  mov     edx, 10h; cb
0x180061784  mov     r15, clsidOle1
0x180061787  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x18006178c  test    eax, eax
0x18006178e  jnz     short loc_18006179A
0x180061790  mov     eax, 80070057h
0x180061795  jmp     loc_180061928
0x18006179a  test    rbp, rbp
0x18006179d  jnz     short loc_1800617A9
0x18006179f  mov     edi, 800401EAh
0x1800617a4  jmp     loc_18006191A
0x1800617a9  mov     lpszFileName, rbp; lpFileName
0x1800617ac  xor     ebx, ebx
0x1800617ae  call    cs:__imp_GetFileAttributesW
0x1800617b4  cmp     eax, 0FFFFFFFFh
0x1800617b7  jz      short loc_1800617C5
0x1800617b9  bt      eax, 0Ah
0x1800617bd  mov     eax, 100000h
0x1800617c2  cmovb   ebx, eax
0x1800617c5  mov     edi, 3
0x1800617ca  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x1800617d3  mov     r8d, edi; dwShareMode
0x1800617d6  mov     [rsp+0A8h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1800617da  xor     r9d, r9d; lpSecurityAttributes
0x1800617dd  mov     [rsp+0A8h+dwCreationDisposition], edi; dwCreationDisposition
0x1800617e1  mov     edx, 80000100h; dwDesiredAccess
0x1800617e6  mov     lpszFileName, rbp; lpFileName
0x1800617e9  call    cs:__imp_CreateFileW
0x1800617ef  mov     rsi, rax
0x1800617f2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800617f6  jnz     short loc_18006182B
0x1800617f8  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x180061801  xor     r9d, r9d; lpSecurityAttributes
0x180061804  mov     [rsp+0A8h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180061808  mov     r8d, edi; dwShareMode
0x18006180b  mov     edx, 80000000h; dwDesiredAccess
0x180061810  mov     [rsp+0A8h+dwCreationDisposition], edi; dwCreationDisposition
0x180061814  mov     lpszFileName, rbp; lpFileName
0x180061817  call    cs:__imp_CreateFileW
0x18006181d  mov     rsi, rax
0x180061820  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180061824  jnz     short loc_180061871
0x180061826  jmp     loc_18006179F
0x18006182b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180061833  lea     clsidOle1, [rsp+0A8h+basicInformation]; FileInformation
0x180061838  movdqu  xmmword ptr [rsp+0A8h+basicInformation.CreationTime], xmm0
0x18006183e  mov     r9d, 28h ; '('; Length
0x180061844  lea     pcid, [rsp+0A8h+IoStatusBlock]; IoStatusBlock
0x180061849  movdqu  xmmword ptr [rsp+0A8h+basicInformation.LastWriteTime], xmm0
0x18006184f  mov     qword ptr [rsp+0A8h+basicInformation.FileAttributes], 0
0x180061858  mov     lpszFileName, rax; FileHandle
0x18006185b  xorps   xmm0, xmm0
0x18006185e  mov     [rsp+0A8h+dwCreationDisposition], 4; FileInformationClass
0x180061866  movups  xmmword ptr [rsp+0A8h+IoStatusBlock.___u0], xmm0
0x18006186b  call    cs:__imp_NtSetInformationFile
0x180061871  mov     pcid, r14
0x180061874  mov     lpszFileName, rsi
0x180061877  call    cs:__imp_DfGetClass
0x18006187d  mov     pcid, qword ptr cs:GUID_NULL.Data4
0x180061884  mov     edi, eax
0x180061886  mov     lpszFileName, qword ptr cs:GUID_NULL.Data1
0x18006188d  test    eax, eax
0x18006188f  jnz     short loc_1800618A5
0x180061891  mov     rax, [r14]
0x180061894  sub     rax, lpszFileName
0x180061897  jnz     short loc_1800618A0
0x180061899  mov     rax, [r14+8]
0x18006189d  sub     rax, pcid
0x1800618a0  test    rax, rax
0x1800618a3  jnz     short $errRet_31
0x1800618a5  mov     rax, [r15]
0x1800618a8  sub     rax, lpszFileName
0x1800618ab  jnz     short loc_1800618B4
0x1800618ad  mov     rax, [r15+8]
0x1800618b1  sub     rax, pcid
0x1800618b4  test    rax, rax
0x1800618b7  jz      short loc_1800618C6
0x1800618b9  movups  xmm0, xmmword ptr [r15]
0x1800618bd  xor     edi, edi
0x1800618bf  movdqu  xmmword ptr [r14], xmm0
0x1800618c4  jmp     short $errRet_31
0x1800618c6  mov     pcid, r14; pclsid
0x1800618c9  mov     lpszFileName, rsi; hfile
0x1800618cc  call    ?wCoGetClassPattern@@YAJPEAXPEAU_GUID@@@Z; wCoGetClassPattern(void *,_GUID *)
0x1800618d1  mov     edi, eax
0x1800618d3  cmp     eax, 80040154h
0x1800618d8  jnz     short $errRet_31
0x1800618da  mov     lpszFileName, rbp; szPath
0x1800618dd  call    FindExt
0x1800618e2  test    rax, rax
0x1800618e5  jnz     short loc_1800618EE
0x1800618e7  mov     edi, 800401E6h
0x1800618ec  jmp     short $errRet_31
0x1800618ee  mov     pcid, r14; pclsid
0x1800618f1  mov     lpszFileName, rax; pwszExt
0x1800618f4  xor     ebx, ebx
0x1800618f6  call    ?wCoGetClassExt@@YAJPEBGPEAU_GUID@@@Z; wCoGetClassExt(ushort const *,_GUID *)
0x1800618fb  mov     edi, 800401E6h
0x180061900  test    eax, eax
0x180061902  cmovnz  ebx, edi
0x180061905  mov     edi, ebx
0x180061907  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18006190b  jz      short loc_180061916
0x18006190d  mov     lpszFileName, rsi; hObject
0x180061910  call    cs:__imp_CloseHandle
0x180061916  test    edi, edi
0x180061918  jz      short loc_180061926
0x18006191a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180061921  movdqu  xmmword ptr [r14], xmm0
0x180061926  mov     eax, edi
0x180061928  mov     lpszFileName, [rsp+0A8h+var_30]
0x18006192d  xor     lpszFileName, rsp; StackCookie
0x180061930  call    __security_check_cookie
0x180061935  mov     rbx, [rsp+0A8h+arg_10]
0x18006193d  add     rsp, 80h
0x180061944  pop     r15
0x180061946  pop     r14
0x180061948  pop     rdi
0x180061949  pop     rsi
0x18006194a  pop     rbp
0x18006194b  retn
```
