# StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)

- ea: `0x180019aac`
- end: `0x180019e36`
- name: `?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `906`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180018748`
- `0x180019588`
- `0x1800199ac`

## callees

- `0x180019aac`
- `0x18002c8d0`
- `0x180063b74`
- `0x18006fc1c`
- `0x18006fff4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt64` at `0x180019c4c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt64` at `0x180019c4c`

## string_xrefs

- `0x180019b10`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180019e0c`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180019c5d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019ce9`: `MutableLink`
- `0x180019c9b`: `InstalledLocation`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int Field; // r14d
  __int64 v9; // rdx
  int Field_UInt64; // eax
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 *v15; // [rsp+28h] [rbp-20h] BYREF
  char v16; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  if ( a3 && (a3 & 1) == 0 )
    goto LABEL_7;
  v15 = 0;
  v14 = a2 + 8;
  v16 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageFullName", &v15);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v14);
  if ( Field < 0 )
  {
    v9 = 2091;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)Field,
      v14);
    return (unsigned int)Field;
  }
  if ( a3 )
  {
LABEL_7:
    if ( (a3 & 2) == 0 )
      goto LABEL_11;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageFamily", (unsigned int *)(a2 + 16));
  if ( Field < 0 )
  {
    v9 = 2095;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_11:
    if ( (a3 & 4) == 0 )
      goto LABEL_15;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageType", (unsigned int *)(a2 + 24));
  if ( Field < 0 )
  {
    v9 = 2099;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_15:
    if ( (a3 & 8) == 0 )
      goto LABEL_19;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Flags", (unsigned int *)(a2 + 28));
  if ( Field < 0 )
  {
    v9 = 2103;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_19:
    if ( (a3 & 0x10) == 0 )
      goto LABEL_23;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Flags2", (unsigned int *)(a2 + 32));
  if ( Field < 0 )
  {
    v9 = 2107;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_23:
    if ( (a3 & 0x20) == 0 )
      goto LABEL_27;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageOrigin", (unsigned int *)(a2 + 36));
  if ( Field < 0 )
  {
    v9 = 2111;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_27:
    if ( (a3 & 0x40) == 0 )
      goto LABEL_31;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Volume", (unsigned int *)(a2 + 40));
  if ( Field < 0 )
  {
    v9 = 2115;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_31:
    if ( (a3 & 0x80u) == 0LL )
      goto LABEL_35;
  }
  Field_UInt64 = SRCacheContext_GetField_UInt64(*(_QWORD *)a1, L"OSMaxVersionTested", a2 + 48);
  Field = Field_UInt64;
  if ( Field_UInt64 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x230,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt64,
      v14);
    v9 = 2119;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_35:
    if ( (a3 & 0x100) == 0 )
      goto LABEL_39;
  }
  v15 = 0;
  v14 = a2 + 56;
  v16 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"InstalledLocation", &v15);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v14);
  if ( Field < 0 )
  {
    v9 = 2123;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_39:
    if ( (a3 & 0x200) == 0 )
      goto LABEL_43;
  }
  v15 = 0;
  v14 = a2 + 64;
  v16 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"MutableLink", &v15);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v14);
  if ( Field < 0 )
  {
    v9 = 2127;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_43:
    if ( (a3 & 0x400) == 0 )
      goto LABEL_47;
  }
  v15 = 0;
  v14 = a2 + 72;
  v16 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"MutableLocation", &v15);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v14);
  if ( Field < 0 )
  {
    v9 = 2131;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_47:
    if ( (a3 & 0x800) == 0 )
      goto LABEL_51;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"TargetDeviceFamilyName", (unsigned int *)(a2 + 80));
  if ( Field < 0 )
  {
    v9 = 2135;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_51:
    if ( (a3 & 0x1000) == 0 )
      goto LABEL_55;
  }
  v15 = 0;
  v14 = a2 + 88;
  v16 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"DisplayName", &v15);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v14);
  if ( Field < 0 )
  {
    v9 = 2139;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_55:
    if ( (a3 & 0x2000) == 0 )
      goto LABEL_58;
  }
  v12 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"SourceBundle", (unsigned int *)(a2 + 96));
  v13 = v12;
  if ( v12 >= 0 )
  {
LABEL_58:
    *(_QWORD *)a2 = a4;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v12,
      v14);
    return v13;
  }
}

```

## disassembly

```asm
0x180019aac  push    rbp
0x180019aae  push    rbx
0x180019aaf  push    rsi
0x180019ab0  push    rdi
0x180019ab1  push    r14
0x180019ab3  push    r15
0x180019ab5  mov     rbp, rsp
0x180019ab8  sub     rsp, 48h
0x180019abc  mov     r15, r9
0x180019abf  mov     rbx, r8
0x180019ac2  mov     rdi, rdx
0x180019ac5  mov     rsi, rcx
0x180019ac8  test    r8, r8
0x180019acb  jz      short loc_180019AD2
0x180019acd  test    bl, 1
0x180019ad0  jz      short loc_180019B2C
0x180019ad2  lea     rax, [rdx+8]
0x180019ad6  mov     [rbp+var_20], 0
0x180019ade  lea     rdx, aPackagefullnam; "PackageFullName"
0x180019ae5  mov     [rbp+var_28], rax
0x180019ae9  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180019aed  mov     [rbp+var_18], 1
0x180019af1  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180019af6  lea     rcx, [rbp+var_28]
0x180019afa  mov     r14d, eax
0x180019afd  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180019b02  test    r14d, r14d
0x180019b05  jns     short loc_180019B27
0x180019b07  mov     edx, 82Bh; void *
0x180019b0c  mov     rcx, [rbp+30h]; this
0x180019b10  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019b17  mov     r9d, r14d; char *
0x180019b1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019b1f  mov     eax, r14d
0x180019b22  jmp     loc_180019E29
0x180019b27  test    rbx, rbx
0x180019b2a  jz      short loc_180019B31
0x180019b2c  test    bl, 2
0x180019b2f  jz      short loc_180019B57
0x180019b31  lea     r8, [rdi+10h]; unsigned int *
0x180019b35  mov     rcx, rsi; this
0x180019b38  lea     rdx, aPackagefamily; "PackageFamily"
0x180019b3f  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180019b44  mov     r14d, eax
0x180019b47  test    eax, eax
0x180019b49  jns     short loc_180019B52
0x180019b4b  mov     edx, 82Fh
0x180019b50  jmp     short loc_180019B0C
0x180019b52  test    rbx, rbx
0x180019b55  jz      short loc_180019B5C
0x180019b57  test    bl, 4
0x180019b5a  jz      short loc_180019B82
0x180019b5c  lea     r8, [rdi+18h]; unsigned int *
0x180019b60  mov     rcx, rsi; this
0x180019b63  lea     rdx, aPackagetype; "PackageType"
0x180019b6a  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180019b6f  mov     r14d, eax
0x180019b72  test    eax, eax
0x180019b74  jns     short loc_180019B7D
0x180019b76  mov     edx, 833h
0x180019b7b  jmp     short loc_180019B0C
0x180019b7d  test    rbx, rbx
0x180019b80  jz      short loc_180019B87
0x180019b82  test    bl, 8
0x180019b85  jz      short loc_180019BB0
0x180019b87  lea     r8, [rdi+1Ch]; unsigned int *
0x180019b8b  mov     rcx, rsi; this
0x180019b8e  lea     rdx, aFlags; "Flags"
0x180019b95  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180019b9a  mov     r14d, eax
0x180019b9d  test    eax, eax
0x180019b9f  jns     short loc_180019BAB
0x180019ba1  mov     edx, 837h
0x180019ba6  jmp     loc_180019B0C
0x180019bab  test    rbx, rbx
0x180019bae  jz      short loc_180019BB5
0x180019bb0  test    bl, 10h
0x180019bb3  jz      short loc_180019BDE
0x180019bb5  lea     r8, [rdi+20h]; unsigned int *
0x180019bb9  mov     rcx, rsi; this
0x180019bbc  lea     rdx, aFlags2; "Flags2"
0x180019bc3  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180019bc8  mov     r14d, eax
0x180019bcb  test    eax, eax
0x180019bcd  jns     short loc_180019BD9
0x180019bcf  mov     edx, 83Bh
0x180019bd4  jmp     loc_180019B0C
0x180019bd9  test    rbx, rbx
0x180019bdc  jz      short loc_180019BE3
0x180019bde  test    bl, 20h
0x180019be1  jz      short loc_180019C0C
0x180019be3  lea     r8, [rdi+24h]; unsigned int *
0x180019be7  mov     rcx, rsi; this
0x180019bea  lea     rdx, aPackageorigin; "PackageOrigin"
0x180019bf1  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180019bf6  mov     r14d, eax
0x180019bf9  test    eax, eax
0x180019bfb  jns     short loc_180019C07
0x180019bfd  mov     edx, 83Fh
0x180019c02  jmp     loc_180019B0C
0x180019c07  test    rbx, rbx
0x180019c0a  jz      short loc_180019C11
0x180019c0c  test    bl, 40h
0x180019c0f  jz      short loc_180019C3A
0x180019c11  lea     r8, [rdi+28h]; unsigned int *
0x180019c15  mov     rcx, rsi; this
0x180019c18  lea     rdx, aVolume; "Volume"
0x180019c1f  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180019c24  mov     r14d, eax
0x180019c27  test    eax, eax
0x180019c29  jns     short loc_180019C35
0x180019c2b  mov     edx, 843h
0x180019c30  jmp     loc_180019B0C
0x180019c35  test    rbx, rbx
0x180019c38  jz      short loc_180019C3E
0x180019c3a  test    bl, bl
0x180019c3c  jns     short loc_180019C80
0x180019c3e  mov     rcx, [rsi]
0x180019c41  lea     r8, [rdi+30h]
0x180019c45  lea     rdx, aOsmaxversionte; "OSMaxVersionTested"
0x180019c4c  call    cs:__imp_SRCacheContext_GetField_UInt64
0x180019c52  mov     r14d, eax
0x180019c55  test    eax, eax
0x180019c57  jns     short loc_180019C7B
0x180019c59  mov     rcx, [rbp+30h]; this
0x180019c5d  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019c64  mov     r9d, eax; char *
0x180019c67  mov     edx, 230h; void *
0x180019c6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c71  mov     edx, 847h
0x180019c76  jmp     loc_180019B0C
0x180019c7b  test    rbx, rbx
0x180019c7e  jz      short loc_180019C87
0x180019c80  bt      rbx, 8
0x180019c85  jnb     short loc_180019CCE
0x180019c87  lea     rax, [rdi+38h]
0x180019c8b  mov     [rbp+var_20], 0
0x180019c93  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180019c97  mov     [rbp+var_28], rax
0x180019c9b  lea     rdx, aInstalledlocat; "InstalledLocation"
0x180019ca2  mov     [rbp+var_18], 1
0x180019ca6  mov     rcx, rsi; this
0x180019ca9  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180019cae  lea     rcx, [rbp+var_28]
0x180019cb2  mov     r14d, eax
0x180019cb5  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180019cba  test    r14d, r14d
0x180019cbd  jns     short loc_180019CC9
0x180019cbf  mov     edx, 84Bh
0x180019cc4  jmp     loc_180019B0C
0x180019cc9  test    rbx, rbx
0x180019ccc  jz      short loc_180019CD5
0x180019cce  bt      rbx, 9
0x180019cd3  jnb     short loc_180019D1C
0x180019cd5  lea     rax, [rdi+40h]
0x180019cd9  mov     [rbp+var_20], 0
0x180019ce1  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180019ce5  mov     [rbp+var_28], rax
0x180019ce9  lea     rdx, aMutablelink; "MutableLink"
0x180019cf0  mov     [rbp+var_18], 1
0x180019cf4  mov     rcx, rsi; this
0x180019cf7  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180019cfc  lea     rcx, [rbp+var_28]
0x180019d00  mov     r14d, eax
0x180019d03  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180019d08  test    r14d, r14d
0x180019d0b  jns     short loc_180019D17
0x180019d0d  mov     edx, 84Fh
0x180019d12  jmp     loc_180019B0C
0x180019d17  test    rbx, rbx
0x180019d1a  jz      short loc_180019D23
0x180019d1c  bt      rbx, 0Ah
0x180019d21  jnb     short loc_180019D6A
0x180019d23  lea     rax, [rdi+48h]
0x180019d27  mov     [rbp+var_20], 0
0x180019d2f  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180019d33  mov     [rbp+var_28], rax
0x180019d37  lea     rdx, aMutablelocatio; "MutableLocation"
0x180019d3e  mov     [rbp+var_18], 1
0x180019d42  mov     rcx, rsi; this
0x180019d45  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180019d4a  lea     rcx, [rbp+var_28]
0x180019d4e  mov     r14d, eax
0x180019d51  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180019d56  test    r14d, r14d
0x180019d59  jns     short loc_180019D65
0x180019d5b  mov     edx, 853h
0x180019d60  jmp     loc_180019B0C
0x180019d65  test    rbx, rbx
0x180019d68  jz      short loc_180019D71
0x180019d6a  bt      rbx, 0Bh
0x180019d6f  jnb     short loc_180019D9A
0x180019d71  lea     r8, [rdi+50h]; unsigned int *
0x180019d75  mov     rcx, rsi; this
0x180019d78  lea     rdx, aTargetdevicefa; "TargetDeviceFamilyName"
0x180019d7f  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180019d84  mov     r14d, eax
0x180019d87  test    eax, eax
0x180019d89  jns     short loc_180019D95
0x180019d8b  mov     edx, 857h
0x180019d90  jmp     loc_180019B0C
0x180019d95  test    rbx, rbx
0x180019d98  jz      short loc_180019DA1
0x180019d9a  bt      rbx, 0Ch
0x180019d9f  jnb     short loc_180019DE8
0x180019da1  lea     rax, [rdi+58h]
0x180019da5  mov     [rbp+var_20], 0
0x180019dad  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180019db1  mov     [rbp+var_28], rax
0x180019db5  lea     rdx, aDisplayname; "DisplayName"
0x180019dbc  mov     [rbp+var_18], 1
0x180019dc0  mov     rcx, rsi; this
0x180019dc3  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180019dc8  lea     rcx, [rbp+var_28]
0x180019dcc  mov     r14d, eax
0x180019dcf  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180019dd4  test    r14d, r14d
0x180019dd7  jns     short loc_180019DE3
0x180019dd9  mov     edx, 85Bh
0x180019dde  jmp     loc_180019B0C
0x180019de3  test    rbx, rbx
0x180019de6  jz      short loc_180019DEF
0x180019de8  bt      rbx, 0Dh
0x180019ded  jnb     short loc_180019E24
0x180019def  lea     r8, [rdi+60h]; unsigned int *
0x180019df3  mov     rcx, rsi; this
0x180019df6  lea     rdx, aSourcebundle; "SourceBundle"
0x180019dfd  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180019e02  mov     ebx, eax
0x180019e04  test    eax, eax
0x180019e06  jns     short loc_180019E24
0x180019e08  mov     rcx, [rbp+30h]; this
0x180019e0c  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019e13  mov     r9d, eax; char *
0x180019e16  mov     edx, 85Fh; void *
0x180019e1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019e20  mov     eax, ebx
0x180019e22  jmp     short loc_180019E29
0x180019e24  mov     [rdi], r15
0x180019e27  xor     eax, eax
0x180019e29  add     rsp, 48h
0x180019e2d  pop     r15
0x180019e2f  pop     r14
0x180019e31  pop     rdi
0x180019e32  pop     rsi
0x180019e33  pop     rbx
0x180019e34  pop     rbp
0x180019e35  retn
```
