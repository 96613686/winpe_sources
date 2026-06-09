# OpenDisplayMux(ushort const *,int,HKEY__ * *)

- ea: `0x18004da68`
- end: `0x18004deb1`
- name: `?OpenDisplayMux@@YAJPEBGHPEAPEAUHKEY__@@@Z`
- size: `1097`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, HKEY *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006f60`
- `0x180007bb0`

## callees

- `0x180008bf0`
- `0x18001f340`
- `0x180026620`
- `0x180026640`
- `0x1800269d4`
- `0x180029404`
- `0x18004d894`
- `0x18004d904`
- `0x18004d930`
- `0x18004da68`
- `0x18004def8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004db8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004dbf4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004dc25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004dd69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ddc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004db8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004dbf4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004dc25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004dd69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ddc9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OpenDisplayMux(const unsigned __int16 *a1, int a2, HKEY *a3)
{
  const char *v6; // r9
  __int64 result; // rax
  const unsigned __int16 *v8; // rsi
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  HKEY v13; // rbx
  HKEY v14; // rbx
  __int64 v15; // rcx
  REGSAM v16; // r9d
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // eax
  unsigned int v20; // ebx
  HKEY v21; // rbx
  __int64 v22; // rdi
  HKEY v23; // rbx
  HKEY v24; // rax
  int v25; // [rsp+20h] [rbp-68h]
  int v26; // [rsp+20h] [rbp-68h]
  HKEY v27; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v28[8]; // [rsp+38h] [rbp-50h] BYREF
  unsigned __int16 *v29[3]; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int16 *v30[3]; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  HKEY hKey; // [rsp+A8h] [rbp+20h] BYREF

  try
  {
    if ( !IsDisplayInMuxPair(a1) )
      return 2147942487LL;
    hKey = 0;
    std::vector<unsigned short>::vector<unsigned short>(v29);
    v8 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ICM\\ProfileAssociations\\Display\\";
    if ( !a2 )
      v8 = L"SYSTEM\\CurrentControlSet\\Control\\Class\\";
    v9 = StringCchCatW(v29[0], 0x104u, v8);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBC,
        (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\displaymuxprofileoperations.cxx",
        (const char *)(unsigned int)v9,
        v25);
      std::vector<unsigned short>::_Tidy(v29);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v10;
    }
    v11 = StringCchCatW(v29[0], 0x104u, L"{4d36e96e-e325-11ce-bfc1-08002be10318}\\MDM0");
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBD,
        (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\displaymuxprofileoperations.cxx",
        (const char *)(unsigned int)v11,
        v25);
      std::vector<unsigned short>::_Tidy(v29);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v12;
    }
    v13 = hKey;
    if ( a2 )
    {
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v27);
        RegCloseKey(v13);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v27);
      }
      v15 = -2147483647;
      v16 = 131099;
    }
    else
    {
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v27);
        RegCloseKey(v13);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v27);
      }
      hKey = 0;
      if ( !CreateOrOpenKey_0(HKEY_LOCAL_MACHINE, v29[0], 0, 0x2001Bu, &hKey) )
      {
LABEL_33:
        v24 = hKey;
        if ( hKey )
        {
          hKey = 0;
          *a3 = v24;
          std::vector<unsigned short>::_Tidy(v29);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return 0;
        }
        else
        {
          std::vector<unsigned short>::_Tidy(v29);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return 2147500037LL;
        }
      }
      v14 = hKey;
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v27);
        RegCloseKey(v14);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v27);
      }
      v15 = -2147483646;
      v16 = 131097;
    }
    hKey = 0;
    if ( CreateOrOpenKey_0((HKEY)v15, v29[0], 0, v16, &hKey) )
    {
      v27 = 0;
      std::vector<unsigned short>::vector<unsigned short>(v30);
      v17 = StringCchCatW(v30[0], 0x104u, v8);
      v18 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE6,
          (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\displaymuxprofileoperations.cxx",
          (const char *)(unsigned int)v17,
          v26);
        std::vector<unsigned short>::_Tidy(v30);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
        std::vector<unsigned short>::_Tidy(v29);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v18;
      }
      v19 = StringCchCatW(v30[0], 0x104u, a1);
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE7,
          (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\displaymuxprofileoperations.cxx",
          (const char *)(unsigned int)v19,
          v26);
        std::vector<unsigned short>::_Tidy(v30);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
        std::vector<unsigned short>::_Tidy(v29);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v20;
      }
      v21 = v27;
      if ( v27 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v28);
        RegCloseKey(v21);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v28);
      }
      v27 = 0;
      v22 = -(__int64)(a2 != 0);
      if ( !CreateOrOpenKey_0((HKEY)(v22 - 2147483646), v30[0], 0, 0x20019u, &v27) )
      {
        v23 = hKey;
        if ( hKey )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)v28);
          RegCloseKey(v23);
          wil::last_error_context::~last_error_context((wil::last_error_context *)v28);
        }
        hKey = 0;
        if ( !CreateOrOpenKey_0((HKEY)(v22 - 2147483646), v29[0], 1, 0x2001Bu, &hKey) )
          MirrorRegKeys(v27, hKey);
      }
      std::vector<unsigned short>::_Tidy(v30);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
    }
    goto LABEL_33;
  }
  catch ( ... )
  {
    LODWORD(hKey) = wil::details::in1diag3::Return_CaughtException(
                      retaddr,
                      (void *)0x107,
                      (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\displaymuxprofileoperations.cxx",
                      v6);
    return (unsigned int)hKey;
  }
  return result;
}

```

## disassembly

```asm
0x18004da68  mov     [rsp+arg_0], rbx
0x18004da6d  mov     [rsp+arg_8], rsi
0x18004da72  push    rdi
0x18004da73  push    r12
0x18004da75  push    r15
0x18004da77  sub     rsp, 70h
0x18004da7b  mov     r12, r8
0x18004da7e  mov     edi, edx
0x18004da80  mov     r15, rcx
0x18004da83  call    ?IsDisplayInMuxPair@@YA_NPEBG@Z; IsDisplayInMuxPair(ushort const *)
0x18004da88  test    al, al
0x18004da8a  jnz     short loc_18004DA96
0x18004da8c  mov     eax, 80070057h
0x18004da91  jmp     loc_18004DE9A
0x18004da96  mov     [rsp+88h+hKey], 0
0x18004daa2  lea     rcx, [rsp+88h+var_48]
0x18004daa7  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18004daac  nop
0x18004daad  lea     rax, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Cla"...
0x18004dab4  lea     rsi, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x18004dabb  test    edi, edi
0x18004dabd  cmovz   rsi, rax
0x18004dac1  mov     r8, rsi; unsigned __int16 *
0x18004dac4  mov     edx, 104h; unsigned __int64
0x18004dac9  mov     rcx, [rsp+88h+var_48]; unsigned __int16 *
0x18004dace  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004dad3  mov     ebx, eax
0x18004dad5  test    eax, eax
0x18004dad7  jns     short loc_18004DB15
0x18004dad9  mov     rcx, [rsp+88h]; this
0x18004dae1  mov     r9d, eax; char *
0x18004dae4  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\core\\color\\mscms"...
0x18004daeb  mov     edx, 0BCh; void *
0x18004daf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004daf5  nop
0x18004daf6  lea     rcx, [rsp+88h+var_48]
0x18004dafb  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004db00  nop
0x18004db01  lea     rcx, [rsp+88h+hKey]
0x18004db09  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004db0e  mov     eax, ebx
0x18004db10  jmp     loc_18004DE9A
0x18004db15  lea     r8, a4d36e96eE32511; "{4d36e96e-e325-11ce-bfc1-08002be10318}"...
0x18004db1c  mov     edx, 104h; unsigned __int64
0x18004db21  mov     rcx, [rsp+88h+var_48]; unsigned __int16 *
0x18004db26  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004db2b  mov     ebx, eax
0x18004db2d  test    eax, eax
0x18004db2f  jns     short loc_18004DB6D
0x18004db31  mov     rcx, [rsp+88h]; this
0x18004db39  mov     r9d, eax; char *
0x18004db3c  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\core\\color\\mscms"...
0x18004db43  mov     edx, 0BDh; void *
0x18004db48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004db4d  nop
0x18004db4e  lea     rcx, [rsp+88h+var_48]
0x18004db53  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004db58  nop
0x18004db59  lea     rcx, [rsp+88h+hKey]
0x18004db61  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004db66  mov     eax, ebx
0x18004db68  jmp     loc_18004DE9A
0x18004db6d  mov     rbx, [rsp+88h+hKey]
0x18004db75  test    edi, edi
0x18004db77  jnz     loc_18004DC13
0x18004db7d  test    rbx, rbx
0x18004db80  jz      short loc_18004DB9F
0x18004db82  lea     rcx, [rsp+88h+var_58]; this
0x18004db87  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004db8c  mov     rcx, rbx; hKey
0x18004db8f  call    cs:__imp_RegCloseKey
0x18004db95  lea     rcx, [rsp+88h+var_58]; this
0x18004db9a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004db9f  mov     [rsp+88h+hKey], 0
0x18004dbab  lea     rax, [rsp+88h+hKey]
0x18004dbb3  mov     qword ptr [rsp+88h+var_68], rax
0x18004dbb8  mov     r9d, 2001Bh
0x18004dbbe  xor     r8d, r8d
0x18004dbc1  mov     rdx, [rsp+88h+var_48]
0x18004dbc6  mov     rcx, 0FFFFFFFF80000002h
0x18004dbcd  call    CreateOrOpenKey_0
0x18004dbd2  test    eax, eax
0x18004dbd4  jz      loc_18004DE3B
0x18004dbda  mov     rbx, [rsp+88h+hKey]
0x18004dbe2  test    rbx, rbx
0x18004dbe5  jz      short loc_18004DC04
0x18004dbe7  lea     rcx, [rsp+88h+var_58]; this
0x18004dbec  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004dbf1  mov     rcx, rbx; hKey
0x18004dbf4  call    cs:__imp_RegCloseKey
0x18004dbfa  lea     rcx, [rsp+88h+var_58]; this
0x18004dbff  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004dc04  mov     rcx, 0FFFFFFFF80000002h
0x18004dc0b  mov     r9d, 20019h
0x18004dc11  jmp     short loc_18004DC42
0x18004dc13  test    rbx, rbx
0x18004dc16  jz      short loc_18004DC35
0x18004dc18  lea     rcx, [rsp+88h+var_58]; this
0x18004dc1d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004dc22  mov     rcx, rbx; hKey
0x18004dc25  call    cs:__imp_RegCloseKey
0x18004dc2b  lea     rcx, [rsp+88h+var_58]; this
0x18004dc30  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004dc35  mov     rcx, 0FFFFFFFF80000001h
0x18004dc3c  mov     r9d, 2001Bh
0x18004dc42  lea     rax, [rsp+88h+hKey]
0x18004dc4a  xor     r8d, r8d
0x18004dc4d  mov     rdx, [rsp+88h+var_48]
0x18004dc52  mov     [rsp+88h+hKey], r8
0x18004dc5a  mov     qword ptr [rsp+88h+var_68], rax; int
0x18004dc5f  call    CreateOrOpenKey_0
0x18004dc64  test    eax, eax
0x18004dc66  jz      loc_18004DE3B
0x18004dc6c  mov     [rsp+88h+var_58], 0
0x18004dc75  lea     rcx, [rsp+88h+var_30]
0x18004dc7a  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18004dc7f  nop
0x18004dc80  mov     r8, rsi; unsigned __int16 *
0x18004dc83  mov     esi, 104h
0x18004dc88  mov     edx, esi; unsigned __int64
0x18004dc8a  mov     rcx, [rsp+88h+var_30]; unsigned __int16 *
0x18004dc8f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004dc94  mov     ebx, eax
0x18004dc96  test    eax, eax
0x18004dc98  jns     short loc_18004DCEA
0x18004dc9a  mov     rcx, [rsp+88h]; this
0x18004dca2  mov     r9d, eax; char *
0x18004dca5  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\core\\color\\mscms"...
0x18004dcac  lea     edx, [rsi-1Eh]; void *
0x18004dcaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dcb4  nop
0x18004dcb5  lea     rcx, [rsp+88h+var_30]
0x18004dcba  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004dcbf  nop
0x18004dcc0  lea     rcx, [rsp+88h+var_58]
0x18004dcc5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004dcca  nop
0x18004dccb  lea     rcx, [rsp+88h+var_48]
0x18004dcd0  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004dcd5  nop
0x18004dcd6  lea     rcx, [rsp+88h+hKey]
0x18004dcde  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004dce3  mov     eax, ebx
0x18004dce5  jmp     loc_18004DE9A
0x18004dcea  mov     r8, r15; unsigned __int16 *
0x18004dced  mov     rdx, rsi; unsigned __int64
0x18004dcf0  mov     rcx, [rsp+88h+var_30]; unsigned __int16 *
0x18004dcf5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004dcfa  mov     ebx, eax
0x18004dcfc  test    eax, eax
0x18004dcfe  jns     short loc_18004DD52
0x18004dd00  mov     rcx, [rsp+88h]; this
0x18004dd08  mov     r9d, eax; char *
0x18004dd0b  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\core\\color\\mscms"...
0x18004dd12  mov     edx, 0E7h; void *
0x18004dd17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dd1c  nop
0x18004dd1d  lea     rcx, [rsp+88h+var_30]
0x18004dd22  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004dd27  nop
0x18004dd28  lea     rcx, [rsp+88h+var_58]
0x18004dd2d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004dd32  nop
0x18004dd33  lea     rcx, [rsp+88h+var_48]
0x18004dd38  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004dd3d  nop
0x18004dd3e  lea     rcx, [rsp+88h+hKey]
0x18004dd46  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004dd4b  mov     eax, ebx
0x18004dd4d  jmp     loc_18004DE9A
0x18004dd52  mov     rbx, [rsp+88h+var_58]
0x18004dd57  test    rbx, rbx
0x18004dd5a  jz      short loc_18004DD79
0x18004dd5c  lea     rcx, [rsp+88h+var_50]; this
0x18004dd61  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004dd66  mov     rcx, rbx; hKey
0x18004dd69  call    cs:__imp_RegCloseKey
0x18004dd6f  lea     rcx, [rsp+88h+var_50]; this
0x18004dd74  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004dd79  mov     [rsp+88h+var_58], 0
0x18004dd82  neg     edi
0x18004dd84  sbb     rdi, rdi
0x18004dd87  lea     rax, [rsp+88h+var_58]
0x18004dd8c  mov     qword ptr [rsp+88h+var_68], rax
0x18004dd91  mov     r9d, 20019h
0x18004dd97  xor     r8d, r8d
0x18004dd9a  mov     rdx, [rsp+88h+var_30]
0x18004dd9f  lea     rcx, [rdi-7FFFFFFEh]
0x18004dda6  call    CreateOrOpenKey_0
0x18004ddab  test    eax, eax
0x18004ddad  jnz     short loc_18004DE26
0x18004ddaf  mov     rbx, [rsp+88h+hKey]
0x18004ddb7  test    rbx, rbx
0x18004ddba  jz      short loc_18004DDD9
0x18004ddbc  lea     rcx, [rsp+88h+var_50]; this
0x18004ddc1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004ddc6  mov     rcx, rbx; hKey
0x18004ddc9  call    cs:__imp_RegCloseKey
0x18004ddcf  lea     rcx, [rsp+88h+var_50]; this
0x18004ddd4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004ddd9  mov     [rsp+88h+hKey], 0
0x18004dde5  lea     rax, [rsp+88h+hKey]
0x18004dded  mov     qword ptr [rsp+88h+var_68], rax
0x18004ddf2  mov     r9d, 2001Bh
0x18004ddf8  mov     r8d, 1
0x18004ddfe  mov     rdx, [rsp+88h+var_48]
0x18004de03  lea     rcx, [rdi-7FFFFFFEh]
0x18004de0a  call    CreateOrOpenKey_0
0x18004de0f  test    eax, eax
0x18004de11  jnz     short loc_18004DE26
0x18004de13  mov     rdx, [rsp+88h+hKey]; HKEY
0x18004de1b  mov     rcx, [rsp+88h+var_58]; hKey
0x18004de20  call    ?MirrorRegKeys@@YAXPEAUHKEY__@@0@Z; MirrorRegKeys(HKEY__ *,HKEY__ *)
0x18004de25  nop
0x18004de26  lea     rcx, [rsp+88h+var_30]
0x18004de2b  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004de30  nop
0x18004de31  lea     rcx, [rsp+88h+var_58]
0x18004de36  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004de3b  mov     rax, [rsp+88h+hKey]
0x18004de43  test    rax, rax
0x18004de46  jz      short loc_18004DE74
0x18004de48  mov     [rsp+88h+hKey], 0
0x18004de54  mov     [r12], rax
0x18004de58  lea     rcx, [rsp+88h+var_48]
0x18004de5d  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004de62  nop
0x18004de63  lea     rcx, [rsp+88h+hKey]
0x18004de6b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004de70  xor     eax, eax
0x18004de72  jmp     short loc_18004DE9A
0x18004de74  lea     rcx, [rsp+88h+var_48]
0x18004de79  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004de7e  nop
0x18004de7f  lea     rcx, [rsp+88h+hKey]
0x18004de87  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004de8c  mov     eax, 80004005h
0x18004de91  jmp     short loc_18004DE9A
0x18004de93  mov     eax, dword ptr [rsp+88h+hKey]
0x18004de9a  lea     r11, [rsp+88h+var_18]
0x18004de9f  mov     rbx, [r11+20h]
0x18004dea3  mov     rsi, [r11+28h]
0x18004dea7  mov     rsp, r11
0x18004deaa  pop     r15
0x18004deac  pop     r12
0x18004deae  pop     rdi
0x18004deaf  retn
```
