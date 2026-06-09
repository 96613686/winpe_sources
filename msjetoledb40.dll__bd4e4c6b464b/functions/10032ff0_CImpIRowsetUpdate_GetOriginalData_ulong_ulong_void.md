# CImpIRowsetUpdate::GetOriginalData(ulong,ulong,void *)

- ea: `0x10032ff0`
- end: `0x10033167`
- name: `?GetOriginalData@CImpIRowsetUpdate@@UAGJKKPAX@Z`
- size: `375`
- prototype: `int(CImpIRowsetUpdate *__hidden this, unsigned int, unsigned int, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x1000ba90`
- `0x1001c380`
- `0x1002b570`
- `0x10032ff0`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1003314b`
- `KERNEL32!LeaveCriticalSection` at `0x1003314b`
- `KERNEL32!EnterCriticalSection` at `0x1003309d`
- `KERNEL32!EnterCriticalSection` at `0x1003309d`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1003301e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1003301e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003312f`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003312f`

## pseudocode

```c
int __stdcall CImpIRowsetUpdate::GetOriginalData(
        CImpIRowsetUpdate *this,
        struct tagOreoHROW *a2,
        unsigned int a3,
        CRowset *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // esi
  _DWORD *LockSemaphore; // eax
  CTransactionState *v6; // ecx
  int isZombie; // eax
  struct _RTL_CRITICAL_SECTION *v9; // esi
  _DWORD *v10; // edi
  _DWORD *v11; // eax
  int Data; // edi
  const struct _GUID *v13; // [esp+0h] [ebp-28h]
  int *v14; // [esp+4h] [ebp-24h]
  _BYTE v15[4]; // [esp+10h] [ebp-18h] BYREF
  struct _RTL_CRITICAL_SECTION *v16; // [esp+14h] [ebp-14h]
  unsigned __int16 v17[2]; // [esp+18h] [ebp-10h] BYREF
  int v18; // [esp+24h] [ebp-4h]

  SetErrorInfo(0, 0);
  v18 = 0;
  *(_DWORD *)v17 = 1;
  v4 = (struct _RTL_CRITICAL_SECTION *)*((_DWORD *)this + 2);
  LockSemaphore = v4[2].LockSemaphore;
  if ( LockSemaphore )
  {
    if ( LockSemaphore[4] == 1 && (v6 = (CTransactionState *)LockSemaphore[2]) != 0 )
      isZombie = CTransactionState::isZombie(v6);
    else
      isZombie = LockSemaphore[3];
    if ( isZombie == 1 )
      return -2147418113;
  }
  if ( ((int)v4[4].DebugInfo & 0x400) != 0 )
    return -2147217888;
  v9 = v4 + 3;
  v16 = v9;
  EnterCriticalSection(v9);
  v10 = *(_DWORD **)(*((_DWORD *)this + 2) + 104);
  if ( (unsigned int)a2 > v10[6] + 8 * v10[5] - 1
    || (*(_BYTE *)((((unsigned int)a2 - v10[6]) >> 3) + v10[4])
      & *((_BYTE *)&Bitmap::ThisBit + (((unsigned int)a2 - v10[6]) & 7))) != 0
    || (v11 = (_DWORD *)(v10[2] + (_DWORD)a2 * *v10)) == 0
    || *v11 == -1 )
  {
    Data = -2147217916;
LABEL_17:
    if ( !*(_DWORD *)v17
      && Data != -2147024882
      && !JetGetDatabaseInfo(
            *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 56) + 16),
            *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 56) + 20),
            v15,
            4,
            3) )
    {
      CExtError::SendHRtoOLEAuto(Data, (__int128 *)&IID_IRowsetUpdate, 0, v13, (int)v14);
    }
    goto LABEL_21;
  }
  Data = CRowset::UtilGetData(a3, *((CRowset **)this + 2), a4, v11, (const void *)1, a2, v17, (unsigned int)v13, v14);
  if ( Data < 0 )
    goto LABEL_17;
LABEL_21:
  if ( v9 )
    LeaveCriticalSection(v9);
  return Data;
}

```

## disassembly

```asm
0x10032ff0  mov     edi, edi
0x10032ff2  push    ebp
0x10032ff3  mov     ebp, esp
0x10032ff5  push    0FFFFFFFFh
0x10032ff7  push    offset ?Hash@CImpIRowsetLocate@@UAGJKKQBKQAPBEQAK2@Z_SEH
0x10032ffc  mov     eax, large fs:0
0x10033002  push    eax
0x10033003  sub     esp, 0Ch
0x10033006  push    ebx
0x10033007  push    esi
0x10033008  push    edi; int
0x10033009  mov     eax, ___security_cookie
0x1003300e  xor     eax, ebp
0x10033010  push    eax; struct _GUID *
0x10033011  lea     eax, [ebp+var_C]
0x10033014  mov     large fs:0, eax
0x1003301a  push    0; perrinfo
0x1003301c  push    0; dwReserved
0x1003301e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10033024  mov     ebx, [ebp+this]
0x10033027  mov     [ebp+var_4], 0
0x1003302e  mov     dword ptr [ebp+var_10], 1
0x10033035  mov     esi, [ebx+8]
0x10033038  mov     eax, [esi+40h]
0x1003303b  test    eax, eax
0x1003303d  jz      short loc_10033074
0x1003303f  cmp     dword ptr [eax+10h], 1
0x10033043  jnz     short loc_10033053
0x10033045  mov     ecx, [eax+8]; this
0x10033048  test    ecx, ecx
0x1003304a  jz      short loc_10033053
0x1003304c  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x10033051  jmp     short loc_10033056
0x10033053  mov     eax, [eax+0Ch]
0x10033056  cmp     eax, 1
0x10033059  jnz     short loc_10033074
0x1003305b  mov     eax, 8000FFFFh
0x10033060  mov     ecx, [ebp+var_C]
0x10033063  mov     large fs:0, ecx
0x1003306a  pop     ecx
0x1003306b  pop     edi
0x1003306c  pop     esi
0x1003306d  pop     ebx
0x1003306e  mov     esp, ebp
0x10033070  pop     ebp
0x10033071  retn    10h
0x10033074  test    dword ptr [esi+60h], 400h
0x1003307b  jz      short loc_10033096
0x1003307d  mov     eax, 80040E20h
0x10033082  mov     ecx, [ebp+var_C]
0x10033085  mov     large fs:0, ecx
0x1003308c  pop     ecx
0x1003308d  pop     edi
0x1003308e  pop     esi
0x1003308f  pop     ebx
0x10033090  mov     esp, ebp
0x10033092  pop     ebp
0x10033093  retn    10h
0x10033096  add     esi, 48h ; 'H'
0x10033099  push    esi; lpCriticalSection
0x1003309a  mov     [ebp+var_14], esi
0x1003309d  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100330a3  mov     eax, [ebx+8]
0x100330a6  mov     ecx, [ebp+arg_4]
0x100330a9  mov     edi, [eax+68h]
0x100330ac  mov     eax, [edi+14h]
0x100330af  lea     eax, ds:0FFFFFFFFh[eax*8]
0x100330b6  add     eax, [edi+18h]
0x100330b9  cmp     ecx, eax
0x100330bb  ja      short loc_10033108
0x100330bd  mov     eax, [edi+10h]
0x100330c0  mov     edx, ecx
0x100330c2  sub     edx, [edi+18h]
0x100330c5  mov     ecx, edx
0x100330c7  and     edx, 7
0x100330ca  shr     ecx, 3
0x100330cd  mov     al, [ecx+eax]
0x100330d0  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x100330d6  jnz     short loc_10033108
0x100330d8  mov     eax, [edi]
0x100330da  mov     edx, [ebp+arg_4]
0x100330dd  imul    eax, edx
0x100330e0  add     eax, [edi+8]
0x100330e3  jz      short loc_10033108
0x100330e5  cmp     dword ptr [eax], 0FFFFFFFFh
0x100330e8  jz      short loc_10033108
0x100330ea  lea     ecx, [ebp+var_10]
0x100330ed  push    ecx; unsigned __int16
0x100330ee  mov     ecx, [ebx+8]
0x100330f1  push    edx; struct tagOreoHROW *
0x100330f2  mov     edx, [ebp+arg_8]
0x100330f5  push    1; void *
0x100330f7  push    eax; unsigned int
0x100330f8  push    [ebp+arg_C]; this
0x100330fb  call    ?UtilGetData@CRowset@@IAGJKPBXPAUtagOreoHROW@@GKAAH@Z; CRowset::UtilGetData(ulong,void const *,tagOreoHROW *,ushort,ulong,int &)
0x10033100  mov     edi, eax
0x10033102  test    edi, edi
0x10033104  jns     short loc_10033146
0x10033106  jmp     short loc_1003310D
0x10033108  mov     edi, 80040E04h
0x1003310d  cmp     dword ptr [ebp+var_10], 0
0x10033111  jnz     short loc_10033146
0x10033113  mov     eax, [ebx+8]
0x10033116  mov     eax, [eax+38h]
0x10033119  cmp     edi, 8007000Eh
0x1003311f  jz      short loc_10033146
0x10033121  push    3
0x10033123  push    4
0x10033125  lea     ecx, [ebp+var_18]
0x10033128  push    ecx
0x10033129  push    dword ptr [eax+14h]
0x1003312c  push    dword ptr [eax+10h]
0x1003312f  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10033135  test    eax, eax
0x10033137  jnz     short loc_10033146
0x10033139  push    eax; int
0x1003313a  push    offset _IID_IRowsetUpdate; int
0x1003313f  mov     edx, edi
0x10033141  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10033146  test    esi, esi
0x10033148  jz      short loc_10033151
0x1003314a  push    esi; lpCriticalSection
0x1003314b  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10033151  mov     eax, edi
0x10033153  mov     ecx, [ebp+var_C]
0x10033156  mov     large fs:0, ecx
0x1003315d  pop     ecx
0x1003315e  pop     edi
0x1003315f  pop     esi
0x10033160  pop     ebx
0x10033161  mov     esp, ebp
0x10033163  pop     ebp
0x10033164  retn    10h
0x1004dd20  lea     ecx, [ebp+var_14]; this
0x1004dd23  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dd2d  nop
0x1004dd2e  nop
0x1004dd2f  mov     edx, [esp-4+arg_4]
0x1004dd33  lea     eax, [edx+0Ch]
0x1004dd36  mov     ecx, [edx-1Ch]
0x1004dd39  xor     ecx, eax; StackCookie
0x1004dd3b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004dd40  mov     eax, offset stru_1004F328
0x1004dd45  jmp     ___CxxFrameHandler3
```
