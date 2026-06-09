# LpacRegHelper::GetLpacMitigationPolicy(void *,ushort const *,ushort const *,void *,unsigned __int64 * *,ulong)

- ea: `0x180020898`
- end: `0x180020aa9`
- name: `?GetLpacMitigationPolicy@LpacRegHelper@@CAJPEAXPEBG10PEAPEA_KK@Z`
- size: `529`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, void *, unsigned __int64 **, DWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020664`

## callees

- `0x180004594`
- `0x18000a4d8`
- `0x18000a740`
- `0x18000c7d4`
- `0x18001ef5c`
- `0x180020898`
- `0x180020f70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800209e6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800209e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002090e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002090e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a65`

## string_xrefs

- `0x1800208c7`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x180020977`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x180020a3e`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x180020a81`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LpacRegHelper::GetLpacMitigationPolicy(
        const WCHAR *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void *a4,
        unsigned __int64 **a5,
        DWORD pcbData)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  unsigned __int64 **v10; // r14
  const WCHAR *v11; // rax
  unsigned __int64 *v12; // rbx
  const WCHAR *v13; // rcx
  HKEY *v14; // rax
  void *v15; // rcx
  int v16; // eax
  unsigned int v17; // edi
  __int64 v18; // rsi
  int v19; // eax
  LSTATUS ValueW; // eax
  unsigned __int64 v22; // r9
  __int64 v23; // rdx
  int pdwType; // [rsp+20h] [rbp-20h]
  int pdwTypea; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  LPCWSTR lpValue; // [rsp+60h] [rbp+20h] BYREF
  HKEY hkey; // [rsp+68h] [rbp+28h] BYREF

  lpValue = a1;
  if ( !a2 )
  {
    v8 = 661;
LABEL_3:
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)0x80070057LL,
      pdwType);
    return v9;
  }
  if ( !a3 )
  {
    v8 = 662;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v8 = 663;
    goto LABEL_3;
  }
  v10 = a5;
  if ( !a5 )
  {
    v8 = 664;
    goto LABEL_3;
  }
  v11 = (const WCHAR *)LocalAlloc(0, 0x18u);
  v12 = (unsigned __int64 *)v11;
  lpValue = v11;
  if ( v11 )
  {
    v13 = v11 + 12;
    do
    {
      *(_QWORD *)v11 = 0;
      v11 += 4;
    }
    while ( v11 != v13 );
  }
  if ( !v12 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29B,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)0x8007000ELL,
      pdwType);
    return v9;
  }
  hkey = 0;
  v14 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
  v16 = LpacRegHelper::OpenLpacRegistrySubKey(v15, a2, a3, 0, v14);
  v17 = v16;
  if ( v16 >= 0 )
  {
    v18 = 0;
    while ( 1 )
    {
      lpValue = 0;
      v19 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &lpValue,
              L"MitigationOption%d",
              v18);
      v17 = v19;
      if ( v19 < 0 )
        break;
      pcbData = 8;
      ValueW = RegGetValueW(hkey, 0, lpValue, 0x40u, 0, &v12[v18], &pcbData);
      v17 = ValueW;
      if ( ValueW > 0 )
        v17 = (unsigned __int16)ValueW | 0x80070000;
      if ( (v17 & 0x80000000) != 0 )
      {
        v22 = v17;
        v23 = 693;
        goto LABEL_25;
      }
      wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&lpValue);
      if ( (unsigned __int64)++v18 >= 3 )
      {
        *v10 = v12;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        return 0;
      }
    }
    v22 = (unsigned int)v19;
    v23 = 687;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)v22,
      pdwTypea);
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&lpValue);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A5,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)(unsigned int)v16,
      pdwTypea);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  LocalFree(v12);
  return v17;
}

```

## disassembly

```asm
0x180020898  mov     [rsp-18h+arg_10], rbx
0x18002089d  mov     [rsp-18h+arg_18], rsi
0x1800208a2  mov     [rsp-18h+lpValue], rcx
0x1800208a7  push    rbp
0x1800208a8  push    rdi
0x1800208a9  push    r14
0x1800208ab  mov     rbp, rsp
0x1800208ae  sub     rsp, 40h
0x1800208b2  mov     rdi, r8
0x1800208b5  mov     rsi, rdx
0x1800208b8  test    rdx, rdx
0x1800208bb  jnz     short loc_1800208DF
0x1800208bd  mov     edx, 295h; void *
0x1800208c2  mov     ebx, 80070057h
0x1800208c7  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800208ce  mov     r9d, ebx; char *
0x1800208d1  mov     rcx, [rbp+18h]; this
0x1800208d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800208da  jmp     loc_180020A93
0x1800208df  test    rdi, rdi
0x1800208e2  jnz     short loc_1800208EB
0x1800208e4  mov     edx, 296h
0x1800208e9  jmp     short loc_1800208C2
0x1800208eb  test    r9, r9
0x1800208ee  jnz     short loc_1800208F7
0x1800208f0  mov     edx, 297h
0x1800208f5  jmp     short loc_1800208C2
0x1800208f7  mov     r14, [rbp+arg_20]
0x1800208fb  test    r14, r14
0x1800208fe  jnz     short loc_180020907
0x180020900  mov     edx, 298h
0x180020905  jmp     short loc_1800208C2
0x180020907  mov     edx, 18h; uBytes
0x18002090c  xor     ecx, ecx; uFlags
0x18002090e  call    cs:__imp_LocalAlloc
0x180020915  nop     dword ptr [rax+rax+00h]
0x18002091a  mov     rbx, rax
0x18002091d  mov     [rbp+lpValue], rax
0x180020921  test    rax, rax
0x180020924  jz      short loc_18002093D
0x180020926  lea     rcx, [rax+18h]
0x18002092a  cmp     rax, rcx
0x18002092d  jz      short loc_18002093D
0x18002092f  xor     edx, edx
0x180020931  mov     [rax], rdx
0x180020934  add     rax, 8
0x180020938  cmp     rax, rcx
0x18002093b  jnz     short loc_18002092F
0x18002093d  test    rbx, rbx
0x180020940  jz      loc_180020A75
0x180020946  mov     [rbp+hkey], 0
0x18002094e  lea     rcx, [rbp+hkey]
0x180020952  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180020957  mov     [rsp+40h+pdwType], rax; int
0x18002095c  xor     r9d, r9d; unsigned __int16 *
0x18002095f  mov     r8, rdi; unsigned __int16 *
0x180020962  mov     rdx, rsi; unsigned __int16 *
0x180020965  call    ?OpenLpacRegistrySubKey@LpacRegHelper@@CAJPEAXPEBG11PEAPEAUHKEY__@@@Z; LpacRegHelper::OpenLpacRegistrySubKey(void *,ushort const *,ushort const *,ushort const *,HKEY__ * *)
0x18002096a  mov     edi, eax
0x18002096c  test    eax, eax
0x18002096e  jns     short loc_18002098D
0x180020970  mov     rcx, [rbp+18h]; this
0x180020974  mov     r9d, eax; char *
0x180020977  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002097e  mov     edx, 2A5h; void *
0x180020983  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020988  jmp     loc_180020A58
0x18002098d  xor     esi, esi
0x18002098f  mov     [rbp+lpValue], 0
0x180020997  mov     r8, rsi
0x18002099a  lea     rdx, aMitigationopti; "MitigationOption%d"
0x1800209a1  lea     rcx, [rbp+lpValue]
0x1800209a5  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x1800209aa  mov     edi, eax
0x1800209ac  test    eax, eax
0x1800209ae  js      loc_180020A36
0x1800209b4  lea     rax, [rbx+rsi*8]
0x1800209b8  mov     [rbp+arg_28], 8
0x1800209bf  lea     rcx, [rbp+arg_28]
0x1800209c3  mov     [rsp+40h+pcbData], rcx; pcbData
0x1800209c8  mov     [rsp+40h+pvData], rax; pvData
0x1800209cd  mov     [rsp+40h+pdwType], 0; pdwType
0x1800209d6  mov     r9d, 40h ; '@'; dwFlags
0x1800209dc  mov     r8, [rbp+lpValue]; lpValue
0x1800209e0  xor     edx, edx; lpSubKey
0x1800209e2  mov     rcx, [rbp+hkey]; hkey
0x1800209e6  call    cs:__imp_RegGetValueW
0x1800209ed  nop     dword ptr [rax+rax+00h]
0x1800209f2  mov     edi, eax
0x1800209f4  test    eax, eax
0x1800209f6  jle     short loc_180020A01
0x1800209f8  movzx   edi, ax
0x1800209fb  or      edi, 80070000h
0x180020a01  test    edi, edi
0x180020a03  js      short loc_180020A2C
0x180020a05  lea     rcx, [rbp+lpValue]
0x180020a09  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x180020a0e  inc     rsi
0x180020a11  cmp     rsi, 3
0x180020a15  jb      loc_18002098F
0x180020a1b  mov     [r14], rbx
0x180020a1e  lea     rcx, [rbp+hkey]
0x180020a22  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020a27  nop
0x180020a28  xor     eax, eax
0x180020a2a  jmp     short loc_180020A95
0x180020a2c  mov     r9d, edi
0x180020a2f  mov     edx, 2B5h
0x180020a34  jmp     short loc_180020A3E
0x180020a36  mov     r9d, eax; char *
0x180020a39  mov     edx, 2AFh; void *
0x180020a3e  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180020a45  mov     rcx, [rbp+18h]; this
0x180020a49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020a4e  lea     rcx, [rbp+lpValue]
0x180020a52  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x180020a57  nop
0x180020a58  lea     rcx, [rbp+hkey]
0x180020a5c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020a61  nop
0x180020a62  mov     rcx, rbx; hMem
0x180020a65  call    cs:__imp_LocalFree
0x180020a6c  nop     dword ptr [rax+rax+00h]
0x180020a71  mov     eax, edi
0x180020a73  jmp     short loc_180020A95
0x180020a75  mov     rcx, [rbp+18h]; this
0x180020a79  mov     ebx, 8007000Eh
0x180020a7e  mov     r9d, ebx; char *
0x180020a81  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180020a88  mov     edx, 29Bh; void *
0x180020a8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020a92  nop
0x180020a93  mov     eax, ebx
0x180020a95  mov     rbx, [rsp+40h+arg_10]
0x180020a9a  mov     rsi, [rsp+40h+arg_18]
0x180020a9f  add     rsp, 40h
0x180020aa3  pop     r14
0x180020aa5  pop     rdi
0x180020aa6  pop     rbp
0x180020aa7  retn
```
