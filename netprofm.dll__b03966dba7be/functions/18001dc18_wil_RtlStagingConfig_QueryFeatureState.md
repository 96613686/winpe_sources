# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18001dc18`
- end: `0x18001dd3d`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800198f8`

## callees

- `0x1800120d0`
- `0x18001d950`
- `0x18001dc18`
- `0x180043010`

## string_xrefs

- `0x18001dc64`: `RtlQueryFeatureConfiguration`

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
0x18001dc18  mov     [rsp+arg_10], rbx
0x18001dc1d  push    rbp
0x18001dc1e  push    rsi
0x18001dc1f  push    rdi
0x18001dc20  sub     rsp, 50h
0x18001dc24  mov     rax, cs:__security_cookie
0x18001dc2b  xor     rax, rsp
0x18001dc2e  mov     [rsp+68h+var_20], rax
0x18001dc33  xor     esi, esi
0x18001dc35  mov     [rsp+68h+var_28], 0
0x18001dc3e  test    r8d, r8d
0x18001dc41  mov     rdi, r9
0x18001dc44  mov     ebp, edx
0x18001dc46  mov     rbx, rcx
0x18001dc49  setz    sil
0x18001dc4d  xor     eax, eax
0x18001dc4f  mov     [rsp+68h+var_38], rax
0x18001dc54  mov     [rsp+68h+var_30], eax
0x18001dc58  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001dc5f  test    rax, rax
0x18001dc62  jnz     short loc_18001DCB8
0x18001dc64  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001dc6b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001dc70  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18001dc77  test    rax, rax
0x18001dc7a  jnz     short loc_18001DCB8
0x18001dc7c  mov     r8d, 0C0000139h
0x18001dc82  xor     r9d, r9d
0x18001dc85  test    rdi, rdi
0x18001dc88  jz      short loc_18001DC98
0x18001dc8a  xor     ecx, ecx
0x18001dc8c  cmp     r8d, 80000022h
0x18001dc93  setnz   cl
0x18001dc96  mov     [rdi], ecx
0x18001dc98  mov     eax, r9d
0x18001dc9b  mov     rcx, [rsp+68h+var_20]
0x18001dca0  xor     rcx, rsp; StackCookie
0x18001dca3  call    __security_check_cookie
0x18001dca8  mov     rbx, [rsp+68h+arg_10]
0x18001dcb0  add     rsp, 50h
0x18001dcb4  pop     rdi
0x18001dcb5  pop     rsi
0x18001dcb6  pop     rbp
0x18001dcb7  retn
0x18001dcb8  lea     r9, [rsp+68h+var_38]
0x18001dcbd  mov     edx, esi
0x18001dcbf  lea     r8, [rsp+68h+var_28]
0x18001dcc4  mov     ecx, ebp
0x18001dcc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dccb  mov     r8d, eax
0x18001dcce  test    eax, eax
0x18001dcd0  jnz     short loc_18001DD1A
0x18001dcd2  mov     edx, dword ptr [rsp+68h+var_38+4]
0x18001dcd6  lea     r9d, [r8+1]
0x18001dcda  mov     eax, [rsp+68h+var_30]
0x18001dcde  mov     ecx, edx
0x18001dce0  mov     [rbx+0Ch], eax
0x18001dce3  mov     eax, edx
0x18001dce5  shr     eax, 0Eh
0x18001dce8  shr     ecx, 4
0x18001dceb  and     eax, 3
0x18001dcee  and     ecx, 3
0x18001dcf1  mov     [rbx+8], eax
0x18001dcf4  mov     [rbx], ecx
0x18001dcf6  mov     eax, edx
0x18001dcf8  mov     ecx, edx
0x18001dcfa  shr     eax, 6
0x18001dcfd  shr     ecx, 8
0x18001dd00  and     eax, r9d
0x18001dd03  and     cl, 3Fh
0x18001dd06  shr     edx, 7
0x18001dd09  and     edx, r9d
0x18001dd0c  mov     [rbx+4], cl
0x18001dd0f  mov     [rbx+10h], edx
0x18001dd12  mov     [rbx+14h], eax
0x18001dd15  jmp     loc_18001DC85
0x18001dd1a  cmp     eax, 117h
0x18001dd1f  jnz     loc_18001DC82
0x18001dd25  mov     eax, dword ptr [rsp+68h+var_38+4]
0x18001dd29  mov     r9d, 1
0x18001dd2f  shr     eax, 7
0x18001dd32  and     eax, r9d
0x18001dd35  mov     [rbx+10h], eax
0x18001dd38  jmp     loc_18001DC85
```
