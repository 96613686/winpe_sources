# CImpICommandPrepare::Unprepare(void)

- ea: `0x10010f80`
- end: `0x10011123`
- name: `?Unprepare@CImpICommandPrepare@@UAGJXZ`
- size: `419`
- prototype: `int(CImpICommandPrepare *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1000ba90`
- `0x10010f80`
- `0x100147f0`
- `0x10016e10`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x100496d0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10011107`
- `KERNEL32!LeaveCriticalSection` at `0x10011107`
- `KERNEL32!EnterCriticalSection` at `0x10010fd3`
- `KERNEL32!EnterCriticalSection` at `0x10010fd3`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10010fc0`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10010fc0`
- `msjet40!__imp__JetCloseTable@8` at `0x10011022`
- `msjet40!__imp__JetCloseTable@8` at `0x10011022`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100110eb`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100110eb`

## pseudocode

```c
int __stdcall CImpICommandPrepare::Unprepare(CImpICommandPrepare *this)
{
  CImpICommandPrepare *v1; // edi
  int v2; // ebx
  struct _RTL_CRITICAL_SECTION *v3; // esi
  _DWORD *v4; // ecx
  int v5; // eax
  int v6; // edx
  int v7; // eax
  int v8; // eax
  JET_ERR v9; // eax
  JET_ERR v10; // ebx
  JET_SESID v11; // eax
  int v12; // eax
  const struct _GUID *v14; // [esp+0h] [ebp-28h]
  const struct _GUID *v15; // [esp+4h] [ebp-24h]
  JET_SESID sesid; // [esp+14h] [ebp-14h] BYREF
  JET_ERR v17; // [esp+18h] [ebp-10h]
  int v18; // [esp+24h] [ebp-4h]

  v1 = this;
  v2 = 0;
  v17 = 0;
  sesid = *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 52) + 16);
  SetErrorInfo(0, 0);
  v3 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 248);
  EnterCriticalSection(v3);
  v18 = 0;
  v4 = (_DWORD *)*((_DWORD *)this + 2);
  if ( v4[24] )
  {
LABEL_5:
    v8 = *((_DWORD *)this + 2);
    if ( (*(_BYTE *)(v8 + 60) & 0x10) != 0 )
    {
      if ( *(_DWORD *)(v8 + 100) != -1 )
      {
        if ( !*(_DWORD *)(v8 + 96) )
        {
          v9 = JetCloseTable(sesid, *(_DWORD *)(v8 + 100));
          v10 = v9;
          v17 = v9;
          if ( v9 == -1108 )
          {
            if ( CDBSession::AddJetTableId(
                   *(CDBSession **)(*((_DWORD *)this + 2) + 52),
                   *(_DWORD *)(*((_DWORD *)this + 2) + 100)) >= 0 )
              v10 = 0;
            v17 = v10;
          }
          else if ( v9 )
          {
            v2 = -2147467259;
LABEL_19:
            CExtError::SendJetErrortoOLEAuto(
              v2,
              *(char **)(*(_DWORD *)(*((_DWORD *)v1 + 2) + 52) + 16),
              v9,
              (int)&IID_ICommandPrepare,
              (int)v14,
              v15);
            goto LABEL_24;
          }
        }
        *(_DWORD *)(*((_DWORD *)this + 2) + 100) = -1;
      }
      *(_DWORD *)(*((_DWORD *)this + 2) + 60) &= ~0x10u;
      v2 = CJetParameterList::PurgeParameters((CJetParameterList *)(*((_DWORD *)this + 2) + 84));
      if ( v2 >= 0 )
      {
        v11 = *(_DWORD *)(*((_DWORD *)this + 2) + 104);
        sesid = v11;
        if ( v11 )
        {
          (*(void (__thiscall **)(JET_SESID, int))(*(_DWORD *)v11 + 4))(sesid, 1);
          v1 = this;
          *(_DWORD *)(*((_DWORD *)this + 2) + 104) = 0;
        }
      }
      v9 = v17;
      if ( v17 )
        goto LABEL_19;
    }
    if ( v2 >= 0 )
      goto LABEL_24;
    v12 = *(_DWORD *)(*((_DWORD *)v1 + 2) + 52);
    v6 = *(_DWORD *)(v12 + 20);
    v7 = *(_DWORD *)(v12 + 16);
    if ( v2 == -2147024882 )
      goto LABEL_24;
    goto LABEL_22;
  }
  if ( !v4[20] )
  {
    v2 = CCommand::CheckForZombieCommandAndFix((int)v4);
    goto LABEL_5;
  }
  v5 = v4[13];
  v2 = -2147217915;
  v6 = *(_DWORD *)(v5 + 20);
  v7 = *(_DWORD *)(v5 + 16);
LABEL_22:
  if ( !JetGetDatabaseInfo(v7, v6, &sesid, 4, 3) )
    CExtError::SendHRtoOLEAuto(v2, (__int128 *)&IID_ICommandPrepare, 0, v14, (int)v15);
LABEL_24:
  if ( v3 )
    LeaveCriticalSection(v3);
  return v2;
}

```

## disassembly

```asm
0x10010f80  mov     edi, edi
0x10010f82  push    ebp
0x10010f83  mov     ebp, esp
0x10010f85  push    0FFFFFFFFh
0x10010f87  push    offset ?DropColumn@CImpITableDef@@UAGJPAUtagDBID@@0@Z_SEH
0x10010f8c  mov     eax, large fs:0
0x10010f92  push    eax
0x10010f93  sub     esp, 0Ch
0x10010f96  push    ebx
0x10010f97  push    esi
0x10010f98  push    edi; int
0x10010f99  mov     eax, ___security_cookie
0x10010f9e  xor     eax, ebp
0x10010fa0  push    eax; struct _GUID *
0x10010fa1  lea     eax, [ebp+var_C]
0x10010fa4  mov     large fs:0, eax
0x10010faa  mov     edi, [ebp+this]
0x10010fad  xor     ebx, ebx
0x10010faf  push    ebx; perrinfo
0x10010fb0  push    ebx; dwReserved
0x10010fb1  mov     [ebp+var_10], ebx
0x10010fb4  mov     eax, [edi+8]
0x10010fb7  mov     eax, [eax+34h]
0x10010fba  mov     eax, [eax+10h]
0x10010fbd  mov     [ebp+sesid], eax
0x10010fc0  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10010fc6  mov     esi, [edi+8]
0x10010fc9  add     esi, 0F8h
0x10010fcf  push    esi; lpCriticalSection
0x10010fd0  mov     [ebp+var_18], esi
0x10010fd3  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10010fd9  mov     [ebp+var_4], ebx
0x10010fdc  mov     ecx, [edi+8]
0x10010fdf  cmp     [ecx+60h], ebx
0x10010fe2  jnz     short loc_10011003
0x10010fe4  cmp     [ecx+50h], ebx
0x10010fe7  jbe     short loc_10010FFC
0x10010fe9  mov     eax, [ecx+34h]
0x10010fec  mov     ebx, 80040E05h
0x10010ff1  mov     edx, [eax+14h]
0x10010ff4  mov     eax, [eax+10h]
0x10010ff7  jmp     loc_100110E1
0x10010ffc  call    ?CheckForZombieCommandAndFix@CCommand@@QAGJXZ; CCommand::CheckForZombieCommandAndFix(void)
0x10011001  mov     ebx, eax
0x10011003  mov     eax, [edi+8]
0x10011006  test    byte ptr [eax+3Ch], 10h
0x1001100a  jz      loc_100110C7
0x10011010  mov     ecx, [eax+64h]
0x10011013  cmp     ecx, 0FFFFFFFFh
0x10011016  jz      short loc_10011062
0x10011018  cmp     dword ptr [eax+60h], 0
0x1001101c  jnz     short loc_10011058
0x1001101e  push    ecx; tableid
0x1001101f  push    [ebp+sesid]; sesid
0x10011022  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10011028  mov     ebx, eax
0x1001102a  mov     [ebp+var_10], ebx
0x1001102d  cmp     ebx, 0FFFFFBACh
0x10011033  jz      short loc_10011040
0x10011035  test    ebx, ebx
0x10011037  jz      short loc_10011058
0x10011039  mov     ebx, 80004005h
0x1001103e  jmp     short loc_100110AF
0x10011040  mov     eax, [edi+8]
0x10011043  push    dword ptr [eax+64h]; unsigned int
0x10011046  mov     ecx, [eax+34h]; this
0x10011049  call    ?AddJetTableId@CDBSession@@QAEJK@Z; CDBSession::AddJetTableId(ulong)
0x1001104e  xor     ecx, ecx
0x10011050  test    eax, eax
0x10011052  cmovns  ebx, ecx
0x10011055  mov     [ebp+var_10], ebx
0x10011058  mov     eax, [edi+8]
0x1001105b  mov     dword ptr [eax+64h], 0FFFFFFFFh
0x10011062  mov     eax, [edi+8]
0x10011065  and     dword ptr [eax+3Ch], 0FFFFFFEFh
0x10011069  mov     ecx, [edi+8]
0x1001106c  add     ecx, 54h ; 'T'; this
0x1001106f  call    ?PurgeParameters@CJetParameterList@@QAEJXZ; CJetParameterList::PurgeParameters(void)
0x10011074  mov     ebx, eax
0x10011076  test    ebx, ebx
0x10011078  js      short loc_100110A8
0x1001107a  mov     eax, [edi+8]
0x1001107d  mov     eax, [eax+68h]
0x10011080  mov     [ebp+sesid], eax
0x10011083  test    eax, eax
0x10011085  jz      short loc_100110A8
0x10011087  mov     eax, [eax]
0x10011089  push    1
0x1001108b  mov     edi, [eax+4]
0x1001108e  mov     ecx, edi
0x10011090  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10011096  mov     ecx, [ebp+sesid]
0x10011099  call    edi
0x1001109b  mov     edi, [ebp+this]
0x1001109e  mov     eax, [edi+8]
0x100110a1  mov     dword ptr [eax+68h], 0
0x100110a8  mov     eax, [ebp+var_10]
0x100110ab  test    eax, eax
0x100110ad  jz      short loc_100110C7
0x100110af  push    offset _IID_ICommandPrepare; int
0x100110b4  push    eax; unsigned int
0x100110b5  mov     eax, [edi+8]
0x100110b8  mov     edx, ebx
0x100110ba  mov     ecx, [eax+34h]
0x100110bd  mov     ecx, [ecx+10h]
0x100110c0  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x100110c5  jmp     short loc_10011102
0x100110c7  mov     ecx, ebx
0x100110c9  test    ebx, ebx
0x100110cb  jns     short loc_10011102
0x100110cd  mov     eax, [edi+8]
0x100110d0  mov     eax, [eax+34h]
0x100110d3  mov     edx, [eax+14h]
0x100110d6  mov     eax, [eax+10h]
0x100110d9  cmp     ecx, 8007000Eh
0x100110df  jz      short loc_10011102
0x100110e1  push    3
0x100110e3  push    4
0x100110e5  lea     ecx, [ebp+sesid]
0x100110e8  push    ecx
0x100110e9  push    edx
0x100110ea  push    eax
0x100110eb  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x100110f1  test    eax, eax
0x100110f3  jnz     short loc_10011102
0x100110f5  push    eax; int
0x100110f6  push    offset _IID_ICommandPrepare; int
0x100110fb  mov     edx, ebx
0x100110fd  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10011102  test    esi, esi
0x10011104  jz      short loc_1001110D
0x10011106  push    esi; lpCriticalSection
0x10011107  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001110d  mov     eax, ebx
0x1001110f  mov     ecx, [ebp+var_C]
0x10011112  mov     large fs:0, ecx
0x10011119  pop     ecx
0x1001111a  pop     edi
0x1001111b  pop     esi
0x1001111c  pop     ebx
0x1001111d  mov     esp, ebp
0x1001111f  pop     ebp
0x10011120  retn    4
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
