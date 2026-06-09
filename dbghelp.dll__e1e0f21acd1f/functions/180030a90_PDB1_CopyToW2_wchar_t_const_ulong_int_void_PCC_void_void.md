# PDB1::CopyToW2(wchar_t const *,ulong,int (*(*)(void *,PCC))(void),void *)

- ea: `0x180030a90`
- end: `0x180031215`
- name: `?CopyToW2@PDB1@@UEAAHPEB_WKP6AP6AHXZPEAXW4PCC@@@Z1@Z`
- size: `1925`
- prototype: `__int64 __fastcall(PDB1 *__hidden this, const wchar_t *, unsigned int, int (__high *(__high *)(void *, enum PCC))(void), void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180026980`
- `0x18002bf30`
- `0x18002cdc0`
- `0x18002e960`
- `0x1800303e0`
- `0x1800308e0`
- `0x180030a90`
- `0x180031f90`
- `0x1800321b0`
- `0x180035d30`
- `0x180037a00`
- `0x1800566d0`
- `0x180084220`
- `0x180168f90`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180030c56`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180030c56`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180030eff`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180030eff`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180030c1c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180030c1c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180030c0a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180030c0a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180030b42`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180030b5c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180030b42`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180030b5c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180030b94`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180030b94`

## string_xrefs

- `0x180030b55`: `api-ms-win-core-file-l2-1-1.dll`
- `0x180030b3b`: `kernel32.dll`
- `0x180030b8a`: `CopyFileExW`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PDB1::CopyToW2(
        PDB1 *this,
        const wchar_t *a2,
        int a3,
        int (__high *(__high *a4)(void *, enum PCC))(void),
        void *a5)
{
  int (__high *(__high *v5)(void *, enum PCC))(void); // r13
  int v8; // r15d
  int v9; // edi
  HMODULE Library; // rax
  __int64 result; // rax
  FARPROC ProcAddress; // rax
  DWORD FileAttributesW; // eax
  bool v14; // bl
  unsigned int v15; // eax
  unsigned int v16; // esi
  unsigned int v17; // ebx
  DBI1 *v18; // r13
  __int64 v19; // rdi
  void (__fastcall *v20)(__int64, _QWORD); // r15
  unsigned __int16 v21; // ax
  _QWORD *i; // rdi
  _QWORD *v23; // r15
  _QWORD *v24; // rdi
  _QWORD *j; // r15
  unsigned int v26; // r8d
  PSGSI1::EnumPubsByAddr *v27; // rdx
  void (__fastcall ***v28)(_QWORD, __int64); // rcx
  unsigned int v29; // eax
  unsigned int v30; // ebx
  int v31; // esi
  int v32; // esi
  unsigned int v33; // edx
  bool v34; // [rsp+40h] [rbp-1158h]
  struct PDB *v35; // [rsp+48h] [rbp-1150h] BYREF
  int v36; // [rsp+50h] [rbp-1148h]
  struct _GUID v37; // [rsp+60h] [rbp-1138h] BYREF
  int v38; // [rsp+70h] [rbp-1128h]
  int v39; // [rsp+74h] [rbp-1124h]
  int v40; // [rsp+78h] [rbp-1120h] BYREF
  __int64 v41; // [rsp+80h] [rbp-1118h] BYREF
  int (__high *(__high *v42)(void *, enum PCC))(void); // [rsp+88h] [rbp-1110h]
  __int64 v43; // [rsp+90h] [rbp-1108h] BYREF
  void *v44; // [rsp+98h] [rbp-1100h]
  _QWORD v45[4]; // [rsp+A0h] [rbp-10F8h] BYREF
  __int128 v46; // [rsp+C0h] [rbp-10D8h] BYREF
  __int128 v47; // [rsp+D0h] [rbp-10C8h] BYREF
  __int128 v48; // [rsp+E0h] [rbp-10B8h]
  int (__high *(__high *v49)(void *, enum PCC))(void); // [rsp+F0h] [rbp-10A8h]
  void *v50; // [rsp+F8h] [rbp-10A0h]
  int v51; // [rsp+100h] [rbp-1098h]
  unsigned int v52; // [rsp+104h] [rbp-1094h]
  PSGSI1::EnumPubsByAddr *v53; // [rsp+108h] [rbp-1090h]
  __int16 v54; // [rsp+110h] [rbp-1088h]
  void **v55; // [rsp+118h] [rbp-1080h]
  PSGSI1::EnumPubsByAddr *v56; // [rsp+120h] [rbp-1078h]
  __int64 v57; // [rsp+128h] [rbp-1070h]
  PDB1 *v58; // [rsp+130h] [rbp-1068h]
  __int64 v59; // [rsp+138h] [rbp-1060h]
  PDBErrors *v60; // [rsp+140h] [rbp-1058h] BYREF
  struct _GUID v61; // [rsp+148h] [rbp-1050h] BYREF
  _WORD v62[1024]; // [rsp+160h] [rbp-1038h] BYREF
  wchar_t v63[1024]; // [rsp+960h] [rbp-838h] BYREF

  v59 = -2;
  try
  {
    v5 = a4;
    v42 = (int (__high *(__high *)(void *, enum PCC))(void))a4;
    v36 = a3;
    v58 = this;
    v44 = a5;
    v34 = a3 & 1;
    v8 = a3 & 2;
    v39 = v8;
    v9 = a3 & 0x20;
    v38 = v9;
    if ( (a3 & 1) == 0 && (a3 & 0x20) == 0 )
    {
      Library = LoadLibraryExW(L"kernel32.dll", 0, 8u);
      if ( !Library && (Library = LoadLibraryExW(L"api-ms-win-core-file-l2-1-1.dll", 0, 8u)) == 0
        || (ProcAddress = GetProcAddress(Library, "CopyFileExW")) == 0 )
      {
        (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *))(**((_QWORD **)this + 67) + 8LL))(
          *((_QWORD *)this + 67),
          24,
          a2);
        return 0;
      }
      if ( ((int (__fastcall *)(char *, const wchar_t *, _QWORD, _QWORD, _QWORD, _DWORD))ProcAddress)(
             (char *)this + 16,
             a2,
             0,
             0,
             0,
             0) < 0 )
      {
        (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *))(**((_QWORD **)this + 67) + 8LL))(
          *((_QWORD *)this + 67),
          3,
          a2);
        return 0;
      }
      FileAttributesW = GetFileAttributesW(a2);
      if ( (FileAttributesW & 1) != 0 )
        SetFileAttributesW(a2, FileAttributesW & 0xFFFFFFFE);
      if ( !v8
        || (v61 = 0, result = FUuidCreate(&v61), (_DWORD)result)
        && (v14 = (*((_BYTE *)this + 945) & 2) != 0,
            v15 = _time64(0),
            result = PDB1::patchSigAndAge(a2, v15, &v61, 1u, 1u, 0, v14),
            (_DWORD)result) )
      {
        v16 = 1;
        goto LABEL_65;
      }
      return result;
    }
    if ( *((_DWORD *)this + 136) <= 0x130BA2Cu )
      return 0;
    v17 = 0;
    *(_QWORD *)&v37.Data1 = 0;
    result = PDB1::OpenDBI(this, 0, "r", (struct DBI **)&v37);
    if ( !(_DWORD)result )
      return result;
    v35 = 0;
    v16 = PDB1::OpenEx2W(a2, "fwx", 0, 4 * cbPgPdbDef, &v40, v63, 0x400u, &v35);
    v41 = 0;
    *(_QWORD *)&v61.Data1 = 0;
    v43 = 0;
    if ( v16 )
    {
      if ( (!v9
         || (*(unsigned int (__fastcall **)(struct PDB *, const char *, struct _GUID *))(*(_QWORD *)v35 + 64LL))(
              v35,
              "w",
              &v61)
         && (*(unsigned int (__fastcall **)(struct PDB *, const char *, __int64 *))(*(_QWORD *)v35 + 72LL))(
              v35,
              "w",
              &v43))
        && (*(unsigned int (__fastcall **)(struct PDB *, _QWORD, __int64 *))(*(_QWORD *)v35 + 48LL))(v35, 0, &v41) )
      {
        v46 = 0;
        v47 = 0;
        v48 = 0;
        v55 = &pdb_internal::Array<ReadOnlySafeSpanPtr>::`vftable';
        v56 = 0;
        v57 = 0;
        v45[0] = this;
        v45[1] = v35;
        v18 = *(DBI1 **)&v37.Data1;
        v45[2] = *(_QWORD *)&v37.Data1;
        v19 = v41;
        v45[3] = v41;
        v51 = v36;
        v52 = 0;
        v49 = v42;
        v50 = v44;
        v53 = 0;
        v54 = 0;
        v20 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v41 + 352LL);
        v21 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&v37.Data1 + 344LL))(*(_QWORD *)&v37.Data1);
        v20(v19, v21);
        if ( !(unsigned int)PDBCopy::CopyMods((PDBCopy *)v45)
          || !(unsigned int)PDBCopy::CopyPublics((PDBCopy *)v45)
          || !(unsigned int)PDBCopy::CopySecMap((PDBCopy *)v45)
          || !(unsigned int)PDBCopy::CopyDbg((PDBCopy *)v45) )
        {
          if ( v53 )
            _o_wcsncpy_s(v62, 1024, v53, -1);
          else
            v62[0] = 0;
          (*(void (__fastcall **)(_QWORD, _QWORD, _WORD *))(**((_QWORD **)this + 67) + 8LL))(
            *((_QWORD *)this + 67),
            v52,
            v62);
          v16 = 0;
        }
        v23 = (_QWORD *)*((_QWORD *)&v46 + 1);
        for ( i = (_QWORD *)v46; i != v23; ++i )
        {
          if ( *i )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*i + 128LL))(*i);
        }
        v24 = (_QWORD *)*((_QWORD *)&v47 + 1);
        for ( j = (_QWORD *)v48; v24 != j; ++v24 )
        {
          if ( *v24 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v24 + 128LL))(*v24);
        }
        if ( v53 )
          PSGSI1::EnumPubsByAddr::release(v53);
        v26 = v57;
        v27 = v56;
        if ( (_DWORD)v57 )
        {
          do
          {
            v28 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v27 + v17);
            if ( v28 )
            {
              (**v28)(v28, 1);
              v26 = v57;
              v27 = v56;
            }
            ++v17;
          }
          while ( v17 < v26 );
        }
        v55 = &pdb_internal::Array<ReadOnlySafeSpanPtr>::`vftable';
        if ( v27 )
          PSGSI1::EnumPubsByAddr::release(v27);
        std::vector<unsigned __int64>::~vector<unsigned __int64>((char *)&v47 + 8);
        std::vector<unsigned __int64>::~vector<unsigned __int64>(&v46);
        v9 = v38;
        v8 = v39;
        goto LABEL_52;
      }
      v29 = (*(__int64 (__fastcall **)(struct PDB *, _WORD *, __int64))(*(_QWORD *)v35 + 152LL))(v35, v62, 1024);
      (*(void (__fastcall **)(_QWORD, _QWORD, _WORD *))(**((_QWORD **)this + 67) + 8LL))(
        *((_QWORD *)this + 67),
        v29,
        v62);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, wchar_t *))(**((_QWORD **)this + 67) + 8LL))(
        *((_QWORD *)this + 67),
        (unsigned int)v40,
        v63);
    }
    v18 = *(DBI1 **)&v37.Data1;
    v16 = 0;
LABEL_52:
    v30 = *((_DWORD *)v18 + 238);
    DBI1::Close(v18);
    if ( v9 )
    {
      v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 64LL))(v43) & v16;
      v16 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&v61.Data1 + 64LL))(*(_QWORD *)&v61.Data1) & v31;
    }
    if ( v41 )
      v16 &= (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 112LL))(v41);
    if ( v35 )
    {
      v32 = (*(__int64 (__fastcall **)(struct PDB *))(*(_QWORD *)v35 + 80LL))(v35) & v16;
      v16 = (*(__int64 (__fastcall **)(struct PDB *))(*(_QWORD *)v35 + 88LL))(v35) & v32;
    }
    if ( !v16 )
      goto LABEL_67;
    if ( !v8 )
    {
      v33 = *((_DWORD *)this + 137);
      if ( *((_DWORD *)this + 136) < 0x1312E94u )
      {
        v37 = 0;
        v37.Data1 = v33;
      }
      else
      {
        v37 = *(struct _GUID *)((char *)this + 556);
      }
      v16 &= PDB1::patchSigAndAge(a2, v33, &v37, *((_DWORD *)this + 138), v30, v34, 0);
      if ( !v16 )
        goto LABEL_67;
    }
    v5 = (int (__high *(__high *)(void *, enum PCC))(void))v42;
LABEL_65:
    if ( (v36 & 0x10) != 0 )
      v16 = PDB1::eraseNamedStream(a2, v5, v44, (*((_BYTE *)this + 945) & 2) != 0);
LABEL_67:
    result = v16;
  }
  catch ( PDBErrors *v60 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v58 + 67) + 8LL))(
      *((_QWORD *)v58 + 67),
      *(unsigned int *)v60,
      0);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180030a90  push    rdi
0x180030a92  push    r12
0x180030a94  push    r13
0x180030a96  push    r14
0x180030a98  push    r15
0x180030a9a  mov     eax, 1170h
0x180030a9f  call    _alloca_probe
0x180030aa4  sub     rsp, rax
0x180030aa7  mov     [rsp+1198h+var_1060], 0FFFFFFFFFFFFFFFEh
0x180030ab3  mov     [rsp+1198h+arg_10], rbx
0x180030abb  mov     [rsp+1198h+arg_18], rsi
0x180030ac3  mov     rax, cs:__security_cookie
0x180030aca  xor     rax, rsp
0x180030acd  mov     [rsp+1198h+var_38], rax
0x180030ad5  mov     r13, r9
0x180030ad8  mov     [rsp+1198h+var_1110], r9
0x180030ae0  mov     [rsp+1198h+var_1148], r8d
0x180030ae5  mov     r12, rdx
0x180030ae8  mov     r14, rcx
0x180030aeb  mov     [rsp+1198h+var_1068], rcx
0x180030af3  mov     rax, [rsp+1198h+arg_20]
0x180030afb  mov     [rsp+1198h+var_1100], rax
0x180030b03  movzx   eax, r8b
0x180030b07  and     al, 1
0x180030b09  mov     [rsp+1198h+var_1158], al
0x180030b0d  mov     r15d, r8d
0x180030b10  and     r15d, 2
0x180030b14  mov     [rsp+1198h+var_1124], r15d
0x180030b19  mov     edi, r8d
0x180030b1c  and     edi, 20h
0x180030b1f  mov     [rsp+1198h+var_1128], edi
0x180030b23  test    al, al
0x180030b25  jnz     loc_180030C98
0x180030b2b  test    edi, edi
0x180030b2d  jnz     loc_180030C98
0x180030b33  xor     edx, edx; hFile
0x180030b35  mov     r8d, 8; dwFlags
0x180030b3b  lea     rcx, LibFileName; "kernel32.dll"
0x180030b42  call    cs:__imp_LoadLibraryExW
0x180030b48  test    rax, rax
0x180030b4b  jnz     short loc_180030B8A
0x180030b4d  xor     edx, edx; hFile
0x180030b4f  mov     r8d, 8; dwFlags
0x180030b55  lea     rcx, aApiMsWinCoreFi_0; "api-ms-win-core-file-l2-1-1.dll"
0x180030b5c  call    cs:__imp_LoadLibraryExW
0x180030b62  test    rax, rax
0x180030b65  jnz     short loc_180030B8A
0x180030b67  mov     rcx, [r14+218h]
0x180030b6e  mov     rax, [rcx]
0x180030b71  mov     r8, r12
0x180030b74  mov     edx, 18h
0x180030b79  mov     rax, [rax+8]
0x180030b7d  call    cs:__guard_dispatch_icall_fptr
0x180030b83  xor     eax, eax
0x180030b85  jmp     loc_1800311E7
0x180030b8a  lea     rdx, aCopyfileexw; "CopyFileExW"
0x180030b91  mov     rcx, rax; hModule
0x180030b94  call    cs:__imp_GetProcAddress
0x180030b9a  test    rax, rax
0x180030b9d  jnz     short loc_180030BC2
0x180030b9f  mov     rcx, [r14+218h]
0x180030ba6  mov     rax, [rcx]
0x180030ba9  mov     r8, r12
0x180030bac  mov     edx, 18h
0x180030bb1  mov     rax, [rax+8]
0x180030bb5  call    cs:__guard_dispatch_icall_fptr
0x180030bbb  xor     eax, eax
0x180030bbd  jmp     loc_1800311E7
0x180030bc2  lea     rcx, [r14+10h]
0x180030bc6  xor     ebx, ebx
0x180030bc8  mov     dword ptr [rsp+1198h+var_1170], ebx
0x180030bcc  mov     [rsp+1198h+var_1178], rbx
0x180030bd1  xor     r9d, r9d
0x180030bd4  xor     r8d, r8d
0x180030bd7  mov     rdx, r12
0x180030bda  call    cs:__guard_dispatch_icall_fptr
0x180030be0  test    eax, eax
0x180030be2  jns     short loc_180030C07
0x180030be4  mov     rcx, [r14+218h]
0x180030beb  mov     rax, [rcx]
0x180030bee  mov     r8, r12
0x180030bf1  mov     edx, 3
0x180030bf6  mov     rax, [rax+8]
0x180030bfa  call    cs:__guard_dispatch_icall_fptr
0x180030c00  xor     eax, eax
0x180030c02  jmp     loc_1800311E7
0x180030c07  mov     rcx, r12; lpFileName
0x180030c0a  call    cs:__imp_GetFileAttributesW
0x180030c10  test    al, 1
0x180030c12  jz      short loc_180030C22
0x180030c14  and     eax, 0FFFFFFFEh
0x180030c17  mov     edx, eax; dwFileAttributes
0x180030c19  mov     rcx, r12; lpFileName
0x180030c1c  call    cs:__imp_SetFileAttributesW
0x180030c22  test    r15d, r15d
0x180030c25  jz      short loc_180030C8E
0x180030c27  xorps   xmm0, xmm0
0x180030c2a  movups  xmmword ptr [rsp+1198h+var_1050.Data1], xmm0
0x180030c32  lea     rcx, [rsp+1198h+var_1050]; struct _GUID *
0x180030c3a  call    ?FUuidCreate@@YAHPEAU_GUID@@@Z; FUuidCreate(_GUID *)
0x180030c3f  test    eax, eax
0x180030c41  jz      loc_1800311E7
0x180030c47  movzx   ebx, byte ptr [r14+3B1h]
0x180030c4f  shr     bl, 1
0x180030c51  and     bl, 1
0x180030c54  xor     ecx, ecx; Time
0x180030c56  call    cs:__imp__time64
0x180030c5c  mov     rdx, rax; unsigned int
0x180030c5f  mov     [rsp+1198h+var_1168], bl; bool
0x180030c63  mov     byte ptr [rsp+1198h+var_1170], 0; bool
0x180030c68  mov     dword ptr [rsp+1198h+var_1178], 1; unsigned int
0x180030c70  mov     r9d, 1; unsigned int
0x180030c76  lea     r8, [rsp+1198h+var_1050]; struct _GUID *
0x180030c7e  mov     rcx, r12; wchar_t *
0x180030c81  call    ?patchSigAndAge@PDB1@@CAHPEB_WKAEBU_GUID@@KK_N2@Z; PDB1::patchSigAndAge(wchar_t const *,ulong,_GUID const &,ulong,ulong,bool,bool)
0x180030c86  test    eax, eax
0x180030c88  jz      loc_1800311E7
0x180030c8e  mov     esi, 1
0x180030c93  jmp     loc_1800311B6
0x180030c98  cmp     dword ptr [rcx+220h], 130BA2Ch
0x180030ca2  ja      short loc_180030CAB
0x180030ca4  xor     eax, eax
0x180030ca6  jmp     loc_1800311E7
0x180030cab  xor     ebx, ebx
0x180030cad  mov     qword ptr [rsp+1198h+var_1138.Data1], rbx
0x180030cb2  lea     r9, [rsp+1198h+var_1138]; struct DBI **
0x180030cb7  lea     r8, aR; "r"
0x180030cbe  xor     edx, edx; char *
0x180030cc0  call    ?OpenDBI@PDB1@@UEAAHPEBD0PEAPEAUDBI@@@Z; PDB1::OpenDBI(char const *,char const *,DBI * *)
0x180030cc5  test    eax, eax
0x180030cc7  jz      loc_1800311E7
0x180030ccd  mov     [rsp+1198h+var_1150], rbx
0x180030cd2  mov     r9d, cs:?cbPgPdbDef@@3JB; long const cbPgPdbDef
0x180030cd9  lea     r9d, ds:0[r9*4]; int
0x180030ce1  lea     rax, [rsp+1198h+var_1150]
0x180030ce6  mov     [rsp+1198h+var_1160], rax; struct PDB **
0x180030ceb  mov     qword ptr [rsp+1198h+var_1168], 400h; unsigned __int64
0x180030cf4  lea     rax, [rsp+1198h+var_838]
0x180030cfc  mov     [rsp+1198h+var_1170], rax; wchar_t *
0x180030d01  lea     rax, [rsp+1198h+var_1120]
0x180030d06  mov     [rsp+1198h+var_1178], rax; int *
0x180030d0b  xor     r8d, r8d; unsigned int
0x180030d0e  lea     rdx, aFwx; "fwx"
0x180030d15  mov     rcx, r12; lpFileName
0x180030d18  call    ?OpenEx2W@PDB1@@SAHPEB_WPEBDKJPEAJPEA_W_KPEAPEAUPDB@@@Z; PDB1::OpenEx2W(wchar_t const *,char const *,ulong,long,long *,wchar_t *,unsigned __int64,PDB * *)
0x180030d1d  mov     esi, eax
0x180030d1f  mov     [rsp+1198h+var_1118], rbx
0x180030d27  mov     qword ptr [rsp+1198h+var_1050.Data1], rbx
0x180030d2f  mov     [rsp+1198h+var_1108], rbx
0x180030d37  test    eax, eax
0x180030d39  jz      loc_18003108C
0x180030d3f  test    edi, edi
0x180030d41  jz      short loc_180030D95
0x180030d43  mov     rcx, [rsp+1198h+var_1150]
0x180030d48  mov     rax, [rcx]
0x180030d4b  lea     r8, [rsp+1198h+var_1050]
0x180030d53  lea     rdx, aW_0; "w"
0x180030d5a  mov     rax, [rax+40h]
0x180030d5e  call    cs:__guard_dispatch_icall_fptr
0x180030d64  test    eax, eax
0x180030d66  jz      loc_180031045
0x180030d6c  mov     rcx, [rsp+1198h+var_1150]
0x180030d71  mov     rax, [rcx]
0x180030d74  lea     r8, [rsp+1198h+var_1108]
0x180030d7c  lea     rdx, aW_0; "w"
0x180030d83  mov     rax, [rax+48h]
0x180030d87  call    cs:__guard_dispatch_icall_fptr
0x180030d8d  test    eax, eax
0x180030d8f  jz      loc_180031045
0x180030d95  mov     rcx, [rsp+1198h+var_1150]
0x180030d9a  mov     rax, [rcx]
0x180030d9d  lea     r8, [rsp+1198h+var_1118]
0x180030da5  xor     edx, edx
0x180030da7  mov     rax, [rax+30h]
0x180030dab  call    cs:__guard_dispatch_icall_fptr
0x180030db1  test    eax, eax
0x180030db3  jz      loc_180031045
0x180030db9  xorps   xmm0, xmm0
0x180030dbc  movdqa  [rsp+1198h+var_10D8], xmm0
0x180030dc5  xorps   xmm1, xmm1
0x180030dc8  movdqa  [rsp+1198h+var_10C8], xmm1
0x180030dd1  movdqa  [rsp+1198h+var_10B8], xmm0
0x180030dda  lea     rax, ??_7?$Array@VReadOnlySafeSpanPtr@@@pdb_internal@@6B@; const pdb_internal::Array<ReadOnlySafeSpanPtr>::`vftable'
0x180030de1  mov     [rsp+1198h+var_1080], rax
0x180030de9  mov     [rsp+1198h+var_1078], rbx
0x180030df1  mov     [rsp+1198h+var_1070], rbx
0x180030df9  mov     [rsp+1198h+var_10F8], r14
0x180030e01  mov     rax, [rsp+1198h+var_1150]
0x180030e06  mov     [rsp+1198h+var_10F0], rax
0x180030e0e  mov     r13, qword ptr [rsp+1198h+var_1138.Data1]
0x180030e13  mov     [rsp+1198h+var_10E8], r13
0x180030e1b  mov     rdi, [rsp+1198h+var_1118]
0x180030e23  mov     [rsp+1198h+var_10E0], rdi
0x180030e2b  mov     eax, [rsp+1198h+var_1148]
0x180030e2f  mov     [rsp+1198h+var_1098], eax
0x180030e36  mov     [rsp+1198h+var_1094], ebx
0x180030e3d  mov     rax, [rsp+1198h+var_1110]
0x180030e45  mov     [rsp+1198h+var_10A8], rax
0x180030e4d  mov     rax, [rsp+1198h+var_1100]
0x180030e55  mov     [rsp+1198h+var_10A0], rax
0x180030e5d  mov     [rsp+1198h+var_1090], rbx
0x180030e65  mov     [rsp+1198h+var_1088], bx
0x180030e6d  mov     rax, [rdi]
0x180030e70  mov     r15, [rax+160h]
0x180030e77  mov     rdx, [r13+0]
0x180030e7b  mov     rcx, r13
0x180030e7e  mov     rax, [rdx+158h]
0x180030e85  call    cs:__guard_dispatch_icall_fptr
0x180030e8b  movzx   edx, ax
0x180030e8e  mov     rcx, rdi
0x180030e91  mov     rax, r15
0x180030e94  call    cs:__guard_dispatch_icall_fptr
0x180030e9a  lea     rcx, [rsp+1198h+var_10F8]; this
0x180030ea2  call    ?CopyMods@PDBCopy@@AEAAHXZ; PDBCopy::CopyMods(void)
0x180030ea7  test    eax, eax
0x180030ea9  jz      short loc_180030EDE
0x180030eab  lea     rcx, [rsp+1198h+var_10F8]; this
0x180030eb3  call    ?CopyPublics@PDBCopy@@AEAAHXZ; PDBCopy::CopyPublics(void)
0x180030eb8  test    eax, eax
0x180030eba  jz      short loc_180030EDE
0x180030ebc  lea     rcx, [rsp+1198h+var_10F8]; this
0x180030ec4  call    ?CopySecMap@PDBCopy@@AEAAHXZ; PDBCopy::CopySecMap(void)
0x180030ec9  test    eax, eax
0x180030ecb  jz      short loc_180030EDE
0x180030ecd  lea     rcx, [rsp+1198h+var_10F8]; this
0x180030ed5  call    ?CopyDbg@PDBCopy@@AEAAHXZ; PDBCopy::CopyDbg(void)
0x180030eda  test    eax, eax
0x180030edc  jnz     short loc_180030F34
0x180030ede  mov     r8, [rsp+1198h+var_1090]
0x180030ee6  test    r8, r8
0x180030ee9  jz      short loc_180030F07
0x180030eeb  mov     edx, 400h
0x180030ef0  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180030ef7  lea     rcx, [rsp+1198h+var_1038]
0x180030eff  call    cs:__imp__o_wcsncpy_s
0x180030f05  jmp     short loc_180030F0F
0x180030f07  mov     [rsp+1198h+var_1038], bx
0x180030f0f  mov     rcx, [r14+218h]
0x180030f16  mov     rax, [rcx]
0x180030f19  lea     r8, [rsp+1198h+var_1038]
0x180030f21  mov     edx, [rsp+1198h+var_1094]
0x180030f28  mov     rax, [rax+8]
0x180030f2c  call    cs:__guard_dispatch_icall_fptr
0x180030f32  mov     esi, ebx
0x180030f34  mov     rdi, qword ptr [rsp+1198h+var_10D8]
0x180030f3c  mov     r15, qword ptr [rsp+1198h+var_10D8+8]
0x180030f44  cmp     rdi, r15
0x180030f47  jz      short loc_180030F71
0x180030f49  nop     dword ptr [rax+00000000h]
0x180030f50  mov     rcx, [rdi]
0x180030f53  test    rcx, rcx
0x180030f56  jz      short loc_180030F68
0x180030f58  mov     rax, [rcx]
0x180030f5b  mov     rax, [rax+80h]
0x180030f62  call    cs:__guard_dispatch_icall_fptr
0x180030f68  add     rdi, 8
0x180030f6c  cmp     rdi, r15
0x180030f6f  jnz     short loc_180030F50
0x180030f71  mov     rdi, qword ptr [rsp+1198h+var_10C8+8]
0x180030f79  mov     r15, qword ptr [rsp+1198h+var_10B8]
0x180030f81  cmp     rdi, r15
0x180030f84  jz      short loc_180030FA7
0x180030f86  mov     rcx, [rdi]
0x180030f89  test    rcx, rcx
0x180030f8c  jz      short loc_180030F9E
0x180030f8e  mov     rax, [rcx]
0x180030f91  mov     rax, [rax+80h]
0x180030f98  call    cs:__guard_dispatch_icall_fptr
0x180030f9e  add     rdi, 8
0x180030fa2  cmp     rdi, r15
0x180030fa5  jnz     short loc_180030F86
0x180030fa7  mov     rcx, [rsp+1198h+var_1090]; this
0x180030faf  test    rcx, rcx
0x180030fb2  jz      short loc_180030FB9
0x180030fb4  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x180030fb9  mov     r8d, dword ptr [rsp+1198h+var_1070]
0x180030fc1  mov     rdx, [rsp+1198h+var_1078]
0x180030fc9  test    r8d, r8d
0x180030fcc  jz      short loc_180031003
0x180030fce  xchg    ax, ax
0x180030fd0  mov     eax, ebx
0x180030fd2  mov     rcx, [rdx+rax*8]
0x180030fd6  test    rcx, rcx
0x180030fd9  jz      short loc_180030FFC
0x180030fdb  mov     rax, [rcx]
0x180030fde  mov     edx, 1
0x180030fe3  mov     rax, [rax]
0x180030fe6  call    cs:__guard_dispatch_icall_fptr
0x180030fec  mov     r8d, dword ptr [rsp+1198h+var_1070]
0x180030ff4  mov     rdx, [rsp+1198h+var_1078]
0x180030ffc  inc     ebx
0x180030ffe  cmp     ebx, r8d
0x180031001  jb      short loc_180030FD0
0x180031003  lea     rax, ??_7?$Array@VReadOnlySafeSpanPtr@@@pdb_internal@@6B@; const pdb_internal::Array<ReadOnlySafeSpanPtr>::`vftable'
0x18003100a  mov     [rsp+1198h+var_1080], rax
0x180031012  test    rdx, rdx
0x180031015  jz      short loc_18003101F
0x180031017  mov     rcx, rdx; this
0x18003101a  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x18003101f  lea     rcx, [rsp+1198h+var_10C8+8]
  ... truncated ...
```
