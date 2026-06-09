# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000c86c`
- end: `0x18000caa4`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180008eb0`

## callees

- `0x1800021d0`
- `0x180002b78`
- `0x18000c86c`
- `0x18000cd00`
- `0x180030510`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c8f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c8f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c90c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c90c`

## string_xrefs

- `0x18000c8ee`: `ntdll.dll`

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
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x18000c86c  push    rbp
0x18000c86e  push    rbx
0x18000c86f  push    rsi
0x18000c870  push    rdi
0x18000c871  push    r14
0x18000c873  push    r15
0x18000c875  lea     rbp, [rsp-0F68h]
0x18000c87d  mov     eax, 1068h
0x18000c882  call    _alloca_probe
0x18000c887  sub     rsp, rax
0x18000c88a  mov     rax, cs:__security_cookie
0x18000c891  xor     rax, rsp
0x18000c894  mov     [rbp+0F90h+var_40], rax
0x18000c89b  mov     rax, [rcx+8]
0x18000c89f  xor     ebx, ebx
0x18000c8a1  sub     rax, [rcx]
0x18000c8a4  xor     esi, esi
0x18000c8a6  mov     r14, rcx
0x18000c8a9  cmp     rax, 0Ch
0x18000c8ad  jb      loc_18000CA70
0x18000c8b3  xor     r15d, r15d
0x18000c8b6  xor     edx, edx; Val
0x18000c8b8  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000c8bd  mov     r8d, 1000h; Size
0x18000c8c3  call    memset_0
0x18000c8c8  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000c8d0  mov     [rsp+1090h+var_1050], 1000h
0x18000c8d8  mov     [rsp+1090h+var_104C], 0
0x18000c8e0  jnz     short loc_18000C92A
0x18000c8e2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c8e9  test    rax, rax
0x18000c8ec  jnz     short loc_18000C902
0x18000c8ee  lea     rcx, ModuleName; "ntdll.dll"
0x18000c8f5  call    cs:__imp_GetModuleHandleW
0x18000c8fb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c902  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000c909  mov     rcx, rax; hModule
0x18000c90c  call    cs:__imp_GetProcAddress
0x18000c912  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000c919  test    rax, rax
0x18000c91c  jnz     short loc_18000C92A
0x18000c91e  mov     edi, 0C0000139h
0x18000c923  mov     ebx, edi
0x18000c925  jmp     loc_18000CA57
0x18000c92a  lea     rax, [rsp+1090h+var_1050]
0x18000c92f  xor     r8d, r8d
0x18000c932  mov     [rsp+1090h+var_1068], rax
0x18000c937  lea     r9, [rsp+1090h+var_104C]
0x18000c93c  lea     rax, [rsp+1090h+var_1040]
0x18000c941  xor     edx, edx
0x18000c943  mov     [rsp+1090h+var_1070], rax
0x18000c948  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000c94f  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000c956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c95b  mov     ebx, eax
0x18000c95d  mov     edi, eax
0x18000c95f  test    eax, eax
0x18000c961  jnz     loc_18000CA57
0x18000c967  mov     r9d, [rsp+1090h+var_1050]
0x18000c96c  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000c976  mov     rax, r11
0x18000c979  mul     r9
0x18000c97c  shr     rdx, 3
0x18000c980  lea     rcx, [rdx+rdx*2]
0x18000c984  shl     rcx, 2
0x18000c988  cmp     r9, rcx
0x18000c98b  jz      short loc_18000C995
0x18000c98d  xor     r9d, r9d
0x18000c990  mov     [rsp+1090h+var_1050], r9d
0x18000c995  mov     r8, [r14]
0x18000c998  mov     rax, r11
0x18000c99b  mov     ecx, r9d
0x18000c99e  mul     rcx
0x18000c9a1  mov     rcx, [r14+8]
0x18000c9a5  mov     rax, r11
0x18000c9a8  mov     r10, rdx
0x18000c9ab  sub     rcx, r8
0x18000c9ae  mul     rcx
0x18000c9b1  shr     r10, 3
0x18000c9b5  shr     rdx, 3
0x18000c9b9  lea     rax, [rdx+rdx*2]
0x18000c9bd  lea     rsi, [r8+rax*4]
0x18000c9c1  jmp     short loc_18000CA2C
0x18000c9c3  mov     eax, r10d
0x18000c9c6  lea     rcx, [rax+rax*2]
0x18000c9ca  lea     rdx, [rdx+rcx*4]
0x18000c9ce  lea     rax, [rsp+1090h+var_1040]
0x18000c9d3  cmp     rax, rdx
0x18000c9d6  jz      short loc_18000C9FD
0x18000c9d8  mov     r11d, [r8]
0x18000c9db  lea     rcx, [rsp+1090h+var_1040]
0x18000c9e0  cmp     [rcx], r11d
0x18000c9e3  jnz     short loc_18000C9F4
0x18000c9e5  movzx   eax, word ptr [r8+4]
0x18000c9ea  cmp     [rcx+4], ax
0x18000c9ee  jz      loc_18000CA96
0x18000c9f4  add     rcx, 0Ch
0x18000c9f8  cmp     rcx, rdx
0x18000c9fb  jnz     short loc_18000C9E0
0x18000c9fd  mov     eax, r9d
0x18000ca00  add     rax, 0Ch
0x18000ca04  cmp     rax, 1000h
0x18000ca0a  ja      short loc_18000CA28
0x18000ca0c  movsd   xmm0, qword ptr [r8]
0x18000ca11  add     r9d, 0Ch
0x18000ca15  movsd   qword ptr [rdx], xmm0
0x18000ca19  inc     r10d
0x18000ca1c  mov     eax, [r8+8]
0x18000ca20  mov     [rdx+8], eax
0x18000ca23  mov     [rsp+1090h+var_1050], r9d
0x18000ca28  add     r8, 0Ch
0x18000ca2c  lea     rdx, [rsp+1090h+var_1040]
0x18000ca31  cmp     r8, rsi
0x18000ca34  jnz     short loc_18000C9C3
0x18000ca36  mov     eax, [rsp+1090h+var_104C]
0x18000ca3a  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000ca41  mov     [rsp+1090h+var_1060], 1
0x18000ca49  mov     r8d, r9d
0x18000ca4c  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000ca50  call    wil_details_NtUpdateWnfStateData
0x18000ca55  mov     esi, eax
0x18000ca57  cmp     esi, 0C0000001h
0x18000ca5d  jnz     short loc_18000CA70
0x18000ca5f  inc     r15d
0x18000ca62  cmp     r15d, 64h ; 'd'
0x18000ca66  jge     short loc_18000CA70
0x18000ca68  test    edi, edi
0x18000ca6a  jz      loc_18000C8B6
0x18000ca70  test    ebx, ebx
0x18000ca72  cmovz   ebx, esi
0x18000ca75  mov     eax, ebx
0x18000ca77  mov     rcx, [rbp+0F90h+var_40]
0x18000ca7e  xor     rcx, rsp; StackCookie
0x18000ca81  call    __security_check_cookie
0x18000ca86  add     rsp, 1068h
0x18000ca8d  pop     r15
0x18000ca8f  pop     r14
0x18000ca91  pop     rdi
0x18000ca92  pop     rsi
0x18000ca93  pop     rbx
0x18000ca94  pop     rbp
0x18000ca95  retn
0x18000ca96  mov     eax, [r8+8]
0x18000ca9a  add     [rcx+8], eax
0x18000ca9d  mov     r9d, [rsp+1090h+var_1050]
0x18000caa2  jmp     short loc_18000CA28
```
