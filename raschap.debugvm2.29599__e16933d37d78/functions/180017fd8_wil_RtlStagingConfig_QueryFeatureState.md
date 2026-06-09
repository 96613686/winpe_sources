# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180017fd8`
- end: `0x1800180fd`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180018794`
- `0x180020730`

## callees

- `0x180013b20`
- `0x180017fd8`
- `0x1800188ac`
- `0x180027010`

## string_xrefs

- `0x180018024`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  BOOL v7; // esi
  __int64 (__fastcall *NtDllProcedureAddress)(_QWORD, BOOL, __int64 *, __int64 *); // rax
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
  NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))wil_details_GetNtDllProcedureAddress("RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress;
    if ( !NtDllProcedureAddress )
    {
      v9 = -1073741511;
LABEL_4:
      v10 = 0;
      goto LABEL_5;
    }
  }
  v12 = NtDllProcedureAddress(a2, v7, &v15, &v16);
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
0x180017fd8  mov     [rsp+arg_10], rbx
0x180017fdd  push    rbp
0x180017fde  push    rsi
0x180017fdf  push    rdi
0x180017fe0  sub     rsp, 50h
0x180017fe4  mov     rax, cs:__security_cookie
0x180017feb  xor     rax, rsp
0x180017fee  mov     [rsp+68h+var_20], rax
0x180017ff3  xor     esi, esi
0x180017ff5  mov     [rsp+68h+var_38], 0
0x180017ffe  test    r8d, r8d
0x180018001  mov     rdi, r9
0x180018004  mov     ebp, edx
0x180018006  mov     rbx, rcx
0x180018009  setz    sil
0x18001800d  xor     eax, eax
0x18001800f  mov     [rsp+68h+var_30], rax
0x180018014  mov     [rsp+68h+var_28], eax
0x180018018  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001801f  test    rax, rax
0x180018022  jnz     short loc_180018078
0x180018024  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001802b  call    wil_details_GetNtDllProcedureAddress
0x180018030  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180018037  test    rax, rax
0x18001803a  jnz     short loc_180018078
0x18001803c  mov     r8d, 0C0000139h
0x180018042  xor     r9d, r9d
0x180018045  test    rdi, rdi
0x180018048  jz      short loc_180018058
0x18001804a  xor     ecx, ecx
0x18001804c  cmp     r8d, 80000022h
0x180018053  setnz   cl
0x180018056  mov     [rdi], ecx
0x180018058  mov     eax, r9d
0x18001805b  mov     rcx, [rsp+68h+var_20]
0x180018060  xor     rcx, rsp; StackCookie
0x180018063  call    __security_check_cookie
0x180018068  mov     rbx, [rsp+68h+arg_10]
0x180018070  add     rsp, 50h
0x180018074  pop     rdi
0x180018075  pop     rsi
0x180018076  pop     rbp
0x180018077  retn
0x180018078  lea     r9, [rsp+68h+var_30]
0x18001807d  mov     edx, esi
0x18001807f  lea     r8, [rsp+68h+var_38]
0x180018084  mov     ecx, ebp
0x180018086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001808b  mov     r8d, eax
0x18001808e  test    eax, eax
0x180018090  jnz     short loc_1800180DA
0x180018092  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180018096  lea     r9d, [r8+1]
0x18001809a  mov     eax, [rsp+68h+var_28]
0x18001809e  mov     ecx, edx
0x1800180a0  mov     [rbx+0Ch], eax
0x1800180a3  mov     eax, edx
0x1800180a5  shr     eax, 0Eh
0x1800180a8  shr     ecx, 4
0x1800180ab  and     eax, 3
0x1800180ae  and     ecx, 3
0x1800180b1  mov     [rbx+8], eax
0x1800180b4  mov     [rbx], ecx
0x1800180b6  mov     eax, edx
0x1800180b8  mov     ecx, edx
0x1800180ba  shr     eax, 6
0x1800180bd  shr     ecx, 8
0x1800180c0  and     eax, r9d
0x1800180c3  and     cl, 3Fh
0x1800180c6  shr     edx, 7
0x1800180c9  and     edx, r9d
0x1800180cc  mov     [rbx+4], cl
0x1800180cf  mov     [rbx+10h], edx
0x1800180d2  mov     [rbx+14h], eax
0x1800180d5  jmp     loc_180018045
0x1800180da  cmp     eax, 117h
0x1800180df  jnz     loc_180018042
0x1800180e5  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800180e9  mov     r9d, 1
0x1800180ef  shr     eax, 7
0x1800180f2  and     eax, r9d
0x1800180f5  mov     [rbx+10h], eax
0x1800180f8  jmp     loc_180018045
```
