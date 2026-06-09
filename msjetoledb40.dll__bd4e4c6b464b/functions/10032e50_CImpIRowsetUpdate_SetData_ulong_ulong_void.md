# CImpIRowsetUpdate::SetData(ulong,ulong,void *)

- ea: `0x10032e50`
- end: `0x10032fe0`
- name: `?SetData@CImpIRowsetUpdate@@UAGJKKPAX@Z`
- size: `400`
- prototype: `int(CImpIRowsetUpdate *__hidden this, unsigned int, unsigned int, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x1000ba90`
- `0x1001c380`
- `0x1001c680`
- `0x1001f2d0`
- `0x1001fc50`
- `0x10029a90`
- `0x10032e50`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10032fc4`
- `KERNEL32!LeaveCriticalSection` at `0x10032fc4`
- `KERNEL32!EnterCriticalSection` at `0x10032ed9`
- `KERNEL32!EnterCriticalSection` at `0x10032ed9`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10032e7e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10032e7e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10032fa8`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10032fa8`

## pseudocode

```c
int __stdcall CImpIRowsetUpdate::SetData(CImpIRowsetUpdate *this, struct tagOreoHROW *a2, unsigned int a3, CRowset *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // esi
  struct _RTL_CRITICAL_SECTION *v5; // edx
  _DWORD *LockSemaphore; // eax
  CTransactionState *v7; // ecx
  int isZombie; // eax
  int v9; // edi
  int v10; // edi
  int v11; // eax
  JET_ERR *PtrOfExtBuffer; // eax
  JET_ERR *v13; // edi
  JET_ERR v14; // eax
  CExtBuffer *v16; // [esp+0h] [ebp-2Ch]
  unsigned int v17; // [esp+4h] [ebp-28h]
  char v18[4]; // [esp+10h] [ebp-1Ch] BYREF
  JoltProperties *v19; // [esp+14h] [ebp-18h]
  unsigned int v20; // [esp+18h] [ebp-14h] BYREF
  struct _RTL_CRITICAL_SECTION *v21; // [esp+1Ch] [ebp-10h]
  int v22; // [esp+28h] [ebp-4h]

  SetErrorInfo(0, 0);
  v4 = 0;
  v21 = 0;
  v22 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)*((_DWORD *)this + 2);
  LockSemaphore = v5[2].LockSemaphore;
  if ( LockSemaphore
    && (LockSemaphore[4] != 1 || (v7 = (CTransactionState *)LockSemaphore[2]) == 0
      ? (isZombie = LockSemaphore[3])
      : (isZombie = CTransactionState::isZombie(v7)),
        isZombie == 1) )
  {
    v9 = -2147418113;
  }
  else if ( ((int)v5[4].DebugInfo & 0x400) != 0 )
  {
    v9 = -2147217888;
  }
  else
  {
    v4 = v5 + 3;
    v21 = v5 + 3;
    EnterCriticalSection(v5 + 3);
    v10 = *((_DWORD *)this + 2);
    v19 = *(JoltProperties **)(v10 + 160);
    if ( JoltProperties::BinarySearch(v19, 0x75u, &v20) >= 0
      && (v11 = *(_DWORD *)(*(_DWORD *)(v10 + 160) + 16), *(_WORD *)(v11 + 48 * v20 + 16) == 3)
      && (*(_BYTE *)(v11 + 48 * v20 + 24) & 1) != 0 )
    {
      PtrOfExtBuffer = (JET_ERR *)CExtBuffer::GetPtrOfExtBuffer(v16, v17);
      v13 = PtrOfExtBuffer;
      if ( !PtrOfExtBuffer || *PtrOfExtBuffer == -1 )
      {
        v9 = -2147217916;
      }
      else
      {
        v14 = PtrOfExtBuffer[1];
        if ( v14 != 4 && v14 != 16 )
        {
          JoltProperties::GetIntValue(v19, 0xECu, &v20);
          v9 = CRowset::UtilSetData(
                 a3,
                 *((_DWORD **)this + 2),
                 a4,
                 v13,
                 2 * (v20 == 1) + 2,
                 a2,
                 1u,
                 (unsigned int)v16,
                 v17);
          goto LABEL_23;
        }
        v9 = -2147217885;
      }
    }
    else
    {
      v9 = -2147217837;
    }
  }
  if ( !JetGetDatabaseInfo(
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 56) + 16),
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 56) + 20),
          v18,
          4,
          3) )
    CExtError::SendHRtoOLEAuto(v9, (__int128 *)&IID_IRowsetUpdate, 0, (const struct _GUID *)v16, v17);
LABEL_23:
  if ( v4 )
    LeaveCriticalSection(v4);
  return v9;
}

```

## disassembly

```asm
0x10032e50  mov     edi, edi
0x10032e52  push    ebp
0x10032e53  mov     ebp, esp
0x10032e55  push    0FFFFFFFFh
0x10032e57  push    offset ?SetData@CImpIRowsetUpdate@@UAGJKKPAX@Z_SEH
0x10032e5c  mov     eax, large fs:0
0x10032e62  push    eax
0x10032e63  sub     esp, 10h
0x10032e66  push    ebx
0x10032e67  push    esi
0x10032e68  push    edi; int
0x10032e69  mov     eax, ___security_cookie
0x10032e6e  xor     eax, ebp
0x10032e70  push    eax; struct _GUID *
0x10032e71  lea     eax, [ebp+var_C]
0x10032e74  mov     large fs:0, eax
0x10032e7a  push    0; perrinfo
0x10032e7c  push    0; dwReserved
0x10032e7e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10032e84  xor     esi, esi
0x10032e86  mov     [ebp+var_10], esi
0x10032e89  mov     ebx, [ebp+this]
0x10032e8c  mov     [ebp+var_4], esi
0x10032e8f  mov     edx, [ebx+8]
0x10032e92  mov     eax, [edx+40h]
0x10032e95  test    eax, eax
0x10032e97  jz      short loc_10032EBF
0x10032e99  cmp     dword ptr [eax+10h], 1
0x10032e9d  jnz     short loc_10032EAD
0x10032e9f  mov     ecx, [eax+8]; this
0x10032ea2  test    ecx, ecx
0x10032ea4  jz      short loc_10032EAD
0x10032ea6  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x10032eab  jmp     short loc_10032EB0
0x10032ead  mov     eax, [eax+0Ch]
0x10032eb0  cmp     eax, 1
0x10032eb3  jnz     short loc_10032EBF
0x10032eb5  mov     edi, 8000FFFFh
0x10032eba  jmp     loc_10032F94
0x10032ebf  test    dword ptr [edx+60h], 400h
0x10032ec6  jz      short loc_10032ED2
0x10032ec8  mov     edi, 80040E20h
0x10032ecd  jmp     loc_10032F94
0x10032ed2  lea     esi, [edx+48h]
0x10032ed5  push    esi; lpCriticalSection
0x10032ed6  mov     [ebp+var_10], esi
0x10032ed9  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10032edf  mov     edi, [ebx+8]
0x10032ee2  lea     ecx, [ebp+var_14]
0x10032ee5  push    ecx; unsigned int *
0x10032ee6  push    75h ; 'u'; unsigned int
0x10032ee8  mov     eax, [edi+0A0h]
0x10032eee  mov     ecx, eax; this
0x10032ef0  mov     [ebp+var_18], eax
0x10032ef3  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10032ef8  test    eax, eax
0x10032efa  js      loc_10032F8F
0x10032f00  mov     eax, [ebp+var_14]
0x10032f03  mov     edx, 3
0x10032f08  lea     ecx, [eax+eax*2]
0x10032f0b  mov     eax, [edi+0A0h]
0x10032f11  add     ecx, ecx
0x10032f13  mov     eax, [eax+10h]
0x10032f16  cmp     dx, [eax+ecx*8+10h]
0x10032f1b  jnz     short loc_10032F8F
0x10032f1d  test    byte ptr [eax+ecx*8+18h], 1
0x10032f22  jz      short loc_10032F8F
0x10032f24  mov     ecx, [edi+68h]
0x10032f27  mov     edx, [ebp+arg_4]
0x10032f2a  call    ?GetPtrOfExtBuffer@CExtBuffer@@QAGPAXK@Z; CExtBuffer::GetPtrOfExtBuffer(ulong)
0x10032f2f  mov     edi, eax
0x10032f31  test    edi, edi
0x10032f33  jz      short loc_10032F88
0x10032f35  cmp     dword ptr [edi], 0FFFFFFFFh
0x10032f38  jz      short loc_10032F88
0x10032f3a  mov     eax, [edi+4]
0x10032f3d  cmp     eax, 4
0x10032f40  jz      short loc_10032F81
0x10032f42  cmp     eax, 10h
0x10032f45  jz      short loc_10032F81
0x10032f47  mov     ecx, [ebp+var_18]; this
0x10032f4a  lea     eax, [ebp+var_14]
0x10032f4d  push    eax; unsigned int *
0x10032f4e  push    0ECh; unsigned int
0x10032f53  call    ?GetIntValue@JoltProperties@@QBEJKAAK@Z; JoltProperties::GetIntValue(ulong,ulong &)
0x10032f58  mov     edx, [ebp+arg_8]
0x10032f5b  xor     eax, eax
0x10032f5d  cmp     [ebp+var_14], 1
0x10032f61  mov     ecx, [ebx+8]
0x10032f64  push    1; unsigned int
0x10032f66  push    [ebp+arg_4]; struct tagOreoHROW *
0x10032f69  setz    al
0x10032f6c  lea     eax, ds:2[eax*2]
0x10032f73  push    eax; void *
0x10032f74  push    edi; unsigned int
0x10032f75  push    [ebp+arg_C]; this
0x10032f78  call    ?UtilSetData@CRowset@@IAGJKPBXPAUtagOreoHROW@@KKH@Z; CRowset::UtilSetData(ulong,void const *,tagOreoHROW *,ulong,ulong,int)
0x10032f7d  mov     edi, eax
0x10032f7f  jmp     short loc_10032FBF
0x10032f81  mov     edi, 80040E23h
0x10032f86  jmp     short loc_10032F94
0x10032f88  mov     edi, 80040E04h
0x10032f8d  jmp     short loc_10032F94
0x10032f8f  mov     edi, 80040E53h
0x10032f94  mov     eax, [ebx+8]
0x10032f97  lea     ecx, [ebp+var_1C]
0x10032f9a  push    3
0x10032f9c  push    4
0x10032f9e  push    ecx
0x10032f9f  mov     eax, [eax+38h]
0x10032fa2  push    dword ptr [eax+14h]
0x10032fa5  push    dword ptr [eax+10h]
0x10032fa8  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10032fae  test    eax, eax
0x10032fb0  jnz     short loc_10032FBF
0x10032fb2  push    eax; int
0x10032fb3  push    offset _IID_IRowsetUpdate; int
0x10032fb8  mov     edx, edi
0x10032fba  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10032fbf  test    esi, esi
0x10032fc1  jz      short loc_10032FCA
0x10032fc3  push    esi; lpCriticalSection
0x10032fc4  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10032fca  mov     eax, edi
0x10032fcc  mov     ecx, [ebp+var_C]
0x10032fcf  mov     large fs:0, ecx
0x10032fd6  pop     ecx
0x10032fd7  pop     edi
0x10032fd8  pop     esi
0x10032fd9  pop     ebx
0x10032fda  mov     esp, ebp
0x10032fdc  pop     ebp
0x10032fdd  retn    10h
0x1004eda0  lea     ecx, [ebp+var_10]; this
0x1004eda3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004edad  nop
0x1004edae  nop
0x1004edaf  mov     edx, [esp-4+arg_4]
0x1004edb3  lea     eax, [edx+0Ch]
0x1004edb6  mov     ecx, [edx-20h]
0x1004edb9  xor     ecx, eax; StackCookie
0x1004edbb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004edc0  mov     eax, offset stru_1004FF80
0x1004edc5  jmp     ___CxxFrameHandler3
```
