# CAppExport::ExportDllNames(_GUID,ushort *)

- ea: `0x18004afcc`
- end: `0x18004b52e`
- name: `?ExportDllNames@CAppExport@@AEAAJU_GUID@@PEAG@Z`
- size: `1378`
- prototype: `int(CAppExport *__hidden this, struct _GUID *__struct_ptr, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fe08`

## callees

- `0x18000a01c`
- `0x18000be28`
- `0x18001a6c8`
- `0x18003a604`
- `0x18003a6a8`
- `0x18003a77c`
- `0x18003e5e4`
- `0x18004afcc`
- `0x180055502`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x18004b05a`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004b05a`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18004b1e7`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18004b257`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18004b1e7`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18004b257`
- `MfcSubs!?Mid@CString@@QEBA?AV1@H@Z` at `0x18004b1c7`
- `MfcSubs!?Mid@CString@@QEBA?AV1@H@Z` at `0x18004b237`
- `MfcSubs!?Mid@CString@@QEBA?AV1@H@Z` at `0x18004b1c7`
- `MfcSubs!?Mid@CString@@QEBA?AV1@H@Z` at `0x18004b237`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18004b38b`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18004b38b`
- `MfcSubs!?ReverseFind@CString@@QEBAHG@Z` at `0x18004b19c`
- `MfcSubs!?ReverseFind@CString@@QEBAHG@Z` at `0x18004b19c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b2c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b3a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b4dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b2c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b3a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b4dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b203`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b28a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b315`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b203`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b28a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b315`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAppExport::ExportDllNames(CAppExport *this, struct _GUID *a2, unsigned __int16 *a3)
{
  int v4; // r13d
  int SimpleTableDispenser; // edi
  int v6; // eax
  unsigned __int16 *v7; // rsi
  int i; // eax
  __int64 v9; // r12
  __int64 v10; // rdx
  const unsigned __int16 *v11; // rcx
  BOOL v12; // esi
  int v13; // eax
  unsigned int v14; // edx
  int v15; // eax
  int v16; // edi
  const unsigned __int16 **v17; // rax
  int v18; // eax
  unsigned __int64 v19; // rsi
  const unsigned __int16 **v20; // rax
  unsigned __int64 v21; // rdi
  int k; // edx
  char *v23; // rax
  signed __int64 v24; // r9
  int v25; // ecx
  int v26; // r8d
  FileInfo *v27; // rax
  unsigned int v28; // edx
  FileInfo *v29; // rdi
  unsigned int v30; // edx
  int j; // r14d
  __int64 result; // rax
  unsigned int v33; // edx
  signed __int64 v34; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+58h] [rbp-B0h] BYREF
  int v36; // [rsp+60h] [rbp-A8h] BYREF
  FileInfo *v37; // [rsp+68h] [rbp-A0h]
  unsigned __int64 v38; // [rsp+70h] [rbp-98h]
  void **v39; // [rsp+78h] [rbp-90h] BYREF
  __int64 v40; // [rsp+80h] [rbp-88h]
  int v41; // [rsp+88h] [rbp-80h]
  __int64 v42; // [rsp+8Ch] [rbp-7Ch]
  unsigned __int16 *v43; // [rsp+98h] [rbp-70h]
  _BYTE v44[8]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v45[8]; // [rsp+A8h] [rbp-60h] BYREF
  struct _GUID *v46; // [rsp+B0h] [rbp-58h]
  unsigned __int16 *v47; // [rsp+B8h] [rbp-50h] BYREF
  int v48; // [rsp+C0h] [rbp-48h]
  int v49; // [rsp+C4h] [rbp-44h]
  int v50; // [rsp+C8h] [rbp-40h]
  int v51; // [rsp+CCh] [rbp-3Ch]
  FileInfo *v52; // [rsp+D0h] [rbp-38h]

  v46 = a2;
  v39 = &CArray<DllInfo *,DllInfo * const &>::`vftable';
  v40 = 0;
  v42 = 0;
  v4 = 0;
  v41 = 0;
  v47 = a3;
  v48 = 0;
  v49 = -268435455;
  v50 = 130;
  v51 = 2 * safe_lstrlenW(a3) + 2;
  v35 = 0;
  if ( *((_QWORD *)this + 22) )
  {
LABEL_5:
    v6 = memcmp_0(tidCOMSERVICES_DLLNAMES_EXPORT, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, unsigned __int16 **, __int64, int, int, __int64 *))(**((_QWORD **)this + 22) + 24LL))(
                             *((_QWORD *)this + 22),
                             didCOMSERVICES,
                             tidCOMSERVICES_DLLNAMES_EXPORT,
                             &v47,
                             1,
                             1,
                             v6 != 0 ? 6 : 4,
                             &v35);
    goto LABEL_6;
  }
  v34 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v34);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 22, v34, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v34 + 16LL))(v34);
    goto LABEL_5;
  }
LABEL_6:
  if ( SimpleTableDispenser < 0 )
    goto LABEL_53;
  if ( !v35 )
  {
    SimpleTableDispenser = -2147024882;
    goto LABEL_55;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 24LL))(v35);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_53;
  v7 = 0;
  for ( i = 0; ; i = v34 + 1 )
  {
    LODWORD(v34) = i;
    if ( i >= *((_DWORD *)this + 24) )
    {
      for ( j = 0; j < v4; ++j )
      {
        LODWORD(v34) = *(_DWORD *)(*(_QWORD *)(v40 + 8LL * j) + 8LL);
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 120LL))(v35);
        if ( SimpleTableDispenser < 0 )
          goto LABEL_51;
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct _GUID *))(*(_QWORD *)v35
                                                                                                  + 160LL))(
                                 v35,
                                 0,
                                 0,
                                 v46);
        if ( SimpleTableDispenser < 0 )
          goto LABEL_51;
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v35 + 160LL))(
                                 v35,
                                 1,
                                 0,
                                 **(_QWORD **)(v40 + 8LL * j));
        if ( SimpleTableDispenser < 0 )
          goto LABEL_51;
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, signed __int64 *))(*(_QWORD *)v35 + 160LL))(
                                 v35,
                                 2,
                                 0,
                                 &v34);
        if ( SimpleTableDispenser < 0 )
          goto LABEL_51;
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 144LL))(v35);
        if ( SimpleTableDispenser < 0 )
          goto LABEL_51;
      }
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 96LL))(v35);
      goto LABEL_51;
    }
    v9 = i;
    v10 = *(_QWORD *)(*((_QWORD *)this + 11) + 8LL * i);
    v11 = *(const unsigned __int16 **)v10;
    if ( *(_DWORD *)(*(_QWORD *)v10 - 8LL) )
    {
      v36 = 1;
      v37 = 0;
      v12 = 1;
      if ( *(_DWORD *)(v10 + 8) == 6 )
      {
        v13 = IsLocalPath(v11, 0);
        SimpleTableDispenser = v13;
        if ( v13 < 0 )
          goto LABEL_15;
        v12 = v13 != 1;
      }
      v15 = CString::ReverseFind(*(CString **)(*((_QWORD *)this + 11) + 8 * v9), 0x5Cu);
      v16 = v15;
      if ( v12 && v15 > 0 )
      {
        v17 = (const unsigned __int16 **)CString::Mid(
                                           *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v9),
                                           v44,
                                           (unsigned int)v15);
        v18 = safe_lstrlenW(*v17) + 1;
        v19 = v18;
        v38 = v18;
        CString::~CString((CString *)v44);
        v7 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v19, 2u));
        v43 = v7;
        if ( !v7 )
          goto LABEL_20;
        v20 = (const unsigned __int16 **)CString::Mid(
                                           *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v9),
                                           v45,
                                           (unsigned int)(v16 + 1));
        SimpleTableDispenser = StringCchCopyW(v7, v38, *v20);
        CString::~CString((CString *)v45);
      }
      else
      {
        v21 = (int)(safe_lstrlenW(**(const unsigned __int16 ***)(*((_QWORD *)this + 11) + 8 * v9)) + 1);
        v7 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v21, 2u));
        v43 = v7;
        if ( !v7 )
        {
LABEL_20:
          SimpleTableDispenser = -2147024882;
LABEL_15:
          CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v36, v14);
          goto LABEL_53;
        }
        SimpleTableDispenser = StringCchCopyW(v7, v21, **(const unsigned __int16 ***)(*((_QWORD *)this + 11) + 8 * v9));
      }
      if ( SimpleTableDispenser < 0 )
      {
        CoTaskMemFree(v7);
        goto LABEL_15;
      }
      for ( k = 0; k < v4; ++k )
      {
        v23 = **(char ***)(v40 + 8LL * k);
        v24 = (char *)v7 - v23;
        do
        {
          v25 = *(unsigned __int16 *)&v23[v24];
          v26 = *(unsigned __int16 *)v23 - v25;
          if ( v26 )
            break;
          v23 += 2;
        }
        while ( v25 );
        if ( !v26 )
          goto LABEL_40;
      }
      v27 = (FileInfo *)CoTaskMemAlloc(0x10u);
      v52 = v27;
      if ( v27 )
        v29 = FileInfo::FileInfo(v27);
      else
        v29 = 0;
      v38 = (unsigned __int64)v29;
      v37 = v29;
      if ( !v29 )
      {
        SimpleTableDispenser = -2147024882;
        CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v36, v28);
        goto LABEL_51;
      }
      if ( v4 >= 0 )
      {
        try
        {
          CArray<DllInfo *,DllInfo * const &>::SetSize(&v39, (unsigned int)(v4 + 1));
          *(_QWORD *)(v40 + 8LL * v4) = v29;
          v4 = v41;
        }
        catch ( ... )
        {
          DllInfo::`scalar deleting destructor'((DllInfo *)v38);
          LODWORD(v34) = -2147024882;
          CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v36, v33);
          SimpleTableDispenser = v34;
          v7 = v43;
LABEL_51:
          if ( v7 )
            CoTaskMemFree(v7);
LABEL_53:
          if ( v35 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
            v35 = 0;
          }
LABEL_55:
          CArray<DllInfo *,DllInfo * const &>::SetSize(&v39, 0);
          CArray<DllInfo *,DllInfo * const &>::~CArray<DllInfo *,DllInfo * const &>((__int64)&v39);
          result = (unsigned int)SimpleTableDispenser;
        }
      }
      CString::operator=(v29, v7);
      *((_DWORD *)v29 + 2) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 8 * v9) + 8LL);
      v36 = 0;
LABEL_40:
      CoTaskMemFree(v7);
      v7 = 0;
      CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v36, v30);
    }
  }
}

```

## disassembly

```asm
0x18004afcc  mov     r11, rsp
0x18004afcf  mov     [r11+18h], rbx
0x18004afd3  push    rsi
0x18004afd4  push    rdi
0x18004afd5  push    r12
0x18004afd7  push    r13
0x18004afd9  push    r14
0x18004afdb  sub     rsp, 0E0h
0x18004afe2  mov     [rsp+108h+var_58], rdx
0x18004afea  mov     r14, rcx
0x18004afed  lea     rax, ??_7?$CArray@PEAUDllInfo@@AEBQEAU1@@@6B@; const CArray<DllInfo *,DllInfo * const &>::`vftable'
0x18004aff4  mov     [rsp+108h+var_90], rax
0x18004aff9  xor     ebx, ebx
0x18004affb  mov     [r11-88h], rbx
0x18004b002  mov     [r11-7Ch], rbx
0x18004b006  mov     r13d, ebx
0x18004b009  mov     [r11-80h], ebx
0x18004b00d  mov     [r11-50h], r8
0x18004b011  mov     [r11-48h], ebx
0x18004b015  mov     dword ptr [r11-44h], 0F0000001h
0x18004b01d  mov     dword ptr [r11-40h], 82h
0x18004b025  mov     rcx, r8; unsigned __int16 *
0x18004b028  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004b02d  lea     eax, ds:2[rax*2]
0x18004b034  mov     [rsp+108h+var_3C], eax
0x18004b03b  mov     [rsp+108h+var_B0], rbx
0x18004b040  cmp     [r14+0B0h], rbx
0x18004b047  jnz     short loc_18004B08D
0x18004b049  mov     [rsp+108h+var_B8], rbx
0x18004b04e  lea     rdx, [rsp+108h+var_B8]
0x18004b053  lea     rcx, IID_ISimpleTableDispenser
0x18004b05a  call    cs:__imp_GetSimpleTableDispenser
0x18004b060  mov     edi, eax
0x18004b062  test    eax, eax
0x18004b064  js      loc_18004B0FA
0x18004b06a  mov     rcx, [rsp+108h+var_B8]
0x18004b06f  xor     eax, eax
0x18004b071  lock cmpxchg [r14+0B0h], rcx
0x18004b07a  jz      short loc_18004B08D
0x18004b07c  mov     rcx, [rsp+108h+var_B8]
0x18004b081  mov     rax, [rcx]
0x18004b084  mov     rax, [rax+10h]
0x18004b088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b08d  mov     r8d, 10h; Size
0x18004b093  lea     rdx, TID_APPLICATION; Buf2
0x18004b09a  lea     rcx, tidCOMSERVICES_DLLNAMES_EXPORT; Buf1
0x18004b0a1  call    memcmp_0
0x18004b0a6  neg     eax
0x18004b0a8  sbb     edx, edx
0x18004b0aa  and     edx, 2
0x18004b0ad  add     edx, 4
0x18004b0b0  mov     rcx, [r14+0B0h]
0x18004b0b7  mov     rax, [rcx]
0x18004b0ba  lea     r9, [rsp+108h+var_B0]
0x18004b0bf  mov     [rsp+108h+var_D0], r9
0x18004b0c4  mov     [rsp+108h+var_D8], edx
0x18004b0c8  mov     [rsp+108h+var_E0], 1
0x18004b0d0  mov     [rsp+108h+var_E8], 1
0x18004b0d9  lea     r9, [rsp+108h+var_50]
0x18004b0e1  lea     r8, tidCOMSERVICES_DLLNAMES_EXPORT
0x18004b0e8  lea     rdx, didCOMSERVICES
0x18004b0ef  mov     rax, [rax+18h]
0x18004b0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b0f8  mov     edi, eax
0x18004b0fa  test    edi, edi
0x18004b0fc  js      loc_18004B4E2
0x18004b102  mov     rcx, [rsp+108h+var_B0]
0x18004b107  test    rcx, rcx
0x18004b10a  jnz     short loc_18004B116
0x18004b10c  mov     edi, 8007000Eh
0x18004b111  jmp     loc_18004B4FD
0x18004b116  mov     rax, [rcx]
0x18004b119  mov     rax, [rax+18h]
0x18004b11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b122  mov     edi, eax
0x18004b124  test    eax, eax
0x18004b126  js      loc_18004B4E2
0x18004b12c  mov     rsi, rbx
0x18004b12f  mov     eax, ebx
0x18004b131  mov     dword ptr [rsp+108h+var_B8], eax
0x18004b135  cmp     eax, [r14+60h]
0x18004b139  jge     loc_18004B3E1
0x18004b13f  movsxd  r12, eax
0x18004b142  mov     rax, [r14+58h]
0x18004b146  mov     rdx, [rax+r12*8]
0x18004b14a  mov     rcx, [rdx]; unsigned __int16 *
0x18004b14d  cmp     [rcx-8], ebx
0x18004b150  jz      loc_18004B3B9
0x18004b156  mov     [rsp+108h+var_A8], 1
0x18004b15e  mov     [rsp+108h+var_A0], rbx
0x18004b163  mov     esi, 1
0x18004b168  cmp     dword ptr [rdx+8], 6
0x18004b16c  jnz     short loc_18004B18F
0x18004b16e  xor     edx, edx; unsigned __int16 **
0x18004b170  call    ?IsLocalPath@@YAJPEBGPEAPEAG@Z; IsLocalPath(ushort const *,ushort * *)
0x18004b175  mov     edi, eax
0x18004b177  test    eax, eax
0x18004b179  jns     short loc_18004B18A
0x18004b17b  lea     rcx, [rsp+108h+var_A8]
0x18004b180  call    ??1?$CPtr@UFileInfo@@@@QEAA@XZ; CPtr<FileInfo>::~CPtr<FileInfo>(void)
0x18004b185  jmp     loc_18004B4E2
0x18004b18a  cmp     eax, esi
0x18004b18c  cmovz   esi, ebx
0x18004b18f  mov     edx, 5Ch ; '\'
0x18004b194  mov     rcx, [r14+58h]
0x18004b198  mov     rcx, [rcx+r12*8]
0x18004b19c  call    cs:__imp_?ReverseFind@CString@@QEBAHG@Z; CString::ReverseFind(ushort)
0x18004b1a2  mov     edi, eax
0x18004b1a4  test    esi, esi
0x18004b1a6  jz      loc_18004B25F
0x18004b1ac  test    eax, eax
0x18004b1ae  jle     loc_18004B25F
0x18004b1b4  mov     rcx, [r14+58h]
0x18004b1b8  mov     r8d, eax
0x18004b1bb  lea     rdx, [rsp+108h+var_68]
0x18004b1c3  mov     rcx, [rcx+r12*8]
0x18004b1c7  call    cs:__imp_?Mid@CString@@QEBA?AV1@H@Z; CString::Mid(int)
0x18004b1cd  mov     rcx, [rax]; unsigned __int16 *
0x18004b1d0  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004b1d5  inc     eax
0x18004b1d7  movsxd  rsi, eax
0x18004b1da  mov     [rsp+108h+var_98], rsi
0x18004b1df  lea     rcx, [rsp+108h+var_68]
0x18004b1e7  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18004b1ed  mov     eax, 2
0x18004b1f2  mul     rsi
0x18004b1f5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004b1fc  cmovb   rax, rcx
0x18004b200  mov     rcx, rax; cb
0x18004b203  call    cs:__imp_CoTaskMemAlloc
0x18004b209  mov     rsi, rax
0x18004b20c  mov     [rsp+108h+var_70], rax
0x18004b214  test    rax, rax
0x18004b217  jnz     short loc_18004B223
0x18004b219  mov     edi, 8007000Eh
0x18004b21e  jmp     loc_18004B17B
0x18004b223  lea     r8d, [rdi+1]
0x18004b227  mov     rcx, [r14+58h]
0x18004b22b  lea     rdx, [rsp+108h+var_60]
0x18004b233  mov     rcx, [rcx+r12*8]
0x18004b237  call    cs:__imp_?Mid@CString@@QEBA?AV1@H@Z; CString::Mid(int)
0x18004b23d  mov     r8, [rax]; unsigned __int16 *
0x18004b240  mov     rdx, [rsp+108h+var_98]; unsigned __int64
0x18004b245  mov     rcx, rsi; unsigned __int16 *
0x18004b248  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b24d  mov     edi, eax
0x18004b24f  lea     rcx, [rsp+108h+var_60]
0x18004b257  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18004b25d  jmp     short loc_18004B2BC
0x18004b25f  mov     rax, [r14+58h]
0x18004b263  mov     rcx, [rax+r12*8]
0x18004b267  mov     rcx, [rcx]; unsigned __int16 *
0x18004b26a  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004b26f  inc     eax
0x18004b271  movsxd  rdi, eax
0x18004b274  mov     eax, 2
0x18004b279  mul     rdi
0x18004b27c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004b283  cmovb   rax, rcx
0x18004b287  mov     rcx, rax; cb
0x18004b28a  call    cs:__imp_CoTaskMemAlloc
0x18004b290  mov     rsi, rax
0x18004b293  mov     [rsp+108h+var_70], rax
0x18004b29b  test    rax, rax
0x18004b29e  jz      loc_18004B219
0x18004b2a4  mov     rax, [r14+58h]
0x18004b2a8  mov     r8, [rax+r12*8]
0x18004b2ac  mov     r8, [r8]; unsigned __int16 *
0x18004b2af  mov     rdx, rdi; unsigned __int64
0x18004b2b2  mov     rcx, rsi; unsigned __int16 *
0x18004b2b5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b2ba  mov     edi, eax
0x18004b2bc  test    edi, edi
0x18004b2be  jns     short loc_18004B2CE
0x18004b2c0  mov     rcx, rsi; pv
0x18004b2c3  call    cs:__imp_CoTaskMemFree
0x18004b2c9  jmp     loc_18004B17B
0x18004b2ce  mov     edx, ebx
0x18004b2d0  cmp     edx, r13d
0x18004b2d3  jge     short loc_18004B310
0x18004b2d5  movsxd  rax, edx
0x18004b2d8  mov     rcx, [rsp+108h+var_88]
0x18004b2e0  mov     rcx, [rcx+rax*8]
0x18004b2e4  mov     rax, [rcx]
0x18004b2e7  mov     r9, rsi
0x18004b2ea  sub     r9, rax
0x18004b2ed  movzx   r8d, word ptr [rax]
0x18004b2f1  movzx   ecx, word ptr [rax+r9]
0x18004b2f6  sub     r8d, ecx
0x18004b2f9  jnz     short loc_18004B303
0x18004b2fb  add     rax, 2
0x18004b2ff  test    ecx, ecx
0x18004b301  jnz     short loc_18004B2ED
0x18004b303  test    r8d, r8d
0x18004b306  jz      loc_18004B3A3
0x18004b30c  inc     edx
0x18004b30e  jmp     short loc_18004B2D0
0x18004b310  mov     ecx, 10h; cb
0x18004b315  call    cs:__imp_CoTaskMemAlloc
0x18004b31b  mov     [rsp+108h+var_38], rax
0x18004b323  test    rax, rax
0x18004b326  jz      short loc_18004B335
0x18004b328  mov     rcx, rax; this
0x18004b32b  call    ??0FileInfo@@QEAA@XZ; FileInfo::FileInfo(void)
0x18004b330  mov     rdi, rax
0x18004b333  jmp     short loc_18004B338
0x18004b335  mov     rdi, rbx
0x18004b338  mov     [rsp+108h+var_98], rdi
0x18004b33d  mov     [rsp+108h+var_A0], rdi
0x18004b342  test    rdi, rdi
0x18004b345  jnz     short loc_18004B35B
0x18004b347  mov     edi, 8007000Eh
0x18004b34c  lea     rcx, [rsp+108h+var_A8]
0x18004b351  call    ??1?$CPtr@UFileInfo@@@@QEAA@XZ; CPtr<FileInfo>::~CPtr<FileInfo>(void)
0x18004b356  jmp     loc_18004B4D4
0x18004b35b  test    r13d, r13d
0x18004b35e  js      short loc_18004B385
0x18004b360  lea     edx, [r13+1]
0x18004b364  lea     rcx, [rsp+108h+var_90]
0x18004b369  call    ?SetSize@?$CArray@PEAUDllInfo@@AEBQEAU1@@@QEAAXHH@Z; CArray<DllInfo *,DllInfo * const &>::SetSize(int,int)
0x18004b36e  movsxd  rax, r13d
0x18004b371  mov     rcx, [rsp+108h+var_88]
0x18004b379  mov     [rcx+rax*8], rdi
0x18004b37d  mov     r13d, [rsp+108h+var_80]
0x18004b385  mov     rdx, rsi
0x18004b388  mov     rcx, rdi
0x18004b38b  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x18004b391  mov     rax, [r14+58h]
0x18004b395  mov     rcx, [rax+r12*8]
0x18004b399  mov     eax, [rcx+8]
0x18004b39c  mov     [rdi+8], eax
0x18004b39f  mov     [rsp+108h+var_A8], ebx
0x18004b3a3  mov     rcx, rsi; pv
0x18004b3a6  call    cs:__imp_CoTaskMemFree
0x18004b3ac  mov     rsi, rbx
0x18004b3af  lea     rcx, [rsp+108h+var_A8]
0x18004b3b4  call    ??1?$CPtr@UFileInfo@@@@QEAA@XZ; CPtr<FileInfo>::~CPtr<FileInfo>(void)
0x18004b3b9  mov     eax, dword ptr [rsp+108h+var_B8]
0x18004b3bd  inc     eax
0x18004b3bf  jmp     loc_18004B131
0x18004b3c4  lea     rcx, [rsp+108h+var_A8]
0x18004b3c9  call    ??1?$CPtr@UFileInfo@@@@QEAA@XZ; CPtr<FileInfo>::~CPtr<FileInfo>(void)
0x18004b3ce  xor     ebx, ebx
0x18004b3d0  mov     edi, dword ptr [rsp+108h+var_B8]
0x18004b3d4  mov     rsi, [rsp+108h+var_70]
0x18004b3dc  jmp     loc_18004B4D4
0x18004b3e1  mov     r14d, ebx
0x18004b3e4  cmp     r14d, r13d
0x18004b3e7  jge     loc_18004B4C1
0x18004b3ed  movsxd  r12, r14d
0x18004b3f0  mov     rax, [rsp+108h+var_88]
0x18004b3f8  mov     rax, [rax+r12*8]
0x18004b3fc  mov     ecx, [rax+8]
0x18004b3ff  mov     dword ptr [rsp+108h+var_B8], ecx
0x18004b403  mov     rcx, [rsp+108h+var_B0]
0x18004b408  mov     rax, [rcx]
0x18004b40b  mov     rax, [rax+78h]
0x18004b40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b414  mov     edi, eax
0x18004b416  test    eax, eax
0x18004b418  js      loc_18004B4D4
0x18004b41e  mov     rcx, [rsp+108h+var_B0]
0x18004b423  mov     rax, [rcx]
0x18004b426  mov     r9, [rsp+108h+var_58]
0x18004b42e  xor     r8d, r8d
0x18004b431  xor     edx, edx
0x18004b433  mov     rax, [rax+0A0h]
0x18004b43a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b43f  mov     edi, eax
0x18004b441  test    eax, eax
0x18004b443  js      loc_18004B4D4
0x18004b449  mov     rcx, [rsp+108h+var_B0]
0x18004b44e  mov     rax, [rcx]
0x18004b451  mov     r9, [rsp+108h+var_88]
0x18004b459  mov     r9, [r9+r12*8]
0x18004b45d  mov     r9, [r9]
0x18004b460  xor     r8d, r8d
0x18004b463  lea     edx, [r8+1]
0x18004b467  mov     rax, [rax+0A0h]
0x18004b46e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b473  mov     edi, eax
0x18004b475  test    eax, eax
0x18004b477  js      short loc_18004B4D4
0x18004b479  mov     rcx, [rsp+108h+var_B0]
0x18004b47e  mov     rax, [rcx]
0x18004b481  lea     r9, [rsp+108h+var_B8]
0x18004b486  xor     r8d, r8d
0x18004b489  lea     edx, [r8+2]
0x18004b48d  mov     rax, [rax+0A0h]
0x18004b494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b499  mov     edi, eax
0x18004b49b  test    eax, eax
0x18004b49d  js      short loc_18004B4D4
0x18004b49f  mov     rcx, [rsp+108h+var_B0]
0x18004b4a4  mov     rax, [rcx]
0x18004b4a7  mov     rax, [rax+90h]
0x18004b4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b4b3  mov     edi, eax
0x18004b4b5  test    eax, eax
0x18004b4b7  js      short loc_18004B4D4
  ... truncated ...
```
