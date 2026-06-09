# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180015c74`
- end: `0x180015d99`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180015c4c`

## callees

- `0x18000e2f0`
- `0x180015a54`
- `0x180015c74`
- `0x180018010`

## string_xrefs

- `0x180015cc0`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  BOOL v7; // esi
  FARPROC NtDllProcedureAddress; // rax
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
  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
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
0x180015c74  mov     [rsp+arg_10], rbx
0x180015c79  push    rbp
0x180015c7a  push    rsi
0x180015c7b  push    rdi
0x180015c7c  sub     rsp, 50h
0x180015c80  mov     rax, cs:__security_cookie
0x180015c87  xor     rax, rsp
0x180015c8a  mov     [rsp+68h+var_20], rax
0x180015c8f  xor     esi, esi
0x180015c91  mov     [rsp+68h+var_38], 0
0x180015c9a  test    r8d, r8d
0x180015c9d  mov     rdi, r9
0x180015ca0  mov     ebp, edx
0x180015ca2  mov     rbx, rcx
0x180015ca5  setz    sil
0x180015ca9  xor     eax, eax
0x180015cab  mov     [rsp+68h+var_30], rax
0x180015cb0  mov     [rsp+68h+var_28], eax
0x180015cb4  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180015cbb  test    rax, rax
0x180015cbe  jnz     short loc_180015D14
0x180015cc0  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180015cc7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180015ccc  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180015cd3  test    rax, rax
0x180015cd6  jnz     short loc_180015D14
0x180015cd8  mov     r8d, 0C0000139h
0x180015cde  xor     r9d, r9d
0x180015ce1  test    rdi, rdi
0x180015ce4  jz      short loc_180015CF4
0x180015ce6  xor     ecx, ecx
0x180015ce8  cmp     r8d, 80000022h
0x180015cef  setnz   cl
0x180015cf2  mov     [rdi], ecx
0x180015cf4  mov     eax, r9d
0x180015cf7  mov     rcx, [rsp+68h+var_20]
0x180015cfc  xor     rcx, rsp; StackCookie
0x180015cff  call    __security_check_cookie
0x180015d04  mov     rbx, [rsp+68h+arg_10]
0x180015d0c  add     rsp, 50h
0x180015d10  pop     rdi
0x180015d11  pop     rsi
0x180015d12  pop     rbp
0x180015d13  retn
0x180015d14  lea     r9, [rsp+68h+var_30]
0x180015d19  mov     edx, esi
0x180015d1b  lea     r8, [rsp+68h+var_38]
0x180015d20  mov     ecx, ebp
0x180015d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d27  mov     r8d, eax
0x180015d2a  test    eax, eax
0x180015d2c  jnz     short loc_180015D76
0x180015d2e  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180015d32  lea     r9d, [r8+1]
0x180015d36  mov     eax, [rsp+68h+var_28]
0x180015d3a  mov     ecx, edx
0x180015d3c  mov     [rbx+0Ch], eax
0x180015d3f  mov     eax, edx
0x180015d41  shr     eax, 0Eh
0x180015d44  shr     ecx, 4
0x180015d47  and     eax, 3
0x180015d4a  and     ecx, 3
0x180015d4d  mov     [rbx+8], eax
0x180015d50  mov     [rbx], ecx
0x180015d52  mov     eax, edx
0x180015d54  mov     ecx, edx
0x180015d56  shr     eax, 6
0x180015d59  shr     ecx, 8
0x180015d5c  and     eax, r9d
0x180015d5f  and     cl, 3Fh
0x180015d62  shr     edx, 7
0x180015d65  and     edx, r9d
0x180015d68  mov     [rbx+4], cl
0x180015d6b  mov     [rbx+10h], edx
0x180015d6e  mov     [rbx+14h], eax
0x180015d71  jmp     loc_180015CE1
0x180015d76  cmp     eax, 117h
0x180015d7b  jnz     loc_180015CDE
0x180015d81  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180015d85  mov     r9d, 1
0x180015d8b  shr     eax, 7
0x180015d8e  and     eax, r9d
0x180015d91  mov     [rbx+10h], eax
0x180015d94  jmp     loc_180015CE1
```
