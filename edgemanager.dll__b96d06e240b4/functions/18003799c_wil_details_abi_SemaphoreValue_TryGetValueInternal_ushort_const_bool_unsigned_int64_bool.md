# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003799c`
- end: `0x180037b54`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180037918`

## callees

- `0x180009db8`
- `0x18000a518`
- `0x1800154cc`
- `0x18002b530`
- `0x180036c18`
- `0x180037308`
- `0x1800376e4`
- `0x18003799c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180037a00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180037a9e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180037a00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180037a9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a10`

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
0x18003799c  mov     [rsp-8+arg_8], rbx
0x1800379a1  mov     [rsp-8+arg_18], rdi
0x1800379a6  push    rbp
0x1800379a7  lea     rbp, [rsp-160h]
0x1800379af  sub     rsp, 260h
0x1800379b6  mov     rax, cs:__security_cookie
0x1800379bd  xor     rax, rsp
0x1800379c0  mov     [rbp+160h+var_10], rax
0x1800379c7  mov     rdi, r8
0x1800379ca  mov     qword ptr [r8], 0
0x1800379d1  mov     r8, rcx; unsigned __int16 *
0x1800379d4  mov     edx, 104h; unsigned __int64
0x1800379d9  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800379de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800379e3  lea     r8, aP0; "_p0"
0x1800379ea  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800379ef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800379f4  lea     r8, [rsp+260h+Name]; lpName
0x1800379f9  xor     edx, edx; bInheritHandle
0x1800379fb  mov     ecx, 1F0003h; dwDesiredAccess
0x180037a00  call    cs:__imp_OpenSemaphoreW
0x180037a06  mov     [rsp+260h+var_230], rax
0x180037a0b  test    rax, rax
0x180037a0e  jnz     short loc_180037A3E
0x180037a10  call    cs:__imp_GetLastError
0x180037a16  cmp     eax, 2
0x180037a19  jz      loc_180037B22
0x180037a1f  mov     rcx, [rbp+168h]; this
0x180037a26  lea     r8, aWil; "wil"
0x180037a2d  mov     edx, 0D0h; void *
0x180037a32  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180037a37  mov     ebx, eax
0x180037a39  jmp     loc_180037B24
0x180037a3e  lea     rdx, [rsp+260h+var_23C]; int *
0x180037a43  mov     [rsp+260h+var_23C], 0
0x180037a4b  mov     rcx, rax; hHandle
0x180037a4e  mov     [rsp+260h+var_240], 0; int
0x180037a56  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180037a5b  mov     ebx, eax
0x180037a5d  test    eax, eax
0x180037a5f  jns     short loc_180037A81
0x180037a61  mov     rcx, [rbp+168h]; this
0x180037a68  lea     r8, aWil; "wil"
0x180037a6f  mov     r9d, eax; char *
0x180037a72  mov     edx, 0D6h; void *
0x180037a77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037a7c  jmp     loc_180037B24
0x180037a81  lea     r8, asc_1800A0870; "h"
0x180037a88  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180037a8d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037a92  lea     r8, [rsp+260h+Name]; lpName
0x180037a97  xor     edx, edx; bInheritHandle
0x180037a99  mov     ecx, 1F0003h; dwDesiredAccess
0x180037a9e  call    cs:__imp_OpenSemaphoreW
0x180037aa4  mov     [rsp+260h+var_238], rax
0x180037aa9  test    rax, rax
0x180037aac  jnz     short loc_180037AD4
0x180037aae  mov     rcx, [rbp+168h]; this
0x180037ab5  lea     r8, aWil; "wil"
0x180037abc  mov     edx, 0DCh; void *
0x180037ac1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180037ac6  mov     ebx, eax
0x180037ac8  lea     rcx, [rsp+260h+var_238]
0x180037acd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180037ad2  jmp     short loc_180037B24
0x180037ad4  lea     rdx, [rsp+260h+var_240]; int *
0x180037ad9  mov     rcx, rax; hHandle
0x180037adc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180037ae1  mov     ebx, eax
0x180037ae3  test    eax, eax
0x180037ae5  jns     short loc_180037B04
0x180037ae7  mov     rcx, [rbp+168h]; this
0x180037aee  lea     r8, aWil; "wil"
0x180037af5  mov     r9d, eax; char *
0x180037af8  mov     edx, 0DEh; void *
0x180037afd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037b02  jmp     short loc_180037AC8
0x180037b04  lea     rcx, [rsp+260h+var_238]
0x180037b09  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180037b0e  movsxd  rcx, [rsp+260h+var_240]
0x180037b13  movsxd  rax, [rsp+260h+var_23C]
0x180037b18  shl     rcx, 1Fh
0x180037b1c  or      rcx, rax
0x180037b1f  mov     [rdi], rcx
0x180037b22  xor     ebx, ebx
0x180037b24  lea     rcx, [rsp+260h+var_230]
0x180037b29  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180037b2e  mov     eax, ebx
0x180037b30  mov     rcx, [rbp+160h+var_10]
0x180037b37  xor     rcx, rsp; StackCookie
0x180037b3a  call    __security_check_cookie
0x180037b3f  lea     r11, [rsp+260h+var_s0]
0x180037b47  mov     rbx, [r11+18h]
0x180037b4b  mov     rdi, [r11+28h]
0x180037b4f  mov     rsp, r11
0x180037b52  pop     rbp
0x180037b53  retn
```
