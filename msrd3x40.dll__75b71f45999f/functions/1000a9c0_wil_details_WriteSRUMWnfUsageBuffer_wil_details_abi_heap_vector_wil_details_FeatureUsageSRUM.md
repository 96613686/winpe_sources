# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1000a9c0`
- end: `0x1000ac10`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YGJPAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `592`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1000e5f0`

## callees

- `0x1000a9c0`
- `0x1000eb60`
- `0x1005e3b0`
- `0x1005f180`
- `0x1005f490`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000aa45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000ab8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000aa45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000ab8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000aa34`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000ab7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000aa34`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000ab7a`

## string_xrefs

- `0x1000aa2f`: `ntdll.dll`
- `0x1000ab75`: `ntdll.dll`
- `0x1000ab85`: `NtUpdateWnfStateData`

## pseudocode

```c
int __thiscall wil_details_WriteSRUMWnfUsageBuffer(int *this)
{
  int v2; // ecx
  int v3; // edi
  unsigned int v4; // eax
  int v5; // ebx
  HMODULE ModuleHandleW; // eax
  int v7; // eax
  unsigned int v8; // edi
  unsigned int v9; // ebx
  int v10; // esi
  unsigned int v11; // edx
  unsigned int *v12; // edx
  unsigned int *v13; // eax
  unsigned int v14; // ecx
  FARPROC NtUpdateWnfStateData; // esi
  int v16; // ebx
  HMODULE v17; // eax
  unsigned int v19; // [esp+2Ch] [ebp-1028h] BYREF
  unsigned int v20; // [esp+30h] [ebp-1024h]
  int v21; // [esp+34h] [ebp-1020h]
  int v22; // [esp+38h] [ebp-101Ch]
  int v23; // [esp+3Ch] [ebp-1018h]
  int *v24; // [esp+40h] [ebp-1014h]
  int v25; // [esp+44h] [ebp-1010h]
  int v26; // [esp+48h] [ebp-100Ch] BYREF
  unsigned int v27[1025]; // [esp+4Ch] [ebp-1008h] BYREF

  v2 = 0;
  v3 = 0;
  v4 = this[1] - *this;
  v24 = this;
  if ( v4 >= 0xC )
  {
    v5 = 0;
    v23 = 0;
    do
    {
      memset(v27, 0, 0x1000u);
      v19 = 4096;
      if ( g_wil_details_pfnNtQueryWnfStateData )
        goto LABEL_8;
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      g_wil_details_pfnNtQueryWnfStateData = (int (__thiscall *)(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD))GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
      if ( g_wil_details_pfnNtQueryWnfStateData )
      {
LABEL_8:
        v7 = g_wil_details_pfnNtQueryWnfStateData(
               g_wil_details_pfnNtQueryWnfStateData,
               &__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
               0,
               0,
               &v26,
               v27,
               &v19);
        v2 = v7;
        v21 = v7;
        if ( !v7 )
        {
          v8 = v19;
          if ( v19 % 0xC )
          {
            v8 = 0;
            v19 = 0;
          }
          v9 = v8 / 0xC;
          v20 = v8 / 0xC;
          v10 = *v24;
          v11 = (v24[1] - *v24) / 0xCu;
          v22 = v21;
          v25 = v10 + 12 * v11;
          if ( v10 != v25 )
          {
            v22 = v21;
            do
            {
              v12 = &v27[3 * v9];
              v13 = v27;
              if ( v27 == v12 )
              {
LABEL_18:
                v14 = v8 + 12;
                if ( v8 + 12 <= 0x1000 )
                {
                  v8 += 12;
                  *(_QWORD *)v12 = *(_QWORD *)v10;
                  v12[2] = *(_DWORD *)(v10 + 8);
                  v19 = v14;
                  v20 = v9 + 1;
                }
              }
              else
              {
                while ( *v13 != *(_DWORD *)v10 || *((_WORD *)v13 + 2) != *(_WORD *)(v10 + 4) )
                {
                  v13 += 3;
                  if ( v13 == v12 )
                  {
                    v9 = v20;
                    goto LABEL_18;
                  }
                }
                v13[2] += *(_DWORD *)(v10 + 8);
                v8 = v19;
              }
              v9 = v20;
              v10 += 12;
            }
            while ( v10 != v25 );
          }
          NtUpdateWnfStateData = (FARPROC)g_wil_details_pfnNtUpdateWnfStateData;
          v16 = v26;
          if ( g_wil_details_pfnNtUpdateWnfStateData )
            goto LABEL_27;
          v17 = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
          if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
          {
            v17 = GetModuleHandleW(L"ntdll.dll");
            `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = v17;
          }
          NtUpdateWnfStateData = GetProcAddress(v17, "NtUpdateWnfStateData");
          g_wil_details_pfnNtUpdateWnfStateData = (int)NtUpdateWnfStateData;
          if ( NtUpdateWnfStateData )
LABEL_27:
            v3 = ((int (__thiscall *)(FARPROC, void *, unsigned int *, unsigned int, _DWORD, _DWORD, int, int))NtUpdateWnfStateData)(
                   NtUpdateWnfStateData,
                   &__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                   v27,
                   v8,
                   0,
                   0,
                   v16,
                   1);
          else
            v3 = -1073741511;
          v2 = v21;
          v7 = v22;
          v5 = v23;
        }
      }
      else
      {
        v7 = -1073741511;
        v2 = -1073741511;
      }
      v23 = ++v5;
    }
    while ( v3 == -1073741823 && v5 < 100 && !v7 );
  }
  if ( v2 )
    return v2;
  return v3;
}

```

## disassembly

```asm
0x1000a9c0  mov     edi, edi
0x1000a9c2  push    ebp
0x1000a9c3  mov     ebp, esp
0x1000a9c5  and     esp, 0FFFFFFF8h
0x1000a9c8  mov     eax, 102Ch
0x1000a9cd  call    __chkstk
0x1000a9d2  mov     eax, ___security_cookie
0x1000a9d7  xor     eax, esp
0x1000a9d9  mov     [esp+102Ch+var_4], eax
0x1000a9e0  mov     edx, ecx
0x1000a9e2  xor     ecx, ecx
0x1000a9e4  push    ebx
0x1000a9e5  push    esi
0x1000a9e6  push    edi
0x1000a9e7  mov     eax, [edx+4]
0x1000a9ea  xor     edi, edi
0x1000a9ec  sub     eax, [edx]
0x1000a9ee  mov     [esp+1038h+var_1014], edx
0x1000a9f2  cmp     eax, 0Ch
0x1000a9f5  jb      loc_1000ABF4
0x1000a9fb  xor     ebx, ebx
0x1000a9fd  mov     [esp+1038h+var_1018], ebx
0x1000aa01  push    1000h; Size
0x1000aa06  lea     eax, [esp+103Ch+var_1008]
0x1000aa0a  push    0; Val
0x1000aa0c  push    eax; void *
0x1000aa0d  call    _memset
0x1000aa12  add     esp, 0Ch
0x1000aa15  mov     [esp+1038h+var_1028], 1000h
0x1000aa1d  cmp     _g_wil_details_pfnNtQueryWnfStateData, 0
0x1000aa24  jnz     short loc_1000AA60
0x1000aa26  mov     eax, ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1000aa2b  test    eax, eax
0x1000aa2d  jnz     short loc_1000AA3F
0x1000aa2f  push    offset ModuleName; "ntdll.dll"
0x1000aa34  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x1000aa3a  mov     ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A, eax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1000aa3f  push    offset aNtquerywnfstat; "NtQueryWnfStateData"
0x1000aa44  push    eax; hModule
0x1000aa45  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1000aa4b  mov     _g_wil_details_pfnNtQueryWnfStateData, eax
0x1000aa50  test    eax, eax
0x1000aa52  jnz     short loc_1000AA60
0x1000aa54  mov     eax, 0C0000139h
0x1000aa59  mov     ecx, eax
0x1000aa5b  jmp     loc_1000ABDA
0x1000aa60  mov     esi, _g_wil_details_pfnNtQueryWnfStateData
0x1000aa66  lea     eax, [esp+1038h+var_1028]
0x1000aa6a  push    eax
0x1000aa6b  lea     eax, [esp+103Ch+var_1008]
0x1000aa6f  mov     ecx, esi
0x1000aa71  push    eax
0x1000aa72  lea     eax, [esp+1040h+var_100C]
0x1000aa76  push    eax
0x1000aa77  push    0
0x1000aa79  push    0; unsigned int
0x1000aa7b  push    offset ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; void *
0x1000aa80  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000aa86  call    esi ; _g_wil_details_pfnNtQueryWnfStateData
0x1000aa88  mov     ecx, eax
0x1000aa8a  mov     [esp+1038h+var_1020], ecx
0x1000aa8e  test    ecx, ecx
0x1000aa90  jnz     loc_1000ABDA
0x1000aa96  mov     edi, [esp+1038h+var_1028]
0x1000aa9a  mov     eax, 0AAAAAAABh
0x1000aa9f  mul     edi
0x1000aaa1  mov     eax, edi
0x1000aaa3  shr     edx, 3
0x1000aaa6  lea     ecx, [edx+edx*2]
0x1000aaa9  shl     ecx, 2
0x1000aaac  sub     eax, ecx
0x1000aaae  jz      short loc_1000AAB6
0x1000aab0  xor     edi, edi
0x1000aab2  mov     [esp+1038h+var_1028], edi
0x1000aab6  mov     eax, 0AAAAAAABh
0x1000aabb  mul     edi
0x1000aabd  mov     eax, [esp+1038h+var_1014]
0x1000aac1  mov     ebx, edx
0x1000aac3  shr     ebx, 3
0x1000aac6  mov     [esp+1038h+var_1024], ebx
0x1000aaca  mov     esi, [eax]
0x1000aacc  mov     ecx, [eax+4]
0x1000aacf  mov     eax, 0AAAAAAABh
0x1000aad4  sub     ecx, esi
0x1000aad6  mul     ecx
0x1000aad8  mov     ecx, [esp+1038h+var_1020]
0x1000aadc  shr     edx, 3
0x1000aadf  mov     [esp+1038h+var_101C], ecx
0x1000aae3  lea     eax, [edx+edx*2]
0x1000aae6  lea     eax, [esi+eax*4]
0x1000aae9  mov     [esp+1038h+var_1010], eax
0x1000aaed  cmp     esi, eax
0x1000aaef  jz      short loc_1000AB5E
0x1000aaf1  mov     [esp+1038h+var_101C], ecx
0x1000aaf5  lea     eax, [ebx+ebx*2]
0x1000aaf8  lea     edx, [esp+1038h+var_1008]
0x1000aafc  lea     edx, [edx+eax*4]
0x1000aaff  lea     eax, [esp+1038h+var_1008]
0x1000ab03  mov     ecx, eax
0x1000ab05  cmp     ecx, edx
0x1000ab07  jz      short loc_1000AB2D
0x1000ab09  mov     ebx, [esi]
0x1000ab0b  nop     dword ptr [eax+eax+00h]
0x1000ab10  cmp     [eax], ebx
0x1000ab12  jnz     short loc_1000AB22
0x1000ab14  mov     cx, [eax+4]
0x1000ab18  cmp     cx, [esi+4]
0x1000ab1c  jz      loc_1000ABA4
0x1000ab22  add     eax, 0Ch
0x1000ab25  cmp     eax, edx
0x1000ab27  jnz     short loc_1000AB10
0x1000ab29  mov     ebx, [esp+1038h+var_1024]
0x1000ab2d  lea     ecx, [edi+0Ch]
0x1000ab30  cmp     ecx, 1000h
0x1000ab36  ja      short loc_1000AB51
0x1000ab38  movq    xmm0, qword ptr [esi]
0x1000ab3c  mov     edi, ecx
0x1000ab3e  movq    qword ptr [edx], xmm0
0x1000ab42  inc     ebx
0x1000ab43  mov     eax, [esi+8]
0x1000ab46  mov     [edx+8], eax
0x1000ab49  mov     [esp+1038h+var_1028], edi
0x1000ab4d  mov     [esp+1038h+var_1024], ebx
0x1000ab51  mov     ebx, [esp+1038h+var_1024]
0x1000ab55  add     esi, 0Ch
0x1000ab58  cmp     esi, [esp+1038h+var_1010]
0x1000ab5c  jnz     short loc_1000AAF5
0x1000ab5e  mov     esi, _g_wil_details_pfnNtUpdateWnfStateData
0x1000ab64  mov     ebx, [esp+1038h+var_100C]
0x1000ab68  test    esi, esi
0x1000ab6a  jnz     short loc_1000ABB0
0x1000ab6c  mov     eax, ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1000ab71  test    eax, eax
0x1000ab73  jnz     short loc_1000AB85
0x1000ab75  push    offset ModuleName; "ntdll.dll"
0x1000ab7a  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x1000ab80  mov     ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A, eax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1000ab85  push    offset aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1000ab8a  push    eax; hModule
0x1000ab8b  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1000ab91  mov     esi, eax
0x1000ab93  mov     _g_wil_details_pfnNtUpdateWnfStateData, esi
0x1000ab99  test    esi, esi
0x1000ab9b  jnz     short loc_1000ABB0
0x1000ab9d  mov     edi, 0C0000139h
0x1000aba2  jmp     short loc_1000ABCE
0x1000aba4  mov     ecx, [esi+8]
0x1000aba7  add     [eax+8], ecx
0x1000abaa  mov     edi, [esp+1038h+var_1028]
0x1000abae  jmp     short loc_1000AB51
0x1000abb0  push    1
0x1000abb2  push    ebx
0x1000abb3  push    0
0x1000abb5  push    0
0x1000abb7  push    edi
0x1000abb8  lea     eax, [esp+104Ch+var_1008]
0x1000abbc  mov     ecx, esi
0x1000abbe  push    eax; unsigned int
0x1000abbf  push    offset ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; void *
0x1000abc4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000abca  call    esi ; _g_wil_details_pfnNtUpdateWnfStateData
0x1000abcc  mov     edi, eax
0x1000abce  mov     ecx, [esp+1038h+var_1020]
0x1000abd2  mov     eax, [esp+1038h+var_101C]
0x1000abd6  mov     ebx, [esp+1038h+var_1018]
0x1000abda  inc     ebx
0x1000abdb  mov     [esp+1038h+var_1018], ebx
0x1000abdf  cmp     edi, 0C0000001h
0x1000abe5  jnz     short loc_1000ABF4
0x1000abe7  cmp     ebx, 64h ; 'd'
0x1000abea  jge     short loc_1000ABF4
0x1000abec  test    eax, eax
0x1000abee  jz      loc_1000AA01
0x1000abf4  test    ecx, ecx
0x1000abf6  cmovnz  edi, ecx
0x1000abf9  mov     ecx, [esp+1038h+var_4]
0x1000ac00  mov     eax, edi
0x1000ac02  pop     edi
0x1000ac03  pop     esi
0x1000ac04  pop     ebx
0x1000ac05  xor     ecx, esp; StackCookie
0x1000ac07  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000ac0c  mov     esp, ebp
0x1000ac0e  pop     ebp
0x1000ac0f  retn
```
