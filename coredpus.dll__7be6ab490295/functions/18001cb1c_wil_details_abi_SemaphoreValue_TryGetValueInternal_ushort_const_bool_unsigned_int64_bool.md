# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001cb1c`
- end: `0x18001cce7`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `459`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001ca98`

## callees

- `0x180011d9c`
- `0x180014330`
- `0x1800163d8`
- `0x18001887c`
- `0x18001a0d4`
- `0x18001b9bc`
- `0x18001c698`
- `0x18001cb1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001cb80`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001cc2a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001cb80`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001cc2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb96`

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
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v6;
  if ( v6 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(Name, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x18001cb1c  mov     [rsp-8+arg_8], rbx
0x18001cb21  mov     [rsp-8+arg_18], rdi
0x18001cb26  push    rbp
0x18001cb27  lea     rbp, [rsp-160h]
0x18001cb2f  sub     rsp, 260h
0x18001cb36  mov     rax, cs:__security_cookie
0x18001cb3d  xor     rax, rsp
0x18001cb40  mov     [rbp+160h+var_10], rax
0x18001cb47  mov     rdi, r8
0x18001cb4a  mov     qword ptr [r8], 0
0x18001cb51  mov     r8, rcx; unsigned __int16 *
0x18001cb54  mov     edx, 104h; unsigned __int64
0x18001cb59  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001cb5e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001cb63  lea     r8, aP0; "_p0"
0x18001cb6a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001cb6f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001cb74  lea     r8, [rsp+260h+Name]; lpName
0x18001cb79  xor     edx, edx; bInheritHandle
0x18001cb7b  mov     ecx, 1F0003h; dwDesiredAccess
0x18001cb80  call    cs:__imp_OpenSemaphoreW
0x18001cb87  nop     dword ptr [rax+rax+00h]
0x18001cb8c  mov     [rsp+260h+var_230], rax
0x18001cb91  test    rax, rax
0x18001cb94  jnz     short loc_18001CBCA
0x18001cb96  call    cs:__imp_GetLastError
0x18001cb9d  nop     dword ptr [rax+rax+00h]
0x18001cba2  cmp     eax, 2
0x18001cba5  jz      loc_18001CCB4
0x18001cbab  mov     rcx, [rbp+168h]; this
0x18001cbb2  lea     r8, aWil; "wil"
0x18001cbb9  mov     edx, 0D0h; void *
0x18001cbbe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001cbc3  mov     ebx, eax
0x18001cbc5  jmp     loc_18001CCB6
0x18001cbca  lea     rdx, [rsp+260h+var_23C]; int *
0x18001cbcf  mov     [rsp+260h+var_23C], 0
0x18001cbd7  mov     rcx, rax; hHandle
0x18001cbda  mov     [rsp+260h+var_240], 0; int
0x18001cbe2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001cbe7  mov     ebx, eax
0x18001cbe9  test    eax, eax
0x18001cbeb  jns     short loc_18001CC0D
0x18001cbed  mov     rcx, [rbp+168h]; this
0x18001cbf4  lea     r8, aWil; "wil"
0x18001cbfb  mov     r9d, eax; char *
0x18001cbfe  mov     edx, 0D6h; void *
0x18001cc03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cc08  jmp     loc_18001CCB6
0x18001cc0d  lea     r8, asc_180034100; "h"
0x18001cc14  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001cc19  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001cc1e  lea     r8, [rsp+260h+Name]; lpName
0x18001cc23  xor     edx, edx; bInheritHandle
0x18001cc25  mov     ecx, 1F0003h; dwDesiredAccess
0x18001cc2a  call    cs:__imp_OpenSemaphoreW
0x18001cc31  nop     dword ptr [rax+rax+00h]
0x18001cc36  mov     [rsp+260h+var_238], rax
0x18001cc3b  test    rax, rax
0x18001cc3e  jnz     short loc_18001CC66
0x18001cc40  mov     rcx, [rbp+168h]; this
0x18001cc47  lea     r8, aWil; "wil"
0x18001cc4e  mov     edx, 0DCh; void *
0x18001cc53  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001cc58  mov     ebx, eax
0x18001cc5a  lea     rcx, [rsp+260h+var_238]
0x18001cc5f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001cc64  jmp     short loc_18001CCB6
0x18001cc66  lea     rdx, [rsp+260h+var_240]; int *
0x18001cc6b  mov     rcx, rax; hHandle
0x18001cc6e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001cc73  mov     ebx, eax
0x18001cc75  test    eax, eax
0x18001cc77  jns     short loc_18001CC96
0x18001cc79  mov     rcx, [rbp+168h]; this
0x18001cc80  lea     r8, aWil; "wil"
0x18001cc87  mov     r9d, eax; char *
0x18001cc8a  mov     edx, 0DEh; void *
0x18001cc8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cc94  jmp     short loc_18001CC5A
0x18001cc96  lea     rcx, [rsp+260h+var_238]
0x18001cc9b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001cca0  movsxd  rcx, [rsp+260h+var_240]
0x18001cca5  movsxd  rax, [rsp+260h+var_23C]
0x18001ccaa  shl     rcx, 1Fh
0x18001ccae  or      rcx, rax
0x18001ccb1  mov     [rdi], rcx
0x18001ccb4  xor     ebx, ebx
0x18001ccb6  lea     rcx, [rsp+260h+var_230]
0x18001ccbb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ccc0  mov     eax, ebx
0x18001ccc2  mov     rcx, [rbp+160h+var_10]
0x18001ccc9  xor     rcx, rsp; StackCookie
0x18001cccc  call    __security_check_cookie
0x18001ccd1  lea     r11, [rsp+260h+var_s0]
0x18001ccd9  mov     rbx, [r11+18h]
0x18001ccdd  mov     rdi, [r11+28h]
0x18001cce1  mov     rsp, r11
0x18001cce4  pop     rbp
0x18001cce5  retn
```
