# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000b0a8`
- end: `0x18000b2e0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180004420`

## callees

- `0x1800024e0`
- `0x180002efc`
- `0x18000b0a8`
- `0x18000b570`
- `0x1800588d0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b131`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b131`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b148`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b148`

## string_xrefs

- `0x18000b12a`: `ntdll.dll`

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
0x18000b0a8  push    rbp
0x18000b0aa  push    rbx
0x18000b0ab  push    rsi
0x18000b0ac  push    rdi
0x18000b0ad  push    r14
0x18000b0af  push    r15
0x18000b0b1  lea     rbp, [rsp-0F68h]
0x18000b0b9  mov     eax, 1068h
0x18000b0be  call    _alloca_probe
0x18000b0c3  sub     rsp, rax
0x18000b0c6  mov     rax, cs:__security_cookie
0x18000b0cd  xor     rax, rsp
0x18000b0d0  mov     [rbp+0F90h+var_40], rax
0x18000b0d7  mov     rax, [rcx+8]
0x18000b0db  xor     ebx, ebx
0x18000b0dd  sub     rax, [rcx]
0x18000b0e0  xor     esi, esi
0x18000b0e2  mov     r14, rcx
0x18000b0e5  cmp     rax, 0Ch
0x18000b0e9  jb      loc_18000B2AC
0x18000b0ef  xor     r15d, r15d
0x18000b0f2  xor     edx, edx; Val
0x18000b0f4  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000b0f9  mov     r8d, 1000h; Size
0x18000b0ff  call    memset_0
0x18000b104  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000b10c  mov     [rsp+1090h+var_1050], 1000h
0x18000b114  mov     [rsp+1090h+var_104C], 0
0x18000b11c  jnz     short loc_18000B166
0x18000b11e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b125  test    rax, rax
0x18000b128  jnz     short loc_18000B13E
0x18000b12a  lea     rcx, ModuleName; "ntdll.dll"
0x18000b131  call    cs:__imp_GetModuleHandleW
0x18000b137  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b13e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000b145  mov     rcx, rax; hModule
0x18000b148  call    cs:__imp_GetProcAddress
0x18000b14e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000b155  test    rax, rax
0x18000b158  jnz     short loc_18000B166
0x18000b15a  mov     edi, 0C0000139h
0x18000b15f  mov     ebx, edi
0x18000b161  jmp     loc_18000B293
0x18000b166  lea     rax, [rsp+1090h+var_1050]
0x18000b16b  xor     r8d, r8d
0x18000b16e  mov     [rsp+1090h+var_1068], rax
0x18000b173  lea     r9, [rsp+1090h+var_104C]
0x18000b178  lea     rax, [rsp+1090h+var_1040]
0x18000b17d  xor     edx, edx
0x18000b17f  mov     [rsp+1090h+var_1070], rax
0x18000b184  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b18b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000b192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b197  mov     ebx, eax
0x18000b199  mov     edi, eax
0x18000b19b  test    eax, eax
0x18000b19d  jnz     loc_18000B293
0x18000b1a3  mov     r9d, [rsp+1090h+var_1050]
0x18000b1a8  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000b1b2  mov     rax, r11
0x18000b1b5  mul     r9
0x18000b1b8  shr     rdx, 3
0x18000b1bc  lea     rcx, [rdx+rdx*2]
0x18000b1c0  shl     rcx, 2
0x18000b1c4  cmp     r9, rcx
0x18000b1c7  jz      short loc_18000B1D1
0x18000b1c9  xor     r9d, r9d
0x18000b1cc  mov     [rsp+1090h+var_1050], r9d
0x18000b1d1  mov     r8, [r14]
0x18000b1d4  mov     rax, r11
0x18000b1d7  mov     ecx, r9d
0x18000b1da  mul     rcx
0x18000b1dd  mov     rcx, [r14+8]
0x18000b1e1  mov     rax, r11
0x18000b1e4  mov     r10, rdx
0x18000b1e7  sub     rcx, r8
0x18000b1ea  mul     rcx
0x18000b1ed  shr     r10, 3
0x18000b1f1  shr     rdx, 3
0x18000b1f5  lea     rax, [rdx+rdx*2]
0x18000b1f9  lea     rsi, [r8+rax*4]
0x18000b1fd  jmp     short loc_18000B268
0x18000b1ff  mov     eax, r10d
0x18000b202  lea     rcx, [rax+rax*2]
0x18000b206  lea     rdx, [rdx+rcx*4]
0x18000b20a  lea     rax, [rsp+1090h+var_1040]
0x18000b20f  cmp     rax, rdx
0x18000b212  jz      short loc_18000B239
0x18000b214  mov     r11d, [r8]
0x18000b217  lea     rcx, [rsp+1090h+var_1040]
0x18000b21c  cmp     [rcx], r11d
0x18000b21f  jnz     short loc_18000B230
0x18000b221  movzx   eax, word ptr [r8+4]
0x18000b226  cmp     [rcx+4], ax
0x18000b22a  jz      loc_18000B2D2
0x18000b230  add     rcx, 0Ch
0x18000b234  cmp     rcx, rdx
0x18000b237  jnz     short loc_18000B21C
0x18000b239  mov     eax, r9d
0x18000b23c  add     rax, 0Ch
0x18000b240  cmp     rax, 1000h
0x18000b246  ja      short loc_18000B264
0x18000b248  movsd   xmm0, qword ptr [r8]
0x18000b24d  add     r9d, 0Ch
0x18000b251  movsd   qword ptr [rdx], xmm0
0x18000b255  inc     r10d
0x18000b258  mov     eax, [r8+8]
0x18000b25c  mov     [rdx+8], eax
0x18000b25f  mov     [rsp+1090h+var_1050], r9d
0x18000b264  add     r8, 0Ch
0x18000b268  lea     rdx, [rsp+1090h+var_1040]
0x18000b26d  cmp     r8, rsi
0x18000b270  jnz     short loc_18000B1FF
0x18000b272  mov     eax, [rsp+1090h+var_104C]
0x18000b276  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b27d  mov     [rsp+1090h+var_1060], 1
0x18000b285  mov     r8d, r9d
0x18000b288  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000b28c  call    wil_details_NtUpdateWnfStateData
0x18000b291  mov     esi, eax
0x18000b293  cmp     esi, 0C0000001h
0x18000b299  jnz     short loc_18000B2AC
0x18000b29b  inc     r15d
0x18000b29e  cmp     r15d, 64h ; 'd'
0x18000b2a2  jge     short loc_18000B2AC
0x18000b2a4  test    edi, edi
0x18000b2a6  jz      loc_18000B0F2
0x18000b2ac  test    ebx, ebx
0x18000b2ae  cmovz   ebx, esi
0x18000b2b1  mov     eax, ebx
0x18000b2b3  mov     rcx, [rbp+0F90h+var_40]
0x18000b2ba  xor     rcx, rsp; StackCookie
0x18000b2bd  call    __security_check_cookie
0x18000b2c2  add     rsp, 1068h
0x18000b2c9  pop     r15
0x18000b2cb  pop     r14
0x18000b2cd  pop     rdi
0x18000b2ce  pop     rsi
0x18000b2cf  pop     rbx
0x18000b2d0  pop     rbp
0x18000b2d1  retn
0x18000b2d2  mov     eax, [r8+8]
0x18000b2d6  add     [rcx+8], eax
0x18000b2d9  mov     r9d, [rsp+1090h+var_1050]
0x18000b2de  jmp     short loc_18000B264
```
