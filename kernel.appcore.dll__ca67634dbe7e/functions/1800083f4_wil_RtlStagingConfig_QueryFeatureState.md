# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1800083f4`
- end: `0x1800084e6`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180008c20`

## callees

- `0x1800083f4`
- `0x180008d34`
- `0x180009dd0`
- `0x18000a010`

## string_xrefs

- `0x18000843f`: `RtlQueryFeatureConfiguration`

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
0x1800083f4  mov     r11, rsp
0x1800083f7  mov     [r11+18h], rbx
0x1800083fb  mov     [r11+20h], rsi
0x1800083ff  push    rdi
0x180008400  sub     rsp, 50h
0x180008404  mov     rax, cs:__security_cookie
0x18000840b  xor     rax, rsp
0x18000840e  mov     [rsp+58h+var_10], rax
0x180008413  xor     edi, edi
0x180008415  mov     qword ptr [r11-28h], 0
0x18000841d  test    r8d, r8d
0x180008420  mov     esi, edx
0x180008422  mov     rbx, rcx
0x180008425  setz    dil
0x180008429  xor     eax, eax
0x18000842b  mov     [r11-20h], rax
0x18000842f  mov     [rsp+58h+var_18], eax
0x180008433  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000843a  test    rax, rax
0x18000843d  jnz     short loc_18000845B
0x18000843f  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180008446  call    wil_details_GetNtDllProcedureAddress
0x18000844b  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180008452  test    rax, rax
0x180008455  jnz     short loc_18000845B
0x180008457  xor     edx, edx
0x180008459  jmp     short loc_1800084C7
0x18000845b  lea     r9, [rsp+58h+var_20]
0x180008460  mov     edx, edi
0x180008462  lea     r8, [rsp+58h+var_28]
0x180008467  mov     ecx, esi
0x180008469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000846e  test    eax, eax
0x180008470  jnz     short loc_1800084AD
0x180008472  mov     ecx, [rsp+58h+var_1C]
0x180008476  mov     edx, 1
0x18000847b  mov     eax, ecx
0x18000847d  shr     eax, 4
0x180008480  and     eax, 3
0x180008483  mov     [rbx], eax
0x180008485  mov     eax, ecx
0x180008487  shr     eax, 8
0x18000848a  and     al, 3Fh
0x18000848c  mov     [rbx+4], al
0x18000848f  mov     eax, [rsp+58h+var_18]
0x180008493  mov     [rbx+0Ch], eax
0x180008496  mov     eax, ecx
0x180008498  shr     eax, 0Eh
0x18000849b  and     eax, 3
0x18000849e  mov     [rbx+8], eax
0x1800084a1  mov     eax, ecx
0x1800084a3  shr     eax, 6
0x1800084a6  and     eax, edx
0x1800084a8  mov     [rbx+14h], eax
0x1800084ab  jmp     short loc_1800084BF
0x1800084ad  xor     edx, edx
0x1800084af  cmp     eax, 117h
0x1800084b4  jnz     short loc_1800084C7
0x1800084b6  mov     ecx, [rsp+58h+var_1C]
0x1800084ba  mov     edx, 1
0x1800084bf  shr     ecx, 7
0x1800084c2  and     ecx, edx
0x1800084c4  mov     [rbx+10h], ecx
0x1800084c7  mov     eax, edx
0x1800084c9  mov     rcx, [rsp+58h+var_10]
0x1800084ce  xor     rcx, rsp; StackCookie
0x1800084d1  call    __security_check_cookie
0x1800084d6  mov     rbx, [rsp+58h+arg_10]
0x1800084db  mov     rsi, [rsp+58h+arg_18]
0x1800084e0  add     rsp, 50h
0x1800084e4  pop     rdi
0x1800084e5  retn
```
