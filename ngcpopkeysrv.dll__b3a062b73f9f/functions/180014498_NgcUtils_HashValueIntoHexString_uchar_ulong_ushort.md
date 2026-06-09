# NgcUtils::HashValueIntoHexString(uchar *,ulong,ushort * *)

- ea: `0x180014498`
- end: `0x18001457f`
- name: `?HashValueIntoHexString@NgcUtils@@YAJPEAEKPEAPEAG@Z`
- size: `231`
- prototype: `int(NgcUtils *__hidden this, unsigned __int8 *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014478`

## callees

- `0x180004de0`
- `0x18000b0fc`
- `0x18000db5c`
- `0x180010730`
- `0x18001368c`
- `0x180014498`
- `0x180015194`

## import_xrefs

- `bcrypt!BCryptHash` at `0x1800144d5`
- `bcrypt!BCryptHash` at `0x1800144d5`

## string_xrefs

- `0x1800144e4`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001452f`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
int __fastcall NgcUtils::HashValueIntoHexString(NgcUtils *this, unsigned __int8 *a2, _QWORD *a3, unsigned __int16 **a4)
{
  int v5; // eax
  const unsigned __int8 *v7; // rdx
  int v8; // eax
  int v9; // ebx
  int v10; // [rsp+20h] [rbp-58h]
  unsigned int v11[2]; // [rsp+40h] [rbp-38h] BYREF
  BYTE pbBinary[32]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v10 = (int)a2;
  v5 = BCryptHash(65, 0, 0, this);
  if ( v5 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x89,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
             (const char *)(unsigned int)v5,
             v10);
  *(_QWORD *)v11 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v11,
    0);
  v8 = NgcUtils::ConvertBinaryToString(pbBinary, v7, 0x4000000Cu, (LPWSTR *)v11);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v9 = 0;
    *a3 = *(_QWORD *)v11;
    *(_QWORD *)v11 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)v8,
      v10);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v11);
  return v9;
}

```

## disassembly

```asm
0x180014498  mov     [rsp+arg_18], rbx
0x18001449d  push    rdi
0x18001449e  sub     rsp, 70h
0x1800144a2  mov     rax, cs:__security_cookie
0x1800144a9  xor     rax, rsp
0x1800144ac  mov     [rsp+78h+var_10], rax
0x1800144b1  lea     rax, [rsp+78h+pbBinary]
0x1800144b6  mov     [rsp+78h+var_48], 20h ; ' '
0x1800144be  mov     [rsp+78h+var_50], rax
0x1800144c3  mov     rdi, r8
0x1800144c6  mov     dword ptr [rsp+78h+var_58], edx; int
0x1800144ca  mov     r9, rcx
0x1800144cd  xor     edx, edx
0x1800144cf  xor     r8d, r8d
0x1800144d2  lea     ecx, [rdx+41h]
0x1800144d5  call    cs:__imp_BCryptHash
0x1800144db  test    eax, eax
0x1800144dd  jns     short loc_1800144FA
0x1800144df  mov     rcx, [rsp+78h]; this
0x1800144e4  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800144eb  mov     r9d, eax; char *
0x1800144ee  mov     edx, 89h; void *
0x1800144f3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800144f8  jmp     short loc_180014564
0x1800144fa  xor     edx, edx
0x1800144fc  mov     qword ptr [rsp+78h+var_38], 0
0x180014505  lea     rcx, [rsp+78h+var_38]
0x18001450a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001450f  lea     r9, [rsp+78h+var_38]; unsigned int
0x180014514  mov     r8d, 4000000Ch; unsigned int
0x18001451a  lea     rcx, [rsp+78h+pbBinary]; pbBinary
0x18001451f  call    ?ConvertBinaryToString@NgcUtils@@YAJPEBEKKPEAPEAG@Z; NgcUtils::ConvertBinaryToString(uchar const *,ulong,ulong,ushort * *)
0x180014524  mov     ebx, eax
0x180014526  test    eax, eax
0x180014528  jns     short loc_180014545
0x18001452a  mov     rcx, [rsp+78h]; this
0x18001452f  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180014536  mov     r9d, eax; char *
0x180014539  mov     edx, 90h; void *
0x18001453e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014543  jmp     short loc_180014558
0x180014545  mov     rax, qword ptr [rsp+78h+var_38]
0x18001454a  xor     ebx, ebx
0x18001454c  mov     [rdi], rax
0x18001454f  mov     qword ptr [rsp+78h+var_38], 0
0x180014558  lea     rcx, [rsp+78h+var_38]
0x18001455d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014562  mov     eax, ebx
0x180014564  mov     rcx, [rsp+78h+var_10]
0x180014569  xor     rcx, rsp; StackCookie
0x18001456c  call    __security_check_cookie
0x180014571  mov     rbx, [rsp+78h+arg_18]
0x180014579  add     rsp, 70h
0x18001457d  pop     rdi
0x18001457e  retn
```
