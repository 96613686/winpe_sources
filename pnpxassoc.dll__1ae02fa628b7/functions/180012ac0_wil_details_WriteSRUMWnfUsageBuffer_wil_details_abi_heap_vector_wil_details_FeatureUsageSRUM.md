# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180012ac0`
- end: `0x180012cf8`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180010190`

## callees

- `0x180012ac0`
- `0x180012d00`
- `0x180012dce`
- `0x180012e00`
- `0x180012e90`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180012b60`
- `KERNEL32!GetProcAddress` at `0x180012b60`
- `KERNEL32!GetModuleHandleW` at `0x180012b49`
- `KERNEL32!GetModuleHandleW` at `0x180012b49`

## string_xrefs

- `0x180012b42`: `ntdll.dll`

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
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180012ac0  push    rbp
0x180012ac2  push    rbx
0x180012ac3  push    rsi
0x180012ac4  push    rdi
0x180012ac5  push    r14
0x180012ac7  push    r15
0x180012ac9  lea     rbp, [rsp-0F68h]
0x180012ad1  mov     eax, 1068h
0x180012ad6  call    _alloca_probe
0x180012adb  sub     rsp, rax
0x180012ade  mov     rax, cs:__security_cookie
0x180012ae5  xor     rax, rsp
0x180012ae8  mov     [rbp+0F90h+var_40], rax
0x180012aef  mov     rax, [rcx+8]
0x180012af3  xor     ebx, ebx
0x180012af5  sub     rax, [rcx]
0x180012af8  xor     esi, esi
0x180012afa  mov     r14, rcx
0x180012afd  cmp     rax, 0Ch
0x180012b01  jb      loc_180012CC4
0x180012b07  xor     r15d, r15d
0x180012b0a  xor     edx, edx; Val
0x180012b0c  lea     rcx, [rsp+1090h+var_1040]; void *
0x180012b11  mov     r8d, 1000h; Size
0x180012b17  call    memset_0
0x180012b1c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180012b24  mov     [rsp+1090h+var_1050], 1000h
0x180012b2c  mov     [rsp+1090h+var_104C], 0
0x180012b34  jnz     short loc_180012B7E
0x180012b36  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012b3d  test    rax, rax
0x180012b40  jnz     short loc_180012B56
0x180012b42  lea     rcx, ModuleName; "ntdll.dll"
0x180012b49  call    cs:__imp_GetModuleHandleW
0x180012b4f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012b56  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180012b5d  mov     rcx, rax; hModule
0x180012b60  call    cs:__imp_GetProcAddress
0x180012b66  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180012b6d  test    rax, rax
0x180012b70  jnz     short loc_180012B7E
0x180012b72  mov     edi, 0C0000139h
0x180012b77  mov     ebx, edi
0x180012b79  jmp     loc_180012CAB
0x180012b7e  lea     rax, [rsp+1090h+var_1050]
0x180012b83  xor     r8d, r8d
0x180012b86  mov     [rsp+1090h+var_1068], rax
0x180012b8b  lea     r9, [rsp+1090h+var_104C]
0x180012b90  lea     rax, [rsp+1090h+var_1040]
0x180012b95  xor     edx, edx
0x180012b97  mov     [rsp+1090h+var_1070], rax
0x180012b9c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180012ba3  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180012baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012baf  mov     ebx, eax
0x180012bb1  mov     edi, eax
0x180012bb3  test    eax, eax
0x180012bb5  jnz     loc_180012CAB
0x180012bbb  mov     r9d, [rsp+1090h+var_1050]
0x180012bc0  mov     r11, 0AAAAAAAAAAAAAAABh
0x180012bca  mov     rax, r11
0x180012bcd  mul     r9
0x180012bd0  shr     rdx, 3
0x180012bd4  lea     rcx, [rdx+rdx*2]
0x180012bd8  shl     rcx, 2
0x180012bdc  cmp     r9, rcx
0x180012bdf  jz      short loc_180012BE9
0x180012be1  xor     r9d, r9d
0x180012be4  mov     [rsp+1090h+var_1050], r9d
0x180012be9  mov     r8, [r14]
0x180012bec  mov     rax, r11
0x180012bef  mov     ecx, r9d
0x180012bf2  mul     rcx
0x180012bf5  mov     rcx, [r14+8]
0x180012bf9  mov     rax, r11
0x180012bfc  mov     r10, rdx
0x180012bff  sub     rcx, r8
0x180012c02  mul     rcx
0x180012c05  shr     r10, 3
0x180012c09  shr     rdx, 3
0x180012c0d  lea     rax, [rdx+rdx*2]
0x180012c11  lea     rsi, [r8+rax*4]
0x180012c15  jmp     short loc_180012C80
0x180012c17  mov     eax, r10d
0x180012c1a  lea     rcx, [rax+rax*2]
0x180012c1e  lea     rdx, [rdx+rcx*4]
0x180012c22  lea     rax, [rsp+1090h+var_1040]
0x180012c27  cmp     rax, rdx
0x180012c2a  jz      short loc_180012C51
0x180012c2c  mov     r11d, [r8]
0x180012c2f  lea     rcx, [rsp+1090h+var_1040]
0x180012c34  cmp     [rcx], r11d
0x180012c37  jnz     short loc_180012C48
0x180012c39  movzx   eax, word ptr [r8+4]
0x180012c3e  cmp     [rcx+4], ax
0x180012c42  jz      loc_180012CEA
0x180012c48  add     rcx, 0Ch
0x180012c4c  cmp     rcx, rdx
0x180012c4f  jnz     short loc_180012C34
0x180012c51  mov     eax, r9d
0x180012c54  add     rax, 0Ch
0x180012c58  cmp     rax, 1000h
0x180012c5e  ja      short loc_180012C7C
0x180012c60  movsd   xmm0, qword ptr [r8]
0x180012c65  add     r9d, 0Ch
0x180012c69  movsd   qword ptr [rdx], xmm0
0x180012c6d  inc     r10d
0x180012c70  mov     eax, [r8+8]
0x180012c74  mov     [rdx+8], eax
0x180012c77  mov     [rsp+1090h+var_1050], r9d
0x180012c7c  add     r8, 0Ch
0x180012c80  lea     rdx, [rsp+1090h+var_1040]
0x180012c85  cmp     r8, rsi
0x180012c88  jnz     short loc_180012C17
0x180012c8a  mov     eax, [rsp+1090h+var_104C]
0x180012c8e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180012c95  mov     [rsp+1090h+var_1060], 1
0x180012c9d  mov     r8d, r9d
0x180012ca0  mov     dword ptr [rsp+1090h+var_1068], eax
0x180012ca4  call    wil_details_NtUpdateWnfStateData
0x180012ca9  mov     esi, eax
0x180012cab  cmp     esi, 0C0000001h
0x180012cb1  jnz     short loc_180012CC4
0x180012cb3  inc     r15d
0x180012cb6  cmp     r15d, 64h ; 'd'
0x180012cba  jge     short loc_180012CC4
0x180012cbc  test    edi, edi
0x180012cbe  jz      loc_180012B0A
0x180012cc4  test    ebx, ebx
0x180012cc6  cmovz   ebx, esi
0x180012cc9  mov     eax, ebx
0x180012ccb  mov     rcx, [rbp+0F90h+var_40]
0x180012cd2  xor     rcx, rsp; StackCookie
0x180012cd5  call    __security_check_cookie
0x180012cda  add     rsp, 1068h
0x180012ce1  pop     r15
0x180012ce3  pop     r14
0x180012ce5  pop     rdi
0x180012ce6  pop     rsi
0x180012ce7  pop     rbx
0x180012ce8  pop     rbp
0x180012ce9  retn
0x180012cea  mov     eax, [r8+8]
0x180012cee  add     [rcx+8], eax
0x180012cf1  mov     r9d, [rsp+1090h+var_1050]
0x180012cf6  jmp     short loc_180012C7C
```
