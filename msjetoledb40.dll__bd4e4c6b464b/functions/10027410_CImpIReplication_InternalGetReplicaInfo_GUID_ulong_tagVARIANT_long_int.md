# CImpIReplication::InternalGetReplicaInfo(_GUID *,ulong,tagVARIANT *,long &,int &)

- ea: `0x10027410`
- end: `0x10027659`
- name: `?InternalGetReplicaInfo@CImpIReplication@@QAEJPAU_GUID@@KPAUtagVARIANT@@AAJAAH@Z`
- size: `585`
- prototype: `int __thiscall(CImpIReplication *__hidden this, struct _GUID *, unsigned int, struct tagVARIANT *, int *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x10026d80`

## callees

- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10027410`
- `0x10027860`
- `0x1004d420`

## import_xrefs

- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10027462`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10027462`
- `msjet40!__imp__JetCloseTable@8` at `0x1002763a`
- `msjet40!__imp__JetCloseTable@8` at `0x1002763a`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1002760b`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1002760b`
- `msjet40!__imp__JetMove@16` at `0x10027579`
- `msjet40!__imp__JetMove@16` at `0x10027579`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100275b5`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100275b5`

## pseudocode

```c
int __thiscall CImpIReplication::InternalGetReplicaInfo(
        CImpIReplication *this,
        struct _GUID *a2,
        unsigned int a3,
        struct tagVARIANT *a4,
        int *a5,
        int *a6)
{
  int v7; // eax
  int v8; // edi
  CReplCover **v9; // eax
  CReplCover *v10; // esi
  JET_ERR v11; // eax
  CReplCover *v12; // esi
  bool v13; // zf
  struct tagVARIANT *v14; // ecx
  const struct _GUID *v16; // [esp+2Ch] [ebp-90h]
  const struct _GUID *v17; // [esp+30h] [ebp-8Ch]
  JET_SESID sesid; // [esp+38h] [ebp-84h]
  struct _GUID *v19; // [esp+3Ch] [ebp-80h]
  int v20; // [esp+44h] [ebp-78h]
  unsigned int pcbActual; // [esp+48h] [ebp-74h] BYREF
  CImpIReplication *v22; // [esp+4Ch] [ebp-70h]
  struct tagVARIANT *v23; // [esp+50h] [ebp-6Ch] BYREF
  CReplCover **v24; // [esp+54h] [ebp-68h]
  float pvData; // [esp+58h] [ebp-64h] BYREF
  _BYTE v26[16]; // [esp+5Ch] [ebp-60h] BYREF
  _BYTE v27[4]; // [esp+6Ch] [ebp-50h] BYREF
  int v28; // [esp+70h] [ebp-4Ch]
  JET_TABLEID tableid; // [esp+74h] [ebp-48h]
  JET_COLUMNID columnid; // [esp+A8h] [ebp-14h]

  v19 = a2;
  v23 = a4;
  v7 = *((_DWORD *)this + 2);
  v8 = 0;
  v22 = this;
  sesid = *(_DWORD *)(v7 + 16);
  v20 = *(_DWORD *)(v7 + 20);
  SetErrorInfo(0, 0);
  *a5 = 0;
  tableid = -1;
  *a6 = 1;
  v9 = (CReplCover **)((char *)this + 16);
  v24 = (CReplCover **)((char *)this + 16);
  if ( !a2 )
  {
    v10 = *v9;
    v19 = (struct _GUID *)v26;
    if ( CReplCover::Initialize(*v9) < 0 )
    {
      v11 = -1029;
      v8 = -2147467259;
      *a5 = -1029;
LABEL_15:
      CExtError::SendJetErrortoOLEAuto(
        v8,
        *(char **)(*((_DWORD *)v22 + 2) + 16),
        v11,
        (int)&IID_IReplication,
        (int)v16,
        v17);
      goto LABEL_27;
    }
    v11 = (*(int (__thiscall **)(_DWORD, JET_SESID, int, _DWORD, int, _BYTE *, int, unsigned int *))(*((_DWORD *)v10 + 2) + 40))(
            *(_DWORD *)(*((_DWORD *)v10 + 2) + 40),
            sesid,
            v20,
            0,
            1,
            v26,
            16,
            &pcbActual);
    *a5 = v11;
    if ( v11 < 0 )
    {
      v8 = -2147467259;
      goto LABEL_15;
    }
    v9 = v24;
  }
  v12 = *v9;
  if ( CReplCover::Initialize(*v9) < 0 )
  {
    v11 = -1029;
    v8 = -2147467259;
    *a5 = -1029;
    goto LABEL_15;
  }
  v11 = (*(int (__thiscall **)(_DWORD, JET_SESID, int, struct _GUID *, int, _BYTE *, int, unsigned int *))(*((_DWORD *)v12 + 2) + 40))(
          *(_DWORD *)(*((_DWORD *)v12 + 2) + 40),
          sesid,
          v20,
          v19,
          20,
          v27,
          68,
          &pcbActual);
  *a5 = v11;
  if ( v11 < 0 )
  {
    v8 = -2147467259;
    goto LABEL_15;
  }
  if ( !v28 )
  {
    v8 = -2147467259;
LABEL_13:
    v13 = v11 == 0;
    goto LABEL_14;
  }
  v11 = JetMove(sesid, tableid, 0x80000000, 0);
  *a5 = v11;
  if ( v11 < 0 )
  {
    v8 = -2147467259;
    goto LABEL_15;
  }
  if ( a3 != 18 )
  {
    v8 = -2147024809;
    goto LABEL_13;
  }
  v11 = JetRetrieveColumn(sesid, tableid, columnid, &pvData, 4u, &pcbActual, 0, 0);
  *a5 = v11;
  if ( v11 < 0 )
  {
    v8 = -2147467259;
    goto LABEL_15;
  }
  v14 = v23;
  v23->vt = 3;
  v14->lVal = (int)pvData;
  v11 = *a5;
  v13 = *a5 == 0;
  if ( *a5 < 0 )
  {
    v8 = -2147467259;
    goto LABEL_15;
  }
LABEL_14:
  if ( !v13 )
    goto LABEL_15;
  if ( v8 >= 0 )
    goto LABEL_28;
  if ( !JetGetDatabaseInfo(*(_DWORD *)(*((_DWORD *)v22 + 2) + 16), *(_DWORD *)(*((_DWORD *)v22 + 2) + 20), &v23, 4, 3) )
    CExtError::SendHRtoOLEAuto(v8, (__int128 *)&IID_IReplication, 0, v16, (int)v17);
LABEL_27:
  *a6 = 0;
LABEL_28:
  if ( tableid != -1 )
    JetCloseTable(sesid, tableid);
  return v8;
}

```

## disassembly

```asm
0x10027410  mov     edi, edi
0x10027412  push    ebp
0x10027413  mov     ebp, esp
0x10027415  and     esp, 0FFFFFFF8h
0x10027418  sub     esp, 84h
0x1002741e  mov     eax, ___security_cookie
0x10027423  xor     eax, esp
0x10027425  mov     [esp+84h+var_4], eax
0x1002742c  mov     eax, [ebp+arg_0]
0x1002742f  push    ebx
0x10027430  mov     ebx, [ebp+arg_C]
0x10027433  push    esi; int
0x10027434  mov     [esp+8Ch+var_80], eax
0x10027438  mov     esi, ecx
0x1002743a  mov     eax, [ebp+arg_8]
0x1002743d  mov     [esp+8Ch+var_6C], eax
0x10027441  mov     eax, [ebp+arg_10]
0x10027444  mov     [esp+8Ch+var_7C], eax
0x10027448  mov     eax, [esi+8]
0x1002744b  push    edi; struct _GUID *
0x1002744c  xor     edi, edi
0x1002744e  mov     [esp+90h+var_70], esi
0x10027452  push    edi; perrinfo
0x10027453  mov     ecx, [eax+10h]
0x10027456  mov     eax, [eax+14h]
0x10027459  push    edi; dwReserved
0x1002745a  mov     [esp+98h+sesid], ecx
0x1002745e  mov     [esp+98h+var_78], eax
0x10027462  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10027468  mov     eax, [esp+90h+var_7C]
0x1002746c  mov     [ebx], edi
0x1002746e  mov     [esp+90h+tableid], 0FFFFFFFFh
0x10027476  mov     dword ptr [eax], 1
0x1002747c  lea     eax, [esi+10h]
0x1002747f  mov     [esp+90h+var_68], eax
0x10027483  cmp     [esp+90h+var_80], edi
0x10027487  jnz     short loc_100274E8
0x10027489  mov     esi, [eax]
0x1002748b  lea     ecx, [esp+90h+var_60]
0x1002748f  mov     [esp+90h+var_80], ecx
0x10027493  mov     ecx, esi; this
0x10027495  call    ?Initialize@CReplCover@@QAEJXZ; CReplCover::Initialize(void)
0x1002749a  test    eax, eax
0x1002749c  jns     short loc_100274AF
0x1002749e  mov     eax, 0FFFFFBFBh
0x100274a3  mov     edi, 80004005h
0x100274a8  mov     [ebx], eax
0x100274aa  jmp     loc_1002754D
0x100274af  mov     eax, [esi+8]
0x100274b2  mov     esi, [eax+28h]
0x100274b5  lea     eax, [esp+90h+pcbActual]
0x100274b9  push    eax
0x100274ba  push    10h
0x100274bc  lea     eax, [esp+98h+var_60]
0x100274c0  mov     ecx, esi
0x100274c2  push    eax
0x100274c3  push    1
0x100274c5  push    0
0x100274c7  push    [esp+0A4h+var_78]
0x100274cb  push    [esp+0A8h+sesid]
0x100274cf  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100274d5  call    esi
0x100274d7  mov     [ebx], eax
0x100274d9  test    eax, eax
0x100274db  jns     short loc_100274E4
0x100274dd  mov     edi, 80004005h
0x100274e2  jmp     short loc_1002754D
0x100274e4  mov     eax, [esp+90h+var_68]
0x100274e8  mov     esi, [eax]
0x100274ea  mov     ecx, esi; this
0x100274ec  call    ?Initialize@CReplCover@@QAEJXZ; CReplCover::Initialize(void)
0x100274f1  test    eax, eax
0x100274f3  jns     short loc_10027503
0x100274f5  mov     eax, 0FFFFFBFBh
0x100274fa  mov     edi, 80004005h
0x100274ff  mov     [ebx], eax
0x10027501  jmp     short loc_1002754D
0x10027503  mov     eax, [esi+8]
0x10027506  mov     esi, [eax+28h]
0x10027509  lea     eax, [esp+90h+pcbActual]
0x1002750d  push    eax
0x1002750e  push    44h ; 'D'
0x10027510  lea     eax, [esp+98h+var_50]
0x10027514  mov     ecx, esi
0x10027516  push    eax
0x10027517  push    14h
0x10027519  push    [esp+0A0h+var_80]
0x1002751d  push    [esp+0A4h+var_78]
0x10027521  push    [esp+0A8h+sesid]
0x10027525  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002752b  call    esi
0x1002752d  mov     [ebx], eax
0x1002752f  test    eax, eax
0x10027531  jns     short loc_1002753A
0x10027533  mov     edi, 80004005h
0x10027538  jmp     short loc_1002754D
0x1002753a  cmp     [esp+90h+var_4C], edi
0x1002753e  jnz     short loc_10027569
0x10027540  mov     edi, 80004005h
0x10027545  test    eax, eax
0x10027547  jz      loc_100275F1
0x1002754d  push    offset _IID_IReplication; int
0x10027552  push    eax; unsigned int
0x10027553  mov     eax, [esp+98h+var_70]
0x10027557  mov     edx, edi
0x10027559  mov     ecx, [eax+8]
0x1002755c  mov     ecx, [ecx+10h]
0x1002755f  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10027564  jmp     loc_10027622
0x10027569  mov     esi, [esp+90h+sesid]
0x1002756d  push    0; grbit
0x1002756f  push    80000000h; cRow
0x10027574  push    [esp+98h+tableid]; tableid
0x10027578  push    esi; sesid
0x10027579  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1002757f  mov     [ebx], eax
0x10027581  test    eax, eax
0x10027583  jns     short loc_1002758C
0x10027585  mov     edi, 80004005h
0x1002758a  jmp     short loc_1002754D
0x1002758c  cmp     [ebp+arg_4], 12h
0x10027590  jz      short loc_10027599
0x10027592  mov     edi, 80070057h
0x10027597  jmp     short loc_10027545
0x10027599  push    0; pretinfo
0x1002759b  push    0; grbit
0x1002759d  lea     eax, [esp+98h+pcbActual]
0x100275a1  push    eax; pcbActual
0x100275a2  push    4; cbData
0x100275a4  lea     eax, [esp+0A0h+pvData]
0x100275a8  push    eax; pvData
0x100275a9  push    [esp+0A4h+columnid]; columnid
0x100275b0  push    [esp+0A8h+tableid]; tableid
0x100275b4  push    esi; sesid
0x100275b5  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x100275bb  mov     [ebx], eax
0x100275bd  test    eax, eax
0x100275bf  jns     short loc_100275C8
0x100275c1  mov     edi, 80004005h
0x100275c6  jmp     short loc_1002754D
0x100275c8  mov     ecx, [esp+90h+var_6C]
0x100275cc  mov     eax, 3
0x100275d1  mov     [ecx], ax
0x100275d4  cvttss2si eax, [esp+90h+pvData]
0x100275da  mov     [ecx+8], eax
0x100275dd  mov     eax, [ebx]
0x100275df  test    eax, eax
0x100275e1  jns     loc_10027547
0x100275e7  mov     edi, 80004005h
0x100275ec  jmp     loc_1002754D
0x100275f1  test    edi, edi
0x100275f3  jns     short loc_1002762C
0x100275f5  mov     eax, [esp+90h+var_70]
0x100275f9  lea     ecx, [esp+90h+var_6C]
0x100275fd  push    3
0x100275ff  push    4
0x10027601  push    ecx
0x10027602  mov     eax, [eax+8]
0x10027605  push    dword ptr [eax+14h]
0x10027608  push    dword ptr [eax+10h]
0x1002760b  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10027611  test    eax, eax
0x10027613  jnz     short loc_10027622
0x10027615  push    eax; int
0x10027616  push    offset _IID_IReplication; int
0x1002761b  mov     edx, edi
0x1002761d  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10027622  mov     eax, [esp+90h+var_7C]
0x10027626  mov     dword ptr [eax], 0
0x1002762c  mov     eax, [esp+90h+tableid]
0x10027630  cmp     eax, 0FFFFFFFFh
0x10027633  jz      short loc_10027640
0x10027635  push    eax; tableid
0x10027636  push    [esp+94h+sesid]; sesid
0x1002763a  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10027640  mov     ecx, [esp+90h+var_4]
0x10027647  mov     eax, edi
0x10027649  pop     edi
0x1002764a  pop     esi
0x1002764b  pop     ebx
0x1002764c  xor     ecx, esp; StackCookie
0x1002764e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10027653  mov     esp, ebp
0x10027655  pop     ebp
0x10027656  retn    14h
```
