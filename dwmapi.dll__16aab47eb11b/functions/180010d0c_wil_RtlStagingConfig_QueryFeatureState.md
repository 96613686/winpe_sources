# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180010d0c`
- end: `0x180010e31`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000f24c`

## callees

- `0x180009b4c`
- `0x18000d0a0`
- `0x180010d0c`
- `0x180017010`

## string_xrefs

- `0x180010d58`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  BOOL v7; // esi
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v9; // r8d
  unsigned int v10; // r9d
  int v12; // eax
  unsigned int v13; // edx
  unsigned int v14; // ecx
  __int64 v15; // [rsp+30h] [rbp-38h] BYREF
  __int64 v16; // [rsp+38h] [rbp-30h] BYREF
  int v17; // [rsp+40h] [rbp-28h]

  v15 = 0;
  v7 = a3 == 0;
  v16 = 0;
  v17 = 0;
  NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress;
    if ( !NtDllProcedureAddress )
    {
      v9 = -1073741511;
LABEL_4:
      v10 = 0;
      goto LABEL_5;
    }
  }
  v12 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))NtDllProcedureAddress)(a2, v7, &v15, &v16);
  v9 = v12;
  if ( v12 )
  {
    if ( v12 != 279 )
      goto LABEL_4;
    v10 = 1;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v16) >> 7) & 1;
  }
  else
  {
    v13 = HIDWORD(v16);
    v10 = 1;
    v14 = HIDWORD(v16);
    *(_DWORD *)(a1 + 12) = v17;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v14 >> 14;
    *(_DWORD *)a1 = (v14 >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v13) & 0x3F;
    *(_DWORD *)(a1 + 16) = (v13 >> 7) & 1;
    *(_DWORD *)(a1 + 20) = (v13 >> 6) & 1;
  }
LABEL_5:
  if ( a4 )
    *a4 = v9 != -2147483614;
  return v10;
}

```

## disassembly

```asm
0x180010d0c  mov     [rsp+arg_10], rbx
0x180010d11  push    rbp
0x180010d12  push    rsi
0x180010d13  push    rdi
0x180010d14  sub     rsp, 50h
0x180010d18  mov     rax, cs:__security_cookie
0x180010d1f  xor     rax, rsp
0x180010d22  mov     [rsp+68h+var_20], rax
0x180010d27  xor     esi, esi
0x180010d29  mov     [rsp+68h+var_38], 0
0x180010d32  test    r8d, r8d
0x180010d35  mov     rdi, r9
0x180010d38  mov     ebp, edx
0x180010d3a  mov     rbx, rcx
0x180010d3d  setz    sil
0x180010d41  xor     eax, eax
0x180010d43  mov     [rsp+68h+var_30], rax
0x180010d48  mov     [rsp+68h+var_28], eax
0x180010d4c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180010d53  test    rax, rax
0x180010d56  jnz     short loc_180010DAC
0x180010d58  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180010d5f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180010d64  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180010d6b  test    rax, rax
0x180010d6e  jnz     short loc_180010DAC
0x180010d70  mov     r8d, 0C0000139h
0x180010d76  xor     r9d, r9d
0x180010d79  test    rdi, rdi
0x180010d7c  jz      short loc_180010D8C
0x180010d7e  xor     ecx, ecx
0x180010d80  cmp     r8d, 80000022h
0x180010d87  setnz   cl
0x180010d8a  mov     [rdi], ecx
0x180010d8c  mov     eax, r9d
0x180010d8f  mov     rcx, [rsp+68h+var_20]
0x180010d94  xor     rcx, rsp; StackCookie
0x180010d97  call    __security_check_cookie
0x180010d9c  mov     rbx, [rsp+68h+arg_10]
0x180010da4  add     rsp, 50h
0x180010da8  pop     rdi
0x180010da9  pop     rsi
0x180010daa  pop     rbp
0x180010dab  retn
0x180010dac  lea     r9, [rsp+68h+var_30]
0x180010db1  mov     edx, esi
0x180010db3  lea     r8, [rsp+68h+var_38]
0x180010db8  mov     ecx, ebp
0x180010dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dbf  mov     r8d, eax
0x180010dc2  test    eax, eax
0x180010dc4  jnz     short loc_180010E0E
0x180010dc6  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180010dca  lea     r9d, [r8+1]
0x180010dce  mov     eax, [rsp+68h+var_28]
0x180010dd2  mov     ecx, edx
0x180010dd4  mov     [rbx+0Ch], eax
0x180010dd7  mov     eax, edx
0x180010dd9  shr     eax, 0Eh
0x180010ddc  shr     ecx, 4
0x180010ddf  and     eax, 3
0x180010de2  and     ecx, 3
0x180010de5  mov     [rbx+8], eax
0x180010de8  mov     [rbx], ecx
0x180010dea  mov     eax, edx
0x180010dec  mov     ecx, edx
0x180010dee  shr     eax, 6
0x180010df1  shr     ecx, 8
0x180010df4  and     eax, r9d
0x180010df7  and     cl, 3Fh
0x180010dfa  shr     edx, 7
0x180010dfd  and     edx, r9d
0x180010e00  mov     [rbx+4], cl
0x180010e03  mov     [rbx+10h], edx
0x180010e06  mov     [rbx+14h], eax
0x180010e09  jmp     loc_180010D79
0x180010e0e  cmp     eax, 117h
0x180010e13  jnz     loc_180010D76
0x180010e19  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180010e1d  mov     r9d, 1
0x180010e23  shr     eax, 7
0x180010e26  and     eax, r9d
0x180010e29  mov     [rbx+10h], eax
0x180010e2c  jmp     loc_180010D79
```
