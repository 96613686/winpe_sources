# RepoMan::CRepository::CRepository(RepoMan::CRepoMan *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,_REPOMAN_OPEN_OPTIONS,ConfigureOptions,RepoMan::CRepository::FormatDetails const &)

- ea: `0x1800a3d1c`
- end: `0x1800a4117`
- name: `??0CRepository@RepoMan@@QEAA@PEAVCRepoMan@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4_REPOMAN_OPEN_OPTIONS@@W4ConfigureOptions@@AEBUFormatDetails@01@@Z`
- size: `1019`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x1800b22e4`

## callees

- `0x1800028e8`
- `0x180003710`
- `0x1800038ac`
- `0x180008084`
- `0x180009368`
- `0x18000ac38`
- `0x18000b388`
- `0x180013b14`
- `0x1800a30dc`
- `0x1800a3d1c`
- `0x1800aed50`
- `0x1800ddb48`
- `0x1800dfffc`
- `0x18018cdf8`
- `0x18018e288`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a3da1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a3e94`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a3da1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a3e94`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a3e4d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a3f74`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a409f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a3e4d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a3f74`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a409f`

## string_xrefs

- `0x1800a3e7b`: `CRepository.OpenReadOnlyDB`
- `0x1800a3f90`: `CRepository.CreateOrOpenDB`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
_QWORD *__fastcall RepoMan::CRepository::CRepository(
        _QWORD *a1,
        __int64 a2,
        const CHAR *a3,
        char a4,
        __int64 a5,
        struct RepoMan::CRepository::FormatDetails *a6)
{
  __int64 v9; // rbx
  _QWORD *v10; // rax
  void *v11; // rcx
  void **v12; // rax
  void *v13; // rcx
  void *v14; // rdi
  IStream *v15; // rcx
  void *v16; // rax
  IStream *v17; // rcx
  __int64 *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  void *v21; // rbx
  IStream *v22; // rcx
  __int64 v23; // rax
  __int64 *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  void *v27; // rbx
  IStream *v29; // [rsp+30h] [rbp-79h] BYREF
  void *Block; // [rsp+38h] [rbp-71h] BYREF
  void *v31; // [rsp+40h] [rbp-69h] BYREF
  void *v32[2]; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v33[40]; // [rsp+58h] [rbp-51h] BYREF
  __int64 v34; // [rsp+80h] [rbp-29h]
  _BYTE v35[48]; // [rsp+88h] [rbp-21h] BYREF

  v32[1] = a1;
  v9 = a5;
  *((_DWORD *)a1 + 2) = 1;
  *a1 = &RepoMan::CRepository::`vftable';
  a1[2] = a2;
  *((_DWORD *)a1 + 6) = 2;
  a1[4] = 0;
  RepoMan::CRepository::FormatDetails::FormatDetails((RepoMan::CRepository::FormatDetails *)(a1 + 5), a6);
  v32[0] = a1 + 14;
  a1[14] = 0;
  a1[15] = 0;
  v10 = malloc(0x48u);
  if ( !v10 )
    std::_Xbad_alloc();
  *v10 = v10;
  v10[1] = v10;
  v10[2] = v10;
  *((_WORD *)v10 + 12) = 257;
  a1[14] = v10;
  RepoMan::Tracer::Tracer(v33, 1, "CRepository.ctor");
  if ( (a4 & 1) != 0 )
  {
    v31 = 0;
    if ( (a5 & 4) != 0 )
    {
      Block = 0;
      RepoMan::FileSystem::OpenFileAsStream(&v29, a3, 0, &Block, 0);
      v11 = Block;
      if ( Block )
        (*(void (__fastcall **)(void *))(*(_QWORD *)Block + 16LL))(Block);
      v12 = (void **)RepoMan::CRepository::CreateInMemoryDB(v11, &Block, v29);
      v13 = *v12;
      *v12 = 0;
      v31 = v13;
      v14 = Block;
      if ( Block )
      {
        sqlite3pp::database::~database((sqlite3pp::database *)((char *)Block + 88));
        free(v14);
      }
      v15 = v29;
      if ( v29 )
      {
        v29 = 0;
        ((void (__fastcall *)(IStream *))v15->lpVtbl->Release)(v15);
      }
    }
    else
    {
      *((_DWORD *)a1 + 6) = 1;
      RepoMan::Tracer::Tracer(v35, 1, "CRepository.OpenReadOnlyDB");
      v16 = malloc(0x1A8u);
      if ( !v16 )
        std::_Xbad_alloc();
      v32[0] = v16;
      v31 = (void *)RepoMan::Database::Database(v16, a3, 1);
      RepoMan::Logger::CreateValue((unsigned int)&v29, 1, 9, (_DWORD)a3, 0);
      (*(void (__fastcall **)(__int64, IStream **))(*(_QWORD *)v34 + 48LL))(v34, &v29);
      v17 = v29;
      if ( v29 )
      {
        v29 = 0;
        ((void (__fastcall *)(IStream *))v17->lpVtbl->AddRef)(v17);
      }
      RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v35);
    }
    v18 = (__int64 *)RepoMan::Schema::Make(&Block, &v31, a5);
    v19 = *v18;
    *v18 = 0;
    v20 = a1[4];
    a1[4] = v19;
    if ( v20 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 24LL))(v20, 1);
    if ( Block )
      (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)Block + 24LL))(Block, 1);
    v21 = v31;
    if ( v31 )
    {
      sqlite3pp::database::~database((sqlite3pp::database *)((char *)v31 + 88));
      free(v21);
    }
  }
  else
  {
    if ( (a4 & 2) == 0 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        104,
        (unsigned int)"src\\repoman\\src\\inc\\Repository.hpp",
        (unsigned int)"call failed",
        -2147418113,
        8);
    LODWORD(v31) = 6;
    RepoMan::Tracer::Tracer(v35, 1, "CRepository.CreateOrOpenDB");
    if ( (unsigned __int8)RepoMan::CRepoMan::FlightValue(a1[2], 8) )
    {
      v9 = a5 | 0x18;
    }
    else if ( !RepoMan::Folder::Exists(a3) )
    {
      v9 = a5 | 8;
    }
    RepoMan::Logger::CreateValue((unsigned int)&v29, 1, 9, (_DWORD)a3, 0);
    (*(void (__fastcall **)(__int64, IStream **))(*(_QWORD *)v34 + 48LL))(v34, &v29);
    v22 = v29;
    if ( v29 )
    {
      v29 = 0;
      ((void (__fastcall *)(IStream *))v22->lpVtbl->AddRef)(v22);
    }
    if ( *((_QWORD *)a3 + 3) > 0xFu )
      a3 = *(const CHAR **)a3;
    v29 = (IStream *)a3;
    v23 = std::make_unique<RepoMan::Database,char const *,int &,0>(v32, &v29, &v31);
    v24 = (__int64 *)RepoMan::Schema::Make(&Block, v23, v9);
    v25 = *v24;
    *v24 = 0;
    v26 = a1[4];
    a1[4] = v25;
    if ( v26 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 24LL))(v26, 1);
    if ( Block )
      (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)Block + 24LL))(Block, 1);
    Block = (void *)19937;
    v27 = v32[0];
    if ( v32[0] )
    {
      sqlite3pp::database::~database((sqlite3pp::database *)((char *)v32[0] + 88));
      free(v27);
    }
    RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v35);
  }
  RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v33);
  return a1;
}

```

## disassembly

```asm
0x1800a3d1c  mov     [rsp-8+arg_8], rbx
0x1800a3d21  push    rbp
0x1800a3d22  push    rsi
0x1800a3d23  push    rdi
0x1800a3d24  push    r12
0x1800a3d26  push    r13
0x1800a3d28  push    r14
0x1800a3d2a  push    r15
0x1800a3d2c  lea     rbp, [rsp-17h]
0x1800a3d31  sub     rsp, 0C0h
0x1800a3d38  mov     rax, cs:__security_cookie
0x1800a3d3f  xor     rax, rsp
0x1800a3d42  mov     [rbp+47h+var_38], rax
0x1800a3d46  mov     r14d, r9d
0x1800a3d49  mov     rdi, r8
0x1800a3d4c  mov     rax, rdx
0x1800a3d4f  mov     rsi, rcx
0x1800a3d52  mov     [rbp+47h+var_A0], rcx
0x1800a3d56  mov     rbx, [rbp+47h+arg_20]
0x1800a3d5a  mov     rdx, [rbp+47h+arg_28]; struct RepoMan::CRepository::FormatDetails *
0x1800a3d5e  xor     r12d, r12d
0x1800a3d61  lea     r13d, [r12+1]
0x1800a3d66  mov     [rcx+8], r13d
0x1800a3d6a  lea     rcx, ??_7CRepository@RepoMan@@6B@; const RepoMan::CRepository::`vftable'
0x1800a3d71  mov     [rsi], rcx
0x1800a3d74  mov     [rsi+10h], rax
0x1800a3d78  mov     dword ptr [rsi+18h], 2
0x1800a3d7f  mov     [rsi+20h], r12
0x1800a3d83  lea     rcx, [rsi+28h]; this
0x1800a3d87  call    ??0FormatDetails@CRepository@RepoMan@@QEAA@AEBU012@@Z; RepoMan::CRepository::FormatDetails::FormatDetails(RepoMan::CRepository::FormatDetails const &)
0x1800a3d8c  nop
0x1800a3d8d  lea     r15, [rsi+70h]
0x1800a3d91  mov     [rbp+47h+var_A8], r15
0x1800a3d95  mov     [r15], r12
0x1800a3d98  mov     [r15+8], r12
0x1800a3d9c  lea     ecx, [r12+48h]; Size
0x1800a3da1  call    cs:__imp_malloc
0x1800a3da7  test    rax, rax
0x1800a3daa  jz      loc_1800A4111
0x1800a3db0  mov     [rax], rax
0x1800a3db3  mov     [rax+8], rax
0x1800a3db7  mov     [rax+10h], rax
0x1800a3dbb  mov     word ptr [rax+18h], 101h
0x1800a3dc1  mov     [r15], rax
0x1800a3dc4  lea     r8, aCrepositoryCto_0; "CRepository.ctor"
0x1800a3dcb  mov     edx, r13d
0x1800a3dce  lea     rcx, [rbp+47h+var_98]
0x1800a3dd2  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x1800a3dd7  nop
0x1800a3dd8  test    r13b, r14b
0x1800a3ddb  jz      loc_1800A3F7F
0x1800a3de1  mov     [rbp+47h+var_B0], r12
0x1800a3de5  test    bl, 4
0x1800a3de8  jz      loc_1800A3E77
0x1800a3dee  mov     [rbp+47h+Block], r12
0x1800a3df2  mov     byte ptr [rsp+0F0h+var_D0], r12b
0x1800a3df7  lea     r9, [rbp+47h+Block]
0x1800a3dfb  xor     r8d, r8d
0x1800a3dfe  mov     rdx, rdi
0x1800a3e01  lea     rcx, [rbp+47h+var_C0]
0x1800a3e05  call    ?OpenFileAsStream@FileSystem@RepoMan@@YA?AV?$ComPtr@UIStream@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4OpenMode@12@AEBV?$ComPtr@UIRepoProgress@@@2@W4OpenFlags@@@Z; RepoMan::FileSystem::OpenFileAsStream(std::string const &,RepoMan::FileSystem::OpenMode,RepoMan::ComPtr<IRepoProgress> const &,OpenFlags)
0x1800a3e0a  nop
0x1800a3e0b  mov     rcx, [rbp+47h+Block]
0x1800a3e0f  test    rcx, rcx
0x1800a3e12  jz      short loc_1800A3E21
0x1800a3e14  mov     rax, [rcx]
0x1800a3e17  mov     rax, [rax+10h]
0x1800a3e1b  call    cs:__guard_dispatch_icall_fptr
0x1800a3e21  mov     r8, [rbp+47h+var_C0]
0x1800a3e25  lea     rdx, [rbp+47h+Block]
0x1800a3e29  call    ?CreateInMemoryDB@CRepository@RepoMan@@QEAA?AV?$unique_ptr@VDatabase@RepoMan@@U?$default_delete@VDatabase@RepoMan@@@std@@@std@@PEAUIStream@@@Z; RepoMan::CRepository::CreateInMemoryDB(IStream *)
0x1800a3e2e  mov     rcx, [rax]
0x1800a3e31  mov     [rax], r12
0x1800a3e34  mov     [rbp+47h+var_B0], rcx
0x1800a3e38  mov     rdi, [rbp+47h+Block]
0x1800a3e3c  test    rdi, rdi
0x1800a3e3f  jz      short loc_1800A3E54
0x1800a3e41  lea     rcx, [rdi+58h]; this
0x1800a3e45  call    ??1database@sqlite3pp@@QEAA@XZ; sqlite3pp::database::~database(void)
0x1800a3e4a  mov     rcx, rdi; Block
0x1800a3e4d  call    cs:__imp_free
0x1800a3e53  nop
0x1800a3e54  mov     rcx, [rbp+47h+var_C0]
0x1800a3e58  test    rcx, rcx
0x1800a3e5b  jz      loc_1800A3F0E
0x1800a3e61  mov     [rbp+47h+var_C0], r12
0x1800a3e65  mov     rax, [rcx]
0x1800a3e68  mov     rax, [rax+10h]
0x1800a3e6c  call    cs:__guard_dispatch_icall_fptr
0x1800a3e72  jmp     loc_1800A3F0E
0x1800a3e77  mov     [rsi+18h], r13d
0x1800a3e7b  lea     r8, aCrepositoryOpe; "CRepository.OpenReadOnlyDB"
0x1800a3e82  mov     edx, r13d
0x1800a3e85  lea     rcx, [rbp+47h+var_68]
0x1800a3e89  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x1800a3e8e  nop
0x1800a3e8f  mov     ecx, 1A8h; Size
0x1800a3e94  call    cs:__imp_malloc
0x1800a3e9a  test    rax, rax
0x1800a3e9d  jz      loc_1800A40E4
0x1800a3ea3  mov     [rbp+47h+var_A8], rax
0x1800a3ea7  mov     r8d, r13d
0x1800a3eaa  mov     rdx, rdi
0x1800a3ead  mov     rcx, rax
0x1800a3eb0  call    ??0Database@RepoMan@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@Z; RepoMan::Database::Database(std::string const &,int)
0x1800a3eb5  nop
0x1800a3eb6  mov     [rbp+47h+var_B0], rax
0x1800a3eba  mov     [rsp+0F0h+var_D0], r12
0x1800a3ebf  mov     r9, rdi
0x1800a3ec2  mov     r8d, 9
0x1800a3ec8  mov     edx, r13d
0x1800a3ecb  lea     rcx, [rbp+47h+var_C0]
0x1800a3ecf  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x1800a3ed4  mov     rcx, [rbp+47h+var_70]
0x1800a3ed8  mov     rax, [rcx]
0x1800a3edb  lea     rdx, [rbp+47h+var_C0]
0x1800a3edf  mov     rax, [rax+30h]
0x1800a3ee3  call    cs:__guard_dispatch_icall_fptr
0x1800a3ee9  nop
0x1800a3eea  mov     rcx, [rbp+47h+var_C0]
0x1800a3eee  test    rcx, rcx
0x1800a3ef1  jz      short loc_1800A3F05
0x1800a3ef3  mov     [rbp+47h+var_C0], r12
0x1800a3ef7  mov     rax, [rcx]
0x1800a3efa  mov     rax, [rax+8]
0x1800a3efe  call    cs:__guard_dispatch_icall_fptr
0x1800a3f04  nop
0x1800a3f05  lea     rcx, [rbp+47h+var_68]; this
0x1800a3f09  call    ??1Tracer@RepoMan@@QEAA@XZ; RepoMan::Tracer::~Tracer(void)
0x1800a3f0e  mov     r8, rbx
0x1800a3f11  lea     rdx, [rbp+47h+var_B0]
0x1800a3f15  lea     rcx, [rbp+47h+Block]
0x1800a3f19  call    ?Make@Schema@RepoMan@@SA?AV?$unique_ptr@VSchema@RepoMan@@U?$default_delete@VSchema@RepoMan@@@std@@@std@@$$QEAV?$unique_ptr@VDatabase@RepoMan@@U?$default_delete@VDatabase@RepoMan@@@std@@@4@W4ConfigureOptions@@@Z; RepoMan::Schema::Make(std::unique_ptr<RepoMan::Database> &&,ConfigureOptions)
0x1800a3f1e  mov     rdx, [rax]
0x1800a3f21  mov     [rax], r12
0x1800a3f24  mov     rcx, [rsi+20h]
0x1800a3f28  mov     [rsi+20h], rdx
0x1800a3f2c  test    rcx, rcx
0x1800a3f2f  jz      short loc_1800A3F41
0x1800a3f31  mov     rax, [rcx]
0x1800a3f34  mov     edx, r13d
0x1800a3f37  mov     rax, [rax+18h]
0x1800a3f3b  call    cs:__guard_dispatch_icall_fptr
0x1800a3f41  mov     rcx, [rbp+47h+Block]
0x1800a3f45  test    rcx, rcx
0x1800a3f48  jz      short loc_1800A3F5B
0x1800a3f4a  mov     rax, [rcx]
0x1800a3f4d  mov     edx, r13d
0x1800a3f50  mov     rax, [rax+18h]
0x1800a3f54  call    cs:__guard_dispatch_icall_fptr
0x1800a3f5a  nop
0x1800a3f5b  mov     rbx, [rbp+47h+var_B0]
0x1800a3f5f  test    rbx, rbx
0x1800a3f62  jz      loc_1800A40B0
0x1800a3f68  lea     rcx, [rbx+58h]; this
0x1800a3f6c  call    ??1database@sqlite3pp@@QEAA@XZ; sqlite3pp::database::~database(void)
0x1800a3f71  mov     rcx, rbx; Block
0x1800a3f74  call    cs:__imp_free
0x1800a3f7a  jmp     loc_1800A40B0
0x1800a3f7f  test    r14b, 2
0x1800a3f83  jz      loc_1800A40EA
0x1800a3f89  mov     dword ptr [rbp+47h+var_B0], 6
0x1800a3f90  lea     r8, aCrepositoryCre; "CRepository.CreateOrOpenDB"
0x1800a3f97  mov     edx, r13d
0x1800a3f9a  lea     rcx, [rbp+47h+var_68]
0x1800a3f9e  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x1800a3fa3  nop
0x1800a3fa4  mov     edx, 8
0x1800a3fa9  mov     rcx, [rsi+10h]
0x1800a3fad  call    ?FlightValue@CRepoMan@RepoMan@@QEBA_NW4_REPOMAN_FLIGHT@@@Z; RepoMan::CRepoMan::FlightValue(_REPOMAN_FLIGHT)
0x1800a3fb2  test    al, al
0x1800a3fb4  jz      short loc_1800A3FBC
0x1800a3fb6  or      rbx, 18h
0x1800a3fba  jmp     short loc_1800A3FCC
0x1800a3fbc  mov     rcx, rdi; lpMultiByteStr
0x1800a3fbf  call    ?Exists@Folder@RepoMan@@QEBA_NXZ; RepoMan::Folder::Exists(void)
0x1800a3fc4  test    al, al
0x1800a3fc6  jnz     short loc_1800A3FCC
0x1800a3fc8  or      rbx, 8
0x1800a3fcc  mov     [rsp+0F0h+var_D0], r12
0x1800a3fd1  mov     r9, rdi
0x1800a3fd4  mov     r8d, 9
0x1800a3fda  mov     edx, r13d
0x1800a3fdd  lea     rcx, [rbp+47h+var_C0]
0x1800a3fe1  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x1800a3fe6  mov     rcx, [rbp+47h+var_70]
0x1800a3fea  mov     rax, [rcx]
0x1800a3fed  lea     rdx, [rbp+47h+var_C0]
0x1800a3ff1  mov     rax, [rax+30h]
0x1800a3ff5  call    cs:__guard_dispatch_icall_fptr
0x1800a3ffb  nop
0x1800a3ffc  mov     rcx, [rbp+47h+var_C0]
0x1800a4000  test    rcx, rcx
0x1800a4003  jz      short loc_1800A4017
0x1800a4005  mov     [rbp+47h+var_C0], r12
0x1800a4009  mov     rax, [rcx]
0x1800a400c  mov     rax, [rax+8]
0x1800a4010  call    cs:__guard_dispatch_icall_fptr
0x1800a4016  nop
0x1800a4017  cmp     qword ptr [rdi+18h], 0Fh
0x1800a401c  jbe     short loc_1800A4021
0x1800a401e  mov     rdi, [rdi]
0x1800a4021  mov     [rbp+47h+var_C0], rdi
0x1800a4025  lea     r8, [rbp+47h+var_B0]
0x1800a4029  lea     rdx, [rbp+47h+var_C0]
0x1800a402d  lea     rcx, [rbp+47h+var_A8]
0x1800a4031  call    ??$make_unique@VDatabase@RepoMan@@PEBDAEAH$0A@@std@@YA?AV?$unique_ptr@VDatabase@RepoMan@@U?$default_delete@VDatabase@RepoMan@@@std@@@0@$$QEAPEBDAEAH@Z; std::make_unique<RepoMan::Database,char const *,int &,0>(char const * &&,int &)
0x1800a4036  nop
0x1800a4037  mov     r8, rbx
0x1800a403a  mov     rdx, rax
0x1800a403d  lea     rcx, [rbp+47h+Block]
0x1800a4041  call    ?Make@Schema@RepoMan@@SA?AV?$unique_ptr@VSchema@RepoMan@@U?$default_delete@VSchema@RepoMan@@@std@@@std@@$$QEAV?$unique_ptr@VDatabase@RepoMan@@U?$default_delete@VDatabase@RepoMan@@@std@@@4@W4ConfigureOptions@@@Z; RepoMan::Schema::Make(std::unique_ptr<RepoMan::Database> &&,ConfigureOptions)
0x1800a4046  mov     rdx, [rax]
0x1800a4049  mov     [rax], r12
0x1800a404c  mov     rcx, [rsi+20h]
0x1800a4050  mov     [rsi+20h], rdx
0x1800a4054  test    rcx, rcx
0x1800a4057  jz      short loc_1800A4069
0x1800a4059  mov     rax, [rcx]
0x1800a405c  mov     edx, r13d
0x1800a405f  mov     rax, [rax+18h]
0x1800a4063  call    cs:__guard_dispatch_icall_fptr
0x1800a4069  mov     rcx, [rbp+47h+Block]
0x1800a406d  test    rcx, rcx
0x1800a4070  jz      short loc_1800A4082
0x1800a4072  mov     rax, [rcx]
0x1800a4075  mov     edx, r13d
0x1800a4078  mov     rax, [rax+18h]
0x1800a407c  call    cs:__guard_dispatch_icall_fptr
0x1800a4082  mov     [rbp+47h+Block], 4DE1h
0x1800a408a  mov     rbx, [rbp+47h+var_A8]
0x1800a408e  test    rbx, rbx
0x1800a4091  jz      short loc_1800A40A6
0x1800a4093  lea     rcx, [rbx+58h]; this
0x1800a4097  call    ??1database@sqlite3pp@@QEAA@XZ; sqlite3pp::database::~database(void)
0x1800a409c  mov     rcx, rbx; Block
0x1800a409f  call    cs:__imp_free
0x1800a40a5  nop
0x1800a40a6  lea     rcx, [rbp+47h+var_68]; this
0x1800a40aa  call    ??1Tracer@RepoMan@@QEAA@XZ; RepoMan::Tracer::~Tracer(void)
0x1800a40af  nop
0x1800a40b0  lea     rcx, [rbp+47h+var_98]; this
0x1800a40b4  call    ??1Tracer@RepoMan@@QEAA@XZ; RepoMan::Tracer::~Tracer(void)
0x1800a40b9  nop
0x1800a40ba  mov     rax, rsi
0x1800a40bd  mov     rcx, [rbp+47h+var_38]
0x1800a40c1  xor     rcx, rsp; StackCookie
0x1800a40c4  call    __security_check_cookie
0x1800a40c9  mov     rbx, [rsp+0F0h+arg_8]
0x1800a40d1  add     rsp, 0C0h
0x1800a40d8  pop     r15
0x1800a40da  pop     r14
0x1800a40dc  pop     r13
0x1800a40de  pop     r12
0x1800a40e0  pop     rdi
0x1800a40e1  pop     rsi
0x1800a40e2  pop     rbp
0x1800a40e3  retn
0x1800a40e4  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800a40ea  mov     dword ptr [rsp+0F0h+var_D0], 8
0x1800a40f2  mov     r9d, 8000FFFFh
0x1800a40f8  lea     r8, aCallFailed; "call failed"
0x1800a40ff  lea     rdx, aSrcRepomanSrcI_19; "src\\repoman\\src\\inc\\Repository.hpp"
0x1800a4106  mov     ecx, 68h ; 'h'
0x1800a410b  call    ??$RaiseException@VException@RepoMan@@W4Error@2@@RepoMan@@YAXHQEBDPEBDW4Error@0@W4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Exception,RepoMan::Error>(int,char const * const,char const *,RepoMan::Error,RepoMan::ILogger::Verbosity)
0x1800a4111  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
