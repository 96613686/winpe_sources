# CDBSession::~CDBSession(void)

- ea: `0x10015dc0`
- end: `0x1001602c`
- name: `??1CDBSession@@QAE@XZ`
- size: `620`
- prototype: `void __usercall(CDBSession *__hidden this@<ecx>)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x10016be0`
- `0x1001a7b0`
- `0x1001a970`
- `0x1001b4a0`

## callees

- `0x1000bb00`
- `0x10015dc0`
- `0x10016f60`
- `0x10017690`
- `0x1001c6d0`
- `0x10020410`
- `0x10049580`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x10015ff5`
- `KERNEL32!DeleteCriticalSection` at `0x10015ff5`
- `KERNEL32!LeaveCriticalSection` at `0x10015f32`
- `KERNEL32!LeaveCriticalSection` at `0x10015f32`
- `KERNEL32!EnterCriticalSection` at `0x10015f15`
- `KERNEL32!EnterCriticalSection` at `0x10015f15`
- `msjet40!__imp__JetCloseDatabase@12` at `0x10015fa8`
- `msjet40!__imp__JetCloseDatabase@12` at `0x10015fa8`
- `msjet40!__imp__JetEndSession@8` at `0x10015fb9`
- `msjet40!__imp__JetEndSession@8` at `0x10015fb9`
- `msjet40!__imp__JetRollback@8` at `0x10015f4f`
- `msjet40!__imp__JetRollback@8` at `0x10015f4f`

## pseudocode

```c
void __thiscall CDBSession::~CDBSession(CDBSession *this)
{
  _DWORD *v2; // eax
  int v3; // ebx
  _DWORD *v4; // eax
  _DWORD *v5; // eax
  _DWORD *v6; // eax
  _DWORD *v7; // eax
  _DWORD *v8; // eax
  _DWORD *v9; // eax
  _DWORD *v10; // eax
  _DWORD *v11; // eax
  _DWORD *v12; // eax
  _DWORD *v13; // eax
  _DWORD *v14; // eax
  _DWORD *v15; // eax
  int v16; // eax
  int v17; // esi
  int v18; // eax
  CTransactionState *v19; // ecx
  JET_DBID v20; // eax
  JET_SESID v21; // eax
  int v22; // ecx
  int v23; // ecx
  void *v24; // [esp-4h] [ebp-24h]
  void *v25; // [esp-4h] [ebp-24h]
  void *v26; // [esp-4h] [ebp-24h]
  void *v27; // [esp-4h] [ebp-24h]
  void *v28; // [esp-4h] [ebp-24h]
  void *v29; // [esp-4h] [ebp-24h]
  void *v30; // [esp-4h] [ebp-24h]
  void *v31; // [esp-4h] [ebp-24h]
  void *v32; // [esp-4h] [ebp-24h]
  void *v33; // [esp-4h] [ebp-24h]
  void *v34; // [esp-4h] [ebp-24h]
  void *v35; // [esp-4h] [ebp-24h]
  CExtBuffer *v36; // [esp+0h] [ebp-20h]
  unsigned int v37; // [esp+4h] [ebp-1Ch]

  v2 = (_DWORD *)*((_DWORD *)this + 8);
  v3 = 0;
  *(_DWORD *)this = &CDBSession::`vftable';
  if ( v2 )
  {
    *v2 = &CImpIDBCreateCommand::`vftable';
    operator delete(v2);
  }
  v4 = (_DWORD *)*((_DWORD *)this + 10);
  if ( v4 )
  {
    v24 = (void *)*((_DWORD *)this + 10);
    *v4 = &CImpIOpenRowset::`vftable';
    operator delete(v24);
  }
  v5 = (_DWORD *)*((_DWORD *)this + 11);
  if ( v5 )
  {
    v25 = (void *)*((_DWORD *)this + 11);
    *v5 = &CImpITableDef::`vftable';
    operator delete(v25);
  }
  v6 = (_DWORD *)*((_DWORD *)this + 12);
  if ( v6 )
  {
    v26 = (void *)*((_DWORD *)this + 12);
    *v6 = &CImpIIndexDef::`vftable';
    operator delete(v26);
  }
  v7 = (_DWORD *)*((_DWORD *)this + 9);
  if ( v7 )
  {
    v27 = (void *)*((_DWORD *)this + 9);
    *v7 = &CImpIDBSchemaRowset::`vftable';
    operator delete(v27);
  }
  v8 = (_DWORD *)*((_DWORD *)this + 15);
  if ( v8 )
  {
    v28 = (void *)*((_DWORD *)this + 15);
    *v8 = &CImpITransactionLocal::`vftable';
    operator delete(v28);
  }
  v9 = (_DWORD *)*((_DWORD *)this + 13);
  if ( v9 )
  {
    v29 = (void *)*((_DWORD *)this + 13);
    *v9 = &CImpIGetDataSource::`vftable';
    operator delete(v29);
  }
  v10 = (_DWORD *)*((_DWORD *)this + 14);
  if ( v10 )
  {
    v30 = (void *)*((_DWORD *)this + 14);
    *v10 = &CImpISessionProperties::`vftable';
    operator delete(v30);
  }
  v11 = (_DWORD *)*((_DWORD *)this + 16);
  if ( v11 )
  {
    v31 = (void *)*((_DWORD *)this + 16);
    *v11 = &CImpIDBUserAttributes::`vftable';
    operator delete(v31);
  }
  v12 = (_DWORD *)*((_DWORD *)this + 17);
  if ( v12 )
  {
    v32 = (void *)*((_DWORD *)this + 17);
    *v12 = &CImpIAlterTable::`vftable';
    operator delete(v32);
  }
  v13 = (_DWORD *)*((_DWORD *)this + 18);
  if ( v13 )
  {
    v33 = (void *)*((_DWORD *)this + 18);
    *v13 = &CImpIAlterIndex::`vftable';
    operator delete(v33);
  }
  v14 = (_DWORD *)*((_DWORD *)this + 19);
  if ( v14 )
  {
    v34 = (void *)*((_DWORD *)this + 19);
    *v14 = &CImpIReplication::`vftable';
    operator delete(v34);
  }
  v15 = (_DWORD *)*((_DWORD *)this + 20);
  if ( v15 )
  {
    v35 = (void *)*((_DWORD *)this + 20);
    *v15 = &CImpIIdle::`vftable';
    operator delete(v35);
  }
  EnterCriticalSection(&g_CriticalSection);
  if ( g_pSessionList )
    CExtBuffer::DeleteFromExtBuffer(v36, v37);
  LeaveCriticalSection(&g_CriticalSection);
  if ( !*((_DWORD *)this + 38) )
  {
    v16 = *((_DWORD *)this + 22);
    if ( v16 )
    {
      v3 = *(_DWORD *)(v16 + 8);
      JetRollback(*((_DWORD *)this + 4), 1u);
    }
    v17 = *((_DWORD *)this + 22);
    if ( v17 )
    {
      while ( 1 )
      {
        v18 = v3;
        _InterlockedDecrement((volatile signed __int32 *)v17);
        if ( !*(_DWORD *)v17 )
        {
          v19 = *(CTransactionState **)(v17 + 8);
          if ( v19 )
            CTransactionState::Release(v19);
          operator delete((void *)v17);
          v18 = v3;
        }
        *((_DWORD *)this + 22) = v3;
        if ( !v3 )
          break;
        v3 = *(_DWORD *)(v3 + 8);
        v17 = v18;
      }
    }
    CDBSession::CleanupJetTableIdsNotReallyClosedInTransactions(this);
    v20 = *((_DWORD *)this + 5);
    if ( v20 != -1 )
      JetCloseDatabase(*((_DWORD *)this + 4), v20, 0);
    v21 = *((_DWORD *)this + 4);
    if ( v21 != -1 )
      JetEndSession(v21, 1u);
  }
  _InterlockedDecrement((volatile signed __int32 *)(*((_DWORD *)this + 21) + 124));
  v22 = *((_DWORD *)this + 21);
  if ( v22 )
  {
    v23 = *(_DWORD *)(v22 + 8);
    if ( v23 )
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v23 + 8))(*(_DWORD *)(*(_DWORD *)v23 + 8), v23);
  }
  CSettableProperties::~CSettableProperties((CDBSession *)((char *)this + 136));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  CLVParamArray::Clear((CDBSession *)((char *)this + 92));
  if ( *((_DWORD *)this + 23) )
  {
    operator delete(*((void **)this + 23));
    *((_DWORD *)this + 23) = 0;
  }
}

```

## disassembly

```asm
0x10015dc0  mov     edi, edi
0x10015dc2  push    ebp
0x10015dc3  mov     ebp, esp
0x10015dc5  push    0FFFFFFFFh
0x10015dc7  push    offset ??1CDBSession@@QAE@XZ_SEH
0x10015dcc  mov     eax, large fs:0
0x10015dd2  push    eax
0x10015dd3  push    ecx
0x10015dd4  push    ebx
0x10015dd5  push    esi
0x10015dd6  push    edi; unsigned int
0x10015dd7  mov     eax, ___security_cookie
0x10015ddc  xor     eax, ebp
0x10015dde  push    eax; this
0x10015ddf  lea     eax, [ebp+var_C]
0x10015de2  mov     large fs:0, eax
0x10015de8  mov     edi, ecx
0x10015dea  mov     eax, [edi+20h]
0x10015ded  xor     ebx, ebx
0x10015def  mov     dword ptr [edi], offset ??_7CDBSession@@6B@; const CDBSession::`vftable'
0x10015df5  test    eax, eax
0x10015df7  jz      short loc_10015E08
0x10015df9  push    eax; Block
0x10015dfa  mov     dword ptr [eax], offset ??_7CImpIDBCreateCommand@@6B@; const CImpIDBCreateCommand::`vftable'
0x10015e00  call    ??3@YAXPAX@Z; operator delete(void *)
0x10015e05  add     esp, 4
0x10015e08  mov     eax, [edi+28h]
0x10015e0b  test    eax, eax
0x10015e0d  jz      short loc_10015E1E
0x10015e0f  push    eax; Block
0x10015e10  mov     dword ptr [eax], offset ??_7CImpIOpenRowset@@6B@; const CImpIOpenRowset::`vftable'
0x10015e16  call    ??3@YAXPAX@Z; operator delete(void *)
0x10015e1b  add     esp, 4
0x10015e1e  mov     eax, [edi+2Ch]
0x10015e21  test    eax, eax
0x10015e23  jz      short loc_10015E34
0x10015e25  push    eax; Block
0x10015e26  mov     dword ptr [eax], offset ??_7CImpITableDef@@6B@; const CImpITableDef::`vftable'
0x10015e2c  call    ??3@YAXPAX@Z; operator delete(void *)
0x10015e31  add     esp, 4
0x10015e34  mov     eax, [edi+30h]
0x10015e37  test    eax, eax
0x10015e39  jz      short loc_10015E4A
0x10015e3b  push    eax; Block
0x10015e3c  mov     dword ptr [eax], offset ??_7CImpIIndexDef@@6B@; const CImpIIndexDef::`vftable'
0x10015e42  call    ??3@YAXPAX@Z; operator delete(void *)
0x10015e47  add     esp, 4
0x10015e4a  mov     eax, [edi+24h]
0x10015e4d  test    eax, eax
0x10015e4f  jz      short loc_10015E60
0x10015e51  push    eax; Block
0x10015e52  mov     dword ptr [eax], offset ??_7CImpIDBSchemaRowset@@6B@; const CImpIDBSchemaRowset::`vftable'
0x10015e58  call    ??3@YAXPAX@Z; operator delete(void *)
0x10015e5d  add     esp, 4
0x10015e60  mov     eax, [edi+3Ch]
0x10015e63  test    eax, eax
0x10015e65  jz      short loc_10015E76
0x10015e67  push    eax; Block
0x10015e68  mov     dword ptr [eax], offset ??_7CImpITransactionLocal@@6B@; const CImpITransactionLocal::`vftable'
0x10015e6e  call    ??3@YAXPAX@Z; operator delete(void *)
0x10015e73  add     esp, 4
0x10015e76  mov     eax, [edi+34h]
0x10015e79  test    eax, eax
0x10015e7b  jz      short loc_10015E8C
0x10015e7d  push    eax; Block
0x10015e7e  mov     dword ptr [eax], offset ??_7CImpIGetDataSource@@6B@; const CImpIGetDataSource::`vftable'
0x10015e84  call    ??3@YAXPAX@Z; operator delete(void *)
0x10015e89  add     esp, 4
0x10015e8c  mov     eax, [edi+38h]
0x10015e8f  test    eax, eax
0x10015e91  jz      short loc_10015EA2
0x10015e93  push    eax; Block
0x10015e94  mov     dword ptr [eax], offset ??_7CImpISessionProperties@@6B@; const CImpISessionProperties::`vftable'
0x10015e9a  call    ??3@YAXPAX@Z; operator delete(void *)
0x10015e9f  add     esp, 4
0x10015ea2  mov     eax, [edi+40h]
0x10015ea5  test    eax, eax
0x10015ea7  jz      short loc_10015EB8
0x10015ea9  push    eax; Block
0x10015eaa  mov     dword ptr [eax], offset ??_7CImpIDBUserAttributes@@6B@; const CImpIDBUserAttributes::`vftable'
0x10015eb0  call    ??3@YAXPAX@Z; operator delete(void *)
0x10015eb5  add     esp, 4
0x10015eb8  mov     eax, [edi+44h]
0x10015ebb  test    eax, eax
0x10015ebd  jz      short loc_10015ECE
0x10015ebf  push    eax; Block
0x10015ec0  mov     dword ptr [eax], offset ??_7CImpIAlterTable@@6B@; const CImpIAlterTable::`vftable'
0x10015ec6  call    ??3@YAXPAX@Z; operator delete(void *)
0x10015ecb  add     esp, 4
0x10015ece  mov     eax, [edi+48h]
0x10015ed1  test    eax, eax
0x10015ed3  jz      short loc_10015EE4
0x10015ed5  push    eax; Block
0x10015ed6  mov     dword ptr [eax], offset ??_7CImpIAlterIndex@@6B@; const CImpIAlterIndex::`vftable'
0x10015edc  call    ??3@YAXPAX@Z; operator delete(void *)
0x10015ee1  add     esp, 4
0x10015ee4  mov     eax, [edi+4Ch]
0x10015ee7  test    eax, eax
0x10015ee9  jz      short loc_10015EFA
0x10015eeb  push    eax; Block
0x10015eec  mov     dword ptr [eax], offset ??_7CImpIReplication@@6B@; const CImpIReplication::`vftable'
0x10015ef2  call    ??3@YAXPAX@Z; operator delete(void *)
0x10015ef7  add     esp, 4
0x10015efa  mov     eax, [edi+50h]
0x10015efd  test    eax, eax
0x10015eff  jz      short loc_10015F10
0x10015f01  push    eax; Block
0x10015f02  mov     dword ptr [eax], offset ??_7CImpIIdle@@6B@; const CImpIIdle::`vftable'
0x10015f08  call    ??3@YAXPAX@Z; operator delete(void *)
0x10015f0d  add     esp, 4
0x10015f10  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x10015f15  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10015f1b  mov     ecx, ?g_pSessionList@@3PAVCExtBuffer@@A; CExtBuffer * g_pSessionList
0x10015f21  test    ecx, ecx
0x10015f23  jz      short loc_10015F2D
0x10015f25  mov     edx, [edi+0Ch]
0x10015f28  call    ?DeleteFromExtBuffer@CExtBuffer@@QAGXK@Z; CExtBuffer::DeleteFromExtBuffer(ulong)
0x10015f2d  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x10015f32  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10015f38  cmp     [edi+98h], ebx
0x10015f3e  jnz     short loc_10015FBF
0x10015f40  mov     eax, [edi+58h]
0x10015f43  test    eax, eax
0x10015f45  jz      short loc_10015F55
0x10015f47  mov     ebx, [eax+8]
0x10015f4a  push    1; grbit
0x10015f4c  push    dword ptr [edi+10h]; sesid
0x10015f4f  call    ds:__imp__JetRollback@8; JetRollback(x,x)
0x10015f55  mov     esi, [edi+58h]
0x10015f58  test    esi, esi
0x10015f5a  jz      short loc_10015F93
0x10015f5c  nop     dword ptr [eax+00h]
0x10015f60  mov     eax, ebx
0x10015f62  mov     [ebp+var_10], eax
0x10015f65  lock dec dword ptr [esi]
0x10015f68  cmp     dword ptr [esi], 0
0x10015f6b  ja      short loc_10015F85
0x10015f6d  mov     ecx, [esi+8]; this
0x10015f70  test    ecx, ecx
0x10015f72  jz      short loc_10015F79
0x10015f74  call    ?Release@CTransactionState@@QAEKXZ; CTransactionState::Release(void)
0x10015f79  push    esi; Block
0x10015f7a  call    ??3@YAXPAX@Z; operator delete(void *)
0x10015f7f  mov     eax, [ebp+var_10]
0x10015f82  add     esp, 4
0x10015f85  mov     [edi+58h], ebx
0x10015f88  test    ebx, ebx
0x10015f8a  jz      short loc_10015F93
0x10015f8c  mov     ebx, [ebx+8]
0x10015f8f  mov     esi, eax
0x10015f91  jmp     short loc_10015F60
0x10015f93  mov     ecx, edi; this
0x10015f95  call    ?CleanupJetTableIdsNotReallyClosedInTransactions@CDBSession@@AAEJXZ; CDBSession::CleanupJetTableIdsNotReallyClosedInTransactions(void)
0x10015f9a  mov     eax, [edi+14h]
0x10015f9d  cmp     eax, 0FFFFFFFFh
0x10015fa0  jz      short loc_10015FAE
0x10015fa2  push    0; grbit
0x10015fa4  push    eax; dbid
0x10015fa5  push    dword ptr [edi+10h]; sesid
0x10015fa8  call    ds:__imp__JetCloseDatabase@12; JetCloseDatabase(x,x,x)
0x10015fae  mov     eax, [edi+10h]
0x10015fb1  cmp     eax, 0FFFFFFFFh
0x10015fb4  jz      short loc_10015FBF
0x10015fb6  push    1; grbit
0x10015fb8  push    eax; sesid
0x10015fb9  call    ds:__imp__JetEndSession@8; JetEndSession(x,x)
0x10015fbf  mov     eax, [edi+54h]
0x10015fc2  add     eax, 7Ch ; '|'
0x10015fc5  lock dec dword ptr [eax]
0x10015fc8  mov     ecx, [edi+54h]
0x10015fcb  test    ecx, ecx
0x10015fcd  jz      short loc_10015FE6
0x10015fcf  mov     ecx, [ecx+8]
0x10015fd2  test    ecx, ecx
0x10015fd4  jz      short loc_10015FE6
0x10015fd6  mov     eax, [ecx]
0x10015fd8  push    ecx
0x10015fd9  mov     esi, [eax+8]
0x10015fdc  mov     ecx, esi
0x10015fde  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10015fe4  call    esi
0x10015fe6  lea     ecx, [edi+88h]; this
0x10015fec  call    ??1CSettableProperties@@UAE@XZ; CSettableProperties::~CSettableProperties(void)
0x10015ff1  lea     eax, [edi+68h]
0x10015ff4  push    eax; lpCriticalSection
0x10015ff5  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10015ffb  lea     ecx, [edi+5Ch]; this
0x10015ffe  call    ?Clear@CLVParamArray@@QAEJXZ; CLVParamArray::Clear(void)
0x10016003  mov     eax, [edi+5Ch]
0x10016006  test    eax, eax
0x10016008  jz      short loc_1001601A
0x1001600a  push    eax; Block
0x1001600b  call    ??3@YAXPAX@Z; operator delete(void *)
0x10016010  add     esp, 4
0x10016013  mov     dword ptr [edi+5Ch], 0
0x1001601a  mov     ecx, [ebp+var_C]
0x1001601d  mov     large fs:0, ecx
0x10016024  pop     ecx
0x10016025  pop     edi
0x10016026  pop     esi
0x10016027  pop     ebx
0x10016028  mov     esp, ebp
0x1001602a  pop     ebp
0x1001602b  retn
0x1004e250  nop
0x1004e251  nop
0x1004e252  mov     edx, [esp-4+arg_4]
0x1004e256  lea     eax, [edx+0Ch]
0x1004e259  mov     ecx, [edx-14h]
0x1004e25c  xor     ecx, eax; StackCookie
0x1004e25e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e263  mov     eax, offset stru_1004F608
0x1004e268  jmp     ___CxxFrameHandler3
```
