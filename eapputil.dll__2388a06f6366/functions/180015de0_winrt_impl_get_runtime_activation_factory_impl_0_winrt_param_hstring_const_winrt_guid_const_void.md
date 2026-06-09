# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180015de0`
- end: `0x180016148`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `872`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015bec`

## callees

- `0x1800021d0`
- `0x180002cdb`
- `0x180002d17`
- `0x1800036a0`
- `0x18000397d`
- `0x180003989`
- `0x1800039b9`
- `0x1800039c5`
- `0x1800083ec`
- `0x180013cd0`
- `0x180015018`
- `0x180015158`
- `0x180015de0`
- `0x180017418`
- `0x180033010`

## string_xrefs

- `0x180015e48`: `combase.dll`
- `0x180016088`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  LPCWSTR *v12; // r14
  char *v13; // rdi
  __int64 last_trivial_2; // rax
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rdi
  LPCWSTR *v17; // rcx
  unsigned __int64 v18; // rcx
  LPCWSTR *v19; // r8
  _WORD *v20; // rdi
  unsigned __int64 v21; // rdi
  LPCWSTR *v22; // rcx
  const WCHAR *v23; // rcx
  HMODULE v24; // rdi
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // r8
  LPCWSTR *v27; // rcx
  FARPROC v28; // rax
  unsigned int (__fastcall ***v30)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v33; // [rsp+50h] [rbp-28h]
  unsigned __int64 v34; // [rsp+58h] [rbp-20h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, __int64))winrt_activation_handler)(v8, a3, a4);
    return a1;
  }
  ActivationFactory_0 = RoGetActivationFactory_0(v8, a3, a4);
  if ( ActivationFactory_0 == -2147221008 )
  {
    Library = LoadLibraryExW_0(L"combase.dll", 0, 0x1000u);
    ProcAddress = WINRT_IMPL_GetProcAddress(Library, "CoIncrementMTAUsage");
    if ( !ProcAddress )
    {
      *a1 = -2147221008;
      return a1;
    }
    v30 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v30);
    ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  *(_OWORD *)lpLibFileName = 0;
  v33 = 0;
  v34 = 0;
  std::wstring::_Construct<1,unsigned short const *>(lpLibFileName);
  while ( 1 )
  {
    do
    {
      v12 = lpLibFileName;
      if ( v34 > 7 )
        v12 = (LPCWSTR *)lpLibFileName[0];
      if ( !v33
        || (v13 = (char *)v12 + 2 * v33,
            last_trivial_2 = _std_find_last_trivial_2(v12, v13, 46),
            (char *)last_trivial_2 == v13)
        || (v15 = (last_trivial_2 - (__int64)v12) >> 1, v15 == -1) )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_54;
      }
      v16 = v33;
      if ( v15 > v33 )
      {
        v18 = v15 - v33;
        if ( v15 - v33 > v34 - v33 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(lpLibFileName);
        }
        else
        {
          v33 = (last_trivial_2 - (__int64)v12) >> 1;
          v19 = lpLibFileName;
          if ( v34 > 7 )
            v19 = (LPCWSTR *)lpLibFileName[0];
          v20 = (_WORD *)v19 + v16;
          if ( v18 )
          {
            while ( v18 )
            {
              *v20++ = 0;
              --v18;
            }
          }
          *((_WORD *)v19 + v15) = 0;
        }
      }
      else
      {
        v33 = (last_trivial_2 - (__int64)v12) >> 1;
        v17 = lpLibFileName;
        if ( v34 > 7 )
          v17 = (LPCWSTR *)lpLibFileName[0];
        *((_WORD *)v17 + v15) = 0;
      }
      v21 = v33;
      if ( v34 - v33 < 4 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          lpLibFileName,
          4);
      }
      else
      {
        v33 += 4LL;
        v22 = lpLibFileName;
        if ( v34 > 7 )
          v22 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v22 + 2 * v21) = (LPCWSTR)0x6C006C0064002ELL;
        *((_WORD *)v22 + v21 + 4) = 0;
      }
      v23 = (const WCHAR *)lpLibFileName;
      if ( v34 > 7 )
        v23 = lpLibFileName[0];
      v24 = LoadLibraryExW_0(v23, 0, 0x1000u);
      v25 = v33;
      v26 = v33 - 4;
      v27 = lpLibFileName;
      if ( v33 >= 4 )
      {
        v33 -= 4LL;
        if ( v34 > 7 )
          v27 = (LPCWSTR *)lpLibFileName[0];
LABEL_42:
        *((_WORD *)v27 + v26) = 0;
        continue;
      }
      if ( v34 - v33 >= 0xFFFFFFFFFFFFFFFCuLL )
      {
        v33 -= 4LL;
        if ( v34 > 7 )
          v27 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v27 + 2 * v25) = 0;
        goto LABEL_42;
      }
      std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(lpLibFileName);
    }
    while ( !v24 );
    v28 = WINRT_IMPL_GetProcAddress(v24, "DllGetActivationFactory");
    if ( !v28 )
      goto LABEL_50;
    v30 = 0;
    if ( !((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v28)(
            *a2,
            &v30)
      && !(**v30)(v30, a3, a4) )
    {
      break;
    }
    if ( v30 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v30);
LABEL_50:
    WINRT_IMPL_FreeLibrary(v24);
  }
  *a1 = 0;
  if ( v30 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v30);
LABEL_54:
  std::wstring::~wstring(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180015de0  push    rbp
0x180015de2  push    rbx
0x180015de3  push    rsi
0x180015de4  push    rdi
0x180015de5  push    r12
0x180015de7  push    r13
0x180015de9  push    r14
0x180015deb  push    r15
0x180015ded  mov     rbp, rsp
0x180015df0  sub     rsp, 78h
0x180015df4  mov     rax, cs:__security_cookie
0x180015dfb  xor     rax, rsp
0x180015dfe  mov     [rbp+var_18], rax
0x180015e02  mov     r13, r9
0x180015e05  mov     r12, r8
0x180015e08  mov     r15, rdx
0x180015e0b  mov     rsi, rcx
0x180015e0e  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180015e15  xor     r14d, r14d
0x180015e18  mov     r8, r9
0x180015e1b  mov     rdx, r12
0x180015e1e  mov     rcx, [r15]
0x180015e21  test    rax, rax
0x180015e24  jz      short loc_180015E32
0x180015e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e2b  mov     [rsi], eax
0x180015e2d  jmp     loc_180016128
0x180015e32  call    RoGetActivationFactory_0
0x180015e37  mov     ebx, eax
0x180015e39  cmp     eax, 800401F0h
0x180015e3e  jnz     short loc_180015E90
0x180015e40  xor     edx, edx; hFile
0x180015e42  mov     r8d, 1000h; dwFlags
0x180015e48  lea     rcx, LibFileName; "combase.dll"
0x180015e4f  call    LoadLibraryExW_0
0x180015e54  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x180015e5b  mov     rcx, rax; hModule
0x180015e5e  call    WINRT_IMPL_GetProcAddress
0x180015e63  test    rax, rax
0x180015e66  jnz     short loc_180015E73
0x180015e68  mov     dword ptr [rsi], 800401F0h
0x180015e6e  jmp     loc_180016128
0x180015e73  mov     [rbp+var_48], r14
0x180015e77  lea     rcx, [rbp+var_48]
0x180015e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e80  mov     r8, r13
0x180015e83  mov     rdx, r12
0x180015e86  mov     rcx, [r15]
0x180015e89  call    RoGetActivationFactory_0
0x180015e8e  mov     ebx, eax
0x180015e90  test    ebx, ebx
0x180015e92  jnz     short loc_180015E9C
0x180015e94  mov     [rsi], r14d
0x180015e97  jmp     loc_180016128
0x180015e9c  mov     [rbp+pperrinfo], r14
0x180015ea0  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180015ea4  xor     ecx, ecx; dwReserved
0x180015ea6  call    GetErrorInfo_0
0x180015eab  xorps   xmm0, xmm0
0x180015eae  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x180015eb2  mov     [rbp+var_28], r14
0x180015eb6  mov     [rbp+var_20], r14
0x180015eba  mov     rax, [r15]
0x180015ebd  test    rax, rax
0x180015ec0  jz      short loc_180015ECC
0x180015ec2  mov     rdx, [rax+10h]
0x180015ec6  mov     r8d, [rax+4]
0x180015eca  jmp     short loc_180015ED6
0x180015ecc  lea     rdx, Src
0x180015ed3  mov     r8, r14
0x180015ed6  lea     rcx, [rbp+lpLibFileName]
0x180015eda  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180015edf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180015ee3  mov     rax, [rbp+var_28]
0x180015ee7  lea     r14, [rbp+lpLibFileName]
0x180015eeb  cmp     [rbp+var_20], 7
0x180015ef0  cmova   r14, [rbp+lpLibFileName]
0x180015ef5  test    rax, rax
0x180015ef8  jz      loc_180016102
0x180015efe  dec     rax
0x180015f01  cmp     rax, rcx
0x180015f04  cmovnb  rax, rcx
0x180015f08  inc     rax
0x180015f0b  lea     rdi, [r14+rax*2]
0x180015f0f  mov     r8d, 2Eh ; '.'
0x180015f15  mov     rdx, rdi
0x180015f18  mov     rcx, r14
0x180015f1b  call    __std_find_last_trivial_2
0x180015f20  mov     rdx, rax
0x180015f23  cmp     rax, rdi
0x180015f26  jz      loc_180016102
0x180015f2c  sub     rdx, r14
0x180015f2f  sar     rdx, 1
0x180015f32  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180015f36  jz      loc_180016102
0x180015f3c  mov     rdi, [rbp+var_28]
0x180015f40  cmp     rdx, rdi
0x180015f43  ja      short loc_180015F5F
0x180015f45  mov     [rbp+var_28], rdx
0x180015f49  lea     rcx, [rbp+lpLibFileName]
0x180015f4d  cmp     [rbp+var_20], 7
0x180015f52  cmova   rcx, [rbp+lpLibFileName]
0x180015f57  xor     eax, eax
0x180015f59  mov     [rcx+rdx*2], ax
0x180015f5d  jmp     short loc_180015FAC
0x180015f5f  mov     rcx, rdx
0x180015f62  sub     rcx, rdi
0x180015f65  mov     rax, [rbp+var_20]
0x180015f69  sub     rax, rdi
0x180015f6c  cmp     rcx, rax
0x180015f6f  ja      short loc_180015F9D
0x180015f71  mov     [rbp+var_28], rdx
0x180015f75  lea     r8, [rbp+lpLibFileName]
0x180015f79  cmp     [rbp+var_20], 7
0x180015f7e  cmova   r8, [rbp+lpLibFileName]
0x180015f83  lea     rdi, [r8+rdi*2]
0x180015f87  test    rcx, rcx
0x180015f8a  jz      short loc_180015F94
0x180015f8c  xor     eax, eax
0x180015f8e  movzx   eax, ax
0x180015f91  rep stosw
0x180015f94  xor     eax, eax
0x180015f96  mov     [r8+rdx*2], ax
0x180015f9b  jmp     short loc_180015FAC
0x180015f9d  mov     r9, rcx
0x180015fa0  mov     rdx, rcx
0x180015fa3  lea     rcx, [rbp+lpLibFileName]; Src
0x180015fa7  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180015fac  mov     rdi, [rbp+var_28]
0x180015fb0  mov     rax, [rbp+var_20]
0x180015fb4  sub     rax, rdi
0x180015fb7  mov     ecx, 4
0x180015fbc  cmp     rax, rcx
0x180015fbf  jb      short loc_180015FED
0x180015fc1  lea     rdx, [rdi+4]
0x180015fc5  mov     [rbp+var_28], rdx
0x180015fc9  lea     rcx, [rbp+lpLibFileName]
0x180015fcd  cmp     [rbp+var_20], 7
0x180015fd2  cmova   rcx, [rbp+lpLibFileName]
0x180015fd7  mov     rax, 6C006C0064002Eh
0x180015fe1  mov     [rcx+rdi*2], rax
0x180015fe5  xor     eax, eax
0x180015fe7  mov     [rcx+rdx*2], ax
0x180015feb  jmp     short loc_180015FFE
0x180015fed  mov     [rsp+78h+var_58], rcx; __int64
0x180015ff2  mov     rdx, rcx
0x180015ff5  lea     rcx, [rbp+lpLibFileName]; Src
0x180015ff9  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x180015ffe  lea     rcx, [rbp+lpLibFileName]
0x180016002  cmp     [rbp+var_20], 7
0x180016007  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18001600c  xor     edx, edx; hFile
0x18001600e  mov     r8d, 1000h; dwFlags
0x180016014  call    LoadLibraryExW_0
0x180016019  mov     rdi, rax
0x18001601c  mov     rdx, [rbp+var_28]
0x180016020  lea     r8, [rdx-4]
0x180016024  lea     rcx, [rbp+lpLibFileName]; Src
0x180016028  cmp     r8, rdx
0x18001602b  ja      short loc_18001603F
0x18001602d  mov     [rbp+var_28], r8
0x180016031  cmp     [rbp+var_20], 7
0x180016036  cmova   rcx, [rbp+lpLibFileName]
0x18001603b  xor     eax, eax
0x18001603d  jmp     short loc_180016066
0x18001603f  mov     rax, [rbp+var_20]
0x180016043  sub     rax, rdx
0x180016046  mov     r10, 0FFFFFFFFFFFFFFFCh
0x18001604d  cmp     rax, r10
0x180016050  jb      short loc_18001606D
0x180016052  mov     [rbp+var_28], r8
0x180016056  cmp     [rbp+var_20], 7
0x18001605b  cmova   rcx, [rbp+lpLibFileName]
0x180016060  xor     eax, eax
0x180016062  mov     [rcx+rdx*2], rax
0x180016066  mov     [rcx+r8*2], ax
0x18001606b  jmp     short loc_180016078
0x18001606d  mov     r9, r10
0x180016070  mov     rdx, r10
0x180016073  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180016078  test    rdi, rdi
0x18001607b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180016082  jz      loc_180015EE3
0x180016088  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x18001608f  mov     rcx, rdi; hModule
0x180016092  call    WINRT_IMPL_GetProcAddress
0x180016097  test    rax, rax
0x18001609a  jz      short loc_1800160DD
0x18001609c  mov     [rbp+var_48], 0
0x1800160a4  lea     rdx, [rbp+var_48]
0x1800160a8  mov     rcx, [r15]
0x1800160ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160b0  test    eax, eax
0x1800160b2  jnz     short loc_1800160CD
0x1800160b4  mov     rcx, [rbp+var_48]
0x1800160b8  mov     rax, [rcx]
0x1800160bb  mov     r8, r13
0x1800160be  mov     rdx, r12
0x1800160c1  mov     rax, [rax]
0x1800160c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160c9  test    eax, eax
0x1800160cb  jz      short loc_1800160EA
0x1800160cd  cmp     [rbp+var_48], 0
0x1800160d2  jz      short loc_1800160DD
0x1800160d4  lea     rcx, [rbp+var_48]
0x1800160d8  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800160dd  mov     rcx, rdi; hLibModule
0x1800160e0  call    WINRT_IMPL_FreeLibrary
0x1800160e5  jmp     loc_180015EDF
0x1800160ea  mov     dword ptr [rsi], 0
0x1800160f0  cmp     [rbp+var_48], 0
0x1800160f5  jz      short loc_18001610F
0x1800160f7  lea     rcx, [rbp+var_48]
0x1800160fb  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180016100  jmp     short loc_18001610F
0x180016102  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180016106  xor     ecx, ecx; dwReserved
0x180016108  call    SetErrorInfo_0
0x18001610d  mov     [rsi], ebx
0x18001610f  lea     rcx, [rbp+lpLibFileName]
0x180016113  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016118  cmp     [rbp+pperrinfo], 0
0x18001611d  jz      short loc_180016128
0x18001611f  lea     rcx, [rbp+pperrinfo]
0x180016123  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180016128  mov     rax, rsi
0x18001612b  mov     rcx, [rbp+var_18]
0x18001612f  xor     rcx, rsp; StackCookie
0x180016132  call    __security_check_cookie
0x180016137  add     rsp, 78h
0x18001613b  pop     r15
0x18001613d  pop     r14
0x18001613f  pop     r13
0x180016141  pop     r12
0x180016143  pop     rdi
0x180016144  pop     rsi
0x180016145  pop     rbx
0x180016146  pop     rbp
0x180016147  retn
```
