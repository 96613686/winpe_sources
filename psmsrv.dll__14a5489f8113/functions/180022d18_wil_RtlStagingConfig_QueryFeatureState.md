# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180022d18`
- end: `0x180022e3d`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002359c`

## callees

- `0x18001b7e0`
- `0x180022d18`
- `0x1800236b4`
- `0x18002f010`

## string_xrefs

- `0x180022d64`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  BOOL v7; // esi
  __int64 (__fastcall *NtDllProcedureAddress)(_QWORD, BOOL, __int64 *, __int64 *); // rax
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
  NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))wil_details_GetNtDllProcedureAddress("RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress;
    if ( !NtDllProcedureAddress )
    {
      v9 = -1073741511;
LABEL_4:
      v10 = 0;
      goto LABEL_5;
    }
  }
  v12 = NtDllProcedureAddress(a2, v7, &v15, &v16);
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
0x180022d18  mov     [rsp+arg_10], rbx
0x180022d1d  push    rbp
0x180022d1e  push    rsi
0x180022d1f  push    rdi
0x180022d20  sub     rsp, 50h
0x180022d24  mov     rax, cs:__security_cookie
0x180022d2b  xor     rax, rsp
0x180022d2e  mov     [rsp+68h+var_20], rax
0x180022d33  xor     esi, esi
0x180022d35  mov     [rsp+68h+var_38], 0
0x180022d3e  test    r8d, r8d
0x180022d41  mov     rdi, r9
0x180022d44  mov     ebp, edx
0x180022d46  mov     rbx, rcx
0x180022d49  setz    sil
0x180022d4d  xor     eax, eax
0x180022d4f  mov     [rsp+68h+var_30], rax
0x180022d54  mov     [rsp+68h+var_28], eax
0x180022d58  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180022d5f  test    rax, rax
0x180022d62  jnz     short loc_180022DB8
0x180022d64  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180022d6b  call    wil_details_GetNtDllProcedureAddress
0x180022d70  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180022d77  test    rax, rax
0x180022d7a  jnz     short loc_180022DB8
0x180022d7c  mov     r8d, 0C0000139h
0x180022d82  xor     r9d, r9d
0x180022d85  test    rdi, rdi
0x180022d88  jz      short loc_180022D98
0x180022d8a  xor     ecx, ecx
0x180022d8c  cmp     r8d, 80000022h
0x180022d93  setnz   cl
0x180022d96  mov     [rdi], ecx
0x180022d98  mov     eax, r9d
0x180022d9b  mov     rcx, [rsp+68h+var_20]
0x180022da0  xor     rcx, rsp; StackCookie
0x180022da3  call    __security_check_cookie
0x180022da8  mov     rbx, [rsp+68h+arg_10]
0x180022db0  add     rsp, 50h
0x180022db4  pop     rdi
0x180022db5  pop     rsi
0x180022db6  pop     rbp
0x180022db7  retn
0x180022db8  lea     r9, [rsp+68h+var_30]
0x180022dbd  mov     edx, esi
0x180022dbf  lea     r8, [rsp+68h+var_38]
0x180022dc4  mov     ecx, ebp
0x180022dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022dcb  mov     r8d, eax
0x180022dce  test    eax, eax
0x180022dd0  jnz     short loc_180022E1A
0x180022dd2  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180022dd6  lea     r9d, [r8+1]
0x180022dda  mov     eax, [rsp+68h+var_28]
0x180022dde  mov     ecx, edx
0x180022de0  mov     [rbx+0Ch], eax
0x180022de3  mov     eax, edx
0x180022de5  shr     eax, 0Eh
0x180022de8  shr     ecx, 4
0x180022deb  and     eax, 3
0x180022dee  and     ecx, 3
0x180022df1  mov     [rbx+8], eax
0x180022df4  mov     [rbx], ecx
0x180022df6  mov     eax, edx
0x180022df8  mov     ecx, edx
0x180022dfa  shr     eax, 6
0x180022dfd  shr     ecx, 8
0x180022e00  and     eax, r9d
0x180022e03  and     cl, 3Fh
0x180022e06  shr     edx, 7
0x180022e09  and     edx, r9d
0x180022e0c  mov     [rbx+4], cl
0x180022e0f  mov     [rbx+10h], edx
0x180022e12  mov     [rbx+14h], eax
0x180022e15  jmp     loc_180022D85
0x180022e1a  cmp     eax, 117h
0x180022e1f  jnz     loc_180022D82
0x180022e25  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180022e29  mov     r9d, 1
0x180022e2f  shr     eax, 7
0x180022e32  and     eax, r9d
0x180022e35  mov     [rbx+10h], eax
0x180022e38  jmp     loc_180022D85
```
