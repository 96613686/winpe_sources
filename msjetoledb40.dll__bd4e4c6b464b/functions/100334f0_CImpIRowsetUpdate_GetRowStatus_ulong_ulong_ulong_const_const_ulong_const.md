# CImpIRowsetUpdate::GetRowStatus(ulong,ulong,ulong const * const,ulong * const)

- ea: `0x100334f0`
- end: `0x100336e5`
- name: `?GetRowStatus@CImpIRowsetUpdate@@UAGJKKQBKQAK@Z`
- size: `501`
- prototype: `int(CImpIRowsetUpdate *__hidden this, unsigned int, unsigned int, const unsigned int *const, unsigned int *const)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1000ba90`
- `0x1001c380`
- `0x100334f0`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x100336c9`
- `KERNEL32!LeaveCriticalSection` at `0x100336c9`
- `KERNEL32!EnterCriticalSection` at `0x1003358e`
- `KERNEL32!EnterCriticalSection` at `0x1003358e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10033521`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10033521`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100336ad`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100336ad`

## pseudocode

```c
int __stdcall CImpIRowsetUpdate::GetRowStatus(
        struct _RTL_CRITICAL_SECTION **this,
        unsigned int a2,
        unsigned int a3,
        const unsigned int *a4,
        unsigned int *const a5)
{
  int v5; // ebx
  struct _RTL_CRITICAL_SECTION *v6; // esi
  CImpIRowsetUpdate *v7; // edi
  struct _RTL_CRITICAL_SECTION *v8; // edx
  _DWORD *LockSemaphore; // eax
  CTransactionState *v10; // ecx
  int isZombie; // eax
  unsigned int v12; // ecx
  int v13; // esi
  _DWORD *v14; // edi
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  int v17; // edx
  unsigned __int8 v18; // al
  unsigned int v19; // ecx
  _DWORD *v20; // eax
  int v21; // eax
  unsigned int *v22; // ecx
  int v23; // edx
  bool v24; // zf
  const struct _GUID *v26; // [esp+0h] [ebp-2Ch]
  int v27; // [esp+4h] [ebp-28h]
  struct _RTL_CRITICAL_SECTION *v28; // [esp+10h] [ebp-1Ch] BYREF
  struct _RTL_CRITICAL_SECTION *v29; // [esp+14h] [ebp-18h]
  int v30; // [esp+18h] [ebp-14h]
  unsigned int v31; // [esp+1Ch] [ebp-10h]
  int v32; // [esp+28h] [ebp-4h]

  v5 = 0;
  v30 = 0;
  SetErrorInfo(0, 0);
  v6 = 0;
  v29 = 0;
  v7 = (CImpIRowsetUpdate *)this;
  v32 = 0;
  v8 = this[2];
  LockSemaphore = v8[2].LockSemaphore;
  if ( LockSemaphore
    && (LockSemaphore[4] != 1 || (v10 = (CTransactionState *)LockSemaphore[2]) == 0
      ? (isZombie = LockSemaphore[3])
      : (isZombie = CTransactionState::isZombie(v10)),
        isZombie == 1)
    || !v8[4].SpinCount && !v8[9].SpinCount )
  {
    v5 = -2147418113;
    goto LABEL_35;
  }
  if ( ((int)v8[4].DebugInfo & 0x400) != 0 )
  {
    v5 = -2147217888;
    goto LABEL_35;
  }
  v6 = v8 + 3;
  v28 = v8 + 3;
  v29 = v8 + 3;
  EnterCriticalSection(v8 + 3);
  if ( !a3 )
    goto LABEL_37;
  if ( !a4 || !a5 )
  {
    v5 = -2147024809;
LABEL_35:
    if ( !JetGetDatabaseInfo(
            *(_DWORD *)(this[2][2].RecursionCount + 16),
            *(_DWORD *)(this[2][2].RecursionCount + 20),
            &v28,
            4,
            3) )
      CExtError::SendHRtoOLEAuto(v5, (__int128 *)&IID_IRowsetUpdate, 0, v26, v27);
    goto LABEL_37;
  }
  v12 = 0;
  v29 = 0;
  v13 = 0;
  do
  {
    v14 = *(_DWORD **)(*((_DWORD *)v7 + 2) + 104);
    v31 = 4 * v12;
    v15 = a4[v12];
    if ( v15 > v14[6] + 8 * v14[5] - 1 )
    {
      v19 = v31;
LABEL_26:
      v23 = 1;
      v21 = 16;
      v30 = 1;
      v22 = (unsigned int *const)((char *)a5 + v19);
      goto LABEL_27;
    }
    v16 = v15 - v14[6];
    v17 = v16 & 7;
    v18 = *(_BYTE *)((v16 >> 3) + v14[4]);
    v19 = v31;
    if ( (v18 & *((_BYTE *)&Bitmap::ThisBit + v17)) != 0 )
      goto LABEL_26;
    v20 = (_DWORD *)(v14[2] + a4[v31 / 4] * *v14);
    if ( !v20 )
      goto LABEL_26;
    if ( *v20 == -1 )
      goto LABEL_26;
    v21 = v20[1];
    if ( v21 == 16 )
      goto LABEL_26;
    v22 = &a5[v31 / 4];
    if ( (v21 & 4) != 0 )
      v21 = 4;
    v23 = v30;
    v13 = 1;
LABEL_27:
    v7 = (CImpIRowsetUpdate *)this;
    *v22 = v21;
    v12 = (unsigned int)&v29->DebugInfo + 1;
    v29 = (struct _RTL_CRITICAL_SECTION *)v12;
  }
  while ( v12 < a3 );
  v24 = v13 == 1;
  v5 = 0;
  v6 = v28;
  if ( v24 )
  {
    v5 = 265946;
    if ( v23 != 1 )
      v5 = 0;
  }
  else if ( v23 == 1 )
  {
    v5 = -2147217887;
  }
LABEL_37:
  if ( v6 )
    LeaveCriticalSection(v6);
  return v5;
}

```

## disassembly

```asm
0x100334f0  mov     edi, edi
0x100334f2  push    ebp
0x100334f3  mov     ebp, esp
0x100334f5  push    0FFFFFFFFh
0x100334f7  push    offset ?Release@CStorageObject@@QAGKXZ_SEH
0x100334fc  mov     eax, large fs:0
0x10033502  push    eax
0x10033503  sub     esp, 10h
0x10033506  push    ebx
0x10033507  push    esi
0x10033508  push    edi; int
0x10033509  mov     eax, ___security_cookie
0x1003350e  xor     eax, ebp
0x10033510  push    eax; struct _GUID *
0x10033511  lea     eax, [ebp+var_C]
0x10033514  mov     large fs:0, eax
0x1003351a  xor     ebx, ebx
0x1003351c  push    ebx; perrinfo
0x1003351d  push    ebx; dwReserved
0x1003351e  mov     [ebp+var_14], ebx
0x10033521  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10033527  xor     esi, esi
0x10033529  mov     [ebp+var_18], esi
0x1003352c  mov     edi, [ebp+this]
0x1003352f  mov     [ebp+var_4], esi
0x10033532  mov     edx, [edi+8]
0x10033535  mov     eax, [edx+40h]
0x10033538  test    eax, eax
0x1003353a  jz      short loc_10033558
0x1003353c  cmp     dword ptr [eax+10h], 1
0x10033540  jnz     short loc_10033550
0x10033542  mov     ecx, [eax+8]; this
0x10033545  test    ecx, ecx
0x10033547  jz      short loc_10033550
0x10033549  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x1003354e  jmp     short loc_10033553
0x10033550  mov     eax, [eax+0Ch]
0x10033553  cmp     eax, 1
0x10033556  jz      short loc_10033567
0x10033558  cmp     dword ptr [edx+74h], 0
0x1003355c  jnz     short loc_10033571
0x1003355e  cmp     dword ptr [edx+0ECh], 0
0x10033565  jnz     short loc_10033571
0x10033567  mov     ebx, 8000FFFFh
0x1003356c  jmp     loc_10033699
0x10033571  test    dword ptr [edx+60h], 400h
0x10033578  jz      short loc_10033584
0x1003357a  mov     ebx, 80040E20h
0x1003357f  jmp     loc_10033699
0x10033584  lea     esi, [edx+48h]
0x10033587  push    esi; lpCriticalSection
0x10033588  mov     [ebp+var_1C], esi
0x1003358b  mov     [ebp+var_18], esi
0x1003358e  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10033594  mov     eax, [ebp+arg_8]
0x10033597  test    eax, eax
0x10033599  jz      loc_100336C4
0x1003359f  cmp     [ebp+arg_C], 0
0x100335a3  jz      loc_10033694
0x100335a9  cmp     [ebp+arg_10], 0
0x100335ad  jz      loc_10033694
0x100335b3  xor     ecx, ecx
0x100335b5  mov     [ebp+var_18], ecx
0x100335b8  test    eax, eax
0x100335ba  jz      loc_100336C4
0x100335c0  mov     ebx, [ebp+arg_10]
0x100335c3  xor     esi, esi
0x100335c5  nop     word ptr [eax+eax+00000000h]
0x100335d0  mov     eax, [edi+8]
0x100335d3  mov     edi, [eax+68h]
0x100335d6  lea     eax, ds:0[ecx*4]
0x100335dd  mov     ecx, [ebp+arg_C]
0x100335e0  mov     [ebp+var_10], eax
0x100335e3  mov     ecx, [eax+ecx]
0x100335e6  mov     eax, [edi+14h]
0x100335e9  lea     eax, ds:0FFFFFFFFh[eax*8]
0x100335f0  add     eax, [edi+18h]
0x100335f3  cmp     ecx, eax
0x100335f5  ja      short loc_10033645
0x100335f7  mov     eax, [edi+10h]
0x100335fa  mov     edx, ecx
0x100335fc  sub     edx, [edi+18h]
0x100335ff  mov     ecx, edx
0x10033601  and     edx, 7
0x10033604  shr     ecx, 3
0x10033607  mov     al, [ecx+eax]
0x1003360a  mov     ecx, [ebp+var_10]
0x1003360d  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x10033613  jnz     short loc_10033648
0x10033615  mov     edx, [ebp+arg_C]
0x10033618  mov     eax, [edi]
0x1003361a  imul    eax, [ecx+edx]
0x1003361e  add     eax, [edi+8]
0x10033621  jz      short loc_10033648
0x10033623  cmp     dword ptr [eax], 0FFFFFFFFh
0x10033626  jz      short loc_10033648
0x10033628  mov     eax, [eax+4]
0x1003362b  cmp     eax, 10h
0x1003362e  jz      short loc_10033648
0x10033630  add     ecx, ebx
0x10033632  test    al, 4
0x10033634  jz      short loc_1003363B
0x10033636  mov     eax, 4
0x1003363b  mov     edx, [ebp+var_14]
0x1003363e  mov     esi, 1
0x10033643  jmp     short loc_10033657
0x10033645  mov     ecx, [ebp+var_10]
0x10033648  mov     edx, 1
0x1003364d  mov     eax, 10h
0x10033652  mov     [ebp+var_14], edx
0x10033655  add     ecx, ebx
0x10033657  mov     edi, [ebp+this]
0x1003365a  mov     [ecx], eax
0x1003365c  mov     ecx, [ebp+var_18]
0x1003365f  inc     ecx
0x10033660  mov     [ebp+var_18], ecx
0x10033663  cmp     ecx, [ebp+arg_8]
0x10033666  jb      loc_100335D0
0x1003366c  cmp     esi, 1
0x1003366f  mov     ebx, 0
0x10033674  mov     esi, [ebp+var_1C]
0x10033677  jnz     short loc_10033688
0x10033679  xor     eax, eax
0x1003367b  mov     ebx, 40EDAh
0x10033680  cmp     edx, 1
0x10033683  cmovnz  ebx, eax
0x10033686  jmp     short loc_100336C4
0x10033688  cmp     edx, 1
0x1003368b  jnz     short loc_100336C4
0x1003368d  mov     ebx, 80040E21h
0x10033692  jmp     short loc_100336C4
0x10033694  mov     ebx, 80070057h
0x10033699  mov     eax, [edi+8]
0x1003369c  lea     ecx, [ebp+var_1C]
0x1003369f  push    3
0x100336a1  push    4
0x100336a3  push    ecx
0x100336a4  mov     eax, [eax+38h]
0x100336a7  push    dword ptr [eax+14h]
0x100336aa  push    dword ptr [eax+10h]
0x100336ad  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x100336b3  test    eax, eax
0x100336b5  jnz     short loc_100336C4
0x100336b7  push    eax; int
0x100336b8  push    offset _IID_IRowsetUpdate; int
0x100336bd  mov     edx, ebx
0x100336bf  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x100336c4  test    esi, esi
0x100336c6  jz      short loc_100336CF
0x100336c8  push    esi; lpCriticalSection
0x100336c9  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100336cf  mov     eax, ebx
0x100336d1  mov     ecx, [ebp+var_C]
0x100336d4  mov     large fs:0, ecx
0x100336db  pop     ecx
0x100336dc  pop     edi
0x100336dd  pop     esi
0x100336de  pop     ebx
0x100336df  mov     esp, ebp
0x100336e1  pop     ebp
0x100336e2  retn    14h
0x1004e550  lea     ecx, [ebp+var_18]; this
0x1004e553  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004e55d  nop
0x1004e55e  nop
0x1004e55f  mov     edx, [esp-4+arg_4]
0x1004e563  lea     eax, [edx+0Ch]
0x1004e566  mov     ecx, [edx-20h]
0x1004e569  xor     ecx, eax; StackCookie
0x1004e56b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e570  mov     eax, offset stru_1004F968
0x1004e575  jmp     ___CxxFrameHandler3
```
