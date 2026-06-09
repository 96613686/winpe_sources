# RegDBRestore(ushort *)

- ea: `0x18000e890`
- end: `0x18000eaf1`
- name: `?RegDBRestore@@YAJPEAG@Z`
- size: `609`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000717c`
- `0x18000e890`
- `0x180018658`
- `0x180018844`
- `0x1800188d8`
- `0x180018a2c`
- `0x180055822`
- `0x180055880`
- `0x180055940`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ea8a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ea8a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e99b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e99b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e9bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e9bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eaa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eaa7`

## string_xrefs

- `0x18000e992`: `clbcatq.dll`
- `0x18000e9ad`: `OpenComponentLibraryEx`

## pseudocode

```c
signed int __fastcall RegDBRestore(unsigned __int16 *a1)
{
  signed int result; // eax
  unsigned __int16 *v3; // rbx
  __int64 v4; // r15
  __int64 v5; // rax
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  unsigned __int16 **v12; // rdi
  HMODULE Library; // rax
  HMODULE v14; // r14
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  signed int v17; // ebx
  int i; // edi
  unsigned __int16 *v19; // [rsp+30h] [rbp+0h] BYREF
  __int64 v20; // [rsp+38h] [rbp+8h] BYREF
  unsigned __int16 **v21; // [rsp+40h] [rbp+10h]
  _QWORD v22[16]; // [rsp+50h] [rbp+20h] BYREF

  v20 = 0;
  v19 = 0;
  if ( !(unsigned int)GetRegistrationDirectory(&v19) )
    return -2147024893;
  v3 = v19;
  result = _GetLatestVersion(v19, &v20);
  if ( (int)(result + 0x80000000) < 0 || result == -2147024894 )
  {
    v4 = 2;
    if ( v20 + 1 < 0xFFFFFFFFFFFFLL )
      v4 = v20 + 1;
    v5 = -1;
    do
      ++v5;
    while ( v3[v5] );
    v6 = (unsigned int)(v5 + 19);
    v7 = (unsigned int)v6;
    v6 *= 2LL;
    v8 = v6 + 15;
    if ( v6 + 15 < v6 )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = v8 & 0xFFFFFFFFFFFFFFF0uLL;
    v10 = alloca(v9);
    v11 = alloca(v9);
    v12 = &v19;
    v21 = &v19;
    result = StringCchPrintfW((unsigned __int16 *)&v19, v7, L"%s\\R%012I64x.clb", v3, v4);
    if ( result >= 0 )
    {
      Library = LoadLibraryExW(L"clbcatq.dll", 0, 0);
      v14 = Library;
      if ( !Library )
        goto LABEL_31;
      v19 = 0;
      ProcAddress = GetProcAddress(Library, "OpenComponentLibraryEx");
      if ( ProcAddress )
      {
        v17 = ((__int64 (__fastcall *)(unsigned __int16 *, __int64, unsigned __int16 **))ProcAddress)(a1, 131073, &v19);
        if ( v17 < 0 )
        {
          if ( v17 == -2147217391 )
            v17 = -2147217387;
        }
        else
        {
          LODWORD(v20) = 0;
          v17 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64, __int64 *, _QWORD *))(*(_QWORD *)v19 + 376LL))(
                  v19,
                  5,
                  &v20,
                  v22);
          if ( v17 >= 0 )
          {
            for ( i = 0; i < (int)v20; ++i )
            {
              if ( !memcmp_0(&v22[3 * i], &SCHEMA_COMReg, 0x10u) )
              {
                if ( LODWORD(v22[3 * i + 2]) == 14 )
                  goto LABEL_24;
                break;
              }
            }
            v17 = -2147467259;
LABEL_24:
            v12 = v21;
          }
          (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v19 + 16LL))(v19);
        }
      }
      else
      {
        LastError = GetLastError();
        v17 = LastError;
        if ( LastError > 0 )
          v17 = (unsigned __int16)LastError | 0x80070000;
      }
      FreeLibrary(v14);
      if ( v17 < 0 )
        return v17;
      if ( (unsigned int)InternalCopyFileW(a1, (const unsigned __int16 *)v12) )
      {
        return SetRegDbVersionInRegistryInternal(v4);
      }
      else
      {
LABEL_31:
        result = GetLastError();
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e890  push    rbp
0x18000e892  push    r12
0x18000e894  push    r13
0x18000e896  push    r14
0x18000e898  push    r15
0x18000e89a  sub     rsp, 0E0h
0x18000e8a1  lea     rbp, [rsp+30h]
0x18000e8a6  mov     [rbp+0D0h+arg_8], rbx
0x18000e8ad  mov     [rbp+0D0h+arg_10], rdi
0x18000e8b4  mov     rax, cs:__security_cookie
0x18000e8bb  xor     rax, rbp
0x18000e8be  mov     [rbp+0D0h+var_30], rax
0x18000e8c5  mov     r13, rcx
0x18000e8c8  xor     r12d, r12d
0x18000e8cb  lea     rcx, [rbp+0D0h+var_D0]
0x18000e8cf  mov     [rbp+0D0h+var_C8], r12
0x18000e8d3  mov     [rbp+0D0h+var_D0], r12
0x18000e8d7  call    _GetRegistrationDirectory
0x18000e8dc  test    eax, eax
0x18000e8de  jnz     short loc_18000E8EA
0x18000e8e0  mov     eax, 80070003h
0x18000e8e5  jmp     loc_18000EAC3
0x18000e8ea  mov     rbx, [rbp+0D0h+var_D0]
0x18000e8ee  lea     rdx, [rbp+0D0h+var_C8]; __int64 *
0x18000e8f2  mov     rcx, rbx; unsigned __int16 *
0x18000e8f5  call    ?_GetLatestVersion@@YAJPEBGPEA_J@Z; _GetLatestVersion(ushort const *,__int64 *)
0x18000e8fa  mov     edx, 80000000h
0x18000e8ff  lea     ecx, [rax+rdx]
0x18000e902  test    edx, ecx
0x18000e904  jnz     short loc_18000E911
0x18000e906  cmp     eax, 80070002h
0x18000e90b  jnz     loc_18000EAC3
0x18000e911  mov     rax, [rbp+0D0h+var_C8]
0x18000e915  mov     rcx, 0FFFFFFFFFFFFh
0x18000e91f  inc     rax
0x18000e922  mov     r15d, 2
0x18000e928  cmp     rax, rcx
0x18000e92b  cmovl   r15, rax
0x18000e92f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e933  inc     rax
0x18000e936  cmp     [rbx+rax*2], r12w
0x18000e93b  jnz     short loc_18000E933
0x18000e93d  add     eax, 13h
0x18000e940  mov     edx, eax
0x18000e942  add     rax, rax
0x18000e945  lea     rcx, [rax+0Fh]
0x18000e949  cmp     rcx, rax
0x18000e94c  ja      short loc_18000E958
0x18000e94e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000e958  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000e95c  mov     rax, rcx
0x18000e95f  call    _alloca_probe
0x18000e964  sub     rsp, rcx
0x18000e967  lea     r8, aSR012i64xClb; "%s\\R%012I64x.clb"
0x18000e96e  mov     r9, rbx
0x18000e971  lea     rdi, [rsp+100h+var_D0]
0x18000e976  mov     [rsp+100h+var_E0], r15
0x18000e97b  mov     rcx, rdi; unsigned __int16 *
0x18000e97e  mov     [rbp+0D0h+var_C0], rdi
0x18000e982  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e987  test    eax, eax
0x18000e989  js      loc_18000EAC3
0x18000e98f  xor     r8d, r8d; dwFlags
0x18000e992  lea     rcx, aClbcatqDll_0; "clbcatq.dll"
0x18000e999  xor     edx, edx; hFile
0x18000e99b  call    cs:__imp_LoadLibraryExW
0x18000e9a1  mov     r14, rax
0x18000e9a4  test    rax, rax
0x18000e9a7  jz      loc_18000EAA7
0x18000e9ad  lea     rdx, ProcName; "OpenComponentLibraryEx"
0x18000e9b4  mov     [rbp+0D0h+var_D0], r12
0x18000e9b8  mov     rcx, rax; hModule
0x18000e9bb  call    cs:__imp_GetProcAddress
0x18000e9c1  test    rax, rax
0x18000e9c4  jnz     short loc_18000E9E4
0x18000e9c6  call    cs:__imp_GetLastError
0x18000e9cc  mov     ebx, eax
0x18000e9ce  test    eax, eax
0x18000e9d0  jle     loc_18000EA87
0x18000e9d6  movzx   ebx, ax
0x18000e9d9  or      ebx, 80070000h
0x18000e9df  jmp     loc_18000EA87
0x18000e9e4  lea     r8, [rbp+0D0h+var_D0]
0x18000e9e8  mov     edx, 20001h
0x18000e9ed  mov     rcx, r13
0x18000e9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9f5  mov     ebx, eax
0x18000e9f7  test    eax, eax
0x18000e9f9  js      short loc_18000EA79
0x18000e9fb  mov     rcx, [rbp+0D0h+var_D0]
0x18000e9ff  lea     r9, [rbp+0D0h+var_B0]
0x18000ea03  mov     dword ptr [rbp+0D0h+var_C8], r12d
0x18000ea07  lea     r8, [rbp+0D0h+var_C8]
0x18000ea0b  mov     edx, 5
0x18000ea10  mov     rax, [rcx]
0x18000ea13  mov     rax, [rax+178h]
0x18000ea1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea1f  mov     ebx, eax
0x18000ea21  test    eax, eax
0x18000ea23  js      short loc_18000EA67
0x18000ea25  mov     edi, r12d
0x18000ea28  cmp     edi, dword ptr [rbp+0D0h+var_C8]
0x18000ea2b  jge     short loc_18000EA5E
0x18000ea2d  movsxd  rcx, edi
0x18000ea30  lea     rdx, ?SCHEMA_COMReg@@3U_GUID@@B; Buf2
0x18000ea37  mov     r8d, 10h; Size
0x18000ea3d  lea     r12, [rcx+rcx*2]
0x18000ea41  lea     rcx, [rbp+0D0h+var_B0]
0x18000ea45  lea     rcx, [rcx+r12*8]; Buf1
0x18000ea49  call    memcmp_0
0x18000ea4e  test    eax, eax
0x18000ea50  jz      short loc_18000EA56
0x18000ea52  inc     edi
0x18000ea54  jmp     short loc_18000EA28
0x18000ea56  cmp     [rbp+r12*8+0D0h+var_A0], 0Eh
0x18000ea5c  jz      short loc_18000EA63
0x18000ea5e  mov     ebx, 80004005h
0x18000ea63  mov     rdi, [rbp+0D0h+var_C0]
0x18000ea67  mov     rcx, [rbp+0D0h+var_D0]
0x18000ea6b  mov     rax, [rcx]
0x18000ea6e  mov     rax, [rax+10h]
0x18000ea72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea77  jmp     short loc_18000EA87
0x18000ea79  cmp     ebx, 80041011h
0x18000ea7f  mov     eax, 80041015h
0x18000ea84  cmovz   ebx, eax
0x18000ea87  mov     rcx, r14; hLibModule
0x18000ea8a  call    cs:__imp_FreeLibrary
0x18000ea90  test    ebx, ebx
0x18000ea92  jns     short loc_18000EA98
0x18000ea94  mov     eax, ebx
0x18000ea96  jmp     short loc_18000EAC3
0x18000ea98  mov     rdx, rdi; unsigned __int16 *
0x18000ea9b  mov     rcx, r13; unsigned __int16 *
0x18000ea9e  call    ?InternalCopyFileW@@YAHPEBG0K@Z; InternalCopyFileW(ushort const *,ushort const *,ulong)
0x18000eaa3  test    eax, eax
0x18000eaa5  jnz     short loc_18000EABB
0x18000eaa7  call    cs:__imp_GetLastError
0x18000eaad  test    eax, eax
0x18000eaaf  jle     short loc_18000EAC3
0x18000eab1  movzx   eax, ax
0x18000eab4  or      eax, 80070000h
0x18000eab9  jmp     short loc_18000EAC3
0x18000eabb  mov     rcx, r15; __int64
0x18000eabe  call    ?SetRegDbVersionInRegistryInternal@@YAJ_J@Z; SetRegDbVersionInRegistryInternal(__int64)
0x18000eac3  mov     rcx, [rbp+0D0h+var_30]
0x18000eaca  xor     rcx, rbp; StackCookie
0x18000eacd  call    __security_check_cookie
0x18000ead2  mov     rbx, [rbp+0D0h+arg_8]
0x18000ead9  mov     rdi, [rbp+0D0h+arg_10]
0x18000eae0  lea     rsp, [rbp+0B0h]
0x18000eae7  pop     r15
0x18000eae9  pop     r14
0x18000eaeb  pop     r13
0x18000eaed  pop     r12
0x18000eaef  pop     rbp
0x18000eaf0  retn
```
