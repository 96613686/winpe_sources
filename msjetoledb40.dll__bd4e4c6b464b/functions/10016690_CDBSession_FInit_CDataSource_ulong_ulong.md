# CDBSession::FInit(CDataSource *,ulong,ulong)

- ea: `0x10016690`
- end: `0x100167f5`
- name: `?FInit@CDBSession@@QAEJPAVCDataSource@@KK@Z`
- size: `357`
- prototype: `int __thiscall(CDBSession *__hidden this, struct CDataSource *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1001a7b0`
- `0x1001a970`

## callees

- `0x10016040`
- `0x10016690`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1001f2d0`

## import_xrefs

- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100166a1`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100166a1`
- `msjet40!__imp__JetCloseDatabase@12` at `0x100167ba`
- `msjet40!__imp__JetCloseDatabase@12` at `0x100167ba`
- `msjet40!__imp__JetEndSession@8` at `0x100167d2`
- `msjet40!__imp__JetEndSession@8` at `0x100167d2`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10016795`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10016795`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10016730`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10016730`

## pseudocode

```c
int __thiscall CDBSession::FInit(CDBSession *this, struct CDataSource *a2, unsigned int a3, unsigned int a4)
{
  int v4; // ebx
  int v6; // ecx
  int v7; // eax
  int v8; // esi
  int result; // eax
  int v10; // ebx
  JET_DBID v11; // eax
  JET_SESID v12; // eax
  const struct _GUID *v13; // [esp+0h] [ebp-14h]
  const struct _GUID *v14; // [esp+4h] [ebp-10h]
  JoltProperties *v15; // [esp+Ch] [ebp-8h] BYREF
  unsigned int v16; // [esp+10h] [ebp-4h] BYREF

  v4 = 0;
  SetErrorInfo(0, 0);
  v6 = *((_DWORD *)this + 21);
  if ( v6 )
    (*(void (__thiscall **)(_DWORD, _DWORD))(*(_DWORD *)v6 + 8))(*(_DWORD *)(*(_DWORD *)v6 + 8), *((_DWORD *)this + 21));
  *((_DWORD *)this + 21) = a2;
  (*(void (__thiscall **)(_DWORD, _DWORD))(**((_DWORD **)a2 + 2) + 4))(
    *(_DWORD *)(**((_DWORD **)a2 + 2) + 4),
    *((_DWORD *)a2 + 2));
  _InterlockedIncrement((volatile signed __int32 *)(*((_DWORD *)this + 21) + 124));
  *((_DWORD *)this + 5) = a4;
  v7 = *((_DWORD *)this + 21);
  *((_DWORD *)this + 4) = a3;
  v15 = *(JoltProperties **)(v7 + 164);
  if ( JoltProperties::BinarySearch(v15, 0x118u, &v16) >= 0
    && *(_WORD *)(*((_DWORD *)v15 + 4) + 48 * v16 + 24) == 0xFFFF )
  {
    v4 = JetSetSystemParameter(*((_DWORD *)this + 21) + 96, a3, 72, 1, 0);
    if ( v4 < 0 )
    {
      v8 = -2147467259;
      goto LABEL_9;
    }
  }
  v16 = v4;
  result = CDBSession::FInit(this);
  v10 = result;
  v8 = result;
  if ( v16 )
  {
    v4 = v16;
LABEL_9:
    CExtError::SendJetErrortoOLEAuto(v8, *((char **)this + 4), v4, (int)&IID_IDBCreateSession, (int)v13, v14);
    if ( v8 >= 0 )
      return v8;
    goto LABEL_15;
  }
  if ( result >= 0 )
    return result;
  v8 = result;
  if ( result != -2147024882 && !JetGetDatabaseInfo(*((_DWORD *)this + 4), *((_DWORD *)this + 5), &v15, 4, 3) )
    CExtError::SendHRtoOLEAuto(v10, (__int128 *)&IID_IDBCreateSession, 0, v13, (int)v14);
LABEL_15:
  v11 = *((_DWORD *)this + 5);
  if ( v11 != -1 )
  {
    JetCloseDatabase(*((_DWORD *)this + 4), v11, 0);
    *((_DWORD *)this + 5) = -1;
  }
  v12 = *((_DWORD *)this + 4);
  if ( v12 != -1 )
  {
    JetEndSession(v12, 1u);
    *((_DWORD *)this + 4) = -1;
  }
  return v8;
}

```

## disassembly

```asm
0x10016690  mov     edi, edi
0x10016692  push    ebp
0x10016693  mov     ebp, esp
0x10016695  sub     esp, 8
0x10016698  push    ebx
0x10016699  push    esi; int
0x1001669a  push    edi; struct _GUID *
0x1001669b  xor     ebx, ebx
0x1001669d  mov     edi, ecx
0x1001669f  push    ebx; perrinfo
0x100166a0  push    ebx; dwReserved
0x100166a1  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x100166a7  mov     ecx, [edi+54h]
0x100166aa  test    ecx, ecx
0x100166ac  jz      short loc_100166BE
0x100166ae  mov     eax, [ecx]
0x100166b0  push    ecx
0x100166b1  mov     esi, [eax+8]
0x100166b4  mov     ecx, esi
0x100166b6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100166bc  call    esi
0x100166be  mov     eax, [ebp+arg_0]
0x100166c1  mov     [edi+54h], eax
0x100166c4  mov     eax, [eax+8]
0x100166c7  push    eax
0x100166c8  mov     ecx, [eax]
0x100166ca  mov     esi, [ecx+4]
0x100166cd  mov     ecx, esi
0x100166cf  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100166d5  call    esi
0x100166d7  mov     eax, [edi+54h]
0x100166da  add     eax, 7Ch ; '|'
0x100166dd  lock inc dword ptr [eax]
0x100166e0  mov     eax, [ebp+arg_8]
0x100166e3  lea     ecx, [ebp+var_4]
0x100166e6  mov     esi, [ebp+arg_4]
0x100166e9  mov     [edi+14h], eax
0x100166ec  mov     eax, [edi+54h]
0x100166ef  push    ecx; unsigned int *
0x100166f0  mov     [edi+10h], esi
0x100166f3  push    118h; unsigned int
0x100166f8  mov     eax, [eax+0A4h]
0x100166fe  mov     ecx, eax; this
0x10016700  mov     [ebp+var_8], eax
0x10016703  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10016708  test    eax, eax
0x1001670a  js      short loc_10016743
0x1001670c  mov     eax, [ebp+var_4]
0x1001670f  lea     ecx, [eax+eax*2]
0x10016712  mov     eax, [ebp+var_8]
0x10016715  add     ecx, ecx
0x10016717  mov     eax, [eax+10h]
0x1001671a  cmp     word ptr [eax+ecx*8+18h], 0FFFFh
0x10016720  jnz     short loc_10016743
0x10016722  mov     eax, [edi+54h]
0x10016725  push    0
0x10016727  push    1
0x10016729  push    48h ; 'H'
0x1001672b  push    esi
0x1001672c  add     eax, 60h ; '`'
0x1001672f  push    eax
0x10016730  call    ds:__imp__JetSetSystemParameter@20; JetSetSystemParameter(x,x,x,x,x)
0x10016736  mov     ebx, eax
0x10016738  test    ebx, ebx
0x1001673a  jns     short loc_10016743
0x1001673c  mov     esi, 80004005h
0x10016741  jmp     short loc_1001675A
0x10016743  mov     ecx, edi; this
0x10016745  mov     [ebp+var_4], ebx
0x10016748  call    ?FInit@CDBSession@@QAEJXZ; CDBSession::FInit(void)
0x1001674d  mov     ebx, eax
0x1001674f  cmp     [ebp+var_4], 0
0x10016753  mov     esi, ebx
0x10016755  jz      short loc_10016779
0x10016757  mov     ebx, [ebp+var_4]
0x1001675a  mov     ecx, [edi+10h]
0x1001675d  mov     edx, esi
0x1001675f  push    offset _IID_IDBCreateSession; int
0x10016764  push    ebx; unsigned int
0x10016765  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1001676a  test    esi, esi
0x1001676c  js      short loc_100167AC
0x1001676e  pop     edi
0x1001676f  mov     eax, esi
0x10016771  pop     esi
0x10016772  pop     ebx
0x10016773  mov     esp, ebp
0x10016775  pop     ebp
0x10016776  retn    0Ch
0x10016779  test    ebx, ebx
0x1001677b  jns     short loc_100167EA
0x1001677d  mov     esi, ebx
0x1001677f  cmp     ebx, 8007000Eh
0x10016785  jz      short loc_100167AC
0x10016787  push    3
0x10016789  push    4
0x1001678b  lea     eax, [ebp+var_8]
0x1001678e  push    eax
0x1001678f  push    dword ptr [edi+14h]
0x10016792  push    dword ptr [edi+10h]
0x10016795  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1001679b  test    eax, eax
0x1001679d  jnz     short loc_100167AC
0x1001679f  push    eax; int
0x100167a0  push    offset _IID_IDBCreateSession; int
0x100167a5  mov     edx, ebx
0x100167a7  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x100167ac  mov     eax, [edi+14h]
0x100167af  cmp     eax, 0FFFFFFFFh
0x100167b2  jz      short loc_100167C7
0x100167b4  push    0; grbit
0x100167b6  push    eax; dbid
0x100167b7  push    dword ptr [edi+10h]; sesid
0x100167ba  call    ds:__imp__JetCloseDatabase@12; JetCloseDatabase(x,x,x)
0x100167c0  mov     dword ptr [edi+14h], 0FFFFFFFFh
0x100167c7  mov     eax, [edi+10h]
0x100167ca  cmp     eax, 0FFFFFFFFh
0x100167cd  jz      short loc_100167DF
0x100167cf  push    1; grbit
0x100167d1  push    eax; sesid
0x100167d2  call    ds:__imp__JetEndSession@8; JetEndSession(x,x)
0x100167d8  mov     dword ptr [edi+10h], 0FFFFFFFFh
0x100167df  pop     edi
0x100167e0  mov     eax, esi
0x100167e2  pop     esi
0x100167e3  pop     ebx
0x100167e4  mov     esp, ebp
0x100167e6  pop     ebp
0x100167e7  retn    0Ch
0x100167ea  pop     edi
0x100167eb  pop     esi
0x100167ec  mov     eax, ebx
0x100167ee  pop     ebx
0x100167ef  mov     esp, ebp
0x100167f1  pop     ebp
0x100167f2  retn    0Ch
```
