# CMDMPushConfiguration::GetFromRegistry(ushort const *,tagVARIANT *)

- ea: `0x18002c920`
- end: `0x18002cbd5`
- name: `?GetFromRegistry@CMDMPushConfiguration@@AEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `693`
- prototype: `__int64 __fastcall(CMDMPushConfiguration *this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c804`

## callees

- `0x1800039f0`
- `0x180003a14`
- `0x1800043a8`
- `0x1800060b4`
- `0x18000bab4`
- `0x18000c63c`
- `0x18002c920`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ca20`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002caf1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ca20`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002caf1`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002c99c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002c99c`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cb75`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cb75`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::GetFromRegistry(
        CMDMPushConfiguration *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v10; // r9
  LSTATUS ValueW; // eax
  unsigned int v12; // edi
  DWORD v14; // ebx
  _DWORD *v15; // rax
  _DWORD *pvData; // rdi
  LSTATUS v17; // eax
  const struct std::nothrow_t *v18; // rdx
  signed int v19; // esi
  __int64 v20; // rdx
  BSTR v21; // rax
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v26; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD *v27; // [rsp+48h] [rbp-B8h]
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a2 )
  {
    v6 = 862;
LABEL_3:
    v7 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
      (const char *)v7,
      pdwType);
    return v7;
  }
  if ( !a3 )
  {
    v6 = 863;
    goto LABEL_3;
  }
  memset_0(SubKey, 0, 0x208u);
  v8 = *((_QWORD *)this + 1);
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v10 = L"OSData\\";
  if ( !IsStateSeparationEnabled )
    v10 = &word_1800401D0;
  v7 = StringCchPrintfW(SubKey, 0x104u, L"%sSoftware\\Microsoft\\Enrollments\\%s\\Push", v10, v8);
  if ( (v7 & 0x80000000) != 0 )
  {
    v6 = 871;
    goto LABEL_4;
  }
  v26 = 0;
  pcbData = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, a2, 0x5Au, &v26, 0, &pcbData);
  v12 = ValueW;
  if ( ValueW > 0 )
    v12 = (unsigned __int16)ValueW | 0x80070000;
  if ( (v12 & 0x80000000) == 0 )
  {
    v14 = pcbData;
    v15 = operator new[](pcbData, (const struct std::nothrow_t *)&std::nothrow);
    pvData = v15;
    if ( v15 )
      memset_0(v15, 0, v14);
    else
      pvData = 0;
    v27 = pvData;
    if ( !pvData )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x376,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
        (const char *)0x8007000ELL,
        pdwTypea);
      return v7;
    }
    v17 = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, a2, 0x5Au, &v26, pvData, &pcbData);
    v19 = v17;
    if ( v17 > 0 )
      v19 = (unsigned __int16)v17 | 0x80070000;
    if ( v19 < 0 )
    {
      v7 = -2147024894;
      if ( v19 != -2147024894 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37F,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
          (const char *)(unsigned int)v19,
          pdwTypeb);
        v7 = v19;
      }
      goto LABEL_37;
    }
    switch ( v26 )
    {
      case 1u:
        v21 = SysAllocString((const OLECHAR *)pvData);
        a3->llVal = (LONGLONG)v21;
        if ( !v21 )
        {
          v7 = -2147024882;
          v20 = 900;
          goto LABEL_34;
        }
        a3->vt = 8;
        break;
      case 4u:
        a3->vt = 19;
        a3->lVal = *pvData;
        break;
      case 0xBu:
        a3->vt = 21;
        a3->llVal = *(_QWORD *)pvData;
        break;
      default:
        v7 = -2147418113;
        v20 = 916;
LABEL_34:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
          (const char *)v7,
          pdwTypeb);
LABEL_37:
        operator delete(pvData, v18);
        return v7;
    }
    v7 = 0;
    goto LABEL_37;
  }
  v7 = -2147024894;
  if ( v12 != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x373,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
      (const char *)v12,
      pdwTypea);
    return v12;
  }
  return v7;
}

```

## disassembly

```asm
0x18002c920  push    rbp
0x18002c922  push    rbx
0x18002c923  push    rsi
0x18002c924  push    rdi
0x18002c925  push    r14
0x18002c927  lea     rbp, [rsp-170h]
0x18002c92f  sub     rsp, 270h
0x18002c936  mov     rax, cs:__security_cookie
0x18002c93d  xor     rax, rsp
0x18002c940  mov     [rbp+190h+var_30], rax
0x18002c947  mov     r14, r8
0x18002c94a  mov     rsi, rdx
0x18002c94d  mov     rbx, rcx
0x18002c950  test    rdx, rdx
0x18002c953  jnz     short loc_18002C97A
0x18002c955  mov     edx, 35Eh; void *
0x18002c95a  mov     ebx, 80070057h
0x18002c95f  mov     rcx, [rbp+198h]; this
0x18002c966  mov     r9d, ebx; char *
0x18002c969  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x18002c970  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c975  jmp     loc_18002CBB6
0x18002c97a  test    r14, r14
0x18002c97d  jnz     short loc_18002C986
0x18002c97f  mov     edx, 35Fh
0x18002c984  jmp     short loc_18002C95A
0x18002c986  xor     edx, edx; Val
0x18002c988  mov     r8d, 208h; Size
0x18002c98e  lea     rcx, [rsp+290h+SubKey]; void *
0x18002c993  call    memset_0
0x18002c998  mov     rbx, [rbx+8]
0x18002c99c  call    cs:__imp_RtlIsStateSeparationEnabled
0x18002c9a2  lea     rcx, word_1800401D0
0x18002c9a9  lea     r9, aOsdata; "OSData\\"
0x18002c9b0  test    al, al
0x18002c9b2  cmovz   r9, rcx
0x18002c9b6  mov     [rsp+290h+pdwType], rbx
0x18002c9bb  lea     r8, aSsoftwareMicro; "%sSoftware\\Microsoft\\Enrollments\\%s"...
0x18002c9c2  mov     edx, 104h; unsigned __int64
0x18002c9c7  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x18002c9cc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c9d1  mov     ebx, eax
0x18002c9d3  test    eax, eax
0x18002c9d5  jns     short loc_18002C9DE
0x18002c9d7  mov     edx, 367h
0x18002c9dc  jmp     short loc_18002C95F
0x18002c9de  mov     [rsp+290h+var_24C], 0
0x18002c9e6  mov     [rsp+290h+var_250], 0
0x18002c9ee  lea     rax, [rsp+290h+var_250]
0x18002c9f3  mov     [rsp+290h+pcbData], rax; pcbData
0x18002c9f8  mov     [rsp+290h+pvData], 0; pvData
0x18002ca01  lea     rax, [rsp+290h+var_24C]
0x18002ca06  mov     [rsp+290h+pdwType], rax; int
0x18002ca0b  mov     r9d, 5Ah ; 'Z'; dwFlags
0x18002ca11  mov     r8, rsi; lpValue
0x18002ca14  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18002ca19  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002ca20  call    cs:__imp_RegGetValueW
0x18002ca26  mov     edi, eax
0x18002ca28  test    eax, eax
0x18002ca2a  jle     short loc_18002CA35
0x18002ca2c  movzx   edi, ax
0x18002ca2f  or      edi, 80070000h
0x18002ca35  test    edi, edi
0x18002ca37  jns     short loc_18002CA68
0x18002ca39  mov     ebx, 80070002h
0x18002ca3e  cmp     edi, ebx
0x18002ca40  jz      loc_18002CBB6
0x18002ca46  mov     rcx, [rbp+198h]; this
0x18002ca4d  mov     r9d, edi; char *
0x18002ca50  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x18002ca57  mov     edx, 373h; void *
0x18002ca5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ca61  mov     eax, edi
0x18002ca63  jmp     loc_18002CBB8
0x18002ca68  mov     ebx, [rsp+290h+var_250]
0x18002ca6c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ca73  mov     ecx, ebx; unsigned __int64
0x18002ca75  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002ca7a  mov     rdi, rax
0x18002ca7d  test    rax, rax
0x18002ca80  jz      short loc_18002CA91
0x18002ca82  mov     r8d, ebx; Size
0x18002ca85  xor     edx, edx; Val
0x18002ca87  mov     rcx, rax; void *
0x18002ca8a  call    memset_0
0x18002ca8f  jmp     short loc_18002CA93
0x18002ca91  xor     edi, edi
0x18002ca93  mov     [rsp+290h+var_248], rdi
0x18002ca98  test    rdi, rdi
0x18002ca9b  jnz     short loc_18002CAC3
0x18002ca9d  mov     rcx, [rbp+198h]; this
0x18002caa4  mov     ebx, 8007000Eh
0x18002caa9  mov     r9d, ebx; char *
0x18002caac  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x18002cab3  mov     edx, 376h; void *
0x18002cab8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cabd  nop
0x18002cabe  jmp     loc_18002CBB6
0x18002cac3  lea     rax, [rsp+290h+var_250]
0x18002cac8  mov     [rsp+290h+pcbData], rax; pcbData
0x18002cacd  mov     [rsp+290h+pvData], rdi; pvData
0x18002cad2  lea     rax, [rsp+290h+var_24C]
0x18002cad7  mov     [rsp+290h+pdwType], rax; int
0x18002cadc  mov     r9d, 5Ah ; 'Z'; dwFlags
0x18002cae2  mov     r8, rsi; lpValue
0x18002cae5  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18002caea  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002caf1  call    cs:__imp_RegGetValueW
0x18002caf7  mov     esi, eax
0x18002caf9  test    eax, eax
0x18002cafb  jle     short loc_18002CB06
0x18002cafd  movzx   esi, ax
0x18002cb00  or      esi, 80070000h
0x18002cb06  test    esi, esi
0x18002cb08  jns     short loc_18002CB36
0x18002cb0a  mov     ebx, 80070002h
0x18002cb0f  cmp     esi, ebx
0x18002cb11  jz      loc_18002CBAE
0x18002cb17  mov     rcx, [rbp+198h]; this
0x18002cb1e  mov     r9d, esi; char *
0x18002cb21  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x18002cb28  mov     edx, 37Fh; void *
0x18002cb2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cb32  mov     ebx, esi
0x18002cb34  jmp     short loc_18002CBAE
0x18002cb36  mov     eax, [rsp+290h+var_24C]
0x18002cb3a  sub     eax, 1
0x18002cb3d  jz      short loc_18002CB72
0x18002cb3f  sub     eax, 3
0x18002cb42  jz      short loc_18002CB64
0x18002cb44  cmp     eax, 7
0x18002cb47  jz      short loc_18002CB55
0x18002cb49  mov     ebx, 8000FFFFh
0x18002cb4e  mov     edx, 394h
0x18002cb53  jmp     short loc_18002CB8E
0x18002cb55  mov     word ptr [r14], 15h
0x18002cb5b  mov     rax, [rdi]
0x18002cb5e  mov     [r14+8], rax
0x18002cb62  jmp     short loc_18002CBAC
0x18002cb64  mov     word ptr [r14], 13h
0x18002cb6a  mov     eax, [rdi]
0x18002cb6c  mov     [r14+8], eax
0x18002cb70  jmp     short loc_18002CBAC
0x18002cb72  mov     rcx, rdi; psz
0x18002cb75  call    cs:__imp_SysAllocString
0x18002cb7b  mov     [r14+8], rax
0x18002cb7f  test    rax, rax
0x18002cb82  jnz     short loc_18002CBA6
0x18002cb84  mov     ebx, 8007000Eh
0x18002cb89  mov     edx, 384h; void *
0x18002cb8e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x18002cb95  mov     r9d, ebx; char *
0x18002cb98  mov     rcx, [rbp+198h]; this
0x18002cb9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cba4  jmp     short loc_18002CBAE
0x18002cba6  mov     word ptr [r14], 8
0x18002cbac  xor     ebx, ebx
0x18002cbae  mov     rcx, rdi; void *
0x18002cbb1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002cbb6  mov     eax, ebx
0x18002cbb8  mov     rcx, [rbp+190h+var_30]
0x18002cbbf  xor     rcx, rsp; StackCookie
0x18002cbc2  call    __security_check_cookie
0x18002cbc7  add     rsp, 270h
0x18002cbce  pop     r14
0x18002cbd0  pop     rdi
0x18002cbd1  pop     rsi
0x18002cbd2  pop     rbx
0x18002cbd3  pop     rbp
0x18002cbd4  retn
```
