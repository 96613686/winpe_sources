# wil_details_GetCurrentFeatureEnabledState

- ea: `0x180008a68`
- end: `0x180008cad`
- name: `wil_details_GetCurrentFeatureEnabledState`
- size: `581`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000890c`

## callees

- `0x180001ce0`
- `0x18000890c`
- `0x180008a68`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180008afa`
- `KERNEL32!GetProcAddress` at `0x180008afa`
- `KERNEL32!GetModuleHandleW` at `0x180008ae3`
- `KERNEL32!GetModuleHandleW` at `0x180008ae3`

## string_xrefs

- `0x180008adc`: `ntdll.dll`
- `0x180008af0`: `RtlQueryFeatureConfiguration`

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
  volatile signed __int32 *v21; // r9
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
        v21 = *(volatile signed __int32 **)v20;
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
0x180008a68  mov     [rsp-28h+arg_10], rbx
0x180008a6d  mov     [rsp-28h+arg_18], rsi
0x180008a72  push    rbp
0x180008a73  push    rdi
0x180008a74  push    r12
0x180008a76  push    r14
0x180008a78  push    r15
0x180008a7a  mov     rbp, rsp
0x180008a7d  sub     rsp, 70h
0x180008a81  mov     rax, cs:__security_cookie
0x180008a88  xor     rax, rsp
0x180008a8b  mov     [rbp+var_10], rax
0x180008a8f  mov     al, [rcx+1Ch]
0x180008a92  xor     ebx, ebx
0x180008a94  mov     r14d, [rcx+18h]
0x180008a98  sub     al, 2
0x180008a9a  xorps   xmm0, xmm0
0x180008a9d  mov     rsi, rcx
0x180008aa0  movups  [rbp+var_38], xmm0
0x180008aa4  lea     edi, [rbx+1]
0x180008aa7  cmp     al, dil
0x180008aaa  mov     [rdx], edi
0x180008aac  setnbe  bl
0x180008aaf  xor     eax, eax
0x180008ab1  mov     [rbp+var_28], rax
0x180008ab5  mov     [rbp+var_40], rax
0x180008ab9  mov     [rbp+var_20], rax
0x180008abd  mov     [rbp+var_18], eax
0x180008ac0  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180008ac7  test    rax, rax
0x180008aca  jnz     loc_180008B5F
0x180008ad0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180008ad7  test    rax, rax
0x180008ada  jnz     short loc_180008AF0
0x180008adc  lea     rcx, ModuleName; "ntdll.dll"
0x180008ae3  call    cs:__imp_GetModuleHandleW
0x180008ae9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180008af0  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180008af7  mov     rcx, rax; hModule
0x180008afa  call    cs:__imp_GetProcAddress
0x180008b00  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180008b07  test    rax, rax
0x180008b0a  jnz     short loc_180008B5F
0x180008b0c  xor     r9d, r9d
0x180008b0f  mov     eax, dword ptr [rbp+var_28]
0x180008b12  mov     r8d, dword ptr [rbp+var_38]
0x180008b16  neg     eax
0x180008b18  mov     [rbp+var_40], 0
0x180008b20  mov     eax, dword ptr [rbp+var_28+4]
0x180008b23  mov     r14d, 40h ; '@'
0x180008b29  sbb     ecx, ecx
0x180008b2b  and     ecx, 400h
0x180008b31  neg     eax
0x180008b33  sbb     edx, edx
0x180008b35  and     edx, 800h
0x180008b3b  or      edx, ecx
0x180008b3d  neg     r9d
0x180008b40  sbb     eax, eax
0x180008b42  and     eax, r8d
0x180008b45  and     eax, 3
0x180008b48  mov     ecx, eax
0x180008b4a  shl     ecx, 7
0x180008b4d  or      ecx, edx
0x180008b4f  test    eax, eax
0x180008b51  jnz     short loc_180008BBC
0x180008b53  mov     al, [rsi+1Fh]
0x180008b56  neg     al
0x180008b58  sbb     edx, edx
0x180008b5a  and     edx, r14d
0x180008b5d  jmp     short loc_180008BC6
0x180008b5f  lea     r9, [rbp+var_20]
0x180008b63  mov     edx, ebx
0x180008b65  lea     r8, [rbp+var_40]
0x180008b69  mov     ecx, r14d
0x180008b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b71  test    eax, eax
0x180008b73  jnz     short loc_180008B9C
0x180008b75  mov     ecx, dword ptr [rbp+var_20+4]
0x180008b78  mov     r9d, edi
0x180008b7b  movzx   eax, cl
0x180008b7e  mov     r8d, ecx
0x180008b81  shr     eax, 6
0x180008b84  and     eax, edi
0x180008b86  shr     r8d, 4
0x180008b8a  mov     dword ptr [rbp+var_28+4], eax
0x180008b8d  and     r8d, 3
0x180008b91  movzx   eax, cl
0x180008b94  shr     eax, 7
0x180008b97  jmp     loc_180008B16
0x180008b9c  xor     r9d, r9d
0x180008b9f  cmp     eax, 117h
0x180008ba4  jnz     loc_180008B0F
0x180008baa  test    byte ptr [rbp+var_20+4], 80h
0x180008bae  mov     r9d, edi
0x180008bb1  mov     eax, dword ptr [rbp+var_28]
0x180008bb4  cmovnz  eax, edi
0x180008bb7  jmp     loc_180008B12
0x180008bbc  xor     edx, edx
0x180008bbe  cmp     r8d, 2
0x180008bc2  cmovz   edx, r14d
0x180008bc6  or      ecx, edx
0x180008bc8  mov     edx, 0C00h
0x180008bcd  mov     eax, ecx
0x180008bcf  and     eax, edx
0x180008bd1  cmp     eax, edx
0x180008bd3  jnz     short loc_180008BDA
0x180008bd5  mov     r12d, edi
0x180008bd8  jmp     short loc_180008BE8
0x180008bda  xor     r12d, r12d
0x180008bdd  xor     ebx, ebx
0x180008bdf  test    r14b, cl
0x180008be2  jz      loc_180008C7A
0x180008be8  mov     rsi, [rsi+20h]
0x180008bec  mov     r15d, ecx
0x180008bef  mov     ebx, edi
0x180008bf1  test    rsi, rsi
0x180008bf4  jz      short loc_180008C61
0x180008bf6  mov     rcx, [rsi]
0x180008bf9  test    rcx, rcx
0x180008bfc  jz      short loc_180008C61
0x180008bfe  cmp     byte ptr [rcx+1Eh], 0
0x180008c02  jnz     short loc_180008C4D
0x180008c04  cmp     byte ptr [rcx+1Dh], 0
0x180008c08  jnz     short loc_180008C4D
0x180008c0a  mov     r9, [rcx]
0x180008c0d  mov     [rbp+var_20], 0
0x180008c15  mov     eax, [r9]
0x180008c18  mov     dword ptr [rbp+var_20], eax
0x180008c1b  test    al, 2
0x180008c1d  jz      short loc_180008C25
0x180008c1f  mov     rax, [rbp+var_20]
0x180008c23  jmp     short loc_180008C34
0x180008c25  mov     rdx, [rbp+var_20]
0x180008c29  mov     r8, rcx
0x180008c2c  mov     rcx, r9
0x180008c2f  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x180008c34  test    ebx, ebx
0x180008c36  jz      short loc_180008C41
0x180008c38  test    dil, al
0x180008c3b  jz      short loc_180008C41
0x180008c3d  mov     ebx, edi
0x180008c3f  jmp     short loc_180008C43
0x180008c41  xor     ebx, ebx
0x180008c43  add     rsi, 8
0x180008c47  test    ebx, ebx
0x180008c49  jnz     short loc_180008BF6
0x180008c4b  jmp     short loc_180008C61
0x180008c4d  test    ebx, ebx
0x180008c4f  jz      short loc_180008C5F
0x180008c51  cmp     byte ptr [rcx+1Fh], 0
0x180008c55  jz      short loc_180008C5F
0x180008c57  mov     ebx, edi
0x180008c59  add     rsi, 8
0x180008c5d  jmp     short loc_180008BF6
0x180008c5f  xor     ebx, ebx
0x180008c61  mov     ecx, r15d
0x180008c64  test    r12d, r12d
0x180008c67  jz      short loc_180008C71
0x180008c69  test    ebx, ebx
0x180008c6b  jnz     short loc_180008C71
0x180008c6d  btr     ecx, 0Ah
0x180008c71  test    r14b, cl
0x180008c74  jz      short loc_180008C7A
0x180008c76  test    ebx, ebx
0x180008c78  jnz     short loc_180008C7C
0x180008c7a  xor     edi, edi
0x180008c7c  and     ecx, 0FFFFFFFEh
0x180008c7f  or      ecx, edi
0x180008c81  mov     dword ptr [rbp+var_40], ecx
0x180008c84  mov     rax, [rbp+var_40]
0x180008c88  mov     rcx, [rbp+var_10]
0x180008c8c  xor     rcx, rsp; StackCookie
0x180008c8f  call    __security_check_cookie
0x180008c94  lea     r11, [rsp+70h+var_s0]
0x180008c99  mov     rbx, [r11+40h]
0x180008c9d  mov     rsi, [r11+48h]
0x180008ca1  mov     rsp, r11
0x180008ca4  pop     r15
0x180008ca6  pop     r14
0x180008ca8  pop     r12
0x180008caa  pop     rdi
0x180008cab  pop     rbp
0x180008cac  retn
```
