# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000926c`
- end: `0x180009403`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `407`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800091f8`

## callees

- `0x180002a90`
- `0x180004ee4`
- `0x180007b78`
- `0x180008a84`
- `0x180008aa4`
- `0x180009094`
- `0x1800090e0`
- `0x18000926c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092db`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800092cb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000935b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800092cb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000935b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        unsigned __int64 a2,
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
  StringCchCopyW(Name, a2, a1);
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
0x18000926c  mov     [rsp-8+arg_8], rbx
0x180009271  mov     [rsp-8+arg_18], rdi
0x180009276  push    rbp
0x180009277  lea     rbp, [rsp-160h]
0x18000927f  sub     rsp, 260h
0x180009286  mov     rax, cs:__security_cookie
0x18000928d  xor     rax, rsp
0x180009290  mov     [rbp+160h+var_10], rax
0x180009297  mov     rdi, r8
0x18000929a  mov     qword ptr [r8], 0
0x1800092a1  mov     r8, rcx; wchar_t *
0x1800092a4  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800092a9  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800092ae  lea     r8, aP0; "_p0"
0x1800092b5  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800092ba  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800092bf  lea     r8, [rsp+260h+Name]; lpName
0x1800092c4  xor     edx, edx; bInheritHandle
0x1800092c6  mov     ecx, 1F0003h; dwDesiredAccess
0x1800092cb  call    cs:__imp_OpenSemaphoreW
0x1800092d1  mov     [rsp+260h+var_230], rax
0x1800092d6  test    rax, rax
0x1800092d9  jnz     short loc_180009302
0x1800092db  call    cs:__imp_GetLastError
0x1800092e1  cmp     eax, 2
0x1800092e4  jz      loc_1800093D1
0x1800092ea  mov     rcx, [rbp+168h]; this
0x1800092f1  mov     edx, 0D0h; void *
0x1800092f6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800092fb  mov     ebx, eax
0x1800092fd  jmp     loc_1800093D3
0x180009302  lea     rdx, [rsp+260h+var_23C]; int *
0x180009307  mov     [rsp+260h+var_23C], 0
0x18000930f  mov     rcx, rax; hHandle
0x180009312  mov     [rsp+260h+var_240], 0; int
0x18000931a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000931f  mov     ebx, eax
0x180009321  test    eax, eax
0x180009323  jns     short loc_18000933E
0x180009325  mov     rcx, [rbp+168h]; this
0x18000932c  mov     r9d, eax; char *
0x18000932f  mov     edx, 0D6h; void *
0x180009334  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009339  jmp     loc_1800093D3
0x18000933e  lea     r8, asc_18003BDD8; "h"
0x180009345  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000934a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000934f  lea     r8, [rsp+260h+Name]; lpName
0x180009354  xor     edx, edx; bInheritHandle
0x180009356  mov     ecx, 1F0003h; dwDesiredAccess
0x18000935b  call    cs:__imp_OpenSemaphoreW
0x180009361  mov     [rsp+260h+var_238], rax
0x180009366  test    rax, rax
0x180009369  jnz     short loc_18000938A
0x18000936b  mov     rcx, [rbp+168h]; this
0x180009372  mov     edx, 0DCh; void *
0x180009377  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000937c  mov     ebx, eax
0x18000937e  lea     rcx, [rsp+260h+var_238]
0x180009383  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009388  jmp     short loc_1800093D3
0x18000938a  lea     rdx, [rsp+260h+var_240]; int *
0x18000938f  mov     rcx, rax; hHandle
0x180009392  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009397  mov     ebx, eax
0x180009399  test    eax, eax
0x18000939b  jns     short loc_1800093B3
0x18000939d  mov     rcx, [rbp+168h]; this
0x1800093a4  mov     r9d, eax; char *
0x1800093a7  mov     edx, 0DEh; void *
0x1800093ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800093b1  jmp     short loc_18000937E
0x1800093b3  lea     rcx, [rsp+260h+var_238]
0x1800093b8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800093bd  movsxd  rcx, [rsp+260h+var_240]
0x1800093c2  movsxd  rax, [rsp+260h+var_23C]
0x1800093c7  shl     rcx, 1Fh
0x1800093cb  or      rcx, rax
0x1800093ce  mov     [rdi], rcx
0x1800093d1  xor     ebx, ebx
0x1800093d3  lea     rcx, [rsp+260h+var_230]
0x1800093d8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800093dd  mov     eax, ebx
0x1800093df  mov     rcx, [rbp+160h+var_10]
0x1800093e6  xor     rcx, rsp; StackCookie
0x1800093e9  call    __security_check_cookie
0x1800093ee  lea     r11, [rsp+260h+var_s0]
0x1800093f6  mov     rbx, [r11+18h]
0x1800093fa  mov     rdi, [r11+28h]
0x1800093fe  mov     rsp, r11
0x180009401  pop     rbp
0x180009402  retn
```
