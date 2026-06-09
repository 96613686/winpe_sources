# CAppImport::UpdateRoleTable(_GUID,ushort *,_GUID,_GUID,int,_GUID,ulong)

- ea: `0x18000c04c`
- end: `0x18000c7b9`
- name: `?UpdateRoleTable@CAppImport@@AEAAJU_GUID@@PEAG00H0K@Z`
- size: `1901`
- prototype: `int(CAppImport *__hidden this, struct _GUID *__struct_ptr, unsigned __int16 *, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr, int, struct _GUID *__struct_ptr, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180041220`

## callees

- `0x18000a01c`
- `0x18000c04c`
- `0x18001a6c8`
- `0x180033ce4`
- `0x18003a6a8`
- `0x18003a77c`
- `0x18003e5e4`
- `0x180055502`
- `0x18005551a`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x18000c145`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18000c240`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18000c145`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18000c240`
- `CLBCatQ!ServerGetApplicationType` at `0x18000c4b0`
- `CLBCatQ!ServerGetApplicationType` at `0x18000c4b0`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18000c6f5`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18000c6f5`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18000c665`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18000c665`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x18000c6e6`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x18000c6e6`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x18000c6d9`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x18000c6d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c52c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c756`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c52c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c756`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c2f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c3ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c64c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c2f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c3ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c64c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAppImport::UpdateRoleTable(
        CAppImport *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        struct _GUID *a4,
        struct _GUID *a5,
        int a6,
        struct _GUID *a7,
        unsigned int a8)
{
  int v10; // r13d
  __int64 v11; // r9
  int SimpleTableDispenser; // edi
  int v13; // eax
  _QWORD *v14; // r14
  bool v15; // zf
  __int64 v16; // rax
  const struct _GUID *v17; // rcx
  _QWORD *v18; // rsi
  _QWORD *v19; // rax
  int j; // r14d
  __int64 v21; // rax
  unsigned __int16 *v22; // rax
  int v23; // eax
  struct _GUID *v24; // r14
  int v25; // r14d
  void *v26; // rcx
  unsigned int i; // esi
  const unsigned __int16 **v28; // rdi
  __int64 v29; // r8
  CString *v30; // rax
  unsigned int v31; // edx
  unsigned __int64 v32; // rdi
  CString *v33; // rdx
  unsigned int v34; // edx
  void *v35; // rcx
  __int64 result; // rax
  unsigned int v37; // edx
  unsigned int v38; // [rsp+50h] [rbp-F8h] BYREF
  const unsigned __int16 **v39; // [rsp+58h] [rbp-F0h] BYREF
  unsigned int v40; // [rsp+60h] [rbp-E8h] BYREF
  __int64 *v41; // [rsp+68h] [rbp-E0h] BYREF
  void *v42; // [rsp+70h] [rbp-D8h] BYREF
  __int64 v43; // [rsp+78h] [rbp-D0h] BYREF
  unsigned __int64 v44; // [rsp+80h] [rbp-C8h]
  int v45; // [rsp+88h] [rbp-C0h] BYREF
  unsigned __int64 v46; // [rsp+90h] [rbp-B8h]
  struct _GUID *v47; // [rsp+98h] [rbp-B0h]
  void *Buf2; // [rsp+A0h] [rbp-A8h]
  void **v49; // [rsp+A8h] [rbp-A0h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-98h]
  int v51; // [rsp+B8h] [rbp-90h]
  __int64 v52; // [rsp+BCh] [rbp-8Ch]
  struct _GUID *v53; // [rsp+C8h] [rbp-80h]
  char v54[8]; // [rsp+D0h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+D8h] [rbp-70h]
  unsigned __int16 *v56; // [rsp+E0h] [rbp-68h] BYREF
  int v57; // [rsp+E8h] [rbp-60h]
  int v58; // [rsp+ECh] [rbp-5Ch]
  int v59; // [rsp+F0h] [rbp-58h]
  int v60; // [rsp+F4h] [rbp-54h]
  __int64 v61; // [rsp+F8h] [rbp-50h]
  int v62; // [rsp+100h] [rbp-48h]
  int v63; // [rsp+104h] [rbp-44h]
  int v64; // [rsp+108h] [rbp-40h]
  int v65; // [rsp+10Ch] [rbp-3Ch]
  CString *v66; // [rsp+110h] [rbp-38h]

  v53 = a4;
  Buf2 = a2;
  v47 = a5;
  v38 = a8;
  v41 = 0;
  v49 = &CArray<DllInfo *,DllInfo * const &>::`vftable';
  v50 = 0;
  v52 = 0;
  v10 = 0;
  v51 = 0;
  v56 = a3;
  v57 = 0;
  v58 = -268435455;
  v59 = 130;
  v60 = 2 * safe_lstrlenW(a3) + 2;
  v61 = v11;
  v62 = 0;
  v63 = a6;
  v64 = 72;
  v65 = 16;
  v43 = 0;
  if ( !*((_QWORD *)this + 9) )
  {
    v39 = 0;
    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v39);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_6;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, (signed __int64)v39, 0) )
      (*((void (__fastcall **)(const unsigned __int16 **))*v39 + 2))(v39);
  }
  v13 = memcmp_0(a2, &TID_APPLICATION, 0x10u);
  SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, struct _GUID *, unsigned __int16 **, __int64, int, int, __int64 *))(**((_QWORD **)this + 9) + 24LL))(
                           *((_QWORD *)this + 9),
                           didCOMSERVICES,
                           a2,
                           &v56,
                           2,
                           1,
                           v13 != 0 ? 7 : 5,
                           &v43);
LABEL_6:
  if ( SimpleTableDispenser )
    goto LABEL_74;
  if ( !v43 )
  {
    SimpleTableDispenser = -2147024882;
    goto LABEL_76;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 24LL))(v43);
  if ( SimpleTableDispenser )
    goto LABEL_74;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 32LL))(v43);
  if ( SimpleTableDispenser )
    goto LABEL_74;
  v41 = 0;
  if ( !*((_QWORD *)this + 9) )
  {
    v39 = 0;
    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v39);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_16;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, (signed __int64)v39, 0) )
      (*((void (__fastcall **)(const unsigned __int16 **))*v39 + 2))(v39);
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, struct _GUID *, _QWORD, _QWORD, int, int, __int64 **))(**((_QWORD **)this + 9) + 24LL))(
                           *((_QWORD *)this + 9),
                           didCOMSERVICES,
                           a7,
                           0,
                           0,
                           1,
                           8388612,
                           &v41);
LABEL_16:
  if ( SimpleTableDispenser )
    goto LABEL_74;
  if ( !v41 )
    goto LABEL_18;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64 *))(*v41 + 24))(v41);
  if ( SimpleTableDispenser )
    goto LABEL_74;
  v14 = CoTaskMemAlloc(saturated_mul(v38, 8u));
  pv = v14;
  if ( !v14 )
  {
LABEL_18:
    SimpleTableDispenser = -2147024882;
    goto LABEL_74;
  }
  while ( 1 )
  {
    v15 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v43 + 40LL))(v43) == -2146367487;
    v16 = *v41;
    if ( v15 )
      break;
    SimpleTableDispenser = (*(__int64 (**)(void))(v16 + 120))();
    if ( SimpleTableDispenser )
      goto LABEL_73;
    *v14 = 0;
    for ( i = 0; i < v38; ++i )
    {
      v40 = 0;
      LODWORD(v42) = 0;
      v39 = (const unsigned __int16 **)&v14[i];
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *, void **, const unsigned __int16 **))(*(_QWORD *)v43 + 64LL))(
                               v43,
                               i,
                               &v40,
                               &v42,
                               v39);
      if ( SimpleTableDispenser )
        goto LABEL_73;
      v28 = v39;
      if ( i == a6 )
        *v39 = (const unsigned __int16 *)v47;
      if ( *v28 )
      {
        v29 = 0;
        if ( v40 == 128 )
          v29 = (unsigned int)v42;
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(*v41 + 160))(v41, i, v29);
        if ( SimpleTableDispenser )
          goto LABEL_73;
        v28 = v39;
      }
      if ( !memcmp_0(&tidCOMSERVICES_ROLEDEFINITION_EXPORT, Buf2, 0x10u) && i == 1 && *v28 )
      {
        v45 = 1;
        v46 = 0;
        v30 = (CString *)CoTaskMemAlloc(0x10u);
        v32 = (unsigned __int64)v30;
        v66 = v30;
        if ( v30 )
          CString::CString(v30);
        else
          v32 = 0;
        v44 = v32;
        v46 = v32;
        if ( !v32 )
        {
          SimpleTableDispenser = -2147024882;
          CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v45, v31);
          goto LABEL_73;
        }
        if ( v10 >= 0 )
        {
          try
          {
            CArray<DllInfo *,DllInfo * const &>::SetSize(&v49, (unsigned int)(v10 + 1));
            *(_QWORD *)(v50 + 8LL * v10) = v32;
            v10 = v51;
          }
          catch ( ... )
          {
            DllInfo::`scalar deleting destructor'((DllInfo *)v44);
            v38 = -2147024882;
            CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v45, v37);
            SimpleTableDispenser = v38;
LABEL_73:
            v35 = pv;
            *(_QWORD *)pv = 0;
            CoTaskMemFree(v35);
LABEL_74:
            if ( v43 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
              v43 = 0;
            }
LABEL_76:
            if ( v41 )
            {
              (*(void (__fastcall **)(__int64 *))(*v41 + 16))(v41);
              v41 = 0;
            }
            CArray<DllInfo *,DllInfo * const &>::~CArray<DllInfo *,DllInfo * const &>((__int64)&v49);
            result = (unsigned int)SimpleTableDispenser;
          }
        }
        v33 = CString::CString((CString *)v54, *v39);
        CString::operator=(v32, v33);
        CString::~CString((CString *)v54);
        v45 = 0;
        CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v45, v34);
      }
    }
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64 *))(*v41 + 144))(v41);
    if ( SimpleTableDispenser )
      goto LABEL_73;
  }
  SimpleTableDispenser = (*(__int64 (**)(void))(v16 + 96))();
  if ( SimpleTableDispenser )
    goto LABEL_73;
  if ( memcmp_0(&tidCOMSERVICES_ROLEDEFINITION_EXPORT, Buf2, 0x10u) )
    goto LABEL_73;
  if ( v10 <= 0 )
    goto LABEL_73;
  v18 = 0;
  v38 = 0;
  v40 = 0;
  v42 = 0;
  SimpleTableDispenser = GetSecurityAdmin(v17, &v42);
  if ( !SimpleTableDispenser )
  {
    if ( !v42 )
    {
      SimpleTableDispenser = -2147024882;
      goto LABEL_73;
    }
    v19 = CoTaskMemAlloc(saturated_mul(v10, 8u));
    v18 = v19;
    if ( !v19 )
    {
LABEL_29:
      SimpleTableDispenser = -2147024882;
      goto LABEL_42;
    }
    memset_0(v19, 0, 8LL * v10);
    for ( j = 0; j < v10; ++j )
    {
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)(**(_QWORD **)(v50 + 8LL * j) + 2 * v21) );
      v44 = v21 + 1;
      v22 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v21 + 1, 2u));
      v18[j] = v22;
      if ( !v22 )
        goto LABEL_29;
      SimpleTableDispenser = StringCchCopyW(v22, v44, **(const unsigned __int16 ***)(v50 + 8LL * j));
      if ( SimpleTableDispenser < 0 )
        goto LABEL_42;
    }
    v23 = (*(__int64 (__fastcall **)(void *, struct _GUID *, _QWORD, _QWORD *, int))(*(_QWORD *)v42 + 32LL))(
            v42,
            v47,
            (unsigned int)v10,
            v18,
            3);
    SimpleTableDispenser = v23;
    if ( v23 )
    {
      if ( v23 != 1 )
        goto LABEL_42;
      *((_DWORD *)this + 20) = 1;
    }
    v24 = v53;
    SimpleTableDispenser = ServerGetApplicationType(*((_QWORD *)this + 9), v53, &v40);
    if ( SimpleTableDispenser >= 0 )
    {
      v38 = v40;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(void *, struct _GUID *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v42 + 40LL))(
                               v42,
                               v24,
                               0,
                               0,
                               0,
                               0,
                               0,
                               &v38);
    }
  }
LABEL_42:
  if ( v42 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v42 + 16LL))(v42);
    v42 = 0;
  }
  if ( !v18 )
    goto LABEL_73;
  v25 = 0;
  while ( 1 )
  {
    v26 = (void *)v18[v25];
    if ( v26 )
    {
      CoTaskMemFree(v26);
      v18[v25] = 0;
    }
    if ( ++v25 >= v10 )
    {
      CoTaskMemFree(v18);
      goto LABEL_73;
    }
  }
}

```

## disassembly

```asm
0x18000c04c  mov     r11, rsp
0x18000c04f  mov     [r11+18h], rbx
0x18000c053  push    rsi
0x18000c054  push    rdi
0x18000c055  push    r13
0x18000c057  push    r14
0x18000c059  push    r15
0x18000c05b  sub     rsp, 120h
0x18000c062  mov     [rsp+148h+var_80], r9
0x18000c06a  mov     r14, rdx
0x18000c06d  mov     [rsp+148h+Buf2], rdx
0x18000c075  mov     r15, rcx
0x18000c078  mov     rax, [rsp+148h+arg_20]
0x18000c080  mov     [rsp+148h+var_B0], rax
0x18000c088  mov     rsi, [rsp+148h+arg_30]
0x18000c090  mov     eax, [rsp+148h+arg_38]
0x18000c097  mov     [rsp+148h+var_F8], eax
0x18000c09b  xor     ebx, ebx
0x18000c09d  mov     [rsp+148h+var_E0], rbx
0x18000c0a2  lea     rax, ??_7?$CArray@PEAUDllInfo@@AEBQEAU1@@@6B@; const CArray<DllInfo *,DllInfo * const &>::`vftable'
0x18000c0a9  mov     [r11-0A0h], rax
0x18000c0b0  mov     [r11-98h], rbx
0x18000c0b7  mov     [r11-8Ch], rbx
0x18000c0be  mov     r13d, ebx
0x18000c0c1  mov     [rsp+148h+var_90], ebx
0x18000c0c8  mov     [r11-68h], r8
0x18000c0cc  mov     [r11-60h], ebx
0x18000c0d0  mov     dword ptr [r11-5Ch], 0F0000001h
0x18000c0d8  mov     dword ptr [r11-58h], 82h
0x18000c0e0  mov     rcx, r8; unsigned __int16 *
0x18000c0e3  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18000c0e8  lea     eax, ds:2[rax*2]
0x18000c0ef  mov     [rsp+148h+var_54], eax
0x18000c0f6  mov     [rsp+148h+var_50], r9
0x18000c0fe  mov     [rsp+148h+var_48], ebx
0x18000c105  mov     eax, [rsp+148h+arg_28]
0x18000c10c  mov     [rsp+148h+var_44], eax
0x18000c113  mov     [rsp+148h+var_40], 48h ; 'H'
0x18000c11e  mov     [rsp+148h+var_3C], 10h
0x18000c129  mov     [rsp+148h+var_D0], rbx
0x18000c12e  cmp     [r15+48h], rbx
0x18000c132  jnz     short loc_18000C175
0x18000c134  mov     [rsp+148h+var_F0], rbx
0x18000c139  lea     rdx, [rsp+148h+var_F0]
0x18000c13e  lea     rcx, IID_ISimpleTableDispenser
0x18000c145  call    cs:__imp_GetSimpleTableDispenser
0x18000c14b  mov     edi, eax
0x18000c14d  test    eax, eax
0x18000c14f  js      loc_18000C1D7
0x18000c155  mov     rcx, [rsp+148h+var_F0]
0x18000c15a  xor     eax, eax
0x18000c15c  lock cmpxchg [r15+48h], rcx
0x18000c162  jz      short loc_18000C175
0x18000c164  mov     rcx, [rsp+148h+var_F0]
0x18000c169  mov     rax, [rcx]
0x18000c16c  mov     rax, [rax+10h]
0x18000c170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c175  mov     r8d, 10h; Size
0x18000c17b  lea     rdx, TID_APPLICATION; Buf2
0x18000c182  mov     rcx, r14; Buf1
0x18000c185  call    memcmp_0
0x18000c18a  neg     eax
0x18000c18c  sbb     edx, edx
0x18000c18e  and     edx, 2
0x18000c191  add     edx, 5
0x18000c194  mov     rcx, [r15+48h]
0x18000c198  mov     rax, [rcx]
0x18000c19b  lea     r8, [rsp+148h+var_D0]
0x18000c1a0  mov     [rsp+148h+var_110], r8
0x18000c1a5  mov     dword ptr [rsp+148h+var_118], edx
0x18000c1a9  mov     dword ptr [rsp+148h+var_120], 1
0x18000c1b1  mov     [rsp+148h+var_128], 2
0x18000c1ba  lea     r9, [rsp+148h+var_68]
0x18000c1c2  mov     r8, r14
0x18000c1c5  lea     rdx, didCOMSERVICES
0x18000c1cc  mov     rax, [rax+18h]
0x18000c1d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1d5  mov     edi, eax
0x18000c1d7  test    edi, edi
0x18000c1d9  jnz     loc_18000C75C
0x18000c1df  mov     rcx, [rsp+148h+var_D0]
0x18000c1e4  test    rcx, rcx
0x18000c1e7  jnz     short loc_18000C1F3
0x18000c1e9  mov     edi, 8007000Eh
0x18000c1ee  jmp     loc_18000C777
0x18000c1f3  mov     rax, [rcx]
0x18000c1f6  mov     rax, [rax+18h]
0x18000c1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1ff  mov     edi, eax
0x18000c201  test    eax, eax
0x18000c203  jnz     loc_18000C75C
0x18000c209  mov     rcx, [rsp+148h+var_D0]
0x18000c20e  mov     rax, [rcx]
0x18000c211  mov     rax, [rax+20h]
0x18000c215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c21a  mov     edi, eax
0x18000c21c  test    eax, eax
0x18000c21e  jnz     loc_18000C75C
0x18000c224  mov     [rsp+148h+var_E0], rbx
0x18000c229  cmp     [r15+48h], rbx
0x18000c22d  jnz     short loc_18000C26C
0x18000c22f  mov     [rsp+148h+var_F0], rbx
0x18000c234  lea     rdx, [rsp+148h+var_F0]
0x18000c239  lea     rcx, IID_ISimpleTableDispenser
0x18000c240  call    cs:__imp_GetSimpleTableDispenser
0x18000c246  mov     edi, eax
0x18000c248  test    eax, eax
0x18000c24a  js      short loc_18000C2AA
0x18000c24c  mov     rcx, [rsp+148h+var_F0]
0x18000c251  xor     eax, eax
0x18000c253  lock cmpxchg [r15+48h], rcx
0x18000c259  jz      short loc_18000C26C
0x18000c25b  mov     rcx, [rsp+148h+var_F0]
0x18000c260  mov     rax, [rcx]
0x18000c263  mov     rax, [rax+10h]
0x18000c267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c26c  mov     rcx, [r15+48h]
0x18000c270  mov     rax, [rcx]
0x18000c273  lea     rdx, [rsp+148h+var_E0]
0x18000c278  mov     [rsp+148h+var_110], rdx
0x18000c27d  mov     dword ptr [rsp+148h+var_118], 800004h
0x18000c285  mov     dword ptr [rsp+148h+var_120], 1
0x18000c28d  mov     [rsp+148h+var_128], rbx
0x18000c292  xor     r9d, r9d
0x18000c295  mov     r8, rsi
0x18000c298  lea     rdx, didCOMSERVICES
0x18000c29f  mov     rax, [rax+18h]
0x18000c2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2a8  mov     edi, eax
0x18000c2aa  test    edi, edi
0x18000c2ac  jnz     loc_18000C75C
0x18000c2b2  cmp     [rsp+148h+var_E0], rbx
0x18000c2b7  jnz     short loc_18000C2C3
0x18000c2b9  mov     edi, 8007000Eh
0x18000c2be  jmp     loc_18000C75C
0x18000c2c3  mov     rcx, [rsp+148h+var_E0]
0x18000c2c8  mov     rax, [rcx]
0x18000c2cb  mov     rax, [rax+18h]
0x18000c2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2d4  mov     edi, eax
0x18000c2d6  test    eax, eax
0x18000c2d8  jnz     loc_18000C75C
0x18000c2de  mov     ecx, [rsp+148h+var_F8]
0x18000c2e2  lea     eax, [rdi+8]
0x18000c2e5  mul     rcx
0x18000c2e8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c2ef  cmovb   rax, rcx
0x18000c2f3  mov     rcx, rax; cb
0x18000c2f6  call    cs:__imp_CoTaskMemAlloc
0x18000c2fc  mov     r14, rax
0x18000c2ff  mov     [rsp+148h+pv], rax
0x18000c307  test    rax, rax
0x18000c30a  jz      short loc_18000C2B9
0x18000c30c  mov     rcx, [rsp+148h+var_D0]
0x18000c311  mov     rax, [rcx]
0x18000c314  mov     rax, [rax+28h]
0x18000c318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c31d  mov     rcx, [rsp+148h+var_E0]
0x18000c322  cmp     eax, 80110801h
0x18000c327  mov     rax, [rcx]
0x18000c32a  jnz     loc_18000C54C
0x18000c330  mov     rax, [rax+60h]
0x18000c334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c339  mov     edi, eax
0x18000c33b  test    eax, eax
0x18000c33d  jnz     loc_18000C749
0x18000c343  lea     r8d, [rax+10h]; Size
0x18000c347  mov     rdx, [rsp+148h+Buf2]; Buf2
0x18000c34f  lea     rcx, tidCOMSERVICES_ROLEDEFINITION_EXPORT; Buf1
0x18000c356  call    memcmp_0
0x18000c35b  test    eax, eax
0x18000c35d  jnz     loc_18000C749
0x18000c363  test    r13d, r13d
0x18000c366  jle     loc_18000C749
0x18000c36c  mov     rsi, rbx
0x18000c36f  mov     [rsp+148h+var_F8], ebx
0x18000c373  mov     [rsp+148h+var_E8], ebx
0x18000c377  mov     [rsp+148h+var_D8], rbx
0x18000c37c  lea     rdx, [rsp+148h+var_D8]; void **
0x18000c381  call    ?GetSecurityAdmin@@YAJAEBU_GUID@@PEAPEAX@Z; GetSecurityAdmin(_GUID const &,void * *)
0x18000c386  mov     edi, eax
0x18000c388  test    eax, eax
0x18000c38a  jnz     loc_18000C4F9
0x18000c390  cmp     [rsp+148h+var_D8], rbx
0x18000c395  jnz     short loc_18000C3A1
0x18000c397  mov     edi, 8007000Eh
0x18000c39c  jmp     loc_18000C749
0x18000c3a1  movsxd  rdi, r13d
0x18000c3a4  mov     eax, 8
0x18000c3a9  mul     rdi
0x18000c3ac  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c3b3  cmovb   rax, rcx
0x18000c3b7  mov     rcx, rax; cb
0x18000c3ba  call    cs:__imp_CoTaskMemAlloc
0x18000c3c0  mov     rsi, rax
0x18000c3c3  test    rax, rax
0x18000c3c6  jnz     short loc_18000C3D2
0x18000c3c8  mov     edi, 8007000Eh
0x18000c3cd  jmp     loc_18000C4F9
0x18000c3d2  lea     r8, ds:0[rdi*8]; Size
0x18000c3da  xor     edx, edx; Val
0x18000c3dc  mov     rcx, rsi; void *
0x18000c3df  call    memset_0
0x18000c3e4  mov     r14d, ebx
0x18000c3e7  cmp     r14d, r13d
0x18000c3ea  jge     short loc_18000C466
0x18000c3ec  movsxd  rdi, r14d
0x18000c3ef  mov     rax, [rsp+148h+var_98]
0x18000c3f7  mov     rax, [rax+rdi*8]
0x18000c3fb  mov     rcx, [rax]
0x18000c3fe  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c402  mov     rax, r8
0x18000c405  inc     rax
0x18000c408  cmp     [rcx+rax*2], bx
0x18000c40c  jnz     short loc_18000C405
0x18000c40e  lea     rcx, [rax+1]
0x18000c412  mov     [rsp+148h+var_C8], rcx
0x18000c41a  mov     eax, 2
0x18000c41f  mul     rcx
0x18000c422  cmovb   rax, r8
0x18000c426  mov     rcx, rax; cb
0x18000c429  call    cs:__imp_CoTaskMemAlloc
0x18000c42f  mov     [rsi+rdi*8], rax
0x18000c433  test    rax, rax
0x18000c436  jz      short loc_18000C3C8
0x18000c438  mov     rcx, [rsp+148h+var_98]
0x18000c440  mov     r8, [rcx+rdi*8]
0x18000c444  mov     r8, [r8]; unsigned __int16 *
0x18000c447  mov     rdx, [rsp+148h+var_C8]; unsigned __int64
0x18000c44f  mov     rcx, rax; unsigned __int16 *
0x18000c452  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c457  mov     edi, eax
0x18000c459  test    eax, eax
0x18000c45b  js      loc_18000C4F9
0x18000c461  inc     r14d
0x18000c464  jmp     short loc_18000C3E7
0x18000c466  mov     rcx, [rsp+148h+var_D8]
0x18000c46b  mov     rax, [rcx]
0x18000c46e  mov     dword ptr [rsp+148h+var_128], 3
0x18000c476  mov     r9, rsi
0x18000c479  mov     r8d, r13d
0x18000c47c  mov     rdx, [rsp+148h+var_B0]
0x18000c484  mov     rax, [rax+20h]
0x18000c488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c48d  mov     edi, eax
0x18000c48f  test    eax, eax
0x18000c491  jz      short loc_18000C49C
0x18000c493  cmp     eax, 1
0x18000c496  jnz     short loc_18000C4F9
0x18000c498  mov     [r15+50h], eax
0x18000c49c  lea     r8, [rsp+148h+var_E8]
0x18000c4a1  mov     r14, [rsp+148h+var_80]
0x18000c4a9  mov     rdx, r14
0x18000c4ac  mov     rcx, [r15+48h]
0x18000c4b0  call    cs:__imp_ServerGetApplicationType
0x18000c4b6  mov     edi, eax
0x18000c4b8  test    eax, eax
0x18000c4ba  js      short loc_18000C4F9
0x18000c4bc  mov     eax, [rsp+148h+var_E8]
0x18000c4c0  mov     [rsp+148h+var_F8], eax
0x18000c4c4  mov     rcx, [rsp+148h+var_D8]
0x18000c4c9  mov     rax, [rcx]
0x18000c4cc  lea     rdx, [rsp+148h+var_F8]
0x18000c4d1  mov     [rsp+148h+var_110], rdx
0x18000c4d6  mov     [rsp+148h+var_118], rbx
0x18000c4db  mov     [rsp+148h+var_120], rbx
0x18000c4e0  mov     [rsp+148h+var_128], rbx
0x18000c4e5  xor     r9d, r9d
0x18000c4e8  xor     r8d, r8d
0x18000c4eb  mov     rdx, r14
0x18000c4ee  mov     rax, [rax+28h]
0x18000c4f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4f7  mov     edi, eax
0x18000c4f9  mov     rcx, [rsp+148h+var_D8]
0x18000c4fe  test    rcx, rcx
0x18000c501  jz      short loc_18000C514
0x18000c503  mov     rax, [rcx]
0x18000c506  mov     rax, [rax+10h]
0x18000c50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c50f  mov     [rsp+148h+var_D8], rbx
0x18000c514  test    rsi, rsi
0x18000c517  jz      loc_18000C749
0x18000c51d  mov     r14d, ebx
0x18000c520  mov     r15d, r14d
0x18000c523  mov     rcx, [rsi+r15*8]; pv
0x18000c527  test    rcx, rcx
0x18000c52a  jz      short loc_18000C536
0x18000c52c  call    cs:__imp_CoTaskMemFree
0x18000c532  mov     [rsi+r15*8], rbx
0x18000c536  inc     r14d
0x18000c539  cmp     r14d, r13d
0x18000c53c  jl      short loc_18000C520
0x18000c53e  mov     rcx, rsi; pv
0x18000c541  call    cs:__imp_CoTaskMemFree
0x18000c547  jmp     loc_18000C749
0x18000c54c  mov     rax, [rax+78h]
0x18000c550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c555  mov     edi, eax
0x18000c557  test    eax, eax
0x18000c559  jnz     loc_18000C749
  ... truncated ...
```
