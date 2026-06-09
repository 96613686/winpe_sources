# wil_details_GetCurrentFeatureEnabledState

- ea: `0x1800161a4`
- end: `0x1800163e9`
- name: `wil_details_GetCurrentFeatureEnabledState`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180016048`

## callees

- `0x180016048`
- `0x1800161a4`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001621f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001621f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016236`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016236`

## string_xrefs

- `0x180016218`: `ntdll.dll`
- `0x18001622c`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_details_GetCurrentFeatureEnabledState(__int64 a1, _DWORD *a2)
{
  unsigned int v2; // r14d
  unsigned __int8 v3; // al
  int v5; // edi
  BOOL v6; // ebx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v9; // r9d
  int v10; // eax
  int v11; // r8d
  int v12; // r9d
  int v13; // edx
  int v14; // eax
  unsigned int v15; // ecx
  int v16; // r12d
  __int64 *v17; // rsi
  int v18; // r15d
  BOOL v19; // ebx
  __int64 v20; // rcx
  _DWORD *v21; // r9
  char v22; // al
  int v24; // [rsp+44h] [rbp-2Ch]
  __int64 v25; // [rsp+48h] [rbp-28h] BYREF
  int v26; // [rsp+50h] [rbp-20h]
  __int64 v27; // [rsp+58h] [rbp-18h] BYREF

  v2 = *(_DWORD *)(a1 + 24);
  v3 = *(_BYTE *)(a1 + 28) - 2;
  v5 = 1;
  *a2 = 1;
  v6 = v3 > 1u;
  v24 = 0;
  v27 = 0;
  v25 = 0;
  v26 = 0;
  ProcAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      v9 = 0;
      goto LABEL_6;
    }
  }
  v14 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(v2, v6, &v27, &v25);
  if ( v14 )
  {
    v9 = 0;
    if ( v14 == 279 )
    {
      v9 = 1;
      v10 = (v25 & 0x8000000000LL) != 0;
      goto LABEL_7;
    }
LABEL_6:
    v10 = 0;
LABEL_7:
    v11 = 0;
    goto LABEL_8;
  }
  v9 = 1;
  v24 = (BYTE4(v25) >> 6) & 1;
  v11 = (HIDWORD(v25) >> 4) & 3;
  v10 = BYTE4(v25) >> 7;
LABEL_8:
  v27 = 0;
  v12 = -v9;
  if ( ((unsigned __int8)v11 & (unsigned __int8)-(v12 != 0) & 3) != 0 )
  {
    v13 = 0;
    if ( v11 == 2 )
      v13 = 64;
  }
  else
  {
    v13 = *(_BYTE *)(a1 + 31) != 0 ? 0x40 : 0;
  }
  v15 = v13
      | (v10 != 0 ? 0x400 : 0)
      | (v24 != 0 ? 0x800 : 0)
      | (((unsigned __int8)v11 & (unsigned __int8)-(v12 != 0) & 3) << 7);
  if ( (v13 & 0xC00
      | (v10 != 0 ? 0x400 : 0)
      | (v24 != 0 ? 0x800 : 0)
      | (((unsigned __int8)v11 & (unsigned __int8)-(v12 != 0) & 3) << 7) & 0xC00) == 0xC00 )
  {
    v16 = 1;
  }
  else
  {
    v16 = 0;
    if ( (v13 & 0x40) == 0 )
    {
LABEL_36:
      v5 = 0;
      goto LABEL_37;
    }
  }
  v17 = *(__int64 **)(a1 + 32);
  v18 = v13
      | (v10 != 0 ? 0x400 : 0)
      | (v24 != 0 ? 0x800 : 0)
      | (((unsigned __int8)v11 & (unsigned __int8)-(v12 != 0) & 3) << 7);
  v19 = 1;
  if ( v17 )
  {
    while ( 1 )
    {
      v20 = *v17;
      if ( !*v17 )
        break;
      if ( *(_BYTE *)(v20 + 30) || *(_BYTE *)(v20 + 29) )
      {
        if ( !*(_BYTE *)(v20 + 31) )
        {
          v19 = 0;
          break;
        }
        v19 = 1;
        ++v17;
      }
      else
      {
        v21 = *(_DWORD **)v20;
        v25 = 0;
        LODWORD(v25) = *v21;
        if ( (v25 & 2) != 0 )
          v22 = v25;
        else
          v22 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(v21, v25, v20);
        v19 = (v22 & 1) != 0;
        ++v17;
        if ( (v22 & 1) == 0 )
          break;
      }
    }
  }
  v15 = v18;
  if ( v16 && !v19 )
    v15 = v18 & 0xFFFFFBFF;
  if ( (v15 & 0x40) == 0 || !v19 )
    goto LABEL_36;
LABEL_37:
  LODWORD(v27) = v5 | v15 & 0xFFFFFFFE;
  return v27;
}

```

## disassembly

```asm
0x1800161a4  mov     [rsp-28h+arg_10], rbx
0x1800161a9  mov     [rsp-28h+arg_18], rsi
0x1800161ae  push    rbp
0x1800161af  push    rdi
0x1800161b0  push    r12
0x1800161b2  push    r14
0x1800161b4  push    r15
0x1800161b6  mov     rbp, rsp
0x1800161b9  sub     rsp, 70h
0x1800161bd  mov     rax, cs:__security_cookie
0x1800161c4  xor     rax, rsp
0x1800161c7  mov     [rbp+var_10], rax
0x1800161cb  mov     al, [rcx+1Ch]
0x1800161ce  xor     ebx, ebx
0x1800161d0  mov     r14d, [rcx+18h]
0x1800161d4  sub     al, 2
0x1800161d6  xorps   xmm0, xmm0
0x1800161d9  mov     rsi, rcx
0x1800161dc  movups  [rbp+var_40], xmm0
0x1800161e0  lea     edi, [rbx+1]
0x1800161e3  cmp     al, dil
0x1800161e6  mov     [rdx], edi
0x1800161e8  setnbe  bl
0x1800161eb  xor     eax, eax
0x1800161ed  mov     [rbp+var_30], rax
0x1800161f1  mov     [rbp+var_18], rax
0x1800161f5  mov     [rbp+var_28], rax
0x1800161f9  mov     [rbp+var_20], eax
0x1800161fc  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180016203  test    rax, rax
0x180016206  jnz     loc_18001629B
0x18001620c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180016213  test    rax, rax
0x180016216  jnz     short loc_18001622C
0x180016218  lea     rcx, ModuleName; "ntdll.dll"
0x18001621f  call    cs:__imp_GetModuleHandleW
0x180016225  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18001622c  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180016233  mov     rcx, rax; hModule
0x180016236  call    cs:__imp_GetProcAddress
0x18001623c  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180016243  test    rax, rax
0x180016246  jnz     short loc_18001629B
0x180016248  xor     r9d, r9d
0x18001624b  mov     eax, dword ptr [rbp+var_30]
0x18001624e  mov     r8d, dword ptr [rbp+var_40]
0x180016252  neg     eax
0x180016254  mov     [rbp+var_18], 0
0x18001625c  mov     eax, dword ptr [rbp+var_30+4]
0x18001625f  mov     r14d, 40h ; '@'
0x180016265  sbb     ecx, ecx
0x180016267  and     ecx, 400h
0x18001626d  neg     eax
0x18001626f  sbb     edx, edx
0x180016271  and     edx, 800h
0x180016277  or      edx, ecx
0x180016279  neg     r9d
0x18001627c  sbb     eax, eax
0x18001627e  and     eax, r8d
0x180016281  and     eax, 3
0x180016284  mov     ecx, eax
0x180016286  shl     ecx, 7
0x180016289  or      ecx, edx
0x18001628b  test    eax, eax
0x18001628d  jnz     short loc_1800162F8
0x18001628f  mov     al, [rsi+1Fh]
0x180016292  neg     al
0x180016294  sbb     edx, edx
0x180016296  and     edx, r14d
0x180016299  jmp     short loc_180016302
0x18001629b  lea     r9, [rbp+var_28]
0x18001629f  mov     edx, ebx
0x1800162a1  lea     r8, [rbp+var_18]
0x1800162a5  mov     ecx, r14d
0x1800162a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162ad  test    eax, eax
0x1800162af  jnz     short loc_1800162D8
0x1800162b1  mov     ecx, dword ptr [rbp+var_28+4]
0x1800162b4  mov     r9d, edi
0x1800162b7  movzx   eax, cl
0x1800162ba  mov     r8d, ecx
0x1800162bd  shr     eax, 6
0x1800162c0  and     eax, edi
0x1800162c2  shr     r8d, 4
0x1800162c6  mov     dword ptr [rbp+var_30+4], eax
0x1800162c9  and     r8d, 3
0x1800162cd  movzx   eax, cl
0x1800162d0  shr     eax, 7
0x1800162d3  jmp     loc_180016252
0x1800162d8  xor     r9d, r9d
0x1800162db  cmp     eax, 117h
0x1800162e0  jnz     loc_18001624B
0x1800162e6  test    byte ptr [rbp+var_28+4], 80h
0x1800162ea  mov     r9d, edi
0x1800162ed  mov     eax, dword ptr [rbp+var_30]
0x1800162f0  cmovnz  eax, edi
0x1800162f3  jmp     loc_18001624E
0x1800162f8  xor     edx, edx
0x1800162fa  cmp     r8d, 2
0x1800162fe  cmovz   edx, r14d
0x180016302  or      ecx, edx
0x180016304  mov     edx, 0C00h
0x180016309  mov     eax, ecx
0x18001630b  and     eax, edx
0x18001630d  cmp     eax, edx
0x18001630f  jnz     short loc_180016316
0x180016311  mov     r12d, edi
0x180016314  jmp     short loc_180016324
0x180016316  xor     r12d, r12d
0x180016319  xor     ebx, ebx
0x18001631b  test    r14b, cl
0x18001631e  jz      loc_1800163B6
0x180016324  mov     rsi, [rsi+20h]
0x180016328  mov     r15d, ecx
0x18001632b  mov     ebx, edi
0x18001632d  test    rsi, rsi
0x180016330  jz      short loc_18001639D
0x180016332  mov     rcx, [rsi]
0x180016335  test    rcx, rcx
0x180016338  jz      short loc_18001639D
0x18001633a  cmp     byte ptr [rcx+1Eh], 0
0x18001633e  jnz     short loc_180016389
0x180016340  cmp     byte ptr [rcx+1Dh], 0
0x180016344  jnz     short loc_180016389
0x180016346  mov     r9, [rcx]
0x180016349  mov     [rbp+var_28], 0
0x180016351  mov     eax, [r9]
0x180016354  mov     dword ptr [rbp+var_28], eax
0x180016357  test    al, 2
0x180016359  jz      short loc_180016361
0x18001635b  mov     rax, [rbp+var_28]
0x18001635f  jmp     short loc_180016370
0x180016361  mov     rdx, [rbp+var_28]
0x180016365  mov     r8, rcx
0x180016368  mov     rcx, r9
0x18001636b  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x180016370  test    ebx, ebx
0x180016372  jz      short loc_18001637D
0x180016374  test    dil, al
0x180016377  jz      short loc_18001637D
0x180016379  mov     ebx, edi
0x18001637b  jmp     short loc_18001637F
0x18001637d  xor     ebx, ebx
0x18001637f  add     rsi, 8
0x180016383  test    ebx, ebx
0x180016385  jnz     short loc_180016332
0x180016387  jmp     short loc_18001639D
0x180016389  test    ebx, ebx
0x18001638b  jz      short loc_18001639B
0x18001638d  cmp     byte ptr [rcx+1Fh], 0
0x180016391  jz      short loc_18001639B
0x180016393  mov     ebx, edi
0x180016395  add     rsi, 8
0x180016399  jmp     short loc_180016332
0x18001639b  xor     ebx, ebx
0x18001639d  mov     ecx, r15d
0x1800163a0  test    r12d, r12d
0x1800163a3  jz      short loc_1800163AD
0x1800163a5  test    ebx, ebx
0x1800163a7  jnz     short loc_1800163AD
0x1800163a9  btr     ecx, 0Ah
0x1800163ad  test    r14b, cl
0x1800163b0  jz      short loc_1800163B6
0x1800163b2  test    ebx, ebx
0x1800163b4  jnz     short loc_1800163B8
0x1800163b6  xor     edi, edi
0x1800163b8  and     ecx, 0FFFFFFFEh
0x1800163bb  or      ecx, edi
0x1800163bd  mov     dword ptr [rbp+var_18], ecx
0x1800163c0  mov     rax, [rbp+var_18]
0x1800163c4  mov     rcx, [rbp+var_10]
0x1800163c8  xor     rcx, rsp; StackCookie
0x1800163cb  call    __security_check_cookie
0x1800163d0  lea     r11, [rsp+70h+var_s0]
0x1800163d5  mov     rbx, [r11+40h]
0x1800163d9  mov     rsi, [r11+48h]
0x1800163dd  mov     rsp, r11
0x1800163e0  pop     r15
0x1800163e2  pop     r14
0x1800163e4  pop     r12
0x1800163e6  pop     rdi
0x1800163e7  pop     rbp
0x1800163e8  retn
```
