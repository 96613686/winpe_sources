# W3_SERVER::GetMetadata(ushort const *,ushort const *,IReferencedMetadataInfo * *)

- ea: `0x18001cab0`
- end: `0x18001cf4f`
- name: `?GetMetadata@W3_SERVER@@UEAAJPEBG0PEAPEAVIReferencedMetadataInfo@@@Z`
- size: `1183`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IReferencedMetadataInfo **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callees

- `0x18001ab30`
- `0x18001b978`
- `0x18001cab0`
- `0x180032c80`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x18001cdf9`
- `msvcrt!_wcsupr` at `0x18001cdf9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001cc37`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001cc47`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001cc58`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001cc37`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001cc47`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001cc58`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001cc8f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001ccc8`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001cc8f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001ccc8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ccb4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001cd03`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001cd17`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001cd8b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001cd9f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001cdea`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ce09`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ced7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ccb4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001cd03`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001cd17`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001cd8b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001cd9f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001cdea`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ce09`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ced7`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18001cd63`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18001cd63`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001cdda`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001cdda`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x18001cce1`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x18001cce1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001cb1c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001cb47`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001cb78`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001cb1c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001cb47`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001cb78`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001cbb2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001cbcc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001cbb2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001cbcc`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001cb98`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001cb98`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18001cca3`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18001cca3`
- `iisutil!?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z` at `0x18001ce27`
- `iisutil!?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z` at `0x18001ce27`
- `iisutil!?InsertRecord@TREE_HASH_TABLE@@QEAAJPEAX@Z` at `0x18001cf1c`
- `iisutil!?InsertRecord@TREE_HASH_TABLE@@QEAAJPEAX@Z` at `0x18001cf1c`

## pseudocode

```c
__int64 __fastcall W3_SERVER::GetMetadata(
        W3_SERVER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IReferencedMetadataInfo **a4)
{
  int v8; // ebx
  W3_METADATA *v9; // rcx
  unsigned int CCH; // eax
  unsigned __int16 *Str; // rbx
  unsigned int SizeCCH; // eax
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned int *, _QWORD); // rdi
  unsigned __int16 *v16; // rbx
  unsigned __int16 *v17; // rax
  int v18; // eax
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned int *, _QWORD); // rdi
  unsigned __int16 *v21; // rbx
  unsigned __int16 *v22; // rax
  wchar_t *v23; // rax
  const unsigned __int16 *v24; // rax
  W3_METADATA *v25; // rax
  struct INativeConfigurationElement *v26; // rbx
  const unsigned __int16 *v27; // rax
  W3_METADATA *v28; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v29; // [rsp+58h] [rbp-A8h] BYREF
  struct INativeConfigurationElement *v30; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v32[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[56]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v34[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v35[128]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v36[128]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v37[1024]; // [rsp+320h] [rbp+220h] BYREF

  v28 = 0;
  v30 = 0;
  v31 = 0;
  memset_0(v35, 0, sizeof(v35));
  STRU::STRU((STRU *)v32, v35, 0x80u);
  memset_0(v36, 0, sizeof(v36));
  STRU::STRU((STRU *)v33, v36, 0x80u);
  memset_0(v37, 0, sizeof(v37));
  STRU::STRU((STRU *)v34, v37, 0x400u);
  v29 = 0;
  v8 = STRU::Copy((STRU *)v32, L"MACHINE/WEBROOT/APPHOST/", 0x18u);
  if ( v8 < 0 )
    goto LABEL_4;
  v8 = STRU::Append((STRU *)v32, a2);
  if ( v8 < 0 )
    goto LABEL_4;
  v8 = STRU::Append((STRU *)v32, a3);
  if ( v8 < 0 )
    goto LABEL_4;
  while ( 1 )
  {
    Str = STRU::QueryStr((STRU *)v32);
    if ( Str[STRU::QueryCCH((STRU *)v32) - 1] != 47 )
      break;
    CCH = STRU::QueryCCH((STRU *)v32);
    STRU::SetLen((STRU *)v32, CCH - 1);
  }
  SizeCCH = STRU::QuerySizeCCH((STRU *)v33);
  v14 = *((_QWORD *)this + 187);
  v29 = SizeCCH;
  v15 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)v14 + 32LL);
  v16 = STRU::QueryStr((STRU *)v33);
  v17 = STRU::QueryStr((STRU *)v32);
  v18 = v15(v14, v17, v16, &v29, 0);
  v8 = v18;
  if ( v18 < 0 )
  {
    if ( v18 != -2147024774 )
      goto LABEL_4;
    v8 = STRU::Resize((STRU *)v33, 2 * v29);
    if ( v8 < 0 )
      goto LABEL_4;
    v19 = *((_QWORD *)this + 187);
    v20 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)v19 + 32LL);
    v21 = STRU::QueryStr((STRU *)v33);
    v22 = STRU::QueryStr((STRU *)v32);
    v8 = v20(v19, v22, v21, &v29, 0);
    if ( v8 < 0 )
      goto LABEL_4;
  }
  STRU::SyncWithBuffer((STRU *)v33);
  v23 = STRU::QueryStr((STRU *)v33);
  _wcsupr(v23);
  v24 = STRU::QueryStr((STRU *)v33);
  TREE_HASH_TABLE::FindRecord((W3_SERVER *)((char *)this + 1424), v24, (void **)&v28);
  if ( v28 )
  {
    *a4 = v28;
    v8 = 0;
    goto LABEL_7;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 187) + 56LL))(*((_QWORD *)this + 187), &v31);
  if ( v8 < 0 )
    goto LABEL_4;
  v8 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, _QWORD, _QWORD, struct INativeConfigurationElement **, _QWORD, _QWORD))(*(_QWORD *)v31 + 40LL))(
         v31,
         a2,
         a3,
         0,
         0,
         &v30,
         0,
         0);
  if ( v8 < 0 )
    goto LABEL_4;
  v25 = (W3_METADATA *)operator new(0x148u);
  if ( !v25 )
  {
    v9 = 0;
    v28 = 0;
    goto LABEL_28;
  }
  v28 = W3_METADATA::W3_METADATA(v25);
  v9 = v28;
  if ( !v28 )
  {
LABEL_28:
    v8 = -2147024888;
    goto LABEL_5;
  }
  v26 = v30;
  v27 = STRU::QueryStr((STRU *)v33);
  v8 = W3_METADATA::Initialize(v28, v27, v26, 0, 0, 0, 0, 0);
  if ( v8 >= 0 )
  {
    TREE_HASH_TABLE::InsertRecord((W3_SERVER *)((char *)this + 1424), v28);
    v9 = 0;
    *a4 = v28;
    v28 = 0;
    goto LABEL_5;
  }
LABEL_4:
  v9 = v28;
LABEL_5:
  if ( !v9 )
    goto LABEL_8;
  (*(void (__fastcall **)(W3_METADATA *))(*(_QWORD *)v9 + 40LL))(v9);
LABEL_7:
  v28 = 0;
LABEL_8:
  if ( v30 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  STRU::~STRU((STRU *)v34);
  STRU::~STRU((STRU *)v33);
  STRU::~STRU((STRU *)v32);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001cab0  push    rbp
0x18001cab2  push    rbx
0x18001cab3  push    rsi
0x18001cab4  push    rdi
0x18001cab5  push    r12
0x18001cab7  push    r13
0x18001cab9  push    r14
0x18001cabb  push    r15
0x18001cabd  lea     rbp, [rsp-0A38h]
0x18001cac5  sub     rsp, 0B38h
0x18001cacc  mov     rax, cs:__security_cookie
0x18001cad3  xor     rax, rsp
0x18001cad6  mov     [rbp+0A70h+var_50], rax
0x18001cadd  xor     esi, esi
0x18001cadf  mov     r13, r8
0x18001cae2  mov     r12, rdx
0x18001cae5  mov     [rsp+0B70h+var_B20], rsi
0x18001caea  mov     r14, rcx
0x18001caed  mov     [rsp+0B70h+var_B10], rsi
0x18001caf2  mov     edi, 100h
0x18001caf7  mov     [rsp+0B70h+var_B08], rsi
0x18001cafc  mov     r8d, edi; Size
0x18001caff  lea     rcx, [rbp+0A70h+var_A50]; void *
0x18001cb03  xor     edx, edx; Val
0x18001cb05  mov     r15, r9
0x18001cb08  call    memset_0
0x18001cb0d  lea     ebx, [rdi-80h]
0x18001cb10  mov     r8d, ebx
0x18001cb13  lea     rdx, [rbp+0A70h+var_A50]
0x18001cb17  lea     rcx, [rsp+0B70h+var_B00]
0x18001cb1c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001cb23  nop     dword ptr [rax+rax+00h]
0x18001cb28  mov     r8d, edi; Size
0x18001cb2b  lea     rcx, [rbp+0A70h+var_950]; void *
0x18001cb32  xor     edx, edx; Val
0x18001cb34  call    memset_0
0x18001cb39  mov     r8d, ebx
0x18001cb3c  lea     rdx, [rbp+0A70h+var_950]
0x18001cb43  lea     rcx, [rbp+0A70h+var_AC8]
0x18001cb47  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001cb4e  nop     dword ptr [rax+rax+00h]
0x18001cb53  xor     edx, edx; Val
0x18001cb55  lea     rcx, [rbp+0A70h+var_850]; void *
0x18001cb5c  mov     r8d, 800h; Size
0x18001cb62  call    memset_0
0x18001cb67  mov     r8d, 400h
0x18001cb6d  lea     rdx, [rbp+0A70h+var_850]
0x18001cb74  lea     rcx, [rbp+0A70h+var_A90]
0x18001cb78  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001cb7f  nop     dword ptr [rax+rax+00h]
0x18001cb84  lea     r8d, [rsi+18h]
0x18001cb88  mov     [rsp+0B70h+var_B18], esi
0x18001cb8c  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT/APPHOST/"
0x18001cb93  lea     rcx, [rsp+0B70h+var_B00]
0x18001cb98  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18001cb9f  nop     dword ptr [rax+rax+00h]
0x18001cba4  mov     ebx, eax
0x18001cba6  test    eax, eax
0x18001cba8  js      short loc_18001CBE2
0x18001cbaa  mov     rdx, r12
0x18001cbad  lea     rcx, [rsp+0B70h+var_B00]
0x18001cbb2  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001cbb9  nop     dword ptr [rax+rax+00h]
0x18001cbbe  mov     ebx, eax
0x18001cbc0  test    eax, eax
0x18001cbc2  js      short loc_18001CBE2
0x18001cbc4  mov     rdx, r13
0x18001cbc7  lea     rcx, [rsp+0B70h+var_B00]
0x18001cbcc  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001cbd3  nop     dword ptr [rax+rax+00h]
0x18001cbd8  mov     ebx, eax
0x18001cbda  test    eax, eax
0x18001cbdc  jns     loc_18001CCAF
0x18001cbe2  mov     rcx, [rsp+0B70h+var_B20]
0x18001cbe7  test    rcx, rcx
0x18001cbea  jz      short loc_18001CBFD
0x18001cbec  mov     rax, [rcx]
0x18001cbef  mov     rax, [rax+28h]
0x18001cbf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbf8  mov     [rsp+0B70h+var_B20], rsi
0x18001cbfd  mov     rcx, [rsp+0B70h+var_B10]
0x18001cc02  test    rcx, rcx
0x18001cc05  jz      short loc_18001CC18
0x18001cc07  mov     rax, [rcx]
0x18001cc0a  mov     rax, [rax+10h]
0x18001cc0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc13  mov     [rsp+0B70h+var_B10], rsi
0x18001cc18  mov     rcx, [rsp+0B70h+var_B08]
0x18001cc1d  test    rcx, rcx
0x18001cc20  jz      short loc_18001CC33
0x18001cc22  mov     rax, [rcx]
0x18001cc25  mov     rax, [rax+10h]
0x18001cc29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc2e  mov     [rsp+0B70h+var_B08], rsi
0x18001cc33  lea     rcx, [rbp+0A70h+var_A90]
0x18001cc37  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001cc3e  nop     dword ptr [rax+rax+00h]
0x18001cc43  lea     rcx, [rbp+0A70h+var_AC8]
0x18001cc47  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001cc4e  nop     dword ptr [rax+rax+00h]
0x18001cc53  lea     rcx, [rsp+0B70h+var_B00]
0x18001cc58  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001cc5f  nop     dword ptr [rax+rax+00h]
0x18001cc64  mov     eax, ebx
0x18001cc66  mov     rcx, [rbp+0A70h+var_50]
0x18001cc6d  xor     rcx, rsp; StackCookie
0x18001cc70  call    __security_check_cookie
0x18001cc75  add     rsp, 0B38h
0x18001cc7c  pop     r15
0x18001cc7e  pop     r14
0x18001cc80  pop     r13
0x18001cc82  pop     r12
0x18001cc84  pop     rdi
0x18001cc85  pop     rsi
0x18001cc86  pop     rbx
0x18001cc87  pop     rbp
0x18001cc88  retn
0x18001cc8a  lea     rcx, [rsp+0B70h+var_B00]
0x18001cc8f  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18001cc96  nop     dword ptr [rax+rax+00h]
0x18001cc9b  lea     rcx, [rsp+0B70h+var_B00]
0x18001cca0  lea     edx, [rax-1]
0x18001cca3  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18001ccaa  nop     dword ptr [rax+rax+00h]
0x18001ccaf  lea     rcx, [rsp+0B70h+var_B00]
0x18001ccb4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001ccbb  nop     dword ptr [rax+rax+00h]
0x18001ccc0  lea     rcx, [rsp+0B70h+var_B00]
0x18001ccc5  mov     rbx, rax
0x18001ccc8  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18001cccf  nop     dword ptr [rax+rax+00h]
0x18001ccd4  dec     eax
0x18001ccd6  cmp     word ptr [rbx+rax*2], 2Fh ; '/'
0x18001ccdb  jz      short loc_18001CC8A
0x18001ccdd  lea     rcx, [rbp+0A70h+var_AC8]
0x18001cce1  call    cs:__imp_?QuerySizeCCH@STRU@@QEBAKXZ; STRU::QuerySizeCCH(void)
0x18001cce8  nop     dword ptr [rax+rax+00h]
0x18001cced  mov     rsi, [r14+5D8h]
0x18001ccf4  lea     rcx, [rbp+0A70h+var_AC8]
0x18001ccf8  mov     [rsp+0B70h+var_B18], eax
0x18001ccfc  mov     rax, [rsi]
0x18001ccff  mov     rdi, [rax+20h]
0x18001cd03  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001cd0a  nop     dword ptr [rax+rax+00h]
0x18001cd0f  lea     rcx, [rsp+0B70h+var_B00]
0x18001cd14  mov     rbx, rax
0x18001cd17  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001cd1e  nop     dword ptr [rax+rax+00h]
0x18001cd23  lea     r9, [rsp+0B70h+var_B18]
0x18001cd28  mov     qword ptr [rsp+0B70h+var_B50], 0
0x18001cd31  mov     rdx, rax
0x18001cd34  mov     r8, rbx
0x18001cd37  mov     rax, rdi
0x18001cd3a  mov     rcx, rsi
0x18001cd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd42  xor     esi, esi
0x18001cd44  mov     ebx, eax
0x18001cd46  test    eax, eax
0x18001cd48  jns     loc_18001CDD6
0x18001cd4e  cmp     eax, 8007007Ah
0x18001cd53  jnz     loc_18001CBE2
0x18001cd59  mov     edx, [rsp+0B70h+var_B18]
0x18001cd5d  lea     rcx, [rbp+0A70h+var_AC8]
0x18001cd61  add     edx, edx
0x18001cd63  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18001cd6a  nop     dword ptr [rax+rax+00h]
0x18001cd6f  mov     ebx, eax
0x18001cd71  test    eax, eax
0x18001cd73  js      loc_18001CBE2
0x18001cd79  mov     rsi, [r14+5D8h]
0x18001cd80  lea     rcx, [rbp+0A70h+var_AC8]
0x18001cd84  mov     rax, [rsi]
0x18001cd87  mov     rdi, [rax+20h]
0x18001cd8b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001cd92  nop     dword ptr [rax+rax+00h]
0x18001cd97  lea     rcx, [rsp+0B70h+var_B00]
0x18001cd9c  mov     rbx, rax
0x18001cd9f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001cda6  nop     dword ptr [rax+rax+00h]
0x18001cdab  lea     r9, [rsp+0B70h+var_B18]
0x18001cdb0  mov     qword ptr [rsp+0B70h+var_B50], 0
0x18001cdb9  mov     rdx, rax
0x18001cdbc  mov     r8, rbx
0x18001cdbf  mov     rax, rdi
0x18001cdc2  mov     rcx, rsi
0x18001cdc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdca  xor     esi, esi
0x18001cdcc  mov     ebx, eax
0x18001cdce  test    eax, eax
0x18001cdd0  js      loc_18001CBE2
0x18001cdd6  lea     rcx, [rbp+0A70h+var_AC8]
0x18001cdda  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18001cde1  nop     dword ptr [rax+rax+00h]
0x18001cde6  lea     rcx, [rbp+0A70h+var_AC8]
0x18001cdea  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001cdf1  nop     dword ptr [rax+rax+00h]
0x18001cdf6  mov     rcx, rax; String
0x18001cdf9  call    cs:__imp__wcsupr
0x18001ce00  nop     dword ptr [rax+rax+00h]
0x18001ce05  lea     rcx, [rbp+0A70h+var_AC8]
0x18001ce09  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001ce10  nop     dword ptr [rax+rax+00h]
0x18001ce15  lea     rdi, [r14+590h]
0x18001ce1c  mov     rdx, rax
0x18001ce1f  mov     rcx, rdi
0x18001ce22  lea     r8, [rsp+0B70h+var_B20]
0x18001ce27  call    cs:__imp_?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z; TREE_HASH_TABLE::FindRecord(ushort const *,void * *)
0x18001ce2e  nop     dword ptr [rax+rax+00h]
0x18001ce33  mov     rax, [rsp+0B70h+var_B20]
0x18001ce38  test    rax, rax
0x18001ce3b  jz      short loc_18001CE47
0x18001ce3d  mov     [r15], rax
0x18001ce40  mov     ebx, esi
0x18001ce42  jmp     loc_18001CBF8
0x18001ce47  mov     rcx, [r14+5D8h]
0x18001ce4e  lea     rdx, [rsp+0B70h+var_B08]
0x18001ce53  mov     rax, [rcx]
0x18001ce56  mov     rax, [rax+38h]
0x18001ce5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce5f  mov     ebx, eax
0x18001ce61  test    eax, eax
0x18001ce63  js      loc_18001CBE2
0x18001ce69  mov     rcx, [rsp+0B70h+var_B08]
0x18001ce6e  lea     rdx, [rsp+0B70h+var_B10]
0x18001ce73  mov     [rsp+0B70h+var_B38], rsi
0x18001ce78  xor     r9d, r9d
0x18001ce7b  mov     [rsp+0B70h+var_B40], rsi
0x18001ce80  mov     r8, r13
0x18001ce83  mov     [rsp+0B70h+var_B48], rdx
0x18001ce88  mov     rdx, r12
0x18001ce8b  mov     rax, [rcx]
0x18001ce8e  mov     qword ptr [rsp+0B70h+var_B50], rsi
0x18001ce93  mov     rax, [rax+28h]
0x18001ce97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce9c  mov     ebx, eax
0x18001ce9e  test    eax, eax
0x18001cea0  js      loc_18001CBE2
0x18001cea6  mov     ecx, 148h; Size
0x18001ceab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ceb0  test    rax, rax
0x18001ceb3  jz      loc_18001CF3D
0x18001ceb9  mov     rcx, rax; this
0x18001cebc  call    ??0W3_METADATA@@QEAA@XZ; W3_METADATA::W3_METADATA(void)
0x18001cec1  mov     [rsp+0B70h+var_B20], rax
0x18001cec6  mov     rcx, rax
0x18001cec9  test    rax, rax
0x18001cecc  jz      short loc_18001CF45
0x18001cece  mov     rbx, [rsp+0B70h+var_B10]
0x18001ced3  lea     rcx, [rbp+0A70h+var_AC8]
0x18001ced7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001cede  nop     dword ptr [rax+rax+00h]
0x18001cee3  mov     rcx, [rsp+0B70h+var_B20]; this
0x18001cee8  xor     r9d, r9d; char *
0x18001ceeb  mov     [rsp+0B70h+var_B38], rsi; struct IHttpTraceContext *
0x18001cef0  mov     rdx, rax; unsigned __int16 *
0x18001cef3  mov     [rsp+0B70h+var_B40], rsi; struct STRU *
0x18001cef8  mov     r8, rbx; struct INativeConfigurationElement *
0x18001cefb  mov     [rsp+0B70h+var_B48], rsi; struct INativeSectionException **
0x18001cf00  mov     [rsp+0B70h+var_B50], si; unsigned __int16
0x18001cf05  call    ?Initialize@W3_METADATA@@QEAAJPEBGPEAVINativeConfigurationElement@@PEBDGPEAPEAVINativeSectionException@@PEAVSTRU@@PEAVIHttpTraceContext@@@Z; W3_METADATA::Initialize(ushort const *,INativeConfigurationElement *,char const *,ushort,INativeSectionException * *,STRU *,IHttpTraceContext *)
0x18001cf0a  mov     ebx, eax
0x18001cf0c  test    eax, eax
0x18001cf0e  js      loc_18001CBE2
0x18001cf14  mov     rdx, [rsp+0B70h+var_B20]
0x18001cf19  mov     rcx, rdi
0x18001cf1c  call    cs:__imp_?InsertRecord@TREE_HASH_TABLE@@QEAAJPEAX@Z; TREE_HASH_TABLE::InsertRecord(void *)
0x18001cf23  nop     dword ptr [rax+rax+00h]
0x18001cf28  mov     rax, [rsp+0B70h+var_B20]
0x18001cf2d  mov     rcx, rsi
0x18001cf30  mov     [r15], rax
0x18001cf33  mov     [rsp+0B70h+var_B20], rcx
0x18001cf38  jmp     loc_18001CBE7
0x18001cf3d  mov     rcx, rsi
0x18001cf40  mov     [rsp+0B70h+var_B20], rcx
0x18001cf45  mov     ebx, 80070008h
0x18001cf4a  jmp     loc_18001CBE7
```
