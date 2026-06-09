# GenerateAndSetPin(unsigned __int64,uchar * *,ulong *)

- ea: `0x18001ba2c`
- end: `0x18001bbd4`
- name: `?GenerateAndSetPin@@YAJ_KPEAPEAEPEAK@Z`
- size: `424`
- prototype: `__int64 __fastcall(NgcUtils *this, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b0b4`

## callees

- `0x180004de0`
- `0x18000b0fc`
- `0x18000dad8`
- `0x18000db5c`
- `0x18001070c`
- `0x180010730`
- `0x180013f54`
- `0x180014828`
- `0x180014ab0`
- `0x180015194`
- `0x18001ba2c`

## string_xrefs

- `0x18001ba75`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001baba`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001bb2c`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001bb6b`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 __fastcall GenerateAndSetPin(NgcUtils *this, unsigned __int8 **a2, unsigned int *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  const unsigned __int8 *v8; // rdx
  int v9; // eax
  __int64 v10; // r8
  NgcUtils *v11; // rbx
  __int64 v12; // rdx
  int v13; // edi
  const unsigned __int16 *v14; // r9
  int v15; // eax
  unsigned __int8 **v17; // [rsp+20h] [rbp-49h]
  int v18; // [rsp+20h] [rbp-49h]
  int v19; // [rsp+20h] [rbp-49h]
  unsigned __int8 *v20; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int8 *v21; // [rsp+38h] [rbp-31h] BYREF
  NgcUtils *v22; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int8 **v23; // [rsp+48h] [rbp-21h] BYREF
  unsigned int v24[2]; // [rsp+50h] [rbp-19h] BYREF
  char v25; // [rsp+58h] [rbp-11h]
  UCHAR pbBuffer[32]; // [rsp+60h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v6 = NgcUtils::GenRandom(pbBuffer, 0x20u, (unsigned int)a3);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v22 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v22,
      0);
    v9 = NgcUtils::ConvertBinaryToString(pbBuffer, v8, 0x40000001u, (unsigned int)&v22, (unsigned __int16 **)v17);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v11 = v22;
      v23 = &v20;
      v12 = -1;
      LODWORD(v21) = 0;
      v20 = 0;
      *(_QWORD *)v24 = 0;
      v25 = 1;
      do
        ++v12;
      while ( *((_WORD *)v22 + v12) );
      v13 = NgcUtils::ProtectData(
              (BYTE *)v22,
              (const unsigned __int8 *)(unsigned int)(2 * v12 + 2),
              v10,
              (BYTE **)v24,
              &v21);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v23);
      if ( v13 >= 0 )
      {
        v15 = NgcUtils::SetNCryptStringProperty(
                this,
                (unsigned __int64)L"SmartCardPin",
                (const unsigned __int16 *)v11,
                v14);
        v7 = v15;
        if ( v15 >= 0 )
        {
          *a2 = v20;
          *a3 = (unsigned int)v21;
          v20 = 0;
          wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
            &v20,
            0);
          v7 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x515,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
            (const char *)(unsigned int)v15,
            v19);
          wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
            &v20,
            0);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x510,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
          (const char *)(unsigned int)v13,
          v19);
        wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
          &v20,
          0);
        v7 = v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x507,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v9,
        v18);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x500,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v6,
      (int)v17);
  }
  return v7;
}

```

## disassembly

```asm
0x18001ba2c  push    rbp
0x18001ba2e  push    rbx
0x18001ba2f  push    rsi
0x18001ba30  push    rdi
0x18001ba31  push    r12
0x18001ba33  push    r14
0x18001ba35  push    r15
0x18001ba37  lea     rbp, [rsp-27h]
0x18001ba3c  sub     rsp, 90h
0x18001ba43  mov     rax, cs:__security_cookie
0x18001ba4a  xor     rax, rsp
0x18001ba4d  mov     [rbp+57h+var_40], rax
0x18001ba51  mov     rsi, rdx
0x18001ba54  mov     r15, rcx
0x18001ba57  mov     edx, 20h ; ' '; cbBuffer
0x18001ba5c  lea     rcx, [rbp+57h+pbBuffer]; pbBuffer
0x18001ba60  mov     r14, r8
0x18001ba63  call    ?GenRandom@NgcUtils@@YAJPEAEK@Z; NgcUtils::GenRandom(uchar *,ulong)
0x18001ba68  xor     r12d, r12d
0x18001ba6b  mov     ebx, eax
0x18001ba6d  test    eax, eax
0x18001ba6f  jns     short loc_18001BA8E
0x18001ba71  mov     rcx, [rbp+5Fh]; this
0x18001ba75  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001ba7c  mov     r9d, eax; char *
0x18001ba7f  mov     edx, 500h; void *
0x18001ba84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ba89  jmp     loc_18001BBB4
0x18001ba8e  xor     edx, edx
0x18001ba90  mov     [rbp+57h+var_80], r12
0x18001ba94  lea     rcx, [rbp+57h+var_80]
0x18001ba98  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001ba9d  lea     r9, [rbp+57h+var_80]; unsigned int
0x18001baa1  mov     r8d, 40000001h; unsigned int
0x18001baa7  lea     rcx, [rbp+57h+pbBuffer]; pbBinary
0x18001baab  call    ?ConvertBinaryToString@NgcUtils@@YAJPEBEKKPEAPEAG@Z; NgcUtils::ConvertBinaryToString(uchar const *,ulong,ulong,ushort * *)
0x18001bab0  mov     ebx, eax
0x18001bab2  test    eax, eax
0x18001bab4  jns     short loc_18001BAD3
0x18001bab6  mov     rcx, [rbp+5Fh]; this
0x18001baba  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001bac1  mov     r9d, eax; char *
0x18001bac4  mov     edx, 507h; void *
0x18001bac9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bace  jmp     loc_18001BBAB
0x18001bad3  mov     rbx, [rbp+57h+var_80]
0x18001bad7  lea     rax, [rbp+57h+var_90]
0x18001badb  mov     [rbp+57h+var_78], rax
0x18001badf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001bae3  mov     dword ptr [rbp+57h+var_88], r12d
0x18001bae7  mov     [rbp+57h+var_90], r12
0x18001baeb  mov     qword ptr [rbp+57h+var_70], r12
0x18001baef  mov     [rbp+57h+var_68], 1
0x18001baf3  inc     rdx
0x18001baf6  cmp     [rbx+rdx*2], r12w
0x18001bafb  jnz     short loc_18001BAF3
0x18001bafd  lea     rax, [rbp+57h+var_88]
0x18001bb01  mov     rcx, rbx; this
0x18001bb04  lea     edx, ds:2[rdx*2]; unsigned __int8 *
0x18001bb0b  mov     [rsp+0C0h+var_A0], rax; int
0x18001bb10  lea     r9, [rbp+57h+var_70]; unsigned int
0x18001bb14  call    ?ProtectData@NgcUtils@@YAJPEBEKKPEAPEAEPEAK@Z; NgcUtils::ProtectData(uchar const *,ulong,ulong,uchar * *,ulong *)
0x18001bb19  lea     rcx, [rbp+57h+var_78]
0x18001bb1d  mov     edi, eax
0x18001bb1f  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001bb24  test    edi, edi
0x18001bb26  jns     short loc_18001BB4F
0x18001bb28  mov     rcx, [rbp+5Fh]; this
0x18001bb2c  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001bb33  mov     r9d, edi; char *
0x18001bb36  mov     edx, 510h; void *
0x18001bb3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bb40  xor     edx, edx
0x18001bb42  lea     rcx, [rbp+57h+var_90]
0x18001bb46  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001bb4b  mov     ebx, edi
0x18001bb4d  jmp     short loc_18001BBAB
0x18001bb4f  mov     r8, rbx; unsigned __int16 *
0x18001bb52  lea     rdx, aSmartcardpin; "SmartCardPin"
0x18001bb59  mov     rcx, r15; this
0x18001bb5c  call    ?SetNCryptStringProperty@NgcUtils@@YAJ_KPEBG1@Z; NgcUtils::SetNCryptStringProperty(unsigned __int64,ushort const *,ushort const *)
0x18001bb61  mov     ebx, eax
0x18001bb63  test    eax, eax
0x18001bb65  jns     short loc_18001BB8C
0x18001bb67  mov     rcx, [rbp+5Fh]; this
0x18001bb6b  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001bb72  mov     r9d, eax; char *
0x18001bb75  mov     edx, 515h; void *
0x18001bb7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bb7f  xor     edx, edx
0x18001bb81  lea     rcx, [rbp+57h+var_90]
0x18001bb85  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001bb8a  jmp     short loc_18001BBAB
0x18001bb8c  mov     rax, [rbp+57h+var_90]
0x18001bb90  lea     rcx, [rbp+57h+var_90]
0x18001bb94  mov     [rsi], rax
0x18001bb97  xor     edx, edx
0x18001bb99  mov     eax, dword ptr [rbp+57h+var_88]
0x18001bb9c  mov     [r14], eax
0x18001bb9f  mov     [rbp+57h+var_90], r12
0x18001bba3  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001bba8  mov     ebx, r12d
0x18001bbab  lea     rcx, [rbp+57h+var_80]
0x18001bbaf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001bbb4  mov     eax, ebx
0x18001bbb6  mov     rcx, [rbp+57h+var_40]
0x18001bbba  xor     rcx, rsp; StackCookie
0x18001bbbd  call    __security_check_cookie
0x18001bbc2  add     rsp, 90h
0x18001bbc9  pop     r15
0x18001bbcb  pop     r14
0x18001bbcd  pop     r12
0x18001bbcf  pop     rdi
0x18001bbd0  pop     rsi
0x18001bbd1  pop     rbx
0x18001bbd2  pop     rbp
0x18001bbd3  retn
```
