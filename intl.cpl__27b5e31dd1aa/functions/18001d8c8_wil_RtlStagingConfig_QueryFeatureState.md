# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18001d8c8`
- end: `0x18001d9ed`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18001d8a0`

## callees

- `0x1800072f0`
- `0x18001d8c8`
- `0x18002a150`
- `0x18002b010`

## string_xrefs

- `0x18001d914`: `RtlQueryFeatureConfiguration`

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
0x18001d8c8  mov     [rsp+arg_10], rbx
0x18001d8cd  push    rbp
0x18001d8ce  push    rsi
0x18001d8cf  push    rdi
0x18001d8d0  sub     rsp, 50h
0x18001d8d4  mov     rax, cs:__security_cookie
0x18001d8db  xor     rax, rsp
0x18001d8de  mov     [rsp+68h+var_20], rax
0x18001d8e3  xor     esi, esi
0x18001d8e5  mov     [rsp+68h+var_38], 0
0x18001d8ee  test    r8d, r8d
0x18001d8f1  mov     rdi, r9
0x18001d8f4  mov     ebp, edx
0x18001d8f6  mov     rbx, rcx
0x18001d8f9  setz    sil
0x18001d8fd  xor     eax, eax
0x18001d8ff  mov     [rsp+68h+var_30], rax
0x18001d904  mov     [rsp+68h+var_28], eax
0x18001d908  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001d90f  test    rax, rax
0x18001d912  jnz     short loc_18001D968
0x18001d914  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001d91b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001d920  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18001d927  test    rax, rax
0x18001d92a  jnz     short loc_18001D968
0x18001d92c  mov     r8d, 0C0000139h
0x18001d932  xor     r9d, r9d
0x18001d935  test    rdi, rdi
0x18001d938  jz      short loc_18001D948
0x18001d93a  xor     ecx, ecx
0x18001d93c  cmp     r8d, 80000022h
0x18001d943  setnz   cl
0x18001d946  mov     [rdi], ecx
0x18001d948  mov     eax, r9d
0x18001d94b  mov     rcx, [rsp+68h+var_20]
0x18001d950  xor     rcx, rsp; StackCookie
0x18001d953  call    __security_check_cookie
0x18001d958  mov     rbx, [rsp+68h+arg_10]
0x18001d960  add     rsp, 50h
0x18001d964  pop     rdi
0x18001d965  pop     rsi
0x18001d966  pop     rbp
0x18001d967  retn
0x18001d968  lea     r9, [rsp+68h+var_30]
0x18001d96d  mov     edx, esi
0x18001d96f  lea     r8, [rsp+68h+var_38]
0x18001d974  mov     ecx, ebp
0x18001d976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d97b  mov     r8d, eax
0x18001d97e  test    eax, eax
0x18001d980  jnz     short loc_18001D9CA
0x18001d982  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18001d986  lea     r9d, [r8+1]
0x18001d98a  mov     eax, [rsp+68h+var_28]
0x18001d98e  mov     ecx, edx
0x18001d990  mov     [rbx+0Ch], eax
0x18001d993  mov     eax, edx
0x18001d995  shr     eax, 0Eh
0x18001d998  shr     ecx, 4
0x18001d99b  and     eax, 3
0x18001d99e  and     ecx, 3
0x18001d9a1  mov     [rbx+8], eax
0x18001d9a4  mov     [rbx], ecx
0x18001d9a6  mov     eax, edx
0x18001d9a8  mov     ecx, edx
0x18001d9aa  shr     eax, 6
0x18001d9ad  shr     ecx, 8
0x18001d9b0  and     eax, r9d
0x18001d9b3  and     cl, 3Fh
0x18001d9b6  shr     edx, 7
0x18001d9b9  and     edx, r9d
0x18001d9bc  mov     [rbx+4], cl
0x18001d9bf  mov     [rbx+10h], edx
0x18001d9c2  mov     [rbx+14h], eax
0x18001d9c5  jmp     loc_18001D935
0x18001d9ca  cmp     eax, 117h
0x18001d9cf  jnz     loc_18001D932
0x18001d9d5  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18001d9d9  mov     r9d, 1
0x18001d9df  shr     eax, 7
0x18001d9e2  and     eax, r9d
0x18001d9e5  mov     [rbx+10h], eax
0x18001d9e8  jmp     loc_18001D935
```
