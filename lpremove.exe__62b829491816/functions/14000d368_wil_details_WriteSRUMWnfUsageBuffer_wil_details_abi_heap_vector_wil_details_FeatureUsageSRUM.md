# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000d368`
- end: `0x14000d5a0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140003410`

## callees

- `0x140002190`
- `0x140002c2c`
- `0x14000d368`
- `0x14000d808`
- `0x14000fe00`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000d3f1`
- `KERNEL32!GetModuleHandleW` at `0x14000d3f1`
- `KERNEL32!GetProcAddress` at `0x14000d408`
- `KERNEL32!GetProcAddress` at `0x14000d408`

## string_xrefs

- `0x14000d3ea`: `ntdll.dll`

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
0x14000d368  push    rbp
0x14000d36a  push    rbx
0x14000d36b  push    rsi
0x14000d36c  push    rdi
0x14000d36d  push    r14
0x14000d36f  push    r15
0x14000d371  lea     rbp, [rsp-0F68h]
0x14000d379  mov     eax, 1068h
0x14000d37e  call    _alloca_probe
0x14000d383  sub     rsp, rax
0x14000d386  mov     rax, cs:__security_cookie
0x14000d38d  xor     rax, rsp
0x14000d390  mov     [rbp+0F90h+var_40], rax
0x14000d397  mov     rax, [rcx+8]
0x14000d39b  xor     ebx, ebx
0x14000d39d  sub     rax, [rcx]
0x14000d3a0  xor     esi, esi
0x14000d3a2  mov     r14, rcx
0x14000d3a5  cmp     rax, 0Ch
0x14000d3a9  jb      loc_14000D56C
0x14000d3af  xor     r15d, r15d
0x14000d3b2  xor     edx, edx; Val
0x14000d3b4  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000d3b9  mov     r8d, 1000h; Size
0x14000d3bf  call    memset_0
0x14000d3c4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000d3cc  mov     [rsp+1090h+var_1050], 1000h
0x14000d3d4  mov     [rsp+1090h+var_104C], 0
0x14000d3dc  jnz     short loc_14000D426
0x14000d3de  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d3e5  test    rax, rax
0x14000d3e8  jnz     short loc_14000D3FE
0x14000d3ea  lea     rcx, ModuleName; "ntdll.dll"
0x14000d3f1  call    cs:__imp_GetModuleHandleW
0x14000d3f7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d3fe  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000d405  mov     rcx, rax; hModule
0x14000d408  call    cs:__imp_GetProcAddress
0x14000d40e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000d415  test    rax, rax
0x14000d418  jnz     short loc_14000D426
0x14000d41a  mov     edi, 0C0000139h
0x14000d41f  mov     ebx, edi
0x14000d421  jmp     loc_14000D553
0x14000d426  lea     rax, [rsp+1090h+var_1050]
0x14000d42b  xor     r8d, r8d
0x14000d42e  mov     [rsp+1090h+var_1068], rax
0x14000d433  lea     r9, [rsp+1090h+var_104C]
0x14000d438  lea     rax, [rsp+1090h+var_1040]
0x14000d43d  xor     edx, edx
0x14000d43f  mov     [rsp+1090h+var_1070], rax
0x14000d444  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000d44b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000d452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d457  mov     ebx, eax
0x14000d459  mov     edi, eax
0x14000d45b  test    eax, eax
0x14000d45d  jnz     loc_14000D553
0x14000d463  mov     r9d, [rsp+1090h+var_1050]
0x14000d468  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000d472  mov     rax, r11
0x14000d475  mul     r9
0x14000d478  shr     rdx, 3
0x14000d47c  lea     rcx, [rdx+rdx*2]
0x14000d480  shl     rcx, 2
0x14000d484  cmp     r9, rcx
0x14000d487  jz      short loc_14000D491
0x14000d489  xor     r9d, r9d
0x14000d48c  mov     [rsp+1090h+var_1050], r9d
0x14000d491  mov     r8, [r14]
0x14000d494  mov     rax, r11
0x14000d497  mov     ecx, r9d
0x14000d49a  mul     rcx
0x14000d49d  mov     rcx, [r14+8]
0x14000d4a1  mov     rax, r11
0x14000d4a4  mov     r10, rdx
0x14000d4a7  sub     rcx, r8
0x14000d4aa  mul     rcx
0x14000d4ad  shr     r10, 3
0x14000d4b1  shr     rdx, 3
0x14000d4b5  lea     rax, [rdx+rdx*2]
0x14000d4b9  lea     rsi, [r8+rax*4]
0x14000d4bd  jmp     short loc_14000D528
0x14000d4bf  mov     eax, r10d
0x14000d4c2  lea     rcx, [rax+rax*2]
0x14000d4c6  lea     rdx, [rdx+rcx*4]
0x14000d4ca  lea     rax, [rsp+1090h+var_1040]
0x14000d4cf  cmp     rax, rdx
0x14000d4d2  jz      short loc_14000D4F9
0x14000d4d4  mov     r11d, [r8]
0x14000d4d7  lea     rcx, [rsp+1090h+var_1040]
0x14000d4dc  cmp     [rcx], r11d
0x14000d4df  jnz     short loc_14000D4F0
0x14000d4e1  movzx   eax, word ptr [r8+4]
0x14000d4e6  cmp     [rcx+4], ax
0x14000d4ea  jz      loc_14000D592
0x14000d4f0  add     rcx, 0Ch
0x14000d4f4  cmp     rcx, rdx
0x14000d4f7  jnz     short loc_14000D4DC
0x14000d4f9  mov     eax, r9d
0x14000d4fc  add     rax, 0Ch
0x14000d500  cmp     rax, 1000h
0x14000d506  ja      short loc_14000D524
0x14000d508  movsd   xmm0, qword ptr [r8]
0x14000d50d  add     r9d, 0Ch
0x14000d511  movsd   qword ptr [rdx], xmm0
0x14000d515  inc     r10d
0x14000d518  mov     eax, [r8+8]
0x14000d51c  mov     [rdx+8], eax
0x14000d51f  mov     [rsp+1090h+var_1050], r9d
0x14000d524  add     r8, 0Ch
0x14000d528  lea     rdx, [rsp+1090h+var_1040]
0x14000d52d  cmp     r8, rsi
0x14000d530  jnz     short loc_14000D4BF
0x14000d532  mov     eax, [rsp+1090h+var_104C]
0x14000d536  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000d53d  mov     [rsp+1090h+var_1060], 1
0x14000d545  mov     r8d, r9d
0x14000d548  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000d54c  call    wil_details_NtUpdateWnfStateData
0x14000d551  mov     esi, eax
0x14000d553  cmp     esi, 0C0000001h
0x14000d559  jnz     short loc_14000D56C
0x14000d55b  inc     r15d
0x14000d55e  cmp     r15d, 64h ; 'd'
0x14000d562  jge     short loc_14000D56C
0x14000d564  test    edi, edi
0x14000d566  jz      loc_14000D3B2
0x14000d56c  test    ebx, ebx
0x14000d56e  cmovz   ebx, esi
0x14000d571  mov     eax, ebx
0x14000d573  mov     rcx, [rbp+0F90h+var_40]
0x14000d57a  xor     rcx, rsp; StackCookie
0x14000d57d  call    __security_check_cookie
0x14000d582  add     rsp, 1068h
0x14000d589  pop     r15
0x14000d58b  pop     r14
0x14000d58d  pop     rdi
0x14000d58e  pop     rsi
0x14000d58f  pop     rbx
0x14000d590  pop     rbp
0x14000d591  retn
0x14000d592  mov     eax, [r8+8]
0x14000d596  add     [rcx+8], eax
0x14000d599  mov     r9d, [rsp+1090h+var_1050]
0x14000d59e  jmp     short loc_14000D524
```
