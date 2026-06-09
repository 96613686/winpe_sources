# IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR,_GUID const &,IUnknown * *)

- ea: `0x18001a8d8`
- end: `0x18001aa46`
- name: `?CopyOut@Com@IsolationImplementation@@YAJU_COMPONENT_STORE_FILE_ENUMERATOR@Rtl@Isolation@Windows@@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `366`
- prototype: `int __high(struct Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR, const struct _GUID *, struct IUnknown **)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800a50c0`
- `0x1800ac460`
- `0x1800ad878`

## callees

- `0x1800069a9`
- `0x1800069b5`
- `0x1800069c1`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18001a8d8`
- `0x1800a5018`
- `0x1800a52a4`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001a945`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001aa0b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001a945`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001aa0b`

## string_xrefs

- `0x18001a94e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumstoreassemblyfile.cpp`
- `0x18001a9cc`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumstoreassemblyfile.cpp`
- `0x18001aa17`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumstoreassemblyfile.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CopyOut(__int64 a1, __int64 a2, __int64 a3)
{
  HANDLE ProcessHeap_0; // rax
  IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE *v7; // rax
  IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE *v8; // rdi
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // edx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rcx
  void (*v15)(void); // rax
  HANDLE v16; // rax
  int v17; // eax
  int v18; // r9d
  __int64 v19; // rcx
  int v20; // edx
  unsigned int v22; // [rsp+20h] [rbp-28h]

  ProcessHeap_0 = GetProcessHeap_0();
  v7 = (IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE *)HeapAlloc_0(ProcessHeap_0, 0, 0x28u);
  v8 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 2) = 0;
    *(_QWORD *)v7 = &IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE>::`vftable';
    *((_QWORD *)v7 + 3) = 0;
    v9 = IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE::Initialize(v7, a1);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v17 = (**(__int64 (__fastcall ***)(IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE *, __int64, __int64))v8)(
              v8,
              a2,
              a3);
      v13 = v17;
      if ( v17 >= 0 )
        return 0;
      Windows::ErrorHandling::COM::ReportErrorPropagation(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumstoreassemblyfile.cpp",
        (const char *)0x10,
        v17,
        v18);
      *(_QWORD *)v8 = &IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE>::`vftable';
      v19 = *((_QWORD *)v8 + 3);
      if ( !v19 )
        goto LABEL_8;
      *((_QWORD *)v8 + 3) = 0;
      v15 = *(void (**)(void))(*(_QWORD *)v19 + 16LL);
    }
    else
    {
      if ( v9 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumstoreassemblyfile.cpp",
        (const char *)0xF,
        v10,
        v22);
      v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v10, v11);
      *(_QWORD *)v8 = &IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE>::`vftable';
      v13 = v12;
      v14 = *((_QWORD *)v8 + 3);
      if ( !v14 )
        goto LABEL_8;
      *((_QWORD *)v8 + 3) = 0;
      v15 = *(void (**)(void))(*(_QWORD *)v14 + 16LL);
    }
    v15();
LABEL_8:
    IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE::~CEnumSTORE_ASSEMBLY_FILE(v8);
    v16 = GetProcessHeap_0();
    HeapFree_0(v16, 0, v8);
    return v13;
  }
  if ( g_NTSTATUS_to_break_on_propagate == -1073741801 )
    DebugBreak();
  Windows::ErrorHandling::COM::ReportError(
    (Windows::ErrorHandling::COM *)"Status propagated",
    "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumstoreassemblyfile.cpp",
    (const char *)0xE,
    -1073741801,
    v22);
  return (unsigned int)Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                         (Windows::ErrorHandling::COM *)0xC0000017LL,
                         v20);
}

```

## disassembly

```asm
0x18001a8d8  push    rbx
0x18001a8da  push    rbp
0x18001a8db  push    rsi
0x18001a8dc  push    rdi
0x18001a8dd  push    r15; unsigned int
0x18001a8df  sub     rsp, 20h
0x18001a8e3  mov     rsi, r8
0x18001a8e6  mov     rbp, rdx
0x18001a8e9  mov     rbx, rcx
0x18001a8ec  call    GetProcessHeap_0
0x18001a8f1  xor     edx, edx; dwFlags
0x18001a8f3  mov     rcx, rax; hHeap
0x18001a8f6  lea     r8d, [rdx+28h]; dwBytes
0x18001a8fa  call    HeapAlloc_0
0x18001a8ff  mov     rdi, rax
0x18001a902  test    rax, rax
0x18001a905  jz      loc_18001A9FE
0x18001a90b  mov     dword ptr [rax+8], 0
0x18001a912  lea     r15, ??_7?$CComObject@VCEnumSTORE_ASSEMBLY_FILE@Com@IsolationImplementation@@@Com@IsolationImplementation@@6B@; const IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE>::`vftable'
0x18001a919  mov     qword ptr [rax+10h], 0
0x18001a921  mov     [rax], r15
0x18001a924  mov     qword ptr [rax+18h], 0
0x18001a92c  mov     rdx, rbx
0x18001a92f  mov     rcx, rax
0x18001a932  call    ?Initialize@CEnumSTORE_ASSEMBLY_FILE@Com@IsolationImplementation@@IEAAJU_COMPONENT_STORE_FILE_ENUMERATOR@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE::Initialize(Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR)
0x18001a937  mov     ebx, eax
0x18001a939  test    eax, eax
0x18001a93b  jns     short loc_18001A9AF
0x18001a93d  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18001a943  jnz     short loc_18001A94B
0x18001a945  call    cs:__imp_DebugBreak
0x18001a94b  mov     r9d, ebx; int
0x18001a94e  lea     rdx, aOnecoreComNetf_66; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18001a955  mov     r8d, 0Fh; char *
0x18001a95b  lea     rcx, aStatusPropagat; "Status propagated"
0x18001a962  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18001a967  mov     ecx, ebx; this
0x18001a969  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18001a96e  mov     [rdi], r15
0x18001a971  mov     ebx, eax
0x18001a973  mov     rcx, [rdi+18h]
0x18001a977  test    rcx, rcx
0x18001a97a  jz      short loc_18001A990
0x18001a97c  mov     qword ptr [rdi+18h], 0
0x18001a984  mov     rdx, [rcx]
0x18001a987  mov     rax, [rdx+10h]
0x18001a98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a990  mov     rcx, rdi; this
0x18001a993  call    ??1CEnumSTORE_ASSEMBLY_FILE@Com@IsolationImplementation@@IEAA@XZ; IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE::~CEnumSTORE_ASSEMBLY_FILE(void)
0x18001a998  call    GetProcessHeap_0
0x18001a99d  mov     r8, rdi; lpMem
0x18001a9a0  xor     edx, edx; dwFlags
0x18001a9a2  mov     rcx, rax; hHeap
0x18001a9a5  call    HeapFree_0
0x18001a9aa  jmp     loc_18001AA39
0x18001a9af  mov     rax, [rdi]
0x18001a9b2  mov     r8, rsi
0x18001a9b5  mov     rdx, rbp
0x18001a9b8  mov     rcx, rdi
0x18001a9bb  mov     rax, [rax]
0x18001a9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9c3  mov     ebx, eax
0x18001a9c5  test    eax, eax
0x18001a9c7  jns     short loc_18001A9FA
0x18001a9c9  mov     r8d, eax; int
0x18001a9cc  lea     rcx, aOnecoreComNetf_66; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18001a9d3  mov     edx, 10h; char *
0x18001a9d8  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18001a9dd  mov     [rdi], r15
0x18001a9e0  mov     rcx, [rdi+18h]
0x18001a9e4  test    rcx, rcx
0x18001a9e7  jz      short loc_18001A990
0x18001a9e9  mov     qword ptr [rdi+18h], 0
0x18001a9f1  mov     rax, [rcx]
0x18001a9f4  mov     rax, [rax+10h]
0x18001a9f8  jmp     short loc_18001A98B
0x18001a9fa  xor     ebx, ebx
0x18001a9fc  jmp     short loc_18001AA39
0x18001a9fe  mov     ebx, 0C0000017h
0x18001aa03  cmp     cs:g_NTSTATUS_to_break_on_propagate, ebx
0x18001aa09  jnz     short loc_18001AA11
0x18001aa0b  call    cs:__imp_DebugBreak
0x18001aa11  mov     r9d, 0C0000017h; int
0x18001aa17  lea     rdx, aOnecoreComNetf_66; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18001aa1e  mov     r8d, 0Eh; char *
0x18001aa24  lea     rcx, aStatusPropagat; "Status propagated"
0x18001aa2b  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18001aa30  mov     ecx, ebx; this
0x18001aa32  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18001aa37  mov     ebx, eax
0x18001aa39  mov     eax, ebx
0x18001aa3b  add     rsp, 20h
0x18001aa3f  pop     r15
0x18001aa41  pop     rdi
0x18001aa42  pop     rsi
0x18001aa43  pop     rbp
0x18001aa44  pop     rbx
0x18001aa45  retn
```
