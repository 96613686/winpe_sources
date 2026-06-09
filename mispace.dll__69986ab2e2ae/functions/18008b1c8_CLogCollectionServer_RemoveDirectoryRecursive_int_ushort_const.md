# CLogCollectionServer::_RemoveDirectoryRecursive(int,ushort const *)

- ea: `0x18008b1c8`
- end: `0x18008b4d3`
- name: `?_RemoveDirectoryRecursive@CLogCollectionServer@@AEBA?AV_status_t@@HPEBG@Z`
- size: `779`
- prototype: `struct _status_t __high(int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180086ff8`
- `0x18008b1c8`

## callees

- `0x1800015d8`
- `0x180006350`
- `0x180006dd4`
- `0x18000cdb0`
- `0x180029b04`
- `0x18008b1c8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18008b2bf`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18008b2bf`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18008b465`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18008b465`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18008b4a0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18008b4a0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008b3fb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008b3fb`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18008b3b8`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18008b3b8`

## string_xrefs

- `0x18008b27a`: `CLogCollectionServer::_RemoveDirectoryRecursive`
- `0x18008b2ce`: `CLogCollectionServer::_RemoveDirectoryRecursive`

## pseudocode

```c
_status_t *__fastcall CLogCollectionServer::_RemoveDirectoryRecursive(_DWORD *a1, _status_t *a2, int a3, __int64 a4)
{
  int v8; // eax
  int v9; // r8d
  int v10; // r9d
  char *FirstFileW; // rsi
  int v12; // eax
  bool v13; // zf
  __int64 v14; // rax
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  BOOL v18; // eax
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  int *v22; // rdx
  BOOL v23; // eax
  BOOL NextFileW; // eax
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+44h] [rbp-BCh] BYREF
  const char *v28; // [rsp+48h] [rbp-B8h] BYREF
  char v29[16]; // [rsp+50h] [rbp-B0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR PathName[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR FileName[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(FileName, 0, 0x208u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  *(_QWORD *)a2 = 0;
  *((_BYTE *)a2 + 8) = 0;
  if ( a3 > *a1 )
    return a2;
  v8 = StringCchPrintfW(FileName, 0x104u, L"%s*", a4);
  *(_DWORD *)a2 = v8;
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_18039EB68 > 2 )
    {
      v26 = v8;
      v27 = 2376;
      v28 = "CLogCollectionServer::_RemoveDirectoryRecursive";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)word_18031E0B2,
        v9,
        v10,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26);
    }
    return a2;
  }
  FirstFileW = (char *)FindFirstFileW(FileName, &FindFileData);
  do
  {
    if ( FindFileData.cFileName[0] != 46
      || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
    {
      memset_0(PathName, 0, 0x208u);
      v12 = StringCchPrintfW(PathName, 0x104u, L"%s\\%s", a4, FindFileData.cFileName);
      v13 = (FindFileData.dwFileAttributes & 0x10) == 0;
      *(_DWORD *)a2 = v12;
      if ( v13 )
      {
        v23 = DeleteFileW(PathName);
        _status_t::SetBoolGle(a2, v23);
        v21 = *(_DWORD *)a2;
        if ( *(int *)a2 < 0 && (unsigned int)dword_18039EB68 > 2 )
        {
          v26 = 2412;
          v22 = &dword_18031D1A4;
          goto LABEL_20;
        }
      }
      else
      {
        v14 = CLogCollectionServer::_RemoveDirectoryRecursive(a1, v29, (unsigned int)(a3 + 1), PathName);
        *(_QWORD *)a2 = *(_QWORD *)v14;
        *((_DWORD *)a2 + 2) = *(_DWORD *)(v14 + 8);
        v17 = *(_DWORD *)a2;
        if ( *(int *)a2 < 0 && (unsigned int)dword_18039EB68 > 2 )
        {
          v27 = *(_DWORD *)a2;
          v26 = 2399;
          v28 = "CLogCollectionServer::_RemoveDirectoryRecursive";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v17,
            (unsigned int)&unk_18031E2A0,
            v15,
            v16,
            (__int64)&v28,
            (__int64)&v26,
            (__int64)&v27);
        }
        v18 = RemoveDirectoryW(PathName);
        _status_t::SetBoolGle(a2, v18);
        v21 = *(_DWORD *)a2;
        if ( *(int *)a2 < 0 && (unsigned int)dword_18039EB68 > 2 )
        {
          v26 = 2405;
          v22 = (int *)byte_18031D505;
LABEL_20:
          v27 = v21;
          v28 = "CLogCollectionServer::_RemoveDirectoryRecursive";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v21,
            (_DWORD)v22,
            v19,
            v20,
            (__int64)&v28,
            (__int64)&v26,
            (__int64)&v27);
        }
      }
    }
    NextFileW = FindNextFileW(FirstFileW, &FindFileData);
    _status_t::SetBoolGle(a2, NextFileW);
  }
  while ( *(int *)a2 >= 0 );
  if ( *(_DWORD *)a2 == -2147024878 )
  {
    *(_QWORD *)a2 = 0;
    *((_BYTE *)a2 + 8) = 0;
  }
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(FirstFileW);
  return a2;
}

```

## disassembly

```asm
0x18008b1c8  push    rbp
0x18008b1ca  push    rbx
0x18008b1cb  push    rsi
0x18008b1cc  push    rdi
0x18008b1cd  push    r12
0x18008b1cf  push    r13
0x18008b1d1  push    r14
0x18008b1d3  push    r15
0x18008b1d5  lea     rbp, [rsp-5E8h]
0x18008b1dd  sub     rsp, 6E8h
0x18008b1e4  mov     rax, cs:__security_cookie
0x18008b1eb  xor     rax, rsp
0x18008b1ee  mov     [rbp+620h+var_50], rax
0x18008b1f5  mov     r13d, r8d
0x18008b1f8  mov     rbx, rdx
0x18008b1fb  mov     r15, rcx
0x18008b1fe  xor     edx, edx; Val
0x18008b200  mov     r8d, 208h; Size
0x18008b206  lea     rcx, [rbp+620h+FileName]; void *
0x18008b20d  mov     r14, r9
0x18008b210  call    memset_0
0x18008b215  xor     edx, edx; Val
0x18008b217  lea     rcx, [rsp+720h+FindFileData]; void *
0x18008b21c  mov     r8d, 250h; Size
0x18008b222  call    memset_0
0x18008b227  xor     r12d, r12d
0x18008b22a  mov     [rbx], r12
0x18008b22d  mov     [rbx+8], r12b
0x18008b231  cmp     r13d, [r15]
0x18008b234  jg      loc_18008B4AC
0x18008b23a  mov     r9, r14
0x18008b23d  lea     r8, aS_3; "%s*"
0x18008b244  mov     edx, 104h; unsigned __int64
0x18008b249  lea     rcx, [rbp+620h+FileName]; unsigned __int16 *
0x18008b250  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008b255  mov     [rbx], eax
0x18008b257  mov     ecx, eax
0x18008b259  test    eax, eax
0x18008b25b  jns     short loc_18008B2B3
0x18008b25d  mov     eax, cs:dword_18039EB68
0x18008b263  cmp     eax, 2
0x18008b266  jbe     loc_18008B4AC
0x18008b26c  lea     rax, [rsp+720h+var_6E0]
0x18008b271  mov     [rsp+720h+var_6E0], ecx
0x18008b275  mov     [rsp+720h+var_6F0], rax
0x18008b27a  lea     rdi, aClogcollection_24; "CLogCollectionServer::_RemoveDirectoryR"...
0x18008b281  lea     rax, [rsp+720h+var_6DC]
0x18008b286  mov     [rsp+720h+var_6DC], 948h
0x18008b28e  mov     [rsp+720h+var_6F8], rax
0x18008b293  lea     rdx, word_18031E0B2
0x18008b29a  lea     rax, [rsp+720h+var_6D8]
0x18008b29f  mov     [rsp+720h+var_6D8], rdi
0x18008b2a4  mov     [rsp+720h+var_700], rax
0x18008b2a9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008b2ae  jmp     loc_18008B4AC
0x18008b2b3  lea     rdx, [rsp+720h+FindFileData]; lpFindFileData
0x18008b2b8  lea     rcx, [rbp+620h+FileName]; lpFileName
0x18008b2bf  call    cs:__imp_FindFirstFileW
0x18008b2c6  nop     dword ptr [rax+rax+00h]
0x18008b2cb  mov     rsi, rax
0x18008b2ce  lea     rdi, aClogcollection_24; "CLogCollectionServer::_RemoveDirectoryR"...
0x18008b2d5  cmp     [rbp+620h+FindFileData.cFileName], 2Eh ; '.'
0x18008b2da  jnz     short loc_18008B2FA
0x18008b2dc  movzx   ecx, [rbp+620h+FindFileData.cFileName+2]
0x18008b2e0  test    cx, cx
0x18008b2e3  jz      loc_18008B45D
0x18008b2e9  cmp     cx, 2Eh ; '.'
0x18008b2ed  jnz     short loc_18008B2FA
0x18008b2ef  cmp     [rbp+620h+FindFileData.cFileName+4], r12w
0x18008b2f4  jz      loc_18008B45D
0x18008b2fa  xor     edx, edx; Val
0x18008b2fc  lea     rcx, [rbp+620h+PathName]; void *
0x18008b303  mov     r8d, 208h; Size
0x18008b309  call    memset_0
0x18008b30e  lea     rax, [rbp+620h+FindFileData.cFileName]
0x18008b312  mov     r9, r14
0x18008b315  lea     r8, Format; "%s\\%s"
0x18008b31c  mov     [rsp+720h+var_700], rax
0x18008b321  mov     edx, 104h; unsigned __int64
0x18008b326  lea     rcx, [rbp+620h+PathName]; unsigned __int16 *
0x18008b32d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008b332  test    byte ptr [rsp+720h+FindFileData.dwFileAttributes], 10h
0x18008b337  mov     [rbx], eax
0x18008b339  jz      loc_18008B3F4
0x18008b33f  lea     r8d, [r13+1]
0x18008b343  mov     rcx, r15
0x18008b346  lea     r9, [rbp+620h+PathName]
0x18008b34d  lea     rdx, [rsp+720h+var_6D0]
0x18008b352  call    ?_RemoveDirectoryRecursive@CLogCollectionServer@@AEBA?AV_status_t@@HPEBG@Z; CLogCollectionServer::_RemoveDirectoryRecursive(int,ushort const *)
0x18008b357  movsd   xmm0, qword ptr [rax]
0x18008b35b  movsd   qword ptr [rbx], xmm0
0x18008b35f  mov     eax, [rax+8]
0x18008b362  mov     [rbx+8], eax
0x18008b365  mov     ecx, [rbx]
0x18008b367  test    ecx, ecx
0x18008b369  jns     short loc_18008B3B1
0x18008b36b  mov     eax, cs:dword_18039EB68
0x18008b371  cmp     eax, 2
0x18008b374  jbe     short loc_18008B3B1
0x18008b376  lea     rax, [rsp+720h+var_6DC]
0x18008b37b  mov     [rsp+720h+var_6DC], ecx
0x18008b37f  mov     [rsp+720h+var_6F0], rax
0x18008b384  lea     rdx, unk_18031E2A0
0x18008b38b  lea     rax, [rsp+720h+var_6E0]
0x18008b390  mov     [rsp+720h+var_6E0], 95Fh
0x18008b398  mov     [rsp+720h+var_6F8], rax
0x18008b39d  lea     rax, [rsp+720h+var_6D8]
0x18008b3a2  mov     [rsp+720h+var_700], rax
0x18008b3a7  mov     [rsp+720h+var_6D8], rdi
0x18008b3ac  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008b3b1  lea     rcx, [rbp+620h+PathName]; lpPathName
0x18008b3b8  call    cs:__imp_RemoveDirectoryW
0x18008b3bf  nop     dword ptr [rax+rax+00h]
0x18008b3c4  mov     edx, eax; int
0x18008b3c6  mov     rcx, rbx; this
0x18008b3c9  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x18008b3ce  mov     ecx, [rbx]
0x18008b3d0  test    ecx, ecx
0x18008b3d2  jns     loc_18008B45D
0x18008b3d8  mov     eax, cs:dword_18039EB68
0x18008b3de  cmp     eax, 2
0x18008b3e1  jbe     short loc_18008B45D
0x18008b3e3  mov     [rsp+720h+var_6E0], 965h
0x18008b3eb  lea     rdx, byte_18031D505
0x18008b3f2  jmp     short loc_18008B431
0x18008b3f4  lea     rcx, [rbp+620h+PathName]; lpFileName
0x18008b3fb  call    cs:__imp_DeleteFileW
0x18008b402  nop     dword ptr [rax+rax+00h]
0x18008b407  mov     edx, eax; int
0x18008b409  mov     rcx, rbx; this
0x18008b40c  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x18008b411  mov     ecx, [rbx]
0x18008b413  test    ecx, ecx
0x18008b415  jns     short loc_18008B45D
0x18008b417  mov     eax, cs:dword_18039EB68
0x18008b41d  cmp     eax, 2
0x18008b420  jbe     short loc_18008B45D
0x18008b422  mov     [rsp+720h+var_6E0], 96Ch
0x18008b42a  lea     rdx, dword_18031D1A4
0x18008b431  lea     rax, [rsp+720h+var_6DC]
0x18008b436  mov     [rsp+720h+var_6F0], rax
0x18008b43b  lea     rax, [rsp+720h+var_6E0]
0x18008b440  mov     [rsp+720h+var_6F8], rax
0x18008b445  lea     rax, [rsp+720h+var_6D8]
0x18008b44a  mov     [rsp+720h+var_700], rax
0x18008b44f  mov     [rsp+720h+var_6DC], ecx
0x18008b453  mov     [rsp+720h+var_6D8], rdi
0x18008b458  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008b45d  lea     rdx, [rsp+720h+FindFileData]; lpFindFileData
0x18008b462  mov     rcx, rsi; hFindFile
0x18008b465  call    cs:__imp_FindNextFileW
0x18008b46c  nop     dword ptr [rax+rax+00h]
0x18008b471  mov     edx, eax; int
0x18008b473  mov     rcx, rbx; this
0x18008b476  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x18008b47b  cmp     [rbx], r12d
0x18008b47e  jge     loc_18008B2D5
0x18008b484  cmp     dword ptr [rbx], 80070012h
0x18008b48a  jnz     short loc_18008B493
0x18008b48c  mov     [rbx], r12
0x18008b48f  mov     [rbx+8], r12b
0x18008b493  lea     rcx, [rsi-1]
0x18008b497  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18008b49b  ja      short loc_18008B4AC
0x18008b49d  mov     rcx, rsi; hFindFile
0x18008b4a0  call    cs:__imp_FindClose
0x18008b4a7  nop     dword ptr [rax+rax+00h]
0x18008b4ac  mov     rax, rbx
0x18008b4af  mov     rcx, [rbp+620h+var_50]
0x18008b4b6  xor     rcx, rsp; StackCookie
0x18008b4b9  call    __security_check_cookie
0x18008b4be  add     rsp, 6E8h
0x18008b4c5  pop     r15
0x18008b4c7  pop     r14
0x18008b4c9  pop     r13
0x18008b4cb  pop     r12
0x18008b4cd  pop     rdi
0x18008b4ce  pop     rsi
0x18008b4cf  pop     rbx
0x18008b4d0  pop     rbp
0x18008b4d1  retn
```
