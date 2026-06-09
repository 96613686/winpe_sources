# IsolationImplementation::Com::CComponentStore::IStore_GetDeploymentProperty(ulong,IDefinitionAppId *,_STORE_ASSEMBLY_INSTALLATION_REFERENCE const *,_GUID const &,ushort const *,tagBLOB *)

- ea: `0x1800adf54`
- end: `0x1800ae5cf`
- name: `?IStore_GetDeploymentProperty@CComponentStore@Com@IsolationImplementation@@IEAAJKPEAUIDefinitionAppId@@PEBU_STORE_ASSEMBLY_INSTALLATION_REFERENCE@@AEBU_GUID@@PEBGPEAUtagBLOB@@@Z`
- size: `1659`
- prototype: `int(IsolationImplementation::Com::CComponentStore *__hidden this, unsigned int, struct IDefinitionAppId *, const struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *, const struct _GUID *, const unsigned __int16 *, struct tagBLOB *)`
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800aaea0`

## callees

- `0x180006991`
- `0x1800069b5`
- `0x1800069c1`
- `0x180012874`
- `0x180012acc`
- `0x180012b38`
- `0x180017514`
- `0x180017530`
- `0x1800187f0`
- `0x180018940`
- `0x1800193bc`
- `0x180030508`
- `0x180031b3c`
- `0x180039c1c`
- `0x18003eb10`
- `0x1800adf54`
- `0x1800fe440`
- `0x18010b5bc`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ae025`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ae070`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ae0cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ae584`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ae025`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ae070`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ae0cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ae584`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800adfe2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ae176`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ae231`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ae2f1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ae3ba`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ae470`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800adfe2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ae176`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ae231`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ae2f1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ae3ba`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ae470`

## string_xrefs

- `0x1800adf85`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800adfeb`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ae17f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ae23a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ae2fa`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ae3c3`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ae479`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CComponentStore::IStore_GetDeploymentProperty(
        IsolationImplementation::Com::CComponentStore *this,
        int a2,
        struct IDefinitionAppId *a3,
        const struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *a4,
        const struct _GUID *a5,
        struct _LUNICODE_STRING *a6,
        struct tagBLOB *a7)
{
  int v10; // ebx
  struct Windows::Isolation::Rtl::_DEFINITION_APPID *v11; // r8
  int v12; // edx
  unsigned int v13; // eax
  HANDLE v14; // rdi
  unsigned int v15; // ebx
  HANDLE v16; // rbx
  HANDLE v17; // rbx
  int v18; // eax
  const struct Windows::Isolation::Rtl::_COMPONENT_STORE_REFERENCE_ **v19; // r9
  unsigned int v20; // ebx
  int v21; // edx
  void (__fastcall *v22)(LPVOID *); // rax
  HANDLE v23; // rax
  LPVOID *v24; // rdi
  int v25; // eax
  const unsigned __int16 *v26; // r8
  unsigned int v27; // ebx
  int v28; // edx
  void (__fastcall *v29)(LPVOID *); // rax
  HANDLE v30; // rax
  LPVOID *v31; // rdi
  int v32; // eax
  int v33; // ecx
  unsigned int v34; // ebx
  int v35; // edx
  void (__fastcall *v36)(LPVOID *); // rax
  HANDLE v37; // rax
  LPVOID *v38; // rdi
  int ComponentStoreDeploymentProperties; // eax
  struct tagBLOB *v40; // r8
  unsigned int v41; // ebx
  int v42; // edx
  void (__fastcall *v43)(LPVOID *); // rax
  HANDLE v44; // rax
  LPVOID *v45; // rdi
  int v46; // eax
  unsigned int v47; // ebx
  int v48; // edx
  void (__fastcall *v49)(LPVOID *); // rax
  HANDLE v50; // rax
  LPVOID *v51; // rdi
  void (__fastcall *v52)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v54; // rdi
  HANDLE v55; // rdi
  unsigned int v57; // [rsp+20h] [rbp-E0h]
  LPVOID lpMem[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v59; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hMutex; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v61; // [rsp+58h] [rbp-A8h]
  _BYTE v62[64]; // [rsp+60h] [rbp-A0h] BYREF
  const char *v63; // [rsp+A0h] [rbp-60h] BYREF
  int v64; // [rsp+A8h] [rbp-58h]
  unsigned int v65; // [rsp+B0h] [rbp-50h]
  __int64 v66; // [rsp+B8h] [rbp-48h] BYREF
  IsolationImplementation::Com::CComponentStore *v67; // [rsp+C0h] [rbp-40h]
  __int128 v68; // [rsp+D0h] [rbp-30h]
  __int128 v69; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v70; // [rsp+F0h] [rbp-10h] BYREF
  void *v71[2]; // [rsp+100h] [rbp+0h]

  v67 = this;
  v63 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp";
  v65 = -2147023537;
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v62);
  hMutex = 0;
  v61 = 0;
  v10 = StoreLock::Lock((StoreLock *)&hMutex);
  if ( v10 < 0 )
  {
    if ( v10 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x415,
      v10,
      v57);
    v13 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v10, v12);
    v14 = hMutex;
    v15 = v13;
    if ( hMutex )
    {
      if ( (_BYTE)v61 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v61) = 0;
      }
      CloseHandle_0(v14);
      hMutex = 0;
    }
LABEL_102:
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v62);
    return v15;
  }
  if ( a7 )
  {
    a7->cbSize = 0;
    a7->pBlobData = 0;
  }
  if ( a2 )
  {
    v16 = hMutex;
    v64 = 1053;
    if ( hMutex )
    {
      if ( (_BYTE)v61 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v61) = 0;
      }
      CloseHandle_0(v16);
      hMutex = 0;
    }
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v62);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v63);
  }
  else
  {
    if ( a3 )
    {
      if ( a4 )
      {
        if ( a6 )
        {
          if ( a7 )
          {
            v59 = 0;
            v70 = 0;
            v69 = 0;
            lpMem[1] = lpMem;
            *(_OWORD *)v71 = 0;
            lpMem[0] = lpMem;
            v68 = 0;
            v66 = 0;
            v18 = IsolationImplementation::Com::ConvertIn(a3, (struct IDefinitionAppId *)&v59, v11);
            v20 = v18;
            if ( v18 >= 0 )
            {
              v25 = IsolationImplementation::Com::ConvertIn(
                      (IsolationImplementation::Com *)lpMem,
                      a4,
                      (const struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *)&v66,
                      v19);
              v27 = v25;
              if ( v25 >= 0 )
              {
                v68 = (__int128)*a5;
                v32 = Windows::Rtl::Init((Windows::Rtl *)&v69, a6, v26);
                v34 = v32;
                if ( v32 >= 0 )
                {
                  ComponentStoreDeploymentProperties = RtlFetchComponentStoreDeploymentProperties(
                                                         v33,
                                                         *((_QWORD *)v67 + 2),
                                                         v59,
                                                         v66);
                  v41 = ComponentStoreDeploymentProperties;
                  if ( ComponentStoreDeploymentProperties >= 0 )
                  {
                    v46 = IsolationImplementation::Com::CopyOut(
                            (IsolationImplementation::Com *)((char *)&v70 + 8),
                            (const struct _LBLOB *)a7,
                            v40);
                    v47 = v46;
                    if ( v46 >= 0 )
                    {
                      v15 = 0;
                      if ( v71[1] )
                        IsolationFreeStringRoutine(v71[1]);
                      if ( v59 )
                      {
                        RtlCloseDefinitionAppIdHandle();
                        v59 = 0;
                      }
                      while ( 1 )
                      {
                        v54 = (LPVOID *)lpMem[0];
                        lpMem[0] = *(LPVOID *)lpMem[0];
                        *((_QWORD *)lpMem[0] + 1) = lpMem;
                        if ( v54 == lpMem )
                          break;
                        v52 = (void (__fastcall *)(LPVOID *))v54[2];
                        if ( v52 )
                          v52(v54 + 3);
                        ProcessHeap_0 = GetProcessHeap_0();
                        HeapFree_0(ProcessHeap_0, 0, v54);
                      }
                    }
                    else
                    {
                      if ( v46 == g_NTSTATUS_to_break_on_propagate )
                        DebugBreak();
                      Windows::ErrorHandling::COM::ReportError(
                        (Windows::ErrorHandling::COM *)"Status propagated",
                        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
                        (const char *)0x437,
                        v47,
                        v57);
                      v15 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                              (Windows::ErrorHandling::COM *)v47,
                              v48);
                      if ( v71[1] )
                        IsolationFreeStringRoutine(v71[1]);
                      if ( v59 )
                      {
                        RtlCloseDefinitionAppIdHandle();
                        v59 = 0;
                      }
                      while ( 1 )
                      {
                        v51 = (LPVOID *)lpMem[0];
                        lpMem[0] = *(LPVOID *)lpMem[0];
                        *((_QWORD *)lpMem[0] + 1) = lpMem;
                        if ( v51 == lpMem )
                          break;
                        v49 = (void (__fastcall *)(LPVOID *))v51[2];
                        if ( v49 )
                          v49(v51 + 3);
                        v50 = GetProcessHeap_0();
                        HeapFree_0(v50, 0, v51);
                      }
                    }
                  }
                  else
                  {
                    if ( ComponentStoreDeploymentProperties == g_NTSTATUS_to_break_on_propagate )
                      DebugBreak();
                    Windows::ErrorHandling::COM::ReportError(
                      (Windows::ErrorHandling::COM *)"Status propagated",
                      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
                      (const char *)0x435,
                      v41,
                      v57);
                    v15 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v41, v42);
                    if ( v71[1] )
                      IsolationFreeStringRoutine(v71[1]);
                    if ( v59 )
                    {
                      RtlCloseDefinitionAppIdHandle();
                      v59 = 0;
                    }
                    while ( 1 )
                    {
                      v45 = (LPVOID *)lpMem[0];
                      lpMem[0] = *(LPVOID *)lpMem[0];
                      *((_QWORD *)lpMem[0] + 1) = lpMem;
                      if ( v45 == lpMem )
                        break;
                      v43 = (void (__fastcall *)(LPVOID *))v45[2];
                      if ( v43 )
                        v43(v45 + 3);
                      v44 = GetProcessHeap_0();
                      HeapFree_0(v44, 0, v45);
                    }
                  }
                }
                else
                {
                  if ( v32 == g_NTSTATUS_to_break_on_propagate )
                    DebugBreak();
                  Windows::ErrorHandling::COM::ReportError(
                    (Windows::ErrorHandling::COM *)"Status propagated",
                    "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
                    (const char *)0x42C,
                    v34,
                    v57);
                  v15 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v34, v35);
                  if ( v71[1] )
                    IsolationFreeStringRoutine(v71[1]);
                  if ( v59 )
                  {
                    RtlCloseDefinitionAppIdHandle();
                    v59 = 0;
                  }
                  while ( 1 )
                  {
                    v38 = (LPVOID *)lpMem[0];
                    lpMem[0] = *(LPVOID *)lpMem[0];
                    *((_QWORD *)lpMem[0] + 1) = lpMem;
                    if ( v38 == lpMem )
                      break;
                    v36 = (void (__fastcall *)(LPVOID *))v38[2];
                    if ( v36 )
                      v36(v38 + 3);
                    v37 = GetProcessHeap_0();
                    HeapFree_0(v37, 0, v38);
                  }
                }
              }
              else
              {
                if ( v25 == g_NTSTATUS_to_break_on_propagate )
                  DebugBreak();
                Windows::ErrorHandling::COM::ReportError(
                  (Windows::ErrorHandling::COM *)"Status propagated",
                  "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
                  (const char *)0x429,
                  v27,
                  v57);
                v15 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v27, v28);
                if ( v71[1] )
                  IsolationFreeStringRoutine(v71[1]);
                if ( v59 )
                {
                  RtlCloseDefinitionAppIdHandle();
                  v59 = 0;
                }
                while ( 1 )
                {
                  v31 = (LPVOID *)lpMem[0];
                  lpMem[0] = *(LPVOID *)lpMem[0];
                  *((_QWORD *)lpMem[0] + 1) = lpMem;
                  if ( v31 == lpMem )
                    break;
                  v29 = (void (__fastcall *)(LPVOID *))v31[2];
                  if ( v29 )
                    v29(v31 + 3);
                  v30 = GetProcessHeap_0();
                  HeapFree_0(v30, 0, v31);
                }
              }
            }
            else
            {
              if ( v18 == g_NTSTATUS_to_break_on_propagate )
                DebugBreak();
              Windows::ErrorHandling::COM::ReportError(
                (Windows::ErrorHandling::COM *)"Status propagated",
                "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
                (const char *)0x428,
                v20,
                v57);
              v15 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v20, v21);
              if ( v71[1] )
                IsolationFreeStringRoutine(v71[1]);
              if ( v59 )
              {
                RtlCloseDefinitionAppIdHandle();
                v59 = 0;
              }
              while ( 1 )
              {
                v24 = (LPVOID *)lpMem[0];
                lpMem[0] = *(LPVOID *)lpMem[0];
                *((_QWORD *)lpMem[0] + 1) = lpMem;
                if ( v24 == lpMem )
                  break;
                v22 = (void (__fastcall *)(LPVOID *))v24[2];
                if ( v22 )
                  v22(v24 + 3);
                v23 = GetProcessHeap_0();
                HeapFree_0(v23, 0, v24);
              }
            }
            v55 = hMutex;
            if ( hMutex )
            {
              if ( (_BYTE)v61 )
              {
                ReleaseMutex(hMutex);
                LOBYTE(v61) = 0;
              }
              CloseHandle_0(v55);
              hMutex = 0;
            }
            goto LABEL_102;
          }
          v64 = 1057;
        }
        else
        {
          v64 = 1056;
        }
      }
      else
      {
        v64 = 1055;
      }
    }
    else
    {
      v64 = 1054;
    }
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v63);
    v17 = hMutex;
    if ( hMutex )
    {
      if ( (_BYTE)v61 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v61) = 0;
      }
      CloseHandle_0(v17);
      hMutex = 0;
    }
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v62);
  }
  return v65;
}

```

## disassembly

```asm
0x1800adf54  mov     [rsp-8+arg_8], rbx
0x1800adf59  push    rbp
0x1800adf5a  push    rsi
0x1800adf5b  push    rdi
0x1800adf5c  push    r12
0x1800adf5e  push    r13
0x1800adf60  push    r14
0x1800adf62  push    r15
0x1800adf64  lea     rbp, [rsp-20h]
0x1800adf69  sub     rsp, 120h
0x1800adf70  mov     rax, cs:__security_cookie
0x1800adf77  xor     rax, rsp
0x1800adf7a  mov     [rbp+50h+var_40], rax
0x1800adf7e  mov     rdi, [rbp+50h+arg_30]
0x1800adf85  lea     rax, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800adf8c  mov     r13, [rbp+50h+arg_20]
0x1800adf93  mov     rsi, r9
0x1800adf96  mov     r14, [rbp+50h+arg_28]
0x1800adf9d  mov     r15, r8
0x1800adfa0  mov     [rbp+50h+var_90], rcx
0x1800adfa4  mov     r12d, edx
0x1800adfa7  lea     rcx, [rsp+150h+var_F0]; this
0x1800adfac  mov     [rbp+50h+var_B0], rax
0x1800adfb0  mov     [rbp+50h+var_A0], 8007054Fh
0x1800adfb7  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800adfbc  xor     eax, eax
0x1800adfbe  lea     rcx, [rsp+150h+hMutex]; this
0x1800adfc3  mov     [rsp+150h+hMutex], rax
0x1800adfc8  mov     [rsp+150h+var_F8], ax
0x1800adfcd  call    ?Lock@StoreLock@@QEAAJXZ; StoreLock::Lock(void)
0x1800adfd2  mov     ebx, eax
0x1800adfd4  xor     eax, eax
0x1800adfd6  test    ebx, ebx
0x1800adfd8  jns     short loc_1800AE046
0x1800adfda  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800adfe0  jnz     short loc_1800ADFE8
0x1800adfe2  call    cs:__imp_DebugBreak
0x1800adfe8  mov     r9d, ebx; int
0x1800adfeb  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800adff2  mov     r8d, 415h; char *
0x1800adff8  lea     rcx, aStatusPropagat; "Status propagated"
0x1800adfff  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ae004  mov     ecx, ebx; this
0x1800ae006  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ae00b  mov     rdi, [rsp+150h+hMutex]
0x1800ae010  mov     ebx, eax
0x1800ae012  test    rdi, rdi
0x1800ae015  jz      loc_1800AE59C
0x1800ae01b  cmp     byte ptr [rsp+150h+var_F8], 0
0x1800ae020  jz      short loc_1800AE030
0x1800ae022  mov     rcx, rdi; hMutex
0x1800ae025  call    cs:__imp_ReleaseMutex
0x1800ae02b  mov     byte ptr [rsp+150h+var_F8], 0
0x1800ae030  mov     rcx, rdi; hObject
0x1800ae033  call    CloseHandle_0
0x1800ae038  mov     [rsp+150h+hMutex], 0
0x1800ae041  jmp     loc_1800AE59C
0x1800ae046  test    rdi, rdi
0x1800ae049  jz      short loc_1800AE051
0x1800ae04b  mov     [rdi], eax
0x1800ae04d  mov     [rdi+8], rax
0x1800ae051  test    r12d, r12d
0x1800ae054  jz      short loc_1800AE0A1
0x1800ae056  mov     rbx, [rsp+150h+hMutex]
0x1800ae05b  mov     [rbp+50h+var_A8], 41Dh
0x1800ae062  test    rbx, rbx
0x1800ae065  jz      short loc_1800AE08C
0x1800ae067  cmp     byte ptr [rsp+150h+var_F8], al
0x1800ae06b  jz      short loc_1800AE07B
0x1800ae06d  mov     rcx, rbx; hMutex
0x1800ae070  call    cs:__imp_ReleaseMutex
0x1800ae076  mov     byte ptr [rsp+150h+var_F8], 0
0x1800ae07b  mov     rcx, rbx; hObject
0x1800ae07e  call    CloseHandle_0
0x1800ae083  mov     [rsp+150h+hMutex], 0
0x1800ae08c  lea     rcx, [rsp+150h+var_F0]; this
0x1800ae091  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ae096  lea     rcx, [rbp+50h+var_B0]
0x1800ae09a  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800ae09f  jmp     short loc_1800AE0EF
0x1800ae0a1  xor     r12d, r12d
0x1800ae0a4  test    r15, r15
0x1800ae0a7  jnz     short loc_1800AE0F7
0x1800ae0a9  mov     [rbp+50h+var_A8], 41Eh
0x1800ae0b0  lea     rcx, [rbp+50h+var_B0]
0x1800ae0b4  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800ae0b9  mov     rbx, [rsp+150h+hMutex]
0x1800ae0be  test    rbx, rbx
0x1800ae0c1  jz      short loc_1800AE0E5
0x1800ae0c3  cmp     byte ptr [rsp+150h+var_F8], r12b
0x1800ae0c8  jz      short loc_1800AE0D8
0x1800ae0ca  mov     rcx, rbx; hMutex
0x1800ae0cd  call    cs:__imp_ReleaseMutex
0x1800ae0d3  mov     byte ptr [rsp+150h+var_F8], r12b
0x1800ae0d8  mov     rcx, rbx; hObject
0x1800ae0db  call    CloseHandle_0
0x1800ae0e0  mov     [rsp+150h+hMutex], r12
0x1800ae0e5  lea     rcx, [rsp+150h+var_F0]; this
0x1800ae0ea  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ae0ef  mov     ebx, [rbp+50h+var_A0]
0x1800ae0f2  jmp     loc_1800AE5A6
0x1800ae0f7  test    rsi, rsi
0x1800ae0fa  jnz     short loc_1800AE105
0x1800ae0fc  mov     [rbp+50h+var_A8], 41Fh
0x1800ae103  jmp     short loc_1800AE0B0
0x1800ae105  test    r14, r14
0x1800ae108  jnz     short loc_1800AE113
0x1800ae10a  mov     [rbp+50h+var_A8], 420h
0x1800ae111  jmp     short loc_1800AE0B0
0x1800ae113  test    rdi, rdi
0x1800ae116  jnz     short loc_1800AE121
0x1800ae118  mov     [rbp+50h+var_A8], 421h
0x1800ae11f  jmp     short loc_1800AE0B0
0x1800ae121  xorps   xmm0, xmm0
0x1800ae124  mov     [rsp+150h+var_110], r12
0x1800ae129  xorps   xmm1, xmm1
0x1800ae12c  movdqa  [rbp+50h+var_60], xmm0
0x1800ae131  lea     rax, [rsp+150h+lpMem]
0x1800ae136  movdqa  [rbp+50h+var_70], xmm1
0x1800ae13b  mov     [rsp+150h+var_118], rax
0x1800ae140  lea     rdx, [rsp+150h+var_110]; struct IDefinitionAppId *
0x1800ae145  lea     rax, [rsp+150h+lpMem]
0x1800ae14a  movdqa  xmmword ptr [rbp+50h+var_50], xmm1
0x1800ae14f  mov     rcx, r15; this
0x1800ae152  mov     [rsp+150h+lpMem], rax
0x1800ae157  movups  [rbp+50h+var_80], xmm0
0x1800ae15b  mov     [rbp+50h+var_98], r12
0x1800ae15f  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionAppId@@PEAU_DEFINITION_APPID@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionAppId *,Windows::Isolation::Rtl::_DEFINITION_APPID *)
0x1800ae164  mov     ebx, eax
0x1800ae166  test    eax, eax
0x1800ae168  jns     loc_1800AE20E
0x1800ae16e  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ae174  jnz     short loc_1800AE17C
0x1800ae176  call    cs:__imp_DebugBreak
0x1800ae17c  mov     r9d, ebx; int
0x1800ae17f  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ae186  mov     r8d, 428h; char *
0x1800ae18c  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ae193  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ae198  mov     ecx, ebx; this
0x1800ae19a  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ae19f  mov     rcx, [rbp+50h+var_50+8]; lpMem
0x1800ae1a3  mov     ebx, eax
0x1800ae1a5  test    rcx, rcx
0x1800ae1a8  jz      short loc_1800AE1AF
0x1800ae1aa  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800ae1af  mov     rcx, [rsp+150h+var_110]
0x1800ae1b4  test    rcx, rcx
0x1800ae1b7  jz      short loc_1800AE1E9
0x1800ae1b9  call    RtlCloseDefinitionAppIdHandle
0x1800ae1be  mov     [rsp+150h+var_110], r12
0x1800ae1c3  jmp     short loc_1800AE1E9
0x1800ae1c5  mov     rax, [rdi+10h]
0x1800ae1c9  test    rax, rax
0x1800ae1cc  jz      short loc_1800AE1D7
0x1800ae1ce  lea     rcx, [rdi+18h]
0x1800ae1d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae1d7  call    GetProcessHeap_0
0x1800ae1dc  mov     r8, rdi; lpMem
0x1800ae1df  xor     edx, edx; dwFlags
0x1800ae1e1  mov     rcx, rax; hHeap
0x1800ae1e4  call    HeapFree_0
0x1800ae1e9  mov     rdi, [rsp+150h+lpMem]
0x1800ae1ee  lea     rcx, [rsp+150h+lpMem]
0x1800ae1f3  mov     rax, [rdi]
0x1800ae1f6  mov     [rsp+150h+lpMem], rax
0x1800ae1fb  mov     [rax+8], rcx
0x1800ae1ff  lea     rax, [rsp+150h+lpMem]
0x1800ae204  cmp     rdi, rax
0x1800ae207  jnz     short loc_1800AE1C5
0x1800ae209  jmp     loc_1800AE570
0x1800ae20e  lea     r8, [rbp+50h+var_98]; struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *
0x1800ae212  mov     rdx, rsi; struct _RTL_ALLOCATION_LIST *
0x1800ae215  lea     rcx, [rsp+150h+lpMem]; this
0x1800ae21a  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_STORE_ASSEMBLY_INSTALLATION_REFERENCE@@AEAPEBU_COMPONENT_STORE_REFERENCE_@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_STORE_ASSEMBLY_INSTALLATION_REFERENCE const *,Windows::Isolation::Rtl::_COMPONENT_STORE_REFERENCE_ const * &)
0x1800ae21f  mov     ebx, eax
0x1800ae221  test    eax, eax
0x1800ae223  jns     loc_1800AE2C9
0x1800ae229  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ae22f  jnz     short loc_1800AE237
0x1800ae231  call    cs:__imp_DebugBreak
0x1800ae237  mov     r9d, ebx; int
0x1800ae23a  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ae241  mov     r8d, 429h; char *
0x1800ae247  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ae24e  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ae253  mov     ecx, ebx; this
0x1800ae255  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ae25a  mov     rcx, [rbp+50h+var_50+8]; lpMem
0x1800ae25e  mov     ebx, eax
0x1800ae260  test    rcx, rcx
0x1800ae263  jz      short loc_1800AE26A
0x1800ae265  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800ae26a  mov     rcx, [rsp+150h+var_110]
0x1800ae26f  test    rcx, rcx
0x1800ae272  jz      short loc_1800AE2A4
0x1800ae274  call    RtlCloseDefinitionAppIdHandle
0x1800ae279  mov     [rsp+150h+var_110], r12
0x1800ae27e  jmp     short loc_1800AE2A4
0x1800ae280  mov     rax, [rdi+10h]
0x1800ae284  test    rax, rax
0x1800ae287  jz      short loc_1800AE292
0x1800ae289  lea     rcx, [rdi+18h]
0x1800ae28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae292  call    GetProcessHeap_0
0x1800ae297  mov     r8, rdi; lpMem
0x1800ae29a  xor     edx, edx; dwFlags
0x1800ae29c  mov     rcx, rax; hHeap
0x1800ae29f  call    HeapFree_0
0x1800ae2a4  mov     rdi, [rsp+150h+lpMem]
0x1800ae2a9  lea     rcx, [rsp+150h+lpMem]
0x1800ae2ae  mov     rax, [rdi]
0x1800ae2b1  mov     [rsp+150h+lpMem], rax
0x1800ae2b6  mov     [rax+8], rcx
0x1800ae2ba  lea     rax, [rsp+150h+lpMem]
0x1800ae2bf  cmp     rdi, rax
0x1800ae2c2  jnz     short loc_1800AE280
0x1800ae2c4  jmp     loc_1800AE570
0x1800ae2c9  movups  xmm0, xmmword ptr [r13+0]
0x1800ae2ce  mov     rdx, r14; struct _LUNICODE_STRING *
0x1800ae2d1  lea     rcx, [rbp+50h+var_70]; this
0x1800ae2d5  movdqu  [rbp+50h+var_80], xmm0
0x1800ae2da  call    ?Init@Rtl@Windows@@YAJAEAU_LUNICODE_STRING@@PEBG@Z; Windows::Rtl::Init(_LUNICODE_STRING &,ushort const *)
0x1800ae2df  mov     ebx, eax
0x1800ae2e1  test    eax, eax
0x1800ae2e3  jns     loc_1800AE389
0x1800ae2e9  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ae2ef  jnz     short loc_1800AE2F7
0x1800ae2f1  call    cs:__imp_DebugBreak
0x1800ae2f7  mov     r9d, ebx; int
0x1800ae2fa  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ae301  mov     r8d, 42Ch; char *
0x1800ae307  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ae30e  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ae313  mov     ecx, ebx; this
0x1800ae315  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ae31a  mov     rcx, [rbp+50h+var_50+8]; lpMem
0x1800ae31e  mov     ebx, eax
0x1800ae320  test    rcx, rcx
0x1800ae323  jz      short loc_1800AE32A
0x1800ae325  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800ae32a  mov     rcx, [rsp+150h+var_110]
0x1800ae32f  test    rcx, rcx
0x1800ae332  jz      short loc_1800AE364
0x1800ae334  call    RtlCloseDefinitionAppIdHandle
0x1800ae339  mov     [rsp+150h+var_110], r12
0x1800ae33e  jmp     short loc_1800AE364
0x1800ae340  mov     rax, [rdi+10h]
0x1800ae344  test    rax, rax
0x1800ae347  jz      short loc_1800AE352
0x1800ae349  lea     rcx, [rdi+18h]
0x1800ae34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae352  call    GetProcessHeap_0
0x1800ae357  mov     r8, rdi; lpMem
0x1800ae35a  xor     edx, edx; dwFlags
0x1800ae35c  mov     rcx, rax; hHeap
0x1800ae35f  call    HeapFree_0
0x1800ae364  mov     rdi, [rsp+150h+lpMem]
0x1800ae369  lea     rcx, [rsp+150h+lpMem]
0x1800ae36e  mov     rax, [rdi]
0x1800ae371  mov     [rsp+150h+lpMem], rax
0x1800ae376  mov     [rax+8], rcx
0x1800ae37a  lea     rax, [rsp+150h+lpMem]
0x1800ae37f  cmp     rdi, rax
0x1800ae382  jnz     short loc_1800AE340
0x1800ae384  jmp     loc_1800AE570
0x1800ae389  mov     rdx, [rbp+50h+var_90]
0x1800ae38d  lea     rax, [rbp+50h+var_80]
0x1800ae391  mov     r9, [rbp+50h+var_98]
0x1800ae395  mov     r8, [rsp+150h+var_110]
0x1800ae39a  mov     [rsp+150h+var_128], rax
0x1800ae39f  mov     rdx, [rdx+10h]
0x1800ae3a3  call    RtlFetchComponentStoreDeploymentProperties
0x1800ae3a8  mov     ebx, eax
0x1800ae3aa  test    eax, eax
0x1800ae3ac  jns     loc_1800AE452
0x1800ae3b2  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ae3b8  jnz     short loc_1800AE3C0
0x1800ae3ba  call    cs:__imp_DebugBreak
0x1800ae3c0  mov     r9d, ebx; int
0x1800ae3c3  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ae3ca  mov     r8d, 435h; char *
0x1800ae3d0  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ae3d7  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ae3dc  mov     ecx, ebx; this
0x1800ae3de  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ae3e3  mov     rcx, [rbp+50h+var_50+8]; lpMem
0x1800ae3e7  mov     ebx, eax
0x1800ae3e9  test    rcx, rcx
0x1800ae3ec  jz      short loc_1800AE3F3
0x1800ae3ee  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800ae3f3  mov     rcx, [rsp+150h+var_110]
0x1800ae3f8  test    rcx, rcx
0x1800ae3fb  jz      short loc_1800AE42D
0x1800ae3fd  call    RtlCloseDefinitionAppIdHandle
0x1800ae402  mov     [rsp+150h+var_110], r12
0x1800ae407  jmp     short loc_1800AE42D
0x1800ae409  mov     rax, [rdi+10h]
0x1800ae40d  test    rax, rax
0x1800ae410  jz      short loc_1800AE41B
  ... truncated ...
```
