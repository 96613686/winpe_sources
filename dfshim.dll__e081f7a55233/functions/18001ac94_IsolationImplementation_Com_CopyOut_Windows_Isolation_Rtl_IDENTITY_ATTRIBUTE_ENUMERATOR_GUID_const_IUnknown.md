# IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,_GUID const &,IUnknown * *)

- ea: `0x18001ac94`
- end: `0x18001ae0e`
- name: `?CopyOut@Com@IsolationImplementation@@YAJU_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `378`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800a5b70`
- `0x1800a69e0`
- `0x1800a8be0`

## callees

- `0x1800069a9`
- `0x1800069b5`
- `0x1800069c1`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18001ac94`
- `0x1800a8b4c`
- `0x180107504`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001ad0a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001add4`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001ad0a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001add4`

## string_xrefs

- `0x18001ad13`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumidentityattribute.cpp`
- `0x18001ad95`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumidentityattribute.cpp`
- `0x18001ade0`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumidentityattribute.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CopyOut(__int64 a1, __int64 a2, __int64 a3)
{
  HANDLE ProcessHeap_0; // rax
  IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE *v6; // rax
  IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE *v7; // rdi
  int v8; // eax
  int v9; // ebx
  int v10; // edx
  unsigned int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  void (*v14)(void); // rax
  HANDLE v15; // rax
  int v16; // eax
  int v17; // r9d
  __int64 v18; // rcx
  int v19; // edx
  unsigned int v21; // [rsp+20h] [rbp-48h]

  ProcessHeap_0 = GetProcessHeap_0();
  v6 = (IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE *)HeapAlloc_0(ProcessHeap_0, 0, 0x28u);
  v7 = v6;
  if ( v6 )
  {
    *((_DWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 2) = 0;
    *(_QWORD *)v6 = &IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE>::`vftable';
    *((_QWORD *)v6 + 3) = 0;
    v8 = RtlCloneIdentityAttributeEnumerator(a1, (char *)v6 + 16);
    v9 = 0;
    if ( v8 < 0 )
      v9 = v8;
    if ( v9 >= 0 )
    {
      v16 = (**(__int64 (__fastcall ***)(IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE *, GUID *, __int64))v7)(
              v7,
              &GUID_9cdaae75_246e_4b00_a26d_b9aec137a3eb,
              a3);
      v12 = v16;
      if ( v16 >= 0 )
        return 0;
      Windows::ErrorHandling::COM::ReportErrorPropagation(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumidentityattribute.cpp",
        (const char *)0x10,
        v16,
        v17);
      *(_QWORD *)v7 = &IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE>::`vftable';
      v18 = *((_QWORD *)v7 + 3);
      if ( !v18 )
        goto LABEL_10;
      *((_QWORD *)v7 + 3) = 0;
      v14 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
    }
    else
    {
      if ( v9 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumidentityattribute.cpp",
        (const char *)0xF,
        v9,
        v21);
      v11 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v9, v10);
      *(_QWORD *)v7 = &IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE>::`vftable';
      v12 = v11;
      v13 = *((_QWORD *)v7 + 3);
      if ( !v13 )
        goto LABEL_10;
      *((_QWORD *)v7 + 3) = 0;
      v14 = *(void (**)(void))(*(_QWORD *)v13 + 16LL);
    }
    v14();
LABEL_10:
    IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE::~CEnumIDENTITY_ATTRIBUTE(v7);
    v15 = GetProcessHeap_0();
    HeapFree_0(v15, 0, v7);
    return v12;
  }
  if ( g_NTSTATUS_to_break_on_propagate == -1073741801 )
    DebugBreak();
  Windows::ErrorHandling::COM::ReportError(
    (Windows::ErrorHandling::COM *)"Status propagated",
    "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumidentityattribute.cpp",
    (const char *)0xE,
    -1073741801,
    v21);
  return (unsigned int)Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                         (Windows::ErrorHandling::COM *)0xC0000017LL,
                         v19);
}

```

## disassembly

```asm
0x18001ac94  push    rbx
0x18001ac96  push    rsi
0x18001ac97  push    rdi
0x18001ac98  push    r14
0x18001ac9a  sub     rsp, 48h
0x18001ac9e  mov     rsi, r8
0x18001aca1  mov     rbx, rcx
0x18001aca4  call    GetProcessHeap_0
0x18001aca9  xor     edx, edx; dwFlags
0x18001acab  mov     rcx, rax; hHeap
0x18001acae  lea     r8d, [rdx+28h]; dwBytes
0x18001acb2  call    HeapAlloc_0
0x18001acb7  mov     rdi, rax
0x18001acba  test    rax, rax
0x18001acbd  jz      loc_18001ADC7
0x18001acc3  mov     dword ptr [rax+8], 0
0x18001acca  lea     rdx, [rax+10h]
0x18001acce  mov     qword ptr [rdx], 0
0x18001acd5  lea     r14, ??_7?$CComObject@VCEnumIDENTITY_ATTRIBUTE@Com@IsolationImplementation@@@Com@IsolationImplementation@@6B@; const IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE>::`vftable'
0x18001acdc  mov     [rax], r14
0x18001acdf  mov     qword ptr [rax+18h], 0
0x18001ace7  mov     rcx, rbx
0x18001acea  mov     [rsp+68h+var_38], 0C00000E5h
0x18001acf2  call    RtlCloneIdentityAttributeEnumerator
0x18001acf7  xor     ebx, ebx
0x18001acf9  test    eax, eax
0x18001acfb  cmovs   ebx, eax
0x18001acfe  test    ebx, ebx
0x18001ad00  jns     short loc_18001AD74
0x18001ad02  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18001ad08  jnz     short loc_18001AD10
0x18001ad0a  call    cs:__imp_DebugBreak
0x18001ad10  mov     r9d, ebx; int
0x18001ad13  lea     rdx, aOnecoreComNetf_101; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18001ad1a  mov     r8d, 0Fh; char *
0x18001ad20  lea     rcx, aStatusPropagat; "Status propagated"
0x18001ad27  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18001ad2c  mov     ecx, ebx; this
0x18001ad2e  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18001ad33  mov     [rdi], r14
0x18001ad36  mov     ebx, eax
0x18001ad38  mov     rcx, [rdi+18h]
0x18001ad3c  test    rcx, rcx
0x18001ad3f  jz      short loc_18001AD55
0x18001ad41  mov     qword ptr [rdi+18h], 0
0x18001ad49  mov     rdx, [rcx]
0x18001ad4c  mov     rax, [rdx+10h]
0x18001ad50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad55  mov     rcx, rdi; this
0x18001ad58  call    ??1CEnumIDENTITY_ATTRIBUTE@Com@IsolationImplementation@@IEAA@XZ; IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE::~CEnumIDENTITY_ATTRIBUTE(void)
0x18001ad5d  call    GetProcessHeap_0
0x18001ad62  mov     r8, rdi; lpMem
0x18001ad65  xor     edx, edx; dwFlags
0x18001ad67  mov     rcx, rax; hHeap
0x18001ad6a  call    HeapFree_0
0x18001ad6f  jmp     loc_18001AE02
0x18001ad74  mov     rax, [rdi]
0x18001ad77  lea     rdx, _GUID_9cdaae75_246e_4b00_a26d_b9aec137a3eb
0x18001ad7e  mov     r8, rsi
0x18001ad81  mov     rcx, rdi
0x18001ad84  mov     rax, [rax]
0x18001ad87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad8c  mov     ebx, eax
0x18001ad8e  test    eax, eax
0x18001ad90  jns     short loc_18001ADC3
0x18001ad92  mov     r8d, eax; int
0x18001ad95  lea     rcx, aOnecoreComNetf_101; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18001ad9c  mov     edx, 10h; char *
0x18001ada1  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18001ada6  mov     [rdi], r14
0x18001ada9  mov     rcx, [rdi+18h]
0x18001adad  test    rcx, rcx
0x18001adb0  jz      short loc_18001AD55
0x18001adb2  mov     qword ptr [rdi+18h], 0
0x18001adba  mov     rax, [rcx]
0x18001adbd  mov     rax, [rax+10h]
0x18001adc1  jmp     short loc_18001AD50
0x18001adc3  xor     ebx, ebx
0x18001adc5  jmp     short loc_18001AE02
0x18001adc7  mov     ebx, 0C0000017h
0x18001adcc  cmp     cs:g_NTSTATUS_to_break_on_propagate, ebx
0x18001add2  jnz     short loc_18001ADDA
0x18001add4  call    cs:__imp_DebugBreak
0x18001adda  mov     r9d, 0C0000017h; int
0x18001ade0  lea     rdx, aOnecoreComNetf_101; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18001ade7  mov     r8d, 0Eh; char *
0x18001aded  lea     rcx, aStatusPropagat; "Status propagated"
0x18001adf4  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18001adf9  mov     ecx, ebx; this
0x18001adfb  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18001ae00  mov     ebx, eax
0x18001ae02  mov     eax, ebx
0x18001ae04  add     rsp, 48h
0x18001ae08  pop     r14
0x18001ae0a  pop     rdi
0x18001ae0b  pop     rsi
0x18001ae0c  pop     rbx
0x18001ae0d  retn
```
