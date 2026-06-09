# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18007d8a0`
- end: `0x18007d9c6`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18007a004`

## callees

- `0x18007d698`
- `0x18007d8a0`
- `0x180093c00`
- `0x180095010`

## string_xrefs

- `0x18007d8ec`: `RtlQueryFeatureConfiguration`

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
0x18007d8a0  mov     [rsp+arg_10], rbx
0x18007d8a5  push    rbp
0x18007d8a6  push    rsi
0x18007d8a7  push    rdi
0x18007d8a8  sub     rsp, 50h
0x18007d8ac  mov     rax, cs:__security_cookie
0x18007d8b3  xor     rax, rsp
0x18007d8b6  mov     [rsp+68h+var_20], rax
0x18007d8bb  xor     esi, esi
0x18007d8bd  mov     [rsp+68h+var_38], 0
0x18007d8c6  test    r8d, r8d
0x18007d8c9  mov     rdi, r9
0x18007d8cc  mov     ebp, edx
0x18007d8ce  mov     rbx, rcx
0x18007d8d1  setz    sil
0x18007d8d5  xor     eax, eax
0x18007d8d7  mov     [rsp+68h+var_30], rax
0x18007d8dc  mov     [rsp+68h+var_28], eax
0x18007d8e0  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18007d8e7  test    rax, rax
0x18007d8ea  jnz     short loc_18007D941
0x18007d8ec  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18007d8f3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18007d8f8  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18007d8ff  test    rax, rax
0x18007d902  jnz     short loc_18007D941
0x18007d904  mov     r8d, 0C0000139h
0x18007d90a  xor     r9d, r9d
0x18007d90d  test    rdi, rdi
0x18007d910  jz      short loc_18007D920
0x18007d912  xor     ecx, ecx
0x18007d914  cmp     r8d, 80000022h
0x18007d91b  setnz   cl
0x18007d91e  mov     [rdi], ecx
0x18007d920  mov     eax, r9d
0x18007d923  mov     rcx, [rsp+68h+var_20]
0x18007d928  xor     rcx, rsp; StackCookie
0x18007d92b  call    __security_check_cookie
0x18007d930  mov     rbx, [rsp+68h+arg_10]
0x18007d938  add     rsp, 50h
0x18007d93c  pop     rdi
0x18007d93d  pop     rsi
0x18007d93e  pop     rbp
0x18007d93f  retn
0x18007d941  lea     r9, [rsp+68h+var_30]
0x18007d946  mov     edx, esi
0x18007d948  lea     r8, [rsp+68h+var_38]
0x18007d94d  mov     ecx, ebp
0x18007d94f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d954  mov     r8d, eax
0x18007d957  test    eax, eax
0x18007d959  jnz     short loc_18007D9A3
0x18007d95b  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18007d95f  lea     r9d, [r8+1]
0x18007d963  mov     eax, [rsp+68h+var_28]
0x18007d967  mov     ecx, edx
0x18007d969  mov     [rbx+0Ch], eax
0x18007d96c  mov     eax, edx
0x18007d96e  shr     eax, 0Eh
0x18007d971  shr     ecx, 4
0x18007d974  and     eax, 3
0x18007d977  and     ecx, 3
0x18007d97a  mov     [rbx+8], eax
0x18007d97d  mov     [rbx], ecx
0x18007d97f  mov     eax, edx
0x18007d981  mov     ecx, edx
0x18007d983  shr     eax, 6
0x18007d986  shr     ecx, 8
0x18007d989  and     eax, r9d
0x18007d98c  and     cl, 3Fh
0x18007d98f  shr     edx, 7
0x18007d992  and     edx, r9d
0x18007d995  mov     [rbx+4], cl
0x18007d998  mov     [rbx+10h], edx
0x18007d99b  mov     [rbx+14h], eax
0x18007d99e  jmp     loc_18007D90D
0x18007d9a3  cmp     eax, 117h
0x18007d9a8  jnz     loc_18007D90A
0x18007d9ae  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18007d9b2  mov     r9d, 1
0x18007d9b8  shr     eax, 7
0x18007d9bb  and     eax, r9d
0x18007d9be  mov     [rbx+10h], eax
0x18007d9c1  jmp     loc_18007D90D
```
