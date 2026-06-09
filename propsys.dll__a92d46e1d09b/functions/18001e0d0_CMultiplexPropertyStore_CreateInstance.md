# CMultiplexPropertyStore_CreateInstance

- ea: `0x18001e0d0`
- end: `0x18001e2da`
- name: `CMultiplexPropertyStore_CreateInstance`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180080360`

## callees

- `0x18001e0d0`
- `0x18001e2e0`
- `0x18006ed20`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e257`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e257`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18001e298`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18001e298`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001e13b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001e13b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e0fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e0fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e112`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e112`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18001e2b6`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18001e2b6`

## pseudocode

```c
__int64 __fastcall CMultiplexPropertyStore_CreateInstance(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  HANDLE ProcessHeap; // rax
  char *v7; // rax
  char *v8; // rbx
  int v9; // edi
  int v10; // eax
  int ApartmentId; // edi
  int v13; // ecx
  WCHAR Filename[264]; // [rsp+30h] [rbp-238h] BYREF

  *a4 = 0;
  ProcessHeap = GetProcessHeap();
  v7 = (char *)HeapAlloc(ProcessHeap, 8u, 0x98u);
  v8 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 26) = -2;
    *((_DWORD *)v7 + 27) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v7 + 64));
    *((_DWORD *)v8 + 28) = 1;
    *(_QWORD *)v8 = &CMultiplexPropertyStore::`vftable'{for `IPropertyStore'};
    *((_QWORD *)v8 + 1) = &CMultiplexPropertyStore::`vftable'{for `INamedPropertyStore'};
    *((_QWORD *)v8 + 2) = &CMultiplexPropertyStore::`vftable'{for `IPropertyStoreWithDiagnostic'};
    *((_QWORD *)v8 + 3) = &CMultiplexPropertyStore::`vftable'{for `IObjectProvider'};
    *((_QWORD *)v8 + 4) = &CMultiplexPropertyStore::`vftable'{for `IPropertyStoreCapabilities'};
    *((_QWORD *)v8 + 5) = &CMultiplexPropertyStore::`vftable'{for `IInitializeWithPropertyStores'};
    *((_QWORD *)v8 + 6) = &CMultiplexPropertyStore::`vftable'{for `IPersistPropertyBag'};
    *((_QWORD *)v8 + 7) = &CMultiplexPropertyStore::`vftable'{for `IInitializeWithStream'};
    *((_QWORD *)v8 + 15) = 0;
    *((_QWORD *)v8 + 16) = 0;
    *((_QWORD *)v8 + 17) = 0;
    *((_QWORD *)v8 + 18) = 0;
    _InterlockedIncrement(&g_cRefThisDll);
    v9 = *((_DWORD *)v8 + 27);
    if ( v9 != 2 )
    {
      v10 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
      if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
        goto LABEL_4;
      if ( GetModuleFileNameW(0, Filename, 0x104u) )
      {
        v13 = (FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1) + 1;
        `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = v13;
      }
      else
      {
        v13 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
      }
      if ( v13 != 1 )
        goto LABEL_8;
      if ( v9 == 1 )
      {
        if ( (unsigned int)IsAppCompatModeEnabled(16) )
        {
          `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
          goto LABEL_8;
        }
        v10 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
LABEL_4:
        if ( v10 != 1 )
          goto LABEL_8;
      }
    }
    ApartmentId = SHCoGetApartmentId((unsigned int *)v8 + 26);
    if ( ApartmentId < 0 )
    {
LABEL_9:
      (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8);
      return (unsigned int)ApartmentId;
    }
LABEL_8:
    ApartmentId = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v8)(v8, a3, a4);
    goto LABEL_9;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001e0d0  mov     [rsp+arg_8], rbx
0x18001e0d5  push    rbp
0x18001e0d6  push    rsi
0x18001e0d7  push    r14
0x18001e0d9  sub     rsp, 250h
0x18001e0e0  mov     rax, cs:__security_cookie
0x18001e0e7  xor     rax, rsp
0x18001e0ea  mov     [rsp+268h+var_28], rax
0x18001e0f2  xor     r14d, r14d
0x18001e0f5  mov     rsi, r9
0x18001e0f8  mov     [r9], r14
0x18001e0fb  mov     rbp, r8
0x18001e0fe  call    cs:__imp_GetProcessHeap
0x18001e104  mov     edx, 8; dwFlags
0x18001e109  mov     r8d, 98h; dwBytes
0x18001e10f  mov     rcx, rax; hHeap
0x18001e112  call    cs:__imp_HeapAlloc
0x18001e118  mov     rbx, rax
0x18001e11b  test    rax, rax
0x18001e11e  jz      loc_18001E243
0x18001e124  lea     rcx, [rax+40h]; lpCriticalSection
0x18001e128  mov     [rsp+268h+arg_0], rdi
0x18001e130  mov     dword ptr [rcx+28h], 0FFFFFFFEh
0x18001e137  mov     [rcx+2Ch], r14d
0x18001e13b  call    cs:__imp_InitializeCriticalSection
0x18001e141  mov     dword ptr [rbx+70h], 1
0x18001e148  lea     rax, ??_7CMultiplexPropertyStore@@6BIPropertyStore@@@; const CMultiplexPropertyStore::`vftable'{for `IPropertyStore'}
0x18001e14f  mov     [rbx], rax
0x18001e152  lea     rax, ??_7CMultiplexPropertyStore@@6BINamedPropertyStore@@@; const CMultiplexPropertyStore::`vftable'{for `INamedPropertyStore'}
0x18001e159  mov     [rbx+8], rax
0x18001e15d  lea     rax, ??_7CMultiplexPropertyStore@@6BIPropertyStoreWithDiagnostic@@@; const CMultiplexPropertyStore::`vftable'{for `IPropertyStoreWithDiagnostic'}
0x18001e164  mov     [rbx+10h], rax
0x18001e168  lea     rax, ??_7CMultiplexPropertyStore@@6BIObjectProvider@@@; const CMultiplexPropertyStore::`vftable'{for `IObjectProvider'}
0x18001e16f  mov     [rbx+18h], rax
0x18001e173  lea     rax, ??_7CMultiplexPropertyStore@@6BIPropertyStoreCapabilities@@@; const CMultiplexPropertyStore::`vftable'{for `IPropertyStoreCapabilities'}
0x18001e17a  mov     [rbx+20h], rax
0x18001e17e  lea     rax, ??_7CMultiplexPropertyStore@@6BIInitializeWithPropertyStores@@@; const CMultiplexPropertyStore::`vftable'{for `IInitializeWithPropertyStores'}
0x18001e185  mov     [rbx+28h], rax
0x18001e189  lea     rax, ??_7CMultiplexPropertyStore@@6BIPersistPropertyBag@@@; const CMultiplexPropertyStore::`vftable'{for `IPersistPropertyBag'}
0x18001e190  mov     [rbx+30h], rax
0x18001e194  lea     rax, ??_7CMultiplexPropertyStore@@6BIInitializeWithStream@@@; const CMultiplexPropertyStore::`vftable'{for `IInitializeWithStream'}
0x18001e19b  mov     [rbx+38h], rax
0x18001e19f  mov     [rbx+78h], r14
0x18001e1a3  mov     [rbx+80h], r14
0x18001e1aa  mov     [rbx+88h], r14
0x18001e1b1  mov     [rbx+90h], r14
0x18001e1b8  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18001e1bf  mov     edi, [rbx+6Ch]
0x18001e1c2  cmp     edi, 2
0x18001e1c5  jz      short loc_18001E1E1
0x18001e1c7  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001e1cd  test    eax, eax
0x18001e1cf  jz      short loc_18001E24A
0x18001e1d1  cmp     eax, 1
0x18001e1d4  jnz     short loc_18001E1F0
0x18001e1d6  jmp     short loc_18001E1E1
0x18001e1d8  cmp     edi, 1
0x18001e1db  jz      loc_18001E2B1
0x18001e1e1  lea     rcx, [rbx+68h]; unsigned int *
0x18001e1e5  call    ?SHCoGetApartmentId@@YAJPEAK@Z; SHCoGetApartmentId(ulong *)
0x18001e1ea  mov     edi, eax
0x18001e1ec  test    eax, eax
0x18001e1ee  js      short loc_18001E206
0x18001e1f0  mov     rax, [rbx]
0x18001e1f3  mov     r8, rsi
0x18001e1f6  mov     rdx, rbp
0x18001e1f9  mov     rcx, rbx
0x18001e1fc  mov     rax, [rax]
0x18001e1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e204  mov     edi, eax
0x18001e206  mov     rax, [rbx]
0x18001e209  mov     rcx, rbx
0x18001e20c  mov     rax, [rax+10h]
0x18001e210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e215  mov     eax, edi
0x18001e217  mov     rdi, [rsp+268h+arg_0]
0x18001e21f  mov     rcx, [rsp+268h+var_28]
0x18001e227  xor     rcx, rsp; StackCookie
0x18001e22a  call    __security_check_cookie
0x18001e22f  mov     rbx, [rsp+268h+arg_8]
0x18001e237  add     rsp, 250h
0x18001e23e  pop     r14
0x18001e240  pop     rsi
0x18001e241  pop     rbp
0x18001e242  retn
0x18001e243  mov     eax, 8007000Eh
0x18001e248  jmp     short loc_18001E21F
0x18001e24a  mov     r8d, 104h; nSize
0x18001e250  lea     rdx, [rsp+268h+Filename]; lpFilename
0x18001e255  xor     ecx, ecx; hModule
0x18001e257  call    cs:__imp_GetModuleFileNameW
0x18001e25d  test    eax, eax
0x18001e25f  jnz     short loc_18001E271
0x18001e261  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001e267  cmp     ecx, 1
0x18001e26a  jnz     short loc_18001E1F0
0x18001e26c  jmp     loc_18001E1D8
0x18001e271  mov     [rsp+268h+bIgnoreCase], 1; bIgnoreCase
0x18001e279  lea     r9, StringValue; "\\EXPLORER.EXE"
0x18001e280  mov     r8d, 0FFFFFFFFh; cchSource
0x18001e286  mov     [rsp+268h+cchValue], 0FFFFFFFFh; cchValue
0x18001e28e  lea     rdx, [rsp+268h+Filename]; lpStringSource
0x18001e293  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x18001e298  call    cs:__imp_FindStringOrdinal
0x18001e29e  cmp     eax, 0FFFFFFFFh
0x18001e2a1  mov     ecx, r14d
0x18001e2a4  setnz   cl
0x18001e2a7  inc     ecx
0x18001e2a9  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, ecx; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001e2af  jmp     short loc_18001E267
0x18001e2b1  mov     ecx, 10h
0x18001e2b6  call    cs:__imp_IsAppCompatModeEnabled
0x18001e2bc  test    eax, eax
0x18001e2be  jz      short loc_18001E2CF
0x18001e2c0  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001e2ca  jmp     loc_18001E1F0
0x18001e2cf  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001e2d5  jmp     loc_18001E1D1
```
