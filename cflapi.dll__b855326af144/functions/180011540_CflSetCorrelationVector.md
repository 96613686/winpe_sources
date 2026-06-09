# CflSetCorrelationVector

- ea: `0x180011540`
- end: `0x180011763`
- name: `CflSetCorrelationVector`
- size: `547`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002490`
- `0x180002860`
- `0x18000289c`
- `0x180002ef8`
- `0x1800067c4`
- `0x180008420`
- `0x180008a68`
- `0x180011540`
- `0x180019fb8`
- `0x180027d94`
- `0x180028524`
- `0x18002c11c`
- `0x18002c204`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001172a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001172a`
- `RPCRT4!UuidCreate` at `0x1800115a6`
- `RPCRT4!UuidCreate` at `0x1800115a6`

## string_xrefs

- `0x180011686`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`
- `0x180011656`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CflSetCorrelationVector(_QWORD *a1)
{
  void *v2; // rbx
  const char *v3; // rdx
  unsigned int v4; // edi
  __int64 v5; // r9
  __int64 v6; // rdx
  int updated; // eax
  __int64 v9; // rax
  __int64 v10; // rbx
  __int128 *v11; // rdx
  __int64 *v12; // rax
  __int64 v13; // [rsp+20h] [rbp-128h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-118h] BYREF
  __int128 v15; // [rsp+40h] [rbp-108h] BYREF
  __int64 v16; // [rsp+50h] [rbp-F8h]
  unsigned __int64 v17; // [rsp+58h] [rbp-F0h]
  char v18[32]; // [rsp+60h] [rbp-E8h] BYREF
  char v19[144]; // [rsp+80h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v15 = 0;
  v16 = 0;
  v17 = 15;
  LOBYTE(v15) = 0;
  v2 = operator new(0x90u);
  *((_BYTE *)v2 + 130) = 65;
  Uuid = 0;
  UuidCreate(&Uuid);
  *((_BYTE *)v2 + 129) = 17;
  *((_QWORD *)v2 + 17) = 0x1300000000LL;
  memset_0(v2, 0, 0x81u);
  TLV::Base64Encode<129>(&Uuid, 12, v2);
  *((_WORD *)v2 + 8) = 46;
  *(_QWORD *)&Uuid.Data1 = v2;
  memset_0(v19, 0, 0x81u);
  if ( !TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v2,
          _InterlockedExchangeAdd64((volatile signed __int64 *)v2 + 17, 0),
          v19) )
  {
    v4 = -2147467259;
    v5 = 2147500037LL;
    v6 = 411;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)v5,
      v13);
    if ( v2 )
      operator delete(v2, 0x90u);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
      (const char *)v4,
      v13);
    std::string::~string(&v15);
    return v4;
  }
  updated = CflApiNew::UpdateCorrelationVectorString((CflApiNew *)v19, v3);
  v4 = updated;
  if ( updated < 0 )
  {
    v5 = (unsigned int)updated;
    v6 = 414;
    goto LABEL_5;
  }
  v9 = std::string::string(v18, v19);
  std::string::operator=(&v15, v9);
  std::string::~string(v18);
  if ( v2 )
    operator delete(v2, 0x90u);
  v10 = 0;
  v13 = 0;
  if ( v16 )
  {
    v11 = &v15;
    if ( v17 > 0xF )
      v11 = (__int128 *)v15;
    v12 = (__int64 *)wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
                       &Uuid,
                       v11);
    if ( &v13 != v12 )
    {
      v10 = *v12;
      *v12 = 0;
    }
    if ( *(_QWORD *)&Uuid.Data1 )
      LocalFree(*(HLOCAL *)&Uuid.Data1);
  }
  *a1 = v10;
  std::string::~string(&v15);
  return 0;
}

```

## disassembly

```asm
0x180011540  push    rbx
0x180011542  push    rsi
0x180011543  push    rdi
0x180011544  push    r15
0x180011546  sub     rsp, 128h
0x18001154d  mov     rax, cs:__security_cookie
0x180011554  xor     rax, rsp
0x180011557  mov     [rsp+148h+var_38], rax
0x18001155f  mov     rsi, rcx
0x180011562  xorps   xmm0, xmm0
0x180011565  movups  [rsp+148h+var_108], xmm0
0x18001156a  mov     [rsp+148h+var_F8], 0
0x180011573  mov     [rsp+148h+var_F0], 0Fh
0x18001157c  mov     byte ptr [rsp+148h+var_108], 0
0x180011581  mov     r15d, 90h
0x180011587  mov     ecx, r15d; Size
0x18001158a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001158f  mov     rbx, rax
0x180011592  mov     byte ptr [rax+82h], 41h ; 'A'
0x180011599  xorps   xmm0, xmm0
0x18001159c  movups  xmmword ptr [rsp+148h+Uuid.Data1], xmm0
0x1800115a1  lea     rcx, [rsp+148h+Uuid]; Uuid
0x1800115a6  call    cs:__imp_UuidCreate
0x1800115ac  movaps  xmm0, xmmword ptr [rsp+148h+Uuid.Data1]
0x1800115b1  movdqa  xmmword ptr [rsp+148h+Uuid.Data1], xmm0
0x1800115b7  mov     byte ptr [rbx+81h], 11h
0x1800115be  mov     rax, 1300000000h
0x1800115c8  mov     [rbx+88h], rax
0x1800115cf  lea     edi, [r15-0Fh]
0x1800115d3  mov     r8d, edi; Size
0x1800115d6  xor     edx, edx; Val
0x1800115d8  mov     rcx, rbx; void *
0x1800115db  call    memset_0
0x1800115e0  mov     r8, rbx
0x1800115e3  lea     edx, [rdi-75h]
0x1800115e6  lea     rcx, [rsp+148h+Uuid]
0x1800115eb  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x1800115f0  mov     word ptr [rbx+10h], 2Eh ; '.'
0x1800115f6  mov     qword ptr [rsp+148h+Uuid.Data1], rbx
0x1800115fb  mov     r8d, edi; Size
0x1800115fe  xor     edx, edx; Val
0x180011600  lea     rcx, [rsp+148h+var_C8]; void *
0x180011608  call    memset_0
0x18001160d  xor     edx, edx
0x18001160f  lock xadd [rbx+88h], rdx; unsigned __int64
0x180011618  lea     r8, [rsp+148h+var_C8]; char *
0x180011620  mov     rcx, rbx; this
0x180011623  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180011628  test    al, al
0x18001162a  jnz     short loc_18001163B
0x18001162c  mov     edi, 80004005h
0x180011631  mov     r9d, edi
0x180011634  mov     edx, 19Bh
0x180011639  jmp     short loc_180011656
0x18001163b  lea     rcx, [rsp+148h+var_C8]; this
0x180011643  call    ?UpdateCorrelationVectorString@CflApiNew@@YAJPEBD@Z; CflApiNew::UpdateCorrelationVectorString(char const *)
0x180011648  mov     edi, eax
0x18001164a  test    eax, eax
0x18001164c  jns     short loc_1800116A9
0x18001164e  mov     r9d, eax; char *
0x180011651  mov     edx, 19Eh; void *
0x180011656  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001165d  mov     rcx, [rsp+148h]; this
0x180011665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001166a  nop
0x18001166b  test    rbx, rbx
0x18001166e  jz      short loc_18001167B
0x180011670  mov     rdx, r15; unsigned __int64
0x180011673  mov     rcx, rbx; void *
0x180011676  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001167b  mov     rcx, [rsp+148h]; this
0x180011683  mov     r9d, edi; char *
0x180011686  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x18001168d  mov     edx, 1C2h; void *
0x180011692  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011697  nop
0x180011698  lea     rcx, [rsp+148h+var_108]
0x18001169d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800116a2  mov     eax, edi
0x1800116a4  jmp     loc_180011745
0x1800116a9  lea     rdx, [rsp+148h+var_C8]
0x1800116b1  lea     rcx, [rsp+148h+var_E8]
0x1800116b6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800116bb  mov     rdx, rax
0x1800116be  lea     rcx, [rsp+148h+var_108]
0x1800116c3  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800116c8  lea     rcx, [rsp+148h+var_E8]
0x1800116cd  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800116d2  nop
0x1800116d3  test    rbx, rbx
0x1800116d6  jz      short loc_1800116E3
0x1800116d8  mov     rdx, r15; unsigned __int64
0x1800116db  mov     rcx, rbx; void *
0x1800116de  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800116e3  xor     ebx, ebx
0x1800116e5  mov     [rsp+148h+var_128], rbx
0x1800116ea  cmp     [rsp+148h+var_F8], rbx
0x1800116ef  jz      short loc_180011730
0x1800116f1  lea     rdx, [rsp+148h+var_108]
0x1800116f6  cmp     [rsp+148h+var_F0], 0Fh
0x1800116fc  cmova   rdx, qword ptr [rsp+148h+var_108]
0x180011702  lea     rcx, [rsp+148h+Uuid]
0x180011707  call    ??$make_unique_ansistring@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@0@PEBD_K@Z; wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(char const *,unsigned __int64)
0x18001170c  lea     rcx, [rsp+148h+var_128]
0x180011711  cmp     rcx, rax
0x180011714  jz      short loc_180011720
0x180011716  mov     rbx, [rax]
0x180011719  mov     qword ptr [rax], 0
0x180011720  mov     rcx, qword ptr [rsp+148h+Uuid.Data1]; hMem
0x180011725  test    rcx, rcx
0x180011728  jz      short loc_180011730
0x18001172a  call    cs:__imp_LocalFree
0x180011730  mov     [rsi], rbx
0x180011733  lea     rcx, [rsp+148h+var_108]
0x180011738  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001173d  xor     eax, eax
0x18001173f  jmp     short loc_180011745
0x180011741  mov     eax, [rsp+148h+Uuid.Data1]
0x180011745  mov     rcx, [rsp+148h+var_38]
0x18001174d  xor     rcx, rsp; StackCookie
0x180011750  call    __security_check_cookie
0x180011755  add     rsp, 128h
0x18001175c  pop     r15
0x18001175e  pop     rdi
0x18001175f  pop     rsi
0x180011760  pop     rbx
0x180011761  retn
```
