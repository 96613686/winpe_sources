# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180022b44`
- end: `0x180022d7c`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b470`

## callees

- `0x180022b44`
- `0x180022f34`
- `0x18004371a`
- `0x180043750`
- `0x180043810`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022be4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022be4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022bcd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022bcd`

## string_xrefs

- `0x180022bc6`: `ntdll.dll`

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
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180022b44  push    rbp
0x180022b46  push    rbx
0x180022b47  push    rsi
0x180022b48  push    rdi
0x180022b49  push    r14
0x180022b4b  push    r15
0x180022b4d  lea     rbp, [rsp-0F68h]
0x180022b55  mov     eax, 1068h
0x180022b5a  call    _alloca_probe
0x180022b5f  sub     rsp, rax
0x180022b62  mov     rax, cs:__security_cookie
0x180022b69  xor     rax, rsp
0x180022b6c  mov     [rbp+0F90h+var_40], rax
0x180022b73  mov     rax, [rcx+8]
0x180022b77  xor     ebx, ebx
0x180022b79  sub     rax, [rcx]
0x180022b7c  xor     esi, esi
0x180022b7e  mov     r14, rcx
0x180022b81  cmp     rax, 0Ch
0x180022b85  jb      loc_180022D48
0x180022b8b  xor     r15d, r15d
0x180022b8e  xor     edx, edx; Val
0x180022b90  lea     rcx, [rsp+1090h+var_1040]; void *
0x180022b95  mov     r8d, 1000h; Size
0x180022b9b  call    memset_0
0x180022ba0  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180022ba8  mov     [rsp+1090h+var_1050], 1000h
0x180022bb0  mov     [rsp+1090h+var_104C], 0
0x180022bb8  jnz     short loc_180022C02
0x180022bba  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022bc1  test    rax, rax
0x180022bc4  jnz     short loc_180022BDA
0x180022bc6  lea     rcx, ModuleName; "ntdll.dll"
0x180022bcd  call    cs:__imp_GetModuleHandleW
0x180022bd3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022bda  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180022be1  mov     rcx, rax; hModule
0x180022be4  call    cs:__imp_GetProcAddress
0x180022bea  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180022bf1  test    rax, rax
0x180022bf4  jnz     short loc_180022C02
0x180022bf6  mov     edi, 0C0000139h
0x180022bfb  mov     ebx, edi
0x180022bfd  jmp     loc_180022D2F
0x180022c02  lea     rax, [rsp+1090h+var_1050]
0x180022c07  xor     r8d, r8d
0x180022c0a  mov     [rsp+1090h+var_1068], rax
0x180022c0f  lea     r9, [rsp+1090h+var_104C]
0x180022c14  lea     rax, [rsp+1090h+var_1040]
0x180022c19  xor     edx, edx
0x180022c1b  mov     [rsp+1090h+var_1070], rax
0x180022c20  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180022c27  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180022c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c33  mov     ebx, eax
0x180022c35  mov     edi, eax
0x180022c37  test    eax, eax
0x180022c39  jnz     loc_180022D2F
0x180022c3f  mov     r9d, [rsp+1090h+var_1050]
0x180022c44  mov     r11, 0AAAAAAAAAAAAAAABh
0x180022c4e  mov     rax, r11
0x180022c51  mul     r9
0x180022c54  shr     rdx, 3
0x180022c58  lea     rcx, [rdx+rdx*2]
0x180022c5c  shl     rcx, 2
0x180022c60  cmp     r9, rcx
0x180022c63  jz      short loc_180022C6D
0x180022c65  xor     r9d, r9d
0x180022c68  mov     [rsp+1090h+var_1050], r9d
0x180022c6d  mov     r8, [r14]
0x180022c70  mov     rax, r11
0x180022c73  mov     ecx, r9d
0x180022c76  mul     rcx
0x180022c79  mov     rcx, [r14+8]
0x180022c7d  mov     rax, r11
0x180022c80  mov     r10, rdx
0x180022c83  sub     rcx, r8
0x180022c86  mul     rcx
0x180022c89  shr     r10, 3
0x180022c8d  shr     rdx, 3
0x180022c91  lea     rax, [rdx+rdx*2]
0x180022c95  lea     rsi, [r8+rax*4]
0x180022c99  jmp     short loc_180022D04
0x180022c9b  mov     eax, r10d
0x180022c9e  lea     rcx, [rax+rax*2]
0x180022ca2  lea     rdx, [rdx+rcx*4]
0x180022ca6  lea     rax, [rsp+1090h+var_1040]
0x180022cab  cmp     rax, rdx
0x180022cae  jz      short loc_180022CD5
0x180022cb0  mov     r11d, [r8]
0x180022cb3  lea     rcx, [rsp+1090h+var_1040]
0x180022cb8  cmp     [rcx], r11d
0x180022cbb  jnz     short loc_180022CCC
0x180022cbd  movzx   eax, word ptr [r8+4]
0x180022cc2  cmp     [rcx+4], ax
0x180022cc6  jz      loc_180022D6E
0x180022ccc  add     rcx, 0Ch
0x180022cd0  cmp     rcx, rdx
0x180022cd3  jnz     short loc_180022CB8
0x180022cd5  mov     eax, r9d
0x180022cd8  add     rax, 0Ch
0x180022cdc  cmp     rax, 1000h
0x180022ce2  ja      short loc_180022D00
0x180022ce4  movsd   xmm0, qword ptr [r8]
0x180022ce9  add     r9d, 0Ch
0x180022ced  movsd   qword ptr [rdx], xmm0
0x180022cf1  inc     r10d
0x180022cf4  mov     eax, [r8+8]
0x180022cf8  mov     [rdx+8], eax
0x180022cfb  mov     [rsp+1090h+var_1050], r9d
0x180022d00  add     r8, 0Ch
0x180022d04  lea     rdx, [rsp+1090h+var_1040]
0x180022d09  cmp     r8, rsi
0x180022d0c  jnz     short loc_180022C9B
0x180022d0e  mov     eax, [rsp+1090h+var_104C]
0x180022d12  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180022d19  mov     [rsp+1090h+var_1060], 1
0x180022d21  mov     r8d, r9d
0x180022d24  mov     dword ptr [rsp+1090h+var_1068], eax
0x180022d28  call    wil_details_NtUpdateWnfStateData
0x180022d2d  mov     esi, eax
0x180022d2f  cmp     esi, 0C0000001h
0x180022d35  jnz     short loc_180022D48
0x180022d37  inc     r15d
0x180022d3a  cmp     r15d, 64h ; 'd'
0x180022d3e  jge     short loc_180022D48
0x180022d40  test    edi, edi
0x180022d42  jz      loc_180022B8E
0x180022d48  test    ebx, ebx
0x180022d4a  cmovz   ebx, esi
0x180022d4d  mov     eax, ebx
0x180022d4f  mov     rcx, [rbp+0F90h+var_40]
0x180022d56  xor     rcx, rsp; StackCookie
0x180022d59  call    __security_check_cookie
0x180022d5e  add     rsp, 1068h
0x180022d65  pop     r15
0x180022d67  pop     r14
0x180022d69  pop     rdi
0x180022d6a  pop     rsi
0x180022d6b  pop     rbx
0x180022d6c  pop     rbp
0x180022d6d  retn
0x180022d6e  mov     eax, [r8+8]
0x180022d72  add     [rcx+8], eax
0x180022d75  mov     r9d, [rsp+1090h+var_1050]
0x180022d7a  jmp     short loc_180022D00
```
