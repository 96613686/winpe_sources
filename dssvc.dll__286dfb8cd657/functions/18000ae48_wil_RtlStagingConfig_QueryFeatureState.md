# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000ae48`
- end: `0x18000af6d`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ae20`

## callees

- `0x1800071f8`
- `0x18000ae48`
- `0x18001b340`
- `0x18001c010`

## string_xrefs

- `0x18000ae94`: `RtlQueryFeatureConfiguration`

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
0x18000ae48  mov     [rsp+arg_10], rbx
0x18000ae4d  push    rbp
0x18000ae4e  push    rsi
0x18000ae4f  push    rdi
0x18000ae50  sub     rsp, 50h
0x18000ae54  mov     rax, cs:__security_cookie
0x18000ae5b  xor     rax, rsp
0x18000ae5e  mov     [rsp+68h+var_20], rax
0x18000ae63  xor     esi, esi
0x18000ae65  mov     [rsp+68h+var_38], 0
0x18000ae6e  test    r8d, r8d
0x18000ae71  mov     rdi, r9
0x18000ae74  mov     ebp, edx
0x18000ae76  mov     rbx, rcx
0x18000ae79  setz    sil
0x18000ae7d  xor     eax, eax
0x18000ae7f  mov     [rsp+68h+var_30], rax
0x18000ae84  mov     [rsp+68h+var_28], eax
0x18000ae88  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000ae8f  test    rax, rax
0x18000ae92  jnz     short loc_18000AEE8
0x18000ae94  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000ae9b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000aea0  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000aea7  test    rax, rax
0x18000aeaa  jnz     short loc_18000AEE8
0x18000aeac  mov     r8d, 0C0000139h
0x18000aeb2  xor     r9d, r9d
0x18000aeb5  test    rdi, rdi
0x18000aeb8  jz      short loc_18000AEC8
0x18000aeba  xor     ecx, ecx
0x18000aebc  cmp     r8d, 80000022h
0x18000aec3  setnz   cl
0x18000aec6  mov     [rdi], ecx
0x18000aec8  mov     eax, r9d
0x18000aecb  mov     rcx, [rsp+68h+var_20]
0x18000aed0  xor     rcx, rsp; StackCookie
0x18000aed3  call    __security_check_cookie
0x18000aed8  mov     rbx, [rsp+68h+arg_10]
0x18000aee0  add     rsp, 50h
0x18000aee4  pop     rdi
0x18000aee5  pop     rsi
0x18000aee6  pop     rbp
0x18000aee7  retn
0x18000aee8  lea     r9, [rsp+68h+var_30]
0x18000aeed  mov     edx, esi
0x18000aeef  lea     r8, [rsp+68h+var_38]
0x18000aef4  mov     ecx, ebp
0x18000aef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aefb  mov     r8d, eax
0x18000aefe  test    eax, eax
0x18000af00  jnz     short loc_18000AF4A
0x18000af02  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000af06  lea     r9d, [r8+1]
0x18000af0a  mov     eax, [rsp+68h+var_28]
0x18000af0e  mov     ecx, edx
0x18000af10  mov     [rbx+0Ch], eax
0x18000af13  mov     eax, edx
0x18000af15  shr     eax, 0Eh
0x18000af18  shr     ecx, 4
0x18000af1b  and     eax, 3
0x18000af1e  and     ecx, 3
0x18000af21  mov     [rbx+8], eax
0x18000af24  mov     [rbx], ecx
0x18000af26  mov     eax, edx
0x18000af28  mov     ecx, edx
0x18000af2a  shr     eax, 6
0x18000af2d  shr     ecx, 8
0x18000af30  and     eax, r9d
0x18000af33  and     cl, 3Fh
0x18000af36  shr     edx, 7
0x18000af39  and     edx, r9d
0x18000af3c  mov     [rbx+4], cl
0x18000af3f  mov     [rbx+10h], edx
0x18000af42  mov     [rbx+14h], eax
0x18000af45  jmp     loc_18000AEB5
0x18000af4a  cmp     eax, 117h
0x18000af4f  jnz     loc_18000AEB2
0x18000af55  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000af59  mov     r9d, 1
0x18000af5f  shr     eax, 7
0x18000af62  and     eax, r9d
0x18000af65  mov     [rbx+10h], eax
0x18000af68  jmp     loc_18000AEB5
```
