# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005cc8`
- end: `0x180005e7b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `435`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180003a38`

## callees

- `0x180002100`
- `0x1800038ec`
- `0x18000460c`
- `0x180005504`
- `0x180005524`
- `0x1800059fc`
- `0x180005a48`
- `0x180005cc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005d27`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005dc5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005d27`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005dc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d37`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
  StringCchCopyW(Name, a2, a1);
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
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
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
0x180005cc8  mov     [rsp-8+arg_8], rbx
0x180005ccd  mov     [rsp-8+arg_18], rdi
0x180005cd2  push    rbp
0x180005cd3  lea     rbp, [rsp-160h]
0x180005cdb  sub     rsp, 260h
0x180005ce2  mov     rax, cs:__security_cookie
0x180005ce9  xor     rax, rsp
0x180005cec  mov     [rbp+160h+var_10], rax
0x180005cf3  mov     rdi, r8
0x180005cf6  mov     qword ptr [r8], 0
0x180005cfd  mov     r8, rcx; unsigned __int16 *
0x180005d00  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180005d05  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005d0a  lea     r8, aP0; "_p0"
0x180005d11  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180005d16  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005d1b  lea     r8, [rsp+260h+Name]; lpName
0x180005d20  xor     edx, edx; bInheritHandle
0x180005d22  mov     ecx, 1F0003h; dwDesiredAccess
0x180005d27  call    cs:__imp_OpenSemaphoreW
0x180005d2d  mov     [rsp+260h+var_230], rax
0x180005d32  test    rax, rax
0x180005d35  jnz     short loc_180005D65
0x180005d37  call    cs:__imp_GetLastError
0x180005d3d  cmp     eax, 2
0x180005d40  jz      loc_180005E49
0x180005d46  mov     rcx, [rbp+168h]; this
0x180005d4d  lea     r8, aWil; "wil"
0x180005d54  mov     edx, 0D0h; void *
0x180005d59  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005d5e  mov     ebx, eax
0x180005d60  jmp     loc_180005E4B
0x180005d65  lea     rdx, [rsp+260h+var_23C]; int *
0x180005d6a  mov     [rsp+260h+var_23C], 0
0x180005d72  mov     rcx, rax; hHandle
0x180005d75  mov     [rsp+260h+var_240], 0; int
0x180005d7d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005d82  mov     ebx, eax
0x180005d84  test    eax, eax
0x180005d86  jns     short loc_180005DA8
0x180005d88  mov     rcx, [rbp+168h]; this
0x180005d8f  lea     r8, aWil; "wil"
0x180005d96  mov     r9d, eax; char *
0x180005d99  mov     edx, 0D6h; void *
0x180005d9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005da3  jmp     loc_180005E4B
0x180005da8  lea     r8, asc_18000BD90; "h"
0x180005daf  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180005db4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005db9  lea     r8, [rsp+260h+Name]; lpName
0x180005dbe  xor     edx, edx; bInheritHandle
0x180005dc0  mov     ecx, 1F0003h; dwDesiredAccess
0x180005dc5  call    cs:__imp_OpenSemaphoreW
0x180005dcb  mov     [rsp+260h+var_238], rax
0x180005dd0  test    rax, rax
0x180005dd3  jnz     short loc_180005DFB
0x180005dd5  mov     rcx, [rbp+168h]; this
0x180005ddc  lea     r8, aWil; "wil"
0x180005de3  mov     edx, 0DCh; void *
0x180005de8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005ded  mov     ebx, eax
0x180005def  lea     rcx, [rsp+260h+var_238]
0x180005df4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005df9  jmp     short loc_180005E4B
0x180005dfb  lea     rdx, [rsp+260h+var_240]; int *
0x180005e00  mov     rcx, rax; hHandle
0x180005e03  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005e08  mov     ebx, eax
0x180005e0a  test    eax, eax
0x180005e0c  jns     short loc_180005E2B
0x180005e0e  mov     rcx, [rbp+168h]; this
0x180005e15  lea     r8, aWil; "wil"
0x180005e1c  mov     r9d, eax; char *
0x180005e1f  mov     edx, 0DEh; void *
0x180005e24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e29  jmp     short loc_180005DEF
0x180005e2b  lea     rcx, [rsp+260h+var_238]
0x180005e30  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005e35  movsxd  rcx, [rsp+260h+var_240]
0x180005e3a  movsxd  rax, [rsp+260h+var_23C]
0x180005e3f  shl     rcx, 1Fh
0x180005e43  or      rcx, rax
0x180005e46  mov     [rdi], rcx
0x180005e49  xor     ebx, ebx
0x180005e4b  lea     rcx, [rsp+260h+var_230]
0x180005e50  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005e55  mov     eax, ebx
0x180005e57  mov     rcx, [rbp+160h+var_10]
0x180005e5e  xor     rcx, rsp; StackCookie
0x180005e61  call    __security_check_cookie
0x180005e66  lea     r11, [rsp+260h+var_s0]
0x180005e6e  mov     rbx, [r11+18h]
0x180005e72  mov     rdi, [r11+28h]
0x180005e76  mov     rsp, r11
0x180005e79  pop     rbp
0x180005e7a  retn
```
