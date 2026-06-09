# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000dea4`
- end: `0x18000dfc9`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000de7c`

## callees

- `0x180002a90`
- `0x180009b70`
- `0x18000dea4`
- `0x180038010`

## string_xrefs

- `0x18000def0`: `RtlQueryFeatureConfiguration`

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
0x18000dea4  mov     [rsp+arg_10], rbx
0x18000dea9  push    rbp
0x18000deaa  push    rsi
0x18000deab  push    rdi
0x18000deac  sub     rsp, 50h
0x18000deb0  mov     rax, cs:__security_cookie
0x18000deb7  xor     rax, rsp
0x18000deba  mov     [rsp+68h+var_20], rax
0x18000debf  xor     esi, esi
0x18000dec1  mov     [rsp+68h+var_38], 0
0x18000deca  test    r8d, r8d
0x18000decd  mov     rdi, r9
0x18000ded0  mov     ebp, edx
0x18000ded2  mov     rbx, rcx
0x18000ded5  setz    sil
0x18000ded9  xor     eax, eax
0x18000dedb  mov     [rsp+68h+var_30], rax
0x18000dee0  mov     [rsp+68h+var_28], eax
0x18000dee4  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000deeb  test    rax, rax
0x18000deee  jnz     short loc_18000DF44
0x18000def0  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000def7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000defc  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000df03  test    rax, rax
0x18000df06  jnz     short loc_18000DF44
0x18000df08  mov     r8d, 0C0000139h
0x18000df0e  xor     r9d, r9d
0x18000df11  test    rdi, rdi
0x18000df14  jz      short loc_18000DF24
0x18000df16  xor     ecx, ecx
0x18000df18  cmp     r8d, 80000022h
0x18000df1f  setnz   cl
0x18000df22  mov     [rdi], ecx
0x18000df24  mov     eax, r9d
0x18000df27  mov     rcx, [rsp+68h+var_20]
0x18000df2c  xor     rcx, rsp; StackCookie
0x18000df2f  call    __security_check_cookie
0x18000df34  mov     rbx, [rsp+68h+arg_10]
0x18000df3c  add     rsp, 50h
0x18000df40  pop     rdi
0x18000df41  pop     rsi
0x18000df42  pop     rbp
0x18000df43  retn
0x18000df44  lea     r9, [rsp+68h+var_30]
0x18000df49  mov     edx, esi
0x18000df4b  lea     r8, [rsp+68h+var_38]
0x18000df50  mov     ecx, ebp
0x18000df52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df57  mov     r8d, eax
0x18000df5a  test    eax, eax
0x18000df5c  jnz     short loc_18000DFA6
0x18000df5e  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000df62  lea     r9d, [r8+1]
0x18000df66  mov     eax, [rsp+68h+var_28]
0x18000df6a  mov     ecx, edx
0x18000df6c  mov     [rbx+0Ch], eax
0x18000df6f  mov     eax, edx
0x18000df71  shr     eax, 0Eh
0x18000df74  shr     ecx, 4
0x18000df77  and     eax, 3
0x18000df7a  and     ecx, 3
0x18000df7d  mov     [rbx+8], eax
0x18000df80  mov     [rbx], ecx
0x18000df82  mov     eax, edx
0x18000df84  mov     ecx, edx
0x18000df86  shr     eax, 6
0x18000df89  shr     ecx, 8
0x18000df8c  and     eax, r9d
0x18000df8f  and     cl, 3Fh
0x18000df92  shr     edx, 7
0x18000df95  and     edx, r9d
0x18000df98  mov     [rbx+4], cl
0x18000df9b  mov     [rbx+10h], edx
0x18000df9e  mov     [rbx+14h], eax
0x18000dfa1  jmp     loc_18000DF11
0x18000dfa6  cmp     eax, 117h
0x18000dfab  jnz     loc_18000DF0E
0x18000dfb1  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000dfb5  mov     r9d, 1
0x18000dfbb  shr     eax, 7
0x18000dfbe  and     eax, r9d
0x18000dfc1  mov     [rbx+10h], eax
0x18000dfc4  jmp     loc_18000DF11
```
