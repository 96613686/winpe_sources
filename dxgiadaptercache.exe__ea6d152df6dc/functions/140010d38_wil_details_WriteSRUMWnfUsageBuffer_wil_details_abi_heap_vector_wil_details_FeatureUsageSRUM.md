# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140010d38`
- end: `0x140010f70`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140003280`

## callees

- `0x1400022a0`
- `0x140002d4c`
- `0x140010d38`
- `0x140011008`
- `0x1400113b0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010dd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010dd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140010dc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140010dc1`

## string_xrefs

- `0x140010dba`: `ntdll.dll`

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
0x140010d38  push    rbp
0x140010d3a  push    rbx
0x140010d3b  push    rsi
0x140010d3c  push    rdi
0x140010d3d  push    r14
0x140010d3f  push    r15
0x140010d41  lea     rbp, [rsp-0F68h]
0x140010d49  mov     eax, 1068h
0x140010d4e  call    _alloca_probe
0x140010d53  sub     rsp, rax
0x140010d56  mov     rax, cs:__security_cookie
0x140010d5d  xor     rax, rsp
0x140010d60  mov     [rbp+0F90h+var_40], rax
0x140010d67  mov     rax, [rcx+8]
0x140010d6b  xor     ebx, ebx
0x140010d6d  sub     rax, [rcx]
0x140010d70  xor     esi, esi
0x140010d72  mov     r14, rcx
0x140010d75  cmp     rax, 0Ch
0x140010d79  jb      loc_140010F3C
0x140010d7f  xor     r15d, r15d
0x140010d82  xor     edx, edx; Val
0x140010d84  lea     rcx, [rsp+1090h+var_1040]; void *
0x140010d89  mov     r8d, 1000h; Size
0x140010d8f  call    memset_0
0x140010d94  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x140010d9c  mov     [rsp+1090h+var_1050], 1000h
0x140010da4  mov     [rsp+1090h+var_104C], 0
0x140010dac  jnz     short loc_140010DF6
0x140010dae  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140010db5  test    rax, rax
0x140010db8  jnz     short loc_140010DCE
0x140010dba  lea     rcx, ModuleName; "ntdll.dll"
0x140010dc1  call    cs:__imp_GetModuleHandleW
0x140010dc7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140010dce  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140010dd5  mov     rcx, rax; hModule
0x140010dd8  call    cs:__imp_GetProcAddress
0x140010dde  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140010de5  test    rax, rax
0x140010de8  jnz     short loc_140010DF6
0x140010dea  mov     edi, 0C0000139h
0x140010def  mov     ebx, edi
0x140010df1  jmp     loc_140010F23
0x140010df6  lea     rax, [rsp+1090h+var_1050]
0x140010dfb  xor     r8d, r8d
0x140010dfe  mov     [rsp+1090h+var_1068], rax
0x140010e03  lea     r9, [rsp+1090h+var_104C]
0x140010e08  lea     rax, [rsp+1090h+var_1040]
0x140010e0d  xor     edx, edx
0x140010e0f  mov     [rsp+1090h+var_1070], rax
0x140010e14  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140010e1b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140010e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e27  mov     ebx, eax
0x140010e29  mov     edi, eax
0x140010e2b  test    eax, eax
0x140010e2d  jnz     loc_140010F23
0x140010e33  mov     r9d, [rsp+1090h+var_1050]
0x140010e38  mov     r11, 0AAAAAAAAAAAAAAABh
0x140010e42  mov     rax, r11
0x140010e45  mul     r9
0x140010e48  shr     rdx, 3
0x140010e4c  lea     rcx, [rdx+rdx*2]
0x140010e50  shl     rcx, 2
0x140010e54  cmp     r9, rcx
0x140010e57  jz      short loc_140010E61
0x140010e59  xor     r9d, r9d
0x140010e5c  mov     [rsp+1090h+var_1050], r9d
0x140010e61  mov     r8, [r14]
0x140010e64  mov     rax, r11
0x140010e67  mov     ecx, r9d
0x140010e6a  mul     rcx
0x140010e6d  mov     rcx, [r14+8]
0x140010e71  mov     rax, r11
0x140010e74  mov     r10, rdx
0x140010e77  sub     rcx, r8
0x140010e7a  mul     rcx
0x140010e7d  shr     r10, 3
0x140010e81  shr     rdx, 3
0x140010e85  lea     rax, [rdx+rdx*2]
0x140010e89  lea     rsi, [r8+rax*4]
0x140010e8d  jmp     short loc_140010EF8
0x140010e8f  mov     eax, r10d
0x140010e92  lea     rcx, [rax+rax*2]
0x140010e96  lea     rdx, [rdx+rcx*4]
0x140010e9a  lea     rax, [rsp+1090h+var_1040]
0x140010e9f  cmp     rax, rdx
0x140010ea2  jz      short loc_140010EC9
0x140010ea4  mov     r11d, [r8]
0x140010ea7  lea     rcx, [rsp+1090h+var_1040]
0x140010eac  cmp     [rcx], r11d
0x140010eaf  jnz     short loc_140010EC0
0x140010eb1  movzx   eax, word ptr [r8+4]
0x140010eb6  cmp     [rcx+4], ax
0x140010eba  jz      loc_140010F62
0x140010ec0  add     rcx, 0Ch
0x140010ec4  cmp     rcx, rdx
0x140010ec7  jnz     short loc_140010EAC
0x140010ec9  mov     eax, r9d
0x140010ecc  add     rax, 0Ch
0x140010ed0  cmp     rax, 1000h
0x140010ed6  ja      short loc_140010EF4
0x140010ed8  movsd   xmm0, qword ptr [r8]
0x140010edd  add     r9d, 0Ch
0x140010ee1  movsd   qword ptr [rdx], xmm0
0x140010ee5  inc     r10d
0x140010ee8  mov     eax, [r8+8]
0x140010eec  mov     [rdx+8], eax
0x140010eef  mov     [rsp+1090h+var_1050], r9d
0x140010ef4  add     r8, 0Ch
0x140010ef8  lea     rdx, [rsp+1090h+var_1040]
0x140010efd  cmp     r8, rsi
0x140010f00  jnz     short loc_140010E8F
0x140010f02  mov     eax, [rsp+1090h+var_104C]
0x140010f06  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140010f0d  mov     [rsp+1090h+var_1060], 1
0x140010f15  mov     r8d, r9d
0x140010f18  mov     dword ptr [rsp+1090h+var_1068], eax
0x140010f1c  call    wil_details_NtUpdateWnfStateData
0x140010f21  mov     esi, eax
0x140010f23  cmp     esi, 0C0000001h
0x140010f29  jnz     short loc_140010F3C
0x140010f2b  inc     r15d
0x140010f2e  cmp     r15d, 64h ; 'd'
0x140010f32  jge     short loc_140010F3C
0x140010f34  test    edi, edi
0x140010f36  jz      loc_140010D82
0x140010f3c  test    ebx, ebx
0x140010f3e  cmovz   ebx, esi
0x140010f41  mov     eax, ebx
0x140010f43  mov     rcx, [rbp+0F90h+var_40]
0x140010f4a  xor     rcx, rsp; StackCookie
0x140010f4d  call    __security_check_cookie
0x140010f52  add     rsp, 1068h
0x140010f59  pop     r15
0x140010f5b  pop     r14
0x140010f5d  pop     rdi
0x140010f5e  pop     rsi
0x140010f5f  pop     rbx
0x140010f60  pop     rbp
0x140010f61  retn
0x140010f62  mov     eax, [r8+8]
0x140010f66  add     [rcx+8], eax
0x140010f69  mov     r9d, [rsp+1090h+var_1050]
0x140010f6e  jmp     short loc_140010EF4
```
