# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180008de4`
- end: `0x18000901c`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002850`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180008de4`
- `0x180009490`
- `0x18003acd0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008e6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008e6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008e84`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008e84`

## string_xrefs

- `0x180008e66`: `ntdll.dll`

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
0x180008de4  push    rbp
0x180008de6  push    rbx
0x180008de7  push    rsi
0x180008de8  push    rdi
0x180008de9  push    r14
0x180008deb  push    r15
0x180008ded  lea     rbp, [rsp-0F68h]
0x180008df5  mov     eax, 1068h
0x180008dfa  call    _alloca_probe
0x180008dff  sub     rsp, rax
0x180008e02  mov     rax, cs:__security_cookie
0x180008e09  xor     rax, rsp
0x180008e0c  mov     [rbp+0F90h+var_40], rax
0x180008e13  mov     rax, [rcx+8]
0x180008e17  xor     ebx, ebx
0x180008e19  sub     rax, [rcx]
0x180008e1c  xor     esi, esi
0x180008e1e  mov     r14, rcx
0x180008e21  cmp     rax, 0Ch
0x180008e25  jb      loc_180008FE8
0x180008e2b  xor     r15d, r15d
0x180008e2e  xor     edx, edx; Val
0x180008e30  lea     rcx, [rsp+1090h+var_1040]; void *
0x180008e35  mov     r8d, 1000h; Size
0x180008e3b  call    memset_0
0x180008e40  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180008e48  mov     [rsp+1090h+var_1050], 1000h
0x180008e50  mov     [rsp+1090h+var_104C], 0
0x180008e58  jnz     short loc_180008EA2
0x180008e5a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008e61  test    rax, rax
0x180008e64  jnz     short loc_180008E7A
0x180008e66  lea     rcx, ModuleName; "ntdll.dll"
0x180008e6d  call    cs:__imp_GetModuleHandleW
0x180008e73  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008e7a  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180008e81  mov     rcx, rax; hModule
0x180008e84  call    cs:__imp_GetProcAddress
0x180008e8a  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008e91  test    rax, rax
0x180008e94  jnz     short loc_180008EA2
0x180008e96  mov     edi, 0C0000139h
0x180008e9b  mov     ebx, edi
0x180008e9d  jmp     loc_180008FCF
0x180008ea2  lea     rax, [rsp+1090h+var_1050]
0x180008ea7  xor     r8d, r8d
0x180008eaa  mov     [rsp+1090h+var_1068], rax
0x180008eaf  lea     r9, [rsp+1090h+var_104C]
0x180008eb4  lea     rax, [rsp+1090h+var_1040]
0x180008eb9  xor     edx, edx
0x180008ebb  mov     [rsp+1090h+var_1070], rax
0x180008ec0  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008ec7  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ed3  mov     ebx, eax
0x180008ed5  mov     edi, eax
0x180008ed7  test    eax, eax
0x180008ed9  jnz     loc_180008FCF
0x180008edf  mov     r9d, [rsp+1090h+var_1050]
0x180008ee4  mov     r11, 0AAAAAAAAAAAAAAABh
0x180008eee  mov     rax, r11
0x180008ef1  mul     r9
0x180008ef4  shr     rdx, 3
0x180008ef8  lea     rcx, [rdx+rdx*2]
0x180008efc  shl     rcx, 2
0x180008f00  cmp     r9, rcx
0x180008f03  jz      short loc_180008F0D
0x180008f05  xor     r9d, r9d
0x180008f08  mov     [rsp+1090h+var_1050], r9d
0x180008f0d  mov     r8, [r14]
0x180008f10  mov     rax, r11
0x180008f13  mov     ecx, r9d
0x180008f16  mul     rcx
0x180008f19  mov     rcx, [r14+8]
0x180008f1d  mov     rax, r11
0x180008f20  mov     r10, rdx
0x180008f23  sub     rcx, r8
0x180008f26  mul     rcx
0x180008f29  shr     r10, 3
0x180008f2d  shr     rdx, 3
0x180008f31  lea     rax, [rdx+rdx*2]
0x180008f35  lea     rsi, [r8+rax*4]
0x180008f39  jmp     short loc_180008FA4
0x180008f3b  mov     eax, r10d
0x180008f3e  lea     rcx, [rax+rax*2]
0x180008f42  lea     rdx, [rdx+rcx*4]
0x180008f46  lea     rax, [rsp+1090h+var_1040]
0x180008f4b  cmp     rax, rdx
0x180008f4e  jz      short loc_180008F75
0x180008f50  mov     r11d, [r8]
0x180008f53  lea     rcx, [rsp+1090h+var_1040]
0x180008f58  cmp     [rcx], r11d
0x180008f5b  jnz     short loc_180008F6C
0x180008f5d  movzx   eax, word ptr [r8+4]
0x180008f62  cmp     [rcx+4], ax
0x180008f66  jz      loc_18000900E
0x180008f6c  add     rcx, 0Ch
0x180008f70  cmp     rcx, rdx
0x180008f73  jnz     short loc_180008F58
0x180008f75  mov     eax, r9d
0x180008f78  add     rax, 0Ch
0x180008f7c  cmp     rax, 1000h
0x180008f82  ja      short loc_180008FA0
0x180008f84  movsd   xmm0, qword ptr [r8]
0x180008f89  add     r9d, 0Ch
0x180008f8d  movsd   qword ptr [rdx], xmm0
0x180008f91  inc     r10d
0x180008f94  mov     eax, [r8+8]
0x180008f98  mov     [rdx+8], eax
0x180008f9b  mov     [rsp+1090h+var_1050], r9d
0x180008fa0  add     r8, 0Ch
0x180008fa4  lea     rdx, [rsp+1090h+var_1040]
0x180008fa9  cmp     r8, rsi
0x180008fac  jnz     short loc_180008F3B
0x180008fae  mov     eax, [rsp+1090h+var_104C]
0x180008fb2  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008fb9  mov     [rsp+1090h+var_1060], 1
0x180008fc1  mov     r8d, r9d
0x180008fc4  mov     dword ptr [rsp+1090h+var_1068], eax
0x180008fc8  call    wil_details_NtUpdateWnfStateData
0x180008fcd  mov     esi, eax
0x180008fcf  cmp     esi, 0C0000001h
0x180008fd5  jnz     short loc_180008FE8
0x180008fd7  inc     r15d
0x180008fda  cmp     r15d, 64h ; 'd'
0x180008fde  jge     short loc_180008FE8
0x180008fe0  test    edi, edi
0x180008fe2  jz      loc_180008E2E
0x180008fe8  test    ebx, ebx
0x180008fea  cmovz   ebx, esi
0x180008fed  mov     eax, ebx
0x180008fef  mov     rcx, [rbp+0F90h+var_40]
0x180008ff6  xor     rcx, rsp; StackCookie
0x180008ff9  call    __security_check_cookie
0x180008ffe  add     rsp, 1068h
0x180009005  pop     r15
0x180009007  pop     r14
0x180009009  pop     rdi
0x18000900a  pop     rsi
0x18000900b  pop     rbx
0x18000900c  pop     rbp
0x18000900d  retn
0x18000900e  mov     eax, [r8+8]
0x180009012  add     [rcx+8], eax
0x180009015  mov     r9d, [rsp+1090h+var_1050]
0x18000901a  jmp     short loc_180008FA0
```
