# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000ca18`
- end: `0x18000cc50`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180003150`

## callees

- `0x180002270`
- `0x180002be8`
- `0x18000ca18`
- `0x18000d330`
- `0x180013ff0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000caa1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000caa1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cab8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cab8`

## string_xrefs

- `0x18000ca9a`: `ntdll.dll`

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
0x18000ca18  push    rbp
0x18000ca1a  push    rbx
0x18000ca1b  push    rsi
0x18000ca1c  push    rdi
0x18000ca1d  push    r14
0x18000ca1f  push    r15
0x18000ca21  lea     rbp, [rsp-0F68h]
0x18000ca29  mov     eax, 1068h
0x18000ca2e  call    _alloca_probe
0x18000ca33  sub     rsp, rax
0x18000ca36  mov     rax, cs:__security_cookie
0x18000ca3d  xor     rax, rsp
0x18000ca40  mov     [rbp+0F90h+var_40], rax
0x18000ca47  mov     rax, [rcx+8]
0x18000ca4b  xor     ebx, ebx
0x18000ca4d  sub     rax, [rcx]
0x18000ca50  xor     esi, esi
0x18000ca52  mov     r14, rcx
0x18000ca55  cmp     rax, 0Ch
0x18000ca59  jb      loc_18000CC1C
0x18000ca5f  xor     r15d, r15d
0x18000ca62  xor     edx, edx; Val
0x18000ca64  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000ca69  mov     r8d, 1000h; Size
0x18000ca6f  call    memset_0
0x18000ca74  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000ca7c  mov     [rsp+1090h+var_1050], 1000h
0x18000ca84  mov     [rsp+1090h+var_104C], 0
0x18000ca8c  jnz     short loc_18000CAD6
0x18000ca8e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ca95  test    rax, rax
0x18000ca98  jnz     short loc_18000CAAE
0x18000ca9a  lea     rcx, ModuleName; "ntdll.dll"
0x18000caa1  call    cs:__imp_GetModuleHandleW
0x18000caa7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000caae  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000cab5  mov     rcx, rax; hModule
0x18000cab8  call    cs:__imp_GetProcAddress
0x18000cabe  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000cac5  test    rax, rax
0x18000cac8  jnz     short loc_18000CAD6
0x18000caca  mov     edi, 0C0000139h
0x18000cacf  mov     ebx, edi
0x18000cad1  jmp     loc_18000CC03
0x18000cad6  lea     rax, [rsp+1090h+var_1050]
0x18000cadb  xor     r8d, r8d
0x18000cade  mov     [rsp+1090h+var_1068], rax
0x18000cae3  lea     r9, [rsp+1090h+var_104C]
0x18000cae8  lea     rax, [rsp+1090h+var_1040]
0x18000caed  xor     edx, edx
0x18000caef  mov     [rsp+1090h+var_1070], rax
0x18000caf4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000cafb  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000cb02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb07  mov     ebx, eax
0x18000cb09  mov     edi, eax
0x18000cb0b  test    eax, eax
0x18000cb0d  jnz     loc_18000CC03
0x18000cb13  mov     r9d, [rsp+1090h+var_1050]
0x18000cb18  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000cb22  mov     rax, r11
0x18000cb25  mul     r9
0x18000cb28  shr     rdx, 3
0x18000cb2c  lea     rcx, [rdx+rdx*2]
0x18000cb30  shl     rcx, 2
0x18000cb34  cmp     r9, rcx
0x18000cb37  jz      short loc_18000CB41
0x18000cb39  xor     r9d, r9d
0x18000cb3c  mov     [rsp+1090h+var_1050], r9d
0x18000cb41  mov     r8, [r14]
0x18000cb44  mov     rax, r11
0x18000cb47  mov     ecx, r9d
0x18000cb4a  mul     rcx
0x18000cb4d  mov     rcx, [r14+8]
0x18000cb51  mov     rax, r11
0x18000cb54  mov     r10, rdx
0x18000cb57  sub     rcx, r8
0x18000cb5a  mul     rcx
0x18000cb5d  shr     r10, 3
0x18000cb61  shr     rdx, 3
0x18000cb65  lea     rax, [rdx+rdx*2]
0x18000cb69  lea     rsi, [r8+rax*4]
0x18000cb6d  jmp     short loc_18000CBD8
0x18000cb6f  mov     eax, r10d
0x18000cb72  lea     rcx, [rax+rax*2]
0x18000cb76  lea     rdx, [rdx+rcx*4]
0x18000cb7a  lea     rax, [rsp+1090h+var_1040]
0x18000cb7f  cmp     rax, rdx
0x18000cb82  jz      short loc_18000CBA9
0x18000cb84  mov     r11d, [r8]
0x18000cb87  lea     rcx, [rsp+1090h+var_1040]
0x18000cb8c  cmp     [rcx], r11d
0x18000cb8f  jnz     short loc_18000CBA0
0x18000cb91  movzx   eax, word ptr [r8+4]
0x18000cb96  cmp     [rcx+4], ax
0x18000cb9a  jz      loc_18000CC42
0x18000cba0  add     rcx, 0Ch
0x18000cba4  cmp     rcx, rdx
0x18000cba7  jnz     short loc_18000CB8C
0x18000cba9  mov     eax, r9d
0x18000cbac  add     rax, 0Ch
0x18000cbb0  cmp     rax, 1000h
0x18000cbb6  ja      short loc_18000CBD4
0x18000cbb8  movsd   xmm0, qword ptr [r8]
0x18000cbbd  add     r9d, 0Ch
0x18000cbc1  movsd   qword ptr [rdx], xmm0
0x18000cbc5  inc     r10d
0x18000cbc8  mov     eax, [r8+8]
0x18000cbcc  mov     [rdx+8], eax
0x18000cbcf  mov     [rsp+1090h+var_1050], r9d
0x18000cbd4  add     r8, 0Ch
0x18000cbd8  lea     rdx, [rsp+1090h+var_1040]
0x18000cbdd  cmp     r8, rsi
0x18000cbe0  jnz     short loc_18000CB6F
0x18000cbe2  mov     eax, [rsp+1090h+var_104C]
0x18000cbe6  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000cbed  mov     [rsp+1090h+var_1060], 1
0x18000cbf5  mov     r8d, r9d
0x18000cbf8  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000cbfc  call    wil_details_NtUpdateWnfStateData
0x18000cc01  mov     esi, eax
0x18000cc03  cmp     esi, 0C0000001h
0x18000cc09  jnz     short loc_18000CC1C
0x18000cc0b  inc     r15d
0x18000cc0e  cmp     r15d, 64h ; 'd'
0x18000cc12  jge     short loc_18000CC1C
0x18000cc14  test    edi, edi
0x18000cc16  jz      loc_18000CA62
0x18000cc1c  test    ebx, ebx
0x18000cc1e  cmovz   ebx, esi
0x18000cc21  mov     eax, ebx
0x18000cc23  mov     rcx, [rbp+0F90h+var_40]
0x18000cc2a  xor     rcx, rsp; StackCookie
0x18000cc2d  call    __security_check_cookie
0x18000cc32  add     rsp, 1068h
0x18000cc39  pop     r15
0x18000cc3b  pop     r14
0x18000cc3d  pop     rdi
0x18000cc3e  pop     rsi
0x18000cc3f  pop     rbx
0x18000cc40  pop     rbp
0x18000cc41  retn
0x18000cc42  mov     eax, [r8+8]
0x18000cc46  add     [rcx+8], eax
0x18000cc49  mov     r9d, [rsp+1090h+var_1050]
0x18000cc4e  jmp     short loc_18000CBD4
```
