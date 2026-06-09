# GetSymmetricPopKeyTransportKeyInfo(NgcKeyTransportKey *,_NGC_IDP_ACCOUNT_INFO *,ushort const *,ulong,bool,uchar * *,ulong *,ushort * *)

- ea: `0x1800122c8`
- end: `0x180012428`
- name: `?GetSymmetricPopKeyTransportKeyInfo@@YAJPEAVNgcKeyTransportKey@@PEAU_NGC_IDP_ACCOUNT_INFO@@PEBGK_NPEAPEAEPEAKPEAPEAG@Z`
- size: `352`
- prototype: `__int64 __fastcall(NgcUtils **this, struct _NGC_IDP_ACCOUNT_INFO *, const unsigned __int16 *, unsigned int, bool, unsigned __int8 **, unsigned int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012014`
- `0x180012430`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18000db5c`
- `0x18001070c`
- `0x180010730`
- `0x1800122c8`
- `0x180012858`
- `0x180015288`
- `0x1800192ec`

## string_xrefs

- `0x180012304`: `onecore\ds\security\ngc\ngcpopkey\lib\keytransportkey.cpp`
- `0x18001236b`: `onecore\ds\security\ngc\ngcpopkey\lib\keytransportkey.cpp`
- `0x1800123b5`: `onecore\ds\security\ngc\ngcpopkey\lib\keytransportkey.cpp`

## pseudocode

```c
__int64 __fastcall GetSymmetricPopKeyTransportKeyInfo(
        NgcUtils **this,
        struct _NGC_IDP_ACCOUNT_INFO *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        bool a5,
        unsigned __int8 **a6,
        unsigned int *a7,
        unsigned __int16 **a8)
{
  unsigned __int16 **v9; // rdi
  int v10; // eax
  unsigned int KeyBlobForServer; // ebx
  unsigned int v12; // ebx
  unsigned __int16 **v13; // rcx
  unsigned __int16 **v14; // r8
  int v15; // eax
  unsigned int v16; // r15d
  unsigned __int8 *v17; // rax
  int v19; // [rsp+20h] [rbp-38h]
  unsigned __int8 *v20; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int8 **v21; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int8 *v22; // [rsp+40h] [rbp-18h] BYREF
  char v23; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]

  v9 = a8;
  if ( a8 )
    *a8 = 0;
  v10 = OpenSymmetricPopKeyTransportKey((struct NgcKeyTransportKey *)this, a2, a3, a4, a5);
  KeyBlobForServer = v10;
  if ( v10 >= 0 )
  {
    v12 = 0;
    LODWORD(a8) = 0;
    v20 = 0;
    if ( a6 && a7 )
    {
      v21 = &v20;
      v22 = 0;
      v23 = 1;
      KeyBlobForServer = NgcKeyTransportKey::GetKeyBlobForServer((NgcKeyTransportKey *)this, &v22, (unsigned int *)&a8);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v21);
      if ( (KeyBlobForServer & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA8,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\keytransportkey.cpp",
          (const char *)KeyBlobForServer,
          v19);
LABEL_20:
        wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
          &v20,
          0);
        return KeyBlobForServer;
      }
      v12 = (unsigned int)a8;
    }
    v13 = 0;
    a8 = 0;
    if ( v9 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &a8,
        0);
      v15 = NgcUtils::DuplicateString(this[4], (const unsigned __int16 *)&a8, v14);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAF,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\keytransportkey.cpp",
          (const char *)(unsigned int)v15,
          v19);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&a8);
        KeyBlobForServer = v16;
        goto LABEL_20;
      }
      v13 = a8;
    }
    if ( a6 && a7 )
    {
      v17 = v20;
      v20 = 0;
      *a6 = v17;
      *a7 = v12;
    }
    if ( v9 )
    {
      a8 = 0;
      *v9 = (unsigned __int16 *)v13;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&a8);
    KeyBlobForServer = 0;
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9F,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\keytransportkey.cpp",
    (const char *)(unsigned int)v10,
    v19);
  return KeyBlobForServer;
}

```

## disassembly

```asm
0x1800122c8  push    rbp
0x1800122ca  push    rbx
0x1800122cb  push    rsi
0x1800122cc  push    rdi
0x1800122cd  push    r14
0x1800122cf  push    r15
0x1800122d1  mov     rbp, rsp
0x1800122d4  sub     rsp, 58h
0x1800122d8  mov     r15, rcx
0x1800122db  mov     rdi, [rbp+arg_38]
0x1800122df  test    rdi, rdi
0x1800122e2  jz      short loc_1800122EB
0x1800122e4  mov     qword ptr [rdi], 0
0x1800122eb  mov     al, [rbp+arg_20]
0x1800122ee  mov     [rsp+58h+var_38], al; int
0x1800122f2  call    ?OpenSymmetricPopKeyTransportKey@@YAJPEAVNgcKeyTransportKey@@PEAU_NGC_IDP_ACCOUNT_INFO@@PEBGK_N@Z; OpenSymmetricPopKeyTransportKey(NgcKeyTransportKey *,_NGC_IDP_ACCOUNT_INFO *,ushort const *,ulong,bool)
0x1800122f7  mov     ebx, eax
0x1800122f9  test    eax, eax
0x1800122fb  jns     short loc_18001231A
0x1800122fd  mov     rcx, [rbp+30h]; this
0x180012301  mov     r9d, eax; char *
0x180012304  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001230b  mov     edx, 9Fh; void *
0x180012310  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012315  jmp     loc_180012419
0x18001231a  xor     ebx, ebx
0x18001231c  mov     dword ptr [rbp+arg_38], ebx
0x18001231f  mov     [rbp+var_28], rbx
0x180012323  mov     rsi, [rbp+arg_30]
0x180012327  mov     r14, [rbp+arg_28]
0x18001232b  test    r14, r14
0x18001232e  jz      short loc_180012384
0x180012330  test    rsi, rsi
0x180012333  jz      short loc_180012384
0x180012335  lea     rax, [rbp+var_28]
0x180012339  mov     [rbp+var_20], rax
0x18001233d  mov     [rbp+var_18], rbx
0x180012341  mov     [rbp+var_10], 1
0x180012345  lea     r8, [rbp+arg_38]; unsigned int *
0x180012349  lea     rdx, [rbp+var_18]; unsigned __int8 **
0x18001234d  mov     rcx, r15; this
0x180012350  call    ?GetKeyBlobForServer@NgcKeyTransportKey@@QEAAJPEAPEAEPEAK@Z; NgcKeyTransportKey::GetKeyBlobForServer(uchar * *,ulong *)
0x180012355  mov     ebx, eax
0x180012357  lea     rcx, [rbp+var_20]
0x18001235b  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180012360  test    ebx, ebx
0x180012362  jns     short loc_180012381
0x180012364  mov     rcx, [rbp+30h]; this
0x180012368  mov     r9d, ebx; char *
0x18001236b  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180012372  mov     edx, 0A8h; void *
0x180012377  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001237c  jmp     loc_18001240E
0x180012381  mov     ebx, dword ptr [rbp+arg_38]
0x180012384  xor     ecx, ecx
0x180012386  mov     [rbp+arg_38], rcx
0x18001238a  test    rdi, rdi
0x18001238d  jz      short loc_1800123D8
0x18001238f  xor     edx, edx
0x180012391  lea     rcx, [rbp+arg_38]
0x180012395  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001239a  lea     rdx, [rbp+arg_38]; unsigned __int16 *
0x18001239e  mov     rcx, [r15+20h]; this
0x1800123a2  call    ?DuplicateString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::DuplicateString(ushort const *,ushort * *)
0x1800123a7  mov     r15d, eax
0x1800123aa  test    eax, eax
0x1800123ac  jns     short loc_1800123D4
0x1800123ae  mov     rcx, [rbp+30h]; this
0x1800123b2  mov     r9d, eax; char *
0x1800123b5  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800123bc  mov     edx, 0AFh; void *
0x1800123c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800123c6  lea     rcx, [rbp+arg_38]
0x1800123ca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800123cf  mov     ebx, r15d
0x1800123d2  jmp     short loc_18001240E
0x1800123d4  mov     rcx, [rbp+arg_38]
0x1800123d8  test    r14, r14
0x1800123db  jz      short loc_1800123F3
0x1800123dd  test    rsi, rsi
0x1800123e0  jz      short loc_1800123F3
0x1800123e2  mov     rax, [rbp+var_28]
0x1800123e6  mov     [rbp+var_28], 0
0x1800123ee  mov     [r14], rax
0x1800123f1  mov     [rsi], ebx
0x1800123f3  test    rdi, rdi
0x1800123f6  jz      short loc_180012403
0x1800123f8  mov     [rbp+arg_38], 0
0x180012400  mov     [rdi], rcx
0x180012403  lea     rcx, [rbp+arg_38]
0x180012407  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001240c  xor     ebx, ebx
0x18001240e  xor     edx, edx
0x180012410  lea     rcx, [rbp+var_28]
0x180012414  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180012419  mov     eax, ebx
0x18001241b  add     rsp, 58h
0x18001241f  pop     r15
0x180012421  pop     r14
0x180012423  pop     rdi
0x180012424  pop     rsi
0x180012425  pop     rbx
0x180012426  pop     rbp
0x180012427  retn
```
