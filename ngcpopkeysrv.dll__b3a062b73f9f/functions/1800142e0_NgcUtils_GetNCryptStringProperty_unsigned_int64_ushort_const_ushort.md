# NgcUtils::GetNCryptStringProperty(unsigned __int64,ushort const *,ushort * *)

- ea: `0x1800142e0`
- end: `0x180014377`
- name: `?GetNCryptStringProperty@NgcUtils@@YAJ_KPEBGPEAPEAG@Z`
- size: `151`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, unsigned __int64, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800181a0`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x1800141e4`
- `0x1800142e0`

## string_xrefs

- `0x180014335`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::GetNCryptStringProperty(
        NgcUtils *this,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  int NCryptBinaryBlob; // ebx
  HLOCAL *v7; // [rsp+20h] [rbp-28h] BYREF
  __int64 v8; // [rsp+28h] [rbp-20h] BYREF
  char v9; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int8 *v11; // [rsp+58h] [rbp+10h] BYREF
  HLOCAL v12; // [rsp+68h] [rbp+20h] BYREF

  v8 = 0;
  v7 = &v12;
  v9 = 1;
  v12 = 0;
  NCryptBinaryBlob = NgcUtils::GetNCryptBinaryBlob((NCRYPT_HANDLE)this, L"Name", (unsigned __int16 *)&v8, &v11);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&v7);
  if ( NCryptBinaryBlob >= 0 )
  {
    NCryptBinaryBlob = 0;
    *(_QWORD *)a3 = v12;
    v12 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)NCryptBinaryBlob,
      (int)v7);
  }
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v12, 0);
  return (unsigned int)NCryptBinaryBlob;
}

```

## disassembly

```asm
0x1800142e0  mov     r11, rsp
0x1800142e3  mov     [r11+8], rbx
0x1800142e7  push    rdi
0x1800142e8  sub     rsp, 40h
0x1800142ec  lea     rax, [r11+20h]
0x1800142f0  mov     qword ptr [r11-20h], 0
0x1800142f8  mov     rdi, r8
0x1800142fb  mov     [r11-28h], rax
0x1800142ff  lea     r9, [r11+10h]; unsigned __int8 **
0x180014303  mov     [rsp+48h+var_18], 1
0x180014308  lea     r8, [r11-20h]; unsigned __int16 *
0x18001430c  mov     qword ptr [r11+20h], 0
0x180014314  lea     rdx, aName; "Name"
0x18001431b  call    ?GetNCryptBinaryBlob@NgcUtils@@YAJ_KPEBGPEAPEAEPEAK@Z; NgcUtils::GetNCryptBinaryBlob(unsigned __int64,ushort const *,uchar * *,ulong *)
0x180014320  lea     rcx, [rsp+48h+var_28]
0x180014325  mov     ebx, eax
0x180014327  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001432c  test    ebx, ebx
0x18001432e  jns     short loc_18001434B
0x180014330  mov     rcx, [rsp+48h]; this
0x180014335  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001433c  mov     r9d, ebx; char *
0x18001433f  mov     edx, 0D2h; void *
0x180014344  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014349  jmp     short loc_18001435E
0x18001434b  mov     rax, [rsp+48h+arg_18]
0x180014350  xor     ebx, ebx
0x180014352  mov     [rdi], rax
0x180014355  mov     [rsp+48h+arg_18], 0
0x18001435e  xor     edx, edx
0x180014360  lea     rcx, [rsp+48h+arg_18]
0x180014365  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001436a  mov     eax, ebx
0x18001436c  mov     rbx, [rsp+48h+arg_0]
0x180014371  add     rsp, 40h
0x180014375  pop     rdi
0x180014376  retn
```
