# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1800176e4`
- end: `0x180017809`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180013b80`

## callees

- `0x18000a520`
- `0x18000f020`
- `0x1800176e4`
- `0x180020010`

## string_xrefs

- `0x180017730`: `RtlQueryFeatureConfiguration`

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
0x1800176e4  mov     [rsp+arg_10], rbx
0x1800176e9  push    rbp
0x1800176ea  push    rsi
0x1800176eb  push    rdi
0x1800176ec  sub     rsp, 50h
0x1800176f0  mov     rax, cs:__security_cookie
0x1800176f7  xor     rax, rsp
0x1800176fa  mov     [rsp+68h+var_20], rax
0x1800176ff  xor     esi, esi
0x180017701  mov     [rsp+68h+var_38], 0
0x18001770a  test    r8d, r8d
0x18001770d  mov     rdi, r9
0x180017710  mov     ebp, edx
0x180017712  mov     rbx, rcx
0x180017715  setz    sil
0x180017719  xor     eax, eax
0x18001771b  mov     [rsp+68h+var_30], rax
0x180017720  mov     [rsp+68h+var_28], eax
0x180017724  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001772b  test    rax, rax
0x18001772e  jnz     short loc_180017784
0x180017730  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180017737  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001773c  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180017743  test    rax, rax
0x180017746  jnz     short loc_180017784
0x180017748  mov     r8d, 0C0000139h
0x18001774e  xor     r9d, r9d
0x180017751  test    rdi, rdi
0x180017754  jz      short loc_180017764
0x180017756  xor     ecx, ecx
0x180017758  cmp     r8d, 80000022h
0x18001775f  setnz   cl
0x180017762  mov     [rdi], ecx
0x180017764  mov     eax, r9d
0x180017767  mov     rcx, [rsp+68h+var_20]
0x18001776c  xor     rcx, rsp; StackCookie
0x18001776f  call    __security_check_cookie
0x180017774  mov     rbx, [rsp+68h+arg_10]
0x18001777c  add     rsp, 50h
0x180017780  pop     rdi
0x180017781  pop     rsi
0x180017782  pop     rbp
0x180017783  retn
0x180017784  lea     r9, [rsp+68h+var_30]
0x180017789  mov     edx, esi
0x18001778b  lea     r8, [rsp+68h+var_38]
0x180017790  mov     ecx, ebp
0x180017792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017797  mov     r8d, eax
0x18001779a  test    eax, eax
0x18001779c  jnz     short loc_1800177E6
0x18001779e  mov     edx, dword ptr [rsp+68h+var_30+4]
0x1800177a2  lea     r9d, [r8+1]
0x1800177a6  mov     eax, [rsp+68h+var_28]
0x1800177aa  mov     ecx, edx
0x1800177ac  mov     [rbx+0Ch], eax
0x1800177af  mov     eax, edx
0x1800177b1  shr     eax, 0Eh
0x1800177b4  shr     ecx, 4
0x1800177b7  and     eax, 3
0x1800177ba  and     ecx, 3
0x1800177bd  mov     [rbx+8], eax
0x1800177c0  mov     [rbx], ecx
0x1800177c2  mov     eax, edx
0x1800177c4  mov     ecx, edx
0x1800177c6  shr     eax, 6
0x1800177c9  shr     ecx, 8
0x1800177cc  and     eax, r9d
0x1800177cf  and     cl, 3Fh
0x1800177d2  shr     edx, 7
0x1800177d5  and     edx, r9d
0x1800177d8  mov     [rbx+4], cl
0x1800177db  mov     [rbx+10h], edx
0x1800177de  mov     [rbx+14h], eax
0x1800177e1  jmp     loc_180017751
0x1800177e6  cmp     eax, 117h
0x1800177eb  jnz     loc_18001774E
0x1800177f1  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800177f5  mov     r9d, 1
0x1800177fb  shr     eax, 7
0x1800177fe  and     eax, r9d
0x180017801  mov     [rbx+10h], eax
0x180017804  jmp     loc_180017751
```
