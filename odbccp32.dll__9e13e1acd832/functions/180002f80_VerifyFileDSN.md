# VerifyFileDSN

- ea: `0x180002f80`
- end: `0x180003229`
- name: `VerifyFileDSN`
- size: `681`
- prototype: `__int64 __fastcall(HWND hWnd, __int64, __int16, __int16)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000295c`
- `0x18000c440`

## callees

- `0x180002f80`
- `0x18000b784`
- `0x180013c7c`
- `0x180013f00`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800031e7`
- `KERNEL32!GetLastError` at `0x1800031e7`
- `KERNEL32!FreeLibrary` at `0x1800031df`
- `KERNEL32!FreeLibrary` at `0x1800031df`
- `KERNEL32!GetProcAddress` at `0x180002fee`
- `KERNEL32!GetProcAddress` at `0x180003002`
- `KERNEL32!GetProcAddress` at `0x180003016`
- `KERNEL32!GetProcAddress` at `0x18000302a`
- `KERNEL32!GetProcAddress` at `0x18000303d`
- `KERNEL32!GetProcAddress` at `0x180003050`
- `KERNEL32!GetProcAddress` at `0x180003063`
- `KERNEL32!GetProcAddress` at `0x180002fee`
- `KERNEL32!GetProcAddress` at `0x180003002`
- `KERNEL32!GetProcAddress` at `0x180003016`
- `KERNEL32!GetProcAddress` at `0x18000302a`
- `KERNEL32!GetProcAddress` at `0x18000303d`
- `KERNEL32!GetProcAddress` at `0x180003050`
- `KERNEL32!GetProcAddress` at `0x180003063`

## string_xrefs

- `0x180002fcc`: `ODBC32.DLL`
- `0x1800031ed`: `ODBC32.DLL`

## pseudocode

```c
__int64 __fastcall VerifyFileDSN(HWND hWnd, __int64 a2, __int16 a3, __int16 a4)
{
  unsigned __int16 v5; // bx
  __int64 v6; // rdx
  __int64 v7; // r9
  HMODULE LibraryPD; // rax
  HMODULE v9; // rdi
  FARPROC v10; // r14
  FARPROC v11; // rsi
  FARPROC v12; // r15
  FARPROC v13; // r12
  DWORD LastError; // eax
  __int64 v16; // [rsp+50h] [rbp-30h] BYREF
  __int64 v17; // [rsp+58h] [rbp-28h] BYREF
  FARPROC v18; // [rsp+60h] [rbp-20h]
  FARPROC ProcAddress; // [rsp+68h] [rbp-18h]
  FARPROC v20; // [rsp+70h] [rbp-10h]

  v5 = -1;
  v17 = 0;
  v16 = 0;
  PrivateDriverRootInitialized((HMODULE)hinst);
  LibraryPD = LoadLibraryPD(L"ODBC32.DLL", v6, 2048, v7);
  v9 = LibraryPD;
  if ( !LibraryPD )
  {
    LastError = GetLastError();
    CpanelError(hWnd, 0x691u, 0x730u, (__int64)L"ODBC32.DLL", LastError);
    return v5;
  }
  ProcAddress = GetProcAddress(LibraryPD, "SQLAllocHandle");
  v18 = GetProcAddress(v9, "SQLSetEnvAttr");
  v20 = GetProcAddress(v9, "ODBCInternalConnectW");
  v10 = GetProcAddress(v9, "SQLDisconnect");
  v11 = GetProcAddress(v9, "SQLFreeHandle");
  v12 = GetProcAddress(v9, "SearchStatusCode");
  v13 = GetProcAddress(v9, "LockHandle");
  if ( ProcAddress
    && v18
    && v20
    && v10
    && v11
    && v12
    && v13
    && (((__int64 (__fastcall *)(__int64, _QWORD, __int64 *))ProcAddress)(1, 0, &v17) & 0xFFFE) == 0 )
  {
    ((void (__fastcall *)(__int64, __int64, __int64, _QWORD))v18)(v17, 200, 380, 0);
    if ( (((__int64 (__fastcall *)(__int64, __int64, __int64 *))ProcAddress)(2, v17, &v16) & 0xFFFE) != 0 )
    {
LABEL_18:
      ((void (__fastcall *)(__int64, __int64))v11)(1, v17);
      goto LABEL_19;
    }
    v5 = ((__int64 (__fastcall *)(__int64, HWND, __int64, __int64, _QWORD, _WORD, _QWORD, __int16, __int16))v20)(
           v16,
           hWnd,
           a2,
           4294967293LL,
           0,
           0,
           0,
           a3,
           a4);
    if ( v5 == 1 )
    {
      ((void (__fastcall *)(__int64, __int64, __int64))v13)(v16, 2, 1);
      if ( !((unsigned __int16 (__fastcall *)(__int64, const wchar_t *))v12)(v16, L"HY000") )
        v5 = ((unsigned __int16 (__fastcall *)(__int64, const wchar_t *))v12)(v16, L"S1000") != 0;
      ((void (__fastcall *)(__int64, __int64))v13)(v16, 2);
    }
    else if ( v5 )
    {
LABEL_17:
      ((void (__fastcall *)(__int64, __int64))v11)(2, v16);
      goto LABEL_18;
    }
    ((void (__fastcall *)(__int64))v10)(v16);
    goto LABEL_17;
  }
LABEL_19:
  FreeLibrary(v9);
  return v5;
}

```

## disassembly

```asm
0x180002f80  mov     rax, rsp
0x180002f83  mov     [rax+8], rbx
0x180002f87  mov     [rax+20h], r9w
0x180002f8c  mov     [rax+18h], r8w
0x180002f91  mov     [rax+10h], rdx
0x180002f95  push    rbp
0x180002f96  push    rsi
0x180002f97  push    rdi
0x180002f98  push    r12
0x180002f9a  push    r13
0x180002f9c  push    r14
0x180002f9e  push    r15
0x180002fa0  mov     rbp, rsp
0x180002fa3  sub     rsp, 80h
0x180002faa  mov     r13, rcx
0x180002fad  xor     esi, esi
0x180002faf  mov     rcx, cs:hinst
0x180002fb6  or      ebx, 0FFFFFFFFh
0x180002fb9  mov     [rbp+var_28], rsi
0x180002fbd  mov     [rbp+var_30], rsi
0x180002fc1  call    PrivateDriverRootInitialized
0x180002fc6  mov     r8d, 800h
0x180002fcc  lea     rcx, aOdbc32Dll; "ODBC32.DLL"
0x180002fd3  call    LoadLibraryPD
0x180002fd8  mov     rdi, rax
0x180002fdb  test    rax, rax
0x180002fde  jz      loc_1800031E7
0x180002fe4  lea     rdx, ProcName; "SQLAllocHandle"
0x180002feb  mov     rcx, rax; hModule
0x180002fee  call    cs:__imp_GetProcAddress
0x180002ff4  lea     rdx, aSqlsetenvattr; "SQLSetEnvAttr"
0x180002ffb  mov     rcx, rdi; hModule
0x180002ffe  mov     [rbp+var_18], rax
0x180003002  call    cs:__imp_GetProcAddress
0x180003008  lea     rdx, aOdbcinternalco; "ODBCInternalConnectW"
0x18000300f  mov     rcx, rdi; hModule
0x180003012  mov     [rbp+var_20], rax
0x180003016  call    cs:__imp_GetProcAddress
0x18000301c  lea     rdx, aSqldisconnect; "SQLDisconnect"
0x180003023  mov     rcx, rdi; hModule
0x180003026  mov     [rbp+var_10], rax
0x18000302a  call    cs:__imp_GetProcAddress
0x180003030  lea     rdx, aSqlfreehandle; "SQLFreeHandle"
0x180003037  mov     rcx, rdi; hModule
0x18000303a  mov     r14, rax
0x18000303d  call    cs:__imp_GetProcAddress
0x180003043  lea     rdx, aSearchstatusco; "SearchStatusCode"
0x18000304a  mov     rcx, rdi; hModule
0x18000304d  mov     rsi, rax
0x180003050  call    cs:__imp_GetProcAddress
0x180003056  lea     rdx, aLockhandle; "LockHandle"
0x18000305d  mov     rcx, rdi; hModule
0x180003060  mov     r15, rax
0x180003063  call    cs:__imp_GetProcAddress
0x180003069  mov     r12, rax
0x18000306c  xor     ecx, ecx
0x18000306e  mov     rax, [rbp+var_18]
0x180003072  test    rax, rax
0x180003075  jz      loc_1800031DC
0x18000307b  cmp     [rbp+var_20], rcx
0x18000307f  jz      loc_1800031DC
0x180003085  cmp     [rbp+var_10], rcx
0x180003089  jz      loc_1800031DC
0x18000308f  test    r14, r14
0x180003092  jz      loc_1800031DC
0x180003098  test    rsi, rsi
0x18000309b  jz      loc_1800031DC
0x1800030a1  test    r15, r15
0x1800030a4  jz      loc_1800031DC
0x1800030aa  test    r12, r12
0x1800030ad  jz      loc_1800031DC
0x1800030b3  lea     ecx, [rbx+2]
0x1800030b6  xor     edx, edx
0x1800030b8  lea     r8, [rbp+var_28]
0x1800030bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c1  test    ax, 0FFFEh
0x1800030c5  jnz     loc_1800031DC
0x1800030cb  mov     rcx, [rbp+var_28]
0x1800030cf  xor     r9d, r9d
0x1800030d2  mov     rax, [rbp+var_20]
0x1800030d6  mov     edx, 0C8h
0x1800030db  mov     r8d, 17Ch
0x1800030e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e6  mov     rdx, [rbp+var_28]
0x1800030ea  lea     ecx, [rbx+3]
0x1800030ed  mov     rax, [rbp+var_18]
0x1800030f1  lea     r8, [rbp+var_30]
0x1800030f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030fa  test    ax, 0FFFEh
0x1800030fe  jnz     loc_1800031CB
0x180003104  movzx   eax, [rbp+arg_18]
0x180003108  lea     r9d, [rbx-2]
0x18000310c  mov     r8, [rbp+arg_8]
0x180003110  xor     edx, edx
0x180003112  mov     rcx, [rbp+var_30]
0x180003116  mov     [rsp+80h+var_40], ax
0x18000311b  movzx   eax, [rbp+arg_10]
0x18000311f  mov     [rsp+80h+var_48], ax
0x180003124  mov     rax, [rbp+var_10]
0x180003128  mov     [rsp+80h+var_50], rdx
0x18000312d  mov     [rsp+80h+var_58], dx
0x180003132  mov     qword ptr [rsp+80h+var_60], rdx
0x180003137  mov     rdx, r13
0x18000313a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000313f  movzx   ebx, ax
0x180003142  mov     eax, 1
0x180003147  cmp     bx, ax
0x18000314a  jnz     short loc_1800031A9
0x18000314c  mov     rcx, [rbp+var_30]
0x180003150  lea     edx, [rax+1]
0x180003153  mov     r8d, eax
0x180003156  mov     rax, r12
0x180003159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000315e  mov     rcx, [rbp+var_30]
0x180003162  lea     rdx, aHy000; "HY000"
0x180003169  mov     rax, r15
0x18000316c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003171  xor     r13d, r13d
0x180003174  test    ax, ax
0x180003177  jnz     short loc_180003194
0x180003179  mov     rcx, [rbp+var_30]
0x18000317d  lea     rdx, aS1000; "S1000"
0x180003184  mov     rax, r15
0x180003187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000318c  test    ax, ax
0x18000318f  jnz     short loc_180003194
0x180003191  mov     ebx, r13d
0x180003194  mov     rcx, [rbp+var_30]
0x180003198  xor     r8d, r8d
0x18000319b  mov     rax, r12
0x18000319e  lea     edx, [r8+2]
0x1800031a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a7  jmp     short loc_1800031AE
0x1800031a9  test    bx, bx
0x1800031ac  jnz     short loc_1800031BA
0x1800031ae  mov     rcx, [rbp+var_30]
0x1800031b2  mov     rax, r14
0x1800031b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ba  mov     rdx, [rbp+var_30]
0x1800031be  mov     ecx, 2
0x1800031c3  mov     rax, rsi
0x1800031c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031cb  mov     rdx, [rbp+var_28]
0x1800031cf  mov     ecx, 1
0x1800031d4  mov     rax, rsi
0x1800031d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031dc  mov     rcx, rdi; hLibModule
0x1800031df  call    cs:__imp_FreeLibrary
0x1800031e5  jmp     short loc_18000320B
0x1800031e7  call    cs:__imp_GetLastError
0x1800031ed  lea     r9, aOdbc32Dll; "ODBC32.DLL"
0x1800031f4  mov     edx, 691h
0x1800031f9  mov     r8d, 730h
0x1800031ff  mov     [rsp+80h+var_60], eax; int
0x180003203  mov     rcx, r13; hWnd
0x180003206  call    CpanelError
0x18000320b  movzx   eax, bx
0x18000320e  mov     rbx, [rsp+80h+arg_0]
0x180003216  add     rsp, 80h
0x18000321d  pop     r15
0x18000321f  pop     r14
0x180003221  pop     r13
0x180003223  pop     r12
0x180003225  pop     rdi
0x180003226  pop     rsi
0x180003227  pop     rbp
0x180003228  retn
```
