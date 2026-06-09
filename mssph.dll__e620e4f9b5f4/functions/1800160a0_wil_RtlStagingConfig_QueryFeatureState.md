# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1800160a0`
- end: `0x1800161c5`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800134e8`

## callees

- `0x18000d720`
- `0x18000fcd0`
- `0x1800160a0`
- `0x180027010`

## string_xrefs

- `0x1800160ec`: `RtlQueryFeatureConfiguration`

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
0x1800160a0  mov     [rsp+arg_10], rbx
0x1800160a5  push    rbp
0x1800160a6  push    rsi
0x1800160a7  push    rdi
0x1800160a8  sub     rsp, 50h
0x1800160ac  mov     rax, cs:__security_cookie
0x1800160b3  xor     rax, rsp
0x1800160b6  mov     [rsp+68h+var_20], rax
0x1800160bb  xor     esi, esi
0x1800160bd  mov     [rsp+68h+var_38], 0
0x1800160c6  test    r8d, r8d
0x1800160c9  mov     rdi, r9
0x1800160cc  mov     ebp, edx
0x1800160ce  mov     rbx, rcx
0x1800160d1  setz    sil
0x1800160d5  xor     eax, eax
0x1800160d7  mov     [rsp+68h+var_30], rax
0x1800160dc  mov     [rsp+68h+var_28], eax
0x1800160e0  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800160e7  test    rax, rax
0x1800160ea  jnz     short loc_180016140
0x1800160ec  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1800160f3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800160f8  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1800160ff  test    rax, rax
0x180016102  jnz     short loc_180016140
0x180016104  mov     r8d, 0C0000139h
0x18001610a  xor     r9d, r9d
0x18001610d  test    rdi, rdi
0x180016110  jz      short loc_180016120
0x180016112  xor     ecx, ecx
0x180016114  cmp     r8d, 80000022h
0x18001611b  setnz   cl
0x18001611e  mov     [rdi], ecx
0x180016120  mov     eax, r9d
0x180016123  mov     rcx, [rsp+68h+var_20]
0x180016128  xor     rcx, rsp; StackCookie
0x18001612b  call    __security_check_cookie
0x180016130  mov     rbx, [rsp+68h+arg_10]
0x180016138  add     rsp, 50h
0x18001613c  pop     rdi
0x18001613d  pop     rsi
0x18001613e  pop     rbp
0x18001613f  retn
0x180016140  lea     r9, [rsp+68h+var_30]
0x180016145  mov     edx, esi
0x180016147  lea     r8, [rsp+68h+var_38]
0x18001614c  mov     ecx, ebp
0x18001614e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016153  mov     r8d, eax
0x180016156  test    eax, eax
0x180016158  jnz     short loc_1800161A2
0x18001615a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18001615e  lea     r9d, [r8+1]
0x180016162  mov     eax, [rsp+68h+var_28]
0x180016166  mov     ecx, edx
0x180016168  mov     [rbx+0Ch], eax
0x18001616b  mov     eax, edx
0x18001616d  shr     eax, 0Eh
0x180016170  shr     ecx, 4
0x180016173  and     eax, 3
0x180016176  and     ecx, 3
0x180016179  mov     [rbx+8], eax
0x18001617c  mov     [rbx], ecx
0x18001617e  mov     eax, edx
0x180016180  mov     ecx, edx
0x180016182  shr     eax, 6
0x180016185  shr     ecx, 8
0x180016188  and     eax, r9d
0x18001618b  and     cl, 3Fh
0x18001618e  shr     edx, 7
0x180016191  and     edx, r9d
0x180016194  mov     [rbx+4], cl
0x180016197  mov     [rbx+10h], edx
0x18001619a  mov     [rbx+14h], eax
0x18001619d  jmp     loc_18001610D
0x1800161a2  cmp     eax, 117h
0x1800161a7  jnz     loc_18001610A
0x1800161ad  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800161b1  mov     r9d, 1
0x1800161b7  shr     eax, 7
0x1800161ba  and     eax, r9d
0x1800161bd  mov     [rbx+10h], eax
0x1800161c0  jmp     loc_18001610D
```
