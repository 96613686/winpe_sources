# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002ef58`
- end: `0x18002f0f4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002a688`

## callees

- `0x180001e80`
- `0x18001ef50`
- `0x18002a364`
- `0x18002c678`
- `0x18002e474`
- `0x18002e494`
- `0x18002ee50`
- `0x18002ef58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002efbc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002f04c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002efbc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002f04c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002efcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002efcc`

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
0x18002ef58  mov     [rsp-8+arg_8], rbx
0x18002ef5d  mov     [rsp-8+arg_18], rdi
0x18002ef62  push    rbp
0x18002ef63  lea     rbp, [rsp-160h]
0x18002ef6b  sub     rsp, 260h
0x18002ef72  mov     rax, cs:__security_cookie
0x18002ef79  xor     rax, rsp
0x18002ef7c  mov     [rbp+160h+var_10], rax
0x18002ef83  mov     rdi, r8
0x18002ef86  mov     qword ptr [r8], 0
0x18002ef8d  mov     r8, rcx; unsigned __int16 *
0x18002ef90  mov     edx, 104h; unsigned __int64
0x18002ef95  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002ef9a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ef9f  lea     r8, aP0; "_p0"
0x18002efa6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002efab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002efb0  lea     r8, [rsp+260h+Name]; lpName
0x18002efb5  xor     edx, edx; bInheritHandle
0x18002efb7  mov     ecx, 1F0003h; dwDesiredAccess
0x18002efbc  call    cs:__imp_OpenSemaphoreW
0x18002efc2  mov     [rsp+260h+var_230], rax
0x18002efc7  test    rax, rax
0x18002efca  jnz     short loc_18002EFF3
0x18002efcc  call    cs:__imp_GetLastError
0x18002efd2  cmp     eax, 2
0x18002efd5  jz      loc_18002F0C2
0x18002efdb  mov     rcx, [rbp+168h]; this
0x18002efe2  mov     edx, 0D0h; void *
0x18002efe7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002efec  mov     ebx, eax
0x18002efee  jmp     loc_18002F0C4
0x18002eff3  lea     rdx, [rsp+260h+var_23C]; int *
0x18002eff8  mov     [rsp+260h+var_23C], 0
0x18002f000  mov     rcx, rax; hHandle
0x18002f003  mov     [rsp+260h+var_240], 0; int
0x18002f00b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002f010  mov     ebx, eax
0x18002f012  test    eax, eax
0x18002f014  jns     short loc_18002F02F
0x18002f016  mov     rcx, [rbp+168h]; this
0x18002f01d  mov     r9d, eax; char *
0x18002f020  mov     edx, 0D6h; void *
0x18002f025  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f02a  jmp     loc_18002F0C4
0x18002f02f  lea     r8, asc_180064338; "h"
0x18002f036  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002f03b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002f040  lea     r8, [rsp+260h+Name]; lpName
0x18002f045  xor     edx, edx; bInheritHandle
0x18002f047  mov     ecx, 1F0003h; dwDesiredAccess
0x18002f04c  call    cs:__imp_OpenSemaphoreW
0x18002f052  mov     [rsp+260h+var_238], rax
0x18002f057  test    rax, rax
0x18002f05a  jnz     short loc_18002F07B
0x18002f05c  mov     rcx, [rbp+168h]; this
0x18002f063  mov     edx, 0DCh; void *
0x18002f068  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f06d  mov     ebx, eax
0x18002f06f  lea     rcx, [rsp+260h+var_238]
0x18002f074  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002f079  jmp     short loc_18002F0C4
0x18002f07b  lea     rdx, [rsp+260h+var_240]; int *
0x18002f080  mov     rcx, rax; hHandle
0x18002f083  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002f088  mov     ebx, eax
0x18002f08a  test    eax, eax
0x18002f08c  jns     short loc_18002F0A4
0x18002f08e  mov     rcx, [rbp+168h]; this
0x18002f095  mov     r9d, eax; char *
0x18002f098  mov     edx, 0DEh; void *
0x18002f09d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f0a2  jmp     short loc_18002F06F
0x18002f0a4  lea     rcx, [rsp+260h+var_238]
0x18002f0a9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002f0ae  movsxd  rcx, [rsp+260h+var_240]
0x18002f0b3  movsxd  rax, [rsp+260h+var_23C]
0x18002f0b8  shl     rcx, 1Fh
0x18002f0bc  or      rcx, rax
0x18002f0bf  mov     [rdi], rcx
0x18002f0c2  xor     ebx, ebx
0x18002f0c4  lea     rcx, [rsp+260h+var_230]
0x18002f0c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002f0ce  mov     eax, ebx
0x18002f0d0  mov     rcx, [rbp+160h+var_10]
0x18002f0d7  xor     rcx, rsp; StackCookie
0x18002f0da  call    __security_check_cookie
0x18002f0df  lea     r11, [rsp+260h+var_s0]
0x18002f0e7  mov     rbx, [r11+18h]
0x18002f0eb  mov     rdi, [r11+28h]
0x18002f0ef  mov     rsp, r11
0x18002f0f2  pop     rbp
0x18002f0f3  retn
```
