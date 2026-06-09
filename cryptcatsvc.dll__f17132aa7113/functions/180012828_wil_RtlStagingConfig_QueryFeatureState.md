# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180012828`
- end: `0x18001294d`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180012800`

## callees

- `0x18000be40`
- `0x180012410`
- `0x180012828`
- `0x180022010`

## string_xrefs

- `0x180012874`: `RtlQueryFeatureConfiguration`

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
  int v16; // [rsp+38h] [rbp-30h]
  __int64 v17; // [rsp+40h] [rbp-28h] BYREF

  v17 = 0;
  v7 = a3 == 0;
  v15 = 0;
  v16 = 0;
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
  v12 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))NtDllProcedureAddress)(a2, v7, &v17, &v15);
  v9 = v12;
  if ( v12 )
  {
    if ( v12 != 279 )
      goto LABEL_4;
    v10 = 1;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v15) >> 7) & 1;
  }
  else
  {
    v13 = HIDWORD(v15);
    v10 = 1;
    v14 = HIDWORD(v15);
    *(_DWORD *)(a1 + 12) = v16;
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
0x180012828  mov     [rsp+arg_10], rbx
0x18001282d  push    rbp
0x18001282e  push    rsi
0x18001282f  push    rdi
0x180012830  sub     rsp, 50h
0x180012834  mov     rax, cs:__security_cookie
0x18001283b  xor     rax, rsp
0x18001283e  mov     [rsp+68h+var_20], rax
0x180012843  xor     esi, esi
0x180012845  mov     [rsp+68h+var_28], 0
0x18001284e  test    r8d, r8d
0x180012851  mov     rdi, r9
0x180012854  mov     ebp, edx
0x180012856  mov     rbx, rcx
0x180012859  setz    sil
0x18001285d  xor     eax, eax
0x18001285f  mov     [rsp+68h+var_38], rax
0x180012864  mov     [rsp+68h+var_30], eax
0x180012868  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001286f  test    rax, rax
0x180012872  jnz     short loc_1800128C8
0x180012874  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001287b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180012880  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180012887  test    rax, rax
0x18001288a  jnz     short loc_1800128C8
0x18001288c  mov     r8d, 0C0000139h
0x180012892  xor     r9d, r9d
0x180012895  test    rdi, rdi
0x180012898  jz      short loc_1800128A8
0x18001289a  xor     ecx, ecx
0x18001289c  cmp     r8d, 80000022h
0x1800128a3  setnz   cl
0x1800128a6  mov     [rdi], ecx
0x1800128a8  mov     eax, r9d
0x1800128ab  mov     rcx, [rsp+68h+var_20]
0x1800128b0  xor     rcx, rsp; StackCookie
0x1800128b3  call    __security_check_cookie
0x1800128b8  mov     rbx, [rsp+68h+arg_10]
0x1800128c0  add     rsp, 50h
0x1800128c4  pop     rdi
0x1800128c5  pop     rsi
0x1800128c6  pop     rbp
0x1800128c7  retn
0x1800128c8  lea     r9, [rsp+68h+var_38]
0x1800128cd  mov     edx, esi
0x1800128cf  lea     r8, [rsp+68h+var_28]
0x1800128d4  mov     ecx, ebp
0x1800128d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128db  mov     r8d, eax
0x1800128de  test    eax, eax
0x1800128e0  jnz     short loc_18001292A
0x1800128e2  mov     edx, dword ptr [rsp+68h+var_38+4]
0x1800128e6  lea     r9d, [r8+1]
0x1800128ea  mov     eax, [rsp+68h+var_30]
0x1800128ee  mov     ecx, edx
0x1800128f0  mov     [rbx+0Ch], eax
0x1800128f3  mov     eax, edx
0x1800128f5  shr     eax, 0Eh
0x1800128f8  shr     ecx, 4
0x1800128fb  and     eax, 3
0x1800128fe  and     ecx, 3
0x180012901  mov     [rbx+8], eax
0x180012904  mov     [rbx], ecx
0x180012906  mov     eax, edx
0x180012908  mov     ecx, edx
0x18001290a  shr     eax, 6
0x18001290d  shr     ecx, 8
0x180012910  and     eax, r9d
0x180012913  and     cl, 3Fh
0x180012916  shr     edx, 7
0x180012919  and     edx, r9d
0x18001291c  mov     [rbx+4], cl
0x18001291f  mov     [rbx+10h], edx
0x180012922  mov     [rbx+14h], eax
0x180012925  jmp     loc_180012895
0x18001292a  cmp     eax, 117h
0x18001292f  jnz     loc_180012892
0x180012935  mov     eax, dword ptr [rsp+68h+var_38+4]
0x180012939  mov     r9d, 1
0x18001293f  shr     eax, 7
0x180012942  and     eax, r9d
0x180012945  mov     [rbx+10h], eax
0x180012948  jmp     loc_180012895
```
