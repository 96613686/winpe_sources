# ?try_create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1801a0448`
- end: `0x1801a04c6`
- name: `?try_create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `126`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD, LPSECURITY_ATTRIBUTES lpSemaphoreAttributes, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801cfdf8`

## callees

- `0x1801a0448`
- `0x1801a06e4`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x1801a0479`
- `KERNEL32!CreateSemaphoreExW` at `0x1801a0479`
- `KERNEL32!GetLastError` at `0x1801a0497`
- `KERNEL32!GetLastError` at `0x1801a0497`

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
0x1801a0448  mov     r11, rsp
0x1801a044b  mov     [r11+20h], r9
0x1801a044f  mov     [r11+18h], r8d
0x1801a0453  mov     [rsp+lInitialCount], edx
0x1801a0457  mov     [r11+8], rcx
0x1801a045b  push    rbx
0x1801a045c  sub     rsp, 30h
0x1801a0460  mov     eax, [rsp+38h+arg_20]
0x1801a0464  mov     edx, [rsp+38h+lInitialCount]; lInitialCount
0x1801a0468  mov     rcx, [rsp+38h+lpSemaphoreAttributes]; lpSemaphoreAttributes
0x1801a046d  mov     [rsp+38h+dwDesiredAccess], eax; dwDesiredAccess
0x1801a0471  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1801a0479  call    cs:__imp_CreateSemaphoreExW
0x1801a047f  mov     rbx, rax
0x1801a0482  test    rax, rax
0x1801a0485  jnz     short loc_1801A0497
0x1801a0487  mov     rax, [rsp+38h+arg_30]
0x1801a048c  test    rax, rax
0x1801a048f  jz      short loc_1801A0493
0x1801a0491  mov     [rax], bl
0x1801a0493  xor     al, al
0x1801a0495  jmp     short loc_1801A04C0
0x1801a0497  call    cs:__imp_GetLastError
0x1801a049d  cmp     eax, 0B7h
0x1801a04a2  mov     rax, [rsp+38h+arg_30]
0x1801a04a7  setz    cl
0x1801a04aa  test    rax, rax
0x1801a04ad  jz      short loc_1801A04B1
0x1801a04af  mov     [rax], cl
0x1801a04b1  mov     rcx, [rsp+38h+arg_0]
0x1801a04b6  mov     rdx, rbx
0x1801a04b9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1801a04be  mov     al, 1
0x1801a04c0  add     rsp, 30h
0x1801a04c4  pop     rbx
0x1801a04c5  retn
```
