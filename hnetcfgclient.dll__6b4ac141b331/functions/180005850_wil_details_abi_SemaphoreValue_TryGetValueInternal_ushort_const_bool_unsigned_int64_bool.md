# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005850`
- end: `0x1800059ec`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180003860`

## callees

- `0x180003738`
- `0x18000443c`
- `0x180005124`
- `0x180005144`
- `0x18000561c`
- `0x180005698`
- `0x180005850`
- `0x18002d200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800058b4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005944`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800058b4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058c4`

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
0x180005850  mov     [rsp-8+arg_8], rbx
0x180005855  mov     [rsp-8+arg_18], rdi
0x18000585a  push    rbp
0x18000585b  lea     rbp, [rsp-160h]
0x180005863  sub     rsp, 260h
0x18000586a  mov     rax, cs:__security_cookie
0x180005871  xor     rax, rsp
0x180005874  mov     [rbp+160h+var_10], rax
0x18000587b  mov     rdi, r8
0x18000587e  mov     qword ptr [r8], 0
0x180005885  mov     r8, rcx; unsigned __int16 *
0x180005888  mov     edx, 104h; unsigned __int64
0x18000588d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180005892  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005897  lea     r8, aP0; "_p0"
0x18000589e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800058a3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800058a8  lea     r8, [rsp+260h+Name]; lpName
0x1800058ad  xor     edx, edx; bInheritHandle
0x1800058af  mov     ecx, 1F0003h; dwDesiredAccess
0x1800058b4  call    cs:__imp_OpenSemaphoreW
0x1800058ba  mov     [rsp+260h+var_230], rax
0x1800058bf  test    rax, rax
0x1800058c2  jnz     short loc_1800058EB
0x1800058c4  call    cs:__imp_GetLastError
0x1800058ca  cmp     eax, 2
0x1800058cd  jz      loc_1800059BA
0x1800058d3  mov     rcx, [rbp+168h]; this
0x1800058da  mov     edx, 0D0h; void *
0x1800058df  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800058e4  mov     ebx, eax
0x1800058e6  jmp     loc_1800059BC
0x1800058eb  lea     rdx, [rsp+260h+var_23C]; int *
0x1800058f0  mov     [rsp+260h+var_23C], 0
0x1800058f8  mov     rcx, rax; hHandle
0x1800058fb  mov     [rsp+260h+var_240], 0; int
0x180005903  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005908  mov     ebx, eax
0x18000590a  test    eax, eax
0x18000590c  jns     short loc_180005927
0x18000590e  mov     rcx, [rbp+168h]; this
0x180005915  mov     r9d, eax; char *
0x180005918  mov     edx, 0D6h; void *
0x18000591d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005922  jmp     loc_1800059BC
0x180005927  lea     r8, asc_180033D88; "h"
0x18000592e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180005933  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005938  lea     r8, [rsp+260h+Name]; lpName
0x18000593d  xor     edx, edx; bInheritHandle
0x18000593f  mov     ecx, 1F0003h; dwDesiredAccess
0x180005944  call    cs:__imp_OpenSemaphoreW
0x18000594a  mov     [rsp+260h+var_238], rax
0x18000594f  test    rax, rax
0x180005952  jnz     short loc_180005973
0x180005954  mov     rcx, [rbp+168h]; this
0x18000595b  mov     edx, 0DCh; void *
0x180005960  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005965  mov     ebx, eax
0x180005967  lea     rcx, [rsp+260h+var_238]
0x18000596c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005971  jmp     short loc_1800059BC
0x180005973  lea     rdx, [rsp+260h+var_240]; int *
0x180005978  mov     rcx, rax; hHandle
0x18000597b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005980  mov     ebx, eax
0x180005982  test    eax, eax
0x180005984  jns     short loc_18000599C
0x180005986  mov     rcx, [rbp+168h]; this
0x18000598d  mov     r9d, eax; char *
0x180005990  mov     edx, 0DEh; void *
0x180005995  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000599a  jmp     short loc_180005967
0x18000599c  lea     rcx, [rsp+260h+var_238]
0x1800059a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800059a6  movsxd  rcx, [rsp+260h+var_240]
0x1800059ab  movsxd  rax, [rsp+260h+var_23C]
0x1800059b0  shl     rcx, 1Fh
0x1800059b4  or      rcx, rax
0x1800059b7  mov     [rdi], rcx
0x1800059ba  xor     ebx, ebx
0x1800059bc  lea     rcx, [rsp+260h+var_230]
0x1800059c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800059c6  mov     eax, ebx
0x1800059c8  mov     rcx, [rbp+160h+var_10]
0x1800059cf  xor     rcx, rsp; StackCookie
0x1800059d2  call    __security_check_cookie
0x1800059d7  lea     r11, [rsp+260h+var_s0]
0x1800059df  mov     rbx, [r11+18h]
0x1800059e3  mov     rdi, [r11+28h]
0x1800059e7  mov     rsp, r11
0x1800059ea  pop     rbp
0x1800059eb  retn
```
