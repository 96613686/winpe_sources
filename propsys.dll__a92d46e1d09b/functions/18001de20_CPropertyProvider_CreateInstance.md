# CPropertyProvider_CreateInstance

- ea: `0x18001de20`
- end: `0x18001e0c5`
- name: `CPropertyProvider_CreateInstance`
- size: `677`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001de20`
- `0x18001e2e0`
- `0x18001e3c8`
- `0x18006bb14`
- `0x18006ed20`
- `0x18006fb74`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e06d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e06d`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18001df62`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18001df62`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001de8e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001de8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001de4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001de4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001de5e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001de5e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001dfa2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001dfa2`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001e032`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001e032`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18001e0a1`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18001e0a1`

## pseudocode

```c
__int64 __fastcall CPropertyProvider_CreateInstance(__int64 a1, __int64 a2, const IID *a3, void **a4)
{
  HANDLE ProcessHeap; // rax
  char *v7; // rax
  char *v8; // rbx
  int v9; // edi
  int v10; // eax
  HRESULT ApartmentId; // edi
  __int64 (__fastcall ***v13)(_QWORD, const IID *, void **); // rcx
  WCHAR StringSource[264]; // [rsp+40h] [rbp-248h] BYREF

  *a4 = 0;
  ProcessHeap = GetProcessHeap();
  v7 = (char *)HeapAlloc(ProcessHeap, 8u, 0xA0u);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  *((_DWORD *)v7 + 28) = -2;
  *((_DWORD *)v7 + 29) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v7 + 72));
  *((_DWORD *)v8 + 30) = 1;
  *(_QWORD *)v8 = &CPropertyProvider::`vftable'{for `IPropertyProvider'};
  *((_QWORD *)v8 + 1) = &CPropertyProvider::`vftable'{for `INamedPropertyStore'};
  *((_QWORD *)v8 + 2) = &CPropertyProvider::`vftable'{for `IPropertyStoreInit'};
  *((_QWORD *)v8 + 3) = &CPropertyProvider::`vftable'{for `IObjectProvider'};
  *((_QWORD *)v8 + 4) = &CPropertyProvider::`vftable'{for `IPropertyStoreCapabilities'};
  *((_QWORD *)v8 + 5) = &CPropertyProvider::`vftable'{for `IPropertyStoreWithDiagnostic'};
  *((_QWORD *)v8 + 6) = &CPropertyProvider::`vftable'{for `IObjectWithClassIdentity'};
  *((_QWORD *)v8 + 7) = &CPropertyProvider::`vftable'{for `IInitializeWithDelegate'};
  *((_QWORD *)v8 + 8) = &CPropertyProvider::`vftable'{for `ISetFileChangeSourceInfo'};
  *((_QWORD *)v8 + 16) = 0;
  *((_QWORD *)v8 + 17) = 0;
  *((_QWORD *)v8 + 18) = 0;
  *((_QWORD *)v8 + 19) = 0;
  _InterlockedIncrement(&g_cRefThisDll);
  v9 = *((_DWORD *)v8 + 29);
  if ( v9 == 2 )
    goto LABEL_9;
  v10 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  if ( !`_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
  {
    if ( GetModuleFileNameW(0, StringSource, 0x104u) )
    {
      if ( FindStringOrdinal(0x800000u, StringSource, -1, L"\\EXPLORER.EXE", -1, 1) != -1 )
      {
        `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
        goto LABEL_10;
      }
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 1;
    }
    else if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess != 1 )
    {
      goto LABEL_10;
    }
    if ( v9 != 1 )
      goto LABEL_9;
    if ( (unsigned int)IsAppCompatModeEnabled(16) )
    {
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
      goto LABEL_10;
    }
    v10 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  }
  if ( v10 != 1 )
  {
LABEL_10:
    ApartmentId = QISearch(v8, &stru_1800B1870, a3, a4);
    if ( ApartmentId < 0 && !memcmp_0(&IID_IMarshal, a3, 0x10u) )
    {
      if ( !*((_QWORD *)v8 + 19) )
        CoCreateFreeThreadedMarshaler((LPUNKNOWN)v8, (LPUNKNOWN *)v8 + 19);
      v13 = (__int64 (__fastcall ***)(_QWORD, const IID *, void **))*((_QWORD *)v8 + 19);
      if ( v13 )
        ApartmentId = (**v13)(v13, a3, a4);
    }
    goto LABEL_11;
  }
LABEL_9:
  ApartmentId = SHCoGetApartmentId((unsigned int *)v8 + 28);
  if ( ApartmentId >= 0 )
    goto LABEL_10;
LABEL_11:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 30, 0xFFFFFFFF) == 1 )
  {
    CPropertyProvider::~CPropertyProvider((CPropertyProvider *)v8);
    operator delete(v8, (const struct std::nothrow_t *)0xA0);
  }
  return (unsigned int)ApartmentId;
}

```

## disassembly

```asm
0x18001de20  push    rbx
0x18001de22  push    rbp
0x18001de23  push    rdi
0x18001de24  push    r14
0x18001de26  sub     rsp, 268h
0x18001de2d  mov     rax, cs:__security_cookie
0x18001de34  xor     rax, rsp
0x18001de37  mov     [rsp+288h+var_38], rax
0x18001de3f  xor     edi, edi
0x18001de41  mov     r14, r9
0x18001de44  mov     [r9], rdi
0x18001de47  mov     rbp, r8
0x18001de4a  call    cs:__imp_GetProcessHeap
0x18001de50  mov     edx, 8; dwFlags
0x18001de55  mov     r8d, 0A0h; dwBytes
0x18001de5b  mov     rcx, rax; hHeap
0x18001de5e  call    cs:__imp_HeapAlloc
0x18001de64  mov     rbx, rax
0x18001de67  test    rax, rax
0x18001de6a  jz      loc_18001DFFE
0x18001de70  lea     rcx, [rax+48h]; lpCriticalSection
0x18001de74  mov     [rsp+288h+arg_0], rsi
0x18001de7c  mov     dword ptr [rcx+28h], 0FFFFFFFEh
0x18001de83  mov     [rcx+2Ch], edi
0x18001de86  mov     [rsp+288h+var_28], r15
0x18001de8e  call    cs:__imp_InitializeCriticalSection
0x18001de94  lea     rax, ??_7CPropertyProvider@@6BIPropertyProvider@@@; const CPropertyProvider::`vftable'{for `IPropertyProvider'}
0x18001de9b  mov     dword ptr [rbx+78h], 1
0x18001dea2  mov     [rbx], rax
0x18001dea5  lea     rax, ??_7CPropertyProvider@@6BINamedPropertyStore@@@; const CPropertyProvider::`vftable'{for `INamedPropertyStore'}
0x18001deac  mov     [rbx+8], rax
0x18001deb0  lea     rax, ??_7CPropertyProvider@@6BIPropertyStoreInit@@@; const CPropertyProvider::`vftable'{for `IPropertyStoreInit'}
0x18001deb7  mov     [rbx+10h], rax
0x18001debb  lea     rax, ??_7CPropertyProvider@@6BIObjectProvider@@@; const CPropertyProvider::`vftable'{for `IObjectProvider'}
0x18001dec2  mov     [rbx+18h], rax
0x18001dec6  lea     rax, ??_7CPropertyProvider@@6BIPropertyStoreCapabilities@@@; const CPropertyProvider::`vftable'{for `IPropertyStoreCapabilities'}
0x18001decd  mov     [rbx+20h], rax
0x18001ded1  lea     rax, ??_7CPropertyProvider@@6BIPropertyStoreWithDiagnostic@@@; const CPropertyProvider::`vftable'{for `IPropertyStoreWithDiagnostic'}
0x18001ded8  mov     [rbx+28h], rax
0x18001dedc  lea     rax, ??_7CPropertyProvider@@6BIObjectWithClassIdentity@@@; const CPropertyProvider::`vftable'{for `IObjectWithClassIdentity'}
0x18001dee3  mov     [rbx+30h], rax
0x18001dee7  lea     rax, ??_7CPropertyProvider@@6BIInitializeWithDelegate@@@; const CPropertyProvider::`vftable'{for `IInitializeWithDelegate'}
0x18001deee  mov     [rbx+38h], rax
0x18001def2  lea     rax, ??_7CPropertyProvider@@6BISetFileChangeSourceInfo@@@; const CPropertyProvider::`vftable'{for `ISetFileChangeSourceInfo'}
0x18001def9  mov     [rbx+40h], rax
0x18001defd  mov     [rbx+80h], rdi
0x18001df04  mov     [rbx+88h], rdi
0x18001df0b  mov     [rbx+90h], rdi
0x18001df12  mov     [rbx+98h], rdi
0x18001df19  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18001df20  mov     edi, [rbx+74h]
0x18001df23  mov     esi, 0FFFFFFFFh
0x18001df28  cmp     edi, 2
0x18001df2b  jz      short loc_18001DF83
0x18001df2d  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001df33  test    eax, eax
0x18001df35  jz      loc_18001E060
0x18001df3b  cmp     eax, 1
0x18001df3e  jnz     short loc_18001DF92
0x18001df40  jmp     short loc_18001DF83
0x18001df42  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x18001df4a  lea     r9, StringValue; "\\EXPLORER.EXE"
0x18001df51  mov     r8d, esi; cchSource
0x18001df54  mov     [rsp+288h+cchValue], esi; cchValue
0x18001df58  lea     rdx, [rsp+288h+StringSource]; lpStringSource
0x18001df5d  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x18001df62  call    cs:__imp_FindStringOrdinal
0x18001df68  cmp     eax, esi
0x18001df6a  jnz     loc_18001E08D
0x18001df70  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 1; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001df7a  cmp     edi, 1
0x18001df7d  jz      loc_18001E09C
0x18001df83  lea     rcx, [rbx+70h]; unsigned int *
0x18001df87  call    ?SHCoGetApartmentId@@YAJPEAK@Z; SHCoGetApartmentId(ulong *)
0x18001df8c  mov     edi, eax
0x18001df8e  test    eax, eax
0x18001df90  js      short loc_18001DFAE
0x18001df92  mov     r9, r14; ppv
0x18001df95  lea     rdx, stru_1800B1870; pqit
0x18001df9c  mov     r8, rbp; riid
0x18001df9f  mov     rcx, rbx; that
0x18001dfa2  call    cs:__imp_QISearch
0x18001dfa8  mov     edi, eax
0x18001dfaa  test    eax, eax
0x18001dfac  js      short loc_18001E005
0x18001dfae  lock xadd [rbx+78h], esi
0x18001dfb3  mov     r15, [rsp+288h+var_28]
0x18001dfbb  cmp     esi, 1
0x18001dfbe  mov     rsi, [rsp+288h+arg_0]
0x18001dfc6  jz      short loc_18001DFE7
0x18001dfc8  mov     eax, edi
0x18001dfca  mov     rcx, [rsp+288h+var_38]
0x18001dfd2  xor     rcx, rsp; StackCookie
0x18001dfd5  call    __security_check_cookie
0x18001dfda  add     rsp, 268h
0x18001dfe1  pop     r14
0x18001dfe3  pop     rdi
0x18001dfe4  pop     rbp
0x18001dfe5  pop     rbx
0x18001dfe6  retn
0x18001dfe7  mov     rcx, rbx; this
0x18001dfea  call    ??1CPropertyProvider@@AEAA@XZ; CPropertyProvider::~CPropertyProvider(void)
0x18001dfef  mov     edx, 0A0h; struct std::nothrow_t *
0x18001dff4  mov     rcx, rbx; void *
0x18001dff7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001dffc  jmp     short loc_18001DFC8
0x18001dffe  mov     eax, 8007000Eh
0x18001e003  jmp     short loc_18001DFCA
0x18001e005  mov     r8d, 10h; Size
0x18001e00b  lea     rcx, IID_IMarshal; Buf1
0x18001e012  mov     rdx, rbp; Buf2
0x18001e015  call    memcmp_0
0x18001e01a  test    eax, eax
0x18001e01c  jnz     short loc_18001DFAE
0x18001e01e  cmp     qword ptr [rbx+98h], 0
0x18001e026  jnz     short loc_18001E038
0x18001e028  lea     rdx, [rbx+98h]; ppunkMarshal
0x18001e02f  mov     rcx, rbx; punkOuter
0x18001e032  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18001e038  mov     rcx, [rbx+98h]
0x18001e03f  test    rcx, rcx
0x18001e042  jz      loc_18001DFAE
0x18001e048  mov     rax, [rcx]
0x18001e04b  mov     r8, r14
0x18001e04e  mov     rdx, rbp
0x18001e051  mov     rax, [rax]
0x18001e054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e059  mov     edi, eax
0x18001e05b  jmp     loc_18001DFAE
0x18001e060  mov     r8d, 104h; nSize
0x18001e066  lea     rdx, [rsp+288h+StringSource]; lpFilename
0x18001e06b  xor     ecx, ecx; hModule
0x18001e06d  call    cs:__imp_GetModuleFileNameW
0x18001e073  test    eax, eax
0x18001e075  jnz     loc_18001DF42
0x18001e07b  cmp     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 1; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001e082  jnz     loc_18001DF92
0x18001e088  jmp     loc_18001DF7A
0x18001e08d  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001e097  jmp     loc_18001DF92
0x18001e09c  mov     ecx, 10h
0x18001e0a1  call    cs:__imp_IsAppCompatModeEnabled
0x18001e0a7  test    eax, eax
0x18001e0a9  jz      short loc_18001E0BA
0x18001e0ab  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001e0b5  jmp     loc_18001DF92
0x18001e0ba  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001e0c0  jmp     loc_18001DF3B
```
