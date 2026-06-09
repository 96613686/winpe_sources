# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18001af34`
- end: `0x18001b059`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800178ec`

## callees

- `0x180014130`
- `0x18001aca0`
- `0x18001af34`
- `0x180025010`

## string_xrefs

- `0x18001af80`: `RtlQueryFeatureConfiguration`

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
0x18001af34  mov     [rsp+arg_10], rbx
0x18001af39  push    rbp
0x18001af3a  push    rsi
0x18001af3b  push    rdi
0x18001af3c  sub     rsp, 50h
0x18001af40  mov     rax, cs:__security_cookie
0x18001af47  xor     rax, rsp
0x18001af4a  mov     [rsp+68h+var_20], rax
0x18001af4f  xor     esi, esi
0x18001af51  mov     [rsp+68h+var_38], 0
0x18001af5a  test    r8d, r8d
0x18001af5d  mov     rdi, r9
0x18001af60  mov     ebp, edx
0x18001af62  mov     rbx, rcx
0x18001af65  setz    sil
0x18001af69  xor     eax, eax
0x18001af6b  mov     [rsp+68h+var_30], rax
0x18001af70  mov     [rsp+68h+var_28], eax
0x18001af74  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001af7b  test    rax, rax
0x18001af7e  jnz     short loc_18001AFD4
0x18001af80  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001af87  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001af8c  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18001af93  test    rax, rax
0x18001af96  jnz     short loc_18001AFD4
0x18001af98  mov     r8d, 0C0000139h
0x18001af9e  xor     r9d, r9d
0x18001afa1  test    rdi, rdi
0x18001afa4  jz      short loc_18001AFB4
0x18001afa6  xor     ecx, ecx
0x18001afa8  cmp     r8d, 80000022h
0x18001afaf  setnz   cl
0x18001afb2  mov     [rdi], ecx
0x18001afb4  mov     eax, r9d
0x18001afb7  mov     rcx, [rsp+68h+var_20]
0x18001afbc  xor     rcx, rsp; StackCookie
0x18001afbf  call    __security_check_cookie
0x18001afc4  mov     rbx, [rsp+68h+arg_10]
0x18001afcc  add     rsp, 50h
0x18001afd0  pop     rdi
0x18001afd1  pop     rsi
0x18001afd2  pop     rbp
0x18001afd3  retn
0x18001afd4  lea     r9, [rsp+68h+var_30]
0x18001afd9  mov     edx, esi
0x18001afdb  lea     r8, [rsp+68h+var_38]
0x18001afe0  mov     ecx, ebp
0x18001afe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afe7  mov     r8d, eax
0x18001afea  test    eax, eax
0x18001afec  jnz     short loc_18001B036
0x18001afee  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18001aff2  lea     r9d, [r8+1]
0x18001aff6  mov     eax, [rsp+68h+var_28]
0x18001affa  mov     ecx, edx
0x18001affc  mov     [rbx+0Ch], eax
0x18001afff  mov     eax, edx
0x18001b001  shr     eax, 0Eh
0x18001b004  shr     ecx, 4
0x18001b007  and     eax, 3
0x18001b00a  and     ecx, 3
0x18001b00d  mov     [rbx+8], eax
0x18001b010  mov     [rbx], ecx
0x18001b012  mov     eax, edx
0x18001b014  mov     ecx, edx
0x18001b016  shr     eax, 6
0x18001b019  shr     ecx, 8
0x18001b01c  and     eax, r9d
0x18001b01f  and     cl, 3Fh
0x18001b022  shr     edx, 7
0x18001b025  and     edx, r9d
0x18001b028  mov     [rbx+4], cl
0x18001b02b  mov     [rbx+10h], edx
0x18001b02e  mov     [rbx+14h], eax
0x18001b031  jmp     loc_18001AFA1
0x18001b036  cmp     eax, 117h
0x18001b03b  jnz     loc_18001AF9E
0x18001b041  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18001b045  mov     r9d, 1
0x18001b04b  shr     eax, 7
0x18001b04e  and     eax, r9d
0x18001b051  mov     [rbx+10h], eax
0x18001b054  jmp     loc_18001AFA1
```
