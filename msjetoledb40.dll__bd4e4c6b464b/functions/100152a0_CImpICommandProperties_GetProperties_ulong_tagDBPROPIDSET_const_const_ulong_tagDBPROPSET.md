# CImpICommandProperties::GetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *)

- ea: `0x100152a0`
- end: `0x100153d3`
- name: `?GetProperties@CImpICommandProperties@@UAGJKQBUtagDBPROPIDSET@@PAKPAPAUtagDBPROPSET@@@Z`
- size: `307`
- prototype: `int(CImpICommandProperties *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPSET **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x100152a0`
- `0x1001c380`
- `0x10020a50`
- `0x1004c660`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x100153b7`
- `KERNEL32!LeaveCriticalSection` at `0x100153b7`
- `KERNEL32!EnterCriticalSection` at `0x100152e4`
- `KERNEL32!EnterCriticalSection` at `0x100152e4`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100152ce`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100152ce`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001539b`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001539b`

## pseudocode

```c
int __stdcall CImpICommandProperties::GetProperties(
        CImpICommandProperties *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // esi
  int Properties; // ebx
  GUID *p_guidPropertySet; // edx
  const GUID *v8; // ecx
  unsigned int v9; // edi
  bool v10; // cf
  CImpICommandProperties *v11; // edi
  CSettableProperties *v12; // ecx
  struct CSettableProperties *v14; // [esp+0h] [ebp-24h]
  const struct _GUID *v15; // [esp+0h] [ebp-24h]
  unsigned int v16; // [esp+4h] [ebp-20h]
  int v17; // [esp+4h] [ebp-20h]
  _BYTE v18[4]; // [esp+10h] [ebp-14h] BYREF
  LPCRITICAL_SECTION v19; // [esp+14h] [ebp-10h]
  int v20; // [esp+20h] [ebp-4h]

  SetErrorInfo(0, 0);
  v19 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 248);
  v5 = v19;
  EnterCriticalSection(v19);
  v20 = 0;
  Properties = GenericGetProperties(
                 (unsigned int)a4,
                 (const struct tagDBPROPIDSET *const)a5,
                 *(unsigned int **)(*(_DWORD *)(*((_DWORD *)this + 2) + 52) + 84),
                 (struct tagDBPROPSET **)this + 3,
                 (struct CDataSource *)0x40,
                 v14,
                 v16);
  if ( Properties < 0 )
  {
    v11 = this;
LABEL_13:
    if ( Properties != -2147024882
      && !JetGetDatabaseInfo(
            *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v11 + 2) + 52) + 16),
            *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v11 + 2) + 52) + 20),
            v18,
            4,
            3) )
    {
      CExtError::SendHRtoOLEAuto(Properties, (__int128 *)&IID_ICommandProperties, 0, v15, v17);
    }
  }
  else if ( a2 == 1 && a3 && a4 && !*a4 )
  {
    p_guidPropertySet = &a3->guidPropertySet;
    v8 = &DBPROPSET_PROPERTIESINERROR;
    v9 = 12;
    while ( v8->Data1 == p_guidPropertySet->Data1 )
    {
      v8 = (const GUID *)((char *)v8 + 4);
      p_guidPropertySet = (GUID *)((char *)p_guidPropertySet + 4);
      v10 = v9 < 4;
      v9 -= 4;
      if ( v10 )
      {
        v11 = this;
        v12 = *(CSettableProperties **)(*((_DWORD *)this + 2) + 272);
        if ( !v12 )
          break;
        Properties = CSettableProperties::DumpProperties(v12, a4, a5);
        if ( Properties >= 0 )
          break;
        goto LABEL_13;
      }
    }
  }
  if ( v5 )
    LeaveCriticalSection(v5);
  return Properties;
}

```

## disassembly

```asm
0x100152a0  mov     edi, edi
0x100152a2  push    ebp
0x100152a3  mov     ebp, esp
0x100152a5  push    0FFFFFFFFh
0x100152a7  push    offset ?StartTransaction@CImpITransactionLocal@@UAGJJKPAUITransactionOptions@@PAK@Z_SEH
0x100152ac  mov     eax, large fs:0
0x100152b2  push    eax
0x100152b3  sub     esp, 8
0x100152b6  push    ebx
0x100152b7  push    esi
0x100152b8  push    edi; int
0x100152b9  mov     eax, ___security_cookie
0x100152be  xor     eax, ebp
0x100152c0  push    eax; struct _GUID *
0x100152c1  lea     eax, [ebp+var_C]
0x100152c4  mov     large fs:0, eax
0x100152ca  push    0; perrinfo
0x100152cc  push    0; dwReserved
0x100152ce  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x100152d4  mov     ebx, [ebp+this]
0x100152d7  mov     esi, [ebx+8]
0x100152da  add     esi, 0F8h
0x100152e0  push    esi; lpCriticalSection
0x100152e1  mov     [ebp+var_10], esi
0x100152e4  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100152ea  mov     edi, [ebp+arg_C]
0x100152ed  mov     edx, [ebp+arg_8]
0x100152f0  mov     [ebp+var_4], 0
0x100152f7  mov     eax, [ebx+8]
0x100152fa  push    40h ; '@'; struct CDataSource *
0x100152fc  mov     eax, [eax+34h]
0x100152ff  mov     ecx, [eax+54h]
0x10015302  lea     eax, [ebx+0Ch]
0x10015305  push    eax; struct tagDBPROPSET **
0x10015306  push    ecx; unsigned int *
0x10015307  push    [ebp+arg_10]; struct tagDBPROPIDSET *
0x1001530a  mov     ecx, [ebp+arg_4]
0x1001530d  push    edi; unsigned int
0x1001530e  call    ?GenericGetProperties@@YGJKQBUtagDBPROPIDSET@@PAKPAPAUtagDBPROPSET@@PAVCDataSource@@PAVCSettableProperties@@K@Z; GenericGetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *,CDataSource *,CSettableProperties *,ulong)
0x10015313  mov     ebx, eax
0x10015315  test    ebx, ebx
0x10015317  js      short loc_1001537C
0x10015319  cmp     [ebp+arg_4], 1
0x1001531d  jnz     loc_100153B2
0x10015323  mov     eax, [ebp+arg_8]
0x10015326  test    eax, eax
0x10015328  jz      loc_100153B2
0x1001532e  test    edi, edi
0x10015330  jz      loc_100153B2
0x10015336  cmp     dword ptr [edi], 0
0x10015339  jnz     short loc_100153B2
0x1001533b  lea     edx, [eax+8]
0x1001533e  mov     ecx, offset _DBPROPSET_PROPERTIESINERROR
0x10015343  mov     edi, 0Ch
0x10015348  mov     eax, [ecx]
0x1001534a  cmp     eax, [edx]
0x1001534c  jnz     short loc_100153B2
0x1001534e  add     ecx, 4
0x10015351  add     edx, 4
0x10015354  sub     edi, 4
0x10015357  jnb     short loc_10015348
0x10015359  mov     edi, [ebp+this]
0x1001535c  mov     eax, [edi+8]
0x1001535f  mov     ecx, [eax+110h]; this
0x10015365  test    ecx, ecx
0x10015367  jz      short loc_100153B2
0x10015369  push    [ebp+arg_10]; struct tagDBPROPSET **
0x1001536c  push    [ebp+arg_C]; unsigned int *
0x1001536f  call    ?DumpProperties@CSettableProperties@@QAEJPAKPAPAUtagDBPROPSET@@@Z; CSettableProperties::DumpProperties(ulong *,tagDBPROPSET * *)
0x10015374  mov     ebx, eax
0x10015376  test    ebx, ebx
0x10015378  jns     short loc_100153B2
0x1001537a  jmp     short loc_1001537F
0x1001537c  mov     edi, [ebp+this]
0x1001537f  mov     eax, [edi+8]
0x10015382  mov     eax, [eax+34h]
0x10015385  cmp     ebx, 8007000Eh
0x1001538b  jz      short loc_100153B2
0x1001538d  push    3
0x1001538f  push    4
0x10015391  lea     ecx, [ebp+var_14]
0x10015394  push    ecx
0x10015395  push    dword ptr [eax+14h]
0x10015398  push    dword ptr [eax+10h]
0x1001539b  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x100153a1  test    eax, eax
0x100153a3  jnz     short loc_100153B2
0x100153a5  push    eax; int
0x100153a6  push    offset _IID_ICommandProperties; int
0x100153ab  mov     edx, ebx
0x100153ad  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x100153b2  test    esi, esi
0x100153b4  jz      short loc_100153BD
0x100153b6  push    esi; lpCriticalSection
0x100153b7  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100153bd  mov     eax, ebx
0x100153bf  mov     ecx, [ebp+var_C]
0x100153c2  mov     large fs:0, ecx
0x100153c9  pop     ecx
0x100153ca  pop     edi
0x100153cb  pop     esi
0x100153cc  pop     ebx
0x100153cd  mov     esp, ebp
0x100153cf  pop     ebp
0x100153d0  retn    14h
0x1004ddb0  lea     ecx, [ebp+var_10]; this
0x1004ddb3  jmp     ??1CMutex@@QAE@XZ
0x1004ddbd  nop
0x1004ddbe  nop
0x1004ddbf  mov     edx, [esp-4+arg_4]
0x1004ddc3  lea     eax, [edx+0Ch]
0x1004ddc6  mov     ecx, [edx-18h]
0x1004ddc9  xor     ecx, eax; StackCookie
0x1004ddcb  call    @__security_check_cookie@4
0x1004ddd0  mov     eax, offset stru_1004F3AC
0x1004ddd5  jmp     ___CxxFrameHandler3
```
