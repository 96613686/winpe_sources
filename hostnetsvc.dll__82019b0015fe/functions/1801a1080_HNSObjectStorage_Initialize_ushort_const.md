# HNSObjectStorage::Initialize(ushort const *)

- ea: `0x1801a1080`
- end: `0x1801a154e`
- name: `?Initialize@HNSObjectStorage@@QEAAJPEBG@Z`
- size: `1230`
- prototype: `signed int __fastcall(HNSObjectStorage *this, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800b368c`

## callees

- `0x18005f0c0`
- `0x18005f560`
- `0x18005f59c`
- `0x18005ffb8`
- `0x18005ffc4`
- `0x18006038c`
- `0x180067c00`
- `0x180069104`
- `0x18006c530`
- `0x18008c6c0`
- `0x1801a079c`
- `0x1801a0a8c`
- `0x1801a0c64`
- `0x1801a1080`
- `0x1801a1980`
- `0x1801a3fa8`
- `0x1801a4210`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a12ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a12ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a116e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a1180`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a116e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a1180`
- `CRYPTSP!CryptAcquireContextW` at `0x1801a12c0`
- `CRYPTSP!CryptAcquireContextW` at `0x1801a12c0`
- `CRYPTSP!CryptReleaseContext` at `0x1801a1292`
- `CRYPTSP!CryptReleaseContext` at `0x1801a1292`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801a1458`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801a1458`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801a144b`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801a144b`

## pseudocode

```c
signed int __fastcall HNSObjectStorage::Initialize(HNSObjectStorage *this, LPCWSTR lpFileName)
{
  unsigned int v4; // eax
  __int64 v5; // r12
  __int64 v6; // r13
  _QWORD *v7; // rax
  _QWORD *v8; // r15
  unsigned __int16 *const near *v9; // r13
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // r8
  HKEY *v13; // rbx
  HKEY v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rcx
  _QWORD *v17; // rdx
  _QWORD *v18; // rax
  signed int result; // eax
  bool v20; // sf
  __int64 v21; // r8
  char **v22; // rbx
  unsigned __int64 v23; // rdx
  char *v24; // r15
  __int64 v25; // rbx
  __int64 v26; // r8
  char v27; // bl
  const WCHAR *v28; // rdx
  __int64 v29; // r8
  int v30; // r14d
  _QWORD **v31; // r14
  _QWORD *v32; // rcx
  wil *v33; // rcx
  bool v34; // [rsp+30h] [rbp-D8h] BYREF
  char v35; // [rsp+31h] [rbp-D7h]
  unsigned int v36; // [rsp+34h] [rbp-D4h] BYREF
  int v37; // [rsp+38h] [rbp-D0h]
  int v38; // [rsp+3Ch] [rbp-CCh] BYREF
  _QWORD *v39; // [rsp+40h] [rbp-C8h]
  unsigned __int16 *const near *v40; // [rsp+50h] [rbp-B8h]
  __int64 v41; // [rsp+58h] [rbp-B0h]
  unsigned __int16 *const near *v42; // [rsp+60h] [rbp-A8h]
  __int64 v43; // [rsp+68h] [rbp-A0h]
  LPCWSTR lpNewFileName[2]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v45; // [rsp+80h] [rbp-88h]
  unsigned __int64 v46; // [rsp+88h] [rbp-80h]
  _QWORD v47[7]; // [rsp+90h] [rbp-78h] BYREF
  _QWORD *v48; // [rsp+C8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v37 = 0;
  v34 = 0;
  v38 = 0;
  *((_DWORD *)this + 1357) = 0;
  v36 = 0;
  v4 = 0;
  v5 = -1;
  while ( v4 < 8 )
  {
    try
    {
      *(_OWORD *)lpNewFileName = 0;
      v6 = v4;
      v7 = operator new(0x10u);
      v8 = v7;
      v39 = v7;
      v9 = (&HNSObjectStorage::m_registryStorePath)[v6];
      v10 = -1;
      do
        ++v10;
      while ( *((_WORD *)v9 + v10) );
      *v7 = 0;
      v7[1] = 0;
      v40 = v9;
      v41 = v10;
      HNS::Service::SharedMemory::OpenRegistry((_DWORD)v7 + 8);
      v42 = v9;
      v43 = v10;
      HNS::Service::SharedMemory::OpenRegistry((unsigned int)v8);
      v13 = (HKEY *)*((_QWORD *)this + v36 + 30);
      *((_QWORD *)this + v36 + 30) = v8;
      if ( v13 )
      {
        v14 = v13[1];
        if ( v14 )
        {
          RegCloseKey(v14);
          v13[1] = 0;
        }
        if ( *v13 )
        {
          RegCloseKey(*v13);
          *v13 = 0;
        }
        operator delete(v13, (const struct std::nothrow_t *)0x10);
      }
      v15 = *((_QWORD *)this + v36 + 30);
      v47[0] = &std::_Func_impl_no_alloc<_lambda_1f8e126b2954b720ae02b04bdb7ea558_,void,wil::basic_zstring_view<unsigned short>,bool,unsigned char *,unsigned long const &>::`vftable';
      v47[1] = lpNewFileName;
      v47[2] = this;
      v47[3] = &v36;
      v48 = v47;
      LOBYTE(v12) = 1;
      HNS::Service::SharedMemory::RegistryStore::EnumerateSubStore(v11, v15, v12, v47);
      HNS::Service::SharedMemory::RegistryStore::EnumerateSubStore(v16, v15 + 8, 0, v47);
      if ( v48 )
      {
        v17 = v47;
        LOBYTE(v17) = v48 != v47;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v48 + 32LL))(v48, v17);
      }
      v37 |= 1u;
      v4 = ++v36;
    }
    catch ( ... )
    {
      return wil::details::in1diag3::Return_CaughtExceptionMsg(
               retaddr,
               (void *)0x327,
               (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\storage\\hnsobjectstorage.cpp",
               "Unable to initialize imos for %ls",
               (const char *)(&HNSObjectStorage::m_registryStorePath)[v36]);
    }
  }
  if ( !*(_QWORD *)this )
  {
    v18 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v39 = v18;
    if ( !v18 )
    {
      *(_QWORD *)this = 0;
      return -2147024882;
    }
    *v18 = &FileBlockStorage::`vftable';
    v18[1] = -1;
    *(_QWORD *)this = v18;
  }
  if ( Sha256Helper::CryptProvider )
    CryptReleaseContext(Sha256Helper::CryptProvider, 0);
  Sha256Helper::CryptProvider = 0;
  if ( !CryptAcquireContextW(
          &Sha256Helper::CryptProvider,
          0,
          L"Microsoft Enhanced RSA and AES Cryptographic Provider",
          0x18u,
          0xF0000040) )
  {
    result = GetLastError();
    v20 = result < 0;
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v20 = result < 0;
    }
    if ( v20 )
      return result;
  }
  if ( (*(int (__fastcall **)(_QWORD, LPCWSTR, _QWORD))(**(_QWORD **)this + 8LL))(*(_QWORD *)this, lpFileName, 0) < 0 )
    return 0;
  result = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)this + 40LL))(*(_QWORD *)this, &v38);
  if ( result < 0 )
    return result;
  v22 = (char **)((char *)this + 5464);
  if ( *((_BYTE *)this + 5496) )
  {
    v23 = -1;
    do
      ++v23;
    while ( lpFileName[v23] );
    if ( v23 > *((_QWORD *)this + 686) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char *)this + 5464,
        v23,
        v21,
        lpFileName);
    }
    else
    {
      if ( *((_QWORD *)this + 686) <= 7u )
        v24 = (char *)this + 5464;
      else
        v24 = *v22;
      *((_QWORD *)this + 685) = v23;
      v25 = 2 * v23;
      memmove_0(v24, lpFileName, 2 * v23);
      *(_WORD *)&v24[v25] = 0;
    }
  }
  else
  {
    *(_OWORD *)v22 = 0;
    *((_QWORD *)this + 685) = 0;
    *((_QWORD *)this + 686) = 0;
    v26 = -1;
    do
      ++v26;
    while ( lpFileName[v26] );
    std::wstring::_Construct<1,unsigned short const *>((char *)this + 5464, lpFileName, v26);
    *((_BYTE *)this + 5496) = 1;
  }
  if ( v38 )
  {
    if ( (int)HNSObjectStorage::ReadFileData(this, &v34) >= 0 )
    {
      v27 = 0;
      if ( !v34 )
        return v27 != 0 ? 0x80070570 : 0;
    }
    else
    {
      v27 = 1;
    }
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
    *(_OWORD *)lpNewFileName = 0;
    v45 = 0;
    v46 = 0;
    do
      ++v5;
    while ( lpFileName[v5] );
    std::wstring::_Construct<1,unsigned short const *>(lpNewFileName, lpFileName, v5);
    std::wstring::append(lpNewFileName, L".corrupt");
    v28 = (const WCHAR *)lpNewFileName;
    if ( v46 > 7 )
      v28 = lpNewFileName[0];
    CopyFileW(lpFileName, v28, 0);
    if ( v27 )
      DeleteFileW(lpFileName);
    LOBYTE(v29) = 1;
    v30 = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR, __int64))(**(_QWORD **)this + 8LL))(
            *(_QWORD *)this,
            lpFileName,
            v29);
    if ( v30 < 0 )
    {
      std::wstring::~wstring(lpNewFileName);
      return v30;
    }
    std::wstring::~wstring(lpNewFileName);
    if ( !v27 )
      goto LABEL_59;
  }
  else
  {
    v27 = 0;
  }
  v35 = v27;
  HNSObjectStorage::Clear(this);
  v31 = (_QWORD **)((char *)this + 40);
  while ( 1 )
  {
    v32 = *v31;
    if ( !*v31 )
      break;
    *v31 = (_QWORD *)*v32;
    operator delete(v32, (const struct std::nothrow_t *)0x18);
  }
  result = SpanAllocator::AllocateSpan((HNSObjectStorage *)((char *)this + 40), 0, 0x80u);
  if ( result < 0 )
    return result;
  memset_0((char *)this + 304, 0, 0x1400u);
  try
  {
    *((_DWORD *)this + 1356) = 0;
    HNSObjectStorage::FlushObjects(this, 1u);
  }
  catch ( ... )
  {
    v37 = wil::ResultFromCaughtException(v33);
    HNSTraceProvider::TraceError("HNSObjectStorage::Initialize", 0x37Eu, v37);
    result = v37;
    if ( v37 >= 0 )
    {
      v27 = v35;
      goto LABEL_59;
    }
    return result;
  }
LABEL_59:
  if ( v34 )
    return -2147018053;
  return v27 != 0 ? 0x80070570 : 0;
}

```

## disassembly

```asm
0x1801a1080  mov     [rsp+arg_10], rbx
0x1801a1085  mov     [rsp+arg_18], rsi
0x1801a108a  push    rdi
0x1801a108b  push    r12
0x1801a108d  push    r13
0x1801a108f  push    r14
0x1801a1091  push    r15
0x1801a1093  sub     rsp, 0E0h
0x1801a109a  mov     rax, cs:__security_cookie
0x1801a10a1  xor     rax, rsp
0x1801a10a4  mov     [rsp+108h+var_38], rax
0x1801a10ac  mov     r14, rdx
0x1801a10af  mov     rsi, rcx
0x1801a10b2  xor     edi, edi
0x1801a10b4  mov     [rsp+108h+var_D0], edi
0x1801a10b8  mov     [rsp+108h+var_D8], dil
0x1801a10bd  mov     [rsp+108h+var_CC], edi
0x1801a10c1  mov     [rcx+1534h], edi
0x1801a10c7  mov     [rsp+108h+var_D4], edi
0x1801a10cb  mov     eax, edi
0x1801a10cd  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801a10d1  cmp     eax, 8
0x1801a10d4  jnb     loc_1801A124F
0x1801a10da  xorps   xmm0, xmm0
0x1801a10dd  movups  xmmword ptr [rsp+108h+lpNewFileName], xmm0
0x1801a10e2  mov     r13d, eax
0x1801a10e5  lea     rbx, ?m_registryStorePath@HNSObjectStorage@@1QBQEAGB; ushort * const near * const HNSObjectStorage::m_registryStorePath
0x1801a10ec  mov     ecx, 10h; Size
0x1801a10f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801a10f6  mov     r15, rax
0x1801a10f9  mov     [rsp+108h+var_C8], rax
0x1801a10fe  mov     r13, [rbx+r13*8]
0x1801a1102  mov     rbx, r12
0x1801a1105  inc     rbx
0x1801a1108  cmp     [r13+rbx*2+0], di
0x1801a110e  jnz     short loc_1801A1105
0x1801a1110  mov     [rax], rdi
0x1801a1113  lea     rcx, [rax+8]; unsigned int
0x1801a1117  mov     [rcx], rdi
0x1801a111a  mov     [rsp+108h+var_B8], r13
0x1801a111f  mov     [rsp+108h+var_B0], rbx
0x1801a1124  xor     r8d, r8d
0x1801a1127  lea     rdx, [rsp+108h+var_B8]
0x1801a112c  call    ?OpenRegistry@SharedMemory@Service@HNS@@YAXAEAVVmRegistryKey@Vml@@V?$basic_zstring_view@G@wil@@_N@Z; HNS::Service::SharedMemory::OpenRegistry(Vml::VmRegistryKey &,wil::basic_zstring_view<ushort>,bool)
0x1801a1131  mov     [rsp+108h+var_A8], r13
0x1801a1136  mov     [rsp+108h+var_A0], rbx
0x1801a113b  mov     r8b, 1
0x1801a113e  lea     rdx, [rsp+108h+var_A8]
0x1801a1143  mov     rcx, r15; unsigned int
0x1801a1146  call    ?OpenRegistry@SharedMemory@Service@HNS@@YAXAEAVVmRegistryKey@Vml@@V?$basic_zstring_view@G@wil@@_N@Z; HNS::Service::SharedMemory::OpenRegistry(Vml::VmRegistryKey &,wil::basic_zstring_view<ushort>,bool)
0x1801a114b  nop
0x1801a114c  mov     eax, [rsp+108h+var_D4]
0x1801a1150  mov     rbx, [rsi+rax*8+0F0h]
0x1801a1158  mov     [rsi+rax*8+0F0h], r15
0x1801a1160  test    rbx, rbx
0x1801a1163  jz      short loc_1801A1196
0x1801a1165  mov     rcx, [rbx+8]; hKey
0x1801a1169  test    rcx, rcx
0x1801a116c  jz      short loc_1801A1178
0x1801a116e  call    cs:__imp_RegCloseKey
0x1801a1174  mov     [rbx+8], rdi
0x1801a1178  cmp     [rbx], rdi
0x1801a117b  jz      short loc_1801A1189
0x1801a117d  mov     rcx, [rbx]; hKey
0x1801a1180  call    cs:__imp_RegCloseKey
0x1801a1186  mov     [rbx], rdi
0x1801a1189  mov     edx, 10h; struct std::nothrow_t *
0x1801a118e  mov     rcx, rbx; void *
0x1801a1191  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801a1196  mov     eax, [rsp+108h+var_D4]
0x1801a119a  mov     rbx, [rsi+rax*8+0F0h]
0x1801a11a2  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1f8e126b2954b720ae02b04bdb7ea558_@@XV?$basic_zstring_view@G@wil@@_NPEAEAEBK@std@@6B@; const std::_Func_impl_no_alloc<_lambda_1f8e126b2954b720ae02b04bdb7ea558_,void,wil::basic_zstring_view<ushort>,bool,uchar *,ulong const &>::`vftable'
0x1801a11a9  mov     [rsp+108h+var_78], rax
0x1801a11b1  lea     rax, [rsp+108h+lpNewFileName]
0x1801a11b6  mov     [rsp+108h+var_70], rax
0x1801a11be  mov     [rsp+108h+var_68], rsi
0x1801a11c6  lea     rax, [rsp+108h+var_D4]
0x1801a11cb  mov     [rsp+108h+var_60], rax
0x1801a11d3  lea     rax, [rsp+108h+var_78]
0x1801a11db  mov     [rsp+108h+var_40], rax
0x1801a11e3  lea     r9, [rsp+108h+var_78]
0x1801a11eb  mov     r8b, 1
0x1801a11ee  mov     rdx, rbx
0x1801a11f1  call    ?EnumerateSubStore@RegistryStore@SharedMemory@Service@HNS@@AEAAXAEAVVmRegistryKey@Vml@@_NAEBV?$function@$$A6AXV?$basic_zstring_view@G@wil@@_NPEAEAEBK@Z@std@@@Z; HNS::Service::SharedMemory::RegistryStore::EnumerateSubStore(Vml::VmRegistryKey &,bool,std::function<void (wil::basic_zstring_view<ushort>,bool,uchar *,ulong const &)> const &)
0x1801a11f6  lea     rdx, [rbx+8]
0x1801a11fa  lea     r9, [rsp+108h+var_78]
0x1801a1202  xor     r8d, r8d
0x1801a1205  call    ?EnumerateSubStore@RegistryStore@SharedMemory@Service@HNS@@AEAAXAEAVVmRegistryKey@Vml@@_NAEBV?$function@$$A6AXV?$basic_zstring_view@G@wil@@_NPEAEAEBK@Z@std@@@Z; HNS::Service::SharedMemory::RegistryStore::EnumerateSubStore(Vml::VmRegistryKey &,bool,std::function<void (wil::basic_zstring_view<ushort>,bool,uchar *,ulong const &)> const &)
0x1801a120a  nop
0x1801a120b  mov     rcx, [rsp+108h+var_40]
0x1801a1213  test    rcx, rcx
0x1801a1216  jz      short loc_1801A1232
0x1801a1218  mov     rax, [rcx]
0x1801a121b  lea     rdx, [rsp+108h+var_78]
0x1801a1223  cmp     rcx, rdx
0x1801a1226  setnz   dl
0x1801a1229  mov     rax, [rax+20h]
0x1801a122d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a1232  or      [rsp+108h+var_D0], 1
0x1801a1237  mov     eax, [rsp+108h+var_D4]
0x1801a123b  inc     eax
0x1801a123d  mov     [rsp+108h+var_D4], eax
0x1801a1241  jmp     loc_1801A10D1
0x1801a1246  mov     eax, [rsp+108h+var_CC]
0x1801a124a  jmp     loc_1801A1521
0x1801a124f  cmp     [rsi], rdi
0x1801a1252  jnz     short loc_1801A1284
0x1801a1254  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801a125b  mov     ecx, 10h; unsigned __int64
0x1801a1260  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801a1265  mov     [rsp+108h+var_C8], rax
0x1801a126a  test    rax, rax
0x1801a126d  jz      loc_1801A1349
0x1801a1273  lea     rcx, ??_7FileBlockStorage@@6B@; const FileBlockStorage::`vftable'
0x1801a127a  mov     [rax], rcx
0x1801a127d  mov     [rax+8], r12
0x1801a1281  mov     [rsi], rax
0x1801a1284  mov     rcx, cs:?CryptProvider@Sha256Helper@@0_KA; hProv
0x1801a128b  test    rcx, rcx
0x1801a128e  jz      short loc_1801A1298
0x1801a1290  xor     edx, edx; dwFlags
0x1801a1292  call    cs:__imp_CryptReleaseContext
0x1801a1298  mov     cs:?CryptProvider@Sha256Helper@@0_KA, rdi; unsigned __int64 Sha256Helper::CryptProvider
0x1801a129f  mov     [rsp+108h+dwFlags], 0F0000040h; dwFlags
0x1801a12a7  mov     r13d, 18h
0x1801a12ad  mov     r9d, r13d; dwProvType
0x1801a12b0  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x1801a12b7  xor     edx, edx; szContainer
0x1801a12b9  lea     rcx, ?CryptProvider@Sha256Helper@@0_KA; phProv
0x1801a12c0  call    cs:__imp_CryptAcquireContextW
0x1801a12c6  test    eax, eax
0x1801a12c8  jnz     short loc_1801A12E4
0x1801a12ca  call    cs:__imp_GetLastError
0x1801a12d0  test    eax, eax
0x1801a12d2  jle     short loc_1801A12DE
0x1801a12d4  movzx   eax, ax
0x1801a12d7  or      eax, 80070000h
0x1801a12dc  test    eax, eax
0x1801a12de  js      loc_1801A1521
0x1801a12e4  mov     rcx, [rsi]
0x1801a12e7  mov     rax, [rcx]
0x1801a12ea  xor     r8d, r8d
0x1801a12ed  mov     rdx, r14
0x1801a12f0  mov     rax, [rax+8]
0x1801a12f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a12f9  test    eax, eax
0x1801a12fb  js      loc_1801A151F
0x1801a1301  mov     rcx, [rsi]
0x1801a1304  mov     rax, [rcx]
0x1801a1307  lea     rdx, [rsp+108h+var_CC]
0x1801a130c  mov     rax, [rax+28h]
0x1801a1310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a1315  test    eax, eax
0x1801a1317  js      loc_1801A1521
0x1801a131d  lea     rbx, [rsi+1558h]
0x1801a1324  cmp     [rbx+20h], dil
0x1801a1328  jz      short loc_1801A1383
0x1801a132a  mov     rdx, r12
0x1801a132d  inc     rdx
0x1801a1330  cmp     [r14+rdx*2], di
0x1801a1335  jnz     short loc_1801A132D
0x1801a1337  cmp     rdx, [rbx+18h]
0x1801a133b  ja      short loc_1801A1376
0x1801a133d  cmp     qword ptr [rbx+18h], 7
0x1801a1342  jbe     short loc_1801A1356
0x1801a1344  mov     r15, [rbx]
0x1801a1347  jmp     short loc_1801A1359
0x1801a1349  mov     [rsi], rdi
0x1801a134c  mov     eax, 8007000Eh
0x1801a1351  jmp     loc_1801A1521
0x1801a1356  mov     r15, rbx
0x1801a1359  mov     [rbx+10h], rdx
0x1801a135d  lea     rbx, [rdx+rdx]
0x1801a1361  mov     r8, rbx; Size
0x1801a1364  mov     rdx, r14; Src
0x1801a1367  mov     rcx, r15; void *
0x1801a136a  call    memmove_0
0x1801a136f  mov     [rbx+r15], di
0x1801a1374  jmp     short loc_1801A13AD
0x1801a1376  mov     r9, r14
0x1801a1379  mov     rcx, rbx
0x1801a137c  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1801a1381  jmp     short loc_1801A13AD
0x1801a1383  xorps   xmm0, xmm0
0x1801a1386  movups  xmmword ptr [rbx], xmm0
0x1801a1389  mov     [rbx+10h], rdi
0x1801a138d  mov     [rbx+18h], rdi
0x1801a1391  mov     r8, r12
0x1801a1394  inc     r8
0x1801a1397  cmp     [r14+r8*2], di
0x1801a139c  jnz     short loc_1801A1394
0x1801a139e  mov     rdx, r14
0x1801a13a1  mov     rcx, rbx
0x1801a13a4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1801a13a9  mov     byte ptr [rbx+20h], 1
0x1801a13ad  cmp     [rsp+108h+var_CC], edi
0x1801a13b1  jnz     short loc_1801A13BB
0x1801a13b3  mov     bl, dil
0x1801a13b6  jmp     loc_1801A1495
0x1801a13bb  lea     rdx, [rsp+108h+var_D8]; bool *
0x1801a13c0  mov     rcx, rsi; this
0x1801a13c3  call    ?ReadFileData@HNSObjectStorage@@IEAAJAEA_N@Z; HNSObjectStorage::ReadFileData(bool &)
0x1801a13c8  test    eax, eax
0x1801a13ca  jns     short loc_1801A13D0
0x1801a13cc  mov     bl, 1
0x1801a13ce  jmp     short loc_1801A13DE
0x1801a13d0  mov     bl, dil
0x1801a13d3  cmp     [rsp+108h+var_D8], dil
0x1801a13d8  jz      loc_1801A1514
0x1801a13de  mov     rcx, [rsi]
0x1801a13e1  mov     rax, [rcx]
0x1801a13e4  mov     rax, [rax+10h]
0x1801a13e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a13ed  xorps   xmm0, xmm0
0x1801a13f0  movups  xmmword ptr [rsp+108h+lpNewFileName], xmm0
0x1801a13f5  mov     [rsp+108h+var_88], rdi
0x1801a13fd  mov     [rsp+108h+var_80], rdi
0x1801a1405  inc     r12
0x1801a1408  cmp     [r14+r12*2], di
0x1801a140d  jnz     short loc_1801A1405
0x1801a140f  mov     r8, r12
0x1801a1412  mov     rdx, r14
0x1801a1415  lea     rcx, [rsp+108h+lpNewFileName]
0x1801a141a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1801a141f  nop
0x1801a1420  lea     rdx, aCorrupt; ".corrupt"
0x1801a1427  lea     rcx, [rsp+108h+lpNewFileName]; Src
0x1801a142c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1801a1431  lea     rdx, [rsp+108h+lpNewFileName]
0x1801a1436  cmp     [rsp+108h+var_80], 7
0x1801a143f  cmova   rdx, [rsp+108h+lpNewFileName]; lpNewFileName
0x1801a1445  xor     r8d, r8d; bFailIfExists
0x1801a1448  mov     rcx, r14; lpExistingFileName
0x1801a144b  call    cs:__imp_CopyFileW
0x1801a1451  test    bl, bl
0x1801a1453  jz      short loc_1801A145E
0x1801a1455  mov     rcx, r14; lpFileName
0x1801a1458  call    cs:__imp_DeleteFileW
0x1801a145e  mov     rcx, [rsi]
0x1801a1461  mov     rax, [rcx]
0x1801a1464  mov     r8b, 1
0x1801a1467  mov     rdx, r14
0x1801a146a  mov     rax, [rax+8]
0x1801a146e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a1473  mov     r14d, eax
0x1801a1476  lea     rcx, [rsp+108h+lpNewFileName]; void *
0x1801a147b  test    eax, eax
0x1801a147d  jns     short loc_1801A148C
0x1801a147f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a1484  mov     eax, r14d
0x1801a1487  jmp     loc_1801A1521
0x1801a148c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a1491  test    bl, bl
0x1801a1493  jz      short loc_1801A1506
0x1801a1495  mov     [rsp+108h+var_D7], bl
0x1801a1499  mov     rcx, rsi; this
0x1801a149c  call    ?Clear@HNSObjectStorage@@IEAAXXZ; HNSObjectStorage::Clear(void)
0x1801a14a1  lea     r14, [rsi+28h]
0x1801a14a5  jmp     short loc_1801A14B5
0x1801a14a7  mov     rax, [rcx]
0x1801a14aa  mov     [r14], rax
0x1801a14ad  mov     rdx, r13; struct std::nothrow_t *
0x1801a14b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801a14b5  mov     rcx, [r14]; void *
0x1801a14b8  test    rcx, rcx
0x1801a14bb  jnz     short loc_1801A14A7
0x1801a14bd  xor     edx, edx; unsigned int
0x1801a14bf  mov     r8d, 80h; unsigned int
0x1801a14c5  mov     rcx, r14; this
0x1801a14c8  call    ?AllocateSpan@SpanAllocator@@QEAAJKK@Z; SpanAllocator::AllocateSpan(ulong,ulong)
0x1801a14cd  test    eax, eax
0x1801a14cf  js      short loc_1801A1521
0x1801a14d1  lea     rcx, [rsi+130h]; void *
0x1801a14d8  xor     edx, edx; Val
0x1801a14da  mov     r8d, 1400h; Size
0x1801a14e0  call    memset_0
0x1801a14e5  mov     [rsi+1530h], edi
0x1801a14eb  mov     dl, 1; unsigned __int8
0x1801a14ed  mov     rcx, rsi; this
0x1801a14f0  call    ?FlushObjects@HNSObjectStorage@@QEAAXE@Z; HNSObjectStorage::FlushObjects(uchar)
0x1801a14f5  nop
0x1801a14f6  jmp     short loc_1801A1506
0x1801a14f8  mov     eax, [rsp+108h+var_D0]
0x1801a14fc  xor     edi, edi
0x1801a14fe  test    eax, eax
0x1801a1500  js      short loc_1801A1521
0x1801a1502  mov     bl, [rsp+108h+var_D7]
0x1801a1506  cmp     [rsp+108h+var_D8], dil
0x1801a150b  jz      short loc_1801A1514
0x1801a150d  mov     eax, 80071ABBh
0x1801a1512  jmp     short loc_1801A1521
0x1801a1514  neg     bl
0x1801a1516  sbb     eax, eax
0x1801a1518  and     eax, 80070570h
0x1801a151d  jmp     short loc_1801A1521
0x1801a151f  xor     eax, eax
0x1801a1521  mov     rcx, [rsp+108h+var_38]
0x1801a1529  xor     rcx, rsp; StackCookie
0x1801a152c  call    __security_check_cookie
0x1801a1531  lea     r11, [rsp+108h+var_28]
  ... truncated ...
```
