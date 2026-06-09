# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180015e1c`
- end: `0x180015f4f`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800163f0`

## callees

- `0x180015e1c`
- `0x180015f58`
- `0x1800292b0`
- `0x18002a010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  unsigned int v7; // [rsp+50h] [rbp-18h] BYREF

  v7 = a3;
  v3 = a2 & 1;
  v4 = a3;
  if ( a3 )
  {
    v4 = a3 - 1;
    if ( a3 == 1 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1);
      goto LABEL_17;
    }
    v4 = a3 - 2;
    if ( a3 == 2 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1) + 1;
      goto LABEL_17;
    }
    v4 = a3 - 3;
    if ( a3 == 3 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1) + 2;
      goto LABEL_17;
    }
    v4 = a3 - 4;
    if ( a3 == 4 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1) + 3;
      goto LABEL_17;
    }
    v4 = a3 - 5;
    if ( a3 == 5 )
    {
      v5 = 2 * (unsigned int)!(a2 & 1) + 8;
      goto LABEL_17;
    }
    if ( a3 == 6 )
    {
      v5 = 2 * (unsigned int)!(a2 & 1) + 9;
      goto LABEL_17;
    }
    if ( (unsigned __int8)(a3 - 100) <= 0x31u )
    {
      v5 = (unsigned __int8)(a3 - 100) + (v3 != 0 ? 100 : 150);
      goto LABEL_17;
    }
  }
  v5 = 255;
LABEL_17:
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil_details_FeatureReporting_ReportUsageToServiceDirect(
                                                                                                     v4,
                                                                                                     a2,
                                                                                                     v5);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(59485045, Feature_VPN_BugFixes_25C_RasmansDependency_logged_traits, 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180015e1c  push    rbx
0x180015e1e  sub     rsp, 60h
0x180015e22  mov     rax, cs:__security_cookie
0x180015e29  xor     rax, rsp
0x180015e2c  mov     [rsp+68h+var_10], rax
0x180015e31  mov     ebx, edx
0x180015e33  mov     [rsp+68h+var_18], r8d
0x180015e38  and     ebx, 1
0x180015e3b  mov     r9d, r8d
0x180015e3e  mov     ecx, r8d
0x180015e41  test    r8d, r8d
0x180015e44  jz      loc_180015EE9
0x180015e4a  sub     ecx, 1
0x180015e4d  jz      loc_180015EDC
0x180015e53  sub     ecx, 1
0x180015e56  jz      short loc_180015ECD
0x180015e58  sub     ecx, 1
0x180015e5b  jz      short loc_180015EBE
0x180015e5d  sub     ecx, 1
0x180015e60  jz      short loc_180015EAF
0x180015e62  sub     ecx, 1
0x180015e65  jz      short loc_180015EA0
0x180015e67  cmp     ecx, 1
0x180015e6a  jz      short loc_180015E91
0x180015e6c  sub     r9b, 64h ; 'd'
0x180015e70  cmp     r9b, 31h ; '1'
0x180015e74  ja      short loc_180015EE9
0x180015e76  mov     eax, ebx
0x180015e78  neg     eax
0x180015e7a  movzx   eax, r9b
0x180015e7e  sbb     r8d, r8d
0x180015e81  and     r8d, 0FFFFFFCEh
0x180015e85  add     r8d, 96h
0x180015e8c  add     r8d, eax
0x180015e8f  jmp     short loc_180015EEF
0x180015e91  mov     eax, ebx
0x180015e93  xor     eax, 1
0x180015e96  lea     r8d, ds:9[rax*2]
0x180015e9e  jmp     short loc_180015EEF
0x180015ea0  mov     eax, ebx
0x180015ea2  xor     eax, 1
0x180015ea5  lea     r8d, ds:8[rax*2]
0x180015ead  jmp     short loc_180015EEF
0x180015eaf  mov     eax, ebx
0x180015eb1  xor     eax, 1
0x180015eb4  lea     r8d, ds:3[rax*4]
0x180015ebc  jmp     short loc_180015EEF
0x180015ebe  mov     eax, ebx
0x180015ec0  xor     eax, 1
0x180015ec3  lea     r8d, ds:2[rax*4]
0x180015ecb  jmp     short loc_180015EEF
0x180015ecd  mov     eax, ebx
0x180015ecf  xor     eax, 1
0x180015ed2  lea     r8d, ds:1[rax*4]
0x180015eda  jmp     short loc_180015EEF
0x180015edc  mov     r8d, ebx
0x180015edf  xor     r8d, 1
0x180015ee3  shl     r8d, 2
0x180015ee7  jmp     short loc_180015EEF
0x180015ee9  mov     r8d, 0FFh
0x180015eef  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x180015ef4  test    eax, eax
0x180015ef6  jz      short loc_180015F3C
0x180015ef8  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180015eff  test    rax, rax
0x180015f02  jz      short loc_180015F3C
0x180015f04  mov     rdx, cs:off_18003C050
0x180015f0b  lea     rcx, [rsp+68h+var_18]
0x180015f10  mov     [rsp+68h+var_30], 1
0x180015f19  mov     r9d, ebx
0x180015f1c  mov     [rsp+68h+var_38], 0
0x180015f21  xor     r8d, r8d
0x180015f24  mov     [rsp+68h+var_40], 0
0x180015f2d  mov     [rsp+68h+var_48], rcx
0x180015f32  mov     ecx, 38BAB75h
0x180015f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f3c  mov     rcx, [rsp+68h+var_10]
0x180015f41  xor     rcx, rsp; StackCookie
0x180015f44  call    __security_check_cookie
0x180015f49  add     rsp, 60h
0x180015f4d  pop     rbx
0x180015f4e  retn
```
