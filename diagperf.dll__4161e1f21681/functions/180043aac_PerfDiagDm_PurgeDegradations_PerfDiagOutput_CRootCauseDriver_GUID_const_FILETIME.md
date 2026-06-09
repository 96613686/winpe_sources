# PerfDiagDm::PurgeDegradations<PerfDiagOutput::CRootCauseDriver>(_GUID const &,_FILETIME)

- ea: `0x180043aac`
- end: `0x180043d35`
- name: `??$PurgeDegradations@UCRootCauseDriver@PerfDiagOutput@@@PerfDiagDm@@YAJAEBU_GUID@@U_FILETIME@@@Z`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800bc880`

## callees

- `0x18001769c`
- `0x18001f3c0`
- `0x180028f6c`
- `0x18002b1b0`
- `0x180032e50`
- `0x18003d028`
- `0x180043aac`
- `0x180043d3c`
- `0x1800b4960`
- `0x1800b74d8`
- `0x1800b77c0`
- `0x1800bb300`
- `0x1800be2f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043be7`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180043b6f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180043b6f`
- `api-ms-win-core-file-l1-1-0!UnlockFile` at `0x180043cdb`
- `api-ms-win-core-file-l1-1-0!UnlockFile` at `0x180043cdb`
- `api-ms-win-core-file-l1-1-0!LockFileEx` at `0x180043bdd`
- `api-ms-win-core-file-l1-1-0!LockFileEx` at `0x180043bdd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180043c8c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180043c8c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180043c9a`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180043c9a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043b46`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043b46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043ce4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043ce4`

## pseudocode

```c
__int64 __fastcall PerfDiagDm::PurgeDegradations<PerfDiagOutput::CRootCauseDriver>(unsigned int *a1, __int64 a2)
{
  unsigned int v2; // ebx
  int ResolverDataFilename; // edi
  HANDLE v5; // rax
  void *v6; // rsi
  DWORD FileSize; // r14d
  signed int LastError; // eax
  _QWORD *v9; // rax
  __int64 v10; // r8
  DWORD FileSizeHigh; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE v13; // [rsp+48h] [rbp-C0h]
  LPCWSTR lpFileName; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v15; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+68h] [rbp-A0h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp-98h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v19[88]; // [rsp+B0h] [rbp-58h] BYREF
  unsigned int v20; // [rsp+11Ch] [rbp+14h]
  unsigned __int64 v21; // [rsp+120h] [rbp+18h] BYREF
  DWORD v22; // [rsp+128h] [rbp+20h]

  v20 = HIDWORD(a2);
  v2 = a2;
  FileSizeHigh = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
  ResolverDataFilename = PerfDiagDm::GetResolverDataFilename((__int64)&lpFileName, a1);
  if ( ResolverDataFilename >= 0 )
  {
    if ( PerfDiagDm::CPerfDiagSecurityAttribute::Init((PerfDiagDm::CPerfDiagSecurityAttribute *)&SecurityAttributes) >= 0 )
    {
      v5 = CreateFileW(lpFileName, 0xC0000000, 3u, &SecurityAttributes, 3u, 0, 0);
      v6 = v5;
      v13 = v5;
      if ( v5 == (HANDLE)-1LL )
      {
        ResolverDataFilename = 1;
      }
      else
      {
        ResolverDataFilename = -2147467259;
        FileSize = GetFileSize(v5, &FileSizeHigh);
        v22 = FileSize;
        if ( FileSize - 1 <= 0xFFFFFFFD )
        {
          PerfDiagShared::Serializer::CStringInterner::CStringInterner((PerfDiagShared::Serializer::CStringInterner *)v19);
          v15 = 0;
          v16 = 0;
          memset(&Overlapped, 0, sizeof(Overlapped));
          if ( LockFileEx(v6, 2u, 0, FileSize, FileSizeHigh, &Overlapped) )
          {
            ResolverDataFilename = PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCauseDriver>>(
                                     v6,
                                     (struct PerfDiagShared::Serializer::CStringInterner *)v19);
            if ( ResolverDataFilename >= 0 )
            {
              v21 = __PAIR64__(v20, v2);
              v9 = (_QWORD *)std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PerfDiagOutput::CRootCauseDriver>>>,PerfDiagDm::CRootCauseOlderPredicate<PerfDiagOutput::CRootCauseDriver>>(
                               &v21,
                               v15,
                               *((_QWORD *)&v15 + 1),
                               __PAIR64__(v20, v2));
              std::vector<PerfDiagOutput::CRootCauseDriver>::erase(&v15, &v21, *v9, v10);
              if ( SetFilePointer(v6, 0, 0, 0) != -1 )
              {
                SetEndOfFile(v6);
                ResolverDataFilename = PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCauseDriver>>(v6);
              }
            }
          }
          else
          {
            LastError = GetLastError();
            ResolverDataFilename = LastError;
            if ( LastError > 0 )
              ResolverDataFilename = (unsigned __int16)LastError | 0x80070000;
          }
          std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>>>>(&v15);
          PerfDiagShared::Serializer::CStringInterner::~CStringInterner((PerfDiagShared::Serializer::CStringInterner *)v19);
        }
        UnlockFile(v6, 0, 0, FileSize, FileSizeHigh);
        CloseHandle(v6);
      }
    }
    else
    {
      ResolverDataFilename = -2147467259;
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
  PerfDiagDm::CPerfDiagSecurityAttribute::~CPerfDiagSecurityAttribute((PerfDiagDm::CPerfDiagSecurityAttribute *)&SecurityAttributes);
  return (unsigned int)ResolverDataFilename;
}

```

## disassembly

```asm
0x180043aac  mov     [rsp+arg_0], rbx
0x180043ab1  mov     [rsp+arg_8], rdx
0x180043ab6  push    rsi
0x180043ab7  push    rdi
0x180043ab8  push    r14
0x180043aba  sub     rsp, 0F0h
0x180043ac1  mov     rbx, rdx
0x180043ac4  mov     rdi, rcx
0x180043ac7  mov     [rsp+108h+FileSizeHigh], 0
0x180043acf  xorps   xmm0, xmm0
0x180043ad2  xor     eax, eax
0x180043ad4  movups  xmmword ptr [rsp+108h+SecurityAttributes.nLength], xmm0
0x180043ad9  mov     qword ptr [rsp+108h+SecurityAttributes.bInheritHandle], rax
0x180043ae1  lea     rcx, [rsp+108h+lpFileName]
0x180043ae6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180043aeb  nop
0x180043aec  mov     rdx, rdi
0x180043aef  lea     rcx, [rsp+108h+lpFileName]
0x180043af4  call    ?GetResolverDataFilename@PerfDiagDm@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBU_GUID@@@Z; PerfDiagDm::GetResolverDataFilename(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,_GUID const &)
0x180043af9  mov     edi, eax
0x180043afb  test    eax, eax
0x180043afd  js      loc_180043CEB
0x180043b03  lea     rcx, [rsp+108h+SecurityAttributes]; this
0x180043b08  call    ?Init@CPerfDiagSecurityAttribute@PerfDiagDm@@QEAAJXZ; PerfDiagDm::CPerfDiagSecurityAttribute::Init(void)
0x180043b0d  test    eax, eax
0x180043b0f  jns     short loc_180043B1B
0x180043b11  mov     edi, 80004005h
0x180043b16  jmp     loc_180043CEB
0x180043b1b  mov     [rsp+108h+hTemplateFile], 0; hTemplateFile
0x180043b24  mov     [rsp+108h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180043b2c  mov     r8d, 3; dwShareMode
0x180043b32  mov     [rsp+108h+dwCreationDisposition], r8d; dwCreationDisposition
0x180043b37  lea     r9, [rsp+108h+SecurityAttributes]; lpSecurityAttributes
0x180043b3c  mov     edx, 0C0000000h; dwDesiredAccess
0x180043b41  mov     rcx, [rsp+108h+lpFileName]; lpFileName
0x180043b46  call    cs:__imp_CreateFileW
0x180043b4c  mov     rsi, rax
0x180043b4f  mov     [rsp+108h+var_C0], rax
0x180043b54  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180043b58  jnz     short loc_180043B62
0x180043b5a  lea     edi, [rax+2]
0x180043b5d  jmp     loc_180043CEB
0x180043b62  mov     edi, 80004005h
0x180043b67  lea     rdx, [rsp+108h+FileSizeHigh]; lpFileSizeHigh
0x180043b6c  mov     rcx, rsi; hFile
0x180043b6f  call    cs:__imp_GetFileSize
0x180043b75  mov     r14d, eax
0x180043b78  mov     [rsp+108h+arg_18], eax
0x180043b7f  lea     ecx, [rax-1]
0x180043b82  cmp     ecx, 0FFFFFFFDh
0x180043b85  ja      loc_180043CC8
0x180043b8b  lea     rcx, [rsp+108h+var_58]; this
0x180043b93  call    ??0CStringInterner@Serializer@PerfDiagShared@@QEAA@XZ; PerfDiagShared::Serializer::CStringInterner::CStringInterner(void)
0x180043b98  nop
0x180043b99  xorps   xmm0, xmm0
0x180043b9c  movdqu  [rsp+108h+var_B0], xmm0
0x180043ba2  mov     [rsp+108h+var_A0], 0
0x180043bab  movups  xmmword ptr [rsp+108h+Overlapped.Internal], xmm0
0x180043bb3  movups  xmmword ptr [rsp+108h+Overlapped.10h], xmm0
0x180043bbb  lea     rax, [rsp+108h+Overlapped]
0x180043bc3  mov     qword ptr [rsp+108h+dwFlagsAndAttributes], rax; lpOverlapped
0x180043bc8  mov     eax, [rsp+108h+FileSizeHigh]
0x180043bcc  mov     [rsp+108h+dwCreationDisposition], eax; nNumberOfBytesToLockHigh
0x180043bd0  mov     r9d, r14d; nNumberOfBytesToLockLow
0x180043bd3  xor     r8d, r8d; dwReserved
0x180043bd6  lea     edx, [r8+2]; dwFlags
0x180043bda  mov     rcx, rsi; hFile
0x180043bdd  call    cs:__imp_LockFileEx
0x180043be3  test    eax, eax
0x180043be5  jnz     short loc_180043C1A
0x180043be7  call    cs:__imp_GetLastError
0x180043bed  mov     edi, eax
0x180043bef  test    eax, eax
0x180043bf1  jle     short loc_180043BFC
0x180043bf3  movzx   edi, ax
0x180043bf6  or      edi, 80070000h
0x180043bfc  lea     rcx, [rsp+108h+var_B0]; void *
0x180043c01  call    ??1?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>(void)
0x180043c06  nop
0x180043c07  lea     rcx, [rsp+108h+var_58]; this
0x180043c0f  call    ??1CStringInterner@Serializer@PerfDiagShared@@QEAA@XZ; PerfDiagShared::Serializer::CStringInterner::~CStringInterner(void)
0x180043c14  nop
0x180043c15  jmp     loc_180043CC8
0x180043c1a  lea     r8, [rsp+108h+var_B0]
0x180043c1f  lea     rdx, [rsp+108h+var_58]; struct PerfDiagShared::Serializer::CStringInterner *
0x180043c27  mov     rcx, rsi; hFile
0x180043c2a  call    ??$ReadFromFile@V?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Z; PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCauseDriver>>(void *,PerfDiagShared::Serializer::CStringInterner &,std::vector<PerfDiagOutput::CRootCauseDriver> &)
0x180043c2f  mov     edi, eax
0x180043c31  test    eax, eax
0x180043c33  js      short loc_180043CAF
0x180043c35  mov     eax, dword ptr [rsp+108h+arg_8+4]
0x180043c3c  mov     dword ptr [rsp+108h+arg_10], ebx
0x180043c43  mov     dword ptr [rsp+108h+arg_10+4], eax
0x180043c4a  mov     r9, [rsp+108h+arg_10]
0x180043c52  mov     r8, qword ptr [rsp+108h+var_B0+8]
0x180043c57  mov     rdx, qword ptr [rsp+108h+var_B0]
0x180043c5c  lea     rcx, [rsp+108h+arg_10]
0x180043c64  call    ??$remove_if@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@std@@V?$CRootCauseOlderPredicate@UCRootCauseDriver@PerfDiagOutput@@@PerfDiagDm@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@0@V10@0V?$CRootCauseOlderPredicate@UCRootCauseDriver@PerfDiagOutput@@@PerfDiagDm@@@Z; std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PerfDiagOutput::CRootCauseDriver>>>,PerfDiagDm::CRootCauseOlderPredicate<PerfDiagOutput::CRootCauseDriver>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PerfDiagOutput::CRootCauseDriver>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PerfDiagOutput::CRootCauseDriver>>>,PerfDiagDm::CRootCauseOlderPredicate<PerfDiagOutput::CRootCauseDriver>)
0x180043c69  mov     r9, r8
0x180043c6c  mov     r8, [rax]
0x180043c6f  lea     rdx, [rsp+108h+arg_10]
0x180043c77  lea     rcx, [rsp+108h+var_B0]
0x180043c7c  call    ?erase@?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@2@0@Z; std::vector<PerfDiagOutput::CRootCauseDriver>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<PerfDiagOutput::CRootCauseDriver>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<PerfDiagOutput::CRootCauseDriver>>>)
0x180043c81  xor     r9d, r9d; dwMoveMethod
0x180043c84  xor     r8d, r8d; lpDistanceToMoveHigh
0x180043c87  xor     edx, edx; lDistanceToMove
0x180043c89  mov     rcx, rsi; hFile
0x180043c8c  call    cs:__imp_SetFilePointer
0x180043c92  cmp     eax, 0FFFFFFFFh
0x180043c95  jz      short loc_180043CAF
0x180043c97  mov     rcx, rsi; hFile
0x180043c9a  call    cs:__imp_SetEndOfFile
0x180043ca0  lea     rdx, [rsp+108h+var_B0]
0x180043ca5  mov     rcx, rsi; hFile
0x180043ca8  call    ??$WriteToFile@V?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEBV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Z; PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCauseDriver>>(void *,std::vector<PerfDiagOutput::CRootCauseDriver> const &)
0x180043cad  mov     edi, eax
0x180043caf  lea     rcx, [rsp+108h+var_B0]; void *
0x180043cb4  call    ??1?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>(void)
0x180043cb9  nop
0x180043cba  lea     rcx, [rsp+108h+var_58]; this
0x180043cc2  call    ??1CStringInterner@Serializer@PerfDiagShared@@QEAA@XZ; PerfDiagShared::Serializer::CStringInterner::~CStringInterner(void)
0x180043cc7  nop
0x180043cc8  mov     eax, [rsp+108h+FileSizeHigh]
0x180043ccc  mov     [rsp+108h+dwCreationDisposition], eax; nNumberOfBytesToUnlockHigh
0x180043cd0  mov     r9d, r14d; nNumberOfBytesToUnlockLow
0x180043cd3  xor     r8d, r8d; dwFileOffsetHigh
0x180043cd6  xor     edx, edx; dwFileOffsetLow
0x180043cd8  mov     rcx, rsi; hFile
0x180043cdb  call    cs:__imp_UnlockFile
0x180043ce1  mov     rcx, rsi; hObject
0x180043ce4  call    cs:__imp_CloseHandle
0x180043cea  nop
0x180043ceb  mov     rcx, [rsp+108h+lpFileName]
0x180043cf0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180043cf4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180043cf9  nop
0x180043cfa  lea     rcx, [rsp+108h+SecurityAttributes]; this
0x180043cff  call    ??1CPerfDiagSecurityAttribute@PerfDiagDm@@QEAA@XZ; PerfDiagDm::CPerfDiagSecurityAttribute::~CPerfDiagSecurityAttribute(void)
0x180043d04  mov     eax, edi
0x180043d06  mov     rbx, [rsp+108h+arg_0]
0x180043d0e  add     rsp, 0F0h
0x180043d15  pop     r14
0x180043d17  pop     rdi
0x180043d18  pop     rsi
0x180043d19  retn
0x180043d1a  mov     edi, dword ptr [rsp+108h+arg_10]
0x180043d21  mov     rsi, [rsp+108h+var_C0]
0x180043d26  mov     r14d, [rsp+108h+arg_18]
0x180043d2e  jmp     short loc_180043CC8
0x180043d30  jmp     short loc_180043D1A
0x180043d32  jmp     short loc_180043D1A
```
