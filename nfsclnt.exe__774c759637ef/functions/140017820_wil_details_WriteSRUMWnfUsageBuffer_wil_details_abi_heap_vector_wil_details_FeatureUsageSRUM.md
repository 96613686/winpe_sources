# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140017820`
- end: `0x140017a58`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1400122a0`

## callees

- `0x140017820`
- `0x140017a60`
- `0x14001830e`
- `0x140018350`
- `0x1400183e0`
- `0x140019010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400178c0`
- `KERNEL32!GetProcAddress` at `0x1400178c0`
- `KERNEL32!GetModuleHandleW` at `0x1400178a9`
- `KERNEL32!GetModuleHandleW` at `0x1400178a9`

## string_xrefs

- `0x1400178a2`: `ntdll.dll`

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
0x140017820  push    rbp
0x140017822  push    rbx
0x140017823  push    rsi
0x140017824  push    rdi
0x140017825  push    r14
0x140017827  push    r15
0x140017829  lea     rbp, [rsp-0F68h]
0x140017831  mov     eax, 1068h
0x140017836  call    _alloca_probe
0x14001783b  sub     rsp, rax
0x14001783e  mov     rax, cs:__security_cookie
0x140017845  xor     rax, rsp
0x140017848  mov     [rbp+0F90h+var_40], rax
0x14001784f  mov     rax, [rcx+8]
0x140017853  xor     ebx, ebx
0x140017855  sub     rax, [rcx]
0x140017858  xor     esi, esi
0x14001785a  mov     r14, rcx
0x14001785d  cmp     rax, 0Ch
0x140017861  jb      loc_140017A24
0x140017867  xor     r15d, r15d
0x14001786a  xor     edx, edx; Val
0x14001786c  lea     rcx, [rsp+1090h+var_1040]; void *
0x140017871  mov     r8d, 1000h; Size
0x140017877  call    memset_0
0x14001787c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x140017884  mov     [rsp+1090h+var_1050], 1000h
0x14001788c  mov     [rsp+1090h+var_104C], 0
0x140017894  jnz     short loc_1400178DE
0x140017896  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001789d  test    rax, rax
0x1400178a0  jnz     short loc_1400178B6
0x1400178a2  lea     rcx, ModuleName; "ntdll.dll"
0x1400178a9  call    cs:__imp_GetModuleHandleW
0x1400178af  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400178b6  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1400178bd  mov     rcx, rax; hModule
0x1400178c0  call    cs:__imp_GetProcAddress
0x1400178c6  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1400178cd  test    rax, rax
0x1400178d0  jnz     short loc_1400178DE
0x1400178d2  mov     edi, 0C0000139h
0x1400178d7  mov     ebx, edi
0x1400178d9  jmp     loc_140017A0B
0x1400178de  lea     rax, [rsp+1090h+var_1050]
0x1400178e3  xor     r8d, r8d
0x1400178e6  mov     [rsp+1090h+var_1068], rax
0x1400178eb  lea     r9, [rsp+1090h+var_104C]
0x1400178f0  lea     rax, [rsp+1090h+var_1040]
0x1400178f5  xor     edx, edx
0x1400178f7  mov     [rsp+1090h+var_1070], rax
0x1400178fc  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140017903  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14001790a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001790f  mov     ebx, eax
0x140017911  mov     edi, eax
0x140017913  test    eax, eax
0x140017915  jnz     loc_140017A0B
0x14001791b  mov     r9d, [rsp+1090h+var_1050]
0x140017920  mov     r11, 0AAAAAAAAAAAAAAABh
0x14001792a  mov     rax, r11
0x14001792d  mul     r9
0x140017930  shr     rdx, 3
0x140017934  lea     rcx, [rdx+rdx*2]
0x140017938  shl     rcx, 2
0x14001793c  cmp     r9, rcx
0x14001793f  jz      short loc_140017949
0x140017941  xor     r9d, r9d
0x140017944  mov     [rsp+1090h+var_1050], r9d
0x140017949  mov     r8, [r14]
0x14001794c  mov     rax, r11
0x14001794f  mov     ecx, r9d
0x140017952  mul     rcx
0x140017955  mov     rcx, [r14+8]
0x140017959  mov     rax, r11
0x14001795c  mov     r10, rdx
0x14001795f  sub     rcx, r8
0x140017962  mul     rcx
0x140017965  shr     r10, 3
0x140017969  shr     rdx, 3
0x14001796d  lea     rax, [rdx+rdx*2]
0x140017971  lea     rsi, [r8+rax*4]
0x140017975  jmp     short loc_1400179E0
0x140017977  mov     eax, r10d
0x14001797a  lea     rcx, [rax+rax*2]
0x14001797e  lea     rdx, [rdx+rcx*4]
0x140017982  lea     rax, [rsp+1090h+var_1040]
0x140017987  cmp     rax, rdx
0x14001798a  jz      short loc_1400179B1
0x14001798c  mov     r11d, [r8]
0x14001798f  lea     rcx, [rsp+1090h+var_1040]
0x140017994  cmp     [rcx], r11d
0x140017997  jnz     short loc_1400179A8
0x140017999  movzx   eax, word ptr [r8+4]
0x14001799e  cmp     [rcx+4], ax
0x1400179a2  jz      loc_140017A4A
0x1400179a8  add     rcx, 0Ch
0x1400179ac  cmp     rcx, rdx
0x1400179af  jnz     short loc_140017994
0x1400179b1  mov     eax, r9d
0x1400179b4  add     rax, 0Ch
0x1400179b8  cmp     rax, 1000h
0x1400179be  ja      short loc_1400179DC
0x1400179c0  movsd   xmm0, qword ptr [r8]
0x1400179c5  add     r9d, 0Ch
0x1400179c9  movsd   qword ptr [rdx], xmm0
0x1400179cd  inc     r10d
0x1400179d0  mov     eax, [r8+8]
0x1400179d4  mov     [rdx+8], eax
0x1400179d7  mov     [rsp+1090h+var_1050], r9d
0x1400179dc  add     r8, 0Ch
0x1400179e0  lea     rdx, [rsp+1090h+var_1040]
0x1400179e5  cmp     r8, rsi
0x1400179e8  jnz     short loc_140017977
0x1400179ea  mov     eax, [rsp+1090h+var_104C]
0x1400179ee  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1400179f5  mov     [rsp+1090h+var_1060], 1
0x1400179fd  mov     r8d, r9d
0x140017a00  mov     dword ptr [rsp+1090h+var_1068], eax
0x140017a04  call    wil_details_NtUpdateWnfStateData
0x140017a09  mov     esi, eax
0x140017a0b  cmp     esi, 0C0000001h
0x140017a11  jnz     short loc_140017A24
0x140017a13  inc     r15d
0x140017a16  cmp     r15d, 64h ; 'd'
0x140017a1a  jge     short loc_140017A24
0x140017a1c  test    edi, edi
0x140017a1e  jz      loc_14001786A
0x140017a24  test    ebx, ebx
0x140017a26  cmovz   ebx, esi
0x140017a29  mov     eax, ebx
0x140017a2b  mov     rcx, [rbp+0F90h+var_40]
0x140017a32  xor     rcx, rsp; StackCookie
0x140017a35  call    __security_check_cookie
0x140017a3a  add     rsp, 1068h
0x140017a41  pop     r15
0x140017a43  pop     r14
0x140017a45  pop     rdi
0x140017a46  pop     rsi
0x140017a47  pop     rbx
0x140017a48  pop     rbp
0x140017a49  retn
0x140017a4a  mov     eax, [r8+8]
0x140017a4e  add     [rcx+8], eax
0x140017a51  mov     r9d, [rsp+1090h+var_1050]
0x140017a56  jmp     short loc_1400179DC
```
