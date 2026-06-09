# wil_QueryFeatureState(x,x,x,x,x,x)

- ea: `0x1000a1b0`
- end: `0x1000a2dc`
- name: `_wil_QueryFeatureState@24`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1000cc40`

## callees

- `0x1000a1b0`
- `0x1000eb60`
- `0x1005e3b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000a223`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000a223`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000a212`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000a212`

## string_xrefs

- `0x1000a20d`: `ntdll.dll`
- `0x1000a21d`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
int __fastcall wil_QueryFeatureState(int a1, void *a2, int a3, int a4, _DWORD *a5, _DWORD *a6)
{
  int v7; // ebx
  FARPROC RtlQueryFeatureConfiguration; // eax
  HMODULE ModuleHandleW; // eax
  int v10; // edx
  int v11; // eax
  unsigned int v12; // ecx
  int result; // eax
  _BYTE v14[8]; // [esp+Ch] [ebp-24h] BYREF
  void *v15; // [esp+14h] [ebp-1Ch]
  unsigned int v16; // [esp+18h] [ebp-18h]
  int (__thiscall *v17)(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD); // [esp+1Ch] [ebp-14h]
  __int64 v18; // [esp+20h] [ebp-10h] BYREF
  int v19; // [esp+28h] [ebp-8h]

  v15 = a2;
  if ( a5 )
    *a5 = 0;
  *a6 = 1;
  v7 = 0;
  v19 = 0;
  v18 = 0;
  v16 = a3 == 0;
  RtlQueryFeatureConfiguration = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  v17 = (int (__thiscall *)(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    RtlQueryFeatureConfiguration = GetProcAddress(ModuleHandleW, "RtlQueryFeatureConfiguration");
    v17 = (int (__thiscall *)(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD))RtlQueryFeatureConfiguration;
    g_wil_details_pfnRtlQueryFeatureConfiguration = (int)RtlQueryFeatureConfiguration;
    if ( !RtlQueryFeatureConfiguration )
    {
      v10 = -1073741511;
      goto LABEL_13;
    }
  }
  v11 = v17(RtlQueryFeatureConfiguration, v15, v16, v14, &v18);
  v10 = v11;
  if ( v11 )
  {
    v10 = v11;
    if ( v11 != 279 )
      goto LABEL_13;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v18) >> 7) & 1;
  }
  else
  {
    v12 = HIDWORD(v18);
    *(_DWORD *)a1 = (HIDWORD(v18) >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v12) & 0x3F;
    *(_DWORD *)(a1 + 12) = v19;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v12 >> 14;
    *(_DWORD *)(a1 + 20) = (v12 >> 6) & 1;
    *(_DWORD *)(a1 + 16) = (v12 >> 7) & 1;
  }
  v7 = 1;
LABEL_13:
  result = v7;
  if ( a5 )
    *a5 = v10 != -2147483614;
  return result;
}

```

## disassembly

```asm
0x1000a1b0  mov     edi, edi
0x1000a1b2  push    ebp
0x1000a1b3  mov     ebp, esp
0x1000a1b5  sub     esp, 24h
0x1000a1b8  mov     eax, ___security_cookie
0x1000a1bd  xor     eax, ebp
0x1000a1bf  mov     [ebp+var_4], eax
0x1000a1c2  mov     eax, [ebp+arg_C]
0x1000a1c5  push    ebx
0x1000a1c6  push    esi
0x1000a1c7  push    edi
0x1000a1c8  mov     edi, [ebp+arg_8]
0x1000a1cb  mov     esi, ecx
0x1000a1cd  mov     [ebp+var_1C], edx
0x1000a1d0  test    edi, edi
0x1000a1d2  jz      short loc_1000A1DA
0x1000a1d4  mov     dword ptr [edi], 0
0x1000a1da  mov     dword ptr [eax], 1
0x1000a1e0  xor     ebx, ebx
0x1000a1e2  xor     eax, eax
0x1000a1e4  mov     [ebp+var_8], ebx
0x1000a1e7  cmp     [ebp+arg_0], eax
0x1000a1ea  xorps   xmm0, xmm0
0x1000a1ed  movq    [ebp+var_10], xmm0
0x1000a1f2  setz    al
0x1000a1f5  mov     [ebp+var_18], eax
0x1000a1f8  mov     eax, _g_wil_details_pfnRtlQueryFeatureConfiguration
0x1000a1fd  mov     [ebp+var_14], eax
0x1000a200  test    eax, eax
0x1000a202  jnz     short loc_1000A23C
0x1000a204  mov     eax, ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1000a209  test    eax, eax
0x1000a20b  jnz     short loc_1000A21D
0x1000a20d  push    offset ModuleName; "ntdll.dll"
0x1000a212  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x1000a218  mov     ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A, eax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1000a21d  push    offset aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1000a222  push    eax; hModule
0x1000a223  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1000a229  mov     [ebp+var_14], eax
0x1000a22c  mov     _g_wil_details_pfnRtlQueryFeatureConfiguration, eax
0x1000a231  test    eax, eax
0x1000a233  jnz     short loc_1000A23C
0x1000a235  mov     edx, 0C0000139h
0x1000a23a  jmp     short loc_1000A2B6
0x1000a23c  lea     ecx, [ebp+var_10]
0x1000a23f  push    ecx
0x1000a240  lea     ecx, [ebp+var_24]
0x1000a243  push    ecx
0x1000a244  push    [ebp+var_18]; unsigned int
0x1000a247  mov     ecx, eax
0x1000a249  push    [ebp+var_1C]; void *
0x1000a24c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000a252  call    [ebp+var_14]
0x1000a255  mov     edx, eax
0x1000a257  mov     ecx, edx
0x1000a259  test    edx, edx
0x1000a25b  jnz     short loc_1000A29B
0x1000a25d  mov     ecx, dword ptr [ebp+var_10+4]
0x1000a260  mov     eax, ecx
0x1000a262  shr     eax, 4
0x1000a265  and     eax, 3
0x1000a268  mov     [esi], eax
0x1000a26a  mov     eax, ecx
0x1000a26c  shr     eax, 8
0x1000a26f  and     al, 3Fh
0x1000a271  mov     [esi+4], al
0x1000a274  mov     eax, [ebp+var_8]
0x1000a277  mov     [esi+0Ch], eax
0x1000a27a  mov     eax, ecx
0x1000a27c  shr     eax, 0Eh
0x1000a27f  and     eax, 3
0x1000a282  mov     [esi+8], eax
0x1000a285  mov     eax, ecx
0x1000a287  shr     eax, 6
0x1000a28a  and     eax, 1
0x1000a28d  shr     ecx, 7
0x1000a290  and     ecx, 1
0x1000a293  mov     [esi+14h], eax
0x1000a296  mov     [esi+10h], ecx
0x1000a299  jmp     short loc_1000A2B1
0x1000a29b  mov     edx, ecx
0x1000a29d  cmp     ecx, 117h
0x1000a2a3  jnz     short loc_1000A2B6
0x1000a2a5  mov     eax, dword ptr [ebp+var_10+4]
0x1000a2a8  shr     eax, 7
0x1000a2ab  and     eax, 1
0x1000a2ae  mov     [esi+10h], eax
0x1000a2b1  mov     ebx, 1
0x1000a2b6  mov     eax, ebx
0x1000a2b8  test    edi, edi
0x1000a2ba  jz      short loc_1000A2C9
0x1000a2bc  xor     ecx, ecx
0x1000a2be  cmp     edx, 80000022h
0x1000a2c4  setnz   cl
0x1000a2c7  mov     [edi], ecx
0x1000a2c9  mov     ecx, [ebp+var_4]
0x1000a2cc  pop     edi
0x1000a2cd  pop     esi
0x1000a2ce  xor     ecx, ebp; StackCookie
0x1000a2d0  pop     ebx
0x1000a2d1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000a2d6  mov     esp, ebp
0x1000a2d8  pop     ebp
0x1000a2d9  retn    10h
```
