# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000a478`
- end: `0x18000a6b0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002d60`

## callees

- `0x180001cf0`
- `0x1800026c8`
- `0x18000a478`
- `0x18000ab30`
- `0x180011c00`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a518`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a518`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a501`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a501`

## string_xrefs

- `0x18000a4fa`: `ntdll.dll`

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
0x18000a478  push    rbp
0x18000a47a  push    rbx
0x18000a47b  push    rsi
0x18000a47c  push    rdi
0x18000a47d  push    r14
0x18000a47f  push    r15
0x18000a481  lea     rbp, [rsp-0F68h]
0x18000a489  mov     eax, 1068h
0x18000a48e  call    _alloca_probe
0x18000a493  sub     rsp, rax
0x18000a496  mov     rax, cs:__security_cookie
0x18000a49d  xor     rax, rsp
0x18000a4a0  mov     [rbp+0F90h+var_40], rax
0x18000a4a7  mov     rax, [rcx+8]
0x18000a4ab  xor     ebx, ebx
0x18000a4ad  sub     rax, [rcx]
0x18000a4b0  xor     esi, esi
0x18000a4b2  mov     r14, rcx
0x18000a4b5  cmp     rax, 0Ch
0x18000a4b9  jb      loc_18000A67C
0x18000a4bf  xor     r15d, r15d
0x18000a4c2  xor     edx, edx; Val
0x18000a4c4  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000a4c9  mov     r8d, 1000h; Size
0x18000a4cf  call    memset_0
0x18000a4d4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000a4dc  mov     [rsp+1090h+var_1050], 1000h
0x18000a4e4  mov     [rsp+1090h+var_104C], 0
0x18000a4ec  jnz     short loc_18000A536
0x18000a4ee  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a4f5  test    rax, rax
0x18000a4f8  jnz     short loc_18000A50E
0x18000a4fa  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a501  call    cs:__imp_GetModuleHandleW
0x18000a507  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a50e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000a515  mov     rcx, rax; hModule
0x18000a518  call    cs:__imp_GetProcAddress
0x18000a51e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000a525  test    rax, rax
0x18000a528  jnz     short loc_18000A536
0x18000a52a  mov     edi, 0C0000139h
0x18000a52f  mov     ebx, edi
0x18000a531  jmp     loc_18000A663
0x18000a536  lea     rax, [rsp+1090h+var_1050]
0x18000a53b  xor     r8d, r8d
0x18000a53e  mov     [rsp+1090h+var_1068], rax
0x18000a543  lea     r9, [rsp+1090h+var_104C]
0x18000a548  lea     rax, [rsp+1090h+var_1040]
0x18000a54d  xor     edx, edx
0x18000a54f  mov     [rsp+1090h+var_1070], rax
0x18000a554  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a55b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000a562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a567  mov     ebx, eax
0x18000a569  mov     edi, eax
0x18000a56b  test    eax, eax
0x18000a56d  jnz     loc_18000A663
0x18000a573  mov     r9d, [rsp+1090h+var_1050]
0x18000a578  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000a582  mov     rax, r11
0x18000a585  mul     r9
0x18000a588  shr     rdx, 3
0x18000a58c  lea     rcx, [rdx+rdx*2]
0x18000a590  shl     rcx, 2
0x18000a594  cmp     r9, rcx
0x18000a597  jz      short loc_18000A5A1
0x18000a599  xor     r9d, r9d
0x18000a59c  mov     [rsp+1090h+var_1050], r9d
0x18000a5a1  mov     r8, [r14]
0x18000a5a4  mov     rax, r11
0x18000a5a7  mov     ecx, r9d
0x18000a5aa  mul     rcx
0x18000a5ad  mov     rcx, [r14+8]
0x18000a5b1  mov     rax, r11
0x18000a5b4  mov     r10, rdx
0x18000a5b7  sub     rcx, r8
0x18000a5ba  mul     rcx
0x18000a5bd  shr     r10, 3
0x18000a5c1  shr     rdx, 3
0x18000a5c5  lea     rax, [rdx+rdx*2]
0x18000a5c9  lea     rsi, [r8+rax*4]
0x18000a5cd  jmp     short loc_18000A638
0x18000a5cf  mov     eax, r10d
0x18000a5d2  lea     rcx, [rax+rax*2]
0x18000a5d6  lea     rdx, [rdx+rcx*4]
0x18000a5da  lea     rax, [rsp+1090h+var_1040]
0x18000a5df  cmp     rax, rdx
0x18000a5e2  jz      short loc_18000A609
0x18000a5e4  mov     r11d, [r8]
0x18000a5e7  lea     rcx, [rsp+1090h+var_1040]
0x18000a5ec  cmp     [rcx], r11d
0x18000a5ef  jnz     short loc_18000A600
0x18000a5f1  movzx   eax, word ptr [r8+4]
0x18000a5f6  cmp     [rcx+4], ax
0x18000a5fa  jz      loc_18000A6A2
0x18000a600  add     rcx, 0Ch
0x18000a604  cmp     rcx, rdx
0x18000a607  jnz     short loc_18000A5EC
0x18000a609  mov     eax, r9d
0x18000a60c  add     rax, 0Ch
0x18000a610  cmp     rax, 1000h
0x18000a616  ja      short loc_18000A634
0x18000a618  movsd   xmm0, qword ptr [r8]
0x18000a61d  add     r9d, 0Ch
0x18000a621  movsd   qword ptr [rdx], xmm0
0x18000a625  inc     r10d
0x18000a628  mov     eax, [r8+8]
0x18000a62c  mov     [rdx+8], eax
0x18000a62f  mov     [rsp+1090h+var_1050], r9d
0x18000a634  add     r8, 0Ch
0x18000a638  lea     rdx, [rsp+1090h+var_1040]
0x18000a63d  cmp     r8, rsi
0x18000a640  jnz     short loc_18000A5CF
0x18000a642  mov     eax, [rsp+1090h+var_104C]
0x18000a646  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a64d  mov     [rsp+1090h+var_1060], 1
0x18000a655  mov     r8d, r9d
0x18000a658  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000a65c  call    wil_details_NtUpdateWnfStateData
0x18000a661  mov     esi, eax
0x18000a663  cmp     esi, 0C0000001h
0x18000a669  jnz     short loc_18000A67C
0x18000a66b  inc     r15d
0x18000a66e  cmp     r15d, 64h ; 'd'
0x18000a672  jge     short loc_18000A67C
0x18000a674  test    edi, edi
0x18000a676  jz      loc_18000A4C2
0x18000a67c  test    ebx, ebx
0x18000a67e  cmovz   ebx, esi
0x18000a681  mov     eax, ebx
0x18000a683  mov     rcx, [rbp+0F90h+var_40]
0x18000a68a  xor     rcx, rsp; StackCookie
0x18000a68d  call    __security_check_cookie
0x18000a692  add     rsp, 1068h
0x18000a699  pop     r15
0x18000a69b  pop     r14
0x18000a69d  pop     rdi
0x18000a69e  pop     rsi
0x18000a69f  pop     rbx
0x18000a6a0  pop     rbp
0x18000a6a1  retn
0x18000a6a2  mov     eax, [r8+8]
0x18000a6a6  add     [rcx+8], eax
0x18000a6a9  mov     r9d, [rsp+1090h+var_1050]
0x18000a6ae  jmp     short loc_18000A634
```
