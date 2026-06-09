# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000a5b8`
- end: `0x14000a7f0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140002f40`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x14000a5b8`
- `0x14000ad60`
- `0x1400a7290`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a641`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a641`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a658`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a658`

## string_xrefs

- `0x14000a63a`: `ntdll.dll`

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
0x14000a5b8  push    rbp
0x14000a5ba  push    rbx
0x14000a5bb  push    rsi
0x14000a5bc  push    rdi
0x14000a5bd  push    r14
0x14000a5bf  push    r15
0x14000a5c1  lea     rbp, [rsp-0F68h]
0x14000a5c9  mov     eax, 1068h
0x14000a5ce  call    _alloca_probe
0x14000a5d3  sub     rsp, rax
0x14000a5d6  mov     rax, cs:__security_cookie
0x14000a5dd  xor     rax, rsp
0x14000a5e0  mov     [rbp+0F90h+var_40], rax
0x14000a5e7  mov     rax, [rcx+8]
0x14000a5eb  xor     ebx, ebx
0x14000a5ed  sub     rax, [rcx]
0x14000a5f0  xor     esi, esi
0x14000a5f2  mov     r14, rcx
0x14000a5f5  cmp     rax, 0Ch
0x14000a5f9  jb      loc_14000A7BC
0x14000a5ff  xor     r15d, r15d
0x14000a602  xor     edx, edx; Val
0x14000a604  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000a609  mov     r8d, 1000h; Size
0x14000a60f  call    memset_0
0x14000a614  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000a61c  mov     [rsp+1090h+var_1050], 1000h
0x14000a624  mov     [rsp+1090h+var_104C], 0
0x14000a62c  jnz     short loc_14000A676
0x14000a62e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a635  test    rax, rax
0x14000a638  jnz     short loc_14000A64E
0x14000a63a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000a641  call    cs:__imp_GetModuleHandleW
0x14000a647  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a64e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000a655  mov     rcx, rax; hModule
0x14000a658  call    cs:__imp_GetProcAddress
0x14000a65e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000a665  test    rax, rax
0x14000a668  jnz     short loc_14000A676
0x14000a66a  mov     edi, 0C0000139h
0x14000a66f  mov     ebx, edi
0x14000a671  jmp     loc_14000A7A3
0x14000a676  lea     rax, [rsp+1090h+var_1050]
0x14000a67b  xor     r8d, r8d
0x14000a67e  mov     [rsp+1090h+var_1068], rax
0x14000a683  lea     r9, [rsp+1090h+var_104C]
0x14000a688  lea     rax, [rsp+1090h+var_1040]
0x14000a68d  xor     edx, edx
0x14000a68f  mov     [rsp+1090h+var_1070], rax
0x14000a694  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000a69b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000a6a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a6a7  mov     ebx, eax
0x14000a6a9  mov     edi, eax
0x14000a6ab  test    eax, eax
0x14000a6ad  jnz     loc_14000A7A3
0x14000a6b3  mov     r9d, [rsp+1090h+var_1050]
0x14000a6b8  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000a6c2  mov     rax, r11
0x14000a6c5  mul     r9
0x14000a6c8  shr     rdx, 3
0x14000a6cc  lea     rcx, [rdx+rdx*2]
0x14000a6d0  shl     rcx, 2
0x14000a6d4  cmp     r9, rcx
0x14000a6d7  jz      short loc_14000A6E1
0x14000a6d9  xor     r9d, r9d
0x14000a6dc  mov     [rsp+1090h+var_1050], r9d
0x14000a6e1  mov     r8, [r14]
0x14000a6e4  mov     rax, r11
0x14000a6e7  mov     ecx, r9d
0x14000a6ea  mul     rcx
0x14000a6ed  mov     rcx, [r14+8]
0x14000a6f1  mov     rax, r11
0x14000a6f4  mov     r10, rdx
0x14000a6f7  sub     rcx, r8
0x14000a6fa  mul     rcx
0x14000a6fd  shr     r10, 3
0x14000a701  shr     rdx, 3
0x14000a705  lea     rax, [rdx+rdx*2]
0x14000a709  lea     rsi, [r8+rax*4]
0x14000a70d  jmp     short loc_14000A778
0x14000a70f  mov     eax, r10d
0x14000a712  lea     rcx, [rax+rax*2]
0x14000a716  lea     rdx, [rdx+rcx*4]
0x14000a71a  lea     rax, [rsp+1090h+var_1040]
0x14000a71f  cmp     rax, rdx
0x14000a722  jz      short loc_14000A749
0x14000a724  mov     r11d, [r8]
0x14000a727  lea     rcx, [rsp+1090h+var_1040]
0x14000a72c  cmp     [rcx], r11d
0x14000a72f  jnz     short loc_14000A740
0x14000a731  movzx   eax, word ptr [r8+4]
0x14000a736  cmp     [rcx+4], ax
0x14000a73a  jz      loc_14000A7E2
0x14000a740  add     rcx, 0Ch
0x14000a744  cmp     rcx, rdx
0x14000a747  jnz     short loc_14000A72C
0x14000a749  mov     eax, r9d
0x14000a74c  add     rax, 0Ch
0x14000a750  cmp     rax, 1000h
0x14000a756  ja      short loc_14000A774
0x14000a758  movsd   xmm0, qword ptr [r8]
0x14000a75d  add     r9d, 0Ch
0x14000a761  movsd   qword ptr [rdx], xmm0
0x14000a765  inc     r10d
0x14000a768  mov     eax, [r8+8]
0x14000a76c  mov     [rdx+8], eax
0x14000a76f  mov     [rsp+1090h+var_1050], r9d
0x14000a774  add     r8, 0Ch
0x14000a778  lea     rdx, [rsp+1090h+var_1040]
0x14000a77d  cmp     r8, rsi
0x14000a780  jnz     short loc_14000A70F
0x14000a782  mov     eax, [rsp+1090h+var_104C]
0x14000a786  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000a78d  mov     [rsp+1090h+var_1060], 1
0x14000a795  mov     r8d, r9d
0x14000a798  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000a79c  call    wil_details_NtUpdateWnfStateData
0x14000a7a1  mov     esi, eax
0x14000a7a3  cmp     esi, 0C0000001h
0x14000a7a9  jnz     short loc_14000A7BC
0x14000a7ab  inc     r15d
0x14000a7ae  cmp     r15d, 64h ; 'd'
0x14000a7b2  jge     short loc_14000A7BC
0x14000a7b4  test    edi, edi
0x14000a7b6  jz      loc_14000A602
0x14000a7bc  test    ebx, ebx
0x14000a7be  cmovz   ebx, esi
0x14000a7c1  mov     eax, ebx
0x14000a7c3  mov     rcx, [rbp+0F90h+var_40]
0x14000a7ca  xor     rcx, rsp; StackCookie
0x14000a7cd  call    __security_check_cookie
0x14000a7d2  add     rsp, 1068h
0x14000a7d9  pop     r15
0x14000a7db  pop     r14
0x14000a7dd  pop     rdi
0x14000a7de  pop     rsi
0x14000a7df  pop     rbx
0x14000a7e0  pop     rbp
0x14000a7e1  retn
0x14000a7e2  mov     eax, [r8+8]
0x14000a7e6  add     [rcx+8], eax
0x14000a7e9  mov     r9d, [rsp+1090h+var_1050]
0x14000a7ee  jmp     short loc_14000A774
```
