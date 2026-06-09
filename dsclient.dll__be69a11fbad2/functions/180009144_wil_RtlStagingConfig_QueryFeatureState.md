# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180009144`
- end: `0x180009269`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180005fa8`

## callees

- `0x180008f40`
- `0x180009144`
- `0x180009950`
- `0x18000a010`

## string_xrefs

- `0x180009190`: `RtlQueryFeatureConfiguration`

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
0x180009144  mov     [rsp+arg_10], rbx
0x180009149  push    rbp
0x18000914a  push    rsi
0x18000914b  push    rdi
0x18000914c  sub     rsp, 50h
0x180009150  mov     rax, cs:__security_cookie
0x180009157  xor     rax, rsp
0x18000915a  mov     [rsp+68h+var_20], rax
0x18000915f  xor     esi, esi
0x180009161  mov     [rsp+68h+var_38], 0
0x18000916a  test    r8d, r8d
0x18000916d  mov     rdi, r9
0x180009170  mov     ebp, edx
0x180009172  mov     rbx, rcx
0x180009175  setz    sil
0x180009179  xor     eax, eax
0x18000917b  mov     [rsp+68h+var_30], rax
0x180009180  mov     [rsp+68h+var_28], eax
0x180009184  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000918b  test    rax, rax
0x18000918e  jnz     short loc_1800091E4
0x180009190  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180009197  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000919c  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1800091a3  test    rax, rax
0x1800091a6  jnz     short loc_1800091E4
0x1800091a8  mov     r8d, 0C0000139h
0x1800091ae  xor     r9d, r9d
0x1800091b1  test    rdi, rdi
0x1800091b4  jz      short loc_1800091C4
0x1800091b6  xor     ecx, ecx
0x1800091b8  cmp     r8d, 80000022h
0x1800091bf  setnz   cl
0x1800091c2  mov     [rdi], ecx
0x1800091c4  mov     eax, r9d
0x1800091c7  mov     rcx, [rsp+68h+var_20]
0x1800091cc  xor     rcx, rsp; StackCookie
0x1800091cf  call    __security_check_cookie
0x1800091d4  mov     rbx, [rsp+68h+arg_10]
0x1800091dc  add     rsp, 50h
0x1800091e0  pop     rdi
0x1800091e1  pop     rsi
0x1800091e2  pop     rbp
0x1800091e3  retn
0x1800091e4  lea     r9, [rsp+68h+var_30]
0x1800091e9  mov     edx, esi
0x1800091eb  lea     r8, [rsp+68h+var_38]
0x1800091f0  mov     ecx, ebp
0x1800091f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091f7  mov     r8d, eax
0x1800091fa  test    eax, eax
0x1800091fc  jnz     short loc_180009246
0x1800091fe  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180009202  lea     r9d, [r8+1]
0x180009206  mov     eax, [rsp+68h+var_28]
0x18000920a  mov     ecx, edx
0x18000920c  mov     [rbx+0Ch], eax
0x18000920f  mov     eax, edx
0x180009211  shr     eax, 0Eh
0x180009214  shr     ecx, 4
0x180009217  and     eax, 3
0x18000921a  and     ecx, 3
0x18000921d  mov     [rbx+8], eax
0x180009220  mov     [rbx], ecx
0x180009222  mov     eax, edx
0x180009224  mov     ecx, edx
0x180009226  shr     eax, 6
0x180009229  shr     ecx, 8
0x18000922c  and     eax, r9d
0x18000922f  and     cl, 3Fh
0x180009232  shr     edx, 7
0x180009235  and     edx, r9d
0x180009238  mov     [rbx+4], cl
0x18000923b  mov     [rbx+10h], edx
0x18000923e  mov     [rbx+14h], eax
0x180009241  jmp     loc_1800091B1
0x180009246  cmp     eax, 117h
0x18000924b  jnz     loc_1800091AE
0x180009251  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180009255  mov     r9d, 1
0x18000925b  shr     eax, 7
0x18000925e  and     eax, r9d
0x180009261  mov     [rbx+10h], eax
0x180009264  jmp     loc_1800091B1
```
