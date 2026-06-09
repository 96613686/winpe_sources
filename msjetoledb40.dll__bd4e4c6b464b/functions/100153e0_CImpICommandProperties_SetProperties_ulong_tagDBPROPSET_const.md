# CImpICommandProperties::SetProperties(ulong,tagDBPROPSET * const)

- ea: `0x100153e0`
- end: `0x100155bc`
- name: `?SetProperties@CImpICommandProperties@@UAGJKQAUtagDBPROPSET@@@Z`
- size: `476`
- prototype: `int(CImpICommandProperties *__hidden this, unsigned int, struct tagDBPROPSET *const)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x1000e8d0`
- `0x100153e0`
- `0x1001c380`
- `0x10020410`
- `0x100204c0`
- `0x100205d0`
- `0x100207d0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1001546f`
- `KERNEL32!LeaveCriticalSection` at `0x100155a0`
- `KERNEL32!LeaveCriticalSection` at `0x1001546f`
- `KERNEL32!LeaveCriticalSection` at `0x100155a0`
- `KERNEL32!EnterCriticalSection` at `0x10015424`
- `KERNEL32!EnterCriticalSection` at `0x1001545b`
- `KERNEL32!EnterCriticalSection` at `0x10015424`
- `KERNEL32!EnterCriticalSection` at `0x1001545b`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001540e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001540e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10015572`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10015572`

## pseudocode

```c
int __stdcall CImpICommandProperties::SetProperties(
        CImpICommandProperties *this,
        unsigned int a2,
        struct tagDBPROPSET *const a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // esi
  char *v4; // eax
  int v5; // eax
  int v6; // ebx
  int v7; // ecx
  int v8; // eax
  struct _RTL_CRITICAL_SECTION *v9; // edi
  char *v10; // eax
  int v11; // eax
  unsigned int i; // ecx
  const struct CSettableProperties *v13; // ecx
  signed int v14; // eax
  int v15; // eax
  int v16; // eax
  const struct _GUID *v18; // [esp+0h] [ebp-38h]
  int v19; // [esp+4h] [ebp-34h]
  _DWORD v20[4]; // [esp+10h] [ebp-28h] BYREF
  int v21; // [esp+20h] [ebp-18h]
  LPCRITICAL_SECTION v22; // [esp+24h] [ebp-14h]
  char *v23; // [esp+28h] [ebp-10h] BYREF
  int v24; // [esp+34h] [ebp-4h]

  SetErrorInfo(0, 0);
  v22 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 248);
  v3 = v22;
  EnterCriticalSection(v22);
  v24 = 0;
  if ( !a2 )
  {
    v6 = 0;
    goto LABEL_23;
  }
  v4 = (char *)*((_DWORD *)this + 2);
  v23 = v4;
  if ( !a3 )
  {
    v5 = *((_DWORD *)v4 + 13);
    v6 = -2147024809;
    v7 = *(_DWORD *)(v5 + 20);
    v8 = *(_DWORD *)(v5 + 16);
    goto LABEL_19;
  }
  v9 = (struct _RTL_CRITICAL_SECTION *)(v4 + 248);
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 248));
  v10 = (char *)*((_DWORD *)v23 + 20);
  v23 = v10;
  if ( v9 )
  {
    LeaveCriticalSection(v9);
    v10 = v23;
  }
  if ( !v10 )
  {
    for ( i = 0; i < a2; ++i )
    {
      if ( a3[i].cProperties && !a3[i].rgProperties )
      {
        v6 = -2147024809;
        v15 = *(_DWORD *)(*((_DWORD *)this + 2) + 52);
        v7 = *(_DWORD *)(v15 + 20);
        v8 = *(_DWORD *)(v15 + 16);
        goto LABEL_19;
      }
    }
    memset(&v20[1], 0, 12);
    v20[0] = &CRowsetProperties::`vftable';
    v21 = 0;
    LOBYTE(v24) = 1;
    v6 = CSettableProperties::FInit((CSettableProperties *)v20);
    if ( v6 >= 0 )
    {
      v13 = (CImpICommandProperties *)((char *)this + 12);
      v23 = (char *)this + 12;
      if ( (_DWORD *)((char *)this + 12) == v20 )
        goto LABEL_17;
      v14 = CSettableProperties::CopyFrom((CSettableProperties *)v20, v13);
      v13 = (const struct CSettableProperties *)v23;
      v6 = v14;
      if ( v14 >= 0 )
      {
        v21 = *((_DWORD *)v23 + 4);
LABEL_17:
        v6 = CSettableProperties::SetProperties(v13, a2, a3, 0);
        if ( v6 >= 0 )
        {
          LOBYTE(v24) = 0;
          CSettableProperties::~CSettableProperties((CSettableProperties *)v20);
          goto LABEL_23;
        }
      }
    }
    LOBYTE(v24) = 0;
    CSettableProperties::~CSettableProperties((CSettableProperties *)v20);
    v16 = *(_DWORD *)(*((_DWORD *)this + 2) + 52);
    v7 = *(_DWORD *)(v16 + 20);
    v8 = *(_DWORD *)(v16 + 16);
    if ( v6 == -2147024882 )
      goto LABEL_23;
    goto LABEL_19;
  }
  v6 = -2147217915;
  v11 = *(_DWORD *)(*((_DWORD *)this + 2) + 52);
  v7 = *(_DWORD *)(v11 + 20);
  v8 = *(_DWORD *)(v11 + 16);
LABEL_19:
  if ( !JetGetDatabaseInfo(v8, v7, &v23, 4, 3) )
    CExtError::SendHRtoOLEAuto(v6, (__int128 *)&IID_ICommandProperties, 0, v18, v19);
LABEL_23:
  if ( v3 )
    LeaveCriticalSection(v3);
  return v6;
}

```

## disassembly

```asm
0x100153e0  mov     edi, edi
0x100153e2  push    ebp
0x100153e3  mov     ebp, esp
0x100153e5  push    0FFFFFFFFh
0x100153e7  push    offset ?SetProperties@CImpICommandProperties@@UAGJKQAUtagDBPROPSET@@@Z_SEH
0x100153ec  mov     eax, large fs:0
0x100153f2  push    eax
0x100153f3  sub     esp, 1Ch
0x100153f6  push    ebx
0x100153f7  push    esi
0x100153f8  push    edi; int
0x100153f9  mov     eax, ___security_cookie
0x100153fe  xor     eax, ebp
0x10015400  push    eax; struct _GUID *
0x10015401  lea     eax, [ebp+var_C]
0x10015404  mov     large fs:0, eax
0x1001540a  xor     ebx, ebx
0x1001540c  push    ebx; perrinfo
0x1001540d  push    ebx; dwReserved
0x1001540e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10015414  mov     edi, [ebp+this]
0x10015417  mov     esi, [edi+8]
0x1001541a  add     esi, 0F8h
0x10015420  push    esi; lpCriticalSection
0x10015421  mov     [ebp+var_14], esi
0x10015424  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001542a  mov     [ebp+var_4], ebx
0x1001542d  cmp     [ebp+arg_4], ebx
0x10015430  jz      loc_10015599
0x10015436  mov     eax, [edi+8]
0x10015439  mov     [ebp+var_10], eax
0x1001543c  cmp     [ebp+arg_8], ebx
0x1001543f  jnz     short loc_10015454
0x10015441  mov     eax, [eax+34h]
0x10015444  mov     ebx, 80070057h
0x10015449  mov     ecx, [eax+14h]
0x1001544c  mov     eax, [eax+10h]
0x1001544f  jmp     loc_10015568
0x10015454  lea     edi, [eax+0F8h]
0x1001545a  push    edi; lpCriticalSection
0x1001545b  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10015461  mov     eax, [ebp+var_10]
0x10015464  mov     eax, [eax+50h]
0x10015467  mov     [ebp+var_10], eax
0x1001546a  test    edi, edi
0x1001546c  jz      short loc_10015478
0x1001546e  push    edi; lpCriticalSection
0x1001546f  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10015475  mov     eax, [ebp+var_10]
0x10015478  test    eax, eax
0x1001547a  jz      short loc_10015495
0x1001547c  mov     ecx, [ebp+this]
0x1001547f  mov     ebx, 80040E05h
0x10015484  mov     eax, [ecx+8]
0x10015487  mov     eax, [eax+34h]
0x1001548a  mov     ecx, [eax+14h]
0x1001548d  mov     eax, [eax+10h]
0x10015490  jmp     loc_10015568
0x10015495  mov     edi, [ebp+arg_4]
0x10015498  xor     ecx, ecx
0x1001549a  test    edi, edi
0x1001549c  jz      loc_1001559B
0x100154a2  mov     edx, [ebp+arg_8]
0x100154a5  lea     eax, [ecx+ecx*2]
0x100154a8  cmp     dword ptr [edx+eax*8+4], 0
0x100154ad  jz      short loc_100154B5
0x100154af  cmp     dword ptr [edx+eax*8], 0
0x100154b3  jz      short loc_1001551A
0x100154b5  inc     ecx
0x100154b6  cmp     ecx, edi
0x100154b8  jb      short loc_100154A5
0x100154ba  mov     [ebp+var_24], 0
0x100154c1  mov     [ebp+var_20], 0
0x100154c8  mov     [ebp+var_1C], 0
0x100154cf  mov     [ebp+var_28], offset ??_7CRowsetProperties@@6B@; const CRowsetProperties::`vftable'
0x100154d6  mov     [ebp+var_18], 0
0x100154dd  lea     ecx, [ebp+var_28]; this
0x100154e0  mov     byte ptr [ebp+var_4], 1
0x100154e4  call    ?FInit@CSettableProperties@@QAEJXZ; CSettableProperties::FInit(void)
0x100154e9  mov     ebx, eax
0x100154eb  test    ebx, ebx
0x100154ed  js      short loc_10015545
0x100154ef  mov     ecx, [ebp+this]
0x100154f2  lea     eax, [ebp+var_28]
0x100154f5  add     ecx, 0Ch; this
0x100154f8  xor     ebx, ebx
0x100154fa  mov     [ebp+var_10], ecx
0x100154fd  cmp     ecx, eax
0x100154ff  jz      short loc_10015530
0x10015501  push    ecx; struct CSettableProperties *
0x10015502  mov     ecx, eax; this
0x10015504  call    ?CopyFrom@CSettableProperties@@QAEJABV1@@Z; CSettableProperties::CopyFrom(CSettableProperties const &)
0x10015509  mov     ecx, [ebp+var_10]
0x1001550c  mov     ebx, eax
0x1001550e  test    ebx, ebx
0x10015510  js      short loc_10015545
0x10015512  mov     eax, [ecx+10h]
0x10015515  mov     [ebp+var_18], eax
0x10015518  jmp     short loc_10015534
0x1001551a  mov     ecx, [ebp+this]
0x1001551d  mov     ebx, 80070057h
0x10015522  mov     eax, [ecx+8]
0x10015525  mov     eax, [eax+34h]
0x10015528  mov     ecx, [eax+14h]
0x1001552b  mov     eax, [eax+10h]
0x1001552e  jmp     short loc_10015568
0x10015530  test    ebx, ebx
0x10015532  js      short loc_10015545
0x10015534  push    0; struct CDBSession *
0x10015536  push    [ebp+arg_8]; struct tagDBPROPSET *
0x10015539  push    edi; unsigned int
0x1001553a  call    ?SetProperties@CSettableProperties@@QAEJKPAUtagDBPROPSET@@PAVCDBSession@@@Z; CSettableProperties::SetProperties(ulong,tagDBPROPSET *,CDBSession *)
0x1001553f  mov     ebx, eax
0x10015541  test    ebx, ebx
0x10015543  jns     short loc_1001558B
0x10015545  lea     ecx, [ebp+var_28]; this
0x10015548  mov     byte ptr [ebp+var_4], 0
0x1001554c  call    ??1CSettableProperties@@UAE@XZ; CSettableProperties::~CSettableProperties(void)
0x10015551  mov     ecx, [ebp+this]
0x10015554  mov     eax, [ecx+8]
0x10015557  mov     eax, [eax+34h]
0x1001555a  mov     ecx, [eax+14h]
0x1001555d  mov     eax, [eax+10h]
0x10015560  cmp     ebx, 8007000Eh
0x10015566  jz      short loc_1001559B
0x10015568  push    3
0x1001556a  push    4
0x1001556c  lea     edx, [ebp+var_10]
0x1001556f  push    edx
0x10015570  push    ecx
0x10015571  push    eax
0x10015572  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10015578  test    eax, eax
0x1001557a  jnz     short loc_1001559B
0x1001557c  push    eax; int
0x1001557d  push    offset _IID_ICommandProperties; int
0x10015582  mov     edx, ebx
0x10015584  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10015589  jmp     short loc_1001559B
0x1001558b  lea     ecx, [ebp+var_28]; this
0x1001558e  mov     byte ptr [ebp+var_4], 0
0x10015592  call    ??1CSettableProperties@@UAE@XZ; CSettableProperties::~CSettableProperties(void)
0x10015597  jmp     short loc_1001559B
0x10015599  xor     ebx, ebx
0x1001559b  test    esi, esi
0x1001559d  jz      short loc_100155A6
0x1001559f  push    esi; lpCriticalSection
0x100155a0  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100155a6  mov     eax, ebx
0x100155a8  mov     ecx, [ebp+var_C]
0x100155ab  mov     large fs:0, ecx
0x100155b2  pop     ecx
0x100155b3  pop     edi
0x100155b4  pop     esi
0x100155b5  pop     ebx
0x100155b6  mov     esp, ebp
0x100155b8  pop     ebp
0x100155b9  retn    0Ch
0x1004e210  lea     ecx, [ebp+var_14]; this
0x1004e213  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004e218  lea     ecx, [ebp+var_28]; this
0x1004e21b  jmp     ??1CTableProperties@@UAE@XZ; CTableProperties::~CTableProperties(void)
0x1004e225  nop
0x1004e226  nop
0x1004e227  mov     edx, [esp-4+arg_4]
0x1004e22b  lea     eax, [edx+0Ch]
0x1004e22e  mov     ecx, [edx-2Ch]
0x1004e231  xor     ecx, eax; StackCookie
0x1004e233  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e238  mov     eax, offset stru_1004F708
0x1004e23d  jmp     ___CxxFrameHandler3
```
