# DRMpFileUnprotect

- ea: `0x1800527e0`
- end: `0x180052a09`
- name: `DRMpFileUnprotect`
- size: `553`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001284`
- `0x18000343a`
- `0x18005109c`
- `0x1800516b8`
- `0x1800527e0`
- `0x180053aa4`
- `0x1800570f4`
- `0x18005bdc0`
- `0x18005f010`

## string_xrefs

- `0x180052965`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`
- `0x1800529a1`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`
- `0x1800529df`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DRMpFileUnprotect(__int64 a1, unsigned __int16 **a2, __int64 a3)
{
  _QWORD **v5; // r14
  void **v6; // r8
  volatile signed __int32 *v7; // rbx
  unsigned int v9; // [rsp+30h] [rbp-EB8h] BYREF
  _QWORD **v10; // [rsp+38h] [rbp-EB0h] BYREF
  volatile signed __int32 *v11; // [rsp+40h] [rbp-EA8h]
  __int64 v12; // [rsp+48h] [rbp-EA0h]
  void *Block[2]; // [rsp+50h] [rbp-E98h] BYREF
  __int64 v14; // [rsp+60h] [rbp-E88h]
  unsigned __int64 v15; // [rsp+68h] [rbp-E80h]
  _BYTE pExceptionObject[1216]; // [rsp+80h] [rbp-E68h] BYREF
  _BYTE v17[1216]; // [rsp+540h] [rbp-9A8h] BYREF
  _BYTE v18[1216]; // [rsp+A00h] [rbp-4E8h] BYREF

  v12 = -2;
  try
  {
    if ( !a1 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
        0x80u,
        L"hFile",
        -2147024809);
      throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
    }
    if ( !a3 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)v17,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
        0x81u,
        L"pilbOutputByteStream",
        -2147024809);
      throw (Microsoft::FoundationServices::Common::FsException *)v17;
    }
    ConvertHandle<Microsoft::InformationProtection::CProtectedFile>(&v10, a1);
    if ( !((unsigned __int8 (__fastcall *)(_QWORD **))(*v10)[1])(v10) )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)v18,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
        0x84u,
        L"pProtectedFile->IsValid()",
        -2147024809);
      throw (Microsoft::FoundationServices::Common::FsException *)v18;
    }
    v15 = 7;
    v14 = 0;
    LOWORD(Block[0]) = 0;
    v5 = v10;
    (*(void (__fastcall **)(_QWORD *, __int64))(*v10[3] + 24LL))(v10[3], a3);
    Microsoft::InformationProtection::CProtectedFile::GetProtectedExtension(v5, Block);
    if ( a2 )
    {
      v9 = 0;
      v6 = Block;
      if ( v15 >= 8 )
        v6 = (void **)Block[0];
      Microsoft::InformationProtection::IppUtil::StrCbAllocateAndCopy(a2, &v9, (const unsigned __int16 *)v6);
    }
    if ( v15 >= 8 )
      operator delete(Block[0]);
    v15 = 7;
    v14 = 0;
    LOWORD(Block[0]) = 0;
    v7 = v11;
    if ( v11 )
    {
      if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
  }
  catch ( ... )
  {
    Microsoft::InformationProtection::IppUtil::HandlePublicAPIException();
  }
  return 0;
}

```

## disassembly

```asm
0x1800527e0  mov     r11, rsp
0x1800527e3  push    rsi
0x1800527e4  push    rdi
0x1800527e5  push    r14
0x1800527e7  sub     rsp, 0ED0h
0x1800527ee  mov     [rsp+0EE8h+var_EA0], 0FFFFFFFFFFFFFFFEh
0x1800527f7  mov     [r11+20h], rbx
0x1800527fb  mov     rax, cs:__security_cookie
0x180052802  xor     rax, rsp
0x180052805  mov     [rsp+0EE8h+var_28], rax
0x18005280d  mov     rsi, r8
0x180052810  mov     rbx, rdx
0x180052813  xor     edi, edi
0x180052815  test    rcx, rcx
0x180052818  jz      loc_180052950
0x18005281e  test    rsi, rsi
0x180052821  jz      loc_18005298C
0x180052827  mov     rdx, rcx
0x18005282a  lea     rcx, [rsp+0EE8h+var_EB0]
0x18005282f  call    ??$ConvertHandle@VCProtectedFile@InformationProtection@Microsoft@@@@YA?AV?$shared_ptr@VCProtectedFile@InformationProtection@Microsoft@@@tr1@std@@PEAX@Z; ConvertHandle<Microsoft::InformationProtection::CProtectedFile>(void *)
0x180052834  nop
0x180052835  mov     rcx, [rsp+0EE8h+var_EB0]
0x18005283a  mov     rax, [rcx]
0x18005283d  mov     rax, [rax+8]
0x180052841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052846  test    al, al
0x180052848  jz      loc_1800529CA
0x18005284e  mov     [rsp+0EE8h+var_E80], 7
0x180052857  mov     [rsp+0EE8h+var_E88], 0
0x180052860  xor     eax, eax
0x180052862  mov     word ptr [rsp+0EE8h+Block], ax
0x180052867  mov     r14, [rsp+0EE8h+var_EB0]
0x18005286c  mov     rcx, [r14+18h]
0x180052870  mov     rax, [rcx]
0x180052873  mov     rdx, rsi
0x180052876  mov     rax, [rax+18h]
0x18005287a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005287f  lea     rdx, [rsp+0EE8h+Block]
0x180052884  mov     rcx, r14
0x180052887  call    ?GetProtectedExtension@CProtectedFile@InformationProtection@Microsoft@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::InformationProtection::CProtectedFile::GetProtectedExtension(std::wstring &)
0x18005288c  test    rbx, rbx
0x18005288f  jz      short loc_1800528B8
0x180052891  mov     [rsp+0EE8h+var_EB8], 0
0x180052899  lea     r8, [rsp+0EE8h+Block]
0x18005289e  cmp     [rsp+0EE8h+var_E80], 8
0x1800528a4  cmovnb  r8, [rsp+0EE8h+Block]; unsigned __int16 *
0x1800528aa  lea     rdx, [rsp+0EE8h+var_EB8]; unsigned int *
0x1800528af  mov     rcx, rbx; unsigned __int16 **
0x1800528b2  call    ?StrCbAllocateAndCopy@IppUtil@InformationProtection@Microsoft@@SAXPEAPEAGPEAKPEBG@Z; Microsoft::InformationProtection::IppUtil::StrCbAllocateAndCopy(ushort * *,ulong *,ushort const *)
0x1800528b7  nop
0x1800528b8  cmp     [rsp+0EE8h+var_E80], 8
0x1800528be  jb      short loc_1800528CA
0x1800528c0  mov     rcx, [rsp+0EE8h+Block]; Block
0x1800528c5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800528ca  mov     [rsp+0EE8h+var_E80], 7
0x1800528d3  mov     [rsp+0EE8h+var_E88], 0
0x1800528dc  xor     eax, eax
0x1800528de  mov     word ptr [rsp+0EE8h+Block], ax
0x1800528e3  mov     rbx, [rsp+0EE8h+var_EA8]
0x1800528e8  test    rbx, rbx
0x1800528eb  jz      short loc_180052924
0x1800528ed  or      esi, 0FFFFFFFFh
0x1800528f0  mov     eax, esi
0x1800528f2  lock xadd [rbx+8], eax
0x1800528f7  add     eax, esi
0x1800528f9  jnz     short loc_180052924
0x1800528fb  mov     rax, [rbx]
0x1800528fe  mov     rcx, rbx
0x180052901  mov     rax, [rax]
0x180052904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052909  mov     eax, esi
0x18005290b  lock xadd [rbx+0Ch], eax
0x180052910  add     eax, esi
0x180052912  jnz     short loc_180052924
0x180052914  mov     rax, [rbx]
0x180052917  mov     rcx, rbx
0x18005291a  mov     rax, [rax+8]
0x18005291e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052923  nop
0x180052924  jmp     short loc_18005292A
0x180052926  mov     edi, [rsp+0EE8h+var_EB8]
0x18005292a  mov     eax, edi
0x18005292c  mov     rcx, [rsp+0EE8h+var_28]
0x180052934  xor     rcx, rsp; StackCookie
0x180052937  call    __security_check_cookie
0x18005293c  mov     rbx, [rsp+0EE8h+arg_18]
0x180052944  add     rsp, 0ED0h
0x18005294b  pop     r14
0x18005294d  pop     rdi
0x18005294e  pop     rsi
0x18005294f  retn
0x180052950  mov     [rsp+0EE8h+var_EC8], 80070057h; int
0x180052958  lea     r9, aHfile; "hFile"
0x18005295f  mov     r8d, 80h; unsigned int
0x180052965  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x18005296c  lea     rcx, [r11-0E68h]; this
0x180052973  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180052978  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x18005297f  lea     rcx, [rsp+0EE8h+pExceptionObject]; pExceptionObject
0x180052987  call    _CxxThrowException_0
0x18005298c  mov     [rsp+0EE8h+var_EC8], 80070057h; int
0x180052994  lea     r9, aPilboutputbyte; "pilbOutputByteStream"
0x18005299b  mov     r8d, 81h; unsigned int
0x1800529a1  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x1800529a8  lea     rcx, [rsp+0EE8h+var_9A8]; this
0x1800529b0  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800529b5  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x1800529bc  lea     rcx, [rsp+0EE8h+var_9A8]; pExceptionObject
0x1800529c4  call    _CxxThrowException_0
0x1800529ca  mov     [rsp+0EE8h+var_EC8], 80070057h; int
0x1800529d2  lea     r9, aPprotectedfile; "pProtectedFile->IsValid()"
0x1800529d9  mov     r8d, 84h; unsigned int
0x1800529df  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x1800529e6  lea     rcx, [rsp+0EE8h+var_4E8]; this
0x1800529ee  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800529f3  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x1800529fa  lea     rcx, [rsp+0EE8h+var_4E8]; pExceptionObject
0x180052a02  call    _CxxThrowException_0
```
