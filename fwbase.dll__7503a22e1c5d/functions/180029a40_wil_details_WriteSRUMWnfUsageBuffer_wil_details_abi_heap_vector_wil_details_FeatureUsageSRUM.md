# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180029a40`
- end: `0x180029d08`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `712`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800216f0`

## callees

- `0x18001e1d0`
- `0x18001eb54`
- `0x180029a40`
- `0x18002f5f0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029b02`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029c5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029b02`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029c5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180029aeb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180029c43`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180029aeb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180029c43`

## string_xrefs

- `0x180029ae4`: `ntdll.dll`
- `0x180029c3c`: `ntdll.dll`
- `0x180029c50`: `NtUpdateWnfStateData`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int v2; // ebp
  unsigned int v3; // ebx
  int v4; // r14d
  HMODULE ModuleHandleW; // rax
  int v6; // esi
  unsigned int v7; // ebx
  __int64 v8; // r8
  unsigned int v9; // r10d
  unsigned __int64 v10; // r11
  _DWORD *v11; // rdx
  _DWORD *v12; // rax
  FARPROC ProcAddress; // rax
  int v14; // edi
  HMODULE v15; // rax
  __int64 v17; // [rsp+28h] [rbp-1060h]
  unsigned int v18; // [rsp+40h] [rbp-1048h] BYREF
  _DWORD v19[3]; // [rsp+44h] [rbp-1044h] BYREF
  _DWORD v20[1024]; // [rsp+50h] [rbp-1038h] BYREF

  v2 = 0;
  v3 = 0;
  if ( (unsigned __int64)(a1[1] - *a1) >= 0xC )
  {
    v4 = 0;
    do
    {
      memset_0(v20, 0, sizeof(v20));
      v18 = 4096;
      v19[0] = 0;
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
        v2 = ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, _DWORD *, _DWORD *, unsigned int *))g_wil_details_pfnNtQueryWnfStateData)(
               &__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
               0,
               0,
               v19,
               v20,
               &v18);
        v6 = v2;
        if ( !v2 )
        {
          v7 = v18;
          if ( v18 != 12 * (v18 / 0xCuLL) )
          {
            v7 = 0;
            v18 = 0;
          }
          v8 = *a1;
          v9 = v7 / 0xC;
          v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
          if ( *a1 != v10 )
          {
            do
            {
              v11 = &v20[3 * v9];
              if ( v20 == v11 )
              {
LABEL_17:
                if ( (unsigned __int64)v7 + 12 <= 0x1000 )
                {
                  v7 += 12;
                  *(_QWORD *)v11 = *(_QWORD *)v8;
                  ++v9;
                  v11[2] = *(_DWORD *)(v8 + 8);
                  v18 = v7;
                }
              }
              else
              {
                v12 = v20;
                while ( *v12 != *(_DWORD *)v8 || *((_WORD *)v12 + 2) != *(_WORD *)(v8 + 4) )
                {
                  v12 += 3;
                  if ( v12 == v11 )
                    goto LABEL_17;
                }
                v12[2] += *(_DWORD *)(v8 + 8);
                v7 = v18;
              }
              v8 += 12;
            }
            while ( v8 != v10 );
          }
          ProcAddress = (FARPROC)g_wil_details_pfnNtUpdateWnfStateData;
          v14 = v19[0];
          if ( g_wil_details_pfnNtUpdateWnfStateData )
            goto LABEL_26;
          v15 = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
          if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
          {
            v15 = GetModuleHandleW(L"ntdll.dll");
            `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = v15;
          }
          ProcAddress = GetProcAddress(v15, "NtUpdateWnfStateData");
          g_wil_details_pfnNtUpdateWnfStateData = (__int64)ProcAddress;
          if ( ProcAddress )
          {
LABEL_26:
            LODWORD(v17) = v14;
            v3 = ((__int64 (__fastcall *)(void *, _DWORD *, _QWORD, _QWORD, _QWORD, __int64, int))ProcAddress)(
                   &__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                   v20,
                   v7,
                   0,
                   0,
                   v17,
                   1);
          }
          else
          {
            v3 = -1073741511;
          }
        }
      }
      else
      {
        v6 = -1073741511;
        v2 = -1073741511;
      }
      if ( v3 != -1073741823 )
        break;
      if ( ++v4 >= 100 )
        break;
    }
    while ( !v6 );
  }
  if ( !v2 )
    return v3;
  return v2;
}

```

## disassembly

```asm
0x180029a40  push    rbx
0x180029a42  push    rbp
0x180029a43  push    r12
0x180029a45  push    r15
0x180029a47  mov     eax, 1068h
0x180029a4c  call    _alloca_probe
0x180029a51  sub     rsp, rax
0x180029a54  mov     rax, cs:__security_cookie
0x180029a5b  xor     rax, rsp
0x180029a5e  mov     [rsp+1088h+var_38], rax
0x180029a66  mov     rax, [rcx+8]
0x180029a6a  xor     r12d, r12d
0x180029a6d  sub     rax, [rcx]
0x180029a70  mov     r15, rcx
0x180029a73  mov     ebp, r12d
0x180029a76  mov     ebx, r12d
0x180029a79  cmp     rax, 0Ch
0x180029a7d  jb      loc_180029CE3
0x180029a83  mov     [rsp+1088h+arg_10], r13
0x180029a8b  mov     r13, 0AAAAAAAAAAAAAAABh
0x180029a95  mov     [rsp+1088h+var_28], r14
0x180029a9d  mov     r14d, r12d
0x180029aa0  mov     [rsp+1088h+arg_0], rsi
0x180029aa8  mov     [rsp+1088h+arg_8], rdi
0x180029ab0  xor     edx, edx; Val
0x180029ab2  lea     rcx, [rsp+1088h+var_1038]; void *
0x180029ab7  mov     r8d, 1000h; Size
0x180029abd  call    memset_0
0x180029ac2  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, r12
0x180029ac9  mov     [rsp+1088h+var_1048], 1000h
0x180029ad1  mov     [rsp+1088h+var_1044], r12d
0x180029ad6  jnz     short loc_180029B20
0x180029ad8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180029adf  test    rax, rax
0x180029ae2  jnz     short loc_180029AF8
0x180029ae4  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180029aeb  call    cs:__imp_GetModuleHandleW
0x180029af1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180029af8  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180029aff  mov     rcx, rax; hModule
0x180029b02  call    cs:__imp_GetProcAddress
0x180029b08  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180029b0f  test    rax, rax
0x180029b12  jnz     short loc_180029B20
0x180029b14  mov     esi, 0C0000139h
0x180029b19  mov     ebp, esi
0x180029b1b  jmp     loc_180029CAA
0x180029b20  lea     rax, [rsp+1088h+var_1048]
0x180029b25  xor     r8d, r8d
0x180029b28  mov     [rsp+1088h+var_1060], rax
0x180029b2d  lea     r9, [rsp+1088h+var_1044]
0x180029b32  lea     rax, [rsp+1088h+var_1038]
0x180029b37  xor     edx, edx
0x180029b39  mov     [rsp+1088h+var_1068], rax
0x180029b3e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180029b45  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180029b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b51  mov     ebp, eax
0x180029b53  mov     esi, eax
0x180029b55  test    eax, eax
0x180029b57  jnz     loc_180029CAA
0x180029b5d  mov     ebx, [rsp+1088h+var_1048]
0x180029b61  mov     rax, r13
0x180029b64  mul     rbx
0x180029b67  shr     rdx, 3
0x180029b6b  lea     rcx, [rdx+rdx*2]
0x180029b6f  shl     rcx, 2
0x180029b73  cmp     rbx, rcx
0x180029b76  jz      short loc_180029B7F
0x180029b78  mov     ebx, r12d
0x180029b7b  mov     [rsp+1088h+var_1048], ebx
0x180029b7f  mov     r8, [r15]
0x180029b82  mov     rax, r13
0x180029b85  mov     ecx, ebx
0x180029b87  mul     rcx
0x180029b8a  mov     rcx, [r15+8]
0x180029b8e  mov     rax, r13
0x180029b91  mov     r10, rdx
0x180029b94  sub     rcx, r8
0x180029b97  mul     rcx
0x180029b9a  shr     r10, 3
0x180029b9e  shr     rdx, 3
0x180029ba2  lea     rax, [rdx+rdx*2]
0x180029ba6  lea     r11, [r8+rax*4]
0x180029baa  cmp     r8, r11
0x180029bad  jz      short loc_180029C20
0x180029baf  nop
0x180029bb0  mov     eax, r10d
0x180029bb3  lea     rdx, [rsp+1088h+var_1038]
0x180029bb8  lea     rcx, [rax+rax*2]
0x180029bbc  lea     rdx, [rdx+rcx*4]
0x180029bc0  lea     rax, [rsp+1088h+var_1038]
0x180029bc5  cmp     rax, rdx
0x180029bc8  jz      short loc_180029BEF
0x180029bca  mov     r9d, [r8]
0x180029bcd  lea     rax, [rsp+1088h+var_1038]
0x180029bd2  cmp     [rax], r9d
0x180029bd5  jnz     short loc_180029BE6
0x180029bd7  movzx   ecx, word ptr [r8+4]
0x180029bdc  cmp     [rax+4], cx
0x180029be0  jz      loc_180029C73
0x180029be6  add     rax, 0Ch
0x180029bea  cmp     rax, rdx
0x180029bed  jnz     short loc_180029BD2
0x180029bef  mov     eax, ebx
0x180029bf1  add     rax, 0Ch
0x180029bf5  cmp     rax, 1000h
0x180029bfb  ja      short loc_180029C17
0x180029bfd  movsd   xmm0, qword ptr [r8]
0x180029c02  add     ebx, 0Ch
0x180029c05  movsd   qword ptr [rdx], xmm0
0x180029c09  inc     r10d
0x180029c0c  mov     eax, [r8+8]
0x180029c10  mov     [rdx+8], eax
0x180029c13  mov     [rsp+1088h+var_1048], ebx
0x180029c17  add     r8, 0Ch
0x180029c1b  cmp     r8, r11
0x180029c1e  jnz     short loc_180029BB0
0x180029c20  mov     rax, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180029c27  mov     edi, [rsp+1088h+var_1044]
0x180029c2b  test    rax, rax
0x180029c2e  jnz     short loc_180029C80
0x180029c30  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180029c37  test    rax, rax
0x180029c3a  jnz     short loc_180029C50
0x180029c3c  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180029c43  call    cs:__imp_GetModuleHandleW
0x180029c49  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180029c50  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180029c57  mov     rcx, rax; hModule
0x180029c5a  call    cs:__imp_GetProcAddress
0x180029c60  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180029c67  test    rax, rax
0x180029c6a  jnz     short loc_180029C80
0x180029c6c  mov     ebx, 0C0000139h
0x180029c71  jmp     short loc_180029CAA
0x180029c73  mov     ecx, [r8+8]
0x180029c77  add     [rax+8], ecx
0x180029c7a  mov     ebx, [rsp+1088h+var_1048]
0x180029c7e  jmp     short loc_180029C17
0x180029c80  mov     [rsp+1088h+var_1058], 1
0x180029c88  lea     rdx, [rsp+1088h+var_1038]
0x180029c8d  mov     dword ptr [rsp+1088h+var_1060], edi
0x180029c91  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180029c98  xor     r9d, r9d
0x180029c9b  mov     [rsp+1088h+var_1068], r12
0x180029ca0  mov     r8d, ebx
0x180029ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ca8  mov     ebx, eax
0x180029caa  cmp     ebx, 0C0000001h
0x180029cb0  jnz     short loc_180029CC3
0x180029cb2  inc     r14d
0x180029cb5  cmp     r14d, 64h ; 'd'
0x180029cb9  jge     short loc_180029CC3
0x180029cbb  test    esi, esi
0x180029cbd  jz      loc_180029AB0
0x180029cc3  mov     r14, [rsp+1088h+var_28]
0x180029ccb  mov     r13, [rsp+1088h+arg_10]
0x180029cd3  mov     rdi, [rsp+1088h+arg_8]
0x180029cdb  mov     rsi, [rsp+1088h+arg_0]
0x180029ce3  test    ebp, ebp
0x180029ce5  cmovz   ebp, ebx
0x180029ce8  mov     eax, ebp
0x180029cea  mov     rcx, [rsp+1088h+var_38]
0x180029cf2  xor     rcx, rsp; StackCookie
0x180029cf5  call    __security_check_cookie
0x180029cfa  add     rsp, 1068h
0x180029d01  pop     r15
0x180029d03  pop     r12
0x180029d05  pop     rbp
0x180029d06  pop     rbx
0x180029d07  retn
```
