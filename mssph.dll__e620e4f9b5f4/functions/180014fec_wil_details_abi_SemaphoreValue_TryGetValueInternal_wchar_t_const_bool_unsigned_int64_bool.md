# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180014fec`
- end: `0x1800151a4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180014f68`

## callees

- `0x18000e9f4`
- `0x18000f1bc`
- `0x18000fcd0`
- `0x1800121a8`
- `0x180013390`
- `0x18001469c`
- `0x180014c70`
- `0x180014fec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015050`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800150ee`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015050`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800150ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015060`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  wil::details *v12; // rax
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v20; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v6;
  if ( v6 )
  {
    v19 = 0;
    v18 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v19);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v18);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v20 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v18);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v20,
          v16);
        *a3 = v19 | (unsigned __int64)((__int64)v18 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v20,
      v14);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v21,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x180014fec  mov     [rsp-8+arg_8], rbx
0x180014ff1  mov     [rsp-8+arg_18], rdi
0x180014ff6  push    rbp
0x180014ff7  lea     rbp, [rsp-160h]
0x180014fff  sub     rsp, 260h
0x180015006  mov     rax, cs:__security_cookie
0x18001500d  xor     rax, rsp
0x180015010  mov     [rbp+160h+var_10], rax
0x180015017  mov     rdi, r8
0x18001501a  mov     qword ptr [r8], 0
0x180015021  mov     r8, rcx; wchar_t *
0x180015024  mov     edx, 104h; unsigned __int64
0x180015029  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18001502e  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180015033  lea     r8, aP0; "_p0"
0x18001503a  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18001503f  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180015044  lea     r8, [rsp+260h+Name]; lpName
0x180015049  xor     edx, edx; bInheritHandle
0x18001504b  mov     ecx, 1F0003h; dwDesiredAccess
0x180015050  call    cs:__imp_OpenSemaphoreW
0x180015056  mov     [rsp+260h+var_230], rax
0x18001505b  test    rax, rax
0x18001505e  jnz     short loc_18001508E
0x180015060  call    cs:__imp_GetLastError
0x180015066  cmp     eax, 2
0x180015069  jz      loc_180015172
0x18001506f  mov     rcx, [rbp+168h]; this
0x180015076  lea     r8, aWil; "wil"
0x18001507d  mov     edx, 0D0h; void *
0x180015082  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015087  mov     ebx, eax
0x180015089  jmp     loc_180015174
0x18001508e  lea     rdx, [rsp+260h+var_23C]; int *
0x180015093  mov     [rsp+260h+var_23C], 0
0x18001509b  mov     rcx, rax; hHandle
0x18001509e  mov     [rsp+260h+var_240], 0; int
0x1800150a6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800150ab  mov     ebx, eax
0x1800150ad  test    eax, eax
0x1800150af  jns     short loc_1800150D1
0x1800150b1  mov     rcx, [rbp+168h]; this
0x1800150b8  lea     r8, aWil; "wil"
0x1800150bf  mov     r9d, eax; char *
0x1800150c2  mov     edx, 0D6h; void *
0x1800150c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800150cc  jmp     loc_180015174
0x1800150d1  lea     r8, asc_18002B860; "h"
0x1800150d8  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800150dd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800150e2  lea     r8, [rsp+260h+Name]; lpName
0x1800150e7  xor     edx, edx; bInheritHandle
0x1800150e9  mov     ecx, 1F0003h; dwDesiredAccess
0x1800150ee  call    cs:__imp_OpenSemaphoreW
0x1800150f4  mov     [rsp+260h+var_238], rax
0x1800150f9  test    rax, rax
0x1800150fc  jnz     short loc_180015124
0x1800150fe  mov     rcx, [rbp+168h]; this
0x180015105  lea     r8, aWil; "wil"
0x18001510c  mov     edx, 0DCh; void *
0x180015111  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015116  mov     ebx, eax
0x180015118  lea     rcx, [rsp+260h+var_238]
0x18001511d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015122  jmp     short loc_180015174
0x180015124  lea     rdx, [rsp+260h+var_240]; int *
0x180015129  mov     rcx, rax; hHandle
0x18001512c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180015131  mov     ebx, eax
0x180015133  test    eax, eax
0x180015135  jns     short loc_180015154
0x180015137  mov     rcx, [rbp+168h]; this
0x18001513e  lea     r8, aWil; "wil"
0x180015145  mov     r9d, eax; char *
0x180015148  mov     edx, 0DEh; void *
0x18001514d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015152  jmp     short loc_180015118
0x180015154  lea     rcx, [rsp+260h+var_238]
0x180015159  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001515e  movsxd  rcx, [rsp+260h+var_240]
0x180015163  movsxd  rax, [rsp+260h+var_23C]
0x180015168  shl     rcx, 1Fh
0x18001516c  or      rcx, rax
0x18001516f  mov     [rdi], rcx
0x180015172  xor     ebx, ebx
0x180015174  lea     rcx, [rsp+260h+var_230]
0x180015179  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001517e  mov     eax, ebx
0x180015180  mov     rcx, [rbp+160h+var_10]
0x180015187  xor     rcx, rsp; StackCookie
0x18001518a  call    __security_check_cookie
0x18001518f  lea     r11, [rsp+260h+var_s0]
0x180015197  mov     rbx, [r11+18h]
0x18001519b  mov     rdi, [r11+28h]
0x18001519f  mov     rsp, r11
0x1800151a2  pop     rbp
0x1800151a3  retn
```
