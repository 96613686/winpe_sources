# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180045fac`
- end: `0x180046164`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180045f28`

## callees

- `0x18003a5cc`
- `0x18003bf28`
- `0x180042410`
- `0x180044224`
- `0x180044ddc`
- `0x180045b04`
- `0x180045b80`
- `0x180045fac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180046010`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800460ae`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180046010`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800460ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046020`

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
0x180045fac  mov     [rsp-8+arg_8], rbx
0x180045fb1  mov     [rsp-8+arg_18], rdi
0x180045fb6  push    rbp
0x180045fb7  lea     rbp, [rsp-160h]
0x180045fbf  sub     rsp, 260h
0x180045fc6  mov     rax, cs:__security_cookie
0x180045fcd  xor     rax, rsp
0x180045fd0  mov     [rbp+160h+var_10], rax
0x180045fd7  mov     rdi, r8
0x180045fda  mov     qword ptr [r8], 0
0x180045fe1  mov     r8, rcx; unsigned __int16 *
0x180045fe4  mov     edx, 104h; unsigned __int64
0x180045fe9  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180045fee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180045ff3  lea     r8, aP0; "_p0"
0x180045ffa  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180045fff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180046004  lea     r8, [rsp+260h+Name]; lpName
0x180046009  xor     edx, edx; bInheritHandle
0x18004600b  mov     ecx, 1F0003h; dwDesiredAccess
0x180046010  call    cs:__imp_OpenSemaphoreW
0x180046016  mov     [rsp+260h+var_230], rax
0x18004601b  test    rax, rax
0x18004601e  jnz     short loc_18004604E
0x180046020  call    cs:__imp_GetLastError
0x180046026  cmp     eax, 2
0x180046029  jz      loc_180046132
0x18004602f  mov     rcx, [rbp+168h]; this
0x180046036  lea     r8, aWil; "wil"
0x18004603d  mov     edx, 0D0h; void *
0x180046042  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180046047  mov     ebx, eax
0x180046049  jmp     loc_180046134
0x18004604e  lea     rdx, [rsp+260h+var_23C]; int *
0x180046053  mov     [rsp+260h+var_23C], 0
0x18004605b  mov     rcx, rax; hHandle
0x18004605e  mov     [rsp+260h+var_240], 0; int
0x180046066  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18004606b  mov     ebx, eax
0x18004606d  test    eax, eax
0x18004606f  jns     short loc_180046091
0x180046071  mov     rcx, [rbp+168h]; this
0x180046078  lea     r8, aWil; "wil"
0x18004607f  mov     r9d, eax; char *
0x180046082  mov     edx, 0D6h; void *
0x180046087  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004608c  jmp     loc_180046134
0x180046091  lea     r8, asc_180086DC8; "h"
0x180046098  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18004609d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800460a2  lea     r8, [rsp+260h+Name]; lpName
0x1800460a7  xor     edx, edx; bInheritHandle
0x1800460a9  mov     ecx, 1F0003h; dwDesiredAccess
0x1800460ae  call    cs:__imp_OpenSemaphoreW
0x1800460b4  mov     [rsp+260h+var_238], rax
0x1800460b9  test    rax, rax
0x1800460bc  jnz     short loc_1800460E4
0x1800460be  mov     rcx, [rbp+168h]; this
0x1800460c5  lea     r8, aWil; "wil"
0x1800460cc  mov     edx, 0DCh; void *
0x1800460d1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800460d6  mov     ebx, eax
0x1800460d8  lea     rcx, [rsp+260h+var_238]
0x1800460dd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800460e2  jmp     short loc_180046134
0x1800460e4  lea     rdx, [rsp+260h+var_240]; int *
0x1800460e9  mov     rcx, rax; hHandle
0x1800460ec  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800460f1  mov     ebx, eax
0x1800460f3  test    eax, eax
0x1800460f5  jns     short loc_180046114
0x1800460f7  mov     rcx, [rbp+168h]; this
0x1800460fe  lea     r8, aWil; "wil"
0x180046105  mov     r9d, eax; char *
0x180046108  mov     edx, 0DEh; void *
0x18004610d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046112  jmp     short loc_1800460D8
0x180046114  lea     rcx, [rsp+260h+var_238]
0x180046119  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004611e  movsxd  rcx, [rsp+260h+var_240]
0x180046123  movsxd  rax, [rsp+260h+var_23C]
0x180046128  shl     rcx, 1Fh
0x18004612c  or      rcx, rax
0x18004612f  mov     [rdi], rcx
0x180046132  xor     ebx, ebx
0x180046134  lea     rcx, [rsp+260h+var_230]
0x180046139  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004613e  mov     eax, ebx
0x180046140  mov     rcx, [rbp+160h+var_10]
0x180046147  xor     rcx, rsp; StackCookie
0x18004614a  call    __security_check_cookie
0x18004614f  lea     r11, [rsp+260h+var_s0]
0x180046157  mov     rbx, [r11+18h]
0x18004615b  mov     rdi, [r11+28h]
0x18004615f  mov     rsp, r11
0x180046162  pop     rbp
0x180046163  retn
```
