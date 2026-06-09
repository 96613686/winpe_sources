# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800223a8`
- end: `0x1800225e0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800098a0`

## callees

- `0x1800223a8`
- `0x180022cd0`
- `0x180033e9a`
- `0x180033ed0`
- `0x180033f90`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022431`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022431`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022448`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022448`

## string_xrefs

- `0x18002242a`: `ntdll.dll`

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
0x1800223a8  push    rbp
0x1800223aa  push    rbx
0x1800223ab  push    rsi
0x1800223ac  push    rdi
0x1800223ad  push    r14
0x1800223af  push    r15
0x1800223b1  lea     rbp, [rsp-0F68h]
0x1800223b9  mov     eax, 1068h
0x1800223be  call    _alloca_probe
0x1800223c3  sub     rsp, rax
0x1800223c6  mov     rax, cs:__security_cookie
0x1800223cd  xor     rax, rsp
0x1800223d0  mov     [rbp+0F90h+var_40], rax
0x1800223d7  mov     rax, [rcx+8]
0x1800223db  xor     ebx, ebx
0x1800223dd  sub     rax, [rcx]
0x1800223e0  xor     esi, esi
0x1800223e2  mov     r14, rcx
0x1800223e5  cmp     rax, 0Ch
0x1800223e9  jb      loc_1800225AC
0x1800223ef  xor     r15d, r15d
0x1800223f2  xor     edx, edx; Val
0x1800223f4  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800223f9  mov     r8d, 1000h; Size
0x1800223ff  call    memset_0
0x180022404  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18002240c  mov     [rsp+1090h+var_1050], 1000h
0x180022414  mov     [rsp+1090h+var_104C], 0
0x18002241c  jnz     short loc_180022466
0x18002241e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022425  test    rax, rax
0x180022428  jnz     short loc_18002243E
0x18002242a  lea     rcx, ModuleName; "ntdll.dll"
0x180022431  call    cs:__imp_GetModuleHandleW
0x180022437  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002243e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180022445  mov     rcx, rax; hModule
0x180022448  call    cs:__imp_GetProcAddress
0x18002244e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180022455  test    rax, rax
0x180022458  jnz     short loc_180022466
0x18002245a  mov     edi, 0C0000139h
0x18002245f  mov     ebx, edi
0x180022461  jmp     loc_180022593
0x180022466  lea     rax, [rsp+1090h+var_1050]
0x18002246b  xor     r8d, r8d
0x18002246e  mov     [rsp+1090h+var_1068], rax
0x180022473  lea     r9, [rsp+1090h+var_104C]
0x180022478  lea     rax, [rsp+1090h+var_1040]
0x18002247d  xor     edx, edx
0x18002247f  mov     [rsp+1090h+var_1070], rax
0x180022484  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002248b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180022492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022497  mov     ebx, eax
0x180022499  mov     edi, eax
0x18002249b  test    eax, eax
0x18002249d  jnz     loc_180022593
0x1800224a3  mov     r9d, [rsp+1090h+var_1050]
0x1800224a8  mov     r11, 0AAAAAAAAAAAAAAABh
0x1800224b2  mov     rax, r11
0x1800224b5  mul     r9
0x1800224b8  shr     rdx, 3
0x1800224bc  lea     rcx, [rdx+rdx*2]
0x1800224c0  shl     rcx, 2
0x1800224c4  cmp     r9, rcx
0x1800224c7  jz      short loc_1800224D1
0x1800224c9  xor     r9d, r9d
0x1800224cc  mov     [rsp+1090h+var_1050], r9d
0x1800224d1  mov     r8, [r14]
0x1800224d4  mov     rax, r11
0x1800224d7  mov     ecx, r9d
0x1800224da  mul     rcx
0x1800224dd  mov     rcx, [r14+8]
0x1800224e1  mov     rax, r11
0x1800224e4  mov     r10, rdx
0x1800224e7  sub     rcx, r8
0x1800224ea  mul     rcx
0x1800224ed  shr     r10, 3
0x1800224f1  shr     rdx, 3
0x1800224f5  lea     rax, [rdx+rdx*2]
0x1800224f9  lea     rsi, [r8+rax*4]
0x1800224fd  jmp     short loc_180022568
0x1800224ff  mov     eax, r10d
0x180022502  lea     rcx, [rax+rax*2]
0x180022506  lea     rdx, [rdx+rcx*4]
0x18002250a  lea     rax, [rsp+1090h+var_1040]
0x18002250f  cmp     rax, rdx
0x180022512  jz      short loc_180022539
0x180022514  mov     r11d, [r8]
0x180022517  lea     rcx, [rsp+1090h+var_1040]
0x18002251c  cmp     [rcx], r11d
0x18002251f  jnz     short loc_180022530
0x180022521  movzx   eax, word ptr [r8+4]
0x180022526  cmp     [rcx+4], ax
0x18002252a  jz      loc_1800225D2
0x180022530  add     rcx, 0Ch
0x180022534  cmp     rcx, rdx
0x180022537  jnz     short loc_18002251C
0x180022539  mov     eax, r9d
0x18002253c  add     rax, 0Ch
0x180022540  cmp     rax, 1000h
0x180022546  ja      short loc_180022564
0x180022548  movsd   xmm0, qword ptr [r8]
0x18002254d  add     r9d, 0Ch
0x180022551  movsd   qword ptr [rdx], xmm0
0x180022555  inc     r10d
0x180022558  mov     eax, [r8+8]
0x18002255c  mov     [rdx+8], eax
0x18002255f  mov     [rsp+1090h+var_1050], r9d
0x180022564  add     r8, 0Ch
0x180022568  lea     rdx, [rsp+1090h+var_1040]
0x18002256d  cmp     r8, rsi
0x180022570  jnz     short loc_1800224FF
0x180022572  mov     eax, [rsp+1090h+var_104C]
0x180022576  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002257d  mov     [rsp+1090h+var_1060], 1
0x180022585  mov     r8d, r9d
0x180022588  mov     dword ptr [rsp+1090h+var_1068], eax
0x18002258c  call    wil_details_NtUpdateWnfStateData
0x180022591  mov     esi, eax
0x180022593  cmp     esi, 0C0000001h
0x180022599  jnz     short loc_1800225AC
0x18002259b  inc     r15d
0x18002259e  cmp     r15d, 64h ; 'd'
0x1800225a2  jge     short loc_1800225AC
0x1800225a4  test    edi, edi
0x1800225a6  jz      loc_1800223F2
0x1800225ac  test    ebx, ebx
0x1800225ae  cmovz   ebx, esi
0x1800225b1  mov     eax, ebx
0x1800225b3  mov     rcx, [rbp+0F90h+var_40]
0x1800225ba  xor     rcx, rsp; StackCookie
0x1800225bd  call    __security_check_cookie
0x1800225c2  add     rsp, 1068h
0x1800225c9  pop     r15
0x1800225cb  pop     r14
0x1800225cd  pop     rdi
0x1800225ce  pop     rsi
0x1800225cf  pop     rbx
0x1800225d0  pop     rbp
0x1800225d1  retn
0x1800225d2  mov     eax, [r8+8]
0x1800225d6  add     [rcx+8], eax
0x1800225d9  mov     r9d, [rsp+1090h+var_1050]
0x1800225de  jmp     short loc_180022564
```
