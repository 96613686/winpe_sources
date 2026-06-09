# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)

- ea: `0x18001f888`
- end: `0x18001fcdd`
- name: `?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z`
- size: `1109`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001f160`

## callees

- `0x1800017e0`
- `0x1800023c0`
- `0x180006960`
- `0x1800069ec`
- `0x180009810`
- `0x180009994`
- `0x18001ed38`
- `0x18001ee04`
- `0x18001f080`
- `0x18001f888`
- `0x18001fec8`
- `0x180026010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fb40`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fb40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fb93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fcbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fb93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fcbc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f9f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f9f0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001f941`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001f941`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001fbc5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001fbc5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001fbd6`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001fbd6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001fb79`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001fc9f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001fb79`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001fc9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        int a3,
        int a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6)
{
  const unsigned __int16 *v7; // r15
  int result; // eax
  HANDLE FirstFileW; // r13
  int v10; // edi
  int v11; // esi
  void *v12; // rbx
  LPCVOID v13; // r15
  HANDLE v14; // r12
  HANDLE FileW; // rax
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // r9
  unsigned int v18; // r15d
  LPCVOID v19; // r12
  char v20; // r13
  __int64 v21; // rcx
  __int64 v22; // rax
  _QWORD *v23; // rbx
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v24; // r8
  void **v25; // rbx
  signed int Error; // ebx
  signed int v27; // ebx
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  int hTemplateFile; // [rsp+30h] [rbp-D0h]
  HANDLE v31; // [rsp+50h] [rbp-B0h]
  unsigned int v32; // [rsp+58h] [rbp-A8h] BYREF
  void *v33; // [rsp+60h] [rbp-A0h]
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v34; // [rsp+68h] [rbp-98h]
  LPCVOID v35; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v36; // [rsp+78h] [rbp-88h]
  int v37; // [rsp+7Ch] [rbp-84h]
  int v38; // [rsp+80h] [rbp-80h]
  int v39; // [rsp+84h] [rbp-7Ch]
  HANDLE v40; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v41; // [rsp+90h] [rbp-70h]
  LPCVOID lpBaseAddress; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v43; // [rsp+A0h] [rbp-60h]
  HANDLE hObject; // [rsp+A8h] [rbp-58h]
  _BYTE v45[16]; // [rsp+C0h] [rbp-40h] BYREF
  _WORD v46[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v47; // [rsp+D4h] [rbp-2Ch]
  char v48; // [rsp+D5h] [rbp-2Bh]
  __int16 v49; // [rsp+D6h] [rbp-2Ah]
  union _LARGE_INTEGER v50; // [rsp+E0h] [rbp-20h]
  struct _GUID v51; // [rsp+E8h] [rbp-18h]
  void *v52; // [rsp+118h] [rbp+18h]
  unsigned int v53; // [rsp+120h] [rbp+20h]
  int v54; // [rsp+124h] [rbp+24h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+130h] [rbp+30h] BYREF
  WCHAR FileName[264]; // [rsp+380h] [rbp+280h] BYREF
  WCHAR v57[264]; // [rsp+590h] [rbp+490h] BYREF

  v38 = a4;
  v39 = a3;
  v34 = this;
  v7 = a5;
  v41 = a5;
  memset_0(FileName, 0, 0x208u);
  result = StringCchCopyW(FileName, 0x104u, a5);
  if ( result < 0 )
    return result;
  result = StringCchCatW(FileName, 0x104u, a6);
  if ( result < 0 )
    return result;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  v31 = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
    return 0;
  v10 = v37;
  v11 = v37;
  do
  {
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      memset_0(v57, 0, 0x208u);
      if ( StringCchCopyW(v57, 0x104u, v7) >= 0 && StringCchCatW(v57, 0x104u, FindFileData.cFileName) >= 0 )
      {
        v12 = 0;
        v40 = 0;
        v13 = 0;
        lpBaseAddress = 0;
        v14 = 0;
        hObject = 0;
        FileW = CreateFileW(v57, 0x80000000, 1u, 0, 3u, 0x80u, 0);
        if ( FileW == (HANDLE)-1LL )
        {
          if ( ATL::AtlHresultFromLastError() < 0 )
            goto LABEL_43;
        }
        else
        {
          v12 = FileW;
          v40 = FileW;
        }
        if ( ATL::CAtlFileMappingBase::MapFile(
               (ATL::CAtlFileMappingBase *)&lpBaseAddress,
               v12,
               v16,
               v17,
               dwCreationDisposition,
               dwFlagsAndAttributes) >= 0 )
        {
          v18 = v43;
          if ( v43 <= 0x100000 )
          {
            v19 = lpBaseAddress;
            v32 = 0;
            if ( (unsigned int)v43 >= 4 )
            {
              v24 = v34;
              v20 = *((_BYTE *)v34 + 104);
              if ( !v20 )
              {
                LODWORD(v33) = v43 - 4;
                v25 = (void **)((char *)v34 + 128);
                if ( *((_DWORD *)v34 + 34) < (unsigned int)(v43 - 4) )
                {
                  free(*v25);
                  *v25 = 0;
                  *((_DWORD *)v34 + 34) = 0;
                  if ( !ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(v25, v18) )
                  {
LABEL_23:
                    Error = 0;
                    if ( v19 && !UnmapViewOfFile(v19) )
                      Error = ATL::AtlHresultFromLastError();
                    if ( hObject && !CloseHandle(hObject) && Error >= 0 )
                      ATL::AtlHresultFromLastError();
                    FirstFileW = v31;
LABEL_31:
                    ATL::CHandle::~CHandle((ATL::CHandle *)&v40);
                    v7 = v41;
                    continue;
                  }
                  v24 = v34;
                  *((_DWORD *)v34 + 34) = v18;
                }
                if ( (unsigned int)Performance::RtlCompression::CRtlCompressBuffer::operator()(
                                     (__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, int, int, __int64, __int64))v24
                                   + 11,
                                     (__int64)*v25 + 4,
                                     (__int64)v19,
                                     v18,
                                     (__int64)*v25 + 4,
                                     (int)v33,
                                     hTemplateFile,
                                     (__int64)&v32,
                                     *((_QWORD *)v24 + 14))
                  || v32 > (unsigned int)v33 )
                {
                  v20 = 1;
                }
                v32 += 4;
                *(_DWORD *)*v25 = v18;
                if ( !v20 )
                {
                  v18 = v32;
                  v33 = *v25;
                  v35 = v33;
                  v37 = v11;
                  v21 = 56;
                  v22 = v32;
                  goto LABEL_17;
                }
              }
            }
            else
            {
              v20 = 1;
            }
            v33 = (void *)v19;
            v35 = v19;
            v37 = v10;
            v21 = 40;
            v22 = v18;
LABEL_17:
            v36 = v18;
            if ( (unsigned __int64)(v22 + 48) <= 0xFFB8 )
            {
              v23 = (_QWORD *)((char *)v34 + v21);
              if ( *(_QWORD *)std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,0>>::find(
                                (char *)v34 + v21,
                                v45,
                                &v35) == *v23 )
              {
                memset_0(v46, 0, 0x58u);
                v46[0] = v38;
                v50 = a2;
                v51 = PerfTrackMetadataGuid;
                v47 = 33 - (v20 != 0);
                v49 = 0;
                v48 = 0;
                v52 = v33;
                v53 = v18;
                v54 = v39;
                (*(void (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)v34 + 2) + 192LL))(
                  *((_QWORD *)v34 + 2),
                  v46,
                  0,
                  0);
              }
            }
            goto LABEL_23;
          }
        }
        v14 = hObject;
        v13 = lpBaseAddress;
LABEL_43:
        v27 = 0;
        if ( v13 && !UnmapViewOfFile(v13) )
          v27 = ATL::AtlHresultFromLastError();
        if ( v14 && !CloseHandle(v14) && v27 >= 0 )
          ATL::AtlHresultFromLastError();
        goto LABEL_31;
      }
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  FindClose(FirstFileW);
  return 0;
}

```

## disassembly

```asm
0x18001f888  push    rbp
0x18001f88a  push    rbx
0x18001f88b  push    rsi
0x18001f88c  push    rdi
0x18001f88d  push    r12
0x18001f88f  push    r13
0x18001f891  push    r14
0x18001f893  push    r15
0x18001f895  lea     rbp, [rsp-6B8h]
0x18001f89d  sub     rsp, 7B8h
0x18001f8a4  mov     rax, cs:__security_cookie
0x18001f8ab  xor     rax, rsp
0x18001f8ae  mov     [rbp+6F0h+var_50], rax
0x18001f8b5  mov     [rbp+6F0h+var_770], r9d
0x18001f8b9  mov     [rbp+6F0h+var_76C], r8d
0x18001f8bd  mov     r14, rdx
0x18001f8c0  mov     [rsp+7F0h+var_788], rcx
0x18001f8c5  mov     r15, [rbp+6F0h+arg_20]
0x18001f8cc  mov     [rbp+6F0h+var_760], r15
0x18001f8d0  mov     rbx, [rbp+6F0h+arg_28]
0x18001f8d7  xor     edx, edx; Val
0x18001f8d9  mov     r8d, 208h; Size
0x18001f8df  lea     rcx, [rbp+6F0h+FileName]; void *
0x18001f8e6  call    memset_0
0x18001f8eb  mov     r8, r15; unsigned __int16 *
0x18001f8ee  mov     r12d, 104h
0x18001f8f4  mov     edx, r12d; unsigned __int64
0x18001f8f7  lea     rcx, [rbp+6F0h+FileName]; unsigned __int16 *
0x18001f8fe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f903  test    eax, eax
0x18001f905  js      loc_18001FBDE
0x18001f90b  mov     r8, rbx; unsigned __int16 *
0x18001f90e  mov     edx, r12d; unsigned __int64
0x18001f911  lea     rcx, [rbp+6F0h+FileName]; unsigned __int16 *
0x18001f918  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f91d  test    eax, eax
0x18001f91f  js      loc_18001FBDE
0x18001f925  xor     edx, edx; Val
0x18001f927  mov     r8d, 250h; Size
0x18001f92d  lea     rcx, [rbp+6F0h+FindFileData]; void *
0x18001f931  call    memset_0
0x18001f936  lea     rdx, [rbp+6F0h+FindFileData]; lpFindFileData
0x18001f93a  lea     rcx, [rbp+6F0h+FileName]; lpFileName
0x18001f941  call    cs:__imp_FindFirstFileW
0x18001f947  mov     r13, rax
0x18001f94a  mov     [rsp+7F0h+var_7A0], rax
0x18001f94f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f953  jz      loc_18001FBDC
0x18001f959  mov     edi, [rsp+7F0h+var_774]
0x18001f95d  mov     esi, [rsp+7F0h+var_774]
0x18001f961  test    byte ptr [rbp+6F0h+FindFileData.dwFileAttributes], 10h
0x18001f965  jnz     loc_18001FBBE
0x18001f96b  xor     edx, edx; Val
0x18001f96d  mov     r8d, 208h; Size
0x18001f973  lea     rcx, [rbp+6F0h+var_260]; void *
0x18001f97a  call    memset_0
0x18001f97f  mov     r8, r15; unsigned __int16 *
0x18001f982  mov     rdx, r12; unsigned __int64
0x18001f985  lea     rcx, [rbp+6F0h+var_260]; unsigned __int16 *
0x18001f98c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f991  test    eax, eax
0x18001f993  js      loc_18001FBBE
0x18001f999  lea     r8, [rbp+6F0h+FindFileData.cFileName]; unsigned __int16 *
0x18001f99d  mov     rdx, r12; unsigned __int64
0x18001f9a0  lea     rcx, [rbp+6F0h+var_260]; unsigned __int16 *
0x18001f9a7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f9ac  test    eax, eax
0x18001f9ae  js      loc_18001FBBE
0x18001f9b4  xor     ebx, ebx
0x18001f9b6  mov     [rbp+6F0h+var_768], rbx
0x18001f9ba  xor     r15d, r15d
0x18001f9bd  mov     [rbp+6F0h+lpBaseAddress], r15
0x18001f9c1  xor     r12d, r12d
0x18001f9c4  mov     [rbp+6F0h+hObject], r12
0x18001f9c8  mov     [rsp+7F0h+hTemplateFile], r12; hTemplateFile
0x18001f9cd  mov     [rsp+7F0h+dwFlagsAndAttributes], 80h; unsigned int
0x18001f9d5  mov     [rsp+7F0h+dwCreationDisposition], 3; unsigned int
0x18001f9dd  xor     r9d, r9d; lpSecurityAttributes
0x18001f9e0  mov     edx, 80000000h; dwDesiredAccess
0x18001f9e5  lea     r8d, [rbx+1]; dwShareMode
0x18001f9e9  lea     rcx, [rbp+6F0h+var_260]; lpFileName
0x18001f9f0  call    cs:__imp_CreateFileW
0x18001f9f6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f9fa  jnz     short loc_18001FA0B
0x18001f9fc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001fa01  test    eax, eax
0x18001fa03  js      loc_18001FC95
0x18001fa09  jmp     short loc_18001FA12
0x18001fa0b  mov     rbx, rax
0x18001fa0e  mov     [rbp+6F0h+var_768], rax
0x18001fa12  mov     rdx, rbx; void *
0x18001fa15  lea     rcx, [rbp+6F0h+lpBaseAddress]; this
0x18001fa19  call    ?MapFile@CAtlFileMappingBase@ATL@@QEAAJPEAX_K1KK@Z; ATL::CAtlFileMappingBase::MapFile(void *,unsigned __int64,unsigned __int64,ulong,ulong)
0x18001fa1e  test    eax, eax
0x18001fa20  js      loc_18001FC8D
0x18001fa26  mov     r15, [rbp+6F0h+var_750]
0x18001fa2a  cmp     r15, 100000h
0x18001fa31  ja      loc_18001FC8D
0x18001fa37  mov     r12, [rbp+6F0h+lpBaseAddress]
0x18001fa3b  mov     [rsp+7F0h+var_798], 0
0x18001fa43  cmp     r15d, 4
0x18001fa47  jnb     loc_18001FB13
0x18001fa4d  mov     r13b, 1
0x18001fa50  mov     rax, r12
0x18001fa53  mov     [rsp+7F0h+var_790], rax
0x18001fa58  mov     [rsp+7F0h+var_780], rax
0x18001fa5d  mov     [rsp+7F0h+var_774], edi
0x18001fa61  mov     ecx, 28h ; '('
0x18001fa66  mov     eax, r15d
0x18001fa69  mov     [rsp+7F0h+var_778], r15d
0x18001fa6e  add     rax, 30h ; '0'
0x18001fa72  cmp     rax, 0FFB8h
0x18001fa78  ja      loc_18001FB6F
0x18001fa7e  mov     rbx, [rsp+7F0h+var_788]
0x18001fa83  add     rbx, rcx
0x18001fa86  lea     r8, [rsp+7F0h+var_780]
0x18001fa8b  lea     rdx, [rbp+6F0h+var_730]
0x18001fa8f  mov     rcx, rbx
0x18001fa92  call    ?find@?$_Tree@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@@std@@@2@AEBU?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,0>>::find(Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator> const &)
0x18001fa97  mov     rcx, [rbx]
0x18001fa9a  cmp     [rax], rcx
0x18001fa9d  jnz     loc_18001FB6F
0x18001faa3  xor     edx, edx; Val
0x18001faa5  lea     r8d, [rdx+58h]; Size
0x18001faa9  lea     rcx, [rbp+6F0h+var_720]; void *
0x18001faad  call    memset_0
0x18001fab2  mov     eax, [rbp+6F0h+var_770]
0x18001fab5  mov     [rbp+6F0h+var_720], ax
0x18001fab9  mov     [rbp+6F0h+var_710], r14
0x18001fabd  movups  xmm0, xmmword ptr cs:PerfTrackMetadataGuid.Data1
0x18001fac4  movdqu  [rbp+6F0h+var_708], xmm0
0x18001fac9  neg     r13b
0x18001facc  sbb     al, al
0x18001face  add     al, 21h ; '!'
0x18001fad0  mov     [rbp+6F0h+var_71C], al
0x18001fad3  xor     eax, eax
0x18001fad5  mov     [rbp+6F0h+var_71A], ax
0x18001fad9  mov     [rbp+6F0h+var_71B], al
0x18001fadc  mov     rax, [rsp+7F0h+var_790]
0x18001fae1  mov     [rbp+6F0h+var_6D8], rax
0x18001fae5  mov     [rbp+6F0h+var_6D0], r15d
0x18001fae9  mov     eax, [rbp+6F0h+var_76C]
0x18001faec  mov     [rbp+6F0h+var_6CC], eax
0x18001faef  mov     rax, [rsp+7F0h+var_788]
0x18001faf4  mov     rcx, [rax+10h]
0x18001faf8  mov     rax, [rcx]
0x18001fafb  xor     r9d, r9d
0x18001fafe  xor     r8d, r8d
0x18001fb01  lea     rdx, [rbp+6F0h+var_720]
0x18001fb05  mov     rax, [rax+0C0h]
0x18001fb0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb11  jmp     short loc_18001FB6F
0x18001fb13  mov     r8, [rsp+7F0h+var_788]
0x18001fb18  mov     r13b, [r8+68h]
0x18001fb1c  test    r13b, r13b
0x18001fb1f  jnz     loc_18001FA50
0x18001fb25  lea     eax, [r15-4]
0x18001fb29  mov     dword ptr [rsp+7F0h+var_790], eax
0x18001fb2d  lea     rbx, [r8+80h]
0x18001fb34  cmp     [rbx+8], eax
0x18001fb37  jnb     loc_18001FC0D
0x18001fb3d  mov     rcx, [rbx]; Block
0x18001fb40  call    cs:__imp_free
0x18001fb46  mov     qword ptr [rbx], 0
0x18001fb4d  mov     rax, [rsp+7F0h+var_788]
0x18001fb52  mov     dword ptr [rax+88h], 0
0x18001fb5c  mov     edx, r15d
0x18001fb5f  mov     rcx, rbx
0x18001fb62  call    ?AllocateBytes@?$CHeapPtrBase@U_TRACE_LOGFILE_HEADER@@VCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x18001fb67  test    al, al
0x18001fb69  jnz     loc_18001FC01
0x18001fb6f  xor     ebx, ebx
0x18001fb71  test    r12, r12
0x18001fb74  jz      short loc_18001FB8A
0x18001fb76  mov     rcx, r12; lpBaseAddress
0x18001fb79  call    cs:__imp_UnmapViewOfFile
0x18001fb7f  test    eax, eax
0x18001fb81  jnz     short loc_18001FB8A
0x18001fb83  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001fb88  mov     ebx, eax
0x18001fb8a  mov     rcx, [rbp+6F0h+hObject]; hObject
0x18001fb8e  test    rcx, rcx
0x18001fb91  jz      short loc_18001FBA6
0x18001fb93  call    cs:__imp_CloseHandle
0x18001fb99  test    eax, eax
0x18001fb9b  jnz     short loc_18001FBA6
0x18001fb9d  test    ebx, ebx
0x18001fb9f  js      short loc_18001FBA6
0x18001fba1  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001fba6  mov     r13, [rsp+7F0h+var_7A0]
0x18001fbab  lea     rcx, [rbp+6F0h+var_768]; this
0x18001fbaf  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x18001fbb4  mov     r15, [rbp+6F0h+var_760]
0x18001fbb8  mov     r12d, 104h
0x18001fbbe  lea     rdx, [rbp+6F0h+FindFileData]; lpFindFileData
0x18001fbc2  mov     rcx, r13; hFindFile
0x18001fbc5  call    cs:__imp_FindNextFileW
0x18001fbcb  test    eax, eax
0x18001fbcd  jnz     loc_18001F961
0x18001fbd3  mov     rcx, r13; hFindFile
0x18001fbd6  call    cs:__imp_FindClose
0x18001fbdc  xor     eax, eax
0x18001fbde  mov     rcx, [rbp+6F0h+var_50]
0x18001fbe5  xor     rcx, rsp; StackCookie
0x18001fbe8  call    __security_check_cookie
0x18001fbed  add     rsp, 7B8h
0x18001fbf4  pop     r15
0x18001fbf6  pop     r14
0x18001fbf8  pop     r13
0x18001fbfa  pop     r12
0x18001fbfc  pop     rdi
0x18001fbfd  pop     rsi
0x18001fbfe  pop     rbx
0x18001fbff  pop     rbp
0x18001fc00  retn
0x18001fc01  mov     r8, [rsp+7F0h+var_788]
0x18001fc06  mov     [r8+88h], r15d
0x18001fc0d  mov     rdx, [rbx]
0x18001fc10  add     rdx, 4
0x18001fc14  lea     rcx, [r8+58h]
0x18001fc18  mov     rax, [r8+70h]
0x18001fc1c  mov     [rsp+7F0h+var_7B0], rax
0x18001fc21  lea     rax, [rsp+7F0h+var_798]
0x18001fc26  mov     [rsp+7F0h+var_7B8], rax
0x18001fc2b  mov     eax, dword ptr [rsp+7F0h+var_790]
0x18001fc2f  mov     [rsp+7F0h+dwFlagsAndAttributes], eax
0x18001fc33  mov     qword ptr [rsp+7F0h+dwCreationDisposition], rdx
0x18001fc38  mov     r9d, r15d
0x18001fc3b  mov     r8, r12
0x18001fc3e  call    ??RCRtlCompressBuffer@RtlCompression@Performance@@QEBAJGPEBXKPEAXKKPEAK1@Z; Performance::RtlCompression::CRtlCompressBuffer::operator()(ushort,void const *,ulong,void *,ulong,ulong,ulong *,void *)
0x18001fc43  mov     ecx, [rsp+7F0h+var_798]
0x18001fc47  test    eax, eax
0x18001fc49  jnz     short loc_18001FC51
0x18001fc4b  cmp     ecx, dword ptr [rsp+7F0h+var_790]
0x18001fc4f  jbe     short loc_18001FC54
0x18001fc51  mov     r13b, 1
0x18001fc54  add     ecx, 4
0x18001fc57  mov     [rsp+7F0h+var_798], ecx
0x18001fc5b  mov     rax, [rbx]
0x18001fc5e  mov     [rax], r15d
0x18001fc61  test    r13b, r13b
0x18001fc64  jnz     loc_18001FA50
0x18001fc6a  mov     r15d, [rsp+7F0h+var_798]
0x18001fc6f  mov     rcx, [rbx]
0x18001fc72  mov     [rsp+7F0h+var_790], rcx
0x18001fc77  mov     [rsp+7F0h+var_780], rcx
0x18001fc7c  mov     [rsp+7F0h+var_774], esi
0x18001fc80  mov     ecx, 38h ; '8'
0x18001fc85  mov     eax, r15d
0x18001fc88  jmp     loc_18001FA69
0x18001fc8d  mov     r12, [rbp+6F0h+hObject]
0x18001fc91  mov     r15, [rbp+6F0h+lpBaseAddress]
0x18001fc95  xor     ebx, ebx
0x18001fc97  test    r15, r15
0x18001fc9a  jz      short loc_18001FCB0
0x18001fc9c  mov     rcx, r15; lpBaseAddress
0x18001fc9f  call    cs:__imp_UnmapViewOfFile
0x18001fca5  test    eax, eax
0x18001fca7  jnz     short loc_18001FCB0
0x18001fca9  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001fcae  mov     ebx, eax
0x18001fcb0  test    r12, r12
0x18001fcb3  jz      loc_18001FBAB
0x18001fcb9  mov     rcx, r12; hObject
0x18001fcbc  call    cs:__imp_CloseHandle
0x18001fcc2  test    eax, eax
0x18001fcc4  jnz     loc_18001FBAB
0x18001fcca  test    ebx, ebx
0x18001fccc  js      loc_18001FBAB
0x18001fcd2  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001fcd7  jmp     loc_18001FBAB
```
