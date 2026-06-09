# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180017a2c`
- end: `0x180017bce`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800179b8`

## callees

- `0x180001710`
- `0x180004c00`
- `0x1800085c0`
- `0x180011490`
- `0x180016644`
- `0x180016664`
- `0x180017560`
- `0x180017a2c`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x180017a95`
- `KERNEL32!OpenSemaphoreW` at `0x180017b27`
- `KERNEL32!OpenSemaphoreW` at `0x180017a95`
- `KERNEL32!OpenSemaphoreW` at `0x180017b27`
- `KERNEL32!GetLastError` at `0x180017aa5`
- `KERNEL32!GetLastError` at `0x180017aa5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v11;
    if ( v11 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180017a2c  mov     [rsp-8+arg_8], rbx
0x180017a31  push    rbp
0x180017a32  push    rdi
0x180017a33  push    r14
0x180017a35  lea     rbp, [rsp-160h]
0x180017a3d  sub     rsp, 260h
0x180017a44  mov     rax, cs:__security_cookie
0x180017a4b  xor     rax, rsp
0x180017a4e  mov     [rbp+170h+var_20], rax
0x180017a55  mov     rdi, r8
0x180017a58  mov     qword ptr [r8], 0
0x180017a5f  mov     r8, rcx; unsigned __int16 *
0x180017a62  mov     r14d, 104h
0x180017a68  mov     edx, r14d; unsigned __int64
0x180017a6b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180017a70  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017a75  lea     r8, aP0; "_p0"
0x180017a7c  mov     edx, r14d; unsigned __int64
0x180017a7f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180017a84  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017a89  lea     r8, [rsp+270h+Name]; lpName
0x180017a8e  xor     edx, edx; bInheritHandle
0x180017a90  mov     ecx, 1F0003h; dwDesiredAccess
0x180017a95  call    cs:__imp_OpenSemaphoreW
0x180017a9b  mov     [rsp+270h+var_240], rax
0x180017aa0  test    rax, rax
0x180017aa3  jnz     short loc_180017ACB
0x180017aa5  call    cs:__imp_GetLastError
0x180017aab  cmp     eax, 2
0x180017aae  jz      loc_180017B9D
0x180017ab4  mov     rcx, [rbp+178h]; this
0x180017abb  lea     edx, [r14-34h]; void *
0x180017abf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017ac4  mov     ebx, eax
0x180017ac6  jmp     loc_180017B9F
0x180017acb  lea     rdx, [rsp+270h+var_24C]; int *
0x180017ad0  mov     [rsp+270h+var_24C], 0
0x180017ad8  mov     rcx, rax; hHandle
0x180017adb  mov     [rsp+270h+var_250], 0; int
0x180017ae3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180017ae8  mov     ebx, eax
0x180017aea  test    eax, eax
0x180017aec  jns     short loc_180017B07
0x180017aee  mov     rcx, [rbp+178h]; this
0x180017af5  mov     r9d, eax; char *
0x180017af8  mov     edx, 0D6h; void *
0x180017afd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b02  jmp     loc_180017B9F
0x180017b07  lea     r8, asc_18003B320; "h"
0x180017b0e  mov     rdx, r14; unsigned __int64
0x180017b11  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180017b16  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017b1b  lea     r8, [rsp+270h+Name]; lpName
0x180017b20  xor     edx, edx; bInheritHandle
0x180017b22  mov     ecx, 1F0003h; dwDesiredAccess
0x180017b27  call    cs:__imp_OpenSemaphoreW
0x180017b2d  mov     [rsp+270h+var_248], rax
0x180017b32  test    rax, rax
0x180017b35  jnz     short loc_180017B56
0x180017b37  mov     rcx, [rbp+178h]; this
0x180017b3e  mov     edx, 0DCh; void *
0x180017b43  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017b48  mov     ebx, eax
0x180017b4a  lea     rcx, [rsp+270h+var_248]
0x180017b4f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017b54  jmp     short loc_180017B9F
0x180017b56  lea     rdx, [rsp+270h+var_250]; int *
0x180017b5b  mov     rcx, rax; hHandle
0x180017b5e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180017b63  mov     ebx, eax
0x180017b65  test    eax, eax
0x180017b67  jns     short loc_180017B7F
0x180017b69  mov     rcx, [rbp+178h]; this
0x180017b70  mov     r9d, eax; char *
0x180017b73  mov     edx, 0DEh; void *
0x180017b78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b7d  jmp     short loc_180017B4A
0x180017b7f  lea     rcx, [rsp+270h+var_248]
0x180017b84  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017b89  movsxd  rcx, [rsp+270h+var_250]
0x180017b8e  movsxd  rax, [rsp+270h+var_24C]
0x180017b93  shl     rcx, 1Fh
0x180017b97  or      rcx, rax
0x180017b9a  mov     [rdi], rcx
0x180017b9d  xor     ebx, ebx
0x180017b9f  lea     rcx, [rsp+270h+var_240]
0x180017ba4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017ba9  mov     eax, ebx
0x180017bab  mov     rcx, [rbp+170h+var_20]
0x180017bb2  xor     rcx, rsp; StackCookie
0x180017bb5  call    __security_check_cookie
0x180017bba  mov     rbx, [rsp+270h+arg_8]
0x180017bc2  add     rsp, 260h
0x180017bc9  pop     r14
0x180017bcb  pop     rdi
0x180017bcc  pop     rbp
0x180017bcd  retn
```
