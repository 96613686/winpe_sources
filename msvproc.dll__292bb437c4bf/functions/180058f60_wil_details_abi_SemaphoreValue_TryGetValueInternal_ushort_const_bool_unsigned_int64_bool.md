# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180058f60`
- end: `0x1800590fc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180056aec`

## callees

- `0x180054140`
- `0x1800568a4`
- `0x180057d24`
- `0x180058af8`
- `0x180058b18`
- `0x180058d90`
- `0x180058e0c`
- `0x180058f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180058fc4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180059054`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180058fc4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180059054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058fd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058fd4`

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
0x180058f60  mov     [rsp-8+arg_8], rbx
0x180058f65  mov     [rsp-8+arg_18], rdi
0x180058f6a  push    rbp
0x180058f6b  lea     rbp, [rsp-160h]
0x180058f73  sub     rsp, 260h
0x180058f7a  mov     rax, cs:__security_cookie
0x180058f81  xor     rax, rsp
0x180058f84  mov     [rbp+160h+var_10], rax
0x180058f8b  mov     rdi, r8
0x180058f8e  mov     qword ptr [r8], 0
0x180058f95  mov     r8, rcx; unsigned __int16 *
0x180058f98  mov     edx, 104h; unsigned __int64
0x180058f9d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180058fa2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180058fa7  lea     r8, aP0; "_p0"
0x180058fae  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180058fb3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180058fb8  lea     r8, [rsp+260h+Name]; lpName
0x180058fbd  xor     edx, edx; bInheritHandle
0x180058fbf  mov     ecx, 1F0003h; dwDesiredAccess
0x180058fc4  call    cs:__imp_OpenSemaphoreW
0x180058fca  mov     [rsp+260h+var_230], rax
0x180058fcf  test    rax, rax
0x180058fd2  jnz     short loc_180058FFB
0x180058fd4  call    cs:__imp_GetLastError
0x180058fda  cmp     eax, 2
0x180058fdd  jz      loc_1800590CA
0x180058fe3  mov     rcx, [rbp+168h]; this
0x180058fea  mov     edx, 0D0h; void *
0x180058fef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180058ff4  mov     ebx, eax
0x180058ff6  jmp     loc_1800590CC
0x180058ffb  lea     rdx, [rsp+260h+var_23C]; int *
0x180059000  mov     [rsp+260h+var_23C], 0
0x180059008  mov     rcx, rax; hHandle
0x18005900b  mov     [rsp+260h+var_240], 0; int
0x180059013  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180059018  mov     ebx, eax
0x18005901a  test    eax, eax
0x18005901c  jns     short loc_180059037
0x18005901e  mov     rcx, [rbp+168h]; this
0x180059025  mov     r9d, eax; char *
0x180059028  mov     edx, 0D6h; void *
0x18005902d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059032  jmp     loc_1800590CC
0x180059037  lea     r8, asc_1800DCE80; "h"
0x18005903e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180059043  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180059048  lea     r8, [rsp+260h+Name]; lpName
0x18005904d  xor     edx, edx; bInheritHandle
0x18005904f  mov     ecx, 1F0003h; dwDesiredAccess
0x180059054  call    cs:__imp_OpenSemaphoreW
0x18005905a  mov     [rsp+260h+var_238], rax
0x18005905f  test    rax, rax
0x180059062  jnz     short loc_180059083
0x180059064  mov     rcx, [rbp+168h]; this
0x18005906b  mov     edx, 0DCh; void *
0x180059070  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180059075  mov     ebx, eax
0x180059077  lea     rcx, [rsp+260h+var_238]
0x18005907c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180059081  jmp     short loc_1800590CC
0x180059083  lea     rdx, [rsp+260h+var_240]; int *
0x180059088  mov     rcx, rax; hHandle
0x18005908b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180059090  mov     ebx, eax
0x180059092  test    eax, eax
0x180059094  jns     short loc_1800590AC
0x180059096  mov     rcx, [rbp+168h]; this
0x18005909d  mov     r9d, eax; char *
0x1800590a0  mov     edx, 0DEh; void *
0x1800590a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800590aa  jmp     short loc_180059077
0x1800590ac  lea     rcx, [rsp+260h+var_238]
0x1800590b1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800590b6  movsxd  rcx, [rsp+260h+var_240]
0x1800590bb  movsxd  rax, [rsp+260h+var_23C]
0x1800590c0  shl     rcx, 1Fh
0x1800590c4  or      rcx, rax
0x1800590c7  mov     [rdi], rcx
0x1800590ca  xor     ebx, ebx
0x1800590cc  lea     rcx, [rsp+260h+var_230]
0x1800590d1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800590d6  mov     eax, ebx
0x1800590d8  mov     rcx, [rbp+160h+var_10]
0x1800590df  xor     rcx, rsp; StackCookie
0x1800590e2  call    __security_check_cookie
0x1800590e7  lea     r11, [rsp+260h+var_s0]
0x1800590ef  mov     rbx, [r11+18h]
0x1800590f3  mov     rdi, [r11+28h]
0x1800590f7  mov     rsp, r11
0x1800590fa  pop     rbp
0x1800590fb  retn
```
