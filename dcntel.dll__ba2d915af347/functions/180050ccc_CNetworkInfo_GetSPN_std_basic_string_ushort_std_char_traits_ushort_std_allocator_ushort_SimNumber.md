# CNetworkInfo::GetSPN(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,SimNumber)

- ea: `0x180050ccc`
- end: `0x180050ea7`
- name: `?GetSPN@CNetworkInfo@@CAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4SimNumber@@@Z`
- size: `475`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180050c30`
- `0x180050c80`

## callees

- `0x180008dc0`
- `0x180009f08`
- `0x180009f14`
- `0x1800157b8`
- `0x18001daf0`
- `0x18001dcc8`
- `0x180050ccc`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180050d55`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180050d55`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050d9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050d9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e8d`

## string_xrefs

- `0x180050d4e`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HMODULE __fastcall CNetworkInfo::GetSPN(char *a1, int a2, __int64 a3)
{
  char *v4; // rbx
  HMODULE result; // rax
  __int64 *v6; // rcx
  __int64 v7; // r8
  unsigned __int64 v8; // rdx
  char *v9; // rdi
  __int64 v10; // rbx
  signed int LastError; // eax
  int v12; // edx
  unsigned int v13; // r8d
  signed int v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  int v17; // [rsp+40h] [rbp-39h] BYREF
  int v18; // [rsp+44h] [rbp-35h] BYREF
  const int *v19; // [rsp+48h] [rbp-31h] BYREF
  HMODULE v20; // [rsp+50h] [rbp-29h]
  _BYTE v21[44]; // [rsp+60h] [rbp-19h] BYREF
  _WORD Src[18]; // [rsp+8Ch] [rbp+13h] BYREF

  v4 = a1;
  if ( *((_QWORD *)a1 + 3) )
  {
    if ( *((_QWORD *)a1 + 3) > 7u )
      a1 = *(char **)a1;
    *((_QWORD *)v4 + 2) = 1;
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
  v18 = 0;
  memset_0(v21, 0, 0x4Cu);
  v17 = 76;
  result = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v19 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v20 = result;
  if ( result )
  {
    result = (HMODULE)GetProcAddress(result, "NtQueryWnfStateData");
    if ( result )
    {
      v6 = &WNF_CELL_UICC_STATUS_DETAILS_SLOT0;
      if ( a2 != 1 )
        v6 = &WNF_CELL_UICC_STATUS_DETAILS_SLOT1;
      result = (HMODULE)((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, int *, _BYTE *, int *))result)(
                          v6,
                          0,
                          0,
                          &v18,
                          v21,
                          &v17);
      if ( (int)result >= 0 && v17 == 76 )
      {
        v8 = -1;
        do
          ++v8;
        while ( Src[v8] );
        if ( v8 > *((_QWORD *)v4 + 3) )
        {
          result = (HMODULE)std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                              (char **)v4,
                              v8,
                              v7,
                              Src);
        }
        else
        {
          if ( *((_QWORD *)v4 + 3) <= 7u )
            v9 = v4;
          else
            v9 = *(char **)v4;
          *((_QWORD *)v4 + 2) = v8;
          v10 = 2 * v8;
          result = (HMODULE)memmove_0(v9, Src, 2 * v8);
          *(_WORD *)&v9[v10] = 0;
        }
      }
      v19 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( v20 )
      {
        result = (HMODULE)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v19);
        if ( !(_BYTE)result )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v12, v13);
          __debugbreak();
        }
      }
    }
    else
    {
      v19 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( v20 )
      {
        result = (HMODULE)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v19);
        if ( !(_BYTE)result )
        {
          v14 = GetLastError();
          if ( v14 > 0 )
            v14 = (unsigned __int16)v14 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
          JUMPOUT(0x180050EA6LL);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180050ccc  mov     [rsp-8+arg_8], rbx
0x180050cd1  mov     [rsp-8+arg_10], rsi
0x180050cd6  push    rbp
0x180050cd7  push    rdi
0x180050cd8  push    r15
0x180050cda  lea     rbp, [rsp-47h]
0x180050cdf  sub     rsp, 0C0h
0x180050ce6  mov     rax, cs:__security_cookie
0x180050ced  xor     rax, rsp
0x180050cf0  mov     [rbp+57h+var_20], rax
0x180050cf4  mov     edi, edx
0x180050cf6  mov     rbx, rcx
0x180050cf9  xor     esi, esi
0x180050cfb  cmp     qword ptr [rcx+18h], 1
0x180050d00  jb      short loc_180050D1C
0x180050d02  cmp     qword ptr [rcx+18h], 7
0x180050d07  jbe     short loc_180050D0C
0x180050d09  mov     rcx, [rcx]
0x180050d0c  mov     qword ptr [rbx+10h], 1
0x180050d14  mov     dword ptr [rcx], 23h ; '#'
0x180050d1a  jmp     short loc_180050D2D
0x180050d1c  lea     r9, asc_1801B4764; "#"
0x180050d23  mov     edx, 1
0x180050d28  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180050d2d  mov     [rbp+57h+var_8C], esi
0x180050d30  xor     edx, edx; Val
0x180050d32  lea     r8d, [rdx+4Ch]; Size
0x180050d36  lea     rcx, [rbp+57h+var_70]; void *
0x180050d3a  call    memset_0
0x180050d3f  mov     [rbp+57h+var_90], 4Ch ; 'L'
0x180050d46  xor     edx, edx; hFile
0x180050d48  mov     r8d, 800h; dwFlags
0x180050d4e  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180050d55  call    cs:__imp_LoadLibraryExW
0x180050d5b  lea     r15, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180050d62  mov     [rbp+57h+var_88], r15
0x180050d66  mov     [rbp+57h+var_80], rax
0x180050d6a  test    rax, rax
0x180050d6d  jnz     short loc_180050D93
0x180050d6f  mov     rcx, [rbp+57h+var_20]
0x180050d73  xor     rcx, rsp; StackCookie
0x180050d76  call    __security_check_cookie
0x180050d7b  lea     r11, [rsp+0D0h+var_10]
0x180050d83  mov     rbx, [r11+28h]
0x180050d87  mov     rsi, [r11+30h]
0x180050d8b  mov     rsp, r11
0x180050d8e  pop     r15
0x180050d90  pop     rdi
0x180050d91  pop     rbp
0x180050d92  retn
0x180050d93  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180050d9a  mov     rcx, rax; hModule
0x180050d9d  call    cs:__imp_GetProcAddress
0x180050da3  test    rax, rax
0x180050da6  jnz     short loc_180050DC5
0x180050da8  mov     [rbp+57h+var_88], r15
0x180050dac  cmp     [rbp+57h+var_80], rsi
0x180050db0  jz      short loc_180050D6F
0x180050db2  lea     rcx, [rbp+57h+var_88]
0x180050db6  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180050dbb  test    al, al
0x180050dbd  jz      loc_180050E8D
0x180050dc3  jmp     short loc_180050D6F
0x180050dc5  lea     rdx, WNF_CELL_UICC_STATUS_DETAILS_SLOT1
0x180050dcc  lea     rcx, WNF_CELL_UICC_STATUS_DETAILS_SLOT0
0x180050dd3  cmp     edi, 1
0x180050dd6  cmovnz  rcx, rdx
0x180050dda  lea     rdx, [rbp+57h+var_90]
0x180050dde  mov     [rsp+0D0h+var_A8], rdx
0x180050de3  lea     rdx, [rbp+57h+var_70]
0x180050de7  mov     [rsp+0D0h+var_B0], rdx
0x180050dec  lea     r9, [rbp+57h+var_8C]
0x180050df0  xor     r8d, r8d
0x180050df3  xor     edx, edx
0x180050df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050dfa  test    eax, eax
0x180050dfc  js      short loc_180050E54
0x180050dfe  cmp     [rbp+57h+var_90], 4Ch ; 'L'
0x180050e02  jnz     short loc_180050E54
0x180050e04  lea     rax, [rbp+57h+Src]
0x180050e08  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180050e0c  inc     rdx
0x180050e0f  cmp     [rax+rdx*2], si
0x180050e13  jnz     short loc_180050E0C
0x180050e15  cmp     rdx, [rbx+18h]
0x180050e19  ja      short loc_180050E47
0x180050e1b  cmp     qword ptr [rbx+18h], 7
0x180050e20  jbe     short loc_180050E27
0x180050e22  mov     rdi, [rbx]
0x180050e25  jmp     short loc_180050E2A
0x180050e27  mov     rdi, rbx
0x180050e2a  mov     [rbx+10h], rdx
0x180050e2e  lea     rbx, [rdx+rdx]
0x180050e32  mov     r8, rbx; Size
0x180050e35  lea     rdx, [rbp+57h+Src]; Src
0x180050e39  mov     rcx, rdi; void *
0x180050e3c  call    memmove_0
0x180050e41  mov     [rbx+rdi], si
0x180050e45  jmp     short loc_180050E54
0x180050e47  lea     r9, [rbp+57h+Src]
0x180050e4b  mov     rcx, rbx
0x180050e4e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180050e53  nop
0x180050e54  mov     [rbp+57h+var_88], r15
0x180050e58  cmp     [rbp+57h+var_80], rsi
0x180050e5c  jz      loc_180050D6F
0x180050e62  lea     rcx, [rbp+57h+var_88]
0x180050e66  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180050e6b  test    al, al
0x180050e6d  jnz     loc_180050D6F
0x180050e73  call    cs:__imp_GetLastError
0x180050e79  test    eax, eax
0x180050e7b  jle     short loc_180050E85
0x180050e7d  movzx   eax, ax
0x180050e80  or      eax, 80070000h
0x180050e85  mov     ecx, eax; this
0x180050e87  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180050e8c  int     3; Trap to Debugger
0x180050e8d  call    cs:__imp_GetLastError
0x180050e93  test    eax, eax
0x180050e95  jle     short loc_180050E9F
0x180050e97  movzx   eax, ax
0x180050e9a  or      eax, 80070000h
0x180050e9f  mov     ecx, eax; this
0x180050ea1  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
