# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140016c98`
- end: `0x140016ed0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140012bf0`

## callees

- `0x140016c98`
- `0x140016ed8`
- `0x1400187b2`
- `0x1400187e0`
- `0x1400188a0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140016d38`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140016d38`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140016d21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140016d21`

## string_xrefs

- `0x140016d1a`: `ntdll.dll`

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
0x140016c98  push    rbp
0x140016c9a  push    rbx
0x140016c9b  push    rsi
0x140016c9c  push    rdi
0x140016c9d  push    r14
0x140016c9f  push    r15
0x140016ca1  lea     rbp, [rsp-0F68h]
0x140016ca9  mov     eax, 1068h
0x140016cae  call    _alloca_probe
0x140016cb3  sub     rsp, rax
0x140016cb6  mov     rax, cs:__security_cookie
0x140016cbd  xor     rax, rsp
0x140016cc0  mov     [rbp+0F90h+var_40], rax
0x140016cc7  mov     rax, [rcx+8]
0x140016ccb  xor     ebx, ebx
0x140016ccd  sub     rax, [rcx]
0x140016cd0  xor     esi, esi
0x140016cd2  mov     r14, rcx
0x140016cd5  cmp     rax, 0Ch
0x140016cd9  jb      loc_140016E9C
0x140016cdf  xor     r15d, r15d
0x140016ce2  xor     edx, edx; Val
0x140016ce4  lea     rcx, [rsp+1090h+var_1040]; void *
0x140016ce9  mov     r8d, 1000h; Size
0x140016cef  call    memset_0
0x140016cf4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x140016cfc  mov     [rsp+1090h+var_1050], 1000h
0x140016d04  mov     [rsp+1090h+var_104C], 0
0x140016d0c  jnz     short loc_140016D56
0x140016d0e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140016d15  test    rax, rax
0x140016d18  jnz     short loc_140016D2E
0x140016d1a  lea     rcx, ModuleName; "ntdll.dll"
0x140016d21  call    cs:__imp_GetModuleHandleW
0x140016d27  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140016d2e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140016d35  mov     rcx, rax; hModule
0x140016d38  call    cs:__imp_GetProcAddress
0x140016d3e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140016d45  test    rax, rax
0x140016d48  jnz     short loc_140016D56
0x140016d4a  mov     edi, 0C0000139h
0x140016d4f  mov     ebx, edi
0x140016d51  jmp     loc_140016E83
0x140016d56  lea     rax, [rsp+1090h+var_1050]
0x140016d5b  xor     r8d, r8d
0x140016d5e  mov     [rsp+1090h+var_1068], rax
0x140016d63  lea     r9, [rsp+1090h+var_104C]
0x140016d68  lea     rax, [rsp+1090h+var_1040]
0x140016d6d  xor     edx, edx
0x140016d6f  mov     [rsp+1090h+var_1070], rax
0x140016d74  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140016d7b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140016d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016d87  mov     ebx, eax
0x140016d89  mov     edi, eax
0x140016d8b  test    eax, eax
0x140016d8d  jnz     loc_140016E83
0x140016d93  mov     r9d, [rsp+1090h+var_1050]
0x140016d98  mov     r11, 0AAAAAAAAAAAAAAABh
0x140016da2  mov     rax, r11
0x140016da5  mul     r9
0x140016da8  shr     rdx, 3
0x140016dac  lea     rcx, [rdx+rdx*2]
0x140016db0  shl     rcx, 2
0x140016db4  cmp     r9, rcx
0x140016db7  jz      short loc_140016DC1
0x140016db9  xor     r9d, r9d
0x140016dbc  mov     [rsp+1090h+var_1050], r9d
0x140016dc1  mov     r8, [r14]
0x140016dc4  mov     rax, r11
0x140016dc7  mov     ecx, r9d
0x140016dca  mul     rcx
0x140016dcd  mov     rcx, [r14+8]
0x140016dd1  mov     rax, r11
0x140016dd4  mov     r10, rdx
0x140016dd7  sub     rcx, r8
0x140016dda  mul     rcx
0x140016ddd  shr     r10, 3
0x140016de1  shr     rdx, 3
0x140016de5  lea     rax, [rdx+rdx*2]
0x140016de9  lea     rsi, [r8+rax*4]
0x140016ded  jmp     short loc_140016E58
0x140016def  mov     eax, r10d
0x140016df2  lea     rcx, [rax+rax*2]
0x140016df6  lea     rdx, [rdx+rcx*4]
0x140016dfa  lea     rax, [rsp+1090h+var_1040]
0x140016dff  cmp     rax, rdx
0x140016e02  jz      short loc_140016E29
0x140016e04  mov     r11d, [r8]
0x140016e07  lea     rcx, [rsp+1090h+var_1040]
0x140016e0c  cmp     [rcx], r11d
0x140016e0f  jnz     short loc_140016E20
0x140016e11  movzx   eax, word ptr [r8+4]
0x140016e16  cmp     [rcx+4], ax
0x140016e1a  jz      loc_140016EC2
0x140016e20  add     rcx, 0Ch
0x140016e24  cmp     rcx, rdx
0x140016e27  jnz     short loc_140016E0C
0x140016e29  mov     eax, r9d
0x140016e2c  add     rax, 0Ch
0x140016e30  cmp     rax, 1000h
0x140016e36  ja      short loc_140016E54
0x140016e38  movsd   xmm0, qword ptr [r8]
0x140016e3d  add     r9d, 0Ch
0x140016e41  movsd   qword ptr [rdx], xmm0
0x140016e45  inc     r10d
0x140016e48  mov     eax, [r8+8]
0x140016e4c  mov     [rdx+8], eax
0x140016e4f  mov     [rsp+1090h+var_1050], r9d
0x140016e54  add     r8, 0Ch
0x140016e58  lea     rdx, [rsp+1090h+var_1040]
0x140016e5d  cmp     r8, rsi
0x140016e60  jnz     short loc_140016DEF
0x140016e62  mov     eax, [rsp+1090h+var_104C]
0x140016e66  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140016e6d  mov     [rsp+1090h+var_1060], 1
0x140016e75  mov     r8d, r9d
0x140016e78  mov     dword ptr [rsp+1090h+var_1068], eax
0x140016e7c  call    wil_details_NtUpdateWnfStateData
0x140016e81  mov     esi, eax
0x140016e83  cmp     esi, 0C0000001h
0x140016e89  jnz     short loc_140016E9C
0x140016e8b  inc     r15d
0x140016e8e  cmp     r15d, 64h ; 'd'
0x140016e92  jge     short loc_140016E9C
0x140016e94  test    edi, edi
0x140016e96  jz      loc_140016CE2
0x140016e9c  test    ebx, ebx
0x140016e9e  cmovz   ebx, esi
0x140016ea1  mov     eax, ebx
0x140016ea3  mov     rcx, [rbp+0F90h+var_40]
0x140016eaa  xor     rcx, rsp; StackCookie
0x140016ead  call    __security_check_cookie
0x140016eb2  add     rsp, 1068h
0x140016eb9  pop     r15
0x140016ebb  pop     r14
0x140016ebd  pop     rdi
0x140016ebe  pop     rsi
0x140016ebf  pop     rbx
0x140016ec0  pop     rbp
0x140016ec1  retn
0x140016ec2  mov     eax, [r8+8]
0x140016ec6  add     [rcx+8], eax
0x140016ec9  mov     r9d, [rsp+1090h+var_1050]
0x140016ece  jmp     short loc_140016E54
```
