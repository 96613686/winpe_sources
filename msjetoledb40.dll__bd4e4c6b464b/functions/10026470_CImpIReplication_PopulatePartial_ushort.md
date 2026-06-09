# CImpIReplication::PopulatePartial(ushort *)

- ea: `0x10026470`
- end: `0x100265d8`
- name: `?PopulatePartial@CImpIReplication@@UAGJPAG@Z`
- size: `360`
- prototype: `int(CImpIReplication *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10026470`
- `0x10027860`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10026569`
- `KERNEL32!LeaveCriticalSection` at `0x10026569`
- `KERNEL32!EnterCriticalSection` at `0x100264c7`
- `KERNEL32!EnterCriticalSection` at `0x100264c7`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100264b7`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100264b7`
- `msjet40!__imp__JetCloseDatabase@12` at `0x1002655e`
- `msjet40!__imp__JetCloseDatabase@12` at `0x100265c1`
- `msjet40!__imp__JetCloseDatabase@12` at `0x1002655e`
- `msjet40!__imp__JetCloseDatabase@12` at `0x100265c1`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100264ed`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100264ed`
- `msjet40!__imp__JetOpenDatabase@20` at `0x10026512`
- `msjet40!__imp__JetOpenDatabase@20` at `0x10026512`

## pseudocode

```c
int __stdcall CImpIReplication::PopulatePartial(CImpIReplication *this, unsigned __int16 *a2)
{
  int v2; // ebx
  int v3; // eax
  JET_SESID v4; // ecx
  int v5; // eax
  struct _RTL_CRITICAL_SECTION *v6; // esi
  JET_ERR v7; // eax
  CReplCover *v8; // edi
  const struct _GUID *v10; // [esp+0h] [ebp-30h]
  const struct _GUID *v11; // [esp+4h] [ebp-2Ch]
  int v12; // [esp+14h] [ebp-1Ch] BYREF
  JET_DBID v13; // [esp+18h] [ebp-18h]
  JET_SESID sesid; // [esp+1Ch] [ebp-14h]
  JET_DBID dbid[4]; // [esp+20h] [ebp-10h] BYREF

  v2 = 0;
  v3 = *((_DWORD *)this + 2);
  v4 = *(_DWORD *)(v3 + 16);
  v5 = *(_DWORD *)(v3 + 20);
  sesid = v4;
  v12 = v5;
  dbid[0] = -1;
  SetErrorInfo(0, 0);
  v6 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  EnterCriticalSection(v6);
  dbid[3] = 0;
  if ( !a2 )
  {
    v2 = -2147024809;
    if ( !JetGetDatabaseInfo(
            *(_DWORD *)(*((_DWORD *)this + 2) + 16),
            *(_DWORD *)(*((_DWORD *)this + 2) + 20),
            &v12,
            4,
            3) )
      CExtError::SendHRtoOLEAuto(-2147024809, (__int128 *)&IID_IReplication, 0, v10, (int)v11);
    goto LABEL_9;
  }
  v7 = JetOpenDatabase(sesid, a2, 0, dbid, 0);
  if ( v7 >= 0 )
  {
    v8 = (CReplCover *)*((_DWORD *)this + 4);
    v13 = dbid[0];
    if ( CReplCover::Initialize(v8) >= 0 )
    {
      v7 = (*(int (__thiscall **)(_DWORD, JET_SESID, int, JET_DBID, _DWORD))(*((_DWORD *)v8 + 2) + 24))(
             *(_DWORD *)(*((_DWORD *)v8 + 2) + 24),
             sesid,
             v12,
             v13,
             0);
      if ( v7 >= 0 )
      {
        v7 = JetCloseDatabase(sesid, dbid[0], 0);
        if ( !v7 )
        {
          dbid[0] = -1;
          goto LABEL_11;
        }
      }
      else if ( v7 == -1011 )
      {
        v2 = -2147024882;
        goto LABEL_8;
      }
    }
    else
    {
      v7 = -1029;
    }
  }
  v2 = -2147467259;
LABEL_8:
  CExtError::SendJetErrortoOLEAuto(
    v2,
    *(char **)(*((_DWORD *)this + 2) + 16),
    v7,
    (int)&IID_IReplication,
    (int)v10,
    v11);
LABEL_9:
  if ( dbid[0] != -1 )
    JetCloseDatabase(sesid, dbid[0], 1u);
LABEL_11:
  if ( v6 )
    LeaveCriticalSection(v6);
  return v2;
}

```

## disassembly

```asm
0x10026470  mov     edi, edi
0x10026472  push    ebp
0x10026473  mov     ebp, esp
0x10026475  push    0FFFFFFFFh
0x10026477  push    offset ?PopulatePartial@CImpIReplication@@UAGJPAG@Z_SEH
0x1002647c  mov     eax, large fs:0
0x10026482  push    eax
0x10026483  sub     esp, 14h
0x10026486  push    ebx
0x10026487  push    esi
0x10026488  push    edi; struct _GUID *
0x10026489  mov     eax, ___security_cookie
0x1002648e  xor     eax, ebp
0x10026490  push    eax; int
0x10026491  lea     eax, [ebp+var_C]
0x10026494  mov     large fs:0, eax
0x1002649a  mov     edi, [ebp+this]
0x1002649d  xor     ebx, ebx
0x1002649f  push    ebx; perrinfo
0x100264a0  push    ebx; dwReserved
0x100264a1  mov     eax, [edi+8]
0x100264a4  mov     ecx, [eax+10h]
0x100264a7  mov     eax, [eax+14h]
0x100264aa  mov     [ebp+sesid], ecx
0x100264ad  mov     [ebp+var_1C], eax
0x100264b0  mov     [ebp+dbid], 0FFFFFFFFh
0x100264b7  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x100264bd  mov     esi, [edi+8]
0x100264c0  add     esi, 68h ; 'h'
0x100264c3  push    esi; lpCriticalSection
0x100264c4  mov     [ebp+var_20], esi
0x100264c7  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100264cd  mov     eax, [ebp+arg_4]
0x100264d0  mov     [ebp+var_4], ebx
0x100264d3  test    eax, eax
0x100264d5  jnz     short loc_10026506
0x100264d7  mov     eax, [edi+8]
0x100264da  lea     ecx, [ebp+var_1C]
0x100264dd  push    3
0x100264df  push    4
0x100264e1  push    ecx
0x100264e2  push    dword ptr [eax+14h]
0x100264e5  mov     ebx, 80070057h
0x100264ea  push    dword ptr [eax+10h]
0x100264ed  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x100264f3  test    eax, eax
0x100264f5  jnz     short loc_10026550
0x100264f7  push    eax; int
0x100264f8  push    offset _IID_IReplication; int
0x100264fd  mov     edx, ebx
0x100264ff  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10026504  jmp     short loc_10026550
0x10026506  push    0
0x10026508  lea     ecx, [ebp+dbid]
0x1002650b  push    ecx
0x1002650c  push    0
0x1002650e  push    eax
0x1002650f  push    [ebp+sesid]
0x10026512  call    ds:__imp__JetOpenDatabase@20; JetOpenDatabase(x,x,x,x,x)
0x10026518  test    eax, eax
0x1002651a  js      short loc_10026535
0x1002651c  mov     edi, [edi+10h]
0x1002651f  mov     ecx, edi; this
0x10026521  mov     eax, [ebp+dbid]
0x10026524  mov     [ebp+var_18], eax
0x10026527  call    ?Initialize@CReplCover@@QAEJXZ; CReplCover::Initialize(void)
0x1002652c  test    eax, eax
0x1002652e  jns     short loc_10026585
0x10026530  mov     eax, 0FFFFFBFBh
0x10026535  mov     ebx, 80004005h
0x1002653a  mov     ecx, [ebp+this]
0x1002653d  mov     edx, ebx
0x1002653f  push    offset _IID_IReplication; int
0x10026544  push    eax; unsigned int
0x10026545  mov     ecx, [ecx+8]
0x10026548  mov     ecx, [ecx+10h]
0x1002654b  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10026550  mov     eax, [ebp+dbid]
0x10026553  cmp     eax, 0FFFFFFFFh
0x10026556  jz      short loc_10026564
0x10026558  push    1; grbit
0x1002655a  push    eax; dbid
0x1002655b  push    [ebp+sesid]; sesid
0x1002655e  call    ds:__imp__JetCloseDatabase@12; JetCloseDatabase(x,x,x)
0x10026564  test    esi, esi
0x10026566  jz      short loc_1002656F
0x10026568  push    esi; lpCriticalSection
0x10026569  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1002656f  mov     eax, ebx
0x10026571  mov     ecx, [ebp+var_C]
0x10026574  mov     large fs:0, ecx
0x1002657b  pop     ecx
0x1002657c  pop     edi
0x1002657d  pop     esi
0x1002657e  pop     ebx
0x1002657f  mov     esp, ebp
0x10026581  pop     ebp
0x10026582  retn    8
0x10026585  mov     eax, [edi+8]
0x10026588  push    0
0x1002658a  push    [ebp+var_18]
0x1002658d  push    [ebp+var_1C]
0x10026590  mov     edi, [eax+18h]
0x10026593  mov     ecx, edi
0x10026595  push    [ebp+sesid]
0x10026598  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002659e  call    edi
0x100265a0  test    eax, eax
0x100265a2  jns     short loc_100265B9
0x100265a4  cmp     eax, 0FFFFB175h
0x100265a9  jz      short loc_10026535
0x100265ab  cmp     eax, 0FFFFFC0Dh
0x100265b0  jnz     short loc_10026535
0x100265b2  mov     ebx, 8007000Eh
0x100265b7  jmp     short loc_1002653A
0x100265b9  push    0; grbit
0x100265bb  push    [ebp+dbid]; dbid
0x100265be  push    [ebp+sesid]; sesid
0x100265c1  call    ds:__imp__JetCloseDatabase@12; JetCloseDatabase(x,x,x)
0x100265c7  test    eax, eax
0x100265c9  jnz     loc_10026535
0x100265cf  mov     [ebp+dbid], 0FFFFFFFFh
0x100265d6  jmp     short loc_10026564
0x1004e980  lea     ecx, [ebp+var_20]; this
0x1004e983  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004e98d  nop
0x1004e98e  nop
0x1004e98f  mov     edx, [esp-4+arg_4]
0x1004e993  lea     eax, [edx+0Ch]
0x1004e996  mov     ecx, [edx-24h]
0x1004e999  xor     ecx, eax; StackCookie
0x1004e99b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e9a0  mov     eax, offset stru_1004FC8C
0x1004e9a5  jmp     ___CxxFrameHandler3
```
