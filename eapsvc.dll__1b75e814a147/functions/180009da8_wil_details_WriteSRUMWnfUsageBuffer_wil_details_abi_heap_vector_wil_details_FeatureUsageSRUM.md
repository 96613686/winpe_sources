# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180009da8`
- end: `0x180009fe0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002b70`

## callees

- `0x180001f60`
- `0x1800028dc`
- `0x180009da8`
- `0x18000a270`
- `0x180014e20`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009e48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009e48`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009e31`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009e31`

## string_xrefs

- `0x180009e2a`: `ntdll.dll`

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
0x180009da8  push    rbp
0x180009daa  push    rbx
0x180009dab  push    rsi
0x180009dac  push    rdi
0x180009dad  push    r14
0x180009daf  push    r15
0x180009db1  lea     rbp, [rsp-0F68h]
0x180009db9  mov     eax, 1068h
0x180009dbe  call    _alloca_probe
0x180009dc3  sub     rsp, rax
0x180009dc6  mov     rax, cs:__security_cookie
0x180009dcd  xor     rax, rsp
0x180009dd0  mov     [rbp+0F90h+var_40], rax
0x180009dd7  mov     rax, [rcx+8]
0x180009ddb  xor     ebx, ebx
0x180009ddd  sub     rax, [rcx]
0x180009de0  xor     esi, esi
0x180009de2  mov     r14, rcx
0x180009de5  cmp     rax, 0Ch
0x180009de9  jb      loc_180009FAC
0x180009def  xor     r15d, r15d
0x180009df2  xor     edx, edx; Val
0x180009df4  lea     rcx, [rsp+1090h+var_1040]; void *
0x180009df9  mov     r8d, 1000h; Size
0x180009dff  call    memset_0
0x180009e04  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180009e0c  mov     [rsp+1090h+var_1050], 1000h
0x180009e14  mov     [rsp+1090h+var_104C], 0
0x180009e1c  jnz     short loc_180009E66
0x180009e1e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009e25  test    rax, rax
0x180009e28  jnz     short loc_180009E3E
0x180009e2a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180009e31  call    cs:__imp_GetModuleHandleW
0x180009e37  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009e3e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180009e45  mov     rcx, rax; hModule
0x180009e48  call    cs:__imp_GetProcAddress
0x180009e4e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180009e55  test    rax, rax
0x180009e58  jnz     short loc_180009E66
0x180009e5a  mov     edi, 0C0000139h
0x180009e5f  mov     ebx, edi
0x180009e61  jmp     loc_180009F93
0x180009e66  lea     rax, [rsp+1090h+var_1050]
0x180009e6b  xor     r8d, r8d
0x180009e6e  mov     [rsp+1090h+var_1068], rax
0x180009e73  lea     r9, [rsp+1090h+var_104C]
0x180009e78  lea     rax, [rsp+1090h+var_1040]
0x180009e7d  xor     edx, edx
0x180009e7f  mov     [rsp+1090h+var_1070], rax
0x180009e84  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180009e8b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180009e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e97  mov     ebx, eax
0x180009e99  mov     edi, eax
0x180009e9b  test    eax, eax
0x180009e9d  jnz     loc_180009F93
0x180009ea3  mov     r9d, [rsp+1090h+var_1050]
0x180009ea8  mov     r11, 0AAAAAAAAAAAAAAABh
0x180009eb2  mov     rax, r11
0x180009eb5  mul     r9
0x180009eb8  shr     rdx, 3
0x180009ebc  lea     rcx, [rdx+rdx*2]
0x180009ec0  shl     rcx, 2
0x180009ec4  cmp     r9, rcx
0x180009ec7  jz      short loc_180009ED1
0x180009ec9  xor     r9d, r9d
0x180009ecc  mov     [rsp+1090h+var_1050], r9d
0x180009ed1  mov     r8, [r14]
0x180009ed4  mov     rax, r11
0x180009ed7  mov     ecx, r9d
0x180009eda  mul     rcx
0x180009edd  mov     rcx, [r14+8]
0x180009ee1  mov     rax, r11
0x180009ee4  mov     r10, rdx
0x180009ee7  sub     rcx, r8
0x180009eea  mul     rcx
0x180009eed  shr     r10, 3
0x180009ef1  shr     rdx, 3
0x180009ef5  lea     rax, [rdx+rdx*2]
0x180009ef9  lea     rsi, [r8+rax*4]
0x180009efd  jmp     short loc_180009F68
0x180009eff  mov     eax, r10d
0x180009f02  lea     rcx, [rax+rax*2]
0x180009f06  lea     rdx, [rdx+rcx*4]
0x180009f0a  lea     rax, [rsp+1090h+var_1040]
0x180009f0f  cmp     rax, rdx
0x180009f12  jz      short loc_180009F39
0x180009f14  mov     r11d, [r8]
0x180009f17  lea     rcx, [rsp+1090h+var_1040]
0x180009f1c  cmp     [rcx], r11d
0x180009f1f  jnz     short loc_180009F30
0x180009f21  movzx   eax, word ptr [r8+4]
0x180009f26  cmp     [rcx+4], ax
0x180009f2a  jz      loc_180009FD2
0x180009f30  add     rcx, 0Ch
0x180009f34  cmp     rcx, rdx
0x180009f37  jnz     short loc_180009F1C
0x180009f39  mov     eax, r9d
0x180009f3c  add     rax, 0Ch
0x180009f40  cmp     rax, 1000h
0x180009f46  ja      short loc_180009F64
0x180009f48  movsd   xmm0, qword ptr [r8]
0x180009f4d  add     r9d, 0Ch
0x180009f51  movsd   qword ptr [rdx], xmm0
0x180009f55  inc     r10d
0x180009f58  mov     eax, [r8+8]
0x180009f5c  mov     [rdx+8], eax
0x180009f5f  mov     [rsp+1090h+var_1050], r9d
0x180009f64  add     r8, 0Ch
0x180009f68  lea     rdx, [rsp+1090h+var_1040]
0x180009f6d  cmp     r8, rsi
0x180009f70  jnz     short loc_180009EFF
0x180009f72  mov     eax, [rsp+1090h+var_104C]
0x180009f76  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180009f7d  mov     [rsp+1090h+var_1060], 1
0x180009f85  mov     r8d, r9d
0x180009f88  mov     dword ptr [rsp+1090h+var_1068], eax
0x180009f8c  call    wil_details_NtUpdateWnfStateData
0x180009f91  mov     esi, eax
0x180009f93  cmp     esi, 0C0000001h
0x180009f99  jnz     short loc_180009FAC
0x180009f9b  inc     r15d
0x180009f9e  cmp     r15d, 64h ; 'd'
0x180009fa2  jge     short loc_180009FAC
0x180009fa4  test    edi, edi
0x180009fa6  jz      loc_180009DF2
0x180009fac  test    ebx, ebx
0x180009fae  cmovz   ebx, esi
0x180009fb1  mov     eax, ebx
0x180009fb3  mov     rcx, [rbp+0F90h+var_40]
0x180009fba  xor     rcx, rsp; StackCookie
0x180009fbd  call    __security_check_cookie
0x180009fc2  add     rsp, 1068h
0x180009fc9  pop     r15
0x180009fcb  pop     r14
0x180009fcd  pop     rdi
0x180009fce  pop     rsi
0x180009fcf  pop     rbx
0x180009fd0  pop     rbp
0x180009fd1  retn
0x180009fd2  mov     eax, [r8+8]
0x180009fd6  add     [rcx+8], eax
0x180009fd9  mov     r9d, [rsp+1090h+var_1050]
0x180009fde  jmp     short loc_180009F64
```
