# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000bd38`
- end: `0x14000bf70`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140003390`

## callees

- `0x140002600`
- `0x140003168`
- `0x14000bd38`
- `0x14000c1f0`
- `0x1400130e0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bdc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bdc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bdd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bdd8`

## string_xrefs

- `0x14000bdba`: `ntdll.dll`

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
0x14000bd38  push    rbp
0x14000bd3a  push    rbx
0x14000bd3b  push    rsi
0x14000bd3c  push    rdi
0x14000bd3d  push    r14
0x14000bd3f  push    r15
0x14000bd41  lea     rbp, [rsp-0F68h]
0x14000bd49  mov     eax, 1068h
0x14000bd4e  call    _alloca_probe
0x14000bd53  sub     rsp, rax
0x14000bd56  mov     rax, cs:__security_cookie
0x14000bd5d  xor     rax, rsp
0x14000bd60  mov     [rbp+0F90h+var_40], rax
0x14000bd67  mov     rax, [rcx+8]
0x14000bd6b  xor     ebx, ebx
0x14000bd6d  sub     rax, [rcx]
0x14000bd70  xor     esi, esi
0x14000bd72  mov     r14, rcx
0x14000bd75  cmp     rax, 0Ch
0x14000bd79  jb      loc_14000BF3C
0x14000bd7f  xor     r15d, r15d
0x14000bd82  xor     edx, edx; Val
0x14000bd84  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000bd89  mov     r8d, 1000h; Size
0x14000bd8f  call    memset_0
0x14000bd94  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000bd9c  mov     [rsp+1090h+var_1050], 1000h
0x14000bda4  mov     [rsp+1090h+var_104C], 0
0x14000bdac  jnz     short loc_14000BDF6
0x14000bdae  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bdb5  test    rax, rax
0x14000bdb8  jnz     short loc_14000BDCE
0x14000bdba  lea     rcx, ModuleName; "ntdll.dll"
0x14000bdc1  call    cs:__imp_GetModuleHandleW
0x14000bdc7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bdce  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000bdd5  mov     rcx, rax; hModule
0x14000bdd8  call    cs:__imp_GetProcAddress
0x14000bdde  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000bde5  test    rax, rax
0x14000bde8  jnz     short loc_14000BDF6
0x14000bdea  mov     edi, 0C0000139h
0x14000bdef  mov     ebx, edi
0x14000bdf1  jmp     loc_14000BF23
0x14000bdf6  lea     rax, [rsp+1090h+var_1050]
0x14000bdfb  xor     r8d, r8d
0x14000bdfe  mov     [rsp+1090h+var_1068], rax
0x14000be03  lea     r9, [rsp+1090h+var_104C]
0x14000be08  lea     rax, [rsp+1090h+var_1040]
0x14000be0d  xor     edx, edx
0x14000be0f  mov     [rsp+1090h+var_1070], rax
0x14000be14  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000be1b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000be22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be27  mov     ebx, eax
0x14000be29  mov     edi, eax
0x14000be2b  test    eax, eax
0x14000be2d  jnz     loc_14000BF23
0x14000be33  mov     r9d, [rsp+1090h+var_1050]
0x14000be38  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000be42  mov     rax, r11
0x14000be45  mul     r9
0x14000be48  shr     rdx, 3
0x14000be4c  lea     rcx, [rdx+rdx*2]
0x14000be50  shl     rcx, 2
0x14000be54  cmp     r9, rcx
0x14000be57  jz      short loc_14000BE61
0x14000be59  xor     r9d, r9d
0x14000be5c  mov     [rsp+1090h+var_1050], r9d
0x14000be61  mov     r8, [r14]
0x14000be64  mov     rax, r11
0x14000be67  mov     ecx, r9d
0x14000be6a  mul     rcx
0x14000be6d  mov     rcx, [r14+8]
0x14000be71  mov     rax, r11
0x14000be74  mov     r10, rdx
0x14000be77  sub     rcx, r8
0x14000be7a  mul     rcx
0x14000be7d  shr     r10, 3
0x14000be81  shr     rdx, 3
0x14000be85  lea     rax, [rdx+rdx*2]
0x14000be89  lea     rsi, [r8+rax*4]
0x14000be8d  jmp     short loc_14000BEF8
0x14000be8f  mov     eax, r10d
0x14000be92  lea     rcx, [rax+rax*2]
0x14000be96  lea     rdx, [rdx+rcx*4]
0x14000be9a  lea     rax, [rsp+1090h+var_1040]
0x14000be9f  cmp     rax, rdx
0x14000bea2  jz      short loc_14000BEC9
0x14000bea4  mov     r11d, [r8]
0x14000bea7  lea     rcx, [rsp+1090h+var_1040]
0x14000beac  cmp     [rcx], r11d
0x14000beaf  jnz     short loc_14000BEC0
0x14000beb1  movzx   eax, word ptr [r8+4]
0x14000beb6  cmp     [rcx+4], ax
0x14000beba  jz      loc_14000BF62
0x14000bec0  add     rcx, 0Ch
0x14000bec4  cmp     rcx, rdx
0x14000bec7  jnz     short loc_14000BEAC
0x14000bec9  mov     eax, r9d
0x14000becc  add     rax, 0Ch
0x14000bed0  cmp     rax, 1000h
0x14000bed6  ja      short loc_14000BEF4
0x14000bed8  movsd   xmm0, qword ptr [r8]
0x14000bedd  add     r9d, 0Ch
0x14000bee1  movsd   qword ptr [rdx], xmm0
0x14000bee5  inc     r10d
0x14000bee8  mov     eax, [r8+8]
0x14000beec  mov     [rdx+8], eax
0x14000beef  mov     [rsp+1090h+var_1050], r9d
0x14000bef4  add     r8, 0Ch
0x14000bef8  lea     rdx, [rsp+1090h+var_1040]
0x14000befd  cmp     r8, rsi
0x14000bf00  jnz     short loc_14000BE8F
0x14000bf02  mov     eax, [rsp+1090h+var_104C]
0x14000bf06  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000bf0d  mov     [rsp+1090h+var_1060], 1
0x14000bf15  mov     r8d, r9d
0x14000bf18  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000bf1c  call    wil_details_NtUpdateWnfStateData
0x14000bf21  mov     esi, eax
0x14000bf23  cmp     esi, 0C0000001h
0x14000bf29  jnz     short loc_14000BF3C
0x14000bf2b  inc     r15d
0x14000bf2e  cmp     r15d, 64h ; 'd'
0x14000bf32  jge     short loc_14000BF3C
0x14000bf34  test    edi, edi
0x14000bf36  jz      loc_14000BD82
0x14000bf3c  test    ebx, ebx
0x14000bf3e  cmovz   ebx, esi
0x14000bf41  mov     eax, ebx
0x14000bf43  mov     rcx, [rbp+0F90h+var_40]
0x14000bf4a  xor     rcx, rsp; StackCookie
0x14000bf4d  call    __security_check_cookie
0x14000bf52  add     rsp, 1068h
0x14000bf59  pop     r15
0x14000bf5b  pop     r14
0x14000bf5d  pop     rdi
0x14000bf5e  pop     rsi
0x14000bf5f  pop     rbx
0x14000bf60  pop     rbp
0x14000bf61  retn
0x14000bf62  mov     eax, [r8+8]
0x14000bf66  add     [rcx+8], eax
0x14000bf69  mov     r9d, [rsp+1090h+var_1050]
0x14000bf6e  jmp     short loc_14000BEF4
```
