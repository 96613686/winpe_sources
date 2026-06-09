# CImpIRowsetUpdate::InsertRow(ulong,ulong,void *,ulong *)

- ea: `0x10032ba0`
- end: `0x10032e44`
- name: `?InsertRow@CImpIRowsetUpdate@@UAGJKKPAXPAK@Z`
- size: `676`
- prototype: `int(CImpIRowsetUpdate *__hidden this, unsigned int, unsigned int, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update`

## callees

- `0x1000ba90`
- `0x10015b10`
- `0x1001c380`
- `0x1001c5c0`
- `0x1001c680`
- `0x1001f2d0`
- `0x10027a40`
- `0x10027a60`
- `0x10029a90`
- `0x10032ba0`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10032e1e`
- `KERNEL32!LeaveCriticalSection` at `0x10032e1e`
- `KERNEL32!EnterCriticalSection` at `0x10032c50`
- `KERNEL32!EnterCriticalSection` at `0x10032c50`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10032bee`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10032bee`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10032e02`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10032e02`

## pseudocode

```c
int __stdcall CImpIRowsetUpdate::InsertRow(
        CImpIRowsetUpdate *this,
        unsigned int a2,
        unsigned int a3,
        CRowset *a4,
        unsigned int *a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // esi
  struct _RTL_CRITICAL_SECTION *v6; // edx
  _DWORD *LockSemaphore; // eax
  CTransactionState *v8; // ecx
  int isZombie; // eax
  int v10; // edi
  JoltProperties *v11; // edi
  int v12; // eax
  _DWORD *v13; // ecx
  int inserted; // eax
  bool v15; // zf
  unsigned int v16; // edx
  _DWORD *v17; // eax
  int v18; // eax
  _DWORD *PtrOfExtBuffer; // eax
  const struct _GUID *v21; // [esp+0h] [ebp-44h]
  void *v22; // [esp+0h] [ebp-44h]
  void *v23; // [esp+4h] [ebp-40h]
  unsigned int *v24; // [esp+4h] [ebp-40h]
  unsigned int v25; // [esp+14h] [ebp-30h] BYREF
  CRowset *v26; // [esp+18h] [ebp-2Ch]
  int v27; // [esp+1Ch] [ebp-28h] BYREF
  unsigned int *v28; // [esp+20h] [ebp-24h]
  unsigned int v29; // [esp+24h] [ebp-20h] BYREF
  unsigned int v30[2]; // [esp+28h] [ebp-1Ch] BYREF
  int v31; // [esp+30h] [ebp-14h]
  int v32; // [esp+40h] [ebp-4h]

  v26 = a4;
  v28 = a5;
  v29 = 0;
  v27 = 0;
  SetErrorInfo(0, 0);
  if ( a5 )
    *a5 = 0;
  v5 = 0;
  v32 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)*((_DWORD *)this + 2);
  LockSemaphore = v6[2].LockSemaphore;
  if ( LockSemaphore
    && (LockSemaphore[4] != 1 || (v8 = (CTransactionState *)LockSemaphore[2]) == 0
      ? (isZombie = LockSemaphore[3])
      : (isZombie = CTransactionState::isZombie(v8)),
        isZombie == 1) )
  {
    v10 = -2147418113;
  }
  else if ( ((int)v6[4].DebugInfo & 0x400) != 0 )
  {
    v10 = -2147217888;
  }
  else
  {
    v5 = v6 + 3;
    EnterCriticalSection(v6 + 3);
    v11 = *(JoltProperties **)(*((_DWORD *)this + 2) + 160);
    if ( JoltProperties::BinarySearch(v11, 0x75u, &v25) < 0
      || (v12 = *((_DWORD *)v11 + 4), *(_WORD *)(v12 + 48 * v25 + 16) != 3)
      || (*(_BYTE *)(v12 + 48 * v25 + 24) & 4) == 0 )
    {
      v10 = -2147217837;
      goto LABEL_37;
    }
    if ( a3 )
    {
      CExtBuffer::GetItemOfExtBuffer((CExtBuffer *)&v27, (unsigned int)v21, v23);
      if ( v26 || v27 && !*(_DWORD *)(v27 + 36) )
      {
        if ( !CRowset::RowNotify((CRowset *)&v29, 8u, 0, (enum DBREASONENUM)v21, (enum DBEVENTPHASEENUM)v23) )
        {
          v13 = (_DWORD *)*((_DWORD *)this + 2);
          v30[1] = 8;
          v30[0] = -1;
          v31 = 0;
          v10 = CRowset::UtilSetData(a3, v13, v26, (JET_ERR *)v30, 0, 0, 0, (unsigned int)v21, (int)v23);
          if ( v10 >= 0 )
          {
            if ( v28 )
              ++v31;
            inserted = CExtBuffer::InsertIntoExtBuffer((CExtBuffer *)&v29, v22, v24);
            if ( inserted < 0 )
            {
              v10 = inserted;
              CRowset::RowNotify(
                (CRowset *)&v29,
                8u,
                (const unsigned int *const)3,
                (enum DBREASONENUM)v22,
                (enum DBEVENTPHASEENUM)v24);
              goto LABEL_37;
            }
            if ( v28 )
              *v28 = v29;
            v15 = CPendingChange::IsPending((CPendingChange *)(*((_DWORD *)this + 2) + 220)) == 1;
            v17 = (_DWORD *)*((_DWORD *)this + 2);
            if ( v15 || !v17[59] )
            {
              v17[57] = v16;
              v17[56] = v16;
              v16 = v29;
            }
            v18 = *((_DWORD *)this + 2);
            if ( (*(_BYTE *)(v18 + 96) & 0x10) == 0 )
            {
              *(_DWORD *)(v18 + 228) = v16;
              *(_DWORD *)(v18 + 224) = v16;
              PtrOfExtBuffer = CExtBuffer::GetPtrOfExtBuffer((CExtBuffer *)v22, (unsigned int)v24);
              ++PtrOfExtBuffer[2];
            }
          }
          CRowset::RowNotify(
            (CRowset *)&v29,
            8u,
            (const unsigned int *const)4,
            (enum DBREASONENUM)v22,
            (enum DBEVENTPHASEENUM)v24);
          goto LABEL_40;
        }
        v10 = -2147217842;
      }
      else
      {
        v10 = -2147024809;
      }
    }
    else
    {
      v10 = -2147217920;
    }
  }
LABEL_37:
  if ( v10 != -2147024882
    && !JetGetDatabaseInfo(
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 56) + 16),
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 56) + 20),
          &v25,
          4,
          3) )
  {
    CExtError::SendHRtoOLEAuto(v10, (__int128 *)&IID_IRowsetUpdate, 0, v21, (int)v23);
  }
LABEL_40:
  if ( v5 )
    LeaveCriticalSection(v5);
  return v10;
}

```

## disassembly

```asm
0x10032ba0  mov     edi, edi
0x10032ba2  push    ebp
0x10032ba3  mov     ebp, esp
0x10032ba5  push    0FFFFFFFFh
0x10032ba7  push    offset ?InsertRow@CImpIRowsetUpdate@@UAGJKKPAXPAK@Z_SEH
0x10032bac  mov     eax, large fs:0
0x10032bb2  push    eax
0x10032bb3  sub     esp, 28h
0x10032bb6  mov     eax, ___security_cookie
0x10032bbb  xor     eax, ebp
0x10032bbd  mov     [ebp+var_10], eax
0x10032bc0  push    ebx
0x10032bc1  push    esi
0x10032bc2  push    edi; int
0x10032bc3  push    eax; struct _GUID *
0x10032bc4  lea     eax, [ebp+var_C]
0x10032bc7  mov     large fs:0, eax
0x10032bcd  mov     eax, [ebp+arg_C]
0x10032bd0  mov     esi, [ebp+arg_10]
0x10032bd3  mov     ebx, [ebp+this]
0x10032bd6  push    0; perrinfo
0x10032bd8  push    0; dwReserved
0x10032bda  mov     [ebp+var_2C], eax
0x10032bdd  mov     [ebp+var_24], esi
0x10032be0  mov     [ebp+var_20], 0
0x10032be7  mov     [ebp+var_28], 0
0x10032bee  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10032bf4  test    esi, esi
0x10032bf6  jz      short loc_10032BFE
0x10032bf8  mov     dword ptr [esi], 0
0x10032bfe  xor     esi, esi
0x10032c00  mov     [ebp+var_34], esi
0x10032c03  mov     [ebp+var_4], esi
0x10032c06  mov     edx, [ebx+8]
0x10032c09  mov     eax, [edx+40h]
0x10032c0c  test    eax, eax
0x10032c0e  jz      short loc_10032C36
0x10032c10  cmp     dword ptr [eax+10h], 1
0x10032c14  jnz     short loc_10032C24
0x10032c16  mov     ecx, [eax+8]; this
0x10032c19  test    ecx, ecx
0x10032c1b  jz      short loc_10032C24
0x10032c1d  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x10032c22  jmp     short loc_10032C27
0x10032c24  mov     eax, [eax+0Ch]
0x10032c27  cmp     eax, 1
0x10032c2a  jnz     short loc_10032C36
0x10032c2c  mov     edi, 8000FFFFh
0x10032c31  jmp     loc_10032DE6
0x10032c36  test    dword ptr [edx+60h], 400h
0x10032c3d  jz      short loc_10032C49
0x10032c3f  mov     edi, 80040E20h
0x10032c44  jmp     loc_10032DE6
0x10032c49  lea     esi, [edx+48h]
0x10032c4c  push    esi; lpCriticalSection
0x10032c4d  mov     [ebp+var_34], esi
0x10032c50  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10032c56  mov     eax, [ebx+8]
0x10032c59  mov     edi, [eax+0A0h]
0x10032c5f  lea     eax, [ebp+var_30]
0x10032c62  push    eax; unsigned int *
0x10032c63  push    75h ; 'u'; unsigned int
0x10032c65  mov     ecx, edi; this
0x10032c67  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10032c6c  test    eax, eax
0x10032c6e  js      loc_10032DE1
0x10032c74  mov     eax, [ebp+var_30]
0x10032c77  mov     edx, 3
0x10032c7c  lea     ecx, [eax+eax*2]
0x10032c7f  mov     eax, [edi+10h]
0x10032c82  add     ecx, ecx
0x10032c84  cmp     dx, [eax+ecx*8+10h]
0x10032c89  jnz     loc_10032DE1
0x10032c8f  test    byte ptr [eax+ecx*8+18h], 4
0x10032c94  jz      loc_10032DE1
0x10032c9a  mov     edi, [ebp+arg_8]
0x10032c9d  test    edi, edi
0x10032c9f  jnz     short loc_10032CAB
0x10032ca1  mov     edi, 80040E00h
0x10032ca6  jmp     loc_10032DE6
0x10032cab  mov     ecx, [ebx+8]
0x10032cae  lea     eax, [ebp+var_28]
0x10032cb1  push    eax; this
0x10032cb2  mov     edx, edi
0x10032cb4  mov     ecx, [ecx+64h]
0x10032cb7  call    ?GetItemOfExtBuffer@CExtBuffer@@QAGJKPAX@Z; CExtBuffer::GetItemOfExtBuffer(ulong,void *)
0x10032cbc  cmp     [ebp+var_2C], 0
0x10032cc0  jnz     short loc_10032CD9
0x10032cc2  mov     eax, [ebp+var_28]
0x10032cc5  test    eax, eax
0x10032cc7  jz      short loc_10032CCF
0x10032cc9  cmp     dword ptr [eax+24h], 0
0x10032ccd  jz      short loc_10032CD9
0x10032ccf  mov     edi, 80070057h
0x10032cd4  jmp     loc_10032DE6
0x10032cd9  mov     ecx, [ebx+8]
0x10032cdc  lea     eax, [ebp+var_20]
0x10032cdf  push    0; unsigned int *
0x10032ce1  push    8; unsigned int
0x10032ce3  push    eax; this
0x10032ce4  mov     edx, 1
0x10032ce9  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x10032cee  test    eax, eax
0x10032cf0  jz      short loc_10032CFC
0x10032cf2  mov     edi, 80040E4Eh
0x10032cf7  jmp     loc_10032DE6
0x10032cfc  mov     ecx, [ebx+8]
0x10032cff  lea     eax, [ebp+var_1C]
0x10032d02  push    0; unsigned int
0x10032d04  push    0; struct tagOreoHROW *
0x10032d06  push    0; void *
0x10032d08  push    eax; unsigned int
0x10032d09  push    [ebp+var_2C]; this
0x10032d0c  mov     edx, edi
0x10032d0e  mov     [ebp+var_18], 8
0x10032d15  mov     [ebp+var_1C], 0FFFFFFFFh
0x10032d1c  mov     [ebp+var_14], 0
0x10032d23  call    ?UtilSetData@CRowset@@IAGJKPBXPAUtagOreoHROW@@KKH@Z; CRowset::UtilSetData(ulong,void const *,tagOreoHROW *,ulong,ulong,int)
0x10032d28  mov     edi, eax
0x10032d2a  test    edi, edi
0x10032d2c  js      loc_10032DCA
0x10032d32  cmp     [ebp+var_24], 0
0x10032d36  jz      short loc_10032D3B
0x10032d38  inc     [ebp+var_14]
0x10032d3b  mov     eax, [ebx+8]
0x10032d3e  lea     ecx, [ebp+var_20]
0x10032d41  push    ecx; this
0x10032d42  lea     edx, [ebp+var_1C]
0x10032d45  mov     ecx, [eax+68h]
0x10032d48  call    ?InsertIntoExtBuffer@CExtBuffer@@QAGJPAXAAK@Z; CExtBuffer::InsertIntoExtBuffer(void *,ulong &)
0x10032d4d  test    eax, eax
0x10032d4f  jns     short loc_10032D6A
0x10032d51  mov     ecx, [ebx+8]
0x10032d54  mov     edi, eax
0x10032d56  push    3; unsigned int *
0x10032d58  lea     eax, [ebp+var_20]
0x10032d5b  mov     edx, 1
0x10032d60  push    8; unsigned int
0x10032d62  push    eax; this
0x10032d63  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x10032d68  jmp     short loc_10032DE6
0x10032d6a  mov     eax, [ebp+var_24]
0x10032d6d  mov     edx, [ebp+var_20]
0x10032d70  test    eax, eax
0x10032d72  jz      short loc_10032D76
0x10032d74  mov     [eax], edx
0x10032d76  mov     ecx, [ebx+8]
0x10032d79  lea     ecx, [ecx+0DCh]; this
0x10032d7f  call    ?IsPending@CPendingChange@@QBEHXZ; CPendingChange::IsPending(void)
0x10032d84  cmp     eax, 1
0x10032d87  mov     eax, [ebx+8]
0x10032d8a  jz      short loc_10032D95
0x10032d8c  cmp     dword ptr [eax+0ECh], 0
0x10032d93  jnz     short loc_10032DA4
0x10032d95  mov     [eax+0E4h], edx
0x10032d9b  mov     [eax+0E0h], edx
0x10032da1  mov     edx, [ebp+var_20]
0x10032da4  mov     eax, [ebx+8]
0x10032da7  test    byte ptr [eax+60h], 10h
0x10032dab  jnz     short loc_10032DCA
0x10032dad  mov     [eax+0E4h], edx
0x10032db3  mov     [eax+0E0h], edx
0x10032db9  mov     ecx, [ebx+8]
0x10032dbc  mov     edx, [ebp+var_20]
0x10032dbf  mov     ecx, [ecx+68h]
0x10032dc2  call    ?GetPtrOfExtBuffer@CExtBuffer@@QAGPAXK@Z; CExtBuffer::GetPtrOfExtBuffer(ulong)
0x10032dc7  inc     dword ptr [eax+8]
0x10032dca  mov     ecx, [ebx+8]
0x10032dcd  lea     eax, [ebp+var_20]
0x10032dd0  push    4; unsigned int *
0x10032dd2  push    8; unsigned int
0x10032dd4  push    eax; this
0x10032dd5  mov     edx, 1
0x10032dda  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x10032ddf  jmp     short loc_10032E19
0x10032de1  mov     edi, 80040E53h
0x10032de6  mov     eax, [ebx+8]
0x10032de9  mov     eax, [eax+38h]
0x10032dec  cmp     edi, 8007000Eh
0x10032df2  jz      short loc_10032E19
0x10032df4  push    3
0x10032df6  push    4
0x10032df8  lea     ecx, [ebp+var_30]
0x10032dfb  push    ecx
0x10032dfc  push    dword ptr [eax+14h]
0x10032dff  push    dword ptr [eax+10h]
0x10032e02  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10032e08  test    eax, eax
0x10032e0a  jnz     short loc_10032E19
0x10032e0c  push    eax; int
0x10032e0d  push    offset _IID_IRowsetUpdate; int
0x10032e12  mov     edx, edi
0x10032e14  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10032e19  test    esi, esi
0x10032e1b  jz      short loc_10032E24
0x10032e1d  push    esi; lpCriticalSection
0x10032e1e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10032e24  mov     eax, edi
0x10032e26  mov     ecx, [ebp+var_C]
0x10032e29  mov     large fs:0, ecx
0x10032e30  pop     ecx
0x10032e31  pop     edi
0x10032e32  pop     esi
0x10032e33  pop     ebx
0x10032e34  mov     ecx, [ebp+var_10]
0x10032e37  xor     ecx, ebp; StackCookie
0x10032e39  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10032e3e  mov     esp, ebp
0x10032e40  pop     ebp
0x10032e41  retn    14h
0x1004ed60  lea     ecx, [ebp+var_34]; this
0x1004ed63  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004ed6d  nop
0x1004ed6e  nop
0x1004ed6f  mov     edx, [esp-4+arg_4]
0x1004ed73  lea     eax, [edx+0Ch]
0x1004ed76  mov     ecx, [edx-38h]
0x1004ed79  xor     ecx, eax; StackCookie
0x1004ed7b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004ed80  mov     ecx, [edx-4]
0x1004ed83  xor     ecx, eax; StackCookie
0x1004ed85  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004ed8a  mov     eax, offset stru_1004FF54
0x1004ed8f  jmp     ___CxxFrameHandler3
```
