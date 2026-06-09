# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180007cfc`
- end: `0x180007e21`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180007c14`

## callees

- `0x180007cfc`
- `0x18000a398`
- `0x18000b410`
- `0x180015010`

## string_xrefs

- `0x180007d48`: `RtlQueryFeatureConfiguration`

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
0x180007cfc  mov     [rsp+arg_10], rbx
0x180007d01  push    rbp
0x180007d02  push    rsi
0x180007d03  push    rdi
0x180007d04  sub     rsp, 50h
0x180007d08  mov     rax, cs:__security_cookie
0x180007d0f  xor     rax, rsp
0x180007d12  mov     [rsp+68h+var_20], rax
0x180007d17  xor     esi, esi
0x180007d19  mov     [rsp+68h+var_38], 0
0x180007d22  test    r8d, r8d
0x180007d25  mov     rdi, r9
0x180007d28  mov     ebp, edx
0x180007d2a  mov     rbx, rcx
0x180007d2d  setz    sil
0x180007d31  xor     eax, eax
0x180007d33  mov     [rsp+68h+var_30], rax
0x180007d38  mov     [rsp+68h+var_28], eax
0x180007d3c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180007d43  test    rax, rax
0x180007d46  jnz     short loc_180007D9C
0x180007d48  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180007d4f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180007d54  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180007d5b  test    rax, rax
0x180007d5e  jnz     short loc_180007D9C
0x180007d60  mov     r8d, 0C0000139h
0x180007d66  xor     r9d, r9d
0x180007d69  test    rdi, rdi
0x180007d6c  jz      short loc_180007D7C
0x180007d6e  xor     ecx, ecx
0x180007d70  cmp     r8d, 80000022h
0x180007d77  setnz   cl
0x180007d7a  mov     [rdi], ecx
0x180007d7c  mov     eax, r9d
0x180007d7f  mov     rcx, [rsp+68h+var_20]
0x180007d84  xor     rcx, rsp; StackCookie
0x180007d87  call    __security_check_cookie
0x180007d8c  mov     rbx, [rsp+68h+arg_10]
0x180007d94  add     rsp, 50h
0x180007d98  pop     rdi
0x180007d99  pop     rsi
0x180007d9a  pop     rbp
0x180007d9b  retn
0x180007d9c  lea     r9, [rsp+68h+var_30]
0x180007da1  mov     edx, esi
0x180007da3  lea     r8, [rsp+68h+var_38]
0x180007da8  mov     ecx, ebp
0x180007daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007daf  mov     r8d, eax
0x180007db2  test    eax, eax
0x180007db4  jnz     short loc_180007DFE
0x180007db6  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180007dba  lea     r9d, [r8+1]
0x180007dbe  mov     eax, [rsp+68h+var_28]
0x180007dc2  mov     ecx, edx
0x180007dc4  mov     [rbx+0Ch], eax
0x180007dc7  mov     eax, edx
0x180007dc9  shr     eax, 0Eh
0x180007dcc  shr     ecx, 4
0x180007dcf  and     eax, 3
0x180007dd2  and     ecx, 3
0x180007dd5  mov     [rbx+8], eax
0x180007dd8  mov     [rbx], ecx
0x180007dda  mov     eax, edx
0x180007ddc  mov     ecx, edx
0x180007dde  shr     eax, 6
0x180007de1  shr     ecx, 8
0x180007de4  and     eax, r9d
0x180007de7  and     cl, 3Fh
0x180007dea  shr     edx, 7
0x180007ded  and     edx, r9d
0x180007df0  mov     [rbx+4], cl
0x180007df3  mov     [rbx+10h], edx
0x180007df6  mov     [rbx+14h], eax
0x180007df9  jmp     loc_180007D69
0x180007dfe  cmp     eax, 117h
0x180007e03  jnz     loc_180007D66
0x180007e09  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180007e0d  mov     r9d, 1
0x180007e13  shr     eax, 7
0x180007e16  and     eax, r9d
0x180007e19  mov     [rbx+10h], eax
0x180007e1c  jmp     loc_180007D69
```
