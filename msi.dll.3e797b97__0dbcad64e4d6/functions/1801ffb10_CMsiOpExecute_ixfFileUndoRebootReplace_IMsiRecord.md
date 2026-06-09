# CMsiOpExecute::ixfFileUndoRebootReplace(IMsiRecord &)

- ea: `0x1801ffb10`
- end: `0x18020016f`
- name: `?ixfFileUndoRebootReplace@CMsiOpExecute@@IEAA?AW4iesEnum@@AEAVIMsiRecord@@@Z`
- size: `1631`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c6ebc`
- `0x18012c888`
- `0x1801328bc`
- `0x1801e8810`

## callees

- `0x180005af8`
- `0x180018ee0`
- `0x180019cc0`
- `0x180082cec`
- `0x1800ee66c`
- `0x1801e4980`
- `0x1801e7418`
- `0x1801ffb10`
- `0x1802651de`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1801ffd35`
- `ADVAPI32!RegQueryValueExW` at `0x1801ffe1e`
- `ADVAPI32!RegQueryValueExW` at `0x1801ffd35`
- `ADVAPI32!RegQueryValueExW` at `0x1801ffe1e`
- `ADVAPI32!RegCloseKey` at `0x1801ffe33`
- `ADVAPI32!RegCloseKey` at `0x1802000c5`
- `ADVAPI32!RegCloseKey` at `0x1801ffe33`
- `ADVAPI32!RegCloseKey` at `0x1802000c5`
- `ADVAPI32!RegSetValueExW` at `0x1802000b4`
- `ADVAPI32!RegSetValueExW` at `0x1802000b4`
- `KERNEL32!lstrlenW` at `0x1801fff02`
- `KERNEL32!lstrlenW` at `0x1801fffc7`
- `KERNEL32!lstrlenW` at `0x1801ffffd`
- `KERNEL32!lstrlenW` at `0x1801fff02`
- `KERNEL32!lstrlenW` at `0x1801fffc7`
- `KERNEL32!lstrlenW` at `0x1801ffffd`

## string_xrefs

- `0x1801ffb7c`: `ixfFileUndoRebootReplace`
- `0x1801ffd1d`: `PendingFileRenameOperations`
- `0x1801ffe17`: `PendingFileRenameOperations`
- `0x18020008d`: `PendingFileRenameOperations`

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
  BYTE *lpData; // rdx
  unsigned __int16 *v15; // r13
  __int64 v16; // r15
  MsiString *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  MsiString *v20; // rax
  void *v21; // r15
  __int64 v22; // rax
  __int64 v23; // rcx
  const WCHAR *v24; // r15
  __int64 v25; // rcx
  int v26; // r15d
  int v27; // r15d
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  void *v32; // [rsp+48h] [rbp-B8h] BYREF
  void *v33; // [rsp+50h] [rbp-B0h]
  unsigned int i; // [rsp+58h] [rbp-A8h]
  void *v35; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+68h] [rbp-98h]
  __int64 v37; // [rsp+70h] [rbp-90h] BYREF
  __int64 v38; // [rsp+78h] [rbp-88h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+88h] [rbp-78h] BYREF
  const WCHAR *v41; // [rsp+90h] [rbp-70h]
  __int64 v42; // [rsp+98h] [rbp-68h]
  __int64 v43; // [rsp+A0h] [rbp-60h] BYREF
  LPCWSTR lpString; // [rsp+B0h] [rbp-50h] BYREF
  int v45; // [rsp+B8h] [rbp-48h]
  BYTE Data[400]; // [rsp+C0h] [rbp-40h] BYREF

  v2 = *a2;
  v43 = 0;
  v5 = 1;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v2 + 72))(a2, 1);
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v6 + 56LL))(v6) )
  {
    CMsiOpExecute::DispatchError(a1, 0x1000000, 2901, L"ixfFileUndoRebootReplace", 1);
LABEL_16:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    v5 = 3;
    goto LABEL_33;
  }
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 2);
  v8 = MsiString::MsiString((MsiString *)&v37, L"??\\");
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v8 + 168LL))(*(_QWORD *)v8, v6);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 56LL))(v7) )
  {
    v10 = MsiString::MsiString((MsiString *)&v38, L"??\\");
    v11 = (void *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v10 + 168LL))(*(_QWORD *)v10, v7);
    v33 = &MsiString::s_NullString;
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  else
  {
    v33 = &MsiString::s_NullString;
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
  v45 = 200;
  lpString = (LPCWSTR)Data;
  cbData = 200;
  v12 = RegQueryValueExW(hKey, L"PendingFileRenameOperations", 0, &Type, Data, &cbData);
  if ( v12 == 234 )
  {
    v13 = (int)cbData;
    if ( v45 > 200 )
      operator delete((void *)lpString);
    if ( (int)v13 <= 200 )
    {
      lpData = Data;
      lpString = (LPCWSTR)Data;
    }
    else
    {
      lpData = (BYTE *)operator new(saturated_mul(v13, 2u));
      lpString = (LPCWSTR)lpData;
    }
    v45 = lpData != 0 ? v13 : 0;
    if ( !lpData )
    {
      CTempBuffer<unsigned short,200>::~CTempBuffer<unsigned short,200>(&lpString);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      goto LABEL_16;
    }
    v12 = RegQueryValueExW(hKey, L"PendingFileRenameOperations", 0, &Type, lpData, &cbData);
  }
  if ( v12 )
  {
    RegCloseKey(hKey);
    CTempBuffer<unsigned short,200>::~CTempBuffer<unsigned short,200>(&lpString);
LABEL_7:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    goto LABEL_33;
  }
  v15 = (unsigned __int16 *)lpString;
  v32 = &MsiString::s_NullString;
  v35 = &MsiString::s_NullString;
  v42 = cbData >> 1;
  v16 = (unsigned int)(v42 - 1);
  v41 = &lpString[v42];
  for ( i = v42 - 1; ; v16 = i )
  {
    v17 = MsiString::MsiString((MsiString *)&v39, v15);
    MsiString::operator=(&v32, v17);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v32 + 56LL))(v32) )
      break;
    v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 80LL))(v9);
    v36 = v16;
    if ( (*(unsigned int (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)v32 + 200LL))(v32, 5, v18) )
    {
      v19 = lstrlenW(v15) + 1;
      if ( v19 + v15 - lpString >= v16 )
        break;
      v20 = MsiString::MsiString((MsiString *)&v40, &v15[v19]);
      MsiString::operator=(&v35, v20);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      v21 = v35;
      v33 = v35;
      if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v35 + 56LL))(v35)
        && !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v11 + 56LL))(v11)
        || (v22 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v11 + 80LL))(v11),
            (*(unsigned int (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)v21 + 200LL))(v21, 5, v22)) )
      {
        v26 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v32 + 56LL))(v32);
        v27 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v33 + 56LL))(v33) + 2 + v26;
        memmove_0(v15, &v15[v27], 2LL * (unsigned int)(v41 - &v15[v27]));
        RegSetValueExW(hKey, L"PendingFileRenameOperations", 0, 7u, (const BYTE *)lpString, 2 * (v42 - v27));
        break;
      }
      v16 = v36;
    }
    v23 = lstrlenW(v15) + 1;
    if ( v23 + v15 - lpString >= v16 )
      break;
    v24 = &v15[v23];
    v25 = lstrlenW(v24) + 1;
    if ( v25 + v24 - lpString >= v36 )
      break;
    v15 = (unsigned __int16 *)&v24[v25];
  }
  RegCloseKey(hKey);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v33 + 16LL))(v33);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
  CTempBuffer<unsigned short,200>::~CTempBuffer<unsigned short,200>(&lpString);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
LABEL_33:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v43);
  return v5;
}

```

## disassembly

```asm
0x1801ffb10  mov     [rsp-8+arg_10], rbx
0x1801ffb15  push    rbp
0x1801ffb16  push    rsi
0x1801ffb17  push    rdi
0x1801ffb18  push    r12
0x1801ffb1a  push    r13
0x1801ffb1c  push    r14
0x1801ffb1e  push    r15
0x1801ffb20  lea     rbp, [rsp-160h]
0x1801ffb28  sub     rsp, 260h
0x1801ffb2f  mov     rax, cs:__security_cookie
0x1801ffb36  xor     rax, rsp
0x1801ffb39  mov     [rbp+190h+var_40], rax
0x1801ffb40  mov     rax, [rdx]
0x1801ffb43  mov     rbx, rdx
0x1801ffb46  mov     rsi, rcx
0x1801ffb49  mov     [rbp+190h+var_1F0], 0
0x1801ffb51  mov     r12d, 1
0x1801ffb57  mov     rcx, rbx
0x1801ffb5a  mov     edx, r12d
0x1801ffb5d  mov     rax, [rax+48h]
0x1801ffb61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffb66  mov     rdi, rax
0x1801ffb69  mov     rcx, rdi
0x1801ffb6c  mov     rax, [rax]
0x1801ffb6f  mov     rax, [rax+38h]
0x1801ffb73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffb78  test    eax, eax
0x1801ffb7a  jnz     short loc_1801FFBA0
0x1801ffb7c  lea     r9, aIxffileundoreb; "ixfFileUndoRebootReplace"
0x1801ffb83  mov     dword ptr [rsp+290h+lpData], r12d
0x1801ffb88  mov     edx, 1000000h
0x1801ffb8d  mov     r8d, 0B55h
0x1801ffb93  mov     rcx, rsi
0x1801ffb96  call    ?DispatchError@CMsiOpExecute@@QEAA?AW4imsEnum@@W4imtEnum@@HPEBGH@Z; CMsiOpExecute::DispatchError(imtEnum,int,ushort const *,int)
0x1801ffb9b  jmp     loc_1801FFDE1
0x1801ffba0  mov     rax, [rbx]
0x1801ffba3  mov     edx, 2
0x1801ffba8  mov     rcx, rbx
0x1801ffbab  mov     rax, [rax+48h]
0x1801ffbaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffbb4  lea     rdx, asc_1802C5EA0; "??\\"
0x1801ffbbb  mov     r14, rax
0x1801ffbbe  lea     rcx, [rsp+290h+var_220]; this
0x1801ffbc3  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x1801ffbc8  mov     rdx, rdi
0x1801ffbcb  mov     rcx, [rax]
0x1801ffbce  mov     rax, [rcx]
0x1801ffbd1  mov     rax, [rax+0A8h]
0x1801ffbd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffbdd  mov     rcx, [rsp+290h+var_220]
0x1801ffbe2  mov     rsi, rax
0x1801ffbe5  mov     rax, [rcx]
0x1801ffbe8  mov     rax, [rax+10h]
0x1801ffbec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffbf1  mov     rax, [r14]
0x1801ffbf4  mov     rcx, r14
0x1801ffbf7  mov     rax, [rax+38h]
0x1801ffbfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffc00  test    eax, eax
0x1801ffc02  jz      short loc_1801FFC5F
0x1801ffc04  lea     rdx, asc_1802C5EA0; "??\\"
0x1801ffc0b  lea     rcx, [rsp+290h+var_218]; this
0x1801ffc10  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x1801ffc15  mov     rdx, r14
0x1801ffc18  mov     rcx, [rax]
0x1801ffc1b  mov     rax, [rcx]
0x1801ffc1e  mov     rax, [rax+0A8h]
0x1801ffc25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffc2a  mov     rbx, rax
0x1801ffc2d  lea     r15, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801ffc34  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801ffc3b  mov     rcx, r15
0x1801ffc3e  mov     [rsp+290h+var_240], r15
0x1801ffc43  mov     rax, [rax+10h]
0x1801ffc47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffc4c  mov     rcx, [rsp+290h+var_218]
0x1801ffc51  mov     rax, [rcx]
0x1801ffc54  mov     rax, [rax+10h]
0x1801ffc58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffc5d  jmp     short loc_1801FFC6E
0x1801ffc5f  lea     r15, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801ffc66  mov     [rsp+290h+var_240], r15
0x1801ffc6b  mov     rbx, r15
0x1801ffc6e  lea     rax, [rsp+290h+hKey]
0x1801ffc73  mov     [rsp+290h+hKey], 0
0x1801ffc7c  mov     [rsp+290h+lpData], rax
0x1801ffc81  lea     rdx, ?szSessionManagerKey@@3QBGB; "SYSTEM\\CurrentControlSet\\Control\\Ses"...
0x1801ffc88  mov     rax, cs:?RegOpenKeyAPI@@3P6AJPEAUHKEY__@@PEBGKKPEAPEAU1@@ZEA; long (*RegOpenKeyAPI)(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x1801ffc8f  mov     r9d, 2001Fh
0x1801ffc95  xor     r8d, r8d
0x1801ffc98  mov     rcx, 0FFFFFFFF80000002h
0x1801ffc9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffca4  test    eax, eax
0x1801ffca6  jz      short loc_1801FFCE1
0x1801ffca8  mov     rax, [rbx]
0x1801ffcab  mov     rcx, rbx
0x1801ffcae  mov     rax, [rax+10h]
0x1801ffcb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffcb7  mov     rax, [rsi]
0x1801ffcba  mov     rcx, rsi
0x1801ffcbd  mov     rax, [rax+10h]
0x1801ffcc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffcc6  mov     rax, [r14]
0x1801ffcc9  mov     rcx, r14
0x1801ffccc  mov     rax, [rax+10h]
0x1801ffcd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffcd5  mov     rax, [rdi]
0x1801ffcd8  mov     rax, [rax+10h]
0x1801ffcdc  jmp     loc_180200130
0x1801ffce1  xor     edx, edx; Val
0x1801ffce3  lea     rcx, [rbp+190h+Data]; void *
0x1801ffce7  mov     r8d, 190h; Size
0x1801ffced  call    memset_0
0x1801ffcf2  mov     ecx, 0C8h
0x1801ffcf7  mov     [rsp+290h+Type], 0
0x1801ffcff  lea     rax, [rbp+190h+Data]
0x1801ffd03  mov     [rbp+190h+var_1D8], ecx
0x1801ffd06  mov     [rbp+190h+lpString], rax
0x1801ffd0a  lea     r9, [rsp+290h+Type]; lpType
0x1801ffd0f  lea     rax, [rsp+290h+cbData]
0x1801ffd14  mov     [rsp+290h+cbData], ecx
0x1801ffd18  mov     rcx, [rsp+290h+hKey]; hKey
0x1801ffd1d  lea     rdx, ?szPendingFileRenameOperationsValue@@3QBGB; "PendingFileRenameOperations"
0x1801ffd24  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1801ffd29  xor     r8d, r8d; lpReserved
0x1801ffd2c  lea     rax, [rbp+190h+Data]
0x1801ffd30  mov     [rsp+290h+lpData], rax; lpData
0x1801ffd35  call    cs:__imp_RegQueryValueExW
0x1801ffd3c  nop     dword ptr [rax+rax+00h]
0x1801ffd41  cmp     eax, 0EAh
0x1801ffd46  jnz     loc_1801FFE2A
0x1801ffd4c  cmp     [rbp+190h+var_1D8], 0C8h
0x1801ffd53  movsxd  r13, [rsp+290h+cbData]
0x1801ffd58  jle     short loc_1801FFD63
0x1801ffd5a  mov     rcx, [rbp+190h+lpString]; void *
0x1801ffd5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801ffd63  cmp     r13d, 0C8h
0x1801ffd6a  jle     short loc_1801FFD90
0x1801ffd6c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1801ffd73  mov     eax, 2
0x1801ffd78  mul     r13
0x1801ffd7b  cmovb   rax, rcx
0x1801ffd7f  mov     rcx, rax; unsigned __int64
0x1801ffd82  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801ffd87  mov     rdx, rax
0x1801ffd8a  mov     [rbp+190h+lpString], rax
0x1801ffd8e  jmp     short loc_1801FFD98
0x1801ffd90  lea     rdx, [rbp+190h+Data]
0x1801ffd94  mov     [rbp+190h+lpString], rdx
0x1801ffd98  mov     rax, rdx
0x1801ffd9b  neg     rax
0x1801ffd9e  sbb     ecx, ecx
0x1801ffda0  and     ecx, r13d
0x1801ffda3  mov     [rbp+190h+var_1D8], ecx
0x1801ffda6  test    rdx, rdx
0x1801ffda9  jnz     short loc_1801FFDFB
0x1801ffdab  lea     rcx, [rbp+190h+lpString]
0x1801ffdaf  call    ??1?$CTempBuffer@G$0MI@@@QEAA@XZ; CTempBuffer<ushort,200>::~CTempBuffer<ushort,200>(void)
0x1801ffdb4  mov     rax, [rbx]
0x1801ffdb7  mov     rcx, rbx
0x1801ffdba  mov     rax, [rax+10h]
0x1801ffdbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffdc3  mov     rax, [rsi]
0x1801ffdc6  mov     rcx, rsi
0x1801ffdc9  mov     rax, [rax+10h]
0x1801ffdcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffdd2  mov     rax, [r14]
0x1801ffdd5  mov     rcx, r14
0x1801ffdd8  mov     rax, [rax+10h]
0x1801ffddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffde1  mov     rax, [rdi]
0x1801ffde4  mov     rcx, rdi
0x1801ffde7  mov     rax, [rax+10h]
0x1801ffdeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffdf0  mov     r12d, 3
0x1801ffdf6  jmp     loc_180200138
0x1801ffdfb  mov     rcx, [rsp+290h+hKey]; hKey
0x1801ffe00  lea     rax, [rsp+290h+cbData]
0x1801ffe05  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1801ffe0a  lea     r9, [rsp+290h+Type]; lpType
0x1801ffe0f  mov     [rsp+290h+lpData], rdx; lpData
0x1801ffe14  xor     r8d, r8d; lpReserved
0x1801ffe17  lea     rdx, ?szPendingFileRenameOperationsValue@@3QBGB; "PendingFileRenameOperations"
0x1801ffe1e  call    cs:__imp_RegQueryValueExW
0x1801ffe25  nop     dword ptr [rax+rax+00h]
0x1801ffe2a  test    eax, eax
0x1801ffe2c  jz      short loc_1801FFE4D
0x1801ffe2e  mov     rcx, [rsp+290h+hKey]; hKey
0x1801ffe33  call    cs:__imp_RegCloseKey
0x1801ffe3a  nop     dword ptr [rax+rax+00h]
0x1801ffe3f  lea     rcx, [rbp+190h+lpString]
0x1801ffe43  call    ??1?$CTempBuffer@G$0MI@@@QEAA@XZ; CTempBuffer<ushort,200>::~CTempBuffer<ushort,200>(void)
0x1801ffe48  jmp     loc_1801FFCA8
0x1801ffe4d  mov     eax, [rsp+290h+cbData]
0x1801ffe51  mov     r13, [rbp+190h+lpString]
0x1801ffe55  shr     eax, 1
0x1801ffe57  mov     ecx, eax
0x1801ffe59  mov     [rsp+290h+var_248], r15
0x1801ffe5e  mov     [rsp+290h+var_230], r15
0x1801ffe63  lea     rax, ds:0[rax*2]
0x1801ffe6b  mov     [rbp+190h+var_1F8], rcx
0x1801ffe6f  add     rax, r13
0x1801ffe72  lea     r15d, [rcx-1]
0x1801ffe76  mov     [rbp+190h+var_200], rax
0x1801ffe7a  mov     [rsp+290h+var_238], r15d
0x1801ffe7f  mov     rdx, r13; unsigned __int16 *
0x1801ffe82  lea     rcx, [rbp+190h+var_210]; this
0x1801ffe86  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x1801ffe8b  mov     rdx, rax
0x1801ffe8e  lea     rcx, [rsp+290h+var_248]
0x1801ffe93  call    ??4MsiString@@QEAAAEAV0@AEBV0@@Z; MsiString::operator=(MsiString const &)
0x1801ffe98  mov     rcx, [rbp+190h+var_210]
0x1801ffe9c  mov     rax, [rcx]
0x1801ffe9f  mov     rax, [rax+10h]
0x1801ffea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffea8  mov     rcx, [rsp+290h+var_248]
0x1801ffead  mov     rax, [rcx]
0x1801ffeb0  mov     rax, [rax+38h]
0x1801ffeb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffeb9  test    eax, eax
0x1801ffebb  jz      loc_1802000C0
0x1801ffec1  mov     rax, [rsi]
0x1801ffec4  mov     rcx, rsi
0x1801ffec7  mov     rax, [rax+50h]
0x1801ffecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffed0  mov     r10, [rsp+290h+var_248]
0x1801ffed5  mov     r8, rax
0x1801ffed8  mov     edx, 5
0x1801ffedd  mov     [rsp+290h+var_228], r15
0x1801ffee2  mov     rcx, [r10]
0x1801ffee5  mov     r9, [rcx+0C8h]
0x1801ffeec  mov     rcx, r10
0x1801ffeef  mov     rax, r9
0x1801ffef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffef7  test    eax, eax
0x1801ffef9  jz      loc_1801FFFC4
0x1801ffeff  mov     rcx, r13; lpString
0x1801fff02  call    cs:__imp_lstrlenW
0x1801fff09  nop     dword ptr [rax+rax+00h]
0x1801fff0e  add     eax, r12d
0x1801fff11  movsxd  rcx, eax
0x1801fff14  mov     rax, r13
0x1801fff17  sub     rax, [rbp+190h+lpString]
0x1801fff1b  sar     rax, 1
0x1801fff1e  add     rax, rcx
0x1801fff21  cmp     rax, r15
0x1801fff24  jge     loc_1802000C0
0x1801fff2a  lea     rdx, ds:0[rcx*2]
0x1801fff32  add     rdx, r13; unsigned __int16 *
0x1801fff35  lea     rcx, [rbp+190h+var_208]; this
0x1801fff39  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x1801fff3e  mov     rdx, rax
0x1801fff41  lea     rcx, [rsp+290h+var_230]
0x1801fff46  call    ??4MsiString@@QEAAAEAV0@AEBV0@@Z; MsiString::operator=(MsiString const &)
0x1801fff4b  mov     rcx, [rbp+190h+var_208]
0x1801fff4f  mov     rax, [rcx]
0x1801fff52  mov     rax, [rax+10h]
0x1801fff56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fff5b  mov     r15, [rsp+290h+var_230]
0x1801fff60  mov     rcx, r15
0x1801fff63  mov     [rsp+290h+var_240], r15
0x1801fff68  mov     rax, [r15]
0x1801fff6b  mov     rax, [rax+38h]
0x1801fff6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fff74  test    eax, eax
0x1801fff76  jnz     short loc_1801FFF8F
0x1801fff78  mov     rax, [rbx]
0x1801fff7b  mov     rcx, rbx
0x1801fff7e  mov     rax, [rax+38h]
0x1801fff82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fff87  test    eax, eax
0x1801fff89  jz      loc_180200035
0x1801fff8f  mov     rax, [rbx]
0x1801fff92  mov     rcx, rbx
0x1801fff95  mov     rax, [rax+50h]
0x1801fff99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fff9e  mov     rcx, [r15]
0x1801fffa1  mov     r8, rax
0x1801fffa4  mov     edx, 5
0x1801fffa9  mov     r9, [rcx+0C8h]
0x1801fffb0  mov     rcx, r15
0x1801fffb3  mov     rax, r9
0x1801fffb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fffbb  test    eax, eax
0x1801fffbd  jnz     short loc_180200035
0x1801fffbf  mov     r15, [rsp+290h+var_228]
0x1801fffc4  mov     rcx, r13; lpString
0x1801fffc7  call    cs:__imp_lstrlenW
0x1801fffce  nop     dword ptr [rax+rax+00h]
0x1801fffd3  add     eax, r12d
0x1801fffd6  movsxd  rcx, eax
0x1801fffd9  mov     rax, r13
0x1801fffdc  sub     rax, [rbp+190h+lpString]
0x1801fffe0  sar     rax, 1
0x1801fffe3  add     rax, rcx
0x1801fffe6  cmp     rax, r15
0x1801fffe9  jge     loc_1802000C0
0x1801fffef  lea     r15, ds:0[rcx*2]
0x1801ffff7  add     r15, r13
  ... truncated ...
```
