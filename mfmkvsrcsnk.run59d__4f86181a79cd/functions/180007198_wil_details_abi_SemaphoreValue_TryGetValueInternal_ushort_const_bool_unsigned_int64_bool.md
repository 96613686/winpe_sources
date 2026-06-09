# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007198`
- end: `0x180007347`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `431`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800048cc`

## callees

- `0x180002400`
- `0x1800046bc`
- `0x180005900`
- `0x180006814`
- `0x180006834`
- `0x180006d84`
- `0x180006e70`
- `0x180007198`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800071fc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007298`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800071fc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007212`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v19);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x180007198  mov     [rsp-8+arg_8], rbx
0x18000719d  mov     [rsp-8+arg_18], rdi
0x1800071a2  push    rbp
0x1800071a3  lea     rbp, [rsp-160h]
0x1800071ab  sub     rsp, 260h
0x1800071b2  mov     rax, cs:__security_cookie
0x1800071b9  xor     rax, rsp
0x1800071bc  mov     [rbp+160h+var_10], rax
0x1800071c3  mov     rdi, r8
0x1800071c6  mov     qword ptr [r8], 0
0x1800071cd  mov     r8, rcx; unsigned __int16 *
0x1800071d0  mov     edx, 104h; unsigned __int64
0x1800071d5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800071da  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800071df  lea     r8, aP0; "_p0"
0x1800071e6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800071eb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800071f0  lea     r8, [rsp+260h+Name]; lpName
0x1800071f5  xor     edx, edx; bInheritHandle
0x1800071f7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800071fc  call    cs:__imp_OpenSemaphoreW
0x180007203  nop     dword ptr [rax+rax+00h]
0x180007208  mov     [rsp+260h+var_230], rax
0x18000720d  test    rax, rax
0x180007210  jnz     short loc_18000723F
0x180007212  call    cs:__imp_GetLastError
0x180007219  nop     dword ptr [rax+rax+00h]
0x18000721e  cmp     eax, 2
0x180007221  jz      loc_180007314
0x180007227  mov     rcx, [rbp+168h]; this
0x18000722e  mov     edx, 0D0h; void *
0x180007233  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007238  mov     ebx, eax
0x18000723a  jmp     loc_180007316
0x18000723f  lea     rdx, [rsp+260h+var_23C]; int *
0x180007244  mov     [rsp+260h+var_23C], 0
0x18000724c  mov     rcx, rax; hHandle
0x18000724f  mov     [rsp+260h+var_240], 0; int
0x180007257  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000725c  mov     ebx, eax
0x18000725e  test    eax, eax
0x180007260  jns     short loc_18000727B
0x180007262  mov     rcx, [rbp+168h]; this
0x180007269  mov     r9d, eax; char *
0x18000726c  mov     edx, 0D6h; void *
0x180007271  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007276  jmp     loc_180007316
0x18000727b  lea     r8, asc_1800BBDC8; "h"
0x180007282  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180007287  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000728c  lea     r8, [rsp+260h+Name]; lpName
0x180007291  xor     edx, edx; bInheritHandle
0x180007293  mov     ecx, 1F0003h; dwDesiredAccess
0x180007298  call    cs:__imp_OpenSemaphoreW
0x18000729f  nop     dword ptr [rax+rax+00h]
0x1800072a4  mov     [rsp+260h+var_238], rax
0x1800072a9  test    rax, rax
0x1800072ac  jnz     short loc_1800072CD
0x1800072ae  mov     rcx, [rbp+168h]; this
0x1800072b5  mov     edx, 0DCh; void *
0x1800072ba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800072bf  mov     ebx, eax
0x1800072c1  lea     rcx, [rsp+260h+var_238]
0x1800072c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800072cb  jmp     short loc_180007316
0x1800072cd  lea     rdx, [rsp+260h+var_240]; int *
0x1800072d2  mov     rcx, rax; hHandle
0x1800072d5  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800072da  mov     ebx, eax
0x1800072dc  test    eax, eax
0x1800072de  jns     short loc_1800072F6
0x1800072e0  mov     rcx, [rbp+168h]; this
0x1800072e7  mov     r9d, eax; char *
0x1800072ea  mov     edx, 0DEh; void *
0x1800072ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800072f4  jmp     short loc_1800072C1
0x1800072f6  lea     rcx, [rsp+260h+var_238]
0x1800072fb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007300  movsxd  rcx, [rsp+260h+var_240]
0x180007305  movsxd  rax, [rsp+260h+var_23C]
0x18000730a  shl     rcx, 1Fh
0x18000730e  or      rcx, rax
0x180007311  mov     [rdi], rcx
0x180007314  xor     ebx, ebx
0x180007316  lea     rcx, [rsp+260h+var_230]
0x18000731b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007320  mov     eax, ebx
0x180007322  mov     rcx, [rbp+160h+var_10]
0x180007329  xor     rcx, rsp; StackCookie
0x18000732c  call    __security_check_cookie
0x180007331  lea     r11, [rsp+260h+var_s0]
0x180007339  mov     rbx, [r11+18h]
0x18000733d  mov     rdi, [r11+28h]
0x180007341  mov     rsp, r11
0x180007344  pop     rbp
0x180007345  retn
```
