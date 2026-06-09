# PerfDiagDm::PurgeDegradations<PerfDiagOutput::CRootCause>(_GUID const &,_FILETIME)

- ea: `0x180043150`
- end: `0x1800433d9`
- name: `??$PurgeDegradations@VCRootCause@PerfDiagOutput@@@PerfDiagDm@@YAJAEBU_GUID@@U_FILETIME@@@Z`
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
- `0x180043150`
- `0x180043d3c`
- `0x1800b270c`
- `0x1800b2c0c`
- `0x1800b4960`
- `0x1800b58e4`
- `0x1800bb3c4`
- `0x1800be2f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004328b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004328b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180043213`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180043213`
- `api-ms-win-core-file-l1-1-0!UnlockFile` at `0x18004337f`
- `api-ms-win-core-file-l1-1-0!UnlockFile` at `0x18004337f`
- `api-ms-win-core-file-l1-1-0!LockFileEx` at `0x180043281`
- `api-ms-win-core-file-l1-1-0!LockFileEx` at `0x180043281`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180043330`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180043330`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18004333e`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18004333e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800431ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800431ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043388`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043388`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PerfDiagDm::PurgeDegradations<PerfDiagOutput::CRootCause>(unsigned int *a1, __int64 a2)
{
  unsigned int v2; // ebx
  int ResolverDataFilename; // edi
  HANDLE v5; // rax
  HANDLE v6; // rsi
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
  ATL::CAtlException *v18; // [rsp+88h] [rbp-80h] BYREF
  _OVERLAPPED Overlapped; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v20[88]; // [rsp+B0h] [rbp-58h] BYREF
  unsigned int v21; // [rsp+11Ch] [rbp+14h]
  unsigned __int64 v22; // [rsp+120h] [rbp+18h] BYREF
  DWORD v23; // [rsp+128h] [rbp+20h]

  v21 = HIDWORD(a2);
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
        v23 = FileSize;
        if ( FileSize - 1 <= 0xFFFFFFFD )
        {
          try
          {
            PerfDiagShared::Serializer::CStringInterner::CStringInterner((PerfDiagShared::Serializer::CStringInterner *)v20);
            v15 = 0;
            v16 = 0;
            memset(&Overlapped, 0, sizeof(Overlapped));
            if ( LockFileEx(v6, 2u, 0, FileSize, FileSizeHigh, &Overlapped) )
            {
              ResolverDataFilename = PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCause>>(
                                       v6,
                                       (struct PerfDiagShared::Serializer::CStringInterner *)v20);
              if ( ResolverDataFilename >= 0 )
              {
                v22 = __PAIR64__(v21, v2);
                v9 = (_QWORD *)std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PerfDiagOutput::CRootCause>>>,PerfDiagDm::CRootCauseOlderPredicate<PerfDiagOutput::CRootCause>>(
                                 &v22,
                                 v15,
                                 *((_QWORD *)&v15 + 1),
                                 __PAIR64__(v21, v2));
                std::vector<PerfDiagOutput::CRootCause>::erase(&v15, &v22, *v9, v10);
                if ( SetFilePointer(v6, 0, 0, 0) != -1 )
                {
                  SetEndOfFile(v6);
                  ResolverDataFilename = PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCause>>(v6);
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
            PerfDiagShared::Serializer::CStringInterner::~CStringInterner((PerfDiagShared::Serializer::CStringInterner *)v20);
          }
          catch ( std::bad_alloc )
          {
            LODWORD(v22) = -2147024882;
            ResolverDataFilename = -2147024882;
            v6 = v13;
            FileSize = v23;
          }
          catch ( ATL::CAtlException *v18 )
          {
            LODWORD(v22) = *(_DWORD *)v18;
            ResolverDataFilename = v22;
            v6 = v13;
            FileSize = v23;
          }
          catch ( std::out_of_range )
          {
            LODWORD(v22) = -2147418113;
            ResolverDataFilename = -2147418113;
            v6 = v13;
            FileSize = v23;
          }
          catch ( ... )
          {
            UnlockFile(v13, 0, 0, v23, FileSizeHigh);
            CloseHandle(v13);
            throw;
          }
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
0x180043150  mov     [rsp+arg_0], rbx
0x180043155  mov     [rsp+arg_8], rdx
0x18004315a  push    rsi
0x18004315b  push    rdi
0x18004315c  push    r14
0x18004315e  sub     rsp, 0F0h
0x180043165  mov     rbx, rdx
0x180043168  mov     rdi, rcx
0x18004316b  mov     [rsp+108h+FileSizeHigh], 0
0x180043173  xorps   xmm0, xmm0
0x180043176  xor     eax, eax
0x180043178  movups  xmmword ptr [rsp+108h+SecurityAttributes.nLength], xmm0
0x18004317d  mov     qword ptr [rsp+108h+SecurityAttributes.bInheritHandle], rax
0x180043185  lea     rcx, [rsp+108h+lpFileName]
0x18004318a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004318f  nop
0x180043190  mov     rdx, rdi
0x180043193  lea     rcx, [rsp+108h+lpFileName]
0x180043198  call    ?GetResolverDataFilename@PerfDiagDm@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBU_GUID@@@Z; PerfDiagDm::GetResolverDataFilename(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,_GUID const &)
0x18004319d  mov     edi, eax
0x18004319f  test    eax, eax
0x1800431a1  js      loc_18004338F
0x1800431a7  lea     rcx, [rsp+108h+SecurityAttributes]; this
0x1800431ac  call    ?Init@CPerfDiagSecurityAttribute@PerfDiagDm@@QEAAJXZ; PerfDiagDm::CPerfDiagSecurityAttribute::Init(void)
0x1800431b1  test    eax, eax
0x1800431b3  jns     short loc_1800431BF
0x1800431b5  mov     edi, 80004005h
0x1800431ba  jmp     loc_18004338F
0x1800431bf  mov     [rsp+108h+hTemplateFile], 0; hTemplateFile
0x1800431c8  mov     [rsp+108h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800431d0  mov     r8d, 3; dwShareMode
0x1800431d6  mov     [rsp+108h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800431db  lea     r9, [rsp+108h+SecurityAttributes]; lpSecurityAttributes
0x1800431e0  mov     edx, 0C0000000h; dwDesiredAccess
0x1800431e5  mov     rcx, [rsp+108h+lpFileName]; lpFileName
0x1800431ea  call    cs:__imp_CreateFileW
0x1800431f0  mov     rsi, rax
0x1800431f3  mov     [rsp+108h+var_C0], rax
0x1800431f8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800431fc  jnz     short loc_180043206
0x1800431fe  lea     edi, [rax+2]
0x180043201  jmp     loc_18004338F
0x180043206  mov     edi, 80004005h
0x18004320b  lea     rdx, [rsp+108h+FileSizeHigh]; lpFileSizeHigh
0x180043210  mov     rcx, rsi; hFile
0x180043213  call    cs:__imp_GetFileSize
0x180043219  mov     r14d, eax
0x18004321c  mov     [rsp+108h+arg_18], eax
0x180043223  lea     ecx, [rax-1]
0x180043226  cmp     ecx, 0FFFFFFFDh
0x180043229  ja      loc_18004336C
0x18004322f  lea     rcx, [rsp+108h+var_58]; this
0x180043237  call    ??0CStringInterner@Serializer@PerfDiagShared@@QEAA@XZ; PerfDiagShared::Serializer::CStringInterner::CStringInterner(void)
0x18004323c  nop
0x18004323d  xorps   xmm0, xmm0
0x180043240  movdqu  [rsp+108h+var_B0], xmm0
0x180043246  mov     [rsp+108h+var_A0], 0
0x18004324f  movups  xmmword ptr [rsp+108h+Overlapped.Internal], xmm0
0x180043257  movups  xmmword ptr [rsp+108h+Overlapped.10h], xmm0
0x18004325f  lea     rax, [rsp+108h+Overlapped]
0x180043267  mov     qword ptr [rsp+108h+dwFlagsAndAttributes], rax; lpOverlapped
0x18004326c  mov     eax, [rsp+108h+FileSizeHigh]
0x180043270  mov     [rsp+108h+dwCreationDisposition], eax; nNumberOfBytesToLockHigh
0x180043274  mov     r9d, r14d; nNumberOfBytesToLockLow
0x180043277  xor     r8d, r8d; dwReserved
0x18004327a  lea     edx, [r8+2]; dwFlags
0x18004327e  mov     rcx, rsi; hFile
0x180043281  call    cs:__imp_LockFileEx
0x180043287  test    eax, eax
0x180043289  jnz     short loc_1800432BE
0x18004328b  call    cs:__imp_GetLastError
0x180043291  mov     edi, eax
0x180043293  test    eax, eax
0x180043295  jle     short loc_1800432A0
0x180043297  movzx   edi, ax
0x18004329a  or      edi, 80070000h
0x1800432a0  lea     rcx, [rsp+108h+var_B0]; void *
0x1800432a5  call    ??1?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>(void)
0x1800432aa  nop
0x1800432ab  lea     rcx, [rsp+108h+var_58]; this
0x1800432b3  call    ??1CStringInterner@Serializer@PerfDiagShared@@QEAA@XZ; PerfDiagShared::Serializer::CStringInterner::~CStringInterner(void)
0x1800432b8  nop
0x1800432b9  jmp     loc_18004336C
0x1800432be  lea     r8, [rsp+108h+var_B0]
0x1800432c3  lea     rdx, [rsp+108h+var_58]; struct PerfDiagShared::Serializer::CStringInterner *
0x1800432cb  mov     rcx, rsi; hFile
0x1800432ce  call    ??$ReadFromFile@V?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Z; PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCause>>(void *,PerfDiagShared::Serializer::CStringInterner &,std::vector<PerfDiagOutput::CRootCause> &)
0x1800432d3  mov     edi, eax
0x1800432d5  test    eax, eax
0x1800432d7  js      short loc_180043353
0x1800432d9  mov     eax, dword ptr [rsp+108h+arg_8+4]
0x1800432e0  mov     dword ptr [rsp+108h+arg_10], ebx
0x1800432e7  mov     dword ptr [rsp+108h+arg_10+4], eax
0x1800432ee  mov     r9, [rsp+108h+arg_10]
0x1800432f6  mov     r8, qword ptr [rsp+108h+var_B0+8]
0x1800432fb  mov     rdx, qword ptr [rsp+108h+var_B0]
0x180043300  lea     rcx, [rsp+108h+arg_10]
0x180043308  call    ??$remove_if@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCRootCause@PerfDiagOutput@@@std@@@std@@@std@@V?$CRootCauseOlderPredicate@VCRootCause@PerfDiagOutput@@@PerfDiagDm@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCRootCause@PerfDiagOutput@@@std@@@std@@@0@V10@0V?$CRootCauseOlderPredicate@VCRootCause@PerfDiagOutput@@@PerfDiagDm@@@Z; std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PerfDiagOutput::CRootCause>>>,PerfDiagDm::CRootCauseOlderPredicate<PerfDiagOutput::CRootCause>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PerfDiagOutput::CRootCause>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<PerfDiagOutput::CRootCause>>>,PerfDiagDm::CRootCauseOlderPredicate<PerfDiagOutput::CRootCause>)
0x18004330d  mov     r9, r8
0x180043310  mov     r8, [rax]
0x180043313  lea     rdx, [rsp+108h+arg_10]
0x18004331b  lea     rcx, [rsp+108h+var_B0]
0x180043320  call    ?erase@?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCRootCause@PerfDiagOutput@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCRootCause@PerfDiagOutput@@@std@@@std@@@2@0@Z; std::vector<PerfDiagOutput::CRootCause>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<PerfDiagOutput::CRootCause>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<PerfDiagOutput::CRootCause>>>)
0x180043325  xor     r9d, r9d; dwMoveMethod
0x180043328  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004332b  xor     edx, edx; lDistanceToMove
0x18004332d  mov     rcx, rsi; hFile
0x180043330  call    cs:__imp_SetFilePointer
0x180043336  cmp     eax, 0FFFFFFFFh
0x180043339  jz      short loc_180043353
0x18004333b  mov     rcx, rsi; hFile
0x18004333e  call    cs:__imp_SetEndOfFile
0x180043344  lea     rdx, [rsp+108h+var_B0]
0x180043349  mov     rcx, rsi; hFile
0x18004334c  call    ??$WriteToFile@V?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Z; PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCause>>(void *,std::vector<PerfDiagOutput::CRootCause> const &)
0x180043351  mov     edi, eax
0x180043353  lea     rcx, [rsp+108h+var_B0]; void *
0x180043358  call    ??1?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>(void)
0x18004335d  nop
0x18004335e  lea     rcx, [rsp+108h+var_58]; this
0x180043366  call    ??1CStringInterner@Serializer@PerfDiagShared@@QEAA@XZ; PerfDiagShared::Serializer::CStringInterner::~CStringInterner(void)
0x18004336b  nop
0x18004336c  mov     eax, [rsp+108h+FileSizeHigh]
0x180043370  mov     [rsp+108h+dwCreationDisposition], eax; nNumberOfBytesToUnlockHigh
0x180043374  mov     r9d, r14d; nNumberOfBytesToUnlockLow
0x180043377  xor     r8d, r8d; dwFileOffsetHigh
0x18004337a  xor     edx, edx; dwFileOffsetLow
0x18004337c  mov     rcx, rsi; hFile
0x18004337f  call    cs:__imp_UnlockFile
0x180043385  mov     rcx, rsi; hObject
0x180043388  call    cs:__imp_CloseHandle
0x18004338e  nop
0x18004338f  mov     rcx, [rsp+108h+lpFileName]
0x180043394  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180043398  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004339d  nop
0x18004339e  lea     rcx, [rsp+108h+SecurityAttributes]; this
0x1800433a3  call    ??1CPerfDiagSecurityAttribute@PerfDiagDm@@QEAA@XZ; PerfDiagDm::CPerfDiagSecurityAttribute::~CPerfDiagSecurityAttribute(void)
0x1800433a8  mov     eax, edi
0x1800433aa  mov     rbx, [rsp+108h+arg_0]
0x1800433b2  add     rsp, 0F0h
0x1800433b9  pop     r14
0x1800433bb  pop     rdi
0x1800433bc  pop     rsi
0x1800433bd  retn
0x1800433be  mov     edi, dword ptr [rsp+108h+arg_10]
0x1800433c5  mov     rsi, [rsp+108h+var_C0]
0x1800433ca  mov     r14d, [rsp+108h+arg_18]
0x1800433d2  jmp     short loc_18004336C
0x1800433d4  jmp     short loc_1800433BE
0x1800433d6  jmp     short loc_1800433BE
```
