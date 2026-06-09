# StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::GetByUserAndApplicationUserModelIdAndFileType(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,ushort const *,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::CacheFlags,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow &,bool &)

- ea: `0x1800b52fc`
- end: `0x1800b5590`
- name: `?GetByUserAndApplicationUserModelIdAndFileType@FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBG2W4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800b6a64`

## callees

- `0x18000e234`
- `0x18003b0d4`
- `0x1800b17ac`
- `0x1800b3c14`
- `0x1800b3d0c`
- `0x1800b52fc`
- `0x1800badc0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5429`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b550c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5429`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b550c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b53ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5525`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b53ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5525`

## string_xrefs

- `0x1800b5338`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800b538a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800b53ec`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800b5409`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800b5573`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`

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
  int v20; // [rsp+28h] [rbp-81h]
  int *v21; // [rsp+28h] [rbp-81h]
  __int64 v22; // [rsp+38h] [rbp-71h] BYREF
  int v23; // [rsp+40h] [rbp-69h]
  __int64 v24; // [rsp+48h] [rbp-61h]
  int v25[4]; // [rsp+50h] [rbp-59h] BYREF
  __int128 v26; // [rsp+60h] [rbp-49h]
  __int128 v27; // [rsp+70h] [rbp-39h]
  __int128 v28; // [rsp+88h] [rbp-21h] BYREF
  __int64 v29; // [rsp+98h] [rbp-11h]
  __int64 v30; // [rsp+A0h] [rbp-9h]
  __int128 v31; // [rsp+A8h] [rbp-1h]
  __int128 v32; // [rsp+B8h] [rbp+Fh]
  __int64 v33; // [rsp+C8h] [rbp+1Fh]
  int v34; // [rsp+D0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+47h]

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
0x1800b52fc  mov     rax, rsp
0x1800b52ff  mov     [rax+8], rbx
0x1800b5303  mov     [rax+10h], rsi
0x1800b5307  mov     [rax+18h], rdi
0x1800b530b  mov     [rax+20h], r12
0x1800b530f  push    rbp
0x1800b5310  push    r14
0x1800b5312  push    r15
0x1800b5314  lea     rbp, [rax-47h]
0x1800b5318  sub     rsp, 0D0h
0x1800b531f  mov     rbx, qword ptr [rbp+3Fh+arg_30]
0x1800b5323  xor     r12d, r12d
0x1800b5326  mov     rsi, r9
0x1800b5329  mov     r14, rcx
0x1800b532c  mov     [rbx], r12b
0x1800b532f  test    rdx, rdx
0x1800b5332  jnz     short loc_1800B5358
0x1800b5334  mov     rcx, [rbp+47h]; this
0x1800b5338  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b533f  mov     ebx, 80070057h
0x1800b5344  mov     edx, 378h; void *
0x1800b5349  mov     r9d, ebx; char *
0x1800b534c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5351  mov     eax, ebx
0x1800b5353  jmp     loc_1800B5533
0x1800b5358  xorps   xmm0, xmm0
0x1800b535b  mov     [rsp+0E0h+var_B8], rbx
0x1800b5360  xorps   xmm1, xmm1
0x1800b5363  lea     rax, [rbp+3Fh+var_98]
0x1800b5367  movdqu  xmmword ptr [rbp+3Fh+var_98], xmm0
0x1800b536c  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800b5371  movdqu  [rbp+3Fh+var_88], xmm1
0x1800b5376  movdqu  [rbp+3Fh+var_78], xmm0
0x1800b537b  call    ?GetByUserAndApplicationUserModelId@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)
0x1800b5380  mov     edi, eax
0x1800b5382  test    eax, eax
0x1800b5384  jns     short loc_1800B53BE
0x1800b5386  mov     rcx, [rbp+47h]; this
0x1800b538a  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b5391  mov     r9d, eax; char *
0x1800b5394  mov     edx, 37Dh; void *
0x1800b5399  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b539e  mov     rcx, qword ptr [rbp+3Fh+var_78+8]
0x1800b53a2  mov     qword ptr [rbp+3Fh+var_78+8], r12
0x1800b53a6  test    rcx, rcx
0x1800b53a9  jz      short loc_1800B53B7
0x1800b53ab  call    cs:__imp_SRCache_Free
0x1800b53b2  nop     dword ptr [rax+rax+00h]
0x1800b53b7  mov     eax, edi
0x1800b53b9  jmp     loc_1800B5533
0x1800b53be  cmp     [rbx], r12b
0x1800b53c1  jz      loc_1800B5518
0x1800b53c7  mov     r8, rsi; unsigned __int16 *
0x1800b53ca  mov     [rbp+3Fh+var_B0], r12
0x1800b53ce  mov     rdx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x1800b53d1  mov     [rbp+3Fh+var_A8], r12d
0x1800b53d5  lea     rcx, [rbp+3Fh+var_B0]; this
0x1800b53d9  mov     [rbp+3Fh+var_A0], r12
0x1800b53dd  call    ?OpenByFileType@FileTypeAssociationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z; StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::OpenByFileType(StateRepository::Cache::Manager_NoThrow &,ushort const *)
0x1800b53e2  mov     edi, eax
0x1800b53e4  test    eax, eax
0x1800b53e6  jns     short loc_1800B543A
0x1800b53e8  mov     rcx, [rbp+47h]; this
0x1800b53ec  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b53f3  mov     r9d, eax; char *
0x1800b53f6  mov     edx, 335h; void *
0x1800b53fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5400  mov     edx, 382h; void *
0x1800b5405  mov     rcx, [rbp+47h]; this
0x1800b5409  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b5410  mov     r9d, edi; char *
0x1800b5413  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5418  mov     rcx, [rbp+3Fh+var_B0]
0x1800b541c  mov     [rbp+3Fh+var_B0], r12
0x1800b5420  test    rcx, rcx
0x1800b5423  jz      loc_1800B539E
0x1800b5429  call    cs:__imp_SRCacheContext_Close
0x1800b5430  nop     dword ptr [rax+rax+00h]
0x1800b5435  jmp     loc_1800B539E
0x1800b543a  mov     rax, [rbp+3Fh+arg_20]
0x1800b543e  mov     r9, rbx
0x1800b5441  mov     r15, [rbp+3Fh+arg_28]
0x1800b5445  mov     rcx, rax
0x1800b5448  or      rcx, 1
0x1800b544c  mov     r8, r15
0x1800b544f  neg     rax
0x1800b5452  sbb     rsi, rsi
0x1800b5455  and     rsi, rcx
0x1800b5458  lea     rcx, [rbp+3Fh+var_B0]
0x1800b545c  mov     rdx, rsi
0x1800b545f  call    ?Get@FileTypeAssociationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@FileTypeAssociation_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::CacheFlags,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow &,bool &)
0x1800b5464  mov     edi, eax
0x1800b5466  test    eax, eax
0x1800b5468  jns     loc_1800B54F6
0x1800b546e  mov     edx, 384h
0x1800b5473  jmp     short loc_1800B5405
0x1800b5475  mov     rdx, [r15+8]
0x1800b5479  lea     r9, [rbp+3Fh+var_60]
0x1800b547d  xorps   xmm0, xmm0
0x1800b5480  mov     [rbp+3Fh+var_50], r12
0x1800b5484  xorps   xmm1, xmm1
0x1800b5487  movdqa  [rbp+3Fh+var_60], xmm0
0x1800b548c  mov     r8d, 1
0x1800b5492  movdqa  [rbp+3Fh+var_40], xmm0
0x1800b5497  mov     rcx, r14
0x1800b549a  movdqa  [rbp+3Fh+var_30], xmm1
0x1800b549f  mov     [rbp+3Fh+var_48], r12
0x1800b54a3  mov     [rbp+3Fh+var_20], r12
0x1800b54a7  mov     [rbp+3Fh+var_18], r12d
0x1800b54ab  mov     qword ptr [rsp+0E0h+var_C0], rbx; int
0x1800b54b0  call    ?Get@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1800b54b5  mov     edi, eax
0x1800b54b7  test    eax, eax
0x1800b54b9  js      loc_1800B556A
0x1800b54bf  cmp     [rbx], r12b
0x1800b54c2  jz      short loc_1800B54D2
0x1800b54c4  mov     rax, qword ptr [rbp+3Fh+var_88+8]
0x1800b54c8  cmp     qword ptr [rbp+3Fh+var_60+8], rax
0x1800b54cc  jz      loc_1800B5555
0x1800b54d2  inc     [rbp+3Fh+var_A8]
0x1800b54d5  lea     rcx, [rbp+3Fh+var_B0]
0x1800b54d9  mov     r9, rbx
0x1800b54dc  mov     r8, r15
0x1800b54df  mov     rdx, rsi
0x1800b54e2  call    ?Get@FileTypeAssociationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@FileTypeAssociation_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::FileTypeAssociationIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::CacheFlags,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow &,bool &)
0x1800b54e7  mov     edi, eax
0x1800b54e9  test    eax, eax
0x1800b54eb  js      short loc_1800B5563
0x1800b54ed  lea     rcx, [rbp+3Fh+var_60]; this
0x1800b54f1  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800b54f6  cmp     [rbx], r12b
0x1800b54f9  jnz     loc_1800B5475
0x1800b54ff  mov     rcx, [rbp+3Fh+var_B0]
0x1800b5503  mov     [rbp+3Fh+var_B0], r12
0x1800b5507  test    rcx, rcx
0x1800b550a  jz      short loc_1800B5518
0x1800b550c  call    cs:__imp_SRCacheContext_Close
0x1800b5513  nop     dword ptr [rax+rax+00h]
0x1800b5518  mov     rcx, qword ptr [rbp+3Fh+var_78+8]
0x1800b551c  mov     qword ptr [rbp+3Fh+var_78+8], r12
0x1800b5520  test    rcx, rcx
0x1800b5523  jz      short loc_1800B5531
0x1800b5525  call    cs:__imp_SRCache_Free
0x1800b552c  nop     dword ptr [rax+rax+00h]
0x1800b5531  xor     eax, eax
0x1800b5533  lea     r11, [rsp+0E0h+var_10]
0x1800b553b  mov     rbx, [r11+20h]
0x1800b553f  mov     rsi, [r11+28h]
0x1800b5543  mov     rdi, [r11+30h]
0x1800b5547  mov     r12, [r11+38h]
0x1800b554b  mov     rsp, r11
0x1800b554e  pop     r15
0x1800b5550  pop     r14
0x1800b5552  pop     rbp
0x1800b5553  retn
0x1800b5555  lea     rcx, [rbp+3Fh+var_60]; this
0x1800b5559  mov     byte ptr [rbx], 1
0x1800b555c  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800b5561  jmp     short loc_1800B54FF
0x1800b5563  mov     edx, 392h
0x1800b5568  jmp     short loc_1800B556F
0x1800b556a  mov     edx, 389h; void *
0x1800b556f  mov     rcx, [rbp+47h]; this
0x1800b5573  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b557a  mov     r9d, edi; char *
0x1800b557d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5582  lea     rcx, [rbp+3Fh+var_60]; this
0x1800b5586  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800b558b  jmp     loc_1800B5418
```
