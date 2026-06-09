# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18002ebbc`
- end: `0x18002ece1`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002abf4`

## callees

- `0x18002e9b8`
- `0x18002ebbc`
- `0x180031680`
- `0x180034010`

## string_xrefs

- `0x18002ec08`: `RtlQueryFeatureConfiguration`

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
0x18002ebbc  mov     [rsp+arg_10], rbx
0x18002ebc1  push    rbp
0x18002ebc2  push    rsi
0x18002ebc3  push    rdi
0x18002ebc4  sub     rsp, 50h
0x18002ebc8  mov     rax, cs:__security_cookie
0x18002ebcf  xor     rax, rsp
0x18002ebd2  mov     [rsp+68h+var_20], rax
0x18002ebd7  xor     esi, esi
0x18002ebd9  mov     [rsp+68h+var_38], 0
0x18002ebe2  test    r8d, r8d
0x18002ebe5  mov     rdi, r9
0x18002ebe8  mov     ebp, edx
0x18002ebea  mov     rbx, rcx
0x18002ebed  setz    sil
0x18002ebf1  xor     eax, eax
0x18002ebf3  mov     [rsp+68h+var_30], rax
0x18002ebf8  mov     [rsp+68h+var_28], eax
0x18002ebfc  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18002ec03  test    rax, rax
0x18002ec06  jnz     short loc_18002EC5C
0x18002ec08  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18002ec0f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002ec14  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18002ec1b  test    rax, rax
0x18002ec1e  jnz     short loc_18002EC5C
0x18002ec20  mov     r8d, 0C0000139h
0x18002ec26  xor     r9d, r9d
0x18002ec29  test    rdi, rdi
0x18002ec2c  jz      short loc_18002EC3C
0x18002ec2e  xor     ecx, ecx
0x18002ec30  cmp     r8d, 80000022h
0x18002ec37  setnz   cl
0x18002ec3a  mov     [rdi], ecx
0x18002ec3c  mov     eax, r9d
0x18002ec3f  mov     rcx, [rsp+68h+var_20]
0x18002ec44  xor     rcx, rsp; StackCookie
0x18002ec47  call    __security_check_cookie
0x18002ec4c  mov     rbx, [rsp+68h+arg_10]
0x18002ec54  add     rsp, 50h
0x18002ec58  pop     rdi
0x18002ec59  pop     rsi
0x18002ec5a  pop     rbp
0x18002ec5b  retn
0x18002ec5c  lea     r9, [rsp+68h+var_30]
0x18002ec61  mov     edx, esi
0x18002ec63  lea     r8, [rsp+68h+var_38]
0x18002ec68  mov     ecx, ebp
0x18002ec6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec6f  mov     r8d, eax
0x18002ec72  test    eax, eax
0x18002ec74  jnz     short loc_18002ECBE
0x18002ec76  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18002ec7a  lea     r9d, [r8+1]
0x18002ec7e  mov     eax, [rsp+68h+var_28]
0x18002ec82  mov     ecx, edx
0x18002ec84  mov     [rbx+0Ch], eax
0x18002ec87  mov     eax, edx
0x18002ec89  shr     eax, 0Eh
0x18002ec8c  shr     ecx, 4
0x18002ec8f  and     eax, 3
0x18002ec92  and     ecx, 3
0x18002ec95  mov     [rbx+8], eax
0x18002ec98  mov     [rbx], ecx
0x18002ec9a  mov     eax, edx
0x18002ec9c  mov     ecx, edx
0x18002ec9e  shr     eax, 6
0x18002eca1  shr     ecx, 8
0x18002eca4  and     eax, r9d
0x18002eca7  and     cl, 3Fh
0x18002ecaa  shr     edx, 7
0x18002ecad  and     edx, r9d
0x18002ecb0  mov     [rbx+4], cl
0x18002ecb3  mov     [rbx+10h], edx
0x18002ecb6  mov     [rbx+14h], eax
0x18002ecb9  jmp     loc_18002EC29
0x18002ecbe  cmp     eax, 117h
0x18002ecc3  jnz     loc_18002EC26
0x18002ecc9  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18002eccd  mov     r9d, 1
0x18002ecd3  shr     eax, 7
0x18002ecd6  and     eax, r9d
0x18002ecd9  mov     [rbx+10h], eax
0x18002ecdc  jmp     loc_18002EC29
```
