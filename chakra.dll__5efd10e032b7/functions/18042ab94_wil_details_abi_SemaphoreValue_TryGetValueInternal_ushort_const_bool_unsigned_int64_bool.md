# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18042ab94`
- end: `0x18042ad4e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `442`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18042ab14`

## callees

- `0x180425bfc`
- `0x180427990`
- `0x1804299b8`
- `0x1804299f4`
- `0x18042a6e0`
- `0x18042a770`
- `0x18042ab94`
- `0x1805a9e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18042ac0d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18042aca9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18042ac0d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18042aca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042ac23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042ac23`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        unsigned __int64 a2,
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
  int v19[2]; // [rsp+28h] [rbp-E0h] BYREF
  HANDLE v20; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD v21[2]; // [rsp+38h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+48h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  v21[1] = -2;
  *a3 = 0;
  StringCchCopyW(Name, a2, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21[0] = v6;
  if ( v6 )
  {
    v19[1] = 0;
    v19[0] = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v19[1]);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        v12,
        (const char *)(unsigned int)ValueFromSemaphore,
        v19[0]);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v20 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
        *a3 = v19[1] | (unsigned __int64)((__int64)v19[0] << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v19[0]);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
  return LastError;
}

```

## disassembly

```asm
0x18042ab94  mov     rax, rsp
0x18042ab97  mov     [rax+20h], r9
0x18042ab9b  mov     [rax+18h], r8
0x18042ab9f  mov     [rax+10h], dl
0x18042aba2  mov     [rax+8], rcx
0x18042aba6  push    rbp
0x18042aba7  push    rbx
0x18042aba8  push    rdi
0x18042aba9  lea     rbp, [rax-178h]
0x18042abb0  sub     rsp, 260h
0x18042abb7  mov     qword ptr [rsp+270h+var_238], 0FFFFFFFFFFFFFFFEh
0x18042abc0  mov     rax, cs:__security_cookie
0x18042abc7  xor     rax, rsp
0x18042abca  mov     [rbp+170h+var_20], rax
0x18042abd1  mov     r8, [rbp+170h+arg_0]; unsigned __int16 *
0x18042abd8  mov     rdi, [rbp+170h+arg_10]
0x18042abdf  mov     qword ptr [rdi], 0
0x18042abe6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18042abeb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18042abf0  lea     r8, aP0; "_p0"
0x18042abf7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18042abfc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18042ac01  lea     r8, [rsp+270h+Name]; lpName
0x18042ac06  xor     edx, edx; bInheritHandle
0x18042ac08  mov     ecx, 1F0003h; dwDesiredAccess
0x18042ac0d  call    cs:__imp_OpenSemaphoreW
0x18042ac14  nop     dword ptr [rax+rax+00h]
0x18042ac19  mov     [rsp+270h+var_240], rax
0x18042ac1e  test    rax, rax
0x18042ac21  jnz     short loc_18042AC50
0x18042ac23  call    cs:__imp_GetLastError
0x18042ac2a  nop     dword ptr [rax+rax+00h]
0x18042ac2f  cmp     eax, 2
0x18042ac32  jz      loc_18042AD25
0x18042ac38  mov     rcx, [rbp+178h]; this
0x18042ac3f  mov     edx, 0D0h; void *
0x18042ac44  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18042ac49  mov     ebx, eax
0x18042ac4b  jmp     loc_18042AD27
0x18042ac50  mov     [rsp+270h+var_250+4], 0
0x18042ac58  mov     [rsp+270h+var_250], 0; int
0x18042ac60  lea     rdx, [rsp+270h+var_250+4]; int *
0x18042ac65  mov     rcx, rax; void *
0x18042ac68  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18042ac6d  mov     ebx, eax
0x18042ac6f  test    eax, eax
0x18042ac71  jns     short loc_18042AC8C
0x18042ac73  mov     rcx, [rbp+178h]; this
0x18042ac7a  mov     r9d, eax; char *
0x18042ac7d  mov     edx, 0D6h; void *
0x18042ac82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18042ac87  jmp     loc_18042AD27
0x18042ac8c  lea     r8, asc_180684740; "h"
0x18042ac93  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18042ac98  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18042ac9d  lea     r8, [rsp+270h+Name]; lpName
0x18042aca2  xor     edx, edx; bInheritHandle
0x18042aca4  mov     ecx, 1F0003h; dwDesiredAccess
0x18042aca9  call    cs:__imp_OpenSemaphoreW
0x18042acb0  nop     dword ptr [rax+rax+00h]
0x18042acb5  mov     [rsp+270h+var_248], rax
0x18042acba  test    rax, rax
0x18042acbd  jnz     short loc_18042ACDE
0x18042acbf  mov     rcx, [rbp+178h]; this
0x18042acc6  mov     edx, 0DCh; void *
0x18042accb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18042acd0  mov     ebx, eax
0x18042acd2  lea     rcx, [rsp+270h+var_248]
0x18042acd7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18042acdc  jmp     short loc_18042AD27
0x18042acde  lea     rdx, [rsp+270h+var_250]; int *
0x18042ace3  mov     rcx, rax; void *
0x18042ace6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18042aceb  mov     ebx, eax
0x18042aced  test    eax, eax
0x18042acef  jns     short loc_18042AD07
0x18042acf1  mov     rcx, [rbp+178h]; this
0x18042acf8  mov     r9d, eax; char *
0x18042acfb  mov     edx, 0DEh; void *
0x18042ad00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18042ad05  jmp     short loc_18042ACD2
0x18042ad07  lea     rcx, [rsp+270h+var_248]
0x18042ad0c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18042ad11  movsxd  rcx, [rsp+270h+var_250]
0x18042ad16  shl     rcx, 1Fh
0x18042ad1a  movsxd  rax, [rsp+270h+var_250+4]
0x18042ad1f  or      rcx, rax
0x18042ad22  mov     [rdi], rcx
0x18042ad25  xor     ebx, ebx
0x18042ad27  lea     rcx, [rsp+270h+var_240]
0x18042ad2c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18042ad31  mov     eax, ebx
0x18042ad33  mov     rcx, [rbp+170h+var_20]
0x18042ad3a  xor     rcx, rsp; StackCookie
0x18042ad3d  call    __security_check_cookie
0x18042ad42  add     rsp, 260h
0x18042ad49  pop     rdi
0x18042ad4a  pop     rbx
0x18042ad4b  pop     rbp
0x18042ad4c  retn
```
