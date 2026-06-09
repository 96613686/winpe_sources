# GetForestName(ushort *,ushort * *)

- ea: `0x180026300`
- end: `0x180026560`
- name: `?GetForestName@@YAJPEAGPEAPEAG@Z`
- size: `608`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180025a10`

## callees

- `0x180001290`
- `0x180004654`
- `0x180015438`
- `0x180026300`
- `0x18005bd72`
- `0x18005bdc0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002639a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002639a`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExA` at `0x180026364`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExA` at `0x180026364`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800263c8`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800263e5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800263c8`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800263e5`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18002651e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18002651e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180026387`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180026387`

## string_xrefs

- `0x180026380`: `netapi32.dll`

## pseudocode

```c
__int64 __fastcall GetForestName(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  HMODULE v5; // rsi
  void (*ProcAddress)(void); // r15
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  FARPROC v9; // rax
  _WORD *v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  signed __int64 v13; // r14
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rcx
  unsigned __int16 *v16; // rax
  __int64 v18; // [rsp+40h] [rbp-108h] BYREF
  int v19; // [rsp+48h] [rbp-100h]
  HMODULE v20; // [rsp+50h] [rbp-F8h]
  void (*v21)(void); // [rsp+58h] [rbp-F0h]
  __int64 v22; // [rsp+60h] [rbp-E8h]
  _OSVERSIONINFOA VersionInformation; // [rsp+70h] [rbp-D8h] BYREF

  v22 = -2;
  v4 = 0;
  v18 = 0;
  v5 = 0;
  ProcAddress = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x90u);
  VersionInformation.dwOSVersionInfoSize = 148;
  if ( GetVersionExA(&VersionInformation) && VersionInformation.dwPlatformId == 2 )
  {
    LibraryW = LoadLibraryW(L"netapi32.dll");
    v5 = LibraryW;
    v20 = LibraryW;
    if ( LibraryW
      && (ProcAddress = (void (*)(void))GetProcAddress(LibraryW, "NetApiBufferFree"), (v21 = ProcAddress) != 0)
      && (v9 = GetProcAddress(v5, "DsGetDcNameW")) != 0
      && !((unsigned int (__fastcall *)(_QWORD, unsigned __int16 *, _QWORD, _QWORD, _DWORD, __int64 *))v9)(
            0,
            a1,
            0,
            0,
            0,
            &v18) )
    {
      if ( !v18 )
      {
LABEL_28:
        FreeLibrary(v5);
        return v4;
      }
      v10 = *(_WORD **)(v18 + 48);
      if ( v10 )
      {
        v11 = 0x7FFFFFFF;
        do
        {
          if ( !*v10 )
            break;
          ++v10;
          --v11;
        }
        while ( v11 );
        v4 = v11 == 0 ? 0x80070057 : 0;
        v12 = (0x7FFFFFFF - v11) & ((unsigned __int128)-(__int128)(unsigned __int64)v11 >> 64);
        if ( v11 )
        {
          try
          {
            v13 = v12 + 1;
            if ( v12 + 1 < v12 )
              SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
            if ( v13 < 0 )
              SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
            v14 = 2LL * (unsigned int)v13;
            v15 = HIDWORD(v13) << 33;
            if ( v15 + v14 < v14 )
              SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
            if ( v15 + v14 )
            {
              v16 = (unsigned __int16 *)operator new[](saturated_mul(v13, 2u));
              *a2 = v16;
              if ( v16 )
                v4 = StringCchCopyW(v16, v13, *(const unsigned __int16 **)(v18 + 48));
              else
                v4 = -2147024882;
            }
          }
          catch ( SafeIntException )
          {
            v19 = -2147467259;
            v4 = -2147467259;
            v5 = v20;
            ProcAddress = v21;
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( (v4 & 0x80000000) == 0 )
        v4 = -2147467259;
    }
  }
  if ( v18 )
    ProcAddress();
  if ( v5 )
    goto LABEL_28;
  return v4;
}

```

## disassembly

```asm
0x180026300  mov     rax, rsp
0x180026303  push    rsi
0x180026304  push    rdi
0x180026305  push    r12
0x180026307  push    r14
0x180026309  push    r15
0x18002630b  sub     rsp, 120h
0x180026312  mov     [rsp+148h+var_E8], 0FFFFFFFFFFFFFFFEh
0x18002631b  mov     [rax+18h], rbx
0x18002631f  mov     rax, cs:__security_cookie
0x180026326  xor     rax, rsp
0x180026329  mov     [rsp+148h+var_38], rax
0x180026331  mov     r12, rdx
0x180026334  mov     r14, rcx
0x180026337  xor     edi, edi
0x180026339  mov     ebx, edi
0x18002633b  mov     [rsp+148h+var_108], rdi
0x180026340  mov     esi, edi
0x180026342  mov     r15d, edi
0x180026345  xor     edx, edx; Val
0x180026347  mov     r8d, 90h; Size
0x18002634d  lea     rcx, [rsp+148h+VersionInformation.dwMajorVersion]; void *
0x180026352  call    memset_0
0x180026357  mov     [rsp+148h+VersionInformation.dwOSVersionInfoSize], 94h
0x18002635f  lea     rcx, [rsp+148h+VersionInformation]; lpVersionInformation
0x180026364  call    cs:__imp_GetVersionExA
0x18002636a  test    eax, eax
0x18002636c  jz      loc_180026504
0x180026372  cmp     [rsp+148h+VersionInformation.dwPlatformId], 2
0x18002637a  jnz     loc_180026504
0x180026380  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x180026387  call    cs:__imp_LoadLibraryW
0x18002638d  mov     rsi, rax
0x180026390  mov     [rsp+148h+var_F8], rax
0x180026395  test    rax, rax
0x180026398  jnz     short loc_1800263BE
0x18002639a  call    cs:__imp_GetLastError
0x1800263a0  mov     ebx, eax
0x1800263a2  test    eax, eax
0x1800263a4  jle     short loc_1800263AF
0x1800263a6  movzx   ebx, ax
0x1800263a9  or      ebx, 80070000h
0x1800263af  mov     eax, 80004005h
0x1800263b4  test    ebx, ebx
0x1800263b6  cmovns  ebx, eax
0x1800263b9  jmp     loc_180026504
0x1800263be  lea     rdx, aNetapibufferfr; "NetApiBufferFree"
0x1800263c5  mov     rcx, rsi; hModule
0x1800263c8  call    cs:__imp_GetProcAddress
0x1800263ce  mov     r15, rax
0x1800263d1  mov     [rsp+148h+var_F0], rax
0x1800263d6  test    rax, rax
0x1800263d9  jz      short loc_18002639A
0x1800263db  lea     rdx, aDsgetdcnamew; "DsGetDcNameW"
0x1800263e2  mov     rcx, rsi; hModule
0x1800263e5  call    cs:__imp_GetProcAddress
0x1800263eb  test    rax, rax
0x1800263ee  jz      short loc_18002639A
0x1800263f0  lea     rcx, [rsp+148h+var_108]
0x1800263f5  mov     [rsp+148h+var_120], rcx
0x1800263fa  mov     [rsp+148h+var_128], edi
0x1800263fe  xor     r9d, r9d
0x180026401  xor     r8d, r8d
0x180026404  mov     rdx, r14
0x180026407  xor     ecx, ecx
0x180026409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002640e  test    eax, eax
0x180026410  jnz     short loc_18002639A
0x180026412  mov     rcx, [rsp+148h+var_108]
0x180026417  test    rcx, rcx
0x18002641a  jz      loc_18002651B
0x180026420  mov     rax, [rcx+30h]
0x180026424  test    rax, rax
0x180026427  jz      loc_180026504
0x18002642d  mov     r8d, 7FFFFFFFh
0x180026433  mov     ecx, r8d
0x180026436  cmp     [rax], di
0x180026439  jz      short loc_180026445
0x18002643b  add     rax, 2
0x18002643f  sub     rcx, 1
0x180026443  jnz     short loc_180026436
0x180026445  mov     rax, rcx
0x180026448  neg     rax
0x18002644b  sbb     ebx, ebx
0x18002644d  not     ebx
0x18002644f  and     ebx, 80070057h
0x180026455  mov     rax, rcx
0x180026458  sub     r8, rcx
0x18002645b  neg     rax
0x18002645e  sbb     rdx, rdx
0x180026461  and     rdx, r8
0x180026464  test    rcx, rcx
0x180026467  jnz     short loc_18002646E
0x180026469  jmp     loc_180026504
0x18002646e  lea     r14, [rdx+1]
0x180026472  cmp     r14, rdx
0x180026475  jb      loc_18002654E
0x18002647b  mov     rcx, r14
0x18002647e  shr     rcx, 20h
0x180026482  mov     rax, rcx
0x180026485  shr     rax, 1Fh
0x180026489  test    eax, eax
0x18002648b  jnz     loc_180026554
0x180026491  mov     eax, r14d
0x180026494  add     rax, rax
0x180026497  shl     rcx, 21h
0x18002649b  lea     rdx, [rcx+rax]
0x18002649f  cmp     rdx, rax
0x1800264a2  jb      loc_180026559
0x1800264a8  test    rdx, rdx
0x1800264ab  jz      short loc_1800264F4
0x1800264ad  mov     eax, 2
0x1800264b2  mul     r14
0x1800264b5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800264bc  cmovb   rax, rcx
0x1800264c0  mov     rcx, rax; unsigned __int64
0x1800264c3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800264c8  mov     [r12], rax
0x1800264cc  test    rax, rax
0x1800264cf  jnz     short loc_1800264D8
0x1800264d1  mov     ebx, 8007000Eh
0x1800264d6  jmp     short loc_180026504
0x1800264d8  mov     r8, [rsp+148h+var_108]
0x1800264dd  mov     r8, [r8+30h]; unsigned __int16 *
0x1800264e1  mov     rdx, r14; unsigned __int64
0x1800264e4  mov     rcx, rax; unsigned __int16 *
0x1800264e7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800264ec  mov     ebx, eax
0x1800264ee  test    eax, eax
0x1800264f0  jns     short loc_1800264F4
0x1800264f2  jmp     short loc_180026504
0x1800264f4  jmp     short loc_180026504
0x1800264f6  mov     ebx, [rsp+148h+var_100]
0x1800264fa  mov     rsi, [rsp+148h+var_F8]
0x1800264ff  mov     r15, [rsp+148h+var_F0]
0x180026504  mov     rcx, [rsp+148h+var_108]
0x180026509  test    rcx, rcx
0x18002650c  jz      short loc_180026516
0x18002650e  mov     rax, r15
0x180026511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026516  test    rsi, rsi
0x180026519  jz      short loc_180026524
0x18002651b  mov     rcx, rsi; hLibModule
0x18002651e  call    cs:__imp_FreeLibrary
0x180026524  mov     eax, ebx
0x180026526  mov     rcx, [rsp+148h+var_38]
0x18002652e  xor     rcx, rsp; StackCookie
0x180026531  call    __security_check_cookie
0x180026536  mov     rbx, [rsp+148h+arg_10]
0x18002653e  add     rsp, 120h
0x180026545  pop     r15
0x180026547  pop     r14
0x180026549  pop     r12
0x18002654b  pop     rdi
0x18002654c  pop     rsi
0x18002654d  retn
0x18002654e  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180026554  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180026559  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
