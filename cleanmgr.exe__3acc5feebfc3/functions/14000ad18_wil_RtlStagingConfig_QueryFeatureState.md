# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x14000ad18`
- end: `0x14000ae3d`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140007a20`

## callees

- `0x1400029a0`
- `0x140006980`
- `0x14000ad18`
- `0x140018010`

## string_xrefs

- `0x14000ad64`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  BOOL v7; // esi
  FARPROC NtDllProcedureAddress; // rax
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
  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
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
0x14000ad18  mov     [rsp+arg_10], rbx
0x14000ad1d  push    rbp
0x14000ad1e  push    rsi
0x14000ad1f  push    rdi
0x14000ad20  sub     rsp, 50h
0x14000ad24  mov     rax, cs:__security_cookie
0x14000ad2b  xor     rax, rsp
0x14000ad2e  mov     [rsp+68h+var_20], rax
0x14000ad33  xor     esi, esi
0x14000ad35  mov     [rsp+68h+var_38], 0
0x14000ad3e  test    r8d, r8d
0x14000ad41  mov     rdi, r9
0x14000ad44  mov     ebp, edx
0x14000ad46  mov     rbx, rcx
0x14000ad49  setz    sil
0x14000ad4d  xor     eax, eax
0x14000ad4f  mov     [rsp+68h+var_30], rax
0x14000ad54  mov     [rsp+68h+var_28], eax
0x14000ad58  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000ad5f  test    rax, rax
0x14000ad62  jnz     short loc_14000ADB8
0x14000ad64  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000ad6b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000ad70  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000ad77  test    rax, rax
0x14000ad7a  jnz     short loc_14000ADB8
0x14000ad7c  mov     r8d, 0C0000139h
0x14000ad82  xor     r9d, r9d
0x14000ad85  test    rdi, rdi
0x14000ad88  jz      short loc_14000AD98
0x14000ad8a  xor     ecx, ecx
0x14000ad8c  cmp     r8d, 80000022h
0x14000ad93  setnz   cl
0x14000ad96  mov     [rdi], ecx
0x14000ad98  mov     eax, r9d
0x14000ad9b  mov     rcx, [rsp+68h+var_20]
0x14000ada0  xor     rcx, rsp; StackCookie
0x14000ada3  call    __security_check_cookie
0x14000ada8  mov     rbx, [rsp+68h+arg_10]
0x14000adb0  add     rsp, 50h
0x14000adb4  pop     rdi
0x14000adb5  pop     rsi
0x14000adb6  pop     rbp
0x14000adb7  retn
0x14000adb8  lea     r9, [rsp+68h+var_30]
0x14000adbd  mov     edx, esi
0x14000adbf  lea     r8, [rsp+68h+var_38]
0x14000adc4  mov     ecx, ebp
0x14000adc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000adcb  mov     r8d, eax
0x14000adce  test    eax, eax
0x14000add0  jnz     short loc_14000AE1A
0x14000add2  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14000add6  lea     r9d, [r8+1]
0x14000adda  mov     eax, [rsp+68h+var_28]
0x14000adde  mov     ecx, edx
0x14000ade0  mov     [rbx+0Ch], eax
0x14000ade3  mov     eax, edx
0x14000ade5  shr     eax, 0Eh
0x14000ade8  shr     ecx, 4
0x14000adeb  and     eax, 3
0x14000adee  and     ecx, 3
0x14000adf1  mov     [rbx+8], eax
0x14000adf4  mov     [rbx], ecx
0x14000adf6  mov     eax, edx
0x14000adf8  mov     ecx, edx
0x14000adfa  shr     eax, 6
0x14000adfd  shr     ecx, 8
0x14000ae00  and     eax, r9d
0x14000ae03  and     cl, 3Fh
0x14000ae06  shr     edx, 7
0x14000ae09  and     edx, r9d
0x14000ae0c  mov     [rbx+4], cl
0x14000ae0f  mov     [rbx+10h], edx
0x14000ae12  mov     [rbx+14h], eax
0x14000ae15  jmp     loc_14000AD85
0x14000ae1a  cmp     eax, 117h
0x14000ae1f  jnz     loc_14000AD82
0x14000ae25  mov     eax, dword ptr [rsp+68h+var_30+4]
0x14000ae29  mov     r9d, 1
0x14000ae2f  shr     eax, 7
0x14000ae32  and     eax, r9d
0x14000ae35  mov     [rbx+10h], eax
0x14000ae38  jmp     loc_14000AD85
```
