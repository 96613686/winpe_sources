# wil_details_GetCurrentFeatureEnabledState

- ea: `0x180014bfc`
- end: `0x180014e41`
- name: `wil_details_GetCurrentFeatureEnabledState`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180014a90`

## callees

- `0x180014a90`
- `0x180014bfc`
- `0x1800191f0`
- `0x18001a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180014c8e`
- `KERNEL32!GetProcAddress` at `0x180014c8e`
- `KERNEL32!GetModuleHandleW` at `0x180014c77`
- `KERNEL32!GetModuleHandleW` at `0x180014c77`

## string_xrefs

- `0x180014c70`: `ntdll.dll`
- `0x180014c84`: `RtlQueryFeatureConfiguration`

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
  __int64 v24; // [rsp+30h] [rbp-40h] BYREF
  __int128 v25; // [rsp+38h] [rbp-38h]
  __int64 v26; // [rsp+48h] [rbp-28h]
  __int64 v27; // [rsp+50h] [rbp-20h] BYREF
  int v28; // [rsp+58h] [rbp-18h]

  v2 = *(_DWORD *)(a1 + 24);
  v3 = *(_BYTE *)(a1 + 28) - 2;
  v25 = 0;
  v5 = 1;
  *a2 = 1;
  v6 = v3 > 1u;
  v26 = 0;
  v24 = 0;
  v27 = 0;
  v28 = 0;
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
  v14 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(v2, v6, &v24, &v27);
  if ( v14 )
  {
    v9 = 0;
    if ( v14 == 279 )
    {
      v9 = 1;
      v10 = v26;
      if ( (v27 & 0x8000000000LL) != 0 )
        v10 = 1;
      goto LABEL_7;
    }
LABEL_6:
    v10 = v26;
LABEL_7:
    v11 = v25;
    goto LABEL_8;
  }
  v9 = 1;
  HIDWORD(v26) = (BYTE4(v27) >> 6) & 1;
  v11 = (HIDWORD(v27) >> 4) & 3;
  v10 = BYTE4(v27) >> 7;
LABEL_8:
  v24 = 0;
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
      | (HIDWORD(v26) != 0 ? 0x800 : 0)
      | (((unsigned __int8)v11 & (unsigned __int8)-(v12 != 0) & 3) << 7);
  if ( (v13 & 0xC00
      | (v10 != 0 ? 0x400 : 0)
      | (HIDWORD(v26) != 0 ? 0x800 : 0)
      | (((unsigned __int8)v11 & (unsigned __int8)-(v12 != 0) & 3) << 7) & 0xC00) == 0xC00 )
  {
    v16 = 1;
  }
  else
  {
    v16 = 0;
    if ( (v13 & 0x40) == 0 )
    {
LABEL_38:
      v5 = 0;
      goto LABEL_39;
    }
  }
  v17 = *(__int64 **)(a1 + 32);
  v18 = v13
      | (v10 != 0 ? 0x400 : 0)
      | (HIDWORD(v26) != 0 ? 0x800 : 0)
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
        v27 = 0;
        LODWORD(v27) = *v21;
        if ( (v27 & 2) != 0 )
          v22 = v27;
        else
          v22 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(v21, v27, v20);
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
    goto LABEL_38;
LABEL_39:
  LODWORD(v24) = v5 | v15 & 0xFFFFFFFE;
  return v24;
}

```

## disassembly

```asm
0x180014bfc  mov     [rsp-28h+arg_10], rbx
0x180014c01  mov     [rsp-28h+arg_18], rsi
0x180014c06  push    rbp
0x180014c07  push    rdi
0x180014c08  push    r12
0x180014c0a  push    r14
0x180014c0c  push    r15
0x180014c0e  mov     rbp, rsp
0x180014c11  sub     rsp, 70h
0x180014c15  mov     rax, cs:__security_cookie
0x180014c1c  xor     rax, rsp
0x180014c1f  mov     [rbp+var_10], rax
0x180014c23  mov     al, [rcx+1Ch]
0x180014c26  xor     ebx, ebx
0x180014c28  mov     r14d, [rcx+18h]
0x180014c2c  sub     al, 2
0x180014c2e  xorps   xmm0, xmm0
0x180014c31  mov     rsi, rcx
0x180014c34  movups  [rbp+var_38], xmm0
0x180014c38  lea     edi, [rbx+1]
0x180014c3b  cmp     al, dil
0x180014c3e  mov     [rdx], edi
0x180014c40  setnbe  bl
0x180014c43  xor     eax, eax
0x180014c45  mov     [rbp+var_28], rax
0x180014c49  mov     [rbp+var_40], rax
0x180014c4d  mov     [rbp+var_20], rax
0x180014c51  mov     [rbp+var_18], eax
0x180014c54  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180014c5b  test    rax, rax
0x180014c5e  jnz     loc_180014CF3
0x180014c64  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180014c6b  test    rax, rax
0x180014c6e  jnz     short loc_180014C84
0x180014c70  lea     rcx, LibFileName; "ntdll.dll"
0x180014c77  call    cs:__imp_GetModuleHandleW
0x180014c7d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180014c84  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180014c8b  mov     rcx, rax; hModule
0x180014c8e  call    cs:__imp_GetProcAddress
0x180014c94  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180014c9b  test    rax, rax
0x180014c9e  jnz     short loc_180014CF3
0x180014ca0  xor     r9d, r9d
0x180014ca3  mov     eax, dword ptr [rbp+var_28]
0x180014ca6  mov     r8d, dword ptr [rbp+var_38]
0x180014caa  neg     eax
0x180014cac  mov     [rbp+var_40], 0
0x180014cb4  mov     eax, dword ptr [rbp+var_28+4]
0x180014cb7  mov     r14d, 40h ; '@'
0x180014cbd  sbb     ecx, ecx
0x180014cbf  and     ecx, 400h
0x180014cc5  neg     eax
0x180014cc7  sbb     edx, edx
0x180014cc9  and     edx, 800h
0x180014ccf  or      edx, ecx
0x180014cd1  neg     r9d
0x180014cd4  sbb     eax, eax
0x180014cd6  and     eax, r8d
0x180014cd9  and     eax, 3
0x180014cdc  mov     ecx, eax
0x180014cde  shl     ecx, 7
0x180014ce1  or      ecx, edx
0x180014ce3  test    eax, eax
0x180014ce5  jnz     short loc_180014D50
0x180014ce7  mov     al, [rsi+1Fh]
0x180014cea  neg     al
0x180014cec  sbb     edx, edx
0x180014cee  and     edx, r14d
0x180014cf1  jmp     short loc_180014D5A
0x180014cf3  lea     r9, [rbp+var_20]
0x180014cf7  mov     edx, ebx
0x180014cf9  lea     r8, [rbp+var_40]
0x180014cfd  mov     ecx, r14d
0x180014d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d05  test    eax, eax
0x180014d07  jnz     short loc_180014D30
0x180014d09  mov     ecx, dword ptr [rbp+var_20+4]
0x180014d0c  mov     r9d, edi
0x180014d0f  movzx   eax, cl
0x180014d12  mov     r8d, ecx
0x180014d15  shr     eax, 6
0x180014d18  and     eax, edi
0x180014d1a  shr     r8d, 4
0x180014d1e  mov     dword ptr [rbp+var_28+4], eax
0x180014d21  and     r8d, 3
0x180014d25  movzx   eax, cl
0x180014d28  shr     eax, 7
0x180014d2b  jmp     loc_180014CAA
0x180014d30  xor     r9d, r9d
0x180014d33  cmp     eax, 117h
0x180014d38  jnz     loc_180014CA3
0x180014d3e  test    byte ptr [rbp+var_20+4], 80h
0x180014d42  mov     r9d, edi
0x180014d45  mov     eax, dword ptr [rbp+var_28]
0x180014d48  cmovnz  eax, edi
0x180014d4b  jmp     loc_180014CA6
0x180014d50  xor     edx, edx
0x180014d52  cmp     r8d, 2
0x180014d56  cmovz   edx, r14d
0x180014d5a  or      ecx, edx
0x180014d5c  mov     edx, 0C00h
0x180014d61  mov     eax, ecx
0x180014d63  and     eax, edx
0x180014d65  cmp     eax, edx
0x180014d67  jnz     short loc_180014D6E
0x180014d69  mov     r12d, edi
0x180014d6c  jmp     short loc_180014D7C
0x180014d6e  xor     r12d, r12d
0x180014d71  xor     ebx, ebx
0x180014d73  test    r14b, cl
0x180014d76  jz      loc_180014E0E
0x180014d7c  mov     rsi, [rsi+20h]
0x180014d80  mov     r15d, ecx
0x180014d83  mov     ebx, edi
0x180014d85  test    rsi, rsi
0x180014d88  jz      short loc_180014DF5
0x180014d8a  mov     rcx, [rsi]
0x180014d8d  test    rcx, rcx
0x180014d90  jz      short loc_180014DF5
0x180014d92  cmp     byte ptr [rcx+1Eh], 0
0x180014d96  jnz     short loc_180014DE1
0x180014d98  cmp     byte ptr [rcx+1Dh], 0
0x180014d9c  jnz     short loc_180014DE1
0x180014d9e  mov     r9, [rcx]
0x180014da1  mov     [rbp+var_20], 0
0x180014da9  mov     eax, [r9]
0x180014dac  mov     dword ptr [rbp+var_20], eax
0x180014daf  test    al, 2
0x180014db1  jz      short loc_180014DB9
0x180014db3  mov     rax, [rbp+var_20]
0x180014db7  jmp     short loc_180014DC8
0x180014db9  mov     rdx, [rbp+var_20]
0x180014dbd  mov     r8, rcx
0x180014dc0  mov     rcx, r9
0x180014dc3  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x180014dc8  test    ebx, ebx
0x180014dca  jz      short loc_180014DD5
0x180014dcc  test    dil, al
0x180014dcf  jz      short loc_180014DD5
0x180014dd1  mov     ebx, edi
0x180014dd3  jmp     short loc_180014DD7
0x180014dd5  xor     ebx, ebx
0x180014dd7  add     rsi, 8
0x180014ddb  test    ebx, ebx
0x180014ddd  jnz     short loc_180014D8A
0x180014ddf  jmp     short loc_180014DF5
0x180014de1  test    ebx, ebx
0x180014de3  jz      short loc_180014DF3
0x180014de5  cmp     byte ptr [rcx+1Fh], 0
0x180014de9  jz      short loc_180014DF3
0x180014deb  mov     ebx, edi
0x180014ded  add     rsi, 8
0x180014df1  jmp     short loc_180014D8A
0x180014df3  xor     ebx, ebx
0x180014df5  mov     ecx, r15d
0x180014df8  test    r12d, r12d
0x180014dfb  jz      short loc_180014E05
0x180014dfd  test    ebx, ebx
0x180014dff  jnz     short loc_180014E05
0x180014e01  btr     ecx, 0Ah
0x180014e05  test    r14b, cl
0x180014e08  jz      short loc_180014E0E
0x180014e0a  test    ebx, ebx
0x180014e0c  jnz     short loc_180014E10
0x180014e0e  xor     edi, edi
0x180014e10  and     ecx, 0FFFFFFFEh
0x180014e13  or      ecx, edi
0x180014e15  mov     dword ptr [rbp+var_40], ecx
0x180014e18  mov     rax, [rbp+var_40]
0x180014e1c  mov     rcx, [rbp+var_10]
0x180014e20  xor     rcx, rsp; StackCookie
0x180014e23  call    __security_check_cookie
0x180014e28  lea     r11, [rsp+70h+var_s0]
0x180014e2d  mov     rbx, [r11+40h]
0x180014e31  mov     rsi, [r11+48h]
0x180014e35  mov     rsp, r11
0x180014e38  pop     r15
0x180014e3a  pop     r14
0x180014e3c  pop     r12
0x180014e3e  pop     rdi
0x180014e3f  pop     rbp
0x180014e40  retn
```
