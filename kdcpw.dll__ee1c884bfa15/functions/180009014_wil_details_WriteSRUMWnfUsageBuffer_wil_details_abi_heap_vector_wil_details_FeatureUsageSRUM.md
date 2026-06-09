# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180009014`
- end: `0x18000924c`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002670`

## callees

- `0x180001630`
- `0x180001f88`
- `0x180009014`
- `0x180009a20`
- `0x18000ca90`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800090b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800090b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000909d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000909d`

## string_xrefs

- `0x180009096`: `ntdll.dll`

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
0x180009014  push    rbp
0x180009016  push    rbx
0x180009017  push    rsi
0x180009018  push    rdi
0x180009019  push    r14
0x18000901b  push    r15
0x18000901d  lea     rbp, [rsp-0F68h]
0x180009025  mov     eax, 1068h
0x18000902a  call    _alloca_probe
0x18000902f  sub     rsp, rax
0x180009032  mov     rax, cs:__security_cookie
0x180009039  xor     rax, rsp
0x18000903c  mov     [rbp+0F90h+var_40], rax
0x180009043  mov     rax, [rcx+8]
0x180009047  xor     ebx, ebx
0x180009049  sub     rax, [rcx]
0x18000904c  xor     esi, esi
0x18000904e  mov     r14, rcx
0x180009051  cmp     rax, 0Ch
0x180009055  jb      loc_180009218
0x18000905b  xor     r15d, r15d
0x18000905e  xor     edx, edx; Val
0x180009060  lea     rcx, [rsp+1090h+var_1040]; void *
0x180009065  mov     r8d, 1000h; Size
0x18000906b  call    memset_0
0x180009070  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180009078  mov     [rsp+1090h+var_1050], 1000h
0x180009080  mov     [rsp+1090h+var_104C], 0
0x180009088  jnz     short loc_1800090D2
0x18000908a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009091  test    rax, rax
0x180009094  jnz     short loc_1800090AA
0x180009096  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000909d  call    cs:__imp_GetModuleHandleW
0x1800090a3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800090aa  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800090b1  mov     rcx, rax; hModule
0x1800090b4  call    cs:__imp_GetProcAddress
0x1800090ba  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800090c1  test    rax, rax
0x1800090c4  jnz     short loc_1800090D2
0x1800090c6  mov     edi, 0C0000139h
0x1800090cb  mov     ebx, edi
0x1800090cd  jmp     loc_1800091FF
0x1800090d2  lea     rax, [rsp+1090h+var_1050]
0x1800090d7  xor     r8d, r8d
0x1800090da  mov     [rsp+1090h+var_1068], rax
0x1800090df  lea     r9, [rsp+1090h+var_104C]
0x1800090e4  lea     rax, [rsp+1090h+var_1040]
0x1800090e9  xor     edx, edx
0x1800090eb  mov     [rsp+1090h+var_1070], rax
0x1800090f0  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800090f7  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800090fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009103  mov     ebx, eax
0x180009105  mov     edi, eax
0x180009107  test    eax, eax
0x180009109  jnz     loc_1800091FF
0x18000910f  mov     r9d, [rsp+1090h+var_1050]
0x180009114  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000911e  mov     rax, r11
0x180009121  mul     r9
0x180009124  shr     rdx, 3
0x180009128  lea     rcx, [rdx+rdx*2]
0x18000912c  shl     rcx, 2
0x180009130  cmp     r9, rcx
0x180009133  jz      short loc_18000913D
0x180009135  xor     r9d, r9d
0x180009138  mov     [rsp+1090h+var_1050], r9d
0x18000913d  mov     r8, [r14]
0x180009140  mov     rax, r11
0x180009143  mov     ecx, r9d
0x180009146  mul     rcx
0x180009149  mov     rcx, [r14+8]
0x18000914d  mov     rax, r11
0x180009150  mov     r10, rdx
0x180009153  sub     rcx, r8
0x180009156  mul     rcx
0x180009159  shr     r10, 3
0x18000915d  shr     rdx, 3
0x180009161  lea     rax, [rdx+rdx*2]
0x180009165  lea     rsi, [r8+rax*4]
0x180009169  jmp     short loc_1800091D4
0x18000916b  mov     eax, r10d
0x18000916e  lea     rcx, [rax+rax*2]
0x180009172  lea     rdx, [rdx+rcx*4]
0x180009176  lea     rax, [rsp+1090h+var_1040]
0x18000917b  cmp     rax, rdx
0x18000917e  jz      short loc_1800091A5
0x180009180  mov     r11d, [r8]
0x180009183  lea     rcx, [rsp+1090h+var_1040]
0x180009188  cmp     [rcx], r11d
0x18000918b  jnz     short loc_18000919C
0x18000918d  movzx   eax, word ptr [r8+4]
0x180009192  cmp     [rcx+4], ax
0x180009196  jz      loc_18000923E
0x18000919c  add     rcx, 0Ch
0x1800091a0  cmp     rcx, rdx
0x1800091a3  jnz     short loc_180009188
0x1800091a5  mov     eax, r9d
0x1800091a8  add     rax, 0Ch
0x1800091ac  cmp     rax, 1000h
0x1800091b2  ja      short loc_1800091D0
0x1800091b4  movsd   xmm0, qword ptr [r8]
0x1800091b9  add     r9d, 0Ch
0x1800091bd  movsd   qword ptr [rdx], xmm0
0x1800091c1  inc     r10d
0x1800091c4  mov     eax, [r8+8]
0x1800091c8  mov     [rdx+8], eax
0x1800091cb  mov     [rsp+1090h+var_1050], r9d
0x1800091d0  add     r8, 0Ch
0x1800091d4  lea     rdx, [rsp+1090h+var_1040]
0x1800091d9  cmp     r8, rsi
0x1800091dc  jnz     short loc_18000916B
0x1800091de  mov     eax, [rsp+1090h+var_104C]
0x1800091e2  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800091e9  mov     [rsp+1090h+var_1060], 1
0x1800091f1  mov     r8d, r9d
0x1800091f4  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800091f8  call    wil_details_NtUpdateWnfStateData
0x1800091fd  mov     esi, eax
0x1800091ff  cmp     esi, 0C0000001h
0x180009205  jnz     short loc_180009218
0x180009207  inc     r15d
0x18000920a  cmp     r15d, 64h ; 'd'
0x18000920e  jge     short loc_180009218
0x180009210  test    edi, edi
0x180009212  jz      loc_18000905E
0x180009218  test    ebx, ebx
0x18000921a  cmovz   ebx, esi
0x18000921d  mov     eax, ebx
0x18000921f  mov     rcx, [rbp+0F90h+var_40]
0x180009226  xor     rcx, rsp; StackCookie
0x180009229  call    __security_check_cookie
0x18000922e  add     rsp, 1068h
0x180009235  pop     r15
0x180009237  pop     r14
0x180009239  pop     rdi
0x18000923a  pop     rsi
0x18000923b  pop     rbx
0x18000923c  pop     rbp
0x18000923d  retn
0x18000923e  mov     eax, [r8+8]
0x180009242  add     [rcx+8], eax
0x180009245  mov     r9d, [rsp+1090h+var_1050]
0x18000924a  jmp     short loc_1800091D0
```
