# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001d064`
- end: `0x18001d29c`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180011990`

## callees

- `0x1800022e0`
- `0x180002cbc`
- `0x18001d064`
- `0x18001d34c`
- `0x18001ea10`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d0ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d0ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d104`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d104`

## string_xrefs

- `0x18001d0e6`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int v1; // ebx
  unsigned int updated; // esi
  int v4; // r15d
  HMODULE ModuleHandleW; // rax
  int v6; // edi
  unsigned int v7; // r9d
  __int64 v8; // r8
  int v9; // r10d
  unsigned __int64 v10; // rsi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  unsigned int v14; // [rsp+40h] [rbp-C0h]
  _DWORD v15[3]; // [rsp+44h] [rbp-BCh] BYREF
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
        v1 = ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, _DWORD *))g_wil_details_pfnNtQueryWnfStateData)(
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
              if ( (unsigned __int64)v7 + 12 <= 0x1000 )
              {
                v7 += 12;
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
                      (unsigned int)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                      (unsigned int)v16,
                      v7,
                      v7,
                      (unsigned int)v16,
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
0x18001d064  push    rbp
0x18001d066  push    rbx
0x18001d067  push    rsi
0x18001d068  push    rdi
0x18001d069  push    r14
0x18001d06b  push    r15
0x18001d06d  lea     rbp, [rsp-0F68h]
0x18001d075  mov     eax, 1068h
0x18001d07a  call    _alloca_probe
0x18001d07f  sub     rsp, rax
0x18001d082  mov     rax, cs:__security_cookie
0x18001d089  xor     rax, rsp
0x18001d08c  mov     [rbp+0F90h+var_40], rax
0x18001d093  mov     rax, [rcx+8]
0x18001d097  xor     ebx, ebx
0x18001d099  sub     rax, [rcx]
0x18001d09c  xor     esi, esi
0x18001d09e  mov     r14, rcx
0x18001d0a1  cmp     rax, 0Ch
0x18001d0a5  jb      loc_18001D268
0x18001d0ab  xor     r15d, r15d
0x18001d0ae  xor     edx, edx; Val
0x18001d0b0  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001d0b5  mov     r8d, 1000h; Size
0x18001d0bb  call    memset_0
0x18001d0c0  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18001d0c8  mov     [rsp+1090h+var_1050], 1000h
0x18001d0d0  mov     [rsp+1090h+var_104C], 0
0x18001d0d8  jnz     short loc_18001D122
0x18001d0da  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001d0e1  test    rax, rax
0x18001d0e4  jnz     short loc_18001D0FA
0x18001d0e6  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001d0ed  call    cs:__imp_GetModuleHandleW
0x18001d0f3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001d0fa  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18001d101  mov     rcx, rax; hModule
0x18001d104  call    cs:__imp_GetProcAddress
0x18001d10a  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18001d111  test    rax, rax
0x18001d114  jnz     short loc_18001D122
0x18001d116  mov     edi, 0C0000139h
0x18001d11b  mov     ebx, edi
0x18001d11d  jmp     loc_18001D24F
0x18001d122  lea     rax, [rsp+1090h+var_1050]
0x18001d127  xor     r8d, r8d
0x18001d12a  mov     [rsp+1090h+var_1068], rax
0x18001d12f  lea     r9, [rsp+1090h+var_104C]
0x18001d134  lea     rax, [rsp+1090h+var_1040]
0x18001d139  xor     edx, edx
0x18001d13b  mov     [rsp+1090h+var_1070], rax
0x18001d140  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001d147  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18001d14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d153  mov     ebx, eax
0x18001d155  mov     edi, eax
0x18001d157  test    eax, eax
0x18001d159  jnz     loc_18001D24F
0x18001d15f  mov     r9d, [rsp+1090h+var_1050]
0x18001d164  mov     r11, 0AAAAAAAAAAAAAAABh
0x18001d16e  mov     rax, r11
0x18001d171  mul     r9
0x18001d174  shr     rdx, 3
0x18001d178  lea     rcx, [rdx+rdx*2]
0x18001d17c  shl     rcx, 2
0x18001d180  cmp     r9, rcx
0x18001d183  jz      short loc_18001D18D
0x18001d185  xor     r9d, r9d
0x18001d188  mov     [rsp+1090h+var_1050], r9d
0x18001d18d  mov     r8, [r14]
0x18001d190  mov     rax, r11
0x18001d193  mov     ecx, r9d
0x18001d196  mul     rcx
0x18001d199  mov     rcx, [r14+8]
0x18001d19d  mov     rax, r11
0x18001d1a0  mov     r10, rdx
0x18001d1a3  sub     rcx, r8
0x18001d1a6  mul     rcx
0x18001d1a9  shr     r10, 3
0x18001d1ad  shr     rdx, 3
0x18001d1b1  lea     rax, [rdx+rdx*2]
0x18001d1b5  lea     rsi, [r8+rax*4]
0x18001d1b9  jmp     short loc_18001D224
0x18001d1bb  mov     eax, r10d
0x18001d1be  lea     rcx, [rax+rax*2]
0x18001d1c2  lea     rdx, [rdx+rcx*4]
0x18001d1c6  lea     rax, [rsp+1090h+var_1040]
0x18001d1cb  cmp     rax, rdx
0x18001d1ce  jz      short loc_18001D1F5
0x18001d1d0  mov     r11d, [r8]
0x18001d1d3  lea     rcx, [rsp+1090h+var_1040]
0x18001d1d8  cmp     [rcx], r11d
0x18001d1db  jnz     short loc_18001D1EC
0x18001d1dd  movzx   eax, word ptr [r8+4]
0x18001d1e2  cmp     [rcx+4], ax
0x18001d1e6  jz      loc_18001D28E
0x18001d1ec  add     rcx, 0Ch
0x18001d1f0  cmp     rcx, rdx
0x18001d1f3  jnz     short loc_18001D1D8
0x18001d1f5  mov     eax, r9d
0x18001d1f8  add     rax, 0Ch
0x18001d1fc  cmp     rax, 1000h
0x18001d202  ja      short loc_18001D220
0x18001d204  movsd   xmm0, qword ptr [r8]
0x18001d209  add     r9d, 0Ch
0x18001d20d  movsd   qword ptr [rdx], xmm0
0x18001d211  inc     r10d
0x18001d214  mov     eax, [r8+8]
0x18001d218  mov     [rdx+8], eax
0x18001d21b  mov     [rsp+1090h+var_1050], r9d
0x18001d220  add     r8, 0Ch
0x18001d224  lea     rdx, [rsp+1090h+var_1040]
0x18001d229  cmp     r8, rsi
0x18001d22c  jnz     short loc_18001D1BB
0x18001d22e  mov     eax, [rsp+1090h+var_104C]
0x18001d232  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001d239  mov     [rsp+1090h+var_1060], 1
0x18001d241  mov     r8d, r9d
0x18001d244  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001d248  call    wil_details_NtUpdateWnfStateData
0x18001d24d  mov     esi, eax
0x18001d24f  cmp     esi, 0C0000001h
0x18001d255  jnz     short loc_18001D268
0x18001d257  inc     r15d
0x18001d25a  cmp     r15d, 64h ; 'd'
0x18001d25e  jge     short loc_18001D268
0x18001d260  test    edi, edi
0x18001d262  jz      loc_18001D0AE
0x18001d268  test    ebx, ebx
0x18001d26a  cmovz   ebx, esi
0x18001d26d  mov     eax, ebx
0x18001d26f  mov     rcx, [rbp+0F90h+var_40]
0x18001d276  xor     rcx, rsp; StackCookie
0x18001d279  call    __security_check_cookie
0x18001d27e  add     rsp, 1068h
0x18001d285  pop     r15
0x18001d287  pop     r14
0x18001d289  pop     rdi
0x18001d28a  pop     rsi
0x18001d28b  pop     rbx
0x18001d28c  pop     rbp
0x18001d28d  retn
0x18001d28e  mov     eax, [r8+8]
0x18001d292  add     [rcx+8], eax
0x18001d295  mov     r9d, [rsp+1090h+var_1050]
0x18001d29a  jmp     short loc_18001D220
```
