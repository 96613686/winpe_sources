# IsolationImplementation::Com::CComponentStore::IStore_GetAssemblyInformation(ulong,IDefinitionIdentity *,_GUID const &,IUnknown * *)

- ea: `0x1800adc58`
- end: `0x1800adf4d`
- name: `?IStore_GetAssemblyInformation@CComponentStore@Com@IsolationImplementation@@IEAAJKPEAUIDefinitionIdentity@@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `757`
- prototype: `int(IsolationImplementation::Com::CComponentStore *__hidden this, unsigned int, struct IDefinitionIdentity *, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800aae90`

## callees

- `0x180006991`
- `0x180012acc`
- `0x180012b38`
- `0x180016c54`
- `0x180017514`
- `0x180017530`
- `0x1800187f0`
- `0x180018940`
- `0x180018a34`
- `0x180018acc`
- `0x1800199b4`
- `0x18002f364`
- `0x180030674`
- `0x180039c1c`
- `0x180043644`
- `0x18004f2dc`
- `0x1800adc58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800adcf4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800add5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800adf0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800adcf4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800add5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800adf0c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800adcbb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ade41`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800adcbb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ade41`

## string_xrefs

- `0x1800adc7b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800adde5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ade4a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800adebd`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800adeda`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CComponentStore::IStore_GetAssemblyInformation(
        IsolationImplementation::Com::CComponentStore *this,
        int a2,
        struct IDefinitionIdentity *a3,
        const struct _GUID *a4,
        struct IUnknown **a5)
{
  int v9; // eax
  struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *v10; // r8
  unsigned int v11; // ebx
  int v12; // edx
  unsigned int v13; // edi
  HANDLE v14; // rbx
  HANDLE v15; // rbx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // r9d
  __int64 v19; // rcx
  __int64 v20; // rbx
  int ComponentStoreComponentManifest; // eax
  int v22; // r9d
  unsigned int v23; // edi
  int v24; // edx
  int v25; // eax
  int v26; // r9d
  HANDLE v27; // rbx
  __int64 v29; // [rsp+20h] [rbp-71h] BYREF
  HANDLE hMutex; // [rsp+30h] [rbp-61h] BYREF
  __int16 v31; // [rsp+38h] [rbp-59h]
  _BYTE v32[64]; // [rsp+40h] [rbp-51h] BYREF
  __int64 v33; // [rsp+80h] [rbp-11h] BYREF
  const char *v34; // [rsp+88h] [rbp-9h] BYREF
  int v35; // [rsp+90h] [rbp-1h]
  unsigned int v36; // [rsp+98h] [rbp+7h]

  v36 = -2147023537;
  v34 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp";
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v32);
  hMutex = 0;
  v31 = 0;
  v9 = StoreLock::Lock((StoreLock *)&hMutex);
  v11 = v9;
  if ( v9 < 0 )
  {
    if ( v9 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x275,
      v11,
      v29);
    v13 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v11, v12);
    goto LABEL_5;
  }
  if ( a5 )
    *a5 = 0;
  if ( a2 )
  {
    v35 = 636;
LABEL_45:
    v27 = hMutex;
    if ( hMutex )
    {
      if ( (_BYTE)v31 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v31) = 0;
      }
      CloseHandle_0(v27);
      hMutex = 0;
    }
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v32);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v34);
    return v36;
  }
  if ( !a3 )
  {
    v35 = 637;
LABEL_16:
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v34);
    v15 = hMutex;
    if ( hMutex )
    {
      if ( (_BYTE)v31 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v31) = 0;
      }
      CloseHandle_0(v15);
      hMutex = 0;
    }
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v32);
    return v36;
  }
  if ( !a5 )
  {
    v35 = 638;
    goto LABEL_16;
  }
  if ( (*(_QWORD *)&a4->Data1 != *(_QWORD *)&GUID_a504e5b0_8ccf_4cb4_9902_c9d1b9abd033.Data1
     || *(_QWORD *)a4->Data4 != *(_QWORD *)GUID_a504e5b0_8ccf_4cb4_9902_c9d1b9abd033.Data4)
    && (*(_QWORD *)&a4->Data1 != *(_QWORD *)&GUID_587bf538_4d90_4a3c_9ef1_58a200a8a9e7.Data1
     || *(_QWORD *)a4->Data4 != *(_QWORD *)GUID_587bf538_4d90_4a3c_9ef1_58a200a8a9e7.Data4) )
  {
    v35 = 639;
    goto LABEL_45;
  }
  v33 = 0;
  v29 = 0;
  v16 = IsolationImplementation::Com::ConvertIn(a3, (struct IDefinitionIdentity *)&v33, v10);
  v13 = v16;
  if ( v16 >= 0 )
  {
    v20 = v33;
    ComponentStoreComponentManifest = RtlGetComponentStoreComponentManifest(v17, *((_QWORD *)this + 2), v33, &v29);
    v23 = ComponentStoreComponentManifest;
    if ( ComponentStoreComponentManifest >= 0 )
    {
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v29) )
      {
        v25 = IsolationImplementation::Com::CopyOut(v29, a4, a5);
        v13 = v25;
        if ( v25 >= 0 )
          v13 = 0;
        else
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
            (const char *)0x28C,
            v25,
            v26);
      }
      else
      {
        v13 = -2147010893;
        Windows::ErrorHandling::COM::ReportErrorOrigination(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
          (const char *)0x289,
          -2147010893,
          v22);
      }
    }
    else
    {
      if ( ComponentStoreComponentManifest == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x286,
        v23,
        v29);
      v13 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v23, v24);
    }
    if ( v29 )
    {
      CdfCloseHandle();
      v29 = 0;
    }
    if ( !v20 )
      goto LABEL_5;
    v19 = v20;
    goto LABEL_29;
  }
  Windows::ErrorHandling::COM::ReportErrorPropagation(
    (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
    (const char *)0x284,
    v16,
    v18);
  v19 = v33;
  if ( v33 )
LABEL_29:
    RtlCloseDefinitionIdentityHandle(v19);
LABEL_5:
  v14 = hMutex;
  if ( hMutex )
  {
    if ( (_BYTE)v31 )
    {
      ReleaseMutex(hMutex);
      LOBYTE(v31) = 0;
    }
    CloseHandle_0(v14);
    hMutex = 0;
  }
  BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v32);
  return v13;
}

```

## disassembly

```asm
0x1800adc58  push    rbp
0x1800adc5a  push    rbx
0x1800adc5b  push    rsi
0x1800adc5c  push    rdi
0x1800adc5d  push    r12
0x1800adc5f  push    r13
0x1800adc61  push    r14
0x1800adc63  push    r15
0x1800adc65  lea     rbp, [rsp-17h]
0x1800adc6a  sub     rsp, 0A8h
0x1800adc71  mov     r13, rcx
0x1800adc74  mov     [rbp+4Fh+var_48], 8007054Fh
0x1800adc7b  lea     rsi, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800adc82  mov     r14, r9
0x1800adc85  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800adc89  mov     [rbp+4Fh+var_58], rsi
0x1800adc8d  mov     rdi, r8
0x1800adc90  mov     r15d, edx
0x1800adc93  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800adc98  xor     r12d, r12d
0x1800adc9b  lea     rcx, [rbp+4Fh+hMutex]; this
0x1800adc9f  mov     [rbp+4Fh+hMutex], r12
0x1800adca3  mov     [rbp+4Fh+var_A8], r12w
0x1800adca8  call    ?Lock@StoreLock@@QEAAJXZ; StoreLock::Lock(void)
0x1800adcad  mov     ebx, eax
0x1800adcaf  test    eax, eax
0x1800adcb1  jns     short loc_1800ADD18
0x1800adcb3  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800adcb9  jnz     short loc_1800ADCC1
0x1800adcbb  call    cs:__imp_DebugBreak
0x1800adcc1  mov     r9d, ebx; int
0x1800adcc4  lea     rcx, aStatusPropagat; "Status propagated"
0x1800adccb  mov     r8d, 275h; char *
0x1800adcd1  mov     rdx, rsi; char *
0x1800adcd4  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800adcd9  mov     ecx, ebx; this
0x1800adcdb  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800adce0  mov     edi, eax
0x1800adce2  mov     rbx, [rbp+4Fh+hMutex]
0x1800adce6  test    rbx, rbx
0x1800adce9  jz      short loc_1800ADD0A
0x1800adceb  cmp     byte ptr [rbp+4Fh+var_A8], r12b
0x1800adcef  jz      short loc_1800ADCFE
0x1800adcf1  mov     rcx, rbx; hMutex
0x1800adcf4  call    cs:__imp_ReleaseMutex
0x1800adcfa  mov     byte ptr [rbp+4Fh+var_A8], r12b
0x1800adcfe  mov     rcx, rbx; hObject
0x1800add01  call    CloseHandle_0
0x1800add06  mov     [rbp+4Fh+hMutex], r12
0x1800add0a  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800add0e  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800add13  jmp     loc_1800ADF37
0x1800add18  mov     rsi, [rbp+4Fh+arg_20]
0x1800add1c  test    rsi, rsi
0x1800add1f  jz      short loc_1800ADD24
0x1800add21  mov     [rsi], r12
0x1800add24  test    r15d, r15d
0x1800add27  jz      short loc_1800ADD35
0x1800add29  mov     [rbp+4Fh+var_50], 27Ch
0x1800add30  jmp     loc_1800ADEFA
0x1800add35  test    rdi, rdi
0x1800add38  jnz     short loc_1800ADD80
0x1800add3a  mov     [rbp+4Fh+var_50], 27Dh
0x1800add41  lea     rcx, [rbp+4Fh+var_58]
0x1800add45  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800add4a  mov     rbx, [rbp+4Fh+hMutex]
0x1800add4e  test    rbx, rbx
0x1800add51  jz      short loc_1800ADD72
0x1800add53  cmp     byte ptr [rbp+4Fh+var_A8], r12b
0x1800add57  jz      short loc_1800ADD66
0x1800add59  mov     rcx, rbx; hMutex
0x1800add5c  call    cs:__imp_ReleaseMutex
0x1800add62  mov     byte ptr [rbp+4Fh+var_A8], r12b
0x1800add66  mov     rcx, rbx; hObject
0x1800add69  call    CloseHandle_0
0x1800add6e  mov     [rbp+4Fh+hMutex], r12
0x1800add72  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800add76  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800add7b  jmp     loc_1800ADF34
0x1800add80  test    rsi, rsi
0x1800add83  jnz     short loc_1800ADD8E
0x1800add85  mov     [rbp+4Fh+var_50], 27Eh
0x1800add8c  jmp     short loc_1800ADD41
0x1800add8e  mov     rax, [r14]
0x1800add91  cmp     rax, qword ptr cs:_GUID_a504e5b0_8ccf_4cb4_9902_c9d1b9abd033.Data1
0x1800add98  jnz     short loc_1800ADDA7
0x1800add9a  mov     rax, [r14+8]
0x1800add9e  cmp     rax, qword ptr cs:_GUID_a504e5b0_8ccf_4cb4_9902_c9d1b9abd033.Data4
0x1800adda5  jz      short loc_1800ADDC8
0x1800adda7  mov     rax, [r14]
0x1800addaa  cmp     rax, qword ptr cs:_GUID_587bf538_4d90_4a3c_9ef1_58a200a8a9e7.Data1
0x1800addb1  jnz     loc_1800ADEF3
0x1800addb7  mov     rax, [r14+8]
0x1800addbb  cmp     rax, qword ptr cs:_GUID_587bf538_4d90_4a3c_9ef1_58a200a8a9e7.Data4
0x1800addc2  jnz     loc_1800ADEF3
0x1800addc8  lea     rdx, [rbp+4Fh+var_60]; struct IDefinitionIdentity *
0x1800addcc  mov     [rbp+4Fh+var_60], r12
0x1800addd0  mov     rcx, rdi; this
0x1800addd3  mov     [rbp+4Fh+var_C0], r12
0x1800addd7  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionIdentity@@PEAU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionIdentity *,Windows::Isolation::Rtl::_DEFINITION_IDENTITY *)
0x1800adddc  mov     edi, eax
0x1800addde  test    eax, eax
0x1800adde0  jns     short loc_1800ADE1F
0x1800adde2  mov     r8d, eax; int
0x1800adde5  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800addec  mov     edx, 284h; char *
0x1800addf1  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800addf6  mov     rcx, [rbp+4Fh+var_C0]
0x1800addfa  test    rcx, rcx
0x1800addfd  jz      short loc_1800ADE08
0x1800addff  call    CdfCloseHandle
0x1800ade04  mov     [rbp+4Fh+var_C0], r12
0x1800ade08  mov     rcx, [rbp+4Fh+var_60]
0x1800ade0c  test    rcx, rcx
0x1800ade0f  jz      loc_1800ADCE2
0x1800ade15  call    RtlCloseDefinitionIdentityHandle
0x1800ade1a  jmp     loc_1800ADCE2
0x1800ade1f  mov     rbx, [rbp+4Fh+var_60]
0x1800ade23  lea     r9, [rbp+4Fh+var_C0]
0x1800ade27  mov     rdx, [r13+10h]
0x1800ade2b  mov     r8, rbx
0x1800ade2e  call    RtlGetComponentStoreComponentManifest
0x1800ade33  mov     edi, eax
0x1800ade35  test    eax, eax
0x1800ade37  jns     short loc_1800ADE8C
0x1800ade39  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ade3f  jnz     short loc_1800ADE47
0x1800ade41  call    cs:__imp_DebugBreak
0x1800ade47  mov     r9d, edi; int
0x1800ade4a  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ade51  mov     r8d, 286h; char *
0x1800ade57  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ade5e  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ade63  mov     ecx, edi; this
0x1800ade65  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ade6a  mov     edi, eax
0x1800ade6c  mov     rcx, [rbp+4Fh+var_C0]
0x1800ade70  test    rcx, rcx
0x1800ade73  jz      short loc_1800ADE7E
0x1800ade75  call    CdfCloseHandle
0x1800ade7a  mov     [rbp+4Fh+var_C0], r12
0x1800ade7e  test    rbx, rbx
0x1800ade81  jz      loc_1800ADCE2
0x1800ade87  mov     rcx, rbx
0x1800ade8a  jmp     short loc_1800ADE15
0x1800ade8c  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x1800ade93  test    rdx, rdx
0x1800ade96  jz      short loc_1800ADED5
0x1800ade98  mov     rcx, [rbp+4Fh+var_C0]
0x1800ade9c  call    RtlIsTypeSafeHandleValid
0x1800adea1  test    al, al
0x1800adea3  jz      short loc_1800ADED5
0x1800adea5  mov     rcx, [rbp+4Fh+var_C0]
0x1800adea9  mov     r8, rsi
0x1800adeac  mov     rdx, r14
0x1800adeaf  call    ?CopyOut@Com@IsolationImplementation@@YAJU_CDF@Rtl@Cdf@Windows@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; IsolationImplementation::Com::CopyOut(Windows::Cdf::Rtl::_CDF,_GUID const &,IUnknown * *)
0x1800adeb4  mov     edi, eax
0x1800adeb6  test    eax, eax
0x1800adeb8  jns     short loc_1800ADED0
0x1800adeba  mov     r8d, eax; int
0x1800adebd  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800adec4  mov     edx, 28Ch; char *
0x1800adec9  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800adece  jmp     short loc_1800ADE6C
0x1800aded0  mov     edi, r12d
0x1800aded3  jmp     short loc_1800ADE6C
0x1800aded5  mov     edi, 800736B3h
0x1800adeda  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800adee1  mov     r8d, edi; int
0x1800adee4  mov     edx, 289h; char *
0x1800adee9  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x1800adeee  jmp     loc_1800ADE6C
0x1800adef3  mov     [rbp+4Fh+var_50], 27Fh
0x1800adefa  mov     rbx, [rbp+4Fh+hMutex]
0x1800adefe  test    rbx, rbx
0x1800adf01  jz      short loc_1800ADF22
0x1800adf03  cmp     byte ptr [rbp+4Fh+var_A8], r12b
0x1800adf07  jz      short loc_1800ADF16
0x1800adf09  mov     rcx, rbx; hMutex
0x1800adf0c  call    cs:__imp_ReleaseMutex
0x1800adf12  mov     byte ptr [rbp+4Fh+var_A8], r12b
0x1800adf16  mov     rcx, rbx; hObject
0x1800adf19  call    CloseHandle_0
0x1800adf1e  mov     [rbp+4Fh+hMutex], r12
0x1800adf22  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800adf26  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800adf2b  lea     rcx, [rbp+4Fh+var_58]
0x1800adf2f  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800adf34  mov     edi, [rbp+4Fh+var_48]
0x1800adf37  mov     eax, edi
0x1800adf39  add     rsp, 0A8h
0x1800adf40  pop     r15
0x1800adf42  pop     r14
0x1800adf44  pop     r13
0x1800adf46  pop     r12
0x1800adf48  pop     rdi
0x1800adf49  pop     rsi
0x1800adf4a  pop     rbx
0x1800adf4b  pop     rbp
0x1800adf4c  retn
```
