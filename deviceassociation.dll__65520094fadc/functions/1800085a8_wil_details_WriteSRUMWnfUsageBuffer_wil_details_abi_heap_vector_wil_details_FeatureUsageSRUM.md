# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800085a8`
- end: `0x1800087e0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180003010`

## callees

- `0x1800085a8`
- `0x1800097dc`
- `0x18000bbc2`
- `0x18000bbf0`
- `0x18000bc80`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008648`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008648`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008631`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008631`

## string_xrefs

- `0x18000862a`: `ntdll.dll`

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
0x1800085a8  push    rbp
0x1800085aa  push    rbx
0x1800085ab  push    rsi
0x1800085ac  push    rdi
0x1800085ad  push    r14
0x1800085af  push    r15
0x1800085b1  lea     rbp, [rsp-0F68h]
0x1800085b9  mov     eax, 1068h
0x1800085be  call    _alloca_probe
0x1800085c3  sub     rsp, rax
0x1800085c6  mov     rax, cs:__security_cookie
0x1800085cd  xor     rax, rsp
0x1800085d0  mov     [rbp+0F90h+var_40], rax
0x1800085d7  mov     rax, [rcx+8]
0x1800085db  xor     ebx, ebx
0x1800085dd  sub     rax, [rcx]
0x1800085e0  xor     esi, esi
0x1800085e2  mov     r14, rcx
0x1800085e5  cmp     rax, 0Ch
0x1800085e9  jb      loc_1800087AC
0x1800085ef  xor     r15d, r15d
0x1800085f2  xor     edx, edx; Val
0x1800085f4  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800085f9  mov     r8d, 1000h; Size
0x1800085ff  call    memset_0
0x180008604  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000860c  mov     [rsp+1090h+var_1050], 1000h
0x180008614  mov     [rsp+1090h+var_104C], 0
0x18000861c  jnz     short loc_180008666
0x18000861e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008625  test    rax, rax
0x180008628  jnz     short loc_18000863E
0x18000862a  lea     rcx, ModuleName; "ntdll.dll"
0x180008631  call    cs:__imp_GetModuleHandleW
0x180008637  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000863e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180008645  mov     rcx, rax; hModule
0x180008648  call    cs:__imp_GetProcAddress
0x18000864e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008655  test    rax, rax
0x180008658  jnz     short loc_180008666
0x18000865a  mov     edi, 0C0000139h
0x18000865f  mov     ebx, edi
0x180008661  jmp     loc_180008793
0x180008666  lea     rax, [rsp+1090h+var_1050]
0x18000866b  xor     r8d, r8d
0x18000866e  mov     [rsp+1090h+var_1068], rax
0x180008673  lea     r9, [rsp+1090h+var_104C]
0x180008678  lea     rax, [rsp+1090h+var_1040]
0x18000867d  xor     edx, edx
0x18000867f  mov     [rsp+1090h+var_1070], rax
0x180008684  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000868b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008697  mov     ebx, eax
0x180008699  mov     edi, eax
0x18000869b  test    eax, eax
0x18000869d  jnz     loc_180008793
0x1800086a3  mov     r9d, [rsp+1090h+var_1050]
0x1800086a8  mov     r11, 0AAAAAAAAAAAAAAABh
0x1800086b2  mov     rax, r11
0x1800086b5  mul     r9
0x1800086b8  shr     rdx, 3
0x1800086bc  lea     rcx, [rdx+rdx*2]
0x1800086c0  shl     rcx, 2
0x1800086c4  cmp     r9, rcx
0x1800086c7  jz      short loc_1800086D1
0x1800086c9  xor     r9d, r9d
0x1800086cc  mov     [rsp+1090h+var_1050], r9d
0x1800086d1  mov     r8, [r14]
0x1800086d4  mov     rax, r11
0x1800086d7  mov     ecx, r9d
0x1800086da  mul     rcx
0x1800086dd  mov     rcx, [r14+8]
0x1800086e1  mov     rax, r11
0x1800086e4  mov     r10, rdx
0x1800086e7  sub     rcx, r8
0x1800086ea  mul     rcx
0x1800086ed  shr     r10, 3
0x1800086f1  shr     rdx, 3
0x1800086f5  lea     rax, [rdx+rdx*2]
0x1800086f9  lea     rsi, [r8+rax*4]
0x1800086fd  jmp     short loc_180008768
0x1800086ff  mov     eax, r10d
0x180008702  lea     rcx, [rax+rax*2]
0x180008706  lea     rdx, [rdx+rcx*4]
0x18000870a  lea     rax, [rsp+1090h+var_1040]
0x18000870f  cmp     rax, rdx
0x180008712  jz      short loc_180008739
0x180008714  mov     r11d, [r8]
0x180008717  lea     rcx, [rsp+1090h+var_1040]
0x18000871c  cmp     [rcx], r11d
0x18000871f  jnz     short loc_180008730
0x180008721  movzx   eax, word ptr [r8+4]
0x180008726  cmp     [rcx+4], ax
0x18000872a  jz      loc_1800087D2
0x180008730  add     rcx, 0Ch
0x180008734  cmp     rcx, rdx
0x180008737  jnz     short loc_18000871C
0x180008739  mov     eax, r9d
0x18000873c  add     rax, 0Ch
0x180008740  cmp     rax, 1000h
0x180008746  ja      short loc_180008764
0x180008748  movsd   xmm0, qword ptr [r8]
0x18000874d  add     r9d, 0Ch
0x180008751  movsd   qword ptr [rdx], xmm0
0x180008755  inc     r10d
0x180008758  mov     eax, [r8+8]
0x18000875c  mov     [rdx+8], eax
0x18000875f  mov     [rsp+1090h+var_1050], r9d
0x180008764  add     r8, 0Ch
0x180008768  lea     rdx, [rsp+1090h+var_1040]
0x18000876d  cmp     r8, rsi
0x180008770  jnz     short loc_1800086FF
0x180008772  mov     eax, [rsp+1090h+var_104C]
0x180008776  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000877d  mov     [rsp+1090h+var_1060], 1
0x180008785  mov     r8d, r9d
0x180008788  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000878c  call    wil_details_NtUpdateWnfStateData
0x180008791  mov     esi, eax
0x180008793  cmp     esi, 0C0000001h
0x180008799  jnz     short loc_1800087AC
0x18000879b  inc     r15d
0x18000879e  cmp     r15d, 64h ; 'd'
0x1800087a2  jge     short loc_1800087AC
0x1800087a4  test    edi, edi
0x1800087a6  jz      loc_1800085F2
0x1800087ac  test    ebx, ebx
0x1800087ae  cmovz   ebx, esi
0x1800087b1  mov     eax, ebx
0x1800087b3  mov     rcx, [rbp+0F90h+var_40]
0x1800087ba  xor     rcx, rsp; StackCookie
0x1800087bd  call    __security_check_cookie
0x1800087c2  add     rsp, 1068h
0x1800087c9  pop     r15
0x1800087cb  pop     r14
0x1800087cd  pop     rdi
0x1800087ce  pop     rsi
0x1800087cf  pop     rbx
0x1800087d0  pop     rbp
0x1800087d1  retn
0x1800087d2  mov     eax, [r8+8]
0x1800087d6  add     [rcx+8], eax
0x1800087d9  mov     r9d, [rsp+1090h+var_1050]
0x1800087de  jmp     short loc_180008764
```
