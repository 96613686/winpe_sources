# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009630`
- end: `0x1800097da`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800095b8`

## callees

- `0x180002af0`
- `0x180005024`
- `0x180007e5c`
- `0x180008e14`
- `0x180008e34`
- `0x180009448`
- `0x180009498`
- `0x180009630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096a5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000968f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000972b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000968f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000972b`

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
0x180009630  mov     [rsp-8+arg_8], rbx
0x180009635  mov     [rsp-8+arg_18], rdi
0x18000963a  push    rbp
0x18000963b  lea     rbp, [rsp-160h]
0x180009643  sub     rsp, 260h
0x18000964a  mov     rax, cs:__security_cookie
0x180009651  xor     rax, rsp
0x180009654  mov     [rbp+160h+var_10], rax
0x18000965b  mov     rdi, r8
0x18000965e  mov     qword ptr [r8], 0
0x180009665  mov     r8, rcx; wchar_t *
0x180009668  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000966d  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009672  lea     r8, aP0; "_p0"
0x180009679  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000967e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009683  lea     r8, [rsp+260h+Name]; lpName
0x180009688  xor     edx, edx; bInheritHandle
0x18000968a  mov     ecx, 1F0003h; dwDesiredAccess
0x18000968f  call    cs:__imp_OpenSemaphoreW
0x180009696  nop     dword ptr [rax+rax+00h]
0x18000969b  mov     [rsp+260h+var_230], rax
0x1800096a0  test    rax, rax
0x1800096a3  jnz     short loc_1800096D2
0x1800096a5  call    cs:__imp_GetLastError
0x1800096ac  nop     dword ptr [rax+rax+00h]
0x1800096b1  cmp     eax, 2
0x1800096b4  jz      loc_1800097A7
0x1800096ba  mov     rcx, [rbp+168h]; this
0x1800096c1  mov     edx, 0D0h; void *
0x1800096c6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800096cb  mov     ebx, eax
0x1800096cd  jmp     loc_1800097A9
0x1800096d2  lea     rdx, [rsp+260h+var_23C]; int *
0x1800096d7  mov     [rsp+260h+var_23C], 0
0x1800096df  mov     rcx, rax; hHandle
0x1800096e2  mov     [rsp+260h+var_240], 0; int
0x1800096ea  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800096ef  mov     ebx, eax
0x1800096f1  test    eax, eax
0x1800096f3  jns     short loc_18000970E
0x1800096f5  mov     rcx, [rbp+168h]; this
0x1800096fc  mov     r9d, eax; char *
0x1800096ff  mov     edx, 0D6h; void *
0x180009704  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009709  jmp     loc_1800097A9
0x18000970e  lea     r8, asc_18003CDD8; "h"
0x180009715  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000971a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000971f  lea     r8, [rsp+260h+Name]; lpName
0x180009724  xor     edx, edx; bInheritHandle
0x180009726  mov     ecx, 1F0003h; dwDesiredAccess
0x18000972b  call    cs:__imp_OpenSemaphoreW
0x180009732  nop     dword ptr [rax+rax+00h]
0x180009737  mov     [rsp+260h+var_238], rax
0x18000973c  test    rax, rax
0x18000973f  jnz     short loc_180009760
0x180009741  mov     rcx, [rbp+168h]; this
0x180009748  mov     edx, 0DCh; void *
0x18000974d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009752  mov     ebx, eax
0x180009754  lea     rcx, [rsp+260h+var_238]
0x180009759  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000975e  jmp     short loc_1800097A9
0x180009760  lea     rdx, [rsp+260h+var_240]; int *
0x180009765  mov     rcx, rax; hHandle
0x180009768  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000976d  mov     ebx, eax
0x18000976f  test    eax, eax
0x180009771  jns     short loc_180009789
0x180009773  mov     rcx, [rbp+168h]; this
0x18000977a  mov     r9d, eax; char *
0x18000977d  mov     edx, 0DEh; void *
0x180009782  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009787  jmp     short loc_180009754
0x180009789  lea     rcx, [rsp+260h+var_238]
0x18000978e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009793  movsxd  rcx, [rsp+260h+var_240]
0x180009798  movsxd  rax, [rsp+260h+var_23C]
0x18000979d  shl     rcx, 1Fh
0x1800097a1  or      rcx, rax
0x1800097a4  mov     [rdi], rcx
0x1800097a7  xor     ebx, ebx
0x1800097a9  lea     rcx, [rsp+260h+var_230]
0x1800097ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800097b3  mov     eax, ebx
0x1800097b5  mov     rcx, [rbp+160h+var_10]
0x1800097bc  xor     rcx, rsp; StackCookie
0x1800097bf  call    __security_check_cookie
0x1800097c4  lea     r11, [rsp+260h+var_s0]
0x1800097cc  mov     rbx, [r11+18h]
0x1800097d0  mov     rdi, [r11+28h]
0x1800097d4  mov     rsp, r11
0x1800097d7  pop     rbp
0x1800097d8  retn
```
