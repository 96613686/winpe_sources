# CreatePresentLimitSemaphore(void * *)

- ea: `0x18005b3a0`
- end: `0x18005b49c`
- name: `?CreatePresentLimitSemaphore@@YAJPEAPEAX@Z`
- size: `252`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d2fc`

## callees

- `0x18005b3a0`
- `0x180075fa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18005b42a`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18005b42a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b472`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b441`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b465`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b487`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b441`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b465`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b487`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005b3e9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005b3e9`

## pseudocode

```c
__int64 __fastcall CreatePresentLimitSemaphore(void **a1)
{
  HANDLE v2; // rax
  PSECURITY_DESCRIPTOR v3; // rcx
  signed int LastError; // eax
  unsigned int v6; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-30h] BYREF
  _SECURITY_ATTRIBUTES SemaphoreAttributes; // [rsp+38h] [rbp-28h] BYREF
  WCHAR StringSecurityDescriptor[4]; // [rsp+50h] [rbp-10h] BYREF

  wcscpy(StringSecurityDescriptor, L"D:");
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    *(_QWORD *)&SemaphoreAttributes.nLength = 24;
    SemaphoreAttributes.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&SemaphoreAttributes.bInheritHandle = 0;
    v2 = CreateSemaphoreExW(&SemaphoreAttributes, 1, 40, 0, 0, 0x100002u);
    v3 = SecurityDescriptor;
    *a1 = v2;
    if ( v2 )
    {
      if ( v3 )
        LocalFree(v3);
      return 0;
    }
    else
    {
      if ( v3 )
        LocalFree(v3);
      return 2147942414LL;
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return v6;
  }
}

```

## disassembly

```asm
0x18005b3a0  mov     [rsp-8+arg_8], rbx
0x18005b3a5  push    rbp
0x18005b3a6  mov     rbp, rsp
0x18005b3a9  sub     rsp, 60h
0x18005b3ad  mov     rax, cs:__security_cookie
0x18005b3b4  xor     rax, rsp
0x18005b3b7  mov     [rbp+var_8], rax
0x18005b3bb  mov     eax, dword ptr cs:aD; "D:"
0x18005b3c1  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18005b3c5  xor     r9d, r9d; SecurityDescriptorSize
0x18005b3c8  mov     dword ptr [rbp+StringSecurityDescriptor], eax
0x18005b3cb  movzx   eax, word ptr cs:aD+4; ""
0x18005b3d2  mov     rbx, rcx
0x18005b3d5  lea     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18005b3d9  mov     [rbp+var_C], ax
0x18005b3dd  mov     [rbp+SecurityDescriptor], 0
0x18005b3e5  lea     edx, [r9+1]; StringSDRevision
0x18005b3e9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005b3ef  test    eax, eax
0x18005b3f1  jz      short loc_18005B472
0x18005b3f3  mov     rax, [rbp+SecurityDescriptor]
0x18005b3f7  lea     rcx, [rbp+SemaphoreAttributes]; lpSemaphoreAttributes
0x18005b3fb  xor     r9d, r9d; lpName
0x18005b3fe  mov     [rsp+60h+dwDesiredAccess], 100002h; dwDesiredAccess
0x18005b406  mov     qword ptr [rbp+SemaphoreAttributes.nLength], 18h
0x18005b40e  mov     [rbp+SemaphoreAttributes.lpSecurityDescriptor], rax
0x18005b412  mov     qword ptr [rbp+SemaphoreAttributes.bInheritHandle], 0
0x18005b41a  lea     edx, [r9+1]; lInitialCount
0x18005b41e  mov     [rsp+60h+dwFlags], 0; dwFlags
0x18005b426  lea     r8d, [r9+28h]; lMaximumCount
0x18005b42a  call    cs:__imp_CreateSemaphoreExW
0x18005b430  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18005b434  mov     [rbx], rax
0x18005b437  test    rax, rax
0x18005b43a  jz      short loc_18005B460
0x18005b43c  test    rcx, rcx
0x18005b43f  jz      short loc_18005B447
0x18005b441  call    cs:__imp_LocalFree
0x18005b447  xor     eax, eax
0x18005b449  mov     rcx, [rbp+var_8]
0x18005b44d  xor     rcx, rsp; StackCookie
0x18005b450  call    __security_check_cookie
0x18005b455  mov     rbx, [rsp+60h+arg_8]
0x18005b45a  add     rsp, 60h
0x18005b45e  pop     rbp
0x18005b45f  retn
0x18005b460  test    rcx, rcx
0x18005b463  jz      short loc_18005B46B
0x18005b465  call    cs:__imp_LocalFree
0x18005b46b  mov     eax, 8007000Eh
0x18005b470  jmp     short loc_18005B449
0x18005b472  call    cs:__imp_GetLastError
0x18005b478  mov     ebx, eax
0x18005b47a  test    eax, eax
0x18005b47c  jg      short loc_18005B491
0x18005b47e  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18005b482  test    rcx, rcx
0x18005b485  jz      short loc_18005B48D
0x18005b487  call    cs:__imp_LocalFree
0x18005b48d  mov     eax, ebx
0x18005b48f  jmp     short loc_18005B449
0x18005b491  movzx   ebx, ax
0x18005b494  or      ebx, 80070000h
0x18005b49a  jmp     short loc_18005B47E
```
