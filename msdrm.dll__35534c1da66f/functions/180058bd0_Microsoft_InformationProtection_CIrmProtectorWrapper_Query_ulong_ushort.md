# Microsoft::InformationProtection::CIrmProtectorWrapper::Query(ulong,ushort * *)

- ea: `0x180058bd0`
- end: `0x180058c93`
- name: `?Query@CIrmProtectorWrapper@InformationProtection@Microsoft@@UEAAXKPEAPEAG@Z`
- size: `195`
- prototype: `void __fastcall(Microsoft::InformationProtection::CIrmProtectorWrapper *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000343a`
- `0x1800516b8`
- `0x180058bd0`
- `0x18005bdc0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180058bfc`
- `OLEAUT32!__imp_SysAllocString` at `0x180058bfc`

## string_xrefs

- `0x180058c38`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x180058c70`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`

## pseudocode

```c
void __fastcall Microsoft::InformationProtection::CIrmProtectorWrapper::Query(
        const OLECHAR **this,
        int a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v4; // rax
  _BYTE pExceptionObject[1216]; // [rsp+30h] [rbp-4D8h] BYREF

  if ( (unsigned int)(a2 - 1) > 1 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
      0xAAu,
      &Src,
      -2147024809);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  v4 = SysAllocString(this[4]);
  if ( !v4 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
      0x9Eu,
      &Src,
      -2147024882);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  *a3 = v4;
}

```

## disassembly

```asm
0x180058bd0  push    rbx
0x180058bd2  sub     rsp, 500h
0x180058bd9  mov     rax, cs:__security_cookie
0x180058be0  xor     rax, rsp
0x180058be3  mov     [rsp+508h+var_18], rax
0x180058beb  mov     rbx, r8
0x180058bee  sub     edx, 1
0x180058bf1  jz      short loc_180058BF8
0x180058bf3  cmp     edx, 1
0x180058bf6  jnz     short loc_180058C23
0x180058bf8  mov     rcx, [rcx+20h]; psz
0x180058bfc  call    cs:__imp_SysAllocString
0x180058c02  test    rax, rax
0x180058c05  jz      short loc_180058C5B
0x180058c07  mov     [rbx], rax
0x180058c0a  mov     rcx, [rsp+508h+var_18]
0x180058c12  xor     rcx, rsp; StackCookie
0x180058c15  call    __security_check_cookie
0x180058c1a  add     rsp, 500h
0x180058c21  pop     rbx
0x180058c22  retn
0x180058c23  lea     r9, Src; unsigned __int16 *
0x180058c2a  mov     [rsp+508h+var_4E8], 80070057h; int
0x180058c32  mov     r8d, 0AAh; unsigned int
0x180058c38  lea     rdx, aDsSecurityRmSr_3; "ds\\security\\rm\\src\\client\\promethi"...
0x180058c3f  lea     rcx, [rsp+508h+pExceptionObject]; this
0x180058c44  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180058c49  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180058c50  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x180058c55  call    _CxxThrowException_0
0x180058c5b  lea     r9, Src; unsigned __int16 *
0x180058c62  mov     [rsp+508h+var_4E8], 8007000Eh; int
0x180058c6a  mov     r8d, 9Eh; unsigned int
0x180058c70  lea     rdx, aDsSecurityRmSr_3; "ds\\security\\rm\\src\\client\\promethi"...
0x180058c77  lea     rcx, [rsp+508h+pExceptionObject]; this
0x180058c7c  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180058c81  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180058c88  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x180058c8d  call    _CxxThrowException_0
```
