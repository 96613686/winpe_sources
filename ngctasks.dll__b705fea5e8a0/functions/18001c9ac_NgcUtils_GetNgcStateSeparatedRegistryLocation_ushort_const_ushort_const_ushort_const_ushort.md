# NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x18001c9ac`
- end: `0x18001cb61`
- name: `?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z`
- size: `437`
- prototype: `__int64 __fastcall(NgcUtils *this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `9`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800108f8`
- `0x180010b28`
- `0x180010de8`
- `0x180010ef8`
- `0x18001159c`
- `0x180012438`
- `0x180014490`
- `0x180014c24`
- `0x180016850`

## callees

- `0x18000cc34`
- `0x18000cc58`
- `0x180010310`
- `0x180014bcc`
- `0x180017440`
- `0x18001c754`
- `0x18001c9ac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001caac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001caac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb4b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001c9ee`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001ca80`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001c9ee`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001ca80`

## string_xrefs

- `0x18001ca15`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x18001ca4e`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x18001ca91`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x18001caf5`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NgcUtils::GetNgcStateSeparatedRegistryLocation(
        NgcUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int PersistedRegistryLocationW; // eax
  unsigned int v7; // ebx
  HLOCAL v9; // rbx
  unsigned int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  HLOCAL v13; // rax
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
    if ( (v7 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB6,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
        (const char *)v7,
        (int)&v18);
    return v7;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, (unsigned int)v18);
  v9 = hMem;
  if ( !hMem )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)0x8007000ELL,
      (int)&v18);
    return v7;
  }
  v10 = GetPersistedRegistryLocationW(
          L"NgcCrypto",
          L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\Ngc",
          hMem,
          (unsigned int)v18);
  if ( v10 )
  {
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xC0,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
            (const char *)v10,
            (unsigned int)&v18);
    if ( v9 )
      LocalFree(v9);
    return v11;
  }
  if ( a3 )
  {
    hMem = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &hMem,
      0);
    v12 = NgcUtils::CombineSeparateStrings((NgcUtils *)v9, L"\\", a3, (const unsigned __int16 *)&hMem, &v18);
    v11 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
        (const char *)(unsigned int)v12,
        v15);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
      if ( v9 )
        LocalFree(v9);
      return v11;
    }
    v13 = hMem;
    hMem = 0;
    *(_QWORD *)a4 = v13;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  }
  else
  {
    v14 = v9;
    v9 = 0;
    *(_QWORD *)a4 = v14;
  }
  if ( v9 )
    LocalFree(v9);
  return 0;
}

```

## disassembly

```asm
0x18001c9ac  mov     r11, rsp
0x18001c9af  mov     [r11+18h], rbx
0x18001c9b3  mov     [r11+10h], rdx
0x18001c9b7  mov     [r11+8], rcx
0x18001c9bb  push    rbp
0x18001c9bc  push    rsi
0x18001c9bd  push    rdi
0x18001c9be  mov     rbp, rsp
0x18001c9c1  sub     rsp, 30h
0x18001c9c5  mov     rsi, r9
0x18001c9c8  mov     rdi, r8
0x18001c9cb  mov     dword ptr [rbp+arg_8], 0
0x18001c9d2  lea     rax, [rbp+arg_8]
0x18001c9d6  mov     [r11-28h], rax
0x18001c9da  xor     r9d, r9d
0x18001c9dd  xor     r8d, r8d
0x18001c9e0  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x18001c9e7  lea     rcx, aNgccrypto; "NgcCrypto"
0x18001c9ee  call    cs:__imp_GetPersistedRegistryLocationW
0x18001c9f4  mov     ebx, eax
0x18001c9f6  cmp     eax, 0EAh
0x18001c9fb  jz      short loc_18001CA2D
0x18001c9fd  test    eax, eax
0x18001c9ff  jle     short loc_18001CA0A
0x18001ca01  movzx   ebx, ax
0x18001ca04  or      ebx, 80070000h
0x18001ca0a  test    ebx, ebx
0x18001ca0c  jns     short loc_18001CA26
0x18001ca0e  mov     rcx, [rbp+18h]; this
0x18001ca12  mov     r9d, ebx; char *
0x18001ca15  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001ca1c  mov     edx, 0B6h; void *
0x18001ca21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ca26  mov     eax, ebx
0x18001ca28  jmp     loc_18001CB54
0x18001ca2d  mov     edx, dword ptr [rbp+arg_8]
0x18001ca30  lea     rcx, [rbp+hMem]
0x18001ca34  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18001ca39  mov     rbx, [rbp+hMem]
0x18001ca3d  test    rbx, rbx
0x18001ca40  jnz     short loc_18001CA62
0x18001ca42  mov     rcx, [rbp+18h]; this
0x18001ca46  mov     ebx, 8007000Eh
0x18001ca4b  mov     r9d, ebx; char *
0x18001ca4e  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001ca55  mov     edx, 0B9h; void *
0x18001ca5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ca5f  nop
0x18001ca60  jmp     short loc_18001CA26
0x18001ca62  lea     rax, [rbp+arg_8]
0x18001ca66  mov     qword ptr [rsp+30h+var_10], rax; int
0x18001ca6b  mov     r9d, dword ptr [rbp+arg_8]
0x18001ca6f  mov     r8, rbx
0x18001ca72  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x18001ca79  lea     rcx, aNgccrypto; "NgcCrypto"
0x18001ca80  call    cs:__imp_GetPersistedRegistryLocationW
0x18001ca86  test    eax, eax
0x18001ca88  jz      short loc_18001CABA
0x18001ca8a  mov     rcx, [rbp+18h]; this
0x18001ca8e  mov     r9d, eax; char *
0x18001ca91  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001ca98  mov     edx, 0C0h; void *
0x18001ca9d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001caa2  mov     edi, eax
0x18001caa4  test    rbx, rbx
0x18001caa7  jz      short loc_18001CAB3
0x18001caa9  mov     rcx, rbx; hMem
0x18001caac  call    cs:__imp_LocalFree
0x18001cab2  nop
0x18001cab3  mov     eax, edi
0x18001cab5  jmp     loc_18001CB54
0x18001caba  test    rdi, rdi
0x18001cabd  jz      short loc_18001CB3B
0x18001cabf  mov     [rbp+hMem], 0
0x18001cac7  xor     edx, edx
0x18001cac9  lea     rcx, [rbp+hMem]
0x18001cacd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001cad2  lea     r9, [rbp+hMem]; unsigned __int16 *
0x18001cad6  mov     r8, rdi; unsigned __int16 *
0x18001cad9  lea     rdx, asc_180024838; "\\"
0x18001cae0  mov     rcx, rbx; this
0x18001cae3  call    ?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001cae8  mov     edi, eax
0x18001caea  test    eax, eax
0x18001caec  jns     short loc_18001CB21
0x18001caee  mov     rcx, [rbp+18h]; this
0x18001caf2  mov     r9d, eax; char *
0x18001caf5  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001cafc  mov     edx, 0C9h; void *
0x18001cb01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cb06  lea     rcx, [rbp+hMem]
0x18001cb0a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001cb0f  nop
0x18001cb10  test    rbx, rbx
0x18001cb13  jz      short loc_18001CB1F
0x18001cb15  mov     rcx, rbx; hMem
0x18001cb18  call    cs:__imp_LocalFree
0x18001cb1e  nop
0x18001cb1f  jmp     short loc_18001CAB3
0x18001cb21  mov     rax, [rbp+hMem]
0x18001cb25  mov     [rbp+hMem], 0
0x18001cb2d  mov     [rsi], rax
0x18001cb30  lea     rcx, [rbp+hMem]
0x18001cb34  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001cb39  jmp     short loc_18001CB43
0x18001cb3b  mov     rax, rbx
0x18001cb3e  xor     ebx, ebx
0x18001cb40  mov     [rsi], rax
0x18001cb43  test    rbx, rbx
0x18001cb46  jz      short loc_18001CB52
0x18001cb48  mov     rcx, rbx; hMem
0x18001cb4b  call    cs:__imp_LocalFree
0x18001cb51  nop
0x18001cb52  xor     eax, eax
0x18001cb54  mov     rbx, [rsp+30h+arg_10]
0x18001cb59  add     rsp, 30h
0x18001cb5d  pop     rdi
0x18001cb5e  pop     rsi
0x18001cb5f  pop     rbp
0x18001cb60  retn
```
