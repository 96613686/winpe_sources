# KIsUnlockSettingEnabled

- ea: `0x140052a74`
- end: `0x140052b9f`
- name: `KIsUnlockSettingEnabled`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140052a24`

## callees

- `0x140025a94`
- `0x1400527d0`
- `0x1400528fc`
- `0x140052a74`

## import_xrefs

- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x140052afa`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x140052b57`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x140052afa`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x140052b57`

## string_xrefs

- `0x140052aab`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModelUnlock`
- `0x140052a9d`: `\Registry\Machine\SOFTWARE\Policies\Microsoft\Windows\Appx`

## pseudocode

```c
__int64 __fastcall KIsUnlockSettingEnabled(UNICODE_STRING *a1, unsigned int *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  UNICODE_STRING v14; // [rsp+20h] [rbp-48h] BYREF
  UNICODE_STRING v15; // [rsp+30h] [rbp-38h] BYREF
  UNICODE_STRING v16; // [rsp+40h] [rbp-28h] BYREF
  UNICODE_STRING v17; // [rsp+50h] [rbp-18h] BYREF

  *(_QWORD *)&v15.Length = 9830548;
  *(_QWORD *)&v14.Length = 7733364;
  v14.Buffer = L"\\Registry\\Machine\\SOFTWARE\\Policies\\Microsoft\\Windows\\Appx";
  *a2 = 0xFFFF;
  v15.Buffer = L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModelUnlock";
  v16 = 0;
  v17 = 0;
  v4 = KGetAppModelStateSeparatedRegKeyPath(
         (__int64)L"AppxPolicies",
         (__int64)L"\\Registry\\Machine\\SOFTWARE\\Policies\\Microsoft\\Windows\\Appx",
         &v17);
  if ( v4 >= 0 )
  {
    v4 = KGetUnlockSetting(&v17, a1, a2);
    if ( v4 >= 0 )
    {
      if ( !(unsigned __int8)RtlIsStateSeparationEnabled(v6, v5, v7, v8, *(_QWORD *)&v14.Length, v14.Buffer)
        || *a2 == 0xFFFF && (v4 = KGetUnlockSetting(&v14, a1, a2), v4 >= 0) )
      {
        if ( *a2 == 0xFFFF )
        {
          v4 = KGetAppModelStateSeparatedRegKeyPath(
                 (__int64)L"AppModelUnlock",
                 (__int64)L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModelUnlock",
                 &v16);
          if ( v4 >= 0 )
          {
            v4 = KGetUnlockSetting(&v16, a1, a2);
            if ( v4 >= 0
              && (unsigned __int8)RtlIsStateSeparationEnabled(v10, v9, v11, v12, *(_QWORD *)&v14.Length, v14.Buffer)
              && *a2 == 0xFFFF )
            {
              v4 = KGetUnlockSetting(&v15, a1, a2);
            }
          }
        }
      }
    }
  }
  AppModelFreeUnicodeString(&v16);
  AppModelFreeUnicodeString(&v17);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140052a74  push    rbp
0x140052a76  push    rbx
0x140052a77  push    rsi
0x140052a78  push    rdi
0x140052a79  push    r14
0x140052a7b  push    r15
0x140052a7d  mov     rbp, rsp
0x140052a80  sub     rsp, 68h
0x140052a84  mov     rdi, rdx
0x140052a87  mov     [rbp+var_38], 960094h
0x140052a8f  mov     rsi, rcx
0x140052a92  mov     [rbp+var_48], 760074h
0x140052a9a  xorps   xmm0, xmm0
0x140052a9d  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\SOFTWARE\\Policies"...
0x140052aa4  xorps   xmm1, xmm1
0x140052aa7  mov     [rbp+var_40], rdx
0x140052aab  lea     r15, aRegistryMachin_3; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x140052ab2  mov     r14d, 0FFFFh
0x140052ab8  lea     r8, [rbp+var_18]
0x140052abc  mov     [rdi], r14d
0x140052abf  lea     rcx, aAppxpolicies; "AppxPolicies"
0x140052ac6  mov     [rbp+var_30], r15
0x140052aca  movups  [rbp+var_28], xmm0
0x140052ace  movups  xmmword ptr [rbp+var_18.Length], xmm1
0x140052ad2  call    KGetAppModelStateSeparatedRegKeyPath
0x140052ad7  mov     ebx, eax
0x140052ad9  test    eax, eax
0x140052adb  js      loc_140052B7D
0x140052ae1  mov     r8, rdi
0x140052ae4  lea     rcx, [rbp+var_18]
0x140052ae8  mov     rdx, rsi
0x140052aeb  call    KGetUnlockSetting
0x140052af0  mov     ebx, eax
0x140052af2  test    eax, eax
0x140052af4  js      loc_140052B7D
0x140052afa  call    cs:__imp_RtlIsStateSeparationEnabled
0x140052b01  nop     dword ptr [rax+rax+00h]
0x140052b06  test    al, al
0x140052b08  jz      short loc_140052B24
0x140052b0a  cmp     [rdi], r14d
0x140052b0d  jnz     short loc_140052B7D
0x140052b0f  mov     r8, rdi
0x140052b12  lea     rcx, [rbp+var_48]
0x140052b16  mov     rdx, rsi
0x140052b19  call    KGetUnlockSetting
0x140052b1e  mov     ebx, eax
0x140052b20  test    eax, eax
0x140052b22  js      short loc_140052B7D
0x140052b24  cmp     [rdi], r14d
0x140052b27  jnz     short loc_140052B7D
0x140052b29  lea     r8, [rbp+var_28]
0x140052b2d  mov     rdx, r15
0x140052b30  lea     rcx, aAppmodelunlock; "AppModelUnlock"
0x140052b37  call    KGetAppModelStateSeparatedRegKeyPath
0x140052b3c  mov     ebx, eax
0x140052b3e  test    eax, eax
0x140052b40  js      short loc_140052B7D
0x140052b42  mov     r8, rdi
0x140052b45  lea     rcx, [rbp+var_28]
0x140052b49  mov     rdx, rsi
0x140052b4c  call    KGetUnlockSetting
0x140052b51  mov     ebx, eax
0x140052b53  test    eax, eax
0x140052b55  js      short loc_140052B7D
0x140052b57  call    cs:__imp_RtlIsStateSeparationEnabled
0x140052b5e  nop     dword ptr [rax+rax+00h]
0x140052b63  test    al, al
0x140052b65  jz      short loc_140052B7D
0x140052b67  cmp     [rdi], r14d
0x140052b6a  jnz     short loc_140052B7D
0x140052b6c  mov     r8, rdi
0x140052b6f  lea     rcx, [rbp+var_38]
0x140052b73  mov     rdx, rsi
0x140052b76  call    KGetUnlockSetting
0x140052b7b  mov     ebx, eax
0x140052b7d  lea     rcx, [rbp+var_28]
0x140052b81  call    AppModelFreeUnicodeString
0x140052b86  lea     rcx, [rbp+var_18]
0x140052b8a  call    AppModelFreeUnicodeString
0x140052b8f  mov     eax, ebx
0x140052b91  add     rsp, 68h
0x140052b95  pop     r15
0x140052b97  pop     r14
0x140052b99  pop     rdi
0x140052b9a  pop     rsi
0x140052b9b  pop     rbx
0x140052b9c  pop     rbp
0x140052b9d  retn
```
