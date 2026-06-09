# WriteMiscInfo(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)

- ea: `0x18000e11c`
- end: `0x18000e430`
- name: `?WriteMiscInfo@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z`
- size: `788`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _MINIDUMP_STREAM_INFO *, struct _INTERNAL_PROCESS *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000c19c`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x18000780c`
- `0x18000bcbc`
- `0x18000e11c`
- `0x1800105e8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000e23d`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000e25c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000e23d`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000e25c`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18000e301`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18000e301`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000e279`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000e291`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000e2a9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000e279`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000e291`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000e2a9`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000e3fe`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000e3fe`

## string_xrefs

- `0x18000e236`: `api-ms-win-core-version-l1-1-0.dll`
- `0x18000e255`: `version.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WriteMiscInfo(
        struct _MINIDUMP_STATE *a1,
        struct _MINIDUMP_STREAM_INFO *a2,
        struct _INTERNAL_PROCESS *a3)
{
  unsigned __int16 v5; // r13
  int v6; // ecx
  FARPROC ProcAddress; // rdi
  FARPROC v8; // rsi
  FARPROC v9; // r14
  HMODULE Library; // rbx
  unsigned __int16 v11; // r15
  unsigned __int16 v12; // r12
  unsigned __int16 v13; // ax
  struct _MINIDUMP_STATE *v14; // rdi
  unsigned int v15; // edi
  unsigned __int16 *v17; // [rsp+30h] [rbp-D8h]
  __int64 v18; // [rsp+38h] [rbp-D0h]
  __int64 v19; // [rsp+40h] [rbp-C8h]
  unsigned __int16 v20[2]; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int16 v21; // [rsp+5Ch] [rbp-ACh] BYREF
  unsigned __int16 v22[2]; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int16 v23[2]; // [rsp+64h] [rbp-A4h] BYREF
  int v24; // [rsp+68h] [rbp-A0h] BYREF
  int v25; // [rsp+6Ch] [rbp-9Ch]
  HMODULE v26; // [rsp+70h] [rbp-98h] BYREF
  FARPROC v27; // [rsp+78h] [rbp-90h]
  FARPROC v28; // [rsp+80h] [rbp-88h]
  FARPROC v29; // [rsp+88h] [rbp-80h]
  struct _MINIDUMP_STATE *v30; // [rsp+90h] [rbp-78h]
  struct _MINIDUMP_STREAM_INFO *v31; // [rsp+98h] [rbp-70h]
  __int64 v32; // [rsp+A0h] [rbp-68h]
  int v33; // [rsp+A8h] [rbp-60h] BYREF
  int v34; // [rsp+ACh] [rbp-5Ch]
  unsigned int v35; // [rsp+B0h] [rbp-58h]
  int v36; // [rsp+B4h] [rbp-54h]
  int v37; // [rsp+B8h] [rbp-50h]
  int v38; // [rsp+BCh] [rbp-4Ch]
  int v39; // [rsp+C0h] [rbp-48h]
  int v40; // [rsp+C4h] [rbp-44h]
  int v41; // [rsp+C8h] [rbp-40h]
  int v42; // [rsp+CCh] [rbp-3Ch]
  int v43; // [rsp+D0h] [rbp-38h]
  _BYTE v44[520]; // [rsp+190h] [rbp+88h] BYREF
  wchar_t Buffer[312]; // [rsp+398h] [rbp+290h] BYREF
  WCHAR Filename[264]; // [rsp+608h] [rbp+500h] BYREF

  v32 = -2;
  v31 = a2;
  v30 = a1;
  v5 = 0;
  v24 = 0;
  memset_0(&v33, 0, 0x554u);
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, int *, int *, int, _QWORD, char *))(**((_QWORD **)a1 + 2) + 512LL))(
    *((_QWORD *)a1 + 2),
    *(_QWORD *)a1,
    v35,
    &v24,
    &v33,
    1364,
    0,
    (char *)a1 + 200);
  v6 = v24 | 1 | v34;
  v34 = v6;
  v35 = *(_DWORD *)a3;
  if ( *((_DWORD *)a3 + 5) )
  {
    v6 |= 2u;
    v34 = v6;
    v36 = *((_DWORD *)a3 + 6);
    v37 = *((_DWORD *)a3 + 7);
    v38 = *((_DWORD *)a3 + 8);
  }
  if ( *((_DWORD *)a3 + 9) )
  {
    v34 = v6 | 4;
    v39 = *((_DWORD *)a3 + 11);
    v40 = *((_DWORD *)a3 + 12);
    v41 = *((_DWORD *)a3 + 13);
    v42 = *((_DWORD *)a3 + 14);
    v43 = *((_DWORD *)a3 + 15);
  }
  ProcAddress = 0;
  v27 = 0;
  v8 = 0;
  v28 = 0;
  v9 = 0;
  v29 = 0;
  Library = LoadLibraryExW(L"api-ms-win-core-version-l1-1-0.dll", 0, 0);
  v26 = Library;
  if ( !Library )
  {
    Library = LoadLibraryExW(L"version.dll", 0, 0);
    v26 = Library;
  }
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetFileVersionInfoSizeExW");
    v27 = ProcAddress;
    v8 = GetProcAddress(Library, "GetFileVersionInfoExW");
    v28 = v8;
    v9 = GetProcAddress(Library, "VerQueryValueW");
    v29 = v9;
  }
  v11 = 0;
  v20[0] = 0;
  v12 = 0;
  v21 = 0;
  v22[0] = 0;
  v13 = 0;
  v25 = 0;
  v23[0] = 0;
  if ( Library && ProcAddress && v8 && v9 )
  {
    if ( GetModuleFileNameW((HMODULE)0x180000000LL, Filename, 0x104u) - 1 > 0x102 )
    {
      v13 = v25;
    }
    else
    {
      VersionQuery::GetModuleVersion((VersionQuery *)&v26, Filename, v20, &v21, v22, v23);
      v11 = v20[0];
      v12 = v21;
      v5 = v22[0];
      v13 = v23[0];
    }
  }
  LODWORD(v19) = v5;
  LODWORD(v18) = v12;
  LODWORD(v17) = v11;
  swprintf_s(Buffer, 0x28u, L"%ws.%ws,%u.%u.%u.%u", L"dbgcore", L"amd64", v17, v18, v19, v13);
  v14 = v30;
  if ( (*(int (__fastcall **)(_QWORD, _BYTE *, __int64))(**((_QWORD **)v30 + 2) + 480LL))(
         *((_QWORD *)v30 + 2),
         v44,
         260) >= 0 )
    v34 |= 0x100u;
  v33 = 1364;
  v15 = WriteAtOffset(v14, *((_DWORD *)v31 + 8), &v33, 0x554u);
  if ( Library )
    FreeLibrary(Library);
  return v15;
}

```

## disassembly

```asm
0x18000e11c  mov     rax, rsp
0x18000e11f  push    rbp
0x18000e120  push    rsi
0x18000e121  push    rdi
0x18000e122  push    r12
0x18000e124  push    r13
0x18000e126  push    r14
0x18000e128  push    r15
0x18000e12a  lea     rbp, [rax-758h]
0x18000e131  sub     rsp, 820h
0x18000e138  mov     [rbp+750h+var_7B8], 0FFFFFFFFFFFFFFFEh
0x18000e140  mov     [rax+20h], rbx
0x18000e144  mov     rax, cs:__security_cookie
0x18000e14b  xor     rax, rsp
0x18000e14e  mov     [rbp+750h+var_40], rax
0x18000e155  mov     rbx, r8
0x18000e158  mov     [rbp+750h+var_7C0], rdx
0x18000e15c  mov     rdi, rcx
0x18000e15f  mov     [rbp+750h+var_7C8], rcx
0x18000e163  xor     r13d, r13d
0x18000e166  mov     dword ptr [rsp+850h+var_7F0], r13d
0x18000e16b  mov     esi, 554h
0x18000e170  mov     r8d, esi; Size
0x18000e173  xor     edx, edx; Val
0x18000e175  lea     rcx, [rbp+750h+var_7B0]; void *
0x18000e179  call    memset_0
0x18000e17e  mov     r10, [rdi+10h]
0x18000e182  mov     rax, [r10]
0x18000e185  lea     rcx, [rdi+0C8h]
0x18000e18c  mov     qword ptr [rsp+850h+var_818], rcx
0x18000e191  mov     [rsp+850h+var_820], r13
0x18000e196  mov     dword ptr [rsp+850h+var_828], esi
0x18000e19a  lea     rcx, [rbp+750h+var_7B0]
0x18000e19e  mov     [rsp+850h+var_830], rcx
0x18000e1a3  lea     r9, [rsp+850h+var_7F0]
0x18000e1a8  mov     r8d, [rbp+750h+var_7A8]
0x18000e1ac  mov     rdx, [rdi]
0x18000e1af  mov     rcx, r10
0x18000e1b2  mov     rax, [rax+200h]
0x18000e1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1be  mov     eax, dword ptr [rsp+850h+var_7F0]
0x18000e1c2  or      eax, 1
0x18000e1c5  mov     ecx, [rbp+750h+var_7AC]
0x18000e1c8  or      ecx, eax
0x18000e1ca  mov     [rbp+750h+var_7AC], ecx
0x18000e1cd  mov     eax, [rbx]
0x18000e1cf  mov     [rbp+750h+var_7A8], eax
0x18000e1d2  cmp     [rbx+14h], r13d
0x18000e1d6  jz      short loc_18000E1F0
0x18000e1d8  or      ecx, 2
0x18000e1db  mov     [rbp+750h+var_7AC], ecx
0x18000e1de  mov     eax, [rbx+18h]
0x18000e1e1  mov     [rbp+750h+var_7A4], eax
0x18000e1e4  mov     eax, [rbx+1Ch]
0x18000e1e7  mov     [rbp+750h+var_7A0], eax
0x18000e1ea  mov     eax, [rbx+20h]
0x18000e1ed  mov     [rbp+750h+var_79C], eax
0x18000e1f0  cmp     [rbx+24h], r13d
0x18000e1f4  jz      short loc_18000E21A
0x18000e1f6  or      ecx, 4
0x18000e1f9  mov     [rbp+750h+var_7AC], ecx
0x18000e1fc  mov     eax, [rbx+2Ch]
0x18000e1ff  mov     [rbp+750h+var_798], eax
0x18000e202  mov     eax, [rbx+30h]
0x18000e205  mov     [rbp+750h+var_794], eax
0x18000e208  mov     eax, [rbx+34h]
0x18000e20b  mov     [rbp+750h+var_790], eax
0x18000e20e  mov     eax, [rbx+38h]
0x18000e211  mov     [rbp+750h+var_78C], eax
0x18000e214  mov     eax, [rbx+3Ch]
0x18000e217  mov     [rbp+750h+var_788], eax
0x18000e21a  mov     rdi, r13
0x18000e21d  mov     [rsp+850h+var_7E0], r13
0x18000e222  mov     rsi, r13
0x18000e225  mov     [rsp+850h+var_7D8], r13
0x18000e22a  mov     r14, r13
0x18000e22d  mov     [rbp+750h+var_7D0], r13
0x18000e231  xor     r8d, r8d; dwFlags
0x18000e234  xor     edx, edx; hFile
0x18000e236  lea     rcx, LibFileName; "api-ms-win-core-version-l1-1-0.dll"
0x18000e23d  call    cs:__imp_LoadLibraryExW
0x18000e243  mov     rbx, rax
0x18000e246  mov     [rsp+850h+var_7E8], rax
0x18000e24b  test    rax, rax
0x18000e24e  jnz     short loc_18000E26A
0x18000e250  xor     r8d, r8d; dwFlags
0x18000e253  xor     edx, edx; hFile
0x18000e255  lea     rcx, aVersionDll; "version.dll"
0x18000e25c  call    cs:__imp_LoadLibraryExW
0x18000e262  mov     rbx, rax
0x18000e265  mov     [rsp+850h+var_7E8], rax
0x18000e26a  test    rbx, rbx
0x18000e26d  jz      short loc_18000E2B6
0x18000e26f  lea     rdx, aGetfileversion_2; "GetFileVersionInfoSizeExW"
0x18000e276  mov     rcx, rbx; hModule
0x18000e279  call    cs:__imp_GetProcAddress
0x18000e27f  mov     rdi, rax
0x18000e282  mov     [rsp+850h+var_7E0], rax
0x18000e287  lea     rdx, aGetfileversion; "GetFileVersionInfoExW"
0x18000e28e  mov     rcx, rbx; hModule
0x18000e291  call    cs:__imp_GetProcAddress
0x18000e297  mov     rsi, rax
0x18000e29a  mov     [rsp+850h+var_7D8], rax
0x18000e29f  lea     rdx, aVerqueryvaluew; "VerQueryValueW"
0x18000e2a6  mov     rcx, rbx; hModule
0x18000e2a9  call    cs:__imp_GetProcAddress
0x18000e2af  mov     r14, rax
0x18000e2b2  mov     [rbp+750h+var_7D0], rax
0x18000e2b6  mov     r15d, r13d
0x18000e2b9  mov     [rsp+850h+var_800], r13w
0x18000e2bf  mov     r12d, r13d
0x18000e2c2  mov     [rsp+850h+var_7FC], r13w
0x18000e2c8  mov     [rsp+850h+var_7F8], r13w
0x18000e2ce  xor     eax, eax
0x18000e2d0  mov     dword ptr [rsp+850h+var_7F0+4], eax
0x18000e2d4  mov     [rsp+850h+var_7F4], ax
0x18000e2d9  test    rbx, rbx
0x18000e2dc  jz      short loc_18000E35C
0x18000e2de  test    rdi, rdi
0x18000e2e1  jz      short loc_18000E35C
0x18000e2e3  test    rsi, rsi
0x18000e2e6  jz      short loc_18000E35C
0x18000e2e8  test    r14, r14
0x18000e2eb  jz      short loc_18000E35C
0x18000e2ed  mov     r8d, 104h; nSize
0x18000e2f3  lea     rdx, [rbp+750h+Filename]; lpFilename
0x18000e2fa  lea     rcx, cs:180000000h; hModule
0x18000e301  call    cs:__imp_GetModuleFileNameW
0x18000e307  dec     eax
0x18000e309  cmp     eax, 102h
0x18000e30e  ja      short loc_18000E358
0x18000e310  lea     rax, [rsp+850h+var_7F4]
0x18000e315  mov     [rsp+850h+var_828], rax; unsigned __int16 *
0x18000e31a  lea     rax, [rsp+850h+var_7F8]
0x18000e31f  mov     [rsp+850h+var_830], rax; unsigned __int16 *
0x18000e324  lea     r9, [rsp+850h+var_7FC]; unsigned __int16 *
0x18000e329  lea     r8, [rsp+850h+var_800]; unsigned __int16 *
0x18000e32e  lea     rdx, [rbp+750h+Filename]; unsigned __int16 *
0x18000e335  lea     rcx, [rsp+850h+var_7E8]; this
0x18000e33a  call    ?GetModuleVersion@VersionQuery@@QEAA_NPEBGPEAG111@Z; VersionQuery::GetModuleVersion(ushort const *,ushort *,ushort *,ushort *,ushort *)
0x18000e33f  movzx   r15d, [rsp+850h+var_800]
0x18000e345  movzx   r12d, [rsp+850h+var_7FC]
0x18000e34b  movzx   r13d, [rsp+850h+var_7F8]
0x18000e351  movzx   eax, [rsp+850h+var_7F4]
0x18000e356  jmp     short loc_18000E35C
0x18000e358  mov     eax, dword ptr [rsp+850h+var_7F0+4]
0x18000e35c  movzx   eax, ax
0x18000e35f  movzx   ecx, r13w
0x18000e363  movzx   edx, r12w
0x18000e367  movzx   r9d, r15w
0x18000e36b  mov     [rsp+40h], eax
0x18000e36f  mov     [rsp+850h+var_818], ecx
0x18000e373  mov     dword ptr [rsp+850h+var_820], edx
0x18000e377  mov     dword ptr [rsp+850h+var_828], r9d
0x18000e37c  lea     rax, aAmd64; "amd64"
0x18000e383  mov     [rsp+850h+var_830], rax
0x18000e388  lea     r9, aDbgcore; "dbgcore"
0x18000e38f  lea     r8, aWsWsUUUU; "%ws.%ws,%u.%u.%u.%u"
0x18000e396  mov     edx, 28h ; '('; BufferCount
0x18000e39b  lea     rcx, [rbp+750h+Buffer]; Buffer
0x18000e3a2  call    swprintf_s
0x18000e3a7  mov     rdi, [rbp+750h+var_7C8]
0x18000e3ab  mov     rcx, [rdi+10h]
0x18000e3af  mov     rax, [rcx]
0x18000e3b2  mov     r8d, 104h
0x18000e3b8  lea     rdx, [rbp+750h+var_6C8]
0x18000e3bf  mov     rax, [rax+1E0h]
0x18000e3c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3cb  test    eax, eax
0x18000e3cd  js      short loc_18000E3D4
0x18000e3cf  bts     [rbp+750h+var_7AC], 8
0x18000e3d4  mov     [rbp+750h+var_7B0], 554h
0x18000e3db  mov     r9d, 554h; unsigned int
0x18000e3e1  lea     r8, [rbp+750h+var_7B0]; void *
0x18000e3e5  mov     rdx, [rbp+750h+var_7C0]
0x18000e3e9  mov     edx, [rdx+20h]; unsigned int
0x18000e3ec  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000e3ef  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000e3f4  mov     edi, eax
0x18000e3f6  test    rbx, rbx
0x18000e3f9  jz      short loc_18000E404
0x18000e3fb  mov     rcx, rbx; hLibModule
0x18000e3fe  call    cs:__imp_FreeLibrary
0x18000e404  mov     eax, edi
0x18000e406  mov     rcx, [rbp+750h+var_40]
0x18000e40d  xor     rcx, rsp; StackCookie
0x18000e410  call    __security_check_cookie
0x18000e415  mov     rbx, [rsp+850h+arg_18]
0x18000e41d  add     rsp, 820h
0x18000e424  pop     r15
0x18000e426  pop     r14
0x18000e428  pop     r13
0x18000e42a  pop     r12
0x18000e42c  pop     rdi
0x18000e42d  pop     rsi
0x18000e42e  pop     rbp
0x18000e42f  retn
```
