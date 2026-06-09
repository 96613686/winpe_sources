# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180014970`
- end: `0x180014b07`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `407`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800148fc`

## callees

- `0x1800109dc`
- `0x180012060`
- `0x180013c84`
- `0x180013ca4`
- `0x1800143d8`
- `0x180014424`
- `0x180014970`
- `0x18001ed20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149df`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800149cf`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180014a5f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800149cf`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180014a5f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
0x180014970  mov     [rsp-8+arg_8], rbx
0x180014975  mov     [rsp-8+arg_18], rdi
0x18001497a  push    rbp
0x18001497b  lea     rbp, [rsp-160h]
0x180014983  sub     rsp, 260h
0x18001498a  mov     rax, cs:__security_cookie
0x180014991  xor     rax, rsp
0x180014994  mov     [rbp+160h+var_10], rax
0x18001499b  mov     rdi, r8
0x18001499e  mov     qword ptr [r8], 0
0x1800149a5  mov     r8, rcx; unsigned __int16 *
0x1800149a8  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800149ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800149b2  lea     r8, aP0; "_p0"
0x1800149b9  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800149be  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800149c3  lea     r8, [rsp+260h+Name]; lpName
0x1800149c8  xor     edx, edx; bInheritHandle
0x1800149ca  mov     ecx, 1F0003h; dwDesiredAccess
0x1800149cf  call    cs:__imp_OpenSemaphoreW
0x1800149d5  mov     [rsp+260h+var_230], rax
0x1800149da  test    rax, rax
0x1800149dd  jnz     short loc_180014A06
0x1800149df  call    cs:__imp_GetLastError
0x1800149e5  cmp     eax, 2
0x1800149e8  jz      loc_180014AD5
0x1800149ee  mov     rcx, [rbp+168h]; this
0x1800149f5  mov     edx, 0D0h; void *
0x1800149fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800149ff  mov     ebx, eax
0x180014a01  jmp     loc_180014AD7
0x180014a06  lea     rdx, [rsp+260h+var_23C]; int *
0x180014a0b  mov     [rsp+260h+var_23C], 0
0x180014a13  mov     rcx, rax; hHandle
0x180014a16  mov     [rsp+260h+var_240], 0; int
0x180014a1e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180014a23  mov     ebx, eax
0x180014a25  test    eax, eax
0x180014a27  jns     short loc_180014A42
0x180014a29  mov     rcx, [rbp+168h]; this
0x180014a30  mov     r9d, eax; char *
0x180014a33  mov     edx, 0D6h; void *
0x180014a38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a3d  jmp     loc_180014AD7
0x180014a42  lea     r8, asc_1800221B8; "h"
0x180014a49  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180014a4e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014a53  lea     r8, [rsp+260h+Name]; lpName
0x180014a58  xor     edx, edx; bInheritHandle
0x180014a5a  mov     ecx, 1F0003h; dwDesiredAccess
0x180014a5f  call    cs:__imp_OpenSemaphoreW
0x180014a65  mov     [rsp+260h+var_238], rax
0x180014a6a  test    rax, rax
0x180014a6d  jnz     short loc_180014A8E
0x180014a6f  mov     rcx, [rbp+168h]; this
0x180014a76  mov     edx, 0DCh; void *
0x180014a7b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014a80  mov     ebx, eax
0x180014a82  lea     rcx, [rsp+260h+var_238]
0x180014a87  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180014a8c  jmp     short loc_180014AD7
0x180014a8e  lea     rdx, [rsp+260h+var_240]; int *
0x180014a93  mov     rcx, rax; hHandle
0x180014a96  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180014a9b  mov     ebx, eax
0x180014a9d  test    eax, eax
0x180014a9f  jns     short loc_180014AB7
0x180014aa1  mov     rcx, [rbp+168h]; this
0x180014aa8  mov     r9d, eax; char *
0x180014aab  mov     edx, 0DEh; void *
0x180014ab0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014ab5  jmp     short loc_180014A82
0x180014ab7  lea     rcx, [rsp+260h+var_238]
0x180014abc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180014ac1  movsxd  rcx, [rsp+260h+var_240]
0x180014ac6  movsxd  rax, [rsp+260h+var_23C]
0x180014acb  shl     rcx, 1Fh
0x180014acf  or      rcx, rax
0x180014ad2  mov     [rdi], rcx
0x180014ad5  xor     ebx, ebx
0x180014ad7  lea     rcx, [rsp+260h+var_230]
0x180014adc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180014ae1  mov     eax, ebx
0x180014ae3  mov     rcx, [rbp+160h+var_10]
0x180014aea  xor     rcx, rsp; StackCookie
0x180014aed  call    __security_check_cookie
0x180014af2  lea     r11, [rsp+260h+var_s0]
0x180014afa  mov     rbx, [r11+18h]
0x180014afe  mov     rdi, [r11+28h]
0x180014b02  mov     rsp, r11
0x180014b05  pop     rbp
0x180014b06  retn
```
