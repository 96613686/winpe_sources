# CONFIG_SYSTEM::GetMetadata(ushort *,tagVARIANT *)

- ea: `0x180016e30`
- end: `0x1800172f6`
- name: `?GetMetadata@CONFIG_SYSTEM@@UEAAJPEAGPEAUtagVARIANT@@@Z`
- size: `1222`
- prototype: `int(CONFIG_SYSTEM *__hidden this, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x180016e30`
- `0x18001aa7c`
- `0x18004f374`
- `0x180056128`
- `0x180059bea`
- `0x180059bf6`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017083`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017083`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180017060`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180017060`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180016f5f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017231`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180016f5f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017231`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180016ffc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180017182`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001720f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180016ffc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180017182`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001720f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180016e88`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180016e88`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800171ef`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800171ef`
- `OLEAUT32!__imp_SysAllocString` at `0x180017005`
- `OLEAUT32!__imp_SysAllocString` at `0x1800171a7`
- `OLEAUT32!__imp_SysAllocString` at `0x180017218`
- `OLEAUT32!__imp_SysAllocString` at `0x180017264`
- `OLEAUT32!__imp_SysAllocString` at `0x180017005`
- `OLEAUT32!__imp_SysAllocString` at `0x1800171a7`
- `OLEAUT32!__imp_SysAllocString` at `0x180017218`
- `OLEAUT32!__imp_SysAllocString` at `0x180017264`

## string_xrefs

- `0x180016ea3`: `pathMapper`
- `0x180016ebc`: `pathMapper2`
- `0x180016f92`: `disableExtensions`
- `0x180017017`: `mappingExtension`
- `0x18001723f`: `availableReadableMetadata`
- `0x18001710d`: `hideExceptionPhysicalPath`
- `0x1800171da`: `schemaPath`
- `0x18001724f`: `pathMapper,pathMapper2,changeHandler,ignoreInvalidAttributes,ignoreInvalidRanges,ignoreInvalidDecryption,expandEnvironmentStrings,disableExtensions,availableSections,mappingExtension,hideExceptionPhysicalPath,lockMetadata,managedRuntimeVersion,defaultManagedRuntimeVersion,schemaPath`
- `0x180017258`: `pathMapper,pathMapper2,changeHandler,ignoreInvalidAttributes,ignoreInvalidRanges,ignoreInvalidDecryption,expandEnvironmentStrings,disableExtensions,hideExceptionPhysicalPath,lockMetadata,defaultManagedRuntimeVersion`

## pseudocode

```c
__int64 __fastcall CONFIG_SYSTEM::GetMetadata(RTL_SRWLOCK *this, unsigned __int16 *a2, struct tagVARIANT *a3)
{
  int v6; // esi
  LONGLONG v7; // rbp
  signed int PathMapper; // esi
  SCHEMA_TABLE *Ptr; // rcx
  const OLECHAR *Str; // rax
  PVOID v12; // rax
  RTL_SRWLOCK *v13; // rbx
  LONGLONG v14; // r14
  VARTYPE v15; // bp
  const OLECHAR *v16; // rcx
  BSTR v17; // rax
  const OLECHAR *v18; // rax
  BSTR v19; // rax
  const OLECHAR *v20; // rcx
  BSTR v21; // rax
  VARTYPE v22; // bp
  GUID *v23; // r8
  struct IUnknown *v24; // [rsp+20h] [rbp-2A8h] BYREF
  _BYTE v25[56]; // [rsp+28h] [rbp-2A0h] BYREF
  _BYTE v26[64]; // [rsp+60h] [rbp-268h] BYREF
  unsigned __int16 v27[256]; // [rsp+A0h] [rbp-228h] BYREF

  memset_0(v27, 0, sizeof(v27));
  STRU::STRU((STRU *)v26, v27, 0x100u);
  if ( !a2 || !a3 )
  {
    PathMapper = -2147024809;
    goto LABEL_11;
  }
  v6 = wcscmp_0(L"pathMapper", a2);
  if ( !v6 || !wcscmp_0(L"pathMapper2", a2) )
  {
    v22 = 0;
    v24 = 0;
    v23 = &IID_IAppHostPathMapper;
    if ( v6 )
      v23 = &IID_IAppHostPathMapper2;
    PathMapper = CONFIG_CACHE::GetPathMapper((CONFIG_CACHE *)&this[5], &v24, v23);
    if ( PathMapper >= 0 )
    {
      if ( v24 )
      {
        a3->llVal = (LONGLONG)v24;
        v22 = 13;
      }
      a3->vt = v22;
    }
  }
  else if ( !wcscmp_0(L"changeHandler", a2) )
  {
    v13 = this + 117;
    AcquireSRWLockShared(this + 117);
    v14 = *((_QWORD *)this[118].Ptr + 9);
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v14 + 8LL))(v14);
    ReleaseSRWLockShared(v13);
    v15 = 0;
    PathMapper = 0;
    if ( v14 )
    {
      a3->llVal = v14;
      v15 = 13;
    }
    a3->vt = v15;
  }
  else
  {
    v7 = 0;
    PathMapper = 0;
    if ( !wcscmp_0(L"ignoreInvalidAttributes", a2) )
    {
      a3->vt = 11;
      a3->iVal = -(((__int64)this[129].Ptr & 1) != 0);
      goto LABEL_11;
    }
    if ( !wcscmp_0(L"ignoreInvalidRanges", a2) )
    {
      a3->vt = 11;
      a3->iVal = -(((__int64)this[129].Ptr & 2) != 0);
      goto LABEL_11;
    }
    if ( !wcscmp_0(L"ignoreInvalidDecryption", a2) )
    {
      a3->vt = 11;
      a3->iVal = -(((__int64)this[129].Ptr & 8) != 0);
      goto LABEL_11;
    }
    if ( !wcscmp_0(L"expandEnvironmentStrings", a2) )
    {
      a3->vt = 11;
      a3->iVal = -(((__int64)this[129].Ptr & 0x20) != 0);
      goto LABEL_11;
    }
    if ( !wcscmp_0(L"disableExtensions", a2) )
    {
      a3->vt = 11;
      a3->iVal = -(((__int64)this[129].Ptr & 0x40) != 0);
      goto LABEL_11;
    }
    if ( !wcscmp_0(L"availableSections", a2) )
    {
      Ptr = (SCHEMA_TABLE *)this[130].Ptr;
      if ( Ptr )
      {
        PathMapper = SCHEMA_TABLE::GetAvailableSections(Ptr, (struct STRU *)v26);
        if ( PathMapper >= 0 )
        {
          a3->vt = 8;
          Str = STRU::QueryStr((STRU *)v26);
          a3->llVal = (LONGLONG)SysAllocString(Str);
        }
      }
      else
      {
        PathMapper = -2147024883;
      }
      goto LABEL_11;
    }
    if ( !wcscmp_0(L"mappingExtension", a2) )
    {
      a3->vt = 13;
      v12 = this[4].Ptr;
      if ( v12 )
        v7 = (LONGLONG)v12 + 8;
      a3->llVal = v7;
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)this[4].Ptr + 8LL))(this[4].Ptr);
      goto LABEL_11;
    }
    if ( !wcscmp_0(L"hideExceptionPhysicalPath", a2) )
    {
      a3->vt = 11;
      a3->iVal = -((LODWORD(this[129].Ptr) & 0x80u) != 0);
      goto LABEL_11;
    }
    if ( !wcscmp_0(L"lockMetadata", a2) )
    {
      a3->vt = 11;
      a3->iVal = -(HIDWORD(this[3].Ptr) != 0);
      goto LABEL_11;
    }
    if ( !wcscmp_0(L"managedRuntimeVersion", a2) )
    {
      a3->vt = 8;
      v16 = STRU::QueryStr((STRU *)&this[27]);
LABEL_37:
      v17 = SysAllocString(v16);
      a3->llVal = (LONGLONG)v17;
      if ( !v17 )
        PathMapper = -2147024888;
      goto LABEL_11;
    }
    if ( !wcscmp_0(L"defaultManagedRuntimeVersion", a2) )
    {
      a3->vt = 8;
      v16 = &szDomain;
      if ( this[102].Ptr )
        v16 = (const OLECHAR *)this[102].Ptr;
      goto LABEL_37;
    }
    if ( !wcscmp_0(L"schemaPath", a2) )
    {
      STRU::STRU((STRU *)v25);
      PathMapper = SCHEMA_FILE_LIST::QuerySchemaDirectory((struct STRU *)v25);
      if ( PathMapper >= 0 )
      {
        a3->vt = 8;
        v18 = STRU::QueryStr((STRU *)v25);
        v19 = SysAllocString(v18);
        a3->llVal = (LONGLONG)v19;
        if ( !v19 )
          PathMapper = -2147024888;
      }
      STRU::~STRU((STRU *)v25);
    }
    else
    {
      if ( !wcscmp_0(L"availableReadableMetadata", a2) )
      {
        v20 = L"pathMapper,pathMapper2,changeHandler,ignoreInvalidAttributes,ignoreInvalidRanges,ignoreInvalidDecryption,e"
               "xpandEnvironmentStrings,disableExtensions,availableSections,mappingExtension,hideExceptionPhysicalPath,lo"
               "ckMetadata,managedRuntimeVersion,defaultManagedRuntimeVersion,schemaPath";
      }
      else
      {
        if ( wcscmp_0(L"availableWritableMetadata", a2) )
        {
          PathMapper = -2147024846;
          goto LABEL_11;
        }
        v20 = L"pathMapper,pathMapper2,changeHandler,ignoreInvalidAttributes,ignoreInvalidRanges,ignoreInvalidDecryption,e"
               "xpandEnvironmentStrings,disableExtensions,hideExceptionPhysicalPath,lockMetadata,defaultManagedRuntimeVersion";
      }
      a3->vt = 8;
      v21 = SysAllocString(v20);
      a3->llVal = (LONGLONG)v21;
      if ( !v21 )
        PathMapper = -2147024882;
    }
  }
LABEL_11:
  STRU::~STRU((STRU *)v26);
  return (unsigned int)PathMapper;
}

```

## disassembly

```asm
0x180016e30  mov     [rsp+arg_8], rbx
0x180016e35  mov     [rsp+arg_18], rbp
0x180016e3a  push    rsi
0x180016e3b  push    rdi
0x180016e3c  push    r14
0x180016e3e  sub     rsp, 2B0h
0x180016e45  mov     rax, cs:__security_cookie
0x180016e4c  xor     rax, rsp
0x180016e4f  mov     [rsp+2C8h+var_28], rax
0x180016e57  mov     rdi, r8
0x180016e5a  mov     rbx, rdx
0x180016e5d  mov     r14, rcx
0x180016e60  xor     edx, edx; Val
0x180016e62  mov     r8d, 200h; Size
0x180016e68  lea     rcx, [rsp+2C8h+var_228]; void *
0x180016e70  call    memset_0
0x180016e75  mov     r8d, 100h
0x180016e7b  lea     rdx, [rsp+2C8h+var_228]
0x180016e83  lea     rcx, [rsp+2C8h+var_268]
0x180016e88  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180016e8e  test    rbx, rbx
0x180016e91  jz      loc_1800172EC
0x180016e97  test    rdi, rdi
0x180016e9a  jz      loc_1800172EC
0x180016ea0  mov     rdx, rbx; String2
0x180016ea3  lea     rcx, aPathmapper; "pathMapper"
0x180016eaa  call    wcscmp_0
0x180016eaf  mov     esi, eax
0x180016eb1  test    eax, eax
0x180016eb3  jz      loc_18001729E
0x180016eb9  mov     rdx, rbx; String2
0x180016ebc  lea     rcx, aPathmapper2; "pathMapper2"
0x180016ec3  call    wcscmp_0
0x180016ec8  test    eax, eax
0x180016eca  jz      loc_18001729E
0x180016ed0  mov     rdx, rbx; String2
0x180016ed3  lea     rcx, aChangehandler; "changeHandler"
0x180016eda  call    wcscmp_0
0x180016edf  test    eax, eax
0x180016ee1  jz      loc_180017056
0x180016ee7  xor     ebp, ebp
0x180016ee9  lea     rcx, aIgnoreinvalida; "ignoreInvalidAttributes"
0x180016ef0  mov     rdx, rbx; String2
0x180016ef3  mov     esi, ebp
0x180016ef5  call    wcscmp_0
0x180016efa  test    eax, eax
0x180016efc  jz      loc_1800170A3
0x180016f02  mov     rdx, rbx; String2
0x180016f05  lea     rcx, aIgnoreinvalidr; "ignoreInvalidRanges"
0x180016f0c  call    wcscmp_0
0x180016f11  test    eax, eax
0x180016f13  jz      loc_1800170BF
0x180016f19  mov     rdx, rbx; String2
0x180016f1c  lea     rcx, aIgnoreinvalidd; "ignoreInvalidDecryption"
0x180016f23  call    wcscmp_0
0x180016f28  test    eax, eax
0x180016f2a  jz      loc_1800170DB
0x180016f30  mov     rdx, rbx; String2
0x180016f33  lea     rcx, aExpandenvironm; "expandEnvironmentStrings"
0x180016f3a  call    wcscmp_0
0x180016f3f  test    eax, eax
0x180016f41  jnz     short loc_180016F8F
0x180016f43  mov     word ptr [rdi], 0Bh
0x180016f48  mov     eax, [r14+408h]
0x180016f4f  and     al, 20h
0x180016f51  neg     al
0x180016f53  sbb     ax, ax
0x180016f56  mov     [rdi+8], ax
0x180016f5a  lea     rcx, [rsp+2C8h+var_268]
0x180016f5f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180016f65  mov     eax, esi
0x180016f67  mov     rcx, [rsp+2C8h+var_28]
0x180016f6f  xor     rcx, rsp; StackCookie
0x180016f72  call    __security_check_cookie
0x180016f77  lea     r11, [rsp+2C8h+var_18]
0x180016f7f  mov     rbx, [r11+28h]
0x180016f83  mov     rbp, [r11+38h]
0x180016f87  mov     rsp, r11
0x180016f8a  pop     r14
0x180016f8c  pop     rdi
0x180016f8d  pop     rsi
0x180016f8e  retn
0x180016f8f  mov     rdx, rbx; String2
0x180016f92  lea     rcx, aDisableextensi; "disableExtensions"
0x180016f99  call    wcscmp_0
0x180016f9e  test    eax, eax
0x180016fa0  jnz     short loc_180016FBB
0x180016fa2  mov     word ptr [rdi], 0Bh
0x180016fa7  mov     eax, [r14+408h]
0x180016fae  and     al, 40h
0x180016fb0  neg     al
0x180016fb2  sbb     ax, ax
0x180016fb5  mov     [rdi+8], ax
0x180016fb9  jmp     short loc_180016F5A
0x180016fbb  mov     rdx, rbx; String2
0x180016fbe  lea     rcx, aAvailablesecti; "availableSections"
0x180016fc5  call    wcscmp_0
0x180016fca  test    eax, eax
0x180016fcc  jnz     short loc_180017014
0x180016fce  mov     rcx, [r14+410h]; this
0x180016fd5  test    rcx, rcx
0x180016fd8  jz      loc_1800170F7
0x180016fde  lea     rdx, [rsp+2C8h+var_268]; struct STRU *
0x180016fe3  call    ?GetAvailableSections@SCHEMA_TABLE@@QEAAJPEAVSTRU@@@Z; SCHEMA_TABLE::GetAvailableSections(STRU *)
0x180016fe8  mov     esi, eax
0x180016fea  test    eax, eax
0x180016fec  js      loc_180016F5A
0x180016ff2  lea     rcx, [rsp+2C8h+var_268]
0x180016ff7  mov     word ptr [rdi], 8
0x180016ffc  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180017002  mov     rcx, rax; psz
0x180017005  call    cs:__imp_SysAllocString
0x18001700b  mov     [rdi+8], rax
0x18001700f  jmp     loc_180016F5A
0x180017014  mov     rdx, rbx; String2
0x180017017  lea     rcx, aMappingextensi; "mappingExtension"
0x18001701e  call    wcscmp_0
0x180017023  test    eax, eax
0x180017025  jnz     loc_18001710A
0x18001702b  mov     word ptr [rdi], 0Dh
0x180017030  mov     rax, [r14+20h]
0x180017034  test    rax, rax
0x180017037  jnz     loc_180017101
0x18001703d  mov     [rdi+8], rbp
0x180017041  mov     rcx, [r14+20h]
0x180017045  mov     rax, [rcx]
0x180017048  mov     rax, [rax+8]
0x18001704c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017051  jmp     loc_180016F5A
0x180017056  lea     rbx, [r14+3A8h]
0x18001705d  mov     rcx, rbx; SRWLock
0x180017060  call    cs:__imp_AcquireSRWLockShared
0x180017066  mov     rax, [r14+3B0h]
0x18001706d  mov     r14, [rax+48h]
0x180017071  mov     rcx, r14
0x180017074  mov     rax, [r14]
0x180017077  mov     rax, [rax+8]
0x18001707b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017080  mov     rcx, rbx; SRWLock
0x180017083  call    cs:__imp_ReleaseSRWLockShared
0x180017089  xor     ebp, ebp
0x18001708b  mov     esi, ebp
0x18001708d  test    r14, r14
0x180017090  jz      short loc_18001709B
0x180017092  mov     [rdi+8], r14
0x180017096  mov     ebp, 0Dh
0x18001709b  mov     [rdi], bp
0x18001709e  jmp     loc_180016F5A
0x1800170a3  mov     word ptr [rdi], 0Bh
0x1800170a8  mov     eax, [r14+408h]
0x1800170af  and     al, 1
0x1800170b1  neg     al
0x1800170b3  sbb     ax, ax
0x1800170b6  mov     [rdi+8], ax
0x1800170ba  jmp     loc_180016F5A
0x1800170bf  mov     word ptr [rdi], 0Bh
0x1800170c4  mov     eax, [r14+408h]
0x1800170cb  and     al, 2
0x1800170cd  neg     al
0x1800170cf  sbb     ax, ax
0x1800170d2  mov     [rdi+8], ax
0x1800170d6  jmp     loc_180016F5A
0x1800170db  mov     word ptr [rdi], 0Bh
0x1800170e0  mov     eax, [r14+408h]
0x1800170e7  and     al, 8
0x1800170e9  neg     al
0x1800170eb  sbb     ax, ax
0x1800170ee  mov     [rdi+8], ax
0x1800170f2  jmp     loc_180016F5A
0x1800170f7  mov     esi, 8007000Dh
0x1800170fc  jmp     loc_180016F5A
0x180017101  lea     rbp, [rax+8]
0x180017105  jmp     loc_18001703D
0x18001710a  mov     rdx, rbx; String2
0x18001710d  lea     rcx, aHideexceptionp; "hideExceptionPhysicalPath"
0x180017114  call    wcscmp_0
0x180017119  test    eax, eax
0x18001711b  jnz     short loc_180017139
0x18001711d  mov     word ptr [rdi], 0Bh
0x180017122  mov     eax, [r14+408h]
0x180017129  and     al, 80h
0x18001712b  neg     al
0x18001712d  sbb     ax, ax
0x180017130  mov     [rdi+8], ax
0x180017134  jmp     loc_180016F5A
0x180017139  mov     rdx, rbx; String2
0x18001713c  lea     rcx, aLockmetadata; "lockMetadata"
0x180017143  call    wcscmp_0
0x180017148  test    eax, eax
0x18001714a  jnz     short loc_180017163
0x18001714c  mov     word ptr [rdi], 0Bh
0x180017151  mov     eax, [r14+1Ch]
0x180017155  neg     eax
0x180017157  sbb     cx, cx
0x18001715a  mov     [rdi+8], cx
0x18001715e  jmp     loc_180016F5A
0x180017163  mov     rdx, rbx; String2
0x180017166  lea     rcx, aManagedruntime; "managedRuntimeVersion"
0x18001716d  call    wcscmp_0
0x180017172  test    eax, eax
0x180017174  jnz     short loc_1800171C4
0x180017176  lea     rcx, [r14+0D8h]
0x18001717d  mov     word ptr [rdi], 8
0x180017182  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180017188  mov     rcx, rax
0x18001718b  jmp     short loc_1800171A7
0x18001718d  mov     word ptr [rdi], 8
0x180017192  lea     rcx, szDomain
0x180017199  mov     rax, [r14+330h]
0x1800171a0  test    rax, rax
0x1800171a3  cmovnz  rcx, rax; psz
0x1800171a7  call    cs:__imp_SysAllocString
0x1800171ad  mov     [rdi+8], rax
0x1800171b1  test    rax, rax
0x1800171b4  jnz     loc_180016F5A
0x1800171ba  mov     esi, 80070008h
0x1800171bf  jmp     loc_180016F5A
0x1800171c4  mov     rdx, rbx; String2
0x1800171c7  lea     rcx, aDefaultmanaged; "defaultManagedRuntimeVersion"
0x1800171ce  call    wcscmp_0
0x1800171d3  test    eax, eax
0x1800171d5  jz      short loc_18001718D
0x1800171d7  mov     rdx, rbx; String2
0x1800171da  lea     rcx, aSchemapath; "schemaPath"
0x1800171e1  call    wcscmp_0
0x1800171e6  test    eax, eax
0x1800171e8  jnz     short loc_18001723C
0x1800171ea  lea     rcx, [rsp+2C8h+var_2A0]
0x1800171ef  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800171f5  lea     rcx, [rsp+2C8h+var_2A0]; struct STRU *
0x1800171fa  call    ?QuerySchemaDirectory@SCHEMA_FILE_LIST@@SAJPEAVSTRU@@@Z; SCHEMA_FILE_LIST::QuerySchemaDirectory(STRU *)
0x1800171ff  lea     rcx, [rsp+2C8h+var_2A0]
0x180017204  mov     esi, eax
0x180017206  test    eax, eax
0x180017208  js      short loc_180017231
0x18001720a  mov     word ptr [rdi], 8
0x18001720f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180017215  mov     rcx, rax; psz
0x180017218  call    cs:__imp_SysAllocString
0x18001721e  mov     [rdi+8], rax
0x180017222  lea     rcx, [rsp+2C8h+var_2A0]
0x180017227  test    rax, rax
0x18001722a  jnz     short loc_180017231
0x18001722c  mov     esi, 80070008h
0x180017231  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180017237  jmp     loc_180016F5A
0x18001723c  mov     rdx, rbx; String2
0x18001723f  lea     rcx, aAvailablereada_1; "availableReadableMetadata"
0x180017246  call    wcscmp_0
0x18001724b  test    eax, eax
0x18001724d  jnz     short loc_180017281
0x18001724f  lea     rcx, aPathmapperPath_0; "pathMapper,pathMapper2,changeHandler,ig"...
0x180017256  jmp     short loc_18001725F
0x180017258  lea     rcx, psz; "pathMapper,pathMapper2,changeHandler,ig"...
0x18001725f  mov     word ptr [rdi], 8
0x180017264  call    cs:__imp_SysAllocString
0x18001726a  mov     [rdi+8], rax
0x18001726e  test    rax, rax
0x180017271  jnz     loc_180016F5A
0x180017277  mov     esi, 8007000Eh
0x18001727c  jmp     loc_180016F5A
0x180017281  mov     rdx, rbx; String2
0x180017284  lea     rcx, aAvailablewrita; "availableWritableMetadata"
0x18001728b  call    wcscmp_0
0x180017290  test    eax, eax
0x180017292  jz      short loc_180017258
0x180017294  mov     esi, 80070032h
0x180017299  jmp     loc_180016F5A
0x18001729e  xor     ebp, ebp
0x1800172a0  lea     rax, IID_IAppHostPathMapper2
0x1800172a7  test    esi, esi
0x1800172a9  mov     [rsp+2C8h+var_2A8], rbp
0x1800172ae  lea     r8, IID_IAppHostPathMapper
0x1800172b5  cmovnz  r8, rax; struct _GUID *
0x1800172b9  lea     rcx, [r14+28h]; this
0x1800172bd  lea     rdx, [rsp+2C8h+var_2A8]; struct IUnknown **
0x1800172c2  call    ?GetPathMapper@CONFIG_CACHE@@QEAAJPEAPEAUIUnknown@@AEBU_GUID@@@Z; CONFIG_CACHE::GetPathMapper(IUnknown * *,_GUID const &)
0x1800172c7  mov     esi, eax
0x1800172c9  test    eax, eax
0x1800172cb  js      loc_180016F5A
0x1800172d1  mov     rax, [rsp+2C8h+var_2A8]
0x1800172d6  test    rax, rax
0x1800172d9  jz      short loc_1800172E4
0x1800172db  mov     [rdi+8], rax
0x1800172df  mov     ebp, 0Dh
0x1800172e4  mov     [rdi], bp
0x1800172e7  jmp     loc_180016F5A
0x1800172ec  mov     esi, 80070057h
0x1800172f1  jmp     loc_180016F5A
```
