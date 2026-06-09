# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000c058`
- end: `0x18000c17d`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c030`

## callees

- `0x1800017a0`
- `0x180003910`
- `0x18000c058`
- `0x180034010`

## string_xrefs

- `0x18000c0a4`: `RtlQueryFeatureConfiguration`

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
0x18000c058  mov     [rsp+arg_10], rbx
0x18000c05d  push    rbp
0x18000c05e  push    rsi
0x18000c05f  push    rdi
0x18000c060  sub     rsp, 50h
0x18000c064  mov     rax, cs:__security_cookie
0x18000c06b  xor     rax, rsp
0x18000c06e  mov     [rsp+68h+var_20], rax
0x18000c073  xor     esi, esi
0x18000c075  mov     [rsp+68h+var_38], 0
0x18000c07e  test    r8d, r8d
0x18000c081  mov     rdi, r9
0x18000c084  mov     ebp, edx
0x18000c086  mov     rbx, rcx
0x18000c089  setz    sil
0x18000c08d  xor     eax, eax
0x18000c08f  mov     [rsp+68h+var_30], rax
0x18000c094  mov     [rsp+68h+var_28], eax
0x18000c098  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000c09f  test    rax, rax
0x18000c0a2  jnz     short loc_18000C0F8
0x18000c0a4  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000c0ab  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000c0b0  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000c0b7  test    rax, rax
0x18000c0ba  jnz     short loc_18000C0F8
0x18000c0bc  mov     r8d, 0C0000139h
0x18000c0c2  xor     r9d, r9d
0x18000c0c5  test    rdi, rdi
0x18000c0c8  jz      short loc_18000C0D8
0x18000c0ca  xor     ecx, ecx
0x18000c0cc  cmp     r8d, 80000022h
0x18000c0d3  setnz   cl
0x18000c0d6  mov     [rdi], ecx
0x18000c0d8  mov     eax, r9d
0x18000c0db  mov     rcx, [rsp+68h+var_20]
0x18000c0e0  xor     rcx, rsp; StackCookie
0x18000c0e3  call    __security_check_cookie
0x18000c0e8  mov     rbx, [rsp+68h+arg_10]
0x18000c0f0  add     rsp, 50h
0x18000c0f4  pop     rdi
0x18000c0f5  pop     rsi
0x18000c0f6  pop     rbp
0x18000c0f7  retn
0x18000c0f8  lea     r9, [rsp+68h+var_30]
0x18000c0fd  mov     edx, esi
0x18000c0ff  lea     r8, [rsp+68h+var_38]
0x18000c104  mov     ecx, ebp
0x18000c106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c10b  mov     r8d, eax
0x18000c10e  test    eax, eax
0x18000c110  jnz     short loc_18000C15A
0x18000c112  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000c116  lea     r9d, [r8+1]
0x18000c11a  mov     eax, [rsp+68h+var_28]
0x18000c11e  mov     ecx, edx
0x18000c120  mov     [rbx+0Ch], eax
0x18000c123  mov     eax, edx
0x18000c125  shr     eax, 0Eh
0x18000c128  shr     ecx, 4
0x18000c12b  and     eax, 3
0x18000c12e  and     ecx, 3
0x18000c131  mov     [rbx+8], eax
0x18000c134  mov     [rbx], ecx
0x18000c136  mov     eax, edx
0x18000c138  mov     ecx, edx
0x18000c13a  shr     eax, 6
0x18000c13d  shr     ecx, 8
0x18000c140  and     eax, r9d
0x18000c143  and     cl, 3Fh
0x18000c146  shr     edx, 7
0x18000c149  and     edx, r9d
0x18000c14c  mov     [rbx+4], cl
0x18000c14f  mov     [rbx+10h], edx
0x18000c152  mov     [rbx+14h], eax
0x18000c155  jmp     loc_18000C0C5
0x18000c15a  cmp     eax, 117h
0x18000c15f  jnz     loc_18000C0C2
0x18000c165  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000c169  mov     r9d, 1
0x18000c16f  shr     eax, 7
0x18000c172  and     eax, r9d
0x18000c175  mov     [rbx+10h], eax
0x18000c178  jmp     loc_18000C0C5
```
