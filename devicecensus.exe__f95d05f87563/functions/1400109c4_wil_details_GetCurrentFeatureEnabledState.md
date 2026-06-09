# wil_details_GetCurrentFeatureEnabledState

- ea: `0x1400109c4`
- end: `0x140010c08`
- name: `wil_details_GetCurrentFeatureEnabledState`
- size: `580`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140010858`

## callees

- `0x1400023ba`
- `0x140010858`
- `0x1400109c4`
- `0x1400115f0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010a55`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010a55`

## string_xrefs

- `0x140010a38`: `ntdll.dll`
- `0x140010a4b`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_details_GetCurrentFeatureEnabledState(__int64 a1, _DWORD *a2)
{
  unsigned int v2; // r14d
  unsigned __int8 v3; // al
  int v5; // edi
  BOOL v6; // ebx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW_0; // rax
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
    ModuleHandleW_0 = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW_0 = GetModuleHandleW_0(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW_0;
    }
    ProcAddress = GetProcAddress(ModuleHandleW_0, "RtlQueryFeatureConfiguration");
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
0x1400109c4  mov     [rsp-28h+arg_10], rbx
0x1400109c9  mov     [rsp-28h+arg_18], rsi
0x1400109ce  push    rbp
0x1400109cf  push    rdi
0x1400109d0  push    r12
0x1400109d2  push    r14
0x1400109d4  push    r15
0x1400109d6  mov     rbp, rsp
0x1400109d9  sub     rsp, 70h
0x1400109dd  mov     rax, cs:__security_cookie
0x1400109e4  xor     rax, rsp
0x1400109e7  mov     [rbp+var_10], rax
0x1400109eb  mov     al, [rcx+1Ch]
0x1400109ee  xor     ebx, ebx
0x1400109f0  mov     r14d, [rcx+18h]
0x1400109f4  sub     al, 2
0x1400109f6  xorps   xmm0, xmm0
0x1400109f9  mov     rsi, rcx
0x1400109fc  movups  [rbp+var_38], xmm0
0x140010a00  lea     edi, [rbx+1]
0x140010a03  cmp     al, dil
0x140010a06  mov     [rdx], edi
0x140010a08  setnbe  bl
0x140010a0b  xor     eax, eax
0x140010a0d  mov     [rbp+var_28], rax
0x140010a11  mov     [rbp+var_40], rax
0x140010a15  mov     [rbp+var_20], rax
0x140010a19  mov     [rbp+var_18], eax
0x140010a1c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x140010a23  test    rax, rax
0x140010a26  jnz     loc_140010ABA
0x140010a2c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x140010a33  test    rax, rax
0x140010a36  jnz     short loc_140010A4B
0x140010a38  lea     rcx, LibFileName; "ntdll.dll"
0x140010a3f  call    GetModuleHandleW_0
0x140010a44  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x140010a4b  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x140010a52  mov     rcx, rax; hModule
0x140010a55  call    cs:__imp_GetProcAddress
0x140010a5b  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x140010a62  test    rax, rax
0x140010a65  jnz     short loc_140010ABA
0x140010a67  xor     r9d, r9d
0x140010a6a  mov     eax, dword ptr [rbp+var_28]
0x140010a6d  mov     r8d, dword ptr [rbp+var_38]
0x140010a71  neg     eax
0x140010a73  mov     [rbp+var_40], 0
0x140010a7b  mov     eax, dword ptr [rbp+var_28+4]
0x140010a7e  mov     r14d, 40h ; '@'
0x140010a84  sbb     ecx, ecx
0x140010a86  and     ecx, 400h
0x140010a8c  neg     eax
0x140010a8e  sbb     edx, edx
0x140010a90  and     edx, 800h
0x140010a96  or      edx, ecx
0x140010a98  neg     r9d
0x140010a9b  sbb     eax, eax
0x140010a9d  and     eax, r8d
0x140010aa0  and     eax, 3
0x140010aa3  mov     ecx, eax
0x140010aa5  shl     ecx, 7
0x140010aa8  or      ecx, edx
0x140010aaa  test    eax, eax
0x140010aac  jnz     short loc_140010B17
0x140010aae  mov     al, [rsi+1Fh]
0x140010ab1  neg     al
0x140010ab3  sbb     edx, edx
0x140010ab5  and     edx, r14d
0x140010ab8  jmp     short loc_140010B21
0x140010aba  lea     r9, [rbp+var_20]
0x140010abe  mov     edx, ebx
0x140010ac0  lea     r8, [rbp+var_40]
0x140010ac4  mov     ecx, r14d
0x140010ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010acc  test    eax, eax
0x140010ace  jnz     short loc_140010AF7
0x140010ad0  mov     ecx, dword ptr [rbp+var_20+4]
0x140010ad3  mov     r9d, edi
0x140010ad6  movzx   eax, cl
0x140010ad9  mov     r8d, ecx
0x140010adc  shr     eax, 6
0x140010adf  and     eax, edi
0x140010ae1  shr     r8d, 4
0x140010ae5  mov     dword ptr [rbp+var_28+4], eax
0x140010ae8  and     r8d, 3
0x140010aec  movzx   eax, cl
0x140010aef  shr     eax, 7
0x140010af2  jmp     loc_140010A71
0x140010af7  xor     r9d, r9d
0x140010afa  cmp     eax, 117h
0x140010aff  jnz     loc_140010A6A
0x140010b05  test    byte ptr [rbp+var_20+4], 80h
0x140010b09  mov     r9d, edi
0x140010b0c  mov     eax, dword ptr [rbp+var_28]
0x140010b0f  cmovnz  eax, edi
0x140010b12  jmp     loc_140010A6D
0x140010b17  xor     edx, edx
0x140010b19  cmp     r8d, 2
0x140010b1d  cmovz   edx, r14d
0x140010b21  or      ecx, edx
0x140010b23  mov     edx, 0C00h
0x140010b28  mov     eax, ecx
0x140010b2a  and     eax, edx
0x140010b2c  cmp     eax, edx
0x140010b2e  jnz     short loc_140010B35
0x140010b30  mov     r12d, edi
0x140010b33  jmp     short loc_140010B43
0x140010b35  xor     r12d, r12d
0x140010b38  xor     ebx, ebx
0x140010b3a  test    r14b, cl
0x140010b3d  jz      loc_140010BD5
0x140010b43  mov     rsi, [rsi+20h]
0x140010b47  mov     r15d, ecx
0x140010b4a  mov     ebx, edi
0x140010b4c  test    rsi, rsi
0x140010b4f  jz      short loc_140010BBC
0x140010b51  mov     rcx, [rsi]
0x140010b54  test    rcx, rcx
0x140010b57  jz      short loc_140010BBC
0x140010b59  cmp     byte ptr [rcx+1Eh], 0
0x140010b5d  jnz     short loc_140010BA8
0x140010b5f  cmp     byte ptr [rcx+1Dh], 0
0x140010b63  jnz     short loc_140010BA8
0x140010b65  mov     r9, [rcx]
0x140010b68  mov     [rbp+var_20], 0
0x140010b70  mov     eax, [r9]
0x140010b73  mov     dword ptr [rbp+var_20], eax
0x140010b76  test    al, 2
0x140010b78  jz      short loc_140010B80
0x140010b7a  mov     rax, [rbp+var_20]
0x140010b7e  jmp     short loc_140010B8F
0x140010b80  mov     rdx, [rbp+var_20]
0x140010b84  mov     r8, rcx
0x140010b87  mov     rcx, r9
0x140010b8a  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x140010b8f  test    ebx, ebx
0x140010b91  jz      short loc_140010B9C
0x140010b93  test    dil, al
0x140010b96  jz      short loc_140010B9C
0x140010b98  mov     ebx, edi
0x140010b9a  jmp     short loc_140010B9E
0x140010b9c  xor     ebx, ebx
0x140010b9e  add     rsi, 8
0x140010ba2  test    ebx, ebx
0x140010ba4  jnz     short loc_140010B51
0x140010ba6  jmp     short loc_140010BBC
0x140010ba8  test    ebx, ebx
0x140010baa  jz      short loc_140010BBA
0x140010bac  cmp     byte ptr [rcx+1Fh], 0
0x140010bb0  jz      short loc_140010BBA
0x140010bb2  mov     ebx, edi
0x140010bb4  add     rsi, 8
0x140010bb8  jmp     short loc_140010B51
0x140010bba  xor     ebx, ebx
0x140010bbc  mov     ecx, r15d
0x140010bbf  test    r12d, r12d
0x140010bc2  jz      short loc_140010BCC
0x140010bc4  test    ebx, ebx
0x140010bc6  jnz     short loc_140010BCC
0x140010bc8  btr     ecx, 0Ah
0x140010bcc  test    r14b, cl
0x140010bcf  jz      short loc_140010BD5
0x140010bd1  test    ebx, ebx
0x140010bd3  jnz     short loc_140010BD7
0x140010bd5  xor     edi, edi
0x140010bd7  and     ecx, 0FFFFFFFEh
0x140010bda  or      ecx, edi
0x140010bdc  mov     dword ptr [rbp+var_40], ecx
0x140010bdf  mov     rax, [rbp+var_40]
0x140010be3  mov     rcx, [rbp+var_10]
0x140010be7  xor     rcx, rsp; StackCookie
0x140010bea  call    __security_check_cookie
0x140010bef  lea     r11, [rsp+70h+var_s0]
0x140010bf4  mov     rbx, [r11+40h]
0x140010bf8  mov     rsi, [r11+48h]
0x140010bfc  mov     rsp, r11
0x140010bff  pop     r15
0x140010c01  pop     r14
0x140010c03  pop     r12
0x140010c05  pop     rdi
0x140010c06  pop     rbp
0x140010c07  retn
```
