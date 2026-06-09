# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000cf84`
- end: `0x18000d0a9`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000cf5c`

## callees

- `0x180004de0`
- `0x18000cc50`
- `0x18000cf84`
- `0x180028010`

## string_xrefs

- `0x18000cfd0`: `RtlQueryFeatureConfiguration`

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
0x18000cf84  mov     [rsp+arg_10], rbx
0x18000cf89  push    rbp
0x18000cf8a  push    rsi
0x18000cf8b  push    rdi
0x18000cf8c  sub     rsp, 50h
0x18000cf90  mov     rax, cs:__security_cookie
0x18000cf97  xor     rax, rsp
0x18000cf9a  mov     [rsp+68h+var_20], rax
0x18000cf9f  xor     esi, esi
0x18000cfa1  mov     [rsp+68h+var_38], 0
0x18000cfaa  test    r8d, r8d
0x18000cfad  mov     rdi, r9
0x18000cfb0  mov     ebp, edx
0x18000cfb2  mov     rbx, rcx
0x18000cfb5  setz    sil
0x18000cfb9  xor     eax, eax
0x18000cfbb  mov     [rsp+68h+var_30], rax
0x18000cfc0  mov     [rsp+68h+var_28], eax
0x18000cfc4  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000cfcb  test    rax, rax
0x18000cfce  jnz     short loc_18000D024
0x18000cfd0  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000cfd7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000cfdc  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000cfe3  test    rax, rax
0x18000cfe6  jnz     short loc_18000D024
0x18000cfe8  mov     r8d, 0C0000139h
0x18000cfee  xor     r9d, r9d
0x18000cff1  test    rdi, rdi
0x18000cff4  jz      short loc_18000D004
0x18000cff6  xor     ecx, ecx
0x18000cff8  cmp     r8d, 80000022h
0x18000cfff  setnz   cl
0x18000d002  mov     [rdi], ecx
0x18000d004  mov     eax, r9d
0x18000d007  mov     rcx, [rsp+68h+var_20]
0x18000d00c  xor     rcx, rsp; StackCookie
0x18000d00f  call    __security_check_cookie
0x18000d014  mov     rbx, [rsp+68h+arg_10]
0x18000d01c  add     rsp, 50h
0x18000d020  pop     rdi
0x18000d021  pop     rsi
0x18000d022  pop     rbp
0x18000d023  retn
0x18000d024  lea     r9, [rsp+68h+var_30]
0x18000d029  mov     edx, esi
0x18000d02b  lea     r8, [rsp+68h+var_38]
0x18000d030  mov     ecx, ebp
0x18000d032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d037  mov     r8d, eax
0x18000d03a  test    eax, eax
0x18000d03c  jnz     short loc_18000D086
0x18000d03e  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000d042  lea     r9d, [r8+1]
0x18000d046  mov     eax, [rsp+68h+var_28]
0x18000d04a  mov     ecx, edx
0x18000d04c  mov     [rbx+0Ch], eax
0x18000d04f  mov     eax, edx
0x18000d051  shr     eax, 0Eh
0x18000d054  shr     ecx, 4
0x18000d057  and     eax, 3
0x18000d05a  and     ecx, 3
0x18000d05d  mov     [rbx+8], eax
0x18000d060  mov     [rbx], ecx
0x18000d062  mov     eax, edx
0x18000d064  mov     ecx, edx
0x18000d066  shr     eax, 6
0x18000d069  shr     ecx, 8
0x18000d06c  and     eax, r9d
0x18000d06f  and     cl, 3Fh
0x18000d072  shr     edx, 7
0x18000d075  and     edx, r9d
0x18000d078  mov     [rbx+4], cl
0x18000d07b  mov     [rbx+10h], edx
0x18000d07e  mov     [rbx+14h], eax
0x18000d081  jmp     loc_18000CFF1
0x18000d086  cmp     eax, 117h
0x18000d08b  jnz     loc_18000CFEE
0x18000d091  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000d095  mov     r9d, 1
0x18000d09b  shr     eax, 7
0x18000d09e  and     eax, r9d
0x18000d0a1  mov     [rbx+10h], eax
0x18000d0a4  jmp     loc_18000CFF1
```
