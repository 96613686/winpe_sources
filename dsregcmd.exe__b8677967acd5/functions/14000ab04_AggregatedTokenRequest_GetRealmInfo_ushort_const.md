# AggregatedTokenRequest::GetRealmInfo(ushort const *)

- ea: `0x14000ab04`
- end: `0x14000b0b7`
- name: `?GetRealmInfo@AggregatedTokenRequest@@AEAA?AURealmInfo@1@PEBG@Z`
- size: `1459`
- prototype: `__int64 __fastcall(__int64, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x14000b4f4`

## callees

- `0x1400028ac`
- `0x140005458`
- `0x1400054e8`
- `0x140005838`
- `0x140007bf8`
- `0x14000ab04`
- `0x14000b0fc`
- `0x14000caac`
- `0x14000d134`
- `0x1400189f0`
- `0x14002c3e8`
- `0x140030010`

## pseudocode

```c
__int64 __fastcall AggregatedTokenRequest::GetRealmInfo(__int64 a1, __int64 a2, _WORD *a3)
{
  char v6; // di
  __int64 *v7; // r13
  _QWORD *v8; // r12
  __int64 v9; // rdx
  int v10; // eax
  char v12; // bl
  __int64 v13; // rbx
  char v14; // r12
  _QWORD *v15; // rdx
  _QWORD *v16; // rdx
  int v17; // eax
  _QWORD *v18; // rdx
  _QWORD *v19; // rdx
  _QWORD *v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rax
  _QWORD *v23; // rdx
  __int64 v24; // rbx
  _QWORD *v25; // rdx
  _QWORD *v26; // rdx
  __int64 *v27; // rbx
  int v28; // ecx
  int v29; // ecx
  _QWORD *v30; // rdx
  void *v31; // rbx
  _QWORD *v32; // rax
  _QWORD pExceptionObject[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v34; // [rsp+40h] [rbp-20h] BYREF
  void *Block[3]; // [rsp+48h] [rbp-18h] BYREF

  v6 = 1;
  v7 = (__int64 *)(a2 + 8);
  *(_QWORD *)(a2 + 8) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *(_QWORD *)(a2 + 16) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v8 = (_QWORD *)(a2 + 24);
  *(_QWORD *)(a2 + 24) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v9 = *(_QWORD *)(a1 + 8);
  v10 = *(_DWORD *)(v9 + 300);
  if ( v10 == 1 )
  {
    *(_DWORD *)a2 = 1;
    return a2;
  }
  v12 = 0;
  if ( v10 != 2 )
    goto LABEL_28;
  if ( a3 && *a3 )
  {
    v13 = pExceptionObject[0];
    v14 = 0;
LABEL_9:
    if ( !a3 )
      goto LABEL_13;
    if ( !*a3 )
      goto LABEL_13;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v34,
      (__int64 *)(*(_QWORD *)(a1 + 8) + 272LL));
    v6 |= 0x24u;
    if ( !*(_DWORD *)(v34 - 16) )
      goto LABEL_13;
    goto LABEL_12;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    pExceptionObject,
    (__int64 *)(v9 + 280));
  v6 = 19;
  v13 = pExceptionObject[0];
  v14 = 0;
  if ( !*(_DWORD *)(pExceptionObject[0] - 16LL) )
    goto LABEL_9;
LABEL_12:
  v14 = 1;
LABEL_13:
  if ( (v6 & 4) != 0 )
  {
    v6 &= ~4u;
    v15 = (_QWORD *)(v34 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v34 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 8LL))(*v15);
  }
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    v16 = (_QWORD *)(v13 - 24);
    v17 = _InterlockedExchangeAdd((volatile signed __int32 *)(v13 - 24 + 16), 0xFFFFFFFF);
    v12 = 0;
    if ( v17 <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 8LL))(*v16);
  }
  else
  {
    v12 = 0;
  }
  if ( v14 )
  {
    *(_DWORD *)a2 = 2;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v34,
      (__int64 *)(*(_QWORD *)(a1 + 8) + 280LL));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(v7, &v34);
    v18 = (_QWORD *)(v34 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v34 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v34,
      (__int64 *)(*(_QWORD *)(a1 + 8) + 280LL));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (_QWORD *)(a2 + 24),
      &v34);
    v19 = (_QWORD *)(v34 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v34 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v34,
      (__int64 *)(*(_QWORD *)(a1 + 8) + 272LL));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (_QWORD *)(a2 + 16),
      &v34);
    v20 = (_QWORD *)(v34 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v34 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 8LL))(*v20);
    return a2;
  }
  v8 = (_QWORD *)(a2 + 24);
LABEL_28:
  v21 = *(_QWORD *)(a1 + 8);
  if ( *(_DWORD *)(v21 + 300) == 2 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v34,
      (__int64 *)(v21 + 264));
    v6 |= 8u;
    v22 = v34;
    if ( *(_DWORD *)(v34 - 16) )
      v12 = 1;
  }
  else
  {
    v22 = v34;
  }
  if ( (v6 & 8) != 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(v22 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v22 - 24) + 8LL))(*(_QWORD *)(v22 - 24));
  if ( v12 )
  {
    *(_DWORD *)a2 = 2;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v34,
      (__int64 *)(*(_QWORD *)(a1 + 8) + 264LL));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(v7, &v34);
    v23 = (_QWORD *)(v34 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v34 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 8LL))(*v23);
LABEL_54:
    v32 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            Block,
            v7);
    AggregatedTokenRequest::ParseMexToRealmInfo(a1, v32, a2);
    if ( a3 && *a3 )
      goto LABEL_59;
    if ( !*(_DWORD *)(*v8 - 16LL) )
    {
      Exception::Exception((Exception *)Block, -894894046);
      throw (Exception *)Block;
    }
    if ( a3 && *a3 )
    {
LABEL_59:
      if ( !*(_DWORD *)(*(_QWORD *)(a2 + 16) - 16LL) )
      {
        Exception::Exception((Exception *)Block, -894894045);
        throw (Exception *)Block;
      }
    }
    return a2;
  }
  v24 = *(_QWORD *)(a1 + 8);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    pExceptionObject,
    (__int64 *)(v24 + 8));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v34,
    (__int64)a3);
  UserRealm::GetUserRealm((unsigned int)Block, (unsigned int)&v34, a1 + 24, (unsigned int)pExceptionObject, v24);
  v25 = (_QWORD *)(v34 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v34 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 8LL))(*v25);
  v26 = (_QWORD *)(pExceptionObject[0] - 24LL);
  if ( _InterlockedDecrement((volatile signed __int32 *)(pExceptionObject[0] - 24LL + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 8LL))(*v26);
  v27 = (__int64 *)Block[0];
  if ( !Block[0] )
  {
    Exception::Exception((Exception *)pExceptionObject, -894894056);
    throw (Exception *)pExceptionObject;
  }
  v28 = *((_DWORD *)Block[0] + 11);
  if ( !v28 )
  {
    if ( *((_DWORD *)Block[0] + 12) )
    {
      NotImplementedException::NotImplementedException((NotImplementedException *)pExceptionObject, 0);
      throw (NotImplementedException *)pExceptionObject;
    }
    *(_DWORD *)a2 = 2;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      pExceptionObject,
      v27 + 7);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      v7,
      pExceptionObject);
    v30 = (_QWORD *)(pExceptionObject[0] - 24LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(pExceptionObject[0] - 24LL + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v30 + 8LL))(*v30);
    v31 = Block[0];
    if ( Block[0] )
    {
      UserRealm::~UserRealm((UserRealm *)Block[0]);
      operator delete(v31);
    }
    goto LABEL_54;
  }
  v29 = v28 - 1;
  if ( v29 )
  {
    if ( v29 == 1 )
    {
      Exception::Exception((Exception *)pExceptionObject, -894894056);
      throw (Exception *)pExceptionObject;
    }
    Exception::Exception((Exception *)pExceptionObject, -894894055);
    throw (Exception *)pExceptionObject;
  }
  *(_DWORD *)a2 = 1;
  if ( v27 )
  {
    UserRealm::~UserRealm((UserRealm *)v27);
    operator delete(v27);
  }
  return a2;
}

```

## disassembly

```asm
0x14000ab04  mov     [rsp-38h+arg_0], rbx
0x14000ab09  mov     [rsp-38h+arg_8], rdx
0x14000ab0e  push    rbp
0x14000ab0f  push    rsi
0x14000ab10  push    rdi
0x14000ab11  push    r12
0x14000ab13  push    r13
0x14000ab15  push    r14
0x14000ab17  push    r15
0x14000ab19  mov     rbp, rsp
0x14000ab1c  sub     rsp, 60h
0x14000ab20  mov     r14, r8
0x14000ab23  mov     rsi, rdx
0x14000ab26  mov     r15, rcx
0x14000ab29  mov     edi, 1
0x14000ab2e  mov     [rbp+arg_18], edi
0x14000ab31  lea     r13, [rdx+8]
0x14000ab35  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000ab3c  lea     rbx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000ab43  mov     rcx, rbx
0x14000ab46  mov     rax, [rax+18h]
0x14000ab4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab4f  add     rax, 18h
0x14000ab53  mov     [r13+0], rax
0x14000ab57  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000ab5e  mov     rcx, rbx
0x14000ab61  mov     rax, [rax+18h]
0x14000ab65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab6a  add     rax, 18h
0x14000ab6e  mov     [rsi+10h], rax
0x14000ab72  lea     r12, [rsi+18h]
0x14000ab76  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000ab7d  mov     rcx, rbx
0x14000ab80  mov     rax, [rax+18h]
0x14000ab84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab89  add     rax, 18h
0x14000ab8d  mov     [r12], rax
0x14000ab91  mov     [rbp+arg_18], edi
0x14000ab94  mov     rdx, [r15+8]
0x14000ab98  mov     eax, [rdx+12Ch]
0x14000ab9e  cmp     eax, edi
0x14000aba0  jnz     short loc_14000ABBF
0x14000aba2  mov     [rsi], edi
0x14000aba4  mov     rax, rsi
0x14000aba7  mov     rbx, [rsp+60h+arg_0]
0x14000abaf  add     rsp, 60h
0x14000abb3  pop     r15
0x14000abb5  pop     r14
0x14000abb7  pop     r13
0x14000abb9  pop     r12
0x14000abbb  pop     rdi
0x14000abbc  pop     rsi
0x14000abbd  pop     rbp
0x14000abbe  retn
0x14000abbf  xor     ebx, ebx
0x14000abc1  cmp     eax, 2
0x14000abc4  jnz     loc_14000ADA2
0x14000abca  test    r14, r14
0x14000abcd  jz      short loc_14000ABDE
0x14000abcf  cmp     [r14], bx
0x14000abd3  jz      short loc_14000ABDE
0x14000abd5  mov     rbx, [rbp+pExceptionObject]
0x14000abd9  xor     r12d, r12d
0x14000abdc  jmp     short loc_14000AC04
0x14000abde  add     rdx, 118h
0x14000abe5  lea     rcx, [rbp+pExceptionObject]
0x14000abe9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000abee  nop
0x14000abef  mov     edi, 13h
0x14000abf4  mov     [rbp+arg_18], edi
0x14000abf7  mov     rbx, [rbp+pExceptionObject]
0x14000abfb  xor     r12d, r12d
0x14000abfe  cmp     [rbx-10h], r12d
0x14000ac02  jnz     short loc_14000AC33
0x14000ac04  test    r14, r14
0x14000ac07  jz      short loc_14000AC36
0x14000ac09  cmp     [r14], r12w
0x14000ac0d  jz      short loc_14000AC36
0x14000ac0f  mov     rdx, [r15+8]
0x14000ac13  add     rdx, 110h
0x14000ac1a  lea     rcx, [rbp+var_20]
0x14000ac1e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ac23  or      edi, 24h
0x14000ac26  mov     [rbp+arg_18], edi
0x14000ac29  mov     rax, [rbp+var_20]
0x14000ac2d  cmp     [rax-10h], r12d
0x14000ac31  jz      short loc_14000AC36
0x14000ac33  mov     r12b, 1
0x14000ac36  test    dil, 4
0x14000ac3a  jz      short loc_14000AC67
0x14000ac3c  and     edi, 0FFFFFFFBh
0x14000ac3f  mov     [rbp+arg_18], edi
0x14000ac42  mov     rdx, [rbp+var_20]
0x14000ac46  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000ac4a  or      eax, 0FFFFFFFFh
0x14000ac4d  lock xadd [rdx+10h], eax
0x14000ac52  sub     eax, 1
0x14000ac55  jg      short loc_14000AC67
0x14000ac57  mov     rcx, [rdx]
0x14000ac5a  mov     rax, [rcx]
0x14000ac5d  mov     rax, [rax+8]
0x14000ac61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ac66  nop
0x14000ac67  test    dil, 2
0x14000ac6b  jz      short loc_14000AC97
0x14000ac6d  and     edi, 0FFFFFFFDh
0x14000ac70  mov     [rbp+arg_18], edi
0x14000ac73  lea     rdx, [rbx-18h]
0x14000ac77  or      eax, 0FFFFFFFFh
0x14000ac7a  lock xadd [rdx+10h], eax
0x14000ac7f  xor     ebx, ebx
0x14000ac81  sub     eax, 1
0x14000ac84  jg      short loc_14000AC99
0x14000ac86  mov     rcx, [rdx]
0x14000ac89  mov     rax, [rcx]
0x14000ac8c  mov     rax, [rax+8]
0x14000ac90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ac95  jmp     short loc_14000AC99
0x14000ac97  xor     ebx, ebx
0x14000ac99  test    r12b, r12b
0x14000ac9c  jz      loc_14000AD9E
0x14000aca2  mov     dword ptr [rsi], 2
0x14000aca8  mov     rdx, [r15+8]
0x14000acac  mov     r12d, 118h
0x14000acb2  add     rdx, r12
0x14000acb5  lea     rcx, [rbp+var_20]
0x14000acb9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000acbe  or      edi, 40h
0x14000acc1  mov     [rbp+arg_18], edi
0x14000acc4  lea     rdx, [rbp+var_20]
0x14000acc8  mov     rcx, r13
0x14000accb  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000acd0  nop
0x14000acd1  mov     rdx, [rbp+var_20]
0x14000acd5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000acd9  or      r14d, 0FFFFFFFFh
0x14000acdd  mov     eax, r14d
0x14000ace0  lock xadd [rdx+10h], eax
0x14000ace5  add     eax, r14d
0x14000ace8  test    eax, eax
0x14000acea  jg      short loc_14000ACFB
0x14000acec  mov     rcx, [rdx]
0x14000acef  mov     rax, [rcx]
0x14000acf2  mov     rax, [rax+8]
0x14000acf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000acfb  mov     rdx, [r15+8]
0x14000acff  add     rdx, r12
0x14000ad02  lea     rcx, [rbp+var_20]
0x14000ad06  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ad0b  bts     edi, 7
0x14000ad0f  mov     [rbp+arg_18], edi
0x14000ad12  lea     rdx, [rbp+var_20]
0x14000ad16  lea     rcx, [rsi+18h]
0x14000ad1a  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ad1f  nop
0x14000ad20  mov     rdx, [rbp+var_20]
0x14000ad24  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000ad28  mov     eax, r14d
0x14000ad2b  lock xadd [rdx+10h], eax
0x14000ad30  add     eax, r14d
0x14000ad33  test    eax, eax
0x14000ad35  jg      short loc_14000AD46
0x14000ad37  mov     rcx, [rdx]
0x14000ad3a  mov     rax, [rcx]
0x14000ad3d  mov     rax, [rax+8]
0x14000ad41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad46  mov     rdx, [r15+8]
0x14000ad4a  add     rdx, 110h
0x14000ad51  lea     rcx, [rbp+var_20]
0x14000ad55  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ad5a  bts     edi, 8
0x14000ad5e  mov     [rbp+arg_18], edi
0x14000ad61  lea     rdx, [rbp+var_20]
0x14000ad65  lea     rcx, [rsi+10h]
0x14000ad69  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ad6e  nop
0x14000ad6f  mov     rdx, [rbp+var_20]
0x14000ad73  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000ad77  mov     eax, r14d
0x14000ad7a  lock xadd [rdx+10h], eax
0x14000ad7f  add     eax, r14d
0x14000ad82  test    eax, eax
0x14000ad84  jg      loc_14000ABA4
0x14000ad8a  mov     rcx, [rdx]
0x14000ad8d  mov     rax, [rcx]
0x14000ad90  mov     rax, [rax+8]
0x14000ad94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad99  jmp     loc_14000ABA4
0x14000ad9e  lea     r12, [rsi+18h]
0x14000ada2  mov     rdx, [r15+8]
0x14000ada6  cmp     dword ptr [rdx+12Ch], 2
0x14000adad  jnz     short loc_14000ADD5
0x14000adaf  add     rdx, 108h
0x14000adb6  lea     rcx, [rbp+var_20]
0x14000adba  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000adbf  or      edi, 208h
0x14000adc5  mov     [rbp+arg_18], edi
0x14000adc8  mov     rax, [rbp+var_20]
0x14000adcc  cmp     [rax-10h], ebx
0x14000adcf  jz      short loc_14000ADD9
0x14000add1  mov     bl, 1
0x14000add3  jmp     short loc_14000ADD9
0x14000add5  mov     rax, [rbp+var_20]
0x14000add9  test    dil, 8
0x14000addd  jz      short loc_14000AE05
0x14000addf  and     edi, 0FFFFFFF7h
0x14000ade2  mov     [rbp+arg_18], edi
0x14000ade5  lea     rdx, [rax-18h]
0x14000ade9  or      eax, 0FFFFFFFFh
0x14000adec  lock xadd [rdx+10h], eax
0x14000adf1  sub     eax, 1
0x14000adf4  jg      short loc_14000AE05
0x14000adf6  mov     rcx, [rdx]
0x14000adf9  mov     rax, [rcx]
0x14000adfc  mov     rax, [rax+8]
0x14000ae00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae05  test    bl, bl
0x14000ae07  jz      short loc_14000AE64
0x14000ae09  mov     dword ptr [rsi], 2
0x14000ae0f  mov     rdx, [r15+8]
0x14000ae13  add     rdx, 108h
0x14000ae1a  lea     rcx, [rbp+var_20]
0x14000ae1e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ae23  bts     edi, 0Ah
0x14000ae27  mov     [rbp+arg_18], edi
0x14000ae2a  lea     rdx, [rbp+var_20]
0x14000ae2e  mov     rcx, r13
0x14000ae31  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ae36  nop
0x14000ae37  mov     rdx, [rbp+var_20]
0x14000ae3b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000ae3f  or      eax, 0FFFFFFFFh
0x14000ae42  lock xadd [rdx+10h], eax
0x14000ae47  sub     eax, 1
0x14000ae4a  jg      loc_14000AFB9
0x14000ae50  mov     rcx, [rdx]
0x14000ae53  mov     rax, [rcx]
0x14000ae56  mov     rax, [rax+8]
0x14000ae5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae5f  jmp     loc_14000AFB9
0x14000ae64  mov     rbx, [r15+8]
0x14000ae68  lea     rdx, [rbx+8]
0x14000ae6c  lea     rcx, [rbp+pExceptionObject]
0x14000ae70  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ae75  bts     edi, 0Bh
0x14000ae79  mov     [rbp+arg_18], edi
0x14000ae7c  mov     rdx, r14
0x14000ae7f  lea     rcx, [rbp+var_20]
0x14000ae83  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000ae88  nop
0x14000ae89  lea     r8, [r15+18h]
0x14000ae8d  mov     [rsp+60h+var_40], rbx
0x14000ae92  lea     r9, [rbp+pExceptionObject]
0x14000ae96  lea     rdx, [rbp+var_20]
0x14000ae9a  lea     rcx, [rbp+Block]
0x14000ae9e  call    ?GetUserRealm@UserRealm@@SA?AV?$unique_ptr@VUserRealm@@U?$default_delete@VUserRealm@@@std@@@std@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00AEBVAuthenticationContext@@@Z; UserRealm::GetUserRealm(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,AuthenticationContext const &)
0x14000aea3  nop
0x14000aea4  mov     rdx, [rbp+var_20]
0x14000aea8  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000aeac  or      ebx, 0FFFFFFFFh
0x14000aeaf  mov     eax, ebx
0x14000aeb1  lock xadd [rdx+10h], eax
0x14000aeb6  add     eax, ebx
0x14000aeb8  test    eax, eax
0x14000aeba  jg      short loc_14000AECC
0x14000aebc  mov     rcx, [rdx]
0x14000aebf  mov     rax, [rcx]
0x14000aec2  mov     rax, [rax+8]
0x14000aec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aecb  nop
0x14000aecc  mov     rdx, [rbp+pExceptionObject]
0x14000aed0  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000aed4  mov     eax, ebx
0x14000aed6  lock xadd [rdx+10h], eax
0x14000aedb  add     eax, ebx
0x14000aedd  test    eax, eax
0x14000aedf  jg      short loc_14000AEF0
0x14000aee1  mov     rcx, [rdx]
0x14000aee4  mov     rax, [rcx]
0x14000aee7  mov     rax, [rax+8]
0x14000aeeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aef0  mov     rbx, [rbp+Block]
0x14000aef4  xor     edx, edx; unsigned int
0x14000aef6  test    rbx, rbx
0x14000aef9  jz      loc_14000B063
0x14000aeff  mov     ecx, [rbx+2Ch]
0x14000af02  test    ecx, ecx
0x14000af04  jz      short loc_14000AF46
0x14000af06  sub     ecx, 1
0x14000af09  jz      short loc_14000AF1D
0x14000af0b  cmp     ecx, 1
0x14000af0e  lea     rcx, [rbp+pExceptionObject]; this
0x14000af12  jnz     loc_14000B029
0x14000af18  jmp     loc_14000B082
0x14000af1d  mov     dword ptr [rsi], 1
0x14000af23  test    rbx, rbx
0x14000af26  jz      loc_14000ABA4
0x14000af2c  mov     rcx, rbx; this
0x14000af2f  call    ??1UserRealm@@QEAA@XZ; UserRealm::~UserRealm(void)
0x14000af34  mov     edx, 48h ; 'H'
  ... truncated ...
```
