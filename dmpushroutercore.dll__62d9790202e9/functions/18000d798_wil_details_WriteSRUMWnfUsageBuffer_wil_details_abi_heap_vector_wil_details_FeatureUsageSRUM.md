# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000d798`
- end: `0x18000d9d0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180006760`

## callees

- `0x1800039f0`
- `0x1800043a8`
- `0x18000d798`
- `0x18000e520`
- `0x1800388e0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d821`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d821`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d838`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d838`

## string_xrefs

- `0x18000d81a`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int v1; // ebx
  unsigned int updated; // esi
  int v4; // r15d
  HMODULE ModuleHandleW; // rax
  int v6; // edi
  __int64 v7; // r9
  __int64 v8; // r8
  int v9; // r10d
  unsigned __int64 v10; // rsi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  unsigned int v14; // [rsp+40h] [rbp-C0h]
  int v15[3]; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v16[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v1 = 0;
  updated = 0;
  if ( (unsigned __int64)(a1[1] - *a1) >= 0xC )
  {
    v4 = 0;
    do
    {
      memset_0(v16, 0, sizeof(v16));
      v15[0] = 0;
      if ( g_wil_details_pfnNtQueryWnfStateData )
        goto LABEL_8;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      g_wil_details_pfnNtQueryWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
      if ( g_wil_details_pfnNtQueryWnfStateData )
      {
LABEL_8:
        v1 = ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, int *))g_wil_details_pfnNtQueryWnfStateData)(
               &__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
               0,
               0,
               v15);
        v6 = v1;
        if ( !v1 )
        {
          v7 = 0;
          v14 = 0;
          v8 = *a1;
          v9 = 0;
          v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
          while ( v8 != v10 )
          {
            v11 = &v16[3 * v9];
            if ( v16 == v11 )
            {
LABEL_15:
              if ( (unsigned __int64)(unsigned int)v7 + 12 <= 0x1000 )
              {
                v7 = (unsigned int)(v7 + 12);
                *(_QWORD *)v11 = *(_QWORD *)v8;
                ++v9;
                v11[2] = *(_DWORD *)(v8 + 8);
                v14 = v7;
              }
            }
            else
            {
              v12 = v16;
              while ( *v12 != *(_DWORD *)v8 || *((_WORD *)v12 + 2) != *(_WORD *)(v8 + 4) )
              {
                v12 += 3;
                if ( v12 == v11 )
                  goto LABEL_15;
              }
              v12[2] += *(_DWORD *)(v8 + 8);
              v7 = v14;
            }
            v8 += 12;
          }
          updated = wil_details_NtUpdateWnfStateData(
                      (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                      (__int64)v16,
                      v7,
                      v7,
                      (int)v16,
                      v15[0],
                      1);
        }
      }
      else
      {
        v6 = -1073741511;
        v1 = -1073741511;
      }
      if ( updated != -1073741823 )
        break;
      if ( ++v4 >= 100 )
        break;
    }
    while ( !v6 );
  }
  if ( !v1 )
    return updated;
  return v1;
}

```

## disassembly

```asm
0x18000d798  push    rbp
0x18000d79a  push    rbx
0x18000d79b  push    rsi
0x18000d79c  push    rdi
0x18000d79d  push    r14
0x18000d79f  push    r15
0x18000d7a1  lea     rbp, [rsp-0F68h]
0x18000d7a9  mov     eax, 1068h
0x18000d7ae  call    _alloca_probe
0x18000d7b3  sub     rsp, rax
0x18000d7b6  mov     rax, cs:__security_cookie
0x18000d7bd  xor     rax, rsp
0x18000d7c0  mov     [rbp+0F90h+var_40], rax
0x18000d7c7  mov     rax, [rcx+8]
0x18000d7cb  xor     ebx, ebx
0x18000d7cd  sub     rax, [rcx]
0x18000d7d0  xor     esi, esi
0x18000d7d2  mov     r14, rcx
0x18000d7d5  cmp     rax, 0Ch
0x18000d7d9  jb      loc_18000D99C
0x18000d7df  xor     r15d, r15d
0x18000d7e2  xor     edx, edx; Val
0x18000d7e4  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000d7e9  mov     r8d, 1000h; Size
0x18000d7ef  call    memset_0
0x18000d7f4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000d7fc  mov     [rsp+1090h+var_1050], 1000h
0x18000d804  mov     [rsp+1090h+var_104C], 0
0x18000d80c  jnz     short loc_18000D856
0x18000d80e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d815  test    rax, rax
0x18000d818  jnz     short loc_18000D82E
0x18000d81a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000d821  call    cs:__imp_GetModuleHandleW
0x18000d827  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d82e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000d835  mov     rcx, rax; hModule
0x18000d838  call    cs:__imp_GetProcAddress
0x18000d83e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000d845  test    rax, rax
0x18000d848  jnz     short loc_18000D856
0x18000d84a  mov     edi, 0C0000139h
0x18000d84f  mov     ebx, edi
0x18000d851  jmp     loc_18000D983
0x18000d856  lea     rax, [rsp+1090h+var_1050]
0x18000d85b  xor     r8d, r8d
0x18000d85e  mov     [rsp+1090h+var_1068], rax
0x18000d863  lea     r9, [rsp+1090h+var_104C]
0x18000d868  lea     rax, [rsp+1090h+var_1040]
0x18000d86d  xor     edx, edx
0x18000d86f  mov     [rsp+1090h+var_1070], rax
0x18000d874  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d87b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000d882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d887  mov     ebx, eax
0x18000d889  mov     edi, eax
0x18000d88b  test    eax, eax
0x18000d88d  jnz     loc_18000D983
0x18000d893  mov     r9d, [rsp+1090h+var_1050]
0x18000d898  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000d8a2  mov     rax, r11
0x18000d8a5  mul     r9
0x18000d8a8  shr     rdx, 3
0x18000d8ac  lea     rcx, [rdx+rdx*2]
0x18000d8b0  shl     rcx, 2
0x18000d8b4  cmp     r9, rcx
0x18000d8b7  jz      short loc_18000D8C1
0x18000d8b9  xor     r9d, r9d
0x18000d8bc  mov     [rsp+1090h+var_1050], r9d
0x18000d8c1  mov     r8, [r14]
0x18000d8c4  mov     rax, r11
0x18000d8c7  mov     ecx, r9d
0x18000d8ca  mul     rcx
0x18000d8cd  mov     rcx, [r14+8]
0x18000d8d1  mov     rax, r11
0x18000d8d4  mov     r10, rdx
0x18000d8d7  sub     rcx, r8
0x18000d8da  mul     rcx
0x18000d8dd  shr     r10, 3
0x18000d8e1  shr     rdx, 3
0x18000d8e5  lea     rax, [rdx+rdx*2]
0x18000d8e9  lea     rsi, [r8+rax*4]
0x18000d8ed  jmp     short loc_18000D958
0x18000d8ef  mov     eax, r10d
0x18000d8f2  lea     rcx, [rax+rax*2]
0x18000d8f6  lea     rdx, [rdx+rcx*4]
0x18000d8fa  lea     rax, [rsp+1090h+var_1040]
0x18000d8ff  cmp     rax, rdx
0x18000d902  jz      short loc_18000D929
0x18000d904  mov     r11d, [r8]
0x18000d907  lea     rcx, [rsp+1090h+var_1040]
0x18000d90c  cmp     [rcx], r11d
0x18000d90f  jnz     short loc_18000D920
0x18000d911  movzx   eax, word ptr [r8+4]
0x18000d916  cmp     [rcx+4], ax
0x18000d91a  jz      loc_18000D9C2
0x18000d920  add     rcx, 0Ch
0x18000d924  cmp     rcx, rdx
0x18000d927  jnz     short loc_18000D90C
0x18000d929  mov     eax, r9d
0x18000d92c  add     rax, 0Ch
0x18000d930  cmp     rax, 1000h
0x18000d936  ja      short loc_18000D954
0x18000d938  movsd   xmm0, qword ptr [r8]
0x18000d93d  add     r9d, 0Ch
0x18000d941  movsd   qword ptr [rdx], xmm0
0x18000d945  inc     r10d
0x18000d948  mov     eax, [r8+8]
0x18000d94c  mov     [rdx+8], eax
0x18000d94f  mov     [rsp+1090h+var_1050], r9d
0x18000d954  add     r8, 0Ch
0x18000d958  lea     rdx, [rsp+1090h+var_1040]
0x18000d95d  cmp     r8, rsi
0x18000d960  jnz     short loc_18000D8EF
0x18000d962  mov     eax, [rsp+1090h+var_104C]
0x18000d966  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d96d  mov     [rsp+1090h+var_1060], 1
0x18000d975  mov     r8d, r9d
0x18000d978  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000d97c  call    wil_details_NtUpdateWnfStateData
0x18000d981  mov     esi, eax
0x18000d983  cmp     esi, 0C0000001h
0x18000d989  jnz     short loc_18000D99C
0x18000d98b  inc     r15d
0x18000d98e  cmp     r15d, 64h ; 'd'
0x18000d992  jge     short loc_18000D99C
0x18000d994  test    edi, edi
0x18000d996  jz      loc_18000D7E2
0x18000d99c  test    ebx, ebx
0x18000d99e  cmovz   ebx, esi
0x18000d9a1  mov     eax, ebx
0x18000d9a3  mov     rcx, [rbp+0F90h+var_40]
0x18000d9aa  xor     rcx, rsp; StackCookie
0x18000d9ad  call    __security_check_cookie
0x18000d9b2  add     rsp, 1068h
0x18000d9b9  pop     r15
0x18000d9bb  pop     r14
0x18000d9bd  pop     rdi
0x18000d9be  pop     rsi
0x18000d9bf  pop     rbx
0x18000d9c0  pop     rbp
0x18000d9c1  retn
0x18000d9c2  mov     eax, [r8+8]
0x18000d9c6  add     [rcx+8], eax
0x18000d9c9  mov     r9d, [rsp+1090h+var_1050]
0x18000d9ce  jmp     short loc_18000D954
```
