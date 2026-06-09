# container::FilesystemProvider::Setup(Schema::Containers::Definition::FilesystemNamespace const &,_WC_FILESYSTEM_PROVIDER const &,void *)

- ea: `0x180024a84`
- end: `0x1800251d9`
- name: `?Setup@FilesystemProvider@container@@YAXAEBUFilesystemNamespace@Definition@Containers@Schema@@AEBW4_WC_FILESYSTEM_PROVIDER@@PEAX@Z`
- size: `1877`
- prototype: `void __fastcall(container::FilesystemProvider *__hidden this, const struct Schema::Containers::Definition::FilesystemNamespace *, const enum _WC_FILESYSTEM_PROVIDER *, void *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update`

## callers

- `0x1800063f0`
- `0x18000f620`

## callees

- `0x180002ad0`
- `0x180002ee4`
- `0x180002f1c`
- `0x1800051b0`
- `0x18000bdec`
- `0x18000ca10`
- `0x180011fe8`
- `0x18001d894`
- `0x18001e6dc`
- `0x18001f184`
- `0x1800215cc`
- `0x180024078`
- `0x180024350`
- `0x1800244a8`
- `0x180024664`
- `0x180024700`
- `0x180024a84`
- `0x18002524c`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x180024c8d`
- `ntdll!RtlDoesFileExists_U` at `0x180024c8d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180024ff9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180024ff9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180024cf6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180024cf6`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180024fac`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180024fac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024f87`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024f87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025031`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025031`
- `wc_storage!WcAttachFilterEx` at `0x180024e7d`
- `wc_storage!WcAttachFilterEx` at `0x180024e7d`
- `BINDFLTAPI!BfSetupFilterBatched` at `0x180025079`
- `BINDFLTAPI!BfSetupFilterBatched` at `0x1800250bf`
- `BINDFLTAPI!BfSetupFilterBatched` at `0x180025079`
- `BINDFLTAPI!BfSetupFilterBatched` at `0x1800250bf`
- `UNIONFSAPI!MigrateFileSystemUnion` at `0x180024cd0`
- `UNIONFSAPI!MigrateFileSystemUnion` at `0x180024cd0`
- `UNIONFSAPI!CreateFileSystemUnion` at `0x180024d54`
- `UNIONFSAPI!CreateFileSystemUnion` at `0x180024d54`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall container::FilesystemProvider::Setup(
        container::FilesystemProvider *this,
        const struct Schema::Containers::Definition::FilesystemNamespace *a2,
        const enum _WC_FILESYSTEM_PROVIDER *a3,
        void *a4)
{
  unsigned int v6; // r15d
  char v7; // al
  container::FilesystemProvider *v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  container::FilesystemProvider *v11; // rax
  unsigned __int64 v12; // rdi
  __int64 v13; // rcx
  _QWORD *v14; // rdx
  _QWORD *v15; // rcx
  container::FilesystemProvider *v16; // rdx
  __int64 v17; // r8
  const WCHAR *v18; // rcx
  PCWSTR *v19; // r8
  int v20; // eax
  const WCHAR *v21; // rcx
  void *v22; // rdx
  unsigned int v23; // r8d
  const char *v24; // r9
  int v25; // eax
  int v26; // ecx
  char *v27; // rdi
  unsigned __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int128 v31; // xmm0
  __int64 v32; // r8
  _QWORD *v33; // rdx
  unsigned __int64 v34; // rdx
  container::FilesystemProvider *v35; // r8
  int v36; // eax
  unsigned __int64 v37; // rdx
  unsigned __int64 v38; // r14
  __int64 v39; // rcx
  const WCHAR *v40; // rsi
  _QWORD *v41; // rcx
  _QWORD *v42; // r15
  _QWORD *v43; // rdi
  _QWORD *v44; // rdx
  _QWORD *v45; // rax
  HANDLE FileW; // rax
  const char *v47; // r9
  void *v48; // rdi
  DWORD FileSize; // eax
  const char *v50; // r9
  DWORD v51; // esi
  const char *v52; // r9
  int v53; // edi
  PCWSTR v54; // rsi
  int v55; // eax
  int v56; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-99h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-99h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-99h]
  int dwCreationDispositionc; // [rsp+20h] [rbp-99h]
  int dwCreationDispositiond; // [rsp+20h] [rbp-99h]
  const char *hTemplateFile; // [rsp+30h] [rbp-89h]
  __int128 v63; // [rsp+40h] [rbp-79h] BYREF
  _QWORD *v64; // [rsp+50h] [rbp-69h]
  int v65[2]; // [rsp+58h] [rbp-61h] BYREF
  DWORD NumberOfBytesRead[2]; // [rsp+60h] [rbp-59h] BYREF
  int *v67; // [rsp+68h] [rbp-51h]
  container::FilesystemProvider *v68; // [rsp+70h] [rbp-49h]
  const struct Schema::Containers::Definition::FilesystemNamespace *v69; // [rsp+78h] [rbp-41h]
  char v70; // [rsp+80h] [rbp-39h]
  LPVOID lpBuffer[2]; // [rsp+88h] [rbp-31h] BYREF
  __int64 v72; // [rsp+98h] [rbp-21h]
  __int64 v73; // [rsp+A0h] [rbp-19h]
  PCWSTR FileName[2]; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v75; // [rsp+B8h] [rbp-1h]
  unsigned __int64 v76; // [rsp+C0h] [rbp+7h]
  __int128 v77; // [rsp+C8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  *(_QWORD *)v65 = a3;
  v6 = 0;
  if ( !(0x6DB6DB6DB6DB6DB7LL * ((__int64)(*((_QWORD *)this + 9) - *((_QWORD *)this + 8)) >> 3)) || (v7 = 1, a3) )
    v7 = 0;
  LOBYTE(dwCreationDisposition) = v7;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x157,
    (unsigned int)"onecore\\base\\gendrv\\silos\\container\\filesystem_provider.cpp",
    (const char *)0x80070057LL,
    dwCreationDisposition,
    (bool)"Job handle cannot be null if bindings are supplied.",
    hTemplateFile);
  if ( *(_DWORD *)a2 == 1 )
  {
    v77 = 0;
    if ( *((_QWORD *)this + 3) <= 7u )
      v8 = this;
    else
      v8 = *(container::FilesystemProvider **)this;
    *(_OWORD *)lpBuffer = 0;
    v72 = 0;
    v73 = 0;
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)v8 + v9) );
    std::wstring::_Construct<1,unsigned short const *>(lpBuffer);
    v10 = container::FilesystemProvider::Details::ExtractGuidFromMountPath(lpBuffer, &v77);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x168,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\filesystem_provider.cpp",
        (const char *)(unsigned int)v10,
        dwCreationDispositiona);
    std::wstring::~wstring(lpBuffer);
    v63 = 0;
    v64 = 0;
    if ( *((_QWORD *)this + 3) <= 7u )
      v11 = this;
    else
      v11 = *(container::FilesystemProvider **)this;
    *(_QWORD *)NumberOfBytesRead = v11;
    std::vector<unsigned short const *>::_Emplace_reallocate<unsigned short const *>(&v63, 0, NumberOfBytesRead);
    v12 = 0;
    v13 = *((_QWORD *)this + 5);
    if ( 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)this + 6) - v13) >> 4) )
    {
      v14 = (_QWORD *)*((_QWORD *)&v63 + 1);
      do
      {
        v15 = (_QWORD *)(48 * v12 + v13 + 16);
        if ( v15[3] > 7u )
          v15 = (_QWORD *)*v15;
        *(_QWORD *)NumberOfBytesRead = v15;
        if ( v14 == v64 )
        {
          std::vector<unsigned short const *>::_Emplace_reallocate<unsigned short const *>(&v63, v14, NumberOfBytesRead);
          v14 = (_QWORD *)*((_QWORD *)&v63 + 1);
        }
        else
        {
          *v14 = v15;
          v14 = (_QWORD *)(*((_QWORD *)&v63 + 1) + 8LL);
          *((_QWORD *)&v63 + 1) += 8LL;
        }
        ++v12;
        v13 = *((_QWORD *)this + 5);
      }
      while ( v12 < 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)this + 6) - v13) >> 4) );
    }
    if ( *((_QWORD *)this + 3) <= 7u )
      v16 = this;
    else
      v16 = *(container::FilesystemProvider **)this;
    *(_OWORD *)lpBuffer = 0;
    v72 = 0;
    v73 = 0;
    v17 = -1;
    do
      ++v17;
    while ( *((_WORD *)v16 + v17) );
    std::wstring::_Construct<1,unsigned short const *>(lpBuffer);
    container::FilesystemProvider::Details::GetUnionConfigPath(FileName);
    std::wstring::~wstring(lpBuffer);
    v18 = (const WCHAR *)FileName;
    if ( v76 > 7 )
      v18 = FileName[0];
    if ( RtlDoesFileExists_U(v18) )
    {
      v19 = FileName;
      if ( v76 > 7 )
        v19 = (PCWSTR *)FileName[0];
      dwCreationDispositionb = v65[0];
      v20 = MigrateFileSystemUnion(v63, (__int64)(*((_QWORD *)&v63 + 1) - v63) >> 3, v19, &v77);
      if ( v20 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x17F,
          (unsigned int)"onecore\\base\\gendrv\\silos\\container\\filesystem_provider.cpp",
          (const char *)(unsigned int)v20,
          dwCreationDispositionb);
      v21 = (const WCHAR *)FileName;
      if ( v76 > 7 )
        v21 = FileName[0];
      if ( !DeleteFileW(v21) )
        wil::details::in1diag3::_Log_GetLastError(retaddr, v22, v23, v24);
    }
    else
    {
      container::FilesystemProvider::Details::InitializeSandbox(this);
      dwCreationDispositionc = v65[0];
      v25 = CreateFileSystemUnion(&v77, v63, (__int64)(*((_QWORD *)&v63 + 1) - v63) >> 3, 0);
      if ( v25 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x191,
          (unsigned int)"onecore\\base\\gendrv\\silos\\container\\filesystem_provider.cpp",
          (const char *)(unsigned int)v25,
          dwCreationDispositionc);
    }
    std::wstring::~wstring(FileName);
    std::vector<unsigned short const *>::~vector<unsigned short const *>(&v63);
    goto LABEL_54;
  }
  v26 = *((_DWORD *)this + 8);
  if ( v26 )
  {
    if ( v26 != 1 )
      goto LABEL_44;
    v6 = 1;
  }
  if ( *((_DWORD *)this + 9) >= 2u )
LABEL_44:
    __fastfail(5u);
  v27 = (char *)operator new[](
                  saturated_mul(
                    0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 6) - *((_QWORD *)this + 5)) >> 4),
                    0x20u));
  *(_QWORD *)&v77 = v27;
  v28 = 0;
  v29 = *((_QWORD *)this + 6);
  v30 = *((_QWORD *)this + 5);
  if ( 0xAAAAAAAAAAAAAAABuLL * ((v29 - v30) >> 4) )
  {
    do
    {
      v31 = *(_OWORD *)(v30 + 48 * v28);
      v32 = 32 * v28;
      *(_OWORD *)&v27[v32] = v31;
      *(_DWORD *)&v27[v32 + 16] = 0;
      v33 = (_QWORD *)(48 * v28 + *((_QWORD *)this + 5) + 16LL);
      if ( v33[3] > 7u )
        v33 = (_QWORD *)*v33;
      *(_QWORD *)&v27[v32 + 24] = v33;
      ++v28;
      v29 = *((_QWORD *)this + 6);
      v30 = *((_QWORD *)this + 5);
    }
    while ( v28 < 0xAAAAAAAAAAAAAAABuLL * ((v29 - v30) >> 4) );
  }
  v34 = 0xAAAAAAAAAAAAAAABuLL * ((v29 - v30) >> 4);
  if ( *((_QWORD *)this + 3) <= 7u )
    v35 = this;
  else
    v35 = *(container::FilesystemProvider **)this;
  dwCreationDispositiond = v34;
  v36 = WcAttachFilterEx(*(_QWORD *)v65, v6, v35, v27);
  if ( v36 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1D4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\filesystem_provider.cpp",
      (const char *)(unsigned int)v36,
      dwCreationDispositiond);
  operator delete(v27, v37);
LABEL_54:
  v67 = v65;
  v68 = this;
  v69 = a2;
  v70 = 1;
  v38 = 0;
  v39 = *((_QWORD *)this + 8);
  if ( 0x6DB6DB6DB6DB6DB7LL * ((*((_QWORD *)this + 9) - v39) >> 3) )
  {
    do
    {
      v40 = (const WCHAR *)(v39 + 56 * v38);
      v63 = 0;
      v41 = 0;
      v64 = 0;
      v42 = (_QWORD *)*((_QWORD *)v40 + 5);
      v43 = (_QWORD *)*((_QWORD *)v40 + 4);
      if ( v43 != v42 )
      {
        v44 = (_QWORD *)*((_QWORD *)&v63 + 1);
        while ( 1 )
        {
          v45 = v43[3] <= 7u ? v43 : (_QWORD *)*v43;
          *(_QWORD *)&v77 = v45;
          if ( v44 == v41 )
          {
            std::vector<unsigned short const *>::_Emplace_reallocate<unsigned short const *>(&v63, v44, &v77);
            v44 = (_QWORD *)*((_QWORD *)&v63 + 1);
          }
          else
          {
            *v44 = v45;
            v44 = (_QWORD *)(*((_QWORD *)&v63 + 1) + 8LL);
            *((_QWORD *)&v63 + 1) += 8LL;
          }
          v43 += 4;
          if ( v43 == v42 )
            break;
          v41 = v64;
        }
      }
      *(_OWORD *)FileName = 0;
      v75 = 0;
      if ( *((_QWORD *)v40 + 3) > 7u )
        v40 = *(const WCHAR **)v40;
      FileW = CreateFileW(v40, 0x80000000, 1u, 0, 3u, 0, 0);
      v48 = FileW;
      *(_QWORD *)&v77 = FileW;
      if ( FileW == (HANDLE)-1LL )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0xD9,
          (unsigned int)"onecore\\base\\gendrv\\silos\\container\\filesystem_provider.cpp",
          v47);
      FileSize = GetFileSize(FileW, 0);
      v51 = FileSize;
      if ( FileSize == -1 )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0xDD,
          (unsigned int)"onecore\\base\\gendrv\\silos\\container\\filesystem_provider.cpp",
          v50);
      NumberOfBytesRead[0] = 0;
      *(_OWORD *)lpBuffer = 0;
      v72 = 0;
      if ( FileSize )
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(lpBuffer, FileSize);
      if ( !ReadFile(v48, lpBuffer[0], v51, NumberOfBytesRead, 0) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0xE8,
          (unsigned int)"onecore\\base\\gendrv\\silos\\container\\filesystem_provider.cpp",
          v52);
      std::vector<unsigned char>::operator=(FileName, lpBuffer);
      std::vector<unsigned char>::~vector<unsigned char>(lpBuffer);
      if ( v48 )
        CloseHandle(v48);
      v53 = (int)FileName[1];
      v54 = FileName[0];
      if ( v38 )
      {
        v55 = BfSetupFilterBatched(
                *(_QWORD *)v65,
                0,
                FileName[0],
                (unsigned int)(LODWORD(FileName[1]) - LODWORD(FileName[0])));
        if ( v55 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x209,
            (unsigned int)"onecore\\base\\gendrv\\silos\\container\\filesystem_provider.cpp",
            (const char *)(unsigned int)v55,
            0x20000000);
      }
      v56 = BfSetupFilterBatched(*(_QWORD *)v65, 0, v54, (unsigned int)(v53 - (_DWORD)v54));
      if ( v56 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x22D,
          (unsigned int)"onecore\\base\\gendrv\\silos\\container\\filesystem_provider.cpp",
          (const char *)(unsigned int)v56,
          209);
      std::vector<unsigned char>::~vector<unsigned char>(FileName);
      std::vector<unsigned short const *>::~vector<unsigned short const *>(&v63);
      ++v38;
      v39 = *((_QWORD *)this + 8);
    }
    while ( v38 < 0x6DB6DB6DB6DB6DB7LL * ((*((_QWORD *)this + 9) - v39) >> 3) );
  }
}

```

## disassembly

```asm
0x180024a84  mov     [rsp-8+arg_8], rbx
0x180024a89  push    rbp
0x180024a8a  push    rsi
0x180024a8b  push    rdi
0x180024a8c  push    r12
0x180024a8e  push    r13
0x180024a90  push    r14
0x180024a92  push    r15
0x180024a94  lea     rbp, [rsp-27h]
0x180024a99  sub     rsp, 0E0h
0x180024aa0  mov     rax, cs:__security_cookie
0x180024aa7  xor     rax, rsp
0x180024aaa  mov     [rbp+57h+var_38], rax
0x180024aae  mov     r13, rdx
0x180024ab1  mov     rbx, rcx
0x180024ab4  mov     qword ptr [rbp+57h+var_B8], r8
0x180024ab8  mov     rax, [rcx+48h]
0x180024abc  sub     rax, [rcx+40h]
0x180024ac0  sar     rax, 3
0x180024ac4  mov     rcx, 6DB6DB6DB6DB6DB7h
0x180024ace  imul    rax, rcx
0x180024ad2  xor     r15d, r15d
0x180024ad5  test    rax, rax
0x180024ad8  jz      short loc_180024AE1
0x180024ada  test    r8, r8
0x180024add  mov     al, 1
0x180024adf  jz      short loc_180024AE4
0x180024ae1  mov     al, r15b
0x180024ae4  mov     rcx, [rbp+5Fh]; this
0x180024ae8  lea     rdx, aJobHandleCanno; "Job handle cannot be null if bindings a"...
0x180024aef  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rdx; bool
0x180024af4  mov     byte ptr [rsp+110h+dwCreationDisposition], al; int
0x180024af8  mov     r9d, 80070057h; char *
0x180024afe  lea     r14, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\container"...
0x180024b05  mov     r8, r14; unsigned int
0x180024b08  mov     edx, 157h; void *
0x180024b0d  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180024b12  cmp     dword ptr [r13+0], 1
0x180024b17  jnz     loc_180024D6E
0x180024b1d  xorps   xmm0, xmm0
0x180024b20  movups  [rbp+57h+var_48], xmm0
0x180024b24  cmp     qword ptr [rbx+18h], 7
0x180024b29  jbe     short loc_180024B30
0x180024b2b  mov     rdx, [rbx]
0x180024b2e  jmp     short loc_180024B33
0x180024b30  mov     rdx, rbx
0x180024b33  movups  xmmword ptr [rbp+57h+lpBuffer], xmm0
0x180024b37  mov     [rbp+57h+var_78], r15
0x180024b3b  mov     [rbp+57h+var_70], r15
0x180024b3f  or      r12, 0FFFFFFFFFFFFFFFFh
0x180024b43  mov     r8, r12
0x180024b46  inc     r8
0x180024b49  cmp     [rdx+r8*2], r15w
0x180024b4e  jnz     short loc_180024B46
0x180024b50  lea     rcx, [rbp+57h+lpBuffer]
0x180024b54  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180024b59  nop
0x180024b5a  lea     rdx, [rbp+57h+var_48]
0x180024b5e  lea     rcx, [rbp+57h+lpBuffer]
0x180024b62  call    ?ExtractGuidFromMountPath@Details@FilesystemProvider@container@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_GUID@@@Z; container::FilesystemProvider::Details::ExtractGuidFromMountPath(std::wstring const &,_GUID &)
0x180024b67  mov     rcx, [rbp+5Fh]; this
0x180024b6b  test    eax, eax
0x180024b6d  js      loc_180025166
0x180024b73  lea     rcx, [rbp+57h+lpBuffer]
0x180024b77  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024b7c  xorps   xmm0, xmm0
0x180024b7f  movdqu  [rbp+57h+var_D0], xmm0
0x180024b84  mov     [rbp+57h+var_C0], r15
0x180024b88  cmp     qword ptr [rbx+18h], 7
0x180024b8d  jbe     short loc_180024B94
0x180024b8f  mov     rax, [rbx]
0x180024b92  jmp     short loc_180024B97
0x180024b94  mov     rax, rbx
0x180024b97  mov     qword ptr [rbp+57h+NumberOfBytesRead], rax
0x180024b9b  lea     r8, [rbp+57h+NumberOfBytesRead]
0x180024b9f  xor     edx, edx
0x180024ba1  lea     rcx, [rbp+57h+var_D0]
0x180024ba5  call    ??$_Emplace_reallocate@PEBG@?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAAPEAPEBGQEAPEBG$$QEAPEBG@Z; std::vector<ushort const *>::_Emplace_reallocate<ushort const *>(ushort const * * const,ushort const * &&)
0x180024baa  mov     rdi, r15
0x180024bad  mov     rcx, [rbx+28h]
0x180024bb1  mov     rax, [rbx+30h]
0x180024bb5  sub     rax, rcx
0x180024bb8  sar     rax, 4
0x180024bbc  mov     rsi, 0AAAAAAAAAAAAAAABh
0x180024bc6  imul    rax, rsi
0x180024bca  test    rax, rax
0x180024bcd  jz      short loc_180024C33
0x180024bcf  mov     rdx, qword ptr [rbp+57h+var_D0+8]
0x180024bd3  lea     rax, [rdi+rdi*2]
0x180024bd7  shl     rax, 4
0x180024bdb  add     rcx, 10h
0x180024bdf  add     rcx, rax
0x180024be2  cmp     qword ptr [rcx+18h], 7
0x180024be7  jbe     short loc_180024BEC
0x180024be9  mov     rcx, [rcx]
0x180024bec  mov     qword ptr [rbp+57h+NumberOfBytesRead], rcx
0x180024bf0  cmp     rdx, [rbp+57h+var_C0]
0x180024bf4  jz      short loc_180024C07
0x180024bf6  mov     [rdx], rcx
0x180024bf9  mov     rdx, qword ptr [rbp+57h+var_D0+8]
0x180024bfd  add     rdx, 8
0x180024c01  mov     qword ptr [rbp+57h+var_D0+8], rdx
0x180024c05  jmp     short loc_180024C18
0x180024c07  lea     r8, [rbp+57h+NumberOfBytesRead]
0x180024c0b  lea     rcx, [rbp+57h+var_D0]
0x180024c0f  call    ??$_Emplace_reallocate@PEBG@?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAAPEAPEBGQEAPEBG$$QEAPEBG@Z; std::vector<ushort const *>::_Emplace_reallocate<ushort const *>(ushort const * * const,ushort const * &&)
0x180024c14  mov     rdx, qword ptr [rbp+57h+var_D0+8]
0x180024c18  inc     rdi
0x180024c1b  mov     rcx, [rbx+28h]
0x180024c1f  mov     rax, [rbx+30h]
0x180024c23  sub     rax, rcx
0x180024c26  sar     rax, 4
0x180024c2a  imul    rax, rsi
0x180024c2e  cmp     rdi, rax
0x180024c31  jb      short loc_180024BD3
0x180024c33  cmp     qword ptr [rbx+18h], 7
0x180024c38  jbe     short loc_180024C3F
0x180024c3a  mov     rdx, [rbx]
0x180024c3d  jmp     short loc_180024C42
0x180024c3f  mov     rdx, rbx
0x180024c42  xorps   xmm0, xmm0
0x180024c45  movups  xmmword ptr [rbp+57h+lpBuffer], xmm0
0x180024c49  mov     [rbp+57h+var_78], r15
0x180024c4d  mov     [rbp+57h+var_70], r15
0x180024c51  mov     r8, r12
0x180024c54  inc     r8
0x180024c57  cmp     [rdx+r8*2], r15w
0x180024c5c  jnz     short loc_180024C54
0x180024c5e  lea     rcx, [rbp+57h+lpBuffer]
0x180024c62  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180024c67  nop
0x180024c68  lea     rdx, [rbp+57h+lpBuffer]
0x180024c6c  lea     rcx, [rbp+57h+FileName]; Src
0x180024c70  call    ?GetUnionConfigPath@Details@FilesystemProvider@container@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z; container::FilesystemProvider::Details::GetUnionConfigPath(std::wstring const &)
0x180024c75  nop
0x180024c76  lea     rcx, [rbp+57h+lpBuffer]
0x180024c7a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024c7f  lea     rcx, [rbp+57h+FileName]
0x180024c83  cmp     [rbp+57h+var_50], 7
0x180024c88  cmova   rcx, [rbp+57h+FileName]; FileName
0x180024c8d  call    cs:__imp_RtlDoesFileExists_U
0x180024c94  nop     dword ptr [rax+rax+00h]
0x180024c99  test    al, al
0x180024c9b  jz      loc_180024D28
0x180024ca1  mov     rax, qword ptr [rbp+57h+var_B8]
0x180024ca5  lea     r8, [rbp+57h+FileName]
0x180024ca9  cmp     [rbp+57h+var_50], 7
0x180024cae  cmova   r8, [rbp+57h+FileName]
0x180024cb3  mov     rcx, qword ptr [rbp+57h+var_D0]
0x180024cb7  mov     rdx, qword ptr [rbp+57h+var_D0+8]
0x180024cbb  sub     rdx, rcx
0x180024cbe  sar     rdx, 3
0x180024cc2  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r15
0x180024cc7  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; int
0x180024ccc  lea     r9, [rbp+57h+var_48]
0x180024cd0  call    cs:__imp_MigrateFileSystemUnion
0x180024cd7  nop     dword ptr [rax+rax+00h]
0x180024cdc  mov     rcx, [rbp+5Fh]; this
0x180024ce0  test    eax, eax
0x180024ce2  js      loc_180025177
0x180024ce8  lea     rcx, [rbp+57h+FileName]
0x180024cec  cmp     [rbp+57h+var_50], 7
0x180024cf1  cmova   rcx, [rbp+57h+FileName]; lpFileName
0x180024cf6  call    cs:__imp_DeleteFileW
0x180024cfd  nop     dword ptr [rax+rax+00h]
0x180024d02  mov     rcx, [rbp+5Fh]; this
0x180024d06  test    eax, eax
0x180024d08  jnz     short loc_180024D10
0x180024d0a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180024d0f  nop
0x180024d10  lea     rcx, [rbp+57h+FileName]
0x180024d14  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024d19  nop
0x180024d1a  lea     rcx, [rbp+57h+var_D0]
0x180024d1e  call    ??1?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::~vector<ushort const *>(void)
0x180024d23  jmp     loc_180024EA0
0x180024d28  mov     rcx, rbx
0x180024d2b  call    ?InitializeSandbox@Details@FilesystemProvider@container@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; container::FilesystemProvider::Details::InitializeSandbox(std::wstring const &)
0x180024d30  mov     rax, qword ptr [rbp+57h+var_B8]
0x180024d34  mov     rdx, qword ptr [rbp+57h+var_D0]
0x180024d38  mov     r8, qword ptr [rbp+57h+var_D0+8]
0x180024d3c  sub     r8, rdx
0x180024d3f  sar     r8, 3
0x180024d43  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r15
0x180024d48  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; int
0x180024d4d  xor     r9d, r9d
0x180024d50  lea     rcx, [rbp+57h+var_48]
0x180024d54  call    cs:__imp_CreateFileSystemUnion
0x180024d5b  nop     dword ptr [rax+rax+00h]
0x180024d60  mov     rcx, [rbp+5Fh]; this
0x180024d64  test    eax, eax
0x180024d66  js      loc_180025143
0x180024d6c  jmp     short loc_180024D10
0x180024d6e  mov     ecx, [rbx+20h]
0x180024d71  test    ecx, ecx
0x180024d73  jz      short loc_180024D7D
0x180024d75  cmp     ecx, 1
0x180024d78  jnz     short loc_180024D89
0x180024d7a  mov     r15d, ecx
0x180024d7d  mov     ecx, [rbx+24h]
0x180024d80  test    ecx, ecx
0x180024d82  jz      short loc_180024D98
0x180024d84  cmp     ecx, 1
0x180024d87  jz      short loc_180024D90
0x180024d89  mov     ecx, 5
0x180024d8e  int     29h; Win8: RtlFailFast(ecx)
0x180024d90  mov     r14d, 1
0x180024d96  jmp     short loc_180024D9B
0x180024d98  xor     r14d, r14d
0x180024d9b  mov     rcx, [rbx+30h]
0x180024d9f  sub     rcx, [rbx+28h]
0x180024da3  sar     rcx, 4
0x180024da7  mov     rsi, 0AAAAAAAAAAAAAAABh
0x180024db1  imul    rcx, rsi
0x180024db5  mov     eax, 20h ; ' '
0x180024dba  mul     rcx
0x180024dbd  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180024dc4  cmovb   rax, r12
0x180024dc8  mov     rcx, rax; unsigned __int64
0x180024dcb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180024dd0  mov     rdi, rax
0x180024dd3  mov     qword ptr [rbp+57h+var_48], rax
0x180024dd7  xor     r9d, r9d
0x180024dda  mov     rdx, [rbx+30h]
0x180024dde  mov     r8, [rbx+28h]
0x180024de2  mov     rcx, rdx
0x180024de5  sub     rcx, r8
0x180024de8  sar     rcx, 4
0x180024dec  imul    rcx, rsi
0x180024df0  test    rcx, rcx
0x180024df3  jz      short loc_180024E50
0x180024df5  lea     rcx, [r9+r9*2]
0x180024df9  shl     rcx, 4
0x180024dfd  movups  xmm0, xmmword ptr [r8+rcx]
0x180024e02  mov     r8, r9
0x180024e05  shl     r8, 5
0x180024e09  movdqu  xmmword ptr [r8+rdi], xmm0
0x180024e0f  mov     dword ptr [r8+rdi+10h], 0
0x180024e18  mov     rdx, [rbx+28h]
0x180024e1c  add     rdx, 10h
0x180024e20  add     rdx, rcx
0x180024e23  cmp     qword ptr [rdx+18h], 7
0x180024e28  jbe     short loc_180024E2D
0x180024e2a  mov     rdx, [rdx]
0x180024e2d  mov     [r8+rdi+18h], rdx
0x180024e32  inc     r9
0x180024e35  mov     rdx, [rbx+30h]
0x180024e39  mov     r8, [rbx+28h]
0x180024e3d  mov     rax, rdx
0x180024e40  sub     rax, r8
0x180024e43  sar     rax, 4
0x180024e47  imul    rax, rsi
0x180024e4b  cmp     r9, rax
0x180024e4e  jb      short loc_180024DF5
0x180024e50  sub     rdx, r8
0x180024e53  sar     rdx, 4
0x180024e57  imul    rdx, rsi
0x180024e5b  cmp     qword ptr [rbx+18h], 7
0x180024e60  jbe     short loc_180024E67
0x180024e62  mov     r8, [rbx]
0x180024e65  jmp     short loc_180024E6A
0x180024e67  mov     r8, rbx
0x180024e6a  mov     [rsp+110h+dwFlagsAndAttributes], r14d
0x180024e6f  mov     [rsp+110h+dwCreationDisposition], edx; int
0x180024e73  mov     r9, rdi
0x180024e76  mov     edx, r15d
0x180024e79  mov     rcx, qword ptr [rbp+57h+var_B8]
0x180024e7d  call    cs:__imp_WcAttachFilterEx
0x180024e84  nop     dword ptr [rax+rax+00h]
0x180024e89  mov     rcx, [rbp+5Fh]; this
0x180024e8d  xor     r15d, r15d
0x180024e90  test    eax, eax
0x180024e92  js      loc_180025188
0x180024e98  mov     rcx, rdi; void *
0x180024e9b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024ea0  lea     rax, [rbp+57h+var_B8]
0x180024ea4  mov     [rbp+57h+var_A8], rax
0x180024ea8  mov     [rbp+57h+var_A0], rbx
0x180024eac  mov     [rbp+57h+var_98], r13
0x180024eb0  mov     [rbp+57h+var_90], 1
0x180024eb4  mov     r14, r15
0x180024eb7  mov     rcx, [rbx+40h]
0x180024ebb  mov     rax, [rbx+48h]
0x180024ebf  sub     rax, rcx
0x180024ec2  sar     rax, 3
0x180024ec6  mov     r13, 6DB6DB6DB6DB6DB7h
0x180024ed0  imul    rax, r13
0x180024ed4  test    rax, rax
0x180024ed7  jz      loc_180025109
0x180024edd  imul    rsi, r14, 38h ; '8'
0x180024ee1  add     rsi, rcx
0x180024ee4  xorps   xmm0, xmm0
0x180024ee7  movdqu  [rbp+57h+var_D0], xmm0
0x180024eec  mov     rcx, r15
0x180024eef  mov     [rbp+57h+var_C0], rcx
0x180024ef3  mov     r15, [rsi+28h]
0x180024ef7  mov     rdi, [rsi+20h]
0x180024efb  cmp     rdi, r15
0x180024efe  jz      short loc_180024F4D
0x180024f00  mov     rdx, qword ptr [rbp+57h+var_D0+8]
  ... truncated ...
```
