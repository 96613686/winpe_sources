# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180008220`
- end: `0x180008458`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002350`

## callees

- `0x180008220`
- `0x180008460`
- `0x18001ca3e`
- `0x18001ca70`
- `0x18001cb00`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800082c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800082c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800082a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800082a9`

## string_xrefs

- `0x1800082a2`: `ntdll.dll`

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
0x180008220  push    rbp
0x180008222  push    rbx
0x180008223  push    rsi
0x180008224  push    rdi
0x180008225  push    r14
0x180008227  push    r15
0x180008229  lea     rbp, [rsp-0F68h]
0x180008231  mov     eax, 1068h
0x180008236  call    _alloca_probe
0x18000823b  sub     rsp, rax
0x18000823e  mov     rax, cs:__security_cookie
0x180008245  xor     rax, rsp
0x180008248  mov     [rbp+0F90h+var_40], rax
0x18000824f  mov     rax, [rcx+8]
0x180008253  xor     ebx, ebx
0x180008255  sub     rax, [rcx]
0x180008258  xor     esi, esi
0x18000825a  mov     r14, rcx
0x18000825d  cmp     rax, 0Ch
0x180008261  jb      loc_180008424
0x180008267  xor     r15d, r15d
0x18000826a  xor     edx, edx; Val
0x18000826c  lea     rcx, [rsp+1090h+var_1040]; void *
0x180008271  mov     r8d, 1000h; Size
0x180008277  call    memset_0
0x18000827c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180008284  mov     [rsp+1090h+var_1050], 1000h
0x18000828c  mov     [rsp+1090h+var_104C], 0
0x180008294  jnz     short loc_1800082DE
0x180008296  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000829d  test    rax, rax
0x1800082a0  jnz     short loc_1800082B6
0x1800082a2  lea     rcx, ModuleName; "ntdll.dll"
0x1800082a9  call    cs:__imp_GetModuleHandleW
0x1800082af  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800082b6  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800082bd  mov     rcx, rax; hModule
0x1800082c0  call    cs:__imp_GetProcAddress
0x1800082c6  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800082cd  test    rax, rax
0x1800082d0  jnz     short loc_1800082DE
0x1800082d2  mov     edi, 0C0000139h
0x1800082d7  mov     ebx, edi
0x1800082d9  jmp     loc_18000840B
0x1800082de  lea     rax, [rsp+1090h+var_1050]
0x1800082e3  xor     r8d, r8d
0x1800082e6  mov     [rsp+1090h+var_1068], rax
0x1800082eb  lea     r9, [rsp+1090h+var_104C]
0x1800082f0  lea     rax, [rsp+1090h+var_1040]
0x1800082f5  xor     edx, edx
0x1800082f7  mov     [rsp+1090h+var_1070], rax
0x1800082fc  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008303  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000830a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000830f  mov     ebx, eax
0x180008311  mov     edi, eax
0x180008313  test    eax, eax
0x180008315  jnz     loc_18000840B
0x18000831b  mov     r9d, [rsp+1090h+var_1050]
0x180008320  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000832a  mov     rax, r11
0x18000832d  mul     r9
0x180008330  shr     rdx, 3
0x180008334  lea     rcx, [rdx+rdx*2]
0x180008338  shl     rcx, 2
0x18000833c  cmp     r9, rcx
0x18000833f  jz      short loc_180008349
0x180008341  xor     r9d, r9d
0x180008344  mov     [rsp+1090h+var_1050], r9d
0x180008349  mov     r8, [r14]
0x18000834c  mov     rax, r11
0x18000834f  mov     ecx, r9d
0x180008352  mul     rcx
0x180008355  mov     rcx, [r14+8]
0x180008359  mov     rax, r11
0x18000835c  mov     r10, rdx
0x18000835f  sub     rcx, r8
0x180008362  mul     rcx
0x180008365  shr     r10, 3
0x180008369  shr     rdx, 3
0x18000836d  lea     rax, [rdx+rdx*2]
0x180008371  lea     rsi, [r8+rax*4]
0x180008375  jmp     short loc_1800083E0
0x180008377  mov     eax, r10d
0x18000837a  lea     rcx, [rax+rax*2]
0x18000837e  lea     rdx, [rdx+rcx*4]
0x180008382  lea     rax, [rsp+1090h+var_1040]
0x180008387  cmp     rax, rdx
0x18000838a  jz      short loc_1800083B1
0x18000838c  mov     r11d, [r8]
0x18000838f  lea     rcx, [rsp+1090h+var_1040]
0x180008394  cmp     [rcx], r11d
0x180008397  jnz     short loc_1800083A8
0x180008399  movzx   eax, word ptr [r8+4]
0x18000839e  cmp     [rcx+4], ax
0x1800083a2  jz      loc_18000844A
0x1800083a8  add     rcx, 0Ch
0x1800083ac  cmp     rcx, rdx
0x1800083af  jnz     short loc_180008394
0x1800083b1  mov     eax, r9d
0x1800083b4  add     rax, 0Ch
0x1800083b8  cmp     rax, 1000h
0x1800083be  ja      short loc_1800083DC
0x1800083c0  movsd   xmm0, qword ptr [r8]
0x1800083c5  add     r9d, 0Ch
0x1800083c9  movsd   qword ptr [rdx], xmm0
0x1800083cd  inc     r10d
0x1800083d0  mov     eax, [r8+8]
0x1800083d4  mov     [rdx+8], eax
0x1800083d7  mov     [rsp+1090h+var_1050], r9d
0x1800083dc  add     r8, 0Ch
0x1800083e0  lea     rdx, [rsp+1090h+var_1040]
0x1800083e5  cmp     r8, rsi
0x1800083e8  jnz     short loc_180008377
0x1800083ea  mov     eax, [rsp+1090h+var_104C]
0x1800083ee  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800083f5  mov     [rsp+1090h+var_1060], 1
0x1800083fd  mov     r8d, r9d
0x180008400  mov     dword ptr [rsp+1090h+var_1068], eax
0x180008404  call    wil_details_NtUpdateWnfStateData
0x180008409  mov     esi, eax
0x18000840b  cmp     esi, 0C0000001h
0x180008411  jnz     short loc_180008424
0x180008413  inc     r15d
0x180008416  cmp     r15d, 64h ; 'd'
0x18000841a  jge     short loc_180008424
0x18000841c  test    edi, edi
0x18000841e  jz      loc_18000826A
0x180008424  test    ebx, ebx
0x180008426  cmovz   ebx, esi
0x180008429  mov     eax, ebx
0x18000842b  mov     rcx, [rbp+0F90h+var_40]
0x180008432  xor     rcx, rsp; StackCookie
0x180008435  call    __security_check_cookie
0x18000843a  add     rsp, 1068h
0x180008441  pop     r15
0x180008443  pop     r14
0x180008445  pop     rdi
0x180008446  pop     rsi
0x180008447  pop     rbx
0x180008448  pop     rbp
0x180008449  retn
0x18000844a  mov     eax, [r8+8]
0x18000844e  add     [rcx+8], eax
0x180008451  mov     r9d, [rsp+1090h+var_1050]
0x180008456  jmp     short loc_1800083DC
```
