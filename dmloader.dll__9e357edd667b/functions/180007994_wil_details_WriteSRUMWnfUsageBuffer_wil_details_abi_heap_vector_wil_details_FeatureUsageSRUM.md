# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180007994`
- end: `0x180007bcc`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180001fd0`

## callees

- `0x1800015d0`
- `0x180001ef0`
- `0x180007994`
- `0x180007e78`
- `0x18000f930`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007a1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007a1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007a34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007a34`

## string_xrefs

- `0x180007a16`: `ntdll.dll`

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
0x180007994  push    rbp
0x180007996  push    rbx
0x180007997  push    rsi
0x180007998  push    rdi
0x180007999  push    r14
0x18000799b  push    r15
0x18000799d  lea     rbp, [rsp-0F68h]
0x1800079a5  mov     eax, 1068h
0x1800079aa  call    _alloca_probe
0x1800079af  sub     rsp, rax
0x1800079b2  mov     rax, cs:__security_cookie
0x1800079b9  xor     rax, rsp
0x1800079bc  mov     [rbp+0F90h+var_40], rax
0x1800079c3  mov     rax, [rcx+8]
0x1800079c7  xor     ebx, ebx
0x1800079c9  sub     rax, [rcx]
0x1800079cc  xor     esi, esi
0x1800079ce  mov     r14, rcx
0x1800079d1  cmp     rax, 0Ch
0x1800079d5  jb      loc_180007B98
0x1800079db  xor     r15d, r15d
0x1800079de  xor     edx, edx; Val
0x1800079e0  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800079e5  mov     r8d, 1000h; Size
0x1800079eb  call    memset_0
0x1800079f0  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x1800079f8  mov     [rsp+1090h+var_1050], 1000h
0x180007a00  mov     [rsp+1090h+var_104C], 0
0x180007a08  jnz     short loc_180007A52
0x180007a0a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007a11  test    rax, rax
0x180007a14  jnz     short loc_180007A2A
0x180007a16  lea     rcx, ModuleName; "ntdll.dll"
0x180007a1d  call    cs:__imp_GetModuleHandleW
0x180007a23  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007a2a  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180007a31  mov     rcx, rax; hModule
0x180007a34  call    cs:__imp_GetProcAddress
0x180007a3a  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180007a41  test    rax, rax
0x180007a44  jnz     short loc_180007A52
0x180007a46  mov     edi, 0C0000139h
0x180007a4b  mov     ebx, edi
0x180007a4d  jmp     loc_180007B7F
0x180007a52  lea     rax, [rsp+1090h+var_1050]
0x180007a57  xor     r8d, r8d
0x180007a5a  mov     [rsp+1090h+var_1068], rax
0x180007a5f  lea     r9, [rsp+1090h+var_104C]
0x180007a64  lea     rax, [rsp+1090h+var_1040]
0x180007a69  xor     edx, edx
0x180007a6b  mov     [rsp+1090h+var_1070], rax
0x180007a70  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180007a77  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180007a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a83  mov     ebx, eax
0x180007a85  mov     edi, eax
0x180007a87  test    eax, eax
0x180007a89  jnz     loc_180007B7F
0x180007a8f  mov     r9d, [rsp+1090h+var_1050]
0x180007a94  mov     r11, 0AAAAAAAAAAAAAAABh
0x180007a9e  mov     rax, r11
0x180007aa1  mul     r9
0x180007aa4  shr     rdx, 3
0x180007aa8  lea     rcx, [rdx+rdx*2]
0x180007aac  shl     rcx, 2
0x180007ab0  cmp     r9, rcx
0x180007ab3  jz      short loc_180007ABD
0x180007ab5  xor     r9d, r9d
0x180007ab8  mov     [rsp+1090h+var_1050], r9d
0x180007abd  mov     r8, [r14]
0x180007ac0  mov     rax, r11
0x180007ac3  mov     ecx, r9d
0x180007ac6  mul     rcx
0x180007ac9  mov     rcx, [r14+8]
0x180007acd  mov     rax, r11
0x180007ad0  mov     r10, rdx
0x180007ad3  sub     rcx, r8
0x180007ad6  mul     rcx
0x180007ad9  shr     r10, 3
0x180007add  shr     rdx, 3
0x180007ae1  lea     rax, [rdx+rdx*2]
0x180007ae5  lea     rsi, [r8+rax*4]
0x180007ae9  jmp     short loc_180007B54
0x180007aeb  mov     eax, r10d
0x180007aee  lea     rcx, [rax+rax*2]
0x180007af2  lea     rdx, [rdx+rcx*4]
0x180007af6  lea     rax, [rsp+1090h+var_1040]
0x180007afb  cmp     rax, rdx
0x180007afe  jz      short loc_180007B25
0x180007b00  mov     r11d, [r8]
0x180007b03  lea     rcx, [rsp+1090h+var_1040]
0x180007b08  cmp     [rcx], r11d
0x180007b0b  jnz     short loc_180007B1C
0x180007b0d  movzx   eax, word ptr [r8+4]
0x180007b12  cmp     [rcx+4], ax
0x180007b16  jz      loc_180007BBE
0x180007b1c  add     rcx, 0Ch
0x180007b20  cmp     rcx, rdx
0x180007b23  jnz     short loc_180007B08
0x180007b25  mov     eax, r9d
0x180007b28  add     rax, 0Ch
0x180007b2c  cmp     rax, 1000h
0x180007b32  ja      short loc_180007B50
0x180007b34  movsd   xmm0, qword ptr [r8]
0x180007b39  add     r9d, 0Ch
0x180007b3d  movsd   qword ptr [rdx], xmm0
0x180007b41  inc     r10d
0x180007b44  mov     eax, [r8+8]
0x180007b48  mov     [rdx+8], eax
0x180007b4b  mov     [rsp+1090h+var_1050], r9d
0x180007b50  add     r8, 0Ch
0x180007b54  lea     rdx, [rsp+1090h+var_1040]
0x180007b59  cmp     r8, rsi
0x180007b5c  jnz     short loc_180007AEB
0x180007b5e  mov     eax, [rsp+1090h+var_104C]
0x180007b62  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180007b69  mov     [rsp+1090h+var_1060], 1
0x180007b71  mov     r8d, r9d
0x180007b74  mov     dword ptr [rsp+1090h+var_1068], eax
0x180007b78  call    wil_details_NtUpdateWnfStateData
0x180007b7d  mov     esi, eax
0x180007b7f  cmp     esi, 0C0000001h
0x180007b85  jnz     short loc_180007B98
0x180007b87  inc     r15d
0x180007b8a  cmp     r15d, 64h ; 'd'
0x180007b8e  jge     short loc_180007B98
0x180007b90  test    edi, edi
0x180007b92  jz      loc_1800079DE
0x180007b98  test    ebx, ebx
0x180007b9a  cmovz   ebx, esi
0x180007b9d  mov     eax, ebx
0x180007b9f  mov     rcx, [rbp+0F90h+var_40]
0x180007ba6  xor     rcx, rsp; StackCookie
0x180007ba9  call    __security_check_cookie
0x180007bae  add     rsp, 1068h
0x180007bb5  pop     r15
0x180007bb7  pop     r14
0x180007bb9  pop     rdi
0x180007bba  pop     rsi
0x180007bbb  pop     rbx
0x180007bbc  pop     rbp
0x180007bbd  retn
0x180007bbe  mov     eax, [r8+8]
0x180007bc2  add     [rcx+8], eax
0x180007bc5  mov     r9d, [rsp+1090h+var_1050]
0x180007bca  jmp     short loc_180007B50
```
