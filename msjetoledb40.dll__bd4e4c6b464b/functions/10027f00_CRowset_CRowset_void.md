# CRowset::~CRowset(void)

- ea: `0x10027f00`
- end: `0x10028329`
- name: `??1CRowset@@UAE@XZ`
- size: `1065`
- prototype: `void __thiscall(CRowset *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x10027ed0`
- `0x10034dd0`

## callees

- `0x1000bcf0`
- `0x10016e10`
- `0x1001c6d0`
- `0x10020410`
- `0x10027f00`
- `0x10049580`
- `0x100495b0`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `msvcrt!free` at `0x10028159`
- `msvcrt!free` at `0x10028288`
- `msvcrt!free` at `0x100282a9`
- `msvcrt!free` at `0x100282ba`
- `msvcrt!free` at `0x10028159`
- `msvcrt!free` at `0x10028288`
- `msvcrt!free` at `0x100282a9`
- `msvcrt!free` at `0x100282ba`
- `KERNEL32!DeleteCriticalSection` at `0x100282c7`
- `KERNEL32!DeleteCriticalSection` at `0x100282de`
- `KERNEL32!DeleteCriticalSection` at `0x1002830b`
- `KERNEL32!DeleteCriticalSection` at `0x100282c7`
- `KERNEL32!DeleteCriticalSection` at `0x100282de`
- `KERNEL32!DeleteCriticalSection` at `0x1002830b`
- `KERNEL32!LeaveCriticalSection` at `0x10027ff4`
- `KERNEL32!LeaveCriticalSection` at `0x1002820f`
- `KERNEL32!LeaveCriticalSection` at `0x100282f6`
- `KERNEL32!LeaveCriticalSection` at `0x10027ff4`
- `KERNEL32!LeaveCriticalSection` at `0x1002820f`
- `KERNEL32!LeaveCriticalSection` at `0x100282f6`
- `KERNEL32!EnterCriticalSection` at `0x10027fe5`
- `KERNEL32!EnterCriticalSection` at `0x100281fa`
- `KERNEL32!EnterCriticalSection` at `0x10027fe5`
- `KERNEL32!EnterCriticalSection` at `0x100281fa`
- `msjet40!__imp__JetCloseTable@8` at `0x10027f9c`
- `msjet40!__imp__JetCloseTable@8` at `0x10027fc1`
- `msjet40!__imp__JetCloseTable@8` at `0x10027f9c`
- `msjet40!__imp__JetCloseTable@8` at `0x10027fc1`

## pseudocode

```c
void __thiscall CRowset::~CRowset(CRowset *this)
{
  CRowset *v1; // ebx
  _DWORD *v2; // edi
  int v3; // eax
  _DWORD *v4; // eax
  CTransactionState *v5; // ecx
  int isZombie; // eax
  unsigned int v7; // esi
  unsigned int v8; // esi
  int v9; // edi
  int v10; // ecx
  int v11; // ecx
  int v12; // edi
  int v13; // eax
  int v14; // esi
  CTransactionState *v15; // ecx
  void *v16; // esi
  _DWORD *v17; // eax
  _DWORD *v18; // eax
  _DWORD *v19; // eax
  _DWORD *v20; // eax
  _DWORD *v21; // eax
  _DWORD *v22; // eax
  _DWORD *v23; // eax
  _DWORD *v24; // eax
  void **v25; // esi
  int v26; // eax
  int v27; // edi
  _DWORD *v28; // edi
  struct _RTL_CRITICAL_SECTION *v29; // esi
  char *v30; // edi
  bool v31; // zf
  unsigned int v32; // ebx
  int v33; // ecx
  void **v34; // eax
  void *v35; // [esp-4h] [ebp-30h]
  void *v36; // [esp-4h] [ebp-30h]
  void *v37; // [esp-4h] [ebp-30h]
  void *v38; // [esp-4h] [ebp-30h]
  void *v39; // [esp-4h] [ebp-30h]
  void *v40; // [esp-4h] [ebp-30h]
  void *v41; // [esp-4h] [ebp-30h]
  void *v42; // [esp-4h] [ebp-30h]
  void *Block; // [esp+10h] [ebp-1Ch]
  void **v45; // [esp+18h] [ebp-14h]
  char *v46; // [esp+1Ch] [ebp-10h]

  v1 = this;
  v2 = (_DWORD *)*((_DWORD *)this + 54);
  *(_DWORD *)this = &CSRSIndexes::`vftable';
  if ( v2 )
  {
    v3 = v2[3];
    v2[1] = 1;
    *(_DWORD *)(v3 + 216) = 0;
    (*(void (__thiscall **)(_DWORD *))(*v2 + 4))(v2);
    v2[3] = 0;
  }
  v4 = (_DWORD *)*((_DWORD *)v1 + 16);
  if ( !v4
    || (v4[4] != 1 || (v5 = (CTransactionState *)v4[2]) == 0
      ? (isZombie = v4[3])
      : (isZombie = CTransactionState::isZombie(v5)),
        !isZombie) )
  {
    v7 = *((_DWORD *)v1 + 27);
    if ( v7 != -1 && JetCloseTable(*(_DWORD *)(*((_DWORD *)v1 + 14) + 16), *((_DWORD *)v1 + 27)) == -1108 )
      CDBSession::AddJetTableId(*((CDBSession **)v1 + 14), v7);
    v8 = *((_DWORD *)v1 + 28);
    if ( v8 != -1 && JetCloseTable(*(_DWORD *)(*((_DWORD *)v1 + 14) + 16), *((_DWORD *)v1 + 28)) == -1108 )
      CDBSession::AddJetTableId(*((CDBSession **)v1 + 14), v8);
  }
  v9 = *((_DWORD *)v1 + 15);
  if ( v9 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 248));
    _InterlockedDecrement((volatile signed __int32 *)(v9 + 80));
    if ( v9 != -248 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 248));
  }
  v10 = *((_DWORD *)v1 + 14);
  if ( v10 )
  {
    v11 = *(_DWORD *)(v10 + 28);
    if ( v11 )
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v11 + 8))(*(_DWORD *)(*(_DWORD *)v11 + 8), v11);
  }
  v12 = *((_DWORD *)v1 + 15);
  if ( v12 && (*(int (__thiscall **)(_DWORD))(*(_DWORD *)v12 + 24))(*((_DWORD *)v1 + 15)) )
  {
    v13 = (*(int (__thiscall **)(_DWORD))(**((_DWORD **)v1 + 15) + 24))(*((_DWORD *)v1 + 15));
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v13 + 8))(*(_DWORD *)(*(_DWORD *)v13 + 8), v13);
  }
  v14 = *((_DWORD *)v1 + 16);
  if ( v14 )
  {
    _InterlockedDecrement((volatile signed __int32 *)v14);
    if ( !*(_DWORD *)v14 )
    {
      v15 = *(CTransactionState **)(v14 + 8);
      if ( v15 )
        CTransactionState::Release(v15);
      operator delete((void *)v14);
    }
    *((_DWORD *)v1 + 16) = 0;
  }
  v16 = (void *)*((_DWORD *)v1 + 3);
  if ( v16 )
  {
    CImpIAccessor::~CImpIAccessor(*((CImpIAccessor **)v1 + 3));
    operator delete(v16);
  }
  v17 = (_DWORD *)*((_DWORD *)v1 + 6);
  if ( v17 )
  {
    v35 = (void *)*((_DWORD *)v1 + 6);
    *v17 = &CImpIRowsetIdentity::`vftable';
    operator delete(v35);
  }
  v18 = (_DWORD *)*((_DWORD *)v1 + 7);
  if ( v18 )
  {
    v36 = (void *)*((_DWORD *)v1 + 7);
    *v18 = &CImpIRowsetIndex::`vftable';
    operator delete(v36);
  }
  v19 = (_DWORD *)*((_DWORD *)v1 + 8);
  if ( v19 )
  {
    v37 = (void *)*((_DWORD *)v1 + 8);
    *v19 = &CImpIRowsetInfo::`vftable';
    operator delete(v37);
  }
  v20 = (_DWORD *)*((_DWORD *)v1 + 4);
  if ( v20 )
  {
    v38 = (void *)*((_DWORD *)v1 + 4);
    *v20 = &CImpIRowsetLocate::`vftable';
    operator delete(v38);
  }
  v21 = (_DWORD *)*((_DWORD *)v1 + 9);
  if ( v21 )
  {
    v39 = (void *)*((_DWORD *)v1 + 9);
    *v21 = &CImpIRowsetUpdate::`vftable';
    operator delete(v39);
  }
  v22 = (_DWORD *)*((_DWORD *)v1 + 10);
  if ( v22 )
  {
    v40 = (void *)*((_DWORD *)v1 + 10);
    *v22 = &CImpIColumnsInfo::`vftable';
    operator delete(v40);
  }
  v23 = (_DWORD *)*((_DWORD *)v1 + 11);
  if ( v23 )
  {
    v41 = (void *)*((_DWORD *)v1 + 11);
    *v23 = &CImpIColumnsRowset::`vftable';
    operator delete(v41);
  }
  v24 = (_DWORD *)*((_DWORD *)v1 + 12);
  if ( v24 )
  {
    v42 = (void *)*((_DWORD *)v1 + 12);
    *v24 = &CImpIConvertType::`vftable';
    operator delete(v42);
  }
  v25 = (void **)*((_DWORD *)v1 + 26);
  if ( v25 )
  {
    if ( v25[2] )
      _free(v25[2]);
    if ( v25[4] != v25 + 8 )
      operator delete(v25[4]);
    operator delete(v25);
  }
  v26 = Sys;
  if ( *((_DWORD *)v1 + 35) && Sys )
  {
    (*(void (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      *((_DWORD *)v1 + 35));
    v26 = Sys;
  }
  v27 = *((_DWORD *)v1 + 37);
  if ( v27 )
  {
    (*(void (__thiscall **)(int, int))(*(_DWORD *)v27 + 4))(v27, 1);
    v26 = Sys;
  }
  if ( *((_DWORD *)v1 + 44) && v26 )
    (*(void (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)v26 + 20))(
      *(_DWORD *)(*(_DWORD *)v26 + 20),
      v26,
      *((_DWORD *)v1 + 44));
  v28 = (_DWORD *)*((_DWORD *)v1 + 13);
  Block = v28;
  if ( v28 )
  {
    v29 = (struct _RTL_CRITICAL_SECTION *)(v28 + 1);
    EnterCriticalSection((LPCRITICAL_SECTION)(v28 + 1));
    if ( _InterlockedExchangeAdd(v28 + 8, 0xFFFFFFFF) )
    {
      if ( v28 != (_DWORD *)-4 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v28 + 1));
    }
    else
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(v28 + 1));
      *v28 = &CRowsetConnectionPointContainer::`vftable';
      v30 = (char *)v28[9];
      v46 = v30;
      if ( v30 )
      {
        v31 = *((_DWORD *)v30 + 10) == 0;
        *(_DWORD *)v30 = &CRowsetConnectionPoint::`vftable';
        if ( !v31 )
        {
          if ( *((_DWORD *)v30 + 17) )
          {
            v32 = 0;
            do
            {
              v33 = **(_DWORD **)(*((_DWORD *)v30 + 10) + 4 * v32);
              if ( v33 )
              {
                v30 = v46;
                if ( !(*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v33 + 8))(*(_DWORD *)(*(_DWORD *)v33 + 8), v33) )
                  **(_DWORD **)(*((_DWORD *)v46 + 10) + 4 * v32) = 0;
              }
              v34 = *(void ***)(*((_DWORD *)v30 + 10) + 4 * v32);
              v45 = v34;
              if ( v34 )
              {
                if ( v34[7] )
                {
                  _free(v34[7]);
                  v34 = v45;
                }
                operator delete(v34);
              }
              ++v32;
            }
            while ( v32 < *((_DWORD *)v30 + 17) );
            v1 = this;
          }
          _free(*((void **)v30 + 10));
        }
        if ( *((_DWORD *)v30 + 15) )
          _free(*((void **)v30 + 15));
        DeleteCriticalSection((LPCRITICAL_SECTION)(v30 + 12));
        operator delete(v30);
      }
      DeleteCriticalSection(v29);
      operator delete(Block);
    }
  }
  CSettableProperties::~CSettableProperties((CRowset *)((char *)v1 + 152));
  DeleteCriticalSection((LPCRITICAL_SECTION)v1 + 3);
  *(_DWORD *)v1 = &CBaseObj::`vftable';
}

```

## disassembly

```asm
0x10027f00  mov     edi, edi
0x10027f02  push    ebp
0x10027f03  mov     ebp, esp
0x10027f05  push    0FFFFFFFFh
0x10027f07  push    offset ??1CRowset@@UAE@XZ_SEH
0x10027f0c  mov     eax, large fs:0
0x10027f12  push    eax
0x10027f13  sub     esp, 10h
0x10027f16  push    ebx
0x10027f17  push    esi
0x10027f18  push    edi
0x10027f19  mov     eax, ___security_cookie
0x10027f1e  xor     eax, ebp
0x10027f20  push    eax
0x10027f21  lea     eax, [ebp+var_C]
0x10027f24  mov     large fs:0, eax
0x10027f2a  mov     ebx, ecx
0x10027f2c  mov     [ebp+var_18], ebx
0x10027f2f  mov     edi, [ebx+0D8h]
0x10027f35  mov     dword ptr [ebx], offset ??_7CSRSIndexes@@6B@; const CSRSIndexes::`vftable'
0x10027f3b  test    edi, edi
0x10027f3d  jz      short loc_10027F6B
0x10027f3f  mov     eax, [edi+0Ch]
0x10027f42  mov     dword ptr [edi+4], 1
0x10027f49  mov     dword ptr [eax+0D8h], 0
0x10027f53  mov     eax, [edi]
0x10027f55  mov     esi, [eax+4]
0x10027f58  mov     ecx, esi
0x10027f5a  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10027f60  mov     ecx, edi
0x10027f62  call    esi
0x10027f64  mov     dword ptr [edi+0Ch], 0
0x10027f6b  mov     eax, [ebx+40h]
0x10027f6e  test    eax, eax
0x10027f70  jz      short loc_10027F8D
0x10027f72  cmp     dword ptr [eax+10h], 1
0x10027f76  jnz     short loc_10027F86
0x10027f78  mov     ecx, [eax+8]; this
0x10027f7b  test    ecx, ecx
0x10027f7d  jz      short loc_10027F86
0x10027f7f  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x10027f84  jmp     short loc_10027F89
0x10027f86  mov     eax, [eax+0Ch]
0x10027f89  test    eax, eax
0x10027f8b  jnz     short loc_10027FD7
0x10027f8d  mov     esi, [ebx+6Ch]
0x10027f90  cmp     esi, 0FFFFFFFFh
0x10027f93  jz      short loc_10027FB2
0x10027f95  mov     eax, [ebx+38h]
0x10027f98  push    esi; tableid
0x10027f99  push    dword ptr [eax+10h]; sesid
0x10027f9c  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10027fa2  cmp     eax, 0FFFFFBACh
0x10027fa7  jnz     short loc_10027FB2
0x10027fa9  mov     ecx, [ebx+38h]; this
0x10027fac  push    esi; unsigned int
0x10027fad  call    ?AddJetTableId@CDBSession@@QAEJK@Z; CDBSession::AddJetTableId(ulong)
0x10027fb2  mov     esi, [ebx+70h]
0x10027fb5  cmp     esi, 0FFFFFFFFh
0x10027fb8  jz      short loc_10027FD7
0x10027fba  mov     eax, [ebx+38h]
0x10027fbd  push    esi; tableid
0x10027fbe  push    dword ptr [eax+10h]; sesid
0x10027fc1  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10027fc7  cmp     eax, 0FFFFFBACh
0x10027fcc  jnz     short loc_10027FD7
0x10027fce  mov     ecx, [ebx+38h]; this
0x10027fd1  push    esi; unsigned int
0x10027fd2  call    ?AddJetTableId@CDBSession@@QAEJK@Z; CDBSession::AddJetTableId(ulong)
0x10027fd7  mov     edi, [ebx+3Ch]
0x10027fda  test    edi, edi
0x10027fdc  jz      short loc_10027FFA
0x10027fde  lea     esi, [edi+0F8h]
0x10027fe4  push    esi; lpCriticalSection
0x10027fe5  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10027feb  lock dec dword ptr [edi+50h]
0x10027fef  test    esi, esi
0x10027ff1  jz      short loc_10027FFA
0x10027ff3  push    esi; lpCriticalSection
0x10027ff4  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10027ffa  mov     ecx, [ebx+38h]
0x10027ffd  test    ecx, ecx
0x10027fff  jz      short loc_10028018
0x10028001  mov     ecx, [ecx+1Ch]
0x10028004  test    ecx, ecx
0x10028006  jz      short loc_10028018
0x10028008  mov     eax, [ecx]
0x1002800a  push    ecx
0x1002800b  mov     esi, [eax+8]
0x1002800e  mov     ecx, esi
0x10028010  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10028016  call    esi
0x10028018  mov     edi, [ebx+3Ch]
0x1002801b  test    edi, edi
0x1002801d  jz      short loc_10028058
0x1002801f  mov     eax, [edi]
0x10028021  mov     esi, [eax+18h]
0x10028024  mov     ecx, esi
0x10028026  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002802c  mov     ecx, edi
0x1002802e  call    esi
0x10028030  test    eax, eax
0x10028032  jz      short loc_10028058
0x10028034  mov     edi, [ebx+3Ch]
0x10028037  mov     eax, [edi]
0x10028039  mov     esi, [eax+18h]
0x1002803c  mov     ecx, esi
0x1002803e  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10028044  mov     ecx, edi
0x10028046  call    esi
0x10028048  push    eax
0x10028049  mov     ecx, [eax]
0x1002804b  mov     esi, [ecx+8]
0x1002804e  mov     ecx, esi
0x10028050  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10028056  call    esi
0x10028058  mov     esi, [ebx+40h]
0x1002805b  test    esi, esi
0x1002805d  jz      short loc_10028083
0x1002805f  lock dec dword ptr [esi]
0x10028062  cmp     dword ptr [esi], 0
0x10028065  ja      short loc_1002807C
0x10028067  mov     ecx, [esi+8]; this
0x1002806a  test    ecx, ecx
0x1002806c  jz      short loc_10028073
0x1002806e  call    ?Release@CTransactionState@@QAEKXZ; CTransactionState::Release(void)
0x10028073  push    esi; Block
0x10028074  call    ??3@YAXPAX@Z; operator delete(void *)
0x10028079  add     esp, 4
0x1002807c  mov     dword ptr [ebx+40h], 0
0x10028083  mov     esi, [ebx+0Ch]
0x10028086  test    esi, esi
0x10028088  jz      short loc_1002809A
0x1002808a  mov     ecx, esi; this
0x1002808c  call    ??1CImpIAccessor@@QAE@XZ; CImpIAccessor::~CImpIAccessor(void)
0x10028091  push    esi; Block
0x10028092  call    ??3@YAXPAX@Z; operator delete(void *)
0x10028097  add     esp, 4
0x1002809a  mov     eax, [ebx+18h]
0x1002809d  test    eax, eax
0x1002809f  jz      short loc_100280B0
0x100280a1  push    eax; Block
0x100280a2  mov     dword ptr [eax], offset ??_7CImpIRowsetIdentity@@6B@; const CImpIRowsetIdentity::`vftable'
0x100280a8  call    ??3@YAXPAX@Z; operator delete(void *)
0x100280ad  add     esp, 4
0x100280b0  mov     eax, [ebx+1Ch]
0x100280b3  test    eax, eax
0x100280b5  jz      short loc_100280C6
0x100280b7  push    eax; Block
0x100280b8  mov     dword ptr [eax], offset ??_7CImpIRowsetIndex@@6B@; const CImpIRowsetIndex::`vftable'
0x100280be  call    ??3@YAXPAX@Z; operator delete(void *)
0x100280c3  add     esp, 4
0x100280c6  mov     eax, [ebx+20h]
0x100280c9  test    eax, eax
0x100280cb  jz      short loc_100280DC
0x100280cd  push    eax; Block
0x100280ce  mov     dword ptr [eax], offset ??_7CImpIRowsetInfo@@6B@; const CImpIRowsetInfo::`vftable'
0x100280d4  call    ??3@YAXPAX@Z; operator delete(void *)
0x100280d9  add     esp, 4
0x100280dc  mov     eax, [ebx+10h]
0x100280df  test    eax, eax
0x100280e1  jz      short loc_100280F2
0x100280e3  push    eax; Block
0x100280e4  mov     dword ptr [eax], offset ??_7CImpIRowsetLocate@@6B@; const CImpIRowsetLocate::`vftable'
0x100280ea  call    ??3@YAXPAX@Z; operator delete(void *)
0x100280ef  add     esp, 4
0x100280f2  mov     eax, [ebx+24h]
0x100280f5  test    eax, eax
0x100280f7  jz      short loc_10028108
0x100280f9  push    eax; Block
0x100280fa  mov     dword ptr [eax], offset ??_7CImpIRowsetUpdate@@6B@; const CImpIRowsetUpdate::`vftable'
0x10028100  call    ??3@YAXPAX@Z; operator delete(void *)
0x10028105  add     esp, 4
0x10028108  mov     eax, [ebx+28h]
0x1002810b  test    eax, eax
0x1002810d  jz      short loc_1002811E
0x1002810f  push    eax; Block
0x10028110  mov     dword ptr [eax], offset ??_7CImpIColumnsInfo@@6B@; const CImpIColumnsInfo::`vftable'
0x10028116  call    ??3@YAXPAX@Z; operator delete(void *)
0x1002811b  add     esp, 4
0x1002811e  mov     eax, [ebx+2Ch]
0x10028121  test    eax, eax
0x10028123  jz      short loc_10028134
0x10028125  push    eax; Block
0x10028126  mov     dword ptr [eax], offset ??_7CImpIColumnsRowset@@6B@; const CImpIColumnsRowset::`vftable'
0x1002812c  call    ??3@YAXPAX@Z; operator delete(void *)
0x10028131  add     esp, 4
0x10028134  mov     eax, [ebx+30h]
0x10028137  test    eax, eax
0x10028139  jz      short loc_1002814A
0x1002813b  push    eax; Block
0x1002813c  mov     dword ptr [eax], offset ??_7CImpIConvertType@@6B@; const CImpIConvertType::`vftable'
0x10028142  call    ??3@YAXPAX@Z; operator delete(void *)
0x10028147  add     esp, 4
0x1002814a  mov     esi, [ebx+68h]
0x1002814d  test    esi, esi
0x1002814f  jz      short loc_1002817E
0x10028151  mov     eax, [esi+8]
0x10028154  test    eax, eax
0x10028156  jz      short loc_10028162
0x10028158  push    eax; Block
0x10028159  call    ds:__imp__free
0x1002815f  add     esp, 4
0x10028162  mov     ecx, [esi+10h]
0x10028165  lea     eax, [esi+20h]
0x10028168  cmp     ecx, eax
0x1002816a  jz      short loc_10028175
0x1002816c  push    ecx; Block
0x1002816d  call    ??3@YAXPAX@Z; operator delete(void *)
0x10028172  add     esp, 4
0x10028175  push    esi; Block
0x10028176  call    ??3@YAXPAX@Z; operator delete(void *)
0x1002817b  add     esp, 4
0x1002817e  mov     edx, [ebx+8Ch]
0x10028184  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x10028189  test    edx, edx
0x1002818b  jz      short loc_100281A7
0x1002818d  test    eax, eax
0x1002818f  jz      short loc_100281A7
0x10028191  mov     ecx, [eax]
0x10028193  push    edx
0x10028194  push    eax
0x10028195  mov     esi, [ecx+14h]
0x10028198  mov     ecx, esi
0x1002819a  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100281a0  call    esi
0x100281a2  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x100281a7  mov     edi, [ebx+94h]
0x100281ad  test    edi, edi
0x100281af  jz      short loc_100281C9
0x100281b1  mov     eax, [edi]
0x100281b3  push    1
0x100281b5  mov     esi, [eax+4]
0x100281b8  mov     ecx, esi
0x100281ba  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100281c0  mov     ecx, edi
0x100281c2  call    esi
0x100281c4  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x100281c9  mov     edx, [ebx+0B0h]
0x100281cf  test    edx, edx
0x100281d1  jz      short loc_100281E8
0x100281d3  test    eax, eax
0x100281d5  jz      short loc_100281E8
0x100281d7  mov     ecx, [eax]
0x100281d9  push    edx
0x100281da  push    eax
0x100281db  mov     esi, [ecx+14h]
0x100281de  mov     ecx, esi
0x100281e0  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100281e6  call    esi
0x100281e8  mov     edi, [ebx+34h]
0x100281eb  mov     [ebp+Block], edi
0x100281ee  test    edi, edi
0x100281f0  jz      loc_100282FC
0x100281f6  lea     esi, [edi+4]
0x100281f9  push    esi; lpCriticalSection
0x100281fa  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10028200  or      eax, 0FFFFFFFFh
0x10028203  lock xadd [edi+20h], eax
0x10028208  jnz     loc_100282F1
0x1002820e  push    esi; lpCriticalSection
0x1002820f  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10028215  mov     dword ptr [edi], offset ??_7CRowsetConnectionPointContainer@@6B@; const CRowsetConnectionPointContainer::`vftable'
0x1002821b  mov     edi, [edi+24h]
0x1002821e  mov     [ebp+var_10], edi
0x10028221  test    edi, edi
0x10028223  jz      loc_100282DD
0x10028229  mov     [ebp+var_4], 0
0x10028230  cmp     dword ptr [edi+28h], 0
0x10028234  mov     dword ptr [edi], offset ??_7CRowsetConnectionPoint@@6B@; const CRowsetConnectionPoint::`vftable'
0x1002823a  jz      short loc_100282B2
0x1002823c  cmp     dword ptr [edi+44h], 0
0x10028240  jbe     short loc_100282A6
0x10028242  xor     ebx, ebx
0x10028244  mov     eax, [edi+28h]
0x10028247  mov     eax, [eax+ebx*4]
0x1002824a  mov     ecx, [eax]
0x1002824c  test    ecx, ecx
0x1002824e  jz      short loc_10028273
0x10028250  mov     eax, [ecx]
0x10028252  push    ecx
0x10028253  mov     edi, [eax+8]
0x10028256  mov     ecx, edi
0x10028258  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002825e  call    edi
0x10028260  mov     edi, [ebp+var_10]
0x10028263  test    eax, eax
0x10028265  jnz     short loc_10028273
0x10028267  mov     eax, [edi+28h]
0x1002826a  mov     eax, [eax+ebx*4]
0x1002826d  mov     dword ptr [eax], 0
0x10028273  mov     eax, [edi+28h]
0x10028276  mov     eax, [eax+ebx*4]
0x10028279  mov     [ebp+var_14], eax
0x1002827c  test    eax, eax
0x1002827e  jz      short loc_1002829D
0x10028280  mov     ecx, [eax+1Ch]
0x10028283  test    ecx, ecx
0x10028285  jz      short loc_10028294
0x10028287  push    ecx; Block
  ... truncated ...
```
