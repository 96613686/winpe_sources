# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001172c`
- end: `0x180011964`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c860`

## callees

- `0x18001172c`
- `0x180011b60`
- `0x18001200e`
- `0x180012040`
- `0x1800120d0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800117cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800117cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800117b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800117b5`

## string_xrefs

- `0x1800117ae`: `ntdll.dll`

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
0x18001172c  push    rbp
0x18001172e  push    rbx
0x18001172f  push    rsi
0x180011730  push    rdi
0x180011731  push    r14
0x180011733  push    r15
0x180011735  lea     rbp, [rsp-0F68h]
0x18001173d  mov     eax, 1068h
0x180011742  call    _alloca_probe
0x180011747  sub     rsp, rax
0x18001174a  mov     rax, cs:__security_cookie
0x180011751  xor     rax, rsp
0x180011754  mov     [rbp+0F90h+var_40], rax
0x18001175b  mov     rax, [rcx+8]
0x18001175f  xor     ebx, ebx
0x180011761  sub     rax, [rcx]
0x180011764  xor     esi, esi
0x180011766  mov     r14, rcx
0x180011769  cmp     rax, 0Ch
0x18001176d  jb      loc_180011930
0x180011773  xor     r15d, r15d
0x180011776  xor     edx, edx; Val
0x180011778  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001177d  mov     r8d, 1000h; Size
0x180011783  call    memset_0
0x180011788  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180011790  mov     [rsp+1090h+var_1050], 1000h
0x180011798  mov     [rsp+1090h+var_104C], 0
0x1800117a0  jnz     short loc_1800117EA
0x1800117a2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800117a9  test    rax, rax
0x1800117ac  jnz     short loc_1800117C2
0x1800117ae  lea     rcx, ModuleName; "ntdll.dll"
0x1800117b5  call    cs:__imp_GetModuleHandleW
0x1800117bb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800117c2  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800117c9  mov     rcx, rax; hModule
0x1800117cc  call    cs:__imp_GetProcAddress
0x1800117d2  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800117d9  test    rax, rax
0x1800117dc  jnz     short loc_1800117EA
0x1800117de  mov     edi, 0C0000139h
0x1800117e3  mov     ebx, edi
0x1800117e5  jmp     loc_180011917
0x1800117ea  lea     rax, [rsp+1090h+var_1050]
0x1800117ef  xor     r8d, r8d
0x1800117f2  mov     [rsp+1090h+var_1068], rax
0x1800117f7  lea     r9, [rsp+1090h+var_104C]
0x1800117fc  lea     rax, [rsp+1090h+var_1040]
0x180011801  xor     edx, edx
0x180011803  mov     [rsp+1090h+var_1070], rax
0x180011808  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001180f  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180011816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001181b  mov     ebx, eax
0x18001181d  mov     edi, eax
0x18001181f  test    eax, eax
0x180011821  jnz     loc_180011917
0x180011827  mov     r9d, [rsp+1090h+var_1050]
0x18001182c  mov     r11, 0AAAAAAAAAAAAAAABh
0x180011836  mov     rax, r11
0x180011839  mul     r9
0x18001183c  shr     rdx, 3
0x180011840  lea     rcx, [rdx+rdx*2]
0x180011844  shl     rcx, 2
0x180011848  cmp     r9, rcx
0x18001184b  jz      short loc_180011855
0x18001184d  xor     r9d, r9d
0x180011850  mov     [rsp+1090h+var_1050], r9d
0x180011855  mov     r8, [r14]
0x180011858  mov     rax, r11
0x18001185b  mov     ecx, r9d
0x18001185e  mul     rcx
0x180011861  mov     rcx, [r14+8]
0x180011865  mov     rax, r11
0x180011868  mov     r10, rdx
0x18001186b  sub     rcx, r8
0x18001186e  mul     rcx
0x180011871  shr     r10, 3
0x180011875  shr     rdx, 3
0x180011879  lea     rax, [rdx+rdx*2]
0x18001187d  lea     rsi, [r8+rax*4]
0x180011881  jmp     short loc_1800118EC
0x180011883  mov     eax, r10d
0x180011886  lea     rcx, [rax+rax*2]
0x18001188a  lea     rdx, [rdx+rcx*4]
0x18001188e  lea     rax, [rsp+1090h+var_1040]
0x180011893  cmp     rax, rdx
0x180011896  jz      short loc_1800118BD
0x180011898  mov     r11d, [r8]
0x18001189b  lea     rcx, [rsp+1090h+var_1040]
0x1800118a0  cmp     [rcx], r11d
0x1800118a3  jnz     short loc_1800118B4
0x1800118a5  movzx   eax, word ptr [r8+4]
0x1800118aa  cmp     [rcx+4], ax
0x1800118ae  jz      loc_180011956
0x1800118b4  add     rcx, 0Ch
0x1800118b8  cmp     rcx, rdx
0x1800118bb  jnz     short loc_1800118A0
0x1800118bd  mov     eax, r9d
0x1800118c0  add     rax, 0Ch
0x1800118c4  cmp     rax, 1000h
0x1800118ca  ja      short loc_1800118E8
0x1800118cc  movsd   xmm0, qword ptr [r8]
0x1800118d1  add     r9d, 0Ch
0x1800118d5  movsd   qword ptr [rdx], xmm0
0x1800118d9  inc     r10d
0x1800118dc  mov     eax, [r8+8]
0x1800118e0  mov     [rdx+8], eax
0x1800118e3  mov     [rsp+1090h+var_1050], r9d
0x1800118e8  add     r8, 0Ch
0x1800118ec  lea     rdx, [rsp+1090h+var_1040]
0x1800118f1  cmp     r8, rsi
0x1800118f4  jnz     short loc_180011883
0x1800118f6  mov     eax, [rsp+1090h+var_104C]
0x1800118fa  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180011901  mov     [rsp+1090h+var_1060], 1
0x180011909  mov     r8d, r9d
0x18001190c  mov     dword ptr [rsp+1090h+var_1068], eax
0x180011910  call    wil_details_NtUpdateWnfStateData
0x180011915  mov     esi, eax
0x180011917  cmp     esi, 0C0000001h
0x18001191d  jnz     short loc_180011930
0x18001191f  inc     r15d
0x180011922  cmp     r15d, 64h ; 'd'
0x180011926  jge     short loc_180011930
0x180011928  test    edi, edi
0x18001192a  jz      loc_180011776
0x180011930  test    ebx, ebx
0x180011932  cmovz   ebx, esi
0x180011935  mov     eax, ebx
0x180011937  mov     rcx, [rbp+0F90h+var_40]
0x18001193e  xor     rcx, rsp; StackCookie
0x180011941  call    __security_check_cookie
0x180011946  add     rsp, 1068h
0x18001194d  pop     r15
0x18001194f  pop     r14
0x180011951  pop     rdi
0x180011952  pop     rsi
0x180011953  pop     rbx
0x180011954  pop     rbp
0x180011955  retn
0x180011956  mov     eax, [r8+8]
0x18001195a  add     [rcx+8], eax
0x18001195d  mov     r9d, [rsp+1090h+var_1050]
0x180011962  jmp     short loc_1800118E8
```
