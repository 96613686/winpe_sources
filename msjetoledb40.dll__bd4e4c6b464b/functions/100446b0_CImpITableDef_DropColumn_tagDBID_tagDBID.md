# CImpITableDef::DropColumn(tagDBID *,tagDBID *)

- ea: `0x100446b0`
- end: `0x10044875`
- name: `?DropColumn@CImpITableDef@@UAGJPAUtagDBID@@0@Z`
- size: `453`
- prototype: `int(CImpITableDef *__hidden this, struct tagDBID *, struct tagDBID *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x1000ba90`
- `0x10016e10`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001e800`
- `0x100446b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10044859`
- `KERNEL32!LeaveCriticalSection` at `0x10044859`
- `KERNEL32!EnterCriticalSection` at `0x100446ff`
- `KERNEL32!EnterCriticalSection` at `0x100446ff`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100446ec`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100446ec`
- `msjet40!__imp__JetCloseTable@8` at `0x1004483d`
- `msjet40!__imp__JetCloseTable@8` at `0x1004483d`
- `msjet40!__imp__JetDeleteColumn@12` at `0x1004477c`
- `msjet40!__imp__JetDeleteColumn@12` at `0x1004477c`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10044814`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10044814`

## pseudocode

```c
int __stdcall CImpITableDef::DropColumn(CImpITableDef *this, struct tagDBID *a2, struct tagDBID *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // esi
  LPOLESTR pwszName; // ecx
  int v5; // edi
  int v6; // eax
  int v7; // eax
  int v8; // ecx
  int v9; // eax
  int v10; // eax
  JET_SESID *v11; // ebx
  unsigned int v13; // [esp-14h] [ebp-3Ch]
  unsigned __int16 *v14; // [esp-10h] [ebp-38h]
  struct _GUID *v15; // [esp+0h] [ebp-28h]
  struct _GUID *v16; // [esp+4h] [ebp-24h]
  unsigned int v17; // [esp+14h] [ebp-14h] BYREF
  JET_TABLEID tableid[4]; // [esp+18h] [ebp-10h] BYREF

  v17 = 0;
  tableid[0] = -1;
  SetErrorInfo(0, 0);
  v3 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  EnterCriticalSection(v3);
  tableid[3] = 0;
  if ( !a2 || !a3 )
  {
    v5 = -2147024809;
    goto LABEL_26;
  }
  if ( a2->eKind != 2 || (pwszName = a2->uName.pwszName) == 0 )
  {
    v5 = -2147217865;
    goto LABEL_26;
  }
  if ( a3->eKind != 2 || !a3->uName.ulPropid )
  {
    v5 = -2147217903;
LABEL_26:
    v10 = *((_DWORD *)this + 2);
    v8 = *(_DWORD *)(v10 + 20);
    v9 = *(_DWORD *)(v10 + 16);
LABEL_27:
    if ( !JetGetDatabaseInfo(v9, v8, &v17, 4, 3) )
      CExtError::SendHRtoOLEAuto(v5, (__int128 *)&IID_ITableDefinition, 0, v15, (int)v16);
    goto LABEL_29;
  }
  v5 = CJOLT::JOLTJetOpenTable(
         *(_DWORD *)(*((_DWORD *)this + 2) + 20),
         *(_DWORD *)(*((_DWORD *)this + 2) + 16),
         (unsigned int)pwszName,
         v13,
         v14,
         (const void *)2,
         tableid,
         (int *)&v17,
         &v15->Data1,
         (int *)v16);
  if ( v5 < 0 )
  {
    v6 = v17;
  }
  else
  {
    v6 = JetDeleteColumn(*(_DWORD *)(*((_DWORD *)this + 2) + 16), tableid[0], a3->uName.ulPropid);
    if ( v6 > -1507 )
    {
      if ( v6 != -1002 )
      {
        if ( !v6 )
          goto LABEL_18;
        goto LABEL_15;
      }
    }
    else if ( v6 != -1507 )
    {
      if ( v6 == -1907 || v6 == -1809 )
      {
        v5 = -2147217911;
        goto LABEL_18;
      }
LABEL_15:
      v5 = -2147467259;
      goto LABEL_18;
    }
    v5 = -2147217903;
  }
LABEL_18:
  if ( v6 )
  {
    CExtError::SendJetErrortoOLEAuto(
      v5,
      *(char **)(*((_DWORD *)this + 2) + 16),
      v6,
      (int)&IID_ITableDefinition,
      (int)v15,
      v16);
    goto LABEL_29;
  }
  if ( v5 < 0 )
  {
    v7 = *((_DWORD *)this + 2);
    v8 = *(_DWORD *)(v7 + 20);
    v9 = *(_DWORD *)(v7 + 16);
    if ( v5 != -2147024882 )
      goto LABEL_27;
  }
LABEL_29:
  v17 = tableid[0];
  if ( tableid[0] != -1 )
  {
    v11 = (JET_SESID *)*((_DWORD *)this + 2);
    if ( JetCloseTable(v11[4], tableid[0]) == -1108 )
      CDBSession::AddJetTableId((CDBSession *)v11, v17);
  }
  if ( v3 )
    LeaveCriticalSection(v3);
  return v5;
}

```

## disassembly

```asm
0x100446b0  mov     edi, edi
0x100446b2  push    ebp
0x100446b3  mov     ebp, esp
0x100446b5  push    0FFFFFFFFh
0x100446b7  push    offset ?DropColumn@CImpITableDef@@UAGJPAUtagDBID@@0@Z_SEH
0x100446bc  mov     eax, large fs:0
0x100446c2  push    eax
0x100446c3  sub     esp, 0Ch
0x100446c6  push    ebx
0x100446c7  push    esi
0x100446c8  push    edi; int
0x100446c9  mov     eax, ___security_cookie
0x100446ce  xor     eax, ebp
0x100446d0  push    eax; struct _GUID *
0x100446d1  lea     eax, [ebp+var_C]
0x100446d4  mov     large fs:0, eax
0x100446da  push    0; perrinfo
0x100446dc  push    0; dwReserved
0x100446de  mov     [ebp+var_14], 0
0x100446e5  mov     [ebp+tableid], 0FFFFFFFFh
0x100446ec  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x100446f2  mov     ebx, [ebp+this]
0x100446f5  mov     esi, [ebx+8]
0x100446f8  add     esi, 68h ; 'h'
0x100446fb  push    esi; lpCriticalSection
0x100446fc  mov     [ebp+var_18], esi
0x100446ff  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10044705  mov     ecx, [ebp+arg_4]
0x10044708  mov     [ebp+var_4], 0
0x1004470f  test    ecx, ecx
0x10044711  jz      loc_100447FC
0x10044717  mov     eax, [ebp+arg_8]
0x1004471a  test    eax, eax
0x1004471c  jz      loc_100447FC
0x10044722  cmp     dword ptr [ecx+10h], 2
0x10044726  jnz     loc_100447F5
0x1004472c  mov     ecx, [ecx+14h]
0x1004472f  test    ecx, ecx
0x10044731  jz      loc_100447F5
0x10044737  cmp     dword ptr [eax+10h], 2
0x1004473b  jnz     loc_100447EE
0x10044741  cmp     dword ptr [eax+14h], 0
0x10044745  jz      loc_100447EE
0x1004474b  mov     eax, [ebx+8]
0x1004474e  lea     edx, [ebp+var_14]
0x10044751  push    edx; unsigned int
0x10044752  lea     edx, [ebp+tableid]
0x10044755  push    edx; unsigned int
0x10044756  mov     edx, [eax+14h]
0x10044759  push    2; void *
0x1004475b  sub     esp, 8
0x1004475e  push    ecx; unsigned int
0x1004475f  mov     ecx, [eax+10h]
0x10044762  call    ?JOLTJetOpenTable@CJOLT@@SGJKKPAGPBXKKPAKAAJ@Z; CJOLT::JOLTJetOpenTable(ulong,ulong,ushort *,void const *,ulong,ulong,ulong *,long &)
0x10044767  mov     edi, eax
0x10044769  test    edi, edi
0x1004476b  js      short loc_100447B9
0x1004476d  mov     eax, [ebp+arg_8]
0x10044770  mov     ecx, [ebx+8]
0x10044773  push    dword ptr [eax+14h]
0x10044776  push    [ebp+tableid]
0x10044779  push    dword ptr [ecx+10h]
0x1004477c  call    ds:__imp__JetDeleteColumn@12; JetDeleteColumn(x,x,x)
0x10044782  cmp     eax, 0FFFFFA1Dh
0x10044787  jg      short loc_100447A0
0x10044789  jz      short loc_100447B2
0x1004478b  cmp     eax, 0FFFFF88Dh
0x10044790  jz      short loc_10044799
0x10044792  cmp     eax, 0FFFFF8EFh
0x10044797  jnz     short loc_100447AB
0x10044799  mov     edi, 80040E09h
0x1004479e  jmp     short loc_100447BC
0x100447a0  cmp     eax, 0FFFFFC16h
0x100447a5  jz      short loc_100447B2
0x100447a7  test    eax, eax
0x100447a9  jz      short loc_100447BC
0x100447ab  mov     edi, 80004005h
0x100447b0  jmp     short loc_100447BC
0x100447b2  mov     edi, 80040E11h
0x100447b7  jmp     short loc_100447BC
0x100447b9  mov     eax, [ebp+var_14]
0x100447bc  mov     edx, edi
0x100447be  test    eax, eax
0x100447c0  jz      short loc_100447D5
0x100447c2  mov     ecx, [ebx+8]
0x100447c5  push    offset _IID_ITableDefinition; int
0x100447ca  push    eax; unsigned int
0x100447cb  mov     ecx, [ecx+10h]
0x100447ce  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x100447d3  jmp     short loc_1004482B
0x100447d5  test    edi, edi
0x100447d7  jns     short loc_1004482B
0x100447d9  mov     eax, [ebx+8]
0x100447dc  mov     edi, edx
0x100447de  mov     ecx, [eax+14h]
0x100447e1  mov     eax, [eax+10h]
0x100447e4  cmp     edx, 8007000Eh
0x100447ea  jz      short loc_1004482B
0x100447ec  jmp     short loc_1004480A
0x100447ee  mov     edi, 80040E11h
0x100447f3  jmp     short loc_10044801
0x100447f5  mov     edi, 80040E37h
0x100447fa  jmp     short loc_10044801
0x100447fc  mov     edi, 80070057h
0x10044801  mov     eax, [ebx+8]
0x10044804  mov     ecx, [eax+14h]
0x10044807  mov     eax, [eax+10h]
0x1004480a  push    3
0x1004480c  push    4
0x1004480e  lea     edx, [ebp+var_14]
0x10044811  push    edx
0x10044812  push    ecx
0x10044813  push    eax
0x10044814  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1004481a  test    eax, eax
0x1004481c  jnz     short loc_1004482B
0x1004481e  push    eax; int
0x1004481f  push    offset _IID_ITableDefinition; int
0x10044824  mov     edx, edi
0x10044826  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1004482b  mov     eax, [ebp+tableid]
0x1004482e  mov     [ebp+var_14], eax
0x10044831  cmp     eax, 0FFFFFFFFh
0x10044834  jz      short loc_10044854
0x10044836  mov     ebx, [ebx+8]
0x10044839  push    eax; tableid
0x1004483a  push    dword ptr [ebx+10h]; sesid
0x1004483d  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10044843  cmp     eax, 0FFFFFBACh
0x10044848  jnz     short loc_10044854
0x1004484a  push    [ebp+var_14]; unsigned int
0x1004484d  mov     ecx, ebx; this
0x1004484f  call    ?AddJetTableId@CDBSession@@QAEJK@Z; CDBSession::AddJetTableId(ulong)
0x10044854  test    esi, esi
0x10044856  jz      short loc_1004485F
0x10044858  push    esi; lpCriticalSection
0x10044859  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1004485f  mov     eax, edi
0x10044861  mov     ecx, [ebp+var_C]
0x10044864  mov     large fs:0, ecx
0x1004486b  pop     ecx
0x1004486c  pop     edi
0x1004486d  pop     esi
0x1004486e  pop     ebx
0x1004486f  mov     esp, ebp
0x10044871  pop     ebp
0x10044872  retn    0Ch
0x1004dd50  lea     ecx, [ebp+var_18]; this
0x1004dd53  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dd5d  nop
0x1004dd5e  nop
0x1004dd5f  mov     edx, [esp-4+arg_4]
0x1004dd63  lea     eax, [edx+0Ch]
0x1004dd66  mov     ecx, [edx-1Ch]
0x1004dd69  xor     ecx, eax; StackCookie
0x1004dd6b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004dd70  mov     eax, offset stru_1004F354
0x1004dd75  jmp     ___CxxFrameHandler3
```
