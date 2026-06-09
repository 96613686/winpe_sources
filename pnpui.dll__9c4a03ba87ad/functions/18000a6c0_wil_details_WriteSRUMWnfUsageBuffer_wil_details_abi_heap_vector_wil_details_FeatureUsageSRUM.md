# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000a6c0`
- end: `0x18000a8f8`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180003a40`

## callees

- `0x18000a6c0`
- `0x18000b1e8`
- `0x18000ccde`
- `0x18000cd10`
- `0x18000cda0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a760`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a760`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a749`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a749`

## string_xrefs

- `0x18000a742`: `ntdll.dll`

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
0x18000a6c0  push    rbp
0x18000a6c2  push    rbx
0x18000a6c3  push    rsi
0x18000a6c4  push    rdi
0x18000a6c5  push    r14
0x18000a6c7  push    r15
0x18000a6c9  lea     rbp, [rsp-0F68h]
0x18000a6d1  mov     eax, 1068h
0x18000a6d6  call    _alloca_probe
0x18000a6db  sub     rsp, rax
0x18000a6de  mov     rax, cs:__security_cookie
0x18000a6e5  xor     rax, rsp
0x18000a6e8  mov     [rbp+0F90h+var_40], rax
0x18000a6ef  mov     rax, [rcx+8]
0x18000a6f3  xor     ebx, ebx
0x18000a6f5  sub     rax, [rcx]
0x18000a6f8  xor     esi, esi
0x18000a6fa  mov     r14, rcx
0x18000a6fd  cmp     rax, 0Ch
0x18000a701  jb      loc_18000A8C4
0x18000a707  xor     r15d, r15d
0x18000a70a  xor     edx, edx; Val
0x18000a70c  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000a711  mov     r8d, 1000h; Size
0x18000a717  call    memset_0
0x18000a71c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000a724  mov     [rsp+1090h+var_1050], 1000h
0x18000a72c  mov     [rsp+1090h+var_104C], 0
0x18000a734  jnz     short loc_18000A77E
0x18000a736  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a73d  test    rax, rax
0x18000a740  jnz     short loc_18000A756
0x18000a742  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a749  call    cs:__imp_GetModuleHandleW
0x18000a74f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a756  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000a75d  mov     rcx, rax; hModule
0x18000a760  call    cs:__imp_GetProcAddress
0x18000a766  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000a76d  test    rax, rax
0x18000a770  jnz     short loc_18000A77E
0x18000a772  mov     edi, 0C0000139h
0x18000a777  mov     ebx, edi
0x18000a779  jmp     loc_18000A8AB
0x18000a77e  lea     rax, [rsp+1090h+var_1050]
0x18000a783  xor     r8d, r8d
0x18000a786  mov     [rsp+1090h+var_1068], rax
0x18000a78b  lea     r9, [rsp+1090h+var_104C]
0x18000a790  lea     rax, [rsp+1090h+var_1040]
0x18000a795  xor     edx, edx
0x18000a797  mov     [rsp+1090h+var_1070], rax
0x18000a79c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a7a3  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000a7aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7af  mov     ebx, eax
0x18000a7b1  mov     edi, eax
0x18000a7b3  test    eax, eax
0x18000a7b5  jnz     loc_18000A8AB
0x18000a7bb  mov     r9d, [rsp+1090h+var_1050]
0x18000a7c0  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000a7ca  mov     rax, r11
0x18000a7cd  mul     r9
0x18000a7d0  shr     rdx, 3
0x18000a7d4  lea     rcx, [rdx+rdx*2]
0x18000a7d8  shl     rcx, 2
0x18000a7dc  cmp     r9, rcx
0x18000a7df  jz      short loc_18000A7E9
0x18000a7e1  xor     r9d, r9d
0x18000a7e4  mov     [rsp+1090h+var_1050], r9d
0x18000a7e9  mov     r8, [r14]
0x18000a7ec  mov     rax, r11
0x18000a7ef  mov     ecx, r9d
0x18000a7f2  mul     rcx
0x18000a7f5  mov     rcx, [r14+8]
0x18000a7f9  mov     rax, r11
0x18000a7fc  mov     r10, rdx
0x18000a7ff  sub     rcx, r8
0x18000a802  mul     rcx
0x18000a805  shr     r10, 3
0x18000a809  shr     rdx, 3
0x18000a80d  lea     rax, [rdx+rdx*2]
0x18000a811  lea     rsi, [r8+rax*4]
0x18000a815  jmp     short loc_18000A880
0x18000a817  mov     eax, r10d
0x18000a81a  lea     rcx, [rax+rax*2]
0x18000a81e  lea     rdx, [rdx+rcx*4]
0x18000a822  lea     rax, [rsp+1090h+var_1040]
0x18000a827  cmp     rax, rdx
0x18000a82a  jz      short loc_18000A851
0x18000a82c  mov     r11d, [r8]
0x18000a82f  lea     rcx, [rsp+1090h+var_1040]
0x18000a834  cmp     [rcx], r11d
0x18000a837  jnz     short loc_18000A848
0x18000a839  movzx   eax, word ptr [r8+4]
0x18000a83e  cmp     [rcx+4], ax
0x18000a842  jz      loc_18000A8EA
0x18000a848  add     rcx, 0Ch
0x18000a84c  cmp     rcx, rdx
0x18000a84f  jnz     short loc_18000A834
0x18000a851  mov     eax, r9d
0x18000a854  add     rax, 0Ch
0x18000a858  cmp     rax, 1000h
0x18000a85e  ja      short loc_18000A87C
0x18000a860  movsd   xmm0, qword ptr [r8]
0x18000a865  add     r9d, 0Ch
0x18000a869  movsd   qword ptr [rdx], xmm0
0x18000a86d  inc     r10d
0x18000a870  mov     eax, [r8+8]
0x18000a874  mov     [rdx+8], eax
0x18000a877  mov     [rsp+1090h+var_1050], r9d
0x18000a87c  add     r8, 0Ch
0x18000a880  lea     rdx, [rsp+1090h+var_1040]
0x18000a885  cmp     r8, rsi
0x18000a888  jnz     short loc_18000A817
0x18000a88a  mov     eax, [rsp+1090h+var_104C]
0x18000a88e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a895  mov     [rsp+1090h+var_1060], 1
0x18000a89d  mov     r8d, r9d
0x18000a8a0  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000a8a4  call    wil_details_NtUpdateWnfStateData
0x18000a8a9  mov     esi, eax
0x18000a8ab  cmp     esi, 0C0000001h
0x18000a8b1  jnz     short loc_18000A8C4
0x18000a8b3  inc     r15d
0x18000a8b6  cmp     r15d, 64h ; 'd'
0x18000a8ba  jge     short loc_18000A8C4
0x18000a8bc  test    edi, edi
0x18000a8be  jz      loc_18000A70A
0x18000a8c4  test    ebx, ebx
0x18000a8c6  cmovz   ebx, esi
0x18000a8c9  mov     eax, ebx
0x18000a8cb  mov     rcx, [rbp+0F90h+var_40]
0x18000a8d2  xor     rcx, rsp; StackCookie
0x18000a8d5  call    __security_check_cookie
0x18000a8da  add     rsp, 1068h
0x18000a8e1  pop     r15
0x18000a8e3  pop     r14
0x18000a8e5  pop     rdi
0x18000a8e6  pop     rsi
0x18000a8e7  pop     rbx
0x18000a8e8  pop     rbp
0x18000a8e9  retn
0x18000a8ea  mov     eax, [r8+8]
0x18000a8ee  add     [rcx+8], eax
0x18000a8f1  mov     r9d, [rsp+1090h+var_1050]
0x18000a8f6  jmp     short loc_18000A87C
```
