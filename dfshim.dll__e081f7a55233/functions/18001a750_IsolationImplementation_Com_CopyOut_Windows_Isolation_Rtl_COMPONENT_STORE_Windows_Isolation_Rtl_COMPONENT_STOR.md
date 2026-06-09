# IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_COMPONENT_STORE,Windows::Isolation::Rtl::_COMPONENT_STORE_COMPONENT_ENUMERATOR,_GUID const &,IUnknown * *)

- ea: `0x18001a750`
- end: `0x18001a8d0`
- name: `?CopyOut@Com@IsolationImplementation@@YAJU_COMPONENT_STORE@Rtl@Isolation@Windows@@U_COMPONENT_STORE_COMPONENT_ENUMERATOR@456@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `384`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800a1fa0`
- `0x1800ac0f8`

## callees

- `0x1800069a9`
- `0x1800069b5`
- `0x1800069c1`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18001a750`
- `0x1800a1e8c`
- `0x1800a2090`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001a7cd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001a893`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001a7cd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001a893`

## string_xrefs

- `0x18001a7d6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumstoreassembly.cpp`
- `0x18001a854`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumstoreassembly.cpp`
- `0x18001a89f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumstoreassembly.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CopyOut(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  HANDLE ProcessHeap_0; // rax
  IsolationImplementation::Com::CEnumSTORE_ASSEMBLY *v9; // rax
  IsolationImplementation::Com::CEnumSTORE_ASSEMBLY *v10; // rsi
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // edx
  unsigned int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rcx
  void (*v17)(void); // rax
  HANDLE v18; // rax
  int v19; // eax
  int v20; // r9d
  __int64 v21; // rcx
  int v22; // edx
  unsigned int v24; // [rsp+20h] [rbp-38h]

  ProcessHeap_0 = GetProcessHeap_0();
  v9 = (IsolationImplementation::Com::CEnumSTORE_ASSEMBLY *)HeapAlloc_0(ProcessHeap_0, 0, 0x30u);
  v10 = v9;
  if ( v9 )
  {
    *((_DWORD *)v9 + 2) = 0;
    *((_QWORD *)v9 + 2) = 0;
    *((_QWORD *)v9 + 3) = 0;
    *(_QWORD *)v9 = &IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CEnumSTORE_ASSEMBLY>::`vftable';
    *((_QWORD *)v9 + 4) = 0;
    v11 = IsolationImplementation::Com::CEnumSTORE_ASSEMBLY::Initialize((__int64)v9, a1, a2);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v19 = (**(__int64 (__fastcall ***)(IsolationImplementation::Com::CEnumSTORE_ASSEMBLY *, __int64, __int64))v10)(
              v10,
              a3,
              a4);
      v15 = v19;
      if ( v19 >= 0 )
        return 0;
      Windows::ErrorHandling::COM::ReportErrorPropagation(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumstoreassembly.cpp",
        (const char *)0x11,
        v19,
        v20);
      *(_QWORD *)v10 = &IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CEnumSTORE_ASSEMBLY>::`vftable';
      v21 = *((_QWORD *)v10 + 4);
      if ( !v21 )
        goto LABEL_8;
      *((_QWORD *)v10 + 4) = 0;
      v17 = *(void (**)(void))(*(_QWORD *)v21 + 16LL);
    }
    else
    {
      if ( v11 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumstoreassembly.cpp",
        (const char *)0x10,
        v12,
        v24);
      v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v12, v13);
      *(_QWORD *)v10 = &IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CEnumSTORE_ASSEMBLY>::`vftable';
      v15 = v14;
      v16 = *((_QWORD *)v10 + 4);
      if ( !v16 )
        goto LABEL_8;
      *((_QWORD *)v10 + 4) = 0;
      v17 = *(void (**)(void))(*(_QWORD *)v16 + 16LL);
    }
    v17();
LABEL_8:
    IsolationImplementation::Com::CEnumSTORE_ASSEMBLY::~CEnumSTORE_ASSEMBLY(v10);
    v18 = GetProcessHeap_0();
    HeapFree_0(v18, 0, v10);
    return v15;
  }
  if ( g_NTSTATUS_to_break_on_propagate == -1073741801 )
    DebugBreak();
  Windows::ErrorHandling::COM::ReportError(
    (Windows::ErrorHandling::COM *)"Status propagated",
    "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumstoreassembly.cpp",
    (const char *)0xF,
    -1073741801,
    v24);
  return (unsigned int)Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                         (Windows::ErrorHandling::COM *)0xC0000017LL,
                         v22);
}

```

## disassembly

```asm
0x18001a750  push    rbx
0x18001a752  push    rbp
0x18001a753  push    rsi
0x18001a754  push    rdi
0x18001a755  push    r12
0x18001a757  push    r14
0x18001a759  sub     rsp, 28h
0x18001a75d  mov     rbp, r9
0x18001a760  mov     r14, r8
0x18001a763  mov     rbx, rdx
0x18001a766  mov     rdi, rcx
0x18001a769  call    GetProcessHeap_0
0x18001a76e  xor     edx, edx; dwFlags
0x18001a770  mov     rcx, rax; hHeap
0x18001a773  lea     r8d, [rdx+30h]; dwBytes
0x18001a777  call    HeapAlloc_0
0x18001a77c  mov     rsi, rax
0x18001a77f  test    rax, rax
0x18001a782  jz      loc_18001A886
0x18001a788  mov     dword ptr [rax+8], 0
0x18001a78f  lea     r12, ??_7?$CComObject@VCEnumSTORE_ASSEMBLY@Com@IsolationImplementation@@@Com@IsolationImplementation@@6B@; const IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CEnumSTORE_ASSEMBLY>::`vftable'
0x18001a796  mov     qword ptr [rax+10h], 0
0x18001a79e  mov     qword ptr [rax+18h], 0
0x18001a7a6  mov     [rax], r12
0x18001a7a9  mov     qword ptr [rax+20h], 0
0x18001a7b1  mov     r8, rbx
0x18001a7b4  mov     rdx, rdi
0x18001a7b7  mov     rcx, rax
0x18001a7ba  call    ?Initialize@CEnumSTORE_ASSEMBLY@Com@IsolationImplementation@@IEAAJU_COMPONENT_STORE@Rtl@Isolation@Windows@@U_COMPONENT_STORE_COMPONENT_ENUMERATOR@567@@Z; IsolationImplementation::Com::CEnumSTORE_ASSEMBLY::Initialize(Windows::Isolation::Rtl::_COMPONENT_STORE,Windows::Isolation::Rtl::_COMPONENT_STORE_COMPONENT_ENUMERATOR)
0x18001a7bf  mov     ebx, eax
0x18001a7c1  test    eax, eax
0x18001a7c3  jns     short loc_18001A837
0x18001a7c5  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18001a7cb  jnz     short loc_18001A7D3
0x18001a7cd  call    cs:__imp_DebugBreak
0x18001a7d3  mov     r9d, ebx; int
0x18001a7d6  lea     rdx, aOnecoreComNetf_111; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18001a7dd  mov     r8d, 10h; char *
0x18001a7e3  lea     rcx, aStatusPropagat; "Status propagated"
0x18001a7ea  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18001a7ef  mov     ecx, ebx; this
0x18001a7f1  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18001a7f6  mov     [rsi], r12
0x18001a7f9  mov     ebx, eax
0x18001a7fb  mov     rcx, [rsi+20h]
0x18001a7ff  test    rcx, rcx
0x18001a802  jz      short loc_18001A818
0x18001a804  mov     qword ptr [rsi+20h], 0
0x18001a80c  mov     rdx, [rcx]
0x18001a80f  mov     rax, [rdx+10h]
0x18001a813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a818  mov     rcx, rsi; this
0x18001a81b  call    ??1CEnumSTORE_ASSEMBLY@Com@IsolationImplementation@@IEAA@XZ; IsolationImplementation::Com::CEnumSTORE_ASSEMBLY::~CEnumSTORE_ASSEMBLY(void)
0x18001a820  call    GetProcessHeap_0
0x18001a825  mov     r8, rsi; lpMem
0x18001a828  xor     edx, edx; dwFlags
0x18001a82a  mov     rcx, rax; hHeap
0x18001a82d  call    HeapFree_0
0x18001a832  jmp     loc_18001A8C1
0x18001a837  mov     rax, [rsi]
0x18001a83a  mov     r8, rbp
0x18001a83d  mov     rdx, r14
0x18001a840  mov     rcx, rsi
0x18001a843  mov     rax, [rax]
0x18001a846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a84b  mov     ebx, eax
0x18001a84d  test    eax, eax
0x18001a84f  jns     short loc_18001A882
0x18001a851  mov     r8d, eax; int
0x18001a854  lea     rcx, aOnecoreComNetf_111; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18001a85b  mov     edx, 11h; char *
0x18001a860  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18001a865  mov     [rsi], r12
0x18001a868  mov     rcx, [rsi+20h]
0x18001a86c  test    rcx, rcx
0x18001a86f  jz      short loc_18001A818
0x18001a871  mov     qword ptr [rsi+20h], 0
0x18001a879  mov     rax, [rcx]
0x18001a87c  mov     rax, [rax+10h]
0x18001a880  jmp     short loc_18001A813
0x18001a882  xor     ebx, ebx
0x18001a884  jmp     short loc_18001A8C1
0x18001a886  mov     ebx, 0C0000017h
0x18001a88b  cmp     cs:g_NTSTATUS_to_break_on_propagate, ebx
0x18001a891  jnz     short loc_18001A899
0x18001a893  call    cs:__imp_DebugBreak
0x18001a899  mov     r9d, 0C0000017h; int
0x18001a89f  lea     rdx, aOnecoreComNetf_111; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18001a8a6  mov     r8d, 0Fh; char *
0x18001a8ac  lea     rcx, aStatusPropagat; "Status propagated"
0x18001a8b3  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18001a8b8  mov     ecx, ebx; this
0x18001a8ba  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18001a8bf  mov     ebx, eax
0x18001a8c1  mov     eax, ebx
0x18001a8c3  add     rsp, 28h
0x18001a8c7  pop     r14
0x18001a8c9  pop     r12
0x18001a8cb  pop     rdi
0x18001a8cc  pop     rsi
0x18001a8cd  pop     rbp
0x18001a8ce  pop     rbx
0x18001a8cf  retn
```
