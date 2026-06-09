# DRMpFileIsProtected

- ea: `0x180052230`
- end: `0x18005242b`
- name: `DRMpFileIsProtected`
- size: `507`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000343a`
- `0x18005109c`
- `0x1800516b8`
- `0x180052230`
- `0x18005bdc0`
- `0x18005be80`
- `0x18005f010`

## string_xrefs

- `0x180052351`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`
- `0x180052388`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`
- `0x1800523c6`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`
- `0x180052401`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\protectedfile\cprotectedfile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DRMpFileIsProtected(__int64 a1, _DWORD *a2)
{
  __int64 v3; // rcx
  volatile signed __int32 *v4; // rbx
  int v6; // [rsp+30h] [rbp-1338h] BYREF
  _QWORD *v7; // [rsp+38h] [rbp-1330h] BYREF
  volatile signed __int32 *v8; // [rsp+40h] [rbp-1328h]
  __int64 v9; // [rsp+48h] [rbp-1320h]
  _BYTE pExceptionObject[1216]; // [rsp+50h] [rbp-1318h] BYREF
  _BYTE v11[1216]; // [rsp+510h] [rbp-E58h] BYREF
  _BYTE v12[1216]; // [rsp+9D0h] [rbp-998h] BYREF
  _BYTE v13[1216]; // [rsp+E90h] [rbp-4D8h] BYREF

  v9 = -2;
  try
  {
    if ( !a1 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
        0xA2u,
        L"hFile",
        -2147024809);
      throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
    }
    if ( !a2 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)v11,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
        0xA3u,
        L"pdwFileStatus",
        -2147024809);
      throw (Microsoft::FoundationServices::Common::FsException *)v11;
    }
    ConvertHandle<Microsoft::InformationProtection::CProtectedFile>(&v7, a1);
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *))(*v7 + 8LL))(v7) )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)v12,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
        0xA6u,
        L"pProtectedFile->IsValid()",
        -2147024809);
      throw (Microsoft::FoundationServices::Common::FsException *)v12;
    }
    v3 = v7[3];
    if ( !v3 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)v13,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\protectedfile\\cprotectedfile.cpp",
        0x45u,
        &Src,
        -2147418113);
      throw (Microsoft::FoundationServices::Common::FsException *)v13;
    }
    v6 = 0;
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v3 + 8LL))(v3, &v6);
    *a2 = v6;
    v4 = v8;
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
        if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
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
0x180052230  push    rdi
0x180052232  mov     eax, 1360h
0x180052237  call    _alloca_probe
0x18005223c  sub     rsp, rax
0x18005223f  mov     [rsp+1368h+var_1320], 0FFFFFFFFFFFFFFFEh
0x180052248  mov     [rsp+1368h+arg_10], rbx
0x180052250  mov     rax, cs:__security_cookie
0x180052257  xor     rax, rsp
0x18005225a  mov     [rsp+1368h+var_18], rax
0x180052262  mov     rbx, rdx
0x180052265  xor     edi, edi
0x180052267  test    rcx, rcx
0x18005226a  jz      loc_18005233C
0x180052270  test    rbx, rbx
0x180052273  jz      loc_180052373
0x180052279  mov     rdx, rcx
0x18005227c  lea     rcx, [rsp+1368h+var_1330]
0x180052281  call    ??$ConvertHandle@VCProtectedFile@InformationProtection@Microsoft@@@@YA?AV?$shared_ptr@VCProtectedFile@InformationProtection@Microsoft@@@tr1@std@@PEAX@Z; ConvertHandle<Microsoft::InformationProtection::CProtectedFile>(void *)
0x180052286  nop
0x180052287  mov     rcx, [rsp+1368h+var_1330]
0x18005228c  mov     rax, [rcx]
0x18005228f  mov     rax, [rax+8]
0x180052293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052298  test    al, al
0x18005229a  jz      loc_1800523B1
0x1800522a0  mov     rax, [rsp+1368h+var_1330]
0x1800522a5  mov     rcx, [rax+18h]
0x1800522a9  test    rcx, rcx
0x1800522ac  jz      loc_1800523EE
0x1800522b2  mov     [rsp+1368h+var_1338], 0
0x1800522ba  mov     rax, [rcx]
0x1800522bd  lea     rdx, [rsp+1368h+var_1338]
0x1800522c2  mov     rax, [rax+8]
0x1800522c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522cb  mov     eax, [rsp+1368h+var_1338]
0x1800522cf  mov     [rbx], eax
0x1800522d1  mov     rbx, [rsp+1368h+var_1328]
0x1800522d6  test    rbx, rbx
0x1800522d9  jz      short loc_180052313
0x1800522db  or      eax, 0FFFFFFFFh
0x1800522de  lock xadd [rbx+8], eax
0x1800522e3  cmp     eax, 1
0x1800522e6  jnz     short loc_180052313
0x1800522e8  mov     rax, [rbx]
0x1800522eb  mov     rcx, rbx
0x1800522ee  mov     rax, [rax]
0x1800522f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522f6  or      eax, 0FFFFFFFFh
0x1800522f9  lock xadd [rbx+0Ch], eax
0x1800522fe  cmp     eax, 1
0x180052301  jnz     short loc_180052313
0x180052303  mov     rax, [rbx]
0x180052306  mov     rcx, rbx
0x180052309  mov     rax, [rax+8]
0x18005230d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052312  nop
0x180052313  jmp     short loc_180052319
0x180052315  mov     edi, [rsp+1368h+var_1338]
0x180052319  mov     eax, edi
0x18005231b  mov     rcx, [rsp+1368h+var_18]
0x180052323  xor     rcx, rsp; StackCookie
0x180052326  call    __security_check_cookie
0x18005232b  mov     rbx, [rsp+1368h+arg_10]
0x180052333  add     rsp, 1360h
0x18005233a  pop     rdi
0x18005233b  retn
0x18005233c  mov     [rsp+1368h+var_1348], 80070057h; int
0x180052344  lea     r9, aHfile; "hFile"
0x18005234b  mov     r8d, 0A2h; unsigned int
0x180052351  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x180052358  lea     rcx, [rsp+1368h+pExceptionObject]; this
0x18005235d  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180052362  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180052369  lea     rcx, [rsp+1368h+pExceptionObject]; pExceptionObject
0x18005236e  call    _CxxThrowException_0
0x180052373  mov     [rsp+1368h+var_1348], 80070057h; int
0x18005237b  lea     r9, aPdwfilestatus; "pdwFileStatus"
0x180052382  mov     r8d, 0A3h; unsigned int
0x180052388  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x18005238f  lea     rcx, [rsp+1368h+var_E58]; this
0x180052397  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18005239c  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x1800523a3  lea     rcx, [rsp+1368h+var_E58]; pExceptionObject
0x1800523ab  call    _CxxThrowException_0
0x1800523b1  mov     [rsp+1368h+var_1348], 80070057h; int
0x1800523b9  lea     r9, aPprotectedfile; "pProtectedFile->IsValid()"
0x1800523c0  mov     r8d, 0A6h; unsigned int
0x1800523c6  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x1800523cd  lea     rcx, [rsp+1368h+var_998]; this
0x1800523d5  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800523da  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x1800523e1  lea     rcx, [rsp+1368h+var_998]; pExceptionObject
0x1800523e9  call    _CxxThrowException_0
0x1800523ee  mov     [rsp+1368h+var_1348], 8000FFFFh; int
0x1800523f6  lea     r9, Src; unsigned __int16 *
0x1800523fd  lea     r8d, [rcx+45h]; unsigned int
0x180052401  lea     rdx, aDsSecurityRmSr_0; "ds\\security\\rm\\src\\client\\promethi"...
0x180052408  lea     rcx, [rsp+1368h+var_4D8]; this
0x180052410  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180052415  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x18005241c  lea     rcx, [rsp+1368h+var_4D8]; pExceptionObject
0x180052424  call    _CxxThrowException_0
```
