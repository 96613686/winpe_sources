# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140014188`
- end: `0x1400143c0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x14000d350`

## callees

- `0x140002f60`
- `0x140003b28`
- `0x140014188`
- `0x140014650`
- `0x14003bcc0`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014228`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014228`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140014211`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140014211`

## string_xrefs

- `0x14001420a`: `ntdll.dll`

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
0x140014188  push    rbp
0x14001418a  push    rbx
0x14001418b  push    rsi
0x14001418c  push    rdi
0x14001418d  push    r14
0x14001418f  push    r15
0x140014191  lea     rbp, [rsp-0F68h]
0x140014199  mov     eax, 1068h
0x14001419e  call    _alloca_probe
0x1400141a3  sub     rsp, rax
0x1400141a6  mov     rax, cs:__security_cookie
0x1400141ad  xor     rax, rsp
0x1400141b0  mov     [rbp+0F90h+var_40], rax
0x1400141b7  mov     rax, [rcx+8]
0x1400141bb  xor     ebx, ebx
0x1400141bd  sub     rax, [rcx]
0x1400141c0  xor     esi, esi
0x1400141c2  mov     r14, rcx
0x1400141c5  cmp     rax, 0Ch
0x1400141c9  jb      loc_14001438C
0x1400141cf  xor     r15d, r15d
0x1400141d2  xor     edx, edx; Val
0x1400141d4  lea     rcx, [rsp+1090h+var_1040]; void *
0x1400141d9  mov     r8d, 1000h; Size
0x1400141df  call    memset_0
0x1400141e4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x1400141ec  mov     [rsp+1090h+var_1050], 1000h
0x1400141f4  mov     [rsp+1090h+var_104C], 0
0x1400141fc  jnz     short loc_140014246
0x1400141fe  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140014205  test    rax, rax
0x140014208  jnz     short loc_14001421E
0x14001420a  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140014211  call    cs:__imp_GetModuleHandleW
0x140014217  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001421e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140014225  mov     rcx, rax; hModule
0x140014228  call    cs:__imp_GetProcAddress
0x14001422e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140014235  test    rax, rax
0x140014238  jnz     short loc_140014246
0x14001423a  mov     edi, 0C0000139h
0x14001423f  mov     ebx, edi
0x140014241  jmp     loc_140014373
0x140014246  lea     rax, [rsp+1090h+var_1050]
0x14001424b  xor     r8d, r8d
0x14001424e  mov     [rsp+1090h+var_1068], rax
0x140014253  lea     r9, [rsp+1090h+var_104C]
0x140014258  lea     rax, [rsp+1090h+var_1040]
0x14001425d  xor     edx, edx
0x14001425f  mov     [rsp+1090h+var_1070], rax
0x140014264  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14001426b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140014272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014277  mov     ebx, eax
0x140014279  mov     edi, eax
0x14001427b  test    eax, eax
0x14001427d  jnz     loc_140014373
0x140014283  mov     r9d, [rsp+1090h+var_1050]
0x140014288  mov     r11, 0AAAAAAAAAAAAAAABh
0x140014292  mov     rax, r11
0x140014295  mul     r9
0x140014298  shr     rdx, 3
0x14001429c  lea     rcx, [rdx+rdx*2]
0x1400142a0  shl     rcx, 2
0x1400142a4  cmp     r9, rcx
0x1400142a7  jz      short loc_1400142B1
0x1400142a9  xor     r9d, r9d
0x1400142ac  mov     [rsp+1090h+var_1050], r9d
0x1400142b1  mov     r8, [r14]
0x1400142b4  mov     rax, r11
0x1400142b7  mov     ecx, r9d
0x1400142ba  mul     rcx
0x1400142bd  mov     rcx, [r14+8]
0x1400142c1  mov     rax, r11
0x1400142c4  mov     r10, rdx
0x1400142c7  sub     rcx, r8
0x1400142ca  mul     rcx
0x1400142cd  shr     r10, 3
0x1400142d1  shr     rdx, 3
0x1400142d5  lea     rax, [rdx+rdx*2]
0x1400142d9  lea     rsi, [r8+rax*4]
0x1400142dd  jmp     short loc_140014348
0x1400142df  mov     eax, r10d
0x1400142e2  lea     rcx, [rax+rax*2]
0x1400142e6  lea     rdx, [rdx+rcx*4]
0x1400142ea  lea     rax, [rsp+1090h+var_1040]
0x1400142ef  cmp     rax, rdx
0x1400142f2  jz      short loc_140014319
0x1400142f4  mov     r11d, [r8]
0x1400142f7  lea     rcx, [rsp+1090h+var_1040]
0x1400142fc  cmp     [rcx], r11d
0x1400142ff  jnz     short loc_140014310
0x140014301  movzx   eax, word ptr [r8+4]
0x140014306  cmp     [rcx+4], ax
0x14001430a  jz      loc_1400143B2
0x140014310  add     rcx, 0Ch
0x140014314  cmp     rcx, rdx
0x140014317  jnz     short loc_1400142FC
0x140014319  mov     eax, r9d
0x14001431c  add     rax, 0Ch
0x140014320  cmp     rax, 1000h
0x140014326  ja      short loc_140014344
0x140014328  movsd   xmm0, qword ptr [r8]
0x14001432d  add     r9d, 0Ch
0x140014331  movsd   qword ptr [rdx], xmm0
0x140014335  inc     r10d
0x140014338  mov     eax, [r8+8]
0x14001433c  mov     [rdx+8], eax
0x14001433f  mov     [rsp+1090h+var_1050], r9d
0x140014344  add     r8, 0Ch
0x140014348  lea     rdx, [rsp+1090h+var_1040]
0x14001434d  cmp     r8, rsi
0x140014350  jnz     short loc_1400142DF
0x140014352  mov     eax, [rsp+1090h+var_104C]
0x140014356  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14001435d  mov     [rsp+1090h+var_1060], 1
0x140014365  mov     r8d, r9d
0x140014368  mov     dword ptr [rsp+1090h+var_1068], eax
0x14001436c  call    wil_details_NtUpdateWnfStateData
0x140014371  mov     esi, eax
0x140014373  cmp     esi, 0C0000001h
0x140014379  jnz     short loc_14001438C
0x14001437b  inc     r15d
0x14001437e  cmp     r15d, 64h ; 'd'
0x140014382  jge     short loc_14001438C
0x140014384  test    edi, edi
0x140014386  jz      loc_1400141D2
0x14001438c  test    ebx, ebx
0x14001438e  cmovz   ebx, esi
0x140014391  mov     eax, ebx
0x140014393  mov     rcx, [rbp+0F90h+var_40]
0x14001439a  xor     rcx, rsp; StackCookie
0x14001439d  call    __security_check_cookie
0x1400143a2  add     rsp, 1068h
0x1400143a9  pop     r15
0x1400143ab  pop     r14
0x1400143ad  pop     rdi
0x1400143ae  pop     rsi
0x1400143af  pop     rbx
0x1400143b0  pop     rbp
0x1400143b1  retn
0x1400143b2  mov     eax, [r8+8]
0x1400143b6  add     [rcx+8], eax
0x1400143b9  mov     r9d, [rsp+1090h+var_1050]
0x1400143be  jmp     short loc_140014344
```
