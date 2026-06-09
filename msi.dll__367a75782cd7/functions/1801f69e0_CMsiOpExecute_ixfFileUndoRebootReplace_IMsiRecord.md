# CMsiOpExecute::ixfFileUndoRebootReplace(IMsiRecord &)

- ea: `0x1801f69e0`
- end: `0x1801f700e`
- name: `?ixfFileUndoRebootReplace@CMsiOpExecute@@IEAA?AW4iesEnum@@AEAVIMsiRecord@@@Z`
- size: `1582`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800da4bc`
- `0x1800db2d0`
- `0x1800e12c4`
- `0x1801df8c0`

## callees

- `0x180061334`
- `0x1800620e4`
- `0x180066074`
- `0x18008be90`
- `0x1800e80a4`
- `0x1801dbbb8`
- `0x1801de4e0`
- `0x1801f69e0`
- `0x18025ab1e`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1801f6c05`
- `ADVAPI32!RegQueryValueExW` at `0x1801f6ce8`
- `ADVAPI32!RegQueryValueExW` at `0x1801f6c05`
- `ADVAPI32!RegQueryValueExW` at `0x1801f6ce8`
- `ADVAPI32!RegCloseKey` at `0x1801f6cf7`
- `ADVAPI32!RegCloseKey` at `0x1801f6f6b`
- `ADVAPI32!RegCloseKey` at `0x1801f6cf7`
- `ADVAPI32!RegCloseKey` at `0x1801f6f6b`
- `ADVAPI32!RegSetValueExW` at `0x1801f6f60`
- `ADVAPI32!RegSetValueExW` at `0x1801f6f60`
- `KERNEL32!lstrlenW` at `0x1801f6dc0`
- `KERNEL32!lstrlenW` at `0x1801f6e7f`
- `KERNEL32!lstrlenW` at `0x1801f6eaf`
- `KERNEL32!lstrlenW` at `0x1801f6dc0`
- `KERNEL32!lstrlenW` at `0x1801f6e7f`
- `KERNEL32!lstrlenW` at `0x1801f6eaf`

## string_xrefs

- `0x1801f6a4c`: `ixfFileUndoRebootReplace`
- `0x1801f6bed`: `PendingFileRenameOperations`
- `0x1801f6ce1`: `PendingFileRenameOperations`
- `0x1801f6f39`: `PendingFileRenameOperations`

## pseudocode

```c
__int64 __fastcall CMsiOpExecute::ixfFileUndoRebootReplace(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  unsigned int v5; // r12d
  __int64 v6; // rdi
  __int64 v7; // r14
  MsiString *v8; // rax
  __int64 v9; // rsi
  MsiString *v10; // rax
  void *v11; // rbx
  LSTATUS v12; // eax
  unsigned __int64 v13; // r13
  unsigned int v14; // eax
  WCHAR *lpData; // rdx
  unsigned __int16 *v16; // r13
  __int64 v17; // r15
  MsiString *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  MsiString *v21; // rax
  void *v22; // r15
  __int64 v23; // rax
  __int64 v24; // rcx
  const WCHAR *v25; // r15
  __int64 v26; // rcx
  int v27; // r15d
  int v28; // r15d
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  void *v33; // [rsp+48h] [rbp-B8h] BYREF
  void *v34; // [rsp+50h] [rbp-B0h]
  unsigned int i; // [rsp+58h] [rbp-A8h]
  void *v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h]
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+88h] [rbp-78h] BYREF
  const WCHAR *v42; // [rsp+90h] [rbp-70h]
  __int64 v43; // [rsp+98h] [rbp-68h]
  __int64 v44; // [rsp+A0h] [rbp-60h] BYREF
  LPCWSTR lpString; // [rsp+B0h] [rbp-50h] BYREF
  int v46; // [rsp+B8h] [rbp-48h]
  BYTE Data[400]; // [rsp+C0h] [rbp-40h] BYREF

  v2 = *a2;
  v44 = 0;
  v5 = 1;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v2 + 72))(a2, 1);
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v6 + 56LL))(v6) )
  {
    CMsiOpExecute::DispatchError(a1, 0x1000000, 2901, L"ixfFileUndoRebootReplace", 1);
LABEL_18:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    v5 = 3;
    goto LABEL_35;
  }
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 2);
  v8 = MsiString::MsiString((MsiString *)&v38, L"??\\");
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v8 + 168LL))(*(_QWORD *)v8, v6);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 56LL))(v7) )
  {
    v10 = MsiString::MsiString((MsiString *)&v39, L"??\\");
    v11 = (void *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v10 + 168LL))(*(_QWORD *)v10, v7);
    v34 = &MsiString::s_NullString;
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  else
  {
    v34 = &MsiString::s_NullString;
    v11 = &MsiString::s_NullString;
  }
  hKey = 0;
  if ( (unsigned int)((__int64 (__fastcall *)(__int64, const unsigned __int16 *, _QWORD, __int64, HKEY *))RegOpenKeyAPI)(
                       -2147483646,
                       L"SYSTEM\\CurrentControlSet\\Control\\Session Manager",
                       0,
                       131103,
                       &hKey) )
    goto LABEL_7;
  memset_0(Data, 0, sizeof(Data));
  Type = 0;
  v46 = 200;
  lpString = (LPCWSTR)Data;
  cbData = 200;
  v12 = RegQueryValueExW(hKey, L"PendingFileRenameOperations", 0, &Type, Data, &cbData);
  if ( v12 == 234 )
  {
    v13 = (int)cbData;
    if ( v46 > 200 )
      operator delete((void *)lpString);
    if ( (int)v13 <= 200 )
    {
      lpData = (WCHAR *)Data;
      lpString = (LPCWSTR)Data;
    }
    else
    {
      v14 = 2 * v13;
      if ( !is_mul_ok(v13, 2u) )
        v14 = -1;
      lpData = (WCHAR *)operator new(v14);
      lpString = lpData;
    }
    v46 = lpData != 0 ? v13 : 0;
    if ( !lpData )
    {
      CTempBuffer<unsigned short,200>::~CTempBuffer<unsigned short,200>((__int64)&lpString);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      goto LABEL_18;
    }
    v12 = RegQueryValueExW(hKey, L"PendingFileRenameOperations", 0, &Type, (LPBYTE)lpData, &cbData);
  }
  if ( v12 )
  {
    RegCloseKey(hKey);
    CTempBuffer<unsigned short,200>::~CTempBuffer<unsigned short,200>((__int64)&lpString);
LABEL_7:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    goto LABEL_35;
  }
  v16 = (unsigned __int16 *)lpString;
  v33 = &MsiString::s_NullString;
  v36 = &MsiString::s_NullString;
  v43 = cbData >> 1;
  v17 = (unsigned int)(v43 - 1);
  v42 = &lpString[v43];
  for ( i = v43 - 1; ; v17 = i )
  {
    v18 = MsiString::MsiString((MsiString *)&v40, v16);
    MsiString::operator=(&v33, v18);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v33 + 56LL))(v33) )
      break;
    v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 80LL))(v9);
    v37 = v17;
    if ( (*(unsigned int (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)v33 + 200LL))(v33, 5, v19) )
    {
      v20 = lstrlenW(v16) + 1;
      if ( v20 + v16 - lpString >= v17 )
        break;
      v21 = MsiString::MsiString((MsiString *)&v41, &v16[v20]);
      MsiString::operator=(&v36, v21);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      v22 = v36;
      v34 = v36;
      if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v36 + 56LL))(v36)
        && !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v11 + 56LL))(v11)
        || (v23 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v11 + 80LL))(v11),
            (*(unsigned int (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)v22 + 200LL))(v22, 5, v23)) )
      {
        v27 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v33 + 56LL))(v33);
        v28 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v34 + 56LL))(v34) + 2 + v27;
        memmove_0(v16, &v16[v28], 2LL * (unsigned int)(v42 - &v16[v28]));
        RegSetValueExW(hKey, L"PendingFileRenameOperations", 0, 7u, (const BYTE *)lpString, 2 * (v43 - v28));
        break;
      }
      v17 = v37;
    }
    v24 = lstrlenW(v16) + 1;
    if ( v24 + v16 - lpString >= v17 )
      break;
    v25 = &v16[v24];
    v26 = lstrlenW(v25) + 1;
    if ( v26 + v25 - lpString >= v37 )
      break;
    v16 = (unsigned __int16 *)&v25[v26];
  }
  RegCloseKey(hKey);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v34 + 16LL))(v34);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v33 + 16LL))(v33);
  CTempBuffer<unsigned short,200>::~CTempBuffer<unsigned short,200>((__int64)&lpString);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
LABEL_35:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v44);
  return v5;
}

```

## disassembly

```asm
0x1801f69e0  mov     [rsp-8+arg_10], rbx
0x1801f69e5  push    rbp
0x1801f69e6  push    rsi
0x1801f69e7  push    rdi
0x1801f69e8  push    r12
0x1801f69ea  push    r13
0x1801f69ec  push    r14
0x1801f69ee  push    r15
0x1801f69f0  lea     rbp, [rsp-160h]
0x1801f69f8  sub     rsp, 260h
0x1801f69ff  mov     rax, cs:__security_cookie
0x1801f6a06  xor     rax, rsp
0x1801f6a09  mov     [rbp+190h+var_40], rax
0x1801f6a10  mov     rax, [rdx]
0x1801f6a13  mov     rbx, rdx
0x1801f6a16  mov     rsi, rcx
0x1801f6a19  mov     [rbp+190h+var_1F0], 0
0x1801f6a21  mov     r12d, 1
0x1801f6a27  mov     rcx, rbx
0x1801f6a2a  mov     edx, r12d
0x1801f6a2d  mov     rax, [rax+48h]
0x1801f6a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6a36  mov     rdi, rax
0x1801f6a39  mov     rcx, rdi
0x1801f6a3c  mov     rax, [rax]
0x1801f6a3f  mov     rax, [rax+38h]
0x1801f6a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6a48  test    eax, eax
0x1801f6a4a  jnz     short loc_1801F6A70
0x1801f6a4c  lea     r9, aIxffileundoreb; "ixfFileUndoRebootReplace"
0x1801f6a53  mov     dword ptr [rsp+290h+lpData], r12d
0x1801f6a58  mov     edx, 1000000h
0x1801f6a5d  mov     r8d, 0B55h
0x1801f6a63  mov     rcx, rsi
0x1801f6a66  call    ?DispatchError@CMsiOpExecute@@QEAA?AW4imsEnum@@W4imtEnum@@HPEBGH@Z; CMsiOpExecute::DispatchError(imtEnum,int,ushort const *,int)
0x1801f6a6b  jmp     loc_1801F6CAB
0x1801f6a70  mov     rax, [rbx]
0x1801f6a73  mov     edx, 2
0x1801f6a78  mov     rcx, rbx
0x1801f6a7b  mov     rax, [rax+48h]
0x1801f6a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6a84  lea     rdx, asc_1802BBF90; "??\\"
0x1801f6a8b  mov     r14, rax
0x1801f6a8e  lea     rcx, [rsp+290h+var_220]; this
0x1801f6a93  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x1801f6a98  mov     rdx, rdi
0x1801f6a9b  mov     rcx, [rax]
0x1801f6a9e  mov     rax, [rcx]
0x1801f6aa1  mov     rax, [rax+0A8h]
0x1801f6aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6aad  mov     rcx, [rsp+290h+var_220]
0x1801f6ab2  mov     rsi, rax
0x1801f6ab5  mov     rax, [rcx]
0x1801f6ab8  mov     rax, [rax+10h]
0x1801f6abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6ac1  mov     rax, [r14]
0x1801f6ac4  mov     rcx, r14
0x1801f6ac7  mov     rax, [rax+38h]
0x1801f6acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6ad0  test    eax, eax
0x1801f6ad2  jz      short loc_1801F6B2F
0x1801f6ad4  lea     rdx, asc_1802BBF90; "??\\"
0x1801f6adb  lea     rcx, [rsp+290h+var_218]; this
0x1801f6ae0  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x1801f6ae5  mov     rdx, r14
0x1801f6ae8  mov     rcx, [rax]
0x1801f6aeb  mov     rax, [rcx]
0x1801f6aee  mov     rax, [rax+0A8h]
0x1801f6af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6afa  mov     rbx, rax
0x1801f6afd  lea     r15, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801f6b04  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801f6b0b  mov     rcx, r15
0x1801f6b0e  mov     [rsp+290h+var_240], r15
0x1801f6b13  mov     rax, [rax+10h]
0x1801f6b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6b1c  mov     rcx, [rsp+290h+var_218]
0x1801f6b21  mov     rax, [rcx]
0x1801f6b24  mov     rax, [rax+10h]
0x1801f6b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6b2d  jmp     short loc_1801F6B3E
0x1801f6b2f  lea     r15, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801f6b36  mov     [rsp+290h+var_240], r15
0x1801f6b3b  mov     rbx, r15
0x1801f6b3e  lea     rax, [rsp+290h+hKey]
0x1801f6b43  mov     [rsp+290h+hKey], 0
0x1801f6b4c  mov     [rsp+290h+lpData], rax
0x1801f6b51  lea     rdx, ?szSessionManagerKey@@3QBGB; "SYSTEM\\CurrentControlSet\\Control\\Ses"...
0x1801f6b58  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x1801f6b5f  mov     r9d, 2001Fh
0x1801f6b65  xor     r8d, r8d
0x1801f6b68  mov     rcx, 0FFFFFFFF80000002h
0x1801f6b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6b74  test    eax, eax
0x1801f6b76  jz      short loc_1801F6BB1
0x1801f6b78  mov     rax, [rbx]
0x1801f6b7b  mov     rcx, rbx
0x1801f6b7e  mov     rax, [rax+10h]
0x1801f6b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6b87  mov     rax, [rsi]
0x1801f6b8a  mov     rcx, rsi
0x1801f6b8d  mov     rax, [rax+10h]
0x1801f6b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6b96  mov     rax, [r14]
0x1801f6b99  mov     rcx, r14
0x1801f6b9c  mov     rax, [rax+10h]
0x1801f6ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6ba5  mov     rax, [rdi]
0x1801f6ba8  mov     rax, [rax+10h]
0x1801f6bac  jmp     loc_1801F6FD0
0x1801f6bb1  xor     edx, edx; Val
0x1801f6bb3  lea     rcx, [rbp+190h+Data]; void *
0x1801f6bb7  mov     r8d, 190h; Size
0x1801f6bbd  call    memset_0
0x1801f6bc2  mov     ecx, 0C8h
0x1801f6bc7  mov     [rsp+290h+Type], 0
0x1801f6bcf  lea     rax, [rbp+190h+Data]
0x1801f6bd3  mov     [rbp+190h+var_1D8], ecx
0x1801f6bd6  mov     [rbp+190h+lpString], rax
0x1801f6bda  lea     r9, [rsp+290h+Type]; lpType
0x1801f6bdf  lea     rax, [rsp+290h+cbData]
0x1801f6be4  mov     [rsp+290h+cbData], ecx
0x1801f6be8  mov     rcx, [rsp+290h+hKey]; hKey
0x1801f6bed  lea     rdx, ?szPendingFileRenameOperationsValue@@3QBGB; "PendingFileRenameOperations"
0x1801f6bf4  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1801f6bf9  xor     r8d, r8d; lpReserved
0x1801f6bfc  lea     rax, [rbp+190h+Data]
0x1801f6c00  mov     [rsp+290h+lpData], rax; lpData
0x1801f6c05  call    cs:__imp_RegQueryValueExW
0x1801f6c0b  cmp     eax, 0EAh
0x1801f6c10  jnz     loc_1801F6CEE
0x1801f6c16  cmp     [rbp+190h+var_1D8], 0C8h
0x1801f6c1d  movsxd  r13, [rsp+290h+cbData]
0x1801f6c22  jle     short loc_1801F6C2D
0x1801f6c24  mov     rcx, [rbp+190h+lpString]; void *
0x1801f6c28  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801f6c2d  cmp     r13d, 0C8h
0x1801f6c34  jle     short loc_1801F6C5A
0x1801f6c36  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1801f6c3d  mov     eax, 2
0x1801f6c42  mul     r13
0x1801f6c45  cmovb   rax, rcx
0x1801f6c49  mov     rcx, rax; unsigned __int64
0x1801f6c4c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801f6c51  mov     rdx, rax
0x1801f6c54  mov     [rbp+190h+lpString], rax
0x1801f6c58  jmp     short loc_1801F6C62
0x1801f6c5a  lea     rdx, [rbp+190h+Data]
0x1801f6c5e  mov     [rbp+190h+lpString], rdx
0x1801f6c62  mov     rax, rdx
0x1801f6c65  neg     rax
0x1801f6c68  sbb     ecx, ecx
0x1801f6c6a  and     ecx, r13d
0x1801f6c6d  mov     [rbp+190h+var_1D8], ecx
0x1801f6c70  test    rdx, rdx
0x1801f6c73  jnz     short loc_1801F6CC5
0x1801f6c75  lea     rcx, [rbp+190h+lpString]
0x1801f6c79  call    ??1?$CTempBuffer@G$0MI@@@QEAA@XZ; CTempBuffer<ushort,200>::~CTempBuffer<ushort,200>(void)
0x1801f6c7e  mov     rax, [rbx]
0x1801f6c81  mov     rcx, rbx
0x1801f6c84  mov     rax, [rax+10h]
0x1801f6c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6c8d  mov     rax, [rsi]
0x1801f6c90  mov     rcx, rsi
0x1801f6c93  mov     rax, [rax+10h]
0x1801f6c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6c9c  mov     rax, [r14]
0x1801f6c9f  mov     rcx, r14
0x1801f6ca2  mov     rax, [rax+10h]
0x1801f6ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6cab  mov     rax, [rdi]
0x1801f6cae  mov     rcx, rdi
0x1801f6cb1  mov     rax, [rax+10h]
0x1801f6cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6cba  mov     r12d, 3
0x1801f6cc0  jmp     loc_1801F6FD8
0x1801f6cc5  mov     rcx, [rsp+290h+hKey]; hKey
0x1801f6cca  lea     rax, [rsp+290h+cbData]
0x1801f6ccf  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1801f6cd4  lea     r9, [rsp+290h+Type]; lpType
0x1801f6cd9  mov     [rsp+290h+lpData], rdx; lpData
0x1801f6cde  xor     r8d, r8d; lpReserved
0x1801f6ce1  lea     rdx, ?szPendingFileRenameOperationsValue@@3QBGB; "PendingFileRenameOperations"
0x1801f6ce8  call    cs:__imp_RegQueryValueExW
0x1801f6cee  test    eax, eax
0x1801f6cf0  jz      short loc_1801F6D0B
0x1801f6cf2  mov     rcx, [rsp+290h+hKey]; hKey
0x1801f6cf7  call    cs:__imp_RegCloseKey
0x1801f6cfd  lea     rcx, [rbp+190h+lpString]
0x1801f6d01  call    ??1?$CTempBuffer@G$0MI@@@QEAA@XZ; CTempBuffer<ushort,200>::~CTempBuffer<ushort,200>(void)
0x1801f6d06  jmp     loc_1801F6B78
0x1801f6d0b  mov     eax, [rsp+290h+cbData]
0x1801f6d0f  mov     r13, [rbp+190h+lpString]
0x1801f6d13  shr     eax, 1
0x1801f6d15  mov     ecx, eax
0x1801f6d17  mov     [rsp+290h+var_248], r15
0x1801f6d1c  mov     [rsp+290h+var_230], r15
0x1801f6d21  lea     rax, ds:0[rax*2]
0x1801f6d29  mov     [rbp+190h+var_1F8], rcx
0x1801f6d2d  add     rax, r13
0x1801f6d30  lea     r15d, [rcx-1]
0x1801f6d34  mov     [rbp+190h+var_200], rax
0x1801f6d38  mov     [rsp+290h+var_238], r15d
0x1801f6d3d  mov     rdx, r13; unsigned __int16 *
0x1801f6d40  lea     rcx, [rbp+190h+var_210]; this
0x1801f6d44  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x1801f6d49  mov     rdx, rax
0x1801f6d4c  lea     rcx, [rsp+290h+var_248]
0x1801f6d51  call    ??4MsiString@@QEAAAEAV0@AEBV0@@Z; MsiString::operator=(MsiString const &)
0x1801f6d56  mov     rcx, [rbp+190h+var_210]
0x1801f6d5a  mov     rax, [rcx]
0x1801f6d5d  mov     rax, [rax+10h]
0x1801f6d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6d66  mov     rcx, [rsp+290h+var_248]
0x1801f6d6b  mov     rax, [rcx]
0x1801f6d6e  mov     rax, [rax+38h]
0x1801f6d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6d77  test    eax, eax
0x1801f6d79  jz      loc_1801F6F66
0x1801f6d7f  mov     rax, [rsi]
0x1801f6d82  mov     rcx, rsi
0x1801f6d85  mov     rax, [rax+50h]
0x1801f6d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6d8e  mov     r10, [rsp+290h+var_248]
0x1801f6d93  mov     r8, rax
0x1801f6d96  mov     edx, 5
0x1801f6d9b  mov     [rsp+290h+var_228], r15
0x1801f6da0  mov     rcx, [r10]
0x1801f6da3  mov     r9, [rcx+0C8h]
0x1801f6daa  mov     rcx, r10
0x1801f6dad  mov     rax, r9
0x1801f6db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6db5  test    eax, eax
0x1801f6db7  jz      loc_1801F6E7C
0x1801f6dbd  mov     rcx, r13; lpString
0x1801f6dc0  call    cs:__imp_lstrlenW
0x1801f6dc6  add     eax, r12d
0x1801f6dc9  movsxd  rcx, eax
0x1801f6dcc  mov     rax, r13
0x1801f6dcf  sub     rax, [rbp+190h+lpString]
0x1801f6dd3  sar     rax, 1
0x1801f6dd6  add     rax, rcx
0x1801f6dd9  cmp     rax, r15
0x1801f6ddc  jge     loc_1801F6F66
0x1801f6de2  lea     rdx, ds:0[rcx*2]
0x1801f6dea  add     rdx, r13; unsigned __int16 *
0x1801f6ded  lea     rcx, [rbp+190h+var_208]; this
0x1801f6df1  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x1801f6df6  mov     rdx, rax
0x1801f6df9  lea     rcx, [rsp+290h+var_230]
0x1801f6dfe  call    ??4MsiString@@QEAAAEAV0@AEBV0@@Z; MsiString::operator=(MsiString const &)
0x1801f6e03  mov     rcx, [rbp+190h+var_208]
0x1801f6e07  mov     rax, [rcx]
0x1801f6e0a  mov     rax, [rax+10h]
0x1801f6e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6e13  mov     r15, [rsp+290h+var_230]
0x1801f6e18  mov     rcx, r15
0x1801f6e1b  mov     [rsp+290h+var_240], r15
0x1801f6e20  mov     rax, [r15]
0x1801f6e23  mov     rax, [rax+38h]
0x1801f6e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6e2c  test    eax, eax
0x1801f6e2e  jnz     short loc_1801F6E47
0x1801f6e30  mov     rax, [rbx]
0x1801f6e33  mov     rcx, rbx
0x1801f6e36  mov     rax, [rax+38h]
0x1801f6e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6e3f  test    eax, eax
0x1801f6e41  jz      loc_1801F6EE1
0x1801f6e47  mov     rax, [rbx]
0x1801f6e4a  mov     rcx, rbx
0x1801f6e4d  mov     rax, [rax+50h]
0x1801f6e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6e56  mov     rcx, [r15]
0x1801f6e59  mov     r8, rax
0x1801f6e5c  mov     edx, 5
0x1801f6e61  mov     r9, [rcx+0C8h]
0x1801f6e68  mov     rcx, r15
0x1801f6e6b  mov     rax, r9
0x1801f6e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6e73  test    eax, eax
0x1801f6e75  jnz     short loc_1801F6EE1
0x1801f6e77  mov     r15, [rsp+290h+var_228]
0x1801f6e7c  mov     rcx, r13; lpString
0x1801f6e7f  call    cs:__imp_lstrlenW
0x1801f6e85  add     eax, r12d
0x1801f6e88  movsxd  rcx, eax
0x1801f6e8b  mov     rax, r13
0x1801f6e8e  sub     rax, [rbp+190h+lpString]
0x1801f6e92  sar     rax, 1
0x1801f6e95  add     rax, rcx
0x1801f6e98  cmp     rax, r15
0x1801f6e9b  jge     loc_1801F6F66
0x1801f6ea1  lea     r15, ds:0[rcx*2]
0x1801f6ea9  add     r15, r13
0x1801f6eac  mov     rcx, r15; lpString
0x1801f6eaf  call    cs:__imp_lstrlenW
0x1801f6eb5  add     eax, r12d
0x1801f6eb8  movsxd  rcx, eax
0x1801f6ebb  mov     rax, r15
  ... truncated ...
```
