# Microsoft::InformationProtection::IppUtil::DuplicateString(ushort * *,ushort const *)

- ea: `0x180056e20`
- end: `0x180056fd0`
- name: `?DuplicateString@IppUtil@InformationProtection@Microsoft@@SAXPEAPEAGPEBG@Z`
- size: `432`
- prototype: `static void(unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005a144`

## callees

- `0x180001284`
- `0x180001290`
- `0x18000343a`
- `0x180004654`
- `0x180015438`
- `0x1800516b8`
- `0x180056e20`
- `0x180057340`
- `0x18005bdc0`

## string_xrefs

- `0x180056f45`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\ipputil.cpp`
- `0x180056f79`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\ipputil.cpp`
- `0x180056fad`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\ipputil.cpp`
- `0x180056fa0`: `StringCchCopy(localStr, uSrcLength, wszSrc)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::InformationProtection::IppUtil::DuplicateString(
        unsigned __int16 **a1,
        const unsigned __int16 *a2)
{
  unsigned __int16 *v4; // r11
  __int64 v5; // rcx
  const unsigned __int16 *v6; // rax
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rsi
  void *v9; // rax
  int v10; // eax
  unsigned __int16 *v11[2]; // [rsp+30h] [rbp-4F8h] BYREF
  _BYTE pExceptionObject[1216]; // [rsp+40h] [rbp-4E8h] BYREF

  v11[1] = (unsigned __int16 *)-2LL;
  v4 = 0;
  v11[0] = 0;
  if ( !a1 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\ipputil.cpp",
      0xC8u,
      L"ppwszDest",
      -2147024809);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  if ( a2 )
  {
    v5 = 0x7FFFFFFF;
    v6 = a2;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = (0x7FFFFFFF - v5) & -(__int64)(v5 != 0);
    if ( !v5 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\ipputil.cpp",
        0xCCu,
        L"StringCchLength(wszSrc, STRSAFE_MAX_CCH, &uSrcLength)",
        -2147024809);
      throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
    }
    v8 = v7 + 1;
    if ( v7 + 1 < v7 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v5);
    v9 = operator new[](saturated_mul(v8, 2u));
    Microsoft::FoundationServices::Common::auto_array<unsigned short>::reset(v11, v9);
    v10 = StringCchCopyW(v11[0], v8, a2);
    if ( v10 < 0 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\ipputil.cpp",
        0xCFu,
        L"StringCchCopy(localStr, uSrcLength, wszSrc)",
        v10);
      throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
    }
  }
  *a1 = v4;
  operator delete(0);
}

```

## disassembly

```asm
0x180056e20  mov     rax, rsp
0x180056e23  push    rbp
0x180056e24  push    rsi
0x180056e25  push    rdi
0x180056e26  sub     rsp, 510h
0x180056e2d  mov     [rsp+528h+var_4F0], 0FFFFFFFFFFFFFFFEh
0x180056e36  mov     [rax+18h], rbx
0x180056e3a  mov     rax, cs:__security_cookie
0x180056e41  xor     rax, rsp
0x180056e44  mov     [rsp+528h+var_28], rax
0x180056e4c  mov     rbx, rdx
0x180056e4f  mov     rdi, rcx
0x180056e52  xor     ebp, ebp
0x180056e54  mov     r11d, ebp
0x180056e57  mov     [rsp+528h+var_4F8], rbp
0x180056e5c  test    rcx, rcx
0x180056e5f  jz      loc_180056F30
0x180056e65  test    rdx, rdx
0x180056e68  jz      loc_180056EFD
0x180056e6e  mov     r9d, 7FFFFFFFh
0x180056e74  mov     ecx, r9d
0x180056e77  mov     rax, rdx
0x180056e7a  cmp     [rax], bp
0x180056e7d  jz      short loc_180056E89
0x180056e7f  add     rax, 2
0x180056e83  sub     rcx, 1
0x180056e87  jnz     short loc_180056E7A
0x180056e89  mov     rax, rcx
0x180056e8c  neg     rax
0x180056e8f  sbb     edx, edx
0x180056e91  not     edx
0x180056e93  and     edx, 80070057h
0x180056e99  mov     rax, rcx
0x180056e9c  sub     r9, rcx
0x180056e9f  neg     rax
0x180056ea2  sbb     r8, r8
0x180056ea5  and     r8, r9
0x180056ea8  test    rcx, rcx
0x180056eab  jz      loc_180056F68
0x180056eb1  lea     rsi, [r8+1]
0x180056eb5  cmp     rsi, r8
0x180056eb8  jb      short loc_180056F2A
0x180056eba  mov     eax, 2
0x180056ebf  mul     rsi
0x180056ec2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180056ec9  cmovb   rax, rcx
0x180056ecd  mov     rcx, rax; unsigned __int64
0x180056ed0  call    ??_U@YAPEAX_K@Z
0x180056ed5  mov     rdx, rax
0x180056ed8  lea     rcx, [rsp+528h+var_4F8]
0x180056edd  call    ?reset@?$auto_array@G@Common@FoundationServices@Microsoft@@QEAAXPEAG@Z
0x180056ee2  mov     r8, rbx; unsigned __int16 *
0x180056ee5  mov     rdx, rsi; unsigned __int64
0x180056ee8  mov     r11, [rsp+528h+var_4F8]
0x180056eed  mov     rcx, r11; unsigned __int16 *
0x180056ef0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z
0x180056ef5  test    eax, eax
0x180056ef7  js      loc_180056F9C
0x180056efd  mov     [rdi], r11
0x180056f00  xor     ecx, ecx; Block
0x180056f02  call    ??3@YAXPEAX@Z
0x180056f07  mov     rcx, [rsp+528h+var_28]
0x180056f0f  xor     rcx, rsp; StackCookie
0x180056f12  call    __security_check_cookie
0x180056f17  mov     rbx, [rsp+528h+arg_10]
0x180056f1f  add     rsp, 510h
0x180056f26  pop     rdi
0x180056f27  pop     rsi
0x180056f28  pop     rbp
0x180056f29  retn
0x180056f2a  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ
0x180056f30  mov     [rsp+528h+var_508], 80070057h; int
0x180056f38  lea     r9, aPpwszdest
0x180056f3f  mov     r8d, 0C8h; unsigned int
0x180056f45  lea     rdx, aDsSecurityRmSr
0x180056f4c  lea     rcx, [rsp+528h+pExceptionObject]; this
0x180056f51  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z
0x180056f56  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180056f5d  lea     rcx, [rsp+528h+pExceptionObject]; pExceptionObject
0x180056f62  call    _CxxThrowException_0
0x180056f68  mov     [rsp+528h+var_508], edx; int
0x180056f6c  lea     r9, aStringcchlengt_3
0x180056f73  mov     r8d, 0CCh; unsigned int
0x180056f79  lea     rdx, aDsSecurityRmSr
0x180056f80  lea     rcx, [rsp+528h+pExceptionObject]; this
0x180056f85  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z
0x180056f8a  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180056f91  lea     rcx, [rsp+528h+pExceptionObject]; pExceptionObject
0x180056f96  call    _CxxThrowException_0
0x180056f9c  mov     [rsp+528h+var_508], eax; int
0x180056fa0  lea     r9, aStringcchcopyL
0x180056fa7  mov     r8d, 0CFh; unsigned int
0x180056fad  lea     rdx, aDsSecurityRmSr
0x180056fb4  lea     rcx, [rsp+528h+pExceptionObject]; this
0x180056fb9  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z
0x180056fbe  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180056fc5  lea     rcx, [rsp+528h+pExceptionObject]; pExceptionObject
0x180056fca  call    _CxxThrowException_0
```
