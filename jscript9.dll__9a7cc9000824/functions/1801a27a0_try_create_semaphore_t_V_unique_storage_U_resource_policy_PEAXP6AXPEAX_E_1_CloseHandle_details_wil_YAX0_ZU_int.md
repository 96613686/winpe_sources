# ?try_create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1801a27a0`
- end: `0x1801a282b`
- name: `?try_create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `139`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD, LPSECURITY_ATTRIBUTES lpSemaphoreAttributes, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801d2a30`

## callees

- `0x1801a27a0`
- `0x1801a2a58`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x1801a27d1`
- `KERNEL32!CreateSemaphoreExW` at `0x1801a27d1`
- `KERNEL32!GetLastError` at `0x1801a27f5`
- `KERNEL32!GetLastError` at `0x1801a27f5`

## pseudocode

```c
char __fastcall _try_create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4,
        DWORD dwDesiredAccess,
        LPSECURITY_ATTRIBUTES lpSemaphoreAttributes,
        bool *a7)
{
  HANDLE Semaphore; // rbx
  bool v9; // zf

  Semaphore = CreateSemaphoreExW(lpSemaphoreAttributes, a2, a3, a4, 0, dwDesiredAccess);
  if ( Semaphore )
  {
    v9 = GetLastError() == 183;
    if ( a7 )
      *a7 = v9;
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      a1,
      Semaphore);
    return 1;
  }
  else
  {
    if ( a7 )
      *a7 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x1801a27a0  mov     r11, rsp
0x1801a27a3  mov     [r11+20h], r9
0x1801a27a7  mov     [r11+18h], r8d
0x1801a27ab  mov     [rsp+lInitialCount], edx
0x1801a27af  mov     [r11+8], rcx
0x1801a27b3  push    rbx
0x1801a27b4  sub     rsp, 30h
0x1801a27b8  mov     eax, [rsp+38h+arg_20]
0x1801a27bc  mov     edx, [rsp+38h+lInitialCount]; lInitialCount
0x1801a27c0  mov     rcx, [rsp+38h+lpSemaphoreAttributes]; lpSemaphoreAttributes
0x1801a27c5  mov     [rsp+38h+dwDesiredAccess], eax; dwDesiredAccess
0x1801a27c9  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1801a27d1  call    cs:__imp_CreateSemaphoreExW
0x1801a27d8  nop     dword ptr [rax+rax+00h]
0x1801a27dd  mov     rbx, rax
0x1801a27e0  test    rax, rax
0x1801a27e3  jnz     short loc_1801A27F5
0x1801a27e5  mov     rax, [rsp+38h+arg_30]
0x1801a27ea  test    rax, rax
0x1801a27ed  jz      short loc_1801A27F1
0x1801a27ef  mov     [rax], bl
0x1801a27f1  xor     al, al
0x1801a27f3  jmp     short loc_1801A2824
0x1801a27f5  call    cs:__imp_GetLastError
0x1801a27fc  nop     dword ptr [rax+rax+00h]
0x1801a2801  cmp     eax, 0B7h
0x1801a2806  mov     rax, [rsp+38h+arg_30]
0x1801a280b  setz    cl
0x1801a280e  test    rax, rax
0x1801a2811  jz      short loc_1801A2815
0x1801a2813  mov     [rax], cl
0x1801a2815  mov     rcx, [rsp+38h+arg_0]
0x1801a281a  mov     rdx, rbx
0x1801a281d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1801a2822  mov     al, 1
0x1801a2824  add     rsp, 30h
0x1801a2828  pop     rbx
0x1801a2829  retn
```
