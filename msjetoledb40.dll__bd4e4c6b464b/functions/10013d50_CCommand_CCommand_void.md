# CCommand::~CCommand(void)

- ea: `0x10013d50`
- end: `0x10013f42`
- name: `??1CCommand@@UAE@XZ`
- size: `498`
- prototype: `void __thiscall(CCommand *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10013d20`

## callees

- `0x1000bcf0`
- `0x10013d50`
- `0x10016e10`
- `0x1001c6d0`
- `0x10020410`
- `0x10049580`
- `0x10049670`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x10013f1c`
- `KERNEL32!DeleteCriticalSection` at `0x10013f1c`
- `msjet40!__imp__JetCloseTable@8` at `0x10013d8e`
- `msjet40!__imp__JetCloseTable@8` at `0x10013d8e`

## pseudocode

```c
void __thiscall CCommand::~CCommand(CCommand *this)
{
  JET_TABLEID v2; // ecx
  int v3; // ebx
  void *v4; // esi
  _DWORD *v5; // eax
  _DWORD *v6; // esi
  _DWORD *v7; // eax
  _DWORD *v8; // eax
  _DWORD *v9; // eax
  _DWORD *v10; // eax
  _DWORD *v11; // eax
  _DWORD *v12; // eax
  void (__thiscall ***v13)(_DWORD, int); // ebx
  int v14; // ecx
  int v15; // ecx
  int v16; // esi
  CTransactionState *v17; // ecx
  void *v18; // [esp-4h] [ebp-20h]
  void *v19; // [esp-4h] [ebp-20h]
  void *v20; // [esp-4h] [ebp-20h]
  void *v21; // [esp-4h] [ebp-20h]
  void *v22; // [esp-4h] [ebp-20h]
  void *v23; // [esp-4h] [ebp-20h]
  void *v24; // [esp-4h] [ebp-20h]

  v2 = *((_DWORD *)this + 25);
  *(_DWORD *)this = &CCommand::`vftable';
  if ( v2 != -1 && JetCloseTable(*(_DWORD *)(*((_DWORD *)this + 13) + 16), v2) == -1108 )
    CDBSession::AddJetTableId(*((CDBSession **)this + 13), *((_DWORD *)this + 25));
  v3 = *((_DWORD *)this + 26);
  if ( v3 )
    (*(void (__thiscall **)(int, int))(*(_DWORD *)v3 + 4))(v3, 1);
  if ( *((_DWORD *)this + 27) && Sys )
    (*(void (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      *((_DWORD *)this + 27));
  v4 = (void *)*((_DWORD *)this + 3);
  if ( v4 )
  {
    CImpIAccessor::~CImpIAccessor(*((CImpIAccessor **)this + 3));
    operator delete(v4);
  }
  v5 = (_DWORD *)*((_DWORD *)this + 4);
  if ( v5 )
  {
    v18 = (void *)*((_DWORD *)this + 4);
    *v5 = &CImpICommandText::`vftable';
    operator delete(v18);
  }
  v6 = (_DWORD *)*((_DWORD *)this + 5);
  if ( v6 )
  {
    *v6 = &CImpICommandProperties::`vftable';
    CSettableProperties::~CSettableProperties((CSettableProperties *)(v6 + 3));
    operator delete(v6);
  }
  v7 = (_DWORD *)*((_DWORD *)this + 6);
  if ( v7 )
  {
    v19 = (void *)*((_DWORD *)this + 6);
    *v7 = &CImpICommandPrepare::`vftable';
    operator delete(v19);
  }
  v8 = (_DWORD *)*((_DWORD *)this + 7);
  if ( v8 )
  {
    v20 = (void *)*((_DWORD *)this + 7);
    *v8 = &CImpICommandWithParameters::`vftable';
    operator delete(v20);
  }
  v9 = (_DWORD *)*((_DWORD *)this + 8);
  if ( v9 )
  {
    v21 = (void *)*((_DWORD *)this + 8);
    *v9 = &CImpIColumnsInfo::`vftable';
    operator delete(v21);
  }
  v10 = (_DWORD *)*((_DWORD *)this + 9);
  if ( v10 )
  {
    v22 = (void *)*((_DWORD *)this + 9);
    *v10 = &CImpIColumnsRowset::`vftable';
    operator delete(v22);
  }
  v11 = (_DWORD *)*((_DWORD *)this + 10);
  if ( v11 )
  {
    v23 = (void *)*((_DWORD *)this + 10);
    *v11 = &CImpIConvertType::`vftable';
    operator delete(v23);
  }
  v12 = (_DWORD *)*((_DWORD *)this + 11);
  if ( v12 )
  {
    v24 = (void *)*((_DWORD *)this + 11);
    *v12 = &CImpICommandPersist::`vftable';
    operator delete(v24);
  }
  v13 = (void (__thiscall ***)(_DWORD, int))*((_DWORD *)this + 68);
  if ( v13 )
    (**v13)(v13, 1);
  v14 = *((_DWORD *)this + 13);
  if ( v14 )
  {
    v15 = *(_DWORD *)(v14 + 28);
    if ( v15 )
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v15 + 8))(*(_DWORD *)(*(_DWORD *)v15 + 8), v15);
  }
  v16 = *((_DWORD *)this + 14);
  if ( v16 )
  {
    _InterlockedDecrement((volatile signed __int32 *)v16);
    if ( !*(_DWORD *)v16 )
    {
      v17 = *(CTransactionState **)(v16 + 8);
      if ( v17 )
        CTransactionState::Release(v17);
      operator delete((void *)v16);
    }
    *((_DWORD *)this + 14) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  CJetParameterList::~CJetParameterList((CCommand *)((char *)this + 84));
  *(_DWORD *)this = &CBaseObj::`vftable';
}

```

## disassembly

```asm
0x10013d50  mov     edi, edi
0x10013d52  push    ebp
0x10013d53  mov     ebp, esp
0x10013d55  push    0FFFFFFFFh
0x10013d57  push    offset ??1CEnum@@QAE@XZ_SEH
0x10013d5c  mov     eax, large fs:0
0x10013d62  push    eax
0x10013d63  push    ebx
0x10013d64  push    esi
0x10013d65  push    edi
0x10013d66  mov     eax, ___security_cookie
0x10013d6b  xor     eax, ebp
0x10013d6d  push    eax
0x10013d6e  lea     eax, [ebp+var_C]
0x10013d71  mov     large fs:0, eax
0x10013d77  mov     edi, ecx
0x10013d79  mov     ecx, [edi+64h]
0x10013d7c  mov     dword ptr [edi], offset ??_7CCommand@@6B@; const CCommand::`vftable'
0x10013d82  cmp     ecx, 0FFFFFFFFh
0x10013d85  jz      short loc_10013DA6
0x10013d87  mov     eax, [edi+34h]
0x10013d8a  push    ecx; tableid
0x10013d8b  push    dword ptr [eax+10h]; sesid
0x10013d8e  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10013d94  cmp     eax, 0FFFFFBACh
0x10013d99  jnz     short loc_10013DA6
0x10013d9b  push    dword ptr [edi+64h]; unsigned int
0x10013d9e  mov     ecx, [edi+34h]; this
0x10013da1  call    ?AddJetTableId@CDBSession@@QAEJK@Z; CDBSession::AddJetTableId(ulong)
0x10013da6  mov     ebx, [edi+68h]
0x10013da9  test    ebx, ebx
0x10013dab  jz      short loc_10013DC0
0x10013dad  mov     eax, [ebx]
0x10013daf  push    1
0x10013db1  mov     esi, [eax+4]
0x10013db4  mov     ecx, esi
0x10013db6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10013dbc  mov     ecx, ebx
0x10013dbe  call    esi
0x10013dc0  mov     edx, [edi+6Ch]
0x10013dc3  test    edx, edx
0x10013dc5  jz      short loc_10013DE1
0x10013dc7  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x10013dcc  test    eax, eax
0x10013dce  jz      short loc_10013DE1
0x10013dd0  mov     ecx, [eax]
0x10013dd2  push    edx
0x10013dd3  push    eax
0x10013dd4  mov     esi, [ecx+14h]
0x10013dd7  mov     ecx, esi
0x10013dd9  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10013ddf  call    esi
0x10013de1  mov     esi, [edi+0Ch]
0x10013de4  test    esi, esi
0x10013de6  jz      short loc_10013DF8
0x10013de8  mov     ecx, esi; this
0x10013dea  call    ??1CImpIAccessor@@QAE@XZ; CImpIAccessor::~CImpIAccessor(void)
0x10013def  push    esi; Block
0x10013df0  call    ??3@YAXPAX@Z; operator delete(void *)
0x10013df5  add     esp, 4
0x10013df8  mov     eax, [edi+10h]
0x10013dfb  test    eax, eax
0x10013dfd  jz      short loc_10013E0E
0x10013dff  push    eax; Block
0x10013e00  mov     dword ptr [eax], offset ??_7CImpICommandText@@6B@; const CImpICommandText::`vftable'
0x10013e06  call    ??3@YAXPAX@Z; operator delete(void *)
0x10013e0b  add     esp, 4
0x10013e0e  mov     esi, [edi+14h]
0x10013e11  test    esi, esi
0x10013e13  jz      short loc_10013E2C
0x10013e15  lea     ecx, [esi+0Ch]; this
0x10013e18  mov     dword ptr [esi], offset ??_7CImpICommandProperties@@6B@; const CImpICommandProperties::`vftable'
0x10013e1e  call    ??1CSettableProperties@@UAE@XZ; CSettableProperties::~CSettableProperties(void)
0x10013e23  push    esi; Block
0x10013e24  call    ??3@YAXPAX@Z; operator delete(void *)
0x10013e29  add     esp, 4
0x10013e2c  mov     eax, [edi+18h]
0x10013e2f  test    eax, eax
0x10013e31  jz      short loc_10013E42
0x10013e33  push    eax; Block
0x10013e34  mov     dword ptr [eax], offset ??_7CImpICommandPrepare@@6B@; const CImpICommandPrepare::`vftable'
0x10013e3a  call    ??3@YAXPAX@Z; operator delete(void *)
0x10013e3f  add     esp, 4
0x10013e42  mov     eax, [edi+1Ch]
0x10013e45  test    eax, eax
0x10013e47  jz      short loc_10013E58
0x10013e49  push    eax; Block
0x10013e4a  mov     dword ptr [eax], offset ??_7CImpICommandWithParameters@@6B@; const CImpICommandWithParameters::`vftable'
0x10013e50  call    ??3@YAXPAX@Z; operator delete(void *)
0x10013e55  add     esp, 4
0x10013e58  mov     eax, [edi+20h]
0x10013e5b  test    eax, eax
0x10013e5d  jz      short loc_10013E6E
0x10013e5f  push    eax; Block
0x10013e60  mov     dword ptr [eax], offset ??_7CImpIColumnsInfo@@6B@; const CImpIColumnsInfo::`vftable'
0x10013e66  call    ??3@YAXPAX@Z; operator delete(void *)
0x10013e6b  add     esp, 4
0x10013e6e  mov     eax, [edi+24h]
0x10013e71  test    eax, eax
0x10013e73  jz      short loc_10013E84
0x10013e75  push    eax; Block
0x10013e76  mov     dword ptr [eax], offset ??_7CImpIColumnsRowset@@6B@; const CImpIColumnsRowset::`vftable'
0x10013e7c  call    ??3@YAXPAX@Z; operator delete(void *)
0x10013e81  add     esp, 4
0x10013e84  mov     eax, [edi+28h]
0x10013e87  test    eax, eax
0x10013e89  jz      short loc_10013E9A
0x10013e8b  push    eax; Block
0x10013e8c  mov     dword ptr [eax], offset ??_7CImpIConvertType@@6B@; const CImpIConvertType::`vftable'
0x10013e92  call    ??3@YAXPAX@Z; operator delete(void *)
0x10013e97  add     esp, 4
0x10013e9a  mov     eax, [edi+2Ch]
0x10013e9d  test    eax, eax
0x10013e9f  jz      short loc_10013EB0
0x10013ea1  push    eax; Block
0x10013ea2  mov     dword ptr [eax], offset ??_7CImpICommandPersist@@6B@; const CImpICommandPersist::`vftable'
0x10013ea8  call    ??3@YAXPAX@Z; operator delete(void *)
0x10013ead  add     esp, 4
0x10013eb0  mov     ebx, [edi+110h]
0x10013eb6  test    ebx, ebx
0x10013eb8  jz      short loc_10013ECC
0x10013eba  mov     eax, [ebx]
0x10013ebc  push    1
0x10013ebe  mov     esi, [eax]
0x10013ec0  mov     ecx, esi
0x10013ec2  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10013ec8  mov     ecx, ebx
0x10013eca  call    esi
0x10013ecc  mov     ecx, [edi+34h]
0x10013ecf  test    ecx, ecx
0x10013ed1  jz      short loc_10013EEA
0x10013ed3  mov     ecx, [ecx+1Ch]
0x10013ed6  test    ecx, ecx
0x10013ed8  jz      short loc_10013EEA
0x10013eda  mov     eax, [ecx]
0x10013edc  push    ecx
0x10013edd  mov     esi, [eax+8]
0x10013ee0  mov     ecx, esi
0x10013ee2  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10013ee8  call    esi
0x10013eea  mov     esi, [edi+38h]
0x10013eed  test    esi, esi
0x10013eef  jz      short loc_10013F15
0x10013ef1  lock dec dword ptr [esi]
0x10013ef4  cmp     dword ptr [esi], 0
0x10013ef7  ja      short loc_10013F0E
0x10013ef9  mov     ecx, [esi+8]; this
0x10013efc  test    ecx, ecx
0x10013efe  jz      short loc_10013F05
0x10013f00  call    ?Release@CTransactionState@@QAEKXZ; CTransactionState::Release(void)
0x10013f05  push    esi; Block
0x10013f06  call    ??3@YAXPAX@Z; operator delete(void *)
0x10013f0b  add     esp, 4
0x10013f0e  mov     dword ptr [edi+38h], 0
0x10013f15  lea     eax, [edi+0F8h]
0x10013f1b  push    eax; lpCriticalSection
0x10013f1c  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10013f22  lea     ecx, [edi+54h]; this
0x10013f25  call    ??1CJetParameterList@@QAE@XZ; CJetParameterList::~CJetParameterList(void)
0x10013f2a  mov     dword ptr [edi], offset ??_7CBaseObj@@6B@; const CBaseObj::`vftable'
0x10013f30  mov     ecx, [ebp+var_C]
0x10013f33  mov     large fs:0, ecx
0x10013f3a  pop     ecx
0x10013f3b  pop     edi
0x10013f3c  pop     esi
0x10013f3d  pop     ebx
0x10013f3e  mov     esp, ebp
0x10013f40  pop     ebp
0x10013f41  retn
0x1004e1b0  nop
0x1004e1b1  nop
0x1004e1b2  mov     edx, [esp-4+arg_4]
0x1004e1b6  lea     eax, [edx+0Ch]
0x1004e1b9  mov     ecx, [edx-10h]
0x1004e1bc  xor     ecx, eax; StackCookie
0x1004e1be  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e1c3  mov     eax, offset stru_1004F608
0x1004e1c8  jmp     ___CxxFrameHandler3
```
