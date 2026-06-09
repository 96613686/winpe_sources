# wil_details_GetCurrentFeatureEnabledState

- ea: `0x180002880`
- end: `0x180002ac8`
- name: `wil_details_GetCurrentFeatureEnabledState`
- size: `584`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180002760`

## callees

- `0x180002760`
- `0x180002880`
- `0x180003a90`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002917`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002917`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002900`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002900`

## string_xrefs

- `0x18000290d`: `RtlQueryFeatureConfiguration`
- `0x1800028f9`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_details_GetCurrentFeatureEnabledState(__int64 a1, _DWORD *a2)
{
  unsigned int v2; // ebp
  bool v3; // cf
  bool v4; // zf
  BOOL v5; // esi
  int v6; // edi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v10; // r9d
  int v11; // eax
  int v12; // edx
  int v13; // ecx
  int v14; // eax
  int v15; // eax
  unsigned int v16; // ecx
  int v17; // ebp
  __int64 *v18; // rbx
  unsigned int v19; // esi
  __int64 v20; // rcx
  int v21; // eax
  volatile signed __int32 *v22; // r9
  char v23; // al
  __int64 v25; // [rsp+30h] [rbp-58h] BYREF
  __int128 v26; // [rsp+38h] [rbp-50h]
  __int64 v27; // [rsp+48h] [rbp-40h]
  __int64 v28; // [rsp+50h] [rbp-38h] BYREF
  int v29; // [rsp+58h] [rbp-30h]

  v2 = *(_DWORD *)(a1 + 24);
  v3 = *(_BYTE *)(a1 + 28) == 2;
  v4 = *(_BYTE *)(a1 + 28) == 3;
  v25 = 0;
  v5 = !v3 && !v4;
  v6 = 1;
  *a2 = 1;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  ProcAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  v26 = 0;
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
      v10 = 0;
      goto LABEL_6;
    }
  }
  v15 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(v2, v5, &v25, &v28);
  if ( v15 )
  {
    v10 = 0;
    if ( v15 == 279 )
    {
      v10 = 1;
      v11 = v27;
      if ( (v28 & 0x8000000000LL) != 0 )
        v11 = 1;
      goto LABEL_7;
    }
LABEL_6:
    v11 = v27;
LABEL_7:
    v12 = v26;
    goto LABEL_8;
  }
  v10 = 1;
  HIDWORD(v27) = (BYTE4(v28) >> 6) & 1;
  v12 = (HIDWORD(v28) >> 4) & 3;
  v11 = BYTE4(v28) >> 7;
LABEL_8:
  v25 = 0;
  if ( !v10 )
  {
    v13 = (v11 != 0 ? 0x400 : 0) | (HIDWORD(v27) != 0 ? 0x800 : 0);
    goto LABEL_20;
  }
  v13 = (v11 != 0 ? 0x400 : 0) | (HIDWORD(v27) != 0 ? 0x800 : 0) | ((v12 & 3) << 7);
  if ( (v12 & 3) == 0 )
  {
LABEL_20:
    v14 = *(_BYTE *)(a1 + 31) != 0 ? 0x40 : 0;
    goto LABEL_21;
  }
  v14 = 0;
  if ( v12 == 2 )
    v14 = 64;
LABEL_21:
  v16 = v14 | v13;
  if ( (v16 & 0xC00) == 0xC00 )
  {
    v17 = 1;
  }
  else
  {
    v17 = 0;
    if ( (v16 & 0x40) == 0 )
    {
LABEL_42:
      v6 = 0;
      goto LABEL_43;
    }
  }
  v18 = *(__int64 **)(a1 + 32);
  v19 = v16;
  if ( v18 )
  {
    while ( 1 )
    {
      v20 = *v18;
      v21 = 1;
      if ( !*v18 )
        break;
      if ( *(_BYTE *)(v20 + 30) || *(_BYTE *)(v20 + 29) )
      {
        if ( !*(_BYTE *)(v20 + 31) )
          goto LABEL_35;
        ++v18;
      }
      else
      {
        v22 = *(volatile signed __int32 **)v20;
        v28 = 0;
        LODWORD(v28) = *v22;
        if ( (v28 & 2) != 0 )
          v23 = v28;
        else
          v23 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(v22, v28, v20);
        if ( (v23 & 1) == 0 )
        {
LABEL_35:
          v21 = 0;
          break;
        }
        ++v18;
      }
    }
  }
  else
  {
    v21 = 1;
  }
  v16 = v19;
  if ( v17 && !v21 )
    v16 = v19 & 0xFFFFFBFF;
  if ( (v16 & 0x40) == 0 || !v21 )
    goto LABEL_42;
LABEL_43:
  LODWORD(v25) = v6 | v16 & 0xFFFFFFFE;
  return v25;
}

```

## disassembly

```asm
0x180002880  mov     [rsp+arg_10], rbx
0x180002885  mov     [rsp+arg_18], rbp
0x18000288a  push    rsi
0x18000288b  push    rdi
0x18000288c  push    r14
0x18000288e  sub     rsp, 70h
0x180002892  mov     rax, cs:__security_cookie
0x180002899  xor     rax, rsp
0x18000289c  mov     [rsp+88h+var_28], rax
0x1800028a1  movzx   eax, byte ptr [rcx+1Ch]
0x1800028a5  xor     r14d, r14d
0x1800028a8  mov     ebp, [rcx+18h]
0x1800028ab  sub     al, 2
0x1800028ad  cmp     al, 1
0x1800028af  mov     [rsp+88h+var_58], r14
0x1800028b4  mov     esi, r14d
0x1800028b7  xorps   xmm0, xmm0
0x1800028ba  setnbe  sil
0x1800028be  mov     edi, 1
0x1800028c3  xor     eax, eax
0x1800028c5  mov     [rdx], edi
0x1800028c7  mov     [rsp+88h+var_40], rax
0x1800028cc  mov     rbx, rcx
0x1800028cf  mov     [rsp+88h+var_38], rax
0x1800028d4  mov     [rsp+88h+var_30], eax
0x1800028d8  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800028df  movups  [rsp+88h+var_50], xmm0
0x1800028e4  test    rax, rax
0x1800028e7  jnz     loc_180002982
0x1800028ed  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800028f4  test    rax, rax
0x1800028f7  jnz     short loc_18000290D
0x1800028f9  lea     rcx, ModuleName; "ntdll.dll"
0x180002900  call    cs:__imp_GetModuleHandleW
0x180002906  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000290d  lea     rdx, ProcName; "RtlQueryFeatureConfiguration"
0x180002914  mov     rcx, rax; hModule
0x180002917  call    cs:__imp_GetProcAddress
0x18000291d  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180002924  test    rax, rax
0x180002927  jnz     short loc_180002982
0x180002929  mov     r9d, r14d
0x18000292c  mov     eax, dword ptr [rsp+88h+var_40]
0x180002930  mov     edx, dword ptr [rsp+88h+var_50]
0x180002934  neg     eax
0x180002936  mov     [rsp+88h+var_58], r14
0x18000293b  mov     eax, dword ptr [rsp+88h+var_40+4]
0x18000293f  sbb     ecx, ecx
0x180002941  and     ecx, 400h
0x180002947  neg     eax
0x180002949  sbb     r8d, r8d
0x18000294c  and     r8d, 800h
0x180002953  or      r8d, ecx
0x180002956  test    r9d, r9d
0x180002959  jz      loc_1800029E1
0x18000295f  mov     eax, edx
0x180002961  and     eax, 3
0x180002964  mov     ecx, eax
0x180002966  shl     ecx, 7
0x180002969  or      ecx, r8d
0x18000296c  test    eax, eax
0x18000296e  jz      short loc_1800029E4
0x180002970  cmp     edx, 2
0x180002973  mov     eax, r14d
0x180002976  mov     r8d, 40h ; '@'
0x18000297c  cmovz   eax, r8d
0x180002980  jmp     short loc_1800029EF
0x180002982  lea     r9, [rsp+88h+var_38]
0x180002987  mov     edx, esi
0x180002989  lea     r8, [rsp+88h+var_58]
0x18000298e  mov     ecx, ebp
0x180002990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002995  test    eax, eax
0x180002997  jnz     short loc_1800029BF
0x180002999  mov     ecx, dword ptr [rsp+88h+var_38+4]
0x18000299d  mov     r9d, edi
0x1800029a0  movzx   eax, cl
0x1800029a3  mov     edx, ecx
0x1800029a5  shr     eax, 6
0x1800029a8  and     eax, edi
0x1800029aa  shr     edx, 4
0x1800029ad  mov     dword ptr [rsp+88h+var_40+4], eax
0x1800029b1  and     edx, 3
0x1800029b4  movzx   eax, cl
0x1800029b7  shr     eax, 7
0x1800029ba  jmp     loc_180002934
0x1800029bf  mov     r9d, r14d
0x1800029c2  cmp     eax, 117h
0x1800029c7  jnz     loc_18000292C
0x1800029cd  test    byte ptr [rsp+88h+var_38+4], 80h
0x1800029d2  mov     r9d, edi
0x1800029d5  mov     eax, dword ptr [rsp+88h+var_40]
0x1800029d9  cmovnz  eax, edi
0x1800029dc  jmp     loc_180002930
0x1800029e1  mov     ecx, r8d
0x1800029e4  movzx   eax, byte ptr [rbx+1Fh]
0x1800029e8  neg     al
0x1800029ea  sbb     eax, eax
0x1800029ec  and     eax, 40h
0x1800029ef  or      ecx, eax
0x1800029f1  mov     eax, ecx
0x1800029f3  and     eax, 0C00h
0x1800029f8  cmp     eax, 0C00h
0x1800029fd  jnz     short loc_180002A03
0x1800029ff  mov     ebp, edi
0x180002a01  jmp     short loc_180002A12
0x180002a03  mov     ebp, r14d
0x180002a06  mov     eax, r14d
0x180002a09  test    cl, 40h
0x180002a0c  jz      loc_180002A95
0x180002a12  mov     rbx, [rbx+20h]
0x180002a16  mov     esi, ecx
0x180002a18  test    rbx, rbx
0x180002a1b  jz      short loc_180002A7C
0x180002a1d  nop     dword ptr [rax]
0x180002a20  mov     rcx, [rbx]
0x180002a23  mov     eax, edi
0x180002a25  test    rcx, rcx
0x180002a28  jz      short loc_180002A7E
0x180002a2a  cmp     [rcx+1Eh], r14b
0x180002a2e  jnz     short loc_180002A6B
0x180002a30  cmp     [rcx+1Dh], r14b
0x180002a34  jnz     short loc_180002A6B
0x180002a36  mov     r9, [rcx]
0x180002a39  mov     [rsp+88h+var_38], r14
0x180002a3e  mov     eax, [r9]
0x180002a41  mov     dword ptr [rsp+88h+var_38], eax
0x180002a45  test    al, 2
0x180002a47  jz      short loc_180002A50
0x180002a49  mov     rax, [rsp+88h+var_38]
0x180002a4e  jmp     short loc_180002A60
0x180002a50  mov     rdx, [rsp+88h+var_38]
0x180002a55  mov     r8, rcx
0x180002a58  mov     rcx, r9
0x180002a5b  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x180002a60  test    dil, al
0x180002a63  jz      short loc_180002A77
0x180002a65  add     rbx, 8
0x180002a69  jmp     short loc_180002A20
0x180002a6b  cmp     [rcx+1Fh], r14b
0x180002a6f  jz      short loc_180002A77
0x180002a71  add     rbx, 8
0x180002a75  jmp     short loc_180002A20
0x180002a77  mov     eax, r14d
0x180002a7a  jmp     short loc_180002A7E
0x180002a7c  mov     eax, edi
0x180002a7e  mov     ecx, esi
0x180002a80  test    ebp, ebp
0x180002a82  jz      short loc_180002A8C
0x180002a84  test    eax, eax
0x180002a86  jnz     short loc_180002A8C
0x180002a88  btr     ecx, 0Ah
0x180002a8c  test    cl, 40h
0x180002a8f  jz      short loc_180002A95
0x180002a91  test    eax, eax
0x180002a93  jnz     short loc_180002A98
0x180002a95  mov     edi, r14d
0x180002a98  and     ecx, 0FFFFFFFEh
0x180002a9b  or      ecx, edi
0x180002a9d  mov     dword ptr [rsp+88h+var_58], ecx
0x180002aa1  mov     rax, [rsp+88h+var_58]
0x180002aa6  mov     rcx, [rsp+88h+var_28]
0x180002aab  xor     rcx, rsp; StackCookie
0x180002aae  call    __security_check_cookie
0x180002ab3  lea     r11, [rsp+88h+var_18]
0x180002ab8  mov     rbx, [r11+30h]
0x180002abc  mov     rbp, [r11+38h]
0x180002ac0  mov     rsp, r11
0x180002ac3  pop     r14
0x180002ac5  pop     rdi
0x180002ac6  pop     rsi
0x180002ac7  retn
```
