# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000f2a8`
- end: `0x18000f39b`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `243`
- prototype: `__int64 __fastcall(__int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000f158`

## callees

- `0x18000f2a8`
- `0x1800186f4`
- `0x180019ad0`
- `0x180035010`

## string_xrefs

- `0x18000f2f3`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3)
{
  BOOL v5; // edi
  __int64 (__fastcall *NtDllProcedureAddress)(_QWORD, BOOL, __int64 *, __int64 *); // rax
  unsigned int v7; // edx
  int v8; // eax
  unsigned int v9; // ecx
  __int64 v11; // [rsp+30h] [rbp-28h] BYREF
  __int64 v12; // [rsp+38h] [rbp-20h] BYREF
  int v13; // [rsp+40h] [rbp-18h]

  v11 = 0;
  v5 = a3 == 0;
  v12 = 0;
  v13 = 0;
  NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( g_wil_details_pfnRtlQueryFeatureConfiguration
    || (NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))wil_details_GetNtDllProcedureAddress(
                                                                                              "RtlQueryFeatureConfiguration"),
        (g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress) != 0) )
  {
    v8 = NtDllProcedureAddress(a2, v5, &v11, &v12);
    if ( v8 )
    {
      v7 = 0;
      if ( v8 != 279 )
        return v7;
      v9 = HIDWORD(v12);
      v7 = 1;
    }
    else
    {
      v9 = HIDWORD(v12);
      v7 = 1;
      *(_DWORD *)a1 = (HIDWORD(v12) >> 4) & 3;
      *(_BYTE *)(a1 + 4) = BYTE1(v9) & 0x3F;
      *(_DWORD *)(a1 + 12) = v13;
      *(_DWORD *)(a1 + 8) = (unsigned __int16)v9 >> 14;
      *(_DWORD *)(a1 + 20) = (v9 >> 6) & 1;
    }
    *(_DWORD *)(a1 + 16) = (v9 >> 7) & 1;
    return v7;
  }
  return 0;
}

```

## disassembly

```asm
0x18000f2a8  mov     r11, rsp
0x18000f2ab  mov     [r11+18h], rbx
0x18000f2af  mov     [r11+20h], rsi
0x18000f2b3  push    rdi
0x18000f2b4  sub     rsp, 50h
0x18000f2b8  mov     rax, cs:__security_cookie
0x18000f2bf  xor     rax, rsp
0x18000f2c2  mov     [rsp+58h+var_10], rax
0x18000f2c7  xor     edi, edi
0x18000f2c9  mov     qword ptr [r11-28h], 0
0x18000f2d1  test    r8d, r8d
0x18000f2d4  mov     esi, edx
0x18000f2d6  mov     rbx, rcx
0x18000f2d9  setz    dil
0x18000f2dd  xor     eax, eax
0x18000f2df  mov     [r11-20h], rax
0x18000f2e3  mov     [rsp+58h+var_18], eax
0x18000f2e7  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000f2ee  test    rax, rax
0x18000f2f1  jnz     short loc_18000F30F
0x18000f2f3  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000f2fa  call    wil_details_GetNtDllProcedureAddress
0x18000f2ff  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000f306  test    rax, rax
0x18000f309  jnz     short loc_18000F30F
0x18000f30b  xor     edx, edx
0x18000f30d  jmp     short loc_18000F37B
0x18000f30f  lea     r9, [rsp+58h+var_20]
0x18000f314  mov     edx, edi
0x18000f316  lea     r8, [rsp+58h+var_28]
0x18000f31b  mov     ecx, esi
0x18000f31d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f322  test    eax, eax
0x18000f324  jnz     short loc_18000F361
0x18000f326  mov     ecx, [rsp+58h+var_1C]
0x18000f32a  mov     edx, 1
0x18000f32f  mov     eax, ecx
0x18000f331  shr     eax, 4
0x18000f334  and     eax, 3
0x18000f337  mov     [rbx], eax
0x18000f339  mov     eax, ecx
0x18000f33b  shr     eax, 8
0x18000f33e  and     al, 3Fh
0x18000f340  mov     [rbx+4], al
0x18000f343  mov     eax, [rsp+58h+var_18]
0x18000f347  mov     [rbx+0Ch], eax
0x18000f34a  mov     eax, ecx
0x18000f34c  shr     eax, 0Eh
0x18000f34f  and     eax, 3
0x18000f352  mov     [rbx+8], eax
0x18000f355  mov     eax, ecx
0x18000f357  shr     eax, 6
0x18000f35a  and     eax, edx
0x18000f35c  mov     [rbx+14h], eax
0x18000f35f  jmp     short loc_18000F373
0x18000f361  xor     edx, edx
0x18000f363  cmp     eax, 117h
0x18000f368  jnz     short loc_18000F37B
0x18000f36a  mov     ecx, [rsp+58h+var_1C]
0x18000f36e  mov     edx, 1
0x18000f373  shr     ecx, 7
0x18000f376  and     ecx, edx
0x18000f378  mov     [rbx+10h], ecx
0x18000f37b  mov     eax, edx
0x18000f37d  mov     rcx, [rsp+58h+var_10]
0x18000f382  xor     rcx, rsp; StackCookie
0x18000f385  call    __security_check_cookie
0x18000f38a  mov     rbx, [rsp+58h+arg_10]
0x18000f38f  mov     rsi, [rsp+58h+arg_18]
0x18000f394  add     rsp, 50h
0x18000f398  pop     rdi
0x18000f399  retn
```
