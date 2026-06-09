# EfsDllReprotectFile

- ea: `0x180015370`
- end: `0x180015816`
- name: `EfsDllReprotectFile`
- size: `1190`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000b10c`
- `0x18000b12c`
- `0x18000dc68`
- `0x18000dc8c`
- `0x18000dce4`
- `0x18000dd28`
- `0x18000e0fc`
- `0x18000ef44`
- `0x18000f13c`
- `0x180015294`
- `0x180015370`
- `0x180017570`
- `0x18001dfa4`
- `0x180024fa8`
- `0x1800264e0`
- `0x18004d314`
- `0x18004d998`
- `0x1800612fc`
- `0x18006861c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015617`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015703`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015729`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015617`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015703`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015729`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015625`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015711`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015737`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015625`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015711`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015737`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001539a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001539a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800153ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800153ea`

## string_xrefs

- `0x1800153a9`: `onecoreuap\ds\security\efs\dll\efsapi.cxx`
- `0x180015401`: `onecoreuap\ds\security\efs\dll\efsapi.cxx`
- `0x180015446`: `onecoreuap\ds\security\efs\dll\efsapi.cxx`
- `0x180015472`: `onecoreuap\ds\security\efs\dll\efsapi.cxx`
- `0x1800154b2`: `onecoreuap\ds\security\efs\dll\efsapi.cxx`
- `0x1800154fa`: `onecoreuap\ds\security\efs\dll\efsapi.cxx`
- `0x18001554b`: `onecoreuap\ds\security\efs\dll\efsapi.cxx`
- `0x18001558f`: `onecoreuap\ds\security\efs\dll\efsapi.cxx`
- `0x1800155f8`: `onecoreuap\ds\security\efs\dll\efsapi.cxx`
- `0x1800156ae`: `onecoreuap\ds\security\efs\dll\efsapi.cxx`
- `0x1800156d9`: `onecoreuap\ds\security\efs\dll\efsapi.cxx`
- `0x180015761`: `onecoreuap\ds\security\efs\dll\efsapi.cxx`
- `0x18001579e`: `onecoreuap\ds\security\efs\dll\efsapi.cxx`

## pseudocode

```c
__int64 __fastcall EfsDllReprotectFile(__int64 a1, const WCHAR *a2, __int64 a3)
{
  DWORD FileAttributesW; // eax
  const char *v7; // r9
  HANDLE FileW; // rax
  const char *v10; // r9
  void *v11; // rdi
  unsigned int LastError; // ebx
  int v13; // eax
  unsigned int FileEfsStream; // eax
  __int64 v15; // rdx
  const struct _EFS_DATA_STREAM_HEADER *v16; // rbx
  unsigned int v17; // eax
  int EdpEnforcementLevel; // eax
  unsigned int v19; // esi
  unsigned int v20; // eax
  int v21; // edi
  void *v22; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int i; // ebx
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  void *v29; // rbx
  HANDLE v30; // rax
  void *v31; // rbx
  HANDLE v32; // rax
  int v33; // eax
  const char *v34; // r9
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-49h]
  _BYTE v36[8]; // [rsp+40h] [rbp-29h] BYREF
  const struct _EFS_DATA_STREAM_HEADER *v37; // [rsp+48h] [rbp-21h] BYREF
  unsigned int v38[2]; // [rsp+50h] [rbp-19h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-11h] BYREF
  __int64 v40; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v41; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int16 *v42; // [rsp+70h] [rbp+7h] BYREF
  __int64 v43; // [rsp+78h] [rbp+Fh] BYREF
  int v44; // [rsp+80h] [rbp+17h] BYREF
  __int64 v45; // [rsp+88h] [rbp+1Fh]
  char v46; // [rsp+90h] [rbp+27h]
  HANDLE v47; // [rsp+98h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  unsigned int v49; // [rsp+E8h] [rbp+7Fh] BYREF

  FileAttributesW = GetFileAttributesW(a2);
  if ( FileAttributesW == -1 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x11B7,
             (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsapi.cxx",
             v7);
  FileW = CreateFileW(a2, 0x180u, 7u, 0, 3u, (unsigned __int8)(FileAttributesW & 0x10) << 21, 0);
  v47 = FileW;
  v11 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v44 = 0;
    v45 = 0;
    v46 = 0;
    LOBYTE(v49) = 0;
    v13 = OefsExclusiveOperationContext::Acquire(&v44, FileW, 3, &v49);
    LastError = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11C6,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsapi.cxx",
        (const char *)(unsigned int)v13,
        dwCreationDisposition);
LABEL_7:
      OefsExclusiveOperationContext::~OefsExclusiveOperationContext((OefsExclusiveOperationContext *)&v44);
      goto LABEL_45;
    }
    if ( !(_BYTE)v49 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x11C9,
                    (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsapi.cxx",
                    (const char *)0x20,
                    dwCreationDisposition);
      goto LABEL_7;
    }
    v37 = 0;
    v49 = 0;
    FileEfsStream = EfspGetFileEfsStream(v11);
    if ( FileEfsStream )
    {
      v15 = 4559;
LABEL_12:
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)v15,
                    (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsapi.cxx",
                    (const char *)FileEfsStream,
                    dwCreationDisposition);
LABEL_13:
      EfsDataStreamHeader::~EfsDataStreamHeader((EfsDataStreamHeader *)&v37);
      goto LABEL_7;
    }
    v16 = v37;
    v36[0] = 0;
    FileEfsStream = EfsValidateEfsStream(v37, v49, v36);
    if ( FileEfsStream )
    {
      v15 = 4561;
      goto LABEL_12;
    }
    if ( !v36[0] )
    {
      LastError = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11D2,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsapi.cxx",
        (const char *)0x80070057LL,
        dwCreationDisposition);
      goto LABEL_13;
    }
    *(_QWORD *)v38 = 0;
    v40 = 0;
    v17 = EfspDecryptFek(a1, v16, 0, 1);
    if ( v17 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x11DA,
                    (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsapi.cxx",
                    (const char *)v17,
                    (unsigned int)v38);
LABEL_20:
      EfsDataStreamHeader::~EfsDataStreamHeader((EfsDataStreamHeader *)&v40);
      EfsFileKey::~EfsFileKey((EfsFileKey *)v38);
      goto LABEL_13;
    }
    v49 = 0;
    EdpEnforcementLevel = EdpGetEdpEnforcementLevel(&v49);
    v19 = EdpEnforcementLevel;
    if ( EdpEnforcementLevel >= 0 )
    {
      if ( v49 )
      {
        lpMem = 0;
        v41 = 0;
        v20 = QueryProtectorsSrv(v16, &v41, &lpMem);
        if ( v20 )
        {
          v21 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x11E7,
                  (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsapi.cxx",
                  (const char *)v20,
                  (unsigned int)v38);
LABEL_27:
          v22 = lpMem;
          if ( lpMem )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v22);
            lpMem = 0;
          }
          EfsDataStreamHeader::~EfsDataStreamHeader((EfsDataStreamHeader *)&v40);
          EfsFileKey::~EfsFileKey((EfsFileKey *)v38);
          EfsDataStreamHeader::~EfsDataStreamHeader((EfsDataStreamHeader *)&v37);
          OefsExclusiveOperationContext::~OefsExclusiveOperationContext((OefsExclusiveOperationContext *)&v44);
          LastError = v21;
          goto LABEL_45;
        }
        for ( i = 0; i < v41; ++i )
        {
          LOBYTE(v49) = 0;
          v42 = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v42,
            0);
          v25 = EfsConvertProtectorToExternalId(
                  *(const unsigned __int16 **)(*(_QWORD *)lpMem + 16LL),
                  &v42,
                  (bool *)&v49);
          v19 = v25;
          if ( v25 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11ED,
              (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsapi.cxx",
              (const char *)(unsigned int)v25,
              (int)v38);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
              &v42,
              v28);
            v29 = lpMem;
            if ( lpMem )
            {
              v30 = GetProcessHeap();
              HeapFree(v30, 0, v29);
              lpMem = 0;
            }
            goto LABEL_23;
          }
          if ( (_BYTE)v49 )
          {
            v21 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x11F0,
                    (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsapi.cxx",
                    (const char *)0x32,
                    (unsigned int)v38);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
              &v42,
              v27);
            goto LABEL_27;
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
            &v42,
            v26);
        }
        v31 = lpMem;
        if ( lpMem )
        {
          v32 = GetProcessHeap();
          HeapFree(v32, 0, v31);
        }
      }
      v43 = 0;
      v33 = EfsConstructDescriptorEfsWithFileKey(a1, a3, *(_QWORD *)v38, &v43);
      v19 = v33;
      if ( v33 >= 0 )
      {
        if ( (unsigned int)EfspSetEfsOnFile(v11) )
        {
          EfsDataStreamHeader::~EfsDataStreamHeader((EfsDataStreamHeader *)&v43);
          EfsDataStreamHeader::~EfsDataStreamHeader((EfsDataStreamHeader *)&v40);
          EfsFileKey::~EfsFileKey((EfsFileKey *)v38);
          EfsDataStreamHeader::~EfsDataStreamHeader((EfsDataStreamHeader *)&v37);
          OefsExclusiveOperationContext::~OefsExclusiveOperationContext((OefsExclusiveOperationContext *)&v44);
          LastError = 0;
          goto LABEL_45;
        }
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x11FC,
                      (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsapi.cxx",
                      v34);
        EfsDataStreamHeader::~EfsDataStreamHeader((EfsDataStreamHeader *)&v43);
        goto LABEL_20;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11F8,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsapi.cxx",
        (const char *)(unsigned int)v33,
        (int)v38);
      EfsDataStreamHeader::~EfsDataStreamHeader((EfsDataStreamHeader *)&v43);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11DE,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsapi.cxx",
        (const char *)(unsigned int)EdpEnforcementLevel,
        (int)v38);
    }
LABEL_23:
    EfsDataStreamHeader::~EfsDataStreamHeader((EfsDataStreamHeader *)&v40);
    EfsFileKey::~EfsFileKey((EfsFileKey *)v38);
    EfsDataStreamHeader::~EfsDataStreamHeader((EfsDataStreamHeader *)&v37);
    OefsExclusiveOperationContext::~OefsExclusiveOperationContext((OefsExclusiveOperationContext *)&v44);
    LastError = v19;
    goto LABEL_45;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x11C1,
                (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsapi.cxx",
                v10);
LABEL_45:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v47);
  return LastError;
}

```

## disassembly

```asm
0x180015370  mov     [rsp-8+arg_0], rbx
0x180015375  mov     [rsp-8+arg_8], rsi
0x18001537a  push    rbp
0x18001537b  push    rdi
0x18001537c  push    r12
0x18001537e  push    r14
0x180015380  push    r15
0x180015382  lea     rbp, [rsp-37h]
0x180015387  sub     rsp, 0A0h
0x18001538e  mov     r14, rcx
0x180015391  mov     r15, r8
0x180015394  mov     rcx, rdx; lpFileName
0x180015397  mov     rbx, rdx
0x18001539a  call    cs:__imp_GetFileAttributesW
0x1800153a0  cmp     eax, 0FFFFFFFFh
0x1800153a3  jnz     short loc_1800153BF
0x1800153a5  mov     rcx, [rbp+5Fh]; this
0x1800153a9  lea     r8, aOnecoreuapDsSe_5; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x1800153b0  mov     edx, 11B7h; void *
0x1800153b5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800153ba  jmp     loc_1800157FA
0x1800153bf  xor     r12d, r12d
0x1800153c2  and     eax, 10h
0x1800153c5  shl     eax, 15h
0x1800153c8  xor     r9d, r9d; lpSecurityAttributes
0x1800153cb  mov     [rsp+0C0h+hTemplateFile], r12; hTemplateFile
0x1800153d0  mov     edx, 180h; dwDesiredAccess
0x1800153d5  mov     [rsp+0C0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800153d9  mov     rcx, rbx; lpFileName
0x1800153dc  lea     esi, [r12+3]
0x1800153e1  lea     r8d, [r12+7]; dwShareMode
0x1800153e6  mov     [rsp+0C0h+dwCreationDisposition], esi; int
0x1800153ea  call    cs:__imp_CreateFileW
0x1800153f0  mov     [rbp+57h+var_28], rax
0x1800153f4  mov     rdi, rax
0x1800153f7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800153fb  jnz     short loc_180015419
0x1800153fd  mov     rcx, [rbp+5Fh]; this
0x180015401  lea     r8, aOnecoreuapDsSe_5; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x180015408  mov     edx, 11C1h; void *
0x18001540d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015412  mov     ebx, eax
0x180015414  jmp     loc_1800157EF
0x180015419  lea     r9, [rbp+57h+arg_18]
0x18001541d  mov     [rbp+57h+var_40], r12d
0x180015421  mov     r8d, esi
0x180015424  mov     [rbp+57h+var_38], r12
0x180015428  mov     rdx, rdi
0x18001542b  mov     [rbp+57h+var_30], r12b
0x18001542f  lea     rcx, [rbp+57h+var_40]
0x180015433  mov     byte ptr [rbp+57h+arg_18], r12b
0x180015437  call    ?Acquire@OefsExclusiveOperationContext@@QEAAJPEAXW4_OEFS_EXCLUSIVE_OPERATION@@PEA_N@Z; OefsExclusiveOperationContext::Acquire(void *,_OEFS_EXCLUSIVE_OPERATION,bool *)
0x18001543c  mov     ebx, eax
0x18001543e  test    eax, eax
0x180015440  jns     short loc_180015468
0x180015442  mov     rcx, [rbp+5Fh]; this
0x180015446  lea     r8, aOnecoreuapDsSe_5; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18001544d  mov     r9d, eax; char *
0x180015450  mov     edx, 11C6h; void *
0x180015455  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001545a  lea     rcx, [rbp+57h+var_40]; this
0x18001545e  call    ??1OefsExclusiveOperationContext@@QEAA@XZ; OefsExclusiveOperationContext::~OefsExclusiveOperationContext(void)
0x180015463  jmp     loc_1800157EF
0x180015468  cmp     byte ptr [rbp+57h+arg_18], r12b
0x18001546c  jnz     short loc_18001548D
0x18001546e  mov     rcx, [rbp+5Fh]; this
0x180015472  lea     r8, aOnecoreuapDsSe_5; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x180015479  mov     r9d, 20h ; ' '; char *
0x18001547f  mov     edx, 11C9h; void *
0x180015484  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180015489  mov     ebx, eax
0x18001548b  jmp     short loc_18001545A
0x18001548d  lea     r8, [rbp+57h+arg_18]
0x180015491  mov     [rbp+57h+var_78], r12
0x180015495  lea     rdx, [rbp+57h+var_78]
0x180015499  mov     [rbp+57h+arg_18], r12d
0x18001549d  mov     rcx, rdi; FileHandle
0x1800154a0  call    EfspGetFileEfsStream
0x1800154a5  test    eax, eax
0x1800154a7  jz      short loc_1800154CE
0x1800154a9  mov     edx, 11CFh; void *
0x1800154ae  mov     rcx, [rbp+5Fh]; this
0x1800154b2  lea     r8, aOnecoreuapDsSe_5; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x1800154b9  mov     r9d, eax; char *
0x1800154bc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800154c1  mov     ebx, eax
0x1800154c3  lea     rcx, [rbp+57h+var_78]; this
0x1800154c7  call    ??1EfsDataStreamHeader@@QEAA@XZ; EfsDataStreamHeader::~EfsDataStreamHeader(void)
0x1800154cc  jmp     short loc_18001545A
0x1800154ce  mov     rbx, [rbp+57h+var_78]
0x1800154d2  lea     r8, [rbp+57h+var_80]
0x1800154d6  mov     edx, [rbp+57h+arg_18]
0x1800154d9  mov     rcx, rbx
0x1800154dc  mov     [rbp+57h+var_80], r12b
0x1800154e0  call    EfsValidateEfsStream
0x1800154e5  test    eax, eax
0x1800154e7  jz      short loc_1800154F0
0x1800154e9  mov     edx, 11D1h
0x1800154ee  jmp     short loc_1800154AE
0x1800154f0  cmp     [rbp+57h+var_80], r12b
0x1800154f4  jnz     short loc_180015515
0x1800154f6  mov     rcx, [rbp+5Fh]; this
0x1800154fa  lea     r8, aOnecoreuapDsSe_5; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x180015501  mov     ebx, 80070057h
0x180015506  mov     edx, 11D2h; void *
0x18001550b  mov     r9d, ebx; char *
0x18001550e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015513  jmp     short loc_1800154C3
0x180015515  lea     rax, [rbp+57h+var_60]
0x180015519  mov     qword ptr [rbp+57h+var_70], r12
0x18001551d  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rax
0x180015522  mov     r9d, 1
0x180015528  lea     rax, [rbp+57h+var_70]
0x18001552c  mov     [rbp+57h+var_60], r12
0x180015530  xor     r8d, r8d
0x180015533  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; int
0x180015538  mov     rdx, rbx
0x18001553b  mov     rcx, r14
0x18001553e  call    ?EfspDecryptFek@@YAJPEAU_EFS_USER_INFO@@PEAU_EFS_DATA_STREAM_HEADER@@PEAU_UNICODE_STRING@@W4EfspDecryptFekFlags@@PEAPEAU_EFS_FILE_KEY@@PEAPEAU2@@Z; EfspDecryptFek(_EFS_USER_INFO *,_EFS_DATA_STREAM_HEADER *,_UNICODE_STRING *,EfspDecryptFekFlags,_EFS_FILE_KEY * *,_EFS_DATA_STREAM_HEADER * *)
0x180015543  test    eax, eax
0x180015545  jz      short loc_180015578
0x180015547  mov     rcx, [rbp+5Fh]; this
0x18001554b  lea     r8, aOnecoreuapDsSe_5; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x180015552  mov     r9d, eax; char *
0x180015555  mov     edx, 11DAh; void *
0x18001555a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001555f  mov     ebx, eax
0x180015561  lea     rcx, [rbp+57h+var_60]; this
0x180015565  call    ??1EfsDataStreamHeader@@QEAA@XZ; EfsDataStreamHeader::~EfsDataStreamHeader(void)
0x18001556a  lea     rcx, [rbp+57h+var_70]; this
0x18001556e  call    ??1EfsFileKey@@QEAA@XZ; EfsFileKey::~EfsFileKey(void)
0x180015573  jmp     loc_1800154C3
0x180015578  lea     rcx, [rbp+57h+arg_18]
0x18001557c  mov     [rbp+57h+arg_18], r12d
0x180015580  call    EdpGetEdpEnforcementLevel
0x180015585  mov     esi, eax
0x180015587  test    eax, eax
0x180015589  jns     short loc_1800155CE
0x18001558b  mov     rcx, [rbp+5Fh]; this
0x18001558f  lea     r8, aOnecoreuapDsSe_5; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x180015596  mov     r9d, eax; char *
0x180015599  mov     edx, 11DEh; void *
0x18001559e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800155a3  lea     rcx, [rbp+57h+var_60]; this
0x1800155a7  call    ??1EfsDataStreamHeader@@QEAA@XZ; EfsDataStreamHeader::~EfsDataStreamHeader(void)
0x1800155ac  lea     rcx, [rbp+57h+var_70]; this
0x1800155b0  call    ??1EfsFileKey@@QEAA@XZ; EfsFileKey::~EfsFileKey(void)
0x1800155b5  lea     rcx, [rbp+57h+var_78]; this
0x1800155b9  call    ??1EfsDataStreamHeader@@QEAA@XZ; EfsDataStreamHeader::~EfsDataStreamHeader(void)
0x1800155be  lea     rcx, [rbp+57h+var_40]; this
0x1800155c2  call    ??1OefsExclusiveOperationContext@@QEAA@XZ; OefsExclusiveOperationContext::~OefsExclusiveOperationContext(void)
0x1800155c7  mov     ebx, esi
0x1800155c9  jmp     loc_1800157EF
0x1800155ce  cmp     [rbp+57h+arg_18], r12d
0x1800155d2  jz      loc_18001573D
0x1800155d8  lea     r8, [rbp+57h+lpMem]
0x1800155dc  mov     [rbp+57h+lpMem], r12
0x1800155e0  lea     rdx, [rbp+57h+var_58]
0x1800155e4  mov     [rbp+57h+var_58], r12d
0x1800155e8  mov     rcx, rbx
0x1800155eb  call    QueryProtectorsSrv
0x1800155f0  test    eax, eax
0x1800155f2  jz      short loc_18001565A
0x1800155f4  mov     rcx, [rbp+5Fh]; this
0x1800155f8  lea     r8, aOnecoreuapDsSe_5; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x1800155ff  mov     r9d, eax; char *
0x180015602  mov     edx, 11E7h; void *
0x180015607  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001560c  mov     edi, eax
0x18001560e  mov     rbx, [rbp+57h+lpMem]
0x180015612  test    rbx, rbx
0x180015615  jz      short loc_18001562F
0x180015617  call    cs:__imp_GetProcessHeap
0x18001561d  mov     r8, rbx; lpMem
0x180015620  xor     edx, edx; dwFlags
0x180015622  mov     rcx, rax; hHeap
0x180015625  call    cs:__imp_HeapFree
0x18001562b  mov     [rbp+57h+lpMem], r12
0x18001562f  lea     rcx, [rbp+57h+var_60]; this
0x180015633  call    ??1EfsDataStreamHeader@@QEAA@XZ; EfsDataStreamHeader::~EfsDataStreamHeader(void)
0x180015638  lea     rcx, [rbp+57h+var_70]; this
0x18001563c  call    ??1EfsFileKey@@QEAA@XZ; EfsFileKey::~EfsFileKey(void)
0x180015641  lea     rcx, [rbp+57h+var_78]; this
0x180015645  call    ??1EfsDataStreamHeader@@QEAA@XZ; EfsDataStreamHeader::~EfsDataStreamHeader(void)
0x18001564a  lea     rcx, [rbp+57h+var_40]; this
0x18001564e  call    ??1OefsExclusiveOperationContext@@QEAA@XZ; OefsExclusiveOperationContext::~OefsExclusiveOperationContext(void)
0x180015653  mov     ebx, edi
0x180015655  jmp     loc_1800157EF
0x18001565a  mov     ebx, r12d
0x18001565d  cmp     ebx, [rbp+57h+var_58]
0x180015660  jnb     loc_180015720
0x180015666  xor     edx, edx
0x180015668  mov     byte ptr [rbp+57h+arg_18], r12b
0x18001566c  lea     rcx, [rbp+57h+var_50]
0x180015670  mov     [rbp+57h+var_50], r12
0x180015674  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015679  mov     rax, [rbp+57h+lpMem]
0x18001567d  lea     r8, [rbp+57h+arg_18]; bool *
0x180015681  lea     rdx, [rbp+57h+var_50]; unsigned __int16 **
0x180015685  mov     rcx, [rax]
0x180015688  mov     rcx, [rcx+10h]; unsigned __int16 *
0x18001568c  call    ?EfsConvertProtectorToExternalId@@YAJPEBGPEAPEAGPEA_N@Z; EfsConvertProtectorToExternalId(ushort const *,ushort * *,bool *)
0x180015691  mov     esi, eax
0x180015693  test    eax, eax
0x180015695  js      short loc_1800156D5
0x180015697  cmp     byte ptr [rbp+57h+arg_18], r12b
0x18001569b  jnz     short loc_1800156AA
0x18001569d  lea     rcx, [rbp+57h+var_50]
0x1800156a1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800156a6  inc     ebx
0x1800156a8  jmp     short loc_18001565D
0x1800156aa  mov     rcx, [rbp+5Fh]; this
0x1800156ae  lea     r8, aOnecoreuapDsSe_5; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x1800156b5  mov     r9d, 32h ; '2'; char *
0x1800156bb  mov     edx, 11F0h; void *
0x1800156c0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800156c5  lea     rcx, [rbp+57h+var_50]
0x1800156c9  mov     edi, eax
0x1800156cb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800156d0  jmp     loc_18001560E
0x1800156d5  mov     rcx, [rbp+5Fh]; this
0x1800156d9  lea     r8, aOnecoreuapDsSe_5; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x1800156e0  mov     r9d, esi; char *
0x1800156e3  mov     edx, 11EDh; void *
0x1800156e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800156ed  lea     rcx, [rbp+57h+var_50]
0x1800156f1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800156f6  mov     rbx, [rbp+57h+lpMem]
0x1800156fa  test    rbx, rbx
0x1800156fd  jz      loc_1800155A3
0x180015703  call    cs:__imp_GetProcessHeap
0x180015709  mov     r8, rbx; lpMem
0x18001570c  xor     edx, edx; dwFlags
0x18001570e  mov     rcx, rax; hHeap
0x180015711  call    cs:__imp_HeapFree
0x180015717  mov     [rbp+57h+lpMem], r12
0x18001571b  jmp     loc_1800155A3
0x180015720  mov     rbx, [rbp+57h+lpMem]
0x180015724  test    rbx, rbx
0x180015727  jz      short loc_18001573D
0x180015729  call    cs:__imp_GetProcessHeap
0x18001572f  mov     r8, rbx; lpMem
0x180015732  xor     edx, edx; dwFlags
0x180015734  mov     rcx, rax; hHeap
0x180015737  call    cs:__imp_HeapFree
0x18001573d  mov     rbx, qword ptr [rbp+57h+var_70]
0x180015741  lea     r9, [rbp+57h+var_48]
0x180015745  mov     r8, rbx
0x180015748  mov     [rbp+57h+var_48], r12
0x18001574c  mov     rdx, r15
0x18001574f  mov     rcx, r14
0x180015752  call    EfsConstructDescriptorEfsWithFileKey
0x180015757  mov     esi, eax
0x180015759  test    eax, eax
0x18001575b  jns     short loc_180015783
0x18001575d  mov     rcx, [rbp+5Fh]; this
0x180015761  lea     r8, aOnecoreuapDsSe_5; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x180015768  mov     r9d, eax; char *
0x18001576b  mov     edx, 11F8h; void *
0x180015770  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015775  lea     rcx, [rbp+57h+var_48]; this
0x180015779  call    ??1EfsDataStreamHeader@@QEAA@XZ; EfsDataStreamHeader::~EfsDataStreamHeader(void)
0x18001577e  jmp     loc_1800155A3
0x180015783  mov     r8, [rbx+8]
0x180015787  xor     r9d, r9d
0x18001578a  mov     rdx, [rbp+57h+var_48]
0x18001578e  mov     rcx, rdi; hFile
0x180015791  call    EfspSetEfsOnFile
0x180015796  test    eax, eax
0x180015798  jnz     short loc_1800157BF
0x18001579a  mov     rcx, [rbp+5Fh]; this
0x18001579e  lea     r8, aOnecoreuapDsSe_5; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x1800157a5  mov     edx, 11FCh; void *
0x1800157aa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800157af  lea     rcx, [rbp+57h+var_48]; this
0x1800157b3  mov     ebx, eax
0x1800157b5  call    ??1EfsDataStreamHeader@@QEAA@XZ; EfsDataStreamHeader::~EfsDataStreamHeader(void)
0x1800157ba  jmp     loc_180015561
0x1800157bf  lea     rcx, [rbp+57h+var_48]; this
0x1800157c3  call    ??1EfsDataStreamHeader@@QEAA@XZ; EfsDataStreamHeader::~EfsDataStreamHeader(void)
0x1800157c8  lea     rcx, [rbp+57h+var_60]; this
0x1800157cc  call    ??1EfsDataStreamHeader@@QEAA@XZ; EfsDataStreamHeader::~EfsDataStreamHeader(void)
0x1800157d1  lea     rcx, [rbp+57h+var_70]; this
0x1800157d5  call    ??1EfsFileKey@@QEAA@XZ; EfsFileKey::~EfsFileKey(void)
0x1800157da  lea     rcx, [rbp+57h+var_78]; this
0x1800157de  call    ??1EfsDataStreamHeader@@QEAA@XZ; EfsDataStreamHeader::~EfsDataStreamHeader(void)
0x1800157e3  lea     rcx, [rbp+57h+var_40]; this
0x1800157e7  call    ??1OefsExclusiveOperationContext@@QEAA@XZ; OefsExclusiveOperationContext::~OefsExclusiveOperationContext(void)
0x1800157ec  mov     ebx, r12d
0x1800157ef  lea     rcx, [rbp+57h+var_28]
0x1800157f3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800157f8  mov     eax, ebx
0x1800157fa  lea     r11, [rsp+0C0h+var_20]
0x180015802  mov     rbx, [r11+30h]
0x180015806  mov     rsi, [r11+38h]
0x18001580a  mov     rsp, r11
0x18001580d  pop     r15
0x18001580f  pop     r14
0x180015811  pop     r12
0x180015813  pop     rdi
  ... truncated ...
```
