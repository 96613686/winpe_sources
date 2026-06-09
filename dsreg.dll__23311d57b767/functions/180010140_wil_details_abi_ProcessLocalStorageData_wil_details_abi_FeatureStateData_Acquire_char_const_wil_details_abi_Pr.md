# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180010140`
- end: `0x180010339`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `505`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004df64`

## callees

- `0x180010140`
- `0x180010340`
- `0x18001035c`
- `0x1800103e8`
- `0x18001e958`
- `0x180030074`
- `0x18003012c`
- `0x180031a4c`
- `0x1800336a0`
- `0x180044300`
- `0x18004d634`
- `0x18004e560`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001017b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001017b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800101b7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800101b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800101df`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800101df`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  unsigned int LastErrorFailHr; // ebx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rdi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // esi
  _DWORD *v16; // rcx
  int v17; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v21 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_14:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    return LastErrorFailHr;
  }
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v23[0] = v12;
  v22 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v22, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v19);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v20);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
    LastErrorFailHr = v15;
    goto LABEL_14;
  }
  v16 = (_DWORD *)(4 * v22);
  if ( 4 * v22 )
  {
    *a2 = v16;
    ++*v16;
  }
  else
  {
    v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    LastErrorFailHr = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"wil",
        (const char *)(unsigned int)v17,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
      goto LABEL_14;
    }
    v6 = v21;
  }
  if ( v12 )
    wil::details::ReleaseMutex(v12, v14);
  if ( v6 )
    wil::details::CloseHandle(v6, v14);
  return 0;
}

```

## disassembly

```asm
0x180010140  mov     [rsp-8+arg_10], rbx
0x180010145  mov     [rsp-8+arg_18], rsi
0x18001014a  push    rbp
0x18001014b  push    rdi
0x18001014c  push    r14
0x18001014e  lea     rbp, [rsp-170h]
0x180010156  sub     rsp, 270h
0x18001015d  mov     rax, cs:__security_cookie
0x180010164  xor     rax, rsp
0x180010167  mov     [rbp+180h+var_20], rax
0x18001016e  mov     r14, rdx
0x180010171  mov     qword ptr [rdx], 0
0x180010178  mov     rbx, rcx
0x18001017b  call    cs:__imp_GetCurrentProcessId
0x180010181  mov     [rsp+280h+var_258], rbx
0x180010186  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001018d  mov     r9d, eax
0x180010190  mov     [rsp+280h+var_260], 130h; int
0x180010198  mov     edx, 104h; unsigned __int64
0x18001019d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800101a2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800101a7  mov     r9d, 1F0001h; dwDesiredAccess
0x1800101ad  lea     rdx, [rsp+280h+Name]; lpName
0x1800101b2  xor     r8d, r8d; dwFlags
0x1800101b5  xor     ecx, ecx; lpMutexAttributes
0x1800101b7  call    cs:__imp_CreateMutexExW
0x1800101bd  mov     [rsp+280h+var_250], rax
0x1800101c2  mov     rbx, rax
0x1800101c5  test    rax, rax
0x1800101c8  jnz     short loc_1800101D6
0x1800101ca  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800101cf  mov     ebx, eax
0x1800101d1  jmp     loc_1800102E3
0x1800101d6  xor     r8d, r8d; bAlertable
0x1800101d9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800101dc  mov     rcx, rbx; hHandle
0x1800101df  call    cs:__imp_WaitForSingleObjectEx
0x1800101e5  cmp     eax, 102h
0x1800101ea  jz      short loc_180010205
0x1800101ec  test    eax, 0FFFFFF7Fh
0x1800101f1  jz      short loc_180010200
0x1800101f3  mov     rcx, [rbp+188h]; this
0x1800101fa  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180010200  mov     rdi, rbx
0x180010203  jmp     short loc_180010207
0x180010205  xor     edi, edi
0x180010207  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18001020c  mov     [rsp+280h+var_240], rdi
0x180010211  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010216  mov     [rsp+280h+var_248], 0
0x18001021f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180010224  mov     esi, eax
0x180010226  test    eax, eax
0x180010228  jns     short loc_180010289
0x18001022a  mov     rcx, [rbp+188h]; this
0x180010231  lea     r8, aWil; "wil"
0x180010238  mov     r9d, eax; char *
0x18001023b  mov     edx, 66h ; 'f'; void *
0x180010240  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010245  mov     rcx, [rbp+188h]; this
0x18001024c  lea     r8, aWil; "wil"
0x180010253  mov     r9d, esi; char *
0x180010256  mov     edx, 6Fh ; 'o'; void *
0x18001025b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010260  mov     rcx, [rbp+188h]; this
0x180010267  lea     r8, aWil; "wil"
0x18001026e  mov     r9d, esi; char *
0x180010271  mov     edx, 12Eh; void *
0x180010276  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001027b  lea     rcx, [rsp+280h+var_240]
0x180010280  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010285  mov     ebx, esi
0x180010287  jmp     short loc_1800102E3
0x180010289  mov     rax, [rsp+280h+var_248]
0x18001028e  lea     rcx, ds:0[rax*4]
0x180010296  test    rcx, rcx
0x180010299  jz      short loc_1800102A6
0x18001029b  mov     [r14], rcx
0x18001029e  mov     eax, [rcx]
0x1800102a0  inc     eax
0x1800102a2  mov     [rcx], eax
0x1800102a4  jmp     short loc_1800102F6
0x1800102a6  mov     r8, r14
0x1800102a9  lea     rdx, [rsp+280h+var_250]
0x1800102ae  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800102b3  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800102b8  mov     ebx, eax
0x1800102ba  test    eax, eax
0x1800102bc  jns     short loc_1800102F1
0x1800102be  mov     rcx, [rbp+188h]; this
0x1800102c5  lea     r8, aWil; "wil"
0x1800102cc  mov     r9d, eax; char *
0x1800102cf  mov     edx, 137h; void *
0x1800102d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800102d9  lea     rcx, [rsp+280h+var_240]
0x1800102de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800102e3  lea     rcx, [rsp+280h+var_250]
0x1800102e8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800102ed  mov     eax, ebx
0x1800102ef  jmp     short loc_180010312
0x1800102f1  mov     rbx, [rsp+280h+var_250]
0x1800102f6  test    rdi, rdi
0x1800102f9  jz      short loc_180010303
0x1800102fb  mov     rcx, rdi; this
0x1800102fe  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180010303  test    rbx, rbx
0x180010306  jz      short loc_180010310
0x180010308  mov     rcx, rbx; this
0x18001030b  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180010310  xor     eax, eax
0x180010312  mov     rcx, [rbp+180h+var_20]
0x180010319  xor     rcx, rsp; StackCookie
0x18001031c  call    __security_check_cookie
0x180010321  lea     r11, [rsp+280h+var_10]
0x180010329  mov     rbx, [r11+30h]
0x18001032d  mov     rsi, [r11+38h]
0x180010331  mov     rsp, r11
0x180010334  pop     r14
0x180010336  pop     rdi
0x180010337  pop     rbp
0x180010338  retn
```
