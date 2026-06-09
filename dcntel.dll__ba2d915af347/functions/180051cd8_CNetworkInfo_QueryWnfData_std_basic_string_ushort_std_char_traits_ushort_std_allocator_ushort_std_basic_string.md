# CNetworkInfo::QueryWnfData(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,SimNumber)

- ea: `0x180051cd8`
- end: `0x180051fd6`
- name: `?QueryWnfData@CNetworkInfo@@CAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4SimNumber@@@Z`
- size: `766`
- prototype: ``
- caller_count: `8`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004fa10`
- `0x18004fb50`
- `0x180050380`
- `0x1800504b0`
- `0x1800b7b50`
- `0x1800b7c90`
- `0x1800b8210`
- `0x1800b8340`

## callees

- `0x180008dc0`
- `0x180009f08`
- `0x180009f14`
- `0x1800157b8`
- `0x18001daf0`
- `0x18001dcc8`
- `0x180051cd8`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180051d8d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180051d8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051ddd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051ddd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fbc`

## string_xrefs

- `0x180051d86`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HMODULE __fastcall CNetworkInfo::QueryWnfData(char *a1, __int64 a2, __int64 a3)
{
  int v3; // r12d
  char *v5; // rbx
  char *v6; // rcx
  HMODULE result; // rax
  int (__fastcall *v8)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // r15
  __int64 *v9; // rcx
  __int64 v10; // r8
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rdx
  char *v13; // r14
  __int64 v14; // rbx
  __int64 *v15; // rcx
  __int64 v16; // r8
  char *v17; // r14
  signed int LastError; // eax
  int v19; // edx
  unsigned int v20; // r8d
  signed int v21; // eax
  int v22; // edx
  unsigned int v23; // r8d
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+44h] [rbp-BCh] BYREF
  const int *v26; // [rsp+48h] [rbp-B8h] BYREF
  HMODULE v27; // [rsp+50h] [rbp-B0h]
  _WORD v28[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v29[160]; // [rsp+A0h] [rbp-60h] BYREF
  _WORD Src[40]; // [rsp+140h] [rbp+40h] BYREF

  v3 = a3;
  v5 = a1;
  if ( *((_QWORD *)a1 + 3) )
  {
    if ( *((_QWORD *)a1 + 3) > 7u )
      a1 = *(char **)a1;
    *((_QWORD *)v5 + 2) = 1;
    *(_DWORD *)a1 = 35;
  }
  else
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)a1,
      1u,
      a3,
      L"#");
  }
  if ( *(_QWORD *)(a2 + 24) )
  {
    if ( *(_QWORD *)(a2 + 24) <= 7u )
      v6 = (char *)a2;
    else
      v6 = *(char **)a2;
    *(_QWORD *)(a2 + 16) = 1;
    *(_WORD *)v6 = asc_1801B4764[0];
    *((_WORD *)v6 + 1) = 0;
  }
  else
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)a2,
      1u,
      a3,
      L"#");
  }
  result = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v26 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v27 = result;
  if ( result )
  {
    result = (HMODULE)GetProcAddress(result, "NtQueryWnfStateData");
    v8 = (int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))result;
    if ( result )
    {
      v25 = 0;
      memset_0(v29, 0, 0xF0u);
      v24 = 240;
      v9 = &WNF_CELL_DEVICE_INFO_CAN0;
      if ( v3 != 1 )
        v9 = &WNF_CELL_DEVICE_INFO_CAN1;
      v11 = -1;
      if ( v8(v9, 0, 0, &v25, v29, &v24) >= 0 && v24 == 240 )
      {
        v12 = -1;
        do
          ++v12;
        while ( Src[v12] );
        if ( v12 > *((_QWORD *)v5 + 3) )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            (char **)v5,
            v12,
            v10,
            Src);
        }
        else
        {
          if ( *((_QWORD *)v5 + 3) <= 7u )
            v13 = v5;
          else
            v13 = *(char **)v5;
          *((_QWORD *)v5 + 2) = v12;
          v14 = 2 * v12;
          memmove_0(v13, Src, 2 * v12);
          *(_WORD *)&v13[v14] = 0;
        }
      }
      v25 = 0;
      memset_0(v28, 0, sizeof(v28));
      v24 = 64;
      v15 = &WNF_CELL_OPERATOR_NAME_CAN0;
      if ( v3 != 1 )
        v15 = &WNF_CELL_OPERATOR_NAME_CAN1;
      if ( v8(v15, 0, 0, &v25, v28, &v24) >= 0 && v24 == 64 )
      {
        do
          ++v11;
        while ( v28[v11] );
        if ( v11 > *(_QWORD *)(a2 + 24) )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            (char **)a2,
            v11,
            v16,
            v28);
        }
        else
        {
          if ( *(_QWORD *)(a2 + 24) <= 7u )
            v17 = (char *)a2;
          else
            v17 = *(char **)a2;
          *(_QWORD *)(a2 + 16) = v11;
          memmove_0(v17, v28, 2 * v11);
          *(_WORD *)&v17[2 * v11] = 0;
        }
      }
      result = (HMODULE)&Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      v26 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( v27 )
      {
        result = (HMODULE)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v26);
        if ( !(_BYTE)result )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v19, v20);
          __debugbreak();
        }
      }
    }
    else
    {
      v26 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( v27 )
      {
        result = (HMODULE)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v26);
        if ( !(_BYTE)result )
        {
          v21 = GetLastError();
          if ( v21 > 0 )
            v21 = (unsigned __int16)v21 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v21, v22, v23);
          JUMPOUT(0x180051FD5LL);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180051cd8  mov     [rsp-8+arg_10], rbx
0x180051cdd  push    rbp
0x180051cde  push    rsi
0x180051cdf  push    rdi
0x180051ce0  push    r12
0x180051ce2  push    r13
0x180051ce4  push    r14
0x180051ce6  push    r15
0x180051ce8  lea     rbp, [rsp-0A0h]
0x180051cf0  sub     rsp, 1A0h
0x180051cf7  mov     rax, cs:__security_cookie
0x180051cfe  xor     rax, rsp
0x180051d01  mov     [rbp+0D0h+var_40], rax
0x180051d08  mov     r12d, r8d
0x180051d0b  mov     rdi, rdx
0x180051d0e  mov     rbx, rcx
0x180051d11  xor     r13d, r13d
0x180051d14  lea     esi, [r13+1]
0x180051d18  cmp     [rcx+18h], rsi
0x180051d1c  jb      short loc_180051D34
0x180051d1e  cmp     qword ptr [rcx+18h], 7
0x180051d23  jbe     short loc_180051D28
0x180051d25  mov     rcx, [rcx]
0x180051d28  mov     [rbx+10h], rsi
0x180051d2c  mov     dword ptr [rcx], 23h ; '#'
0x180051d32  jmp     short loc_180051D43
0x180051d34  lea     r9, asc_1801B4764; "#"
0x180051d3b  mov     rdx, rsi
0x180051d3e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180051d43  cmp     [rdi+18h], rsi
0x180051d47  jb      short loc_180051D6C
0x180051d49  cmp     qword ptr [rdi+18h], 7
0x180051d4e  jbe     short loc_180051D55
0x180051d50  mov     rcx, [rdi]
0x180051d53  jmp     short loc_180051D58
0x180051d55  mov     rcx, rdi
0x180051d58  mov     [rdi+10h], rsi
0x180051d5c  mov     eax, dword ptr cs:asc_1801B4764; "#"
0x180051d62  mov     [rcx], ax
0x180051d65  mov     [rcx+2], r13w
0x180051d6a  jmp     short loc_180051D7E
0x180051d6c  lea     r9, asc_1801B4764; "#"
0x180051d73  mov     rdx, rsi
0x180051d76  mov     rcx, rdi
0x180051d79  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180051d7e  xor     edx, edx; hFile
0x180051d80  mov     r8d, 800h; dwFlags
0x180051d86  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180051d8d  call    cs:__imp_LoadLibraryExW
0x180051d93  lea     r14, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180051d9a  mov     [rsp+1D0h+var_188], r14
0x180051d9f  mov     [rsp+1D0h+var_180], rax
0x180051da4  test    rax, rax
0x180051da7  jnz     short loc_180051DD3
0x180051da9  mov     rcx, [rbp+0D0h+var_40]
0x180051db0  xor     rcx, rsp; StackCookie
0x180051db3  call    __security_check_cookie
0x180051db8  mov     rbx, [rsp+1D0h+arg_10]
0x180051dc0  add     rsp, 1A0h
0x180051dc7  pop     r15
0x180051dc9  pop     r14
0x180051dcb  pop     r13
0x180051dcd  pop     r12
0x180051dcf  pop     rdi
0x180051dd0  pop     rsi
0x180051dd1  pop     rbp
0x180051dd2  retn
0x180051dd3  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180051dda  mov     rcx, rax; hModule
0x180051ddd  call    cs:__imp_GetProcAddress
0x180051de3  mov     r15, rax
0x180051de6  test    rax, rax
0x180051de9  jnz     short loc_180051E0B
0x180051deb  mov     [rsp+1D0h+var_188], r14
0x180051df0  cmp     [rsp+1D0h+var_180], r13
0x180051df5  jz      short loc_180051DA9
0x180051df7  lea     rcx, [rsp+1D0h+var_188]
0x180051dfc  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180051e01  test    al, al
0x180051e03  jz      loc_180051FBC
0x180051e09  jmp     short loc_180051DA9
0x180051e0b  mov     [rsp+1D0h+var_18C], r13d
0x180051e10  mov     r14d, 0F0h
0x180051e16  mov     r8d, r14d; Size
0x180051e19  xor     edx, edx; Val
0x180051e1b  lea     rcx, [rbp+0D0h+var_130]; void *
0x180051e1f  call    memset_0
0x180051e24  mov     [rsp+1D0h+var_190], r14d
0x180051e29  lea     rax, WNF_CELL_DEVICE_INFO_CAN1
0x180051e30  lea     rcx, WNF_CELL_DEVICE_INFO_CAN0
0x180051e37  cmp     r12d, esi
0x180051e3a  cmovnz  rcx, rax
0x180051e3e  lea     rax, [rsp+1D0h+var_190]
0x180051e43  mov     [rsp+1D0h+var_1A8], rax
0x180051e48  lea     rax, [rbp+0D0h+var_130]
0x180051e4c  mov     [rsp+1D0h+var_1B0], rax
0x180051e51  lea     r9, [rsp+1D0h+var_18C]
0x180051e56  xor     r8d, r8d
0x180051e59  xor     edx, edx
0x180051e5b  mov     rax, r15
0x180051e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e63  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180051e67  test    eax, eax
0x180051e69  js      short loc_180051EC2
0x180051e6b  cmp     [rsp+1D0h+var_190], r14d
0x180051e70  jnz     short loc_180051EC2
0x180051e72  lea     rax, [rbp+0D0h+Src]
0x180051e76  mov     rdx, rsi
0x180051e79  inc     rdx
0x180051e7c  cmp     [rax+rdx*2], r13w
0x180051e81  jnz     short loc_180051E79
0x180051e83  cmp     rdx, [rbx+18h]
0x180051e87  ja      short loc_180051EB6
0x180051e89  cmp     qword ptr [rbx+18h], 7
0x180051e8e  jbe     short loc_180051E95
0x180051e90  mov     r14, [rbx]
0x180051e93  jmp     short loc_180051E98
0x180051e95  mov     r14, rbx
0x180051e98  mov     [rbx+10h], rdx
0x180051e9c  lea     rbx, [rdx+rdx]
0x180051ea0  mov     r8, rbx; Size
0x180051ea3  lea     rdx, [rbp+0D0h+Src]; Src
0x180051ea7  mov     rcx, r14; void *
0x180051eaa  call    memmove_0
0x180051eaf  mov     [rbx+r14], r13w
0x180051eb4  jmp     short loc_180051EC2
0x180051eb6  lea     r9, [rbp+0D0h+Src]
0x180051eba  mov     rcx, rbx
0x180051ebd  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180051ec2  mov     [rsp+1D0h+var_18C], r13d
0x180051ec7  mov     ebx, 40h ; '@'
0x180051ecc  mov     r8d, ebx; Size
0x180051ecf  xor     edx, edx; Val
0x180051ed1  lea     rcx, [rsp+1D0h+var_170]; void *
0x180051ed6  call    memset_0
0x180051edb  mov     [rsp+1D0h+var_190], ebx
0x180051edf  lea     rax, WNF_CELL_OPERATOR_NAME_CAN1
0x180051ee6  lea     rcx, WNF_CELL_OPERATOR_NAME_CAN0
0x180051eed  cmp     r12d, 1
0x180051ef1  cmovnz  rcx, rax
0x180051ef5  lea     rax, [rsp+1D0h+var_190]
0x180051efa  mov     [rsp+1D0h+var_1A8], rax
0x180051eff  lea     rax, [rsp+1D0h+var_170]
0x180051f04  mov     [rsp+1D0h+var_1B0], rax
0x180051f09  lea     r9, [rsp+1D0h+var_18C]
0x180051f0e  xor     r8d, r8d
0x180051f11  xor     edx, edx
0x180051f13  mov     rax, r15
0x180051f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f1b  test    eax, eax
0x180051f1d  js      short loc_180051F79
0x180051f1f  cmp     [rsp+1D0h+var_190], ebx
0x180051f23  jnz     short loc_180051F79
0x180051f25  lea     rax, [rsp+1D0h+var_170]
0x180051f2a  inc     rsi
0x180051f2d  cmp     [rax+rsi*2], r13w
0x180051f32  jnz     short loc_180051F2A
0x180051f34  cmp     rsi, [rdi+18h]
0x180051f38  ja      short loc_180051F68
0x180051f3a  cmp     qword ptr [rdi+18h], 7
0x180051f3f  jbe     short loc_180051F46
0x180051f41  mov     r14, [rdi]
0x180051f44  jmp     short loc_180051F49
0x180051f46  mov     r14, rdi
0x180051f49  mov     [rdi+10h], rsi
0x180051f4d  lea     rbx, [rsi+rsi]
0x180051f51  mov     r8, rbx; Size
0x180051f54  lea     rdx, [rsp+1D0h+var_170]; Src
0x180051f59  mov     rcx, r14; void *
0x180051f5c  call    memmove_0
0x180051f61  mov     [rbx+r14], r13w
0x180051f66  jmp     short loc_180051F79
0x180051f68  lea     r9, [rsp+1D0h+var_170]
0x180051f6d  mov     rdx, rsi
0x180051f70  mov     rcx, rdi
0x180051f73  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180051f78  nop
0x180051f79  lea     rax, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180051f80  mov     [rsp+1D0h+var_188], rax
0x180051f85  cmp     [rsp+1D0h+var_180], r13
0x180051f8a  jz      loc_180051DA9
0x180051f90  lea     rcx, [rsp+1D0h+var_188]
0x180051f95  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180051f9a  test    al, al
0x180051f9c  jnz     loc_180051DA9
0x180051fa2  call    cs:__imp_GetLastError
0x180051fa8  test    eax, eax
0x180051faa  jle     short loc_180051FB4
0x180051fac  movzx   eax, ax
0x180051faf  or      eax, 80070000h
0x180051fb4  mov     ecx, eax; this
0x180051fb6  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180051fbb  int     3; Trap to Debugger
0x180051fbc  call    cs:__imp_GetLastError
0x180051fc2  test    eax, eax
0x180051fc4  jle     short loc_180051FCE
0x180051fc6  movzx   eax, ax
0x180051fc9  or      eax, 80070000h
0x180051fce  mov     ecx, eax; this
0x180051fd0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
