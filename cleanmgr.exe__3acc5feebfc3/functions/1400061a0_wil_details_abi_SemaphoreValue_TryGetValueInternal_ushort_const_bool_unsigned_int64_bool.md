# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1400061a0`
- end: `0x14000633c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(size_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000612c`

## callees

- `0x1400029a0`
- `0x1400040ec`
- `0x140004e64`
- `0x1400059a4`
- `0x1400059c4`
- `0x140005f24`
- `0x140005fa0`
- `0x1400061a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006214`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006204`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006294`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006204`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006294`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        size_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  int v13; // r8d
  wil::details *v14; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  void *v17; // rdx
  int v18; // eax
  void *v19; // rdx
  int v20; // r8d
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v24; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v25; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v25 = v6;
  if ( v6 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, v12, L"h");
    v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v24 = v14;
    if ( v14 )
    {
      v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v22);
      LastError = v18;
      if ( v18 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v24,
          v19);
        *a3 = v23 | (unsigned __int64)((__int64)v22 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v20, (const char *)(unsigned int)v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v15, v16);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v24,
      v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v8, v9);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v25,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x1400061a0  mov     [rsp-8+arg_8], rbx
0x1400061a5  mov     [rsp-8+arg_18], rdi
0x1400061aa  push    rbp
0x1400061ab  lea     rbp, [rsp-160h]
0x1400061b3  sub     rsp, 260h
0x1400061ba  mov     rax, cs:__security_cookie
0x1400061c1  xor     rax, rsp
0x1400061c4  mov     [rbp+160h+var_10], rax
0x1400061cb  mov     rdi, r8
0x1400061ce  mov     qword ptr [r8], 0
0x1400061d5  mov     r8, rcx; unsigned __int16 *
0x1400061d8  mov     edx, 104h; unsigned __int64
0x1400061dd  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1400061e2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400061e7  lea     r8, aP0; "_p0"
0x1400061ee  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1400061f3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400061f8  lea     r8, [rsp+260h+Name]; lpName
0x1400061fd  xor     edx, edx; bInheritHandle
0x1400061ff  mov     ecx, 1F0003h; dwDesiredAccess
0x140006204  call    cs:__imp_OpenSemaphoreW
0x14000620a  mov     [rsp+260h+var_230], rax
0x14000620f  test    rax, rax
0x140006212  jnz     short loc_14000623B
0x140006214  call    cs:__imp_GetLastError
0x14000621a  cmp     eax, 2
0x14000621d  jz      loc_14000630A
0x140006223  mov     rcx, [rbp+168h]; this
0x14000622a  mov     edx, 0D0h; void *
0x14000622f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006234  mov     ebx, eax
0x140006236  jmp     loc_14000630C
0x14000623b  lea     rdx, [rsp+260h+var_23C]; int *
0x140006240  mov     [rsp+260h+var_23C], 0
0x140006248  mov     rcx, rax; hHandle
0x14000624b  mov     [rsp+260h+var_240], 0; int
0x140006253  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140006258  mov     ebx, eax
0x14000625a  test    eax, eax
0x14000625c  jns     short loc_140006277
0x14000625e  mov     rcx, [rbp+168h]; this
0x140006265  mov     r9d, eax; char *
0x140006268  mov     edx, 0D6h; void *
0x14000626d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006272  jmp     loc_14000630C
0x140006277  lea     r8, asc_140019FF0; "h"
0x14000627e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x140006283  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006288  lea     r8, [rsp+260h+Name]; lpName
0x14000628d  xor     edx, edx; bInheritHandle
0x14000628f  mov     ecx, 1F0003h; dwDesiredAccess
0x140006294  call    cs:__imp_OpenSemaphoreW
0x14000629a  mov     [rsp+260h+var_238], rax
0x14000629f  test    rax, rax
0x1400062a2  jnz     short loc_1400062C3
0x1400062a4  mov     rcx, [rbp+168h]; this
0x1400062ab  mov     edx, 0DCh; void *
0x1400062b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400062b5  mov     ebx, eax
0x1400062b7  lea     rcx, [rsp+260h+var_238]
0x1400062bc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400062c1  jmp     short loc_14000630C
0x1400062c3  lea     rdx, [rsp+260h+var_240]; int *
0x1400062c8  mov     rcx, rax; hHandle
0x1400062cb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400062d0  mov     ebx, eax
0x1400062d2  test    eax, eax
0x1400062d4  jns     short loc_1400062EC
0x1400062d6  mov     rcx, [rbp+168h]; this
0x1400062dd  mov     r9d, eax; char *
0x1400062e0  mov     edx, 0DEh; void *
0x1400062e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400062ea  jmp     short loc_1400062B7
0x1400062ec  lea     rcx, [rsp+260h+var_238]
0x1400062f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400062f6  movsxd  rcx, [rsp+260h+var_240]
0x1400062fb  movsxd  rax, [rsp+260h+var_23C]
0x140006300  shl     rcx, 1Fh
0x140006304  or      rcx, rax
0x140006307  mov     [rdi], rcx
0x14000630a  xor     ebx, ebx
0x14000630c  lea     rcx, [rsp+260h+var_230]
0x140006311  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006316  mov     eax, ebx
0x140006318  mov     rcx, [rbp+160h+var_10]
0x14000631f  xor     rcx, rsp; StackCookie
0x140006322  call    __security_check_cookie
0x140006327  lea     r11, [rsp+260h+var_s0]
0x14000632f  mov     rbx, [r11+18h]
0x140006333  mov     rdi, [r11+28h]
0x140006337  mov     rsp, r11
0x14000633a  pop     rbp
0x14000633b  retn
```
