# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000d210`
- end: `0x18000d448`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800073d0`

## callees

- `0x18000d210`
- `0x18000d734`
- `0x180015cbe`
- `0x180015cf0`
- `0x180015db0`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000d299`
- `KERNEL32!GetModuleHandleW` at `0x18000d299`
- `KERNEL32!GetProcAddress` at `0x18000d2b0`
- `KERNEL32!GetProcAddress` at `0x18000d2b0`

## string_xrefs

- `0x18000d292`: `ntdll.dll`

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
0x18000d210  push    rbp
0x18000d212  push    rbx
0x18000d213  push    rsi
0x18000d214  push    rdi
0x18000d215  push    r14
0x18000d217  push    r15
0x18000d219  lea     rbp, [rsp-0F68h]
0x18000d221  mov     eax, 1068h
0x18000d226  call    _alloca_probe
0x18000d22b  sub     rsp, rax
0x18000d22e  mov     rax, cs:__security_cookie
0x18000d235  xor     rax, rsp
0x18000d238  mov     [rbp+0F90h+var_40], rax
0x18000d23f  mov     rax, [rcx+8]
0x18000d243  xor     ebx, ebx
0x18000d245  sub     rax, [rcx]
0x18000d248  xor     esi, esi
0x18000d24a  mov     r14, rcx
0x18000d24d  cmp     rax, 0Ch
0x18000d251  jb      loc_18000D414
0x18000d257  xor     r15d, r15d
0x18000d25a  xor     edx, edx; Val
0x18000d25c  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000d261  mov     r8d, 1000h; Size
0x18000d267  call    memset_0
0x18000d26c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000d274  mov     [rsp+1090h+var_1050], 1000h
0x18000d27c  mov     [rsp+1090h+var_104C], 0
0x18000d284  jnz     short loc_18000D2CE
0x18000d286  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d28d  test    rax, rax
0x18000d290  jnz     short loc_18000D2A6
0x18000d292  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000d299  call    cs:__imp_GetModuleHandleW
0x18000d29f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d2a6  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000d2ad  mov     rcx, rax; hModule
0x18000d2b0  call    cs:__imp_GetProcAddress
0x18000d2b6  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000d2bd  test    rax, rax
0x18000d2c0  jnz     short loc_18000D2CE
0x18000d2c2  mov     edi, 0C0000139h
0x18000d2c7  mov     ebx, edi
0x18000d2c9  jmp     loc_18000D3FB
0x18000d2ce  lea     rax, [rsp+1090h+var_1050]
0x18000d2d3  xor     r8d, r8d
0x18000d2d6  mov     [rsp+1090h+var_1068], rax
0x18000d2db  lea     r9, [rsp+1090h+var_104C]
0x18000d2e0  lea     rax, [rsp+1090h+var_1040]
0x18000d2e5  xor     edx, edx
0x18000d2e7  mov     [rsp+1090h+var_1070], rax
0x18000d2ec  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d2f3  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000d2fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2ff  mov     ebx, eax
0x18000d301  mov     edi, eax
0x18000d303  test    eax, eax
0x18000d305  jnz     loc_18000D3FB
0x18000d30b  mov     r9d, [rsp+1090h+var_1050]
0x18000d310  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000d31a  mov     rax, r11
0x18000d31d  mul     r9
0x18000d320  shr     rdx, 3
0x18000d324  lea     rcx, [rdx+rdx*2]
0x18000d328  shl     rcx, 2
0x18000d32c  cmp     r9, rcx
0x18000d32f  jz      short loc_18000D339
0x18000d331  xor     r9d, r9d
0x18000d334  mov     [rsp+1090h+var_1050], r9d
0x18000d339  mov     r8, [r14]
0x18000d33c  mov     rax, r11
0x18000d33f  mov     ecx, r9d
0x18000d342  mul     rcx
0x18000d345  mov     rcx, [r14+8]
0x18000d349  mov     rax, r11
0x18000d34c  mov     r10, rdx
0x18000d34f  sub     rcx, r8
0x18000d352  mul     rcx
0x18000d355  shr     r10, 3
0x18000d359  shr     rdx, 3
0x18000d35d  lea     rax, [rdx+rdx*2]
0x18000d361  lea     rsi, [r8+rax*4]
0x18000d365  jmp     short loc_18000D3D0
0x18000d367  mov     eax, r10d
0x18000d36a  lea     rcx, [rax+rax*2]
0x18000d36e  lea     rdx, [rdx+rcx*4]
0x18000d372  lea     rax, [rsp+1090h+var_1040]
0x18000d377  cmp     rax, rdx
0x18000d37a  jz      short loc_18000D3A1
0x18000d37c  mov     r11d, [r8]
0x18000d37f  lea     rcx, [rsp+1090h+var_1040]
0x18000d384  cmp     [rcx], r11d
0x18000d387  jnz     short loc_18000D398
0x18000d389  movzx   eax, word ptr [r8+4]
0x18000d38e  cmp     [rcx+4], ax
0x18000d392  jz      loc_18000D43A
0x18000d398  add     rcx, 0Ch
0x18000d39c  cmp     rcx, rdx
0x18000d39f  jnz     short loc_18000D384
0x18000d3a1  mov     eax, r9d
0x18000d3a4  add     rax, 0Ch
0x18000d3a8  cmp     rax, 1000h
0x18000d3ae  ja      short loc_18000D3CC
0x18000d3b0  movsd   xmm0, qword ptr [r8]
0x18000d3b5  add     r9d, 0Ch
0x18000d3b9  movsd   qword ptr [rdx], xmm0
0x18000d3bd  inc     r10d
0x18000d3c0  mov     eax, [r8+8]
0x18000d3c4  mov     [rdx+8], eax
0x18000d3c7  mov     [rsp+1090h+var_1050], r9d
0x18000d3cc  add     r8, 0Ch
0x18000d3d0  lea     rdx, [rsp+1090h+var_1040]
0x18000d3d5  cmp     r8, rsi
0x18000d3d8  jnz     short loc_18000D367
0x18000d3da  mov     eax, [rsp+1090h+var_104C]
0x18000d3de  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d3e5  mov     [rsp+1090h+var_1060], 1
0x18000d3ed  mov     r8d, r9d
0x18000d3f0  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000d3f4  call    wil_details_NtUpdateWnfStateData
0x18000d3f9  mov     esi, eax
0x18000d3fb  cmp     esi, 0C0000001h
0x18000d401  jnz     short loc_18000D414
0x18000d403  inc     r15d
0x18000d406  cmp     r15d, 64h ; 'd'
0x18000d40a  jge     short loc_18000D414
0x18000d40c  test    edi, edi
0x18000d40e  jz      loc_18000D25A
0x18000d414  test    ebx, ebx
0x18000d416  cmovz   ebx, esi
0x18000d419  mov     eax, ebx
0x18000d41b  mov     rcx, [rbp+0F90h+var_40]
0x18000d422  xor     rcx, rsp; StackCookie
0x18000d425  call    __security_check_cookie
0x18000d42a  add     rsp, 1068h
0x18000d431  pop     r15
0x18000d433  pop     r14
0x18000d435  pop     rdi
0x18000d436  pop     rsi
0x18000d437  pop     rbx
0x18000d438  pop     rbp
0x18000d439  retn
0x18000d43a  mov     eax, [r8+8]
0x18000d43e  add     [rcx+8], eax
0x18000d441  mov     r9d, [rsp+1090h+var_1050]
0x18000d446  jmp     short loc_18000D3CC
```
