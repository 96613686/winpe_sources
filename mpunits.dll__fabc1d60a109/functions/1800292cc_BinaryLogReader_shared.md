# BinaryLogReader_shared

- ea: `0x1800292cc`
- end: `0x1800295f6`
- name: `BinaryLogReader_shared`
- size: `810`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpSrc@<rcx>, wchar_t *String@<rdx>, wchar_t *@<r8>, int, __int64)`
- caller_count: `6`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180020860`
- `0x180020a10`
- `0x180029010`
- `0x180029040`
- `0x180029600`
- `0x180029690`

## callees

- `0x180006e64`
- `0x180006ef8`
- `0x180007c80`
- `0x18000ab88`
- `0x18000abb8`
- `0x1800292cc`
- `0x180044836`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!malloc` at `0x18002937a`
- `msvcrt!malloc` at `0x1800293e6`
- `msvcrt!malloc` at `0x18002937a`
- `msvcrt!malloc` at `0x1800293e6`
- `msvcrt!free` at `0x18002951c`
- `msvcrt!free` at `0x18002951c`
- `msvcrt!_wcsdup` at `0x1800293c2`
- `msvcrt!_wcsdup` at `0x180029429`
- `msvcrt!_wcsdup` at `0x1800293c2`
- `msvcrt!_wcsdup` at `0x180029429`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800294a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180029551`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800294a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180029551`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800293a8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800293a8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180029365`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002939b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180029365`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002939b`

## string_xrefs

- `0x18002949a`: `mpunits.dll`
- `0x180029546`: `mpunits.dll`
- `0x1800294e7`: `MSFT DSC CU BINARY-LOG-READER`
- `0x1800294ca`: `DIRECTORY-NOT-FOUND`
- `0x1800294d5`: `BinaryLogReader`
- `0x180029570`: `BinaryLogReader`

## pseudocode

```c
__int64 __fastcall BinaryLogReader_shared(LPCWSTR lpSrc, wchar_t *String, wchar_t *a3, __int64 a4, int a5, _QWORD *a6)
{
  unsigned int v10; // ebx
  __int64 v11; // rdi
  DWORD v12; // eax
  DWORD v13; // esi
  WCHAR *v14; // rax
  DWORD FileAttributesW; // eax
  unsigned int v16; // eax
  unsigned int v17; // esi
  void *v18; // rax
  wchar_t *v19; // rax
  LPCWSTR v21; // rbx
  HMODULE v22; // rax
  void *v23; // rcx
  HMODULE ModuleHandleA; // rax
  __int64 v25; // [rsp+30h] [rbp-38h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-28h] BYREF

  v25 = 0;
  if ( !String || !*String )
  {
    *(_DWORD *)&EventDescriptor.Id = 202;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 1;
    Etw_Trace0(&EventDescriptor);
    EventDescriptor = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    *(_QWORD *)&EventDescriptor.Id = Intlstr_GetString_LoadString(ModuleHandleA, 2004);
    LOBYTE(EventDescriptor.Keyword) = 0;
    MI_ReportErrorDetails_ForCustomError(2, (int)L"BinaryLogReader", 0, 0);
    v10 = 4;
    goto LABEL_30;
  }
  if ( !((unsigned int (__fastcall *)(__int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 *, __int64))s_observableFT[0])(
          BinaryLogReader_OnSubscribe,
          BinaryLogReader_OnDestroy,
          &v25,
          48) )
  {
    v11 = v25 + 40;
    *(_OWORD *)(v25 + 40) = 0;
    *(_OWORD *)(v11 + 16) = 0;
    *(_OWORD *)(v11 + 32) = 0;
    v12 = ExpandEnvironmentStringsW(lpSrc, 0, 0);
    v13 = v12;
    if ( v12 )
    {
      v14 = (WCHAR *)malloc(2LL * v12);
      *(_QWORD *)v11 = v14;
      if ( !v14 || ExpandEnvironmentStringsW(lpSrc, v14, v13) != v13 )
        goto LABEL_7;
      FileAttributesW = GetFileAttributesW(*(LPCWSTR *)v11);
      if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
      {
        *(_QWORD *)(v11 + 8) = _wcsdup(String);
        if ( a4 && *(_QWORD *)a4 && (v16 = *(_DWORD *)(a4 + 8)) != 0 )
        {
          *(_DWORD *)(v11 + 40) = v16;
          v17 = v16;
          v18 = malloc(v16);
          *(_QWORD *)(v11 + 32) = v18;
          if ( !v18 )
          {
LABEL_7:
            v10 = 27;
LABEL_26:
            if ( v11 )
            {
              v23 = *(void **)(v11 + 32);
              if ( v23 )
                free(v23);
            }
            goto LABEL_30;
          }
          memcpy_0(v18, *(const void **)a4, v17);
        }
        else
        {
          *(_QWORD *)(v11 + 32) = 0;
          *(_DWORD *)(v11 + 40) = 0;
        }
        if ( !*(_QWORD *)v11 || !*(_QWORD *)(v11 + 8) )
          goto LABEL_7;
        if ( a3 )
        {
          v19 = _wcsdup(a3);
          *(_QWORD *)(v11 + 16) = v19;
          if ( !v19 )
            goto LABEL_7;
        }
        else
        {
          *(_QWORD *)(v11 + 16) = 0;
        }
        *(_DWORD *)(v11 + 24) = a5;
        *a6 = v25;
        *(_DWORD *)&EventDescriptor.Id = 206;
        *(_DWORD *)&EventDescriptor.Level = 4;
        EventDescriptor.Keyword = 1;
        Etw_Trace0(&EventDescriptor);
        return 0;
      }
      *(_DWORD *)&EventDescriptor.Id = 201;
      *(_DWORD *)&EventDescriptor.Level = 4;
      EventDescriptor.Keyword = 1;
      Etw_Trace1_LPCWSTR(&EventDescriptor);
      v21 = *(LPCWSTR *)v11;
      EventDescriptor = 0;
      v22 = GetModuleHandleA("mpunits.dll");
      *(_QWORD *)&EventDescriptor.Id = Intlstr_FormatString_FormatMessage(v22, 2003, v21);
      LOBYTE(EventDescriptor.Keyword) = 1;
      MI_ReportErrorDetails_ForCustomError(
        1,
        (int)L"BinaryLogReader",
        (__int64)L"MSFT DSC CU BINARY-LOG-READER",
        (__int64)L"DIRECTORY-NOT-FOUND");
    }
    v10 = 4;
    goto LABEL_26;
  }
  v10 = 27;
LABEL_30:
  if ( v25 )
  {
    if ( *(_QWORD *)v25 )
      (*(void (**)(void))(*(_QWORD *)v25 + 16LL))();
  }
  *(_DWORD *)&EventDescriptor.Id = 207;
  *(_DWORD *)&EventDescriptor.Level = 4;
  EventDescriptor.Keyword = 1;
  Etw_Trace0(&EventDescriptor);
  return v10;
}

```

## disassembly

```asm
0x1800292cc  push    rbp
0x1800292ce  push    rbx
0x1800292cf  push    rsi
0x1800292d0  push    rdi
0x1800292d1  push    r12
0x1800292d3  push    r13
0x1800292d5  push    r14
0x1800292d7  push    r15
0x1800292d9  mov     rbp, rsp
0x1800292dc  sub     rsp, 68h
0x1800292e0  mov     rax, cs:__security_cookie
0x1800292e7  xor     rax, rsp
0x1800292ea  mov     [rbp+var_18], rax
0x1800292ee  mov     r13, [rbp+arg_28]
0x1800292f2  xor     esi, esi
0x1800292f4  mov     [rbp+var_38], rsi
0x1800292f8  mov     rbx, r9
0x1800292fb  mov     r12, r8
0x1800292fe  mov     r14, rdx
0x180029301  mov     r15, rcx
0x180029304  test    rdx, rdx
0x180029307  jz      loc_180029524
0x18002930d  cmp     [rdx], si
0x180029310  jz      loc_180029524
0x180029316  mov     rax, cs:off_180047B90
0x18002931d  lea     r9d, [rsi+30h]
0x180029321  lea     r8, [rbp+var_38]
0x180029325  lea     rdx, BinaryLogReader_OnDestroy
0x18002932c  lea     rcx, BinaryLogReader_OnSubscribe
0x180029333  mov     rax, [rax]
0x180029336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002933b  test    eax, eax
0x18002933d  jz      short loc_180029347
0x18002933f  lea     ebx, [rsi+1Bh]
0x180029342  jmp     loc_18002959E
0x180029347  mov     rdi, [rbp+var_38]
0x18002934b  xorps   xmm0, xmm0
0x18002934e  add     rdi, 28h ; '('
0x180029352  xor     r8d, r8d; nSize
0x180029355  xor     edx, edx; lpDst
0x180029357  mov     rcx, r15; lpSrc
0x18002935a  movups  xmmword ptr [rdi], xmm0
0x18002935d  movups  xmmword ptr [rdi+10h], xmm0
0x180029361  movups  xmmword ptr [rdi+20h], xmm0
0x180029365  call    cs:__imp_ExpandEnvironmentStringsW
0x18002936b  mov     esi, eax
0x18002936d  test    eax, eax
0x18002936f  jz      loc_180029501
0x180029375  mov     ecx, esi
0x180029377  add     rcx, rcx; Size
0x18002937a  call    cs:__imp_malloc
0x180029380  mov     [rdi], rax
0x180029383  test    rax, rax
0x180029386  jnz     short loc_180029392
0x180029388  mov     ebx, 1Bh
0x18002938d  jmp     loc_180029506
0x180029392  mov     r8d, esi; nSize
0x180029395  mov     rdx, rax; lpDst
0x180029398  mov     rcx, r15; lpSrc
0x18002939b  call    cs:__imp_ExpandEnvironmentStringsW
0x1800293a1  cmp     eax, esi
0x1800293a3  jnz     short loc_180029388
0x1800293a5  mov     rcx, [rdi]; lpFileName
0x1800293a8  call    cs:__imp_GetFileAttributesW
0x1800293ae  cmp     eax, 0FFFFFFFFh
0x1800293b1  jz      loc_180029475
0x1800293b7  test    al, 10h
0x1800293b9  jz      loc_180029475
0x1800293bf  mov     rcx, r14; String
0x1800293c2  call    cs:__imp__wcsdup
0x1800293c8  xor     esi, esi
0x1800293ca  mov     [rdi+8], rax
0x1800293ce  test    rbx, rbx
0x1800293d1  jz      short loc_180029407
0x1800293d3  cmp     [rbx], rsi
0x1800293d6  jz      short loc_180029407
0x1800293d8  mov     eax, [rbx+8]
0x1800293db  test    eax, eax
0x1800293dd  jz      short loc_180029407
0x1800293df  mov     ecx, eax; Size
0x1800293e1  mov     [rdi+28h], eax
0x1800293e4  mov     esi, eax
0x1800293e6  call    cs:__imp_malloc
0x1800293ec  mov     [rdi+20h], rax
0x1800293f0  test    rax, rax
0x1800293f3  jz      short loc_180029388
0x1800293f5  mov     rdx, [rbx]; Src
0x1800293f8  mov     r8d, esi; Size
0x1800293fb  mov     rcx, rax; void *
0x1800293fe  call    memcpy_0
0x180029403  xor     esi, esi
0x180029405  jmp     short loc_18002940E
0x180029407  mov     [rdi+20h], rsi
0x18002940b  mov     [rdi+28h], esi
0x18002940e  cmp     [rdi], rsi
0x180029411  jz      loc_180029388
0x180029417  cmp     [rdi+8], rsi
0x18002941b  jz      loc_180029388
0x180029421  test    r12, r12
0x180029424  jz      short loc_18002943D
0x180029426  mov     rcx, r12; String
0x180029429  call    cs:__imp__wcsdup
0x18002942f  mov     [rdi+10h], rax
0x180029433  test    rax, rax
0x180029436  jnz     short loc_180029441
0x180029438  jmp     loc_180029388
0x18002943d  mov     [rdi+10h], rsi
0x180029441  mov     eax, [rbp+arg_20]
0x180029444  lea     rcx, [rbp+EventDescriptor]
0x180029448  mov     [rdi+18h], eax
0x18002944b  mov     rax, [rbp+var_38]
0x18002944f  mov     [r13+0], rax
0x180029453  mov     dword ptr [rbp+EventDescriptor.Id], 0CEh
0x18002945a  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x180029461  mov     [rbp+EventDescriptor.Keyword], 1
0x180029469  call    Etw_Trace0
0x18002946e  xor     eax, eax
0x180029470  jmp     loc_1800295D9
0x180029475  mov     rdx, [rdi]
0x180029478  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x18002947c  mov     dword ptr [rbp+EventDescriptor.Id], 0C9h
0x180029483  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18002948a  mov     [rbp+EventDescriptor.Keyword], 1
0x180029492  call    Etw_Trace1_LPCWSTR
0x180029497  mov     rbx, [rdi]
0x18002949a  lea     rcx, ModuleName; "mpunits.dll"
0x1800294a1  xorps   xmm0, xmm0
0x1800294a4  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x1800294a8  call    cs:__imp_GetModuleHandleA
0x1800294ae  mov     r8, rbx
0x1800294b1  mov     edx, 7D3h
0x1800294b6  mov     rcx, rax
0x1800294b9  call    _Intlstr_FormatString_FormatMessage
0x1800294be  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x1800294c2  lea     r9, [rbp+EventDescriptor]
0x1800294c6  mov     byte ptr [rbp+EventDescriptor.Keyword], 1
0x1800294ca  lea     rax, aDirectoryNotFo; "DIRECTORY-NOT-FOUND"
0x1800294d1  movaps  xmm0, xmmword ptr [rbp+EventDescriptor.Id]
0x1800294d5  lea     rdx, aBinarylogreade_1; "BinaryLogReader"
0x1800294dc  mov     [rsp+68h+var_40], rax; __int64
0x1800294e1  mov     r8d, 15h
0x1800294e7  lea     rax, aMsftDscCuBinar_0; "MSFT DSC CU BINARY-LOG-READER"
0x1800294ee  movdqa  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x1800294f3  mov     [rsp+68h+var_48], rax; __int64
0x1800294f8  lea     ecx, [r8-14h]; int
0x1800294fc  call    MI_ReportErrorDetails_ForCustomError
0x180029501  mov     ebx, 4
0x180029506  test    rdi, rdi
0x180029509  jz      loc_18002959E
0x18002950f  mov     rcx, [rdi+20h]; Block
0x180029513  test    rcx, rcx
0x180029516  jz      loc_18002959E
0x18002951c  call    cs:__imp_free
0x180029522  jmp     short loc_18002959E
0x180029524  lea     rcx, [rbp+EventDescriptor]
0x180029528  mov     dword ptr [rbp+EventDescriptor.Id], 0CAh
0x18002952f  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x180029536  mov     [rbp+EventDescriptor.Keyword], 1
0x18002953e  call    Etw_Trace0
0x180029543  xorps   xmm0, xmm0
0x180029546  lea     rcx, ModuleName; "mpunits.dll"
0x18002954d  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x180029551  call    cs:__imp_GetModuleHandleA
0x180029557  mov     rcx, rax
0x18002955a  mov     edx, 7D4h
0x18002955f  call    _Intlstr_GetString_LoadString
0x180029564  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x180029568  lea     r9, [rbp+EventDescriptor]
0x18002956c  mov     byte ptr [rbp+EventDescriptor.Keyword], sil
0x180029570  lea     rdx, aBinarylogreade_1; "BinaryLogReader"
0x180029577  movaps  xmm0, xmmword ptr [rbp+EventDescriptor.Id]
0x18002957b  mov     r8d, 5
0x180029581  mov     [rsp+68h+var_40], rsi; __int64
0x180029586  movdqa  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18002958b  mov     [rsp+68h+var_48], rsi; __int64
0x180029590  lea     ecx, [r8-3]; int
0x180029594  call    MI_ReportErrorDetails_ForCustomError
0x180029599  mov     ebx, 4
0x18002959e  mov     rcx, [rbp+var_38]
0x1800295a2  test    rcx, rcx
0x1800295a5  jz      short loc_1800295B8
0x1800295a7  mov     rax, [rcx]
0x1800295aa  test    rax, rax
0x1800295ad  jz      short loc_1800295B8
0x1800295af  mov     rax, [rax+10h]
0x1800295b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295b8  lea     rcx, [rbp+EventDescriptor]
0x1800295bc  mov     dword ptr [rbp+EventDescriptor.Id], 0CFh
0x1800295c3  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x1800295ca  mov     [rbp+EventDescriptor.Keyword], 1
0x1800295d2  call    Etw_Trace0
0x1800295d7  mov     eax, ebx
0x1800295d9  mov     rcx, [rbp+var_18]
0x1800295dd  xor     rcx, rsp; StackCookie
0x1800295e0  call    __security_check_cookie
0x1800295e5  add     rsp, 68h
0x1800295e9  pop     r15
0x1800295eb  pop     r14
0x1800295ed  pop     r13
0x1800295ef  pop     r12
0x1800295f1  pop     rdi
0x1800295f2  pop     rsi
0x1800295f3  pop     rbx
0x1800295f4  pop     rbp
0x1800295f5  retn
```
