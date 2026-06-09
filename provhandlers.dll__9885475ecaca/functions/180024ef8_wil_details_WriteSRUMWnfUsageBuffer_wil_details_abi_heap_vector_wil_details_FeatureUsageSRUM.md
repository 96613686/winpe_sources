# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180024ef8`
- end: `0x180025130`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180015a50`

## callees

- `0x180024ef8`
- `0x180025610`
- `0x18003b96a`
- `0x18003b9a0`
- `0x18003ba60`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024f81`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024f81`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024f98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024f98`

## string_xrefs

- `0x180024f7a`: `ntdll.dll`

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
0x180024ef8  push    rbp
0x180024efa  push    rbx
0x180024efb  push    rsi
0x180024efc  push    rdi
0x180024efd  push    r14
0x180024eff  push    r15
0x180024f01  lea     rbp, [rsp-0F68h]
0x180024f09  mov     eax, 1068h
0x180024f0e  call    _alloca_probe
0x180024f13  sub     rsp, rax
0x180024f16  mov     rax, cs:__security_cookie
0x180024f1d  xor     rax, rsp
0x180024f20  mov     [rbp+0F90h+var_40], rax
0x180024f27  mov     rax, [rcx+8]
0x180024f2b  xor     ebx, ebx
0x180024f2d  sub     rax, [rcx]
0x180024f30  xor     esi, esi
0x180024f32  mov     r14, rcx
0x180024f35  cmp     rax, 0Ch
0x180024f39  jb      loc_1800250FC
0x180024f3f  xor     r15d, r15d
0x180024f42  xor     edx, edx; Val
0x180024f44  lea     rcx, [rsp+1090h+var_1040]; void *
0x180024f49  mov     r8d, 1000h; Size
0x180024f4f  call    memset_0
0x180024f54  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180024f5c  mov     [rsp+1090h+var_1050], 1000h
0x180024f64  mov     [rsp+1090h+var_104C], 0
0x180024f6c  jnz     short loc_180024FB6
0x180024f6e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180024f75  test    rax, rax
0x180024f78  jnz     short loc_180024F8E
0x180024f7a  lea     rcx, ModuleName; "ntdll.dll"
0x180024f81  call    cs:__imp_GetModuleHandleW
0x180024f87  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180024f8e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180024f95  mov     rcx, rax; hModule
0x180024f98  call    cs:__imp_GetProcAddress
0x180024f9e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180024fa5  test    rax, rax
0x180024fa8  jnz     short loc_180024FB6
0x180024faa  mov     edi, 0C0000139h
0x180024faf  mov     ebx, edi
0x180024fb1  jmp     loc_1800250E3
0x180024fb6  lea     rax, [rsp+1090h+var_1050]
0x180024fbb  xor     r8d, r8d
0x180024fbe  mov     [rsp+1090h+var_1068], rax
0x180024fc3  lea     r9, [rsp+1090h+var_104C]
0x180024fc8  lea     rax, [rsp+1090h+var_1040]
0x180024fcd  xor     edx, edx
0x180024fcf  mov     [rsp+1090h+var_1070], rax
0x180024fd4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180024fdb  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180024fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fe7  mov     ebx, eax
0x180024fe9  mov     edi, eax
0x180024feb  test    eax, eax
0x180024fed  jnz     loc_1800250E3
0x180024ff3  mov     r9d, [rsp+1090h+var_1050]
0x180024ff8  mov     r11, 0AAAAAAAAAAAAAAABh
0x180025002  mov     rax, r11
0x180025005  mul     r9
0x180025008  shr     rdx, 3
0x18002500c  lea     rcx, [rdx+rdx*2]
0x180025010  shl     rcx, 2
0x180025014  cmp     r9, rcx
0x180025017  jz      short loc_180025021
0x180025019  xor     r9d, r9d
0x18002501c  mov     [rsp+1090h+var_1050], r9d
0x180025021  mov     r8, [r14]
0x180025024  mov     rax, r11
0x180025027  mov     ecx, r9d
0x18002502a  mul     rcx
0x18002502d  mov     rcx, [r14+8]
0x180025031  mov     rax, r11
0x180025034  mov     r10, rdx
0x180025037  sub     rcx, r8
0x18002503a  mul     rcx
0x18002503d  shr     r10, 3
0x180025041  shr     rdx, 3
0x180025045  lea     rax, [rdx+rdx*2]
0x180025049  lea     rsi, [r8+rax*4]
0x18002504d  jmp     short loc_1800250B8
0x18002504f  mov     eax, r10d
0x180025052  lea     rcx, [rax+rax*2]
0x180025056  lea     rdx, [rdx+rcx*4]
0x18002505a  lea     rax, [rsp+1090h+var_1040]
0x18002505f  cmp     rax, rdx
0x180025062  jz      short loc_180025089
0x180025064  mov     r11d, [r8]
0x180025067  lea     rcx, [rsp+1090h+var_1040]
0x18002506c  cmp     [rcx], r11d
0x18002506f  jnz     short loc_180025080
0x180025071  movzx   eax, word ptr [r8+4]
0x180025076  cmp     [rcx+4], ax
0x18002507a  jz      loc_180025122
0x180025080  add     rcx, 0Ch
0x180025084  cmp     rcx, rdx
0x180025087  jnz     short loc_18002506C
0x180025089  mov     eax, r9d
0x18002508c  add     rax, 0Ch
0x180025090  cmp     rax, 1000h
0x180025096  ja      short loc_1800250B4
0x180025098  movsd   xmm0, qword ptr [r8]
0x18002509d  add     r9d, 0Ch
0x1800250a1  movsd   qword ptr [rdx], xmm0
0x1800250a5  inc     r10d
0x1800250a8  mov     eax, [r8+8]
0x1800250ac  mov     [rdx+8], eax
0x1800250af  mov     [rsp+1090h+var_1050], r9d
0x1800250b4  add     r8, 0Ch
0x1800250b8  lea     rdx, [rsp+1090h+var_1040]
0x1800250bd  cmp     r8, rsi
0x1800250c0  jnz     short loc_18002504F
0x1800250c2  mov     eax, [rsp+1090h+var_104C]
0x1800250c6  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800250cd  mov     [rsp+1090h+var_1060], 1
0x1800250d5  mov     r8d, r9d
0x1800250d8  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800250dc  call    wil_details_NtUpdateWnfStateData
0x1800250e1  mov     esi, eax
0x1800250e3  cmp     esi, 0C0000001h
0x1800250e9  jnz     short loc_1800250FC
0x1800250eb  inc     r15d
0x1800250ee  cmp     r15d, 64h ; 'd'
0x1800250f2  jge     short loc_1800250FC
0x1800250f4  test    edi, edi
0x1800250f6  jz      loc_180024F42
0x1800250fc  test    ebx, ebx
0x1800250fe  cmovz   ebx, esi
0x180025101  mov     eax, ebx
0x180025103  mov     rcx, [rbp+0F90h+var_40]
0x18002510a  xor     rcx, rsp; StackCookie
0x18002510d  call    __security_check_cookie
0x180025112  add     rsp, 1068h
0x180025119  pop     r15
0x18002511b  pop     r14
0x18002511d  pop     rdi
0x18002511e  pop     rsi
0x18002511f  pop     rbx
0x180025120  pop     rbp
0x180025121  retn
0x180025122  mov     eax, [r8+8]
0x180025126  add     [rcx+8], eax
0x180025129  mov     r9d, [rsp+1090h+var_1050]
0x18002512e  jmp     short loc_1800250B4
```
