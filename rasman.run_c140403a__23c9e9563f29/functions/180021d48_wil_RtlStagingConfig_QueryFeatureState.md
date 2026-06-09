# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180021d48`
- end: `0x180021e3a`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180022550`

## callees

- `0x180021d48`
- `0x180022664`
- `0x180026400`
- `0x180027010`

## string_xrefs

- `0x180021d93`: `RtlQueryFeatureConfiguration`

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
0x180021d48  mov     r11, rsp
0x180021d4b  mov     [r11+18h], rbx
0x180021d4f  mov     [r11+20h], rsi
0x180021d53  push    rdi
0x180021d54  sub     rsp, 50h
0x180021d58  mov     rax, cs:__security_cookie
0x180021d5f  xor     rax, rsp
0x180021d62  mov     [rsp+58h+var_10], rax
0x180021d67  xor     edi, edi
0x180021d69  mov     qword ptr [r11-28h], 0
0x180021d71  test    r8d, r8d
0x180021d74  mov     esi, edx
0x180021d76  mov     rbx, rcx
0x180021d79  setz    dil
0x180021d7d  xor     eax, eax
0x180021d7f  mov     [r11-20h], rax
0x180021d83  mov     [rsp+58h+var_18], eax
0x180021d87  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180021d8e  test    rax, rax
0x180021d91  jnz     short loc_180021DAF
0x180021d93  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180021d9a  call    wil_details_GetNtDllProcedureAddress
0x180021d9f  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180021da6  test    rax, rax
0x180021da9  jnz     short loc_180021DAF
0x180021dab  xor     edx, edx
0x180021dad  jmp     short loc_180021E1B
0x180021daf  lea     r9, [rsp+58h+var_20]
0x180021db4  mov     edx, edi
0x180021db6  lea     r8, [rsp+58h+var_28]
0x180021dbb  mov     ecx, esi
0x180021dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dc2  test    eax, eax
0x180021dc4  jnz     short loc_180021E01
0x180021dc6  mov     ecx, [rsp+58h+var_1C]
0x180021dca  mov     edx, 1
0x180021dcf  mov     eax, ecx
0x180021dd1  shr     eax, 4
0x180021dd4  and     eax, 3
0x180021dd7  mov     [rbx], eax
0x180021dd9  mov     eax, ecx
0x180021ddb  shr     eax, 8
0x180021dde  and     al, 3Fh
0x180021de0  mov     [rbx+4], al
0x180021de3  mov     eax, [rsp+58h+var_18]
0x180021de7  mov     [rbx+0Ch], eax
0x180021dea  mov     eax, ecx
0x180021dec  shr     eax, 0Eh
0x180021def  and     eax, 3
0x180021df2  mov     [rbx+8], eax
0x180021df5  mov     eax, ecx
0x180021df7  shr     eax, 6
0x180021dfa  and     eax, edx
0x180021dfc  mov     [rbx+14h], eax
0x180021dff  jmp     short loc_180021E13
0x180021e01  xor     edx, edx
0x180021e03  cmp     eax, 117h
0x180021e08  jnz     short loc_180021E1B
0x180021e0a  mov     ecx, [rsp+58h+var_1C]
0x180021e0e  mov     edx, 1
0x180021e13  shr     ecx, 7
0x180021e16  and     ecx, edx
0x180021e18  mov     [rbx+10h], ecx
0x180021e1b  mov     eax, edx
0x180021e1d  mov     rcx, [rsp+58h+var_10]
0x180021e22  xor     rcx, rsp; StackCookie
0x180021e25  call    __security_check_cookie
0x180021e2a  mov     rbx, [rsp+58h+arg_10]
0x180021e2f  mov     rsi, [rsp+58h+arg_18]
0x180021e34  add     rsp, 50h
0x180021e38  pop     rdi
0x180021e39  retn
```
