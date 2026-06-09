# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000e778`
- end: `0x18000e89d`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180009688`

## callees

- `0x180001bb0`
- `0x18000dd70`
- `0x18000e778`
- `0x18002d010`

## string_xrefs

- `0x18000e7c4`: `RtlQueryFeatureConfiguration`

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
0x18000e778  mov     [rsp+arg_10], rbx
0x18000e77d  push    rbp
0x18000e77e  push    rsi
0x18000e77f  push    rdi
0x18000e780  sub     rsp, 50h
0x18000e784  mov     rax, cs:__security_cookie
0x18000e78b  xor     rax, rsp
0x18000e78e  mov     [rsp+68h+var_20], rax
0x18000e793  xor     esi, esi
0x18000e795  mov     [rsp+68h+var_38], 0
0x18000e79e  test    r8d, r8d
0x18000e7a1  mov     rdi, r9
0x18000e7a4  mov     ebp, edx
0x18000e7a6  mov     rbx, rcx
0x18000e7a9  setz    sil
0x18000e7ad  xor     eax, eax
0x18000e7af  mov     [rsp+68h+var_30], rax
0x18000e7b4  mov     [rsp+68h+var_28], eax
0x18000e7b8  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000e7bf  test    rax, rax
0x18000e7c2  jnz     short loc_18000E818
0x18000e7c4  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000e7cb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000e7d0  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000e7d7  test    rax, rax
0x18000e7da  jnz     short loc_18000E818
0x18000e7dc  mov     r8d, 0C0000139h
0x18000e7e2  xor     r9d, r9d
0x18000e7e5  test    rdi, rdi
0x18000e7e8  jz      short loc_18000E7F8
0x18000e7ea  xor     ecx, ecx
0x18000e7ec  cmp     r8d, 80000022h
0x18000e7f3  setnz   cl
0x18000e7f6  mov     [rdi], ecx
0x18000e7f8  mov     eax, r9d
0x18000e7fb  mov     rcx, [rsp+68h+var_20]
0x18000e800  xor     rcx, rsp; StackCookie
0x18000e803  call    __security_check_cookie
0x18000e808  mov     rbx, [rsp+68h+arg_10]
0x18000e810  add     rsp, 50h
0x18000e814  pop     rdi
0x18000e815  pop     rsi
0x18000e816  pop     rbp
0x18000e817  retn
0x18000e818  lea     r9, [rsp+68h+var_30]
0x18000e81d  mov     edx, esi
0x18000e81f  lea     r8, [rsp+68h+var_38]
0x18000e824  mov     ecx, ebp
0x18000e826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e82b  mov     r8d, eax
0x18000e82e  test    eax, eax
0x18000e830  jnz     short loc_18000E87A
0x18000e832  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000e836  lea     r9d, [r8+1]
0x18000e83a  mov     eax, [rsp+68h+var_28]
0x18000e83e  mov     ecx, edx
0x18000e840  mov     [rbx+0Ch], eax
0x18000e843  mov     eax, edx
0x18000e845  shr     eax, 0Eh
0x18000e848  shr     ecx, 4
0x18000e84b  and     eax, 3
0x18000e84e  and     ecx, 3
0x18000e851  mov     [rbx+8], eax
0x18000e854  mov     [rbx], ecx
0x18000e856  mov     eax, edx
0x18000e858  mov     ecx, edx
0x18000e85a  shr     eax, 6
0x18000e85d  shr     ecx, 8
0x18000e860  and     eax, r9d
0x18000e863  and     cl, 3Fh
0x18000e866  shr     edx, 7
0x18000e869  and     edx, r9d
0x18000e86c  mov     [rbx+4], cl
0x18000e86f  mov     [rbx+10h], edx
0x18000e872  mov     [rbx+14h], eax
0x18000e875  jmp     loc_18000E7E5
0x18000e87a  cmp     eax, 117h
0x18000e87f  jnz     loc_18000E7E2
0x18000e885  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000e889  mov     r9d, 1
0x18000e88f  shr     eax, 7
0x18000e892  and     eax, r9d
0x18000e895  mov     [rbx+10h], eax
0x18000e898  jmp     loc_18000E7E5
```
