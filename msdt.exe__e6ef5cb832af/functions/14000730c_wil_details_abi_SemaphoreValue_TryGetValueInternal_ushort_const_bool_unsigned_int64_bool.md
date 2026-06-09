# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000730c`
- end: `0x1400074cf`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `451`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140007288`

## callees

- `0x140004f70`
- `0x140005da8`
- `0x140006a84`
- `0x140006aa4`
- `0x140006fe0`
- `0x14000706c`
- `0x14000730c`
- `0x140061c90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000738b`
- `KERNEL32!GetLastError` at `0x14000738b`
- `KERNEL32!OpenSemaphoreW` at `0x140007375`
- `KERNEL32!OpenSemaphoreW` at `0x14000741a`
- `KERNEL32!OpenSemaphoreW` at `0x140007375`
- `KERNEL32!OpenSemaphoreW` at `0x14000741a`

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
  HANDLE v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v5;
  if ( v5 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v16);
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
    StringCchCatW(Name, 0x104u, L"h");
    v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v15);
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
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v11, v12);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x14000730c  mov     [rsp-8+arg_8], rbx
0x140007311  push    rbp
0x140007312  push    rdi
0x140007313  push    r14
0x140007315  lea     rbp, [rsp-160h]
0x14000731d  sub     rsp, 260h
0x140007324  mov     rax, cs:__security_cookie
0x14000732b  xor     rax, rsp
0x14000732e  mov     [rbp+170h+var_20], rax
0x140007335  mov     rdi, r8
0x140007338  mov     qword ptr [r8], 0
0x14000733f  mov     r8, rcx; unsigned __int16 *
0x140007342  mov     r14d, 104h
0x140007348  mov     edx, r14d; unsigned __int64
0x14000734b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007350  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140007355  lea     r8, aP0_0; "_p0"
0x14000735c  mov     edx, r14d; unsigned __int64
0x14000735f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007364  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007369  lea     r8, [rsp+270h+Name]; lpName
0x14000736e  xor     edx, edx; bInheritHandle
0x140007370  mov     ecx, 1F0003h; dwDesiredAccess
0x140007375  call    cs:__imp_OpenSemaphoreW
0x14000737c  nop     dword ptr [rax+rax+00h]
0x140007381  mov     [rsp+270h+var_240], rax
0x140007386  test    rax, rax
0x140007389  jnz     short loc_1400073B7
0x14000738b  call    cs:__imp_GetLastError
0x140007392  nop     dword ptr [rax+rax+00h]
0x140007397  cmp     eax, 2
0x14000739a  jz      loc_14000749D
0x1400073a0  mov     rcx, [rbp+178h]; this
0x1400073a7  lea     edx, [r14-34h]; void *
0x1400073ab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400073b0  mov     ebx, eax
0x1400073b2  jmp     loc_14000749F
0x1400073b7  lea     rdx, [rsp+270h+var_24C]; int *
0x1400073bc  mov     [rsp+270h+var_24C], 0
0x1400073c4  mov     rcx, rax; hHandle
0x1400073c7  mov     [rsp+270h+var_250], 0; int
0x1400073cf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400073d4  mov     ebx, eax
0x1400073d6  test    eax, eax
0x1400073d8  jns     short loc_1400073FA
0x1400073da  mov     rcx, [rbp+178h]; this
0x1400073e1  lea     r8, aWil; "wil"
0x1400073e8  mov     r9d, eax; char *
0x1400073eb  mov     edx, 0D6h; void *
0x1400073f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400073f5  jmp     loc_14000749F
0x1400073fa  lea     r8, asc_14006B4B0; "h"
0x140007401  mov     rdx, r14; unsigned __int64
0x140007404  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007409  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000740e  lea     r8, [rsp+270h+Name]; lpName
0x140007413  xor     edx, edx; bInheritHandle
0x140007415  mov     ecx, 1F0003h; dwDesiredAccess
0x14000741a  call    cs:__imp_OpenSemaphoreW
0x140007421  nop     dword ptr [rax+rax+00h]
0x140007426  mov     [rsp+270h+var_248], rax
0x14000742b  test    rax, rax
0x14000742e  jnz     short loc_14000744F
0x140007430  mov     rcx, [rbp+178h]; this
0x140007437  mov     edx, 0DCh; void *
0x14000743c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140007441  mov     ebx, eax
0x140007443  lea     rcx, [rsp+270h+var_248]
0x140007448  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000744d  jmp     short loc_14000749F
0x14000744f  lea     rdx, [rsp+270h+var_250]; int *
0x140007454  mov     rcx, rax; hHandle
0x140007457  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000745c  mov     ebx, eax
0x14000745e  test    eax, eax
0x140007460  jns     short loc_14000747F
0x140007462  mov     rcx, [rbp+178h]; this
0x140007469  lea     r8, aWil; "wil"
0x140007470  mov     r9d, eax; char *
0x140007473  mov     edx, 0DEh; void *
0x140007478  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000747d  jmp     short loc_140007443
0x14000747f  lea     rcx, [rsp+270h+var_248]
0x140007484  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007489  movsxd  rcx, [rsp+270h+var_250]
0x14000748e  movsxd  rax, [rsp+270h+var_24C]
0x140007493  shl     rcx, 1Fh
0x140007497  or      rcx, rax
0x14000749a  mov     [rdi], rcx
0x14000749d  xor     ebx, ebx
0x14000749f  lea     rcx, [rsp+270h+var_240]
0x1400074a4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400074a9  mov     eax, ebx
0x1400074ab  mov     rcx, [rbp+170h+var_20]
0x1400074b2  xor     rcx, rsp; StackCookie
0x1400074b5  call    __security_check_cookie
0x1400074ba  mov     rbx, [rsp+270h+arg_8]
0x1400074c2  add     rsp, 260h
0x1400074c9  pop     r14
0x1400074cb  pop     rdi
0x1400074cc  pop     rbp
0x1400074cd  retn
```
