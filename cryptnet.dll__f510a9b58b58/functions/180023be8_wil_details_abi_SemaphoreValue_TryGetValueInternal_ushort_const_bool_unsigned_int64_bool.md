# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180023be8`
- end: `0x180023d8a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180023b74`

## callees

- `0x180003640`
- `0x180011e40`
- `0x18001afa4`
- `0x180020ebc`
- `0x1800220d4`
- `0x180023588`
- `0x180023be8`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c61`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180023c51`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180023ce3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180023c51`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180023ce3`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wil::details *v5; // rax
  void *v6; // rdx
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  int v11; // r8d
  wil::details *v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  void *v15; // rdx
  int v16; // eax
  void *v17; // rdx
  int v18; // r8d
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v22; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v23; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 260, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v23 = v5;
  if ( v5 )
  {
    v21 = 0;
    v20 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v21);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v11, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, 260, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v22 = v12;
    if ( v12 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v20);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v22,
          v17);
        *a3 = v21 | (unsigned __int64)((__int64)v20 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v18, (const char *)(unsigned int)v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v22,
      v15);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v23,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x180023be8  mov     [rsp-8+arg_8], rbx
0x180023bed  push    rbp
0x180023bee  push    rdi
0x180023bef  push    r14
0x180023bf1  lea     rbp, [rsp-160h]
0x180023bf9  sub     rsp, 260h
0x180023c00  mov     rax, cs:__security_cookie
0x180023c07  xor     rax, rsp
0x180023c0a  mov     [rbp+170h+var_20], rax
0x180023c11  mov     rdi, r8
0x180023c14  mov     qword ptr [r8], 0
0x180023c1b  mov     r8, rcx; unsigned __int16 *
0x180023c1e  mov     r14d, 104h
0x180023c24  mov     edx, r14d; unsigned __int64
0x180023c27  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023c2c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023c31  lea     r8, aP0; "_p0"
0x180023c38  mov     edx, r14d; unsigned __int64
0x180023c3b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023c40  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023c45  lea     r8, [rsp+270h+Name]; lpName
0x180023c4a  xor     edx, edx; bInheritHandle
0x180023c4c  mov     ecx, 1F0003h; dwDesiredAccess
0x180023c51  call    cs:__imp_OpenSemaphoreW
0x180023c57  mov     [rsp+270h+var_240], rax
0x180023c5c  test    rax, rax
0x180023c5f  jnz     short loc_180023C87
0x180023c61  call    cs:__imp_GetLastError
0x180023c67  cmp     eax, 2
0x180023c6a  jz      loc_180023D59
0x180023c70  mov     rcx, [rbp+178h]; this
0x180023c77  lea     edx, [r14-34h]; void *
0x180023c7b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023c80  mov     ebx, eax
0x180023c82  jmp     loc_180023D5B
0x180023c87  lea     rdx, [rsp+270h+var_24C]; int *
0x180023c8c  mov     [rsp+270h+var_24C], 0
0x180023c94  mov     rcx, rax; hHandle
0x180023c97  mov     [rsp+270h+var_250], 0; int
0x180023c9f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180023ca4  mov     ebx, eax
0x180023ca6  test    eax, eax
0x180023ca8  jns     short loc_180023CC3
0x180023caa  mov     rcx, [rbp+178h]; this
0x180023cb1  mov     r9d, eax; char *
0x180023cb4  mov     edx, 0D6h; void *
0x180023cb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023cbe  jmp     loc_180023D5B
0x180023cc3  lea     r8, asc_18002AC78; "h"
0x180023cca  mov     rdx, r14; unsigned __int64
0x180023ccd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023cd2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023cd7  lea     r8, [rsp+270h+Name]; lpName
0x180023cdc  xor     edx, edx; bInheritHandle
0x180023cde  mov     ecx, 1F0003h; dwDesiredAccess
0x180023ce3  call    cs:__imp_OpenSemaphoreW
0x180023ce9  mov     [rsp+270h+var_248], rax
0x180023cee  test    rax, rax
0x180023cf1  jnz     short loc_180023D12
0x180023cf3  mov     rcx, [rbp+178h]; this
0x180023cfa  mov     edx, 0DCh; void *
0x180023cff  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023d04  mov     ebx, eax
0x180023d06  lea     rcx, [rsp+270h+var_248]
0x180023d0b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023d10  jmp     short loc_180023D5B
0x180023d12  lea     rdx, [rsp+270h+var_250]; int *
0x180023d17  mov     rcx, rax; hHandle
0x180023d1a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180023d1f  mov     ebx, eax
0x180023d21  test    eax, eax
0x180023d23  jns     short loc_180023D3B
0x180023d25  mov     rcx, [rbp+178h]; this
0x180023d2c  mov     r9d, eax; char *
0x180023d2f  mov     edx, 0DEh; void *
0x180023d34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023d39  jmp     short loc_180023D06
0x180023d3b  lea     rcx, [rsp+270h+var_248]
0x180023d40  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023d45  movsxd  rcx, [rsp+270h+var_250]
0x180023d4a  movsxd  rax, [rsp+270h+var_24C]
0x180023d4f  shl     rcx, 1Fh
0x180023d53  or      rcx, rax
0x180023d56  mov     [rdi], rcx
0x180023d59  xor     ebx, ebx
0x180023d5b  lea     rcx, [rsp+270h+var_240]
0x180023d60  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023d65  mov     eax, ebx
0x180023d67  mov     rcx, [rbp+170h+var_20]
0x180023d6e  xor     rcx, rsp; StackCookie
0x180023d71  call    __security_check_cookie
0x180023d76  mov     rbx, [rsp+270h+arg_8]
0x180023d7e  add     rsp, 260h
0x180023d85  pop     r14
0x180023d87  pop     rdi
0x180023d88  pop     rbp
0x180023d89  retn
```
