# CMsiServices::WriteLineToIni(IMsiPath *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1801be090`
- end: `0x1801be5ea`
- name: `?WriteLineToIni@CMsiServices@@IEAAPEAVIMsiRecord@@PEAVIMsiPath@@PEBG111@Z`
- size: `1370`
- prototype: `struct IMsiRecord *(CMsiServices *__hidden this, struct IMsiPath *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1801bdc90`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x180013d64`
- `0x180013fe4`
- `0x180014f18`
- `0x180016154`
- `0x18001bbf0`
- `0x180077470`
- `0x18008c93c`
- `0x1800c08f8`
- `0x1800c6b30`
- `0x18013fa30`
- `0x18014676c`
- `0x180153e68`
- `0x1801bd55c`
- `0x1801be090`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801be3ac`
- `KERNEL32!GetLastError` at `0x1801be4be`
- `KERNEL32!GetLastError` at `0x1801be3ac`
- `KERNEL32!GetLastError` at `0x1801be4be`
- `KERNEL32!lstrcmpiW` at `0x1801be0ef`
- `KERNEL32!lstrcmpiW` at `0x1801be0ef`
- `KERNEL32!WriteProfileStringW` at `0x1801be355`
- `KERNEL32!WriteProfileStringW` at `0x1801be46a`
- `KERNEL32!WriteProfileStringW` at `0x1801be355`
- `KERNEL32!WriteProfileStringW` at `0x1801be46a`
- `KERNEL32!WritePrivateProfileStringW` at `0x1801be390`
- `KERNEL32!WritePrivateProfileStringW` at `0x1801be4a2`
- `KERNEL32!WritePrivateProfileStringW` at `0x1801be56e`
- `KERNEL32!WritePrivateProfileStringW` at `0x1801be390`
- `KERNEL32!WritePrivateProfileStringW` at `0x1801be4a2`
- `KERNEL32!WritePrivateProfileStringW` at `0x1801be56e`
- `USER32!PostMessageW` at `0x1801be3df`
- `USER32!PostMessageW` at `0x1801be4fd`
- `USER32!PostMessageW` at `0x1801be3df`
- `USER32!PostMessageW` at `0x1801be4fd`

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
  bool ImpersonationFromPath; // bl
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
    CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>(&v38, 260);
    if ( !v38 )
    {
      v11 = PostError(2346);
      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&v38);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v33);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
      return v11;
    }
    MsiGetWindowsDirectory(v38, v39);
    v13 = *(__int64 (__fastcall **)(CMsiServices *, unsigned __int16 *, __int64))(*(_QWORD *)this + 120LL);
    v14 = CComPointer<IEnumMsiRecord>::operator=(&v33);
    v11 = (struct IMsiRecord *)v13(this, v38, v14);
    if ( v11 )
    {
      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&v38);
LABEL_9:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v33);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
      return v11;
    }
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&v38);
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
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v33);
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
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&v40);
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
        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&v40);
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
    CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&v40);
  }
LABEL_48:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v33);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
  return 0;
}

```

## disassembly

```asm
0x1801be090  push    rbp
0x1801be092  push    rbx
0x1801be093  push    rsi
0x1801be094  push    rdi
0x1801be095  push    r12
0x1801be097  push    r13
0x1801be099  push    r14
0x1801be09b  push    r15
0x1801be09d  lea     rbp, [rsp-78h]
0x1801be0a2  sub     rsp, 178h
0x1801be0a9  mov     rax, cs:__security_cookie
0x1801be0b0  xor     rax, rsp
0x1801be0b3  mov     [rbp+0B0h+var_50], rax
0x1801be0b7  mov     rax, [rbp+0B0h+arg_20]
0x1801be0be  mov     r14, rdx
0x1801be0c1  mov     r12, [rbp+0B0h+lpString]
0x1801be0c8  mov     rdi, rcx
0x1801be0cb  mov     rdx, r8; unsigned __int16 *
0x1801be0ce  mov     [rsp+1B0h+lpKeyName], rax
0x1801be0d3  lea     rcx, [rsp+1B0h+var_170]; this
0x1801be0d8  mov     r13, r9
0x1801be0db  mov     r15, r8
0x1801be0de  xor     esi, esi
0x1801be0e0  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801be0e5  lea     rdx, aWinIni; "WIN.INI"
0x1801be0ec  mov     rcx, r15; lpString1
0x1801be0ef  call    cs:__imp_lstrcmpiW
0x1801be0f6  nop     dword ptr [rax+rax+00h]
0x1801be0fb  lea     ecx, [rsi+1]
0x1801be0fe  test    eax, eax
0x1801be100  jnz     short loc_1801BE108
0x1801be102  test    r14, r14
0x1801be105  cmovz   esi, ecx
0x1801be108  mov     [rsp+1B0h+var_168], r14
0x1801be10d  test    r14, r14
0x1801be110  jnz     loc_1801BE1CA
0x1801be116  mov     edx, 104h
0x1801be11b  lea     rcx, [rsp+1B0h+var_148]
0x1801be120  call    ??0?$CTempBuffer@G$00@@QEAA@H@Z; CTempBuffer<ushort,1>::CTempBuffer<ushort,1>(int)
0x1801be125  mov     rcx, [rsp+1B0h+var_148]; unsigned __int16 *
0x1801be12a  test    rcx, rcx
0x1801be12d  jnz     short loc_1801BE16C
0x1801be12f  mov     ecx, 92Ah; int
0x1801be134  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x1801be139  lea     rcx, [rsp+1B0h+var_148]
0x1801be13e  mov     rbx, rax
0x1801be141  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x1801be146  lea     rcx, [rsp+1B0h+var_168]
0x1801be14b  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801be150  mov     rdx, [rsp+1B0h+var_170]
0x1801be155  mov     rcx, [rdx]
0x1801be158  mov     rax, [rcx+10h]
0x1801be15c  mov     rcx, rdx
0x1801be15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be164  mov     rax, rbx
0x1801be167  jmp     loc_1801BE5C9
0x1801be16c  mov     edx, [rsp+1B0h+var_140]; unsigned int
0x1801be170  call    ?MsiGetWindowsDirectory@@YAIPEAGI@Z; MsiGetWindowsDirectory(ushort *,uint)
0x1801be175  mov     rax, [rdi]
0x1801be178  lea     rcx, [rsp+1B0h+var_168]
0x1801be17d  mov     rbx, [rax+78h]
0x1801be181  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1801be186  mov     rdx, [rsp+1B0h+var_148]
0x1801be18b  mov     r8, rax
0x1801be18e  mov     rax, rbx
0x1801be191  mov     rcx, rdi
0x1801be194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be199  lea     rcx, [rsp+1B0h+var_148]
0x1801be19e  mov     rbx, rax
0x1801be1a1  test    rax, rax
0x1801be1a4  jz      short loc_1801BE1C3
0x1801be1a6  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x1801be1ab  lea     rcx, [rsp+1B0h+var_168]
0x1801be1b0  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801be1b5  mov     rcx, [rsp+1B0h+var_170]
0x1801be1ba  mov     rdx, [rcx]
0x1801be1bd  mov     rax, [rdx+10h]
0x1801be1c1  jmp     short loc_1801BE15F
0x1801be1c3  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x1801be1c8  jmp     short loc_1801BE220
0x1801be1ca  mov     rax, [r14]
0x1801be1cd  mov     rcx, r14
0x1801be1d0  mov     rax, [rax+8]
0x1801be1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be1d9  mov     rdi, [rsp+1B0h+var_168]
0x1801be1de  mov     rcx, [rsp+1B0h+var_170]
0x1801be1e3  mov     rax, [rdi]
0x1801be1e6  mov     rdx, [rcx]
0x1801be1e9  mov     rbx, [rax+88h]
0x1801be1f0  mov     rax, [rdx+10h]
0x1801be1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be1f9  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801be200  mov     rdx, r15
0x1801be203  mov     [rsp+1B0h+var_170], rax
0x1801be208  lea     r8, [rsp+1B0h+var_170]
0x1801be20d  mov     rax, rbx
0x1801be210  mov     rcx, rdi
0x1801be213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be218  mov     rbx, rax
0x1801be21b  test    rax, rax
0x1801be21e  jnz     short loc_1801BE1AB
0x1801be220  mov     rcx, [rsp+1B0h+var_168]
0x1801be225  lea     rdx, [rsp+1B0h+var_160]
0x1801be22a  mov     [rsp+1B0h+var_15C], 0
0x1801be232  mov     [rsp+1B0h+var_160], 0
0x1801be23a  mov     rax, [rcx]
0x1801be23d  mov     rax, [rax+0A0h]
0x1801be244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be249  mov     rbx, rax
0x1801be24c  test    rax, rax
0x1801be24f  jnz     loc_1801BE1AB
0x1801be255  mov     rcx, [rsp+1B0h+var_168]
0x1801be25a  lea     r8, [rsp+1B0h+var_15C]
0x1801be25f  xor     r9d, r9d
0x1801be262  mov     rdx, r15
0x1801be265  mov     rax, [rcx]
0x1801be268  mov     rax, [rax+78h]
0x1801be26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be271  mov     rbx, rax
0x1801be274  test    rax, rax
0x1801be277  jnz     loc_1801BE1AB
0x1801be27d  test    r12, r12
0x1801be280  jz      short loc_1801BE2ED
0x1801be282  cmp     [rsp+1B0h+var_160], eax
0x1801be286  jnz     short loc_1801BE2F8
0x1801be288  mov     rcx, [rsp+1B0h+var_168]
0x1801be28d  mov     rax, [rcx]
0x1801be290  mov     rax, [rax+38h]
0x1801be294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be299  mov     rbx, rax
0x1801be29c  mov     rcx, [rax]
0x1801be29f  mov     rax, [rcx+50h]
0x1801be2a3  mov     rcx, rbx
0x1801be2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be2ab  mov     rdx, rax; unsigned __int16 *
0x1801be2ae  mov     ecx, 94Dh; int
0x1801be2b3  call    ?PostError@@YAPEAVIMsiRecord@@HPEBG@Z; PostError(int,ushort const *)
0x1801be2b8  mov     rcx, [rbx]
0x1801be2bb  mov     rdi, rax
0x1801be2be  mov     rax, [rcx+10h]
0x1801be2c2  mov     rcx, rbx
0x1801be2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be2ca  lea     rcx, [rsp+1B0h+var_168]
0x1801be2cf  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801be2d4  mov     rcx, [rsp+1B0h+var_170]
0x1801be2d9  mov     rdx, [rcx]
0x1801be2dc  mov     rax, [rdx+10h]
0x1801be2e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be2e5  mov     rax, rdi
0x1801be2e8  jmp     loc_1801BE5C9
0x1801be2ed  cmp     [rsp+1B0h+var_15C], 0
0x1801be2f2  jz      loc_1801BE5AC
0x1801be2f8  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x1801be2fd  cmp     eax, 0FFFFFFFFh
0x1801be300  jnz     short loc_1801BE314
0x1801be302  mov     ecx, 5DDh; int
0x1801be307  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x1801be30c  mov     rbx, rax
0x1801be30f  jmp     loc_1801BE1AB
0x1801be314  xor     bl, bl
0x1801be316  mov     edi, 1
0x1801be31b  cmp     eax, edi
0x1801be31d  jnz     short loc_1801BE346
0x1801be31f  test    r14, r14
0x1801be322  jz      short loc_1801BE346
0x1801be324  mov     rcx, [rsp+1B0h+var_170]
0x1801be329  mov     rax, [rcx]
0x1801be32c  mov     rax, [rax+50h]
0x1801be330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be335  mov     rcx, rax; lpFileName
0x1801be338  call    ?GetImpersonationFromPath@@YA_NPEBG@Z; GetImpersonationFromPath(ushort const *)
0x1801be33d  cmp     al, dil
0x1801be340  movzx   ebx, bl
0x1801be343  cmovz   ebx, edi
0x1801be346  cmp     esi, edi
0x1801be348  jnz     short loc_1801BE365
0x1801be34a  mov     rdx, [rsp+1B0h+lpKeyName]; lpKeyName
0x1801be34f  mov     r8, r12; lpString
0x1801be352  mov     rcx, r13; lpAppName
0x1801be355  call    cs:__imp_WriteProfileStringW
0x1801be35c  nop     dword ptr [rax+rax+00h]
0x1801be361  mov     edi, eax
0x1801be363  jmp     short loc_1801BE3A8
0x1801be365  mov     dl, bl; bool
0x1801be367  lea     rcx, [rsp+1B0h+var_158]; this
0x1801be36c  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x1801be371  mov     rcx, [rsp+1B0h+var_170]
0x1801be376  mov     rax, [rcx]
0x1801be379  mov     rax, [rax+50h]
0x1801be37d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be382  mov     rdx, [rsp+1B0h+lpKeyName]; lpKeyName
0x1801be387  mov     r9, rax; lpFileName
0x1801be38a  mov     r8, r12; lpString
0x1801be38d  mov     rcx, r13; lpAppName
0x1801be390  call    cs:__imp_WritePrivateProfileStringW
0x1801be397  nop     dword ptr [rax+rax+00h]
0x1801be39c  lea     rcx, [rsp+1B0h+var_158]; this
0x1801be3a1  mov     edi, eax
0x1801be3a3  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x1801be3a8  test    edi, edi
0x1801be3aa  jnz     short loc_1801BE3CC
0x1801be3ac  call    cs:__imp_GetLastError
0x1801be3b3  nop     dword ptr [rax+rax+00h]
0x1801be3b8  mov     r8, r15; unsigned __int16 *
0x1801be3bb  mov     ecx, 838h; int
0x1801be3c0  mov     edx, eax; int
0x1801be3c2  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x1801be3c7  jmp     loc_1801BE30C
0x1801be3cc  cmp     esi, 1
0x1801be3cf  jnz     short loc_1801BE3EB
0x1801be3d1  xor     r9d, r9d; lParam
0x1801be3d4  lea     edx, [rsi+19h]; Msg
0x1801be3d7  xor     r8d, r8d; wParam
0x1801be3da  mov     ecx, 0FFFFh; hWnd
0x1801be3df  call    cs:__imp_PostMessageW
0x1801be3e6  nop     dword ptr [rax+rax+00h]
0x1801be3eb  test    r12, r12
0x1801be3ee  jnz     loc_1801BE5AC
0x1801be3f4  xor     edx, edx; Val
0x1801be3f6  lea     rcx, [rbp+0B0h+var_120]; void *
0x1801be3fa  mov     r8d, 0C8h; Size
0x1801be400  call    memset_0
0x1801be405  lea     ecx, [r12+64h]
0x1801be40a  mov     r9, r13
0x1801be40d  lea     rax, [rbp+0B0h+var_120]
0x1801be411  mov     [rbp+0B0h+var_128], ecx
0x1801be414  mov     [rbp+0B0h+var_130], rax
0x1801be418  mov     r8, r15
0x1801be41b  lea     rax, [rbp+0B0h+var_130]
0x1801be41f  mov     [rbp+0B0h+var_124], ecx
0x1801be422  mov     [rsp+1B0h+var_180], rax
0x1801be427  mov     rdx, r14
0x1801be42a  mov     [rsp+1B0h+var_188], r12d
0x1801be42f  mov     [rsp+1B0h+var_190], r12
0x1801be434  call    ?ReadLineFromIni@CMsiServices@@IEAAPEAVIMsiRecord@@PEAVIMsiPath@@PEBG11IAEAV?$CTempBufferRef@G@@@Z; CMsiServices::ReadLineFromIni(IMsiPath *,ushort const *,ushort const *,ushort const *,uint,CTempBufferRef<ushort> &)
0x1801be439  mov     rdi, rax
0x1801be43c  test    rax, rax
0x1801be43f  jz      short loc_1801BE44F
0x1801be441  lea     rcx, [rbp+0B0h+var_130]
0x1801be445  call    ??1?$CTempBuffer@G$0GE@@@QEAA@XZ; CTempBuffer<ushort,100>::~CTempBuffer<ushort,100>(void)
0x1801be44a  jmp     loc_1801BE2CA
0x1801be44f  mov     rax, [rbp+0B0h+var_130]
0x1801be453  cmp     r12w, [rax]
0x1801be457  jnz     loc_1801BE5A3
0x1801be45d  cmp     esi, 1
0x1801be460  jnz     short loc_1801BE47A
0x1801be462  xor     r8d, r8d; lpString
0x1801be465  xor     edx, edx; lpKeyName
0x1801be467  mov     rcx, r13; lpAppName
0x1801be46a  call    cs:__imp_WriteProfileStringW
0x1801be471  nop     dword ptr [rax+rax+00h]
0x1801be476  mov     edi, eax
0x1801be478  jmp     short loc_1801BE4BA
0x1801be47a  mov     dl, bl; bool
0x1801be47c  lea     rcx, [rsp+1B0h+var_158]; this
0x1801be481  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x1801be486  mov     rcx, [rsp+1B0h+var_170]
0x1801be48b  mov     rax, [rcx]
0x1801be48e  mov     rax, [rax+50h]
0x1801be492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be497  mov     r9, rax; lpFileName
0x1801be49a  xor     r8d, r8d; lpString
0x1801be49d  xor     edx, edx; lpKeyName
0x1801be49f  mov     rcx, r13; lpAppName
0x1801be4a2  call    cs:__imp_WritePrivateProfileStringW
0x1801be4a9  nop     dword ptr [rax+rax+00h]
0x1801be4ae  lea     rcx, [rsp+1B0h+var_158]; this
0x1801be4b3  mov     edi, eax
0x1801be4b5  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x1801be4ba  test    edi, edi
0x1801be4bc  jnz     short loc_1801BE4EA
0x1801be4be  call    cs:__imp_GetLastError
0x1801be4c5  nop     dword ptr [rax+rax+00h]
0x1801be4ca  mov     r8, r15; unsigned __int16 *
0x1801be4cd  mov     ecx, 838h; int
0x1801be4d2  mov     edx, eax; int
0x1801be4d4  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x1801be4d9  mov     rbx, rax
0x1801be4dc  lea     rcx, [rbp+0B0h+var_130]
0x1801be4e0  call    ??1?$CTempBuffer@G$0GE@@@QEAA@XZ; CTempBuffer<ushort,100>::~CTempBuffer<ushort,100>(void)
0x1801be4e5  jmp     loc_1801BE1AB
0x1801be4ea  cmp     esi, 1
0x1801be4ed  jnz     short loc_1801BE509
0x1801be4ef  xor     r9d, r9d; lParam
0x1801be4f2  lea     edx, [rsi+19h]; Msg
0x1801be4f5  xor     r8d, r8d; wParam
0x1801be4f8  mov     ecx, 0FFFFh; hWnd
0x1801be4fd  call    cs:__imp_PostMessageW
0x1801be504  nop     dword ptr [rax+rax+00h]
0x1801be509  lea     rax, [rbp+0B0h+var_130]
0x1801be50d  mov     [rbp+0B0h+var_124], 64h ; 'd'
0x1801be514  mov     [rsp+1B0h+var_180], rax
0x1801be519  xor     r9d, r9d
0x1801be51c  mov     [rsp+1B0h+var_188], r12d
0x1801be521  mov     r8, r15
0x1801be524  mov     rdx, r14
0x1801be527  mov     [rsp+1B0h+var_190], r12
0x1801be52c  call    ?ReadLineFromIni@CMsiServices@@IEAAPEAVIMsiRecord@@PEAVIMsiPath@@PEBG11IAEAV?$CTempBufferRef@G@@@Z; CMsiServices::ReadLineFromIni(IMsiPath *,ushort const *,ushort const *,ushort const *,uint,CTempBufferRef<ushort> &)
0x1801be531  mov     rdi, rax
0x1801be534  test    rax, rax
  ... truncated ...
```
