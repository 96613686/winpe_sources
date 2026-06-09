# TMetaInferrence::InferServerWiringMeta(void)

- ea: `0x18001fa9c`
- end: `0x18001ff09`
- name: `?InferServerWiringMeta@TMetaInferrence@@AEAAXXZ`
- size: `1133`
- prototype: `void __fastcall(TMetaInferrence *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001e000`

## callees

- `0x180017ad8`
- `0x18001fa9c`
- `0x180030010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001fb82`
- `msvcrt!_wcsicmp` at `0x18001fbb4`
- `msvcrt!_wcsicmp` at `0x18001fbe6`
- `msvcrt!_wcsicmp` at `0x18001fc18`
- `msvcrt!_wcsicmp` at `0x18001fb82`
- `msvcrt!_wcsicmp` at `0x18001fbb4`
- `msvcrt!_wcsicmp` at `0x18001fbe6`
- `msvcrt!_wcsicmp` at `0x18001fc18`

## string_xrefs

- `0x18001fd05`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001fd57`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001fd74`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001fd91`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001fdae`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001fdcb`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001fe1c`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001fe69`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001febb`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001fef1`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001fce3`: `Error in ServerWiringMeta for Table (%s) - ReadPlugin, WritePlugin, Interceptor are all specified as NONE.  At least one of these must be specified.`
- `0x18001fd35`: `Error in ServerWiringMeta for Table (%s) - You cannot define ReadPlugin or WritePlugin when a Merger is defined.`
- `0x18001fb7b`: `catalog.dll`
- `0x18001fbad`: `catalog.dll`
- `0x18001fbdf`: `catalog.dll`
- `0x18001fc11`: `catalog.dll`
- `0x18001fd67`: `ERROR - CATALOG.DLL SHOULD NEVER BE EXPLLICITLY SPECIFIED`
- `0x18001fd84`: `ERROR - CATALOG.DLL SHOULD NEVER BE EXPLLICITLY SPECIFIED`
- `0x18001fda1`: `ERROR - CATALOG.DLL SHOULD NEVER BE EXPLLICITLY SPECIFIED`
- `0x18001fdbe`: `ERROR - CATALOG.DLL SHOULD NEVER BE EXPLLICITLY SPECIFIED`
- `0x18001fe47`: `Error in ServerWiringMeta for Table (%s) - WireOnReadWrite OR WireOnWriteOnly may be specified but not both.`

## pseudocode

```c
void __fastcall TMetaInferrence::InferServerWiringMeta(TMetaInferrence *this)
{
  int v1; // r14d
  unsigned int *v2; // rbx
  unsigned int i; // edi
  unsigned int *v5; // rax
  unsigned int *v6; // rsi
  unsigned int v7; // r9d
  unsigned int v8; // edx
  unsigned int v9; // ecx
  unsigned int v10; // r8d
  unsigned int v11; // eax
  const wchar_t *v12; // rax
  const wchar_t *v13; // rax
  const wchar_t *v14; // rax
  const wchar_t *v15; // rax
  char v16; // al
  __int64 v17; // rcx
  void (***v18)(_QWORD, const wchar_t *, ...); // rdi
  void (*v19)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v20; // rax
  void (***v21)(_QWORD, const wchar_t *, ...); // rdi
  void (*v22)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v23; // rax
  void (***v24)(_QWORD, const wchar_t *, ...); // rdi
  void (*v25)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v26; // rax
  void (***v27)(_QWORD, const wchar_t *, ...); // rdi
  void (*v28)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v29; // rax
  void (***v30)(_QWORD, const wchar_t *, ...); // rdi
  void (*v31)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v32; // rax

  v1 = -1;
  v2 = (unsigned int *)((char *)this + 24);
  for ( i = 0; i < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 312LL))(*((_QWORD *)this + 1)); ++i )
  {
    v5 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 224LL))(
                           *((_QWORD *)this + 1),
                           i);
    v6 = v5;
    v7 = *v5;
    if ( !*v5 )
    {
      (***((void (****)(_QWORD, const wchar_t *, ...))this + 2))(
        *((_QWORD *)this + 2),
        L"Error in ServerWiringMeta row (%d) - NULL specified for Table.",
        i);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x499u,
        0);
    }
    v8 = v5[2];
    if ( !v8 )
    {
      v8 = *v2;
      v5[2] = *v2;
    }
    v9 = v5[4];
    if ( !v9 )
    {
      v9 = *v2;
      v5[4] = *v2;
    }
    v10 = v5[6];
    if ( !v10 )
    {
      v10 = *v2;
      v5[6] = *v2;
    }
    v11 = v5[11];
    if ( !v11 )
    {
      v11 = *v2;
      v6[11] = *v2;
    }
    if ( v7 == v1 )
    {
      if ( *v2 != v11 )
      {
        v30 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v31 = **v30;
        v32 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), v7);
        v31(
          v30,
          L"Error in ServerWiringMeta for Table (%s) - Merge Interceptor must be defined as first interceptor, and there c"
           "an be only one merge interceptor.",
          v32);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - VALIDATION ERROR",
          0x4C0u,
          0);
      }
    }
    else
    {
      v1 = v7;
    }
    if ( *v2 == v8 && *v2 == v9 && *v2 == v10 )
    {
      v18 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v19 = **v18;
      v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), v7);
      v19(
        v18,
        L"Error in ServerWiringMeta for Table (%s) - ReadPlugin, WritePlugin, Interceptor are all specified as NONE.  At l"
         "east one of these must be specified.",
        v20);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x4CBu,
        0);
    }
    if ( v11 != *v2 && (v8 != *v2 || v9 != *v2) )
    {
      v21 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v22 = **v21;
      v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), v7);
      v22(
        v21,
        L"Error in ServerWiringMeta for Table (%s) - You cannot define ReadPlugin or WritePlugin when a Merger is defined.",
        v23);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x4D3u,
        0);
    }
    if ( v6[3] )
    {
      v12 = (const wchar_t *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
      if ( !_wcsicmp(v12, L"catalog.dll") )
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - CATALOG.DLL SHOULD NEVER BE EXPLLICITLY SPECIFIED",
          0x4DAu,
          0);
    }
    if ( v6[5] )
    {
      v13 = (const wchar_t *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
      if ( !_wcsicmp(v13, L"catalog.dll") )
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - CATALOG.DLL SHOULD NEVER BE EXPLLICITLY SPECIFIED",
          0x4DDu,
          0);
    }
    if ( v6[7] )
    {
      v14 = (const wchar_t *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
      if ( !_wcsicmp(v14, L"catalog.dll") )
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - CATALOG.DLL SHOULD NEVER BE EXPLLICITLY SPECIFIED",
          0x4E0u,
          0);
    }
    if ( v6[12] )
    {
      v15 = (const wchar_t *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
      if ( !_wcsicmp(v15, L"catalog.dll") )
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - CATALOG.DLL SHOULD NEVER BE EXPLLICITLY SPECIFIED",
          0x4E3u,
          0);
    }
    if ( !v6[8] || !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1)) )
      v6[8] = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1), 45);
    v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), v6[8]);
    v17 = *((_QWORD *)this + 1);
    if ( (v16 & 0x30) == 0x30 )
    {
      v27 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v28 = **v27;
      v29 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 144LL))(v17, *v6);
      v28(
        v27,
        L"Error in ServerWiringMeta for Table (%s) - WireOnReadWrite OR WireOnWriteOnly may be specified but not both.",
        v29);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x4EFu,
        0);
    }
    if ( ((*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 152LL))(v17, v6[8]) & 3) == 3 )
    {
      v24 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v25 = **v24;
      v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v6);
      v25(v24, L"Error in ServerWiringMeta for Table (%s) - First OR Next may be specified but not both.", v26);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x4F7u,
        0);
    }
    if ( !v6[10] )
      v6[10] = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1), 0);
  }
}

```

## disassembly

```asm
0x18001fa9c  push    rbx
0x18001fa9e  push    rbp
0x18001fa9f  push    rsi
0x18001faa0  push    rdi
0x18001faa1  push    r14
0x18001faa3  sub     rsp, 20h
0x18001faa7  or      r14d, 0FFFFFFFFh
0x18001faab  lea     rbx, [rcx+18h]
0x18001faaf  xor     edi, edi
0x18001fab1  mov     rbp, rcx
0x18001fab4  mov     rcx, [rbp+8]
0x18001fab8  mov     rax, [rcx]
0x18001fabb  mov     rax, [rax+138h]
0x18001fac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fac7  cmp     edi, eax
0x18001fac9  jnb     loc_18001FEFE
0x18001facf  mov     rcx, [rbp+8]
0x18001fad3  mov     edx, edi
0x18001fad5  mov     rax, [rcx]
0x18001fad8  mov     rax, [rax+0E0h]
0x18001fadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fae4  mov     rsi, rax
0x18001fae7  mov     r9d, [rax]
0x18001faea  test    r9d, r9d
0x18001faed  jz      loc_18001FEC8
0x18001faf3  mov     edx, [rax+8]
0x18001faf6  test    edx, edx
0x18001faf8  jnz     short loc_18001FAFF
0x18001fafa  mov     edx, [rbx]
0x18001fafc  mov     [rax+8], edx
0x18001faff  mov     ecx, [rax+10h]
0x18001fb02  test    ecx, ecx
0x18001fb04  jnz     short loc_18001FB0B
0x18001fb06  mov     ecx, [rbx]
0x18001fb08  mov     [rax+10h], ecx
0x18001fb0b  mov     r8d, [rax+18h]
0x18001fb0f  test    r8d, r8d
0x18001fb12  jnz     short loc_18001FB1B
0x18001fb14  mov     r8d, [rbx]
0x18001fb17  mov     [rax+18h], r8d
0x18001fb1b  mov     eax, [rax+2Ch]
0x18001fb1e  test    eax, eax
0x18001fb20  jnz     short loc_18001FB27
0x18001fb22  mov     eax, [rbx]
0x18001fb24  mov     [rsi+2Ch], eax
0x18001fb27  cmp     r9d, r14d
0x18001fb2a  jz      short loc_18001FB31
0x18001fb2c  mov     r14d, r9d
0x18001fb2f  jmp     short loc_18001FB39
0x18001fb31  cmp     [rbx], eax
0x18001fb33  jnz     loc_18001FE76
0x18001fb39  cmp     [rbx], edx
0x18001fb3b  jnz     short loc_18001FB4A
0x18001fb3d  cmp     [rbx], ecx
0x18001fb3f  jnz     short loc_18001FB4A
0x18001fb41  cmp     [rbx], r8d
0x18001fb44  jz      loc_18001FCC0
0x18001fb4a  cmp     eax, [rbx]
0x18001fb4c  jz      short loc_18001FB5E
0x18001fb4e  cmp     edx, [rbx]
0x18001fb50  jnz     loc_18001FD12
0x18001fb56  cmp     ecx, [rbx]
0x18001fb58  jnz     loc_18001FD12
0x18001fb5e  mov     edx, [rsi+0Ch]
0x18001fb61  test    edx, edx
0x18001fb63  jz      short loc_18001FB90
0x18001fb65  mov     rcx, [rbp+8]
0x18001fb69  mov     rax, [rcx]
0x18001fb6c  mov     rax, [rax+90h]
0x18001fb73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb78  mov     rcx, rax; String1
0x18001fb7b  lea     rdx, aCatalogDll; "catalog.dll"
0x18001fb82  call    cs:__imp__wcsicmp
0x18001fb88  test    eax, eax
0x18001fb8a  jz      loc_18001FD64
0x18001fb90  mov     edx, [rsi+14h]
0x18001fb93  test    edx, edx
0x18001fb95  jz      short loc_18001FBC2
0x18001fb97  mov     rcx, [rbp+8]
0x18001fb9b  mov     rax, [rcx]
0x18001fb9e  mov     rax, [rax+90h]
0x18001fba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbaa  mov     rcx, rax; String1
0x18001fbad  lea     rdx, aCatalogDll; "catalog.dll"
0x18001fbb4  call    cs:__imp__wcsicmp
0x18001fbba  test    eax, eax
0x18001fbbc  jz      loc_18001FD81
0x18001fbc2  mov     edx, [rsi+1Ch]
0x18001fbc5  test    edx, edx
0x18001fbc7  jz      short loc_18001FBF4
0x18001fbc9  mov     rcx, [rbp+8]
0x18001fbcd  mov     rax, [rcx]
0x18001fbd0  mov     rax, [rax+90h]
0x18001fbd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbdc  mov     rcx, rax; String1
0x18001fbdf  lea     rdx, aCatalogDll; "catalog.dll"
0x18001fbe6  call    cs:__imp__wcsicmp
0x18001fbec  test    eax, eax
0x18001fbee  jz      loc_18001FD9E
0x18001fbf4  mov     edx, [rsi+30h]
0x18001fbf7  test    edx, edx
0x18001fbf9  jz      short loc_18001FC26
0x18001fbfb  mov     rcx, [rbp+8]
0x18001fbff  mov     rax, [rcx]
0x18001fc02  mov     rax, [rax+90h]
0x18001fc09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc0e  mov     rcx, rax; String1
0x18001fc11  lea     rdx, aCatalogDll; "catalog.dll"
0x18001fc18  call    cs:__imp__wcsicmp
0x18001fc1e  test    eax, eax
0x18001fc20  jz      loc_18001FDBB
0x18001fc26  mov     edx, [rsi+20h]
0x18001fc29  test    edx, edx
0x18001fc2b  jz      short loc_18001FC44
0x18001fc2d  mov     rcx, [rbp+8]
0x18001fc31  mov     rax, [rcx]
0x18001fc34  mov     rax, [rax+98h]
0x18001fc3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc40  test    eax, eax
0x18001fc42  jnz     short loc_18001FC5C
0x18001fc44  mov     rcx, [rbp+8]
0x18001fc48  mov     edx, 2Dh ; '-'
0x18001fc4d  mov     rax, [rcx]
0x18001fc50  mov     rax, [rax+10h]
0x18001fc54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc59  mov     [rsi+20h], eax
0x18001fc5c  mov     rcx, [rbp+8]
0x18001fc60  mov     edx, [rsi+20h]
0x18001fc63  mov     rax, [rcx]
0x18001fc66  mov     rax, [rax+98h]
0x18001fc6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc72  mov     rcx, [rbp+8]
0x18001fc76  and     eax, 30h
0x18001fc79  cmp     al, 30h ; '0'
0x18001fc7b  jz      loc_18001FE29
0x18001fc81  mov     rax, [rcx]
0x18001fc84  mov     edx, [rsi+20h]
0x18001fc87  mov     rax, [rax+98h]
0x18001fc8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc93  and     eax, 3
0x18001fc96  cmp     al, 3
0x18001fc98  jz      loc_18001FDD8
0x18001fc9e  cmp     dword ptr [rsi+28h], 0
0x18001fca2  jnz     short loc_18001FCB9
0x18001fca4  mov     rcx, [rbp+8]
0x18001fca8  xor     edx, edx
0x18001fcaa  mov     rax, [rcx]
0x18001fcad  mov     rax, [rax+10h]
0x18001fcb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcb6  mov     [rsi+28h], eax
0x18001fcb9  inc     edi
0x18001fcbb  jmp     loc_18001FAB4
0x18001fcc0  mov     rdi, [rbp+10h]
0x18001fcc4  mov     edx, r9d
0x18001fcc7  mov     rcx, [rbp+8]
0x18001fccb  mov     rax, [rdi]
0x18001fcce  mov     r8, [rcx]
0x18001fcd1  mov     rbx, [rax]
0x18001fcd4  mov     rax, [r8+90h]
0x18001fcdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fce0  mov     r8, rax
0x18001fce3  lea     rdx, aErrorInServerw_1; "Error in ServerWiringMeta for Table (%s"...
0x18001fcea  mov     rax, rbx
0x18001fced  mov     rcx, rdi
0x18001fcf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcf5  xor     r9d, r9d; unsigned int
0x18001fcf8  lea     rdx, aErrorValidatio; "ERROR - VALIDATION ERROR"
0x18001fcff  mov     r8d, 4CBh; unsigned int
0x18001fd05  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001fd0c  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001fd12  mov     rdi, [rbp+10h]
0x18001fd16  mov     rcx, [rbp+8]
0x18001fd1a  mov     rax, [rdi]
0x18001fd1d  mov     rdx, [rcx]
0x18001fd20  mov     rbx, [rax]
0x18001fd23  mov     rax, [rdx+90h]
0x18001fd2a  mov     edx, r9d
0x18001fd2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd32  mov     r8, rax
0x18001fd35  lea     rdx, aErrorInServerw_0; "Error in ServerWiringMeta for Table (%s"...
0x18001fd3c  mov     rax, rbx
0x18001fd3f  mov     rcx, rdi
0x18001fd42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd47  xor     r9d, r9d; unsigned int
0x18001fd4a  lea     rdx, aErrorValidatio; "ERROR - VALIDATION ERROR"
0x18001fd51  mov     r8d, 4D3h; unsigned int
0x18001fd57  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001fd5e  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001fd64  xor     r9d, r9d; unsigned int
0x18001fd67  lea     rdx, aErrorCatalogDl; "ERROR - CATALOG.DLL SHOULD NEVER BE EXP"...
0x18001fd6e  mov     r8d, 4DAh; unsigned int
0x18001fd74  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001fd7b  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001fd81  xor     r9d, r9d; unsigned int
0x18001fd84  lea     rdx, aErrorCatalogDl; "ERROR - CATALOG.DLL SHOULD NEVER BE EXP"...
0x18001fd8b  mov     r8d, 4DDh; unsigned int
0x18001fd91  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001fd98  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001fd9e  xor     r9d, r9d; unsigned int
0x18001fda1  lea     rdx, aErrorCatalogDl; "ERROR - CATALOG.DLL SHOULD NEVER BE EXP"...
0x18001fda8  mov     r8d, 4E0h; unsigned int
0x18001fdae  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001fdb5  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001fdbb  xor     r9d, r9d; unsigned int
0x18001fdbe  lea     rdx, aErrorCatalogDl; "ERROR - CATALOG.DLL SHOULD NEVER BE EXP"...
0x18001fdc5  mov     r8d, 4E3h; unsigned int
0x18001fdcb  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001fdd2  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001fdd8  mov     rdi, [rbp+10h]
0x18001fddc  mov     rcx, [rbp+8]
0x18001fde0  mov     rax, [rdi]
0x18001fde3  mov     rdx, [rcx]
0x18001fde6  mov     rbx, [rax]
0x18001fde9  mov     rax, [rdx+90h]
0x18001fdf0  mov     edx, [rsi]
0x18001fdf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdf7  mov     r8, rax
0x18001fdfa  lea     rdx, aErrorInServerw_2; "Error in ServerWiringMeta for Table (%s"...
0x18001fe01  mov     rax, rbx
0x18001fe04  mov     rcx, rdi
0x18001fe07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe0c  xor     r9d, r9d; unsigned int
0x18001fe0f  lea     rdx, aErrorValidatio; "ERROR - VALIDATION ERROR"
0x18001fe16  mov     r8d, 4F7h; unsigned int
0x18001fe1c  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001fe23  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001fe29  mov     rdx, [rcx]
0x18001fe2c  mov     rdi, [rbp+10h]
0x18001fe30  mov     rax, [rdi]
0x18001fe33  mov     rbx, [rax]
0x18001fe36  mov     rax, [rdx+90h]
0x18001fe3d  mov     edx, [rsi]
0x18001fe3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe44  mov     r8, rax
0x18001fe47  lea     rdx, aErrorInServerw_3; "Error in ServerWiringMeta for Table (%s"...
0x18001fe4e  mov     rax, rbx
0x18001fe51  mov     rcx, rdi
0x18001fe54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe59  xor     r9d, r9d; unsigned int
0x18001fe5c  lea     rdx, aErrorValidatio; "ERROR - VALIDATION ERROR"
0x18001fe63  mov     r8d, 4EFh; unsigned int
0x18001fe69  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001fe70  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001fe76  mov     rdi, [rbp+10h]
0x18001fe7a  mov     rcx, [rbp+8]
0x18001fe7e  mov     rax, [rdi]
0x18001fe81  mov     rdx, [rcx]
0x18001fe84  mov     rbx, [rax]
0x18001fe87  mov     rax, [rdx+90h]
0x18001fe8e  mov     edx, r9d
0x18001fe91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe96  mov     r8, rax
0x18001fe99  lea     rdx, aErrorInServerw; "Error in ServerWiringMeta for Table (%s"...
0x18001fea0  mov     rax, rbx
0x18001fea3  mov     rcx, rdi
0x18001fea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001feab  xor     r9d, r9d; unsigned int
0x18001feae  lea     rdx, aErrorValidatio; "ERROR - VALIDATION ERROR"
0x18001feb5  mov     r8d, 4C0h; unsigned int
0x18001febb  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001fec2  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001fec8  mov     rcx, [rbp+10h]
0x18001fecc  lea     rdx, aErrorInServerw_4; "Error in ServerWiringMeta row (%d) - NU"...
0x18001fed3  mov     r8d, edi
0x18001fed6  mov     rax, [rcx]
0x18001fed9  mov     rax, [rax]
0x18001fedc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fee1  xor     r9d, r9d; unsigned int
0x18001fee4  lea     rdx, aErrorValidatio; "ERROR - VALIDATION ERROR"
0x18001feeb  mov     r8d, 499h; unsigned int
0x18001fef1  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001fef8  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001fefe  add     rsp, 20h
0x18001ff02  pop     r14
0x18001ff04  pop     rdi
0x18001ff05  pop     rsi
0x18001ff06  pop     rbp
0x18001ff07  pop     rbx
0x18001ff08  retn
```
