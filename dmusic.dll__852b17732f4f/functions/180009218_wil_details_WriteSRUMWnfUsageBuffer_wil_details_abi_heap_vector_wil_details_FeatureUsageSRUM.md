# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180009218`
- end: `0x180009450`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002410`

## callees

- `0x1800016d0`
- `0x1800021a8`
- `0x180009218`
- `0x1800096e0`
- `0x180021750`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800092a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800092a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800092b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800092b8`

## string_xrefs

- `0x18000929a`: `ntdll.dll`

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
0x180009218  push    rbp
0x18000921a  push    rbx
0x18000921b  push    rsi
0x18000921c  push    rdi
0x18000921d  push    r14
0x18000921f  push    r15
0x180009221  lea     rbp, [rsp-0F68h]
0x180009229  mov     eax, 1068h
0x18000922e  call    _alloca_probe
0x180009233  sub     rsp, rax
0x180009236  mov     rax, cs:__security_cookie
0x18000923d  xor     rax, rsp
0x180009240  mov     [rbp+0F90h+var_40], rax
0x180009247  mov     rax, [rcx+8]
0x18000924b  xor     ebx, ebx
0x18000924d  sub     rax, [rcx]
0x180009250  xor     esi, esi
0x180009252  mov     r14, rcx
0x180009255  cmp     rax, 0Ch
0x180009259  jb      loc_18000941C
0x18000925f  xor     r15d, r15d
0x180009262  xor     edx, edx; Val
0x180009264  lea     rcx, [rsp+1090h+var_1040]; void *
0x180009269  mov     r8d, 1000h; Size
0x18000926f  call    memset_0
0x180009274  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000927c  mov     [rsp+1090h+var_1050], 1000h
0x180009284  mov     [rsp+1090h+var_104C], 0
0x18000928c  jnz     short loc_1800092D6
0x18000928e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009295  test    rax, rax
0x180009298  jnz     short loc_1800092AE
0x18000929a  lea     rcx, ModuleName; "ntdll.dll"
0x1800092a1  call    cs:__imp_GetModuleHandleW
0x1800092a7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800092ae  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800092b5  mov     rcx, rax; hModule
0x1800092b8  call    cs:__imp_GetProcAddress
0x1800092be  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800092c5  test    rax, rax
0x1800092c8  jnz     short loc_1800092D6
0x1800092ca  mov     edi, 0C0000139h
0x1800092cf  mov     ebx, edi
0x1800092d1  jmp     loc_180009403
0x1800092d6  lea     rax, [rsp+1090h+var_1050]
0x1800092db  xor     r8d, r8d
0x1800092de  mov     [rsp+1090h+var_1068], rax
0x1800092e3  lea     r9, [rsp+1090h+var_104C]
0x1800092e8  lea     rax, [rsp+1090h+var_1040]
0x1800092ed  xor     edx, edx
0x1800092ef  mov     [rsp+1090h+var_1070], rax
0x1800092f4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800092fb  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180009302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009307  mov     ebx, eax
0x180009309  mov     edi, eax
0x18000930b  test    eax, eax
0x18000930d  jnz     loc_180009403
0x180009313  mov     r9d, [rsp+1090h+var_1050]
0x180009318  mov     r11, 0AAAAAAAAAAAAAAABh
0x180009322  mov     rax, r11
0x180009325  mul     r9
0x180009328  shr     rdx, 3
0x18000932c  lea     rcx, [rdx+rdx*2]
0x180009330  shl     rcx, 2
0x180009334  cmp     r9, rcx
0x180009337  jz      short loc_180009341
0x180009339  xor     r9d, r9d
0x18000933c  mov     [rsp+1090h+var_1050], r9d
0x180009341  mov     r8, [r14]
0x180009344  mov     rax, r11
0x180009347  mov     ecx, r9d
0x18000934a  mul     rcx
0x18000934d  mov     rcx, [r14+8]
0x180009351  mov     rax, r11
0x180009354  mov     r10, rdx
0x180009357  sub     rcx, r8
0x18000935a  mul     rcx
0x18000935d  shr     r10, 3
0x180009361  shr     rdx, 3
0x180009365  lea     rax, [rdx+rdx*2]
0x180009369  lea     rsi, [r8+rax*4]
0x18000936d  jmp     short loc_1800093D8
0x18000936f  mov     eax, r10d
0x180009372  lea     rcx, [rax+rax*2]
0x180009376  lea     rdx, [rdx+rcx*4]
0x18000937a  lea     rax, [rsp+1090h+var_1040]
0x18000937f  cmp     rax, rdx
0x180009382  jz      short loc_1800093A9
0x180009384  mov     r11d, [r8]
0x180009387  lea     rcx, [rsp+1090h+var_1040]
0x18000938c  cmp     [rcx], r11d
0x18000938f  jnz     short loc_1800093A0
0x180009391  movzx   eax, word ptr [r8+4]
0x180009396  cmp     [rcx+4], ax
0x18000939a  jz      loc_180009442
0x1800093a0  add     rcx, 0Ch
0x1800093a4  cmp     rcx, rdx
0x1800093a7  jnz     short loc_18000938C
0x1800093a9  mov     eax, r9d
0x1800093ac  add     rax, 0Ch
0x1800093b0  cmp     rax, 1000h
0x1800093b6  ja      short loc_1800093D4
0x1800093b8  movsd   xmm0, qword ptr [r8]
0x1800093bd  add     r9d, 0Ch
0x1800093c1  movsd   qword ptr [rdx], xmm0
0x1800093c5  inc     r10d
0x1800093c8  mov     eax, [r8+8]
0x1800093cc  mov     [rdx+8], eax
0x1800093cf  mov     [rsp+1090h+var_1050], r9d
0x1800093d4  add     r8, 0Ch
0x1800093d8  lea     rdx, [rsp+1090h+var_1040]
0x1800093dd  cmp     r8, rsi
0x1800093e0  jnz     short loc_18000936F
0x1800093e2  mov     eax, [rsp+1090h+var_104C]
0x1800093e6  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800093ed  mov     [rsp+1090h+var_1060], 1
0x1800093f5  mov     r8d, r9d
0x1800093f8  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800093fc  call    wil_details_NtUpdateWnfStateData
0x180009401  mov     esi, eax
0x180009403  cmp     esi, 0C0000001h
0x180009409  jnz     short loc_18000941C
0x18000940b  inc     r15d
0x18000940e  cmp     r15d, 64h ; 'd'
0x180009412  jge     short loc_18000941C
0x180009414  test    edi, edi
0x180009416  jz      loc_180009262
0x18000941c  test    ebx, ebx
0x18000941e  cmovz   ebx, esi
0x180009421  mov     eax, ebx
0x180009423  mov     rcx, [rbp+0F90h+var_40]
0x18000942a  xor     rcx, rsp; StackCookie
0x18000942d  call    __security_check_cookie
0x180009432  add     rsp, 1068h
0x180009439  pop     r15
0x18000943b  pop     r14
0x18000943d  pop     rdi
0x18000943e  pop     rsi
0x18000943f  pop     rbx
0x180009440  pop     rbp
0x180009441  retn
0x180009442  mov     eax, [r8+8]
0x180009446  add     [rcx+8], eax
0x180009449  mov     r9d, [rsp+1090h+var_1050]
0x18000944e  jmp     short loc_1800093D4
```
