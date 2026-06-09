# StateRepository::Cache::Entity::Protocol_NoThrow::GetByUserAndApplicationUserModelIdAndName(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,ushort const *,StateRepository::Cache::Entity::Protocol_NoThrow::CacheFlags,StateRepository::Cache::Entity::Protocol_NoThrow &,bool &)

- ea: `0x1800b738c`
- end: `0x1800b760c`
- name: `?GetByUserAndApplicationUserModelIdAndName@Protocol_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBG2W4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800ba360`

## callees

- `0x18000ff24`
- `0x18003cccc`
- `0x1800b3980`
- `0x1800b5828`
- `0x1800b5c70`
- `0x1800b738c`
- `0x1800bce5c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b74b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b7597`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b74b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b7597`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b742f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b75b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b742f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b75b0`

## string_xrefs

- `0x1800b73bc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800b740e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800b7474`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800b7491`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800b75ef`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Protocol_NoThrow::GetByUserAndApplicationUserModelIdAndName(
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
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
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
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
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
  v13 = StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::OpenByName(
          (StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow *)&v22,
          a1,
          a4);
  v11 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x335,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v13,
      (int)v25);
    v14 = 898;
    goto LABEL_11;
  }
  v11 = StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::Get(&v22, (a5 | 1) & -(__int64)(a5 != 0), a6, a7);
  if ( v11 < 0 )
  {
    v14 = 900;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
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
    v11 = StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::Get(
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
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
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
0x1800b738c  push    rbp
0x1800b738e  push    rbx
0x1800b738f  push    rsi
0x1800b7390  push    rdi
0x1800b7391  push    r12
0x1800b7393  push    r14
0x1800b7395  push    r15
0x1800b7397  lea     rbp, [rsp-0Fh]
0x1800b739c  sub     rsp, 0D0h
0x1800b73a3  mov     rbx, qword ptr [rbp+3Fh+arg_30]
0x1800b73a7  xor     r12d, r12d
0x1800b73aa  mov     rsi, r9
0x1800b73ad  mov     r14, rcx
0x1800b73b0  mov     [rbx], r12b
0x1800b73b3  test    rdx, rdx
0x1800b73b6  jnz     short loc_1800B73DC
0x1800b73b8  mov     rcx, [rbp+47h]; this
0x1800b73bc  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b73c3  mov     ebx, 80070057h
0x1800b73c8  mov     edx, 378h; void *
0x1800b73cd  mov     r9d, ebx; char *
0x1800b73d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b73d5  mov     eax, ebx
0x1800b73d7  jmp     loc_1800B75BE
0x1800b73dc  xorps   xmm0, xmm0
0x1800b73df  mov     [rsp+100h+var_D8], rbx
0x1800b73e4  xorps   xmm1, xmm1
0x1800b73e7  lea     rax, [rbp+3Fh+var_B8]
0x1800b73eb  movdqu  xmmword ptr [rbp+3Fh+var_B8], xmm0
0x1800b73f0  mov     qword ptr [rsp+100h+var_E0], rax; int
0x1800b73f5  movdqu  [rbp+3Fh+var_A8], xmm1
0x1800b73fa  movdqu  [rbp+3Fh+var_98], xmm0
0x1800b73ff  call    ?GetByUserAndApplicationUserModelId@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)
0x1800b7404  mov     edi, eax
0x1800b7406  test    eax, eax
0x1800b7408  jns     short loc_1800B7442
0x1800b740a  mov     rcx, [rbp+47h]; this
0x1800b740e  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b7415  mov     r9d, eax; char *
0x1800b7418  mov     edx, 37Dh; void *
0x1800b741d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b7422  mov     rcx, qword ptr [rbp+3Fh+var_98+8]
0x1800b7426  mov     qword ptr [rbp+3Fh+var_98+8], r12
0x1800b742a  test    rcx, rcx
0x1800b742d  jz      short loc_1800B743B
0x1800b742f  call    cs:__imp_SRCache_Free
0x1800b7436  nop     dword ptr [rax+rax+00h]
0x1800b743b  mov     eax, edi
0x1800b743d  jmp     loc_1800B75BE
0x1800b7442  cmp     [rbx], r12b
0x1800b7445  jz      loc_1800B75A3
0x1800b744b  mov     r8, rsi; unsigned __int16 *
0x1800b744e  mov     [rsp+100h+var_D0], r12
0x1800b7453  mov     rdx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x1800b7456  mov     [rsp+100h+var_C8], r12d
0x1800b745b  lea     rcx, [rsp+100h+var_D0]; this
0x1800b7460  mov     [rsp+100h+var_C0], r12
0x1800b7465  call    ?OpenByName@ProtocolIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z; StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::OpenByName(StateRepository::Cache::Manager_NoThrow &,ushort const *)
0x1800b746a  mov     edi, eax
0x1800b746c  test    eax, eax
0x1800b746e  jns     short loc_1800B74C4
0x1800b7470  mov     rcx, [rbp+47h]; this
0x1800b7474  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b747b  mov     r9d, eax; char *
0x1800b747e  mov     edx, 335h; void *
0x1800b7483  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b7488  mov     edx, 382h; void *
0x1800b748d  mov     rcx, [rbp+47h]; this
0x1800b7491  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b7498  mov     r9d, edi; char *
0x1800b749b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b74a0  mov     rcx, [rsp+100h+var_D0]
0x1800b74a5  mov     [rsp+100h+var_D0], r12
0x1800b74aa  test    rcx, rcx
0x1800b74ad  jz      loc_1800B7422
0x1800b74b3  call    cs:__imp_SRCacheContext_Close
0x1800b74ba  nop     dword ptr [rax+rax+00h]
0x1800b74bf  jmp     loc_1800B7422
0x1800b74c4  mov     rax, [rbp+3Fh+arg_20]
0x1800b74c8  mov     r9, rbx
0x1800b74cb  mov     r15, [rbp+3Fh+arg_28]
0x1800b74cf  mov     rcx, rax
0x1800b74d2  or      rcx, 1
0x1800b74d6  mov     r8, r15
0x1800b74d9  neg     rax
0x1800b74dc  sbb     rsi, rsi
0x1800b74df  and     rsi, rcx
0x1800b74e2  lea     rcx, [rsp+100h+var_D0]
0x1800b74e7  mov     rdx, rsi
0x1800b74ea  call    ?Get@ProtocolIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Protocol_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Protocol_NoThrow::CacheFlags,StateRepository::Cache::Entity::Protocol_NoThrow &,bool &)
0x1800b74ef  mov     edi, eax
0x1800b74f1  test    eax, eax
0x1800b74f3  jns     loc_1800B757F
0x1800b74f9  mov     edx, 384h
0x1800b74fe  jmp     short loc_1800B748D
0x1800b7500  mov     rdx, [r15+8]
0x1800b7504  lea     r9, [rbp+3Fh+var_80]
0x1800b7508  xorps   xmm0, xmm0
0x1800b750b  mov     [rbp+3Fh+var_70], r12
0x1800b750f  xorps   xmm1, xmm1
0x1800b7512  movdqa  [rbp+3Fh+var_80], xmm0
0x1800b7517  mov     r8d, 1
0x1800b751d  movdqa  [rbp+3Fh+var_60], xmm0
0x1800b7522  mov     rcx, r14
0x1800b7525  movdqa  [rbp+3Fh+var_50], xmm1
0x1800b752a  mov     [rbp+3Fh+var_68], r12
0x1800b752e  mov     [rbp+3Fh+var_40], r12
0x1800b7532  mov     [rbp+3Fh+var_38], r12d
0x1800b7536  mov     qword ptr [rsp+100h+var_E0], rbx; int
0x1800b753b  call    ?Get@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1800b7540  mov     edi, eax
0x1800b7542  test    eax, eax
0x1800b7544  js      loc_1800B75E6
0x1800b754a  cmp     [rbx], r12b
0x1800b754d  jz      short loc_1800B7559
0x1800b754f  mov     rax, qword ptr [rbp+3Fh+var_A8+8]
0x1800b7553  cmp     qword ptr [rbp+3Fh+var_80+8], rax
0x1800b7557  jz      short loc_1800B75D1
0x1800b7559  inc     [rsp+100h+var_C8]
0x1800b755d  lea     rcx, [rsp+100h+var_D0]
0x1800b7562  mov     r9, rbx
0x1800b7565  mov     r8, r15
0x1800b7568  mov     rdx, rsi
0x1800b756b  call    ?Get@ProtocolIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Protocol_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Protocol_NoThrow::CacheFlags,StateRepository::Cache::Entity::Protocol_NoThrow &,bool &)
0x1800b7570  mov     edi, eax
0x1800b7572  test    eax, eax
0x1800b7574  js      short loc_1800B75DF
0x1800b7576  lea     rcx, [rbp+3Fh+var_80]; this
0x1800b757a  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800b757f  cmp     [rbx], r12b
0x1800b7582  jnz     loc_1800B7500
0x1800b7588  mov     rcx, [rsp+100h+var_D0]
0x1800b758d  mov     [rsp+100h+var_D0], r12
0x1800b7592  test    rcx, rcx
0x1800b7595  jz      short loc_1800B75A3
0x1800b7597  call    cs:__imp_SRCacheContext_Close
0x1800b759e  nop     dword ptr [rax+rax+00h]
0x1800b75a3  mov     rcx, qword ptr [rbp+3Fh+var_98+8]
0x1800b75a7  mov     qword ptr [rbp+3Fh+var_98+8], r12
0x1800b75ab  test    rcx, rcx
0x1800b75ae  jz      short loc_1800B75BC
0x1800b75b0  call    cs:__imp_SRCache_Free
0x1800b75b7  nop     dword ptr [rax+rax+00h]
0x1800b75bc  xor     eax, eax
0x1800b75be  add     rsp, 0D0h
0x1800b75c5  pop     r15
0x1800b75c7  pop     r14
0x1800b75c9  pop     r12
0x1800b75cb  pop     rdi
0x1800b75cc  pop     rsi
0x1800b75cd  pop     rbx
0x1800b75ce  pop     rbp
0x1800b75cf  retn
0x1800b75d1  lea     rcx, [rbp+3Fh+var_80]; this
0x1800b75d5  mov     byte ptr [rbx], 1
0x1800b75d8  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800b75dd  jmp     short loc_1800B7588
0x1800b75df  mov     edx, 392h
0x1800b75e4  jmp     short loc_1800B75EB
0x1800b75e6  mov     edx, 389h; void *
0x1800b75eb  mov     rcx, [rbp+47h]; this
0x1800b75ef  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b75f6  mov     r9d, edi; char *
0x1800b75f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b75fe  lea     rcx, [rbp+3Fh+var_80]; this
0x1800b7602  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800b7607  jmp     loc_1800B74A0
```
