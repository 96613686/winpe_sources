# IASRegisterComponent

- ea: `0x18000c470`
- end: `0x18000c9db`
- name: `IASRegisterComponent`
- size: `1387`
- prototype: `__int64 __fastcall(HMODULE hModule, GUID *rguid, __int64, __int64, char, GUID *rguida, unsigned __int16, unsigned __int16, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012050`
- `0x1800120b0`
- `0x180012110`

## callees

- `0x18000c470`
- `0x1800181a2`
- `0x1800181e0`
- `0x180019010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000c618`
- `msvcrt!swprintf_s` at `0x18000c644`
- `msvcrt!swprintf_s` at `0x18000c618`
- `msvcrt!swprintf_s` at `0x18000c644`
- `KERNEL32!GetModuleFileNameW` at `0x18000c50f`
- `KERNEL32!GetModuleFileNameW` at `0x18000c54a`
- `KERNEL32!GetModuleFileNameW` at `0x18000c50f`
- `KERNEL32!GetModuleFileNameW` at `0x18000c54a`
- `KERNEL32!GetLastError` at `0x18000c554`
- `KERNEL32!GetLastError` at `0x18000c98c`
- `KERNEL32!GetLastError` at `0x18000c554`
- `KERNEL32!GetLastError` at `0x18000c98c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c4d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c4d5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c595`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c5c7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c595`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c5c7`

## string_xrefs

- `0x18000c6e9`: `CLSID`
- `0x18000c945`: `REGISTRY`
- `0x18000c75d`: `COMPONENT`

## pseudocode

```c
__int64 __fastcall IASRegisterComponent(
        HMODULE hModule,
        GUID *rguid,
        __int64 a3,
        __int64 a4,
        char a5,
        GUID *rguida,
        unsigned __int16 a7,
        unsigned __int16 a8,
        int a9)
{
  int v13; // ebx
  DWORD ModuleFileNameW; // eax
  signed int v15; // eax
  const wchar_t *v16; // rsi
  int *v17; // r14
  const wchar_t *v18; // rbx
  int v19; // edi
  __int64 v21; // rax
  int v22; // eax
  signed int LastError; // eax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Buffer; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+3Ah] [rbp-C6h]
  int v27; // [rsp+42h] [rbp-BEh]
  wchar_t v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+4Ah] [rbp-B6h]
  int v30; // [rsp+52h] [rbp-AEh]
  OLECHAR sz[40]; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR v32[40]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v33; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v34[526]; // [rsp+102h] [rbp+2h] BYREF
  WCHAR Filename[264]; // [rsp+310h] [rbp+210h] BYREF

  ppv = 0;
  v13 = CoCreateInstance(&CLSID_Registrar, 0, 1u, &IID_IRegistrar, &ppv);
  if ( v13 >= 0 )
  {
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x105u);
    if ( !ModuleFileNameW || ModuleFileNameW == 261 )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return (unsigned int)v13;
    }
    v33 = 0;
    memset_0(v34, 0, 0x208u);
    if ( GetModuleFileNameW(::hModule, &v33, 0x105u) )
    {
      v13 = StringFromGUID2(rguid, sz, 40);
      if ( v13 >= 0 )
      {
        v13 = StringFromGUID2(rguida, v32, 40);
        if ( v13 >= 0 )
        {
          Buffer = 0;
          v26 = 0;
          v27 = 0;
          swprintf_s(&Buffer, 7u, L"%d", a7);
          v28 = 0;
          v29 = 0;
          v30 = 0;
          swprintf_s(&v28, 7u, L"%d", a8);
          v16 = L"LocalServer32";
          if ( (a5 & 1) == 0 )
            v16 = L"InprocServer32";
          v17 = (int *)L"Programmable";
          if ( (a5 & 8) == 0 )
            v17 = &dword_18001C7CC;
          if ( (a5 & 4) != 0 )
          {
            v18 = L"Both";
          }
          else
          {
            v18 = L"Apartment";
            if ( (a5 & 2) == 0 )
              v18 = L"Free";
          }
          v19 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, WCHAR *))(*(_QWORD *)ppv + 24LL))(
                  ppv,
                  L"MODULE",
                  Filename);
          if ( v19 >= 0 )
          {
            v19 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, OLECHAR *))(*(_QWORD *)ppv + 24LL))(
                    ppv,
                    L"CLSID",
                    sz);
            if ( v19 >= 0 )
            {
              v19 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64))(*(_QWORD *)ppv + 24LL))(
                      ppv,
                      L"PROGRAM",
                      a3);
              if ( v19 >= 0 )
              {
                v19 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64))(*(_QWORD *)ppv + 24LL))(
                        ppv,
                        L"COMPONENT",
                        a4);
                if ( v19 >= 0 )
                {
                  v19 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, const wchar_t *))(*(_QWORD *)ppv + 24LL))(
                          ppv,
                          L"TYPENAME",
                          L" ");
                  if ( v19 >= 0 )
                  {
                    v19 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, OLECHAR *))(*(_QWORD *)ppv + 24LL))(
                            ppv,
                            L"LIBID",
                            v32);
                    if ( v19 >= 0 )
                    {
                      v19 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, wchar_t *))(*(_QWORD *)ppv + 24LL))(
                              ppv,
                              L"MAJORVER",
                              &Buffer);
                      if ( v19 >= 0 )
                      {
                        v19 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, wchar_t *))(*(_QWORD *)ppv + 24LL))(
                                ppv,
                                L"MINORVER",
                                &v28);
                        if ( v19 >= 0 )
                        {
                          v19 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, const wchar_t *))(*(_QWORD *)ppv + 24LL))(
                                  ppv,
                                  L"CONTEXT",
                                  v16);
                          if ( v19 >= 0 )
                          {
                            v19 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, int *))(*(_QWORD *)ppv + 24LL))(
                                    ppv,
                                    L"ATTRIBUTES",
                                    v17);
                            if ( v19 >= 0 )
                            {
                              v13 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, const wchar_t *))(*(_QWORD *)ppv + 24LL))(
                                      ppv,
                                      L"MODEL",
                                      v18);
                              if ( v13 >= 0 )
                              {
                                v21 = *(_QWORD *)ppv;
                                if ( a9 )
                                  v22 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, __int64, const unsigned __int16 *))(v21 + 88))(
                                          ppv,
                                          &v33,
                                          102,
                                          L"REGISTRY");
                                else
                                  v22 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, __int64, const unsigned __int16 *))(v21 + 96))(
                                          ppv,
                                          &v33,
                                          102,
                                          L"REGISTRY");
                                v13 = v22;
                                if ( ppv )
                                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                              }
                              else if ( ppv )
                              {
                                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                              }
                              return (unsigned int)v13;
                            }
                            if ( ppv )
                              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                          }
                          else if ( ppv )
                          {
                            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                          }
                        }
                        else if ( ppv )
                        {
                          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                        }
                      }
                      else if ( ppv )
                      {
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                      }
                    }
                    else if ( ppv )
                    {
                      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                    }
                  }
                  else if ( ppv )
                  {
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                  }
                }
                else if ( ppv )
                {
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                }
              }
              else if ( ppv )
              {
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
              }
            }
            else if ( ppv )
            {
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            }
          }
          else if ( ppv )
          {
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          return (unsigned int)v19;
        }
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      else if ( ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    else
    {
      v15 = GetLastError();
      v13 = v15;
      if ( v15 > 0 )
        v13 = (unsigned __int16)v15 | 0x80070000;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  else if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000c470  push    rbp
0x18000c472  push    rbx
0x18000c473  push    rsi
0x18000c474  push    rdi
0x18000c475  push    r12
0x18000c477  push    r14
0x18000c479  push    r15
0x18000c47b  lea     rbp, [rsp-430h]
0x18000c483  sub     rsp, 530h
0x18000c48a  mov     rax, cs:__security_cookie
0x18000c491  xor     rax, rsp
0x18000c494  mov     [rbp+460h+var_40], rax
0x18000c49b  mov     r12, r9
0x18000c49e  mov     r15, r8
0x18000c4a1  mov     rsi, rdx
0x18000c4a4  mov     rdi, rcx
0x18000c4a7  mov     r14, [rbp+460h+rguid]
0x18000c4ae  mov     [rsp+560h+var_530], 0
0x18000c4b7  lea     rax, [rsp+560h+var_530]
0x18000c4bc  mov     [rsp+560h+ppv], rax; ppv
0x18000c4c1  lea     r9, IID_IRegistrar; riid
0x18000c4c8  xor     edx, edx; pUnkOuter
0x18000c4ca  lea     r8d, [rdx+1]; dwClsContext
0x18000c4ce  lea     rcx, CLSID_Registrar; rclsid
0x18000c4d5  call    cs:__imp_CoCreateInstance
0x18000c4db  mov     ebx, eax
0x18000c4dd  test    eax, eax
0x18000c4df  jns     short loc_18000C4FD
0x18000c4e1  mov     rcx, [rsp+560h+var_530]
0x18000c4e6  test    rcx, rcx
0x18000c4e9  jz      short loc_18000C4F8
0x18000c4eb  mov     rdx, [rcx]
0x18000c4ee  mov     rax, [rdx+10h]
0x18000c4f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4f7  nop
0x18000c4f8  jmp     loc_18000C9B8
0x18000c4fd  mov     ebx, 105h
0x18000c502  mov     r8d, ebx; nSize
0x18000c505  lea     rdx, [rbp+460h+Filename]; lpFilename
0x18000c50c  mov     rcx, rdi; hModule
0x18000c50f  call    cs:__imp_GetModuleFileNameW
0x18000c515  test    eax, eax
0x18000c517  jz      loc_18000C98C
0x18000c51d  cmp     eax, ebx
0x18000c51f  jz      loc_18000C98C
0x18000c525  xor     eax, eax
0x18000c527  mov     [rbp+460h+var_460], ax
0x18000c52b  xor     edx, edx; Val
0x18000c52d  mov     r8d, 208h; Size
0x18000c533  lea     rcx, [rbp+460h+var_45E]; void *
0x18000c537  call    memset_0
0x18000c53c  mov     r8d, ebx; nSize
0x18000c53f  lea     rdx, [rbp+460h+var_460]; lpFilename
0x18000c543  mov     rcx, cs:hModule; hModule
0x18000c54a  call    cs:__imp_GetModuleFileNameW
0x18000c550  test    eax, eax
0x18000c552  jnz     short loc_18000C585
0x18000c554  call    cs:__imp_GetLastError
0x18000c55a  mov     ebx, eax
0x18000c55c  test    eax, eax
0x18000c55e  jle     short loc_18000C569
0x18000c560  movzx   ebx, ax
0x18000c563  or      ebx, 80070000h
0x18000c569  mov     rcx, [rsp+560h+var_530]
0x18000c56e  test    rcx, rcx
0x18000c571  jz      short loc_18000C580
0x18000c573  mov     rdx, [rcx]
0x18000c576  mov     rax, [rdx+10h]
0x18000c57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c57f  nop
0x18000c580  jmp     loc_18000C9B8
0x18000c585  mov     edi, 28h ; '('
0x18000c58a  mov     r8d, edi; cchMax
0x18000c58d  lea     rdx, [rsp+560h+sz]; lpsz
0x18000c592  mov     rcx, rsi; rguid
0x18000c595  call    cs:__imp_StringFromGUID2
0x18000c59b  mov     ebx, eax
0x18000c59d  test    eax, eax
0x18000c59f  jns     short loc_18000C5BD
0x18000c5a1  mov     rcx, [rsp+560h+var_530]
0x18000c5a6  test    rcx, rcx
0x18000c5a9  jz      short loc_18000C5B8
0x18000c5ab  mov     rdx, [rcx]
0x18000c5ae  mov     rax, [rdx+10h]
0x18000c5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5b7  nop
0x18000c5b8  jmp     loc_18000C9B8
0x18000c5bd  mov     r8d, edi; cchMax
0x18000c5c0  lea     rdx, [rbp+460h+var_4B0]; lpsz
0x18000c5c4  mov     rcx, r14; rguid
0x18000c5c7  call    cs:__imp_StringFromGUID2
0x18000c5cd  mov     ebx, eax
0x18000c5cf  test    eax, eax
0x18000c5d1  jns     short loc_18000C5EF
0x18000c5d3  mov     rcx, [rsp+560h+var_530]
0x18000c5d8  test    rcx, rcx
0x18000c5db  jz      short loc_18000C5EA
0x18000c5dd  mov     rdx, [rcx]
0x18000c5e0  mov     rax, [rdx+10h]
0x18000c5e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5e9  nop
0x18000c5ea  jmp     loc_18000C9B8
0x18000c5ef  xor     eax, eax
0x18000c5f1  mov     [rsp+560h+Buffer], ax
0x18000c5f6  mov     [rsp+560h+var_526], rax
0x18000c5fb  mov     [rsp+560h+var_51E], eax
0x18000c5ff  movzx   r9d, [rbp+460h+arg_30]
0x18000c607  lea     r8, aD; "%d"
0x18000c60e  lea     ebx, [rax+7]
0x18000c611  mov     edx, ebx; BufferCount
0x18000c613  lea     rcx, [rsp+560h+Buffer]; Buffer
0x18000c618  call    cs:__imp_swprintf_s
0x18000c61e  xor     eax, eax
0x18000c620  mov     [rsp+560h+var_518], ax
0x18000c625  mov     [rsp+560h+var_516], rax
0x18000c62a  mov     [rsp+560h+var_50E], eax
0x18000c62e  movzx   r9d, [rbp+460h+arg_38]
0x18000c636  lea     r8, aD; "%d"
0x18000c63d  mov     edx, ebx; BufferCount
0x18000c63f  lea     rcx, [rsp+560h+var_518]; Buffer
0x18000c644  call    cs:__imp_swprintf_s
0x18000c64a  mov     eax, dword ptr [rbp+460h+arg_20]
0x18000c650  test    al, 1
0x18000c652  lea     rcx, aInprocserver32; "InprocServer32"
0x18000c659  lea     rsi, aLocalserver32; "LocalServer32"
0x18000c660  cmovz   rsi, rcx
0x18000c664  test    al, 8
0x18000c666  lea     rcx, dword_18001C7CC
0x18000c66d  lea     r14, aProgrammable; "Programmable"
0x18000c674  cmovz   r14, rcx
0x18000c678  test    al, 4
0x18000c67a  jz      short loc_18000C685
0x18000c67c  lea     rbx, aBoth; "Both"
0x18000c683  jmp     short loc_18000C699
0x18000c685  test    al, 2
0x18000c687  lea     rbx, aApartment; "Apartment"
0x18000c68e  lea     rax, aFree; "Free"
0x18000c695  cmovz   rbx, rax
0x18000c699  mov     rcx, [rsp+560h+var_530]
0x18000c69e  mov     rax, [rcx]
0x18000c6a1  lea     r8, [rbp+460h+Filename]
0x18000c6a8  lea     rdx, aModule_0; "MODULE"
0x18000c6af  mov     rax, [rax+18h]
0x18000c6b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6b8  mov     edi, eax
0x18000c6ba  test    eax, eax
0x18000c6bc  jns     short loc_18000C6DC
0x18000c6be  mov     rcx, [rsp+560h+var_530]
0x18000c6c3  test    rcx, rcx
0x18000c6c6  jz      short loc_18000C6D5
0x18000c6c8  mov     rdx, [rcx]
0x18000c6cb  mov     rax, [rdx+10h]
0x18000c6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6d4  nop
0x18000c6d5  mov     eax, edi
0x18000c6d7  jmp     loc_18000C9BA
0x18000c6dc  mov     rcx, [rsp+560h+var_530]
0x18000c6e1  mov     rax, [rcx]
0x18000c6e4  lea     r8, [rsp+560h+sz]
0x18000c6e9  lea     rdx, aClsid_0; "CLSID"
0x18000c6f0  mov     rax, [rax+18h]
0x18000c6f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6f9  mov     edi, eax
0x18000c6fb  test    eax, eax
0x18000c6fd  jns     short loc_18000C718
0x18000c6ff  mov     rcx, [rsp+560h+var_530]
0x18000c704  test    rcx, rcx
0x18000c707  jz      short loc_18000C716
0x18000c709  mov     rdx, [rcx]
0x18000c70c  mov     rax, [rdx+10h]
0x18000c710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c715  nop
0x18000c716  jmp     short loc_18000C6D5
0x18000c718  mov     rcx, [rsp+560h+var_530]
0x18000c71d  mov     rax, [rcx]
0x18000c720  mov     r8, r15
0x18000c723  lea     rdx, aProgram; "PROGRAM"
0x18000c72a  mov     rax, [rax+18h]
0x18000c72e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c733  mov     edi, eax
0x18000c735  test    eax, eax
0x18000c737  jns     short loc_18000C752
0x18000c739  mov     rcx, [rsp+560h+var_530]
0x18000c73e  test    rcx, rcx
0x18000c741  jz      short loc_18000C750
0x18000c743  mov     rdx, [rcx]
0x18000c746  mov     rax, [rdx+10h]
0x18000c74a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c74f  nop
0x18000c750  jmp     short loc_18000C6D5
0x18000c752  mov     rcx, [rsp+560h+var_530]
0x18000c757  mov     rax, [rcx]
0x18000c75a  mov     r8, r12
0x18000c75d  lea     rdx, aComponent; "COMPONENT"
0x18000c764  mov     rax, [rax+18h]
0x18000c768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c76d  mov     edi, eax
0x18000c76f  test    eax, eax
0x18000c771  jns     short loc_18000C78F
0x18000c773  mov     rcx, [rsp+560h+var_530]
0x18000c778  test    rcx, rcx
0x18000c77b  jz      short loc_18000C78A
0x18000c77d  mov     rdx, [rcx]
0x18000c780  mov     rax, [rdx+10h]
0x18000c784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c789  nop
0x18000c78a  jmp     loc_18000C6D5
0x18000c78f  mov     rcx, [rsp+560h+var_530]
0x18000c794  mov     rax, [rcx]
0x18000c797  lea     r8, asc_18001C90C; " "
0x18000c79e  lea     rdx, aTypename; "TYPENAME"
0x18000c7a5  mov     rax, [rax+18h]
0x18000c7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7ae  mov     edi, eax
0x18000c7b0  test    eax, eax
0x18000c7b2  jns     short loc_18000C7D0
0x18000c7b4  mov     rcx, [rsp+560h+var_530]
0x18000c7b9  test    rcx, rcx
0x18000c7bc  jz      short loc_18000C7CB
0x18000c7be  mov     rdx, [rcx]
0x18000c7c1  mov     rax, [rdx+10h]
0x18000c7c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7ca  nop
0x18000c7cb  jmp     loc_18000C6D5
0x18000c7d0  mov     rcx, [rsp+560h+var_530]
0x18000c7d5  mov     rax, [rcx]
0x18000c7d8  lea     r8, [rbp+460h+var_4B0]
0x18000c7dc  lea     rdx, aLibid; "LIBID"
0x18000c7e3  mov     rax, [rax+18h]
0x18000c7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7ec  mov     edi, eax
0x18000c7ee  test    eax, eax
0x18000c7f0  jns     short loc_18000C80E
0x18000c7f2  mov     rcx, [rsp+560h+var_530]
0x18000c7f7  test    rcx, rcx
0x18000c7fa  jz      short loc_18000C809
0x18000c7fc  mov     rdx, [rcx]
0x18000c7ff  mov     rax, [rdx+10h]
0x18000c803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c808  nop
0x18000c809  jmp     loc_18000C6D5
0x18000c80e  mov     rcx, [rsp+560h+var_530]
0x18000c813  mov     rax, [rcx]
0x18000c816  lea     r8, [rsp+560h+Buffer]
0x18000c81b  lea     rdx, aMajorver; "MAJORVER"
0x18000c822  mov     rax, [rax+18h]
0x18000c826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c82b  mov     edi, eax
0x18000c82d  test    eax, eax
0x18000c82f  jns     short loc_18000C84D
0x18000c831  mov     rcx, [rsp+560h+var_530]
0x18000c836  test    rcx, rcx
0x18000c839  jz      short loc_18000C848
0x18000c83b  mov     rdx, [rcx]
0x18000c83e  mov     rax, [rdx+10h]
0x18000c842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c847  nop
0x18000c848  jmp     loc_18000C6D5
0x18000c84d  mov     rcx, [rsp+560h+var_530]
0x18000c852  mov     rax, [rcx]
0x18000c855  lea     r8, [rsp+560h+var_518]
0x18000c85a  lea     rdx, aMinorver; "MINORVER"
0x18000c861  mov     rax, [rax+18h]
0x18000c865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c86a  mov     edi, eax
0x18000c86c  test    eax, eax
0x18000c86e  jns     short loc_18000C88C
0x18000c870  mov     rcx, [rsp+560h+var_530]
0x18000c875  test    rcx, rcx
0x18000c878  jz      short loc_18000C887
0x18000c87a  mov     rdx, [rcx]
0x18000c87d  mov     rax, [rdx+10h]
0x18000c881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c886  nop
0x18000c887  jmp     loc_18000C6D5
0x18000c88c  mov     rcx, [rsp+560h+var_530]
0x18000c891  mov     rax, [rcx]
0x18000c894  mov     r8, rsi
0x18000c897  lea     rdx, aContext; "CONTEXT"
0x18000c89e  mov     rax, [rax+18h]
0x18000c8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8a7  mov     edi, eax
0x18000c8a9  test    eax, eax
0x18000c8ab  jns     short loc_18000C8C9
0x18000c8ad  mov     rcx, [rsp+560h+var_530]
0x18000c8b2  test    rcx, rcx
0x18000c8b5  jz      short loc_18000C8C4
0x18000c8b7  mov     rdx, [rcx]
0x18000c8ba  mov     rax, [rdx+10h]
0x18000c8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8c3  nop
0x18000c8c4  jmp     loc_18000C6D5
0x18000c8c9  mov     rcx, [rsp+560h+var_530]
0x18000c8ce  mov     rax, [rcx]
0x18000c8d1  mov     r8, r14
0x18000c8d4  lea     rdx, aAttributes; "ATTRIBUTES"
0x18000c8db  mov     rax, [rax+18h]
0x18000c8df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8e4  mov     edi, eax
0x18000c8e6  test    eax, eax
  ... truncated ...
```
