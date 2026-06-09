# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000d574`
- end: `0x18000d699`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000916c`

## callees

- `0x180001a70`
- `0x180006060`
- `0x18000d574`
- `0x180012010`

## string_xrefs

- `0x18000d5c0`: `RtlQueryFeatureConfiguration`

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
0x18000d574  mov     [rsp+arg_10], rbx
0x18000d579  push    rbp
0x18000d57a  push    rsi
0x18000d57b  push    rdi
0x18000d57c  sub     rsp, 50h
0x18000d580  mov     rax, cs:__security_cookie
0x18000d587  xor     rax, rsp
0x18000d58a  mov     [rsp+68h+var_20], rax
0x18000d58f  xor     esi, esi
0x18000d591  mov     [rsp+68h+var_38], 0
0x18000d59a  test    r8d, r8d
0x18000d59d  mov     rdi, r9
0x18000d5a0  mov     ebp, edx
0x18000d5a2  mov     rbx, rcx
0x18000d5a5  setz    sil
0x18000d5a9  xor     eax, eax
0x18000d5ab  mov     [rsp+68h+var_30], rax
0x18000d5b0  mov     [rsp+68h+var_28], eax
0x18000d5b4  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000d5bb  test    rax, rax
0x18000d5be  jnz     short loc_18000D614
0x18000d5c0  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000d5c7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d5cc  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000d5d3  test    rax, rax
0x18000d5d6  jnz     short loc_18000D614
0x18000d5d8  mov     r8d, 0C0000139h
0x18000d5de  xor     r9d, r9d
0x18000d5e1  test    rdi, rdi
0x18000d5e4  jz      short loc_18000D5F4
0x18000d5e6  xor     ecx, ecx
0x18000d5e8  cmp     r8d, 80000022h
0x18000d5ef  setnz   cl
0x18000d5f2  mov     [rdi], ecx
0x18000d5f4  mov     eax, r9d
0x18000d5f7  mov     rcx, [rsp+68h+var_20]
0x18000d5fc  xor     rcx, rsp; StackCookie
0x18000d5ff  call    __security_check_cookie
0x18000d604  mov     rbx, [rsp+68h+arg_10]
0x18000d60c  add     rsp, 50h
0x18000d610  pop     rdi
0x18000d611  pop     rsi
0x18000d612  pop     rbp
0x18000d613  retn
0x18000d614  lea     r9, [rsp+68h+var_30]
0x18000d619  mov     edx, esi
0x18000d61b  lea     r8, [rsp+68h+var_38]
0x18000d620  mov     ecx, ebp
0x18000d622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d627  mov     r8d, eax
0x18000d62a  test    eax, eax
0x18000d62c  jnz     short loc_18000D676
0x18000d62e  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000d632  lea     r9d, [r8+1]
0x18000d636  mov     eax, [rsp+68h+var_28]
0x18000d63a  mov     ecx, edx
0x18000d63c  mov     [rbx+0Ch], eax
0x18000d63f  mov     eax, edx
0x18000d641  shr     eax, 0Eh
0x18000d644  shr     ecx, 4
0x18000d647  and     eax, 3
0x18000d64a  and     ecx, 3
0x18000d64d  mov     [rbx+8], eax
0x18000d650  mov     [rbx], ecx
0x18000d652  mov     eax, edx
0x18000d654  mov     ecx, edx
0x18000d656  shr     eax, 6
0x18000d659  shr     ecx, 8
0x18000d65c  and     eax, r9d
0x18000d65f  and     cl, 3Fh
0x18000d662  shr     edx, 7
0x18000d665  and     edx, r9d
0x18000d668  mov     [rbx+4], cl
0x18000d66b  mov     [rbx+10h], edx
0x18000d66e  mov     [rbx+14h], eax
0x18000d671  jmp     loc_18000D5E1
0x18000d676  cmp     eax, 117h
0x18000d67b  jnz     loc_18000D5DE
0x18000d681  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000d685  mov     r9d, 1
0x18000d68b  shr     eax, 7
0x18000d68e  and     eax, r9d
0x18000d691  mov     [rbx+10h], eax
0x18000d694  jmp     loc_18000D5E1
```
