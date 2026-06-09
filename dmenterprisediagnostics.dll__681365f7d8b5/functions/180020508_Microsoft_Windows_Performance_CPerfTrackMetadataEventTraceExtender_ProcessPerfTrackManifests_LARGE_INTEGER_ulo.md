# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)

- ea: `0x180020508`
- end: `0x180020994`
- name: `?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z`
- size: `1164`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001fd80`

## callees

- `0x180001800`
- `0x1800023e0`
- `0x180006be0`
- `0x180006c6c`
- `0x180009cd8`
- `0x180009e70`
- `0x18001f900`
- `0x18001f9e8`
- `0x18001fc8c`
- `0x180020508`
- `0x180020b88`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800207cc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800207cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002082b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002096d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002082b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002096d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180020676`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180020676`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800205c1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800205c1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180020863`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180020863`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002087a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002087a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002080b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002094a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002080b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002094a`

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
  int Error; // ebx
  int v27; // ebx
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
          if ( (int)ATL::AtlHresultFromLastError() < 0 )
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
                  if ( !(unsigned __int8)ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(
                                           v25,
                                           v18) )
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
                                     (int)v24 + 88,
                                     *(_DWORD *)v25 + 4,
                                     (_DWORD)v19,
                                     v18,
                                     (__int64)*v25 + 4,
                                     (_DWORD)v33,
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
0x180020508  push    rbp
0x18002050a  push    rbx
0x18002050b  push    rsi
0x18002050c  push    rdi
0x18002050d  push    r12
0x18002050f  push    r13
0x180020511  push    r14
0x180020513  push    r15
0x180020515  lea     rbp, [rsp-6B8h]
0x18002051d  sub     rsp, 7B8h
0x180020524  mov     rax, cs:__security_cookie
0x18002052b  xor     rax, rsp
0x18002052e  mov     [rbp+6F0h+var_50], rax
0x180020535  mov     [rbp+6F0h+var_770], r9d
0x180020539  mov     [rbp+6F0h+var_76C], r8d
0x18002053d  mov     r14, rdx
0x180020540  mov     [rsp+7F0h+var_788], rcx
0x180020545  mov     r15, [rbp+6F0h+arg_20]
0x18002054c  mov     [rbp+6F0h+var_760], r15
0x180020550  mov     rbx, [rbp+6F0h+arg_28]
0x180020557  xor     edx, edx; Val
0x180020559  mov     r8d, 208h; Size
0x18002055f  lea     rcx, [rbp+6F0h+FileName]; void *
0x180020566  call    memset_0
0x18002056b  mov     r8, r15; unsigned __int16 *
0x18002056e  mov     r12d, 104h
0x180020574  mov     edx, r12d; unsigned __int64
0x180020577  lea     rcx, [rbp+6F0h+FileName]; unsigned __int16 *
0x18002057e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180020583  test    eax, eax
0x180020585  js      loc_180020888
0x18002058b  mov     r8, rbx; unsigned __int16 *
0x18002058e  mov     edx, r12d; unsigned __int64
0x180020591  lea     rcx, [rbp+6F0h+FileName]; unsigned __int16 *
0x180020598  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002059d  test    eax, eax
0x18002059f  js      loc_180020888
0x1800205a5  xor     edx, edx; Val
0x1800205a7  mov     r8d, 250h; Size
0x1800205ad  lea     rcx, [rbp+6F0h+FindFileData]; void *
0x1800205b1  call    memset_0
0x1800205b6  lea     rdx, [rbp+6F0h+FindFileData]; lpFindFileData
0x1800205ba  lea     rcx, [rbp+6F0h+FileName]; lpFileName
0x1800205c1  call    cs:__imp_FindFirstFileW
0x1800205c8  nop     dword ptr [rax+rax+00h]
0x1800205cd  mov     r13, rax
0x1800205d0  mov     [rsp+7F0h+var_7A0], rax
0x1800205d5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800205d9  jz      loc_180020886
0x1800205df  mov     edi, [rsp+7F0h+var_774]
0x1800205e3  mov     esi, [rsp+7F0h+var_774]
0x1800205e7  test    byte ptr [rbp+6F0h+FindFileData.dwFileAttributes], 10h
0x1800205eb  jnz     loc_18002085C
0x1800205f1  xor     edx, edx; Val
0x1800205f3  mov     r8d, 208h; Size
0x1800205f9  lea     rcx, [rbp+6F0h+var_260]; void *
0x180020600  call    memset_0
0x180020605  mov     r8, r15; unsigned __int16 *
0x180020608  mov     rdx, r12; unsigned __int64
0x18002060b  lea     rcx, [rbp+6F0h+var_260]; unsigned __int16 *
0x180020612  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180020617  test    eax, eax
0x180020619  js      loc_18002085C
0x18002061f  lea     r8, [rbp+6F0h+FindFileData.cFileName]; unsigned __int16 *
0x180020623  mov     rdx, r12; unsigned __int64
0x180020626  lea     rcx, [rbp+6F0h+var_260]; unsigned __int16 *
0x18002062d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180020632  test    eax, eax
0x180020634  js      loc_18002085C
0x18002063a  xor     ebx, ebx
0x18002063c  mov     [rbp+6F0h+var_768], rbx
0x180020640  xor     r15d, r15d
0x180020643  mov     [rbp+6F0h+lpBaseAddress], r15
0x180020647  xor     r12d, r12d
0x18002064a  mov     [rbp+6F0h+hObject], r12
0x18002064e  mov     [rsp+7F0h+hTemplateFile], r12; hTemplateFile
0x180020653  mov     [rsp+7F0h+dwFlagsAndAttributes], 80h; unsigned int
0x18002065b  mov     [rsp+7F0h+dwCreationDisposition], 3; unsigned int
0x180020663  xor     r9d, r9d; lpSecurityAttributes
0x180020666  mov     edx, 80000000h; dwDesiredAccess
0x18002066b  lea     r8d, [rbx+1]; dwShareMode
0x18002066f  lea     rcx, [rbp+6F0h+var_260]; lpFileName
0x180020676  call    cs:__imp_CreateFileW
0x18002067d  nop     dword ptr [rax+rax+00h]
0x180020682  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020686  jnz     short loc_180020697
0x180020688  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002068d  test    eax, eax
0x18002068f  js      loc_180020940
0x180020695  jmp     short loc_18002069E
0x180020697  mov     rbx, rax
0x18002069a  mov     [rbp+6F0h+var_768], rax
0x18002069e  mov     rdx, rbx; void *
0x1800206a1  lea     rcx, [rbp+6F0h+lpBaseAddress]; this
0x1800206a5  call    ?MapFile@CAtlFileMappingBase@ATL@@QEAAJPEAX_K1KK@Z; ATL::CAtlFileMappingBase::MapFile(void *,unsigned __int64,unsigned __int64,ulong,ulong)
0x1800206aa  test    eax, eax
0x1800206ac  js      loc_180020938
0x1800206b2  mov     r15, [rbp+6F0h+var_750]
0x1800206b6  cmp     r15, 100000h
0x1800206bd  ja      loc_180020938
0x1800206c3  mov     r12, [rbp+6F0h+lpBaseAddress]
0x1800206c7  mov     [rsp+7F0h+var_798], 0
0x1800206cf  cmp     r15d, 4
0x1800206d3  jnb     loc_18002079F
0x1800206d9  mov     r13b, 1
0x1800206dc  mov     rax, r12
0x1800206df  mov     [rsp+7F0h+var_790], rax
0x1800206e4  mov     [rsp+7F0h+var_780], rax
0x1800206e9  mov     [rsp+7F0h+var_774], edi
0x1800206ed  mov     ecx, 28h ; '('
0x1800206f2  mov     eax, r15d
0x1800206f5  mov     [rsp+7F0h+var_778], r15d
0x1800206fa  add     rax, 30h ; '0'
0x1800206fe  cmp     rax, 0FFB8h
0x180020704  ja      loc_180020801
0x18002070a  mov     rbx, [rsp+7F0h+var_788]
0x18002070f  add     rbx, rcx
0x180020712  lea     r8, [rsp+7F0h+var_780]
0x180020717  lea     rdx, [rbp+6F0h+var_730]
0x18002071b  mov     rcx, rbx
0x18002071e  call    ?find@?$_Tree@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@@std@@@2@AEBU?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,0>>::find(Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator> const &)
0x180020723  mov     rcx, [rbx]
0x180020726  cmp     [rax], rcx
0x180020729  jnz     loc_180020801
0x18002072f  xor     edx, edx; Val
0x180020731  lea     r8d, [rdx+58h]; Size
0x180020735  lea     rcx, [rbp+6F0h+var_720]; void *
0x180020739  call    memset_0
0x18002073e  mov     eax, [rbp+6F0h+var_770]
0x180020741  mov     [rbp+6F0h+var_720], ax
0x180020745  mov     [rbp+6F0h+var_710], r14
0x180020749  movups  xmm0, xmmword ptr cs:PerfTrackMetadataGuid.Data1
0x180020750  movdqu  [rbp+6F0h+var_708], xmm0
0x180020755  neg     r13b
0x180020758  sbb     al, al
0x18002075a  add     al, 21h ; '!'
0x18002075c  mov     [rbp+6F0h+var_71C], al
0x18002075f  xor     eax, eax
0x180020761  mov     [rbp+6F0h+var_71A], ax
0x180020765  mov     [rbp+6F0h+var_71B], al
0x180020768  mov     rax, [rsp+7F0h+var_790]
0x18002076d  mov     [rbp+6F0h+var_6D8], rax
0x180020771  mov     [rbp+6F0h+var_6D0], r15d
0x180020775  mov     eax, [rbp+6F0h+var_76C]
0x180020778  mov     [rbp+6F0h+var_6CC], eax
0x18002077b  mov     rax, [rsp+7F0h+var_788]
0x180020780  mov     rcx, [rax+10h]
0x180020784  mov     rax, [rcx]
0x180020787  xor     r9d, r9d
0x18002078a  xor     r8d, r8d
0x18002078d  lea     rdx, [rbp+6F0h+var_720]
0x180020791  mov     rax, [rax+0C0h]
0x180020798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002079d  jmp     short loc_180020801
0x18002079f  mov     r8, [rsp+7F0h+var_788]
0x1800207a4  mov     r13b, [r8+68h]
0x1800207a8  test    r13b, r13b
0x1800207ab  jnz     loc_1800206DC
0x1800207b1  lea     eax, [r15-4]
0x1800207b5  mov     dword ptr [rsp+7F0h+var_790], eax
0x1800207b9  lea     rbx, [r8+80h]
0x1800207c0  cmp     [rbx+8], eax
0x1800207c3  jnb     loc_1800208B8
0x1800207c9  mov     rcx, [rbx]; Block
0x1800207cc  call    cs:__imp_free
0x1800207d3  nop     dword ptr [rax+rax+00h]
0x1800207d8  mov     qword ptr [rbx], 0
0x1800207df  mov     rax, [rsp+7F0h+var_788]
0x1800207e4  mov     dword ptr [rax+88h], 0
0x1800207ee  mov     edx, r15d
0x1800207f1  mov     rcx, rbx
0x1800207f4  call    ?AllocateBytes@?$CHeapPtrBase@U_TRACE_LOGFILE_HEADER@@VCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x1800207f9  test    al, al
0x1800207fb  jnz     loc_1800208AC
0x180020801  xor     ebx, ebx
0x180020803  test    r12, r12
0x180020806  jz      short loc_180020822
0x180020808  mov     rcx, r12; lpBaseAddress
0x18002080b  call    cs:__imp_UnmapViewOfFile
0x180020812  nop     dword ptr [rax+rax+00h]
0x180020817  test    eax, eax
0x180020819  jnz     short loc_180020822
0x18002081b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180020820  mov     ebx, eax
0x180020822  mov     rcx, [rbp+6F0h+hObject]; hObject
0x180020826  test    rcx, rcx
0x180020829  jz      short loc_180020844
0x18002082b  call    cs:__imp_CloseHandle
0x180020832  nop     dword ptr [rax+rax+00h]
0x180020837  test    eax, eax
0x180020839  jnz     short loc_180020844
0x18002083b  test    ebx, ebx
0x18002083d  js      short loc_180020844
0x18002083f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180020844  mov     r13, [rsp+7F0h+var_7A0]
0x180020849  lea     rcx, [rbp+6F0h+var_768]; this
0x18002084d  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x180020852  mov     r15, [rbp+6F0h+var_760]
0x180020856  mov     r12d, 104h
0x18002085c  lea     rdx, [rbp+6F0h+FindFileData]; lpFindFileData
0x180020860  mov     rcx, r13; hFindFile
0x180020863  call    cs:__imp_FindNextFileW
0x18002086a  nop     dword ptr [rax+rax+00h]
0x18002086f  test    eax, eax
0x180020871  jnz     loc_1800205E7
0x180020877  mov     rcx, r13; hFindFile
0x18002087a  call    cs:__imp_FindClose
0x180020881  nop     dword ptr [rax+rax+00h]
0x180020886  xor     eax, eax
0x180020888  mov     rcx, [rbp+6F0h+var_50]
0x18002088f  xor     rcx, rsp; StackCookie
0x180020892  call    __security_check_cookie
0x180020897  add     rsp, 7B8h
0x18002089e  pop     r15
0x1800208a0  pop     r14
0x1800208a2  pop     r13
0x1800208a4  pop     r12
0x1800208a6  pop     rdi
0x1800208a7  pop     rsi
0x1800208a8  pop     rbx
0x1800208a9  pop     rbp
0x1800208aa  retn
0x1800208ac  mov     r8, [rsp+7F0h+var_788]
0x1800208b1  mov     [r8+88h], r15d
0x1800208b8  mov     rdx, [rbx]
0x1800208bb  add     rdx, 4
0x1800208bf  lea     rcx, [r8+58h]
0x1800208c3  mov     rax, [r8+70h]
0x1800208c7  mov     [rsp+7F0h+var_7B0], rax
0x1800208cc  lea     rax, [rsp+7F0h+var_798]
0x1800208d1  mov     [rsp+7F0h+var_7B8], rax
0x1800208d6  mov     eax, dword ptr [rsp+7F0h+var_790]
0x1800208da  mov     [rsp+7F0h+dwFlagsAndAttributes], eax
0x1800208de  mov     qword ptr [rsp+7F0h+dwCreationDisposition], rdx
0x1800208e3  mov     r9d, r15d
0x1800208e6  mov     r8, r12
0x1800208e9  call    ??RCRtlCompressBuffer@RtlCompression@Performance@@QEBAJGPEBXKPEAXKKPEAK1@Z; Performance::RtlCompression::CRtlCompressBuffer::operator()(ushort,void const *,ulong,void *,ulong,ulong,ulong *,void *)
0x1800208ee  mov     ecx, [rsp+7F0h+var_798]
0x1800208f2  test    eax, eax
0x1800208f4  jnz     short loc_1800208FC
0x1800208f6  cmp     ecx, dword ptr [rsp+7F0h+var_790]
0x1800208fa  jbe     short loc_1800208FF
0x1800208fc  mov     r13b, 1
0x1800208ff  add     ecx, 4
0x180020902  mov     [rsp+7F0h+var_798], ecx
0x180020906  mov     rax, [rbx]
0x180020909  mov     [rax], r15d
0x18002090c  test    r13b, r13b
0x18002090f  jnz     loc_1800206DC
0x180020915  mov     r15d, [rsp+7F0h+var_798]
0x18002091a  mov     rcx, [rbx]
0x18002091d  mov     [rsp+7F0h+var_790], rcx
0x180020922  mov     [rsp+7F0h+var_780], rcx
0x180020927  mov     [rsp+7F0h+var_774], esi
0x18002092b  mov     ecx, 38h ; '8'
0x180020930  mov     eax, r15d
0x180020933  jmp     loc_1800206F5
0x180020938  mov     r12, [rbp+6F0h+hObject]
0x18002093c  mov     r15, [rbp+6F0h+lpBaseAddress]
0x180020940  xor     ebx, ebx
0x180020942  test    r15, r15
0x180020945  jz      short loc_180020961
0x180020947  mov     rcx, r15; lpBaseAddress
0x18002094a  call    cs:__imp_UnmapViewOfFile
0x180020951  nop     dword ptr [rax+rax+00h]
0x180020956  test    eax, eax
0x180020958  jnz     short loc_180020961
0x18002095a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002095f  mov     ebx, eax
0x180020961  test    r12, r12
0x180020964  jz      loc_180020849
0x18002096a  mov     rcx, r12; hObject
0x18002096d  call    cs:__imp_CloseHandle
0x180020974  nop     dword ptr [rax+rax+00h]
0x180020979  test    eax, eax
0x18002097b  jnz     loc_180020849
0x180020981  test    ebx, ebx
0x180020983  js      loc_180020849
0x180020989  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002098e  jmp     loc_180020849
```
