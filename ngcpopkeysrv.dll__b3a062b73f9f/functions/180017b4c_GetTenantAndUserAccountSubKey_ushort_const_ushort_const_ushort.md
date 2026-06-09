# GetTenantAndUserAccountSubKey(ushort const *,ushort const *,ushort * *)

- ea: `0x180017b4c`
- end: `0x180017cdf`
- name: `?GetTenantAndUserAccountSubKey@@YAJPEBG0PEAPEAG@Z`
- size: `403`
- prototype: `__int64 __fastcall(NgcUtils *this, NgcUtils *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800177f4`

## callees

- `0x18000b0fc`
- `0x18000db5c`
- `0x180010730`
- `0x180014478`
- `0x180015030`
- `0x180017b4c`
- `0x180017ce8`

## string_xrefs

- `0x180017b94`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`
- `0x180017bea`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`
- `0x180017c56`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`

## pseudocode

```c
__int64 __fastcall GetTenantAndUserAccountSubKey(NgcUtils *this, NgcUtils *a2, unsigned __int16 **a3)
{
  NgcUtils *v6; // rdi
  unsigned __int16 **v7; // r8
  int v8; // eax
  unsigned int v9; // ebx
  const unsigned __int16 *v11; // rbx
  unsigned __int16 **v12; // r8
  int v13; // eax
  int v14; // eax
  unsigned __int16 *v15; // rdx
  unsigned __int16 *v16; // rax
  unsigned __int16 v17[4]; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 v18[4]; // [rsp+28h] [rbp-20h] BYREF
  unsigned __int16 v19[12]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  v6 = 0;
  *(_QWORD *)v18 = 0;
  if ( this )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v18,
      0);
    v8 = NgcUtils::HashStringIntoHexString(this, v18, v7);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
        (const char *)(unsigned int)v8,
        *(int *)v17);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v18);
      return v9;
    }
    v6 = *(NgcUtils **)v18;
  }
  v11 = 0;
  *(_QWORD *)v19 = 0;
  if ( a2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v19,
      0);
    v13 = NgcUtils::HashStringIntoHexString(a2, v19, v12);
    v9 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
        (const char *)(unsigned int)v13,
        *(int *)v17);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v19);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v18);
      return v9;
    }
    v11 = *(const unsigned __int16 **)v19;
  }
  *(_QWORD *)v17 = 0;
  if ( !this )
  {
    if ( !a2 )
      goto LABEL_18;
    v15 = v19;
LABEL_17:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
      v17,
      v15);
    goto LABEL_18;
  }
  if ( !a2 )
  {
    v15 = v18;
    goto LABEL_17;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v17,
    0);
  v14 = NgcUtils::CombineSeparateStrings(v6, L"_", v11, v17, *(unsigned __int16 ***)v17);
  v9 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
      (const char *)(unsigned int)v14,
      *(int *)v17);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v17);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v19);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v18);
    return v9;
  }
LABEL_18:
  v16 = *(unsigned __int16 **)v17;
  *(_QWORD *)v17 = 0;
  *a3 = v16;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v17);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v19);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v18);
  return 0;
}

```

## disassembly

```asm
0x180017b4c  push    rbp
0x180017b4e  push    rbx
0x180017b4f  push    rsi
0x180017b50  push    rdi
0x180017b51  push    r14
0x180017b53  push    r15
0x180017b55  mov     rbp, rsp
0x180017b58  sub     rsp, 48h
0x180017b5c  mov     r15, r8
0x180017b5f  mov     rsi, rdx
0x180017b62  mov     r14, rcx
0x180017b65  xor     edi, edi
0x180017b67  mov     qword ptr [rbp+var_20], rdi
0x180017b6b  test    rcx, rcx
0x180017b6e  jz      short loc_180017BBB
0x180017b70  xor     edx, edx
0x180017b72  lea     rcx, [rbp+var_20]
0x180017b76  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180017b7b  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x180017b7f  mov     rcx, r14; this
0x180017b82  call    ?HashStringIntoHexString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::HashStringIntoHexString(ushort const *,ushort * *)
0x180017b87  mov     ebx, eax
0x180017b89  test    eax, eax
0x180017b8b  jns     short loc_180017BB7
0x180017b8d  mov     rcx, [rbp+30h]; this
0x180017b91  mov     r9d, eax; char *
0x180017b94  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180017b9b  mov     edx, 89h; void *
0x180017ba0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ba5  nop
0x180017ba6  lea     rcx, [rbp+var_20]
0x180017baa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017baf  nop
0x180017bb0  mov     eax, ebx
0x180017bb2  jmp     loc_180017CD2
0x180017bb7  mov     rdi, qword ptr [rbp+var_20]
0x180017bbb  xor     ebx, ebx
0x180017bbd  mov     qword ptr [rbp+var_18], rbx
0x180017bc1  test    rsi, rsi
0x180017bc4  jz      short loc_180017C16
0x180017bc6  xor     edx, edx
0x180017bc8  lea     rcx, [rbp+var_18]
0x180017bcc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180017bd1  lea     rdx, [rbp+var_18]; unsigned __int16 *
0x180017bd5  mov     rcx, rsi; this
0x180017bd8  call    ?HashStringIntoHexString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::HashStringIntoHexString(ushort const *,ushort * *)
0x180017bdd  mov     ebx, eax
0x180017bdf  test    eax, eax
0x180017be1  jns     short loc_180017C12
0x180017be3  mov     rcx, [rbp+30h]; this
0x180017be7  mov     r9d, eax; char *
0x180017bea  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180017bf1  mov     edx, 91h; void *
0x180017bf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017bfb  nop
0x180017bfc  lea     rcx, [rbp+var_18]
0x180017c00  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017c05  nop
0x180017c06  lea     rcx, [rbp+var_20]
0x180017c0a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017c0f  nop
0x180017c10  jmp     short loc_180017BB0
0x180017c12  mov     rbx, qword ptr [rbp+var_18]
0x180017c16  mov     qword ptr [rbp+var_28], 0
0x180017c1e  test    r14, r14
0x180017c21  jz      short loc_180017C91
0x180017c23  lea     rcx, [rbp+var_28]
0x180017c27  test    rsi, rsi
0x180017c2a  jz      short loc_180017C8B
0x180017c2c  xor     edx, edx
0x180017c2e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180017c33  lea     r9, [rbp+var_28]; unsigned __int16 *
0x180017c37  mov     r8, rbx; unsigned __int16 *
0x180017c3a  lea     rdx, asc_18002ADA0; "_"
0x180017c41  mov     rcx, rdi; this
0x180017c44  call    ?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)
0x180017c49  mov     ebx, eax
0x180017c4b  test    eax, eax
0x180017c4d  jns     short loc_180017CA3
0x180017c4f  mov     rcx, [rbp+30h]; this
0x180017c53  mov     r9d, eax; char *
0x180017c56  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180017c5d  mov     edx, 9Ch; void *
0x180017c62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c67  nop
0x180017c68  lea     rcx, [rbp+var_28]
0x180017c6c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017c71  nop
0x180017c72  lea     rcx, [rbp+var_18]
0x180017c76  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017c7b  nop
0x180017c7c  lea     rcx, [rbp+var_20]
0x180017c80  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017c85  nop
0x180017c86  jmp     loc_180017BB0
0x180017c8b  lea     rdx, [rbp+var_20]
0x180017c8f  jmp     short loc_180017C9E
0x180017c91  test    rsi, rsi
0x180017c94  jz      short loc_180017CA3
0x180017c96  lea     rdx, [rbp+var_18]
0x180017c9a  lea     rcx, [rbp+var_28]
0x180017c9e  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180017ca3  mov     rax, qword ptr [rbp+var_28]
0x180017ca7  mov     qword ptr [rbp+var_28], 0
0x180017caf  mov     [r15], rax
0x180017cb2  lea     rcx, [rbp+var_28]
0x180017cb6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017cbb  nop
0x180017cbc  lea     rcx, [rbp+var_18]
0x180017cc0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017cc5  nop
0x180017cc6  lea     rcx, [rbp+var_20]
0x180017cca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017ccf  nop
0x180017cd0  xor     eax, eax
0x180017cd2  add     rsp, 48h
0x180017cd6  pop     r15
0x180017cd8  pop     r14
0x180017cda  pop     rdi
0x180017cdb  pop     rsi
0x180017cdc  pop     rbx
0x180017cdd  pop     rbp
0x180017cde  retn
```
