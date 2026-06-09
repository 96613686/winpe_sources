# CImpICommandPersist::DeleteCommand(tagDBID *)

- ea: `0x10011530`
- end: `0x10011734`
- name: `?DeleteCommand@CImpICommandPersist@@UAGJPAUtagDBID@@@Z`
- size: `516`
- prototype: `int(CImpICommandPersist *__hidden this, struct tagDBID *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x10011530`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10049580`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x100115b4`
- `msvcrt!_wcsicmp` at `0x100115b4`
- `KERNEL32!LeaveCriticalSection` at `0x10011621`
- `KERNEL32!LeaveCriticalSection` at `0x10011718`
- `KERNEL32!LeaveCriticalSection` at `0x10011621`
- `KERNEL32!LeaveCriticalSection` at `0x10011718`
- `KERNEL32!EnterCriticalSection` at `0x10011574`
- `KERNEL32!EnterCriticalSection` at `0x100115ce`
- `KERNEL32!EnterCriticalSection` at `0x10011574`
- `KERNEL32!EnterCriticalSection` at `0x100115ce`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001155e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001155e`
- `msjet40!__imp__JetCloseTable@8` at `0x1001163c`
- `msjet40!__imp__JetCloseTable@8` at `0x1001163c`
- `msjet40!__imp__JetDeleteTable@12` at `0x10011677`
- `msjet40!__imp__JetDeleteTable@12` at `0x10011677`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100116fc`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100116fc`

## pseudocode

```c
int __stdcall CImpICommandPersist::DeleteCommand(CImpICommandPersist *this, struct tagDBID *a2)
{
  int v2; // ebx
  CImpICommandPersist *v3; // esi
  struct _RTL_CRITICAL_SECTION *v4; // edi
  const wchar_t *pwszName; // ecx
  int v6; // eax
  struct _RTL_CRITICAL_SECTION *v7; // esi
  CImpICommandPersist *v8; // ecx
  int v9; // edx
  int v10; // eax
  int v11; // eax
  JET_TABLEID v12; // ecx
  CTransactionState *v13; // ecx
  signed int v14; // eax
  const struct _GUID *v16; // [esp+0h] [ebp-24h]
  const struct _GUID *v17; // [esp+4h] [ebp-20h]
  struct _RTL_CRITICAL_SECTION *v18; // [esp+10h] [ebp-14h] BYREF
  LPCRITICAL_SECTION v19; // [esp+14h] [ebp-10h]
  int v20; // [esp+20h] [ebp-4h]

  v2 = 0;
  SetErrorInfo(0, 0);
  v3 = this;
  v19 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 248);
  v4 = v19;
  EnterCriticalSection(v19);
  v20 = 0;
  if ( !a2 )
  {
    v2 = -2147024809;
    goto LABEL_31;
  }
  if ( a2->eKind == 2 )
  {
    pwszName = a2->uName.pwszName;
    if ( pwszName )
    {
      v6 = *((_DWORD *)this + 2);
      if ( *(_DWORD *)(v6 + 72) == 1 )
      {
        if ( !__wcsicmp(*(const wchar_t **)(v6 + 76), pwszName) )
        {
          v7 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 248);
          v18 = v7;
          EnterCriticalSection(v7);
          v8 = this;
          LOBYTE(v20) = 1;
          v9 = *(_DWORD *)(*((_DWORD *)this + 2) + 76);
          if ( v9 )
          {
            if ( Sys )
            {
              (*(void (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 20))(
                *(_DWORD *)(*(_DWORD *)Sys + 20),
                Sys,
                v9);
              v8 = this;
              v2 = 0;
            }
            *(_DWORD *)(*((_DWORD *)v8 + 2) + 76) = 0;
          }
          v10 = *((_DWORD *)v8 + 2);
          LOBYTE(v20) = 0;
          *(_DWORD *)(v10 + 72) = 0;
          if ( v7 )
            LeaveCriticalSection(v7);
          v3 = this;
        }
        v11 = *((_DWORD *)v3 + 2);
        v12 = *(_DWORD *)(v11 + 100);
        if ( v12 != -1 )
        {
          JetCloseTable(*(_DWORD *)(*(_DWORD *)(v11 + 52) + 16), v12);
          *(_DWORD *)(*((_DWORD *)v3 + 2) + 100) = -1;
          v13 = *(CTransactionState **)(*((_DWORD *)v3 + 2) + 56);
          if ( v13 )
          {
            CTransactionState::Release(v13);
            *(_DWORD *)(*((_DWORD *)v3 + 2) + 56) = 0;
          }
        }
      }
      v14 = JetDeleteTable(
              *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v3 + 2) + 52) + 16),
              *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v3 + 2) + 52) + 20),
              a2->uName.ulPropid);
      if ( v14 > -1305 )
      {
        if ( v14 == -1304 || v14 == -1302 )
        {
          v2 = -2147217856;
          goto LABEL_29;
        }
        if ( !v14 )
          goto LABEL_33;
      }
      else
      {
        if ( v14 == -1305 )
        {
          v2 = -2147217802;
          goto LABEL_29;
        }
        if ( v14 == -8114 || v14 == -1907 || v14 == -1809 )
        {
          v2 = -2147217911;
LABEL_29:
          CExtError::SendJetErrortoOLEAuto(
            v2,
            *(char **)(*(_DWORD *)(*((_DWORD *)v3 + 2) + 52) + 16),
            v14,
            (int)&IID_ICommandPersist,
            (int)v16,
            v17);
          goto LABEL_33;
        }
      }
      v2 = -2147467259;
      goto LABEL_29;
    }
  }
  v2 = -2147217802;
LABEL_31:
  if ( !JetGetDatabaseInfo(
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 52) + 16),
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 52) + 20),
          &v18,
          4,
          3) )
    CExtError::SendHRtoOLEAuto((int)&IID_ICommandPersist, 0, v16, (int)v17);
LABEL_33:
  if ( v4 )
    LeaveCriticalSection(v4);
  return v2;
}

```

## disassembly

```asm
0x10011530  mov     edi, edi
0x10011532  push    ebp
0x10011533  mov     ebp, esp
0x10011535  push    0FFFFFFFFh
0x10011537  push    offset ?AddRef@CDataSource@@UAGKXZ_SEH
0x1001153c  mov     eax, large fs:0
0x10011542  push    eax
0x10011543  sub     esp, 8
0x10011546  push    ebx
0x10011547  push    esi
0x10011548  push    edi; int
0x10011549  mov     eax, ___security_cookie
0x1001154e  xor     eax, ebp
0x10011550  push    eax; struct _GUID *
0x10011551  lea     eax, [ebp+var_C]
0x10011554  mov     large fs:0, eax
0x1001155a  xor     ebx, ebx
0x1001155c  push    ebx; perrinfo
0x1001155d  push    ebx; dwReserved
0x1001155e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10011564  mov     esi, [ebp+this]
0x10011567  mov     edi, [esi+8]
0x1001156a  add     edi, 0F8h
0x10011570  push    edi; lpCriticalSection
0x10011571  mov     [ebp+var_10], edi
0x10011574  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001157a  mov     eax, [ebp+arg_4]
0x1001157d  mov     [ebp+var_4], ebx
0x10011580  test    eax, eax
0x10011582  jnz     short loc_1001158E
0x10011584  mov     ebx, 80070057h
0x10011589  jmp     loc_100116E8
0x1001158e  cmp     dword ptr [eax+10h], 2
0x10011592  jnz     loc_100116E3
0x10011598  mov     ecx, [eax+14h]
0x1001159b  test    ecx, ecx
0x1001159d  jz      loc_100116E3
0x100115a3  mov     eax, [esi+8]
0x100115a6  cmp     dword ptr [eax+48h], 1
0x100115aa  jnz     loc_10011665
0x100115b0  push    ecx; String2
0x100115b1  push    dword ptr [eax+4Ch]; String1
0x100115b4  call    ds:__imp___wcsicmp
0x100115ba  add     esp, 8
0x100115bd  test    eax, eax
0x100115bf  jnz     short loc_1001162A
0x100115c1  mov     esi, [esi+8]
0x100115c4  add     esi, 0F8h
0x100115ca  push    esi; lpCriticalSection
0x100115cb  mov     [ebp+var_14], esi
0x100115ce  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100115d4  mov     ecx, [ebp+this]
0x100115d7  mov     byte ptr [ebp+var_4], 1
0x100115db  mov     eax, [ecx+8]
0x100115de  mov     edx, [eax+4Ch]
0x100115e1  test    edx, edx
0x100115e3  jz      short loc_1001160E
0x100115e5  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x100115ea  test    eax, eax
0x100115ec  jz      short loc_10011604
0x100115ee  mov     ecx, [eax]
0x100115f0  push    edx
0x100115f1  push    eax
0x100115f2  mov     ebx, [ecx+14h]
0x100115f5  mov     ecx, ebx
0x100115f7  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100115fd  call    ebx
0x100115ff  mov     ecx, [ebp+this]
0x10011602  xor     ebx, ebx
0x10011604  mov     eax, [ecx+8]
0x10011607  mov     dword ptr [eax+4Ch], 0
0x1001160e  mov     eax, [ecx+8]
0x10011611  mov     byte ptr [ebp+var_4], 0
0x10011615  mov     dword ptr [eax+48h], 0
0x1001161c  test    esi, esi
0x1001161e  jz      short loc_10011627
0x10011620  push    esi; lpCriticalSection
0x10011621  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10011627  mov     esi, [ebp+this]
0x1001162a  mov     eax, [esi+8]
0x1001162d  mov     ecx, [eax+64h]
0x10011630  cmp     ecx, 0FFFFFFFFh
0x10011633  jz      short loc_10011665
0x10011635  mov     eax, [eax+34h]
0x10011638  push    ecx; tableid
0x10011639  push    dword ptr [eax+10h]; sesid
0x1001163c  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10011642  mov     eax, [esi+8]
0x10011645  mov     dword ptr [eax+64h], 0FFFFFFFFh
0x1001164c  mov     eax, [esi+8]
0x1001164f  mov     ecx, [eax+38h]; this
0x10011652  test    ecx, ecx
0x10011654  jz      short loc_10011665
0x10011656  call    ?Release@CTransactionState@@QAEKXZ; CTransactionState::Release(void)
0x1001165b  mov     eax, [esi+8]
0x1001165e  mov     dword ptr [eax+38h], 0
0x10011665  mov     eax, [esi+8]
0x10011668  mov     ecx, [ebp+arg_4]
0x1001166b  mov     eax, [eax+34h]
0x1001166e  push    dword ptr [ecx+14h]
0x10011671  push    dword ptr [eax+14h]
0x10011674  push    dword ptr [eax+10h]
0x10011677  call    ds:__imp__JetDeleteTable@12; JetDeleteTable(x,x,x)
0x1001167d  cmp     eax, 0FFFFFAE7h
0x10011682  jg      short loc_100116A9
0x10011684  jz      short loc_100116A2
0x10011686  cmp     eax, 0FFFFE04Eh
0x1001168b  jz      short loc_1001169B
0x1001168d  cmp     eax, 0FFFFF88Dh
0x10011692  jz      short loc_1001169B
0x10011694  cmp     eax, 0FFFFF8EFh
0x10011699  jnz     short loc_100116BB
0x1001169b  mov     ebx, 80040E09h
0x100116a0  jmp     short loc_100116CB
0x100116a2  mov     ebx, 80040E76h
0x100116a7  jmp     short loc_100116CB
0x100116a9  cmp     eax, 0FFFFFAE8h
0x100116ae  jz      short loc_100116C2
0x100116b0  cmp     eax, 0FFFFFAEAh
0x100116b5  jz      short loc_100116C2
0x100116b7  test    eax, eax
0x100116b9  jz      short loc_10011713
0x100116bb  mov     ebx, 80004005h
0x100116c0  jmp     short loc_100116C7
0x100116c2  mov     ebx, 80040E40h
0x100116c7  test    eax, eax
0x100116c9  jz      short loc_100116E8
0x100116cb  push    offset _IID_ICommandPersist; int
0x100116d0  push    eax; unsigned int
0x100116d1  mov     eax, [esi+8]
0x100116d4  mov     edx, ebx
0x100116d6  mov     ecx, [eax+34h]
0x100116d9  mov     ecx, [ecx+10h]
0x100116dc  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x100116e1  jmp     short loc_10011713
0x100116e3  mov     ebx, 80040E76h
0x100116e8  mov     eax, [esi+8]
0x100116eb  lea     ecx, [ebp+var_14]
0x100116ee  push    3
0x100116f0  push    4
0x100116f2  push    ecx
0x100116f3  mov     eax, [eax+34h]
0x100116f6  push    dword ptr [eax+14h]
0x100116f9  push    dword ptr [eax+10h]
0x100116fc  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10011702  test    eax, eax
0x10011704  jnz     short loc_10011713
0x10011706  push    eax; int
0x10011707  push    offset _IID_ICommandPersist; int
0x1001170c  mov     edx, ebx
0x1001170e  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10011713  test    edi, edi
0x10011715  jz      short loc_1001171E
0x10011717  push    edi; lpCriticalSection
0x10011718  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001171e  mov     eax, ebx
0x10011720  mov     ecx, [ebp+var_C]
0x10011723  mov     large fs:0, ecx
0x1001172a  pop     ecx
0x1001172b  pop     edi
0x1001172c  pop     esi
0x1001172d  pop     ebx
0x1001172e  mov     esp, ebp
0x10011730  pop     ebp
0x10011731  retn    8
0x1004e000  lea     ecx, [ebp+var_10]; this
0x1004e003  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004e008  lea     ecx, [ebp+var_14]; this
0x1004e00b  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004e015  nop
0x1004e016  nop
0x1004e017  mov     edx, [esp-4+arg_4]
0x1004e01b  lea     eax, [edx+0Ch]
0x1004e01e  mov     ecx, [edx-18h]
0x1004e021  xor     ecx, eax; StackCookie
0x1004e023  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e028  mov     eax, offset stru_1004F57C
0x1004e02d  jmp     ___CxxFrameHandler3
```
