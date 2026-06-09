# Microsoft::Windows::MDM::OmadmClient::NetworkHandler::GetPurposeApn(ushort const *,ulong *,void * *)

- ea: `0x140033520`
- end: `0x140033853`
- name: `?GetPurposeApn@NetworkHandler@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBGPEAKPEAPEAX@Z`
- size: `819`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::NetworkHandler *__hidden this, LPCOLESTR lpsz, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140003450`
- `0x14000bf50`
- `0x14000e610`
- `0x140013404`
- `0x14001391c`
- `0x140031dcc`
- `0x140033520`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1400335df`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1400335df`
- `wcmapi!WcmFreeMemory` at `0x14003366a`
- `wcmapi!WcmFreeMemory` at `0x140033699`
- `wcmapi!WcmFreeMemory` at `0x140033794`
- `wcmapi!WcmFreeMemory` at `0x140033818`
- `wcmapi!WcmFreeMemory` at `0x14003366a`
- `wcmapi!WcmFreeMemory` at `0x140033699`
- `wcmapi!WcmFreeMemory` at `0x140033794`
- `wcmapi!WcmFreeMemory` at `0x140033818`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::NetworkHandler::GetPurposeApn(
        __int64 **this,
        unsigned __int16 *lpsz,
        unsigned int *a3,
        void **a4)
{
  unsigned int v7; // ebx
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  _DWORD *v11; // rcx
  unsigned int v12; // ebx
  _DWORD *v13; // rcx
  __int64 v14; // rdx
  struct COmaDmLogger *Logger; // rax
  int v17; // eax
  _DWORD *v18; // rcx
  HRESULT v19; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD *v20; // [rsp+38h] [rbp-C8h] BYREF
  void **v21; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v22; // [rsp+48h] [rbp-B8h] BYREF
  void *v23; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v24[3]; // [rsp+58h] [rbp-A8h] BYREF
  int v25; // [rsp+70h] [rbp-90h]
  HRESULT *v26; // [rsp+78h] [rbp-88h]
  __int64 *v27; // [rsp+80h] [rbp-80h]
  __int64 v28; // [rsp+88h] [rbp-78h] BYREF
  char v29; // [rsp+90h] [rbp-70h]
  Microsoft::Windows::MDM::OmadmClient::NetworkHandler *v30; // [rsp+98h] [rbp-68h]
  HRESULT *v31; // [rsp+A0h] [rbp-60h]
  void ***v32; // [rsp+A8h] [rbp-58h]
  char v33; // [rsp+B0h] [rbp-50h]
  GUID pclsid; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v35[64]; // [rsp+D0h] [rbp-30h] BYREF

  v21 = a4;
  v19 = 0;
  *a3 = 0;
  *a4 = 0;
  v24[0] = 0;
  v24[1] = "GetPurposeApn";
  v24[2] = COmaDmLogger::GetLogger();
  v25 = 2;
  v26 = &v19;
  v30 = (Microsoft::Windows::MDM::OmadmClient::NetworkHandler *)this;
  v31 = &v19;
  v32 = &v21;
  v33 = 1;
  if ( *lpsz != 123 )
  {
    v19 = StringCchPrintfW(v35, 0x40u, L"{%s}", lpsz);
    lpsz = v35;
    if ( v19 )
      lpsz = 0;
  }
  pclsid = 0;
  v19 = CLSIDFromString(lpsz, &pclsid);
  if ( v19 < 0 )
  {
    if ( *v21 )
      (*(void (__fastcall **)(__int64 *))(*this[6] + 336))(this[6]);
    v7 = 0;
    goto LABEL_30;
  }
  v20 = 0;
  v8 = this[6];
  v9 = *v8;
  v27 = (__int64 *)&v20;
  v28 = 0;
  v29 = 1;
  v19 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))(v9 + 288))(v8, &pclsid, &v28);
  if ( v29 )
  {
    v10 = *v27;
    *v27 = v28;
    if ( v10 )
      WcmFreeMemory();
  }
  v7 = v19;
  if ( v19 < 0 )
  {
    LODWORD(v24[0]) = 18064;
    HIDWORD(v24[0]) = v19;
    v11 = v20;
    v20 = 0;
    if ( v11 )
      WcmFreeMemory();
    if ( v19 < 0 && *v21 )
      (*(void (__fastcall **)(__int64 *))(*this[6] + 336))(this[6]);
    goto LABEL_30;
  }
  v12 = 0;
  v13 = v20;
  if ( !*v20 )
  {
LABEL_25:
    v24[0] = 0x8007000200004691uLL;
    v7 = -2147024894;
    v20 = 0;
    if ( v13 )
      WcmFreeMemory();
    if ( v19 < 0 && *v21 )
      (*(void (__fastcall **)(__int64 *))(*this[6] + 336))(this[6]);
    goto LABEL_30;
  }
  while ( 1 )
  {
    v14 = 133LL * v12;
    if ( v13[v14 + 133] == 3 )
      break;
LABEL_24:
    if ( ++v12 >= *v13 )
      goto LABEL_25;
  }
  v22 = 0;
  v23 = 0;
  v19 = Microsoft::Windows::MDM::OmadmClient::NetworkHandler::CheckApn(
          (Microsoft::Windows::MDM::OmadmClient::NetworkHandler *)this,
          (struct _GUID *)&v13[v14 + 129],
          (const unsigned __int16 *)&v13[v14 + 1],
          &v22,
          &v23);
  if ( v19 < 0 )
  {
    Logger = COmaDmLogger::GetLogger();
    Microsoft::Windows::TelemetryLogger::LogMeasure(Logger, 0, 18066, 0);
    if ( v23 )
      (*(void (__fastcall **)(__int64 *))(*this[6] + 336))(this[6]);
    v13 = v20;
    goto LABEL_24;
  }
  *a3 = v22;
  *v21 = v23;
  v17 = v19;
  v7 = v19;
  v18 = v20;
  v20 = 0;
  if ( v18 )
  {
    WcmFreeMemory();
    v17 = v19;
  }
  if ( v17 < 0 && *v21 )
    (*(void (__fastcall **)(__int64 *))(*this[6] + 336))(this[6]);
LABEL_30:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v24);
  return v7;
}

```

## disassembly

```asm
0x140033520  push    rbp
0x140033522  push    rbx
0x140033523  push    rsi
0x140033524  push    rdi
0x140033525  push    r14
0x140033527  lea     rbp, [rsp-60h]
0x14003352c  sub     rsp, 160h
0x140033533  mov     rax, cs:__security_cookie
0x14003353a  xor     rax, rsp
0x14003353d  mov     [rbp+80h+var_30], rax
0x140033541  mov     rsi, r8
0x140033544  mov     rbx, rdx
0x140033547  mov     rdi, rcx
0x14003354a  mov     [rsp+180h+var_140], r9
0x14003354f  xor     r14d, r14d
0x140033552  mov     [rsp+180h+var_150], r14d
0x140033557  mov     [r8], r14d
0x14003355a  mov     [r9], r14
0x14003355d  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140033562  mov     [rsp+180h+var_128], r14
0x140033567  lea     rcx, aGetpurposeapn; "GetPurposeApn"
0x14003356e  mov     [rsp+180h+var_120], rcx
0x140033573  mov     [rsp+180h+var_118], rax
0x140033578  mov     [rsp+180h+var_110], 2
0x140033580  lea     rax, [rsp+180h+var_150]
0x140033585  mov     [rsp+180h+var_108], rax
0x14003358a  mov     [rbp+80h+var_E8], rdi
0x14003358e  lea     rax, [rsp+180h+var_150]
0x140033593  mov     [rbp+80h+var_E0], rax
0x140033597  lea     rax, [rsp+180h+var_140]
0x14003359c  mov     [rbp+80h+var_D8], rax
0x1400335a0  mov     [rbp+80h+var_D0], 1
0x1400335a4  lea     eax, [r14+7Bh]
0x1400335a8  cmp     ax, [rbx]
0x1400335ab  jz      short loc_1400335D1
0x1400335ad  mov     r9, rbx
0x1400335b0  lea     r8, aS; "{%s}"
0x1400335b7  lea     edx, [rax-3Bh]; unsigned __int64
0x1400335ba  lea     rcx, [rbp+80h+var_B0]; unsigned __int16 *
0x1400335be  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400335c3  mov     [rsp+180h+var_150], eax
0x1400335c7  lea     rbx, [rbp+80h+var_B0]
0x1400335cb  test    eax, eax
0x1400335cd  cmovnz  rbx, r14
0x1400335d1  xorps   xmm0, xmm0
0x1400335d4  movups  xmmword ptr [rbp+80h+pclsid.Data1], xmm0
0x1400335d8  lea     rdx, [rbp+80h+pclsid]; pclsid
0x1400335dc  mov     rcx, rbx; lpsz
0x1400335df  call    cs:__imp_CLSIDFromString
0x1400335e6  nop     dword ptr [rax+rax+00h]
0x1400335eb  mov     [rsp+180h+var_150], eax
0x1400335ef  test    eax, eax
0x1400335f1  jns     short loc_14003361C
0x1400335f3  mov     rax, [rsp+180h+var_140]
0x1400335f8  mov     rdx, [rax]
0x1400335fb  test    rdx, rdx
0x1400335fe  jz      short loc_140033614
0x140033600  mov     rcx, [rdi+30h]
0x140033604  mov     rax, [rcx]
0x140033607  mov     rax, [rax+150h]
0x14003360e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033613  nop
0x140033614  mov     ebx, r14d
0x140033617  jmp     loc_1400337C9
0x14003361c  mov     [rsp+180h+var_148], r14
0x140033621  mov     rcx, [rdi+30h]
0x140033625  mov     rax, [rcx]
0x140033628  lea     rdx, [rsp+180h+var_148]
0x14003362d  mov     [rbp+80h+var_100], rdx
0x140033631  mov     [rbp+80h+var_F8], r14
0x140033635  mov     [rbp+80h+var_F0], 1
0x140033639  lea     r8, [rbp+80h+var_F8]
0x14003363d  lea     rdx, [rbp+80h+pclsid]
0x140033641  mov     rax, [rax+120h]
0x140033648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003364d  mov     [rsp+180h+var_150], eax
0x140033651  cmp     [rbp+80h+var_F0], r14b
0x140033655  jz      short loc_140033676
0x140033657  mov     rdx, [rbp+80h+var_100]
0x14003365b  mov     rcx, [rdx]
0x14003365e  mov     rax, [rbp+80h+var_F8]
0x140033662  mov     [rdx], rax
0x140033665  test    rcx, rcx
0x140033668  jz      short loc_140033676
0x14003366a  call    cs:__imp_WcmFreeMemory
0x140033671  nop     dword ptr [rax+rax+00h]
0x140033676  mov     ebx, [rsp+180h+var_150]
0x14003367a  test    ebx, ebx
0x14003367c  jns     short loc_1400336D3
0x14003367e  mov     dword ptr [rsp+180h+var_128], 4690h
0x140033686  mov     dword ptr [rsp+180h+var_128+4], ebx
0x14003368a  mov     rcx, [rsp+180h+var_148]
0x14003368f  mov     [rsp+180h+var_148], r14
0x140033694  test    rcx, rcx
0x140033697  jz      short loc_1400336A6
0x140033699  call    cs:__imp_WcmFreeMemory
0x1400336a0  nop     dword ptr [rax+rax+00h]
0x1400336a5  nop
0x1400336a6  cmp     [rsp+180h+var_150], r14d
0x1400336ab  jge     short loc_1400336CE
0x1400336ad  mov     rax, [rsp+180h+var_140]
0x1400336b2  mov     rdx, [rax]
0x1400336b5  test    rdx, rdx
0x1400336b8  jz      short loc_1400336CE
0x1400336ba  mov     rcx, [rdi+30h]
0x1400336be  mov     rax, [rcx]
0x1400336c1  mov     rax, [rax+150h]
0x1400336c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400336cd  nop
0x1400336ce  jmp     loc_1400337C9
0x1400336d3  mov     ebx, r14d
0x1400336d6  mov     rcx, [rsp+180h+var_148]
0x1400336db  cmp     [rcx], r14d
0x1400336de  jbe     loc_140033779
0x1400336e4  mov     eax, ebx
0x1400336e6  imul    rdx, rax, 214h
0x1400336ed  cmp     dword ptr [rdx+rcx+214h], 3
0x1400336f5  jnz     short loc_14003376F
0x1400336f7  mov     [rsp+180h+var_138], r14d
0x1400336fc  mov     [rsp+180h+var_130], r14
0x140033701  lea     r8, [rcx+4]
0x140033705  add     r8, rdx; unsigned __int16 *
0x140033708  add     rcx, 204h
0x14003370f  add     rdx, rcx; struct _GUID *
0x140033712  lea     rax, [rsp+180h+var_130]
0x140033717  mov     [rsp+180h+var_160], rax; void **
0x14003371c  lea     r9, [rsp+180h+var_138]; unsigned int *
0x140033721  mov     rcx, rdi; this
0x140033724  call    ?CheckApn@NetworkHandler@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEAU_GUID@@PEBGPEAKPEAPEAX@Z; Microsoft::Windows::MDM::OmadmClient::NetworkHandler::CheckApn(_GUID *,ushort const *,ulong *,void * *)
0x140033729  mov     [rsp+180h+var_150], eax
0x14003372d  test    eax, eax
0x14003372f  jns     loc_1400337F0
0x140033735  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14003373a  xor     r9d, r9d
0x14003373d  xor     edx, edx
0x14003373f  mov     r8d, 4692h
0x140033745  mov     rcx, rax
0x140033748  call    ?LogMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@KPEBGZZ; Microsoft::Windows::TelemetryLogger::LogMeasure(Microsoft::Windows::TracingLevel,ulong,ushort const *,...)
0x14003374d  mov     rdx, [rsp+180h+var_130]
0x140033752  test    rdx, rdx
0x140033755  jz      short loc_14003376A
0x140033757  mov     rcx, [rdi+30h]
0x14003375b  mov     rax, [rcx]
0x14003375e  mov     rax, [rax+150h]
0x140033765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003376a  mov     rcx, [rsp+180h+var_148]
0x14003376f  inc     ebx
0x140033771  cmp     ebx, [rcx]
0x140033773  jb      loc_1400336E4
0x140033779  mov     dword ptr [rsp+180h+var_128], 4691h
0x140033781  mov     ebx, 80070002h
0x140033786  mov     dword ptr [rsp+180h+var_128+4], ebx
0x14003378a  mov     [rsp+180h+var_148], r14
0x14003378f  test    rcx, rcx
0x140033792  jz      short loc_1400337A1
0x140033794  call    cs:__imp_WcmFreeMemory
0x14003379b  nop     dword ptr [rax+rax+00h]
0x1400337a0  nop
0x1400337a1  cmp     [rsp+180h+var_150], r14d
0x1400337a6  jge     short loc_1400337C9
0x1400337a8  mov     rax, [rsp+180h+var_140]
0x1400337ad  mov     rdx, [rax]
0x1400337b0  test    rdx, rdx
0x1400337b3  jz      short loc_1400337C9
0x1400337b5  mov     rcx, [rdi+30h]
0x1400337b9  mov     r8, [rcx]
0x1400337bc  mov     rax, [r8+150h]
0x1400337c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400337c8  nop
0x1400337c9  lea     rcx, [rsp+180h+var_128]; this
0x1400337ce  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x1400337d3  mov     eax, ebx
0x1400337d5  mov     rcx, [rbp+80h+var_30]
0x1400337d9  xor     rcx, rsp; StackCookie
0x1400337dc  call    __security_check_cookie
0x1400337e1  add     rsp, 160h
0x1400337e8  pop     r14
0x1400337ea  pop     rdi
0x1400337eb  pop     rsi
0x1400337ec  pop     rbx
0x1400337ed  pop     rbp
0x1400337ee  retn
0x1400337f0  mov     eax, [rsp+180h+var_138]
0x1400337f4  mov     [rsi], eax
0x1400337f6  mov     rcx, [rsp+180h+var_130]
0x1400337fb  mov     rax, [rsp+180h+var_140]
0x140033800  mov     [rax], rcx
0x140033803  mov     eax, [rsp+180h+var_150]
0x140033807  mov     ebx, eax
0x140033809  mov     rcx, [rsp+180h+var_148]
0x14003380e  mov     [rsp+180h+var_148], r14
0x140033813  test    rcx, rcx
0x140033816  jz      short loc_140033828
0x140033818  call    cs:__imp_WcmFreeMemory
0x14003381f  nop     dword ptr [rax+rax+00h]
0x140033824  mov     eax, [rsp+180h+var_150]
0x140033828  test    eax, eax
0x14003382a  jns     short loc_14003384D
0x14003382c  mov     rax, [rsp+180h+var_140]
0x140033831  mov     rdx, [rax]
0x140033834  test    rdx, rdx
0x140033837  jz      short loc_14003384D
0x140033839  mov     rcx, [rdi+30h]
0x14003383d  mov     r8, [rcx]
0x140033840  mov     rax, [r8+150h]
0x140033847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003384c  nop
0x14003384d  jmp     loc_1400337C9
```
