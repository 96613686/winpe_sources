# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000d0cc`
- end: `0x18000d1f1`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d0a4`

## callees

- `0x180001640`
- `0x18000cdb0`
- `0x18000d0cc`
- `0x180028010`

## string_xrefs

- `0x18000d118`: `RtlQueryFeatureConfiguration`

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
0x18000d0cc  mov     [rsp+arg_10], rbx
0x18000d0d1  push    rbp
0x18000d0d2  push    rsi
0x18000d0d3  push    rdi
0x18000d0d4  sub     rsp, 50h
0x18000d0d8  mov     rax, cs:__security_cookie
0x18000d0df  xor     rax, rsp
0x18000d0e2  mov     [rsp+68h+var_20], rax
0x18000d0e7  xor     esi, esi
0x18000d0e9  mov     [rsp+68h+var_38], 0
0x18000d0f2  test    r8d, r8d
0x18000d0f5  mov     rdi, r9
0x18000d0f8  mov     ebp, edx
0x18000d0fa  mov     rbx, rcx
0x18000d0fd  setz    sil
0x18000d101  xor     eax, eax
0x18000d103  mov     [rsp+68h+var_30], rax
0x18000d108  mov     [rsp+68h+var_28], eax
0x18000d10c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000d113  test    rax, rax
0x18000d116  jnz     short loc_18000D16C
0x18000d118  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000d11f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d124  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000d12b  test    rax, rax
0x18000d12e  jnz     short loc_18000D16C
0x18000d130  mov     r8d, 0C0000139h
0x18000d136  xor     r9d, r9d
0x18000d139  test    rdi, rdi
0x18000d13c  jz      short loc_18000D14C
0x18000d13e  xor     ecx, ecx
0x18000d140  cmp     r8d, 80000022h
0x18000d147  setnz   cl
0x18000d14a  mov     [rdi], ecx
0x18000d14c  mov     eax, r9d
0x18000d14f  mov     rcx, [rsp+68h+var_20]
0x18000d154  xor     rcx, rsp; StackCookie
0x18000d157  call    __security_check_cookie
0x18000d15c  mov     rbx, [rsp+68h+arg_10]
0x18000d164  add     rsp, 50h
0x18000d168  pop     rdi
0x18000d169  pop     rsi
0x18000d16a  pop     rbp
0x18000d16b  retn
0x18000d16c  lea     r9, [rsp+68h+var_30]
0x18000d171  mov     edx, esi
0x18000d173  lea     r8, [rsp+68h+var_38]
0x18000d178  mov     ecx, ebp
0x18000d17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d17f  mov     r8d, eax
0x18000d182  test    eax, eax
0x18000d184  jnz     short loc_18000D1CE
0x18000d186  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000d18a  lea     r9d, [r8+1]
0x18000d18e  mov     eax, [rsp+68h+var_28]
0x18000d192  mov     ecx, edx
0x18000d194  mov     [rbx+0Ch], eax
0x18000d197  mov     eax, edx
0x18000d199  shr     eax, 0Eh
0x18000d19c  shr     ecx, 4
0x18000d19f  and     eax, 3
0x18000d1a2  and     ecx, 3
0x18000d1a5  mov     [rbx+8], eax
0x18000d1a8  mov     [rbx], ecx
0x18000d1aa  mov     eax, edx
0x18000d1ac  mov     ecx, edx
0x18000d1ae  shr     eax, 6
0x18000d1b1  shr     ecx, 8
0x18000d1b4  and     eax, r9d
0x18000d1b7  and     cl, 3Fh
0x18000d1ba  shr     edx, 7
0x18000d1bd  and     edx, r9d
0x18000d1c0  mov     [rbx+4], cl
0x18000d1c3  mov     [rbx+10h], edx
0x18000d1c6  mov     [rbx+14h], eax
0x18000d1c9  jmp     loc_18000D139
0x18000d1ce  cmp     eax, 117h
0x18000d1d3  jnz     loc_18000D136
0x18000d1d9  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000d1dd  mov     r9d, 1
0x18000d1e3  shr     eax, 7
0x18000d1e6  and     eax, r9d
0x18000d1e9  mov     [rbx+10h], eax
0x18000d1ec  jmp     loc_18000D139
```
