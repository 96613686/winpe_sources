# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180015e0c`
- end: `0x180015f31`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e0b0`

## callees

- `0x18000bd6c`
- `0x18000fa10`
- `0x180015e0c`
- `0x180018010`

## string_xrefs

- `0x180015e58`: `RtlQueryFeatureConfiguration`

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
0x180015e0c  mov     [rsp+arg_10], rbx
0x180015e11  push    rbp
0x180015e12  push    rsi
0x180015e13  push    rdi
0x180015e14  sub     rsp, 50h
0x180015e18  mov     rax, cs:__security_cookie
0x180015e1f  xor     rax, rsp
0x180015e22  mov     [rsp+68h+var_20], rax
0x180015e27  xor     esi, esi
0x180015e29  mov     [rsp+68h+var_38], 0
0x180015e32  test    r8d, r8d
0x180015e35  mov     rdi, r9
0x180015e38  mov     ebp, edx
0x180015e3a  mov     rbx, rcx
0x180015e3d  setz    sil
0x180015e41  xor     eax, eax
0x180015e43  mov     [rsp+68h+var_30], rax
0x180015e48  mov     [rsp+68h+var_28], eax
0x180015e4c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180015e53  test    rax, rax
0x180015e56  jnz     short loc_180015EAC
0x180015e58  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180015e5f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180015e64  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180015e6b  test    rax, rax
0x180015e6e  jnz     short loc_180015EAC
0x180015e70  mov     r8d, 0C0000139h
0x180015e76  xor     r9d, r9d
0x180015e79  test    rdi, rdi
0x180015e7c  jz      short loc_180015E8C
0x180015e7e  xor     ecx, ecx
0x180015e80  cmp     r8d, 80000022h
0x180015e87  setnz   cl
0x180015e8a  mov     [rdi], ecx
0x180015e8c  mov     eax, r9d
0x180015e8f  mov     rcx, [rsp+68h+var_20]
0x180015e94  xor     rcx, rsp; StackCookie
0x180015e97  call    __security_check_cookie
0x180015e9c  mov     rbx, [rsp+68h+arg_10]
0x180015ea4  add     rsp, 50h
0x180015ea8  pop     rdi
0x180015ea9  pop     rsi
0x180015eaa  pop     rbp
0x180015eab  retn
0x180015eac  lea     r9, [rsp+68h+var_30]
0x180015eb1  mov     edx, esi
0x180015eb3  lea     r8, [rsp+68h+var_38]
0x180015eb8  mov     ecx, ebp
0x180015eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ebf  mov     r8d, eax
0x180015ec2  test    eax, eax
0x180015ec4  jnz     short loc_180015F0E
0x180015ec6  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180015eca  lea     r9d, [r8+1]
0x180015ece  mov     eax, [rsp+68h+var_28]
0x180015ed2  mov     ecx, edx
0x180015ed4  mov     [rbx+0Ch], eax
0x180015ed7  mov     eax, edx
0x180015ed9  shr     eax, 0Eh
0x180015edc  shr     ecx, 4
0x180015edf  and     eax, 3
0x180015ee2  and     ecx, 3
0x180015ee5  mov     [rbx+8], eax
0x180015ee8  mov     [rbx], ecx
0x180015eea  mov     eax, edx
0x180015eec  mov     ecx, edx
0x180015eee  shr     eax, 6
0x180015ef1  shr     ecx, 8
0x180015ef4  and     eax, r9d
0x180015ef7  and     cl, 3Fh
0x180015efa  shr     edx, 7
0x180015efd  and     edx, r9d
0x180015f00  mov     [rbx+4], cl
0x180015f03  mov     [rbx+10h], edx
0x180015f06  mov     [rbx+14h], eax
0x180015f09  jmp     loc_180015E79
0x180015f0e  cmp     eax, 117h
0x180015f13  jnz     loc_180015E76
0x180015f19  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180015f1d  mov     r9d, 1
0x180015f23  shr     eax, 7
0x180015f26  and     eax, r9d
0x180015f29  mov     [rbx+10h], eax
0x180015f2c  jmp     loc_180015E79
```
