# IsolationImplementation::Com::CComponentStore::IStore_LockAssemblyPath(ulong,IDefinitionIdentity *,void * *,ushort * *)

- ea: `0x1800aed6c`
- end: `0x1800af0d2`
- name: `?IStore_LockAssemblyPath@CComponentStore@Com@IsolationImplementation@@IEAAJKPEAUIDefinitionIdentity@@PEAPEAXPEAPEAG@Z`
- size: `870`
- prototype: `int(IsolationImplementation::Com::CComponentStore *__hidden this, unsigned int, struct IDefinitionIdentity *, void **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800b01d0`

## callees

- `0x180006991`
- `0x180012acc`
- `0x180012b38`
- `0x180014410`
- `0x180017514`
- `0x180017530`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18001b05c`
- `0x180030674`
- `0x180039c1c`
- `0x180043644`
- `0x1800a95c8`
- `0x1800aed6c`
- `0x1800f97ec`
- `0x1800fa36c`
- `0x1800fe440`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800aee31`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800aee82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af09d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800aee31`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800aee82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af09d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800aedcf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800aef3d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800aef95`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800af011`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800aedcf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800aef3d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800aef95`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800af011`

## string_xrefs

- `0x1800aed8f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800aeeda`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800aef46`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800aef9e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800aefdf`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800af01d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CComponentStore::IStore_LockAssemblyPath(
        IsolationImplementation::Com::CComponentStore *this,
        int a2,
        struct IDefinitionIdentity *a3,
        void **a4,
        unsigned __int16 **a5)
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
  __int64 v18; // r8
  int v19; // r9d
  unsigned __int16 *v20; // rcx
  unsigned __int16 *v21; // rbx
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rcx
  unsigned int v25; // edi
  int v26; // edx
  int v27; // eax
  unsigned __int16 **v28; // r8
  unsigned int v29; // edi
  int v30; // edx
  int v31; // eax
  unsigned int v32; // edx
  int v33; // r9d
  _QWORD *v34; // rax
  void *v35; // rdx
  __int64 v36; // rcx
  unsigned __int16 *v37; // rax
  HANDLE v38; // rbx
  unsigned int v40; // [rsp+20h] [rbp-81h]
  unsigned __int16 *v41; // [rsp+30h] [rbp-71h] BYREF
  unsigned int v42[2]; // [rsp+38h] [rbp-69h] BYREF
  __int64 v43; // [rsp+40h] [rbp-61h]
  void *lpMem; // [rsp+48h] [rbp-59h]
  unsigned int v45[2]; // [rsp+50h] [rbp-51h] BYREF
  __int64 v46; // [rsp+58h] [rbp-49h] BYREF
  HANDLE hMutex; // [rsp+60h] [rbp-41h] BYREF
  __int16 v48; // [rsp+68h] [rbp-39h]
  _BYTE v49[128]; // [rsp+70h] [rbp-31h] BYREF

  LODWORD(lpMem) = -2147023537;
  *(_QWORD *)v42 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp";
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v49);
  hMutex = 0;
  v48 = 0;
  v9 = StoreLock::Lock((StoreLock *)&hMutex);
  v11 = v9;
  if ( v9 < 0 )
  {
    if ( v9 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x363,
      v11,
      v40);
    v13 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v11, v12);
    goto LABEL_50;
  }
  v41 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a2 )
  {
    v14 = hMutex;
    LODWORD(v43) = 878;
    if ( hMutex )
    {
      if ( (_BYTE)v48 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v48) = 0;
      }
      CloseHandle_0(v14);
      hMutex = 0;
    }
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v49);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(v42);
    return (unsigned int)lpMem;
  }
  if ( !a3 )
  {
    LODWORD(v43) = 879;
LABEL_17:
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(v42);
    v15 = hMutex;
    if ( hMutex )
    {
      if ( (_BYTE)v48 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v48) = 0;
      }
      CloseHandle_0(v15);
      hMutex = 0;
    }
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v49);
    return (unsigned int)lpMem;
  }
  if ( !a4 )
  {
    LODWORD(v43) = 880;
    goto LABEL_17;
  }
  if ( !a5 )
  {
    LODWORD(v43) = 881;
    goto LABEL_17;
  }
  v16 = IsolationImplementation::Com::ConvertIn(a3, (struct IDefinitionIdentity *)&v41, v10);
  v13 = v16;
  if ( v16 >= 0 )
  {
    v21 = v41;
    v22 = *((_QWORD *)this + 2);
    *(_QWORD *)v45 = 0;
    v46 = 0;
    v43 = 0;
    *(_QWORD *)v42 = 0;
    lpMem = 0;
    v23 = RtlLockComponentStoreComponent(v17, v22, v18, &v41);
    v25 = v23;
    if ( v23 >= 0 )
    {
      v27 = RtlLockComponentStoreComponentPath(v24, *((_QWORD *)this + 2), *(_QWORD *)v45, &v46);
      v29 = v27;
      if ( v27 >= 0 )
      {
        v41 = 0;
        v31 = IsolationImplementation::Com::CopyOutPath(
                (IsolationImplementation::Com *)v42,
                (const struct _LUNICODE_STRING *)&v41,
                v28);
        v13 = v31;
        if ( v31 >= 0 )
        {
          v34 = IsolationImplementation::Com::CoTaskMemAlloc((IsolationImplementation::Com *)0x10, v32);
          v35 = v34;
          if ( v34 )
          {
            *v34 = 0;
            v13 = 0;
            v34[1] = 0;
            *v34 = *(_QWORD *)v45;
            *(_QWORD *)v45 = 0;
            v36 = v34[1];
            v34[1] = v46;
            v37 = v41;
            *a4 = v35;
            *a5 = v37;
            v46 = v36;
          }
          else
          {
            v13 = -2147024882;
            if ( g_HRESULT_to_break_on == -2147024882 )
              DebugBreak();
            Windows::ErrorHandling::COM::ReportError(
              (Windows::ErrorHandling::COM *)"HR originated",
              "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
              (const char *)0x394,
              -2147024882,
              (unsigned int)v42);
          }
        }
        else
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
            (const char *)0x391,
            v31,
            v33);
        }
      }
      else
      {
        if ( v27 == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
          (const char *)0x38A,
          v29,
          (unsigned int)v42);
        v13 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v29, v30);
      }
      if ( lpMem )
        IsolationFreeStringRoutine(lpMem);
    }
    else
    {
      if ( v23 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x382,
        v25,
        (unsigned int)v45);
      v13 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v25, v26);
    }
    anonymous_namespace_::CComDualPathLock::_CComDualPathLock(v45);
    if ( !v21 )
      goto LABEL_50;
    v20 = v21;
    goto LABEL_49;
  }
  Windows::ErrorHandling::COM::ReportErrorPropagation(
    (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
    (const char *)0x373,
    v16,
    v19);
  v20 = v41;
  if ( v41 )
LABEL_49:
    RtlCloseDefinitionIdentityHandle(v20);
LABEL_50:
  v38 = hMutex;
  if ( hMutex )
  {
    if ( (_BYTE)v48 )
    {
      ReleaseMutex(hMutex);
      LOBYTE(v48) = 0;
    }
    CloseHandle_0(v38);
    hMutex = 0;
  }
  BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v49);
  return v13;
}

```

## disassembly

```asm
0x1800aed6c  push    rbp
0x1800aed6e  push    rbx
0x1800aed6f  push    rsi
0x1800aed70  push    rdi
0x1800aed71  push    r12
0x1800aed73  push    r13
0x1800aed75  push    r14
0x1800aed77  push    r15
0x1800aed79  lea     rbp, [rsp-17h]
0x1800aed7e  sub     rsp, 0B8h
0x1800aed85  mov     r13, rcx
0x1800aed88  mov     dword ptr [rbp+4Fh+lpMem], 8007054Fh
0x1800aed8f  lea     rsi, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800aed96  mov     r14, r9
0x1800aed99  lea     rcx, [rbp+4Fh+var_80]; this
0x1800aed9d  mov     qword ptr [rbp+4Fh+var_B8], rsi
0x1800aeda1  mov     rdi, r8
0x1800aeda4  mov     r15d, edx
0x1800aeda7  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800aedac  xor     r12d, r12d
0x1800aedaf  lea     rcx, [rbp+4Fh+hMutex]; this
0x1800aedb3  mov     [rbp+4Fh+hMutex], r12
0x1800aedb7  mov     [rbp+4Fh+var_88], r12w
0x1800aedbc  call    ?Lock@StoreLock@@QEAAJXZ; StoreLock::Lock(void)
0x1800aedc1  mov     ebx, eax
0x1800aedc3  test    eax, eax
0x1800aedc5  jns     short loc_1800AEDFB
0x1800aedc7  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800aedcd  jnz     short loc_1800AEDD5
0x1800aedcf  call    cs:__imp_DebugBreak
0x1800aedd5  mov     r9d, ebx; int
0x1800aedd8  lea     rcx, aStatusPropagat; "Status propagated"
0x1800aeddf  mov     r8d, 363h; char *
0x1800aede5  mov     rdx, rsi; char *
0x1800aede8  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800aeded  mov     ecx, ebx; this
0x1800aedef  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800aedf4  mov     edi, eax
0x1800aedf6  jmp     loc_1800AF08B
0x1800aedfb  mov     [rbp+4Fh+var_C0], r12
0x1800aedff  test    r14, r14
0x1800aee02  jz      short loc_1800AEE07
0x1800aee04  mov     [r14], r12
0x1800aee07  mov     rsi, [rbp+4Fh+arg_20]
0x1800aee0b  test    rsi, rsi
0x1800aee0e  jz      short loc_1800AEE13
0x1800aee10  mov     [rsi], r12
0x1800aee13  test    r15d, r15d
0x1800aee16  jz      short loc_1800AEE5B
0x1800aee18  mov     rbx, [rbp+4Fh+hMutex]
0x1800aee1c  mov     dword ptr [rbp+4Fh+var_B0], 36Eh
0x1800aee23  test    rbx, rbx
0x1800aee26  jz      short loc_1800AEE47
0x1800aee28  cmp     byte ptr [rbp+4Fh+var_88], r12b
0x1800aee2c  jz      short loc_1800AEE3B
0x1800aee2e  mov     rcx, rbx; hMutex
0x1800aee31  call    cs:__imp_ReleaseMutex
0x1800aee37  mov     byte ptr [rbp+4Fh+var_88], r12b
0x1800aee3b  mov     rcx, rbx; hObject
0x1800aee3e  call    CloseHandle_0
0x1800aee43  mov     [rbp+4Fh+hMutex], r12
0x1800aee47  lea     rcx, [rbp+4Fh+var_80]; this
0x1800aee4b  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800aee50  lea     rcx, [rbp+4Fh+var_B8]
0x1800aee54  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800aee59  jmp     short loc_1800AEEA1
0x1800aee5b  test    rdi, rdi
0x1800aee5e  jnz     short loc_1800AEEA9
0x1800aee60  mov     dword ptr [rbp+4Fh+var_B0], 36Fh
0x1800aee67  lea     rcx, [rbp+4Fh+var_B8]
0x1800aee6b  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800aee70  mov     rbx, [rbp+4Fh+hMutex]
0x1800aee74  test    rbx, rbx
0x1800aee77  jz      short loc_1800AEE98
0x1800aee79  cmp     byte ptr [rbp+4Fh+var_88], r12b
0x1800aee7d  jz      short loc_1800AEE8C
0x1800aee7f  mov     rcx, rbx; hMutex
0x1800aee82  call    cs:__imp_ReleaseMutex
0x1800aee88  mov     byte ptr [rbp+4Fh+var_88], r12b
0x1800aee8c  mov     rcx, rbx; hObject
0x1800aee8f  call    CloseHandle_0
0x1800aee94  mov     [rbp+4Fh+hMutex], r12
0x1800aee98  lea     rcx, [rbp+4Fh+var_80]; this
0x1800aee9c  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800aeea1  mov     edi, dword ptr [rbp+4Fh+lpMem]
0x1800aeea4  jmp     loc_1800AF0BC
0x1800aeea9  test    r14, r14
0x1800aeeac  jnz     short loc_1800AEEB7
0x1800aeeae  mov     dword ptr [rbp+4Fh+var_B0], 370h
0x1800aeeb5  jmp     short loc_1800AEE67
0x1800aeeb7  test    rsi, rsi
0x1800aeeba  jnz     short loc_1800AEEC5
0x1800aeebc  mov     dword ptr [rbp+4Fh+var_B0], 371h
0x1800aeec3  jmp     short loc_1800AEE67
0x1800aeec5  lea     rdx, [rbp+4Fh+var_C0]; struct IDefinitionIdentity *
0x1800aeec9  mov     rcx, rdi; this
0x1800aeecc  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionIdentity@@PEAU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionIdentity *,Windows::Isolation::Rtl::_DEFINITION_IDENTITY *)
0x1800aeed1  mov     edi, eax
0x1800aeed3  test    eax, eax
0x1800aeed5  jns     short loc_1800AEEFD
0x1800aeed7  mov     r8d, eax; int
0x1800aeeda  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800aeee1  mov     edx, 373h; char *
0x1800aeee6  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800aeeeb  mov     rcx, [rbp+4Fh+var_C0]
0x1800aeeef  test    rcx, rcx
0x1800aeef2  jz      loc_1800AF08B
0x1800aeef8  jmp     loc_1800AF086
0x1800aeefd  mov     rbx, [rbp+4Fh+var_C0]
0x1800aef01  lea     rax, [rbp+4Fh+var_A0]
0x1800aef05  mov     rdx, [r13+10h]
0x1800aef09  lea     r9, [rbp+4Fh+var_C0]
0x1800aef0d  mov     [rbp+4Fh+var_C0], rbx
0x1800aef11  mov     qword ptr [rsp+0F0h+var_D0], rax; unsigned int
0x1800aef16  mov     qword ptr [rbp+4Fh+var_A0], r12
0x1800aef1a  mov     [rbp+4Fh+var_98], r12
0x1800aef1e  mov     [rbp+4Fh+var_B0], r12
0x1800aef22  mov     qword ptr [rbp+4Fh+var_B8], r12
0x1800aef26  mov     [rbp+4Fh+lpMem], r12
0x1800aef2a  call    RtlLockComponentStoreComponent
0x1800aef2f  mov     edi, eax
0x1800aef31  test    eax, eax
0x1800aef33  jns     short loc_1800AEF6D
0x1800aef35  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800aef3b  jnz     short loc_1800AEF43
0x1800aef3d  call    cs:__imp_DebugBreak
0x1800aef43  mov     r9d, edi; int
0x1800aef46  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800aef4d  mov     r8d, 382h; char *
0x1800aef53  lea     rcx, aStatusPropagat; "Status propagated"
0x1800aef5a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800aef5f  mov     ecx, edi; this
0x1800aef61  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800aef66  mov     edi, eax
0x1800aef68  jmp     loc_1800AF075
0x1800aef6d  mov     r8, qword ptr [rbp+4Fh+var_A0]
0x1800aef71  lea     rax, [rbp+4Fh+var_B8]
0x1800aef75  mov     rdx, [r13+10h]
0x1800aef79  lea     r9, [rbp+4Fh+var_98]
0x1800aef7d  mov     qword ptr [rsp+0F0h+var_D0], rax; unsigned int
0x1800aef82  call    RtlLockComponentStoreComponentPath
0x1800aef87  mov     edi, eax
0x1800aef89  test    eax, eax
0x1800aef8b  jns     short loc_1800AEFC5
0x1800aef8d  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800aef93  jnz     short loc_1800AEF9B
0x1800aef95  call    cs:__imp_DebugBreak
0x1800aef9b  mov     r9d, edi; int
0x1800aef9e  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800aefa5  mov     r8d, 38Ah; char *
0x1800aefab  lea     rcx, aStatusPropagat; "Status propagated"
0x1800aefb2  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800aefb7  mov     ecx, edi; this
0x1800aefb9  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800aefbe  mov     edi, eax
0x1800aefc0  jmp     loc_1800AF067
0x1800aefc5  lea     rdx, [rbp+4Fh+var_C0]; struct _LUNICODE_STRING *
0x1800aefc9  mov     [rbp+4Fh+var_C0], r12
0x1800aefcd  lea     rcx, [rbp+4Fh+var_B8]; this
0x1800aefd1  call    ?CopyOutPath@Com@IsolationImplementation@@YAJAEBU_LUNICODE_STRING@@PEAPEAG@Z; IsolationImplementation::Com::CopyOutPath(_LUNICODE_STRING const &,ushort * *)
0x1800aefd6  mov     edi, eax
0x1800aefd8  test    eax, eax
0x1800aefda  jns     short loc_1800AEFF2
0x1800aefdc  mov     r8d, eax; int
0x1800aefdf  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800aefe6  mov     edx, 391h; char *
0x1800aefeb  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800aeff0  jmp     short loc_1800AF067
0x1800aeff2  mov     ecx, 10h; this
0x1800aeff7  call    ?CoTaskMemAlloc@Com@IsolationImplementation@@YAPEAXK@Z; IsolationImplementation::Com::CoTaskMemAlloc(ulong)
0x1800aeffc  mov     rdx, rax
0x1800aefff  test    rax, rax
0x1800af002  jnz     short loc_1800AF038
0x1800af004  mov     edi, 8007000Eh
0x1800af009  cmp     cs:?g_HRESULT_to_break_on@@3JA, edi; long g_HRESULT_to_break_on
0x1800af00f  jnz     short loc_1800AF017
0x1800af011  call    cs:__imp_DebugBreak
0x1800af017  mov     r9d, 8007000Eh; int
0x1800af01d  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800af024  mov     r8d, 394h; char *
0x1800af02a  lea     rcx, aHrOriginated; "HR originated"
0x1800af031  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800af036  jmp     short loc_1800AF067
0x1800af038  mov     [rax], r12
0x1800af03b  mov     edi, r12d
0x1800af03e  mov     [rax+8], r12
0x1800af042  mov     rax, qword ptr [rbp+4Fh+var_A0]
0x1800af046  mov     [rdx], rax
0x1800af049  mov     rax, [rbp+4Fh+var_98]
0x1800af04d  mov     qword ptr [rbp+4Fh+var_A0], r12
0x1800af051  mov     rcx, [rdx+8]
0x1800af055  mov     [rdx+8], rax
0x1800af059  mov     rax, [rbp+4Fh+var_C0]
0x1800af05d  mov     [r14], rdx
0x1800af060  mov     [rsi], rax
0x1800af063  mov     [rbp+4Fh+var_98], rcx
0x1800af067  mov     rcx, [rbp+4Fh+lpMem]; lpMem
0x1800af06b  test    rcx, rcx
0x1800af06e  jz      short loc_1800AF075
0x1800af070  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800af075  lea     rcx, [rbp+4Fh+var_A0]
0x1800af079  call    _anonymous_namespace___CComDualPathLock___CComDualPathLock
0x1800af07e  test    rbx, rbx
0x1800af081  jz      short loc_1800AF08B
0x1800af083  mov     rcx, rbx
0x1800af086  call    RtlCloseDefinitionIdentityHandle
0x1800af08b  mov     rbx, [rbp+4Fh+hMutex]
0x1800af08f  test    rbx, rbx
0x1800af092  jz      short loc_1800AF0B3
0x1800af094  cmp     byte ptr [rbp+4Fh+var_88], r12b
0x1800af098  jz      short loc_1800AF0A7
0x1800af09a  mov     rcx, rbx; hMutex
0x1800af09d  call    cs:__imp_ReleaseMutex
0x1800af0a3  mov     byte ptr [rbp+4Fh+var_88], r12b
0x1800af0a7  mov     rcx, rbx; hObject
0x1800af0aa  call    CloseHandle_0
0x1800af0af  mov     [rbp+4Fh+hMutex], r12
0x1800af0b3  lea     rcx, [rbp+4Fh+var_80]; this
0x1800af0b7  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800af0bc  mov     eax, edi
0x1800af0be  add     rsp, 0B8h
0x1800af0c5  pop     r15
0x1800af0c7  pop     r14
0x1800af0c9  pop     r13
0x1800af0cb  pop     r12
0x1800af0cd  pop     rdi
0x1800af0ce  pop     rsi
0x1800af0cf  pop     rbx
0x1800af0d0  pop     rbp
0x1800af0d1  retn
```
