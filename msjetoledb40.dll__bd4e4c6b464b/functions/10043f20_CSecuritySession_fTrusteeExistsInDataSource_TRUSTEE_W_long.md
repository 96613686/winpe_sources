# CSecuritySession::fTrusteeExistsInDataSource(_TRUSTEE_W *,long &)

- ea: `0x10043f20`
- end: `0x10044085`
- name: `?fTrusteeExistsInDataSource@CSecuritySession@@QAEJPAU_TRUSTEE_W@@AAJ@Z`
- size: `357`
- prototype: `int __thiscall(CSecuritySession *__hidden this, struct _TRUSTEE_W *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10040610`
- `0x100429a0`

## callees

- `0x1001e800`
- `0x10043ea0`
- `0x10043f20`

## import_xrefs

- `msjet40!__imp__JetCloseTable@8` at `0x10044074`
- `msjet40!__imp__JetCloseTable@8` at `0x10044074`
- `msjet40!__imp__JetMakeKey@20` at `0x10043fae`
- `msjet40!__imp__JetMakeKey@20` at `0x10043fae`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1004401a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1004401a`
- `msjet40!__imp__JetSeek@12` at `0x10043fcc`
- `msjet40!__imp__JetSeek@12` at `0x10043fcc`
- `msjet40!__imp__JetSetCurrentIndex@12` at `0x10043f66`
- `msjet40!__imp__JetSetCurrentIndex@12` at `0x10043f66`

## pseudocode

```c
int __thiscall CSecuritySession::fTrusteeExistsInDataSource(CSecuritySession *this, struct _TRUSTEE_W *a2, int *a3)
{
  int Colid; // esi
  int v5; // eax
  LPWCH ptstrName; // edx
  unsigned int v7; // ecx
  LPWCH v8; // ecx
  JET_ERR Key; // eax
  JET_ERR v11; // eax
  JET_ERR v12; // eax
  TRUSTEE_TYPE TrusteeType; // eax
  int v14; // eax
  unsigned int v16; // [esp-14h] [ebp-30h]
  unsigned __int16 *v17; // [esp-10h] [ebp-2Ch]
  unsigned int *v18; // [esp+0h] [ebp-1Ch]
  int *v19; // [esp+4h] [ebp-18h]
  unsigned int pcbActual; // [esp+Ch] [ebp-10h] BYREF
  JET_COLUMNID columnid; // [esp+10h] [ebp-Ch] BYREF
  JET_TABLEID tableid; // [esp+14h] [ebp-8h] BYREF
  char pvData; // [esp+1Bh] [ebp-1h] BYREF

  tableid = -1;
  Colid = CJOLT::JOLTJetOpenTable(
            *((_DWORD *)this + 2),
            *((_DWORD *)this + 1),
            (unsigned int)L"MSysAccounts",
            v16,
            v17,
            (const void *)0x20,
            &tableid,
            a3,
            v18,
            v19);
  if ( Colid >= 0 )
  {
    v5 = JetSetCurrentIndex(*((_DWORD *)this + 1), tableid, L"Name");
    *a3 = v5;
    if ( v5 < 0 )
    {
      Colid = -2147467259;
      goto LABEL_28;
    }
    ptstrName = a2->ptstrName;
    if ( ptstrName )
    {
      v8 = a2->ptstrName;
      columnid = (JET_COLUMNID)(ptstrName + 1);
      while ( *v8++ )
        ;
      v7 = 2 * ((int)((int)v8 - columnid) >> 1);
    }
    else
    {
      v7 = 0;
    }
    Key = JetMakeKey(*((_DWORD *)this + 1), tableid, ptstrName, v7, 1u);
    *a3 = Key;
    if ( Key < 0 )
    {
      Colid = -2147467259;
      goto LABEL_28;
    }
    v11 = JetSeek(*((_DWORD *)this + 1), tableid, 1u);
    *a3 = v11;
    if ( v11 == -1601 )
    {
      *a3 = 0;
    }
    else
    {
      if ( v11 )
      {
        Colid = -2147467259;
        goto LABEL_28;
      }
      Colid = CSecuritySession::FindColid(this, tableid, L"fGroup", &columnid, a3);
      if ( Colid >= 0 )
      {
        v12 = JetRetrieveColumn(*((_DWORD *)this + 1), tableid, columnid, &pvData, 1u, &pcbActual, 0, 0);
        *a3 = v12;
        if ( v12 < 0 )
        {
          Colid = -2147467259;
          goto LABEL_28;
        }
        TrusteeType = a2->TrusteeType;
        if ( TrusteeType == TRUSTEE_IS_USER )
        {
          if ( pvData )
          {
LABEL_19:
            v14 = 0;
            goto LABEL_20;
          }
        }
        else if ( TrusteeType != TRUSTEE_IS_GROUP || !pvData )
        {
          goto LABEL_19;
        }
        v14 = 1;
LABEL_20:
        if ( v14 )
          goto LABEL_28;
      }
    }
  }
  if ( !Colid )
    Colid = -2147217813;
LABEL_28:
  if ( tableid != -1 )
    JetCloseTable(*((_DWORD *)this + 1), tableid);
  return Colid;
}

```

## disassembly

```asm
0x10043f20  mov     edi, edi
0x10043f22  push    ebp
0x10043f23  mov     ebp, esp
0x10043f25  sub     esp, 10h
0x10043f28  push    ebx
0x10043f29  push    esi; int *
0x10043f2a  push    edi; unsigned int *
0x10043f2b  mov     edi, [ebp+arg_4]
0x10043f2e  lea     eax, [ebp+tableid]
0x10043f31  push    edi; unsigned int
0x10043f32  push    eax; unsigned int
0x10043f33  push    20h ; ' '; void *
0x10043f35  mov     ebx, ecx
0x10043f37  mov     [ebp+tableid], 0FFFFFFFFh
0x10043f3e  sub     esp, 8
0x10043f41  mov     edx, [ebx+8]
0x10043f44  mov     ecx, [ebx+4]
0x10043f47  push    offset aMsysaccounts; "MSysAccounts"
0x10043f4c  call    ?JOLTJetOpenTable@CJOLT@@SGJKKPAGPBXKKPAKAAJ@Z; CJOLT::JOLTJetOpenTable(ulong,ulong,ushort *,void const *,ulong,ulong,ulong *,long &)
0x10043f51  mov     esi, eax
0x10043f53  test    esi, esi
0x10043f55  js      loc_1004405E
0x10043f5b  push    offset aName; "Name"
0x10043f60  push    [ebp+tableid]
0x10043f63  push    dword ptr [ebx+4]
0x10043f66  call    ds:__imp__JetSetCurrentIndex@12; JetSetCurrentIndex(x,x,x)
0x10043f6c  mov     [edi], eax
0x10043f6e  test    eax, eax
0x10043f70  jns     short loc_10043F7C
0x10043f72  mov     esi, 80004005h
0x10043f77  jmp     loc_10044068
0x10043f7c  mov     edx, [ebp+arg_0]
0x10043f7f  mov     edx, [edx+10h]
0x10043f82  test    edx, edx
0x10043f84  jnz     short loc_10043F8A
0x10043f86  xor     ecx, ecx
0x10043f88  jmp     short loc_10043FA4
0x10043f8a  mov     ecx, edx
0x10043f8c  lea     eax, [ecx+2]
0x10043f8f  mov     [ebp+columnid], eax
0x10043f92  mov     ax, [ecx]
0x10043f95  add     ecx, 2
0x10043f98  test    ax, ax
0x10043f9b  jnz     short loc_10043F92
0x10043f9d  sub     ecx, [ebp+columnid]
0x10043fa0  sar     ecx, 1
0x10043fa2  add     ecx, ecx
0x10043fa4  push    1; grbit
0x10043fa6  push    ecx; cbData
0x10043fa7  push    edx; pvData
0x10043fa8  push    [ebp+tableid]; tableid
0x10043fab  push    dword ptr [ebx+4]; sesid
0x10043fae  call    ds:__imp__JetMakeKey@20; JetMakeKey(x,x,x,x,x)
0x10043fb4  mov     [edi], eax
0x10043fb6  test    eax, eax
0x10043fb8  jns     short loc_10043FC4
0x10043fba  mov     esi, 80004005h
0x10043fbf  jmp     loc_10044068
0x10043fc4  push    1; grbit
0x10043fc6  push    [ebp+tableid]; tableid
0x10043fc9  push    dword ptr [ebx+4]; sesid
0x10043fcc  call    ds:__imp__JetSeek@12; JetSeek(x,x,x)
0x10043fd2  mov     [edi], eax
0x10043fd4  cmp     eax, 0FFFFF9BFh
0x10043fd9  jz      short loc_10044058
0x10043fdb  test    eax, eax
0x10043fdd  jz      short loc_10043FE9
0x10043fdf  mov     esi, 80004005h
0x10043fe4  jmp     loc_10044068
0x10043fe9  push    edi; int *
0x10043fea  lea     eax, [ebp+columnid]
0x10043fed  mov     ecx, ebx; this
0x10043fef  push    eax; unsigned int *
0x10043ff0  push    offset aFgroup; "fGroup"
0x10043ff5  push    [ebp+tableid]; unsigned int
0x10043ff8  call    ?FindColid@CSecuritySession@@QAEJKPBGAAKAAJ@Z; CSecuritySession::FindColid(ulong,ushort const *,ulong &,long &)
0x10043ffd  mov     esi, eax
0x10043fff  test    esi, esi
0x10044001  js      short loc_1004405E
0x10044003  push    0; pretinfo
0x10044005  push    0; grbit
0x10044007  lea     eax, [ebp+pcbActual]
0x1004400a  push    eax; pcbActual
0x1004400b  push    1; cbData
0x1004400d  lea     eax, [ebp+pvData]
0x10044010  push    eax; pvData
0x10044011  push    [ebp+columnid]; columnid
0x10044014  push    [ebp+tableid]; tableid
0x10044017  push    dword ptr [ebx+4]; sesid
0x1004401a  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10044020  mov     [edi], eax
0x10044022  test    eax, eax
0x10044024  jns     short loc_1004402D
0x10044026  mov     esi, 80004005h
0x1004402b  jmp     short loc_10044068
0x1004402d  mov     eax, [ebp+arg_0]
0x10044030  mov     eax, [eax+0Ch]
0x10044033  cmp     eax, 1
0x10044036  jnz     short loc_10044046
0x10044038  cmp     [ebp+pvData], 0
0x1004403c  jz      short loc_10044051
0x1004403e  xor     eax, eax
0x10044040  test    eax, eax
0x10044042  jnz     short loc_10044068
0x10044044  jmp     short loc_1004405E
0x10044046  cmp     eax, 2
0x10044049  jnz     short loc_1004403E
0x1004404b  cmp     [ebp+pvData], 0
0x1004404f  jz      short loc_1004403E
0x10044051  mov     eax, 1
0x10044056  jmp     short loc_10044040
0x10044058  mov     dword ptr [edi], 0
0x1004405e  test    esi, esi
0x10044060  mov     eax, 80040E6Bh
0x10044065  cmovz   esi, eax
0x10044068  mov     eax, [ebp+tableid]
0x1004406b  cmp     eax, 0FFFFFFFFh
0x1004406e  jz      short loc_1004407A
0x10044070  push    eax; tableid
0x10044071  push    dword ptr [ebx+4]; sesid
0x10044074  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x1004407a  pop     edi
0x1004407b  mov     eax, esi
0x1004407d  pop     esi
0x1004407e  pop     ebx
0x1004407f  mov     esp, ebp
0x10044081  pop     ebp
0x10044082  retn    8
```
