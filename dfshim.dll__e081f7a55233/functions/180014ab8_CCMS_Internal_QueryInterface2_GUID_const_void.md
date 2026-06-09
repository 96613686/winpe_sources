# CCMS::Internal_QueryInterface2(_GUID const &,void * *)

- ea: `0x180014ab8`
- end: `0x180014dcb`
- name: `?Internal_QueryInterface2@CCMS@@IEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `787`
- prototype: `__int64 __fastcall(CCMS *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18006b5e0`

## callees

- `0x1800069b5`
- `0x1800069c1`
- `0x180014198`
- `0x180014ab8`
- `0x1800187f0`
- `0x180018940`
- `0x180018a34`
- `0x180018acc`
- `0x18001b270`
- `0x18002f678`
- `0x1800fe440`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180014b51`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180014bc4`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180014c00`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180014c42`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180014c6e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180014b51`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180014bc4`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180014c00`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180014c42`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180014c6e`

## string_xrefs

- `0x180014b60`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\helpers.cpp`
- `0x180014c77`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\helpers.cpp`
- `0x180014d0a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\helpers.cpp`
- `0x180014d7a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\helpers.cpp`
- `0x180014d97`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\helpers.cpp`

## pseudocode

```c
__int64 __fastcall CCMS::Internal_QueryInterface2(CCMS *this, const struct _GUID *a2, void **a3, int a4)
{
  __int64 v7; // rcx
  int Microdom; // eax
  unsigned int v9; // ebx
  __int64 v10; // r8
  int v11; // edx
  unsigned int v12; // ebx
  void *v13; // rcx
  __int64 *v14; // rdi
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  int v20; // ebx
  int v21; // edx
  unsigned int v22; // eax
  void *v23; // rdi
  HANDLE ProcessHeap_0; // rax
  void *v25; // xmm1_8
  int v26; // eax
  int v27; // r9d
  __int64 v28; // rdx
  void *v29; // rcx
  int v30; // eax
  int v31; // r9d
  __int128 v33; // [rsp+20h] [rbp-49h] BYREF
  void *v34; // [rsp+30h] [rbp-39h]
  LPVOID lpMem; // [rsp+38h] [rbp-31h] BYREF
  __int128 v36; // [rsp+40h] [rbp-29h] BYREF
  void *v37; // [rsp+50h] [rbp-19h]
  __int128 v38; // [rsp+60h] [rbp-9h] BYREF
  __int128 v39; // [rsp+70h] [rbp+7h] BYREF

  if ( *(_OWORD *)a2 != *(_OWORD *)&GUID_0000000c_0000_0000_c000_000000000046 )
  {
    v12 = -2147467262;
    Windows::ErrorHandling::COM::ReportErrorOrigination(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\helpers.cpp",
      (const char *)0x123,
      -2147467262,
      a4);
    return v12;
  }
  if ( *((_BYTE *)this + 64) )
    goto LABEL_35;
  v7 = *((_QWORD *)this + 5);
  *(_QWORD *)&v36 = 0;
  v38 = 0;
  v33 = 0u;
  v39 = 0;
  v34 = 0;
  lpMem = 0;
  Microdom = CdfFetchMicrodom(v7, &v36);
  v9 = Microdom;
  if ( Microdom >= 0 )
  {
    v14 = (__int64 *)v36;
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v36 + 24LL))(v36, &v38);
    v9 = v15;
    if ( v15 < 0 )
    {
      if ( v15 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      v10 = 278;
      goto LABEL_7;
    }
    v16 = *v14;
    v36 = v38;
    v17 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int128 *))(v16 + 16))(v14, &v36, &v39);
    v9 = v17;
    if ( v17 < 0 )
    {
      if ( v17 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      v10 = 279;
      goto LABEL_7;
    }
    v18 = *v14;
    v36 = v39;
    v19 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int128 *))(v18 + 144))(v14, &v36, &v33);
    v9 = v19;
    if ( v19 < 0 )
    {
      if ( v19 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      v10 = 280;
      goto LABEL_7;
    }
    v20 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<CStreamOnBlobWithLifetimeManagement>>::Allocate(
                       &lpMem,
                       &v36);
    if ( v20 < 0 )
    {
      if ( v20 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\helpers.cpp",
        (const char *)0x11A,
        v20,
        v33);
      v22 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v20, v21);
      v23 = lpMem;
      v12 = v22;
      goto LABEL_26;
    }
    v23 = lpMem;
    v25 = v34;
    v36 = v33;
    v33 = 0u;
    v34 = 0;
    v37 = v25;
    v26 = CStreamOnBlobWithLifetimeManagement::Initialize(lpMem, &v36);
    v12 = v26;
    if ( v26 < 0 )
    {
      v28 = 283;
LABEL_30:
      Windows::ErrorHandling::COM::ReportErrorPropagation(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\helpers.cpp",
        (const char *)v28,
        v26,
        v27);
LABEL_26:
      if ( v23 )
      {
        (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v23 + 112LL))(v23, 0);
        ProcessHeap_0 = GetProcessHeap_0();
        HeapFree_0(ProcessHeap_0, 0, v23);
      }
      goto LABEL_8;
    }
    v26 = (**(__int64 (__fastcall ***)(void *, GUID *, char *))v23)(
            v23,
            &GUID_0000000c_0000_0000_c000_000000000046,
            (char *)this + 56);
    v12 = v26;
    if ( v26 < 0 )
    {
      v28 = 284;
      goto LABEL_30;
    }
    v29 = v34;
    *((_BYTE *)this + 64) = 1;
    if ( v29 )
    {
      v33 = 0u;
      v34 = 0;
      IsolationFreeStringRoutine(v29);
    }
LABEL_35:
    v30 = (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 7))(
            *((_QWORD *)this + 7),
            a2,
            a3);
    v12 = v30;
    if ( v30 >= 0 )
      return 0;
    else
      Windows::ErrorHandling::COM::ReportErrorPropagation(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\helpers.cpp",
        (const char *)0x120,
        v30,
        v31);
    return v12;
  }
  if ( Microdom == g_NTSTATUS_to_break_on_propagate )
    DebugBreak();
  v10 = 277;
LABEL_7:
  Windows::ErrorHandling::COM::ReportError(
    (Windows::ErrorHandling::COM *)"Status propagated",
    "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\helpers.cpp",
    (const char *)v10,
    v9,
    v33);
  v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v9, v11);
LABEL_8:
  v13 = v34;
  if ( v34 )
  {
    v33 = 0u;
    v34 = 0;
    IsolationFreeStringRoutine(v13);
  }
  return v12;
}

```

## disassembly

```asm
0x180014ab8  push    rbp
0x180014aba  push    rbx
0x180014abb  push    rsi
0x180014abc  push    rdi
0x180014abd  push    r12
0x180014abf  push    r14
0x180014ac1  push    r15
0x180014ac3  lea     rbp, [rsp-27h]
0x180014ac8  sub     rsp, 90h
0x180014acf  mov     rax, cs:__security_cookie
0x180014ad6  xor     rax, rsp
0x180014ad9  mov     [rbp+57h+var_40], rax
0x180014add  mov     rax, [rdx]
0x180014ae0  mov     r15, r8
0x180014ae3  cmp     rax, qword ptr cs:_GUID_0000000c_0000_0000_c000_000000000046.Data1
0x180014aea  mov     r14, rdx
0x180014aed  mov     rsi, rcx
0x180014af0  jnz     loc_180014D92
0x180014af6  mov     rax, [rdx+8]
0x180014afa  cmp     rax, qword ptr cs:_GUID_0000000c_0000_0000_c000_000000000046.Data4
0x180014b01  jnz     loc_180014D92
0x180014b07  xor     r12d, r12d
0x180014b0a  cmp     [rcx+40h], r12b
0x180014b0e  jnz     loc_180014D5C
0x180014b14  mov     rcx, [rcx+28h]
0x180014b18  lea     rdx, [rbp+57h+var_80]
0x180014b1c  xorps   xmm0, xmm0
0x180014b1f  mov     qword ptr [rbp+57h+var_80], r12
0x180014b23  xorps   xmm1, xmm1
0x180014b26  mov     qword ptr [rbp+57h+var_A0+8], r12
0x180014b2a  movups  [rbp+57h+var_60], xmm0
0x180014b2e  mov     qword ptr [rbp+57h+var_A0], r12
0x180014b32  movups  [rbp+57h+var_50], xmm1
0x180014b36  mov     [rbp+57h+var_90], r12
0x180014b3a  mov     [rbp+57h+lpMem], r12
0x180014b3e  call    CdfFetchMicrodom
0x180014b43  mov     ebx, eax
0x180014b45  test    eax, eax
0x180014b47  jns     short loc_180014B9F
0x180014b49  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180014b4f  jnz     short loc_180014B57
0x180014b51  call    cs:__imp_DebugBreak
0x180014b57  mov     r8d, 115h; char *
0x180014b5d  mov     r9d, ebx; int
0x180014b60  lea     rdx, aOnecoreComNetf_24; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180014b67  lea     rcx, aStatusPropagat; "Status propagated"
0x180014b6e  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180014b73  mov     ecx, ebx; this
0x180014b75  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180014b7a  mov     ebx, eax
0x180014b7c  mov     rcx, [rbp+57h+var_90]; lpMem
0x180014b80  test    rcx, rcx
0x180014b83  jz      loc_180014DAB
0x180014b89  mov     qword ptr [rbp+57h+var_A0+8], r12
0x180014b8d  mov     qword ptr [rbp+57h+var_A0], r12
0x180014b91  mov     [rbp+57h+var_90], r12
0x180014b95  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180014b9a  jmp     loc_180014DAB
0x180014b9f  mov     rdi, qword ptr [rbp+57h+var_80]
0x180014ba3  lea     rdx, [rbp+57h+var_60]
0x180014ba7  mov     rcx, rdi
0x180014baa  mov     rax, [rdi]
0x180014bad  mov     rax, [rax+18h]
0x180014bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bb6  mov     ebx, eax
0x180014bb8  test    eax, eax
0x180014bba  jns     short loc_180014BD2
0x180014bbc  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180014bc2  jnz     short loc_180014BCA
0x180014bc4  call    cs:__imp_DebugBreak
0x180014bca  mov     r8d, 116h
0x180014bd0  jmp     short loc_180014B5D
0x180014bd2  mov     rax, [rdi]
0x180014bd5  lea     r8, [rbp+57h+var_50]
0x180014bd9  movaps  xmm0, [rbp+57h+var_60]
0x180014bdd  lea     rdx, [rbp+57h+var_80]
0x180014be1  mov     rcx, rdi
0x180014be4  movdqa  [rbp+57h+var_80], xmm0
0x180014be9  mov     rax, [rax+10h]
0x180014bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bf2  mov     ebx, eax
0x180014bf4  test    eax, eax
0x180014bf6  jns     short loc_180014C11
0x180014bf8  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180014bfe  jnz     short loc_180014C06
0x180014c00  call    cs:__imp_DebugBreak
0x180014c06  mov     r8d, 117h
0x180014c0c  jmp     loc_180014B5D
0x180014c11  mov     rax, [rdi]
0x180014c14  lea     r8, [rbp+57h+var_A0]
0x180014c18  movaps  xmm0, [rbp+57h+var_50]
0x180014c1c  lea     rdx, [rbp+57h+var_80]
0x180014c20  mov     rcx, rdi
0x180014c23  movdqa  [rbp+57h+var_80], xmm0
0x180014c28  mov     rax, [rax+90h]
0x180014c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c34  mov     ebx, eax
0x180014c36  test    eax, eax
0x180014c38  jns     short loc_180014C53
0x180014c3a  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180014c40  jnz     short loc_180014C48
0x180014c42  call    cs:__imp_DebugBreak
0x180014c48  mov     r8d, 118h
0x180014c4e  jmp     loc_180014B5D
0x180014c53  lea     rdx, [rbp+57h+var_80]
0x180014c57  lea     rcx, [rbp+57h+lpMem]
0x180014c5b  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@VCStreamOnBlobWithLifetimeManagement@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<CStreamOnBlobWithLifetimeManagement>>::Allocate(void)
0x180014c60  mov     ebx, [rax]
0x180014c62  test    ebx, ebx
0x180014c64  jns     short loc_180014CCE
0x180014c66  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180014c6c  jnz     short loc_180014C74
0x180014c6e  call    cs:__imp_DebugBreak
0x180014c74  mov     r9d, ebx; int
0x180014c77  lea     rdx, aOnecoreComNetf_24; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180014c7e  mov     r8d, 11Ah; char *
0x180014c84  lea     rcx, aStatusPropagat; "Status propagated"
0x180014c8b  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180014c90  mov     ecx, ebx; this
0x180014c92  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180014c97  mov     rdi, [rbp+57h+lpMem]
0x180014c9b  mov     ebx, eax
0x180014c9d  test    rdi, rdi
0x180014ca0  jz      loc_180014B7C
0x180014ca6  mov     rax, [rdi]
0x180014ca9  xor     edx, edx
0x180014cab  mov     rcx, rdi
0x180014cae  mov     rax, [rax+70h]
0x180014cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cb7  call    GetProcessHeap_0
0x180014cbc  mov     r8, rdi; lpMem
0x180014cbf  xor     edx, edx; dwFlags
0x180014cc1  mov     rcx, rax; hHeap
0x180014cc4  call    HeapFree_0
0x180014cc9  jmp     loc_180014B7C
0x180014cce  movups  xmm0, [rbp+57h+var_A0]
0x180014cd2  lea     rdx, [rbp+57h+var_80]
0x180014cd6  mov     rdi, [rbp+57h+lpMem]
0x180014cda  movsd   xmm1, [rbp+57h+var_90]
0x180014cdf  mov     rcx, rdi
0x180014ce2  movaps  [rbp+57h+var_80], xmm0
0x180014ce6  mov     qword ptr [rbp+57h+var_A0+8], r12
0x180014cea  mov     qword ptr [rbp+57h+var_A0], r12
0x180014cee  mov     [rbp+57h+var_90], r12
0x180014cf2  movsd   [rbp+57h+var_70], xmm1
0x180014cf7  call    ?Initialize@CStreamOnBlobWithLifetimeManagement@@QEAAJU_LBLOB@@@Z; CStreamOnBlobWithLifetimeManagement::Initialize(_LBLOB)
0x180014cfc  mov     ebx, eax
0x180014cfe  test    eax, eax
0x180014d00  jns     short loc_180014D18
0x180014d02  mov     edx, 11Bh; char *
0x180014d07  mov     r8d, eax; int
0x180014d0a  lea     rcx, aOnecoreComNetf_24; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180014d11  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180014d16  jmp     short loc_180014C9D
0x180014d18  mov     rax, [rdi]
0x180014d1b  lea     r8, [rsi+38h]
0x180014d1f  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180014d26  mov     rcx, rdi
0x180014d29  mov     rax, [rax]
0x180014d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d31  mov     ebx, eax
0x180014d33  test    eax, eax
0x180014d35  jns     short loc_180014D3E
0x180014d37  mov     edx, 11Ch
0x180014d3c  jmp     short loc_180014D07
0x180014d3e  mov     rcx, [rbp+57h+var_90]; lpMem
0x180014d42  mov     byte ptr [rsi+40h], 1
0x180014d46  test    rcx, rcx
0x180014d49  jz      short loc_180014D5C
0x180014d4b  mov     qword ptr [rbp+57h+var_A0+8], r12
0x180014d4f  mov     qword ptr [rbp+57h+var_A0], r12
0x180014d53  mov     [rbp+57h+var_90], r12
0x180014d57  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180014d5c  mov     rcx, [rsi+38h]
0x180014d60  mov     r8, r15
0x180014d63  mov     rdx, r14
0x180014d66  mov     rax, [rcx]
0x180014d69  mov     rax, [rax]
0x180014d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d71  mov     ebx, eax
0x180014d73  test    eax, eax
0x180014d75  jns     short loc_180014D8D
0x180014d77  mov     r8d, eax; int
0x180014d7a  lea     rcx, aOnecoreComNetf_24; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180014d81  mov     edx, 120h; char *
0x180014d86  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180014d8b  jmp     short loc_180014DAB
0x180014d8d  mov     ebx, r12d
0x180014d90  jmp     short loc_180014DAB
0x180014d92  mov     ebx, 80004002h
0x180014d97  lea     rcx, aOnecoreComNetf_24; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180014d9e  mov     r8d, ebx; int
0x180014da1  mov     edx, 123h; char *
0x180014da6  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x180014dab  mov     eax, ebx
0x180014dad  mov     rcx, [rbp+57h+var_40]
0x180014db1  xor     rcx, rsp; StackCookie
0x180014db4  call    __security_check_cookie
0x180014db9  add     rsp, 90h
0x180014dc0  pop     r15
0x180014dc2  pop     r14
0x180014dc4  pop     r12
0x180014dc6  pop     rdi
0x180014dc7  pop     rsi
0x180014dc8  pop     rbx
0x180014dc9  pop     rbp
0x180014dca  retn
```
