# CImpIReplication::GetTransporterID(ulong,ulong,ushort *,_GUID *,int &)

- ea: `0x10025bf0`
- end: `0x10025e63`
- name: `?GetTransporterID@CImpIReplication@@QAEJKKPAGPAU_GUID@@AAH@Z`
- size: `627`
- prototype: `int __thiscall(CImpIReplication *__hidden this, unsigned int, unsigned int, unsigned __int16 *, struct _GUID *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x10025e70`

## callees

- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10025bf0`
- `0x10027860`
- `0x1004d420`
- `0x1004d5a1`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x10025d41`
- `msvcrt!_wcsicmp` at `0x10025d41`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10025c3f`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10025c3f`
- `msjet40!__imp__JetCloseTable@8` at `0x10025e43`
- `msjet40!__imp__JetCloseTable@8` at `0x10025e43`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10025e17`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10025e17`
- `msjet40!__imp__JetMove@16` at `0x10025d8c`
- `msjet40!__imp__JetMove@16` at `0x10025d8c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10025d0a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10025d6c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10025d0a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10025d6c`

## pseudocode

```c
int __userpurge CImpIReplication::GetTransporterID@<eax>(
        CImpIReplication *this@<ecx>,
        const struct _GUID *a2@<edi>,
        const struct _GUID *a3@<esi>,
        JET_SESID sesid,
        unsigned int a5,
        unsigned __int16 *a6,
        struct _GUID *a7,
        int *a8)
{
  int v8; // ebx
  CReplCover *v9; // esi
  JET_ERR v10; // ecx
  int v11; // esi
  JET_TABLEID v12; // esi
  int v13; // eax
  void *v16; // [esp+4h] [ebp-234h] BYREF
  int *v17; // [esp+8h] [ebp-230h]
  CImpIReplication *v18; // [esp+Ch] [ebp-22Ch]
  unsigned int pcbActual; // [esp+10h] [ebp-228h] BYREF
  JET_TABLEID tableid[4]; // [esp+14h] [ebp-224h] BYREF
  JET_COLUMNID columnid[2]; // [esp+24h] [ebp-214h]
  wchar_t pvData[258]; // [esp+2Ch] [ebp-20Ch] BYREF

  v8 = 0;
  v18 = this;
  v16 = a7;
  v17 = a8;
  *(_OWORD *)tableid = 0;
  *(_QWORD *)columnid = 0;
  SetErrorInfo(0, 0);
  *a8 = 1;
  if ( a6 && a7 )
  {
    tableid[2] = -1;
    v9 = (CReplCover *)*((_DWORD *)v18 + 4);
    if ( CReplCover::Initialize(v9) < 0 )
    {
      v10 = -1029;
      v11 = -2147467259;
LABEL_24:
      CExtError::SendJetErrortoOLEAuto(
        v11,
        *(char **)(*((_DWORD *)v18 + 2) + 16),
        v10,
        (int)&IID_IReplication,
        (int)a2,
        a3);
      *v17 = 0;
      goto LABEL_28;
    }
    v10 = (**((int (__thiscall ***)(_DWORD, JET_SESID, unsigned int, _DWORD, _DWORD, int, JET_TABLEID *, int, unsigned int *))v9
            + 2))(
            **((_DWORD **)v9 + 2),
            sesid,
            a5,
            0,
            0,
            70,
            tableid,
            24,
            &pcbActual);
    if ( v10 < 0 )
    {
LABEL_6:
      v11 = -2147467259;
      goto LABEL_24;
    }
    v12 = 0;
    if ( !tableid[1] )
    {
LABEL_23:
      v10 = -20066;
      v11 = -2147024809;
      goto LABEL_24;
    }
    do
    {
      if ( v10 < 0 )
        break;
      if ( v8 )
        goto LABEL_17;
      v10 = JetRetrieveColumn(sesid, tableid[2], columnid[0], pvData, 0x200u, &pcbActual, 0, 0);
      if ( v10 < 0 )
        goto LABEL_6;
      if ( (pcbActual & 0xFFFFFFFE) >= 0x200 )
        __report_rangecheckfailure();
      *(wchar_t *)((char *)pvData + (pcbActual & 0xFFFFFFFE)) = 0;
      if ( !__wcsicmp(pvData, a6) )
      {
        v10 = JetRetrieveColumn(sesid, tableid[2], tableid[3], v16, 0x10u, &pcbActual, 0, 0);
        if ( v10 < 0 )
          goto LABEL_6;
        v8 = 1;
      }
      ++v12;
      v10 = JetMove(sesid, tableid[2], 1, 0);
    }
    while ( v12 < tableid[1] );
    if ( !v8 )
      goto LABEL_23;
LABEL_17:
    v13 = 0;
    if ( v10 != -1603 )
      v13 = v10;
    v10 = v13;
    if ( v13 < 0 )
    {
      v11 = -2147467259;
      goto LABEL_24;
    }
    v11 = 0;
    v10 = v13;
    if ( v13 )
      goto LABEL_24;
  }
  else
  {
    v11 = -2147024809;
    if ( !JetGetDatabaseInfo(*(_DWORD *)(*((_DWORD *)v18 + 2) + 16), *(_DWORD *)(*((_DWORD *)v18 + 2) + 20), &v16, 4, 3) )
      CExtError::SendHRtoOLEAuto(-2147024809, (__int128 *)&IID_IReplication, 0, a2, (int)a3);
    *v17 = 0;
  }
LABEL_28:
  if ( tableid[2] != -1 )
    JetCloseTable(sesid, tableid[2]);
  return v11;
}

```

## disassembly

```asm
0x10025bf0  mov     edi, edi
0x10025bf2  push    ebp
0x10025bf3  mov     ebp, esp
0x10025bf5  sub     esp, 238h
0x10025bfb  mov     eax, ___security_cookie
0x10025c00  xor     eax, ebp
0x10025c02  mov     [ebp+var_8], eax
0x10025c05  mov     eax, [ebp+arg_10]
0x10025c08  xorps   xmm0, xmm0
0x10025c0b  push    ebx
0x10025c0c  push    esi; int
0x10025c0d  mov     esi, [ebp+arg_C]
0x10025c10  xor     ebx, ebx
0x10025c12  push    edi; struct _GUID *
0x10025c13  mov     edi, [ebp+arg_8]
0x10025c16  push    ebx; perrinfo
0x10025c17  push    ebx; dwReserved
0x10025c18  mov     [ebp+var_22C], ecx
0x10025c1e  mov     [ebp+String2], edi
0x10025c24  mov     [ebp+var_234], esi
0x10025c2a  mov     [ebp+var_230], eax
0x10025c30  movups  xmmword ptr [ebp+tableid], xmm0
0x10025c37  movq    qword ptr [ebp+columnid], xmm0
0x10025c3f  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10025c45  mov     eax, [ebp+var_230]
0x10025c4b  test    edi, edi
0x10025c4d  mov     edi, [ebp+sesid]
0x10025c50  mov     dword ptr [eax], 1
0x10025c56  jz      loc_10025DF8
0x10025c5c  test    esi, esi
0x10025c5e  jz      loc_10025DF8
0x10025c64  mov     esi, [ebp+var_22C]
0x10025c6a  mov     [ebp+tableid+8], 0FFFFFFFFh
0x10025c74  mov     esi, [esi+10h]
0x10025c77  mov     ecx, esi; this
0x10025c79  call    ?Initialize@CReplCover@@QAEJXZ; CReplCover::Initialize(void)
0x10025c7e  test    eax, eax
0x10025c80  jns     short loc_10025C91
0x10025c82  mov     ecx, 0FFFFFBFBh
0x10025c87  mov     esi, 80004005h
0x10025c8c  jmp     loc_10025DD1
0x10025c91  mov     eax, [esi+8]
0x10025c94  mov     esi, [eax]
0x10025c96  lea     eax, [ebp+pcbActual]
0x10025c9c  push    eax
0x10025c9d  push    18h
0x10025c9f  lea     eax, [ebp+tableid]
0x10025ca5  mov     ecx, esi
0x10025ca7  push    eax
0x10025ca8  push    46h ; 'F'
0x10025caa  push    0
0x10025cac  push    0
0x10025cae  push    [ebp+arg_4]
0x10025cb1  push    edi
0x10025cb2  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10025cb8  call    esi
0x10025cba  mov     ecx, eax
0x10025cbc  test    ecx, ecx
0x10025cbe  jns     short loc_10025CCA
0x10025cc0  mov     esi, 80004005h
0x10025cc5  jmp     loc_10025DD1
0x10025cca  xor     esi, esi
0x10025ccc  cmp     [ebp+tableid+4], ebx
0x10025cd2  jbe     loc_10025DC7
0x10025cd8  test    ecx, ecx
0x10025cda  js      loc_10025DA1
0x10025ce0  test    ebx, ebx
0x10025ce2  jnz     loc_10025DA5
0x10025ce8  push    ebx; pretinfo
0x10025ce9  push    ebx; grbit
0x10025cea  lea     eax, [ebp+pcbActual]
0x10025cf0  push    eax; pcbActual
0x10025cf1  push    200h; cbData
0x10025cf6  lea     eax, [ebp+pvData]
0x10025cfc  push    eax; pvData
0x10025cfd  push    [ebp+columnid]; columnid
0x10025d03  push    [ebp+tableid+8]; tableid
0x10025d09  push    edi; sesid
0x10025d0a  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10025d10  mov     ecx, eax
0x10025d12  test    ecx, ecx
0x10025d14  js      short loc_10025CC0
0x10025d16  mov     eax, [ebp+pcbActual]
0x10025d1c  and     eax, 0FFFFFFFEh
0x10025d1f  cmp     eax, 200h
0x10025d24  jnb     loc_10025E5E
0x10025d2a  push    [ebp+String2]; String2
0x10025d30  xor     ecx, ecx
0x10025d32  mov     [ebp+eax+pvData], cx
0x10025d3a  lea     eax, [ebp+pvData]
0x10025d40  push    eax; String1
0x10025d41  call    ds:__imp___wcsicmp
0x10025d47  add     esp, 8
0x10025d4a  test    eax, eax
0x10025d4c  jnz     short loc_10025D81
0x10025d4e  push    eax; pretinfo
0x10025d4f  push    eax; grbit
0x10025d50  lea     eax, [ebp+pcbActual]
0x10025d56  push    eax; pcbActual
0x10025d57  push    10h; cbData
0x10025d59  push    [ebp+var_234]; pvData
0x10025d5f  push    [ebp+tableid+0Ch]; columnid
0x10025d65  push    [ebp+tableid+8]; tableid
0x10025d6b  push    edi; sesid
0x10025d6c  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10025d72  mov     ecx, eax
0x10025d74  test    ecx, ecx
0x10025d76  js      loc_10025CC0
0x10025d7c  mov     ebx, 1
0x10025d81  push    0; grbit
0x10025d83  push    1; cRow
0x10025d85  push    [ebp+tableid+8]; tableid
0x10025d8b  push    edi; sesid
0x10025d8c  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x10025d92  inc     esi
0x10025d93  mov     ecx, eax
0x10025d95  cmp     esi, [ebp+tableid+4]
0x10025d9b  jb      loc_10025CD8
0x10025da1  test    ebx, ebx
0x10025da3  jz      short loc_10025DC7
0x10025da5  xor     eax, eax
0x10025da7  cmp     ecx, 0FFFFF9BDh
0x10025dad  cmovnz  eax, ecx
0x10025db0  mov     ecx, eax
0x10025db2  test    ecx, ecx
0x10025db4  jns     short loc_10025DBD
0x10025db6  mov     esi, 80004005h
0x10025dbb  jmp     short loc_10025DD1
0x10025dbd  xor     esi, esi
0x10025dbf  mov     ecx, eax
0x10025dc1  test    eax, eax
0x10025dc3  jnz     short loc_10025DD1
0x10025dc5  jmp     short loc_10025E36
0x10025dc7  mov     ecx, 0FFFFB19Eh
0x10025dcc  mov     esi, 80070057h
0x10025dd1  mov     eax, [ebp+var_22C]
0x10025dd7  mov     edx, esi
0x10025dd9  push    offset _IID_IReplication; int
0x10025dde  push    ecx; unsigned int
0x10025ddf  mov     ecx, [eax+8]
0x10025de2  mov     ecx, [ecx+10h]
0x10025de5  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10025dea  mov     eax, [ebp+var_230]
0x10025df0  mov     dword ptr [eax], 0
0x10025df6  jmp     short loc_10025E36
0x10025df8  mov     eax, [ebp+var_22C]
0x10025dfe  lea     ecx, [ebp+var_234]
0x10025e04  push    3
0x10025e06  push    4
0x10025e08  push    ecx
0x10025e09  mov     eax, [eax+8]
0x10025e0c  mov     esi, 80070057h
0x10025e11  push    dword ptr [eax+14h]
0x10025e14  push    dword ptr [eax+10h]
0x10025e17  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10025e1d  test    eax, eax
0x10025e1f  jnz     short loc_10025E2E
0x10025e21  push    eax; int
0x10025e22  push    offset _IID_IReplication; int
0x10025e27  mov     edx, esi
0x10025e29  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10025e2e  mov     eax, [ebp+var_230]
0x10025e34  mov     [eax], ebx
0x10025e36  mov     eax, [ebp+tableid+8]
0x10025e3c  cmp     eax, 0FFFFFFFFh
0x10025e3f  jz      short loc_10025E49
0x10025e41  push    eax; tableid
0x10025e42  push    edi; sesid
0x10025e43  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10025e49  mov     ecx, [ebp+var_8]
0x10025e4c  mov     eax, esi
0x10025e4e  pop     edi
0x10025e4f  pop     esi
0x10025e50  xor     ecx, ebp; StackCookie
0x10025e52  pop     ebx
0x10025e53  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10025e58  mov     esp, ebp
0x10025e5a  pop     ebp
0x10025e5b  retn    14h
0x10025e5e  call    ___report_rangecheckfailure
```
