# CDirFltr::Init(wchar_t const *,ulong,_FILETIME const &,_FILETIME const &,_FILETIME const &,_FILETIME const &,int)

- ea: `0x180006660`
- end: `0x180006abf`
- name: `?Init@CDirFltr@@QEAAJPEB_WKAEBU_FILETIME@@111H@Z`
- size: `1119`
- prototype: `signed int __fastcall(CDirFltr *this, const wchar_t *, int, const struct _FILETIME *, const struct _FILETIME *, const struct _FILETIME *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x1800064a0`

## callees

- `0x180004e60`
- `0x180004f60`
- `0x1800055b0`
- `0x180006430`
- `0x180006660`
- `0x180008450`
- `0x18000a0a0`
- `0x18000a210`
- `0x18000bf0c`
- `0x18000d84c`
- `0x18000fcd0`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180006759`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180006796`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180006759`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180006796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000693c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000699d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000693c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000699d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800069b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800069b0`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800066ba`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800066ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069a8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800066e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800066e1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006987`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006987`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800069f8`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180006a1f`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800069f8`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180006a1f`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800068cd`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000692c`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800068cd`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000692c`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800068ac`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18000690b`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800068ac`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18000690b`

## pseudocode

```c
signed int __fastcall CDirFltr::Init(
        CDirFltr *this,
        const wchar_t *a2,
        int a3,
        const struct _FILETIME *a4,
        const struct _FILETIME *a5,
        const struct _FILETIME *a6)
{
  int v8; // eax
  wchar_t *v9; // rax
  __int64 i; // rdx
  wchar_t *v11; // rax
  LPVOID v12; // rax
  void *v13; // rcx
  signed int result; // eax
  bool v15; // sf
  LPVOID v16; // rax
  void *v17; // rcx
  bool v18; // sf
  HANDLE *v19; // r14
  char *FileW; // rbp
  char *v21; // r15
  DWORD LastError; // ebx
  signed int v23; // ebx
  DWORD v24; // eax
  signed int v25; // eax
  _DWORD v26[2]; // [rsp+40h] [rbp-118h] BYREF
  __int64 v27; // [rsp+48h] [rbp-110h]
  _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-108h] BYREF
  _BYTE v29[8]; // [rsp+80h] [rbp-D8h] BYREF
  _WORD *v30; // [rsp+88h] [rbp-D0h]
  int v31; // [rsp+94h] [rbp-C4h]

  *((struct _FILETIME *)this + 10) = *a4;
  *((struct _FILETIME *)this + 11) = *a5;
  *((struct _FILETIME *)this + 12) = *a6;
  *((_DWORD *)this + 16) = a3;
  *((_DWORD *)this + 18) = GetSystemDefaultLCID();
  *((_DWORD *)this + 19) = 255;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  *((_DWORD *)this + 110) = 32 * SystemInfo.dwPageSize;
  *((_DWORD *)this + 168) = 0;
  (*(void (__fastcall **)(char *, const wchar_t *, _QWORD, __int64))(*((_QWORD *)this + 34) + 32LL))(
    (char *)this + 272,
    a2,
    0,
    0xFFFFFFFFLL);
  v8 = *((_DWORD *)this + 73);
  if ( !v8 || *(_WORD *)(*((_QWORD *)this + 35) + 2LL * (unsigned int)(v8 - 1)) != 92 )
    CLMString::Append((CDirFltr *)((char *)this + 272), L"\\", 0xFFFFFFFF);
  if ( *((_DWORD *)this + 73) )
  {
    v9 = wcschr(*((const wchar_t **)this + 35), 0x2Fu);
    if ( v9 )
    {
      for ( i = ((__int64)v9 - *((_QWORD *)this + 35)) >> 1;
            (_DWORD)i != -1;
            LODWORD(i) = ((__int64)v11 - *((_QWORD *)this + 35)) >> 1 )
      {
        *(_WORD *)(*((_QWORD *)this + 35) + 2LL * (unsigned int)i) = 92;
        if ( (unsigned int)(i + 1) >= *((_DWORD *)this + 73) )
          break;
        v11 = wcschr((const wchar_t *)(*((_QWORD *)this + 35) + 2LL * (unsigned int)(i + 1)), 0x2Fu);
        if ( !v11 )
          break;
      }
    }
  }
  if ( *((_DWORD *)this + 73) >= 0x104u )
  {
    TLMString<64,64,32767>::TLMString<64,64,32767>((CLMString *)v29);
    if ( *v30 == 92 && v30[1] == 92 )
    {
      if ( v30[2] != 63 && v30[3] != 92 )
      {
        CLMString::operator=((char *)this + 272, L"\\\\?\\");
        CLMString::Mid(v29, v26, 1, (unsigned int)(v31 - 1));
        CLMString::Append(
          (CDirFltr *)((char *)this + 272),
          (const wchar_t *)(*(_QWORD *)(v27 + 8) + 2LL * v26[0]),
          v26[1]);
      }
    }
    else
    {
      CLMString::operator=((char *)this + 272, L"\\\\?\\");
      CLMString::operator+=((char *)this + 272, v29);
    }
    TLMString<64,64,32767>::~TLMString<64,64,32767>(v29);
  }
  (*(void (__fastcall **)(char *, _QWORD, _QWORD, __int64))(*((_QWORD *)this + 13) + 32LL))(
    (char *)this + 104,
    *((_QWORD *)this + 35),
    0,
    0xFFFFFFFFLL);
  *((_DWORD *)this + 66) = *((_DWORD *)this + 31);
  v12 = VirtualAlloc(0, *((unsigned int *)this + 110), 0x1000u, 4u);
  v13 = (void *)*((_QWORD *)this + 56);
  *((_QWORD *)this + 56) = v12;
  if ( v13 )
    VirtualFree(v13, 0, 0x8000u);
  if ( *((_QWORD *)this + 56) )
    goto LABEL_29;
  result = GetLastError();
  v15 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v15 = result < 0;
  }
  if ( !v15 )
  {
LABEL_29:
    v16 = VirtualAlloc(0, *((unsigned int *)this + 110), 0x1000u, 4u);
    v17 = (void *)*((_QWORD *)this + 58);
    *((_QWORD *)this + 58) = v16;
    if ( v17 )
      VirtualFree(v17, 0, 0x8000u);
    if ( *((_QWORD *)this + 58) )
      goto LABEL_30;
    result = GetLastError();
    v18 = result < 0;
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v18 = result < 0;
    }
    if ( !v18 )
    {
LABEL_30:
      v19 = (HANDLE *)((char *)this + 432);
      FileW = (char *)CreateFileW(*((LPCWSTR *)this + 35), 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
      v21 = (char *)*((_QWORD *)this + 54);
      if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        CloseHandle(v21);
        SetLastError(LastError);
      }
      *v19 = FileW;
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        v24 = GetLastError();
        result = HResultFromFileStatus(v24, (char *)this + 272);
        v23 = result;
        if ( result < 0 )
          return result;
      }
      else
      {
        v23 = 0;
      }
      if ( GetFileInformationByHandleEx(*v19, FileFullDirectoryInfo, *((LPVOID *)this + 56), *((_DWORD *)this + 110)) )
      {
        *((_BYTE *)this + 456) = 0;
        if ( GetFileInformationByHandleEx(*v19, FileFullDirectoryInfo, *((LPVOID *)this + 58), *((_DWORD *)this + 110)) )
        {
          *((_BYTE *)this + 472) = 0;
          goto LABEL_44;
        }
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          (char *)this + 432,
          0);
        v25 = GetLastError();
        if ( v25 == 18 )
        {
LABEL_44:
          if ( v23 < 0 )
            return v23;
          else
            return CDirFltr::FindNextRecord(this);
        }
      }
      else
      {
        *((_BYTE *)this + 456) = 1;
        *((_BYTE *)this + 472) = 1;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          (char *)this + 432,
          0);
        v25 = GetLastError();
        if ( ((v25 - 2) & 0xFFFFFFEF) == 0 )
          goto LABEL_44;
      }
      if ( v25 > 0 )
        v23 = (unsigned __int16)v25 | 0x80070000;
      else
        v23 = v25;
      goto LABEL_44;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006660  mov     [rsp+arg_10], rbx
0x180006665  mov     [rsp+arg_18], rbp
0x18000666a  push    rsi
0x18000666b  push    rdi
0x18000666c  push    r12
0x18000666e  push    r14
0x180006670  push    r15
0x180006672  sub     rsp, 130h
0x180006679  mov     rax, cs:__security_cookie
0x180006680  xor     rax, rsp
0x180006683  mov     [rsp+158h+var_38], rax
0x18000668b  mov     rbx, rdx
0x18000668e  mov     rsi, rcx
0x180006691  mov     rax, [r9]
0x180006694  mov     [rcx+50h], rax
0x180006698  mov     rax, [rsp+158h+arg_20]
0x1800066a0  mov     rcx, [rax]
0x1800066a3  mov     [rsi+58h], rcx
0x1800066a7  mov     rax, [rsp+158h+arg_28]
0x1800066af  mov     rcx, [rax]
0x1800066b2  mov     [rsi+60h], rcx
0x1800066b6  mov     [rsi+40h], r8d
0x1800066ba  call    cs:__imp_GetSystemDefaultLCID
0x1800066c0  mov     [rsi+48h], eax
0x1800066c3  mov     dword ptr [rsi+4Ch], 0FFh
0x1800066ca  xorps   xmm0, xmm0
0x1800066cd  movups  xmmword ptr [rsp+158h+SystemInfo], xmm0
0x1800066d2  movups  xmmword ptr [rsp+158h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800066d7  movups  xmmword ptr [rsp+158h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800066dc  lea     rcx, [rsp+158h+SystemInfo]; lpSystemInfo
0x1800066e1  call    cs:__imp_GetSystemInfo
0x1800066e7  mov     eax, [rsp+158h+SystemInfo.dwPageSize]
0x1800066eb  shl     eax, 5
0x1800066ee  mov     [rsi+1B8h], eax
0x1800066f4  xor     r12d, r12d
0x1800066f7  mov     [rsi+2A0h], r12d
0x1800066fe  lea     rdi, [rsi+110h]
0x180006705  mov     rax, [rdi]
0x180006708  mov     r9d, 0FFFFFFFFh
0x18000670e  xor     r8d, r8d
0x180006711  mov     rdx, rbx
0x180006714  mov     rcx, rdi
0x180006717  mov     rax, [rax+20h]
0x18000671b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006720  mov     eax, [rdi+14h]
0x180006723  test    eax, eax
0x180006725  jz      short loc_180006735
0x180006727  lea     ecx, [rax-1]
0x18000672a  mov     rax, [rdi+8]
0x18000672e  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x180006733  jz      short loc_18000674A
0x180006735  mov     r8d, 0FFFFFFFFh; unsigned int
0x18000673b  lea     rdx, asc_18002B500; "\\"
0x180006742  mov     rcx, rdi; this
0x180006745  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x18000674a  cmp     [rdi+14h], r12d
0x18000674e  jbe     short loc_1800067AF
0x180006750  mov     edx, 2Fh ; '/'; Ch
0x180006755  mov     rcx, [rdi+8]; Str
0x180006759  call    cs:__imp_wcschr
0x18000675f  mov     rdx, rax
0x180006762  test    rax, rax
0x180006765  jz      short loc_1800067AF
0x180006767  sub     rdx, [rdi+8]
0x18000676b  sar     rdx, 1
0x18000676e  cmp     edx, 0FFFFFFFFh
0x180006771  jz      short loc_1800067AF
0x180006773  mov     ecx, edx
0x180006775  mov     rax, [rdi+8]
0x180006779  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x18000677f  lea     eax, [rdx+1]
0x180006782  cmp     eax, [rdi+14h]
0x180006785  jnb     short loc_1800067AF
0x180006787  mov     edx, 2Fh ; '/'; Ch
0x18000678c  mov     ecx, eax
0x18000678e  mov     rax, [rdi+8]
0x180006792  lea     rcx, [rax+rcx*2]; Str
0x180006796  call    cs:__imp_wcschr
0x18000679c  test    rax, rax
0x18000679f  jz      short loc_1800067AF
0x1800067a1  sub     rax, [rdi+8]
0x1800067a5  sar     rax, 1
0x1800067a8  mov     edx, eax
0x1800067aa  cmp     eax, 0FFFFFFFFh
0x1800067ad  jnz     short loc_180006773
0x1800067af  cmp     dword ptr [rdi+14h], 104h
0x1800067b6  jb      loc_18000686F
0x1800067bc  mov     rdx, rdi
0x1800067bf  lea     rcx, [rsp+158h+var_D8]
0x1800067c7  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@AEBV0@@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(TLMString<64,64,32767> const &)
0x1800067cc  nop
0x1800067cd  mov     rax, [rsp+158h+var_D0]
0x1800067d5  cmp     word ptr [rax], 5Ch ; '\'
0x1800067d9  jnz     short loc_180006842
0x1800067db  cmp     word ptr [rax+2], 5Ch ; '\'
0x1800067e0  jnz     short loc_180006842
0x1800067e2  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800067e7  jz      short loc_180006862
0x1800067e9  cmp     word ptr [rax+6], 5Ch ; '\'
0x1800067ee  jz      short loc_180006862
0x1800067f0  lea     rdx, String2; "\\\\?\\"
0x1800067f7  mov     rcx, rdi
0x1800067fa  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800067ff  mov     r9d, [rsp+158h+var_C4]
0x180006807  dec     r9d
0x18000680a  mov     r8d, 1
0x180006810  lea     rdx, [rsp+158h+var_118]
0x180006815  lea     rcx, [rsp+158h+var_D8]
0x18000681d  call    ?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z; CLMString::Mid(uint,uint)
0x180006822  mov     edx, [rsp+158h+var_118]
0x180006826  mov     rax, [rsp+158h+var_110]
0x18000682b  mov     rcx, [rax+8]
0x18000682f  lea     rdx, [rcx+rdx*2]; wchar_t *
0x180006833  mov     r8d, [rsp+158h+var_114]; unsigned int
0x180006838  mov     rcx, rdi; this
0x18000683b  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x180006840  jmp     short loc_180006862
0x180006842  lea     rdx, String2; "\\\\?\\"
0x180006849  mov     rcx, rdi
0x18000684c  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180006851  lea     rdx, [rsp+158h+var_D8]
0x180006859  mov     rcx, rdi
0x18000685c  call    ??YCLMString@@QEAAXAEBV0@@Z; CLMString::operator+=(CLMString const &)
0x180006861  nop
0x180006862  lea     rcx, [rsp+158h+var_D8]
0x18000686a  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x18000686f  lea     rcx, [rsi+68h]
0x180006873  mov     rax, [rcx]
0x180006876  mov     r9d, 0FFFFFFFFh
0x18000687c  xor     r8d, r8d
0x18000687f  mov     rdx, [rsi+118h]
0x180006886  mov     rax, [rax+20h]
0x18000688a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000688f  mov     eax, [rsi+7Ch]
0x180006892  mov     [rsi+108h], eax
0x180006898  mov     edx, [rsi+1B8h]; dwSize
0x18000689e  xor     ecx, ecx; lpAddress
0x1800068a0  mov     r9d, 4; flProtect
0x1800068a6  mov     r8d, 1000h; flAllocationType
0x1800068ac  call    cs:__imp_VirtualAlloc
0x1800068b2  mov     rcx, [rsi+1C0h]; lpAddress
0x1800068b9  mov     [rsi+1C0h], rax
0x1800068c0  test    rcx, rcx
0x1800068c3  jz      short loc_1800068D3
0x1800068c5  xor     edx, edx; dwSize
0x1800068c7  mov     r8d, 8000h; dwFreeType
0x1800068cd  call    cs:__imp_VirtualFree
0x1800068d3  cmp     qword ptr [rsi+1C0h], 0
0x1800068db  jnz     short loc_1800068F7
0x1800068dd  call    cs:__imp_GetLastError
0x1800068e3  test    eax, eax
0x1800068e5  jle     short loc_1800068F1
0x1800068e7  movzx   eax, ax
0x1800068ea  or      eax, 80070000h
0x1800068ef  test    eax, eax
0x1800068f1  js      loc_180006A93
0x1800068f7  mov     edx, [rsi+1B8h]; dwSize
0x1800068fd  xor     ecx, ecx; lpAddress
0x1800068ff  mov     r9d, 4; flProtect
0x180006905  mov     r8d, 1000h; flAllocationType
0x18000690b  call    cs:__imp_VirtualAlloc
0x180006911  mov     rcx, [rsi+1D0h]; lpAddress
0x180006918  mov     [rsi+1D0h], rax
0x18000691f  test    rcx, rcx
0x180006922  jz      short loc_180006932
0x180006924  xor     edx, edx; dwSize
0x180006926  mov     r8d, 8000h; dwFreeType
0x18000692c  call    cs:__imp_VirtualFree
0x180006932  cmp     qword ptr [rsi+1D0h], 0
0x18000693a  jnz     short loc_180006956
0x18000693c  call    cs:__imp_GetLastError
0x180006942  test    eax, eax
0x180006944  jle     short loc_180006950
0x180006946  movzx   eax, ax
0x180006949  or      eax, 80070000h
0x18000694e  test    eax, eax
0x180006950  js      loc_180006A93
0x180006956  lea     r14, [rsi+1B0h]
0x18000695d  mov     [rsp+158h+hTemplateFile], r12; hTemplateFile
0x180006962  mov     [rsp+158h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000696a  mov     [rsp+158h+dwCreationDisposition], 3; dwCreationDisposition
0x180006972  xor     r9d, r9d; lpSecurityAttributes
0x180006975  mov     edx, 80000000h; dwDesiredAccess
0x18000697a  mov     r8d, 7; dwShareMode
0x180006980  mov     rcx, [rsi+118h]; lpFileName
0x180006987  call    cs:__imp_CreateFileW
0x18000698d  mov     rbp, rax
0x180006990  mov     r15, [r14]
0x180006993  lea     rcx, [r15-1]
0x180006997  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000699b  ja      short loc_1800069B6
0x18000699d  call    cs:__imp_GetLastError
0x1800069a3  mov     ebx, eax
0x1800069a5  mov     rcx, r15; hObject
0x1800069a8  call    cs:__imp_CloseHandle
0x1800069ae  mov     ecx, ebx; dwErrCode
0x1800069b0  call    cs:__imp_SetLastError
0x1800069b6  mov     [r14], rbp
0x1800069b9  lea     rax, [rbp-1]
0x1800069bd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800069c1  ja      short loc_1800069C8
0x1800069c3  mov     ebx, r12d
0x1800069c6  jmp     short loc_1800069E2
0x1800069c8  call    cs:__imp_GetLastError
0x1800069ce  mov     ecx, eax
0x1800069d0  mov     rdx, rdi
0x1800069d3  call    ?HResultFromFileStatus@@YAJKAEAV?$TLMString@$0EA@$0EA@$0HPPP@@@@Z; HResultFromFileStatus(ulong,TLMString<64,64,32767> &)
0x1800069d8  mov     ebx, eax
0x1800069da  test    eax, eax
0x1800069dc  js      loc_180006A93
0x1800069e2  mov     r9d, [rsi+1B8h]; dwBufferSize
0x1800069e9  mov     r8, [rsi+1C0h]; lpFileInformation
0x1800069f0  mov     edx, 0Eh; FileInformationClass
0x1800069f5  mov     rcx, [r14]; hFile
0x1800069f8  call    cs:__imp_GetFileInformationByHandleEx
0x1800069fe  test    eax, eax
0x180006a00  jz      short loc_180006A49
0x180006a02  mov     byte ptr [rsi+1C8h], 0
0x180006a09  mov     r9d, [rsi+1B8h]; dwBufferSize
0x180006a10  mov     r8, [rsi+1D0h]; lpFileInformation
0x180006a17  mov     edx, 0Eh; FileInformationClass
0x180006a1c  mov     rcx, [r14]; hFile
0x180006a1f  call    cs:__imp_GetFileInformationByHandleEx
0x180006a25  test    eax, eax
0x180006a27  jz      short loc_180006A32
0x180006a29  mov     byte ptr [rsi+1D8h], 0
0x180006a30  jmp     short loc_180006A83
0x180006a32  xor     edx, edx
0x180006a34  mov     rcx, r14
0x180006a37  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180006a3c  call    cs:__imp_GetLastError
0x180006a42  cmp     eax, 12h
0x180006a45  jnz     short loc_180006A72
0x180006a47  jmp     short loc_180006A83
0x180006a49  mov     byte ptr [rsi+1C8h], 1
0x180006a50  mov     byte ptr [rsi+1D8h], 1
0x180006a57  xor     edx, edx
0x180006a59  mov     rcx, r14
0x180006a5c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180006a61  call    cs:__imp_GetLastError
0x180006a67  lea     ecx, [rax-2]
0x180006a6a  test    ecx, 0FFFFFFEFh
0x180006a70  jz      short loc_180006A83
0x180006a72  test    eax, eax
0x180006a74  jg      short loc_180006A7A
0x180006a76  mov     ebx, eax
0x180006a78  jmp     short loc_180006A83
0x180006a7a  movzx   ebx, ax
0x180006a7d  or      ebx, 80070000h
0x180006a83  test    ebx, ebx
0x180006a85  js      short loc_180006A91
0x180006a87  mov     rcx, rsi; this
0x180006a8a  call    ?FindNextRecord@CDirFltr@@AEAAJXZ; CDirFltr::FindNextRecord(void)
0x180006a8f  jmp     short loc_180006A93
0x180006a91  mov     eax, ebx
0x180006a93  mov     rcx, [rsp+158h+var_38]
0x180006a9b  xor     rcx, rsp; StackCookie
0x180006a9e  call    __security_check_cookie
0x180006aa3  lea     r11, [rsp+158h+var_28]
0x180006aab  mov     rbx, [r11+40h]
0x180006aaf  mov     rbp, [r11+48h]
0x180006ab3  mov     rsp, r11
0x180006ab6  pop     r15
0x180006ab8  pop     r14
0x180006aba  pop     r12
0x180006abc  pop     rdi
0x180006abd  pop     rsi
0x180006abe  retn
```
