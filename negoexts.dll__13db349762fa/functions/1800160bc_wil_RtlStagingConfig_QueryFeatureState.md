# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1800160bc`
- end: `0x1800161e1`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180012370`

## callees

- `0x180015410`
- `0x1800160bc`
- `0x18001ed20`
- `0x180020010`

## string_xrefs

- `0x180016108`: `RtlQueryFeatureConfiguration`

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
0x1800160bc  mov     [rsp+arg_10], rbx
0x1800160c1  push    rbp
0x1800160c2  push    rsi
0x1800160c3  push    rdi
0x1800160c4  sub     rsp, 50h
0x1800160c8  mov     rax, cs:__security_cookie
0x1800160cf  xor     rax, rsp
0x1800160d2  mov     [rsp+68h+var_20], rax
0x1800160d7  xor     esi, esi
0x1800160d9  mov     [rsp+68h+var_38], 0
0x1800160e2  test    r8d, r8d
0x1800160e5  mov     rdi, r9
0x1800160e8  mov     ebp, edx
0x1800160ea  mov     rbx, rcx
0x1800160ed  setz    sil
0x1800160f1  xor     eax, eax
0x1800160f3  mov     [rsp+68h+var_30], rax
0x1800160f8  mov     [rsp+68h+var_28], eax
0x1800160fc  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180016103  test    rax, rax
0x180016106  jnz     short loc_18001615C
0x180016108  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001610f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180016114  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18001611b  test    rax, rax
0x18001611e  jnz     short loc_18001615C
0x180016120  mov     r8d, 0C0000139h
0x180016126  xor     r9d, r9d
0x180016129  test    rdi, rdi
0x18001612c  jz      short loc_18001613C
0x18001612e  xor     ecx, ecx
0x180016130  cmp     r8d, 80000022h
0x180016137  setnz   cl
0x18001613a  mov     [rdi], ecx
0x18001613c  mov     eax, r9d
0x18001613f  mov     rcx, [rsp+68h+var_20]
0x180016144  xor     rcx, rsp; StackCookie
0x180016147  call    __security_check_cookie
0x18001614c  mov     rbx, [rsp+68h+arg_10]
0x180016154  add     rsp, 50h
0x180016158  pop     rdi
0x180016159  pop     rsi
0x18001615a  pop     rbp
0x18001615b  retn
0x18001615c  lea     r9, [rsp+68h+var_30]
0x180016161  mov     edx, esi
0x180016163  lea     r8, [rsp+68h+var_38]
0x180016168  mov     ecx, ebp
0x18001616a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001616f  mov     r8d, eax
0x180016172  test    eax, eax
0x180016174  jnz     short loc_1800161BE
0x180016176  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18001617a  lea     r9d, [r8+1]
0x18001617e  mov     eax, [rsp+68h+var_28]
0x180016182  mov     ecx, edx
0x180016184  mov     [rbx+0Ch], eax
0x180016187  mov     eax, edx
0x180016189  shr     eax, 0Eh
0x18001618c  shr     ecx, 4
0x18001618f  and     eax, 3
0x180016192  and     ecx, 3
0x180016195  mov     [rbx+8], eax
0x180016198  mov     [rbx], ecx
0x18001619a  mov     eax, edx
0x18001619c  mov     ecx, edx
0x18001619e  shr     eax, 6
0x1800161a1  shr     ecx, 8
0x1800161a4  and     eax, r9d
0x1800161a7  and     cl, 3Fh
0x1800161aa  shr     edx, 7
0x1800161ad  and     edx, r9d
0x1800161b0  mov     [rbx+4], cl
0x1800161b3  mov     [rbx+10h], edx
0x1800161b6  mov     [rbx+14h], eax
0x1800161b9  jmp     loc_180016129
0x1800161be  cmp     eax, 117h
0x1800161c3  jnz     loc_180016126
0x1800161c9  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800161cd  mov     r9d, 1
0x1800161d3  shr     eax, 7
0x1800161d6  and     eax, r9d
0x1800161d9  mov     [rbx+10h], eax
0x1800161dc  jmp     loc_180016129
```
