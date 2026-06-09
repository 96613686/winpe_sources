# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180015080`
- end: `0x180015172`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180044ae4`

## callees

- `0x180015080`
- `0x18001ac7c`
- `0x18001cef0`
- `0x18004f010`

## string_xrefs

- `0x1800150cb`: `RtlQueryFeatureConfiguration`

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
0x180015080  mov     r11, rsp
0x180015083  mov     [r11+18h], rbx
0x180015087  mov     [r11+20h], rsi
0x18001508b  push    rdi
0x18001508c  sub     rsp, 50h
0x180015090  mov     rax, cs:__security_cookie
0x180015097  xor     rax, rsp
0x18001509a  mov     [rsp+58h+var_10], rax
0x18001509f  xor     edi, edi
0x1800150a1  mov     qword ptr [r11-28h], 0
0x1800150a9  test    r8d, r8d
0x1800150ac  mov     esi, edx
0x1800150ae  mov     rbx, rcx
0x1800150b1  setz    dil
0x1800150b5  xor     eax, eax
0x1800150b7  mov     [r11-20h], rax
0x1800150bb  mov     [rsp+58h+var_18], eax
0x1800150bf  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800150c6  test    rax, rax
0x1800150c9  jnz     short loc_1800150E7
0x1800150cb  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1800150d2  call    wil_details_GetNtDllProcedureAddress
0x1800150d7  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1800150de  test    rax, rax
0x1800150e1  jnz     short loc_1800150E7
0x1800150e3  xor     edx, edx
0x1800150e5  jmp     short loc_180015153
0x1800150e7  lea     r9, [rsp+58h+var_20]
0x1800150ec  mov     edx, edi
0x1800150ee  lea     r8, [rsp+58h+var_28]
0x1800150f3  mov     ecx, esi
0x1800150f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150fa  test    eax, eax
0x1800150fc  jnz     short loc_180015139
0x1800150fe  mov     ecx, [rsp+58h+var_1C]
0x180015102  mov     edx, 1
0x180015107  mov     eax, ecx
0x180015109  shr     eax, 4
0x18001510c  and     eax, 3
0x18001510f  mov     [rbx], eax
0x180015111  mov     eax, ecx
0x180015113  shr     eax, 8
0x180015116  and     al, 3Fh
0x180015118  mov     [rbx+4], al
0x18001511b  mov     eax, [rsp+58h+var_18]
0x18001511f  mov     [rbx+0Ch], eax
0x180015122  mov     eax, ecx
0x180015124  shr     eax, 0Eh
0x180015127  and     eax, 3
0x18001512a  mov     [rbx+8], eax
0x18001512d  mov     eax, ecx
0x18001512f  shr     eax, 6
0x180015132  and     eax, edx
0x180015134  mov     [rbx+14h], eax
0x180015137  jmp     short loc_18001514B
0x180015139  xor     edx, edx
0x18001513b  cmp     eax, 117h
0x180015140  jnz     short loc_180015153
0x180015142  mov     ecx, [rsp+58h+var_1C]
0x180015146  mov     edx, 1
0x18001514b  shr     ecx, 7
0x18001514e  and     ecx, edx
0x180015150  mov     [rbx+10h], ecx
0x180015153  mov     eax, edx
0x180015155  mov     rcx, [rsp+58h+var_10]
0x18001515a  xor     rcx, rsp; StackCookie
0x18001515d  call    __security_check_cookie
0x180015162  mov     rbx, [rsp+58h+arg_10]
0x180015167  mov     rsi, [rsp+58h+arg_18]
0x18001516c  add     rsp, 50h
0x180015170  pop     rdi
0x180015171  retn
```
