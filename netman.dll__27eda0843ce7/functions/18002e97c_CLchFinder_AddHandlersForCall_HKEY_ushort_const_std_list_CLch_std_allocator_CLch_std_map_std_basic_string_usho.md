# CLchFinder::AddHandlersForCall(HKEY__ *,ushort const *,std::list<CLch *,std::allocator<CLch *>> &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x18002e97c`
- end: `0x18002ec4b`
- name: `?AddHandlersForCall@CLchFinder@@AEAAJPEAUHKEY__@@PEBGAEAV?$list@PEAVCLch@@V?$allocator@PEAVCLch@@@std@@@std@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@4@@Z`
- size: `719`
- prototype: `__int64 __fastcall(__int64, HKEY, unsigned __int16 *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x18002ec54`

## callees

- `0x180001710`
- `0x180004228`
- `0x180004340`
- `0x180004d04`
- `0x180004d80`
- `0x180019c68`
- `0x18001e1e4`
- `0x18001e228`
- `0x18002e6c0`
- `0x18002e97c`
- `0x18002f120`
- `0x18002f6e8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002eac7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002eac7`
- `ADVAPI32!RegEnumKeyExW` at `0x18002ea16`
- `ADVAPI32!RegEnumKeyExW` at `0x18002ea16`
- `ADVAPI32!RegCloseKey` at `0x18002ec04`
- `ADVAPI32!RegCloseKey` at `0x18002ec04`
- `ADVAPI32!RegOpenKeyExW` at `0x18002ea4e`
- `ADVAPI32!RegOpenKeyExW` at `0x18002ea4e`
- `ADVAPI32!RegQueryValueExW` at `0x18002eb78`
- `ADVAPI32!RegQueryValueExW` at `0x18002eb78`

## pseudocode

```c
__int64 __fastcall CLchFinder::AddHandlersForCall(__int64 a1, HKEY a2, unsigned __int16 *a3, _QWORD *a4, __int64 a5)
{
  _QWORD *v5; // r15
  HKEY v6; // r12
  int v7; // esi
  DWORD v8; // edi
  LSTATUS v9; // r14d
  CLch *v10; // rax
  CLch *v11; // r14
  __int64 v12; // r13
  _QWORD *v13; // rcx
  _QWORD *v14; // rax
  char *v15; // rax
  __int64 v16; // rdx
  DWORD v18; // [rsp+40h] [rbp-178h]
  HKEY phkResult; // [rsp+48h] [rbp-170h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-168h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-164h] BYREF
  HKEY v22; // [rsp+58h] [rbp-160h]
  _QWORD *v23; // [rsp+60h] [rbp-158h]
  unsigned __int16 *v24; // [rsp+70h] [rbp-148h]
  __int64 *v25; // [rsp+80h] [rbp-138h]
  __int64 v26; // [rsp+88h] [rbp-130h]
  _QWORD *v27; // [rsp+90h] [rbp-128h] BYREF
  __int64 v28; // [rsp+98h] [rbp-120h]
  CLch *v29; // [rsp+A0h] [rbp-118h]
  char v30[16]; // [rsp+A8h] [rbp-110h] BYREF
  _BYTE v31[40]; // [rsp+B8h] [rbp-100h] BYREF
  WCHAR Name[40]; // [rsp+E0h] [rbp-D8h] BYREF
  BYTE Data[80]; // [rsp+130h] [rbp-88h] BYREF

  v5 = a4;
  v6 = a2;
  v25 = a4;
  v22 = a2;
  v24 = a3;
  v23 = a4;
  v26 = a5;
  v7 = 0;
  v8 = 0;
LABEL_2:
  v18 = v8;
  do
  {
    cchName = 40;
    v9 = RegEnumKeyExW(v6, v8, Name, &cchName, 0, 0, 0, 0);
    if ( !v9 )
    {
      phkResult = 0;
      if ( !RegOpenKeyExW(v6, Name, 0, 0x20019u, &phkResult) )
      {
        v10 = (CLch *)MemAlloc(0x248u);
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          v29 = v10;
          if ( v10 )
            v11 = CLch::CLch(v10);
          else
            v11 = 0;
          if ( v11 )
          {
            v7 = CLch::Initialize(v11, phkResult, v24, Name);
            if ( v7 >= 0 )
            {
              if ( v5[1] == 0xAAAAAAAAAAAAAAALL )
                std::_Xlength_error("list too long");
              v12 = *v25;
              v27 = v5;
              v28 = 0;
              v13 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(24);
              v13[2] = v11;
              ++v5[1];
              v14 = *(_QWORD **)(v12 + 8);
              *v13 = v12;
              v13[1] = v14;
              v28 = 0;
              *(_QWORD *)(v12 + 8) = v13;
              *v14 = v13;
              std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring *,void *>>>(&v27);
            }
          }
          else
          {
            v7 = -2147024882;
          }
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
          {
            v7 = -2147024882;
            v8 = v18;
            v6 = v22;
            v5 = v23;
            __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18002EB35);
          }
        }
        if ( __eh34_try(-1, 2) )
        {
          __eh34_scope_strut(2);
          cbData = 80;
          if ( !RegQueryValueExW(phkResult, L"DeActivationHandler", 0, 0, Data, &cbData) )
          {
            std::wstring::wstring(v31, Name);
            std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(v26, v30, v31);
            v15 = (char *)std::_WChar_traits<unsigned short>::length(Data);
            std::wstring::_Assign<unsigned short>((char **)(*(_QWORD *)v16 + 64LL), Data, v15);
            std::wstring::_Tidy_deallocate((__int64)v31);
          }
        }
        if ( __eh34_catch(2) )
        {
          if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
          {
            v7 = -2147024882;
            v8 = v18;
            v6 = v22;
            v5 = v23;
            __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_18002EBED);
          }
        }
        RegCloseKey(phkResult);
        ++v8;
        goto LABEL_2;
      }
    }
    v18 = ++v8;
  }
  while ( !v9 );
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002e97c  mov     [rsp+arg_0], rsi
0x18002e981  push    rdi
0x18002e982  push    r12
0x18002e984  push    r13
0x18002e986  push    r14
0x18002e988  push    r15
0x18002e98a  sub     rsp, 190h
0x18002e991  mov     rax, cs:__security_cookie
0x18002e998  xor     rax, rsp
0x18002e99b  mov     [rsp+1B8h+var_38], rax
0x18002e9a3  mov     r15, r9
0x18002e9a6  mov     r12, rdx
0x18002e9a9  mov     [rsp+1B8h+var_138], r9
0x18002e9b1  mov     [rsp+1B8h+var_160], rdx
0x18002e9b6  mov     [rsp+1B8h+var_148], r8
0x18002e9bb  mov     [rsp+1B8h+var_158], r9
0x18002e9c0  mov     rax, [rsp+1B8h+arg_20]
0x18002e9c8  mov     [rsp+1B8h+var_130], rax
0x18002e9d0  xor     esi, esi
0x18002e9d2  xor     edi, edi
0x18002e9d4  mov     [rsp+1B8h+var_178], edi
0x18002e9d8  mov     [rsp+1B8h+cchName], 28h ; '('
0x18002e9e0  mov     [rsp+1B8h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18002e9e9  mov     [rsp+1B8h+lpcchClass], 0; lpcchClass
0x18002e9f2  mov     [rsp+1B8h+lpClass], 0; lpClass
0x18002e9fb  mov     [rsp+1B8h+lpReserved], 0; lpReserved
0x18002ea04  lea     r9, [rsp+1B8h+cchName]; lpcchName
0x18002ea09  lea     r8, [rsp+1B8h+Name]; lpName
0x18002ea11  mov     edx, edi; dwIndex
0x18002ea13  mov     rcx, r12; hKey
0x18002ea16  call    cs:__imp_RegEnumKeyExW
0x18002ea1c  mov     r14d, eax
0x18002ea1f  test    eax, eax
0x18002ea21  jnz     loc_18002EC11
0x18002ea27  mov     [rsp+1B8h+phkResult], 0
0x18002ea30  lea     rax, [rsp+1B8h+phkResult]
0x18002ea35  mov     [rsp+1B8h+lpReserved], rax; phkResult
0x18002ea3a  mov     r9d, 20019h; samDesired
0x18002ea40  xor     r8d, r8d; ulOptions
0x18002ea43  lea     rdx, [rsp+1B8h+Name]; lpSubKey
0x18002ea4b  mov     rcx, r12; hKey
0x18002ea4e  call    cs:__imp_RegOpenKeyExW
0x18002ea54  test    eax, eax
0x18002ea56  jnz     loc_18002EC11
0x18002ea5c  mov     ecx, 248h; unsigned __int64
0x18002ea61  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18002ea66  mov     [rsp+1B8h+var_118], rax
0x18002ea6e  test    rax, rax
0x18002ea71  jz      short loc_18002EA80
0x18002ea73  mov     rcx, rax; this
0x18002ea76  call    ??0CLch@@QEAA@XZ; CLch::CLch(void)
0x18002ea7b  mov     r14, rax
0x18002ea7e  jmp     short loc_18002EA83
0x18002ea80  xor     r14d, r14d
0x18002ea83  test    r14, r14
0x18002ea86  jz      loc_18002EB2E
0x18002ea8c  lea     r9, [rsp+1B8h+Name]; unsigned __int16 *
0x18002ea94  mov     r8, [rsp+1B8h+var_148]; unsigned __int16 *
0x18002ea99  mov     rdx, [rsp+1B8h+phkResult]; HKEY
0x18002ea9e  mov     rcx, r14; this
0x18002eaa1  call    ?Initialize@CLch@@QEAAJPEAUHKEY__@@PEBG1@Z; CLch::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18002eaa6  mov     esi, eax
0x18002eaa8  test    eax, eax
0x18002eaaa  js      loc_18002EB33
0x18002eab0  mov     rax, 0AAAAAAAAAAAAAAAh
0x18002eaba  cmp     [r15+8], rax
0x18002eabe  jnz     short loc_18002EACD
0x18002eac0  lea     rcx, aListTooLong; "list too long"
0x18002eac7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002eacd  mov     rax, [rsp+1B8h+var_138]
0x18002ead5  mov     r13, [rax]
0x18002ead8  mov     [rsp+1B8h+var_128], r15
0x18002eae0  mov     [rsp+1B8h+var_120], 0
0x18002eaec  mov     ecx, 18h
0x18002eaf1  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002eaf6  mov     rcx, rax
0x18002eaf9  mov     [rax+10h], r14
0x18002eafd  inc     qword ptr [r15+8]
0x18002eb01  mov     rax, [r13+8]
0x18002eb05  mov     [rcx], r13
0x18002eb08  mov     [rcx+8], rax
0x18002eb0c  mov     [rsp+1B8h+var_120], 0
0x18002eb18  mov     [r13+8], rcx
0x18002eb1c  mov     [rax], rcx
0x18002eb1f  lea     rcx, [rsp+1B8h+var_128]
0x18002eb27  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring *,void *>>>(void)
0x18002eb2c  jmp     short loc_18002EB33
0x18002eb2e  mov     esi, 8007000Eh
0x18002eb33  jmp     short loc_18002EB47
0x18002eb35  mov     esi, [rsp+1B8h+var_174]
0x18002eb39  mov     edi, [rsp+1B8h+var_178]
0x18002eb3d  mov     r12, [rsp+1B8h+var_160]
0x18002eb42  mov     r15, [rsp+1B8h+var_158]
0x18002eb47  mov     [rsp+1B8h+cbData], 50h ; 'P'
0x18002eb4f  lea     rax, [rsp+1B8h+cbData]
0x18002eb54  mov     [rsp+1B8h+lpClass], rax; lpcbData
0x18002eb59  lea     rax, [rsp+1B8h+Data]
0x18002eb61  mov     [rsp+1B8h+lpReserved], rax; lpData
0x18002eb66  xor     r9d, r9d; lpType
0x18002eb69  xor     r8d, r8d; lpReserved
0x18002eb6c  lea     rdx, ?c_szLchDeActivationHandler@@3QBGB; "DeActivationHandler"
0x18002eb73  mov     rcx, [rsp+1B8h+phkResult]; hKey
0x18002eb78  call    cs:__imp_RegQueryValueExW
0x18002eb7e  test    eax, eax
0x18002eb80  jnz     short loc_18002EBFF
0x18002eb82  lea     rdx, [rsp+1B8h+Name]
0x18002eb8a  lea     rcx, [rsp+1B8h+var_100]
0x18002eb92  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002eb97  nop
0x18002eb98  lea     r8, [rsp+1B8h+var_100]
0x18002eba0  lea     rdx, [rsp+1B8h+var_110]
0x18002eba8  mov     rcx, [rsp+1B8h+var_130]
0x18002ebb0  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18002ebb5  mov     rdx, rax
0x18002ebb8  lea     rcx, [rsp+1B8h+Data]
0x18002ebc0  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002ebc5  mov     r8, rax
0x18002ebc8  mov     rcx, [rdx]
0x18002ebcb  add     rcx, 40h ; '@'
0x18002ebcf  lea     rdx, [rsp+1B8h+Data]
0x18002ebd7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002ebdc  nop
0x18002ebdd  lea     rcx, [rsp+1B8h+var_100]
0x18002ebe5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ebea  nop
0x18002ebeb  jmp     short loc_18002EBFF
0x18002ebed  mov     esi, [rsp+1B8h+var_174]
0x18002ebf1  mov     edi, [rsp+1B8h+var_178]
0x18002ebf5  mov     r12, [rsp+1B8h+var_160]
0x18002ebfa  mov     r15, [rsp+1B8h+var_158]
0x18002ebff  mov     rcx, [rsp+1B8h+phkResult]; hKey
0x18002ec04  call    cs:__imp_RegCloseKey
0x18002ec0a  inc     edi
0x18002ec0c  jmp     loc_18002E9D4
0x18002ec11  inc     edi
0x18002ec13  mov     [rsp+1B8h+var_178], edi
0x18002ec17  test    r14d, r14d
0x18002ec1a  jz      loc_18002E9D8
0x18002ec20  mov     eax, esi
0x18002ec22  mov     rcx, [rsp+1B8h+var_38]
0x18002ec2a  xor     rcx, rsp; StackCookie
0x18002ec2d  call    __security_check_cookie
0x18002ec32  mov     rsi, [rsp+1B8h+arg_0]
0x18002ec3a  add     rsp, 190h
0x18002ec41  pop     r15
0x18002ec43  pop     r14
0x18002ec45  pop     r13
0x18002ec47  pop     r12
0x18002ec49  pop     rdi
0x18002ec4a  retn
```
