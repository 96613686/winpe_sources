# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000f9b0`
- end: `0x18000fad5`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180010150`
- `0x180013a00`

## callees

- `0x18000f9b0`
- `0x180010268`
- `0x180018950`
- `0x180019010`

## string_xrefs

- `0x18000f9fc`: `RtlQueryFeatureConfiguration`

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
0x18000f9b0  mov     [rsp+arg_10], rbx
0x18000f9b5  push    rbp
0x18000f9b6  push    rsi
0x18000f9b7  push    rdi
0x18000f9b8  sub     rsp, 50h
0x18000f9bc  mov     rax, cs:__security_cookie
0x18000f9c3  xor     rax, rsp
0x18000f9c6  mov     [rsp+68h+var_20], rax
0x18000f9cb  xor     esi, esi
0x18000f9cd  mov     [rsp+68h+var_38], 0
0x18000f9d6  test    r8d, r8d
0x18000f9d9  mov     rdi, r9
0x18000f9dc  mov     ebp, edx
0x18000f9de  mov     rbx, rcx
0x18000f9e1  setz    sil
0x18000f9e5  xor     eax, eax
0x18000f9e7  mov     [rsp+68h+var_30], rax
0x18000f9ec  mov     [rsp+68h+var_28], eax
0x18000f9f0  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000f9f7  test    rax, rax
0x18000f9fa  jnz     short loc_18000FA50
0x18000f9fc  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000fa03  call    wil_details_GetNtDllProcedureAddress
0x18000fa08  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000fa0f  test    rax, rax
0x18000fa12  jnz     short loc_18000FA50
0x18000fa14  mov     r8d, 0C0000139h
0x18000fa1a  xor     r9d, r9d
0x18000fa1d  test    rdi, rdi
0x18000fa20  jz      short loc_18000FA30
0x18000fa22  xor     ecx, ecx
0x18000fa24  cmp     r8d, 80000022h
0x18000fa2b  setnz   cl
0x18000fa2e  mov     [rdi], ecx
0x18000fa30  mov     eax, r9d
0x18000fa33  mov     rcx, [rsp+68h+var_20]
0x18000fa38  xor     rcx, rsp; StackCookie
0x18000fa3b  call    __security_check_cookie
0x18000fa40  mov     rbx, [rsp+68h+arg_10]
0x18000fa48  add     rsp, 50h
0x18000fa4c  pop     rdi
0x18000fa4d  pop     rsi
0x18000fa4e  pop     rbp
0x18000fa4f  retn
0x18000fa50  lea     r9, [rsp+68h+var_30]
0x18000fa55  mov     edx, esi
0x18000fa57  lea     r8, [rsp+68h+var_38]
0x18000fa5c  mov     ecx, ebp
0x18000fa5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa63  mov     r8d, eax
0x18000fa66  test    eax, eax
0x18000fa68  jnz     short loc_18000FAB2
0x18000fa6a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000fa6e  lea     r9d, [r8+1]
0x18000fa72  mov     eax, [rsp+68h+var_28]
0x18000fa76  mov     ecx, edx
0x18000fa78  mov     [rbx+0Ch], eax
0x18000fa7b  mov     eax, edx
0x18000fa7d  shr     eax, 0Eh
0x18000fa80  shr     ecx, 4
0x18000fa83  and     eax, 3
0x18000fa86  and     ecx, 3
0x18000fa89  mov     [rbx+8], eax
0x18000fa8c  mov     [rbx], ecx
0x18000fa8e  mov     eax, edx
0x18000fa90  mov     ecx, edx
0x18000fa92  shr     eax, 6
0x18000fa95  shr     ecx, 8
0x18000fa98  and     eax, r9d
0x18000fa9b  and     cl, 3Fh
0x18000fa9e  shr     edx, 7
0x18000faa1  and     edx, r9d
0x18000faa4  mov     [rbx+4], cl
0x18000faa7  mov     [rbx+10h], edx
0x18000faaa  mov     [rbx+14h], eax
0x18000faad  jmp     loc_18000FA1D
0x18000fab2  cmp     eax, 117h
0x18000fab7  jnz     loc_18000FA1A
0x18000fabd  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000fac1  mov     r9d, 1
0x18000fac7  shr     eax, 7
0x18000faca  and     eax, r9d
0x18000facd  mov     [rbx+10h], eax
0x18000fad0  jmp     loc_18000FA1D
```
