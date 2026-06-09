# RegDeleteValueW

- ea: `0x1800e4ad0`
- end: `0x1800e4d45`
- name: `RegDeleteValueW`
- size: `629`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `8`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800e45f0`
- `0x1800e48e8`
- `0x1800e4a34`
- `0x1800e4a60`
- `0x180134ef4`
- `0x18013cc80`
- `0x18013df64`
- `0x18014c808`

## callees

- `0x18005e7e0`
- `0x18005feb0`
- `0x180061220`
- `0x1800e4ad0`
- `0x180136e28`
- `0x180139854`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800e4bf7`
- `ntdll!RtlNtStatusToDosError` at `0x1800e4bf7`
- `ntdll!NtDeleteValueKey` at `0x1800e4bd7`
- `ntdll!NtDeleteValueKey` at `0x1800e4cb9`
- `ntdll!NtDeleteValueKey` at `0x1800e4bd7`
- `ntdll!NtDeleteValueKey` at `0x1800e4cb9`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e4b2c`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e4b2c`
- `ntdll!NtClose` at `0x1800e4c77`
- `ntdll!NtClose` at `0x1800e4c77`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegDeleteValue` at `0x1800e4d23`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegDeleteValue` at `0x1800e4d23`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvDeleteValue` at `0x1800e4bb2`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvDeleteValue` at `0x1800e4bb2`

## pseudocode

```c
LSTATUS __stdcall RegDeleteValueW(HKEY hKey, LPCWSTR lpValueName)
{
  ULONG v3; // ebx
  NTSTATUS inited; // eax
  __int16 v5; // ax
  unsigned __int64 v6; // rdi
  HANDLE v7; // rbx
  void *v8; // rsi
  void *v9; // rcx
  NTSTATUS v10; // eax
  NTSTATUS v11; // r14d
  NTSTATUS v12; // ecx
  void *v14; // rcx
  __int64 v15; // [rsp+38h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF
  HANDLE KeyHandle; // [rsp+80h] [rbp+8h] BYREF
  void *v18; // [rsp+90h] [rbp+18h] BYREF
  __int64 v19; // [rsp+98h] [rbp+20h] BYREF

  KeyHandle = hKey;
  DestinationString = 0;
  v15 = 0;
  v19 = 0;
  if ( hKey != HKEY_PERFORMANCE_DATA )
  {
    v3 = MapPredefinedHandleInternal(hKey, &KeyHandle, &v15, &v19);
    if ( v3 )
    {
LABEL_16:
      CLOSE_LOCAL_HANDLE_INTERNAL(v15, v19);
      return v3;
    }
    inited = RtlInitUnicodeStringEx(&DestinationString, lpValueName);
    if ( inited >= 0 )
    {
      v5 = DestinationString.Length + 2;
      DestinationString.Length += 2;
      v6 = (unsigned __int64)KeyHandle;
      if ( ((unsigned __int8)KeyHandle & 1) != 0 )
      {
        if ( (unsigned __int8)IsBaseRegCloseKeyPresent() )
          v3 = BaseRegDeleteValue(v6 & 0xFFFFFFFFFFFFFFFEuLL, &DestinationString);
        goto LABEL_16;
      }
      v7 = 0;
      KeyHandle = 0;
      v8 = 0;
      v18 = 0;
      if ( (unsigned __int16)v5 < 2u || (v5 & 1) != 0 || !DestinationString.Buffer )
      {
        if ( DestinationString.Buffer || v5 != 2 || DestinationString.MaximumLength )
        {
          v3 = 87;
          goto LABEL_16;
        }
        v5 = 2;
      }
      DestinationString.Length = v5 - 2;
      if ( (unsigned __int8)IsTermsrvDeleteKeyPresent() )
        TermsrvDeleteValue(v6, &DestinationString);
      if ( (v6 & 2) == 0 )
      {
LABEL_11:
        v9 = (void *)v6;
        if ( v7 && v8 )
          v9 = v7;
        v10 = NtDeleteValueKey(v9, &DestinationString);
        v11 = v10;
        if ( (v6 & 2) != 0 && v10 == -1073741772 )
        {
          if ( !v7 )
          {
LABEL_14:
            v12 = v11;
LABEL_15:
            v3 = RtlNtStatusToDosError(v12);
            goto LABEL_16;
          }
          if ( v8 )
            v11 = NtDeleteValueKey(v8, &DestinationString);
        }
        if ( v7 && v8 )
        {
          v14 = v7;
          if ( v7 == (HANDLE)v6 )
            v14 = v8;
          NtClose(v14);
        }
        goto LABEL_14;
      }
      inited = BaseRegGetUserAndMachineClass(0, v6, 0x2000000, &v18, &KeyHandle);
      if ( inited >= 0 )
      {
        v7 = KeyHandle;
        v8 = v18;
        goto LABEL_11;
      }
    }
    v12 = inited;
    goto LABEL_15;
  }
  return 6;
}

```

## disassembly

```asm
0x1800e4ad0  mov     rax, rsp
0x1800e4ad3  mov     [rax+10h], rbx
0x1800e4ad7  mov     [rax+8], rcx
0x1800e4adb  push    rsi
0x1800e4adc  push    rdi
0x1800e4add  push    r12
0x1800e4adf  push    r14
0x1800e4ae1  push    r15
0x1800e4ae3  sub     rsp, 50h
0x1800e4ae7  mov     rdi, rdx
0x1800e4aea  xorps   xmm0, xmm0
0x1800e4aed  movups  xmmword ptr [rax-38h], xmm0
0x1800e4af1  xor     r12d, r12d
0x1800e4af4  mov     [rax-40h], r12
0x1800e4af8  mov     [rax+20h], r12
0x1800e4afc  cmp     rcx, 0FFFFFFFF80000004h
0x1800e4b03  jz      loc_1800E4C60
0x1800e4b09  lea     r9, [rax+20h]
0x1800e4b0d  lea     r8, [rax-40h]
0x1800e4b11  lea     rdx, [rax+8]
0x1800e4b15  call    MapPredefinedHandleInternal
0x1800e4b1a  mov     ebx, eax
0x1800e4b1c  test    eax, eax
0x1800e4b1e  jnz     loc_1800E4C05
0x1800e4b24  mov     rdx, rdi; SourceString
0x1800e4b27  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1800e4b2c  call    cs:__imp_RtlInitUnicodeStringEx
0x1800e4b33  nop     dword ptr [rax+rax+00h]
0x1800e4b38  test    eax, eax
0x1800e4b3a  js      loc_1800E4C5C
0x1800e4b40  movzx   eax, [rsp+78h+DestinationString.Length]
0x1800e4b45  lea     r14d, [r12+2]
0x1800e4b4a  add     ax, r14w
0x1800e4b4e  mov     [rsp+78h+DestinationString.Length], ax
0x1800e4b53  mov     rdi, [rsp+78h+KeyHandle]
0x1800e4b5b  test    dil, 1
0x1800e4b5f  jnz     loc_1800E4D0A
0x1800e4b65  mov     ebx, r12d
0x1800e4b68  mov     [rsp+78h+KeyHandle], rbx
0x1800e4b70  mov     esi, r12d
0x1800e4b73  mov     [rsp+78h+arg_10], r12
0x1800e4b7b  cmp     ax, r14w
0x1800e4b7f  jb      loc_1800E4CCD
0x1800e4b85  test    al, 1
0x1800e4b87  jnz     loc_1800E4CCD
0x1800e4b8d  cmp     [rsp+78h+DestinationString.Buffer], r12
0x1800e4b92  jz      loc_1800E4CCD
0x1800e4b98  sub     ax, r14w
0x1800e4b9c  mov     [rsp+78h+DestinationString.Length], ax
0x1800e4ba1  call    IsTermsrvDeleteKeyPresent
0x1800e4ba6  test    al, al
0x1800e4ba8  jz      short loc_1800E4BBE
0x1800e4baa  lea     rdx, [rsp+78h+DestinationString]
0x1800e4baf  mov     rcx, rdi
0x1800e4bb2  call    cs:__imp_TermsrvDeleteValue
0x1800e4bb9  nop     dword ptr [rax+rax+00h]
0x1800e4bbe  mov     r15d, edi
0x1800e4bc1  and     r15d, r14d
0x1800e4bc4  jnz     short loc_1800E4C2F
0x1800e4bc6  mov     rcx, rdi; KeyHandle
0x1800e4bc9  test    rbx, rbx
0x1800e4bcc  jnz     loc_1800E4C88
0x1800e4bd2  lea     rdx, [rsp+78h+DestinationString]; ValueName
0x1800e4bd7  call    cs:__imp_NtDeleteValueKey
0x1800e4bde  nop     dword ptr [rax+rax+00h]
0x1800e4be3  mov     r14d, eax
0x1800e4be6  test    r15d, r15d
0x1800e4be9  jnz     loc_1800E4C94
0x1800e4bef  test    rbx, rbx
0x1800e4bf2  jnz     short loc_1800E4C67
0x1800e4bf4  mov     ecx, r14d; Status
0x1800e4bf7  call    cs:__imp_RtlNtStatusToDosError
0x1800e4bfe  nop     dword ptr [rax+rax+00h]
0x1800e4c03  mov     ebx, eax
0x1800e4c05  mov     rdx, [rsp+78h+arg_18]
0x1800e4c0d  mov     rcx, [rsp+78h+var_40]
0x1800e4c12  call    CLOSE_LOCAL_HANDLE_INTERNAL
0x1800e4c17  mov     eax, ebx
0x1800e4c19  mov     rbx, [rsp+78h+arg_8]
0x1800e4c21  add     rsp, 50h
0x1800e4c25  pop     r15
0x1800e4c27  pop     r14
0x1800e4c29  pop     r12
0x1800e4c2b  pop     rdi
0x1800e4c2c  pop     rsi
0x1800e4c2d  retn
0x1800e4c2f  lea     rax, [rsp+78h+KeyHandle]
0x1800e4c37  mov     [rsp+78h+var_58], rax
0x1800e4c3c  lea     r9, [rsp+78h+arg_10]
0x1800e4c44  mov     r8d, 2000000h
0x1800e4c4a  mov     rdx, rdi
0x1800e4c4d  xor     ecx, ecx
0x1800e4c4f  call    BaseRegGetUserAndMachineClass
0x1800e4c54  test    eax, eax
0x1800e4c56  jns     loc_1800E4CF5
0x1800e4c5c  mov     ecx, eax
0x1800e4c5e  jmp     short loc_1800E4BF7
0x1800e4c60  mov     eax, 6
0x1800e4c65  jmp     short loc_1800E4C19
0x1800e4c67  test    rsi, rsi
0x1800e4c6a  jz      short loc_1800E4BF4
0x1800e4c6c  cmp     rbx, rdi
0x1800e4c6f  mov     rcx, rbx
0x1800e4c72  jnz     short loc_1800E4C77
0x1800e4c74  mov     rcx, rsi; Handle
0x1800e4c77  call    cs:__imp_NtClose
0x1800e4c7e  nop     dword ptr [rax+rax+00h]
0x1800e4c83  jmp     loc_1800E4BF4
0x1800e4c88  test    rsi, rsi
0x1800e4c8b  cmovnz  rcx, rbx
0x1800e4c8f  jmp     loc_1800E4BD2
0x1800e4c94  cmp     eax, 0C0000034h
0x1800e4c99  jnz     loc_1800E4BEF
0x1800e4c9f  test    rbx, rbx
0x1800e4ca2  jz      loc_1800E4BF4
0x1800e4ca8  test    rsi, rsi
0x1800e4cab  jz      loc_1800E4BEF
0x1800e4cb1  lea     rdx, [rsp+78h+DestinationString]; ValueName
0x1800e4cb6  mov     rcx, rsi; KeyHandle
0x1800e4cb9  call    cs:__imp_NtDeleteValueKey
0x1800e4cc0  nop     dword ptr [rax+rax+00h]
0x1800e4cc5  mov     r14d, eax
0x1800e4cc8  jmp     loc_1800E4BEF
0x1800e4ccd  cmp     [rsp+78h+DestinationString.Buffer], r12
0x1800e4cd2  jnz     short loc_1800E4CEB
0x1800e4cd4  cmp     ax, r14w
0x1800e4cd8  jnz     short loc_1800E4CEB
0x1800e4cda  cmp     [rsp+78h+DestinationString.MaximumLength], r12w
0x1800e4ce0  jnz     short loc_1800E4CEB
0x1800e4ce2  movzx   eax, r14w
0x1800e4ce6  jmp     loc_1800E4B98
0x1800e4ceb  mov     ebx, 57h ; 'W'
0x1800e4cf0  jmp     loc_1800E4C05
0x1800e4cf5  mov     rbx, [rsp+78h+KeyHandle]
0x1800e4cfd  mov     rsi, [rsp+78h+arg_10]
0x1800e4d05  jmp     loc_1800E4BC6
0x1800e4d0a  call    IsBaseRegCloseKeyPresent
0x1800e4d0f  test    al, al
0x1800e4d11  jz      loc_1800E4C05
0x1800e4d17  and     rdi, 0FFFFFFFFFFFFFFFEh
0x1800e4d1b  lea     rdx, [rsp+78h+DestinationString]
0x1800e4d20  mov     rcx, rdi
0x1800e4d23  call    cs:__imp_BaseRegDeleteValue
0x1800e4d2a  nop     dword ptr [rax+rax+00h]
0x1800e4d2f  mov     ebx, eax
0x1800e4d31  mov     [rsp+78h+var_48], eax
0x1800e4d35  jmp     loc_1800E4C05
0x1800e4d3a  mov     ebx, eax
0x1800e4d3c  mov     [rsp+78h+var_48], eax
0x1800e4d40  jmp     loc_1800E4C05
```
