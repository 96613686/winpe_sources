# CLch::InitializeConditions(HKEY__ *)

- ea: `0x18002f800`
- end: `0x18002fb0d`
- name: `?InitializeConditions@CLch@@AEAAJPEAUHKEY__@@@Z`
- size: `781`
- prototype: `int(CLch *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002f6e8`

## callees

- `0x180001710`
- `0x180004228`
- `0x1800043a8`
- `0x180019c68`
- `0x18001e228`
- `0x18001efb8`
- `0x18002f800`
- `0x18002fb4c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002f9a0`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002f9a0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f96d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f96d`
- `ADVAPI32!RegEnumKeyExW` at `0x18002f8b5`
- `ADVAPI32!RegEnumKeyExW` at `0x18002f8b5`
- `ADVAPI32!RegCloseKey` at `0x18002fa25`
- `ADVAPI32!RegCloseKey` at `0x18002faa4`
- `ADVAPI32!RegCloseKey` at `0x18002fa25`
- `ADVAPI32!RegCloseKey` at `0x18002faa4`
- `ADVAPI32!RegOpenKeyExW` at `0x18002f857`
- `ADVAPI32!RegOpenKeyExW` at `0x18002f8e8`
- `ADVAPI32!RegOpenKeyExW` at `0x18002f857`
- `ADVAPI32!RegOpenKeyExW` at `0x18002f8e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLch::InitializeConditions(CLch *this, HKEY a2)
{
  CLch *v2; // r15
  int v3; // esi
  DWORD v4; // r14d
  HKEY v5; // rax
  HKEY v6; // rbx
  __int64 v7; // rax
  unsigned int v8; // esi
  void *v9; // rax
  __int64 v10; // r13
  _QWORD *v11; // rax
  _QWORD *v12; // rcx
  unsigned __int64 v13; // rax
  _QWORD *v14; // rcx
  _QWORD *v15; // rax
  unsigned int v16; // edx
  _QWORD **v17; // rcx
  _QWORD *v18; // rcx
  _QWORD *v19; // rbx
  __int128 v21; // [rsp+40h] [rbp-D8h] BYREF
  DWORD v22; // [rsp+50h] [rbp-C8h]
  HKEY v23; // [rsp+58h] [rbp-C0h]
  HKEY hKey; // [rsp+60h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-A8h] BYREF
  CLch *v27; // [rsp+78h] [rbp-A0h]
  __int128 *v28; // [rsp+80h] [rbp-98h] BYREF
  __int64 v29; // [rsp+88h] [rbp-90h]
  WCHAR Name[40]; // [rsp+90h] [rbp-88h] BYREF

  v2 = this;
  v27 = this;
  v3 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(a2, L"Conditions", 0, 0x20019u, &hKey) )
  {
    v21 = 0;
    std::list<CLch *>::_Alloc_sentinel_and_proxy(&v21);
    v4 = 0;
    v22 = 0;
    do
    {
      cchName = 40;
      if ( RegEnumKeyExW(hKey, v4, Name, &cchName, 0, 0, 0, 0) )
        break;
      phkResult = 0;
      if ( !RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
      {
        v5 = (HKEY)MemAlloc(0x10u);
        try
        {
          v6 = v5;
          v23 = v5;
          if ( !v5 )
            goto LABEL_13;
          *(_QWORD *)v5 = 0;
          *((_QWORD *)v5 + 1) = 0;
          v23 = phkResult;
          v7 = -1;
          do
            ++v7;
          while ( Name[v7] );
          v8 = v7 + 1;
          v9 = MemAlloc(saturated_mul((unsigned int)(v7 + 1), 2u));
          *(_QWORD *)v6 = v9;
          if ( v9 )
          {
            _o_wcscpy_s(v9, v8, Name);
            RegQueryString(v23, L"Values", (unsigned __int16 **)v6 + 1);
            if ( *((_QWORD *)&v21 + 1) == 0xAAAAAAAAAAAAAAALL )
              std::_Xlength_error("list too long");
            v3 = 0;
            v10 = v21;
            v28 = &v21;
            v29 = 0;
            v11 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(24);
            v11[2] = v6;
            ++*((_QWORD *)&v21 + 1);
            v12 = *(_QWORD **)(v10 + 8);
            *v11 = v10;
            v11[1] = v12;
            v29 = 0;
            *(_QWORD *)(v10 + 8) = v11;
            *v12 = v11;
            std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring *,void *>>>(&v28);
          }
          else
          {
LABEL_13:
            v3 = -2147024882;
          }
        }
        catch ( std::bad_alloc )
        {
          LODWORD(v23) = -2147024882;
          v3 = -2147024882;
          v4 = v22;
          v2 = v27;
        }
        RegCloseKey(phkResult);
      }
      v22 = ++v4;
    }
    while ( v3 >= 0 );
    if ( *((_QWORD *)&v21 + 1) )
    {
      v13 = 8LL * *((_QWORD *)&v21 + 1);
      if ( !is_mul_ok(*((unsigned __int64 *)&v21 + 1), 8u) )
        v13 = -1;
      *((_QWORD *)v2 + 26) = MemAlloc(v13);
      *((_DWORD *)v2 + 58) = 0;
      v14 = (_QWORD *)v21;
      v15 = *(_QWORD **)v21;
      v16 = 0;
      while ( v15 != v14 )
      {
        *(_QWORD *)(*((_QWORD *)v2 + 26) + 8LL * v16) = v15[2];
        v16 = ++*((_DWORD *)v2 + 58);
        v15 = (_QWORD *)*v15;
        v14 = (_QWORD *)v21;
      }
    }
    RegCloseKey(hKey);
    v17 = (_QWORD **)v21;
    **(_QWORD **)(v21 + 8) = 0;
    v18 = *v17;
    if ( v18 )
    {
      do
      {
        v19 = (_QWORD *)*v18;
        std::_Deallocate<16>(v18, 0x18u);
        v18 = v19;
      }
      while ( v19 );
    }
    std::_Deallocate<16>((_QWORD *)v21, 0x18u);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002f800  mov     [rsp+arg_10], rbx
0x18002f805  push    rsi
0x18002f806  push    rdi
0x18002f807  push    r13
0x18002f809  push    r14
0x18002f80b  push    r15
0x18002f80d  sub     rsp, 0F0h
0x18002f814  mov     rax, cs:__security_cookie
0x18002f81b  xor     rax, rsp
0x18002f81e  mov     [rsp+118h+var_38], rax
0x18002f826  mov     rax, rdx
0x18002f829  mov     r15, rcx
0x18002f82c  mov     [rsp+118h+var_A0], rcx
0x18002f831  xor     edi, edi
0x18002f833  mov     esi, edi
0x18002f835  mov     [rsp+118h+hKey], rdi
0x18002f83a  lea     rcx, [rsp+118h+hKey]
0x18002f83f  mov     [rsp+118h+phkResult], rcx; phkResult
0x18002f844  mov     r9d, 20019h; samDesired
0x18002f84a  xor     r8d, r8d; ulOptions
0x18002f84d  lea     rdx, ?c_szLchConditionsKey@@3QBGB; "Conditions"
0x18002f854  mov     rcx, rax; hKey
0x18002f857  call    cs:__imp_RegOpenKeyExW
0x18002f85d  test    eax, eax
0x18002f85f  jnz     loc_18002FAE3
0x18002f865  xorps   xmm0, xmm0
0x18002f868  movdqu  [rsp+118h+var_D8], xmm0
0x18002f86e  lea     rcx, [rsp+118h+var_D8]
0x18002f873  call    ?_Alloc_sentinel_and_proxy@?$list@PEAVCLch@@V?$allocator@PEAVCLch@@@std@@@std@@AEAAXXZ; std::list<CLch *>::_Alloc_sentinel_and_proxy(void)
0x18002f878  nop
0x18002f879  mov     r14d, edi
0x18002f87c  mov     [rsp+118h+var_C8], edi
0x18002f880  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002f884  mov     [rsp+118h+cchName], 28h ; '('
0x18002f88c  mov     [rsp+118h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18002f891  mov     [rsp+118h+lpcchClass], rdi; lpcchClass
0x18002f896  mov     [rsp+118h+lpClass], rdi; lpClass
0x18002f89b  mov     [rsp+118h+phkResult], rdi; lpReserved
0x18002f8a0  lea     r9, [rsp+118h+cchName]; lpcchName
0x18002f8a5  lea     r8, [rsp+118h+Name]; lpName
0x18002f8ad  mov     edx, r14d; dwIndex
0x18002f8b0  mov     rcx, [rsp+118h+hKey]; hKey
0x18002f8b5  call    cs:__imp_RegEnumKeyExW
0x18002f8bb  test    eax, eax
0x18002f8bd  jnz     loc_18002FA3B
0x18002f8c3  mov     [rsp+118h+var_A8], rdi
0x18002f8c8  lea     rax, [rsp+118h+var_A8]
0x18002f8cd  mov     [rsp+118h+phkResult], rax; phkResult
0x18002f8d2  mov     r9d, 20019h; samDesired
0x18002f8d8  xor     r8d, r8d; ulOptions
0x18002f8db  lea     rdx, [rsp+118h+Name]; lpSubKey
0x18002f8e3  mov     rcx, [rsp+118h+hKey]; hKey
0x18002f8e8  call    cs:__imp_RegOpenKeyExW
0x18002f8ee  test    eax, eax
0x18002f8f0  jnz     loc_18002FA2B
0x18002f8f6  lea     ecx, [rax+10h]; unsigned __int64
0x18002f8f9  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18002f8fe  mov     rbx, rax
0x18002f901  mov     [rsp+118h+var_C0], rax
0x18002f906  test    rax, rax
0x18002f909  jz      loc_18002FA05
0x18002f90f  mov     [rax], rdi
0x18002f912  mov     [rax+8], rdi
0x18002f916  test    rax, rax
0x18002f919  jz      loc_18002FA05
0x18002f91f  mov     rax, [rsp+118h+var_A8]
0x18002f924  mov     [rsp+118h+var_C0], rax
0x18002f929  lea     rcx, [rsp+118h+Name]
0x18002f931  mov     rax, r13
0x18002f934  inc     rax
0x18002f937  cmp     [rcx+rax*2], di
0x18002f93b  jnz     short loc_18002F934
0x18002f93d  lea     esi, [rax+1]
0x18002f940  mov     eax, 2
0x18002f945  mul     rsi
0x18002f948  cmovb   rax, r13
0x18002f94c  mov     rcx, rax; unsigned __int64
0x18002f94f  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18002f954  mov     [rbx], rax
0x18002f957  test    rax, rax
0x18002f95a  jz      loc_18002FA05
0x18002f960  lea     r8, [rsp+118h+Name]
0x18002f968  mov     edx, esi
0x18002f96a  mov     rcx, rax
0x18002f96d  call    cs:__imp__o_wcscpy_s
0x18002f973  lea     r8, [rbx+8]; unsigned __int16 **
0x18002f977  lea     rdx, ?c_szLchConditionValues@@3QBGB; "Values"
0x18002f97e  mov     rcx, [rsp+118h+var_C0]; hKey
0x18002f983  call    ?RegQueryString@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; RegQueryString(HKEY__ *,ushort const *,ushort * *)
0x18002f988  mov     rax, 0AAAAAAAAAAAAAAAh
0x18002f992  cmp     qword ptr [rsp+118h+var_D8+8], rax
0x18002f997  jnz     short loc_18002F9A6
0x18002f999  lea     rcx, aListTooLong; "list too long"
0x18002f9a0  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002f9a6  mov     esi, edi
0x18002f9a8  mov     r13, qword ptr [rsp+118h+var_D8]
0x18002f9ad  lea     rax, [rsp+118h+var_D8]
0x18002f9b2  mov     [rsp+118h+var_98], rax
0x18002f9ba  mov     [rsp+118h+var_90], rdi
0x18002f9c2  mov     ecx, 18h
0x18002f9c7  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002f9cc  mov     [rax+10h], rbx
0x18002f9d0  inc     qword ptr [rsp+118h+var_D8+8]
0x18002f9d5  mov     rcx, [r13+8]
0x18002f9d9  mov     [rax], r13
0x18002f9dc  mov     [rax+8], rcx
0x18002f9e0  mov     [rsp+118h+var_90], rdi
0x18002f9e8  mov     [r13+8], rax
0x18002f9ec  mov     [rcx], rax
0x18002f9ef  lea     rcx, [rsp+118h+var_98]
0x18002f9f7  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring *,void *>>>(void)
0x18002f9fc  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18002fa03  jmp     short loc_18002FA0A
0x18002fa05  mov     esi, 8007000Eh
0x18002fa0a  jmp     short loc_18002FA20
0x18002fa0c  xor     edi, edi
0x18002fa0e  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002fa12  mov     esi, dword ptr [rsp+118h+var_C0]
0x18002fa16  mov     r14d, [rsp+118h+var_C8]
0x18002fa1b  mov     r15, [rsp+118h+var_A0]
0x18002fa20  mov     rcx, [rsp+118h+var_A8]; hKey
0x18002fa25  call    cs:__imp_RegCloseKey
0x18002fa2b  inc     r14d
0x18002fa2e  mov     [rsp+118h+var_C8], r14d
0x18002fa33  test    esi, esi
0x18002fa35  jns     loc_18002F884
0x18002fa3b  cmp     qword ptr [rsp+118h+var_D8+8], rdi
0x18002fa40  jz      short loc_18002FA9F
0x18002fa42  mov     eax, 8
0x18002fa47  mul     qword ptr [rsp+118h+var_D8+8]
0x18002fa4c  cmovb   rax, r13
0x18002fa50  mov     rcx, rax; unsigned __int64
0x18002fa53  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18002fa58  mov     [r15+0D0h], rax
0x18002fa5f  mov     [r15+0E8h], edi
0x18002fa66  mov     rcx, qword ptr [rsp+118h+var_D8]
0x18002fa6b  mov     rax, [rcx]
0x18002fa6e  mov     edx, edi
0x18002fa70  cmp     rax, rcx
0x18002fa73  jz      short loc_18002FA9F
0x18002fa75  mov     r8d, edx
0x18002fa78  mov     rdx, [r15+0D0h]
0x18002fa7f  mov     rcx, [rax+10h]
0x18002fa83  mov     [rdx+r8*8], rcx
0x18002fa87  inc     dword ptr [r15+0E8h]
0x18002fa8e  mov     edx, [r15+0E8h]
0x18002fa95  mov     rax, [rax]
0x18002fa98  mov     rcx, qword ptr [rsp+118h+var_D8]
0x18002fa9d  jmp     short loc_18002FA70
0x18002fa9f  mov     rcx, [rsp+118h+hKey]; hKey
0x18002faa4  call    cs:__imp_RegCloseKey
0x18002faaa  nop
0x18002faab  mov     rcx, qword ptr [rsp+118h+var_D8]
0x18002fab0  mov     rax, [rcx+8]
0x18002fab4  mov     [rax], rdi
0x18002fab7  mov     rcx, [rcx]
0x18002faba  test    rcx, rcx
0x18002fabd  jz      short loc_18002FAD4
0x18002fabf  mov     rbx, [rcx]
0x18002fac2  mov     edx, 18h
0x18002fac7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002facc  mov     rcx, rbx
0x18002facf  test    rbx, rbx
0x18002fad2  jnz     short loc_18002FABF
0x18002fad4  mov     edx, 18h
0x18002fad9  mov     rcx, qword ptr [rsp+118h+var_D8]
0x18002fade  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002fae3  mov     eax, esi
0x18002fae5  mov     rcx, [rsp+118h+var_38]
0x18002faed  xor     rcx, rsp; StackCookie
0x18002faf0  call    __security_check_cookie
0x18002faf5  mov     rbx, [rsp+118h+arg_10]
0x18002fafd  add     rsp, 0F0h
0x18002fb04  pop     r15
0x18002fb06  pop     r14
0x18002fb08  pop     r13
0x18002fb0a  pop     rdi
0x18002fb0b  pop     rsi
0x18002fb0c  retn
```
