# wil_details_GetCurrentFeatureEnabledState

- ea: `0x180010a80`
- end: `0x180010cae`
- name: `wil_details_GetCurrentFeatureEnabledState`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180010924`

## callees

- `0x180001aa0`
- `0x180010924`
- `0x180010a80`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010b15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010b15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010af8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010af8`

## string_xrefs

- `0x180010af1`: `ntdll.dll`
- `0x180010b0b`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_details_GetCurrentFeatureEnabledState(__int64 a1, _DWORD *a2)
{
  unsigned int v2; // esi
  unsigned __int8 v3; // al
  BOOL v5; // ebx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v8; // r9d
  int v9; // eax
  int v10; // r8d
  int v11; // edx
  int v12; // eax
  int v13; // ecx
  int v14; // eax
  unsigned int v15; // r9d
  int v16; // ebx
  __int64 *v17; // rdi
  __int64 v18; // rcx
  _DWORD *v19; // r9
  unsigned __int8 v20; // al
  BOOL v21; // ecx
  unsigned int v22; // eax
  unsigned int v23; // ebx
  __int64 v25; // [rsp+30h] [rbp-40h] BYREF
  __int128 v26; // [rsp+38h] [rbp-38h]
  __int64 v27; // [rsp+48h] [rbp-28h]
  __int64 v28; // [rsp+50h] [rbp-20h] BYREF
  int v29; // [rsp+58h] [rbp-18h]

  v2 = *(_DWORD *)(a1 + 24);
  v3 = *(_BYTE *)(a1 + 28) - 2;
  v26 = 0;
  *a2 = 1;
  v5 = v3 > 1u;
  v27 = 0;
  v25 = 0;
  v28 = 0;
  v29 = 0;
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
      v8 = 0;
      goto LABEL_6;
    }
  }
  v14 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(v2, v5, &v25, &v28);
  if ( v14 )
  {
    v8 = 0;
    if ( v14 == 279 )
    {
      v8 = 1;
      v9 = v27;
      if ( (v28 & 0x8000000000LL) != 0 )
        v9 = 1;
      goto LABEL_7;
    }
LABEL_6:
    v9 = v27;
LABEL_7:
    v10 = v26;
    goto LABEL_8;
  }
  v8 = 1;
  HIDWORD(v27) = (BYTE4(v28) >> 6) & 1;
  v10 = (HIDWORD(v28) >> 4) & 3;
  v9 = BYTE4(v28) >> 7;
LABEL_8:
  v28 = 0;
  v11 = (v9 != 0 ? 0x400 : 0) | (HIDWORD(v27) != 0 ? 0x800 : 0);
  v12 = (unsigned __int8)v10 & (unsigned __int8)-(v8 != 0) & 3;
  if ( v12 )
  {
    v13 = 0;
    if ( v10 == 2 )
      v13 = 64;
  }
  else
  {
    v13 = *(_BYTE *)(a1 + 31) != 0 ? 0x40 : 0;
  }
  v15 = v13 | v11 | (v12 << 7);
  v16 = v15 | (v15 >> 6) & 1;
  LODWORD(v28) = v16;
  if ( ((v15 >> 6) & 1) != 0 )
  {
    v17 = *(__int64 **)(a1 + 32);
    if ( v17 )
    {
      for ( ; (v16 & 1) != 0; LODWORD(v28) = v16 )
      {
        v18 = *v17;
        if ( !*v17 )
          break;
        if ( *(_BYTE *)(v18 + 30) || *(_BYTE *)(v18 + 29) )
        {
          v22 = (v16 & 1) != 0 && *(_BYTE *)(v18 + 31);
          v23 = v16 & 0xFFFFFFFE;
        }
        else
        {
          v19 = *(_DWORD **)v18;
          v25 = 0;
          LODWORD(v25) = *v19;
          v20 = (v25 & 2) != 0 ? v25 : wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(v19, v25, v18);
          v21 = ((unsigned __int8)v16 & v20 & 1) != 0;
          v22 = v16 & 0xFFFFFFFE;
          v23 = v21;
        }
        v16 = v22 | v23;
        ++v17;
      }
    }
  }
  return v28;
}

```

## disassembly

```asm
0x180010a80  mov     [rsp-18h+arg_10], rbx
0x180010a85  mov     [rsp-18h+arg_18], rsi
0x180010a8a  push    rbp
0x180010a8b  push    rdi
0x180010a8c  push    r15
0x180010a8e  mov     rbp, rsp
0x180010a91  sub     rsp, 70h
0x180010a95  mov     rax, cs:__security_cookie
0x180010a9c  xor     rax, rsp
0x180010a9f  mov     [rbp+var_10], rax
0x180010aa3  mov     al, [rcx+1Ch]
0x180010aa6  xor     ebx, ebx
0x180010aa8  mov     esi, [rcx+18h]
0x180010aab  sub     al, 2
0x180010aad  xorps   xmm0, xmm0
0x180010ab0  mov     rdi, rcx
0x180010ab3  movups  [rbp+var_38], xmm0
0x180010ab7  lea     r15d, [rbx+1]
0x180010abb  cmp     al, r15b
0x180010abe  mov     [rdx], r15d
0x180010ac1  setnbe  bl
0x180010ac4  xor     eax, eax
0x180010ac6  mov     [rbp+var_28], rax
0x180010aca  mov     [rbp+var_40], rax
0x180010ace  mov     [rbp+var_20], rax
0x180010ad2  mov     [rbp+var_18], eax
0x180010ad5  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180010adc  test    rax, rax
0x180010adf  jnz     loc_180010B7D
0x180010ae5  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180010aec  test    rax, rax
0x180010aef  jnz     short loc_180010B0B
0x180010af1  lea     rcx, ModuleName; "ntdll.dll"
0x180010af8  call    cs:__imp_GetModuleHandleW
0x180010aff  nop     dword ptr [rax+rax+00h]
0x180010b04  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180010b0b  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180010b12  mov     rcx, rax; hModule
0x180010b15  call    cs:__imp_GetProcAddress
0x180010b1c  nop     dword ptr [rax+rax+00h]
0x180010b21  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180010b28  test    rax, rax
0x180010b2b  jnz     short loc_180010B7D
0x180010b2d  xor     r9d, r9d
0x180010b30  mov     eax, dword ptr [rbp+var_28]
0x180010b33  mov     r8d, dword ptr [rbp+var_38]
0x180010b37  neg     eax
0x180010b39  mov     [rbp+var_20], 0
0x180010b41  mov     eax, dword ptr [rbp+var_28+4]
0x180010b44  sbb     ecx, ecx
0x180010b46  and     ecx, 400h
0x180010b4c  neg     eax
0x180010b4e  sbb     edx, edx
0x180010b50  and     edx, 800h
0x180010b56  or      edx, ecx
0x180010b58  neg     r9d
0x180010b5b  sbb     eax, eax
0x180010b5d  and     eax, r8d
0x180010b60  and     eax, 3
0x180010b63  mov     r9d, eax
0x180010b66  shl     r9d, 7
0x180010b6a  or      r9d, edx
0x180010b6d  test    eax, eax
0x180010b6f  jnz     short loc_180010BD8
0x180010b71  mov     al, [rdi+1Fh]
0x180010b74  neg     al
0x180010b76  sbb     ecx, ecx
0x180010b78  and     ecx, 40h
0x180010b7b  jmp     short loc_180010BE4
0x180010b7d  lea     r9, [rbp+var_20]
0x180010b81  mov     edx, ebx
0x180010b83  lea     r8, [rbp+var_40]
0x180010b87  mov     ecx, esi
0x180010b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b8e  test    eax, eax
0x180010b90  jnz     short loc_180010BB7
0x180010b92  mov     ecx, dword ptr [rbp+var_20+4]
0x180010b95  mov     r9d, r15d
0x180010b98  movzx   eax, cl
0x180010b9b  mov     r8d, ecx
0x180010b9e  shr     eax, 6
0x180010ba1  and     eax, r15d
0x180010ba4  shr     r8d, 4
0x180010ba8  mov     dword ptr [rbp+var_28+4], eax
0x180010bab  and     r8d, 3
0x180010baf  movzx   eax, cl
0x180010bb2  shr     eax, 7
0x180010bb5  jmp     short loc_180010B37
0x180010bb7  xor     r9d, r9d
0x180010bba  cmp     eax, 117h
0x180010bbf  jnz     loc_180010B30
0x180010bc5  test    byte ptr [rbp+var_20+4], 80h
0x180010bc9  mov     r9d, r15d
0x180010bcc  mov     eax, dword ptr [rbp+var_28]
0x180010bcf  cmovnz  eax, r15d
0x180010bd3  jmp     loc_180010B33
0x180010bd8  xor     ecx, ecx
0x180010bda  cmp     r8d, 2
0x180010bde  lea     eax, [rcx+40h]
0x180010be1  cmovz   ecx, eax
0x180010be4  or      r9d, ecx
0x180010be7  mov     eax, r9d
0x180010bea  shr     eax, 6
0x180010bed  and     eax, r15d
0x180010bf0  mov     ebx, eax
0x180010bf2  or      ebx, r9d
0x180010bf5  mov     dword ptr [rbp+var_20], ebx
0x180010bf8  test    eax, eax
0x180010bfa  jz      loc_180010C88
0x180010c00  mov     rdi, [rdi+20h]
0x180010c04  test    rdi, rdi
0x180010c07  jz      short loc_180010C88
0x180010c09  test    r15b, bl
0x180010c0c  jz      short loc_180010C88
0x180010c0e  mov     esi, 0FFFFFFFEh
0x180010c13  mov     rcx, [rdi]
0x180010c16  test    rcx, rcx
0x180010c19  jz      short loc_180010C88
0x180010c1b  cmp     byte ptr [rcx+1Eh], 0
0x180010c1f  jnz     short loc_180010C66
0x180010c21  cmp     byte ptr [rcx+1Dh], 0
0x180010c25  jnz     short loc_180010C66
0x180010c27  mov     r9, [rcx]
0x180010c2a  mov     [rbp+var_40], 0
0x180010c32  mov     eax, [r9]
0x180010c35  mov     dword ptr [rbp+var_40], eax
0x180010c38  test    al, 2
0x180010c3a  jz      short loc_180010C42
0x180010c3c  mov     rax, [rbp+var_40]
0x180010c40  jmp     short loc_180010C51
0x180010c42  mov     rdx, [rbp+var_40]
0x180010c46  mov     r8, rcx
0x180010c49  mov     rcx, r9
0x180010c4c  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x180010c51  and     eax, ebx
0x180010c53  mov     ecx, 0
0x180010c58  test    r15b, al
0x180010c5b  mov     eax, ebx
0x180010c5d  setnz   cl
0x180010c60  and     eax, esi
0x180010c62  mov     ebx, ecx
0x180010c64  jmp     short loc_180010C7A
0x180010c66  test    r15b, bl
0x180010c69  jz      short loc_180010C76
0x180010c6b  cmp     byte ptr [rcx+1Fh], 0
0x180010c6f  jz      short loc_180010C76
0x180010c71  mov     eax, r15d
0x180010c74  jmp     short loc_180010C78
0x180010c76  xor     eax, eax
0x180010c78  and     ebx, esi
0x180010c7a  or      ebx, eax
0x180010c7c  add     rdi, 8
0x180010c80  mov     dword ptr [rbp+var_20], ebx
0x180010c83  test    r15b, bl
0x180010c86  jnz     short loc_180010C13
0x180010c88  mov     rax, [rbp+var_20]
0x180010c8c  mov     rcx, [rbp+var_10]
0x180010c90  xor     rcx, rsp; StackCookie
0x180010c93  call    __security_check_cookie
0x180010c98  lea     r11, [rsp+70h+var_s0]
0x180010c9d  mov     rbx, [r11+30h]
0x180010ca1  mov     rsi, [r11+38h]
0x180010ca5  mov     rsp, r11
0x180010ca8  pop     r15
0x180010caa  pop     rdi
0x180010cab  pop     rbp
0x180010cac  retn
```
