# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000a424`
- end: `0x18000a549`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a3fc`

## callees

- `0x180002620`
- `0x18000a118`
- `0x18000a424`
- `0x180013010`

## string_xrefs

- `0x18000a470`: `RtlQueryFeatureConfiguration`

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
0x18000a424  mov     [rsp+arg_10], rbx
0x18000a429  push    rbp
0x18000a42a  push    rsi
0x18000a42b  push    rdi
0x18000a42c  sub     rsp, 50h
0x18000a430  mov     rax, cs:__security_cookie
0x18000a437  xor     rax, rsp
0x18000a43a  mov     [rsp+68h+var_20], rax
0x18000a43f  xor     esi, esi
0x18000a441  mov     [rsp+68h+var_28], 0
0x18000a44a  test    r8d, r8d
0x18000a44d  mov     rdi, r9
0x18000a450  mov     ebp, edx
0x18000a452  mov     rbx, rcx
0x18000a455  setz    sil
0x18000a459  xor     eax, eax
0x18000a45b  mov     [rsp+68h+var_38], rax
0x18000a460  mov     [rsp+68h+var_30], eax
0x18000a464  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000a46b  test    rax, rax
0x18000a46e  jnz     short loc_18000A4C4
0x18000a470  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000a477  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000a47c  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000a483  test    rax, rax
0x18000a486  jnz     short loc_18000A4C4
0x18000a488  mov     r8d, 0C0000139h
0x18000a48e  xor     r9d, r9d
0x18000a491  test    rdi, rdi
0x18000a494  jz      short loc_18000A4A4
0x18000a496  xor     ecx, ecx
0x18000a498  cmp     r8d, 80000022h
0x18000a49f  setnz   cl
0x18000a4a2  mov     [rdi], ecx
0x18000a4a4  mov     eax, r9d
0x18000a4a7  mov     rcx, [rsp+68h+var_20]
0x18000a4ac  xor     rcx, rsp; StackCookie
0x18000a4af  call    __security_check_cookie
0x18000a4b4  mov     rbx, [rsp+68h+arg_10]
0x18000a4bc  add     rsp, 50h
0x18000a4c0  pop     rdi
0x18000a4c1  pop     rsi
0x18000a4c2  pop     rbp
0x18000a4c3  retn
0x18000a4c4  lea     r9, [rsp+68h+var_38]
0x18000a4c9  mov     edx, esi
0x18000a4cb  lea     r8, [rsp+68h+var_28]
0x18000a4d0  mov     ecx, ebp
0x18000a4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4d7  mov     r8d, eax
0x18000a4da  test    eax, eax
0x18000a4dc  jnz     short loc_18000A526
0x18000a4de  mov     edx, dword ptr [rsp+68h+var_38+4]
0x18000a4e2  lea     r9d, [r8+1]
0x18000a4e6  mov     eax, [rsp+68h+var_30]
0x18000a4ea  mov     ecx, edx
0x18000a4ec  mov     [rbx+0Ch], eax
0x18000a4ef  mov     eax, edx
0x18000a4f1  shr     eax, 0Eh
0x18000a4f4  shr     ecx, 4
0x18000a4f7  and     eax, 3
0x18000a4fa  and     ecx, 3
0x18000a4fd  mov     [rbx+8], eax
0x18000a500  mov     [rbx], ecx
0x18000a502  mov     eax, edx
0x18000a504  mov     ecx, edx
0x18000a506  shr     eax, 6
0x18000a509  shr     ecx, 8
0x18000a50c  and     eax, r9d
0x18000a50f  and     cl, 3Fh
0x18000a512  shr     edx, 7
0x18000a515  and     edx, r9d
0x18000a518  mov     [rbx+4], cl
0x18000a51b  mov     [rbx+10h], edx
0x18000a51e  mov     [rbx+14h], eax
0x18000a521  jmp     loc_18000A491
0x18000a526  cmp     eax, 117h
0x18000a52b  jnz     loc_18000A48E
0x18000a531  mov     eax, dword ptr [rsp+68h+var_38+4]
0x18000a535  mov     r9d, 1
0x18000a53b  shr     eax, 7
0x18000a53e  and     eax, r9d
0x18000a541  mov     [rbx+10h], eax
0x18000a544  jmp     loc_18000A491
```
