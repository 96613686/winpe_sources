# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a120`
- end: `0x18000a2d8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000a09c`

## callees

- `0x180003220`
- `0x180005fcc`
- `0x180007650`
- `0x18000947c`
- `0x18000949c`
- `0x180009b68`
- `0x180009be4`
- `0x18000a120`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a184`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a222`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a184`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a194`

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
0x18000a120  mov     [rsp-8+arg_8], rbx
0x18000a125  mov     [rsp-8+arg_18], rdi
0x18000a12a  push    rbp
0x18000a12b  lea     rbp, [rsp-160h]
0x18000a133  sub     rsp, 260h
0x18000a13a  mov     rax, cs:__security_cookie
0x18000a141  xor     rax, rsp
0x18000a144  mov     [rbp+160h+var_10], rax
0x18000a14b  mov     rdi, r8
0x18000a14e  mov     qword ptr [r8], 0
0x18000a155  mov     r8, rcx; unsigned __int16 *
0x18000a158  mov     edx, 104h; unsigned __int64
0x18000a15d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a162  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a167  lea     r8, aP0; "_p0"
0x18000a16e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a173  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a178  lea     r8, [rsp+260h+Name]; lpName
0x18000a17d  xor     edx, edx; bInheritHandle
0x18000a17f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a184  call    cs:__imp_OpenSemaphoreW
0x18000a18a  mov     [rsp+260h+var_230], rax
0x18000a18f  test    rax, rax
0x18000a192  jnz     short loc_18000A1C2
0x18000a194  call    cs:__imp_GetLastError
0x18000a19a  cmp     eax, 2
0x18000a19d  jz      loc_18000A2A6
0x18000a1a3  mov     rcx, [rbp+168h]; this
0x18000a1aa  lea     r8, aWil; "wil"
0x18000a1b1  mov     edx, 0D0h; void *
0x18000a1b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a1bb  mov     ebx, eax
0x18000a1bd  jmp     loc_18000A2A8
0x18000a1c2  lea     rdx, [rsp+260h+var_23C]; int *
0x18000a1c7  mov     [rsp+260h+var_23C], 0
0x18000a1cf  mov     rcx, rax; hHandle
0x18000a1d2  mov     [rsp+260h+var_240], 0; int
0x18000a1da  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a1df  mov     ebx, eax
0x18000a1e1  test    eax, eax
0x18000a1e3  jns     short loc_18000A205
0x18000a1e5  mov     rcx, [rbp+168h]; this
0x18000a1ec  lea     r8, aWil; "wil"
0x18000a1f3  mov     r9d, eax; char *
0x18000a1f6  mov     edx, 0D6h; void *
0x18000a1fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a200  jmp     loc_18000A2A8
0x18000a205  lea     r8, asc_1800C2718; "h"
0x18000a20c  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a211  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a216  lea     r8, [rsp+260h+Name]; lpName
0x18000a21b  xor     edx, edx; bInheritHandle
0x18000a21d  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a222  call    cs:__imp_OpenSemaphoreW
0x18000a228  mov     [rsp+260h+var_238], rax
0x18000a22d  test    rax, rax
0x18000a230  jnz     short loc_18000A258
0x18000a232  mov     rcx, [rbp+168h]; this
0x18000a239  lea     r8, aWil; "wil"
0x18000a240  mov     edx, 0DCh; void *
0x18000a245  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a24a  mov     ebx, eax
0x18000a24c  lea     rcx, [rsp+260h+var_238]
0x18000a251  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a256  jmp     short loc_18000A2A8
0x18000a258  lea     rdx, [rsp+260h+var_240]; int *
0x18000a25d  mov     rcx, rax; hHandle
0x18000a260  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a265  mov     ebx, eax
0x18000a267  test    eax, eax
0x18000a269  jns     short loc_18000A288
0x18000a26b  mov     rcx, [rbp+168h]; this
0x18000a272  lea     r8, aWil; "wil"
0x18000a279  mov     r9d, eax; char *
0x18000a27c  mov     edx, 0DEh; void *
0x18000a281  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a286  jmp     short loc_18000A24C
0x18000a288  lea     rcx, [rsp+260h+var_238]
0x18000a28d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a292  movsxd  rcx, [rsp+260h+var_240]
0x18000a297  movsxd  rax, [rsp+260h+var_23C]
0x18000a29c  shl     rcx, 1Fh
0x18000a2a0  or      rcx, rax
0x18000a2a3  mov     [rdi], rcx
0x18000a2a6  xor     ebx, ebx
0x18000a2a8  lea     rcx, [rsp+260h+var_230]
0x18000a2ad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a2b2  mov     eax, ebx
0x18000a2b4  mov     rcx, [rbp+160h+var_10]
0x18000a2bb  xor     rcx, rsp; StackCookie
0x18000a2be  call    __security_check_cookie
0x18000a2c3  lea     r11, [rsp+260h+var_s0]
0x18000a2cb  mov     rbx, [r11+18h]
0x18000a2cf  mov     rdi, [r11+28h]
0x18000a2d3  mov     rsp, r11
0x18000a2d6  pop     rbp
0x18000a2d7  retn
```
