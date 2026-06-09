# CMsiServices::WriteLineToIni(IMsiPath *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1801b6220`
- end: `0x1801b673d`
- name: `?WriteLineToIni@CMsiServices@@IEAAPEAVIMsiRecord@@PEAVIMsiPath@@PEBG111@Z`
- size: `1309`
- prototype: `struct IMsiRecord *(CMsiServices *__hidden this, struct IMsiPath *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1801b5e20`

## callees

- `0x180024f9c`
- `0x180026ffc`
- `0x180035a8c`
- `0x18004295c`
- `0x180063fc8`
- `0x180064b4c`
- `0x180064f18`
- `0x180066074`
- `0x180079dd0`
- `0x180085db8`
- `0x1800b8034`
- `0x18013a830`
- `0x18014148c`
- `0x18014e4d4`
- `0x1801b5718`
- `0x1801b6220`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801b652a`
- `KERNEL32!GetLastError` at `0x1801b6624`
- `KERNEL32!GetLastError` at `0x1801b652a`
- `KERNEL32!GetLastError` at `0x1801b6624`
- `KERNEL32!lstrcmpiW` at `0x1801b627f`
- `KERNEL32!lstrcmpiW` at `0x1801b627f`
- `KERNEL32!WriteProfileStringW` at `0x1801b64df`
- `KERNEL32!WriteProfileStringW` at `0x1801b65dc`
- `KERNEL32!WriteProfileStringW` at `0x1801b64df`
- `KERNEL32!WriteProfileStringW` at `0x1801b65dc`
- `KERNEL32!WritePrivateProfileStringW` at `0x1801b6514`
- `KERNEL32!WritePrivateProfileStringW` at `0x1801b660e`
- `KERNEL32!WritePrivateProfileStringW` at `0x1801b66c8`
- `KERNEL32!WritePrivateProfileStringW` at `0x1801b6514`
- `KERNEL32!WritePrivateProfileStringW` at `0x1801b660e`
- `KERNEL32!WritePrivateProfileStringW` at `0x1801b66c8`
- `USER32!PostMessageW` at `0x1801b6557`
- `USER32!PostMessageW` at `0x1801b665d`
- `USER32!PostMessageW` at `0x1801b6557`
- `USER32!PostMessageW` at `0x1801b665d`

## pseudocode

```c
struct IMsiRecord *__fastcall CMsiServices::WriteLineToIni(
        CMsiServices *this,
        struct IMsiPath *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *lpString)
{
  BOOL v10; // esi
  struct IMsiRecord *v11; // rbx
  __int64 (__fastcall *v13)(CMsiServices *, unsigned __int16 *, __int64); // rbx
  __int64 v14; // rax
  struct IMsiPath *v15; // rdi
  __int64 (__fastcall *v16)(struct IMsiPath *, const unsigned __int16 *, void **); // rbx
  __int64 v17; // rbx
  const unsigned __int16 *v18; // rax
  struct IMsiRecord *v19; // rdi
  int v20; // eax
  struct IMsiRecord *v21; // rax
  char ImpersonationFromPath; // bl
  const WCHAR *v23; // rax
  BOOL v24; // edi
  const WCHAR *v25; // rax
  DWORD LastError; // eax
  __int64 v27; // rcx
  BOOL v28; // edi
  const WCHAR *v29; // rax
  DWORD v30; // eax
  const WCHAR *v31; // rax
  void *v32; // [rsp+40h] [rbp-C0h] BYREF
  struct IMsiPath *v33; // [rsp+48h] [rbp-B8h] BYREF
  int v34; // [rsp+50h] [rbp-B0h] BYREF
  int v35; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v36[8]; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpKeyName; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v38; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v39; // [rsp+70h] [rbp-90h]
  _WORD *v40; // [rsp+80h] [rbp-80h] BYREF
  int v41; // [rsp+88h] [rbp-78h]
  int v42; // [rsp+8Ch] [rbp-74h]
  _BYTE v43[208]; // [rsp+90h] [rbp-70h] BYREF

  lpKeyName = a5;
  v10 = 0;
  MsiString::MsiString((MsiString *)&v32, a3);
  if ( !lstrcmpiW(a3, L"WIN.INI") )
    v10 = a2 == 0;
  v33 = a2;
  if ( a2 )
  {
    (*(void (__fastcall **)(struct IMsiPath *))(*(_QWORD *)a2 + 8LL))(a2);
    v15 = v33;
    v16 = *(__int64 (__fastcall **)(struct IMsiPath *, const unsigned __int16 *, void **))(*(_QWORD *)v33 + 136LL);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = &MsiString::s_NullString;
    v11 = (struct IMsiRecord *)v16(v15, a3, &v32);
    if ( v11 )
      goto LABEL_9;
  }
  else
  {
    CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>((__int64)&v38, 260);
    if ( !v38 )
    {
      v11 = PostError(2346);
      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&v38);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v33);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
      return v11;
    }
    MsiGetWindowsDirectory(v38, v39);
    v13 = *(__int64 (__fastcall **)(CMsiServices *, unsigned __int16 *, __int64))(*(_QWORD *)this + 120LL);
    v14 = CComPointer<IEnumMsiRecord>::operator=(&v33);
    v11 = (struct IMsiRecord *)v13(this, v38, v14);
    if ( v11 )
    {
      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&v38);
LABEL_9:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v33);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
      return v11;
    }
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&v38);
  }
  v35 = 0;
  v34 = 0;
  v11 = (struct IMsiRecord *)(*(__int64 (__fastcall **)(struct IMsiPath *, int *))(*(_QWORD *)v33 + 160LL))(v33, &v34);
  if ( v11 )
    goto LABEL_9;
  v11 = (struct IMsiRecord *)(*(__int64 (__fastcall **)(struct IMsiPath *, const unsigned __int16 *, int *, _QWORD))(*(_QWORD *)v33 + 120LL))(
                               v33,
                               a3,
                               &v35,
                               0);
  if ( v11 )
    goto LABEL_9;
  if ( lpString )
  {
    if ( !v34 )
    {
      v17 = (*(__int64 (__fastcall **)(struct IMsiPath *))(*(_QWORD *)v33 + 56LL))(v33);
      v18 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 80LL))(v17);
      v19 = PostError(2381, v18);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
LABEL_17:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v33);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
      return v19;
    }
  }
  else if ( !v35 )
  {
    goto LABEL_48;
  }
  v20 = RunningAsLocalSystem();
  if ( v20 == -1 )
  {
    v21 = PostError(1501);
LABEL_21:
    v11 = v21;
    goto LABEL_9;
  }
  ImpersonationFromPath = 0;
  if ( v20 == 1 && a2 )
  {
    v23 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v32 + 80LL))(v32);
    ImpersonationFromPath = GetImpersonationFromPath(v23);
  }
  if ( v10 )
  {
    v24 = WriteProfileStringW(a4, lpKeyName, lpString);
  }
  else
  {
    CImpersonate::CImpersonate((CImpersonate *)v36, ImpersonationFromPath);
    v25 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v32 + 80LL))(v32);
    v24 = WritePrivateProfileStringW(a4, lpKeyName, lpString, v25);
    CImpersonate::~CImpersonate((CImpersonate *)v36);
  }
  if ( !v24 )
  {
    LastError = GetLastError();
    v21 = PostError(2104, LastError, a3);
    goto LABEL_21;
  }
  if ( v10 )
    PostMessageW(HWND_BROADCAST, 0x1Au, 0, 0);
  if ( !lpString )
  {
    memset_0(v43, 0, 0xC8u);
    v41 = 100;
    v40 = v43;
    v42 = 100;
    v19 = (struct IMsiRecord *)CMsiServices::ReadLineFromIni(100, a2, a3, a4, 0, 0, &v40);
    if ( v19 )
    {
LABEL_34:
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&v40);
      goto LABEL_17;
    }
    if ( !*v40 )
    {
      if ( v10 )
      {
        v28 = WriteProfileStringW(a4, 0, 0);
      }
      else
      {
        CImpersonate::CImpersonate((CImpersonate *)v36, ImpersonationFromPath);
        v29 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v32 + 80LL))(v32);
        v28 = WritePrivateProfileStringW(a4, 0, 0, v29);
        CImpersonate::~CImpersonate((CImpersonate *)v36);
      }
      if ( !v28 )
      {
        v30 = GetLastError();
        v11 = PostError(2104, v30, a3);
LABEL_41:
        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&v40);
        goto LABEL_9;
      }
      if ( v10 )
        PostMessageW(HWND_BROADCAST, 0x1Au, 0, 0);
      v42 = 100;
      v19 = (struct IMsiRecord *)CMsiServices::ReadLineFromIni(v27, a2, a3, 0, 0, 0, &v40);
      if ( v19 )
        goto LABEL_34;
      if ( !*v40 )
      {
        CImpersonate::CImpersonate((CImpersonate *)v36, ImpersonationFromPath);
        v31 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v32 + 80LL))(v32);
        WritePrivateProfileStringW(0, 0, 0, v31);
        v11 = (struct IMsiRecord *)(*(__int64 (__fastcall **)(struct IMsiPath *, const unsigned __int16 *))(*(_QWORD *)v33 + 192LL))(
                                     v33,
                                     a3);
        CImpersonate::~CImpersonate((CImpersonate *)v36);
        goto LABEL_41;
      }
    }
    CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&v40);
  }
LABEL_48:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v33);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
  return 0;
}

```

## disassembly

```asm
0x1801b6220  push    rbp
0x1801b6222  push    rbx
0x1801b6223  push    rsi
0x1801b6224  push    rdi
0x1801b6225  push    r12
0x1801b6227  push    r13
0x1801b6229  push    r14
0x1801b622b  push    r15
0x1801b622d  lea     rbp, [rsp-78h]
0x1801b6232  sub     rsp, 178h
0x1801b6239  mov     rax, cs:__security_cookie
0x1801b6240  xor     rax, rsp
0x1801b6243  mov     [rbp+0B0h+var_50], rax
0x1801b6247  mov     rax, [rbp+0B0h+arg_20]
0x1801b624e  mov     r14, rdx
0x1801b6251  mov     r12, [rbp+0B0h+lpString]
0x1801b6258  mov     rdi, rcx
0x1801b625b  mov     rdx, r8; unsigned __int16 *
0x1801b625e  mov     [rsp+1B0h+lpKeyName], rax
0x1801b6263  lea     rcx, [rsp+1B0h+var_170]; this
0x1801b6268  mov     r13, r9
0x1801b626b  mov     r15, r8
0x1801b626e  xor     esi, esi
0x1801b6270  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801b6275  lea     rdx, aWinIni; "WIN.INI"
0x1801b627c  mov     rcx, r15; lpString1
0x1801b627f  call    cs:__imp_lstrcmpiW
0x1801b6285  lea     ecx, [rsi+1]
0x1801b6288  test    eax, eax
0x1801b628a  jnz     short loc_1801B6292
0x1801b628c  test    r14, r14
0x1801b628f  cmovz   esi, ecx
0x1801b6292  mov     [rsp+1B0h+var_168], r14
0x1801b6297  test    r14, r14
0x1801b629a  jnz     loc_1801B6354
0x1801b62a0  mov     edx, 104h
0x1801b62a5  lea     rcx, [rsp+1B0h+var_148]
0x1801b62aa  call    ??0?$CTempBuffer@G$00@@QEAA@H@Z; CTempBuffer<ushort,1>::CTempBuffer<ushort,1>(int)
0x1801b62af  mov     rcx, [rsp+1B0h+var_148]; unsigned __int16 *
0x1801b62b4  test    rcx, rcx
0x1801b62b7  jnz     short loc_1801B62F6
0x1801b62b9  mov     ecx, 92Ah; int
0x1801b62be  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x1801b62c3  lea     rcx, [rsp+1B0h+var_148]
0x1801b62c8  mov     rbx, rax
0x1801b62cb  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x1801b62d0  lea     rcx, [rsp+1B0h+var_168]
0x1801b62d5  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801b62da  mov     rdx, [rsp+1B0h+var_170]
0x1801b62df  mov     rcx, [rdx]
0x1801b62e2  mov     rax, [rcx+10h]
0x1801b62e6  mov     rcx, rdx
0x1801b62e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b62ee  mov     rax, rbx
0x1801b62f1  jmp     loc_1801B671D
0x1801b62f6  mov     edx, [rsp+1B0h+var_140]; unsigned int
0x1801b62fa  call    ?MsiGetWindowsDirectory@@YAIPEAGI@Z; MsiGetWindowsDirectory(ushort *,uint)
0x1801b62ff  mov     rax, [rdi]
0x1801b6302  lea     rcx, [rsp+1B0h+var_168]
0x1801b6307  mov     rbx, [rax+78h]
0x1801b630b  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1801b6310  mov     rdx, [rsp+1B0h+var_148]
0x1801b6315  mov     r8, rax
0x1801b6318  mov     rax, rbx
0x1801b631b  mov     rcx, rdi
0x1801b631e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6323  lea     rcx, [rsp+1B0h+var_148]
0x1801b6328  mov     rbx, rax
0x1801b632b  test    rax, rax
0x1801b632e  jz      short loc_1801B634D
0x1801b6330  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x1801b6335  lea     rcx, [rsp+1B0h+var_168]
0x1801b633a  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801b633f  mov     rcx, [rsp+1B0h+var_170]
0x1801b6344  mov     rdx, [rcx]
0x1801b6347  mov     rax, [rdx+10h]
0x1801b634b  jmp     short loc_1801B62E9
0x1801b634d  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x1801b6352  jmp     short loc_1801B63AA
0x1801b6354  mov     rax, [r14]
0x1801b6357  mov     rcx, r14
0x1801b635a  mov     rax, [rax+8]
0x1801b635e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6363  mov     rdi, [rsp+1B0h+var_168]
0x1801b6368  mov     rcx, [rsp+1B0h+var_170]
0x1801b636d  mov     rax, [rdi]
0x1801b6370  mov     rdx, [rcx]
0x1801b6373  mov     rbx, [rax+88h]
0x1801b637a  mov     rax, [rdx+10h]
0x1801b637e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6383  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801b638a  mov     rdx, r15
0x1801b638d  mov     [rsp+1B0h+var_170], rax
0x1801b6392  lea     r8, [rsp+1B0h+var_170]
0x1801b6397  mov     rax, rbx
0x1801b639a  mov     rcx, rdi
0x1801b639d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b63a2  mov     rbx, rax
0x1801b63a5  test    rax, rax
0x1801b63a8  jnz     short loc_1801B6335
0x1801b63aa  mov     rcx, [rsp+1B0h+var_168]
0x1801b63af  lea     rdx, [rsp+1B0h+var_160]
0x1801b63b4  mov     [rsp+1B0h+var_15C], 0
0x1801b63bc  mov     [rsp+1B0h+var_160], 0
0x1801b63c4  mov     rax, [rcx]
0x1801b63c7  mov     rax, [rax+0A0h]
0x1801b63ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b63d3  mov     rbx, rax
0x1801b63d6  test    rax, rax
0x1801b63d9  jnz     loc_1801B6335
0x1801b63df  mov     rcx, [rsp+1B0h+var_168]
0x1801b63e4  lea     r8, [rsp+1B0h+var_15C]
0x1801b63e9  xor     r9d, r9d
0x1801b63ec  mov     rdx, r15
0x1801b63ef  mov     rax, [rcx]
0x1801b63f2  mov     rax, [rax+78h]
0x1801b63f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b63fb  mov     rbx, rax
0x1801b63fe  test    rax, rax
0x1801b6401  jnz     loc_1801B6335
0x1801b6407  test    r12, r12
0x1801b640a  jz      short loc_1801B6477
0x1801b640c  cmp     [rsp+1B0h+var_160], eax
0x1801b6410  jnz     short loc_1801B6482
0x1801b6412  mov     rcx, [rsp+1B0h+var_168]
0x1801b6417  mov     rax, [rcx]
0x1801b641a  mov     rax, [rax+38h]
0x1801b641e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6423  mov     rbx, rax
0x1801b6426  mov     rcx, [rax]
0x1801b6429  mov     rax, [rcx+50h]
0x1801b642d  mov     rcx, rbx
0x1801b6430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6435  mov     rdx, rax; unsigned __int16 *
0x1801b6438  mov     ecx, 94Dh; int
0x1801b643d  call    ?PostError@@YAPEAVIMsiRecord@@HPEBG@Z; PostError(int,ushort const *)
0x1801b6442  mov     rcx, [rbx]
0x1801b6445  mov     rdi, rax
0x1801b6448  mov     rax, [rcx+10h]
0x1801b644c  mov     rcx, rbx
0x1801b644f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6454  lea     rcx, [rsp+1B0h+var_168]
0x1801b6459  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801b645e  mov     rcx, [rsp+1B0h+var_170]
0x1801b6463  mov     rdx, [rcx]
0x1801b6466  mov     rax, [rdx+10h]
0x1801b646a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b646f  mov     rax, rdi
0x1801b6472  jmp     loc_1801B671D
0x1801b6477  cmp     [rsp+1B0h+var_15C], 0
0x1801b647c  jz      loc_1801B6700
0x1801b6482  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x1801b6487  cmp     eax, 0FFFFFFFFh
0x1801b648a  jnz     short loc_1801B649E
0x1801b648c  mov     ecx, 5DDh; int
0x1801b6491  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x1801b6496  mov     rbx, rax
0x1801b6499  jmp     loc_1801B6335
0x1801b649e  xor     bl, bl
0x1801b64a0  mov     edi, 1
0x1801b64a5  cmp     eax, edi
0x1801b64a7  jnz     short loc_1801B64D0
0x1801b64a9  test    r14, r14
0x1801b64ac  jz      short loc_1801B64D0
0x1801b64ae  mov     rcx, [rsp+1B0h+var_170]
0x1801b64b3  mov     rax, [rcx]
0x1801b64b6  mov     rax, [rax+50h]
0x1801b64ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b64bf  mov     rcx, rax; lpFileName
0x1801b64c2  call    ?GetImpersonationFromPath@@YA_NPEBG@Z; GetImpersonationFromPath(ushort const *)
0x1801b64c7  cmp     al, dil
0x1801b64ca  movzx   ebx, bl
0x1801b64cd  cmovz   ebx, edi
0x1801b64d0  cmp     esi, edi
0x1801b64d2  jnz     short loc_1801B64E9
0x1801b64d4  mov     rdx, [rsp+1B0h+lpKeyName]; lpKeyName
0x1801b64d9  mov     r8, r12; lpString
0x1801b64dc  mov     rcx, r13; lpAppName
0x1801b64df  call    cs:__imp_WriteProfileStringW
0x1801b64e5  mov     edi, eax
0x1801b64e7  jmp     short loc_1801B6526
0x1801b64e9  mov     dl, bl; bool
0x1801b64eb  lea     rcx, [rsp+1B0h+var_158]; this
0x1801b64f0  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x1801b64f5  mov     rcx, [rsp+1B0h+var_170]
0x1801b64fa  mov     rax, [rcx]
0x1801b64fd  mov     rax, [rax+50h]
0x1801b6501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6506  mov     rdx, [rsp+1B0h+lpKeyName]; lpKeyName
0x1801b650b  mov     r9, rax; lpFileName
0x1801b650e  mov     r8, r12; lpString
0x1801b6511  mov     rcx, r13; lpAppName
0x1801b6514  call    cs:__imp_WritePrivateProfileStringW
0x1801b651a  lea     rcx, [rsp+1B0h+var_158]; this
0x1801b651f  mov     edi, eax
0x1801b6521  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x1801b6526  test    edi, edi
0x1801b6528  jnz     short loc_1801B6544
0x1801b652a  call    cs:__imp_GetLastError
0x1801b6530  mov     r8, r15; unsigned __int16 *
0x1801b6533  mov     ecx, 838h; int
0x1801b6538  mov     edx, eax; int
0x1801b653a  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x1801b653f  jmp     loc_1801B6496
0x1801b6544  cmp     esi, 1
0x1801b6547  jnz     short loc_1801B655D
0x1801b6549  xor     r9d, r9d; lParam
0x1801b654c  lea     edx, [rsi+19h]; Msg
0x1801b654f  xor     r8d, r8d; wParam
0x1801b6552  mov     ecx, 0FFFFh; hWnd
0x1801b6557  call    cs:__imp_PostMessageW
0x1801b655d  test    r12, r12
0x1801b6560  jnz     loc_1801B6700
0x1801b6566  xor     edx, edx; Val
0x1801b6568  lea     rcx, [rbp+0B0h+var_120]; void *
0x1801b656c  mov     r8d, 0C8h; Size
0x1801b6572  call    memset_0
0x1801b6577  lea     ecx, [r12+64h]
0x1801b657c  mov     r9, r13
0x1801b657f  lea     rax, [rbp+0B0h+var_120]
0x1801b6583  mov     [rbp+0B0h+var_128], ecx
0x1801b6586  mov     [rbp+0B0h+var_130], rax
0x1801b658a  mov     r8, r15
0x1801b658d  lea     rax, [rbp+0B0h+var_130]
0x1801b6591  mov     [rbp+0B0h+var_124], ecx
0x1801b6594  mov     [rsp+1B0h+var_180], rax
0x1801b6599  mov     rdx, r14
0x1801b659c  mov     [rsp+1B0h+var_188], r12d
0x1801b65a1  mov     [rsp+1B0h+var_190], r12
0x1801b65a6  call    ?ReadLineFromIni@CMsiServices@@IEAAPEAVIMsiRecord@@PEAVIMsiPath@@PEBG11IAEAV?$CTempBufferRef@G@@@Z; CMsiServices::ReadLineFromIni(IMsiPath *,ushort const *,ushort const *,ushort const *,uint,CTempBufferRef<ushort> &)
0x1801b65ab  mov     rdi, rax
0x1801b65ae  test    rax, rax
0x1801b65b1  jz      short loc_1801B65C1
0x1801b65b3  lea     rcx, [rbp+0B0h+var_130]
0x1801b65b7  call    ??1?$CTempBuffer@G$0GE@@@QEAA@XZ; CTempBuffer<ushort,100>::~CTempBuffer<ushort,100>(void)
0x1801b65bc  jmp     loc_1801B6454
0x1801b65c1  mov     rax, [rbp+0B0h+var_130]
0x1801b65c5  cmp     r12w, [rax]
0x1801b65c9  jnz     loc_1801B66F7
0x1801b65cf  cmp     esi, 1
0x1801b65d2  jnz     short loc_1801B65E6
0x1801b65d4  xor     r8d, r8d; lpString
0x1801b65d7  xor     edx, edx; lpKeyName
0x1801b65d9  mov     rcx, r13; lpAppName
0x1801b65dc  call    cs:__imp_WriteProfileStringW
0x1801b65e2  mov     edi, eax
0x1801b65e4  jmp     short loc_1801B6620
0x1801b65e6  mov     dl, bl; bool
0x1801b65e8  lea     rcx, [rsp+1B0h+var_158]; this
0x1801b65ed  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x1801b65f2  mov     rcx, [rsp+1B0h+var_170]
0x1801b65f7  mov     rax, [rcx]
0x1801b65fa  mov     rax, [rax+50h]
0x1801b65fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6603  mov     r9, rax; lpFileName
0x1801b6606  xor     r8d, r8d; lpString
0x1801b6609  xor     edx, edx; lpKeyName
0x1801b660b  mov     rcx, r13; lpAppName
0x1801b660e  call    cs:__imp_WritePrivateProfileStringW
0x1801b6614  lea     rcx, [rsp+1B0h+var_158]; this
0x1801b6619  mov     edi, eax
0x1801b661b  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x1801b6620  test    edi, edi
0x1801b6622  jnz     short loc_1801B664A
0x1801b6624  call    cs:__imp_GetLastError
0x1801b662a  mov     r8, r15; unsigned __int16 *
0x1801b662d  mov     ecx, 838h; int
0x1801b6632  mov     edx, eax; int
0x1801b6634  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x1801b6639  mov     rbx, rax
0x1801b663c  lea     rcx, [rbp+0B0h+var_130]
0x1801b6640  call    ??1?$CTempBuffer@G$0GE@@@QEAA@XZ; CTempBuffer<ushort,100>::~CTempBuffer<ushort,100>(void)
0x1801b6645  jmp     loc_1801B6335
0x1801b664a  cmp     esi, 1
0x1801b664d  jnz     short loc_1801B6663
0x1801b664f  xor     r9d, r9d; lParam
0x1801b6652  lea     edx, [rsi+19h]; Msg
0x1801b6655  xor     r8d, r8d; wParam
0x1801b6658  mov     ecx, 0FFFFh; hWnd
0x1801b665d  call    cs:__imp_PostMessageW
0x1801b6663  lea     rax, [rbp+0B0h+var_130]
0x1801b6667  mov     [rbp+0B0h+var_124], 64h ; 'd'
0x1801b666e  mov     [rsp+1B0h+var_180], rax
0x1801b6673  xor     r9d, r9d
0x1801b6676  mov     [rsp+1B0h+var_188], r12d
0x1801b667b  mov     r8, r15
0x1801b667e  mov     rdx, r14
0x1801b6681  mov     [rsp+1B0h+var_190], r12
0x1801b6686  call    ?ReadLineFromIni@CMsiServices@@IEAAPEAVIMsiRecord@@PEAVIMsiPath@@PEBG11IAEAV?$CTempBufferRef@G@@@Z; CMsiServices::ReadLineFromIni(IMsiPath *,ushort const *,ushort const *,ushort const *,uint,CTempBufferRef<ushort> &)
0x1801b668b  mov     rdi, rax
0x1801b668e  test    rax, rax
0x1801b6691  jnz     loc_1801B65B3
0x1801b6697  mov     rax, [rbp+0B0h+var_130]
0x1801b669b  cmp     r12w, [rax]
0x1801b669f  jnz     short loc_1801B66F7
0x1801b66a1  mov     dl, bl; bool
0x1801b66a3  lea     rcx, [rsp+1B0h+var_158]; this
0x1801b66a8  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x1801b66ad  mov     rcx, [rsp+1B0h+var_170]
0x1801b66b2  mov     rax, [rcx]
  ... truncated ...
```
