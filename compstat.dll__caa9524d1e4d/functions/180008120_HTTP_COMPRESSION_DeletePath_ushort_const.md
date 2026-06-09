# HTTP_COMPRESSION::DeletePath(ushort const *)

- ea: `0x180008120`
- end: `0x180008478`
- name: `?DeletePath@HTTP_COMPRESSION@@CAJPEBG@Z`
- size: `856`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004180`

## callees

- `0x180004d40`
- `0x180005160`
- `0x180005190`
- `0x1800051c0`
- `0x180005f52`
- `0x180005f90`
- `0x180008120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000841f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000844c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000841f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000844c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800082e4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800082e4`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800082d5`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800082d5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008255`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800083a6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800083f6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008255`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800083a6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800083f6`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180008240`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180008240`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800082c7`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800082c7`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000821e`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000821e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800081a0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800081a0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008380`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008380`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000816c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000816c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800083ff`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800083ff`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180008333`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000842a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180008333`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000842a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180008263`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180008263`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800083d7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800083d7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800083af`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800083af`

## pseudocode

```c
__int64 __fastcall HTTP_COMPRESSION::DeletePath(const unsigned __int16 *a1)
{
  signed int inserted; // ebx
  struct STRING_QUEUE_ITEM *v3; // rax
  struct STRING_QUEUE_ITEM *v4; // rdi
  unsigned int v5; // edx
  const WCHAR *Str; // rax
  HANDLE FirstFileW; // r14
  int v8; // r15d
  int v9; // edx
  int v10; // edx
  unsigned int CCH; // eax
  const WCHAR *v13; // rax
  signed int v14; // esi
  const WCHAR *v15; // rax
  unsigned int v16; // edx
  signed int LastError; // eax
  _QWORD v18[2]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v19[64]; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v21[256]; // [rsp+2C0h] [rbp+1C0h] BYREF

  memset_0(v21, 0, sizeof(v21));
  STRU::STRU((STRU *)v19, v21, 0x100u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v18[1] = v18;
  v18[0] = v18;
  inserted = STRU::Copy((STRU *)v19, a1);
  if ( inserted >= 0 )
  {
    inserted = STRING_QUEUE::InsertHead((STRING_QUEUE *)v18, (struct STRU *)v19);
    if ( inserted >= 0 )
    {
      while ( 1 )
      {
        v3 = STRING_QUEUE::RemoveHead((STRING_QUEUE *)v18);
        v4 = v3;
        if ( !v3 )
          break;
        inserted = STRU::Copy((STRU *)v19, (struct STRING_QUEUE_ITEM *)((char *)v3 + 16));
        if ( inserted < 0
          || (inserted = STRU::Append((STRU *)v19, L"\\*", 2u), inserted < 0)
          || (Str = STRU::QueryStr((STRU *)v19),
              FirstFileW = FindFirstFileW(Str, &FindFileData),
              FirstFileW == (HANDLE)-1LL) )
        {
LABEL_21:
          STRING_QUEUE_ITEM::`scalar deleting destructor'(v4, v5);
          break;
        }
        v8 = 1;
        do
        {
          v9 = FindFileData.cFileName[0] - 46;
          if ( FindFileData.cFileName[0] == 46 )
            v9 = FindFileData.cFileName[1];
          if ( v9 )
          {
            v10 = FindFileData.cFileName[0] - 46;
            if ( FindFileData.cFileName[0] == 46 )
            {
              v10 = FindFileData.cFileName[1] - 46;
              if ( FindFileData.cFileName[1] == 46 )
                v10 = FindFileData.cFileName[2];
            }
            if ( v10 )
            {
              CCH = STRU::QueryCCH((struct STRING_QUEUE_ITEM *)((char *)v4 + 16));
              STRU::SetLen((STRU *)v19, CCH + 1);
              inserted = STRU::Append((STRU *)v19, FindFileData.cFileName);
              if ( inserted < 0 )
                goto LABEL_20;
              if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
              {
                if ( v8 )
                {
                  v8 = 0;
                  inserted = STRING_QUEUE::InsertHead(
                               (STRING_QUEUE *)v18,
                               (struct STRING_QUEUE_ITEM *)((char *)v4 + 16));
                  if ( inserted < 0 )
                    goto LABEL_21;
                }
                inserted = STRING_QUEUE::InsertHead((STRING_QUEUE *)v18, (struct STRU *)v19);
                if ( inserted < 0 )
                {
LABEL_20:
                  FindClose(FirstFileW);
                  goto LABEL_21;
                }
              }
              else
              {
                v13 = STRU::QueryStr((STRU *)v19);
                if ( !DeleteFileW(v13) && GetLastError() != 2 && GetLastError() != 3 )
                {
                  LastError = GetLastError();
                  inserted = LastError;
                  if ( LastError > 0 )
                    inserted = (unsigned __int16)LastError | 0x80070000;
                  goto LABEL_21;
                }
              }
            }
          }
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        v14 = GetLastError();
        if ( v8 )
        {
          v15 = STRU::QueryStr((struct STRING_QUEUE_ITEM *)((char *)v4 + 16));
          if ( !RemoveDirectoryW(v15) && GetLastError() != 2 && GetLastError() != 3 )
            v14 = GetLastError();
        }
        FindClose(FirstFileW);
        STRING_QUEUE_ITEM::`scalar deleting destructor'(v4, v16);
        if ( v14 != 18 )
        {
          if ( v14 > 0 )
            inserted = (unsigned __int16)v14 | 0x80070000;
          else
            inserted = v14;
          break;
        }
      }
    }
  }
  STRING_QUEUE::~STRING_QUEUE((STRING_QUEUE *)v18);
  STRU::~STRU((STRU *)v19);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180008120  push    rbp
0x180008122  push    rbx
0x180008123  lea     rbp, [rsp-3E8h]
0x18000812b  sub     rsp, 4E8h
0x180008132  mov     rax, cs:__security_cookie
0x180008139  xor     rax, rsp
0x18000813c  mov     [rbp+3F0h+var_30], rax
0x180008143  mov     rbx, rcx
0x180008146  xor     edx, edx; Val
0x180008148  lea     rcx, [rbp+3F0h+var_230]; void *
0x18000814f  mov     r8d, 200h; Size
0x180008155  call    memset_0
0x18000815a  mov     r8d, 100h
0x180008160  lea     rdx, [rbp+3F0h+var_230]
0x180008167  lea     rcx, [rsp+4F0h+var_4C0]
0x18000816c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180008172  xor     edx, edx; Val
0x180008174  lea     rcx, [rsp+4F0h+FindFileData]; void *
0x180008179  mov     r8d, 250h; Size
0x18000817f  call    memset_0
0x180008184  lea     rax, [rsp+4F0h+var_4D0]
0x180008189  mov     rdx, rbx
0x18000818c  mov     [rsp+4F0h+var_4C8], rax
0x180008191  lea     rcx, [rsp+4F0h+var_4C0]
0x180008196  lea     rax, [rsp+4F0h+var_4D0]
0x18000819b  mov     [rsp+4F0h+var_4D0], rax
0x1800081a0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800081a6  mov     ebx, eax
0x1800081a8  test    eax, eax
0x1800081aa  js      loc_180008371
0x1800081b0  lea     rdx, [rsp+4F0h+var_4C0]; struct STRU *
0x1800081b5  lea     rcx, [rsp+4F0h+var_4D0]; this
0x1800081ba  call    ?InsertHead@STRING_QUEUE@@QEAAJAEAVSTRU@@@Z; STRING_QUEUE::InsertHead(STRU &)
0x1800081bf  mov     ebx, eax
0x1800081c1  test    eax, eax
0x1800081c3  js      loc_180008371
0x1800081c9  mov     [rsp+4F0h+arg_10], rdi
0x1800081d1  mov     [rsp+4F0h+arg_18], r12
0x1800081d9  mov     [rsp+4F0h+var_10], r13
0x1800081e1  mov     r13d, 2Eh ; '.'
0x1800081e7  mov     [rsp+4F0h+var_18], r14
0x1800081ef  mov     [rsp+4F0h+var_20], r15
0x1800081f7  mov     [rsp+4F0h+arg_8], rsi
0x1800081ff  lea     rcx, [rsp+4F0h+var_4D0]; this
0x180008204  call    ?RemoveHead@STRING_QUEUE@@QEAAPEAVSTRING_QUEUE_ITEM@@XZ; STRING_QUEUE::RemoveHead(void)
0x180008209  mov     rdi, rax
0x18000820c  test    rax, rax
0x18000820f  jz      loc_180008341
0x180008215  lea     rdx, [rax+10h]
0x180008219  lea     rcx, [rsp+4F0h+var_4C0]
0x18000821e  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180008224  mov     ebx, eax
0x180008226  test    eax, eax
0x180008228  js      loc_180008339
0x18000822e  mov     r8d, 2
0x180008234  lea     rdx, asc_18000AFD8; "\\*"
0x18000823b  lea     rcx, [rsp+4F0h+var_4C0]
0x180008240  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180008246  mov     ebx, eax
0x180008248  test    eax, eax
0x18000824a  js      loc_180008339
0x180008250  lea     rcx, [rsp+4F0h+var_4C0]
0x180008255  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000825b  mov     rcx, rax; lpFileName
0x18000825e  lea     rdx, [rsp+4F0h+FindFileData]; lpFindFileData
0x180008263  call    cs:__imp_FindFirstFileW
0x180008269  mov     r14, rax
0x18000826c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008270  jz      loc_180008339
0x180008276  mov     r15d, 1
0x18000827c  movzx   r9d, [rbp+3F0h+FindFileData.cFileName]
0x180008281  movzx   r8d, [rbp+3F0h+FindFileData.cFileName+2]
0x180008286  mov     edx, r9d
0x180008289  sub     edx, r13d
0x18000828c  jnz     short loc_180008298
0x18000828e  xor     eax, eax
0x180008290  mov     edx, r8d
0x180008293  movzx   ecx, ax
0x180008296  sub     edx, ecx
0x180008298  test    edx, edx
0x18000829a  jz      loc_1800083CF
0x1800082a0  mov     edx, r9d
0x1800082a3  sub     edx, r13d
0x1800082a6  jnz     short loc_1800082BB
0x1800082a8  mov     edx, r8d
0x1800082ab  sub     edx, r13d
0x1800082ae  jnz     short loc_1800082BB
0x1800082b0  movzx   edx, [rbp+3F0h+FindFileData.cFileName+4]
0x1800082b4  xor     eax, eax
0x1800082b6  movzx   ecx, ax
0x1800082b9  sub     edx, ecx
0x1800082bb  test    edx, edx
0x1800082bd  jz      loc_1800083CF
0x1800082c3  lea     rcx, [rdi+10h]
0x1800082c7  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800082cd  lea     rcx, [rsp+4F0h+var_4C0]
0x1800082d2  lea     edx, [rax+1]
0x1800082d5  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x1800082db  lea     rdx, [rbp+3F0h+FindFileData.cFileName]
0x1800082df  lea     rcx, [rsp+4F0h+var_4C0]
0x1800082e4  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800082ea  mov     ebx, eax
0x1800082ec  test    eax, eax
0x1800082ee  js      short loc_180008330
0x1800082f0  test    byte ptr [rsp+4F0h+FindFileData.dwFileAttributes], 10h
0x1800082f5  jz      loc_1800083A1
0x1800082fb  test    r15d, r15d
0x1800082fe  jz      short loc_180008317
0x180008300  lea     rdx, [rdi+10h]; struct STRU *
0x180008304  xor     r15d, r15d
0x180008307  lea     rcx, [rsp+4F0h+var_4D0]; this
0x18000830c  call    ?InsertHead@STRING_QUEUE@@QEAAJAEAVSTRU@@@Z; STRING_QUEUE::InsertHead(STRU &)
0x180008311  mov     ebx, eax
0x180008313  test    eax, eax
0x180008315  js      short loc_180008339
0x180008317  lea     rdx, [rsp+4F0h+var_4C0]; struct STRU *
0x18000831c  lea     rcx, [rsp+4F0h+var_4D0]; this
0x180008321  call    ?InsertHead@STRING_QUEUE@@QEAAJAEAVSTRU@@@Z; STRING_QUEUE::InsertHead(STRU &)
0x180008326  mov     ebx, eax
0x180008328  test    eax, eax
0x18000832a  jns     loc_1800083CF
0x180008330  mov     rcx, r14; hFindFile
0x180008333  call    cs:__imp_FindClose
0x180008339  mov     rcx, rdi; this
0x18000833c  call    ??_GSTRING_QUEUE_ITEM@@QEAAPEAXI@Z; STRING_QUEUE_ITEM::`scalar deleting destructor'(uint)
0x180008341  mov     rsi, [rsp+4F0h+arg_8]
0x180008349  mov     r13, [rsp+4F0h+var_10]
0x180008351  mov     r12, [rsp+4F0h+arg_18]
0x180008359  mov     rdi, [rsp+4F0h+arg_10]
0x180008361  mov     r14, [rsp+4F0h+var_18]
0x180008369  mov     r15, [rsp+4F0h+var_20]
0x180008371  lea     rcx, [rsp+4F0h+var_4D0]; this
0x180008376  call    ??1STRING_QUEUE@@QEAA@XZ; STRING_QUEUE::~STRING_QUEUE(void)
0x18000837b  lea     rcx, [rsp+4F0h+var_4C0]
0x180008380  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008386  mov     eax, ebx
0x180008388  mov     rcx, [rbp+3F0h+var_30]
0x18000838f  xor     rcx, rsp; StackCookie
0x180008392  call    __security_check_cookie
0x180008397  add     rsp, 4E8h
0x18000839e  pop     rbx
0x18000839f  pop     rbp
0x1800083a0  retn
0x1800083a1  lea     rcx, [rsp+4F0h+var_4C0]
0x1800083a6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800083ac  mov     rcx, rax; lpFileName
0x1800083af  call    cs:__imp_DeleteFileW
0x1800083b5  test    eax, eax
0x1800083b7  jnz     short loc_1800083CF
0x1800083b9  call    cs:__imp_GetLastError
0x1800083bf  cmp     eax, 2
0x1800083c2  jz      short loc_1800083CF
0x1800083c4  call    cs:__imp_GetLastError
0x1800083ca  cmp     eax, 3
0x1800083cd  jnz     short loc_18000844C
0x1800083cf  lea     rdx, [rsp+4F0h+FindFileData]; lpFindFileData
0x1800083d4  mov     rcx, r14; hFindFile
0x1800083d7  call    cs:__imp_FindNextFileW
0x1800083dd  test    eax, eax
0x1800083df  jnz     loc_18000827C
0x1800083e5  call    cs:__imp_GetLastError
0x1800083eb  mov     esi, eax
0x1800083ed  test    r15d, r15d
0x1800083f0  jz      short loc_180008427
0x1800083f2  lea     rcx, [rdi+10h]
0x1800083f6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800083fc  mov     rcx, rax; lpPathName
0x1800083ff  call    cs:__imp_RemoveDirectoryW
0x180008405  test    eax, eax
0x180008407  jnz     short loc_180008427
0x180008409  call    cs:__imp_GetLastError
0x18000840f  cmp     eax, 2
0x180008412  jz      short loc_180008427
0x180008414  call    cs:__imp_GetLastError
0x18000841a  cmp     eax, 3
0x18000841d  jz      short loc_180008427
0x18000841f  call    cs:__imp_GetLastError
0x180008425  mov     esi, eax
0x180008427  mov     rcx, r14; hFindFile
0x18000842a  call    cs:__imp_FindClose
0x180008430  mov     rcx, rdi; this
0x180008433  call    ??_GSTRING_QUEUE_ITEM@@QEAAPEAXI@Z; STRING_QUEUE_ITEM::`scalar deleting destructor'(uint)
0x180008438  cmp     esi, 12h
0x18000843b  jz      loc_1800081FF
0x180008441  test    esi, esi
0x180008443  jg      short loc_18000846A
0x180008445  mov     ebx, esi
0x180008447  jmp     loc_180008341
0x18000844c  call    cs:__imp_GetLastError
0x180008452  mov     ebx, eax
0x180008454  test    eax, eax
0x180008456  jle     loc_180008339
0x18000845c  movzx   ebx, ax
0x18000845f  or      ebx, 80070000h
0x180008465  jmp     loc_180008339
0x18000846a  movzx   ebx, si
0x18000846d  or      ebx, 80070000h
0x180008473  jmp     loc_180008341
```
