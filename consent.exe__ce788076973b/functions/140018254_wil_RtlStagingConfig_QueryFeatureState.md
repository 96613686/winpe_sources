# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x140018254`
- end: `0x140018379`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x14000ff00`
- `0x14001d39c`

## callees

- `0x14000e99c`
- `0x140018254`
- `0x14001e050`
- `0x14001f010`

## string_xrefs

- `0x1400182a0`: `RtlQueryFeatureConfiguration`

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
0x140018254  mov     [rsp+arg_10], rbx
0x140018259  push    rbp
0x14001825a  push    rsi
0x14001825b  push    rdi
0x14001825c  sub     rsp, 50h
0x140018260  mov     rax, cs:__security_cookie
0x140018267  xor     rax, rsp
0x14001826a  mov     [rsp+68h+var_20], rax
0x14001826f  xor     esi, esi
0x140018271  mov     [rsp+68h+var_38], 0
0x14001827a  test    r8d, r8d
0x14001827d  mov     rdi, r9
0x140018280  mov     ebp, edx
0x140018282  mov     rbx, rcx
0x140018285  setz    sil
0x140018289  xor     eax, eax
0x14001828b  mov     [rsp+68h+var_30], rax
0x140018290  mov     [rsp+68h+var_28], eax
0x140018294  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14001829b  test    rax, rax
0x14001829e  jnz     short loc_1400182F4
0x1400182a0  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1400182a7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1400182ac  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1400182b3  test    rax, rax
0x1400182b6  jnz     short loc_1400182F4
0x1400182b8  mov     r8d, 0C0000139h
0x1400182be  xor     r9d, r9d
0x1400182c1  test    rdi, rdi
0x1400182c4  jz      short loc_1400182D4
0x1400182c6  xor     ecx, ecx
0x1400182c8  cmp     r8d, 80000022h
0x1400182cf  setnz   cl
0x1400182d2  mov     [rdi], ecx
0x1400182d4  mov     eax, r9d
0x1400182d7  mov     rcx, [rsp+68h+var_20]
0x1400182dc  xor     rcx, rsp; StackCookie
0x1400182df  call    __security_check_cookie
0x1400182e4  mov     rbx, [rsp+68h+arg_10]
0x1400182ec  add     rsp, 50h
0x1400182f0  pop     rdi
0x1400182f1  pop     rsi
0x1400182f2  pop     rbp
0x1400182f3  retn
0x1400182f4  lea     r9, [rsp+68h+var_30]
0x1400182f9  mov     edx, esi
0x1400182fb  lea     r8, [rsp+68h+var_38]
0x140018300  mov     ecx, ebp
0x140018302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018307  mov     r8d, eax
0x14001830a  test    eax, eax
0x14001830c  jnz     short loc_140018356
0x14001830e  mov     edx, dword ptr [rsp+68h+var_30+4]
0x140018312  lea     r9d, [r8+1]
0x140018316  mov     eax, [rsp+68h+var_28]
0x14001831a  mov     ecx, edx
0x14001831c  mov     [rbx+0Ch], eax
0x14001831f  mov     eax, edx
0x140018321  shr     eax, 0Eh
0x140018324  shr     ecx, 4
0x140018327  and     eax, 3
0x14001832a  and     ecx, 3
0x14001832d  mov     [rbx+8], eax
0x140018330  mov     [rbx], ecx
0x140018332  mov     eax, edx
0x140018334  mov     ecx, edx
0x140018336  shr     eax, 6
0x140018339  shr     ecx, 8
0x14001833c  and     eax, r9d
0x14001833f  and     cl, 3Fh
0x140018342  shr     edx, 7
0x140018345  and     edx, r9d
0x140018348  mov     [rbx+4], cl
0x14001834b  mov     [rbx+10h], edx
0x14001834e  mov     [rbx+14h], eax
0x140018351  jmp     loc_1400182C1
0x140018356  cmp     eax, 117h
0x14001835b  jnz     loc_1400182BE
0x140018361  mov     eax, dword ptr [rsp+68h+var_30+4]
0x140018365  mov     r9d, 1
0x14001836b  shr     eax, 7
0x14001836e  and     eax, r9d
0x140018371  mov     [rbx+10h], eax
0x140018374  jmp     loc_1400182C1
```
