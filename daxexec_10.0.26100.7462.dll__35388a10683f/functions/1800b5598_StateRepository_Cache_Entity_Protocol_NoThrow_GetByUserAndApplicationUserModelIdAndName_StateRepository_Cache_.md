# StateRepository::Cache::Entity::Protocol_NoThrow::GetByUserAndApplicationUserModelIdAndName(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,ushort const *,StateRepository::Cache::Entity::Protocol_NoThrow::CacheFlags,StateRepository::Cache::Entity::Protocol_NoThrow &,bool &)

- ea: `0x1800b5598`
- end: `0x1800b582c`
- name: `?GetByUserAndApplicationUserModelIdAndName@Protocol_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBG2W4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b84ec`

## callees

- `0x18000e234`
- `0x18003b0d4`
- `0x1800b17ac`
- `0x1800b3c14`
- `0x1800b4070`
- `0x1800b5598`
- `0x1800bb060`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b56c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b57a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b56c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b57a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5647`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b57c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b5647`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b57c1`

## string_xrefs

- `0x1800b55d4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800b5626`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800b5688`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800b56a5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800b580f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`

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
0x1800b5598  mov     rax, rsp
0x1800b559b  mov     [rax+8], rbx
0x1800b559f  mov     [rax+10h], rsi
0x1800b55a3  mov     [rax+18h], rdi
0x1800b55a7  mov     [rax+20h], r12
0x1800b55ab  push    rbp
0x1800b55ac  push    r14
0x1800b55ae  push    r15
0x1800b55b0  lea     rbp, [rax-47h]
0x1800b55b4  sub     rsp, 0D0h
0x1800b55bb  mov     rbx, qword ptr [rbp+3Fh+arg_30]
0x1800b55bf  xor     r12d, r12d
0x1800b55c2  mov     rsi, r9
0x1800b55c5  mov     r14, rcx
0x1800b55c8  mov     [rbx], r12b
0x1800b55cb  test    rdx, rdx
0x1800b55ce  jnz     short loc_1800B55F4
0x1800b55d0  mov     rcx, [rbp+47h]; this
0x1800b55d4  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b55db  mov     ebx, 80070057h
0x1800b55e0  mov     edx, 378h; void *
0x1800b55e5  mov     r9d, ebx; char *
0x1800b55e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b55ed  mov     eax, ebx
0x1800b55ef  jmp     loc_1800B57CF
0x1800b55f4  xorps   xmm0, xmm0
0x1800b55f7  mov     [rsp+0E0h+var_B8], rbx
0x1800b55fc  xorps   xmm1, xmm1
0x1800b55ff  lea     rax, [rbp+3Fh+var_98]
0x1800b5603  movdqu  xmmword ptr [rbp+3Fh+var_98], xmm0
0x1800b5608  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800b560d  movdqu  [rbp+3Fh+var_88], xmm1
0x1800b5612  movdqu  [rbp+3Fh+var_78], xmm0
0x1800b5617  call    ?GetByUserAndApplicationUserModelId@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)
0x1800b561c  mov     edi, eax
0x1800b561e  test    eax, eax
0x1800b5620  jns     short loc_1800B565A
0x1800b5622  mov     rcx, [rbp+47h]; this
0x1800b5626  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b562d  mov     r9d, eax; char *
0x1800b5630  mov     edx, 37Dh; void *
0x1800b5635  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b563a  mov     rcx, qword ptr [rbp+3Fh+var_78+8]
0x1800b563e  mov     qword ptr [rbp+3Fh+var_78+8], r12
0x1800b5642  test    rcx, rcx
0x1800b5645  jz      short loc_1800B5653
0x1800b5647  call    cs:__imp_SRCache_Free
0x1800b564e  nop     dword ptr [rax+rax+00h]
0x1800b5653  mov     eax, edi
0x1800b5655  jmp     loc_1800B57CF
0x1800b565a  cmp     [rbx], r12b
0x1800b565d  jz      loc_1800B57B4
0x1800b5663  mov     r8, rsi; unsigned __int16 *
0x1800b5666  mov     [rbp+3Fh+var_B0], r12
0x1800b566a  mov     rdx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x1800b566d  mov     [rbp+3Fh+var_A8], r12d
0x1800b5671  lea     rcx, [rbp+3Fh+var_B0]; this
0x1800b5675  mov     [rbp+3Fh+var_A0], r12
0x1800b5679  call    ?OpenByName@ProtocolIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z; StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::OpenByName(StateRepository::Cache::Manager_NoThrow &,ushort const *)
0x1800b567e  mov     edi, eax
0x1800b5680  test    eax, eax
0x1800b5682  jns     short loc_1800B56D6
0x1800b5684  mov     rcx, [rbp+47h]; this
0x1800b5688  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b568f  mov     r9d, eax; char *
0x1800b5692  mov     edx, 335h; void *
0x1800b5697  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b569c  mov     edx, 382h; void *
0x1800b56a1  mov     rcx, [rbp+47h]; this
0x1800b56a5  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b56ac  mov     r9d, edi; char *
0x1800b56af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b56b4  mov     rcx, [rbp+3Fh+var_B0]
0x1800b56b8  mov     [rbp+3Fh+var_B0], r12
0x1800b56bc  test    rcx, rcx
0x1800b56bf  jz      loc_1800B563A
0x1800b56c5  call    cs:__imp_SRCacheContext_Close
0x1800b56cc  nop     dword ptr [rax+rax+00h]
0x1800b56d1  jmp     loc_1800B563A
0x1800b56d6  mov     rax, [rbp+3Fh+arg_20]
0x1800b56da  mov     r9, rbx
0x1800b56dd  mov     r15, [rbp+3Fh+arg_28]
0x1800b56e1  mov     rcx, rax
0x1800b56e4  or      rcx, 1
0x1800b56e8  mov     r8, r15
0x1800b56eb  neg     rax
0x1800b56ee  sbb     rsi, rsi
0x1800b56f1  and     rsi, rcx
0x1800b56f4  lea     rcx, [rbp+3Fh+var_B0]
0x1800b56f8  mov     rdx, rsi
0x1800b56fb  call    ?Get@ProtocolIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Protocol_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Protocol_NoThrow::CacheFlags,StateRepository::Cache::Entity::Protocol_NoThrow &,bool &)
0x1800b5700  mov     edi, eax
0x1800b5702  test    eax, eax
0x1800b5704  jns     loc_1800B5792
0x1800b570a  mov     edx, 384h
0x1800b570f  jmp     short loc_1800B56A1
0x1800b5711  mov     rdx, [r15+8]
0x1800b5715  lea     r9, [rbp+3Fh+var_60]
0x1800b5719  xorps   xmm0, xmm0
0x1800b571c  mov     [rbp+3Fh+var_50], r12
0x1800b5720  xorps   xmm1, xmm1
0x1800b5723  movdqa  [rbp+3Fh+var_60], xmm0
0x1800b5728  mov     r8d, 1
0x1800b572e  movdqa  [rbp+3Fh+var_40], xmm0
0x1800b5733  mov     rcx, r14
0x1800b5736  movdqa  [rbp+3Fh+var_30], xmm1
0x1800b573b  mov     [rbp+3Fh+var_48], r12
0x1800b573f  mov     [rbp+3Fh+var_20], r12
0x1800b5743  mov     [rbp+3Fh+var_18], r12d
0x1800b5747  mov     qword ptr [rsp+0E0h+var_C0], rbx; int
0x1800b574c  call    ?Get@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1800b5751  mov     edi, eax
0x1800b5753  test    eax, eax
0x1800b5755  js      loc_1800B5806
0x1800b575b  cmp     [rbx], r12b
0x1800b575e  jz      short loc_1800B576E
0x1800b5760  mov     rax, qword ptr [rbp+3Fh+var_88+8]
0x1800b5764  cmp     qword ptr [rbp+3Fh+var_60+8], rax
0x1800b5768  jz      loc_1800B57F1
0x1800b576e  inc     [rbp+3Fh+var_A8]
0x1800b5771  lea     rcx, [rbp+3Fh+var_B0]
0x1800b5775  mov     r9, rbx
0x1800b5778  mov     r8, r15
0x1800b577b  mov     rdx, rsi
0x1800b577e  call    ?Get@ProtocolIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Protocol_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Protocol_NoThrow::CacheFlags,StateRepository::Cache::Entity::Protocol_NoThrow &,bool &)
0x1800b5783  mov     edi, eax
0x1800b5785  test    eax, eax
0x1800b5787  js      short loc_1800B57FF
0x1800b5789  lea     rcx, [rbp+3Fh+var_60]; this
0x1800b578d  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800b5792  cmp     [rbx], r12b
0x1800b5795  jnz     loc_1800B5711
0x1800b579b  mov     rcx, [rbp+3Fh+var_B0]
0x1800b579f  mov     [rbp+3Fh+var_B0], r12
0x1800b57a3  test    rcx, rcx
0x1800b57a6  jz      short loc_1800B57B4
0x1800b57a8  call    cs:__imp_SRCacheContext_Close
0x1800b57af  nop     dword ptr [rax+rax+00h]
0x1800b57b4  mov     rcx, qword ptr [rbp+3Fh+var_78+8]
0x1800b57b8  mov     qword ptr [rbp+3Fh+var_78+8], r12
0x1800b57bc  test    rcx, rcx
0x1800b57bf  jz      short loc_1800B57CD
0x1800b57c1  call    cs:__imp_SRCache_Free
0x1800b57c8  nop     dword ptr [rax+rax+00h]
0x1800b57cd  xor     eax, eax
0x1800b57cf  lea     r11, [rsp+0E0h+var_10]
0x1800b57d7  mov     rbx, [r11+20h]
0x1800b57db  mov     rsi, [r11+28h]
0x1800b57df  mov     rdi, [r11+30h]
0x1800b57e3  mov     r12, [r11+38h]
0x1800b57e7  mov     rsp, r11
0x1800b57ea  pop     r15
0x1800b57ec  pop     r14
0x1800b57ee  pop     rbp
0x1800b57ef  retn
0x1800b57f1  lea     rcx, [rbp+3Fh+var_60]; this
0x1800b57f5  mov     byte ptr [rbx], 1
0x1800b57f8  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800b57fd  jmp     short loc_1800B579B
0x1800b57ff  mov     edx, 392h
0x1800b5804  jmp     short loc_1800B580B
0x1800b5806  mov     edx, 389h; void *
0x1800b580b  mov     rcx, [rbp+47h]; this
0x1800b580f  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b5816  mov     r9d, edi; char *
0x1800b5819  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b581e  lea     rcx, [rbp+3Fh+var_60]; this
0x1800b5822  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800b5827  jmp     loc_1800B56B4
```
