# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140008708`
- end: `0x140008940`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140002290`

## callees

- `0x140001570`
- `0x1400020d0`
- `0x140008708`
- `0x1400089d8`
- `0x14001a7d0`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008791`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008791`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400087a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400087a8`

## string_xrefs

- `0x14000878a`: `ntdll.dll`

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
0x140008708  push    rbp
0x14000870a  push    rbx
0x14000870b  push    rsi
0x14000870c  push    rdi
0x14000870d  push    r14
0x14000870f  push    r15
0x140008711  lea     rbp, [rsp-0F68h]
0x140008719  mov     eax, 1068h
0x14000871e  call    _alloca_probe
0x140008723  sub     rsp, rax
0x140008726  mov     rax, cs:__security_cookie
0x14000872d  xor     rax, rsp
0x140008730  mov     [rbp+0F90h+var_40], rax
0x140008737  mov     rax, [rcx+8]
0x14000873b  xor     ebx, ebx
0x14000873d  sub     rax, [rcx]
0x140008740  xor     esi, esi
0x140008742  mov     r14, rcx
0x140008745  cmp     rax, 0Ch
0x140008749  jb      loc_14000890C
0x14000874f  xor     r15d, r15d
0x140008752  xor     edx, edx; Val
0x140008754  lea     rcx, [rsp+1090h+var_1040]; void *
0x140008759  mov     r8d, 1000h; Size
0x14000875f  call    memset_0
0x140008764  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000876c  mov     [rsp+1090h+var_1050], 1000h
0x140008774  mov     [rsp+1090h+var_104C], 0
0x14000877c  jnz     short loc_1400087C6
0x14000877e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008785  test    rax, rax
0x140008788  jnz     short loc_14000879E
0x14000878a  lea     rcx, ModuleName; "ntdll.dll"
0x140008791  call    cs:__imp_GetModuleHandleW
0x140008797  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000879e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1400087a5  mov     rcx, rax; hModule
0x1400087a8  call    cs:__imp_GetProcAddress
0x1400087ae  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1400087b5  test    rax, rax
0x1400087b8  jnz     short loc_1400087C6
0x1400087ba  mov     edi, 0C0000139h
0x1400087bf  mov     ebx, edi
0x1400087c1  jmp     loc_1400088F3
0x1400087c6  lea     rax, [rsp+1090h+var_1050]
0x1400087cb  xor     r8d, r8d
0x1400087ce  mov     [rsp+1090h+var_1068], rax
0x1400087d3  lea     r9, [rsp+1090h+var_104C]
0x1400087d8  lea     rax, [rsp+1090h+var_1040]
0x1400087dd  xor     edx, edx
0x1400087df  mov     [rsp+1090h+var_1070], rax
0x1400087e4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1400087eb  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1400087f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400087f7  mov     ebx, eax
0x1400087f9  mov     edi, eax
0x1400087fb  test    eax, eax
0x1400087fd  jnz     loc_1400088F3
0x140008803  mov     r9d, [rsp+1090h+var_1050]
0x140008808  mov     r11, 0AAAAAAAAAAAAAAABh
0x140008812  mov     rax, r11
0x140008815  mul     r9
0x140008818  shr     rdx, 3
0x14000881c  lea     rcx, [rdx+rdx*2]
0x140008820  shl     rcx, 2
0x140008824  cmp     r9, rcx
0x140008827  jz      short loc_140008831
0x140008829  xor     r9d, r9d
0x14000882c  mov     [rsp+1090h+var_1050], r9d
0x140008831  mov     r8, [r14]
0x140008834  mov     rax, r11
0x140008837  mov     ecx, r9d
0x14000883a  mul     rcx
0x14000883d  mov     rcx, [r14+8]
0x140008841  mov     rax, r11
0x140008844  mov     r10, rdx
0x140008847  sub     rcx, r8
0x14000884a  mul     rcx
0x14000884d  shr     r10, 3
0x140008851  shr     rdx, 3
0x140008855  lea     rax, [rdx+rdx*2]
0x140008859  lea     rsi, [r8+rax*4]
0x14000885d  jmp     short loc_1400088C8
0x14000885f  mov     eax, r10d
0x140008862  lea     rcx, [rax+rax*2]
0x140008866  lea     rdx, [rdx+rcx*4]
0x14000886a  lea     rax, [rsp+1090h+var_1040]
0x14000886f  cmp     rax, rdx
0x140008872  jz      short loc_140008899
0x140008874  mov     r11d, [r8]
0x140008877  lea     rcx, [rsp+1090h+var_1040]
0x14000887c  cmp     [rcx], r11d
0x14000887f  jnz     short loc_140008890
0x140008881  movzx   eax, word ptr [r8+4]
0x140008886  cmp     [rcx+4], ax
0x14000888a  jz      loc_140008932
0x140008890  add     rcx, 0Ch
0x140008894  cmp     rcx, rdx
0x140008897  jnz     short loc_14000887C
0x140008899  mov     eax, r9d
0x14000889c  add     rax, 0Ch
0x1400088a0  cmp     rax, 1000h
0x1400088a6  ja      short loc_1400088C4
0x1400088a8  movsd   xmm0, qword ptr [r8]
0x1400088ad  add     r9d, 0Ch
0x1400088b1  movsd   qword ptr [rdx], xmm0
0x1400088b5  inc     r10d
0x1400088b8  mov     eax, [r8+8]
0x1400088bc  mov     [rdx+8], eax
0x1400088bf  mov     [rsp+1090h+var_1050], r9d
0x1400088c4  add     r8, 0Ch
0x1400088c8  lea     rdx, [rsp+1090h+var_1040]
0x1400088cd  cmp     r8, rsi
0x1400088d0  jnz     short loc_14000885F
0x1400088d2  mov     eax, [rsp+1090h+var_104C]
0x1400088d6  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1400088dd  mov     [rsp+1090h+var_1060], 1
0x1400088e5  mov     r8d, r9d
0x1400088e8  mov     dword ptr [rsp+1090h+var_1068], eax
0x1400088ec  call    wil_details_NtUpdateWnfStateData
0x1400088f1  mov     esi, eax
0x1400088f3  cmp     esi, 0C0000001h
0x1400088f9  jnz     short loc_14000890C
0x1400088fb  inc     r15d
0x1400088fe  cmp     r15d, 64h ; 'd'
0x140008902  jge     short loc_14000890C
0x140008904  test    edi, edi
0x140008906  jz      loc_140008752
0x14000890c  test    ebx, ebx
0x14000890e  cmovz   ebx, esi
0x140008911  mov     eax, ebx
0x140008913  mov     rcx, [rbp+0F90h+var_40]
0x14000891a  xor     rcx, rsp; StackCookie
0x14000891d  call    __security_check_cookie
0x140008922  add     rsp, 1068h
0x140008929  pop     r15
0x14000892b  pop     r14
0x14000892d  pop     rdi
0x14000892e  pop     rsi
0x14000892f  pop     rbx
0x140008930  pop     rbp
0x140008931  retn
0x140008932  mov     eax, [r8+8]
0x140008936  add     [rcx+8], eax
0x140008939  mov     r9d, [rsp+1090h+var_1050]
0x14000893e  jmp     short loc_1400088C4
```
