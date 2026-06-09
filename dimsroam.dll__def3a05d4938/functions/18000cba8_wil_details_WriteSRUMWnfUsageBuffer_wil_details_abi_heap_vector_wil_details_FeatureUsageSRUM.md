# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000cba8`
- end: `0x18000cde0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180007610`

## callees

- `0x18000cba8`
- `0x18000d700`
- `0x18000d89e`
- `0x18000d8d0`
- `0x18000d960`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cc31`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cc31`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cc48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cc48`

## string_xrefs

- `0x18000cc2a`: `ntdll.dll`

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
0x18000cba8  push    rbp
0x18000cbaa  push    rbx
0x18000cbab  push    rsi
0x18000cbac  push    rdi
0x18000cbad  push    r14
0x18000cbaf  push    r15
0x18000cbb1  lea     rbp, [rsp-0F68h]
0x18000cbb9  mov     eax, 1068h
0x18000cbbe  call    _alloca_probe
0x18000cbc3  sub     rsp, rax
0x18000cbc6  mov     rax, cs:__security_cookie
0x18000cbcd  xor     rax, rsp
0x18000cbd0  mov     [rbp+0F90h+var_40], rax
0x18000cbd7  mov     rax, [rcx+8]
0x18000cbdb  xor     ebx, ebx
0x18000cbdd  sub     rax, [rcx]
0x18000cbe0  xor     esi, esi
0x18000cbe2  mov     r14, rcx
0x18000cbe5  cmp     rax, 0Ch
0x18000cbe9  jb      loc_18000CDAC
0x18000cbef  xor     r15d, r15d
0x18000cbf2  xor     edx, edx; Val
0x18000cbf4  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000cbf9  mov     r8d, 1000h; Size
0x18000cbff  call    memset_0
0x18000cc04  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000cc0c  mov     [rsp+1090h+var_1050], 1000h
0x18000cc14  mov     [rsp+1090h+var_104C], 0
0x18000cc1c  jnz     short loc_18000CC66
0x18000cc1e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cc25  test    rax, rax
0x18000cc28  jnz     short loc_18000CC3E
0x18000cc2a  lea     rcx, ModuleName; "ntdll.dll"
0x18000cc31  call    cs:__imp_GetModuleHandleW
0x18000cc37  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cc3e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000cc45  mov     rcx, rax; hModule
0x18000cc48  call    cs:__imp_GetProcAddress
0x18000cc4e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000cc55  test    rax, rax
0x18000cc58  jnz     short loc_18000CC66
0x18000cc5a  mov     edi, 0C0000139h
0x18000cc5f  mov     ebx, edi
0x18000cc61  jmp     loc_18000CD93
0x18000cc66  lea     rax, [rsp+1090h+var_1050]
0x18000cc6b  xor     r8d, r8d
0x18000cc6e  mov     [rsp+1090h+var_1068], rax
0x18000cc73  lea     r9, [rsp+1090h+var_104C]
0x18000cc78  lea     rax, [rsp+1090h+var_1040]
0x18000cc7d  xor     edx, edx
0x18000cc7f  mov     [rsp+1090h+var_1070], rax
0x18000cc84  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000cc8b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000cc92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc97  mov     ebx, eax
0x18000cc99  mov     edi, eax
0x18000cc9b  test    eax, eax
0x18000cc9d  jnz     loc_18000CD93
0x18000cca3  mov     r9d, [rsp+1090h+var_1050]
0x18000cca8  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000ccb2  mov     rax, r11
0x18000ccb5  mul     r9
0x18000ccb8  shr     rdx, 3
0x18000ccbc  lea     rcx, [rdx+rdx*2]
0x18000ccc0  shl     rcx, 2
0x18000ccc4  cmp     r9, rcx
0x18000ccc7  jz      short loc_18000CCD1
0x18000ccc9  xor     r9d, r9d
0x18000cccc  mov     [rsp+1090h+var_1050], r9d
0x18000ccd1  mov     r8, [r14]
0x18000ccd4  mov     rax, r11
0x18000ccd7  mov     ecx, r9d
0x18000ccda  mul     rcx
0x18000ccdd  mov     rcx, [r14+8]
0x18000cce1  mov     rax, r11
0x18000cce4  mov     r10, rdx
0x18000cce7  sub     rcx, r8
0x18000ccea  mul     rcx
0x18000cced  shr     r10, 3
0x18000ccf1  shr     rdx, 3
0x18000ccf5  lea     rax, [rdx+rdx*2]
0x18000ccf9  lea     rsi, [r8+rax*4]
0x18000ccfd  jmp     short loc_18000CD68
0x18000ccff  mov     eax, r10d
0x18000cd02  lea     rcx, [rax+rax*2]
0x18000cd06  lea     rdx, [rdx+rcx*4]
0x18000cd0a  lea     rax, [rsp+1090h+var_1040]
0x18000cd0f  cmp     rax, rdx
0x18000cd12  jz      short loc_18000CD39
0x18000cd14  mov     r11d, [r8]
0x18000cd17  lea     rcx, [rsp+1090h+var_1040]
0x18000cd1c  cmp     [rcx], r11d
0x18000cd1f  jnz     short loc_18000CD30
0x18000cd21  movzx   eax, word ptr [r8+4]
0x18000cd26  cmp     [rcx+4], ax
0x18000cd2a  jz      loc_18000CDD2
0x18000cd30  add     rcx, 0Ch
0x18000cd34  cmp     rcx, rdx
0x18000cd37  jnz     short loc_18000CD1C
0x18000cd39  mov     eax, r9d
0x18000cd3c  add     rax, 0Ch
0x18000cd40  cmp     rax, 1000h
0x18000cd46  ja      short loc_18000CD64
0x18000cd48  movsd   xmm0, qword ptr [r8]
0x18000cd4d  add     r9d, 0Ch
0x18000cd51  movsd   qword ptr [rdx], xmm0
0x18000cd55  inc     r10d
0x18000cd58  mov     eax, [r8+8]
0x18000cd5c  mov     [rdx+8], eax
0x18000cd5f  mov     [rsp+1090h+var_1050], r9d
0x18000cd64  add     r8, 0Ch
0x18000cd68  lea     rdx, [rsp+1090h+var_1040]
0x18000cd6d  cmp     r8, rsi
0x18000cd70  jnz     short loc_18000CCFF
0x18000cd72  mov     eax, [rsp+1090h+var_104C]
0x18000cd76  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000cd7d  mov     [rsp+1090h+var_1060], 1
0x18000cd85  mov     r8d, r9d
0x18000cd88  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000cd8c  call    wil_details_NtUpdateWnfStateData
0x18000cd91  mov     esi, eax
0x18000cd93  cmp     esi, 0C0000001h
0x18000cd99  jnz     short loc_18000CDAC
0x18000cd9b  inc     r15d
0x18000cd9e  cmp     r15d, 64h ; 'd'
0x18000cda2  jge     short loc_18000CDAC
0x18000cda4  test    edi, edi
0x18000cda6  jz      loc_18000CBF2
0x18000cdac  test    ebx, ebx
0x18000cdae  cmovz   ebx, esi
0x18000cdb1  mov     eax, ebx
0x18000cdb3  mov     rcx, [rbp+0F90h+var_40]
0x18000cdba  xor     rcx, rsp; StackCookie
0x18000cdbd  call    __security_check_cookie
0x18000cdc2  add     rsp, 1068h
0x18000cdc9  pop     r15
0x18000cdcb  pop     r14
0x18000cdcd  pop     rdi
0x18000cdce  pop     rsi
0x18000cdcf  pop     rbx
0x18000cdd0  pop     rbp
0x18000cdd1  retn
0x18000cdd2  mov     eax, [r8+8]
0x18000cdd6  add     [rcx+8], eax
0x18000cdd9  mov     r9d, [rsp+1090h+var_1050]
0x18000cdde  jmp     short loc_18000CD64
```
