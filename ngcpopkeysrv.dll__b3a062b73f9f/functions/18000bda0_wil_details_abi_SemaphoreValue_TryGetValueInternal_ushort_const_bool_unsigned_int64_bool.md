# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000bda0`
- end: `0x18000bf6e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `462`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000bd1c`

## callees

- `0x180004de0`
- `0x180007968`
- `0x180009228`
- `0x18000b0dc`
- `0x18000b0fc`
- `0x18000b7c8`
- `0x18000b854`
- `0x18000bda0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000be09`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000beac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000be09`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000beac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be19`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v15; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v16[0] = v5;
  if ( v5 )
  {
    v14 = 0;
    v13 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v14);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v13);
      goto LABEL_12;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v15 = v9;
    if ( !v9 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
      goto LABEL_12;
    }
    v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v13);
    LastError = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v13);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
      goto LABEL_12;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    *a3 = v14 | (unsigned __int64)((__int64)v13 << 31);
LABEL_11:
    LastError = 0;
    goto LABEL_12;
  }
  if ( GetLastError() == 2 )
    goto LABEL_11;
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_12:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  return LastError;
}

```

## disassembly

```asm
0x18000bda0  mov     [rsp-8+arg_8], rbx
0x18000bda5  push    rbp
0x18000bda6  push    rdi
0x18000bda7  push    r14
0x18000bda9  lea     rbp, [rsp-160h]
0x18000bdb1  sub     rsp, 260h
0x18000bdb8  mov     rax, cs:__security_cookie
0x18000bdbf  xor     rax, rsp
0x18000bdc2  mov     [rbp+170h+var_20], rax
0x18000bdc9  mov     rdi, r8
0x18000bdcc  mov     qword ptr [r8], 0
0x18000bdd3  mov     r8, rcx; unsigned __int16 *
0x18000bdd6  mov     r14d, 104h
0x18000bddc  mov     edx, r14d; unsigned __int64
0x18000bddf  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000bde4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bde9  lea     r8, aP0; "_p0"
0x18000bdf0  mov     edx, r14d; unsigned __int64
0x18000bdf3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000bdf8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bdfd  lea     r8, [rsp+270h+Name]; lpName
0x18000be02  xor     edx, edx; bInheritHandle
0x18000be04  mov     ecx, 1F0003h; dwDesiredAccess
0x18000be09  call    cs:__imp_OpenSemaphoreW
0x18000be0f  mov     [rsp+270h+var_240], rax
0x18000be14  test    rax, rax
0x18000be17  jnz     short loc_18000BE48
0x18000be19  call    cs:__imp_GetLastError
0x18000be1f  cmp     eax, 2
0x18000be22  jnz     short loc_18000BE29
0x18000be24  jmp     loc_18000BF3D
0x18000be29  mov     rcx, [rbp+178h]; this
0x18000be30  lea     r8, aWil; "wil"
0x18000be37  mov     edx, 0D0h; void *
0x18000be3c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000be41  mov     ebx, eax
0x18000be43  jmp     loc_18000BF3F
0x18000be48  mov     [rsp+270h+var_24C], 0
0x18000be50  mov     [rsp+270h+var_250], 0; int
0x18000be58  lea     rdx, [rsp+270h+var_24C]; int *
0x18000be5d  mov     rcx, rax; hHandle
0x18000be60  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000be65  mov     ebx, eax
0x18000be67  test    eax, eax
0x18000be69  jns     short loc_18000BE8C
0x18000be6b  mov     rcx, [rbp+178h]; this
0x18000be72  mov     r9d, eax; char *
0x18000be75  lea     r8, aWil; "wil"
0x18000be7c  mov     edx, 0D6h; void *
0x18000be81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be86  nop
0x18000be87  jmp     loc_18000BF3F
0x18000be8c  lea     r8, asc_18002A688; "h"
0x18000be93  mov     rdx, r14; unsigned __int64
0x18000be96  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000be9b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bea0  lea     r8, [rsp+270h+Name]; lpName
0x18000bea5  xor     edx, edx; bInheritHandle
0x18000bea7  mov     ecx, 1F0003h; dwDesiredAccess
0x18000beac  call    cs:__imp_OpenSemaphoreW
0x18000beb2  mov     [rsp+270h+var_248], rax
0x18000beb7  test    rax, rax
0x18000beba  jnz     short loc_18000BEE3
0x18000bebc  mov     rcx, [rbp+178h]; this
0x18000bec3  lea     r8, aWil; "wil"
0x18000beca  mov     edx, 0DCh; void *
0x18000becf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bed4  mov     ebx, eax
0x18000bed6  lea     rcx, [rsp+270h+var_248]
0x18000bedb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bee0  nop
0x18000bee1  jmp     short loc_18000BF3F
0x18000bee3  lea     rdx, [rsp+270h+var_250]; int *
0x18000bee8  mov     rcx, rax; hHandle
0x18000beeb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bef0  mov     ebx, eax
0x18000bef2  test    eax, eax
0x18000bef4  jns     short loc_18000BF1F
0x18000bef6  mov     rcx, [rbp+178h]; this
0x18000befd  mov     r9d, eax; char *
0x18000bf00  lea     r8, aWil; "wil"
0x18000bf07  mov     edx, 0DEh; void *
0x18000bf0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bf11  nop
0x18000bf12  lea     rcx, [rsp+270h+var_248]
0x18000bf17  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bf1c  nop
0x18000bf1d  jmp     short loc_18000BF3F
0x18000bf1f  lea     rcx, [rsp+270h+var_248]
0x18000bf24  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bf29  movsxd  rcx, [rsp+270h+var_250]
0x18000bf2e  shl     rcx, 1Fh
0x18000bf32  movsxd  rax, [rsp+270h+var_24C]
0x18000bf37  or      rcx, rax
0x18000bf3a  mov     [rdi], rcx
0x18000bf3d  xor     ebx, ebx
0x18000bf3f  lea     rcx, [rsp+270h+var_240]
0x18000bf44  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bf49  mov     eax, ebx
0x18000bf4b  mov     rcx, [rbp+170h+var_20]
0x18000bf52  xor     rcx, rsp; StackCookie
0x18000bf55  call    __security_check_cookie
0x18000bf5a  mov     rbx, [rsp+270h+arg_8]
0x18000bf62  add     rsp, 260h
0x18000bf69  pop     r14
0x18000bf6b  pop     rdi
0x18000bf6c  pop     rbp
0x18000bf6d  retn
```
