# CImpIJetCompact::Compact(ulong,tagDBPROPSET * const)

- ea: `0x1001ebc0`
- end: `0x1001ee6c`
- name: `?Compact@CImpIJetCompact@@UAGJKQAUtagDBPROPSET@@@Z`
- size: `684`
- prototype: `int(CImpIJetCompact *__hidden this, unsigned int, struct tagDBPROPSET *const)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1000ba90`
- `0x1000e8d0`
- `0x10019cd0`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001ebc0`
- `0x1001fd10`
- `0x100202a0`
- `0x10020410`
- `0x100204c0`
- `0x100205d0`
- `0x100207d0`
- `0x10020c90`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1001ee48`
- `KERNEL32!LeaveCriticalSection` at `0x1001ee48`
- `KERNEL32!EnterCriticalSection` at `0x1001ec53`
- `KERNEL32!EnterCriticalSection` at `0x1001ec53`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001ec43`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001ec43`
- `msjet40!__imp__JetCloseDatabase@12` at `0x1001ed6d`
- `msjet40!__imp__JetCloseDatabase@12` at `0x1001ed6d`
- `msjet40!__imp__JetCompact@28` at `0x1001eda1`
- `msjet40!__imp__JetCompact@28` at `0x1001eda1`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001ee0c`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001ee0c`

## pseudocode

```c
int __stdcall CImpIJetCompact::Compact(CImpIJetCompact *this, unsigned int a2, struct tagDBPROPSET *const a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // esi
  int v4; // edi
  int v5; // ecx
  CDataSource *v6; // ecx
  CDataSource *v7; // ecx
  int v8; // ebx
  JET_DBID v9; // eax
  JET_ERR v10; // eax
  void *v11; // ebx
  struct CDBInitProperties *v13; // [esp+0h] [ebp-48h]
  struct _GUID *v14; // [esp+4h] [ebp-44h]
  _DWORD v15[2]; // [esp+10h] [ebp-38h] BYREF
  JoltProperties *v16; // [esp+18h] [ebp-30h]
  int v17; // [esp+1Ch] [ebp-2Ch]
  LPCRITICAL_SECTION v18; // [esp+20h] [ebp-28h]
  unsigned __int16 *v19; // [esp+24h] [ebp-24h] BYREF
  unsigned __int16 *v20; // [esp+28h] [ebp-20h] BYREF
  int v21; // [esp+2Ch] [ebp-1Ch]
  unsigned __int16 *v22; // [esp+30h] [ebp-18h] BYREF
  JET_SESID sesid; // [esp+34h] [ebp-14h]
  void *Block; // [esp+38h] [ebp-10h] BYREF
  int v25; // [esp+44h] [ebp-4h]

  v21 = 0;
  sesid = *(_DWORD *)(*((_DWORD *)this + 2) + 144);
  v15[1] = 0;
  v16 = 0;
  v17 = 0;
  v15[0] = &CDBDataSourceAdmin::`vftable';
  v25 = 0;
  Block = 0;
  v22 = 0;
  v19 = 0;
  v20 = 0;
  SetErrorInfo(0, 0);
  v18 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 100);
  v3 = v18;
  EnterCriticalSection(v18);
  LOBYTE(v25) = 1;
  if ( a2 && !a3 )
  {
LABEL_3:
    v4 = -2147024809;
    goto LABEL_32;
  }
  v5 = 0;
  if ( a2 )
  {
    while ( !a3[v5].cProperties || a3[v5].rgProperties )
    {
      if ( ++v5 >= a2 )
        goto LABEL_8;
    }
    goto LABEL_3;
  }
LABEL_8:
  v4 = CSettableProperties::FInit((CSettableProperties *)v15);
  if ( v4 >= 0 )
  {
    v4 = CSettableProperties::CopyFrom(
           (CSettableProperties *)v15,
           (const struct CSettableProperties *)(*((_DWORD *)this + 2) + 152));
    if ( v4 >= 0 )
    {
      v4 = CSettableProperties::SetPropertiesToTemplateRW((CSettableProperties *)v15);
      if ( v4 >= 0 )
      {
        v4 = CSettableProperties::SetProperties((CSettableProperties *)v15, a2, a3, 0);
        if ( v4 >= 0 )
        {
          v4 = CDataSource::BuildConnectString(
                 v6,
                 (unsigned __int16 **)&Block,
                 (struct CDBInitProperties *)(*((_DWORD *)this + 2) + 152));
          if ( v4 >= 0 )
          {
            v4 = CDataSource::BuildConnectString(v7, &v22, (struct CDBInitProperties *)v15);
            if ( v4 >= 0 )
            {
              v8 = *((_DWORD *)this + 2);
              JoltProperties::GetStrValue(*(JoltProperties **)(v8 + 160), 0x3Bu, &v19);
              JoltProperties::GetStrValue(v16, 0x3Bu, &v20);
              v4 = ValidateStateForJetCompact(v13, &v14->Data1);
              if ( v4 >= 0 )
              {
                v9 = *(_DWORD *)(v8 + 148);
                if ( v9 != -1 )
                {
                  v10 = JetCloseDatabase(sesid, v9, 0);
                  if ( v10 < 0 )
                  {
                    v11 = Block;
LABEL_29:
                    v4 = -2147467259;
                    goto LABEL_30;
                  }
                  *(_DWORD *)(*((_DWORD *)this + 2) + 148) = -1;
                }
                v11 = Block;
                v10 = JetCompact(sesid, v19, Block, v20, v22, 0, v21);
                if ( v10 > -1032 )
                {
                  if ( v10 != -1003 )
                  {
                    if ( !v10 )
                      goto LABEL_35;
                    if ( v10 >= 0 )
                      goto LABEL_30;
                  }
                  goto LABEL_29;
                }
                switch ( v10 )
                {
                  case -1032:
                    v4 = -2147217911;
                    break;
                  case -1202:
                    v4 = -2147217915;
                    break;
                  case -1201:
                    v4 = -2147217897;
                    break;
                  default:
                    goto LABEL_29;
                }
LABEL_30:
                CExtError::SendJetErrortoOLEAuto(v4, (char *)sesid, v10, (int)&IID_IJetCompact, (int)v13, v14);
                goto LABEL_35;
              }
            }
          }
        }
      }
    }
  }
  if ( v4 != -2147024882 )
  {
LABEL_32:
    if ( !JetGetDatabaseInfo(sesid, -1, &v19, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_IJetCompact, 0, (const struct _GUID *)v13, (int)v14);
  }
  v11 = Block;
LABEL_35:
  if ( v11 )
    operator delete(v11);
  if ( v22 )
    operator delete(v22);
  if ( v3 )
    LeaveCriticalSection(v3);
  CSettableProperties::~CSettableProperties((CSettableProperties *)v15);
  return v4;
}

```

## disassembly

```asm
0x1001ebc0  mov     edi, edi
0x1001ebc2  push    ebp
0x1001ebc3  mov     ebp, esp
0x1001ebc5  push    0FFFFFFFFh
0x1001ebc7  push    offset ?Compact@CImpIJetCompact@@UAGJKQAUtagDBPROPSET@@@Z_SEH
0x1001ebcc  mov     eax, large fs:0
0x1001ebd2  push    eax
0x1001ebd3  sub     esp, 2Ch
0x1001ebd6  push    ebx
0x1001ebd7  push    esi
0x1001ebd8  push    edi; int
0x1001ebd9  mov     eax, ___security_cookie
0x1001ebde  xor     eax, ebp
0x1001ebe0  push    eax; struct _GUID *
0x1001ebe1  lea     eax, [ebp+var_C]
0x1001ebe4  mov     large fs:0, eax
0x1001ebea  mov     ebx, [ebp+this]
0x1001ebed  mov     [ebp+var_1C], 0
0x1001ebf4  mov     eax, [ebx+8]
0x1001ebf7  mov     eax, [eax+90h]
0x1001ebfd  mov     [ebp+sesid], eax
0x1001ec00  mov     [ebp+var_34], 0
0x1001ec07  mov     [ebp+var_30], 0
0x1001ec0e  mov     [ebp+var_2C], 0
0x1001ec15  mov     [ebp+var_38], offset ??_7CDBDataSourceAdmin@@6B@; const CDBDataSourceAdmin::`vftable'
0x1001ec1c  mov     [ebp+var_4], 0
0x1001ec23  push    0; perrinfo
0x1001ec25  push    0; dwReserved
0x1001ec27  mov     [ebp+Block], 0
0x1001ec2e  mov     [ebp+var_18], 0
0x1001ec35  mov     [ebp+var_24], 0
0x1001ec3c  mov     [ebp+var_20], 0
0x1001ec43  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1001ec49  mov     esi, [ebx+8]
0x1001ec4c  add     esi, 64h ; 'd'
0x1001ec4f  push    esi; lpCriticalSection
0x1001ec50  mov     [ebp+var_28], esi
0x1001ec53  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001ec59  mov     ebx, [ebp+arg_4]
0x1001ec5c  mov     edx, [ebp+arg_8]
0x1001ec5f  mov     byte ptr [ebp+var_4], 1
0x1001ec63  test    ebx, ebx
0x1001ec65  jz      short loc_1001EC75
0x1001ec67  test    edx, edx
0x1001ec69  jnz     short loc_1001EC75
0x1001ec6b  mov     edi, 80070057h
0x1001ec70  jmp     loc_1001EDFF
0x1001ec75  xor     ecx, ecx
0x1001ec77  test    ebx, ebx
0x1001ec79  jz      short loc_1001EC95
0x1001ec7b  nop     dword ptr [eax+eax+00h]
0x1001ec80  lea     eax, [ecx+ecx*2]
0x1001ec83  cmp     dword ptr [edx+eax*8+4], 0
0x1001ec88  jz      short loc_1001EC90
0x1001ec8a  cmp     dword ptr [edx+eax*8], 0
0x1001ec8e  jz      short loc_1001EC6B
0x1001ec90  inc     ecx
0x1001ec91  cmp     ecx, ebx
0x1001ec93  jb      short loc_1001EC80
0x1001ec95  lea     ecx, [ebp+var_38]; this
0x1001ec98  call    ?FInit@CSettableProperties@@QAEJXZ; CSettableProperties::FInit(void)
0x1001ec9d  mov     edi, eax
0x1001ec9f  test    edi, edi
0x1001eca1  js      loc_1001EDF7
0x1001eca7  mov     eax, [ebp+this]
0x1001ecaa  lea     ecx, [ebp+var_38]; this
0x1001ecad  mov     eax, [eax+8]
0x1001ecb0  add     eax, 98h
0x1001ecb5  push    eax; struct CSettableProperties *
0x1001ecb6  call    ?CopyFrom@CSettableProperties@@QAEJABV1@@Z; CSettableProperties::CopyFrom(CSettableProperties const &)
0x1001ecbb  mov     edi, eax
0x1001ecbd  test    edi, edi
0x1001ecbf  js      loc_1001EDF7
0x1001ecc5  lea     ecx, [ebp+var_38]; this
0x1001ecc8  call    ?SetPropertiesToTemplateRW@CSettableProperties@@QAEJXZ; CSettableProperties::SetPropertiesToTemplateRW(void)
0x1001eccd  mov     edi, eax
0x1001eccf  test    edi, edi
0x1001ecd1  js      loc_1001EDF7
0x1001ecd7  push    0; struct CDBSession *
0x1001ecd9  push    [ebp+arg_8]; struct tagDBPROPSET *
0x1001ecdc  lea     ecx, [ebp+var_38]; this
0x1001ecdf  push    ebx; unsigned int
0x1001ece0  call    ?SetProperties@CSettableProperties@@QAEJKPAUtagDBPROPSET@@PAVCDBSession@@@Z; CSettableProperties::SetProperties(ulong,tagDBPROPSET *,CDBSession *)
0x1001ece5  mov     edi, eax
0x1001ece7  test    edi, edi
0x1001ece9  js      loc_1001EDF7
0x1001ecef  mov     ebx, [ebp+this]
0x1001ecf2  mov     eax, [ebx+8]
0x1001ecf5  add     eax, 98h
0x1001ecfa  push    eax; struct CDBInitProperties *
0x1001ecfb  lea     eax, [ebp+Block]
0x1001ecfe  push    eax; unsigned __int16 **
0x1001ecff  call    ?BuildConnectString@CDataSource@@QAEJAAPAGAAVCDBInitProperties@@@Z; CDataSource::BuildConnectString(ushort * &,CDBInitProperties &)
0x1001ed04  mov     edi, eax
0x1001ed06  test    edi, edi
0x1001ed08  js      loc_1001EDF7
0x1001ed0e  lea     eax, [ebp+var_38]
0x1001ed11  push    eax; struct CDBInitProperties *
0x1001ed12  lea     eax, [ebp+var_18]
0x1001ed15  push    eax; unsigned __int16 **
0x1001ed16  call    ?BuildConnectString@CDataSource@@QAEJAAPAGAAVCDBInitProperties@@@Z; CDataSource::BuildConnectString(ushort * &,CDBInitProperties &)
0x1001ed1b  mov     edi, eax
0x1001ed1d  test    edi, edi
0x1001ed1f  js      loc_1001EDF7
0x1001ed25  mov     ebx, [ebx+8]
0x1001ed28  lea     eax, [ebp+var_24]
0x1001ed2b  push    eax; unsigned __int16 **
0x1001ed2c  push    3Bh ; ';'; unsigned int
0x1001ed2e  mov     ecx, [ebx+0A0h]; this
0x1001ed34  call    ?GetStrValue@JoltProperties@@QBEJKAAPAG@Z; JoltProperties::GetStrValue(ulong,ushort * &)
0x1001ed39  mov     ecx, [ebp+var_30]; this
0x1001ed3c  lea     eax, [ebp+var_20]
0x1001ed3f  push    eax; unsigned __int16 **
0x1001ed40  push    3Bh ; ';'; unsigned int
0x1001ed42  call    ?GetStrValue@JoltProperties@@QBEJKAAPAG@Z; JoltProperties::GetStrValue(ulong,ushort * &)
0x1001ed47  lea     edx, [ebp+var_1C]
0x1001ed4a  lea     ecx, [ebp+var_38]
0x1001ed4d  call    ?ValidateStateForJetCompact@@YGJPAVCDBInitProperties@@AAK@Z; ValidateStateForJetCompact(CDBInitProperties *,ulong &)
0x1001ed52  mov     edi, eax
0x1001ed54  test    edi, edi
0x1001ed56  js      loc_1001EDF7
0x1001ed5c  mov     eax, [ebx+94h]
0x1001ed62  cmp     eax, 0FFFFFFFFh
0x1001ed65  jz      short loc_1001ED8C
0x1001ed67  push    0; grbit
0x1001ed69  push    eax; dbid
0x1001ed6a  push    [ebp+sesid]; sesid
0x1001ed6d  call    ds:__imp__JetCloseDatabase@12; JetCloseDatabase(x,x,x)
0x1001ed73  test    eax, eax
0x1001ed75  jns     short loc_1001ED7C
0x1001ed77  mov     ebx, [ebp+Block]
0x1001ed7a  jmp     short loc_1001EDE0
0x1001ed7c  mov     eax, [ebp+this]
0x1001ed7f  mov     eax, [eax+8]
0x1001ed82  mov     dword ptr [eax+94h], 0FFFFFFFFh
0x1001ed8c  push    [ebp+var_1C]
0x1001ed8f  mov     ebx, [ebp+Block]
0x1001ed92  push    0
0x1001ed94  push    [ebp+var_18]
0x1001ed97  push    [ebp+var_20]
0x1001ed9a  push    ebx
0x1001ed9b  push    [ebp+var_24]
0x1001ed9e  push    [ebp+sesid]
0x1001eda1  call    ds:__imp__JetCompact@28; JetCompact(x,x,x,x,x,x,x)
0x1001eda7  cmp     eax, 0FFFFFBF8h
0x1001edac  jg      short loc_1001EDD3
0x1001edae  jz      short loc_1001EDCC
0x1001edb0  cmp     eax, 0FFFFFB4Eh
0x1001edb5  jz      short loc_1001EDC5
0x1001edb7  cmp     eax, 0FFFFFB4Fh
0x1001edbc  jnz     short loc_1001EDE0
0x1001edbe  mov     edi, 80040E17h
0x1001edc3  jmp     short loc_1001EDE5
0x1001edc5  mov     edi, 80040E05h
0x1001edca  jmp     short loc_1001EDE5
0x1001edcc  mov     edi, 80040E09h
0x1001edd1  jmp     short loc_1001EDE5
0x1001edd3  cmp     eax, 0FFFFFC15h
0x1001edd8  jz      short loc_1001EDE0
0x1001edda  test    eax, eax
0x1001eddc  jz      short loc_1001EE26
0x1001edde  jns     short loc_1001EDE5
0x1001ede0  mov     edi, 80004005h
0x1001ede5  mov     ecx, [ebp+sesid]
0x1001ede8  mov     edx, edi
0x1001edea  push    offset _IID_IJetCompact; int
0x1001edef  push    eax; unsigned int
0x1001edf0  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1001edf5  jmp     short loc_1001EE26
0x1001edf7  cmp     edi, 8007000Eh
0x1001edfd  jz      short loc_1001EE23
0x1001edff  push    3
0x1001ee01  push    4
0x1001ee03  lea     eax, [ebp+var_24]
0x1001ee06  push    eax
0x1001ee07  push    0FFFFFFFFh
0x1001ee09  push    [ebp+sesid]
0x1001ee0c  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1001ee12  test    eax, eax
0x1001ee14  jnz     short loc_1001EE23
0x1001ee16  push    eax; int
0x1001ee17  push    offset _IID_IJetCompact; int
0x1001ee1c  mov     edx, edi
0x1001ee1e  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1001ee23  mov     ebx, [ebp+Block]
0x1001ee26  test    ebx, ebx
0x1001ee28  jz      short loc_1001EE33
0x1001ee2a  push    ebx; Block
0x1001ee2b  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001ee30  add     esp, 4
0x1001ee33  mov     eax, [ebp+var_18]
0x1001ee36  test    eax, eax
0x1001ee38  jz      short loc_1001EE43
0x1001ee3a  push    eax; Block
0x1001ee3b  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001ee40  add     esp, 4
0x1001ee43  test    esi, esi
0x1001ee45  jz      short loc_1001EE4E
0x1001ee47  push    esi; lpCriticalSection
0x1001ee48  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001ee4e  lea     ecx, [ebp+var_38]; this
0x1001ee51  call    ??1CSettableProperties@@UAE@XZ; CSettableProperties::~CSettableProperties(void)
0x1001ee56  mov     eax, edi
0x1001ee58  mov     ecx, [ebp+var_C]
0x1001ee5b  mov     large fs:0, ecx
0x1001ee62  pop     ecx
0x1001ee63  pop     edi
0x1001ee64  pop     esi
0x1001ee65  pop     ebx
0x1001ee66  mov     esp, ebp
0x1001ee68  pop     ebp
0x1001ee69  retn    0Ch
0x1004e6d0  lea     ecx, [ebp+var_38]; this
0x1004e6d3  jmp     ??1CTableProperties@@UAE@XZ; CTableProperties::~CTableProperties(void)
0x1004e6d8  lea     ecx, [ebp+var_28]; this
0x1004e6db  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004e6e5  nop
0x1004e6e6  nop
0x1004e6e7  mov     edx, [esp-4+arg_4]
0x1004e6eb  lea     eax, [edx+0Ch]
0x1004e6ee  mov     ecx, [edx-3Ch]
0x1004e6f1  xor     ecx, eax; StackCookie
0x1004e6f3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e6f8  mov     eax, offset stru_1004FA80
0x1004e6fd  jmp     ___CxxFrameHandler3
```
