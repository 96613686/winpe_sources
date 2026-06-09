# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800190c8`
- end: `0x180019300`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180003c20`

## callees

- `0x180002e50`
- `0x180003940`
- `0x1800190c8`
- `0x180019c48`
- `0x180020830`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180019151`
- `KERNEL32!GetModuleHandleW` at `0x180019151`
- `KERNEL32!GetProcAddress` at `0x180019168`
- `KERNEL32!GetProcAddress` at `0x180019168`

## string_xrefs

- `0x18001914a`: `ntdll.dll`

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
0x1800190c8  push    rbp
0x1800190ca  push    rbx
0x1800190cb  push    rsi
0x1800190cc  push    rdi
0x1800190cd  push    r14
0x1800190cf  push    r15
0x1800190d1  lea     rbp, [rsp-0F68h]
0x1800190d9  mov     eax, 1068h
0x1800190de  call    _alloca_probe
0x1800190e3  sub     rsp, rax
0x1800190e6  mov     rax, cs:__security_cookie
0x1800190ed  xor     rax, rsp
0x1800190f0  mov     [rbp+0F90h+var_40], rax
0x1800190f7  mov     rax, [rcx+8]
0x1800190fb  xor     ebx, ebx
0x1800190fd  sub     rax, [rcx]
0x180019100  xor     esi, esi
0x180019102  mov     r14, rcx
0x180019105  cmp     rax, 0Ch
0x180019109  jb      loc_1800192CC
0x18001910f  xor     r15d, r15d
0x180019112  xor     edx, edx; Val
0x180019114  lea     rcx, [rsp+1090h+var_1040]; void *
0x180019119  mov     r8d, 1000h; Size
0x18001911f  call    memset_0
0x180019124  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18001912c  mov     [rsp+1090h+var_1050], 1000h
0x180019134  mov     [rsp+1090h+var_104C], 0
0x18001913c  jnz     short loc_180019186
0x18001913e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180019145  test    rax, rax
0x180019148  jnz     short loc_18001915E
0x18001914a  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180019151  call    cs:__imp_GetModuleHandleW
0x180019157  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001915e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180019165  mov     rcx, rax; hModule
0x180019168  call    cs:__imp_GetProcAddress
0x18001916e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180019175  test    rax, rax
0x180019178  jnz     short loc_180019186
0x18001917a  mov     edi, 0C0000139h
0x18001917f  mov     ebx, edi
0x180019181  jmp     loc_1800192B3
0x180019186  lea     rax, [rsp+1090h+var_1050]
0x18001918b  xor     r8d, r8d
0x18001918e  mov     [rsp+1090h+var_1068], rax
0x180019193  lea     r9, [rsp+1090h+var_104C]
0x180019198  lea     rax, [rsp+1090h+var_1040]
0x18001919d  xor     edx, edx
0x18001919f  mov     [rsp+1090h+var_1070], rax
0x1800191a4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800191ab  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800191b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191b7  mov     ebx, eax
0x1800191b9  mov     edi, eax
0x1800191bb  test    eax, eax
0x1800191bd  jnz     loc_1800192B3
0x1800191c3  mov     r9d, [rsp+1090h+var_1050]
0x1800191c8  mov     r11, 0AAAAAAAAAAAAAAABh
0x1800191d2  mov     rax, r11
0x1800191d5  mul     r9
0x1800191d8  shr     rdx, 3
0x1800191dc  lea     rcx, [rdx+rdx*2]
0x1800191e0  shl     rcx, 2
0x1800191e4  cmp     r9, rcx
0x1800191e7  jz      short loc_1800191F1
0x1800191e9  xor     r9d, r9d
0x1800191ec  mov     [rsp+1090h+var_1050], r9d
0x1800191f1  mov     r8, [r14]
0x1800191f4  mov     rax, r11
0x1800191f7  mov     ecx, r9d
0x1800191fa  mul     rcx
0x1800191fd  mov     rcx, [r14+8]
0x180019201  mov     rax, r11
0x180019204  mov     r10, rdx
0x180019207  sub     rcx, r8
0x18001920a  mul     rcx
0x18001920d  shr     r10, 3
0x180019211  shr     rdx, 3
0x180019215  lea     rax, [rdx+rdx*2]
0x180019219  lea     rsi, [r8+rax*4]
0x18001921d  jmp     short loc_180019288
0x18001921f  mov     eax, r10d
0x180019222  lea     rcx, [rax+rax*2]
0x180019226  lea     rdx, [rdx+rcx*4]
0x18001922a  lea     rax, [rsp+1090h+var_1040]
0x18001922f  cmp     rax, rdx
0x180019232  jz      short loc_180019259
0x180019234  mov     r11d, [r8]
0x180019237  lea     rcx, [rsp+1090h+var_1040]
0x18001923c  cmp     [rcx], r11d
0x18001923f  jnz     short loc_180019250
0x180019241  movzx   eax, word ptr [r8+4]
0x180019246  cmp     [rcx+4], ax
0x18001924a  jz      loc_1800192F2
0x180019250  add     rcx, 0Ch
0x180019254  cmp     rcx, rdx
0x180019257  jnz     short loc_18001923C
0x180019259  mov     eax, r9d
0x18001925c  add     rax, 0Ch
0x180019260  cmp     rax, 1000h
0x180019266  ja      short loc_180019284
0x180019268  movsd   xmm0, qword ptr [r8]
0x18001926d  add     r9d, 0Ch
0x180019271  movsd   qword ptr [rdx], xmm0
0x180019275  inc     r10d
0x180019278  mov     eax, [r8+8]
0x18001927c  mov     [rdx+8], eax
0x18001927f  mov     [rsp+1090h+var_1050], r9d
0x180019284  add     r8, 0Ch
0x180019288  lea     rdx, [rsp+1090h+var_1040]
0x18001928d  cmp     r8, rsi
0x180019290  jnz     short loc_18001921F
0x180019292  mov     eax, [rsp+1090h+var_104C]
0x180019296  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001929d  mov     [rsp+1090h+var_1060], 1
0x1800192a5  mov     r8d, r9d
0x1800192a8  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800192ac  call    wil_details_NtUpdateWnfStateData
0x1800192b1  mov     esi, eax
0x1800192b3  cmp     esi, 0C0000001h
0x1800192b9  jnz     short loc_1800192CC
0x1800192bb  inc     r15d
0x1800192be  cmp     r15d, 64h ; 'd'
0x1800192c2  jge     short loc_1800192CC
0x1800192c4  test    edi, edi
0x1800192c6  jz      loc_180019112
0x1800192cc  test    ebx, ebx
0x1800192ce  cmovz   ebx, esi
0x1800192d1  mov     eax, ebx
0x1800192d3  mov     rcx, [rbp+0F90h+var_40]
0x1800192da  xor     rcx, rsp; StackCookie
0x1800192dd  call    __security_check_cookie
0x1800192e2  add     rsp, 1068h
0x1800192e9  pop     r15
0x1800192eb  pop     r14
0x1800192ed  pop     rdi
0x1800192ee  pop     rsi
0x1800192ef  pop     rbx
0x1800192f0  pop     rbp
0x1800192f1  retn
0x1800192f2  mov     eax, [r8+8]
0x1800192f6  add     [rcx+8], eax
0x1800192f9  mov     r9d, [rsp+1090h+var_1050]
0x1800192fe  jmp     short loc_180019284
```
