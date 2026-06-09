# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000a9c8`
- end: `0x18000ac00`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800035e0`

## callees

- `0x1800024a0`
- `0x180003320`
- `0x18000a9c8`
- `0x18000ae90`
- `0x180015650`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aa68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aa68`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aa51`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aa51`

## string_xrefs

- `0x18000aa4a`: `ntdll.dll`

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
0x18000a9c8  push    rbp
0x18000a9ca  push    rbx
0x18000a9cb  push    rsi
0x18000a9cc  push    rdi
0x18000a9cd  push    r14
0x18000a9cf  push    r15
0x18000a9d1  lea     rbp, [rsp-0F68h]
0x18000a9d9  mov     eax, 1068h
0x18000a9de  call    _alloca_probe
0x18000a9e3  sub     rsp, rax
0x18000a9e6  mov     rax, cs:__security_cookie
0x18000a9ed  xor     rax, rsp
0x18000a9f0  mov     [rbp+0F90h+var_40], rax
0x18000a9f7  mov     rax, [rcx+8]
0x18000a9fb  xor     ebx, ebx
0x18000a9fd  sub     rax, [rcx]
0x18000aa00  xor     esi, esi
0x18000aa02  mov     r14, rcx
0x18000aa05  cmp     rax, 0Ch
0x18000aa09  jb      loc_18000ABCC
0x18000aa0f  xor     r15d, r15d
0x18000aa12  xor     edx, edx; Val
0x18000aa14  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000aa19  mov     r8d, 1000h; Size
0x18000aa1f  call    memset_0
0x18000aa24  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000aa2c  mov     [rsp+1090h+var_1050], 1000h
0x18000aa34  mov     [rsp+1090h+var_104C], 0
0x18000aa3c  jnz     short loc_18000AA86
0x18000aa3e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000aa45  test    rax, rax
0x18000aa48  jnz     short loc_18000AA5E
0x18000aa4a  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000aa51  call    cs:__imp_GetModuleHandleW
0x18000aa57  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000aa5e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000aa65  mov     rcx, rax; hModule
0x18000aa68  call    cs:__imp_GetProcAddress
0x18000aa6e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000aa75  test    rax, rax
0x18000aa78  jnz     short loc_18000AA86
0x18000aa7a  mov     edi, 0C0000139h
0x18000aa7f  mov     ebx, edi
0x18000aa81  jmp     loc_18000ABB3
0x18000aa86  lea     rax, [rsp+1090h+var_1050]
0x18000aa8b  xor     r8d, r8d
0x18000aa8e  mov     [rsp+1090h+var_1068], rax
0x18000aa93  lea     r9, [rsp+1090h+var_104C]
0x18000aa98  lea     rax, [rsp+1090h+var_1040]
0x18000aa9d  xor     edx, edx
0x18000aa9f  mov     [rsp+1090h+var_1070], rax
0x18000aaa4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000aaab  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000aab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aab7  mov     ebx, eax
0x18000aab9  mov     edi, eax
0x18000aabb  test    eax, eax
0x18000aabd  jnz     loc_18000ABB3
0x18000aac3  mov     r9d, [rsp+1090h+var_1050]
0x18000aac8  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000aad2  mov     rax, r11
0x18000aad5  mul     r9
0x18000aad8  shr     rdx, 3
0x18000aadc  lea     rcx, [rdx+rdx*2]
0x18000aae0  shl     rcx, 2
0x18000aae4  cmp     r9, rcx
0x18000aae7  jz      short loc_18000AAF1
0x18000aae9  xor     r9d, r9d
0x18000aaec  mov     [rsp+1090h+var_1050], r9d
0x18000aaf1  mov     r8, [r14]
0x18000aaf4  mov     rax, r11
0x18000aaf7  mov     ecx, r9d
0x18000aafa  mul     rcx
0x18000aafd  mov     rcx, [r14+8]
0x18000ab01  mov     rax, r11
0x18000ab04  mov     r10, rdx
0x18000ab07  sub     rcx, r8
0x18000ab0a  mul     rcx
0x18000ab0d  shr     r10, 3
0x18000ab11  shr     rdx, 3
0x18000ab15  lea     rax, [rdx+rdx*2]
0x18000ab19  lea     rsi, [r8+rax*4]
0x18000ab1d  jmp     short loc_18000AB88
0x18000ab1f  mov     eax, r10d
0x18000ab22  lea     rcx, [rax+rax*2]
0x18000ab26  lea     rdx, [rdx+rcx*4]
0x18000ab2a  lea     rax, [rsp+1090h+var_1040]
0x18000ab2f  cmp     rax, rdx
0x18000ab32  jz      short loc_18000AB59
0x18000ab34  mov     r11d, [r8]
0x18000ab37  lea     rcx, [rsp+1090h+var_1040]
0x18000ab3c  cmp     [rcx], r11d
0x18000ab3f  jnz     short loc_18000AB50
0x18000ab41  movzx   eax, word ptr [r8+4]
0x18000ab46  cmp     [rcx+4], ax
0x18000ab4a  jz      loc_18000ABF2
0x18000ab50  add     rcx, 0Ch
0x18000ab54  cmp     rcx, rdx
0x18000ab57  jnz     short loc_18000AB3C
0x18000ab59  mov     eax, r9d
0x18000ab5c  add     rax, 0Ch
0x18000ab60  cmp     rax, 1000h
0x18000ab66  ja      short loc_18000AB84
0x18000ab68  movsd   xmm0, qword ptr [r8]
0x18000ab6d  add     r9d, 0Ch
0x18000ab71  movsd   qword ptr [rdx], xmm0
0x18000ab75  inc     r10d
0x18000ab78  mov     eax, [r8+8]
0x18000ab7c  mov     [rdx+8], eax
0x18000ab7f  mov     [rsp+1090h+var_1050], r9d
0x18000ab84  add     r8, 0Ch
0x18000ab88  lea     rdx, [rsp+1090h+var_1040]
0x18000ab8d  cmp     r8, rsi
0x18000ab90  jnz     short loc_18000AB1F
0x18000ab92  mov     eax, [rsp+1090h+var_104C]
0x18000ab96  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000ab9d  mov     [rsp+1090h+var_1060], 1
0x18000aba5  mov     r8d, r9d
0x18000aba8  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000abac  call    wil_details_NtUpdateWnfStateData
0x18000abb1  mov     esi, eax
0x18000abb3  cmp     esi, 0C0000001h
0x18000abb9  jnz     short loc_18000ABCC
0x18000abbb  inc     r15d
0x18000abbe  cmp     r15d, 64h ; 'd'
0x18000abc2  jge     short loc_18000ABCC
0x18000abc4  test    edi, edi
0x18000abc6  jz      loc_18000AA12
0x18000abcc  test    ebx, ebx
0x18000abce  cmovz   ebx, esi
0x18000abd1  mov     eax, ebx
0x18000abd3  mov     rcx, [rbp+0F90h+var_40]
0x18000abda  xor     rcx, rsp; StackCookie
0x18000abdd  call    __security_check_cookie
0x18000abe2  add     rsp, 1068h
0x18000abe9  pop     r15
0x18000abeb  pop     r14
0x18000abed  pop     rdi
0x18000abee  pop     rsi
0x18000abef  pop     rbx
0x18000abf0  pop     rbp
0x18000abf1  retn
0x18000abf2  mov     eax, [r8+8]
0x18000abf6  add     [rcx+8], eax
0x18000abf9  mov     r9d, [rsp+1090h+var_1050]
0x18000abfe  jmp     short loc_18000AB84
```
