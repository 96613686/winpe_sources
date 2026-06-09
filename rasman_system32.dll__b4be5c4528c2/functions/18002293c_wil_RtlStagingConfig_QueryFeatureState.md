# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18002293c`
- end: `0x180022a2f`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180023004`

## callees

- `0x18002293c`
- `0x180023154`
- `0x1800273d0`
- `0x180028010`

## string_xrefs

- `0x180022987`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3)
{
  BOOL v5; // edi
  __int64 (__fastcall *NtDllProcedureAddress)(_QWORD, BOOL, __int64 *, __int64 *); // rax
  unsigned int v7; // edx
  int v8; // eax
  unsigned int v9; // ecx
  __int64 v11; // [rsp+30h] [rbp-28h] BYREF
  __int64 v12; // [rsp+38h] [rbp-20h] BYREF
  int v13; // [rsp+40h] [rbp-18h]

  v11 = 0;
  v5 = a3 == 0;
  v12 = 0;
  v13 = 0;
  NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( g_wil_details_pfnRtlQueryFeatureConfiguration
    || (NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))wil_details_GetNtDllProcedureAddress(
                                                                                              "RtlQueryFeatureConfiguration"),
        (g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress) != 0) )
  {
    v8 = NtDllProcedureAddress(a2, v5, &v11, &v12);
    if ( v8 )
    {
      v7 = 0;
      if ( v8 != 279 )
        return v7;
      v9 = HIDWORD(v12);
      v7 = 1;
    }
    else
    {
      v9 = HIDWORD(v12);
      v7 = 1;
      *(_DWORD *)a1 = (HIDWORD(v12) >> 4) & 3;
      *(_BYTE *)(a1 + 4) = BYTE1(v9) & 0x3F;
      *(_DWORD *)(a1 + 12) = v13;
      *(_DWORD *)(a1 + 8) = (unsigned __int16)v9 >> 14;
      *(_DWORD *)(a1 + 20) = (v9 >> 6) & 1;
    }
    *(_DWORD *)(a1 + 16) = (v9 >> 7) & 1;
    return v7;
  }
  return 0;
}

```

## disassembly

```asm
0x18002293c  mov     r11, rsp
0x18002293f  mov     [r11+18h], rbx
0x180022943  mov     [r11+20h], rsi
0x180022947  push    rdi
0x180022948  sub     rsp, 50h
0x18002294c  mov     rax, cs:__security_cookie
0x180022953  xor     rax, rsp
0x180022956  mov     [rsp+58h+var_10], rax
0x18002295b  xor     edi, edi
0x18002295d  mov     qword ptr [r11-28h], 0
0x180022965  test    r8d, r8d
0x180022968  mov     esi, edx
0x18002296a  mov     rbx, rcx
0x18002296d  setz    dil
0x180022971  xor     eax, eax
0x180022973  mov     [r11-20h], rax
0x180022977  mov     [rsp+58h+var_18], eax
0x18002297b  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180022982  test    rax, rax
0x180022985  jnz     short loc_1800229A3
0x180022987  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18002298e  call    wil_details_GetNtDllProcedureAddress
0x180022993  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18002299a  test    rax, rax
0x18002299d  jnz     short loc_1800229A3
0x18002299f  xor     edx, edx
0x1800229a1  jmp     short loc_180022A0F
0x1800229a3  lea     r9, [rsp+58h+var_20]
0x1800229a8  mov     edx, edi
0x1800229aa  lea     r8, [rsp+58h+var_28]
0x1800229af  mov     ecx, esi
0x1800229b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229b6  test    eax, eax
0x1800229b8  jnz     short loc_1800229F5
0x1800229ba  mov     ecx, [rsp+58h+var_1C]
0x1800229be  mov     edx, 1
0x1800229c3  mov     eax, ecx
0x1800229c5  shr     eax, 4
0x1800229c8  and     eax, 3
0x1800229cb  mov     [rbx], eax
0x1800229cd  mov     eax, ecx
0x1800229cf  shr     eax, 8
0x1800229d2  and     al, 3Fh
0x1800229d4  mov     [rbx+4], al
0x1800229d7  mov     eax, [rsp+58h+var_18]
0x1800229db  mov     [rbx+0Ch], eax
0x1800229de  mov     eax, ecx
0x1800229e0  shr     eax, 0Eh
0x1800229e3  and     eax, 3
0x1800229e6  mov     [rbx+8], eax
0x1800229e9  mov     eax, ecx
0x1800229eb  shr     eax, 6
0x1800229ee  and     eax, edx
0x1800229f0  mov     [rbx+14h], eax
0x1800229f3  jmp     short loc_180022A07
0x1800229f5  xor     edx, edx
0x1800229f7  cmp     eax, 117h
0x1800229fc  jnz     short loc_180022A0F
0x1800229fe  mov     ecx, [rsp+58h+var_1C]
0x180022a02  mov     edx, 1
0x180022a07  shr     ecx, 7
0x180022a0a  and     ecx, edx
0x180022a0c  mov     [rbx+10h], ecx
0x180022a0f  mov     eax, edx
0x180022a11  mov     rcx, [rsp+58h+var_10]
0x180022a16  xor     rcx, rsp; StackCookie
0x180022a19  call    __security_check_cookie
0x180022a1e  mov     rbx, [rsp+58h+arg_10]
0x180022a23  mov     rsi, [rsp+58h+arg_18]
0x180022a28  add     rsp, 50h
0x180022a2c  pop     rdi
0x180022a2d  retn
```
