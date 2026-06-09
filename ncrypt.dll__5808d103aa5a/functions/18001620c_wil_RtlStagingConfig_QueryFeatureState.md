# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18001620c`
- end: `0x1800162fe`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180014f18`

## callees

- `0x18001620c`
- `0x180019a54`
- `0x18001f1b0`
- `0x180020010`

## string_xrefs

- `0x180016257`: `RtlQueryFeatureConfiguration`

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
0x18001620c  mov     r11, rsp
0x18001620f  mov     [r11+18h], rbx
0x180016213  mov     [r11+20h], rsi
0x180016217  push    rdi
0x180016218  sub     rsp, 50h
0x18001621c  mov     rax, cs:__security_cookie
0x180016223  xor     rax, rsp
0x180016226  mov     [rsp+58h+var_10], rax
0x18001622b  xor     edi, edi
0x18001622d  mov     qword ptr [r11-28h], 0
0x180016235  test    r8d, r8d
0x180016238  mov     esi, edx
0x18001623a  mov     rbx, rcx
0x18001623d  setz    dil
0x180016241  xor     eax, eax
0x180016243  mov     [r11-20h], rax
0x180016247  mov     [rsp+58h+var_18], eax
0x18001624b  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180016252  test    rax, rax
0x180016255  jnz     short loc_180016273
0x180016257  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001625e  call    wil_details_GetNtDllProcedureAddress
0x180016263  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18001626a  test    rax, rax
0x18001626d  jnz     short loc_180016273
0x18001626f  xor     edx, edx
0x180016271  jmp     short loc_1800162DF
0x180016273  lea     r9, [rsp+58h+var_20]
0x180016278  mov     edx, edi
0x18001627a  lea     r8, [rsp+58h+var_28]
0x18001627f  mov     ecx, esi
0x180016281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016286  test    eax, eax
0x180016288  jnz     short loc_1800162C5
0x18001628a  mov     ecx, [rsp+58h+var_1C]
0x18001628e  mov     edx, 1
0x180016293  mov     eax, ecx
0x180016295  shr     eax, 4
0x180016298  and     eax, 3
0x18001629b  mov     [rbx], eax
0x18001629d  mov     eax, ecx
0x18001629f  shr     eax, 8
0x1800162a2  and     al, 3Fh
0x1800162a4  mov     [rbx+4], al
0x1800162a7  mov     eax, [rsp+58h+var_18]
0x1800162ab  mov     [rbx+0Ch], eax
0x1800162ae  mov     eax, ecx
0x1800162b0  shr     eax, 0Eh
0x1800162b3  and     eax, 3
0x1800162b6  mov     [rbx+8], eax
0x1800162b9  mov     eax, ecx
0x1800162bb  shr     eax, 6
0x1800162be  and     eax, edx
0x1800162c0  mov     [rbx+14h], eax
0x1800162c3  jmp     short loc_1800162D7
0x1800162c5  xor     edx, edx
0x1800162c7  cmp     eax, 117h
0x1800162cc  jnz     short loc_1800162DF
0x1800162ce  mov     ecx, [rsp+58h+var_1C]
0x1800162d2  mov     edx, 1
0x1800162d7  shr     ecx, 7
0x1800162da  and     ecx, edx
0x1800162dc  mov     [rbx+10h], ecx
0x1800162df  mov     eax, edx
0x1800162e1  mov     rcx, [rsp+58h+var_10]
0x1800162e6  xor     rcx, rsp; StackCookie
0x1800162e9  call    __security_check_cookie
0x1800162ee  mov     rbx, [rsp+58h+arg_10]
0x1800162f3  mov     rsi, [rsp+58h+arg_18]
0x1800162f8  add     rsp, 50h
0x1800162fc  pop     rdi
0x1800162fd  retn
```
