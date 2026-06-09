# COfflineFilesItem_CreateInstance(IOfflineFilesService *,ushort const *,tagOFFLINEFILES_ITEM_DESCRIPTOR const &,_GUID const &,void * *)

- ea: `0x180002df0`
- end: `0x1800035f5`
- name: `?COfflineFilesItem_CreateInstance@@YAJPEAUIOfflineFilesService@@PEBGAEBUtagOFFLINEFILES_ITEM_DESCRIPTOR@@AEBU_GUID@@PEAPEAX@Z`
- size: `2053`
- prototype: `__int64 __usercall@<rax>(struct IOfflineFilesService *@<rcx>, const unsigned __int16 *@<rdx>, const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *@<r8>, const struct _GUID *@<r9>, void **)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180003ca0`
- `0x180004028`
- `0x18001057c`

## callees

- `0x180002df0`
- `0x180003600`
- `0x180003680`
- `0x180003710`
- `0x18000943c`
- `0x18000b390`
- `0x18000c174`
- `0x1800102a8`
- `0x180011d08`
- `0x180011e04`
- `0x18002ac30`
- `0x18002c010`

## import_xrefs

- `ntdll!RtlpEnsureBufferSize` at `0x180002fb5`
- `ntdll!RtlpEnsureBufferSize` at `0x180003124`
- `ntdll!RtlpEnsureBufferSize` at `0x1800032bb`
- `ntdll!RtlpEnsureBufferSize` at `0x1800034ab`
- `ntdll!RtlpEnsureBufferSize` at `0x180002fb5`
- `ntdll!RtlpEnsureBufferSize` at `0x180003124`
- `ntdll!RtlpEnsureBufferSize` at `0x1800032bb`
- `ntdll!RtlpEnsureBufferSize` at `0x1800034ab`
- `ntdll!RtlInitUnicodeString` at `0x180002f7c`
- `ntdll!RtlInitUnicodeString` at `0x1800030eb`
- `ntdll!RtlInitUnicodeString` at `0x180003282`
- `ntdll!RtlInitUnicodeString` at `0x180003476`
- `ntdll!RtlInitUnicodeString` at `0x180002f7c`
- `ntdll!RtlInitUnicodeString` at `0x1800030eb`
- `ntdll!RtlInitUnicodeString` at `0x180003282`
- `ntdll!RtlInitUnicodeString` at `0x180003476`

## pseudocode

```c
__int64 __fastcall COfflineFilesItem_CreateInstance(
        struct IOfflineFilesService *a1,
        const unsigned __int16 *a2,
        const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *a3,
        const struct _GUID *a4,
        void **a5)
{
  const struct _GUID *v6; // rbx
  int v10; // edi
  int v11; // eax
  _DWORD *v12; // rax
  _DWORD *v13; // rbx
  int v14; // r12d
  __int64 v15; // rdx
  SIZE_T v16; // r8
  __int64 v17; // rcx
  unsigned __int64 v18; // rax
  size_t v19; // r8
  PWSTR v20; // rdx
  unsigned __int64 v21; // rdx
  _DWORD *v22; // rax
  const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *v23; // rcx
  __int64 v24; // rdx
  __int128 v25; // xmm0
  SIZE_T v27; // r8
  int v28; // ecx
  _QWORD *v29; // rax
  _QWORD *v30; // rsi
  int v31; // r12d
  __int64 Length; // rdx
  SIZE_T v33; // r8
  __int64 v34; // rcx
  unsigned __int64 v35; // rax
  size_t v36; // r8
  PWSTR Buffer; // rdx
  unsigned __int64 v38; // rdx
  _QWORD *v39; // rax
  const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *v40; // rcx
  __int64 v41; // rdx
  __int128 v42; // xmm0
  const struct _GUID *v43; // rdx
  int v44; // eax
  void **v45; // rax
  COfflineFilesItem *v46; // rbx
  SIZE_T v47; // r8
  int v48; // ecx
  COfflineFilesShareItem *v49; // rax
  COfflineFilesShareItem *v50; // rax
  const unsigned __int16 *v51; // rax
  const unsigned __int16 *NextComponent; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-10h] BYREF
  void **v56; // [rsp+90h] [rbp+60h]

  v6 = a4;
  v10 = -2147024882;
  *a5 = 0;
  v11 = *((_DWORD *)a3 + 1);
  if ( (v11 & 0x40) != 0 )
  {
    v45 = (void **)operator new(0x570u);
    v56 = v45;
    if ( !v45 )
      return (unsigned int)v10;
    v46 = (COfflineFilesItem *)(v45 + 2);
    COfflineFilesItem::COfflineFilesItem((COfflineFilesItem *)(v45 + 2), OFFLINEFILES_ITEM_TYPE_SERVER, a1);
    v30 = v56;
    *v56 = &COfflineFilesServerItem::`vftable'{for `IOfflineFilesServerItem'};
    v56[1] = &COfflineFilesServerItem::`vftable'{for `IOfflineFilesItemContainer'};
    *(_QWORD *)v46 = &COfflineFilesServerItem::`vftable'{for `COfflineFilesItem'};
    *((_DWORD *)v56 + 346) = 1;
    v10 = COfflineFilesItem::_Initialize(v46, a2, a3);
    if ( v10 < 0 )
      goto LABEL_42;
    v43 = a4;
LABEL_40:
    v44 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v30)(v30, v43, a5);
LABEL_41:
    v10 = v44;
    goto LABEL_42;
  }
  if ( (v11 & 0x4000) != 0 )
  {
    v49 = (COfflineFilesShareItem *)operator new(0x5B0u);
    if ( !v49 )
      return (unsigned int)v10;
    v50 = COfflineFilesShareItem::COfflineFilesShareItem(v49, a1);
    v30 = v50;
    if ( !v50 )
      return (unsigned int)v10;
    v10 = COfflineFilesItem::_Initialize((COfflineFilesShareItem *)((char *)v50 + 80), a2, a3);
    if ( v10 >= 0 )
    {
      v44 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v30)(v30, v6, a5);
      goto LABEL_41;
    }
    goto LABEL_42;
  }
  if ( (*((_BYTE *)a3 + 120) & 0x10) != 0 )
  {
    v29 = operator new(0x5B8u);
    v30 = v29;
    if ( !v29 )
      return (unsigned int)v10;
    v31 = 1;
    v29[11] = &COfflineFilesItem::`vftable';
    v29[13] = a1;
    *((_DWORD *)v29 + 24) = 1;
    v29[81] = v29 + 14;
    v29[83] = 520;
    v29[82] = v29 + 14;
    v29[84] = 520;
    v29[80] = v29 + 14;
    if ( v29 != (_QWORD *)-112LL )
      *((_WORD *)v29 + 56) = 0;
    *((_DWORD *)v29 + 158) = 34078720;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v29[13] + 8LL))(v29[13]);
    memset_0(v30 + 86, 0, 0x300u);
    *((_DWORD *)v30 + 364) = 1;
    *v30 = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesDirectoryItem'};
    v30[1] = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesItemContainer'};
    v30[2] = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesChangeInfo'};
    v30[3] = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesPinInfo2'};
    v30[4] = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesFileSysInfo'};
    v30[5] = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesConnectionInfo'};
    v30[6] = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesShareInfo'};
    v30[7] = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesSuspend'};
    v30[8] = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesSuspendInfo'};
    v30[9] = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesTransparentCacheInfo'};
    v30[10] = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesGhostInfo'};
    v30[11] = &COfflineFilesDirectoryItem::`vftable'{for `COfflineFilesItem'};
    if ( a2 && *a2 )
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, a2);
      Length = DestinationString.Length;
      *((_WORD *)v30 + 316) = 0;
      v47 = Length + 2;
      if ( (unsigned __int64)(Length + 2) > 0xFFFE )
      {
        v48 = -1073741562;
        goto LABEL_55;
      }
      if ( v30 == (_QWORD *)-648LL || v47 > v30[83] )
      {
        if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)(v30 + 81), v47) < 0 )
          goto LABEL_54;
LABEL_33:
        LOWORD(Length) = DestinationString.Length;
      }
    }
    else
    {
      v31 = 0;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"\\\\");
      Length = DestinationString.Length;
      *((_WORD *)v30 + 316) = 0;
      v33 = Length + 2;
      if ( (unsigned __int64)(Length + 2) > 0xFFFE )
      {
        v48 = -1073741562;
        goto LABEL_55;
      }
      if ( v30 == (_QWORD *)-648LL || v33 > v30[83] )
      {
        if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)(v30 + 81), v33) < 0 )
        {
LABEL_54:
          v48 = -1073741801;
LABEL_55:
          v10 = ResultFromNtStatus(v48);
LABEL_35:
          if ( v10 >= 0 )
          {
            v39 = v30 + 86;
            v40 = a3;
            v41 = 6;
            do
            {
              v39 += 16;
              v42 = *(_OWORD *)v40;
              v40 = (const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *)((char *)v40 + 128);
              *((_OWORD *)v39 - 8) = v42;
              *((_OWORD *)v39 - 7) = *((_OWORD *)v40 - 7);
              *((_OWORD *)v39 - 6) = *((_OWORD *)v40 - 6);
              *((_OWORD *)v39 - 5) = *((_OWORD *)v40 - 5);
              *((_OWORD *)v39 - 4) = *((_OWORD *)v40 - 4);
              *((_OWORD *)v39 - 3) = *((_OWORD *)v40 - 3);
              *((_OWORD *)v39 - 2) = *((_OWORD *)v40 - 2);
              *((_OWORD *)v39 - 1) = *((_OWORD *)v40 - 1);
              --v41;
            }
            while ( v41 );
            if ( !v31 && (unsigned int)CscPath_IsUNCServer((const unsigned __int16 *)a3 + 107) )
            {
              NextComponent = CscPath_FindNextComponent((const unsigned __int16 *)v30 + 451);
              v10 = StringCchCopyW((unsigned __int16 *)v30 + 451, 0x105u, NextComponent);
              if ( v10 < 0 )
                goto LABEL_42;
              v6 = a4;
            }
            v43 = v6;
            goto LABEL_40;
          }
LABEL_42:
          (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
          return (unsigned int)v10;
        }
        goto LABEL_33;
      }
    }
    v10 = 0;
    v34 = v30[81];
    v35 = (unsigned __int64)*((unsigned __int16 *)v30 + 316) >> 1;
    v36 = (unsigned __int16)Length;
    Buffer = DestinationString.Buffer;
    v30[80] = v34;
    memmove_0((void *)(v34 + 2 * v35), Buffer, v36);
    v38 = (unsigned __int16)(*((_WORD *)v30 + 316) + DestinationString.Length);
    *((_WORD *)v30 + 316) = v38;
    *((_WORD *)v30 + 317) = v38 + 2;
    *(_WORD *)(v30[80] + 2 * (v38 >> 1)) = 0;
    goto LABEL_35;
  }
  v12 = operator new(0x5B0u);
  v13 = v12;
  if ( !v12 )
    return (unsigned int)v10;
  v12[22] = 0;
  *((_QWORD *)v12 + 12) = a1;
  *((_QWORD *)v12 + 10) = &COfflineFilesItem::`vftable';
  *((_QWORD *)v12 + 80) = v12 + 26;
  *((_QWORD *)v12 + 82) = 520;
  *((_QWORD *)v12 + 81) = v12 + 26;
  *((_QWORD *)v12 + 83) = 520;
  *((_QWORD *)v12 + 79) = v12 + 26;
  if ( v12 != (_DWORD *)-104LL )
    *((_WORD *)v12 + 52) = 0;
  v12[156] = 34078720;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 12) + 8LL))(*((_QWORD *)v12 + 12));
  memset_0(v13 + 170, 0, 0x300u);
  v14 = 1;
  *(_QWORD *)v13 = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesFileItem'};
  *((_QWORD *)v13 + 1) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesChangeInfo'};
  *((_QWORD *)v13 + 2) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesDirtyInfo'};
  *((_QWORD *)v13 + 3) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesPinInfo2'};
  *((_QWORD *)v13 + 4) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesFileSysInfo'};
  *((_QWORD *)v13 + 5) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesConnectionInfo'};
  *((_QWORD *)v13 + 6) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesShareInfo'};
  *((_QWORD *)v13 + 7) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesSuspendInfo'};
  *((_QWORD *)v13 + 8) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesTransparentCacheInfo'};
  *((_QWORD *)v13 + 9) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesGhostInfo'};
  *((_QWORD *)v13 + 10) = &COfflineFilesFileItem::`vftable'{for `COfflineFilesItem'};
  v13[362] = 1;
  if ( a2 && *a2 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    v15 = DestinationString.Length;
    *((_WORD *)v13 + 312) = 0;
    v27 = v15 + 2;
    if ( (unsigned __int64)(v15 + 2) > 0xFFFE )
    {
      v28 = -1073741562;
      goto LABEL_25;
    }
    if ( v13 == (_DWORD *)-640LL || v27 > *((_QWORD *)v13 + 82) )
    {
      if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)(v13 + 160), v27) < 0 )
        goto LABEL_24;
      goto LABEL_11;
    }
LABEL_12:
    v10 = 0;
    v17 = *((_QWORD *)v13 + 80);
    v18 = (unsigned __int64)*((unsigned __int16 *)v13 + 312) >> 1;
    v19 = (unsigned __int16)v15;
    v20 = DestinationString.Buffer;
    *((_QWORD *)v13 + 79) = v17;
    memmove_0((void *)(v17 + 2 * v18), v20, v19);
    v21 = (unsigned __int16)(*((_WORD *)v13 + 312) + DestinationString.Length);
    *((_WORD *)v13 + 312) = v21;
    *((_WORD *)v13 + 313) = v21 + 2;
    *(_WORD *)(*((_QWORD *)v13 + 79) + 2 * (v21 >> 1)) = 0;
    goto LABEL_13;
  }
  v14 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\\\");
  v15 = DestinationString.Length;
  *((_WORD *)v13 + 312) = 0;
  v16 = v15 + 2;
  if ( (unsigned __int64)(v15 + 2) > 0xFFFE )
  {
    v28 = -1073741562;
    goto LABEL_25;
  }
  if ( v13 != (_DWORD *)-640LL && v16 <= *((_QWORD *)v13 + 82) )
    goto LABEL_12;
  if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)(v13 + 160), v16) >= 0 )
  {
LABEL_11:
    LOWORD(v15) = DestinationString.Length;
    goto LABEL_12;
  }
LABEL_24:
  v28 = -1073741801;
LABEL_25:
  v10 = ResultFromNtStatus(v28);
LABEL_13:
  if ( v10 >= 0 )
  {
    v22 = v13 + 170;
    v23 = a3;
    v24 = 6;
    do
    {
      v22 += 32;
      v25 = *(_OWORD *)v23;
      v23 = (const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *)((char *)v23 + 128);
      *((_OWORD *)v22 - 8) = v25;
      *((_OWORD *)v22 - 7) = *((_OWORD *)v23 - 7);
      *((_OWORD *)v22 - 6) = *((_OWORD *)v23 - 6);
      *((_OWORD *)v22 - 5) = *((_OWORD *)v23 - 5);
      *((_OWORD *)v22 - 4) = *((_OWORD *)v23 - 4);
      *((_OWORD *)v22 - 3) = *((_OWORD *)v23 - 3);
      *((_OWORD *)v22 - 2) = *((_OWORD *)v23 - 2);
      *((_OWORD *)v22 - 1) = *((_OWORD *)v23 - 1);
      --v24;
    }
    while ( v24 );
    if ( v14
      || !(unsigned int)CscPath_IsUNCServer((const unsigned __int16 *)a3 + 107)
      || (v51 = CscPath_FindNextComponent((const unsigned __int16 *)v13 + 447),
          v10 = StringCchCopyW((unsigned __int16 *)v13 + 447, 0x105u, v51),
          v10 >= 0) )
    {
      v10 = (**(__int64 (__fastcall ***)(_DWORD *, const struct _GUID *, void **))v13)(v13, a4, a5);
    }
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180002df0  mov     [rsp-38h+arg_8], rbx
0x180002df5  mov     [rsp-38h+arg_18], r9
0x180002dfa  mov     [rsp-38h+arg_0], rcx
0x180002dff  push    rbp
0x180002e00  push    rsi
0x180002e01  push    rdi
0x180002e02  push    r12
0x180002e04  push    r13
0x180002e06  push    r14
0x180002e08  push    r15
0x180002e0a  mov     rbp, rsp
0x180002e0d  sub     rsp, 30h
0x180002e11  mov     r15, [rbp+arg_20]
0x180002e15  xor     r12d, r12d
0x180002e18  mov     rbx, r9
0x180002e1b  mov     r14, r8
0x180002e1e  mov     r13, rdx
0x180002e21  mov     rsi, rcx
0x180002e24  mov     edi, 8007000Eh
0x180002e29  mov     [r15], r12
0x180002e2c  mov     eax, [r8+4]
0x180002e30  test    al, 40h
0x180002e32  jnz     loc_1800033E3
0x180002e38  bt      eax, 0Eh
0x180002e3c  jb      loc_1800034EB
0x180002e42  test    byte ptr [r8+78h], 10h
0x180002e47  jnz     loc_180003143
0x180002e4d  mov     ecx, 5B0h; Size
0x180002e52  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e57  mov     rbx, rax
0x180002e5a  test    rax, rax
0x180002e5d  jz      loc_1800030BA
0x180002e63  lea     rcx, [rbx+68h]
0x180002e67  mov     [rbx+58h], r12d
0x180002e6b  mov     [rbx+60h], rsi
0x180002e6f  mov     edx, 208h
0x180002e74  lea     rax, ??_7COfflineFilesItem@@6B@; const COfflineFilesItem::`vftable'
0x180002e7b  mov     [rbx+50h], rax
0x180002e7f  mov     [rcx+218h], rcx
0x180002e86  mov     [rcx+228h], rdx
0x180002e8d  mov     [rcx+220h], rcx
0x180002e94  mov     [rcx+230h], rdx
0x180002e9b  mov     [rcx+210h], rcx
0x180002ea2  test    rcx, rcx
0x180002ea5  jz      short loc_180002EAB
0x180002ea7  mov     [rcx], r12w
0x180002eab  mov     dword ptr [rcx+208h], 2080000h
0x180002eb5  mov     rcx, [rbx+60h]
0x180002eb9  mov     rax, [rcx]
0x180002ebc  mov     rax, [rax+8]
0x180002ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ec5  lea     rcx, [rbx+2A8h]; void *
0x180002ecc  xor     edx, edx; Val
0x180002ece  mov     r8d, 300h; Size
0x180002ed4  call    memset_0
0x180002ed9  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesFileItem@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesFileItem'}
0x180002ee0  mov     r12d, 1
0x180002ee6  mov     [rbx], rax
0x180002ee9  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesChangeInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesChangeInfo'}
0x180002ef0  mov     [rbx+8], rax
0x180002ef4  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesDirtyInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesDirtyInfo'}
0x180002efb  mov     [rbx+10h], rax
0x180002eff  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesPinInfo2@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesPinInfo2'}
0x180002f06  mov     [rbx+18h], rax
0x180002f0a  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesFileSysInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesFileSysInfo'}
0x180002f11  mov     [rbx+20h], rax
0x180002f15  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesConnectionInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesConnectionInfo'}
0x180002f1c  mov     [rbx+28h], rax
0x180002f20  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesShareInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesShareInfo'}
0x180002f27  mov     [rbx+30h], rax
0x180002f2b  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesSuspendInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesSuspendInfo'}
0x180002f32  mov     [rbx+38h], rax
0x180002f36  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesTransparentCacheInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesTransparentCacheInfo'}
0x180002f3d  mov     [rbx+40h], rax
0x180002f41  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesGhostInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesGhostInfo'}
0x180002f48  mov     [rbx+48h], rax
0x180002f4c  lea     rax, ??_7COfflineFilesFileItem@@6BCOfflineFilesItem@@@; const COfflineFilesFileItem::`vftable'{for `COfflineFilesItem'}
0x180002f53  mov     [rbx+50h], rax
0x180002f57  mov     [rbx+5A8h], r12d
0x180002f5e  test    r13, r13
0x180002f61  jnz     loc_1800030D1
0x180002f67  xorps   xmm0, xmm0
0x180002f6a  lea     rdx, SourceString; "\\\\"
0x180002f71  lea     rcx, [rbp+DestinationString]; DestinationString
0x180002f75  xor     r12d, r12d
0x180002f78  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180002f7c  call    cs:__imp_RtlInitUnicodeString
0x180002f82  movzx   edx, [rbp+DestinationString.Length]
0x180002f86  xor     eax, eax
0x180002f88  mov     [rbx+270h], ax
0x180002f8f  lea     r8, [rdx+2]; RequiredSize
0x180002f93  cmp     r8, 0FFFEh
0x180002f9a  ja      loc_1800035D2
0x180002fa0  lea     rax, [rbx+280h]
0x180002fa7  test    rax, rax
0x180002faa  jnz     loc_1800033BF
0x180002fb0  mov     rdx, rax; Buffer
0x180002fb3  xor     ecx, ecx; Flags
0x180002fb5  call    cs:__imp_RtlpEnsureBufferSize
0x180002fbb  test    eax, eax
0x180002fbd  js      loc_180003132
0x180002fc3  movzx   edx, [rbp+DestinationString.Length]
0x180002fc7  movzx   eax, word ptr [rbx+270h]
0x180002fce  xor     edi, edi
0x180002fd0  mov     rcx, [rbx+280h]
0x180002fd7  shr     rax, 1
0x180002fda  movzx   r8d, dx; Size
0x180002fde  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x180002fe2  mov     [rbx+278h], rcx
0x180002fe9  lea     rcx, [rcx+rax*2]; void *
0x180002fed  call    memmove_0
0x180002ff2  movzx   eax, [rbp+DestinationString.Length]
0x180002ff6  add     ax, [rbx+270h]
0x180002ffd  movzx   edx, ax
0x180003000  mov     [rbx+270h], dx
0x180003007  lea     eax, [rdx+2]
0x18000300a  shr     rdx, 1
0x18000300d  mov     [rbx+272h], ax
0x180003014  xor     eax, eax
0x180003016  mov     rcx, [rbx+278h]
0x18000301d  mov     [rcx+rdx*2], ax
0x180003021  test    edi, edi
0x180003023  js      loc_1800030AB
0x180003029  lea     rax, [rbx+2A8h]
0x180003030  mov     rcx, r14
0x180003033  mov     edx, 6
0x180003038  lea     rax, [rax+80h]
0x18000303f  movups  xmm0, xmmword ptr [rcx]
0x180003042  lea     rcx, [rcx+80h]
0x180003049  movups  xmmword ptr [rax-80h], xmm0
0x18000304d  movups  xmm1, xmmword ptr [rcx-70h]
0x180003051  movups  xmmword ptr [rax-70h], xmm1
0x180003055  movups  xmm0, xmmword ptr [rcx-60h]
0x180003059  movups  xmmword ptr [rax-60h], xmm0
0x18000305d  movups  xmm1, xmmword ptr [rcx-50h]
0x180003061  movups  xmmword ptr [rax-50h], xmm1
0x180003065  movups  xmm0, xmmword ptr [rcx-40h]
0x180003069  movups  xmmword ptr [rax-40h], xmm0
0x18000306d  movups  xmm1, xmmword ptr [rcx-30h]
0x180003071  movups  xmmword ptr [rax-30h], xmm1
0x180003075  movups  xmm0, xmmword ptr [rcx-20h]
0x180003079  movups  xmmword ptr [rax-20h], xmm0
0x18000307d  movups  xmm1, xmmword ptr [rcx-10h]
0x180003081  movups  xmmword ptr [rax-10h], xmm1
0x180003085  sub     rdx, 1
0x180003089  jnz     short loc_180003038
0x18000308b  test    r12d, r12d
0x18000308e  jz      loc_1800035DC
0x180003094  mov     rax, [rbx]
0x180003097  mov     r8, r15
0x18000309a  mov     rdx, [rbp+arg_18]
0x18000309e  mov     rcx, rbx
0x1800030a1  mov     rax, [rax]
0x1800030a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a9  mov     edi, eax
0x1800030ab  mov     rcx, [rbx]
0x1800030ae  mov     rax, [rcx+10h]
0x1800030b2  mov     rcx, rbx
0x1800030b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ba  mov     rbx, [rsp+30h+arg_8]
0x1800030bf  mov     eax, edi
0x1800030c1  add     rsp, 30h
0x1800030c5  pop     r15
0x1800030c7  pop     r14
0x1800030c9  pop     r13
0x1800030cb  pop     r12
0x1800030cd  pop     rdi
0x1800030ce  pop     rsi
0x1800030cf  pop     rbp
0x1800030d0  retn
0x1800030d1  cmp     word ptr [r13+0], 0
0x1800030d7  jz      loc_180002F67
0x1800030dd  xorps   xmm0, xmm0
0x1800030e0  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800030e4  mov     rdx, r13; SourceString
0x1800030e7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800030eb  call    cs:__imp_RtlInitUnicodeString
0x1800030f1  movzx   edx, [rbp+DestinationString.Length]
0x1800030f5  xor     eax, eax
0x1800030f7  mov     [rbx+270h], ax
0x1800030fe  lea     r8, [rdx+2]; RequiredSize
0x180003102  cmp     r8, 0FFFEh
0x180003109  ja      loc_1800035C8
0x18000310f  lea     rax, [rbx+280h]
0x180003116  test    rax, rax
0x180003119  jnz     loc_1800033D1
0x18000311f  mov     rdx, rax; Buffer
0x180003122  xor     ecx, ecx; Flags
0x180003124  call    cs:__imp_RtlpEnsureBufferSize
0x18000312a  test    eax, eax
0x18000312c  jns     loc_180002FC3
0x180003132  mov     ecx, 0C0000017h; int
0x180003137  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000313c  mov     edi, eax
0x18000313e  jmp     loc_180003021
0x180003143  mov     ecx, 5B8h; Size
0x180003148  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000314d  mov     rsi, rax
0x180003150  test    rax, rax
0x180003153  jz      loc_1800030BA
0x180003159  lea     rcx, [rsi+70h]
0x18000315d  mov     edx, 208h
0x180003162  lea     rax, ??_7COfflineFilesItem@@6B@; const COfflineFilesItem::`vftable'
0x180003169  mov     r12d, 1
0x18000316f  mov     [rsi+58h], rax
0x180003173  mov     rax, [rbp+arg_0]
0x180003177  mov     [rsi+68h], rax
0x18000317b  mov     [rsi+60h], r12d
0x18000317f  mov     [rcx+218h], rcx
0x180003186  mov     [rcx+228h], rdx
0x18000318d  mov     [rcx+220h], rcx
0x180003194  mov     [rcx+230h], rdx
0x18000319b  mov     [rcx+210h], rcx
0x1800031a2  test    rcx, rcx
0x1800031a5  jz      short loc_1800031AC
0x1800031a7  xor     eax, eax
0x1800031a9  mov     [rcx], ax
0x1800031ac  mov     dword ptr [rcx+208h], 2080000h
0x1800031b6  mov     rcx, [rsi+68h]
0x1800031ba  mov     rax, [rcx]
0x1800031bd  mov     rax, [rax+8]
0x1800031c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c6  lea     rcx, [rsi+2B0h]; void *
0x1800031cd  xor     edx, edx; Val
0x1800031cf  mov     r8d, 300h; Size
0x1800031d5  call    memset_0
0x1800031da  mov     [rsi+5B0h], r12d
0x1800031e1  lea     rax, ??_7COfflineFilesDirectoryItem@@6BIOfflineFilesDirectoryItem@@@; const COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesDirectoryItem'}
0x1800031e8  mov     [rsi], rax
0x1800031eb  lea     rax, ??_7COfflineFilesDirectoryItem@@6BIOfflineFilesItemContainer@@@; const COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesItemContainer'}
0x1800031f2  mov     [rsi+8], rax
0x1800031f6  lea     rax, ??_7COfflineFilesDirectoryItem@@6BIOfflineFilesChangeInfo@@@; const COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesChangeInfo'}
0x1800031fd  mov     [rsi+10h], rax
0x180003201  lea     rax, ??_7COfflineFilesDirectoryItem@@6BIOfflineFilesPinInfo2@@@; const COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesPinInfo2'}
0x180003208  mov     [rsi+18h], rax
0x18000320c  lea     rax, ??_7COfflineFilesDirectoryItem@@6BIOfflineFilesFileSysInfo@@@; const COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesFileSysInfo'}
0x180003213  mov     [rsi+20h], rax
0x180003217  lea     rax, ??_7COfflineFilesDirectoryItem@@6BIOfflineFilesConnectionInfo@@@; const COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesConnectionInfo'}
0x18000321e  mov     [rsi+28h], rax
0x180003222  lea     rax, ??_7COfflineFilesDirectoryItem@@6BIOfflineFilesShareInfo@@@; const COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesShareInfo'}
0x180003229  mov     [rsi+30h], rax
0x18000322d  lea     rax, ??_7COfflineFilesDirectoryItem@@6BIOfflineFilesSuspend@@@; const COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesSuspend'}
0x180003234  mov     [rsi+38h], rax
0x180003238  lea     rax, ??_7COfflineFilesDirectoryItem@@6BIOfflineFilesSuspendInfo@@@; const COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesSuspendInfo'}
0x18000323f  mov     [rsi+40h], rax
0x180003243  lea     rax, ??_7COfflineFilesDirectoryItem@@6BIOfflineFilesTransparentCacheInfo@@@; const COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesTransparentCacheInfo'}
0x18000324a  mov     [rsi+48h], rax
0x18000324e  lea     rax, ??_7COfflineFilesDirectoryItem@@6BIOfflineFilesGhostInfo@@@; const COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesGhostInfo'}
0x180003255  mov     [rsi+50h], rax
0x180003259  lea     rax, ??_7COfflineFilesDirectoryItem@@6BCOfflineFilesItem@@@; const COfflineFilesDirectoryItem::`vftable'{for `COfflineFilesItem'}
0x180003260  mov     [rsi+58h], rax
0x180003264  test    r13, r13
0x180003267  jnz     loc_18000345C
0x18000326d  xorps   xmm0, xmm0
0x180003270  lea     rdx, SourceString; "\\\\"
0x180003277  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000327b  xor     r12d, r12d
0x18000327e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180003282  call    cs:__imp_RtlInitUnicodeString
0x180003288  movzx   edx, [rbp+DestinationString.Length]
0x18000328c  xor     eax, eax
0x18000328e  mov     [rsi+278h], ax
0x180003295  lea     r8, [rdx+2]; RequiredSize
0x180003299  cmp     r8, 0FFFEh
0x1800032a0  ja      loc_1800035A8
0x1800032a6  lea     rax, [rsi+288h]
0x1800032ad  test    rax, rax
0x1800032b0  jnz     loc_1800034CA
0x1800032b6  mov     rdx, rax; Buffer
0x1800032b9  xor     ecx, ecx; Flags
0x1800032bb  call    cs:__imp_RtlpEnsureBufferSize
0x1800032c1  test    eax, eax
0x1800032c3  js      loc_1800034B9
0x1800032c9  movzx   edx, [rbp+DestinationString.Length]
0x1800032cd  movzx   eax, word ptr [rsi+278h]
0x1800032d4  xor     edi, edi
0x1800032d6  mov     rcx, [rsi+288h]
0x1800032dd  shr     rax, 1
0x1800032e0  movzx   r8d, dx; Size
0x1800032e4  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x1800032e8  mov     [rsi+280h], rcx
0x1800032ef  lea     rcx, [rcx+rax*2]; void *
0x1800032f3  call    memmove_0
0x1800032f8  movzx   eax, [rbp+DestinationString.Length]
0x1800032fc  add     ax, [rsi+278h]
0x180003303  movzx   edx, ax
0x180003306  mov     [rsi+278h], dx
0x18000330d  lea     eax, [rdx+2]
0x180003310  shr     rdx, 1
0x180003313  mov     [rsi+27Ah], ax
0x18000331a  xor     eax, eax
0x18000331c  mov     rcx, [rsi+280h]
0x180003323  mov     [rcx+rdx*2], ax
0x180003327  test    edi, edi
0x180003329  js      loc_1800033B0
0x18000332f  lea     rax, [rsi+2B0h]
0x180003336  mov     rcx, r14
0x180003339  mov     edx, 6
0x18000333e  lea     rax, [rax+80h]
0x180003345  movups  xmm0, xmmword ptr [rcx]
  ... truncated ...
```
