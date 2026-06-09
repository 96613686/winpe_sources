# PerfDiagDm::MergeDegradations<PerfDiagOutput::CRootCause>(ushort const *,std::vector<PerfDiagOutput::CRootCause,std::allocator<PerfDiagOutput::CRootCause>> &,PerfDiagShared::Serializer::CStringInterner &)

- ea: `0x180043758`
- end: `0x180043aa6`
- name: `??$MergeDegradations@VCRootCause@PerfDiagOutput@@@PerfDiagDm@@YAJPEBGAEAV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@AEAVCStringInterner@Serializer@PerfDiagShared@@@Z`
- size: `846`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64, struct PerfDiagShared::Serializer::CStringInterner *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800b24c4`

## callees

- `0x18001f3c0`
- `0x180043758`
- `0x180043d3c`
- `0x1800b270c`
- `0x1800b2c0c`
- `0x1800b3194`
- `0x1800b43a8`
- `0x1800b4960`
- `0x1800b5940`
- `0x1800bea8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043a4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043a4e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180043801`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180043801`
- `api-ms-win-core-file-l1-1-0!UnlockFile` at `0x18004395a`
- `api-ms-win-core-file-l1-1-0!UnlockFile` at `0x18004395a`
- `api-ms-win-core-file-l1-1-0!LockFileEx` at `0x180043876`
- `api-ms-win-core-file-l1-1-0!LockFileEx` at `0x180043876`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180043909`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180043909`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180043917`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180043917`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800437dc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043a3f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800437dc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043a3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043963`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043a7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043963`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043a7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall PerfDiagDm::MergeDegradations<PerfDiagOutput::CRootCause>(
        LPCWSTR lpFileName,
        __int64 a2,
        struct PerfDiagShared::Serializer::CStringInterner *a3)
{
  HANDLE v6; // rax
  void *v7; // r14
  signed int v8; // esi
  DWORD FileSize; // ebx
  signed int LastError; // eax
  const struct PerfDiagOutput::CRootCause *v11; // r8
  struct PerfDiagOutput::CRootCause *v12; // rbx
  PerfDiagDm *v13; // r12
  PerfDiagDm *v14; // rdi
  PerfDiagDm *i; // r15
  __int128 v16; // xmm1
  __int128 v17; // xmm2
  __int128 v18; // xmm3
  HANDLE v19; // rax
  void *v20; // rdi
  signed int v21; // eax
  int v22; // ebx
  DWORD FileSizeHigh; // [rsp+40h] [rbp-B8h] BYREF
  DWORD nNumberOfBytesToUnlockLow; // [rsp+44h] [rbp-B4h]
  HANDLE v25; // [rsp+48h] [rbp-B0h]
  PerfDiagDm *v26[2]; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-98h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-90h] BYREF
  struct PerfDiagOutput::CRootCause *v29[4]; // [rsp+80h] [rbp-78h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+A0h] [rbp-58h] BYREF

  FileSizeHigh = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( (int)PerfDiagDm::CPerfDiagSecurityAttribute::Init((PerfDiagDm::CPerfDiagSecurityAttribute *)&SecurityAttributes) >= 0 )
  {
    v6 = CreateFileW(lpFileName, 0xC0000000, 3u, &SecurityAttributes, 3u, 0, 0);
    v7 = v6;
    v25 = v6;
    if ( v6 == (HANDLE)-1LL )
      goto LABEL_15;
    v8 = -2147467259;
    FileSize = GetFileSize(v6, &FileSizeHigh);
    nNumberOfBytesToUnlockLow = FileSize;
    if ( FileSize - 1 <= 0xFFFFFFFD )
    {
      *(_OWORD *)v26 = 0;
      v27 = 0;
      std::vector<PerfDiagOutput::CRootCause>::vector<PerfDiagOutput::CRootCause>(v29, a2);
      memset(&Overlapped, 0, sizeof(Overlapped));
      if ( LockFileEx(v7, 2u, 0, FileSize, FileSizeHigh, &Overlapped) )
      {
        v8 = PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCause>>(v7, a3);
        if ( v8 >= 0 )
        {
          v12 = v29[0];
          v13 = v26[1];
          v14 = v26[0];
          while ( v12 != v29[1] )
          {
            for ( i = v14; i != v13; i = (PerfDiagDm *)((char *)i + 64) )
            {
              if ( PerfDiagDm::RootCauseIsEqual(i, v12, v11) )
                break;
            }
            if ( i == v13 )
            {
              std::vector<PerfDiagOutput::CRootCause>::push_back(v26, v12);
              v13 = v26[1];
              v14 = v26[0];
            }
            else if ( *((_DWORD *)i + 4) <= *((_DWORD *)v12 + 4) )
            {
              v16 = *((_OWORD *)v12 + 1);
              v17 = *((_OWORD *)v12 + 2);
              v18 = *((_OWORD *)v12 + 3);
              *(_OWORD *)i = *(_OWORD *)v12;
              *((_OWORD *)i + 1) = v16;
              *((_OWORD *)i + 2) = v17;
              *((_OWORD *)i + 3) = v18;
            }
            v12 = (struct PerfDiagOutput::CRootCause *)((char *)v12 + 64);
          }
          std::_Sort<PerfDiagOutput::CRootCause *,__int64,bool (*)(PerfDiagOutput::CRootCause const &,PerfDiagOutput::CRootCause const &)>(
            v14,
            v13,
            (v13 - v14) >> 6);
          if ( SetFilePointer(v7, 0, 0, 0) != -1 )
          {
            SetEndOfFile(v7);
            v8 = PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCause>>(v7);
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
      std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>>>>(v29);
      std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>>>>(v26);
    }
    UnlockFile(v7, 0, 0, nNumberOfBytesToUnlockLow, FileSizeHigh);
    CloseHandle(v7);
    if ( v8 < 0 )
    {
LABEL_15:
      if ( lpFileName )
      {
        v19 = CreateFileW(lpFileName, 0x40000000u, 1u, &SecurityAttributes, 2u, 0, 0);
        v20 = v19;
        if ( v19 == (HANDLE)-1LL )
        {
          v21 = GetLastError();
          v8 = v21;
          if ( v21 > 0 )
            v8 = (unsigned __int16)v21 | 0x80070000;
        }
        else
        {
          v22 = PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCause>>(v19);
          CloseHandle(v20);
          v8 = 0;
          if ( v22 < 0 )
            v8 = v22;
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
0x180043758  mov     [rsp+arg_8], rdx
0x18004375d  mov     [rsp+arg_0], rcx
0x180043762  push    rbx
0x180043763  push    rsi
0x180043764  push    rdi
0x180043765  push    r12
0x180043767  push    r13
0x180043769  push    r14
0x18004376b  push    r15
0x18004376d  sub     rsp, 0C0h
0x180043774  mov     rdi, r8
0x180043777  mov     r13, rcx
0x18004377a  mov     [rsp+0F8h+FileSizeHigh], 0
0x180043782  xorps   xmm0, xmm0
0x180043785  xor     eax, eax
0x180043787  movups  xmmword ptr [rsp+0F8h+SecurityAttributes.nLength], xmm0
0x18004378c  mov     qword ptr [rsp+0F8h+SecurityAttributes.bInheritHandle], rax
0x180043791  lea     rcx, [rsp+0F8h+SecurityAttributes]; this
0x180043796  call    ?Init@CPerfDiagSecurityAttribute@PerfDiagDm@@QEAAJXZ; PerfDiagDm::CPerfDiagSecurityAttribute::Init(void)
0x18004379b  test    eax, eax
0x18004379d  jns     short loc_1800437B3
0x18004379f  lea     rcx, [rsp+0F8h+SecurityAttributes]; this
0x1800437a4  call    ??1CPerfDiagSecurityAttribute@PerfDiagDm@@QEAA@XZ; PerfDiagDm::CPerfDiagSecurityAttribute::~CPerfDiagSecurityAttribute(void)
0x1800437a9  mov     eax, 80004005h
0x1800437ae  jmp     loc_180043A93
0x1800437b3  mov     [rsp+0F8h+hTemplateFile], 0; hTemplateFile
0x1800437bc  mov     [rsp+0F8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800437c4  mov     r8d, 3; dwShareMode
0x1800437ca  mov     [rsp+0F8h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800437cf  lea     r9, [rsp+0F8h+SecurityAttributes]; lpSecurityAttributes
0x1800437d4  mov     edx, 0C0000000h; dwDesiredAccess
0x1800437d9  mov     rcx, r13; lpFileName
0x1800437dc  call    cs:__imp_CreateFileW
0x1800437e2  mov     r14, rax
0x1800437e5  mov     [rsp+0F8h+var_B0], rax
0x1800437ea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800437ee  jz      loc_180043971
0x1800437f4  mov     esi, 80004005h
0x1800437f9  lea     rdx, [rsp+0F8h+FileSizeHigh]; lpFileSizeHigh
0x1800437fe  mov     rcx, rax; hFile
0x180043801  call    cs:__imp_GetFileSize
0x180043807  mov     ebx, eax
0x180043809  mov     [rsp+0F8h+nNumberOfBytesToUnlockLow], eax
0x18004380d  lea     ecx, [rax-1]
0x180043810  cmp     ecx, 0FFFFFFFDh
0x180043813  ja      loc_180043945
0x180043819  xorps   xmm0, xmm0
0x18004381c  movdqu  xmmword ptr [rsp+0F8h+var_A8], xmm0
0x180043822  mov     [rsp+0F8h+var_98], 0
0x18004382b  mov     rdx, [rsp+0F8h+arg_8]
0x180043833  lea     rcx, [rsp+0F8h+var_78]
0x18004383b  call    ??0?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<PerfDiagOutput::CRootCause>::vector<PerfDiagOutput::CRootCause>(std::vector<PerfDiagOutput::CRootCause> const &)
0x180043840  nop
0x180043841  xorps   xmm0, xmm0
0x180043844  movups  xmmword ptr [rsp+0F8h+Overlapped.Internal], xmm0
0x18004384c  movups  xmmword ptr [rsp+0F8h+Overlapped.10h], xmm0
0x180043854  lea     rax, [rsp+0F8h+Overlapped]
0x18004385c  mov     qword ptr [rsp+0F8h+dwFlagsAndAttributes], rax; lpOverlapped
0x180043861  mov     eax, [rsp+0F8h+FileSizeHigh]
0x180043865  mov     [rsp+0F8h+dwCreationDisposition], eax; nNumberOfBytesToLockHigh
0x180043869  mov     r9d, ebx; nNumberOfBytesToLockLow
0x18004386c  xor     r8d, r8d; dwReserved
0x18004386f  lea     edx, [r8+2]; dwFlags
0x180043873  mov     rcx, r14; hFile
0x180043876  call    cs:__imp_LockFileEx
0x18004387c  test    eax, eax
0x18004387e  jnz     short loc_1800438B3
0x180043880  call    cs:__imp_GetLastError
0x180043886  mov     esi, eax
0x180043888  test    eax, eax
0x18004388a  jle     short loc_180043895
0x18004388c  movzx   esi, ax
0x18004388f  or      esi, 80070000h
0x180043895  lea     rcx, [rsp+0F8h+var_78]; void *
0x18004389d  call    ??1?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>(void)
0x1800438a2  nop
0x1800438a3  lea     rcx, [rsp+0F8h+var_A8]; void *
0x1800438a8  call    ??1?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>(void)
0x1800438ad  nop
0x1800438ae  jmp     loc_180043945
0x1800438b3  lea     r8, [rsp+0F8h+var_A8]
0x1800438b8  mov     rdx, rdi; struct PerfDiagShared::Serializer::CStringInterner *
0x1800438bb  mov     rcx, r14; hFile
0x1800438be  call    ??$ReadFromFile@V?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Z; PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCause>>(void *,PerfDiagShared::Serializer::CStringInterner &,std::vector<PerfDiagOutput::CRootCause> &)
0x1800438c3  mov     esi, eax
0x1800438c5  test    eax, eax
0x1800438c7  js      short loc_18004392C
0x1800438c9  mov     rbx, [rsp+0F8h+var_78]
0x1800438d1  mov     r12, [rsp+0F8h+var_A8+8]
0x1800438d6  mov     rdi, [rsp+0F8h+var_A8]
0x1800438db  cmp     rbx, [rsp+0F8h+var_70]
0x1800438e3  jnz     loc_180043984
0x1800438e9  mov     r8, r12
0x1800438ec  sub     r8, rdi
0x1800438ef  sar     r8, 6
0x1800438f3  mov     rdx, r12
0x1800438f6  mov     rcx, rdi
0x1800438f9  call    ??$_Sort@PEAVCRootCause@PerfDiagOutput@@_JP6A_NAEBV12@0@Z@std@@YAXPEAVCRootCause@PerfDiagOutput@@0_JP6A_NAEBV12@2@Z@Z; std::_Sort<PerfDiagOutput::CRootCause *,__int64,bool (*)(PerfDiagOutput::CRootCause const &,PerfDiagOutput::CRootCause const &)>(PerfDiagOutput::CRootCause *,PerfDiagOutput::CRootCause *,__int64,bool (*)(PerfDiagOutput::CRootCause const &,PerfDiagOutput::CRootCause const &))
0x1800438fe  xor     r9d, r9d; dwMoveMethod
0x180043901  xor     r8d, r8d; lpDistanceToMoveHigh
0x180043904  xor     edx, edx; lDistanceToMove
0x180043906  mov     rcx, r14; hFile
0x180043909  call    cs:__imp_SetFilePointer
0x18004390f  cmp     eax, 0FFFFFFFFh
0x180043912  jz      short loc_18004392C
0x180043914  mov     rcx, r14; hFile
0x180043917  call    cs:__imp_SetEndOfFile
0x18004391d  lea     rdx, [rsp+0F8h+var_A8]
0x180043922  mov     rcx, r14; hFile
0x180043925  call    ??$WriteToFile@V?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Z; PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCause>>(void *,std::vector<PerfDiagOutput::CRootCause> const &)
0x18004392a  mov     esi, eax
0x18004392c  lea     rcx, [rsp+0F8h+var_78]; void *
0x180043934  call    ??1?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>(void)
0x180043939  nop
0x18004393a  lea     rcx, [rsp+0F8h+var_A8]; void *
0x18004393f  call    ??1?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>(void)
0x180043944  nop
0x180043945  mov     eax, [rsp+0F8h+FileSizeHigh]
0x180043949  mov     [rsp+0F8h+dwCreationDisposition], eax; nNumberOfBytesToUnlockHigh
0x18004394d  mov     r9d, [rsp+0F8h+nNumberOfBytesToUnlockLow]; nNumberOfBytesToUnlockLow
0x180043952  xor     r8d, r8d; dwFileOffsetHigh
0x180043955  xor     edx, edx; dwFileOffsetLow
0x180043957  mov     rcx, r14; hFile
0x18004395a  call    cs:__imp_UnlockFile
0x180043960  mov     rcx, r14; hObject
0x180043963  call    cs:__imp_CloseHandle
0x180043969  test    esi, esi
0x18004396b  jns     loc_180043A87
0x180043971  test    r13, r13
0x180043974  jnz     loc_180043A13
0x18004397a  mov     esi, 80070057h
0x18004397f  jmp     loc_180043A87
0x180043984  mov     r15, rdi
0x180043987  cmp     rdi, r12
0x18004398a  jz      short loc_1800439A4
0x18004398c  mov     rdx, rbx; struct PerfDiagOutput::CRootCause *
0x18004398f  mov     rcx, r15; this
0x180043992  call    ?RootCauseIsEqual@PerfDiagDm@@YA_NAEBVCRootCause@PerfDiagOutput@@0@Z; PerfDiagDm::RootCauseIsEqual(PerfDiagOutput::CRootCause const &,PerfDiagOutput::CRootCause const &)
0x180043997  test    al, al
0x180043999  jnz     short loc_1800439A4
0x18004399b  add     r15, 40h ; '@'
0x18004399f  cmp     r15, r12
0x1800439a2  jnz     short loc_18004398C
0x1800439a4  cmp     r15, r12
0x1800439a7  jnz     short loc_1800439C2
0x1800439a9  mov     rdx, rbx
0x1800439ac  lea     rcx, [rsp+0F8h+var_A8]
0x1800439b1  call    ?push_back@?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@QEAAX$$QEAVCRootCause@PerfDiagOutput@@@Z; std::vector<PerfDiagOutput::CRootCause>::push_back(PerfDiagOutput::CRootCause &&)
0x1800439b6  mov     r12, [rsp+0F8h+var_A8+8]
0x1800439bb  mov     rdi, [rsp+0F8h+var_A8]
0x1800439c0  jmp     short loc_1800439ED
0x1800439c2  mov     eax, [rbx+10h]
0x1800439c5  cmp     [r15+10h], eax
0x1800439c9  ja      short loc_1800439ED
0x1800439cb  movups  xmm0, xmmword ptr [rbx]
0x1800439ce  movups  xmm1, xmmword ptr [rbx+10h]
0x1800439d2  movups  xmm2, xmmword ptr [rbx+20h]
0x1800439d6  movups  xmm3, xmmword ptr [rbx+30h]
0x1800439da  movups  xmmword ptr [r15], xmm0
0x1800439de  movups  xmmword ptr [r15+10h], xmm1
0x1800439e3  movups  xmmword ptr [r15+20h], xmm2
0x1800439e8  movups  xmmword ptr [r15+30h], xmm3
0x1800439ed  add     rbx, 40h ; '@'
0x1800439f1  jmp     loc_1800438DB
0x1800439f6  mov     r13, [rsp+0F8h+arg_0]
0x1800439fe  mov     esi, [rsp+0F8h+arg_18]
0x180043a05  mov     r14, [rsp+0F8h+var_B0]
0x180043a0a  jmp     loc_180043945
0x180043a0f  jmp     short loc_1800439F6
0x180043a11  jmp     short loc_1800439F6
0x180043a13  mov     [rsp+0F8h+hTemplateFile], 0; hTemplateFile
0x180043a1c  mov     [rsp+0F8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180043a24  mov     [rsp+0F8h+dwCreationDisposition], 2; dwCreationDisposition
0x180043a2c  lea     r9, [rsp+0F8h+SecurityAttributes]; lpSecurityAttributes
0x180043a31  mov     edx, 40000000h; dwDesiredAccess
0x180043a36  mov     r8d, 1; dwShareMode
0x180043a3c  mov     rcx, r13; lpFileName
0x180043a3f  call    cs:__imp_CreateFileW
0x180043a45  mov     rdi, rax
0x180043a48  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180043a4c  jnz     short loc_180043A65
0x180043a4e  call    cs:__imp_GetLastError
0x180043a54  mov     esi, eax
0x180043a56  test    eax, eax
0x180043a58  jle     short loc_180043A87
0x180043a5a  movzx   esi, ax
0x180043a5d  or      esi, 80070000h
0x180043a63  jmp     short loc_180043A87
0x180043a65  mov     rdx, [rsp+0F8h+arg_8]
0x180043a6d  mov     rcx, rdi; hFile
0x180043a70  call    ??$WriteToFile@V?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Z; PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCause>>(void *,std::vector<PerfDiagOutput::CRootCause> const &)
0x180043a75  mov     ebx, eax
0x180043a77  mov     rcx, rdi; hObject
0x180043a7a  call    cs:__imp_CloseHandle
0x180043a80  xor     esi, esi
0x180043a82  test    ebx, ebx
0x180043a84  cmovs   esi, ebx
0x180043a87  lea     rcx, [rsp+0F8h+SecurityAttributes]; this
0x180043a8c  call    ??1CPerfDiagSecurityAttribute@PerfDiagDm@@QEAA@XZ; PerfDiagDm::CPerfDiagSecurityAttribute::~CPerfDiagSecurityAttribute(void)
0x180043a91  mov     eax, esi
0x180043a93  add     rsp, 0C0h
0x180043a9a  pop     r15
0x180043a9c  pop     r14
0x180043a9e  pop     r13
0x180043aa0  pop     r12
0x180043aa2  pop     rdi
0x180043aa3  pop     rsi
0x180043aa4  pop     rbx
0x180043aa5  retn
```
