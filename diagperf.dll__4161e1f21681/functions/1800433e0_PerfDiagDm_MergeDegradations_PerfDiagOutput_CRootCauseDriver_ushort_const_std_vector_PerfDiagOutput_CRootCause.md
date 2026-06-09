# PerfDiagDm::MergeDegradations<PerfDiagOutput::CRootCauseDriver>(ushort const *,std::vector<PerfDiagOutput::CRootCauseDriver,std::allocator<PerfDiagOutput::CRootCauseDriver>> &,PerfDiagShared::Serializer::CStringInterner &)

- ea: `0x1800433e0`
- end: `0x180043750`
- name: `??$MergeDegradations@UCRootCauseDriver@PerfDiagOutput@@@PerfDiagDm@@YAJPEBGAEAV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@AEAVCStringInterner@Serializer@PerfDiagShared@@@Z`
- size: `880`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800b736c`

## callees

- `0x18001f3c0`
- `0x1800433e0`
- `0x180043d3c`
- `0x180043d68`
- `0x1800b4960`
- `0x1800b74d8`
- `0x1800b77c0`
- `0x1800b8d7c`
- `0x1800ba1d4`
- `0x1800be9e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436f8`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180043489`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180043489`
- `api-ms-win-core-file-l1-1-0!UnlockFile` at `0x1800435f0`
- `api-ms-win-core-file-l1-1-0!UnlockFile` at `0x1800435f0`
- `api-ms-win-core-file-l1-1-0!LockFileEx` at `0x1800434fe`
- `api-ms-win-core-file-l1-1-0!LockFileEx` at `0x1800434fe`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004359f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004359f`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800435ad`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800435ad`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043464`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800436e9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043464`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800436e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800435f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043724`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800435f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043724`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall PerfDiagDm::MergeDegradations<PerfDiagOutput::CRootCauseDriver>(
        LPCWSTR lpFileName,
        __int64 a2,
        struct PerfDiagShared::Serializer::CStringInterner *a3)
{
  HANDLE v6; // rax
  void *v7; // r14
  signed int v8; // esi
  DWORD FileSize; // ebx
  signed int LastError; // eax
  const struct PerfDiagOutput::CRootCauseDriver *v11; // r8
  struct PerfDiagOutput::CRootCauseDriver *v12; // rbx
  PerfDiagDm *v13; // r13
  PerfDiagDm *v14; // rdi
  PerfDiagDm *i; // r15
  __int128 v16; // xmm1
  __int128 v17; // xmm2
  __int128 v18; // xmm3
  __int128 v19; // xmm4
  __int64 v20; // xmm5_8
  HANDLE v21; // rax
  void *v22; // rdi
  signed int v23; // eax
  int v24; // ebx
  DWORD FileSizeHigh; // [rsp+40h] [rbp-B8h] BYREF
  DWORD nNumberOfBytesToUnlockLow; // [rsp+44h] [rbp-B4h]
  HANDLE v27; // [rsp+48h] [rbp-B0h]
  PerfDiagDm *v28[2]; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-98h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-90h] BYREF
  struct PerfDiagOutput::CRootCauseDriver *v31[4]; // [rsp+80h] [rbp-78h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+A0h] [rbp-58h] BYREF

  FileSizeHigh = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( PerfDiagDm::CPerfDiagSecurityAttribute::Init((PerfDiagDm::CPerfDiagSecurityAttribute *)&SecurityAttributes) >= 0 )
  {
    v6 = CreateFileW(lpFileName, 0xC0000000, 3u, &SecurityAttributes, 3u, 0, 0);
    v7 = v6;
    v27 = v6;
    if ( v6 == (HANDLE)-1LL )
      goto LABEL_15;
    v8 = -2147467259;
    FileSize = GetFileSize(v6, &FileSizeHigh);
    nNumberOfBytesToUnlockLow = FileSize;
    if ( FileSize - 1 <= 0xFFFFFFFD )
    {
      *(_OWORD *)v28 = 0;
      v29 = 0;
      std::vector<PerfDiagOutput::CRootCauseDriver>::vector<PerfDiagOutput::CRootCauseDriver>(v31, a2);
      memset(&Overlapped, 0, sizeof(Overlapped));
      if ( LockFileEx(v7, 2u, 0, FileSize, FileSizeHigh, &Overlapped) )
      {
        v8 = PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCauseDriver>>(v7, a3);
        if ( v8 >= 0 )
        {
          v12 = v31[0];
          v13 = v28[1];
          v14 = v28[0];
          while ( v12 != v31[1] )
          {
            for ( i = v14; i != v13; i = (PerfDiagDm *)((char *)i + 88) )
            {
              if ( PerfDiagDm::RootCauseIsEqual(i, v12, v11) )
                break;
            }
            if ( i == v13 )
            {
              std::vector<PerfDiagOutput::CRootCauseDriver>::push_back(v28, v12);
              v13 = v28[1];
              v14 = v28[0];
            }
            else if ( *((_DWORD *)i + 4) <= *((_DWORD *)v12 + 4) )
            {
              v16 = *((_OWORD *)v12 + 1);
              v17 = *((_OWORD *)v12 + 2);
              v18 = *((_OWORD *)v12 + 3);
              v19 = *((_OWORD *)v12 + 4);
              v20 = *((_QWORD *)v12 + 10);
              *(_OWORD *)i = *(_OWORD *)v12;
              *((_OWORD *)i + 1) = v16;
              *((_OWORD *)i + 2) = v17;
              *((_OWORD *)i + 3) = v18;
              *((_OWORD *)i + 4) = v19;
              *((_QWORD *)i + 10) = v20;
            }
            v12 = (struct PerfDiagOutput::CRootCauseDriver *)((char *)v12 + 88);
          }
          std::_Sort<PerfDiagOutput::CRootCauseDriver *,__int64,bool (*)(PerfDiagOutput::CRootCauseDriver const &,PerfDiagOutput::CRootCauseDriver const &)>(
            v14,
            v13,
            0x2E8BA2E8BA2E8BA3LL * ((v13 - v14) >> 3));
          if ( SetFilePointer(v7, 0, 0, 0) != -1 )
          {
            SetEndOfFile(v7);
            v8 = PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCauseDriver>>(v7);
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
      }
      std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>>>>(v31);
      std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>>>>(v28);
    }
    UnlockFile(v7, 0, 0, nNumberOfBytesToUnlockLow, FileSizeHigh);
    CloseHandle(v7);
    if ( v8 < 0 )
    {
LABEL_15:
      if ( lpFileName )
      {
        v21 = CreateFileW(lpFileName, 0x40000000u, 1u, &SecurityAttributes, 2u, 0, 0);
        v22 = v21;
        if ( v21 == (HANDLE)-1LL )
        {
          v23 = GetLastError();
          v8 = v23;
          if ( v23 > 0 )
            v8 = (unsigned __int16)v23 | 0x80070000;
        }
        else
        {
          v24 = PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCauseDriver>>(v21);
          CloseHandle(v22);
          v8 = 0;
          if ( v24 < 0 )
            v8 = v24;
        }
      }
      else
      {
        v8 = -2147024809;
      }
    }
    PerfDiagDm::CPerfDiagSecurityAttribute::~CPerfDiagSecurityAttribute((PerfDiagDm::CPerfDiagSecurityAttribute *)&SecurityAttributes);
    return (unsigned int)v8;
  }
  else
  {
    PerfDiagDm::CPerfDiagSecurityAttribute::~CPerfDiagSecurityAttribute((PerfDiagDm::CPerfDiagSecurityAttribute *)&SecurityAttributes);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x1800433e0  mov     [rsp+arg_8], rdx
0x1800433e5  mov     [rsp+arg_0], rcx
0x1800433ea  push    rbx
0x1800433eb  push    rsi
0x1800433ec  push    rdi
0x1800433ed  push    r12
0x1800433ef  push    r13
0x1800433f1  push    r14
0x1800433f3  push    r15
0x1800433f5  sub     rsp, 0C0h
0x1800433fc  mov     rdi, r8
0x1800433ff  mov     r12, rcx
0x180043402  mov     [rsp+0F8h+FileSizeHigh], 0
0x18004340a  xorps   xmm0, xmm0
0x18004340d  xor     eax, eax
0x18004340f  movups  xmmword ptr [rsp+0F8h+SecurityAttributes.nLength], xmm0
0x180043414  mov     qword ptr [rsp+0F8h+SecurityAttributes.bInheritHandle], rax
0x180043419  lea     rcx, [rsp+0F8h+SecurityAttributes]; this
0x18004341e  call    ?Init@CPerfDiagSecurityAttribute@PerfDiagDm@@QEAAJXZ; PerfDiagDm::CPerfDiagSecurityAttribute::Init(void)
0x180043423  test    eax, eax
0x180043425  jns     short loc_18004343B
0x180043427  lea     rcx, [rsp+0F8h+SecurityAttributes]; this
0x18004342c  call    ??1CPerfDiagSecurityAttribute@PerfDiagDm@@QEAA@XZ; PerfDiagDm::CPerfDiagSecurityAttribute::~CPerfDiagSecurityAttribute(void)
0x180043431  mov     eax, 80004005h
0x180043436  jmp     loc_18004373D
0x18004343b  mov     [rsp+0F8h+hTemplateFile], 0; hTemplateFile
0x180043444  mov     [rsp+0F8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004344c  mov     r8d, 3; dwShareMode
0x180043452  mov     [rsp+0F8h+dwCreationDisposition], r8d; dwCreationDisposition
0x180043457  lea     r9, [rsp+0F8h+SecurityAttributes]; lpSecurityAttributes
0x18004345c  mov     edx, 0C0000000h; dwDesiredAccess
0x180043461  mov     rcx, r12; lpFileName
0x180043464  call    cs:__imp_CreateFileW
0x18004346a  mov     r14, rax
0x18004346d  mov     [rsp+0F8h+var_B0], rax
0x180043472  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180043476  jz      loc_180043607
0x18004347c  mov     esi, 80004005h
0x180043481  lea     rdx, [rsp+0F8h+FileSizeHigh]; lpFileSizeHigh
0x180043486  mov     rcx, rax; hFile
0x180043489  call    cs:__imp_GetFileSize
0x18004348f  mov     ebx, eax
0x180043491  mov     [rsp+0F8h+nNumberOfBytesToUnlockLow], eax
0x180043495  lea     ecx, [rax-1]
0x180043498  cmp     ecx, 0FFFFFFFDh
0x18004349b  ja      loc_1800435DB
0x1800434a1  xorps   xmm0, xmm0
0x1800434a4  movdqu  xmmword ptr [rsp+0F8h+var_A8], xmm0
0x1800434aa  mov     [rsp+0F8h+var_98], 0
0x1800434b3  mov     rdx, [rsp+0F8h+arg_8]
0x1800434bb  lea     rcx, [rsp+0F8h+var_78]
0x1800434c3  call    ??0?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<PerfDiagOutput::CRootCauseDriver>::vector<PerfDiagOutput::CRootCauseDriver>(std::vector<PerfDiagOutput::CRootCauseDriver> const &)
0x1800434c8  nop
0x1800434c9  xorps   xmm0, xmm0
0x1800434cc  movups  xmmword ptr [rsp+0F8h+Overlapped.Internal], xmm0
0x1800434d4  movups  xmmword ptr [rsp+0F8h+Overlapped.10h], xmm0
0x1800434dc  lea     rax, [rsp+0F8h+Overlapped]
0x1800434e4  mov     qword ptr [rsp+0F8h+dwFlagsAndAttributes], rax; lpOverlapped
0x1800434e9  mov     eax, [rsp+0F8h+FileSizeHigh]
0x1800434ed  mov     [rsp+0F8h+dwCreationDisposition], eax; nNumberOfBytesToLockHigh
0x1800434f1  mov     r9d, ebx; nNumberOfBytesToLockLow
0x1800434f4  xor     r8d, r8d; dwReserved
0x1800434f7  lea     edx, [r8+2]; dwFlags
0x1800434fb  mov     rcx, r14; hFile
0x1800434fe  call    cs:__imp_LockFileEx
0x180043504  test    eax, eax
0x180043506  jnz     short loc_18004353B
0x180043508  call    cs:__imp_GetLastError
0x18004350e  mov     esi, eax
0x180043510  test    eax, eax
0x180043512  jle     short loc_18004351D
0x180043514  movzx   esi, ax
0x180043517  or      esi, 80070000h
0x18004351d  lea     rcx, [rsp+0F8h+var_78]; void *
0x180043525  call    ??1?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>(void)
0x18004352a  nop
0x18004352b  lea     rcx, [rsp+0F8h+var_A8]; void *
0x180043530  call    ??1?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>(void)
0x180043535  nop
0x180043536  jmp     loc_1800435DB
0x18004353b  lea     r8, [rsp+0F8h+var_A8]
0x180043540  mov     rdx, rdi; struct PerfDiagShared::Serializer::CStringInterner *
0x180043543  mov     rcx, r14; hFile
0x180043546  call    ??$ReadFromFile@V?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Z; PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCauseDriver>>(void *,PerfDiagShared::Serializer::CStringInterner &,std::vector<PerfDiagOutput::CRootCauseDriver> &)
0x18004354b  mov     esi, eax
0x18004354d  test    eax, eax
0x18004354f  js      short loc_1800435C2
0x180043551  mov     rbx, [rsp+0F8h+var_78]
0x180043559  mov     r13, [rsp+0F8h+var_A8+8]
0x18004355e  mov     rdi, [rsp+0F8h+var_A8]
0x180043563  cmp     rbx, [rsp+0F8h+var_70]
0x18004356b  jnz     loc_18004361A
0x180043571  mov     r8, r13
0x180043574  sub     r8, rdi
0x180043577  sar     r8, 3
0x18004357b  mov     rax, 2E8BA2E8BA2E8BA3h
0x180043585  imul    r8, rax
0x180043589  mov     rdx, r13
0x18004358c  mov     rcx, rdi
0x18004358f  call    ??$_Sort@PEAUCRootCauseDriver@PerfDiagOutput@@_JP6A_NAEBU12@0@Z@std@@YAXPEAUCRootCauseDriver@PerfDiagOutput@@0_JP6A_NAEBU12@2@Z@Z; std::_Sort<PerfDiagOutput::CRootCauseDriver *,__int64,bool (*)(PerfDiagOutput::CRootCauseDriver const &,PerfDiagOutput::CRootCauseDriver const &)>(PerfDiagOutput::CRootCauseDriver *,PerfDiagOutput::CRootCauseDriver *,__int64,bool (*)(PerfDiagOutput::CRootCauseDriver const &,PerfDiagOutput::CRootCauseDriver const &))
0x180043594  xor     r9d, r9d; dwMoveMethod
0x180043597  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004359a  xor     edx, edx; lDistanceToMove
0x18004359c  mov     rcx, r14; hFile
0x18004359f  call    cs:__imp_SetFilePointer
0x1800435a5  cmp     eax, 0FFFFFFFFh
0x1800435a8  jz      short loc_1800435C2
0x1800435aa  mov     rcx, r14; hFile
0x1800435ad  call    cs:__imp_SetEndOfFile
0x1800435b3  lea     rdx, [rsp+0F8h+var_A8]
0x1800435b8  mov     rcx, r14; hFile
0x1800435bb  call    ??$WriteToFile@V?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEBV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Z; PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCauseDriver>>(void *,std::vector<PerfDiagOutput::CRootCauseDriver> const &)
0x1800435c0  mov     esi, eax
0x1800435c2  lea     rcx, [rsp+0F8h+var_78]; void *
0x1800435ca  call    ??1?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>(void)
0x1800435cf  nop
0x1800435d0  lea     rcx, [rsp+0F8h+var_A8]; void *
0x1800435d5  call    ??1?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>(void)
0x1800435da  nop
0x1800435db  mov     eax, [rsp+0F8h+FileSizeHigh]
0x1800435df  mov     [rsp+0F8h+dwCreationDisposition], eax; nNumberOfBytesToUnlockHigh
0x1800435e3  mov     r9d, [rsp+0F8h+nNumberOfBytesToUnlockLow]; nNumberOfBytesToUnlockLow
0x1800435e8  xor     r8d, r8d; dwFileOffsetHigh
0x1800435eb  xor     edx, edx; dwFileOffsetLow
0x1800435ed  mov     rcx, r14; hFile
0x1800435f0  call    cs:__imp_UnlockFile
0x1800435f6  mov     rcx, r14; hObject
0x1800435f9  call    cs:__imp_CloseHandle
0x1800435ff  test    esi, esi
0x180043601  jns     loc_180043731
0x180043607  test    r12, r12
0x18004360a  jnz     loc_1800436BD
0x180043610  mov     esi, 80070057h
0x180043615  jmp     loc_180043731
0x18004361a  mov     r15, rdi
0x18004361d  cmp     rdi, r13
0x180043620  jz      short loc_18004363A
0x180043622  mov     rdx, rbx; struct PerfDiagOutput::CRootCauseDriver *
0x180043625  mov     rcx, r15; this
0x180043628  call    ?RootCauseIsEqual@PerfDiagDm@@YA_NAEBUCRootCauseDriver@PerfDiagOutput@@0@Z; PerfDiagDm::RootCauseIsEqual(PerfDiagOutput::CRootCauseDriver const &,PerfDiagOutput::CRootCauseDriver const &)
0x18004362d  test    al, al
0x18004362f  jnz     short loc_18004363A
0x180043631  add     r15, 58h ; 'X'
0x180043635  cmp     r15, r13
0x180043638  jnz     short loc_180043622
0x18004363a  cmp     r15, r13
0x18004363d  jnz     short loc_180043658
0x18004363f  mov     rdx, rbx
0x180043642  lea     rcx, [rsp+0F8h+var_A8]
0x180043647  call    ?push_back@?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@QEAAXAEBUCRootCauseDriver@PerfDiagOutput@@@Z; std::vector<PerfDiagOutput::CRootCauseDriver>::push_back(PerfDiagOutput::CRootCauseDriver const &)
0x18004364c  mov     r13, [rsp+0F8h+var_A8+8]
0x180043651  mov     rdi, [rsp+0F8h+var_A8]
0x180043656  jmp     short loc_180043697
0x180043658  mov     eax, [rbx+10h]
0x18004365b  cmp     [r15+10h], eax
0x18004365f  ja      short loc_180043697
0x180043661  movups  xmm0, xmmword ptr [rbx]
0x180043664  movups  xmm1, xmmword ptr [rbx+10h]
0x180043668  movups  xmm2, xmmword ptr [rbx+20h]
0x18004366c  movups  xmm3, xmmword ptr [rbx+30h]
0x180043670  movups  xmm4, xmmword ptr [rbx+40h]
0x180043674  movsd   xmm5, qword ptr [rbx+50h]
0x180043679  movups  xmmword ptr [r15], xmm0
0x18004367d  movups  xmmword ptr [r15+10h], xmm1
0x180043682  movups  xmmword ptr [r15+20h], xmm2
0x180043687  movups  xmmword ptr [r15+30h], xmm3
0x18004368c  movups  xmmword ptr [r15+40h], xmm4
0x180043691  movsd   qword ptr [r15+50h], xmm5
0x180043697  add     rbx, 58h ; 'X'
0x18004369b  jmp     loc_180043563
0x1800436a0  mov     r12, [rsp+0F8h+arg_0]
0x1800436a8  mov     esi, [rsp+0F8h+arg_18]
0x1800436af  mov     r14, [rsp+0F8h+var_B0]
0x1800436b4  jmp     loc_1800435DB
0x1800436b9  jmp     short loc_1800436A0
0x1800436bb  jmp     short loc_1800436A0
0x1800436bd  mov     [rsp+0F8h+hTemplateFile], 0; hTemplateFile
0x1800436c6  mov     [rsp+0F8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800436ce  mov     [rsp+0F8h+dwCreationDisposition], 2; dwCreationDisposition
0x1800436d6  lea     r9, [rsp+0F8h+SecurityAttributes]; lpSecurityAttributes
0x1800436db  mov     edx, 40000000h; dwDesiredAccess
0x1800436e0  mov     r8d, 1; dwShareMode
0x1800436e6  mov     rcx, r12; lpFileName
0x1800436e9  call    cs:__imp_CreateFileW
0x1800436ef  mov     rdi, rax
0x1800436f2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800436f6  jnz     short loc_18004370F
0x1800436f8  call    cs:__imp_GetLastError
0x1800436fe  mov     esi, eax
0x180043700  test    eax, eax
0x180043702  jle     short loc_180043731
0x180043704  movzx   esi, ax
0x180043707  or      esi, 80070000h
0x18004370d  jmp     short loc_180043731
0x18004370f  mov     rdx, [rsp+0F8h+arg_8]
0x180043717  mov     rcx, rdi; hFile
0x18004371a  call    ??$WriteToFile@V?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEBV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Z; PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCauseDriver>>(void *,std::vector<PerfDiagOutput::CRootCauseDriver> const &)
0x18004371f  mov     ebx, eax
0x180043721  mov     rcx, rdi; hObject
0x180043724  call    cs:__imp_CloseHandle
0x18004372a  xor     esi, esi
0x18004372c  test    ebx, ebx
0x18004372e  cmovs   esi, ebx
0x180043731  lea     rcx, [rsp+0F8h+SecurityAttributes]; this
0x180043736  call    ??1CPerfDiagSecurityAttribute@PerfDiagDm@@QEAA@XZ; PerfDiagDm::CPerfDiagSecurityAttribute::~CPerfDiagSecurityAttribute(void)
0x18004373b  mov     eax, esi
0x18004373d  add     rsp, 0C0h
0x180043744  pop     r15
0x180043746  pop     r14
0x180043748  pop     r13
0x18004374a  pop     r12
0x18004374c  pop     rdi
0x18004374d  pop     rsi
0x18004374e  pop     rbx
0x18004374f  retn
```
