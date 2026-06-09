# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18002b814`
- end: `0x18002b939`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180028100`

## callees

- `0x1800210f0`
- `0x180027240`
- `0x18002b814`
- `0x180046010`

## string_xrefs

- `0x18002b860`: `RtlQueryFeatureConfiguration`

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
0x18002b814  mov     [rsp+arg_10], rbx
0x18002b819  push    rbp
0x18002b81a  push    rsi
0x18002b81b  push    rdi
0x18002b81c  sub     rsp, 50h
0x18002b820  mov     rax, cs:__security_cookie
0x18002b827  xor     rax, rsp
0x18002b82a  mov     [rsp+68h+var_20], rax
0x18002b82f  xor     esi, esi
0x18002b831  mov     [rsp+68h+var_38], 0
0x18002b83a  test    r8d, r8d
0x18002b83d  mov     rdi, r9
0x18002b840  mov     ebp, edx
0x18002b842  mov     rbx, rcx
0x18002b845  setz    sil
0x18002b849  xor     eax, eax
0x18002b84b  mov     [rsp+68h+var_30], rax
0x18002b850  mov     [rsp+68h+var_28], eax
0x18002b854  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18002b85b  test    rax, rax
0x18002b85e  jnz     short loc_18002B8B4
0x18002b860  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18002b867  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002b86c  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18002b873  test    rax, rax
0x18002b876  jnz     short loc_18002B8B4
0x18002b878  mov     r8d, 0C0000139h
0x18002b87e  xor     r9d, r9d
0x18002b881  test    rdi, rdi
0x18002b884  jz      short loc_18002B894
0x18002b886  xor     ecx, ecx
0x18002b888  cmp     r8d, 80000022h
0x18002b88f  setnz   cl
0x18002b892  mov     [rdi], ecx
0x18002b894  mov     eax, r9d
0x18002b897  mov     rcx, [rsp+68h+var_20]
0x18002b89c  xor     rcx, rsp; StackCookie
0x18002b89f  call    __security_check_cookie
0x18002b8a4  mov     rbx, [rsp+68h+arg_10]
0x18002b8ac  add     rsp, 50h
0x18002b8b0  pop     rdi
0x18002b8b1  pop     rsi
0x18002b8b2  pop     rbp
0x18002b8b3  retn
0x18002b8b4  lea     r9, [rsp+68h+var_30]
0x18002b8b9  mov     edx, esi
0x18002b8bb  lea     r8, [rsp+68h+var_38]
0x18002b8c0  mov     ecx, ebp
0x18002b8c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8c7  mov     r8d, eax
0x18002b8ca  test    eax, eax
0x18002b8cc  jnz     short loc_18002B916
0x18002b8ce  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18002b8d2  lea     r9d, [r8+1]
0x18002b8d6  mov     eax, [rsp+68h+var_28]
0x18002b8da  mov     ecx, edx
0x18002b8dc  mov     [rbx+0Ch], eax
0x18002b8df  mov     eax, edx
0x18002b8e1  shr     eax, 0Eh
0x18002b8e4  shr     ecx, 4
0x18002b8e7  and     eax, 3
0x18002b8ea  and     ecx, 3
0x18002b8ed  mov     [rbx+8], eax
0x18002b8f0  mov     [rbx], ecx
0x18002b8f2  mov     eax, edx
0x18002b8f4  mov     ecx, edx
0x18002b8f6  shr     eax, 6
0x18002b8f9  shr     ecx, 8
0x18002b8fc  and     eax, r9d
0x18002b8ff  and     cl, 3Fh
0x18002b902  shr     edx, 7
0x18002b905  and     edx, r9d
0x18002b908  mov     [rbx+4], cl
0x18002b90b  mov     [rbx+10h], edx
0x18002b90e  mov     [rbx+14h], eax
0x18002b911  jmp     loc_18002B881
0x18002b916  cmp     eax, 117h
0x18002b91b  jnz     loc_18002B87E
0x18002b921  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18002b925  mov     r9d, 1
0x18002b92b  shr     eax, 7
0x18002b92e  and     eax, r9d
0x18002b931  mov     [rbx+10h], eax
0x18002b934  jmp     loc_18002B881
```
