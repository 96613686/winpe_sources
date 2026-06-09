# Microsoft::HostGuardian::Client::HgServiceController::AttestForAllValues(wchar_t * const,uint,AttestationResultType *,ShsAttestationFlag *,wchar_t * *,uint *,AttestationResult * *)

- ea: `0x18000ca70`
- end: `0x18000cdb5`
- name: `?AttestForAllValues@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXQEA_WIPEAW4AttestationResultType@@PEAW4ShsAttestationFlag@@PEAPEA_WPEAIPEAPEAUAttestationResult@@@Z`
- size: `837`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::HgServiceController *this, wchar_t *const, unsigned int, enum AttestationResultType *, enum ShsAttestationFlag *, wchar_t **, unsigned int *, struct AttestationResult **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d4d8`

## callees

- `0x180007394`
- `0x180008760`
- `0x180008780`
- `0x180009cec`
- `0x18000b3b0`
- `0x18000c8ec`
- `0x18000ca70`
- `0x18000cfcc`
- `0x18000d2e4`
- `0x1800141a4`
- `0x180014298`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cc3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cc3d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000cb84`
- `OLEAUT32!__imp_SysAllocString` at `0x18000cb84`

## string_xrefs

- `0x18000cb49`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000cbb8`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000cd4f`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000cd64`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000cd79`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000cd91`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000cda3`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgServiceController::AttestForAllValues(
        Microsoft::HostGuardian::Client::HgServiceController *this,
        wchar_t *const a2,
        unsigned int a3,
        enum AttestationResultType *a4,
        enum ShsAttestationFlag *a5,
        wchar_t **a6,
        unsigned int *a7,
        struct AttestationResult **a8)
{
  Microsoft::HostGuardian::Client::HgServicePlugin *v8; // r14
  int v9; // ebx
  enum ShsAttestationFlag *v10; // r15
  int v11; // esi
  const char *v12; // r9
  OLECHAR *v13; // rcx
  int v14; // eax
  wchar_t **v15; // rsi
  BSTR v16; // rax
  unsigned __int64 v17; // rsi
  struct AttestationResult **v18; // r15
  char v19; // al
  SIZE_T v20; // rbx
  Microsoft::HostGuardian::Client::HgServiceController *v21; // rax
  __int64 v22; // r8
  const char *v23; // r9
  Microsoft::HostGuardian::Client::HgServiceController *v24; // rdx
  Microsoft::HostGuardian::Client::HgServiceController *v25; // rcx
  unsigned __int64 v26; // r13
  __int64 v27; // r15
  unsigned int v28; // r8d
  wil *v29; // rcx
  int v30; // [rsp+20h] [rbp-E8h]
  unsigned int v31; // [rsp+40h] [rbp-C8h] BYREF
  OLECHAR *psz; // [rsp+48h] [rbp-C0h] BYREF
  struct AttestationResult *v33[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v34; // [rsp+60h] [rbp-A8h] BYREF
  int v35; // [rsp+74h] [rbp-94h]
  Microsoft::HostGuardian::Client::HgServiceController **v36; // [rsp+80h] [rbp-88h]
  Microsoft::HostGuardian::Client::HgServicePlugin *v37; // [rsp+88h] [rbp-80h]
  int v38; // [rsp+90h] [rbp-78h]
  int v39; // [rsp+94h] [rbp-74h]
  char v40; // [rsp+98h] [rbp-70h]
  Microsoft::HostGuardian::Client::HgServiceController *v41; // [rsp+A0h] [rbp-68h]
  OLECHAR **p_psz; // [rsp+A8h] [rbp-60h]
  unsigned int *v43; // [rsp+B0h] [rbp-58h]
  struct AttestationResult **v44; // [rsp+B8h] [rbp-50h]
  char v45; // [rsp+C0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]
  Microsoft::HostGuardian::Client::HgServiceController *v47; // [rsp+110h] [rbp+8h] BYREF

  v47 = this;
  try
  {
    v8 = this;
    v33[0] = 0;
    psz = 0;
    v9 = 0;
    v31 = 0;
    v41 = this;
    p_psz = &psz;
    v43 = &v31;
    v44 = v33;
    v45 = 1;
    v10 = a5;
    v11 = Microsoft::HostGuardian::Client::HgServicePlugin::QueryAttestationResults(
            this,
            a2,
            a3,
            a4,
            a5,
            &psz,
            &v31,
            v33);
    Microsoft::HostGuardian::HgTelemetry::LogAttestationTelemetry(v11, v10);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D0,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
        (const char *)(unsigned int)v11,
        v30);
    v13 = psz;
    if ( psz )
    {
      v14 = Microsoft::HostGuardian::Client::HgServiceController::AddCertificatesToCache(
              (__int64)v8,
              psz,
              *(_DWORD *)v10,
              v31,
              (__int64)v33[0]);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1D6,
          (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
          (const char *)(unsigned int)v14,
          v30);
      v13 = psz;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1DB,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      v12);
    LODWORD(v34) = wil::ResultFromCaughtException(v29);
    v8 = v47;
    v13 = psz;
    v9 = v34;
  }
  v15 = a6;
  if ( a6 && v13 )
  {
    v16 = SysAllocString(v13);
    *v15 = v16;
    if ( !v16 )
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x1E9,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
        (const char *)0x8007000ELL,
        (int)"Unable to set identifierOut to %ws.",
        (const char *)psz);
      if ( !v9 )
        v9 = -2147024882;
    }
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F1,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
        (const char *)(unsigned int)v9,
        v30);
  }
  else if ( v9 < 0 )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      (const char *)(unsigned int)v9,
      v30);
  }
  *(struct AttestationResult **)&v34 = v33[0];
  v17 = v31;
  if ( v33[0] && v31 )
  {
    v18 = a8;
    if ( a8 )
    {
      v19 = 0;
      goto LABEL_21;
    }
  }
  else
  {
    v18 = a8;
  }
  v19 = 1;
LABEL_21:
  if ( v19 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x287,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      (const char *)0x80004003LL,
      v30);
  v20 = 24LL * v31;
  v21 = (Microsoft::HostGuardian::Client::HgServiceController *)CoTaskMemAlloc(v20);
  v24 = v21;
  v25 = retaddr;
  if ( !v21 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x28B,
      (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      v23);
  for ( ; v20; --v20 )
  {
    *(_BYTE *)v21 = 0;
    v21 = (Microsoft::HostGuardian::Client::HgServiceController *)((char *)v21 + 1);
  }
  v47 = v24;
  v36 = &v47;
  v37 = v8;
  v38 = v17;
  v39 = v35;
  v40 = 1;
  v26 = 0;
  if ( (_DWORD)v17 )
  {
    v27 = v34;
    do
    {
      v34 = *(_OWORD *)(v27 + 24 * v26 + 8);
      Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(v25, &v34, v22, (char *)v24 + 24 * v26 + 8);
      v25 = (Microsoft::HostGuardian::Client::HgServiceController *)*(unsigned int *)(v27 + 24 * v26);
      *((_DWORD *)v47 + 6 * v26++) = (_DWORD)v25;
      v24 = v47;
    }
    while ( v26 < v17 );
    v18 = a8;
  }
  *v18 = v24;
  v47 = 0;
  Microsoft::HostGuardian::Client::HgServiceController::FreeAttestationResults(v25, v17, 0);
  v28 = v31;
  *a7 = v31;
  Microsoft::HostGuardian::Client::HgServicePlugin::FreeAttestationResults(v8, psz, v28, v33[0]);
}

```

## disassembly

```asm
0x18000ca70  mov     r11, rsp
0x18000ca73  mov     [r11+8], rcx
0x18000ca77  push    rbx
0x18000ca78  push    rsi
0x18000ca79  push    r12
0x18000ca7b  push    r13
0x18000ca7d  push    r14
0x18000ca7f  push    r15
0x18000ca81  sub     rsp, 0D8h
0x18000ca88  mov     r14, rcx
0x18000ca8b  mov     [rsp+108h+var_B8], 0
0x18000ca94  mov     [rsp+108h+psz], 0
0x18000ca9d  xor     ebx, ebx
0x18000ca9f  mov     [rsp+108h+var_C8], ebx
0x18000caa3  mov     [r11-68h], rcx
0x18000caa7  lea     rax, [rsp+108h+psz]
0x18000caac  mov     [r11-60h], rax
0x18000cab0  lea     rax, [rsp+108h+var_C8]
0x18000cab5  mov     [r11-58h], rax
0x18000cab9  lea     rax, [rsp+108h+var_B8]
0x18000cabe  mov     [r11-50h], rax
0x18000cac2  mov     byte ptr [r11-48h], 1
0x18000cac7  lea     rax, [rsp+108h+var_B8]
0x18000cacc  mov     [rsp+108h+var_D0], rax; struct AttestationResult **
0x18000cad1  lea     rax, [rsp+108h+var_C8]
0x18000cad6  mov     [rsp+108h+var_D8], rax; unsigned int *
0x18000cadb  lea     rax, [rsp+108h+psz]
0x18000cae0  mov     [rsp+108h+var_E0], rax; wchar_t **
0x18000cae5  mov     r15, [rsp+108h+arg_20]
0x18000caed  mov     [rsp+108h+var_E8], r15; int
0x18000caf2  call    ?QueryAttestationResults@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJQEA_WIPEAW4AttestationResultType@@PEAW4ShsAttestationFlag@@PEAPEA_WPEAIPEAPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::HgServicePlugin::QueryAttestationResults(wchar_t * const,uint,AttestationResultType *,ShsAttestationFlag *,wchar_t * *,uint *,AttestationResult * *)
0x18000caf7  mov     esi, eax
0x18000caf9  mov     rdx, r15; enum ShsAttestationFlag *
0x18000cafc  mov     ecx, eax; int
0x18000cafe  call    ?LogAttestationTelemetry@HgTelemetry@HostGuardian@Microsoft@@SAXJPEAW4ShsAttestationFlag@@@Z; Microsoft::HostGuardian::HgTelemetry::LogAttestationTelemetry(long,ShsAttestationFlag *)
0x18000cb03  mov     rcx, [rsp+108h]; this
0x18000cb0b  test    esi, esi
0x18000cb0d  js      loc_18000CD4C
0x18000cb13  mov     rcx, [rsp+108h+psz]
0x18000cb18  test    rcx, rcx
0x18000cb1b  jz      short loc_18000CB5F
0x18000cb1d  mov     rax, [rsp+108h+var_B8]
0x18000cb22  mov     [rsp+108h+var_E8], rax; int
0x18000cb27  mov     r9d, [rsp+108h+var_C8]
0x18000cb2c  mov     r8d, [r15]
0x18000cb2f  mov     rdx, rcx
0x18000cb32  mov     rcx, r14
0x18000cb35  call    ?AddCertificatesToCache@HgServiceController@Client@HostGuardian@Microsoft@@AEAAJPEA_WW4ShsAttestationFlag@@IPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::HgServiceController::AddCertificatesToCache(wchar_t *,ShsAttestationFlag,uint,AttestationResult *)
0x18000cb3a  mov     rcx, [rsp+108h]; this
0x18000cb42  test    eax, eax
0x18000cb44  jns     short loc_18000CB5A
0x18000cb46  mov     r9d, eax; char *
0x18000cb49  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000cb50  mov     edx, 1D6h; void *
0x18000cb55  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000cb5a  mov     rcx, [rsp+108h+psz]
0x18000cb5f  jmp     short loc_18000CB72
0x18000cb61  mov     r14, [rsp+108h+arg_0]
0x18000cb69  mov     rcx, [rsp+108h+psz]; psz
0x18000cb6e  mov     ebx, dword ptr [rsp+108h+var_A8]
0x18000cb72  mov     rsi, [rsp+108h+arg_28]
0x18000cb7a  test    rsi, rsi
0x18000cb7d  jz      short loc_18000CBE0
0x18000cb7f  test    rcx, rcx
0x18000cb82  jz      short loc_18000CBE0
0x18000cb84  call    cs:__imp_SysAllocString
0x18000cb8a  mov     [rsi], rax
0x18000cb8d  test    rax, rax
0x18000cb90  jnz     short loc_18000CBCE
0x18000cb92  mov     rcx, [rsp+108h]; this
0x18000cb9a  mov     rax, [rsp+108h+psz]
0x18000cb9f  mov     [rsp+108h+var_E0], rax; char *
0x18000cba4  lea     rax, aUnableToSetIde_0; "Unable to set identifierOut to %ws."
0x18000cbab  mov     [rsp+108h+var_E8], rax; int
0x18000cbb0  mov     esi, 8007000Eh
0x18000cbb5  mov     r9d, esi; char *
0x18000cbb8  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000cbbf  mov     edx, 1E9h; void *
0x18000cbc4  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000cbc9  test    ebx, ebx
0x18000cbcb  cmovz   ebx, esi
0x18000cbce  mov     rcx, [rsp+108h]; this
0x18000cbd6  test    ebx, ebx
0x18000cbd8  js      loc_18000CD61
0x18000cbde  jmp     short loc_18000CBF0
0x18000cbe0  mov     rcx, [rsp+108h]; this
0x18000cbe8  test    ebx, ebx
0x18000cbea  js      loc_18000CD76
0x18000cbf0  mov     rax, [rsp+108h+var_B8]
0x18000cbf5  mov     qword ptr [rsp+108h+var_A8], rax
0x18000cbfa  mov     esi, [rsp+108h+var_C8]
0x18000cbfe  test    rax, rax
0x18000cc01  jz      short loc_18000CC18
0x18000cc03  test    esi, esi
0x18000cc05  jz      short loc_18000CC18
0x18000cc07  mov     r15, [rsp+108h+arg_38]
0x18000cc0f  test    r15, r15
0x18000cc12  jz      short loc_18000CC20
0x18000cc14  xor     al, al
0x18000cc16  jmp     short loc_18000CC22
0x18000cc18  mov     r15, [rsp+108h+arg_38]
0x18000cc20  mov     al, 1
0x18000cc22  mov     rcx, [rsp+108h]; this
0x18000cc2a  test    al, al
0x18000cc2c  jnz     loc_18000CD8B
0x18000cc32  lea     rbx, [rsi+rsi*2]
0x18000cc36  shl     rbx, 3
0x18000cc3a  mov     rcx, rbx; cb
0x18000cc3d  call    cs:__imp_CoTaskMemAlloc
0x18000cc43  mov     rdx, rax
0x18000cc46  mov     rcx, [rsp+108h]; this
0x18000cc4e  test    rax, rax
0x18000cc51  jz      loc_18000CDA3
0x18000cc57  test    rbx, rbx
0x18000cc5a  jz      short loc_18000CC68
0x18000cc5c  mov     byte ptr [rax], 0
0x18000cc5f  inc     rax
0x18000cc62  sub     rbx, 1
0x18000cc66  jnz     short loc_18000CC5C
0x18000cc68  mov     [rsp+108h+arg_0], rdx
0x18000cc70  lea     rax, [rsp+108h+arg_0]
0x18000cc78  mov     [rsp+108h+var_88], rax
0x18000cc80  mov     [rsp+108h+var_80], r14
0x18000cc88  mov     [rsp+108h+var_78], esi
0x18000cc8f  mov     eax, [rsp+108h+var_94]
0x18000cc93  mov     [rsp+108h+var_74], eax
0x18000cc9a  mov     [rsp+108h+var_70], 1
0x18000cca2  xor     r13d, r13d
0x18000cca5  test    esi, esi
0x18000cca7  jz      short loc_18000CCFE
0x18000cca9  mov     r15, qword ptr [rsp+108h+var_A8]
0x18000ccae  lea     rbx, ds:0[r13*2]
0x18000ccb6  add     rbx, r13
0x18000ccb9  movups  xmm0, xmmword ptr [r15+rbx*8+8]
0x18000ccbf  movdqu  [rsp+108h+var_A8], xmm0
0x18000ccc5  lea     r9, [rdx+8]
0x18000ccc9  lea     r9, [r9+rbx*8]
0x18000cccd  lea     rdx, [rsp+108h+var_A8]
0x18000ccd2  call    ?CloneBlobForCOM@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXUHgBlob@@_NPEAU5@@Z; Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(HgBlob,bool,HgBlob *)
0x18000ccd7  mov     ecx, [r15+rbx*8]; this
0x18000ccdb  mov     rax, [rsp+108h+arg_0]
0x18000cce3  mov     [rax+rbx*8], ecx
0x18000cce6  inc     r13
0x18000cce9  mov     rdx, [rsp+108h+arg_0]
0x18000ccf1  cmp     r13, rsi
0x18000ccf4  jb      short loc_18000CCAE
0x18000ccf6  mov     r15, [rsp+108h+arg_38]
0x18000ccfe  mov     [r15], rdx
0x18000cd01  mov     [rsp+108h+arg_0], 0
0x18000cd0d  xor     r8d, r8d; struct AttestationResult *
0x18000cd10  mov     edx, esi; unsigned int
0x18000cd12  call    ?FreeAttestationResults@HgServiceController@Client@HostGuardian@Microsoft@@QEAAXIPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::HgServiceController::FreeAttestationResults(uint,AttestationResult *)
0x18000cd17  mov     r8d, [rsp+108h+var_C8]; unsigned int
0x18000cd1c  mov     rax, [rsp+108h+arg_30]
0x18000cd24  mov     [rax], r8d
0x18000cd27  mov     r9, [rsp+108h+var_B8]; struct AttestationResult *
0x18000cd2c  mov     rdx, [rsp+108h+psz]; wchar_t *
0x18000cd31  mov     rcx, r14; this
0x18000cd34  call    ?FreeAttestationResults@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJQEA_WIPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::HgServicePlugin::FreeAttestationResults(wchar_t * const,uint,AttestationResult *)
0x18000cd39  nop
0x18000cd3a  add     rsp, 0D8h
0x18000cd41  pop     r15
0x18000cd43  pop     r14
0x18000cd45  pop     r13
0x18000cd47  pop     r12
0x18000cd49  pop     rsi
0x18000cd4a  pop     rbx
0x18000cd4b  retn
0x18000cd4c  mov     r9d, esi; char *
0x18000cd4f  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000cd56  mov     edx, 1D0h; void *
0x18000cd5b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cd61  mov     r9d, ebx; char *
0x18000cd64  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000cd6b  mov     edx, 1F1h; void *
0x18000cd70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cd76  mov     r9d, ebx; char *
0x18000cd79  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000cd80  mov     edx, 1E2h; void *
0x18000cd85  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cd8b  mov     r9d, 80004003h; char *
0x18000cd91  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000cd98  mov     edx, 287h; void *
0x18000cd9d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cda3  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000cdaa  mov     edx, 28Bh; void *
0x18000cdaf  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
