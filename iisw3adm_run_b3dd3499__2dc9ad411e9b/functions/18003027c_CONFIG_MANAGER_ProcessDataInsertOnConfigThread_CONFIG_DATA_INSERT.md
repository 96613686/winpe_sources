# CONFIG_MANAGER::ProcessDataInsertOnConfigThread(CONFIG_DATA_INSERT *)

- ea: `0x18003027c`
- end: `0x18003056f`
- name: `?ProcessDataInsertOnConfigThread@CONFIG_MANAGER@@QEAAJPEAUCONFIG_DATA_INSERT@@@Z`
- size: `755`
- prototype: `__int64 __fastcall(CONFIG_MANAGER *__hidden this, struct CONFIG_DATA_INSERT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c7fc`

## callees

- `0x180001234`
- `0x18002d780`
- `0x18003027c`
- `0x1800306a0`
- `0x180030774`
- `0x18003c40c`
- `0x18004e094`
- `0x180051778`
- `0x18005a76c`
- `0x180062010`

## import_xrefs

- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x180030421`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x180030442`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x180030463`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x180030421`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x180030442`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x180030463`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800302c0`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800302c0`
- `iisutil!PuDbgPrintError` at `0x180030516`
- `iisutil!PuDbgPrintError` at `0x180030516`

## string_xrefs

- `0x18003050b`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x1800304f1`: `Failed to send the changes to the main thread\n`
- `0x1800304ff`: `CONFIG_MANAGER::ProcessDataInsertOnConfigThread`

## pseudocode

```c
__int64 __fastcall CONFIG_MANAGER::ProcessDataInsertOnConfigThread(CONFIG_MANAGER *this, const unsigned __int16 **a2)
{
  __int64 v3; // rcx
  int Key; // eax
  SITE_DATA_OBJECT_APPHOST *v6; // rdi
  int inserted; // ebx
  unsigned int *v8; // rax
  struct APP_POOL_CHANGED_LIST *v9; // rsi
  unsigned int *v10; // r13
  unsigned int v11; // edi
  __int64 v12; // rbx
  void (__fastcall ***v13)(_QWORD); // rcx
  __int64 v14; // r8
  __int64 v15; // rcx
  CLKRHashTable *v16; // rcx
  CLKRHashTable *v17; // rcx
  unsigned int v18; // r12d
  int v19; // eax
  void **v21; // [rsp+30h] [rbp-30h] BYREF
  int v22; // [rsp+38h] [rbp-28h]
  void *v23; // [rsp+40h] [rbp-20h] BYREF
  __int64 v24; // [rsp+48h] [rbp-18h]
  __int64 v25; // [rsp+50h] [rbp-10h]
  SITE_DATA_OBJECT_APPHOST *v26; // [rsp+A0h] [rbp+40h] BYREF
  SITE_DATA_OBJECT_APPHOST *v27; // [rsp+A8h] [rbp+48h]

  v3 = *((_QWORD *)this + 4);
  v21 = &SITE_DATA_OBJECT_KEY::`vftable';
  v22 = *(_DWORD *)a2;
  v26 = 0;
  Key = CLKRHashTable::FindKey(v3 + 8, &v21, &v26);
  v6 = v26;
  v27 = v26;
  if ( Key )
  {
    if ( Key != 2 )
    {
      inserted = -2147467259;
      goto LABEL_28;
    }
    inserted = CONFIG_APPHOST::InsertData(
                 *((CONFIG_APPHOST **)this + 2),
                 (struct CONFIG_DATA_INSERT *)a2,
                 *((struct APP_POOL_DATA_OBJECT_TABLE_DYNAMIC **)this + 3),
                 *((struct SITE_DATA_OBJECT_TABLE_DYNAMIC **)this + 4),
                 *((struct APPLICATION_DATA_OBJECT_TABLE_DYNAMIC **)this + 5));
    if ( inserted < 0 )
      goto LABEL_28;
    DATA_OBJECT_TABLE::PerformSelfValidation(*((DATA_OBJECT_TABLE **)this + 3));
    DATA_OBJECT_TABLE::PerformSelfValidation(*((DATA_OBJECT_TABLE **)this + 4));
    DATA_OBJECT_TABLE::PerformSelfValidation(*((DATA_OBJECT_TABLE **)this + 5));
    inserted = CONFIG_MANAGER::CrossValidateDataObjects(this);
    if ( inserted < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
          2683,
          "CONFIG_MANAGER::ProcessDataInsertOnConfigThread",
          inserted,
          "Failed cross validating data\n");
      goto LABEL_28;
    }
    v8 = (unsigned int *)operator new(0x18u);
    v9 = (struct APP_POOL_CHANGED_LIST *)v8;
    if ( !v8 )
    {
      inserted = -2147024882;
      goto LABEL_28;
    }
    *(_QWORD *)v8 = 0;
    *((_QWORD *)v8 + 1) = 0;
    v8[5] = 0;
    LODWORD(v26) = 0;
    v10 = v8 + 2;
    v8[4] = -1;
    if ( v8[2] )
    {
      v11 = (unsigned int)v26;
      do
      {
        v12 = v11;
        v13 = *(void (__fastcall ****)(_QWORD))(*(_QWORD *)v9 + 8LL * v11);
        (**v13)(v13);
        ++v11;
        *(_QWORD *)(*(_QWORD *)v9 + 8 * v12) = 0;
      }
      while ( v11 < *v10 );
      v6 = v27;
    }
    *v10 = 0;
    *((_DWORD *)v9 + 4) = 2;
    inserted = CONFIG_MANAGER::SendMainThreadInsertChangesDynamic(this, v9, (struct CONFIG_DATA_INSERT *)a2);
    if ( inserted >= 0 )
    {
      v15 = *((_QWORD *)this + 3);
      v24 = 0;
      v23 = &DATA_OBJECT_TABLE::DeletePredicate;
      v25 = 0;
      CLKRHashTable::DeleteIf(
        (CLKRHashTable *)(v15 + 8),
        (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_Pred,
        &v23);
      v16 = (CLKRHashTable *)(*((_QWORD *)this + 4) + 8LL);
      v23 = &DATA_OBJECT_TABLE::DeletePredicate;
      v24 = 0;
      v25 = 0;
      CLKRHashTable::DeleteIf(
        v16,
        (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_Pred,
        &v23);
      v17 = (CLKRHashTable *)(*((_QWORD *)this + 5) + 8LL);
      v23 = &DATA_OBJECT_TABLE::DeletePredicate;
      v24 = 0;
      v25 = 0;
      CLKRHashTable::DeleteIf(
        v17,
        (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_Pred,
        &v23);
      goto LABEL_28;
    }
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v14 = 2706;
LABEL_27:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
        v14,
        "CONFIG_MANAGER::ProcessDataInsertOnConfigThread",
        inserted,
        "Failed to send the changes to the main thread\n");
    }
  }
  else
  {
    v18 = 0;
    if ( *((_DWORD *)a2 + 20) && *((_DWORD *)a2 + 34) )
    {
      PROTOCOL_BINDING_LIST::RemoveAllBindingsIfNeeded(*((PROTOCOL_BINDING_LIST **)v26 + 8), a2[8]);
      v19 = SITE_DATA_OBJECT_APPHOST::AddBinding(v6, a2[8], a2[15]);
      inserted = v19;
      if ( v19 >= 0 )
      {
        *((_DWORD *)v6 + 80) |= 1u;
        _InterlockedIncrement((volatile signed __int32 *)v6 + 3);
        a2[18] = (const unsigned __int16 *)v6;
        v18 = 2;
      }
      else if ( v19 != -2147024713 )
      {
        goto LABEL_28;
      }
    }
    inserted = CONFIG_MANAGER::SendMainThreadEvaluateRequestDynamic(this, a2, v18);
    if ( inserted >= 0 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 3, 0xFFFFFFFF) == 1 && v6 )
        goto LABEL_33;
      return (unsigned int)inserted;
    }
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v14 = 2766;
      goto LABEL_27;
    }
  }
LABEL_28:
  if ( v6 && _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 3, 0xFFFFFFFF) == 1 )
LABEL_33:
    (**(void (__fastcall ***)(SITE_DATA_OBJECT_APPHOST *, __int64))v6)(v6, 1);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18003027c  mov     [rsp-38h+arg_10], rbx
0x180030281  push    rbp
0x180030282  push    rsi
0x180030283  push    rdi
0x180030284  push    r12
0x180030286  push    r13
0x180030288  push    r14
0x18003028a  push    r15
0x18003028c  mov     rbp, rsp
0x18003028f  sub     rsp, 60h
0x180030293  lea     rax, ??_7SITE_DATA_OBJECT_KEY@@6B@; const SITE_DATA_OBJECT_KEY::`vftable'
0x18003029a  mov     r15, rcx
0x18003029d  mov     rcx, [rcx+20h]
0x1800302a1  lea     r8, [rbp+arg_0]
0x1800302a5  mov     [rbp+var_30], rax
0x1800302a9  mov     r14, rdx
0x1800302ac  mov     eax, [rdx]
0x1800302ae  xor     r13d, r13d
0x1800302b1  lea     rdx, [rbp+var_30]
0x1800302b5  mov     [rbp+var_28], eax
0x1800302b8  add     rcx, 8
0x1800302bc  mov     [rbp+arg_0], r13
0x1800302c0  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800302c6  mov     rdi, [rbp+arg_0]
0x1800302ca  mov     [rbp+arg_8], rdi
0x1800302ce  test    eax, eax
0x1800302d0  jz      loc_180030478
0x1800302d6  lea     r12d, [r13+2]
0x1800302da  cmp     eax, r12d
0x1800302dd  jz      short loc_1800302E9
0x1800302df  mov     ebx, 80004005h
0x1800302e4  jmp     loc_18003051C
0x1800302e9  mov     rax, [r15+28h]
0x1800302ed  mov     rdx, r14; struct CONFIG_DATA_INSERT *
0x1800302f0  mov     r9, [r15+20h]; struct SITE_DATA_OBJECT_TABLE_DYNAMIC *
0x1800302f4  mov     r8, [r15+18h]; struct APP_POOL_DATA_OBJECT_TABLE_DYNAMIC *
0x1800302f8  mov     rcx, [r15+10h]; this
0x1800302fc  mov     [rsp+60h+var_40], rax; struct APPLICATION_DATA_OBJECT_TABLE_DYNAMIC *
0x180030301  call    ?InsertData@CONFIG_APPHOST@@QEAAJPEAUCONFIG_DATA_INSERT@@PEAVAPP_POOL_DATA_OBJECT_TABLE_DYNAMIC@@PEAVSITE_DATA_OBJECT_TABLE_DYNAMIC@@PEAVAPPLICATION_DATA_OBJECT_TABLE_DYNAMIC@@@Z; CONFIG_APPHOST::InsertData(CONFIG_DATA_INSERT *,APP_POOL_DATA_OBJECT_TABLE_DYNAMIC *,SITE_DATA_OBJECT_TABLE_DYNAMIC *,APPLICATION_DATA_OBJECT_TABLE_DYNAMIC *)
0x180030306  mov     ebx, eax
0x180030308  test    eax, eax
0x18003030a  js      loc_18003051C
0x180030310  mov     rcx, [r15+18h]; this
0x180030314  call    ?PerformSelfValidation@DATA_OBJECT_TABLE@@QEAAXXZ; DATA_OBJECT_TABLE::PerformSelfValidation(void)
0x180030319  mov     rcx, [r15+20h]; this
0x18003031d  call    ?PerformSelfValidation@DATA_OBJECT_TABLE@@QEAAXXZ; DATA_OBJECT_TABLE::PerformSelfValidation(void)
0x180030322  mov     rcx, [r15+28h]; this
0x180030326  call    ?PerformSelfValidation@DATA_OBJECT_TABLE@@QEAAXXZ; DATA_OBJECT_TABLE::PerformSelfValidation(void)
0x18003032b  mov     rcx, r15; this
0x18003032e  call    ?CrossValidateDataObjects@CONFIG_MANAGER@@AEAAJXZ; CONFIG_MANAGER::CrossValidateDataObjects(void)
0x180030333  mov     ebx, eax
0x180030335  test    eax, eax
0x180030337  jns     short loc_180030358
0x180030339  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180030340  jz      loc_18003051C
0x180030346  lea     rax, aFailedCrossVal_0; "Failed cross validating data\n"
0x18003034d  mov     r8d, 0A7Bh
0x180030353  jmp     loc_1800304F8
0x180030358  mov     ecx, 18h; Size
0x18003035d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030362  mov     rsi, rax
0x180030365  test    rax, rax
0x180030368  jz      loc_18003046E
0x18003036e  mov     [rax], r13
0x180030371  mov     [rax+8], r13
0x180030375  mov     [rax+14h], r13d
0x180030379  mov     dword ptr [rbp+arg_0], r13d
0x18003037d  lea     r13, [rax+8]
0x180030381  mov     dword ptr [rax+10h], 0FFFFFFFFh
0x180030388  cmp     dword ptr [r13+0], 0
0x18003038d  jbe     short loc_1800303BD
0x18003038f  mov     edi, dword ptr [rbp+arg_0]
0x180030392  mov     rax, [rsi]
0x180030395  mov     ebx, edi
0x180030397  mov     rcx, [rax+rbx*8]
0x18003039b  mov     rax, [rcx]
0x18003039e  mov     rax, [rax]
0x1800303a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303a6  mov     rax, [rsi]
0x1800303a9  inc     edi
0x1800303ab  mov     qword ptr [rax+rbx*8], 0
0x1800303b3  cmp     edi, [r13+0]
0x1800303b7  jb      short loc_180030392
0x1800303b9  mov     rdi, [rbp+arg_8]
0x1800303bd  mov     r8, r14; struct CONFIG_DATA_INSERT *
0x1800303c0  mov     dword ptr [r13+0], 0
0x1800303c8  mov     rdx, rsi; struct APP_POOL_CHANGED_LIST *
0x1800303cb  mov     [rsi+10h], r12d
0x1800303cf  mov     rcx, r15; this
0x1800303d2  call    ?SendMainThreadInsertChangesDynamic@CONFIG_MANAGER@@AEAAJPEAVAPP_POOL_CHANGED_LIST@@PEAUCONFIG_DATA_INSERT@@@Z; CONFIG_MANAGER::SendMainThreadInsertChangesDynamic(APP_POOL_CHANGED_LIST *,CONFIG_DATA_INSERT *)
0x1800303d7  xor     r13d, r13d
0x1800303da  mov     ebx, eax
0x1800303dc  test    eax, eax
0x1800303de  jns     short loc_1800303F8
0x1800303e0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800303e7  jz      loc_18003051C
0x1800303ed  mov     r8d, 0A92h
0x1800303f3  jmp     loc_1800304F1
0x1800303f8  mov     rcx, [r15+18h]
0x1800303fc  lea     rsi, ?_Pred@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_CACHE_ENTRY@@PEAVTOKEN_CACHE_KEY@@VCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_Pred(void const *,void *)
0x180030403  lea     r14, ?DeletePredicate@DATA_OBJECT_TABLE@@CA?AW4LK_PREDICATE@@PEAVDATA_OBJECT@@PEAX@Z; DATA_OBJECT_TABLE::DeletePredicate(DATA_OBJECT *,void *)
0x18003040a  mov     [rbp+var_18], r13
0x18003040e  add     rcx, 8
0x180030412  mov     [rbp+var_20], r14
0x180030416  mov     rdx, rsi
0x180030419  mov     [rbp+var_10], r13
0x18003041d  lea     r8, [rbp+var_20]
0x180030421  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x180030427  mov     rcx, [r15+20h]
0x18003042b  lea     r8, [rbp+var_20]
0x18003042f  add     rcx, 8
0x180030433  mov     [rbp+var_20], r14
0x180030437  mov     rdx, rsi
0x18003043a  mov     [rbp+var_18], r13
0x18003043e  mov     [rbp+var_10], r13
0x180030442  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x180030448  mov     rcx, [r15+28h]
0x18003044c  lea     r8, [rbp+var_20]
0x180030450  add     rcx, 8
0x180030454  mov     [rbp+var_20], r14
0x180030458  mov     rdx, rsi
0x18003045b  mov     [rbp+var_18], r13
0x18003045f  mov     [rbp+var_10], r13
0x180030463  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x180030469  jmp     loc_18003051C
0x18003046e  mov     ebx, 8007000Eh
0x180030473  jmp     loc_18003051C
0x180030478  mov     r12d, r13d
0x18003047b  cmp     [r14+50h], r13d
0x18003047f  jz      short loc_1800304CE
0x180030481  cmp     [r14+88h], r13d
0x180030488  jz      short loc_1800304CE
0x18003048a  mov     rdx, [r14+40h]; unsigned __int16 *
0x18003048e  mov     rcx, [rdi+40h]; this
0x180030492  call    ?RemoveAllBindingsIfNeeded@PROTOCOL_BINDING_LIST@@QEAAHPEBG@Z; PROTOCOL_BINDING_LIST::RemoveAllBindingsIfNeeded(ushort const *)
0x180030497  mov     r8, [r14+78h]; unsigned __int16 *
0x18003049b  mov     rcx, rdi; this
0x18003049e  mov     rdx, [r14+40h]; unsigned __int16 *
0x1800304a2  call    ?AddBinding@SITE_DATA_OBJECT_APPHOST@@QEAAJPEBG0@Z; SITE_DATA_OBJECT_APPHOST::AddBinding(ushort const *,ushort const *)
0x1800304a7  mov     ebx, eax
0x1800304a9  test    eax, eax
0x1800304ab  jns     short loc_1800304B6
0x1800304ad  cmp     eax, 800700B7h
0x1800304b2  jnz     short loc_18003051C
0x1800304b4  jmp     short loc_1800304CE
0x1800304b6  or      dword ptr [rdi+140h], 1
0x1800304bd  lock inc dword ptr [rdi+0Ch]
0x1800304c1  mov     [r14+90h], rdi
0x1800304c8  mov     r12d, 2
0x1800304ce  mov     r8d, r12d
0x1800304d1  mov     rdx, r14
0x1800304d4  mov     rcx, r15
0x1800304d7  call    ?SendMainThreadEvaluateRequestDynamic@CONFIG_MANAGER@@AEAAJPEAUCONFIG_DATA_INSERT@@W4WAS_CHANGE_ITEM_INSERT_DATA_PRE_TASK@@@Z; CONFIG_MANAGER::SendMainThreadEvaluateRequestDynamic(CONFIG_DATA_INSERT *,WAS_CHANGE_ITEM_INSERT_DATA_PRE_TASK)
0x1800304dc  mov     ebx, eax
0x1800304de  test    eax, eax
0x1800304e0  jns     short loc_180030530
0x1800304e2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800304e9  jz      short loc_18003051C
0x1800304eb  mov     r8d, 0ACEh
0x1800304f1  lea     rax, aFailedToSendTh_0; "Failed to send the changes to the main "...
0x1800304f8  mov     rcx, cs:g_pDebug
0x1800304ff  lea     r9, aConfigManagerP_0; "CONFIG_MANAGER::ProcessDataInsertOnConf"...
0x180030506  mov     [rsp+60h+var_38], rax
0x18003050b  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180030512  mov     dword ptr [rsp+60h+var_40], ebx
0x180030516  call    cs:__imp_PuDbgPrintError
0x18003051c  test    rdi, rdi
0x18003051f  jz      short loc_180030555
0x180030521  or      eax, 0FFFFFFFFh
0x180030524  lock xadd [rdi+0Ch], eax
0x180030529  cmp     eax, 1
0x18003052c  jnz     short loc_180030555
0x18003052e  jmp     short loc_180030542
0x180030530  or      eax, 0FFFFFFFFh
0x180030533  lock xadd [rdi+0Ch], eax
0x180030538  cmp     eax, 1
0x18003053b  jnz     short loc_180030555
0x18003053d  test    rdi, rdi
0x180030540  jz      short loc_180030555
0x180030542  mov     rax, [rdi]
0x180030545  mov     edx, 1
0x18003054a  mov     rcx, rdi
0x18003054d  mov     rax, [rax]
0x180030550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030555  mov     eax, ebx
0x180030557  mov     rbx, [rsp+60h+arg_10]
0x18003055f  add     rsp, 60h
0x180030563  pop     r15
0x180030565  pop     r14
0x180030567  pop     r13
0x180030569  pop     r12
0x18003056b  pop     rdi
0x18003056c  pop     rsi
0x18003056d  pop     rbp
0x18003056e  retn
```
