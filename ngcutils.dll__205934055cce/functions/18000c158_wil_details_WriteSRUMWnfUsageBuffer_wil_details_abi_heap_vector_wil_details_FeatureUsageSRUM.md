# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000c158`
- end: `0x18000c390`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180005510`

## callees

- `0x180003080`
- `0x180003bc8`
- `0x18000c158`
- `0x18000c620`
- `0x180057f50`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c1e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c1e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c1f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c1f8`

## string_xrefs

- `0x18000c1da`: `ntdll.dll`

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
0x18000c158  push    rbp
0x18000c15a  push    rbx
0x18000c15b  push    rsi
0x18000c15c  push    rdi
0x18000c15d  push    r14
0x18000c15f  push    r15
0x18000c161  lea     rbp, [rsp-0F68h]
0x18000c169  mov     eax, 1068h
0x18000c16e  call    _alloca_probe
0x18000c173  sub     rsp, rax
0x18000c176  mov     rax, cs:__security_cookie
0x18000c17d  xor     rax, rsp
0x18000c180  mov     [rbp+0F90h+var_40], rax
0x18000c187  mov     rax, [rcx+8]
0x18000c18b  xor     ebx, ebx
0x18000c18d  sub     rax, [rcx]
0x18000c190  xor     esi, esi
0x18000c192  mov     r14, rcx
0x18000c195  cmp     rax, 0Ch
0x18000c199  jb      loc_18000C35C
0x18000c19f  xor     r15d, r15d
0x18000c1a2  xor     edx, edx; Val
0x18000c1a4  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000c1a9  mov     r8d, 1000h; Size
0x18000c1af  call    memset_0
0x18000c1b4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000c1bc  mov     [rsp+1090h+var_1050], 1000h
0x18000c1c4  mov     [rsp+1090h+var_104C], 0
0x18000c1cc  jnz     short loc_18000C216
0x18000c1ce  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c1d5  test    rax, rax
0x18000c1d8  jnz     short loc_18000C1EE
0x18000c1da  lea     rcx, ModuleName; "ntdll.dll"
0x18000c1e1  call    cs:__imp_GetModuleHandleW
0x18000c1e7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c1ee  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000c1f5  mov     rcx, rax; hModule
0x18000c1f8  call    cs:__imp_GetProcAddress
0x18000c1fe  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000c205  test    rax, rax
0x18000c208  jnz     short loc_18000C216
0x18000c20a  mov     edi, 0C0000139h
0x18000c20f  mov     ebx, edi
0x18000c211  jmp     loc_18000C343
0x18000c216  lea     rax, [rsp+1090h+var_1050]
0x18000c21b  xor     r8d, r8d
0x18000c21e  mov     [rsp+1090h+var_1068], rax
0x18000c223  lea     r9, [rsp+1090h+var_104C]
0x18000c228  lea     rax, [rsp+1090h+var_1040]
0x18000c22d  xor     edx, edx
0x18000c22f  mov     [rsp+1090h+var_1070], rax
0x18000c234  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000c23b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000c242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c247  mov     ebx, eax
0x18000c249  mov     edi, eax
0x18000c24b  test    eax, eax
0x18000c24d  jnz     loc_18000C343
0x18000c253  mov     r9d, [rsp+1090h+var_1050]
0x18000c258  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000c262  mov     rax, r11
0x18000c265  mul     r9
0x18000c268  shr     rdx, 3
0x18000c26c  lea     rcx, [rdx+rdx*2]
0x18000c270  shl     rcx, 2
0x18000c274  cmp     r9, rcx
0x18000c277  jz      short loc_18000C281
0x18000c279  xor     r9d, r9d
0x18000c27c  mov     [rsp+1090h+var_1050], r9d
0x18000c281  mov     r8, [r14]
0x18000c284  mov     rax, r11
0x18000c287  mov     ecx, r9d
0x18000c28a  mul     rcx
0x18000c28d  mov     rcx, [r14+8]
0x18000c291  mov     rax, r11
0x18000c294  mov     r10, rdx
0x18000c297  sub     rcx, r8
0x18000c29a  mul     rcx
0x18000c29d  shr     r10, 3
0x18000c2a1  shr     rdx, 3
0x18000c2a5  lea     rax, [rdx+rdx*2]
0x18000c2a9  lea     rsi, [r8+rax*4]
0x18000c2ad  jmp     short loc_18000C318
0x18000c2af  mov     eax, r10d
0x18000c2b2  lea     rcx, [rax+rax*2]
0x18000c2b6  lea     rdx, [rdx+rcx*4]
0x18000c2ba  lea     rax, [rsp+1090h+var_1040]
0x18000c2bf  cmp     rax, rdx
0x18000c2c2  jz      short loc_18000C2E9
0x18000c2c4  mov     r11d, [r8]
0x18000c2c7  lea     rcx, [rsp+1090h+var_1040]
0x18000c2cc  cmp     [rcx], r11d
0x18000c2cf  jnz     short loc_18000C2E0
0x18000c2d1  movzx   eax, word ptr [r8+4]
0x18000c2d6  cmp     [rcx+4], ax
0x18000c2da  jz      loc_18000C382
0x18000c2e0  add     rcx, 0Ch
0x18000c2e4  cmp     rcx, rdx
0x18000c2e7  jnz     short loc_18000C2CC
0x18000c2e9  mov     eax, r9d
0x18000c2ec  add     rax, 0Ch
0x18000c2f0  cmp     rax, 1000h
0x18000c2f6  ja      short loc_18000C314
0x18000c2f8  movsd   xmm0, qword ptr [r8]
0x18000c2fd  add     r9d, 0Ch
0x18000c301  movsd   qword ptr [rdx], xmm0
0x18000c305  inc     r10d
0x18000c308  mov     eax, [r8+8]
0x18000c30c  mov     [rdx+8], eax
0x18000c30f  mov     [rsp+1090h+var_1050], r9d
0x18000c314  add     r8, 0Ch
0x18000c318  lea     rdx, [rsp+1090h+var_1040]
0x18000c31d  cmp     r8, rsi
0x18000c320  jnz     short loc_18000C2AF
0x18000c322  mov     eax, [rsp+1090h+var_104C]
0x18000c326  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000c32d  mov     [rsp+1090h+var_1060], 1
0x18000c335  mov     r8d, r9d
0x18000c338  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000c33c  call    wil_details_NtUpdateWnfStateData
0x18000c341  mov     esi, eax
0x18000c343  cmp     esi, 0C0000001h
0x18000c349  jnz     short loc_18000C35C
0x18000c34b  inc     r15d
0x18000c34e  cmp     r15d, 64h ; 'd'
0x18000c352  jge     short loc_18000C35C
0x18000c354  test    edi, edi
0x18000c356  jz      loc_18000C1A2
0x18000c35c  test    ebx, ebx
0x18000c35e  cmovz   ebx, esi
0x18000c361  mov     eax, ebx
0x18000c363  mov     rcx, [rbp+0F90h+var_40]
0x18000c36a  xor     rcx, rsp; StackCookie
0x18000c36d  call    __security_check_cookie
0x18000c372  add     rsp, 1068h
0x18000c379  pop     r15
0x18000c37b  pop     r14
0x18000c37d  pop     rdi
0x18000c37e  pop     rsi
0x18000c37f  pop     rbx
0x18000c380  pop     rbp
0x18000c381  retn
0x18000c382  mov     eax, [r8+8]
0x18000c386  add     [rcx+8], eax
0x18000c389  mov     r9d, [rsp+1090h+var_1050]
0x18000c38e  jmp     short loc_18000C314
```
