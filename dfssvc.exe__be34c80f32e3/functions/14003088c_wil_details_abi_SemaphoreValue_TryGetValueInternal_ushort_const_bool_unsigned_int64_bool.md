# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14003088c`
- end: `0x140030a4d`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `449`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14003081c`

## callees

- `0x14001e4bc`
- `0x14001e548`
- `0x140027a34`
- `0x14002b458`
- `0x14002f024`
- `0x14002f044`
- `0x14003088c`
- `0x14005ce70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003090e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003090e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400308f8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140030990`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400308f8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140030990`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned int LastError; // ebx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  int v11; // edi
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  unsigned int v16; // r8d
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v20; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v21[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  LastError = 0;
  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21[0] = v6;
  if ( v6 )
  {
    v19 = 0;
    v18 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v19);
    v11 = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, 0x104u, L"h");
      v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v20 = v12;
      if ( !v12 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, v13, v14);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
        goto LABEL_12;
      }
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v18);
      v11 = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
        *a3 = v19 | (unsigned __int64)((__int64)v18 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, v16, (const char *)(unsigned int)v15, v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, v10, (const char *)(unsigned int)ValueFromSemaphore, v18);
    }
    LastError = v11;
  }
  else if ( GetLastError() != 2 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, v7, v8);
  }
LABEL_12:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
  return LastError;
}

```

## disassembly

```asm
0x14003088c  mov     [rsp-8+arg_0], rbx
0x140030891  mov     [rsp-8+arg_8], rsi
0x140030896  push    rbp
0x140030897  push    rdi
0x140030898  push    r14
0x14003089a  lea     rbp, [rsp-160h]
0x1400308a2  sub     rsp, 260h
0x1400308a9  mov     rax, cs:__security_cookie
0x1400308b0  xor     rax, rsp
0x1400308b3  mov     [rbp+170h+var_20], rax
0x1400308ba  mov     rsi, r8
0x1400308bd  xor     ebx, ebx
0x1400308bf  mov     [r8], rbx
0x1400308c2  mov     r14d, 104h
0x1400308c8  mov     r8, rcx; unsigned __int16 *
0x1400308cb  mov     edx, r14d; unsigned __int64
0x1400308ce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400308d3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400308d8  lea     r8, aP0; "_p0"
0x1400308df  mov     edx, r14d; unsigned __int64
0x1400308e2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400308e7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400308ec  lea     r8, [rsp+270h+Name]; lpName
0x1400308f1  xor     edx, edx; bInheritHandle
0x1400308f3  mov     ecx, 1F0003h; dwDesiredAccess
0x1400308f8  call    cs:__imp_OpenSemaphoreW
0x1400308ff  nop     dword ptr [rax+rax+00h]
0x140030904  mov     [rsp+270h+var_240], rax
0x140030909  test    rax, rax
0x14003090c  jnz     short loc_14003093A
0x14003090e  call    cs:__imp_GetLastError
0x140030915  nop     dword ptr [rax+rax+00h]
0x14003091a  cmp     eax, 2
0x14003091d  jz      loc_140030A19
0x140030923  mov     rcx, [rbp+178h]; this
0x14003092a  lea     edx, [r14-37h]; void *
0x14003092e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140030933  mov     ebx, eax
0x140030935  jmp     loc_140030A19
0x14003093a  lea     rdx, [rsp+270h+var_24C]; int *
0x14003093f  mov     [rsp+270h+var_24C], ebx
0x140030943  mov     rcx, rax; hHandle
0x140030946  mov     [rsp+270h+var_250], ebx; int
0x14003094a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14003094f  mov     edi, eax
0x140030951  test    eax, eax
0x140030953  jns     short loc_140030970
0x140030955  mov     rcx, [rbp+178h]; this
0x14003095c  mov     r9d, eax; char *
0x14003095f  mov     edx, 0D3h; void *
0x140030964  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140030969  mov     ebx, edi
0x14003096b  jmp     loc_140030A19
0x140030970  lea     r8, asc_140064A28; "h"
0x140030977  mov     rdx, r14; unsigned __int64
0x14003097a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14003097f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140030984  lea     r8, [rsp+270h+Name]; lpName
0x140030989  xor     edx, edx; bInheritHandle
0x14003098b  mov     ecx, 1F0003h; dwDesiredAccess
0x140030990  call    cs:__imp_OpenSemaphoreW
0x140030997  nop     dword ptr [rax+rax+00h]
0x14003099c  mov     [rsp+270h+var_248], rax
0x1400309a1  test    rax, rax
0x1400309a4  jnz     short loc_1400309C5
0x1400309a6  mov     rcx, [rbp+178h]; this
0x1400309ad  mov     edx, 0D9h; void *
0x1400309b2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400309b7  lea     rcx, [rsp+270h+var_248]
0x1400309bc  mov     ebx, eax
0x1400309be  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400309c3  jmp     short loc_140030A19
0x1400309c5  lea     rdx, [rsp+270h+var_250]; int *
0x1400309ca  mov     rcx, rax; hHandle
0x1400309cd  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400309d2  mov     edi, eax
0x1400309d4  test    eax, eax
0x1400309d6  jns     short loc_1400309FB
0x1400309d8  mov     rcx, [rbp+178h]; this
0x1400309df  mov     r9d, eax; char *
0x1400309e2  mov     edx, 0DBh; void *
0x1400309e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400309ec  lea     rcx, [rsp+270h+var_248]
0x1400309f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400309f6  jmp     loc_140030969
0x1400309fb  lea     rcx, [rsp+270h+var_248]
0x140030a00  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140030a05  movsxd  rdx, [rsp+270h+var_250]
0x140030a0a  movsxd  rcx, [rsp+270h+var_24C]
0x140030a0f  shl     rdx, 1Fh
0x140030a13  or      rdx, rcx
0x140030a16  mov     [rsi], rdx
0x140030a19  lea     rcx, [rsp+270h+var_240]
0x140030a1e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140030a23  mov     eax, ebx
0x140030a25  mov     rcx, [rbp+170h+var_20]
0x140030a2c  xor     rcx, rsp; StackCookie
0x140030a2f  call    __security_check_cookie
0x140030a34  lea     r11, [rsp+270h+var_10]
0x140030a3c  mov     rbx, [r11+20h]
0x140030a40  mov     rsi, [r11+28h]
0x140030a44  mov     rsp, r11
0x140030a47  pop     r14
0x140030a49  pop     rdi
0x140030a4a  pop     rbp
0x140030a4b  retn
```
