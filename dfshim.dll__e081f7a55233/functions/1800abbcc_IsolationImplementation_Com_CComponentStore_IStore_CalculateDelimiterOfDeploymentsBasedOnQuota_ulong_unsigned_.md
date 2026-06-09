# IsolationImplementation::Com::CComponentStore::IStore_CalculateDelimiterOfDeploymentsBasedOnQuota(ulong,unsigned __int64,IDefinitionAppId * * const,_STORE_ASSEMBLY_INSTALLATION_REFERENCE const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1800abbcc`
- end: `0x1800ac0f2`
- name: `?IStore_CalculateDelimiterOfDeploymentsBasedOnQuota@CComponentStore@Com@IsolationImplementation@@IEAAJK_KQEAPEAUIDefinitionAppId@@PEBU_STORE_ASSEMBLY_INSTALLATION_REFERENCE@@0PEA_K33@Z`
- size: `1318`
- prototype: `__int64 __fastcall(IsolationImplementation::Com::CComponentStore *__hidden this, unsigned int, unsigned __int64, struct IDefinitionAppId **const, const struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *, unsigned __int64, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800a9810`

## callees

- `0x180006991`
- `0x1800069b5`
- `0x1800069c1`
- `0x180012acc`
- `0x180012b38`
- `0x1800164c0`
- `0x180017514`
- `0x180017530`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x180030508`
- `0x180031b3c`
- `0x180039c1c`
- `0x1800a9520`
- `0x1800a9c08`
- `0x1800abbcc`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800abc75`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800abcee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800abd47`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800abf4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac0b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800abc75`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800abcee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800abd47`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800abf4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac0b6`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800abc38`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800abdae`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800abeba`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800abfe0`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800abc38`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800abdae`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800abeba`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800abfe0`

## string_xrefs

- `0x1800abbf4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800abdb7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800abe55`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800abec3`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800abfe9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CComponentStore::IStore_CalculateDelimiterOfDeploymentsBasedOnQuota(
        IsolationImplementation::Com::CComponentStore *this,
        int a2,
        unsigned __int64 a3,
        struct IDefinitionAppId **const a4,
        const struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *a5,
        unsigned __int64 a6,
        unsigned __int64 *a7,
        unsigned __int64 *a8,
        unsigned __int64 *a9)
{
  int v11; // eax
  const struct Windows::Isolation::Rtl::_COMPONENT_STORE_REFERENCE_ **v12; // r9
  unsigned int v13; // ebx
  int v14; // edx
  unsigned int v15; // ebx
  HANDLE v16; // rdi
  unsigned __int64 *v17; // r13
  HANDLE v18; // rbx
  HANDLE v19; // rbx
  unsigned __int64 v20; // rsi
  unsigned __int64 v21; // rdi
  int v22; // ebx
  struct Windows::Isolation::Rtl::_DEFINITION_APPID *v23; // r8
  int v24; // edx
  unsigned int v25; // r13d
  __int64 v26; // r14
  _QWORD *v27; // rdx
  unsigned __int64 v28; // rcx
  _QWORD *v29; // rax
  int v30; // eax
  int v31; // eax
  unsigned int v32; // ebx
  int v33; // edx
  void (__fastcall *v34)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v36; // rdi
  HANDLE v37; // rdi
  __int64 v38; // r8
  _QWORD *v39; // rdx
  unsigned __int64 v40; // rcx
  _QWORD *v41; // rax
  int v42; // eax
  unsigned int v43; // ebx
  int v44; // edx
  void (__fastcall *v45)(LPVOID *); // rax
  HANDLE v46; // rax
  LPVOID *v47; // rdi
  void (__fastcall *v48)(LPVOID *); // rax
  HANDLE v49; // rax
  LPVOID *v50; // rdi
  unsigned int v52; // [rsp+28h] [rbp-B9h]
  unsigned int v53; // [rsp+28h] [rbp-B9h]
  LPVOID lpMem[2]; // [rsp+58h] [rbp-89h] BYREF
  __int128 v55; // [rsp+68h] [rbp-79h] BYREF
  unsigned __int64 v56; // [rsp+78h] [rbp-69h]
  unsigned __int64 v57; // [rsp+80h] [rbp-61h]
  HANDLE hMutex; // [rsp+88h] [rbp-59h] BYREF
  __int16 v59; // [rsp+90h] [rbp-51h]
  _BYTE v60[64]; // [rsp+98h] [rbp-49h] BYREF
  unsigned int v61[2]; // [rsp+D8h] [rbp-9h] BYREF

  LODWORD(v56) = -2147023537;
  *(_QWORD *)&v55 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp";
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v60);
  hMutex = 0;
  v59 = 0;
  v11 = StoreLock::Lock((StoreLock *)&hMutex);
  v13 = v11;
  if ( v11 < 0 )
  {
    if ( v11 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x1E7,
      v13,
      v52);
    v15 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v13, v14);
LABEL_5:
    v16 = hMutex;
    if ( hMutex )
    {
      if ( (_BYTE)v59 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v59) = 0;
      }
      CloseHandle_0(v16);
      hMutex = 0;
    }
    goto LABEL_85;
  }
  if ( a7 )
    *a7 = 0;
  v17 = a8;
  if ( a8 )
    *a8 = 0;
  if ( a9 )
    *a9 = 0;
  if ( a6 )
  {
    if ( !a7 )
    {
      DWORD2(v55) = 503;
LABEL_19:
      Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v55);
      v18 = hMutex;
      if ( hMutex )
      {
        if ( (_BYTE)v59 )
        {
          ReleaseMutex(hMutex);
          LOBYTE(v59) = 0;
        }
        CloseHandle_0(v18);
        hMutex = 0;
      }
      BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v60);
      return (unsigned int)v56;
    }
    if ( !a5 )
    {
      DWORD2(v55) = 504;
      goto LABEL_19;
    }
    if ( a3 && !a4 )
    {
      DWORD2(v55) = 505;
      goto LABEL_30;
    }
    v56 = 0;
    v57 = 0;
    v20 = 0;
    v21 = 0;
    v55 = 0;
    if ( a3 )
    {
      v22 = *(_DWORD *)BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::EnlargeNoPreserve(
                         &v55,
                         v61,
                         a3);
      if ( v22 < 0 )
      {
        if ( v22 == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
          (const char *)0x201,
          v22,
          v52);
        v15 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                (Windows::ErrorHandling::COM *)(unsigned int)v22,
                v24);
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v55);
        goto LABEL_5;
      }
      v20 = v56;
      v25 = 0;
      v26 = *((_QWORD *)&v55 + 1);
      v21 = v57;
      while ( 1 )
      {
        if ( v21 < v20 )
        {
          v27 = (_QWORD *)(v26 + 8 * v21);
          v28 = v20 - v21;
          if ( v20 != v21 )
          {
            do
            {
              v29 = v27++;
              *v29 = 0;
              --v28;
            }
            while ( v28 );
          }
          v21 = v20;
          v57 = v20;
        }
        v30 = IsolationImplementation::Com::ConvertIn(a4[v25], (struct IDefinitionAppId *)(v26 + 8LL * v25), v23);
        v15 = v30;
        if ( v30 < 0 )
          break;
        if ( ++v25 >= a3 )
        {
          v17 = a8;
          goto LABEL_50;
        }
      }
      Windows::ErrorHandling::COM::ReportErrorPropagation(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x204,
        v30,
        (int)v12);
      BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v55);
    }
    else
    {
      v26 = *((_QWORD *)&v55 + 1);
LABEL_50:
      lpMem[1] = lpMem;
      *(_QWORD *)v61 = 0;
      lpMem[0] = lpMem;
      v31 = IsolationImplementation::Com::ConvertIn(
              (IsolationImplementation::Com *)lpMem,
              a5,
              (const struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *)v61,
              v12);
      v32 = v31;
      if ( v31 < 0 )
      {
        if ( v31 == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
          (const char *)0x208,
          v32,
          v52);
        v15 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v32, v33);
        while ( 1 )
        {
          v36 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v36 == lpMem )
            break;
          v34 = (void (__fastcall *)(LPVOID *))v36[2];
          if ( v34 )
            v34(v36 + 3);
          ProcessHeap_0 = GetProcessHeap_0();
          HeapFree_0(ProcessHeap_0, 0, v36);
        }
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v55);
        v37 = hMutex;
        if ( !hMutex )
          goto LABEL_85;
        if ( (_BYTE)v59 )
        {
          ReleaseMutex(hMutex);
          LOBYTE(v59) = 0;
        }
        goto LABEL_84;
      }
      v38 = *(_QWORD *)v61;
      if ( v21 < v20 )
      {
        v39 = (_QWORD *)(v26 + 8 * v21);
        v40 = v20 - v21;
        if ( v20 != v21 )
        {
          do
          {
            v41 = v39++;
            *v41 = 0;
            --v40;
          }
          while ( v40 );
        }
        v57 = v20;
      }
      v42 = RtlCalculateDelimiterOfDeploymentsBasedOnQuota(
              a2,
              *((_QWORD *)this + 2),
              a3,
              v26,
              v38,
              a6,
              (__int64)a7,
              (__int64)v17,
              (__int64)a9);
      v43 = v42;
      if ( v42 >= 0 )
      {
        v15 = 0;
        while ( 1 )
        {
          v50 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v50 == lpMem )
            break;
          v48 = (void (__fastcall *)(LPVOID *))v50[2];
          if ( v48 )
            v48(v50 + 3);
          v49 = GetProcessHeap_0();
          HeapFree_0(v49, 0, v50);
        }
      }
      else
      {
        if ( v42 == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
          (const char *)0x215,
          v43,
          v53);
        v15 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v43, v44);
        while ( 1 )
        {
          v47 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v47 == lpMem )
            break;
          v45 = (void (__fastcall *)(LPVOID *))v47[2];
          if ( v45 )
            v45(v47 + 3);
          v46 = GetProcessHeap_0();
          HeapFree_0(v46, 0, v47);
        }
      }
      BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v55);
    }
    v37 = hMutex;
    if ( !hMutex )
    {
LABEL_85:
      BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v60);
      return v15;
    }
    if ( (_BYTE)v59 )
    {
      ReleaseMutex(hMutex);
      LOBYTE(v59) = 0;
    }
LABEL_84:
    CloseHandle_0(v37);
    hMutex = 0;
    goto LABEL_85;
  }
  DWORD2(v55) = 502;
LABEL_30:
  v19 = hMutex;
  if ( hMutex )
  {
    if ( (_BYTE)v59 )
    {
      ReleaseMutex(hMutex);
      LOBYTE(v59) = 0;
    }
    CloseHandle_0(v19);
    hMutex = 0;
  }
  BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v60);
  Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v55);
  return (unsigned int)v56;
}

```

## disassembly

```asm
0x1800abbcc  mov     rax, rsp
0x1800abbcf  mov     [rax+18h], rbx
0x1800abbd3  mov     [rax+20h], r9
0x1800abbd7  mov     [rax+10h], edx
0x1800abbda  mov     [rax+8], rcx
0x1800abbde  push    rbp
0x1800abbdf  push    rsi
0x1800abbe0  push    rdi
0x1800abbe1  push    r12
0x1800abbe3  push    r13
0x1800abbe5  push    r14
0x1800abbe7  push    r15
0x1800abbe9  lea     rbp, [rax-3Fh]
0x1800abbed  sub     rsp, 0E0h
0x1800abbf4  lea     rsi, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800abbfb  mov     dword ptr [rbp+37h+var_A0], 8007054Fh
0x1800abc02  lea     rcx, [rbp+37h+var_80]; this
0x1800abc06  mov     qword ptr [rbp+37h+var_B0], rsi
0x1800abc0a  mov     rdi, r9
0x1800abc0d  mov     r12, r8
0x1800abc10  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800abc15  xor     r14d, r14d
0x1800abc18  lea     rcx, [rbp+37h+hMutex]; this
0x1800abc1c  mov     [rbp+37h+hMutex], r14
0x1800abc20  mov     [rbp+37h+var_88], r14w
0x1800abc25  call    ?Lock@StoreLock@@QEAAJXZ; StoreLock::Lock(void)
0x1800abc2a  mov     ebx, eax
0x1800abc2c  test    eax, eax
0x1800abc2e  jns     short loc_1800ABC90
0x1800abc30  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800abc36  jnz     short loc_1800ABC3E
0x1800abc38  call    cs:__imp_DebugBreak
0x1800abc3e  mov     r9d, ebx; int
0x1800abc41  lea     rcx, aStatusPropagat; "Status propagated"
0x1800abc48  mov     r8d, 1E7h; char *
0x1800abc4e  mov     rdx, rsi; char *
0x1800abc51  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800abc56  mov     ecx, ebx; this
0x1800abc58  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800abc5d  mov     ebx, eax
0x1800abc5f  mov     rdi, [rbp+37h+hMutex]
0x1800abc63  test    rdi, rdi
0x1800abc66  jz      loc_1800AC0CC
0x1800abc6c  cmp     byte ptr [rbp+37h+var_88], r14b
0x1800abc70  jz      short loc_1800ABC7F
0x1800abc72  mov     rcx, rdi; hMutex
0x1800abc75  call    cs:__imp_ReleaseMutex
0x1800abc7b  mov     byte ptr [rbp+37h+var_88], r14b
0x1800abc7f  mov     rcx, rdi; hObject
0x1800abc82  call    CloseHandle_0
0x1800abc87  mov     [rbp+37h+hMutex], r14
0x1800abc8b  jmp     loc_1800AC0CC
0x1800abc90  mov     r15, [rbp+37h+arg_30]
0x1800abc94  test    r15, r15
0x1800abc97  jz      short loc_1800ABC9C
0x1800abc99  mov     [r15], r14
0x1800abc9c  mov     r13, [rbp+37h+arg_38]
0x1800abca0  test    r13, r13
0x1800abca3  jz      short loc_1800ABCA9
0x1800abca5  mov     [r13+0], r14
0x1800abca9  mov     rax, [rbp+37h+arg_40]
0x1800abcb0  test    rax, rax
0x1800abcb3  jz      short loc_1800ABCB8
0x1800abcb5  mov     [rax], r14
0x1800abcb8  cmp     [rbp+37h+arg_28], r14
0x1800abcbc  jnz     short loc_1800ABCC7
0x1800abcbe  mov     dword ptr [rbp+37h+var_B0+8], 1F6h
0x1800abcc5  jmp     short loc_1800ABD35
0x1800abcc7  test    r15, r15
0x1800abcca  jnz     short loc_1800ABD15
0x1800abccc  mov     dword ptr [rbp+37h+var_B0+8], 1F7h
0x1800abcd3  lea     rcx, [rbp+37h+var_B0]
0x1800abcd7  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800abcdc  mov     rbx, [rbp+37h+hMutex]
0x1800abce0  test    rbx, rbx
0x1800abce3  jz      short loc_1800ABD04
0x1800abce5  cmp     byte ptr [rbp+37h+var_88], r14b
0x1800abce9  jz      short loc_1800ABCF8
0x1800abceb  mov     rcx, rbx; hMutex
0x1800abcee  call    cs:__imp_ReleaseMutex
0x1800abcf4  mov     byte ptr [rbp+37h+var_88], r14b
0x1800abcf8  mov     rcx, rbx; hObject
0x1800abcfb  call    CloseHandle_0
0x1800abd00  mov     [rbp+37h+hMutex], r14
0x1800abd04  lea     rcx, [rbp+37h+var_80]; this
0x1800abd08  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800abd0d  mov     ebx, dword ptr [rbp+37h+var_A0]
0x1800abd10  jmp     loc_1800AC0D5
0x1800abd15  cmp     [rbp+37h+arg_20], r14
0x1800abd19  jnz     short loc_1800ABD24
0x1800abd1b  mov     dword ptr [rbp+37h+var_B0+8], 1F8h
0x1800abd22  jmp     short loc_1800ABCD3
0x1800abd24  test    r12, r12
0x1800abd27  jz      short loc_1800ABD71
0x1800abd29  test    rdi, rdi
0x1800abd2c  jnz     short loc_1800ABD71
0x1800abd2e  mov     dword ptr [rbp+37h+var_B0+8], 1F9h
0x1800abd35  mov     rbx, [rbp+37h+hMutex]
0x1800abd39  test    rbx, rbx
0x1800abd3c  jz      short loc_1800ABD5D
0x1800abd3e  cmp     byte ptr [rbp+37h+var_88], r14b
0x1800abd42  jz      short loc_1800ABD51
0x1800abd44  mov     rcx, rbx; hMutex
0x1800abd47  call    cs:__imp_ReleaseMutex
0x1800abd4d  mov     byte ptr [rbp+37h+var_88], r14b
0x1800abd51  mov     rcx, rbx; hObject
0x1800abd54  call    CloseHandle_0
0x1800abd59  mov     [rbp+37h+hMutex], r14
0x1800abd5d  lea     rcx, [rbp+37h+var_80]; this
0x1800abd61  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800abd66  lea     rcx, [rbp+37h+var_B0]
0x1800abd6a  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800abd6f  jmp     short loc_1800ABD0D
0x1800abd71  mov     [rbp+37h+var_A0], r14
0x1800abd75  xorps   xmm0, xmm0
0x1800abd78  mov     [rbp+37h+var_98], r14
0x1800abd7c  mov     rsi, r14
0x1800abd7f  mov     rdi, r14
0x1800abd82  movdqu  [rbp+37h+var_B0], xmm0
0x1800abd87  test    r12, r12
0x1800abd8a  jz      loc_1800ABE76
0x1800abd90  mov     r8, r12
0x1800abd93  lea     rdx, [rbp+37h+var_40]
0x1800abd97  lea     rcx, [rbp+37h+var_B0]
0x1800abd9b  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@_KV?$CTSHANDLE@VCDefinitionAppIdHandleTraits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@V?$CDefaultObjectTraits@V?$CTSHANDLE@VCDefinitionAppIdHandleTraits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@_K@Z; BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::EnlargeNoPreserve(unsigned __int64)
0x1800abda0  mov     ebx, [rax]
0x1800abda2  test    ebx, ebx
0x1800abda4  jns     short loc_1800ABDE7
0x1800abda6  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800abdac  jnz     short loc_1800ABDB4
0x1800abdae  call    cs:__imp_DebugBreak
0x1800abdb4  mov     r9d, ebx; int
0x1800abdb7  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800abdbe  mov     r8d, 201h; char *
0x1800abdc4  lea     rcx, aStatusPropagat; "Status propagated"
0x1800abdcb  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800abdd0  mov     ecx, ebx; this
0x1800abdd2  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800abdd7  lea     rcx, [rbp+37h+var_B0]
0x1800abddb  mov     ebx, eax
0x1800abddd  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CTSHANDLE@VCDefinitionAppIdHandleTraits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800abde2  jmp     loc_1800ABC5F
0x1800abde7  mov     rsi, [rbp+37h+var_A0]
0x1800abdeb  mov     r13d, r14d
0x1800abdee  mov     r14, qword ptr [rbp+37h+var_B0+8]
0x1800abdf2  mov     rdi, [rbp+37h+var_98]
0x1800abdf6  test    r12, r12
0x1800abdf9  jz      short loc_1800ABE4C
0x1800abdfb  cmp     rdi, rsi
0x1800abdfe  jnb     short loc_1800ABE27
0x1800abe00  mov     rcx, rsi
0x1800abe03  lea     rdx, [r14+rdi*8]
0x1800abe07  sub     rcx, rdi
0x1800abe0a  jz      short loc_1800ABE20
0x1800abe0c  mov     rax, rdx
0x1800abe0f  add     rdx, 8
0x1800abe13  mov     qword ptr [rax], 0
0x1800abe1a  sub     rcx, 1
0x1800abe1e  jnz     short loc_1800ABE0C
0x1800abe20  mov     rdi, rsi
0x1800abe23  mov     [rbp+37h+var_98], rsi
0x1800abe27  mov     rax, [rbp+37h+arg_18]
0x1800abe2b  mov     ecx, r13d
0x1800abe2e  lea     rdx, [r14+rcx*8]; struct IDefinitionAppId *
0x1800abe32  mov     rcx, [rax+rcx*8]; this
0x1800abe36  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionAppId@@PEAU_DEFINITION_APPID@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionAppId *,Windows::Isolation::Rtl::_DEFINITION_APPID *)
0x1800abe3b  mov     ebx, eax
0x1800abe3d  test    eax, eax
0x1800abe3f  js      short loc_1800ABE52
0x1800abe41  inc     r13d
0x1800abe44  mov     eax, r13d
0x1800abe47  cmp     rax, r12
0x1800abe4a  jb      short loc_1800ABDFB
0x1800abe4c  mov     r13, [rbp+37h+arg_38]
0x1800abe50  jmp     short loc_1800ABE7A
0x1800abe52  mov     r8d, eax; int
0x1800abe55  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800abe5c  mov     edx, 204h; char *
0x1800abe61  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800abe66  lea     rcx, [rbp+37h+var_B0]
0x1800abe6a  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CTSHANDLE@VCDefinitionAppIdHandleTraits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800abe6f  xor     esi, esi
0x1800abe71  jmp     loc_1800AC0A4
0x1800abe76  mov     r14, qword ptr [rbp+37h+var_B0+8]
0x1800abe7a  mov     rdx, [rbp+37h+arg_20]; struct _RTL_ALLOCATION_LIST *
0x1800abe7e  lea     rax, [rsp+110h+lpMem]
0x1800abe83  mov     [rsp+110h+lpMem+8], rax
0x1800abe88  lea     r8, [rbp+37h+var_40]; struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *
0x1800abe8c  lea     rax, [rsp+110h+lpMem]
0x1800abe91  mov     qword ptr [rbp+37h+var_40], 0
0x1800abe99  lea     rcx, [rsp+110h+lpMem]; this
0x1800abe9e  mov     [rsp+110h+lpMem], rax
0x1800abea3  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_STORE_ASSEMBLY_INSTALLATION_REFERENCE@@AEAPEBU_COMPONENT_STORE_REFERENCE_@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_STORE_ASSEMBLY_INSTALLATION_REFERENCE const *,Windows::Isolation::Rtl::_COMPONENT_STORE_REFERENCE_ const * &)
0x1800abea8  mov     ebx, eax
0x1800abeaa  test    eax, eax
0x1800abeac  jns     loc_1800ABF69
0x1800abeb2  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800abeb8  jnz     short loc_1800ABEC0
0x1800abeba  call    cs:__imp_DebugBreak
0x1800abec0  mov     r9d, ebx; int
0x1800abec3  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800abeca  mov     r8d, 208h; char *
0x1800abed0  lea     rcx, aStatusPropagat; "Status propagated"
0x1800abed7  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800abedc  mov     ecx, ebx; this
0x1800abede  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800abee3  mov     ebx, eax
0x1800abee5  jmp     short loc_1800ABF0B
0x1800abee7  mov     rax, [rdi+10h]
0x1800abeeb  test    rax, rax
0x1800abeee  jz      short loc_1800ABEF9
0x1800abef0  lea     rcx, [rdi+18h]
0x1800abef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abef9  call    GetProcessHeap_0
0x1800abefe  mov     r8, rdi; lpMem
0x1800abf01  xor     edx, edx; dwFlags
0x1800abf03  mov     rcx, rax; hHeap
0x1800abf06  call    HeapFree_0
0x1800abf0b  mov     rdi, [rsp+110h+lpMem]
0x1800abf10  lea     rcx, [rsp+110h+lpMem]
0x1800abf15  mov     rax, [rdi]
0x1800abf18  mov     [rsp+110h+lpMem], rax
0x1800abf1d  mov     [rax+8], rcx
0x1800abf21  lea     rax, [rsp+110h+lpMem]
0x1800abf26  cmp     rdi, rax
0x1800abf29  jnz     short loc_1800ABEE7
0x1800abf2b  lea     rcx, [rbp+37h+var_B0]
0x1800abf2f  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CTSHANDLE@VCDefinitionAppIdHandleTraits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CDefinitionAppIdHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800abf34  mov     rdi, [rbp+37h+hMutex]
0x1800abf38  test    rdi, rdi
0x1800abf3b  jz      loc_1800AC0CC
0x1800abf41  cmp     byte ptr [rbp+37h+var_88], 0
0x1800abf45  jz      short loc_1800ABF54
0x1800abf47  mov     rcx, rdi; hMutex
0x1800abf4a  call    cs:__imp_ReleaseMutex
0x1800abf50  mov     byte ptr [rbp+37h+var_88], 0
0x1800abf54  mov     rcx, rdi; hObject
0x1800abf57  call    CloseHandle_0
0x1800abf5c  mov     [rbp+37h+hMutex], 0
0x1800abf64  jmp     loc_1800AC0CC
0x1800abf69  mov     r8, qword ptr [rbp+37h+var_40]
0x1800abf6d  cmp     rdi, rsi
0x1800abf70  jnb     short loc_1800ABF96
0x1800abf72  mov     rcx, rsi
0x1800abf75  lea     rdx, [r14+rdi*8]
0x1800abf79  sub     rcx, rdi
0x1800abf7c  jz      short loc_1800ABF92
0x1800abf7e  mov     rax, rdx
0x1800abf81  add     rdx, 8
0x1800abf85  mov     qword ptr [rax], 0
0x1800abf8c  sub     rcx, 1
0x1800abf90  jnz     short loc_1800ABF7E
0x1800abf92  mov     [rbp+37h+var_98], rsi
0x1800abf96  mov     rax, [rbp+37h+arg_40]
0x1800abf9d  mov     r9, r14
0x1800abfa0  mov     rdx, [rbp+37h+arg_0]
0x1800abfa4  mov     ecx, [rbp+37h+arg_8]
0x1800abfa7  mov     [rsp+40h], rax
0x1800abfac  mov     rax, [rbp+37h+arg_28]
0x1800abfb0  mov     rdx, [rdx+10h]
0x1800abfb4  mov     [rsp+110h+var_D8], r13
0x1800abfb9  mov     [rsp+110h+var_E0], r15
0x1800abfbe  mov     [rsp+110h+var_E8], rax
0x1800abfc3  mov     qword ptr [rsp+110h+var_F0], r8; unsigned int
0x1800abfc8  mov     r8, r12
0x1800abfcb  call    RtlCalculateDelimiterOfDeploymentsBasedOnQuota
0x1800abfd0  xor     esi, esi
0x1800abfd2  mov     ebx, eax
0x1800abfd4  test    eax, eax
0x1800abfd6  jns     short loc_1800AC053
0x1800abfd8  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800abfde  jnz     short loc_1800ABFE6
0x1800abfe0  call    cs:__imp_DebugBreak
0x1800abfe6  mov     r9d, ebx; int
0x1800abfe9  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800abff0  mov     r8d, 215h; char *
0x1800abff6  lea     rcx, aStatusPropagat; "Status propagated"
0x1800abffd  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ac002  mov     ecx, ebx; this
0x1800ac004  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ac009  mov     ebx, eax
0x1800ac00b  jmp     short loc_1800AC031
0x1800ac00d  mov     rax, [rdi+10h]
0x1800ac011  test    rax, rax
0x1800ac014  jz      short loc_1800AC01F
0x1800ac016  lea     rcx, [rdi+18h]
0x1800ac01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac01f  call    GetProcessHeap_0
0x1800ac024  mov     r8, rdi; lpMem
0x1800ac027  xor     edx, edx; dwFlags
0x1800ac029  mov     rcx, rax; hHeap
0x1800ac02c  call    HeapFree_0
0x1800ac031  mov     rdi, [rsp+110h+lpMem]
0x1800ac036  lea     rcx, [rsp+110h+lpMem]
0x1800ac03b  mov     rax, [rdi]
0x1800ac03e  mov     [rsp+110h+lpMem], rax
0x1800ac043  mov     [rax+8], rcx
0x1800ac047  lea     rax, [rsp+110h+lpMem]
0x1800ac04c  cmp     rdi, rax
0x1800ac04f  jnz     short loc_1800AC00D
  ... truncated ...
```
