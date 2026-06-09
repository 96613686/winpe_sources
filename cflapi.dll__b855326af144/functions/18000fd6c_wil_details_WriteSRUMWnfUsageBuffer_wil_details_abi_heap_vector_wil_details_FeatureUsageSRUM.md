# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000fd6c`
- end: `0x18000ffa4`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180007b70`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x18000fd6c`
- `0x180012860`
- `0x18002df90`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fdf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fdf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fe0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fe0c`

## string_xrefs

- `0x18000fdee`: `ntdll.dll`

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
0x18000fd6c  push    rbp
0x18000fd6e  push    rbx
0x18000fd6f  push    rsi
0x18000fd70  push    rdi
0x18000fd71  push    r14
0x18000fd73  push    r15
0x18000fd75  lea     rbp, [rsp-0F68h]
0x18000fd7d  mov     eax, 1068h
0x18000fd82  call    _alloca_probe
0x18000fd87  sub     rsp, rax
0x18000fd8a  mov     rax, cs:__security_cookie
0x18000fd91  xor     rax, rsp
0x18000fd94  mov     [rbp+0F90h+var_40], rax
0x18000fd9b  mov     rax, [rcx+8]
0x18000fd9f  xor     ebx, ebx
0x18000fda1  sub     rax, [rcx]
0x18000fda4  xor     esi, esi
0x18000fda6  mov     r14, rcx
0x18000fda9  cmp     rax, 0Ch
0x18000fdad  jb      loc_18000FF70
0x18000fdb3  xor     r15d, r15d
0x18000fdb6  xor     edx, edx; Val
0x18000fdb8  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000fdbd  mov     r8d, 1000h; Size
0x18000fdc3  call    memset_0
0x18000fdc8  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000fdd0  mov     [rsp+1090h+var_1050], 1000h
0x18000fdd8  mov     [rsp+1090h+var_104C], 0
0x18000fde0  jnz     short loc_18000FE2A
0x18000fde2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fde9  test    rax, rax
0x18000fdec  jnz     short loc_18000FE02
0x18000fdee  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000fdf5  call    cs:__imp_GetModuleHandleW
0x18000fdfb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fe02  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000fe09  mov     rcx, rax; hModule
0x18000fe0c  call    cs:__imp_GetProcAddress
0x18000fe12  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000fe19  test    rax, rax
0x18000fe1c  jnz     short loc_18000FE2A
0x18000fe1e  mov     edi, 0C0000139h
0x18000fe23  mov     ebx, edi
0x18000fe25  jmp     loc_18000FF57
0x18000fe2a  lea     rax, [rsp+1090h+var_1050]
0x18000fe2f  xor     r8d, r8d
0x18000fe32  mov     [rsp+1090h+var_1068], rax
0x18000fe37  lea     r9, [rsp+1090h+var_104C]
0x18000fe3c  lea     rax, [rsp+1090h+var_1040]
0x18000fe41  xor     edx, edx
0x18000fe43  mov     [rsp+1090h+var_1070], rax
0x18000fe48  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000fe4f  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000fe56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe5b  mov     ebx, eax
0x18000fe5d  mov     edi, eax
0x18000fe5f  test    eax, eax
0x18000fe61  jnz     loc_18000FF57
0x18000fe67  mov     r9d, [rsp+1090h+var_1050]
0x18000fe6c  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000fe76  mov     rax, r11
0x18000fe79  mul     r9
0x18000fe7c  shr     rdx, 3
0x18000fe80  lea     rcx, [rdx+rdx*2]
0x18000fe84  shl     rcx, 2
0x18000fe88  cmp     r9, rcx
0x18000fe8b  jz      short loc_18000FE95
0x18000fe8d  xor     r9d, r9d
0x18000fe90  mov     [rsp+1090h+var_1050], r9d
0x18000fe95  mov     r8, [r14]
0x18000fe98  mov     rax, r11
0x18000fe9b  mov     ecx, r9d
0x18000fe9e  mul     rcx
0x18000fea1  mov     rcx, [r14+8]
0x18000fea5  mov     rax, r11
0x18000fea8  mov     r10, rdx
0x18000feab  sub     rcx, r8
0x18000feae  mul     rcx
0x18000feb1  shr     r10, 3
0x18000feb5  shr     rdx, 3
0x18000feb9  lea     rax, [rdx+rdx*2]
0x18000febd  lea     rsi, [r8+rax*4]
0x18000fec1  jmp     short loc_18000FF2C
0x18000fec3  mov     eax, r10d
0x18000fec6  lea     rcx, [rax+rax*2]
0x18000feca  lea     rdx, [rdx+rcx*4]
0x18000fece  lea     rax, [rsp+1090h+var_1040]
0x18000fed3  cmp     rax, rdx
0x18000fed6  jz      short loc_18000FEFD
0x18000fed8  mov     r11d, [r8]
0x18000fedb  lea     rcx, [rsp+1090h+var_1040]
0x18000fee0  cmp     [rcx], r11d
0x18000fee3  jnz     short loc_18000FEF4
0x18000fee5  movzx   eax, word ptr [r8+4]
0x18000feea  cmp     [rcx+4], ax
0x18000feee  jz      loc_18000FF96
0x18000fef4  add     rcx, 0Ch
0x18000fef8  cmp     rcx, rdx
0x18000fefb  jnz     short loc_18000FEE0
0x18000fefd  mov     eax, r9d
0x18000ff00  add     rax, 0Ch
0x18000ff04  cmp     rax, 1000h
0x18000ff0a  ja      short loc_18000FF28
0x18000ff0c  movsd   xmm0, qword ptr [r8]
0x18000ff11  add     r9d, 0Ch
0x18000ff15  movsd   qword ptr [rdx], xmm0
0x18000ff19  inc     r10d
0x18000ff1c  mov     eax, [r8+8]
0x18000ff20  mov     [rdx+8], eax
0x18000ff23  mov     [rsp+1090h+var_1050], r9d
0x18000ff28  add     r8, 0Ch
0x18000ff2c  lea     rdx, [rsp+1090h+var_1040]
0x18000ff31  cmp     r8, rsi
0x18000ff34  jnz     short loc_18000FEC3
0x18000ff36  mov     eax, [rsp+1090h+var_104C]
0x18000ff3a  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000ff41  mov     [rsp+1090h+var_1060], 1
0x18000ff49  mov     r8d, r9d
0x18000ff4c  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000ff50  call    wil_details_NtUpdateWnfStateData
0x18000ff55  mov     esi, eax
0x18000ff57  cmp     esi, 0C0000001h
0x18000ff5d  jnz     short loc_18000FF70
0x18000ff5f  inc     r15d
0x18000ff62  cmp     r15d, 64h ; 'd'
0x18000ff66  jge     short loc_18000FF70
0x18000ff68  test    edi, edi
0x18000ff6a  jz      loc_18000FDB6
0x18000ff70  test    ebx, ebx
0x18000ff72  cmovz   ebx, esi
0x18000ff75  mov     eax, ebx
0x18000ff77  mov     rcx, [rbp+0F90h+var_40]
0x18000ff7e  xor     rcx, rsp; StackCookie
0x18000ff81  call    __security_check_cookie
0x18000ff86  add     rsp, 1068h
0x18000ff8d  pop     r15
0x18000ff8f  pop     r14
0x18000ff91  pop     rdi
0x18000ff92  pop     rsi
0x18000ff93  pop     rbx
0x18000ff94  pop     rbp
0x18000ff95  retn
0x18000ff96  mov     eax, [r8+8]
0x18000ff9a  add     [rcx+8], eax
0x18000ff9d  mov     r9d, [rsp+1090h+var_1050]
0x18000ffa2  jmp     short loc_18000FF28
```
