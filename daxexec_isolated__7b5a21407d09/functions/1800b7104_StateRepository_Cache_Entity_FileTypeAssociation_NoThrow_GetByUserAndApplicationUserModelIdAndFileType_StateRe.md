# StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::GetByUserAndApplicationUserModelIdAndFileType(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,ushort const *,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::CacheFlags,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow &,bool &)

- ea: `0x1800b7104`
- end: `0x1800b7384`
- name: `?GetByUserAndApplicationUserModelIdAndFileType@FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBG2W4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800b8910`

## callees

- `0x18000ff24`
- `0x18003cccc`
- `0x1800b3980`
- `0x1800b5828`
- `0x1800b5928`
- `0x1800b7104`
- `0x1800bcbbc`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b722b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b730f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b722b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b730f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b71a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b7328`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b71a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b7328`

## string_xrefs

- `0x1800b7134`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800b7186`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800b71ec`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800b7209`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800b7367`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::GetByUserAndApplicationUserModelIdAndFileType(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4,
        __int64 a5,
        __int64 a6,
        _BYTE *a7)
{
  int v10; // eax
  int v11; // edi
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  int v20; // [rsp+20h] [rbp-A1h]
  int *v21; // [rsp+20h] [rbp-A1h]
  __int64 v22; // [rsp+30h] [rbp-91h] BYREF
  int v23; // [rsp+38h] [rbp-89h]
  __int64 v24; // [rsp+40h] [rbp-81h]
  int v25[4]; // [rsp+48h] [rbp-79h] BYREF
  __int128 v26; // [rsp+58h] [rbp-69h]
  __int128 v27; // [rsp+68h] [rbp-59h]
  __int128 v28; // [rsp+80h] [rbp-41h] BYREF
  __int64 v29; // [rsp+90h] [rbp-31h]
  __int64 v30; // [rsp+98h] [rbp-29h]
  __int128 v31; // [rsp+A0h] [rbp-21h]
  __int128 v32; // [rsp+B0h] [rbp-11h]
  __int64 v33; // [rsp+C0h] [rbp-1h]
  int v34; // [rsp+C8h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  *a7 = 0;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x378,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)0x80070057LL,
      v20);
    return 2147942487LL;
  }
  *(_OWORD *)v25 = 0;
  v21 = v25;
  v26 = 0;
  v27 = 0;
  v10 = StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId();
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37D,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)(unsigned int)v10,
      (int)v25);
LABEL_5:
    v12 = *((_QWORD *)&v27 + 1);
    *((_QWORD *)&v27 + 1) = 0;
    if ( v12 )
      SRCache_Free();
    return (unsigned int)v11;
  }
  if ( !*a7 )
    goto LABEL_24;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v13 = StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::OpenByFileType(
          (StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow *)&v22,
          a1,
          a4);
  v11 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x335,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)(unsigned int)v13,
      (int)v25);
    v14 = 898;
    goto LABEL_11;
  }
  v11 = StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::Get(
          &v22,
          (a5 | 1) & -(__int64)(a5 != 0),
          a6,
          a7);
  if ( v11 < 0 )
  {
    v14 = 900;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)(unsigned int)v11,
      (int)v21);
LABEL_12:
    v15 = v22;
    v22 = 0;
    if ( v15 )
      SRCacheContext_Close();
    goto LABEL_5;
  }
  while ( 1 )
  {
    if ( !*a7 )
      goto LABEL_22;
    v16 = *(_QWORD *)(a6 + 8);
    v29 = 0;
    v28 = 0;
    v31 = 0;
    v32 = 0;
    v30 = 0;
    v33 = 0;
    v34 = 0;
    v11 = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(a1, v16, 1, &v28);
    if ( v11 < 0 )
    {
      v19 = 905;
      goto LABEL_30;
    }
    if ( *a7 && *((_QWORD *)&v28 + 1) == *((_QWORD *)&v26 + 1) )
      break;
    ++v23;
    v11 = StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::Get(
            &v22,
            (a5 | 1) & -(__int64)(a5 != 0),
            a6,
            a7);
    if ( v11 < 0 )
    {
      v19 = 914;
LABEL_30:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-FileTypeAssociation.hpp",
        (const char *)(unsigned int)v11,
        (int)a7);
      StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v28);
      goto LABEL_12;
    }
    StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v28);
  }
  *a7 = 1;
  StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v28);
LABEL_22:
  v17 = v22;
  v22 = 0;
  if ( v17 )
    SRCacheContext_Close();
LABEL_24:
  v18 = *((_QWORD *)&v27 + 1);
  *((_QWORD *)&v27 + 1) = 0;
  if ( v18 )
    SRCache_Free();
  return 0;
}

```

## disassembly

```asm
0x1800b7104  push    rbp
0x1800b7106  push    rbx
0x1800b7107  push    rsi
0x1800b7108  push    rdi
0x1800b7109  push    r12
0x1800b710b  push    r14
0x1800b710d  push    r15
0x1800b710f  lea     rbp, [rsp-0Fh]
0x1800b7114  sub     rsp, 0D0h
0x1800b711b  mov     rbx, qword ptr [rbp+3Fh+arg_30]
0x1800b711f  xor     r12d, r12d
0x1800b7122  mov     rsi, r9
0x1800b7125  mov     r14, rcx
0x1800b7128  mov     [rbx], r12b
0x1800b712b  test    rdx, rdx
0x1800b712e  jnz     short loc_1800B7154
0x1800b7130  mov     rcx, [rbp+47h]; this
0x1800b7134  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b713b  mov     ebx, 80070057h
0x1800b7140  mov     edx, 378h; void *
0x1800b7145  mov     r9d, ebx; char *
0x1800b7148  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b714d  mov     eax, ebx
0x1800b714f  jmp     loc_1800B7336
0x1800b7154  xorps   xmm0, xmm0
0x1800b7157  mov     [rsp+100h+var_D8], rbx
0x1800b715c  xorps   xmm1, xmm1
0x1800b715f  lea     rax, [rbp+3Fh+var_B8]
0x1800b7163  movdqu  xmmword ptr [rbp+3Fh+var_B8], xmm0
0x1800b7168  mov     qword ptr [rsp+100h+var_E0], rax; int
0x1800b716d  movdqu  [rbp+3Fh+var_A8], xmm1
0x1800b7172  movdqu  [rbp+3Fh+var_98], xmm0
0x1800b7177  call    ?GetByUserAndApplicationUserModelId@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)
0x1800b717c  mov     edi, eax
0x1800b717e  test    eax, eax
0x1800b7180  jns     short loc_1800B71BA
0x1800b7182  mov     rcx, [rbp+47h]; this
0x1800b7186  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b718d  mov     r9d, eax; char *
0x1800b7190  mov     edx, 37Dh; void *
0x1800b7195  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b719a  mov     rcx, qword ptr [rbp+3Fh+var_98+8]
0x1800b719e  mov     qword ptr [rbp+3Fh+var_98+8], r12
0x1800b71a2  test    rcx, rcx
0x1800b71a5  jz      short loc_1800B71B3
0x1800b71a7  call    cs:__imp_SRCache_Free
0x1800b71ae  nop     dword ptr [rax+rax+00h]
0x1800b71b3  mov     eax, edi
0x1800b71b5  jmp     loc_1800B7336
0x1800b71ba  cmp     [rbx], r12b
0x1800b71bd  jz      loc_1800B731B
0x1800b71c3  mov     r8, rsi; unsigned __int16 *
0x1800b71c6  mov     [rsp+100h+var_D0], r12
0x1800b71cb  mov     rdx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x1800b71ce  mov     [rsp+100h+var_C8], r12d
0x1800b71d3  lea     rcx, [rsp+100h+var_D0]; this
0x1800b71d8  mov     [rsp+100h+var_C0], r12
0x1800b71dd  call    ?OpenByFileType@FileTypeAssociationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z; StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::OpenByFileType(StateRepository::Cache::Manager_NoThrow &,ushort const *)
0x1800b71e2  mov     edi, eax
0x1800b71e4  test    eax, eax
0x1800b71e6  jns     short loc_1800B723C
0x1800b71e8  mov     rcx, [rbp+47h]; this
0x1800b71ec  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b71f3  mov     r9d, eax; char *
0x1800b71f6  mov     edx, 335h; void *
0x1800b71fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b7200  mov     edx, 382h; void *
0x1800b7205  mov     rcx, [rbp+47h]; this
0x1800b7209  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b7210  mov     r9d, edi; char *
0x1800b7213  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b7218  mov     rcx, [rsp+100h+var_D0]
0x1800b721d  mov     [rsp+100h+var_D0], r12
0x1800b7222  test    rcx, rcx
0x1800b7225  jz      loc_1800B719A
0x1800b722b  call    cs:__imp_SRCacheContext_Close
0x1800b7232  nop     dword ptr [rax+rax+00h]
0x1800b7237  jmp     loc_1800B719A
0x1800b723c  mov     rax, [rbp+3Fh+arg_20]
0x1800b7240  mov     r9, rbx
0x1800b7243  mov     r15, [rbp+3Fh+arg_28]
0x1800b7247  mov     rcx, rax
0x1800b724a  or      rcx, 1
0x1800b724e  mov     r8, r15
0x1800b7251  neg     rax
0x1800b7254  sbb     rsi, rsi
0x1800b7257  and     rsi, rcx
0x1800b725a  lea     rcx, [rsp+100h+var_D0]
0x1800b725f  mov     rdx, rsi
0x1800b7262  call    ?Get@FileTypeAssociationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@FileTypeAssociation_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::CacheFlags,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow &,bool &)
0x1800b7267  mov     edi, eax
0x1800b7269  test    eax, eax
0x1800b726b  jns     loc_1800B72F7
0x1800b7271  mov     edx, 384h
0x1800b7276  jmp     short loc_1800B7205
0x1800b7278  mov     rdx, [r15+8]
0x1800b727c  lea     r9, [rbp+3Fh+var_80]
0x1800b7280  xorps   xmm0, xmm0
0x1800b7283  mov     [rbp+3Fh+var_70], r12
0x1800b7287  xorps   xmm1, xmm1
0x1800b728a  movdqa  [rbp+3Fh+var_80], xmm0
0x1800b728f  mov     r8d, 1
0x1800b7295  movdqa  [rbp+3Fh+var_60], xmm0
0x1800b729a  mov     rcx, r14
0x1800b729d  movdqa  [rbp+3Fh+var_50], xmm1
0x1800b72a2  mov     [rbp+3Fh+var_68], r12
0x1800b72a6  mov     [rbp+3Fh+var_40], r12
0x1800b72aa  mov     [rbp+3Fh+var_38], r12d
0x1800b72ae  mov     qword ptr [rsp+100h+var_E0], rbx; int
0x1800b72b3  call    ?Get@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1800b72b8  mov     edi, eax
0x1800b72ba  test    eax, eax
0x1800b72bc  js      loc_1800B735E
0x1800b72c2  cmp     [rbx], r12b
0x1800b72c5  jz      short loc_1800B72D1
0x1800b72c7  mov     rax, qword ptr [rbp+3Fh+var_A8+8]
0x1800b72cb  cmp     qword ptr [rbp+3Fh+var_80+8], rax
0x1800b72cf  jz      short loc_1800B7349
0x1800b72d1  inc     [rsp+100h+var_C8]
0x1800b72d5  lea     rcx, [rsp+100h+var_D0]
0x1800b72da  mov     r9, rbx
0x1800b72dd  mov     r8, r15
0x1800b72e0  mov     rdx, rsi
0x1800b72e3  call    ?Get@FileTypeAssociationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@FileTypeAssociation_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::CacheFlags,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow &,bool &)
0x1800b72e8  mov     edi, eax
0x1800b72ea  test    eax, eax
0x1800b72ec  js      short loc_1800B7357
0x1800b72ee  lea     rcx, [rbp+3Fh+var_80]; this
0x1800b72f2  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800b72f7  cmp     [rbx], r12b
0x1800b72fa  jnz     loc_1800B7278
0x1800b7300  mov     rcx, [rsp+100h+var_D0]
0x1800b7305  mov     [rsp+100h+var_D0], r12
0x1800b730a  test    rcx, rcx
0x1800b730d  jz      short loc_1800B731B
0x1800b730f  call    cs:__imp_SRCacheContext_Close
0x1800b7316  nop     dword ptr [rax+rax+00h]
0x1800b731b  mov     rcx, qword ptr [rbp+3Fh+var_98+8]
0x1800b731f  mov     qword ptr [rbp+3Fh+var_98+8], r12
0x1800b7323  test    rcx, rcx
0x1800b7326  jz      short loc_1800B7334
0x1800b7328  call    cs:__imp_SRCache_Free
0x1800b732f  nop     dword ptr [rax+rax+00h]
0x1800b7334  xor     eax, eax
0x1800b7336  add     rsp, 0D0h
0x1800b733d  pop     r15
0x1800b733f  pop     r14
0x1800b7341  pop     r12
0x1800b7343  pop     rdi
0x1800b7344  pop     rsi
0x1800b7345  pop     rbx
0x1800b7346  pop     rbp
0x1800b7347  retn
0x1800b7349  lea     rcx, [rbp+3Fh+var_80]; this
0x1800b734d  mov     byte ptr [rbx], 1
0x1800b7350  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800b7355  jmp     short loc_1800B7300
0x1800b7357  mov     edx, 392h
0x1800b735c  jmp     short loc_1800B7363
0x1800b735e  mov     edx, 389h; void *
0x1800b7363  mov     rcx, [rbp+47h]; this
0x1800b7367  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b736e  mov     r9d, edi; char *
0x1800b7371  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b7376  lea     rcx, [rbp+3Fh+var_80]; this
0x1800b737a  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800b737f  jmp     loc_1800B7218
```
