# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180012588`
- end: `0x1800127c0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180006ff0`

## callees

- `0x180012588`
- `0x180012ca0`
- `0x1800133e2`
- `0x180013410`
- `0x1800134d0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012611`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012611`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012628`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012628`

## string_xrefs

- `0x18001260a`: `ntdll.dll`

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
0x180012588  push    rbp
0x18001258a  push    rbx
0x18001258b  push    rsi
0x18001258c  push    rdi
0x18001258d  push    r14
0x18001258f  push    r15
0x180012591  lea     rbp, [rsp-0F68h]
0x180012599  mov     eax, 1068h
0x18001259e  call    _alloca_probe
0x1800125a3  sub     rsp, rax
0x1800125a6  mov     rax, cs:__security_cookie
0x1800125ad  xor     rax, rsp
0x1800125b0  mov     [rbp+0F90h+var_40], rax
0x1800125b7  mov     rax, [rcx+8]
0x1800125bb  xor     ebx, ebx
0x1800125bd  sub     rax, [rcx]
0x1800125c0  xor     esi, esi
0x1800125c2  mov     r14, rcx
0x1800125c5  cmp     rax, 0Ch
0x1800125c9  jb      loc_18001278C
0x1800125cf  xor     r15d, r15d
0x1800125d2  xor     edx, edx; Val
0x1800125d4  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800125d9  mov     r8d, 1000h; Size
0x1800125df  call    memset_0
0x1800125e4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x1800125ec  mov     [rsp+1090h+var_1050], 1000h
0x1800125f4  mov     [rsp+1090h+var_104C], 0
0x1800125fc  jnz     short loc_180012646
0x1800125fe  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012605  test    rax, rax
0x180012608  jnz     short loc_18001261E
0x18001260a  lea     rcx, ModuleName; "ntdll.dll"
0x180012611  call    cs:__imp_GetModuleHandleW
0x180012617  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001261e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180012625  mov     rcx, rax; hModule
0x180012628  call    cs:__imp_GetProcAddress
0x18001262e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180012635  test    rax, rax
0x180012638  jnz     short loc_180012646
0x18001263a  mov     edi, 0C0000139h
0x18001263f  mov     ebx, edi
0x180012641  jmp     loc_180012773
0x180012646  lea     rax, [rsp+1090h+var_1050]
0x18001264b  xor     r8d, r8d
0x18001264e  mov     [rsp+1090h+var_1068], rax
0x180012653  lea     r9, [rsp+1090h+var_104C]
0x180012658  lea     rax, [rsp+1090h+var_1040]
0x18001265d  xor     edx, edx
0x18001265f  mov     [rsp+1090h+var_1070], rax
0x180012664  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001266b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180012672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012677  mov     ebx, eax
0x180012679  mov     edi, eax
0x18001267b  test    eax, eax
0x18001267d  jnz     loc_180012773
0x180012683  mov     r9d, [rsp+1090h+var_1050]
0x180012688  mov     r11, 0AAAAAAAAAAAAAAABh
0x180012692  mov     rax, r11
0x180012695  mul     r9
0x180012698  shr     rdx, 3
0x18001269c  lea     rcx, [rdx+rdx*2]
0x1800126a0  shl     rcx, 2
0x1800126a4  cmp     r9, rcx
0x1800126a7  jz      short loc_1800126B1
0x1800126a9  xor     r9d, r9d
0x1800126ac  mov     [rsp+1090h+var_1050], r9d
0x1800126b1  mov     r8, [r14]
0x1800126b4  mov     rax, r11
0x1800126b7  mov     ecx, r9d
0x1800126ba  mul     rcx
0x1800126bd  mov     rcx, [r14+8]
0x1800126c1  mov     rax, r11
0x1800126c4  mov     r10, rdx
0x1800126c7  sub     rcx, r8
0x1800126ca  mul     rcx
0x1800126cd  shr     r10, 3
0x1800126d1  shr     rdx, 3
0x1800126d5  lea     rax, [rdx+rdx*2]
0x1800126d9  lea     rsi, [r8+rax*4]
0x1800126dd  jmp     short loc_180012748
0x1800126df  mov     eax, r10d
0x1800126e2  lea     rcx, [rax+rax*2]
0x1800126e6  lea     rdx, [rdx+rcx*4]
0x1800126ea  lea     rax, [rsp+1090h+var_1040]
0x1800126ef  cmp     rax, rdx
0x1800126f2  jz      short loc_180012719
0x1800126f4  mov     r11d, [r8]
0x1800126f7  lea     rcx, [rsp+1090h+var_1040]
0x1800126fc  cmp     [rcx], r11d
0x1800126ff  jnz     short loc_180012710
0x180012701  movzx   eax, word ptr [r8+4]
0x180012706  cmp     [rcx+4], ax
0x18001270a  jz      loc_1800127B2
0x180012710  add     rcx, 0Ch
0x180012714  cmp     rcx, rdx
0x180012717  jnz     short loc_1800126FC
0x180012719  mov     eax, r9d
0x18001271c  add     rax, 0Ch
0x180012720  cmp     rax, 1000h
0x180012726  ja      short loc_180012744
0x180012728  movsd   xmm0, qword ptr [r8]
0x18001272d  add     r9d, 0Ch
0x180012731  movsd   qword ptr [rdx], xmm0
0x180012735  inc     r10d
0x180012738  mov     eax, [r8+8]
0x18001273c  mov     [rdx+8], eax
0x18001273f  mov     [rsp+1090h+var_1050], r9d
0x180012744  add     r8, 0Ch
0x180012748  lea     rdx, [rsp+1090h+var_1040]
0x18001274d  cmp     r8, rsi
0x180012750  jnz     short loc_1800126DF
0x180012752  mov     eax, [rsp+1090h+var_104C]
0x180012756  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001275d  mov     [rsp+1090h+var_1060], 1
0x180012765  mov     r8d, r9d
0x180012768  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001276c  call    wil_details_NtUpdateWnfStateData
0x180012771  mov     esi, eax
0x180012773  cmp     esi, 0C0000001h
0x180012779  jnz     short loc_18001278C
0x18001277b  inc     r15d
0x18001277e  cmp     r15d, 64h ; 'd'
0x180012782  jge     short loc_18001278C
0x180012784  test    edi, edi
0x180012786  jz      loc_1800125D2
0x18001278c  test    ebx, ebx
0x18001278e  cmovz   ebx, esi
0x180012791  mov     eax, ebx
0x180012793  mov     rcx, [rbp+0F90h+var_40]
0x18001279a  xor     rcx, rsp; StackCookie
0x18001279d  call    __security_check_cookie
0x1800127a2  add     rsp, 1068h
0x1800127a9  pop     r15
0x1800127ab  pop     r14
0x1800127ad  pop     rdi
0x1800127ae  pop     rsi
0x1800127af  pop     rbx
0x1800127b0  pop     rbp
0x1800127b1  retn
0x1800127b2  mov     eax, [r8+8]
0x1800127b6  add     [rcx+8], eax
0x1800127b9  mov     r9d, [rsp+1090h+var_1050]
0x1800127be  jmp     short loc_180012744
```
