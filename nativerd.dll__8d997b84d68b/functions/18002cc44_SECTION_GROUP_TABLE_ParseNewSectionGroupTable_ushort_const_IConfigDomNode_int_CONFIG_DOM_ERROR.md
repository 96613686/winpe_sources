# SECTION_GROUP_TABLE::ParseNewSectionGroupTable(ushort const *,IConfigDomNode *,int,CONFIG_DOM_ERROR *)

- ea: `0x18002cc44`
- end: `0x18002cfff`
- name: `?ParseNewSectionGroupTable@SECTION_GROUP_TABLE@@AEAAJPEBGPEAVIConfigDomNode@@HPEAVCONFIG_DOM_ERROR@@@Z`
- size: `955`
- prototype: `__int64 __usercall@<rax>(SECTION_GROUP_TABLE *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, struct IConfigDomNode *@<r8>, int@<r9d>, struct CONFIG_DOM_ERROR *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18002c078`

## callees

- `0x18000a83c`
- `0x180010468`
- `0x18001807c`
- `0x180018edc`
- `0x18001a118`
- `0x18001c250`
- `0x180023664`
- `0x180025a10`
- `0x18002baf0`
- `0x18002c078`
- `0x18002cc44`
- `0x180059bea`
- `0x180059bf6`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18002cfb4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002cfbf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002cfc9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002cfd4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002cfb4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002cfbf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002cfc9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002cfd4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002cdc3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002cde4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ce28`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ce85`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002cea5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ceb3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002cefd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002cf1c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002cf57`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002cdc3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002cde4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ce28`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ce85`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002cea5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ceb3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002cefd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002cf1c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002cf57`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002ccb0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002ccd5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002ccfb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002cd21`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002ccb0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002ccd5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002ccfb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002cd21`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18002ce58`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18002ce58`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18002ce05`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18002ce05`

## pseudocode

```c
__int64 __fastcall SECTION_GROUP_TABLE::ParseNewSectionGroupTable(
        SECTION_GROUP_TABLE *this,
        const unsigned __int16 *a2,
        struct IConfigDomNode *a3,
        int a4,
        struct CONFIG_DOM_ERROR *a5)
{
  SECTION_GROUP_TABLE *v8; // rdi
  int v9; // ebx
  const wchar_t *Str; // rax
  STRU *v11; // rcx
  const wchar_t *v12; // rax
  unsigned __int16 *v13; // rax
  unsigned int v14; // r9d
  const unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rax
  SECTION_GROUP_TABLE *v17; // rax
  const unsigned __int16 *v18; // rax
  const unsigned __int16 *v19; // rax
  int v20; // eax
  unsigned int v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+34h] [rbp-CCh]
  SECTION_GROUP_TABLE *v24; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v25[56]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[56]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v27[56]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v28[56]; // [rsp+E8h] [rbp-18h] BYREF
  char *v29[2]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v30; // [rsp+130h] [rbp+30h]
  unsigned __int16 v31[32]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v32[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v33[256]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v34[256]; // [rsp+400h] [rbp+300h] BYREF

  v23 = a4;
  memset_0(v33, 0, sizeof(v33));
  STRU::STRU((STRU *)v25, v33, 0x100u);
  memset_0(v34, 0, sizeof(v34));
  STRU::STRU((STRU *)v28, v34, 0x100u);
  memset_0(v31, 0, sizeof(v31));
  STRU::STRU((STRU *)v26, v31, 0x20u);
  memset_0(v32, 0, sizeof(v32));
  STRU::STRU((STRU *)v27, v32, 0x40u);
  v8 = 0;
  v22 = 0;
  v24 = 0;
  *(_OWORD *)v29 = 0;
  v30 = 0;
  if ( !a2 || !a3 || !a5 )
  {
    v9 = -2147024809;
    goto LABEL_34;
  }
  v9 = (*(__int64 (__fastcall **)(struct IConfigDomNode *, unsigned int *))(*(_QWORD *)a3 + 48LL))(a3, &v22);
  if ( v9 < 0 )
    goto LABEL_36;
  while ( (unsigned int)v8 < v22 )
  {
    v9 = (*(__int64 (__fastcall **)(struct IConfigDomNode *, _QWORD, _BYTE *, _BYTE *))(*(_QWORD *)a3 + 32LL))(
           a3,
           (unsigned int)v8,
           v26,
           v27);
    if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147023483 )
      goto LABEL_36;
    Str = STRU::QueryStr((STRU *)v26);
    if ( !wcscmp_0(Str, L"name") )
    {
      v11 = (STRU *)v25;
    }
    else
    {
      v12 = STRU::QueryStr((STRU *)v26);
      if ( wcscmp_0(v12, L"type") )
      {
        v9 = -2147024883;
        v13 = STRU::QueryStr((STRU *)v26);
        v14 = -1073739120;
        goto LABEL_15;
      }
      v11 = (STRU *)v28;
    }
    v9 = STRU::Copy(v11, (const struct STRU *)v27);
    if ( v9 < 0 )
      goto LABEL_36;
    LODWORD(v8) = (_DWORD)v8 + 1;
  }
  if ( STRU::IsEmpty((STRU *)v25) )
  {
    v29[0] = (char *)L"name";
    v9 = -2147024883;
    v29[1] = (char *)L"sectionGroup";
    v14 = -1073739118;
    goto LABEL_16;
  }
  v15 = STRU::QueryStr((STRU *)v25);
  if ( !(unsigned int)CONFIG_SECTION::IsValidSectionName(v15, 0) )
  {
    v9 = -2147024883;
    v13 = STRU::QueryStr((STRU *)v25);
    v14 = -1073739061;
LABEL_15:
    v29[0] = (char *)v13;
LABEL_16:
    CONFIG_DOM_ERROR::SetNodeError(a5, -2147024883, a3, v14, (const char **const)v29);
    goto LABEL_36;
  }
  v16 = STRU::QueryStr((STRU *)v25);
  if ( (int)CONFIG_HASH<SECTION_GROUP_TABLE>::Find((char *)this + 96, v16, &v24) >= 0 )
  {
    v8 = v24;
    v20 = SECTION_GROUP_TABLE::Parse(v24, a2, a3, v23, a5);
LABEL_31:
    v9 = v20;
    if ( v20 >= 0 )
      v9 = 0;
    goto LABEL_34;
  }
  v17 = (SECTION_GROUP_TABLE *)operator new(0x90u);
  if ( !v17 )
  {
    v8 = 0;
    goto LABEL_29;
  }
  v8 = SECTION_GROUP_TABLE::SECTION_GROUP_TABLE(v17, this);
  if ( !v8 )
  {
LABEL_29:
    v9 = -2147024888;
    goto LABEL_34;
  }
  v18 = STRU::QueryStr((STRU *)v25);
  v9 = SECTION_GROUP_TABLE::Create(v8, v18);
  if ( v9 >= 0 )
  {
    v19 = STRU::QueryStr((STRU *)v28);
    v9 = SMALL_STRU::Copy((SECTION_GROUP_TABLE *)((char *)v8 + 48), v19);
    if ( v9 >= 0 )
    {
      v9 = SECTION_GROUP_TABLE::Parse(v8, a2, a3, v23, a5);
      if ( v9 >= 0 )
      {
        STRU::QueryStr((STRU *)v25);
        v20 = CONFIG_HASH<CONFIG_ELEMENT>::Insert((SECTION_GROUP_TABLE *)((char *)this + 96));
        goto LABEL_31;
      }
    }
  }
LABEL_34:
  if ( v8 )
    SECTION_GROUP_TABLE::DereferenceSectionGroupTable(v8);
LABEL_36:
  STRU::~STRU((STRU *)v27);
  STRU::~STRU((STRU *)v26);
  STRU::~STRU((STRU *)v28);
  STRU::~STRU((STRU *)v25);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002cc44  push    rbp
0x18002cc46  push    rbx
0x18002cc47  push    rsi
0x18002cc48  push    rdi
0x18002cc49  push    r12
0x18002cc4b  push    r13
0x18002cc4d  push    r14
0x18002cc4f  push    r15
0x18002cc51  lea     rbp, [rsp-518h]
0x18002cc59  sub     rsp, 618h
0x18002cc60  mov     rax, cs:__security_cookie
0x18002cc67  xor     rax, rsp
0x18002cc6a  mov     [rbp+550h+var_50], rax
0x18002cc71  mov     r14, [rbp+550h+arg_20]
0x18002cc78  mov     rsi, r8
0x18002cc7b  mov     r12, rdx
0x18002cc7e  mov     [rsp+650h+var_61C], r9d
0x18002cc83  mov     r13, rcx
0x18002cc86  mov     edi, 200h
0x18002cc8b  mov     r8d, edi; Size
0x18002cc8e  lea     rcx, [rbp+550h+var_450]; void *
0x18002cc95  xor     edx, edx; Val
0x18002cc97  call    memset_0
0x18002cc9c  mov     ebx, 100h
0x18002cca1  lea     rdx, [rbp+550h+var_450]
0x18002cca8  mov     r8d, ebx
0x18002ccab  lea     rcx, [rsp+650h+var_610]
0x18002ccb0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002ccb6  mov     r8d, edi; Size
0x18002ccb9  lea     rcx, [rbp+550h+var_250]; void *
0x18002ccc0  xor     edx, edx; Val
0x18002ccc2  call    memset_0
0x18002ccc7  mov     r8d, ebx
0x18002ccca  lea     rdx, [rbp+550h+var_250]
0x18002ccd1  lea     rcx, [rbp+550h+var_568]
0x18002ccd5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002ccdb  mov     ebx, 40h ; '@'
0x18002cce0  lea     rcx, [rbp+550h+var_510]; void *
0x18002cce4  mov     r8d, ebx; Size
0x18002cce7  xor     edx, edx; Val
0x18002cce9  call    memset_0
0x18002ccee  lea     r8d, [rbx-20h]
0x18002ccf2  lea     rdx, [rbp+550h+var_510]
0x18002ccf6  lea     rcx, [rsp+650h+var_5D8]
0x18002ccfb  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002cd01  xor     edx, edx; Val
0x18002cd03  lea     r8d, [rbx+40h]; Size
0x18002cd07  lea     rcx, [rbp+550h+var_4D0]; void *
0x18002cd0e  call    memset_0
0x18002cd13  mov     r8d, ebx
0x18002cd16  lea     rdx, [rbp+550h+var_4D0]
0x18002cd1d  lea     rcx, [rbp+550h+var_5A0]
0x18002cd21  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002cd27  xor     edi, edi
0x18002cd29  mov     [rsp+650h+var_620], 0
0x18002cd31  mov     [rsp+650h+var_618], rdi
0x18002cd36  xorps   xmm0, xmm0
0x18002cd39  movups  xmmword ptr [rbp+550h+var_530], xmm0
0x18002cd3d  movups  [rbp+550h+var_520], xmm0
0x18002cd41  test    r12, r12
0x18002cd44  jz      loc_18002CF9E
0x18002cd4a  test    rsi, rsi
0x18002cd4d  jz      loc_18002CF9E
0x18002cd53  test    r14, r14
0x18002cd56  jz      loc_18002CF9E
0x18002cd5c  mov     rax, [rsi]
0x18002cd5f  lea     rdx, [rsp+650h+var_620]
0x18002cd64  mov     rcx, rsi
0x18002cd67  mov     rax, [rax+30h]
0x18002cd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd70  mov     ebx, eax
0x18002cd72  test    eax, eax
0x18002cd74  js      loc_18002CFB0
0x18002cd7a  lea     r15, aName; "name"
0x18002cd81  cmp     edi, [rsp+650h+var_620]
0x18002cd85  jnb     loc_18002CE53
0x18002cd8b  mov     rax, [rsi]
0x18002cd8e  lea     r9, [rbp+550h+var_5A0]
0x18002cd92  lea     r8, [rsp+650h+var_5D8]
0x18002cd97  mov     edx, edi
0x18002cd99  mov     rcx, rsi
0x18002cd9c  mov     rax, [rax+20h]
0x18002cda0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cda5  mov     ecx, 80000000h
0x18002cdaa  mov     ebx, eax
0x18002cdac  add     eax, ecx
0x18002cdae  test    ecx, eax
0x18002cdb0  jnz     short loc_18002CDBE
0x18002cdb2  cmp     ebx, 80070585h
0x18002cdb8  jnz     loc_18002CFB0
0x18002cdbe  lea     rcx, [rsp+650h+var_5D8]
0x18002cdc3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002cdc9  mov     rcx, rax; String1
0x18002cdcc  mov     rdx, r15; String2
0x18002cdcf  call    wcscmp_0
0x18002cdd4  test    eax, eax
0x18002cdd6  jnz     short loc_18002CDDF
0x18002cdd8  lea     rcx, [rsp+650h+var_610]
0x18002cddd  jmp     short loc_18002CE01
0x18002cddf  lea     rcx, [rsp+650h+var_5D8]
0x18002cde4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002cdea  mov     rcx, rax; String1
0x18002cded  lea     rdx, aType; "type"
0x18002cdf4  call    wcscmp_0
0x18002cdf9  test    eax, eax
0x18002cdfb  jnz     short loc_18002CE1C
0x18002cdfd  lea     rcx, [rbp+550h+var_568]
0x18002ce01  lea     rdx, [rbp+550h+var_5A0]
0x18002ce05  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18002ce0b  mov     ebx, eax
0x18002ce0d  test    eax, eax
0x18002ce0f  js      loc_18002CFB0
0x18002ce15  inc     edi
0x18002ce17  jmp     loc_18002CD81
0x18002ce1c  mov     edi, 8007000Dh
0x18002ce21  lea     rcx, [rsp+650h+var_5D8]
0x18002ce26  mov     ebx, edi
0x18002ce28  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002ce2e  mov     r9d, 0C0000A90h; unsigned int
0x18002ce34  mov     [rbp+550h+var_530], rax
0x18002ce38  lea     rax, [rbp+550h+var_530]
0x18002ce3c  mov     r8, rsi; struct IConfigDomNode *
0x18002ce3f  mov     edx, edi; int
0x18002ce41  mov     [rsp+650h+var_630], rax; char **
0x18002ce46  mov     rcx, r14; this
0x18002ce49  call    ?SetNodeError@CONFIG_DOM_ERROR@@QEAAJJPEAVIConfigDomNode@@KQEAPEBD@Z; CONFIG_DOM_ERROR::SetNodeError(long,IConfigDomNode *,ulong,char const * * const)
0x18002ce4e  jmp     loc_18002CFB0
0x18002ce53  lea     rcx, [rsp+650h+var_610]
0x18002ce58  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18002ce5e  test    al, al
0x18002ce60  jz      short loc_18002CE80
0x18002ce62  mov     edi, 8007000Dh
0x18002ce67  mov     [rbp+550h+var_530], r15
0x18002ce6b  lea     rax, aSectiongroup; "sectionGroup"
0x18002ce72  mov     ebx, edi
0x18002ce74  mov     [rbp+550h+var_530+8], rax
0x18002ce78  mov     r9d, 0C0000A92h
0x18002ce7e  jmp     short loc_18002CE38
0x18002ce80  lea     rcx, [rsp+650h+var_610]
0x18002ce85  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002ce8b  mov     rcx, rax; unsigned __int16 *
0x18002ce8e  xor     edx, edx; int
0x18002ce90  call    ?IsValidSectionName@CONFIG_SECTION@@SAHPEBGH@Z; CONFIG_SECTION::IsValidSectionName(ushort const *,int)
0x18002ce95  lea     rcx, [rsp+650h+var_610]
0x18002ce9a  test    eax, eax
0x18002ce9c  jnz     short loc_18002CEB3
0x18002ce9e  mov     edi, 8007000Dh
0x18002cea3  mov     ebx, edi
0x18002cea5  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002ceab  mov     r9d, 0C0000ACBh
0x18002ceb1  jmp     short loc_18002CE34
0x18002ceb3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002ceb9  mov     rdx, rax
0x18002cebc  lea     r8, [rsp+650h+var_618]
0x18002cec1  lea     rcx, [r13+60h]
0x18002cec5  call    ?Find@?$CONFIG_HASH@VSECTION_GROUP_TABLE@@@@QEAAJPEBGPEAPEAVSECTION_GROUP_TABLE@@H@Z; CONFIG_HASH<SECTION_GROUP_TABLE>::Find(ushort const *,SECTION_GROUP_TABLE * *,int)
0x18002ceca  test    eax, eax
0x18002cecc  jns     loc_18002CF77
0x18002ced2  mov     ecx, 90h; Size
0x18002ced7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cedc  test    rax, rax
0x18002cedf  jz      loc_18002CF6E
0x18002cee5  mov     rdx, r13; struct SECTION_GROUP_TABLE *
0x18002cee8  mov     rcx, rax; this
0x18002ceeb  call    ??0SECTION_GROUP_TABLE@@QEAA@PEAV0@@Z; SECTION_GROUP_TABLE::SECTION_GROUP_TABLE(SECTION_GROUP_TABLE *)
0x18002cef0  mov     rdi, rax
0x18002cef3  test    rax, rax
0x18002cef6  jz      short loc_18002CF70
0x18002cef8  lea     rcx, [rsp+650h+var_610]
0x18002cefd  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002cf03  mov     rdx, rax; unsigned __int16 *
0x18002cf06  mov     rcx, rdi; this
0x18002cf09  call    ?Create@SECTION_GROUP_TABLE@@QEAAJPEBG@Z; SECTION_GROUP_TABLE::Create(ushort const *)
0x18002cf0e  mov     ebx, eax
0x18002cf10  test    eax, eax
0x18002cf12  js      loc_18002CFA3
0x18002cf18  lea     rcx, [rbp+550h+var_568]
0x18002cf1c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002cf22  mov     rdx, rax; unsigned __int16 *
0x18002cf25  lea     rcx, [rdi+30h]; this
0x18002cf29  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x18002cf2e  mov     ebx, eax
0x18002cf30  test    eax, eax
0x18002cf32  js      short loc_18002CFA3
0x18002cf34  mov     r9d, [rsp+650h+var_61C]; int
0x18002cf39  mov     r8, rsi; struct IConfigDomNode *
0x18002cf3c  mov     rdx, r12; unsigned __int16 *
0x18002cf3f  mov     [rsp+650h+var_630], r14; struct CONFIG_DOM_ERROR *
0x18002cf44  mov     rcx, rdi; this
0x18002cf47  call    ?Parse@SECTION_GROUP_TABLE@@QEAAJPEBGPEAVIConfigDomNode@@HPEAVCONFIG_DOM_ERROR@@@Z; SECTION_GROUP_TABLE::Parse(ushort const *,IConfigDomNode *,int,CONFIG_DOM_ERROR *)
0x18002cf4c  mov     ebx, eax
0x18002cf4e  test    eax, eax
0x18002cf50  js      short loc_18002CFA3
0x18002cf52  lea     rcx, [rsp+650h+var_610]
0x18002cf57  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002cf5d  mov     r8, rdi
0x18002cf60  lea     rcx, [r13+60h]; this
0x18002cf64  mov     rdx, rax
0x18002cf67  call    ?Insert@?$CONFIG_HASH@VCONFIG_ELEMENT@@@@QEAAJPEBGPEAVCONFIG_ELEMENT@@H@Z; CONFIG_HASH<CONFIG_ELEMENT>::Insert(ushort const *,CONFIG_ELEMENT *,int)
0x18002cf6c  jmp     short loc_18002CF94
0x18002cf6e  xor     edi, edi
0x18002cf70  mov     ebx, 80070008h
0x18002cf75  jmp     short loc_18002CFA3
0x18002cf77  mov     rdi, [rsp+650h+var_618]
0x18002cf7c  mov     r8, rsi; struct IConfigDomNode *
0x18002cf7f  mov     r9d, [rsp+650h+var_61C]; int
0x18002cf84  mov     rcx, rdi; this
0x18002cf87  mov     rdx, r12; unsigned __int16 *
0x18002cf8a  mov     [rsp+650h+var_630], r14; struct CONFIG_DOM_ERROR *
0x18002cf8f  call    ?Parse@SECTION_GROUP_TABLE@@QEAAJPEBGPEAVIConfigDomNode@@HPEAVCONFIG_DOM_ERROR@@@Z; SECTION_GROUP_TABLE::Parse(ushort const *,IConfigDomNode *,int,CONFIG_DOM_ERROR *)
0x18002cf94  mov     ebx, eax
0x18002cf96  test    eax, eax
0x18002cf98  js      short loc_18002CFA3
0x18002cf9a  xor     ebx, ebx
0x18002cf9c  jmp     short loc_18002CFA3
0x18002cf9e  mov     ebx, 80070057h
0x18002cfa3  test    rdi, rdi
0x18002cfa6  jz      short loc_18002CFB0
0x18002cfa8  mov     rcx, rdi; this
0x18002cfab  call    ?DereferenceSectionGroupTable@SECTION_GROUP_TABLE@@QEAAXXZ; SECTION_GROUP_TABLE::DereferenceSectionGroupTable(void)
0x18002cfb0  lea     rcx, [rbp+550h+var_5A0]
0x18002cfb4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002cfba  lea     rcx, [rsp+650h+var_5D8]
0x18002cfbf  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002cfc5  lea     rcx, [rbp+550h+var_568]
0x18002cfc9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002cfcf  lea     rcx, [rsp+650h+var_610]
0x18002cfd4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002cfda  mov     eax, ebx
0x18002cfdc  mov     rcx, [rbp+550h+var_50]
0x18002cfe3  xor     rcx, rsp; StackCookie
0x18002cfe6  call    __security_check_cookie
0x18002cfeb  add     rsp, 618h
0x18002cff2  pop     r15
0x18002cff4  pop     r14
0x18002cff6  pop     r13
0x18002cff8  pop     r12
0x18002cffa  pop     rdi
0x18002cffb  pop     rsi
0x18002cffc  pop     rbx
0x18002cffd  pop     rbp
0x18002cffe  retn
```
