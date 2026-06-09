# NgcUtils::GenRandomGuid(ushort * *)

- ea: `0x180013f9c`
- end: `0x1800140b5`
- name: `?GenRandomGuid@NgcUtils@@YAJPEAPEAG@Z`
- size: `281`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800187a0`
- `0x18001b0b4`

## callees

- `0x180004de0`
- `0x18000b0fc`
- `0x18000db5c`
- `0x180010730`
- `0x18001368c`
- `0x1800136b0`
- `0x1800137d4`
- `0x180013f54`
- `0x180013f9c`
- `0x180015288`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x180014005`
- `RPCRT4!UuidToStringW` at `0x180014005`

## string_xrefs

- `0x180013fdf`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180014016`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180014058`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
int __fastcall NgcUtils::GenRandomGuid(NgcUtils *this, unsigned __int16 **a2, unsigned int a3)
{
  int v4; // eax
  unsigned int v6; // eax
  int v7; // ebx
  unsigned __int16 **v8; // r8
  int v9; // eax
  __int64 v10; // rax
  unsigned __int16 v11[4]; // [rsp+20h] [rbp-30h] BYREF
  RPC_WSTR StringUuid; // [rsp+28h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  Uuid = 0;
  v4 = NgcUtils::GenRandom((PUCHAR)&Uuid, 0x10u, a3);
  if ( v4 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x69,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
             (const char *)(unsigned int)v4,
             *(int *)v11);
  StringUuid = 0;
  v6 = UuidToStringW(&Uuid, &StringUuid);
  if ( v6 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x6E,
           (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
           (const char *)v6,
           *(unsigned int *)v11);
  }
  else
  {
    *(_QWORD *)v11 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v11,
      0);
    v9 = NgcUtils::DuplicateString((NgcUtils *)StringUuid, v11, v8);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v10 = *(_QWORD *)v11;
      *(_QWORD *)v11 = 0;
      *(_QWORD *)this = v10;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v11);
      v7 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
        (const char *)(unsigned int)v9,
        *(int *)v11);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v11);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void NgcUtils::CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (unsigned short *),&void NgcUtils::CloseRpcString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
  return v7;
}

```

## disassembly

```asm
0x180013f9c  mov     [rsp-8+arg_8], rbx
0x180013fa1  mov     [rsp-8+arg_10], rdi
0x180013fa6  push    rbp
0x180013fa7  mov     rbp, rsp
0x180013faa  sub     rsp, 50h
0x180013fae  mov     rax, cs:__security_cookie
0x180013fb5  xor     rax, rsp
0x180013fb8  mov     [rbp+var_10], rax
0x180013fbc  mov     rdi, rcx
0x180013fbf  xorps   xmm0, xmm0
0x180013fc2  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180013fc6  mov     edx, 10h; cbBuffer
0x180013fcb  lea     rcx, [rbp+Uuid]; pbBuffer
0x180013fcf  call    ?GenRandom@NgcUtils@@YAJPEAEK@Z; NgcUtils::GenRandom(uchar *,ulong)
0x180013fd4  test    eax, eax
0x180013fd6  jns     short loc_180013FF5
0x180013fd8  mov     rcx, [rbp+8]; this
0x180013fdc  mov     r9d, eax; char *
0x180013fdf  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013fe6  mov     edx, 69h ; 'i'; void *
0x180013feb  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180013ff0  jmp     loc_180014099
0x180013ff5  mov     [rbp+StringUuid], 0
0x180013ffd  lea     rdx, [rbp+StringUuid]; StringUuid
0x180014001  lea     rcx, [rbp+Uuid]; Uuid
0x180014005  call    cs:__imp_UuidToStringW
0x18001400b  test    eax, eax
0x18001400d  jz      short loc_18001402B
0x18001400f  mov     rcx, [rbp+8]; this
0x180014013  mov     r9d, eax; char *
0x180014016  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001401d  mov     edx, 6Eh ; 'n'; void *
0x180014022  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180014027  mov     ebx, eax
0x180014029  jmp     short loc_18001408E
0x18001402b  mov     qword ptr [rbp+var_30], 0
0x180014033  xor     edx, edx
0x180014035  lea     rcx, [rbp+var_30]
0x180014039  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001403e  lea     rdx, [rbp+var_30]; unsigned __int16 *
0x180014042  mov     rcx, [rbp+StringUuid]; this
0x180014046  call    ?DuplicateString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::DuplicateString(ushort const *,ushort * *)
0x18001404b  mov     ebx, eax
0x18001404d  test    eax, eax
0x18001404f  jns     short loc_180014074
0x180014051  mov     rcx, [rbp+8]; this
0x180014055  mov     r9d, eax; char *
0x180014058  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001405f  mov     edx, 73h ; 's'; void *
0x180014064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014069  lea     rcx, [rbp+var_30]
0x18001406d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014072  jmp     short loc_18001408E
0x180014074  mov     rax, qword ptr [rbp+var_30]
0x180014078  mov     qword ptr [rbp+var_30], 0
0x180014080  mov     [rdi], rax
0x180014083  lea     rcx, [rbp+var_30]
0x180014087  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001408c  xor     ebx, ebx
0x18001408e  lea     rcx, [rbp+StringUuid]
0x180014092  call    ??1?$unique_storage@U?$resource_policy@PEAG$$A6AXPEAG@Z$1?CloseRpcString@NgcUtils@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&NgcUtils::CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (ushort *),&NgcUtils::CloseRpcString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014097  mov     eax, ebx
0x180014099  mov     rcx, [rbp+var_10]
0x18001409d  xor     rcx, rsp; StackCookie
0x1800140a0  call    __security_check_cookie
0x1800140a5  mov     rbx, [rsp+50h+arg_8]
0x1800140aa  mov     rdi, [rsp+50h+arg_10]
0x1800140af  add     rsp, 50h
0x1800140b3  pop     rbp
0x1800140b4  retn
```
