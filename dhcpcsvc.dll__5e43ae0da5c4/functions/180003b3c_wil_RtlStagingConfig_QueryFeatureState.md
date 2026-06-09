# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180003b3c`
- end: `0x180003c2e`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800036c8`

## callees

- `0x180003b3c`
- `0x180003c34`
- `0x1800048c0`
- `0x180014010`

## string_xrefs

- `0x180003b87`: `RtlQueryFeatureConfiguration`

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
0x180003b3c  mov     r11, rsp
0x180003b3f  mov     [r11+18h], rbx
0x180003b43  mov     [r11+20h], rsi
0x180003b47  push    rdi
0x180003b48  sub     rsp, 50h
0x180003b4c  mov     rax, cs:__security_cookie
0x180003b53  xor     rax, rsp
0x180003b56  mov     [rsp+58h+var_10], rax
0x180003b5b  xor     edi, edi
0x180003b5d  mov     qword ptr [r11-28h], 0
0x180003b65  test    r8d, r8d
0x180003b68  mov     esi, edx
0x180003b6a  mov     rbx, rcx
0x180003b6d  setz    dil
0x180003b71  xor     eax, eax
0x180003b73  mov     [r11-20h], rax
0x180003b77  mov     [rsp+58h+var_18], eax
0x180003b7b  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180003b82  test    rax, rax
0x180003b85  jnz     short loc_180003BA3
0x180003b87  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180003b8e  call    wil_details_GetNtDllProcedureAddress
0x180003b93  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180003b9a  test    rax, rax
0x180003b9d  jnz     short loc_180003BA3
0x180003b9f  xor     edx, edx
0x180003ba1  jmp     short loc_180003C0F
0x180003ba3  lea     r9, [rsp+58h+var_20]
0x180003ba8  mov     edx, edi
0x180003baa  lea     r8, [rsp+58h+var_28]
0x180003baf  mov     ecx, esi
0x180003bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bb6  test    eax, eax
0x180003bb8  jnz     short loc_180003BF5
0x180003bba  mov     ecx, [rsp+58h+var_1C]
0x180003bbe  mov     edx, 1
0x180003bc3  mov     eax, ecx
0x180003bc5  shr     eax, 4
0x180003bc8  and     eax, 3
0x180003bcb  mov     [rbx], eax
0x180003bcd  mov     eax, ecx
0x180003bcf  shr     eax, 8
0x180003bd2  and     al, 3Fh
0x180003bd4  mov     [rbx+4], al
0x180003bd7  mov     eax, [rsp+58h+var_18]
0x180003bdb  mov     [rbx+0Ch], eax
0x180003bde  mov     eax, ecx
0x180003be0  shr     eax, 0Eh
0x180003be3  and     eax, 3
0x180003be6  mov     [rbx+8], eax
0x180003be9  mov     eax, ecx
0x180003beb  shr     eax, 6
0x180003bee  and     eax, edx
0x180003bf0  mov     [rbx+14h], eax
0x180003bf3  jmp     short loc_180003C07
0x180003bf5  xor     edx, edx
0x180003bf7  cmp     eax, 117h
0x180003bfc  jnz     short loc_180003C0F
0x180003bfe  mov     ecx, [rsp+58h+var_1C]
0x180003c02  mov     edx, 1
0x180003c07  shr     ecx, 7
0x180003c0a  and     ecx, edx
0x180003c0c  mov     [rbx+10h], ecx
0x180003c0f  mov     eax, edx
0x180003c11  mov     rcx, [rsp+58h+var_10]
0x180003c16  xor     rcx, rsp; StackCookie
0x180003c19  call    __security_check_cookie
0x180003c1e  mov     rbx, [rsp+58h+arg_10]
0x180003c23  mov     rsi, [rsp+58h+arg_18]
0x180003c28  add     rsp, 50h
0x180003c2c  pop     rdi
0x180003c2d  retn
```
