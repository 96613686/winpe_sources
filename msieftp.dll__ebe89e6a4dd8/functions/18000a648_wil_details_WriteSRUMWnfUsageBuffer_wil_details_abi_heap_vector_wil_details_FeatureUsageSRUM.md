# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000a648`
- end: `0x18000a880`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180003000`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18000a648`
- `0x18000adf0`
- `0x1800271f0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a6d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a6d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a6e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a6e8`

## string_xrefs

- `0x18000a6ca`: `ntdll.dll`

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
0x18000a648  push    rbp
0x18000a64a  push    rbx
0x18000a64b  push    rsi
0x18000a64c  push    rdi
0x18000a64d  push    r14
0x18000a64f  push    r15
0x18000a651  lea     rbp, [rsp-0F68h]
0x18000a659  mov     eax, 1068h
0x18000a65e  call    _alloca_probe
0x18000a663  sub     rsp, rax
0x18000a666  mov     rax, cs:__security_cookie
0x18000a66d  xor     rax, rsp
0x18000a670  mov     [rbp+0F90h+var_40], rax
0x18000a677  mov     rax, [rcx+8]
0x18000a67b  xor     ebx, ebx
0x18000a67d  sub     rax, [rcx]
0x18000a680  xor     esi, esi
0x18000a682  mov     r14, rcx
0x18000a685  cmp     rax, 0Ch
0x18000a689  jb      loc_18000A84C
0x18000a68f  xor     r15d, r15d
0x18000a692  xor     edx, edx; Val
0x18000a694  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000a699  mov     r8d, 1000h; Size
0x18000a69f  call    memset_0
0x18000a6a4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000a6ac  mov     [rsp+1090h+var_1050], 1000h
0x18000a6b4  mov     [rsp+1090h+var_104C], 0
0x18000a6bc  jnz     short loc_18000A706
0x18000a6be  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a6c5  test    rax, rax
0x18000a6c8  jnz     short loc_18000A6DE
0x18000a6ca  lea     rcx, ModuleName; "ntdll.dll"
0x18000a6d1  call    cs:__imp_GetModuleHandleW
0x18000a6d7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a6de  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000a6e5  mov     rcx, rax; hModule
0x18000a6e8  call    cs:__imp_GetProcAddress
0x18000a6ee  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000a6f5  test    rax, rax
0x18000a6f8  jnz     short loc_18000A706
0x18000a6fa  mov     edi, 0C0000139h
0x18000a6ff  mov     ebx, edi
0x18000a701  jmp     loc_18000A833
0x18000a706  lea     rax, [rsp+1090h+var_1050]
0x18000a70b  xor     r8d, r8d
0x18000a70e  mov     [rsp+1090h+var_1068], rax
0x18000a713  lea     r9, [rsp+1090h+var_104C]
0x18000a718  lea     rax, [rsp+1090h+var_1040]
0x18000a71d  xor     edx, edx
0x18000a71f  mov     [rsp+1090h+var_1070], rax
0x18000a724  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a72b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000a732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a737  mov     ebx, eax
0x18000a739  mov     edi, eax
0x18000a73b  test    eax, eax
0x18000a73d  jnz     loc_18000A833
0x18000a743  mov     r9d, [rsp+1090h+var_1050]
0x18000a748  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000a752  mov     rax, r11
0x18000a755  mul     r9
0x18000a758  shr     rdx, 3
0x18000a75c  lea     rcx, [rdx+rdx*2]
0x18000a760  shl     rcx, 2
0x18000a764  cmp     r9, rcx
0x18000a767  jz      short loc_18000A771
0x18000a769  xor     r9d, r9d
0x18000a76c  mov     [rsp+1090h+var_1050], r9d
0x18000a771  mov     r8, [r14]
0x18000a774  mov     rax, r11
0x18000a777  mov     ecx, r9d
0x18000a77a  mul     rcx
0x18000a77d  mov     rcx, [r14+8]
0x18000a781  mov     rax, r11
0x18000a784  mov     r10, rdx
0x18000a787  sub     rcx, r8
0x18000a78a  mul     rcx
0x18000a78d  shr     r10, 3
0x18000a791  shr     rdx, 3
0x18000a795  lea     rax, [rdx+rdx*2]
0x18000a799  lea     rsi, [r8+rax*4]
0x18000a79d  jmp     short loc_18000A808
0x18000a79f  mov     eax, r10d
0x18000a7a2  lea     rcx, [rax+rax*2]
0x18000a7a6  lea     rdx, [rdx+rcx*4]
0x18000a7aa  lea     rax, [rsp+1090h+var_1040]
0x18000a7af  cmp     rax, rdx
0x18000a7b2  jz      short loc_18000A7D9
0x18000a7b4  mov     r11d, [r8]
0x18000a7b7  lea     rcx, [rsp+1090h+var_1040]
0x18000a7bc  cmp     [rcx], r11d
0x18000a7bf  jnz     short loc_18000A7D0
0x18000a7c1  movzx   eax, word ptr [r8+4]
0x18000a7c6  cmp     [rcx+4], ax
0x18000a7ca  jz      loc_18000A872
0x18000a7d0  add     rcx, 0Ch
0x18000a7d4  cmp     rcx, rdx
0x18000a7d7  jnz     short loc_18000A7BC
0x18000a7d9  mov     eax, r9d
0x18000a7dc  add     rax, 0Ch
0x18000a7e0  cmp     rax, 1000h
0x18000a7e6  ja      short loc_18000A804
0x18000a7e8  movsd   xmm0, qword ptr [r8]
0x18000a7ed  add     r9d, 0Ch
0x18000a7f1  movsd   qword ptr [rdx], xmm0
0x18000a7f5  inc     r10d
0x18000a7f8  mov     eax, [r8+8]
0x18000a7fc  mov     [rdx+8], eax
0x18000a7ff  mov     [rsp+1090h+var_1050], r9d
0x18000a804  add     r8, 0Ch
0x18000a808  lea     rdx, [rsp+1090h+var_1040]
0x18000a80d  cmp     r8, rsi
0x18000a810  jnz     short loc_18000A79F
0x18000a812  mov     eax, [rsp+1090h+var_104C]
0x18000a816  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a81d  mov     [rsp+1090h+var_1060], 1
0x18000a825  mov     r8d, r9d
0x18000a828  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000a82c  call    wil_details_NtUpdateWnfStateData
0x18000a831  mov     esi, eax
0x18000a833  cmp     esi, 0C0000001h
0x18000a839  jnz     short loc_18000A84C
0x18000a83b  inc     r15d
0x18000a83e  cmp     r15d, 64h ; 'd'
0x18000a842  jge     short loc_18000A84C
0x18000a844  test    edi, edi
0x18000a846  jz      loc_18000A692
0x18000a84c  test    ebx, ebx
0x18000a84e  cmovz   ebx, esi
0x18000a851  mov     eax, ebx
0x18000a853  mov     rcx, [rbp+0F90h+var_40]
0x18000a85a  xor     rcx, rsp; StackCookie
0x18000a85d  call    __security_check_cookie
0x18000a862  add     rsp, 1068h
0x18000a869  pop     r15
0x18000a86b  pop     r14
0x18000a86d  pop     rdi
0x18000a86e  pop     rsi
0x18000a86f  pop     rbx
0x18000a870  pop     rbp
0x18000a871  retn
0x18000a872  mov     eax, [r8+8]
0x18000a876  add     [rcx+8], eax
0x18000a879  mov     r9d, [rsp+1090h+var_1050]
0x18000a87e  jmp     short loc_18000A804
```
