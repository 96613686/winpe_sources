# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x14000e6a0`
- end: `0x14000e7c5`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x14000e678`

## callees

- `0x14000d810`
- `0x14000e6a0`
- `0x140025d70`
- `0x140027010`

## string_xrefs

- `0x14000e6ec`: `RtlQueryFeatureConfiguration`

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
0x14000e6a0  mov     [rsp+arg_10], rbx
0x14000e6a5  push    rbp
0x14000e6a6  push    rsi
0x14000e6a7  push    rdi
0x14000e6a8  sub     rsp, 50h
0x14000e6ac  mov     rax, cs:__security_cookie
0x14000e6b3  xor     rax, rsp
0x14000e6b6  mov     [rsp+68h+var_20], rax
0x14000e6bb  xor     esi, esi
0x14000e6bd  mov     [rsp+68h+var_38], 0
0x14000e6c6  test    r8d, r8d
0x14000e6c9  mov     rdi, r9
0x14000e6cc  mov     ebp, edx
0x14000e6ce  mov     rbx, rcx
0x14000e6d1  setz    sil
0x14000e6d5  xor     eax, eax
0x14000e6d7  mov     [rsp+68h+var_30], rax
0x14000e6dc  mov     [rsp+68h+var_28], eax
0x14000e6e0  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000e6e7  test    rax, rax
0x14000e6ea  jnz     short loc_14000E740
0x14000e6ec  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000e6f3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000e6f8  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000e6ff  test    rax, rax
0x14000e702  jnz     short loc_14000E740
0x14000e704  mov     r8d, 0C0000139h
0x14000e70a  xor     r9d, r9d
0x14000e70d  test    rdi, rdi
0x14000e710  jz      short loc_14000E720
0x14000e712  xor     ecx, ecx
0x14000e714  cmp     r8d, 80000022h
0x14000e71b  setnz   cl
0x14000e71e  mov     [rdi], ecx
0x14000e720  mov     eax, r9d
0x14000e723  mov     rcx, [rsp+68h+var_20]
0x14000e728  xor     rcx, rsp; StackCookie
0x14000e72b  call    __security_check_cookie
0x14000e730  mov     rbx, [rsp+68h+arg_10]
0x14000e738  add     rsp, 50h
0x14000e73c  pop     rdi
0x14000e73d  pop     rsi
0x14000e73e  pop     rbp
0x14000e73f  retn
0x14000e740  lea     r9, [rsp+68h+var_30]
0x14000e745  mov     edx, esi
0x14000e747  lea     r8, [rsp+68h+var_38]
0x14000e74c  mov     ecx, ebp
0x14000e74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e753  mov     r8d, eax
0x14000e756  test    eax, eax
0x14000e758  jnz     short loc_14000E7A2
0x14000e75a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14000e75e  lea     r9d, [r8+1]
0x14000e762  mov     eax, [rsp+68h+var_28]
0x14000e766  mov     ecx, edx
0x14000e768  mov     [rbx+0Ch], eax
0x14000e76b  mov     eax, edx
0x14000e76d  shr     eax, 0Eh
0x14000e770  shr     ecx, 4
0x14000e773  and     eax, 3
0x14000e776  and     ecx, 3
0x14000e779  mov     [rbx+8], eax
0x14000e77c  mov     [rbx], ecx
0x14000e77e  mov     eax, edx
0x14000e780  mov     ecx, edx
0x14000e782  shr     eax, 6
0x14000e785  shr     ecx, 8
0x14000e788  and     eax, r9d
0x14000e78b  and     cl, 3Fh
0x14000e78e  shr     edx, 7
0x14000e791  and     edx, r9d
0x14000e794  mov     [rbx+4], cl
0x14000e797  mov     [rbx+10h], edx
0x14000e79a  mov     [rbx+14h], eax
0x14000e79d  jmp     loc_14000E70D
0x14000e7a2  cmp     eax, 117h
0x14000e7a7  jnz     loc_14000E70A
0x14000e7ad  mov     eax, dword ptr [rsp+68h+var_30+4]
0x14000e7b1  mov     r9d, 1
0x14000e7b7  shr     eax, 7
0x14000e7ba  and     eax, r9d
0x14000e7bd  mov     [rbx+10h], eax
0x14000e7c0  jmp     loc_14000E70D
```
