# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000e45c`
- end: `0x18000e582`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e434`

## callees

- `0x180002af0`
- `0x180009fb8`
- `0x18000e45c`
- `0x180039010`

## string_xrefs

- `0x18000e4a8`: `RtlQueryFeatureConfiguration`

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
0x18000e45c  mov     [rsp+arg_10], rbx
0x18000e461  push    rbp
0x18000e462  push    rsi
0x18000e463  push    rdi
0x18000e464  sub     rsp, 50h
0x18000e468  mov     rax, cs:__security_cookie
0x18000e46f  xor     rax, rsp
0x18000e472  mov     [rsp+68h+var_20], rax
0x18000e477  xor     esi, esi
0x18000e479  mov     [rsp+68h+var_38], 0
0x18000e482  test    r8d, r8d
0x18000e485  mov     rdi, r9
0x18000e488  mov     ebp, edx
0x18000e48a  mov     rbx, rcx
0x18000e48d  setz    sil
0x18000e491  xor     eax, eax
0x18000e493  mov     [rsp+68h+var_30], rax
0x18000e498  mov     [rsp+68h+var_28], eax
0x18000e49c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000e4a3  test    rax, rax
0x18000e4a6  jnz     short loc_18000E4FD
0x18000e4a8  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000e4af  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000e4b4  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000e4bb  test    rax, rax
0x18000e4be  jnz     short loc_18000E4FD
0x18000e4c0  mov     r8d, 0C0000139h
0x18000e4c6  xor     r9d, r9d
0x18000e4c9  test    rdi, rdi
0x18000e4cc  jz      short loc_18000E4DC
0x18000e4ce  xor     ecx, ecx
0x18000e4d0  cmp     r8d, 80000022h
0x18000e4d7  setnz   cl
0x18000e4da  mov     [rdi], ecx
0x18000e4dc  mov     eax, r9d
0x18000e4df  mov     rcx, [rsp+68h+var_20]
0x18000e4e4  xor     rcx, rsp; StackCookie
0x18000e4e7  call    __security_check_cookie
0x18000e4ec  mov     rbx, [rsp+68h+arg_10]
0x18000e4f4  add     rsp, 50h
0x18000e4f8  pop     rdi
0x18000e4f9  pop     rsi
0x18000e4fa  pop     rbp
0x18000e4fb  retn
0x18000e4fd  lea     r9, [rsp+68h+var_30]
0x18000e502  mov     edx, esi
0x18000e504  lea     r8, [rsp+68h+var_38]
0x18000e509  mov     ecx, ebp
0x18000e50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e510  mov     r8d, eax
0x18000e513  test    eax, eax
0x18000e515  jnz     short loc_18000E55F
0x18000e517  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000e51b  lea     r9d, [r8+1]
0x18000e51f  mov     eax, [rsp+68h+var_28]
0x18000e523  mov     ecx, edx
0x18000e525  mov     [rbx+0Ch], eax
0x18000e528  mov     eax, edx
0x18000e52a  shr     eax, 0Eh
0x18000e52d  shr     ecx, 4
0x18000e530  and     eax, 3
0x18000e533  and     ecx, 3
0x18000e536  mov     [rbx+8], eax
0x18000e539  mov     [rbx], ecx
0x18000e53b  mov     eax, edx
0x18000e53d  mov     ecx, edx
0x18000e53f  shr     eax, 6
0x18000e542  shr     ecx, 8
0x18000e545  and     eax, r9d
0x18000e548  and     cl, 3Fh
0x18000e54b  shr     edx, 7
0x18000e54e  and     edx, r9d
0x18000e551  mov     [rbx+4], cl
0x18000e554  mov     [rbx+10h], edx
0x18000e557  mov     [rbx+14h], eax
0x18000e55a  jmp     loc_18000E4C9
0x18000e55f  cmp     eax, 117h
0x18000e564  jnz     loc_18000E4C6
0x18000e56a  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000e56e  mov     r9d, 1
0x18000e574  shr     eax, 7
0x18000e577  and     eax, r9d
0x18000e57a  mov     [rbx+10h], eax
0x18000e57d  jmp     loc_18000E4C9
```
