# NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180022ef4`
- end: `0x180023083`
- name: `?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z`
- size: `399`
- prototype: `__int64 __fastcall(NgcUtils *this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `17`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015644`
- `0x180015bf0`
- `0x180017070`
- `0x1800176a4`
- `0x180018eec`
- `0x180019424`
- `0x18001a170`
- `0x18001a698`
- `0x18001aae8`
- `0x18001b0b4`
- `0x18001b6a0`
- `0x18001bbdc`
- `0x18001c2f8`
- `0x18001c508`
- `0x18001c760`
- `0x18001ca98`
- `0x18001e1a4`

## callees

- `0x18000b0fc`
- `0x18000db5c`
- `0x180010730`
- `0x180013270`
- `0x1800136b0`
- `0x180015030`
- `0x180022ef4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022fe0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002306e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022fe0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002306e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180022f36`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180022fb4`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180022f36`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180022fb4`

## string_xrefs

- `0x180022f5f`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180022fc2`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180023025`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NgcUtils::GetNgcStateSeparatedRegistryLocation(
        NgcUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int PersistedRegistryLocationW; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  HLOCAL v10; // rbx
  unsigned int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  HLOCAL v14; // rax
  int v15; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HLOCAL hMem; // [rsp+50h] [rbp+20h] BYREF
  unsigned __int16 *v18; // [rsp+58h] [rbp+28h] BYREF

  HIDWORD(v18) = HIDWORD(a2);
  hMem = this;
  LODWORD(v18) = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"NgcCrypto",
                                 L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\Ngc",
                                 0,
                                 0);
  v7 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW != 234 )
  {
    if ( PersistedRegistryLocationW > 0 )
      v7 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( (v7 & 0x80000000) == 0 )
      return v7;
    v8 = 182;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)v7,
      (int)&v18);
    return v7;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, (unsigned int)v18);
  v10 = hMem;
  if ( !hMem )
  {
    v7 = -2147024882;
    v8 = 185;
    goto LABEL_6;
  }
  v11 = GetPersistedRegistryLocationW(
          L"NgcCrypto",
          L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\Ngc",
          hMem,
          (unsigned int)v18);
  if ( v11 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xC0,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
            (const char *)v11,
            (unsigned int)&v18);
LABEL_12:
    if ( v10 )
      LocalFree(v10);
    return v12;
  }
  if ( a3 )
  {
    hMem = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &hMem,
      0);
    v13 = NgcUtils::CombineSeparateStrings((NgcUtils *)v10, L"\\", a3, (const unsigned __int16 *)&hMem, &v18);
    v12 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
        (const char *)(unsigned int)v13,
        v15);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
      goto LABEL_12;
    }
    *(_QWORD *)a4 = hMem;
    hMem = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  }
  else
  {
    v14 = v10;
    v10 = 0;
    *(_QWORD *)a4 = v14;
  }
  if ( v10 )
    LocalFree(v10);
  return 0;
}

```

## disassembly

```asm
0x180022ef4  mov     r11, rsp
0x180022ef7  mov     [r11+18h], rbx
0x180022efb  mov     [r11+10h], rdx
0x180022eff  mov     [r11+8], rcx
0x180022f03  push    rbp
0x180022f04  push    rsi
0x180022f05  push    rdi
0x180022f06  mov     rbp, rsp
0x180022f09  sub     rsp, 30h
0x180022f0d  mov     rsi, r9
0x180022f10  mov     dword ptr [rbp+arg_8], 0
0x180022f17  mov     rdi, r8
0x180022f1a  lea     rax, [rbp+arg_8]
0x180022f1e  xor     r9d, r9d
0x180022f21  mov     [r11-28h], rax
0x180022f25  xor     r8d, r8d
0x180022f28  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x180022f2f  lea     rcx, aNgccrypto; "NgcCrypto"
0x180022f36  call    cs:__imp_GetPersistedRegistryLocationW
0x180022f3c  mov     ebx, eax
0x180022f3e  cmp     eax, 0EAh
0x180022f43  jz      short loc_180022F75
0x180022f45  test    eax, eax
0x180022f47  jle     short loc_180022F52
0x180022f49  movzx   ebx, ax
0x180022f4c  or      ebx, 80070000h
0x180022f52  test    ebx, ebx
0x180022f54  jns     short loc_180022F6E
0x180022f56  mov     edx, 0B6h; void *
0x180022f5b  mov     rcx, [rbp+18h]; this
0x180022f5f  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180022f66  mov     r9d, ebx; char *
0x180022f69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022f6e  mov     eax, ebx
0x180022f70  jmp     loc_180023076
0x180022f75  mov     edx, dword ptr [rbp+arg_8]
0x180022f78  lea     rcx, [rbp+hMem]
0x180022f7c  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180022f81  mov     rbx, [rbp+hMem]
0x180022f85  test    rbx, rbx
0x180022f88  jnz     short loc_180022F96
0x180022f8a  mov     ebx, 8007000Eh
0x180022f8f  mov     edx, 0B9h
0x180022f94  jmp     short loc_180022F5B
0x180022f96  mov     r9d, dword ptr [rbp+arg_8]
0x180022f9a  lea     rax, [rbp+arg_8]
0x180022f9e  mov     r8, rbx
0x180022fa1  mov     qword ptr [rsp+30h+var_10], rax; int
0x180022fa6  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x180022fad  lea     rcx, aNgccrypto; "NgcCrypto"
0x180022fb4  call    cs:__imp_GetPersistedRegistryLocationW
0x180022fba  test    eax, eax
0x180022fbc  jz      short loc_180022FED
0x180022fbe  mov     rcx, [rbp+18h]; this
0x180022fc2  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180022fc9  mov     r9d, eax; char *
0x180022fcc  mov     edx, 0C0h; void *
0x180022fd1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180022fd6  mov     edi, eax
0x180022fd8  test    rbx, rbx
0x180022fdb  jz      short loc_180022FE6
0x180022fdd  mov     rcx, rbx; hMem
0x180022fe0  call    cs:__imp_LocalFree
0x180022fe6  mov     eax, edi
0x180022fe8  jmp     loc_180023076
0x180022fed  test    rdi, rdi
0x180022ff0  jz      short loc_18002305E
0x180022ff2  xor     edx, edx
0x180022ff4  mov     [rbp+hMem], 0
0x180022ffc  lea     rcx, [rbp+hMem]
0x180023000  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180023005  lea     r9, [rbp+hMem]; unsigned __int16 *
0x180023009  mov     r8, rdi; unsigned __int16 *
0x18002300c  lea     rdx, asc_18002A2B8; "\\"
0x180023013  mov     rcx, rbx; this
0x180023016  call    ?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)
0x18002301b  mov     edi, eax
0x18002301d  test    eax, eax
0x18002301f  jns     short loc_180023044
0x180023021  mov     rcx, [rbp+18h]; this
0x180023025  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002302c  mov     r9d, eax; char *
0x18002302f  mov     edx, 0C9h; void *
0x180023034  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023039  lea     rcx, [rbp+hMem]
0x18002303d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023042  jmp     short loc_180022FD8
0x180023044  mov     rax, [rbp+hMem]
0x180023048  lea     rcx, [rbp+hMem]
0x18002304c  mov     [rsi], rax
0x18002304f  mov     [rbp+hMem], 0
0x180023057  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002305c  jmp     short loc_180023066
0x18002305e  mov     rax, rbx
0x180023061  xor     ebx, ebx
0x180023063  mov     [rsi], rax
0x180023066  test    rbx, rbx
0x180023069  jz      short loc_180023074
0x18002306b  mov     rcx, rbx; hMem
0x18002306e  call    cs:__imp_LocalFree
0x180023074  xor     eax, eax
0x180023076  mov     rbx, [rsp+30h+arg_10]
0x18002307b  add     rsp, 30h
0x18002307f  pop     rdi
0x180023080  pop     rsi
0x180023081  pop     rbp
0x180023082  retn
```
