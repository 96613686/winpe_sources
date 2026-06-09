# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1800096d0`
- end: `0x1800097f5`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180005030`

## callees

- `0x180009140`
- `0x1800096d0`
- `0x18002e230`
- `0x180030010`

## string_xrefs

- `0x18000971c`: `RtlQueryFeatureConfiguration`

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
0x1800096d0  mov     [rsp+arg_10], rbx
0x1800096d5  push    rbp
0x1800096d6  push    rsi
0x1800096d7  push    rdi
0x1800096d8  sub     rsp, 50h
0x1800096dc  mov     rax, cs:__security_cookie
0x1800096e3  xor     rax, rsp
0x1800096e6  mov     [rsp+68h+var_20], rax
0x1800096eb  xor     esi, esi
0x1800096ed  mov     [rsp+68h+var_38], 0
0x1800096f6  test    r8d, r8d
0x1800096f9  mov     rdi, r9
0x1800096fc  mov     ebp, edx
0x1800096fe  mov     rbx, rcx
0x180009701  setz    sil
0x180009705  xor     eax, eax
0x180009707  mov     [rsp+68h+var_30], rax
0x18000970c  mov     [rsp+68h+var_28], eax
0x180009710  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180009717  test    rax, rax
0x18000971a  jnz     short loc_180009770
0x18000971c  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180009723  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180009728  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000972f  test    rax, rax
0x180009732  jnz     short loc_180009770
0x180009734  mov     r8d, 0C0000139h
0x18000973a  xor     r9d, r9d
0x18000973d  test    rdi, rdi
0x180009740  jz      short loc_180009750
0x180009742  xor     ecx, ecx
0x180009744  cmp     r8d, 80000022h
0x18000974b  setnz   cl
0x18000974e  mov     [rdi], ecx
0x180009750  mov     eax, r9d
0x180009753  mov     rcx, [rsp+68h+var_20]
0x180009758  xor     rcx, rsp; StackCookie
0x18000975b  call    __security_check_cookie
0x180009760  mov     rbx, [rsp+68h+arg_10]
0x180009768  add     rsp, 50h
0x18000976c  pop     rdi
0x18000976d  pop     rsi
0x18000976e  pop     rbp
0x18000976f  retn
0x180009770  lea     r9, [rsp+68h+var_30]
0x180009775  mov     edx, esi
0x180009777  lea     r8, [rsp+68h+var_38]
0x18000977c  mov     ecx, ebp
0x18000977e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009783  mov     r8d, eax
0x180009786  test    eax, eax
0x180009788  jnz     short loc_1800097D2
0x18000978a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000978e  lea     r9d, [r8+1]
0x180009792  mov     eax, [rsp+68h+var_28]
0x180009796  mov     ecx, edx
0x180009798  mov     [rbx+0Ch], eax
0x18000979b  mov     eax, edx
0x18000979d  shr     eax, 0Eh
0x1800097a0  shr     ecx, 4
0x1800097a3  and     eax, 3
0x1800097a6  and     ecx, 3
0x1800097a9  mov     [rbx+8], eax
0x1800097ac  mov     [rbx], ecx
0x1800097ae  mov     eax, edx
0x1800097b0  mov     ecx, edx
0x1800097b2  shr     eax, 6
0x1800097b5  shr     ecx, 8
0x1800097b8  and     eax, r9d
0x1800097bb  and     cl, 3Fh
0x1800097be  shr     edx, 7
0x1800097c1  and     edx, r9d
0x1800097c4  mov     [rbx+4], cl
0x1800097c7  mov     [rbx+10h], edx
0x1800097ca  mov     [rbx+14h], eax
0x1800097cd  jmp     loc_18000973D
0x1800097d2  cmp     eax, 117h
0x1800097d7  jnz     loc_18000973A
0x1800097dd  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800097e1  mov     r9d, 1
0x1800097e7  shr     eax, 7
0x1800097ea  and     eax, r9d
0x1800097ed  mov     [rbx+10h], eax
0x1800097f0  jmp     loc_18000973D
```
