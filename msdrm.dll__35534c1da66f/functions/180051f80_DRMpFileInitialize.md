# DRMpFileInitialize

- ea: `0x180051f80`
- end: `0x180052222`
- name: `DRMpFileInitialize`
- size: `674`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001244`
- `0x18000343a`
- `0x18005117c`
- `0x180051274`
- `0x18005131c`
- `0x1800516b8`
- `0x180051f80`
- `0x180052f50`
- `0x18005bdc0`
- `0x18005be80`
- `0x18005f010`

## string_xrefs

- `0x180052114`: `StringCchLength(wszInputFileExtension, STRSAFE_MAX_CCH, NULL)`
- `0x180052121`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`
- `0x180052152`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`
- `0x180052189`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`
- `0x1800521c0`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`
- `0x1800521f8`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DRMpFileInitialize(
        const unsigned __int16 *a1,
        struct ILockBytes *a2,
        unsigned int a3,
        unsigned int a4,
        _QWORD *a5)
{
  const unsigned __int16 *v8; // rbx
  __int64 v9; // rax
  int v10; // ecx
  Microsoft::InformationProtection::CProtectedFile *v11; // rax
  unsigned int v12; // edx
  __int64 v13; // rax
  volatile signed __int32 *v14; // rbx
  __int64 v15; // rax
  const struct _IPC_PROMPT_CTX *v17; // [rsp+20h] [rbp-1858h]
  __int128 v18; // [rsp+40h] [rbp-1838h] BYREF
  __int128 v19; // [rsp+50h] [rbp-1828h] BYREF
  __int64 v20; // [rsp+60h] [rbp-1818h]
  _BYTE pExceptionObject[1216]; // [rsp+70h] [rbp-1808h] BYREF
  _BYTE v22[1216]; // [rsp+530h] [rbp-1348h] BYREF
  _BYTE v23[1216]; // [rsp+9F0h] [rbp-E88h] BYREF
  _BYTE v24[1216]; // [rsp+EB0h] [rbp-9C8h] BYREF
  _BYTE v25[1216]; // [rsp+1370h] [rbp-508h] BYREF

  v20 = -2;
  v8 = a1;
  if ( a1 )
  {
    v9 = 0x7FFFFFFF;
    do
    {
      if ( !*a1 )
        break;
      ++a1;
      --v9;
    }
    while ( v9 );
    v10 = v9 == 0 ? 0x80070057 : 0;
  }
  else
  {
    v10 = -2147024809;
  }
  try
  {
    if ( v10 < 0 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
        0x2Eu,
        L"StringCchLength(wszInputFileExtension, STRSAFE_MAX_CCH, NULL)",
        v10);
      throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
    }
    if ( !a2 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)v22,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
        0x2Fu,
        L"pilbInputByteStream",
        -2147024809);
      throw (Microsoft::FoundationServices::Common::FsException *)v22;
    }
    if ( !a5 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)v23,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
        0x30u,
        L"phFile",
        -2147024809);
      throw (Microsoft::FoundationServices::Common::FsException *)v23;
    }
    if ( !a3 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)v24,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
        0x31u,
        L"hEnv",
        -2147024809);
      throw (Microsoft::FoundationServices::Common::FsException *)v24;
    }
    if ( !a4 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)v25,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
        0x32u,
        L"hDefaultLibrary",
        -2147024809);
      throw (Microsoft::FoundationServices::Common::FsException *)v25;
    }
    v19 = 0;
    v11 = (Microsoft::InformationProtection::CProtectedFile *)operator new(0x28u);
    *(_QWORD *)&v18 = v11;
    if ( v11 )
      v13 = Microsoft::InformationProtection::CProtectedFile::CProtectedFile(v11, v12, v8, a2, v17, a3, a4);
    else
      v13 = 0;
    v18 = 0;
    std::tr1::shared_ptr<Microsoft::InformationProtection::CProtectedFile>::_Resetp<Microsoft::InformationProtection::CProtectedFile>(
      &v18,
      v13);
    v14 = (volatile signed __int32 *)*((_QWORD *)&v18 + 1);
    v19 = v18;
    v15 = std::tr1::shared_ptr<Microsoft::InformationProtection::CProtectedFile>::shared_ptr<Microsoft::InformationProtection::CProtectedFile>(
            &v18,
            &v19);
    *a5 = CreateHandle<Microsoft::InformationProtection::CProtectedFile>(v15);
    if ( v14 )
    {
      if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
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
0x180051f80  push    rbx
0x180051f82  push    rsi
0x180051f83  push    rdi
0x180051f84  push    r12
0x180051f86  push    r13
0x180051f88  push    r14
0x180051f8a  push    r15
0x180051f8c  mov     eax, 1840h
0x180051f91  call    _alloca_probe
0x180051f96  sub     rsp, rax
0x180051f99  mov     [rsp+1878h+var_1818], 0FFFFFFFFFFFFFFFEh
0x180051fa2  mov     rax, cs:__security_cookie
0x180051fa9  xor     rax, rsp
0x180051fac  mov     [rsp+1878h+var_48], rax
0x180051fb4  mov     r12d, r9d
0x180051fb7  mov     r15d, r8d
0x180051fba  mov     r14, rdx
0x180051fbd  mov     rbx, rcx
0x180051fc0  mov     rsi, [rsp+1878h+arg_20]
0x180051fc8  xor     r13d, r13d
0x180051fcb  mov     edi, r13d
0x180051fce  test    rcx, rcx
0x180051fd1  jz      short loc_180051FF8
0x180051fd3  mov     eax, 7FFFFFFFh
0x180051fd8  cmp     [rcx], r13w
0x180051fdc  jz      short loc_180051FE8
0x180051fde  add     rcx, 2
0x180051fe2  sub     rax, 1
0x180051fe6  jnz     short loc_180051FD8
0x180051fe8  neg     rax
0x180051feb  sbb     ecx, ecx
0x180051fed  not     ecx
0x180051fef  mov     eax, 80070057h
0x180051ff4  and     ecx, eax
0x180051ff6  jmp     short loc_180051FFF
0x180051ff8  mov     eax, 80070057h
0x180051ffd  mov     ecx, eax
0x180051fff  test    ecx, ecx
0x180052001  js      loc_180052110
0x180052007  test    r14, r14
0x18005200a  jz      loc_180052143
0x180052010  test    rsi, rsi
0x180052013  jz      loc_18005217A
0x180052019  test    r15d, r15d
0x18005201c  jz      loc_1800521B1
0x180052022  test    r12d, r12d
0x180052025  jz      loc_1800521E8
0x18005202b  xorps   xmm0, xmm0
0x18005202e  movdqu  [rsp+1878h+var_1828], xmm0
0x180052034  mov     ecx, 28h ; '('; Size
0x180052039  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005203e  mov     qword ptr [rsp+1878h+var_1838], rax
0x180052043  test    rax, rax
0x180052046  jz      short loc_180052062
0x180052048  mov     [rsp+1878h+var_1848], r12d; unsigned int
0x18005204d  mov     [rsp+1878h+var_1850], r15d; unsigned int
0x180052052  mov     r9, r14; struct ILockBytes *
0x180052055  mov     r8, rbx; unsigned __int16 *
0x180052058  mov     rcx, rax; this
0x18005205b  call    ??0CProtectedFile@InformationProtection@Microsoft@@QEAA@KPEBGPEAUILockBytes@@PEBU_IPC_PROMPT_CTX@@KK@Z; Microsoft::InformationProtection::CProtectedFile::CProtectedFile(ulong,ushort const *,ILockBytes *,_IPC_PROMPT_CTX const *,ulong,ulong)
0x180052060  jmp     short loc_180052065
0x180052062  mov     rax, r13
0x180052065  xorps   xmm0, xmm0
0x180052068  movdqu  [rsp+1878h+var_1838], xmm0
0x18005206e  mov     rdx, rax
0x180052071  lea     rcx, [rsp+1878h+var_1838]
0x180052076  call    ??$_Resetp@VCProtectedFile@InformationProtection@Microsoft@@@?$shared_ptr@VCProtectedFile@InformationProtection@Microsoft@@@tr1@std@@AEAAXPEAVCProtectedFile@InformationProtection@Microsoft@@@Z; std::tr1::shared_ptr<Microsoft::InformationProtection::CProtectedFile>::_Resetp<Microsoft::InformationProtection::CProtectedFile>(Microsoft::InformationProtection::CProtectedFile *)
0x18005207b  mov     rbx, qword ptr [rsp+1878h+var_1838+8]
0x180052080  mov     qword ptr [rsp+1878h+var_1828+8], rbx
0x180052085  mov     rax, qword ptr [rsp+1878h+var_1838]
0x18005208a  mov     qword ptr [rsp+1878h+var_1828], rax
0x18005208f  lea     rdx, [rsp+1878h+var_1828]
0x180052094  lea     rcx, [rsp+1878h+var_1838]
0x180052099  call    ??0?$shared_ptr@VCProtectedFile@InformationProtection@Microsoft@@@tr1@std@@QEAA@AEBV012@@Z; std::tr1::shared_ptr<Microsoft::InformationProtection::CProtectedFile>::shared_ptr<Microsoft::InformationProtection::CProtectedFile>(std::tr1::shared_ptr<Microsoft::InformationProtection::CProtectedFile> const &)
0x18005209e  mov     rcx, rax
0x1800520a1  call    ??$CreateHandle@VCProtectedFile@InformationProtection@Microsoft@@@@YAPEAXV?$shared_ptr@VCProtectedFile@InformationProtection@Microsoft@@@tr1@std@@@Z; CreateHandle<Microsoft::InformationProtection::CProtectedFile>(std::tr1::shared_ptr<Microsoft::InformationProtection::CProtectedFile>)
0x1800520a6  mov     [rsi], rax
0x1800520a9  test    rbx, rbx
0x1800520ac  jz      short loc_1800520E5
0x1800520ae  or      esi, 0FFFFFFFFh
0x1800520b1  mov     eax, esi
0x1800520b3  lock xadd [rbx+8], eax
0x1800520b8  add     eax, esi
0x1800520ba  jnz     short loc_1800520E5
0x1800520bc  mov     rax, [rbx]
0x1800520bf  mov     rcx, rbx
0x1800520c2  mov     rax, [rax]
0x1800520c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800520ca  mov     eax, esi
0x1800520cc  lock xadd [rbx+0Ch], eax
0x1800520d1  add     eax, esi
0x1800520d3  jnz     short loc_1800520E5
0x1800520d5  mov     rax, [rbx]
0x1800520d8  mov     rcx, rbx
0x1800520db  mov     rax, [rax+8]
0x1800520df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800520e4  nop
0x1800520e5  jmp     short loc_1800520EB
0x1800520e7  mov     edi, dword ptr [rsp+1878h+var_1838]
0x1800520eb  mov     eax, edi
0x1800520ed  mov     rcx, [rsp+1878h+var_48]
0x1800520f5  xor     rcx, rsp; StackCookie
0x1800520f8  call    __security_check_cookie
0x1800520fd  add     rsp, 1840h
0x180052104  pop     r15
0x180052106  pop     r14
0x180052108  pop     r13
0x18005210a  pop     r12
0x18005210c  pop     rdi
0x18005210d  pop     rsi
0x18005210e  pop     rbx
0x18005210f  retn
0x180052110  mov     dword ptr [rsp+1878h+var_1858], ecx; int
0x180052114  lea     r9, aStringcchlengt_1; "StringCchLength(wszInputFileExtension, "...
0x18005211b  mov     r8d, 2Eh ; '.'; unsigned int
0x180052121  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x180052128  lea     rcx, [rsp+1878h+pExceptionObject]; this
0x18005212d  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180052132  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180052139  lea     rcx, [rsp+1878h+pExceptionObject]; pExceptionObject
0x18005213e  call    _CxxThrowException_0
0x180052143  mov     dword ptr [rsp+1878h+var_1858], eax; int
0x180052147  lea     r9, aPilbinputbytes; "pilbInputByteStream"
0x18005214e  lea     r8d, [r14+2Fh]; unsigned int
0x180052152  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x180052159  lea     rcx, [rsp+1878h+var_1348]; this
0x180052161  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180052166  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x18005216d  lea     rcx, [rsp+1878h+var_1348]; pExceptionObject
0x180052175  call    _CxxThrowException_0
0x18005217a  mov     dword ptr [rsp+1878h+var_1858], eax; int
0x18005217e  lea     r9, aPhfile; "phFile"
0x180052185  lea     r8d, [rsi+30h]; unsigned int
0x180052189  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x180052190  lea     rcx, [rsp+1878h+var_E88]; this
0x180052198  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18005219d  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x1800521a4  lea     rcx, [rsp+1878h+var_E88]; pExceptionObject
0x1800521ac  call    _CxxThrowException_0
0x1800521b1  mov     dword ptr [rsp+1878h+var_1858], eax; int
0x1800521b5  lea     r9, aHenv; "hEnv"
0x1800521bc  lea     r8d, [r15+31h]; unsigned int
0x1800521c0  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x1800521c7  lea     rcx, [rsp+1878h+var_9C8]; this
0x1800521cf  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800521d4  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x1800521db  lea     rcx, [rsp+1878h+var_9C8]; pExceptionObject
0x1800521e3  call    _CxxThrowException_0
0x1800521e8  mov     dword ptr [rsp+1878h+var_1858], eax; int
0x1800521ec  lea     r9, aHdefaultlibrar; "hDefaultLibrary"
0x1800521f3  lea     r8d, [r12+32h]; unsigned int
0x1800521f8  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x1800521ff  lea     rcx, [rsp+1878h+var_508]; this
0x180052207  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18005220c  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180052213  lea     rcx, [rsp+1878h+var_508]; pExceptionObject
0x18005221b  call    _CxxThrowException_0
```
