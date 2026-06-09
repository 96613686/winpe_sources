# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18007b54c`
- end: `0x18007b671`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180077d60`

## callees

- `0x18007b348`
- `0x18007b54c`
- `0x180091140`
- `0x180092010`

## string_xrefs

- `0x18007b598`: `RtlQueryFeatureConfiguration`

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
0x18007b54c  mov     [rsp+arg_10], rbx
0x18007b551  push    rbp
0x18007b552  push    rsi
0x18007b553  push    rdi
0x18007b554  sub     rsp, 50h
0x18007b558  mov     rax, cs:__security_cookie
0x18007b55f  xor     rax, rsp
0x18007b562  mov     [rsp+68h+var_20], rax
0x18007b567  xor     esi, esi
0x18007b569  mov     [rsp+68h+var_38], 0
0x18007b572  test    r8d, r8d
0x18007b575  mov     rdi, r9
0x18007b578  mov     ebp, edx
0x18007b57a  mov     rbx, rcx
0x18007b57d  setz    sil
0x18007b581  xor     eax, eax
0x18007b583  mov     [rsp+68h+var_30], rax
0x18007b588  mov     [rsp+68h+var_28], eax
0x18007b58c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18007b593  test    rax, rax
0x18007b596  jnz     short loc_18007B5EC
0x18007b598  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18007b59f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18007b5a4  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18007b5ab  test    rax, rax
0x18007b5ae  jnz     short loc_18007B5EC
0x18007b5b0  mov     r8d, 0C0000139h
0x18007b5b6  xor     r9d, r9d
0x18007b5b9  test    rdi, rdi
0x18007b5bc  jz      short loc_18007B5CC
0x18007b5be  xor     ecx, ecx
0x18007b5c0  cmp     r8d, 80000022h
0x18007b5c7  setnz   cl
0x18007b5ca  mov     [rdi], ecx
0x18007b5cc  mov     eax, r9d
0x18007b5cf  mov     rcx, [rsp+68h+var_20]
0x18007b5d4  xor     rcx, rsp; StackCookie
0x18007b5d7  call    __security_check_cookie
0x18007b5dc  mov     rbx, [rsp+68h+arg_10]
0x18007b5e4  add     rsp, 50h
0x18007b5e8  pop     rdi
0x18007b5e9  pop     rsi
0x18007b5ea  pop     rbp
0x18007b5eb  retn
0x18007b5ec  lea     r9, [rsp+68h+var_30]
0x18007b5f1  mov     edx, esi
0x18007b5f3  lea     r8, [rsp+68h+var_38]
0x18007b5f8  mov     ecx, ebp
0x18007b5fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b5ff  mov     r8d, eax
0x18007b602  test    eax, eax
0x18007b604  jnz     short loc_18007B64E
0x18007b606  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18007b60a  lea     r9d, [r8+1]
0x18007b60e  mov     eax, [rsp+68h+var_28]
0x18007b612  mov     ecx, edx
0x18007b614  mov     [rbx+0Ch], eax
0x18007b617  mov     eax, edx
0x18007b619  shr     eax, 0Eh
0x18007b61c  shr     ecx, 4
0x18007b61f  and     eax, 3
0x18007b622  and     ecx, 3
0x18007b625  mov     [rbx+8], eax
0x18007b628  mov     [rbx], ecx
0x18007b62a  mov     eax, edx
0x18007b62c  mov     ecx, edx
0x18007b62e  shr     eax, 6
0x18007b631  shr     ecx, 8
0x18007b634  and     eax, r9d
0x18007b637  and     cl, 3Fh
0x18007b63a  shr     edx, 7
0x18007b63d  and     edx, r9d
0x18007b640  mov     [rbx+4], cl
0x18007b643  mov     [rbx+10h], edx
0x18007b646  mov     [rbx+14h], eax
0x18007b649  jmp     loc_18007B5B9
0x18007b64e  cmp     eax, 117h
0x18007b653  jnz     loc_18007B5B6
0x18007b659  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18007b65d  mov     r9d, 1
0x18007b663  shr     eax, 7
0x18007b666  and     eax, r9d
0x18007b669  mov     [rbx+10h], eax
0x18007b66c  jmp     loc_18007B5B9
```
