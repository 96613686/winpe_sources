# GetServerPath(IMsiServices &,bool,bool,IMsiString const * &)

- ea: `0x180148ae8`
- end: `0x18014927f`
- name: `?GetServerPath@@YAPEAVIMsiRecord@@AEAVIMsiServices@@_N1AEAPEBVIMsiString@@@Z`
- size: `1943`
- prototype: `struct IMsiRecord *__fastcall(struct IMsiServices *, bool, bool, const struct IMsiString **)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180092930`
- `0x1801f4f1c`
- `0x180204d20`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x18003c030`
- `0x18004cbfc`
- `0x1800945b0`
- `0x180148ae8`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180148c4a`
- `ADVAPI32!RegQueryValueExW` at `0x180148c4a`
- `ADVAPI32!RegCloseKey` at `0x180148b99`
- `ADVAPI32!RegCloseKey` at `0x180148b99`
- `KERNEL32!InitializeCriticalSection` at `0x180148b73`
- `KERNEL32!InitializeCriticalSection` at `0x180148b73`
- `KERNEL32!LeaveCriticalSection` at `0x180148bbc`
- `KERNEL32!LeaveCriticalSection` at `0x180148bbc`
- `KERNEL32!EnterCriticalSection` at `0x180148b83`
- `KERNEL32!EnterCriticalSection` at `0x180148b83`
- `KERNEL32!GetModuleFileNameW` at `0x180148e57`
- `KERNEL32!GetModuleFileNameW` at `0x180148e57`

## string_xrefs

- `0x180148be9`: `Software\Microsoft\Windows\CurrentVersion\Installer`
- `0x180148c13`: `MsiExecCA32`
- `0x180148c1d`: `MsiExecCA64`
- `0x180148d5b`: `MsiExec.exe`
- `0x180148f35`: `MsiExec.exe`
- `0x180149045`: `MsiExec.exe`
- `0x1801490e8`: `MsiExec.exe`
- `0x1801491a4`: `MsiExec.exe`

## pseudocode

```c
struct IMsiRecord *__fastcall GetServerPath(
        struct IMsiServices *a1,
        char a2,
        unsigned __int8 a3,
        const struct IMsiString **a4)
{
  void *v4; // rdi
  void *v5; // rbx
  int v6; // esi
  const WCHAR *v10; // rdx
  LSTATUS v11; // eax
  __int64 v12; // rax
  __int64 (__fastcall *v13)(struct IMsiServices *, WCHAR *, __int64 **, void **); // rbx
  __int64 v14; // rbx
  __int64 v16; // rax
  __int64 (__fastcall *v17)(struct IMsiServices *, WCHAR *, __int64, void **); // rdi
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(struct IMsiServices *, WCHAR *, __int64); // rsi
  __int64 v21; // rax
  __int64 v22; // rsi
  void *v23; // rsi
  __int64 v24; // r14
  bool v25; // zf
  __int64 *v26; // r15
  __int64 v27; // rax
  __int64 (__fastcall *v28)(__int64 *, const wchar_t *, const struct IMsiString **); // r14
  __int64 v29; // rax
  const struct IMsiString *v30; // rcx
  __int64 *v31; // [rsp+30h] [rbp-D0h] BYREF
  int v32; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  const struct IMsiString *v34; // [rsp+48h] [rbp-B8h] BYREF
  void *v35; // [rsp+50h] [rbp-B0h] BYREF
  void *v36; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 *v38; // [rsp+70h] [rbp-90h]
  int v39; // [rsp+78h] [rbp-88h]
  __int16 v40; // [rsp+80h] [rbp-80h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Data[309]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v43; // [rsp+31Ah] [rbp+21Ah]

  v4 = &MsiString::s_NullString;
  v5 = &MsiString::s_NullString;
  v6 = a3;
  v32 = 0;
  v31 = 0;
  if ( g_fWinNT64 )
  {
    v39 = 1;
    v38 = &v40;
    v40 = 0;
    *(_OWORD *)hKey = 0;
    InitializeCriticalSection(&CriticalSection);
    EnterCriticalSection(&CriticalSection);
    LeaveCriticalSection(&CriticalSection);
    cbData = 131353;
    AdjustREGSAM(&cbData);
    if ( !(unsigned int)((__int64 (__fastcall *)(__int64, const wchar_t *, _QWORD, _QWORD, HKEY *))RegOpenKeyAPI)(
                          -2147483646,
                          L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer",
                          0,
                          cbData,
                          hKey) )
    {
      v10 = L"MsiExecCA64";
      if ( !(_BYTE)v6 )
        v10 = L"MsiExecCA32";
      cbData = 618;
      v11 = RegQueryValueExW(hKey[0], v10, 0, 0, (LPBYTE)Data, &cbData);
      cbData = 618;
      v43 = 0;
      v4 = &MsiString::s_NullString;
      if ( !v11 )
      {
        v12 = *(_QWORD *)a1;
        v35 = &MsiString::s_NullString;
        v13 = *(__int64 (__fastcall **)(struct IMsiServices *, WCHAR *, __int64 **, void **))(v12 + 360);
        (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
        v35 = &MsiString::s_NullString;
        v31 = 0;
        v14 = v13(a1, Data, &v31, &v35);
        if ( v14 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v35 + 16LL))(v35);
          CRegHandle::~CRegHandle((CRegHandle *)hKey);
          (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
          (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
          (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
          if ( v31 )
            (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
          return (struct IMsiRecord *)v14;
        }
        v14 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, int *, _QWORD))(*v31 + 120))(
                v31,
                L"MsiExec.exe",
                &v32,
                0);
        if ( v14 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v35 + 16LL))(v35);
          CRegHandle::~CRegHandle((CRegHandle *)hKey);
          (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
          (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
          (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v31);
          return (struct IMsiRecord *)v14;
        }
        v5 = (void *)(*(__int64 (__fastcall **)(__int64 *))(*v31 + 56))(v31);
        (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v35 + 16LL))(v35);
      }
    }
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
  }
  if ( v32 )
    goto LABEL_31;
  if ( g_fWoW )
  {
    if ( !(_BYTE)v6 )
      goto LABEL_24;
  }
  else if ( (_BYTE)v6 )
  {
    goto LABEL_24;
  }
  if ( GetModuleFileNameW(g_hInstance, Data, 0x104u) )
  {
    v16 = *(_QWORD *)a1;
    v36 = &MsiString::s_NullString;
    v17 = *(__int64 (__fastcall **)(struct IMsiServices *, WCHAR *, __int64, void **))(v16 + 360);
    (*(void (**)(void))(MsiString::s_NullString + 16LL))();
    v36 = &MsiString::s_NullString;
    v18 = CComPointer<IEnumMsiRecord>::operator=(&v31);
    v19 = v17(a1, Data, v18, &v36);
    if ( v19
      || (v19 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, int *, _QWORD))(*v31 + 120))(
                  v31,
                  L"MsiExec.exe",
                  &v32,
                  0)) != 0 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 16LL))(v36);
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v31);
      return (struct IMsiRecord *)v19;
    }
    v4 = (void *)(*(__int64 (__fastcall **)(__int64 *))(*v31 + 56))(v31);
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 16LL))(v36);
  }
LABEL_24:
  if ( v32 )
  {
LABEL_31:
    v23 = &MsiString::s_NullString;
    goto LABEL_32;
  }
  MsiGetSystemDirectory(Data, 0x104u, v6 ^ 1);
  v20 = *(__int64 (__fastcall **)(struct IMsiServices *, WCHAR *, __int64))(*(_QWORD *)a1 + 120LL);
  v21 = CComPointer<IEnumMsiRecord>::operator=(&v31);
  v22 = v20(a1, Data, v21);
  if ( v22
    || (v22 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, int *, _QWORD))(*v31 + 120))(
                v31,
                L"MsiExec.exe",
                &v32,
                0)) != 0 )
  {
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v31);
    return (struct IMsiRecord *)v22;
  }
  v23 = (void *)(*(__int64 (__fastcall **)(__int64 *))(*v31 + 56))(v31);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  if ( !v32 )
  {
    v24 = (*(__int64 (__fastcall **)(struct IMsiServices *, __int64))(*(_QWORD *)a1 + 48LL))(a1, 5);
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v24 + 104LL))(v24, 1, 2605);
    (*(void (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v24 + 128LL))(v24, 2, L"MsiExec.exe");
    (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v24 + 120LL))(v24, 3, v23);
    (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v24 + 120LL))(v24, 4, v4);
    (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v24 + 120LL))(v24, 5, v5);
    goto LABEL_37;
  }
LABEL_32:
  v25 = a2 == 0;
  v26 = v31;
  v34 = (const struct IMsiString *)&MsiString::s_NullString;
  v27 = *v31;
  if ( v25 )
    v28 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, const struct IMsiString **))(v27 + 136);
  else
    v28 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, const struct IMsiString **))(v27 + 432);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  v34 = (const struct IMsiString *)&MsiString::s_NullString;
  v24 = v28(v26, L"MsiExec.exe", &v34);
  v29 = *(_QWORD *)v34;
  if ( !v24 )
  {
    (*(void (**)(void))(v29 + 8))();
    v30 = v34;
    *a4 = v34;
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v30 + 16LL))(v30);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
    v24 = 0;
    goto LABEL_39;
  }
  (*(void (**)(void))(v29 + 16))();
LABEL_37:
  (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
LABEL_39:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v31);
  return (struct IMsiRecord *)v24;
}

```

## disassembly

```asm
0x180148ae8  mov     [rsp-8+arg_8], rbx
0x180148aed  mov     [rsp-8+arg_10], rsi
0x180148af2  push    rbp
0x180148af3  push    rdi
0x180148af4  push    r12
0x180148af6  push    r14
0x180148af8  push    r15
0x180148afa  lea     rbp, [rsp-230h]
0x180148b02  sub     rsp, 330h
0x180148b09  mov     rax, cs:__security_cookie
0x180148b10  xor     rax, rsp
0x180148b13  mov     [rbp+250h+var_30], rax
0x180148b1a  cmp     cs:?g_fWinNT64@@3_NA, 0; bool g_fWinNT64
0x180148b21  lea     rdi, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148b28  mov     rbx, rdi
0x180148b2b  movzx   esi, r8b
0x180148b2f  mov     r12, r9
0x180148b32  mov     [rsp+350h+var_318], 0
0x180148b3a  mov     r15b, dl
0x180148b3d  mov     [rsp+350h+var_320], 0
0x180148b46  mov     r14, rcx
0x180148b49  jz      loc_180148E1E
0x180148b4f  lea     rax, [rbp+250h+var_2D0]
0x180148b53  mov     [rsp+350h+var_2D8], 1
0x180148b5b  mov     [rsp+350h+var_2E0], rax
0x180148b60  lea     rcx, [rbp+250h+CriticalSection]; lpCriticalSection
0x180148b64  xor     eax, eax
0x180148b66  xorps   xmm0, xmm0
0x180148b69  mov     [rbp+250h+var_2D0], ax
0x180148b6d  movdqa  xmmword ptr [rsp+350h+hKey], xmm0
0x180148b73  call    cs:__imp_InitializeCriticalSection
0x180148b7a  nop     dword ptr [rax+rax+00h]
0x180148b7f  lea     rcx, [rbp+250h+CriticalSection]; lpCriticalSection
0x180148b83  call    cs:__imp_EnterCriticalSection
0x180148b8a  nop     dword ptr [rax+rax+00h]
0x180148b8f  mov     rcx, [rsp+350h+hKey]; hKey
0x180148b94  test    rcx, rcx
0x180148b97  jz      short loc_180148BB8
0x180148b99  call    cs:__imp_RegCloseKey
0x180148ba0  nop     dword ptr [rax+rax+00h]
0x180148ba5  mov     rax, [rsp+350h+var_2E0]
0x180148baa  xor     ecx, ecx
0x180148bac  mov     [rsp+350h+hKey], 0
0x180148bb5  mov     [rax], cx
0x180148bb8  lea     rcx, [rbp+250h+CriticalSection]; lpCriticalSection
0x180148bbc  call    cs:__imp_LeaveCriticalSection
0x180148bc3  nop     dword ptr [rax+rax+00h]
0x180148bc8  lea     rcx, [rsp+350h+cbData]; unsigned int *
0x180148bcd  mov     [rsp+350h+cbData], 20119h
0x180148bd5  call    ?AdjustREGSAM@@YAXAEAK@Z; AdjustREGSAM(ulong &)
0x180148bda  mov     r9d, [rsp+350h+cbData]
0x180148bdf  lea     rax, [rsp+350h+hKey]
0x180148be4  mov     [rsp+350h+lpData], rax
0x180148be9  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180148bf0  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180148bf7  xor     r8d, r8d
0x180148bfa  mov     rcx, 0FFFFFFFF80000002h
0x180148c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148c06  test    eax, eax
0x180148c08  jnz     loc_180148E14
0x180148c0e  mov     rcx, [rsp+350h+hKey]; hKey
0x180148c13  lea     rax, aMsiexecca32; "MsiExecCA32"
0x180148c1a  test    sil, sil
0x180148c1d  lea     rdx, aMsiexecca64; "MsiExecCA64"
0x180148c24  mov     edi, 26Ah
0x180148c29  cmovz   rdx, rax; lpValueName
0x180148c2d  mov     [rsp+350h+cbData], edi
0x180148c31  lea     rax, [rsp+350h+cbData]
0x180148c36  xor     r9d, r9d; lpType
0x180148c39  mov     [rsp+350h+lpcbData], rax; lpcbData
0x180148c3e  xor     r8d, r8d; lpReserved
0x180148c41  lea     rax, [rbp+250h+Data]
0x180148c45  mov     [rsp+350h+lpData], rax; lpData
0x180148c4a  call    cs:__imp_RegQueryValueExW
0x180148c51  nop     dword ptr [rax+rax+00h]
0x180148c56  xor     ecx, ecx
0x180148c58  mov     [rsp+350h+cbData], edi
0x180148c5c  mov     [rbp+250h+var_36], cx
0x180148c63  lea     rdi, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148c6a  test    eax, eax
0x180148c6c  jnz     loc_180148E14
0x180148c72  mov     rax, [r14]
0x180148c75  mov     rcx, rdi
0x180148c78  mov     [rsp+350h+var_300], rdi
0x180148c7d  mov     rbx, [rax+168h]
0x180148c84  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148c8b  mov     rax, [rax+10h]
0x180148c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148c94  mov     rcx, [rsp+350h+var_320]
0x180148c99  mov     [rsp+350h+var_300], rdi
0x180148c9e  test    rcx, rcx
0x180148ca1  jz      short loc_180148CAF
0x180148ca3  mov     rdx, [rcx]
0x180148ca6  mov     rax, [rdx+10h]
0x180148caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148caf  lea     r9, [rsp+350h+var_300]
0x180148cb4  mov     [rsp+350h+var_320], 0
0x180148cbd  lea     r8, [rsp+350h+var_320]
0x180148cc2  mov     rcx, r14
0x180148cc5  lea     rdx, [rbp+250h+Data]
0x180148cc9  mov     rax, rbx
0x180148ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148cd1  mov     rbx, rax
0x180148cd4  test    rax, rax
0x180148cd7  jz      short loc_180148D4E
0x180148cd9  mov     rdx, [rsp+350h+var_300]
0x180148cde  mov     rcx, [rdx]
0x180148ce1  mov     rax, [rcx+10h]
0x180148ce5  mov     rcx, rdx
0x180148ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148ced  lea     rcx, [rsp+350h+hKey]; this
0x180148cf2  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180148cf7  mov     rcx, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148cfe  mov     rax, [rcx+10h]
0x180148d02  mov     rcx, rdi
0x180148d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148d0a  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148d11  mov     rcx, rdi
0x180148d14  mov     rax, [rax+10h]
0x180148d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148d1d  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148d24  mov     rcx, rdi
0x180148d27  mov     rax, [rax+10h]
0x180148d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148d30  mov     rcx, [rsp+350h+var_320]
0x180148d35  test    rcx, rcx
0x180148d38  jz      short loc_180148D46
0x180148d3a  mov     rax, [rcx]
0x180148d3d  mov     rax, [rax+10h]
0x180148d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148d46  mov     rax, rbx
0x180148d49  jmp     loc_180149253
0x180148d4e  mov     rcx, [rsp+350h+var_320]
0x180148d53  lea     r8, [rsp+350h+var_318]
0x180148d58  xor     r9d, r9d
0x180148d5b  lea     rdx, aMsiexecExe; "MsiExec.exe"
0x180148d62  mov     rax, [rcx]
0x180148d65  mov     rax, [rax+78h]
0x180148d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148d6e  mov     rbx, rax
0x180148d71  test    rax, rax
0x180148d74  jz      short loc_180148DDC
0x180148d76  mov     rdx, [rsp+350h+var_300]
0x180148d7b  mov     rcx, [rdx]
0x180148d7e  mov     rax, [rcx+10h]
0x180148d82  mov     rcx, rdx
0x180148d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148d8a  lea     rcx, [rsp+350h+hKey]; this
0x180148d8f  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180148d94  mov     rcx, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148d9b  mov     rax, [rcx+10h]
0x180148d9f  mov     rcx, rdi
0x180148da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148da7  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148dae  mov     rcx, rdi
0x180148db1  mov     rax, [rax+10h]
0x180148db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148dba  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148dc1  mov     rcx, rdi
0x180148dc4  mov     rax, [rax+10h]
0x180148dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148dcd  lea     rcx, [rsp+350h+var_320]
0x180148dd2  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180148dd7  jmp     loc_180148D46
0x180148ddc  mov     rcx, [rsp+350h+var_320]
0x180148de1  mov     rax, [rcx]
0x180148de4  mov     rax, [rax+38h]
0x180148de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148ded  mov     rbx, rax
0x180148df0  mov     rcx, rdi
0x180148df3  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148dfa  mov     rax, [rax+10h]
0x180148dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148e03  mov     rcx, [rsp+350h+var_300]
0x180148e08  mov     rax, [rcx]
0x180148e0b  mov     rax, [rax+10h]
0x180148e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148e14  lea     rcx, [rsp+350h+hKey]; this
0x180148e19  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180148e1e  cmp     [rsp+350h+var_318], 0
0x180148e23  jnz     loc_180149151
0x180148e29  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x180148e30  jz      short loc_180148E3D
0x180148e32  test    sil, sil
0x180148e35  jz      loc_180148F90
0x180148e3b  jmp     short loc_180148E46
0x180148e3d  test    sil, sil
0x180148e40  jnz     loc_180148F90
0x180148e46  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180148e4d  lea     rdx, [rbp+250h+Data]; lpFilename
0x180148e51  mov     r8d, 104h; nSize
0x180148e57  call    cs:__imp_GetModuleFileNameW
0x180148e5e  nop     dword ptr [rax+rax+00h]
0x180148e63  test    eax, eax
0x180148e65  jz      loc_180148F90
0x180148e6b  mov     rax, [r14]
0x180148e6e  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148e75  mov     [rsp+350h+var_2F8], rcx
0x180148e7a  mov     rdi, [rax+168h]
0x180148e81  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148e88  mov     rax, [rax+10h]
0x180148e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148e91  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148e98  lea     rcx, [rsp+350h+var_320]
0x180148e9d  mov     [rsp+350h+var_2F8], rax
0x180148ea2  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x180148ea7  mov     r8, rax
0x180148eaa  lea     r9, [rsp+350h+var_2F8]
0x180148eaf  mov     rax, rdi
0x180148eb2  lea     rdx, [rbp+250h+Data]
0x180148eb6  mov     rcx, r14
0x180148eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148ebe  mov     rdi, rax
0x180148ec1  test    rax, rax
0x180148ec4  jz      short loc_180148F28
0x180148ec6  mov     rdx, [rsp+350h+var_2F8]
0x180148ecb  mov     rcx, [rdx]
0x180148ece  mov     rax, [rcx+10h]
0x180148ed2  mov     rcx, rdx
0x180148ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148eda  mov     rcx, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148ee1  lea     rsi, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148ee8  mov     rax, [rcx+10h]
0x180148eec  mov     rcx, rsi
0x180148eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148ef4  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148efb  mov     rcx, rsi
0x180148efe  mov     rax, [rax+10h]
0x180148f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148f07  mov     rax, [rbx]
0x180148f0a  mov     rcx, rbx
0x180148f0d  mov     rax, [rax+10h]
0x180148f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148f16  lea     rcx, [rsp+350h+var_320]
0x180148f1b  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180148f20  mov     rax, rdi
0x180148f23  jmp     loc_180149253
0x180148f28  mov     rcx, [rsp+350h+var_320]
0x180148f2d  lea     r8, [rsp+350h+var_318]
0x180148f32  xor     r9d, r9d
0x180148f35  lea     rdx, aMsiexecExe; "MsiExec.exe"
0x180148f3c  mov     rax, [rcx]
0x180148f3f  mov     rax, [rax+78h]
0x180148f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148f48  mov     rdi, rax
0x180148f4b  test    rax, rax
0x180148f4e  jnz     loc_180148EC6
0x180148f54  mov     rcx, [rsp+350h+var_320]
0x180148f59  mov     rax, [rcx]
0x180148f5c  mov     rax, [rax+38h]
0x180148f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148f65  mov     rdi, rax
0x180148f68  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148f6f  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148f76  mov     rax, [rax+10h]
0x180148f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148f7f  mov     rcx, [rsp+350h+var_2F8]
0x180148f84  mov     rax, [rcx]
0x180148f87  mov     rax, [rax+10h]
0x180148f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148f90  cmp     [rsp+350h+var_318], 0
0x180148f95  jnz     loc_180149151
0x180148f9b  mov     r8d, esi
0x180148f9e  lea     rcx, [rbp+250h+Data]; unsigned __int16 *
0x180148fa2  xor     r8d, 1; int
0x180148fa6  mov     edx, 104h; unsigned int
0x180148fab  call    ?MsiGetSystemDirectory@@YAIPEAGIH@Z; MsiGetSystemDirectory(ushort *,uint,int)
0x180148fb0  mov     rax, [r14]
0x180148fb3  lea     rcx, [rsp+350h+var_320]
0x180148fb8  mov     rsi, [rax+78h]
0x180148fbc  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x180148fc1  mov     r8, rax
0x180148fc4  lea     rdx, [rbp+250h+Data]
0x180148fc8  mov     rax, rsi
0x180148fcb  mov     rcx, r14
0x180148fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148fd3  mov     rsi, rax
0x180148fd6  test    rax, rax
0x180148fd9  jz      short loc_180149038
0x180148fdb  mov     rcx, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148fe2  lea     r14, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148fe9  mov     rax, [rcx+10h]
0x180148fed  mov     rcx, r14
0x180148ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180148ff5  mov     rcx, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180148ffc  mov     rax, [rcx+10h]
0x180149000  mov     rcx, r14
0x180149003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149008  mov     rax, [rdi]
0x18014900b  mov     rcx, rdi
0x18014900e  mov     rax, [rax+10h]
0x180149012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149017  mov     rax, [rbx]
0x18014901a  mov     rcx, rbx
0x18014901d  mov     rax, [rax+10h]
0x180149021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149026  lea     rcx, [rsp+350h+var_320]
0x18014902b  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180149030  mov     rax, rsi
0x180149033  jmp     loc_180149253
  ... truncated ...
```
