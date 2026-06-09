# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000b540`
- end: `0x18000b778`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800021c0`

## callees

- `0x18000b540`
- `0x18000bcb0`
- `0x1800184ce`
- `0x180018500`
- `0x180018590`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000b5e0`
- `KERNEL32!GetProcAddress` at `0x18000b5e0`
- `KERNEL32!GetModuleHandleW` at `0x18000b5c9`
- `KERNEL32!GetModuleHandleW` at `0x18000b5c9`

## string_xrefs

- `0x18000b5c2`: `ntdll.dll`

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
0x18000b540  push    rbp
0x18000b542  push    rbx
0x18000b543  push    rsi
0x18000b544  push    rdi
0x18000b545  push    r14
0x18000b547  push    r15
0x18000b549  lea     rbp, [rsp-0F68h]
0x18000b551  mov     eax, 1068h
0x18000b556  call    _alloca_probe
0x18000b55b  sub     rsp, rax
0x18000b55e  mov     rax, cs:__security_cookie
0x18000b565  xor     rax, rsp
0x18000b568  mov     [rbp+0F90h+var_40], rax
0x18000b56f  mov     rax, [rcx+8]
0x18000b573  xor     ebx, ebx
0x18000b575  sub     rax, [rcx]
0x18000b578  xor     esi, esi
0x18000b57a  mov     r14, rcx
0x18000b57d  cmp     rax, 0Ch
0x18000b581  jb      loc_18000B744
0x18000b587  xor     r15d, r15d
0x18000b58a  xor     edx, edx; Val
0x18000b58c  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000b591  mov     r8d, 1000h; Size
0x18000b597  call    memset_0
0x18000b59c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000b5a4  mov     [rsp+1090h+var_1050], 1000h
0x18000b5ac  mov     [rsp+1090h+var_104C], 0
0x18000b5b4  jnz     short loc_18000B5FE
0x18000b5b6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b5bd  test    rax, rax
0x18000b5c0  jnz     short loc_18000B5D6
0x18000b5c2  lea     rcx, ModuleName; "ntdll.dll"
0x18000b5c9  call    cs:__imp_GetModuleHandleW
0x18000b5cf  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b5d6  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000b5dd  mov     rcx, rax; hModule
0x18000b5e0  call    cs:__imp_GetProcAddress
0x18000b5e6  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000b5ed  test    rax, rax
0x18000b5f0  jnz     short loc_18000B5FE
0x18000b5f2  mov     edi, 0C0000139h
0x18000b5f7  mov     ebx, edi
0x18000b5f9  jmp     loc_18000B72B
0x18000b5fe  lea     rax, [rsp+1090h+var_1050]
0x18000b603  xor     r8d, r8d
0x18000b606  mov     [rsp+1090h+var_1068], rax
0x18000b60b  lea     r9, [rsp+1090h+var_104C]
0x18000b610  lea     rax, [rsp+1090h+var_1040]
0x18000b615  xor     edx, edx
0x18000b617  mov     [rsp+1090h+var_1070], rax
0x18000b61c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b623  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000b62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b62f  mov     ebx, eax
0x18000b631  mov     edi, eax
0x18000b633  test    eax, eax
0x18000b635  jnz     loc_18000B72B
0x18000b63b  mov     r9d, [rsp+1090h+var_1050]
0x18000b640  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000b64a  mov     rax, r11
0x18000b64d  mul     r9
0x18000b650  shr     rdx, 3
0x18000b654  lea     rcx, [rdx+rdx*2]
0x18000b658  shl     rcx, 2
0x18000b65c  cmp     r9, rcx
0x18000b65f  jz      short loc_18000B669
0x18000b661  xor     r9d, r9d
0x18000b664  mov     [rsp+1090h+var_1050], r9d
0x18000b669  mov     r8, [r14]
0x18000b66c  mov     rax, r11
0x18000b66f  mov     ecx, r9d
0x18000b672  mul     rcx
0x18000b675  mov     rcx, [r14+8]
0x18000b679  mov     rax, r11
0x18000b67c  mov     r10, rdx
0x18000b67f  sub     rcx, r8
0x18000b682  mul     rcx
0x18000b685  shr     r10, 3
0x18000b689  shr     rdx, 3
0x18000b68d  lea     rax, [rdx+rdx*2]
0x18000b691  lea     rsi, [r8+rax*4]
0x18000b695  jmp     short loc_18000B700
0x18000b697  mov     eax, r10d
0x18000b69a  lea     rcx, [rax+rax*2]
0x18000b69e  lea     rdx, [rdx+rcx*4]
0x18000b6a2  lea     rax, [rsp+1090h+var_1040]
0x18000b6a7  cmp     rax, rdx
0x18000b6aa  jz      short loc_18000B6D1
0x18000b6ac  mov     r11d, [r8]
0x18000b6af  lea     rcx, [rsp+1090h+var_1040]
0x18000b6b4  cmp     [rcx], r11d
0x18000b6b7  jnz     short loc_18000B6C8
0x18000b6b9  movzx   eax, word ptr [r8+4]
0x18000b6be  cmp     [rcx+4], ax
0x18000b6c2  jz      loc_18000B76A
0x18000b6c8  add     rcx, 0Ch
0x18000b6cc  cmp     rcx, rdx
0x18000b6cf  jnz     short loc_18000B6B4
0x18000b6d1  mov     eax, r9d
0x18000b6d4  add     rax, 0Ch
0x18000b6d8  cmp     rax, 1000h
0x18000b6de  ja      short loc_18000B6FC
0x18000b6e0  movsd   xmm0, qword ptr [r8]
0x18000b6e5  add     r9d, 0Ch
0x18000b6e9  movsd   qword ptr [rdx], xmm0
0x18000b6ed  inc     r10d
0x18000b6f0  mov     eax, [r8+8]
0x18000b6f4  mov     [rdx+8], eax
0x18000b6f7  mov     [rsp+1090h+var_1050], r9d
0x18000b6fc  add     r8, 0Ch
0x18000b700  lea     rdx, [rsp+1090h+var_1040]
0x18000b705  cmp     r8, rsi
0x18000b708  jnz     short loc_18000B697
0x18000b70a  mov     eax, [rsp+1090h+var_104C]
0x18000b70e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b715  mov     [rsp+1090h+var_1060], 1
0x18000b71d  mov     r8d, r9d
0x18000b720  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000b724  call    wil_details_NtUpdateWnfStateData
0x18000b729  mov     esi, eax
0x18000b72b  cmp     esi, 0C0000001h
0x18000b731  jnz     short loc_18000B744
0x18000b733  inc     r15d
0x18000b736  cmp     r15d, 64h ; 'd'
0x18000b73a  jge     short loc_18000B744
0x18000b73c  test    edi, edi
0x18000b73e  jz      loc_18000B58A
0x18000b744  test    ebx, ebx
0x18000b746  cmovz   ebx, esi
0x18000b749  mov     eax, ebx
0x18000b74b  mov     rcx, [rbp+0F90h+var_40]
0x18000b752  xor     rcx, rsp; StackCookie
0x18000b755  call    __security_check_cookie
0x18000b75a  add     rsp, 1068h
0x18000b761  pop     r15
0x18000b763  pop     r14
0x18000b765  pop     rdi
0x18000b766  pop     rsi
0x18000b767  pop     rbx
0x18000b768  pop     rbp
0x18000b769  retn
0x18000b76a  mov     eax, [r8+8]
0x18000b76e  add     [rcx+8], eax
0x18000b771  mov     r9d, [rsp+1090h+var_1050]
0x18000b776  jmp     short loc_18000B6FC
```
