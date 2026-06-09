# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000f6a8`
- end: `0x18000f8e0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800034b0`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x1800033d0`
- `0x18000f6a8`
- `0x18001064c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000f748`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000f748`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000f731`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000f731`

## string_xrefs

- `0x18000f72a`: `ntdll.dll`

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
0x18000f6a8  push    rbp
0x18000f6aa  push    rbx
0x18000f6ab  push    rsi
0x18000f6ac  push    rdi
0x18000f6ad  push    r14
0x18000f6af  push    r15
0x18000f6b1  lea     rbp, [rsp-0F68h]
0x18000f6b9  mov     eax, 1068h
0x18000f6be  call    _alloca_probe
0x18000f6c3  sub     rsp, rax
0x18000f6c6  mov     rax, cs:__security_cookie
0x18000f6cd  xor     rax, rsp
0x18000f6d0  mov     [rbp+0F90h+var_40], rax
0x18000f6d7  mov     rax, [rcx+8]
0x18000f6db  xor     ebx, ebx
0x18000f6dd  sub     rax, [rcx]
0x18000f6e0  xor     esi, esi
0x18000f6e2  mov     r14, rcx
0x18000f6e5  cmp     rax, 0Ch
0x18000f6e9  jb      loc_18000F8AC
0x18000f6ef  xor     r15d, r15d
0x18000f6f2  xor     edx, edx; Val
0x18000f6f4  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000f6f9  mov     r8d, 1000h; Size
0x18000f6ff  call    memset_0
0x18000f704  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000f70c  mov     [rsp+1090h+var_1050], 1000h
0x18000f714  mov     [rsp+1090h+var_104C], 0
0x18000f71c  jnz     short loc_18000F766
0x18000f71e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f725  test    rax, rax
0x18000f728  jnz     short loc_18000F73E
0x18000f72a  lea     rcx, ModuleName; "ntdll.dll"
0x18000f731  call    cs:__imp_GetModuleHandleW
0x18000f737  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f73e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000f745  mov     rcx, rax; hModule
0x18000f748  call    cs:__imp_GetProcAddress
0x18000f74e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000f755  test    rax, rax
0x18000f758  jnz     short loc_18000F766
0x18000f75a  mov     edi, 0C0000139h
0x18000f75f  mov     ebx, edi
0x18000f761  jmp     loc_18000F893
0x18000f766  lea     rax, [rsp+1090h+var_1050]
0x18000f76b  xor     r8d, r8d
0x18000f76e  mov     [rsp+1090h+var_1068], rax
0x18000f773  lea     r9, [rsp+1090h+var_104C]
0x18000f778  lea     rax, [rsp+1090h+var_1040]
0x18000f77d  xor     edx, edx
0x18000f77f  mov     [rsp+1090h+var_1070], rax
0x18000f784  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000f78b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000f792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f797  mov     ebx, eax
0x18000f799  mov     edi, eax
0x18000f79b  test    eax, eax
0x18000f79d  jnz     loc_18000F893
0x18000f7a3  mov     r9d, [rsp+1090h+var_1050]
0x18000f7a8  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000f7b2  mov     rax, r11
0x18000f7b5  mul     r9
0x18000f7b8  shr     rdx, 3
0x18000f7bc  lea     rcx, [rdx+rdx*2]
0x18000f7c0  shl     rcx, 2
0x18000f7c4  cmp     r9, rcx
0x18000f7c7  jz      short loc_18000F7D1
0x18000f7c9  xor     r9d, r9d
0x18000f7cc  mov     [rsp+1090h+var_1050], r9d
0x18000f7d1  mov     r8, [r14]
0x18000f7d4  mov     rax, r11
0x18000f7d7  mov     ecx, r9d
0x18000f7da  mul     rcx
0x18000f7dd  mov     rcx, [r14+8]
0x18000f7e1  mov     rax, r11
0x18000f7e4  mov     r10, rdx
0x18000f7e7  sub     rcx, r8
0x18000f7ea  mul     rcx
0x18000f7ed  shr     r10, 3
0x18000f7f1  shr     rdx, 3
0x18000f7f5  lea     rax, [rdx+rdx*2]
0x18000f7f9  lea     rsi, [r8+rax*4]
0x18000f7fd  jmp     short loc_18000F868
0x18000f7ff  mov     eax, r10d
0x18000f802  lea     rcx, [rax+rax*2]
0x18000f806  lea     rdx, [rdx+rcx*4]
0x18000f80a  lea     rax, [rsp+1090h+var_1040]
0x18000f80f  cmp     rax, rdx
0x18000f812  jz      short loc_18000F839
0x18000f814  mov     r11d, [r8]
0x18000f817  lea     rcx, [rsp+1090h+var_1040]
0x18000f81c  cmp     [rcx], r11d
0x18000f81f  jnz     short loc_18000F830
0x18000f821  movzx   eax, word ptr [r8+4]
0x18000f826  cmp     [rcx+4], ax
0x18000f82a  jz      loc_18000F8D2
0x18000f830  add     rcx, 0Ch
0x18000f834  cmp     rcx, rdx
0x18000f837  jnz     short loc_18000F81C
0x18000f839  mov     eax, r9d
0x18000f83c  add     rax, 0Ch
0x18000f840  cmp     rax, 1000h
0x18000f846  ja      short loc_18000F864
0x18000f848  movsd   xmm0, qword ptr [r8]
0x18000f84d  add     r9d, 0Ch
0x18000f851  movsd   qword ptr [rdx], xmm0
0x18000f855  inc     r10d
0x18000f858  mov     eax, [r8+8]
0x18000f85c  mov     [rdx+8], eax
0x18000f85f  mov     [rsp+1090h+var_1050], r9d
0x18000f864  add     r8, 0Ch
0x18000f868  lea     rdx, [rsp+1090h+var_1040]
0x18000f86d  cmp     r8, rsi
0x18000f870  jnz     short loc_18000F7FF
0x18000f872  mov     eax, [rsp+1090h+var_104C]
0x18000f876  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000f87d  mov     [rsp+1090h+var_1060], 1
0x18000f885  mov     r8d, r9d
0x18000f888  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000f88c  call    wil_details_NtUpdateWnfStateData
0x18000f891  mov     esi, eax
0x18000f893  cmp     esi, 0C0000001h
0x18000f899  jnz     short loc_18000F8AC
0x18000f89b  inc     r15d
0x18000f89e  cmp     r15d, 64h ; 'd'
0x18000f8a2  jge     short loc_18000F8AC
0x18000f8a4  test    edi, edi
0x18000f8a6  jz      loc_18000F6F2
0x18000f8ac  test    ebx, ebx
0x18000f8ae  cmovz   ebx, esi
0x18000f8b1  mov     eax, ebx
0x18000f8b3  mov     rcx, [rbp+0F90h+var_40]
0x18000f8ba  xor     rcx, rsp; StackCookie
0x18000f8bd  call    __security_check_cookie
0x18000f8c2  add     rsp, 1068h
0x18000f8c9  pop     r15
0x18000f8cb  pop     r14
0x18000f8cd  pop     rdi
0x18000f8ce  pop     rsi
0x18000f8cf  pop     rbx
0x18000f8d0  pop     rbp
0x18000f8d1  retn
0x18000f8d2  mov     eax, [r8+8]
0x18000f8d6  add     [rcx+8], eax
0x18000f8d9  mov     r9d, [rsp+1090h+var_1050]
0x18000f8de  jmp     short loc_18000F864
```
