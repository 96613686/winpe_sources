# DRMpFileProtect

- ea: `0x180052440`
- end: `0x1800527cc`
- name: `DRMpFileProtect`
- size: `908`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int16 **, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001284`
- `0x18000343a`
- `0x18005109c`
- `0x1800516b8`
- `0x180052440`
- `0x180053cb0`
- `0x1800570f4`
- `0x18005bdc0`
- `0x18005be80`
- `0x18005f010`

## string_xrefs

- `0x1800526c1`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`
- `0x1800526fa`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`
- `0x180052731`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`
- `0x180052768`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`
- `0x1800527a2`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\api\drmfileapi.cpp`
- `0x1800526ed`: `StringCchLength(wszTemplate, STRSAFE_MAX_CCH, NULL)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DRMpFileProtect(
        __int64 a1,
        _WORD *a2,
        _WORD *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        __int64 a6)
{
  __int64 v10; // rdx
  __int64 v11; // rax
  _WORD *v12; // rcx
  int v13; // eax
  _WORD *v14; // rax
  int v15; // edx
  void **v16; // r8
  const unsigned __int16 *v17; // r8
  volatile signed __int32 *v18; // rbx
  unsigned int v20; // [rsp+40h] [rbp-1878h] BYREF
  int v21[2]; // [rsp+48h] [rbp-1870h] BYREF
  volatile signed __int32 *v22; // [rsp+50h] [rbp-1868h]
  __int64 v23; // [rsp+58h] [rbp-1860h]
  void *Block[2]; // [rsp+60h] [rbp-1858h] BYREF
  __int64 v25; // [rsp+70h] [rbp-1848h]
  unsigned __int64 v26; // [rsp+78h] [rbp-1840h]
  unsigned __int16 *v27[2]; // [rsp+88h] [rbp-1830h] BYREF
  __int64 v28; // [rsp+98h] [rbp-1820h]
  unsigned __int64 v29; // [rsp+A0h] [rbp-1818h]
  _BYTE pExceptionObject[1216]; // [rsp+B0h] [rbp-1808h] BYREF
  _BYTE v31[1216]; // [rsp+570h] [rbp-1348h] BYREF
  _BYTE v32[1216]; // [rsp+A30h] [rbp-E88h] BYREF
  _BYTE v33[1216]; // [rsp+EF0h] [rbp-9C8h] BYREF
  _BYTE v34[1216]; // [rsp+13B0h] [rbp-508h] BYREF

  v23 = -2;
  try
  {
    if ( !a1 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
        0x4Fu,
        L"hFile",
        -2147024809);
      throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
    }
    v10 = 0x7FFFFFFF;
    if ( a2 )
    {
      v11 = 0x7FFFFFFF;
      v12 = a2;
      do
      {
        if ( !*v12 )
          break;
        ++v12;
        --v11;
      }
      while ( v11 );
      v13 = v11 == 0 ? 0x80070057 : 0;
    }
    else
    {
      v13 = -2147024809;
    }
    if ( v13 < 0 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)v31,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
        0x50u,
        L"StringCchLength(wszTemplate, STRSAFE_MAX_CCH, NULL)",
        v13);
      throw (Microsoft::FoundationServices::Common::FsException *)v31;
    }
    if ( a3 )
    {
      v14 = a3;
      do
      {
        if ( !*v14 )
          break;
        ++v14;
        --v10;
      }
      while ( v10 );
      if ( !v10 )
      {
        Microsoft::FoundationServices::Common::FsException::FsException(
          (Microsoft::FoundationServices::Common::FsException *)v32,
          L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
          0x53u,
          L"StringCchLength(wszOwnerEmail, STRSAFE_MAX_CCH, NULL)",
          -2147024809);
        throw (Microsoft::FoundationServices::Common::FsException *)v32;
      }
    }
    if ( !a6 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)v33,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
        0x55u,
        L"pilbOutputByteStream",
        -2147024809);
      throw (Microsoft::FoundationServices::Common::FsException *)v33;
    }
    ConvertHandle<Microsoft::InformationProtection::CProtectedFile>(v21, a1);
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 8LL))(*(_QWORD *)v21) )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)v34,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\api\\drmfileapi.cpp",
        0x58u,
        L"pProtectedFile->IsValid()",
        -2147024809);
      throw (Microsoft::FoundationServices::Common::FsException *)v34;
    }
    v29 = 7;
    v28 = 0;
    LOWORD(v27[0]) = 0;
    v26 = 7;
    v25 = 0;
    LOWORD(Block[0]) = 0;
    Microsoft::InformationProtection::CProtectedFile::Protect(v21[0], v15, (int)a2, (int)a3, Block, (__int64)v27, a6);
    if ( a4 )
    {
      v20 = 0;
      v16 = Block;
      if ( v26 >= 8 )
        v16 = (void **)Block[0];
      Microsoft::InformationProtection::IppUtil::StrCbAllocateAndCopy(a4, &v20, (const unsigned __int16 *)v16);
    }
    if ( a5 )
    {
      v20 = 0;
      v17 = (const unsigned __int16 *)v27;
      if ( v29 >= 8 )
        v17 = v27[0];
      Microsoft::InformationProtection::IppUtil::StrCbAllocateAndCopy(a5, &v20, v17);
    }
    if ( v26 >= 8 )
      operator delete(Block[0]);
    v26 = 7;
    v25 = 0;
    LOWORD(Block[0]) = 0;
    if ( v29 >= 8 )
      operator delete(v27[0]);
    v29 = 7;
    v28 = 0;
    LOWORD(v27[0]) = 0;
    v18 = v22;
    if ( v22 )
    {
      if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
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
0x180052440  push    rbx
0x180052442  push    rsi
0x180052443  push    rdi
0x180052444  push    r12
0x180052446  push    r13
0x180052448  push    r14
0x18005244a  push    r15
0x18005244c  mov     eax, 1880h
0x180052451  call    _alloca_probe
0x180052456  sub     rsp, rax
0x180052459  mov     [rsp+18B8h+var_1860], 0FFFFFFFFFFFFFFFEh
0x180052462  mov     rax, cs:__security_cookie
0x180052469  xor     rax, rsp
0x18005246c  mov     [rsp+18B8h+var_48], rax
0x180052474  mov     r15, r9
0x180052477  mov     r14, r8
0x18005247a  mov     rdi, rdx
0x18005247d  mov     r8, rcx
0x180052480  mov     r12, [rsp+18B8h+arg_20]
0x180052488  mov     r13, [rsp+18B8h+arg_28]
0x180052490  xor     r9d, r9d
0x180052493  mov     esi, r9d
0x180052496  test    rcx, rcx
0x180052499  jz      loc_1800526AE
0x18005249f  mov     edx, 7FFFFFFFh
0x1800524a4  test    rdi, rdi
0x1800524a7  jz      short loc_1800524CE
0x1800524a9  mov     eax, edx
0x1800524ab  mov     rcx, rdi
0x1800524ae  cmp     [rcx], r9w
0x1800524b2  jz      short loc_1800524BE
0x1800524b4  add     rcx, 2
0x1800524b8  sub     rax, 1
0x1800524bc  jnz     short loc_1800524AE
0x1800524be  neg     rax
0x1800524c1  sbb     eax, eax
0x1800524c3  not     eax
0x1800524c5  mov     ebx, 80070057h
0x1800524ca  and     eax, ebx
0x1800524cc  jmp     short loc_1800524D5
0x1800524ce  mov     ebx, 80070057h
0x1800524d3  mov     eax, ebx
0x1800524d5  test    eax, eax
0x1800524d7  js      loc_1800526E9
0x1800524dd  test    r14, r14
0x1800524e0  jz      short loc_18005250A
0x1800524e2  mov     rax, r14
0x1800524e5  cmp     [rax], r9w
0x1800524e9  jz      short loc_1800524F5
0x1800524eb  add     rax, 2
0x1800524ef  sub     rdx, 1
0x1800524f3  jnz     short loc_1800524E5
0x1800524f5  mov     rax, rdx
0x1800524f8  neg     rax
0x1800524fb  sbb     ecx, ecx
0x1800524fd  not     ecx
0x1800524ff  and     ecx, ebx
0x180052501  test    rdx, rdx
0x180052504  jz      loc_180052722
0x18005250a  test    r13, r13
0x18005250d  jz      loc_180052759
0x180052513  mov     rdx, r8
0x180052516  lea     rcx, [rsp+18B8h+var_1870]
0x18005251b  call    ??$ConvertHandle@VCProtectedFile@InformationProtection@Microsoft@@@@YA?AV?$shared_ptr@VCProtectedFile@InformationProtection@Microsoft@@@tr1@std@@PEAX@Z; ConvertHandle<Microsoft::InformationProtection::CProtectedFile>(void *)
0x180052520  nop
0x180052521  mov     rcx, qword ptr [rsp+18B8h+var_1870]
0x180052526  mov     rax, [rcx]
0x180052529  mov     rax, [rax+8]
0x18005252d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052532  test    al, al
0x180052534  jz      loc_180052791
0x18005253a  mov     ecx, 7
0x18005253f  mov     [rsp+18B8h+var_1818], rcx
0x180052547  xor     ebx, ebx
0x180052549  mov     [rsp+18B8h+var_1820], rbx
0x180052551  mov     word ptr [rsp+18B8h+var_1830], bx
0x180052559  mov     [rsp+18B8h+var_1840], rcx
0x18005255e  mov     [rsp+18B8h+var_1848], rbx
0x180052563  mov     word ptr [rsp+18B8h+Block], bx
0x180052568  mov     [rsp+18B8h+var_1888], r13; __int64
0x18005256d  lea     rax, [rsp+18B8h+var_1830]
0x180052575  mov     [rsp+18B8h+var_1890], rax; __int64
0x18005257a  lea     rax, [rsp+18B8h+Block]
0x18005257f  mov     [rsp+18B8h+var_1898], rax; void *
0x180052584  mov     r9, r14; int
0x180052587  mov     r8, rdi; int
0x18005258a  mov     rcx, qword ptr [rsp+18B8h+var_1870]; int
0x18005258f  call    ?Protect@CProtectedFile@InformationProtection@Microsoft@@QEAAXKPEBXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2PEAUILockBytes@@@Z; Microsoft::InformationProtection::CProtectedFile::Protect(ulong,void const *,ushort const *,std::wstring &,std::wstring &,ILockBytes *)
0x180052594  test    r15, r15
0x180052597  jz      short loc_1800525BB
0x180052599  mov     [rsp+18B8h+var_1878], ebx
0x18005259d  lea     r8, [rsp+18B8h+Block]
0x1800525a2  cmp     [rsp+18B8h+var_1840], 8
0x1800525a8  cmovnb  r8, [rsp+18B8h+Block]; unsigned __int16 *
0x1800525ae  lea     rdx, [rsp+18B8h+var_1878]; unsigned int *
0x1800525b3  mov     rcx, r15; unsigned __int16 **
0x1800525b6  call    ?StrCbAllocateAndCopy@IppUtil@InformationProtection@Microsoft@@SAXPEAPEAGPEAKPEBG@Z; Microsoft::InformationProtection::IppUtil::StrCbAllocateAndCopy(ushort * *,ulong *,ushort const *)
0x1800525bb  test    r12, r12
0x1800525be  jz      short loc_1800525EC
0x1800525c0  mov     [rsp+18B8h+var_1878], ebx
0x1800525c4  lea     r8, [rsp+18B8h+var_1830]
0x1800525cc  cmp     [rsp+18B8h+var_1818], 8
0x1800525d5  cmovnb  r8, [rsp+18B8h+var_1830]; unsigned __int16 *
0x1800525de  lea     rdx, [rsp+18B8h+var_1878]; unsigned int *
0x1800525e3  mov     rcx, r12; unsigned __int16 **
0x1800525e6  call    ?StrCbAllocateAndCopy@IppUtil@InformationProtection@Microsoft@@SAXPEAPEAGPEAKPEBG@Z; Microsoft::InformationProtection::IppUtil::StrCbAllocateAndCopy(ushort * *,ulong *,ushort const *)
0x1800525eb  nop
0x1800525ec  cmp     [rsp+18B8h+var_1840], 8
0x1800525f2  jb      short loc_1800525FE
0x1800525f4  mov     rcx, [rsp+18B8h+Block]; Block
0x1800525f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800525fe  mov     edi, 7
0x180052603  mov     [rsp+18B8h+var_1840], rdi
0x180052608  mov     [rsp+18B8h+var_1848], rbx
0x18005260d  mov     word ptr [rsp+18B8h+Block], bx
0x180052612  cmp     [rsp+18B8h+var_1818], 8
0x18005261b  jb      short loc_18005262A
0x18005261d  mov     rcx, [rsp+18B8h+var_1830]; Block
0x180052625  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005262a  mov     [rsp+18B8h+var_1818], rdi
0x180052632  mov     [rsp+18B8h+var_1820], rbx
0x18005263a  mov     word ptr [rsp+18B8h+var_1830], bx
0x180052642  mov     rbx, [rsp+18B8h+var_1868]
0x180052647  test    rbx, rbx
0x18005264a  jz      short loc_180052683
0x18005264c  or      edi, 0FFFFFFFFh
0x18005264f  mov     eax, edi
0x180052651  lock xadd [rbx+8], eax
0x180052656  add     eax, edi
0x180052658  jnz     short loc_180052683
0x18005265a  mov     rax, [rbx]
0x18005265d  mov     rcx, rbx
0x180052660  mov     rax, [rax]
0x180052663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052668  mov     eax, edi
0x18005266a  lock xadd [rbx+0Ch], eax
0x18005266f  add     eax, edi
0x180052671  jnz     short loc_180052683
0x180052673  mov     rax, [rbx]
0x180052676  mov     rcx, rbx
0x180052679  mov     rax, [rax+8]
0x18005267d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052682  nop
0x180052683  jmp     short loc_180052689
0x180052685  mov     esi, [rsp+18B8h+var_1878]
0x180052689  mov     eax, esi
0x18005268b  mov     rcx, [rsp+18B8h+var_48]
0x180052693  xor     rcx, rsp; StackCookie
0x180052696  call    __security_check_cookie
0x18005269b  add     rsp, 1880h
0x1800526a2  pop     r15
0x1800526a4  pop     r14
0x1800526a6  pop     r13
0x1800526a8  pop     r12
0x1800526aa  pop     rdi
0x1800526ab  pop     rsi
0x1800526ac  pop     rbx
0x1800526ad  retn
0x1800526ae  mov     dword ptr [rsp+18B8h+var_1898], 80070057h; int
0x1800526b6  lea     r9, aHfile; "hFile"
0x1800526bd  lea     r8d, [rcx+4Fh]; unsigned int
0x1800526c1  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x1800526c8  lea     rcx, [rsp+18B8h+pExceptionObject]; this
0x1800526d0  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800526d5  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x1800526dc  lea     rcx, [rsp+18B8h+pExceptionObject]; pExceptionObject
0x1800526e4  call    _CxxThrowException_0
0x1800526e9  mov     dword ptr [rsp+18B8h+var_1898], eax; int
0x1800526ed  lea     r9, aStringcchlengt_4; "StringCchLength(wszTemplate, STRSAFE_MA"...
0x1800526f4  mov     r8d, 50h ; 'P'; unsigned int
0x1800526fa  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x180052701  lea     rcx, [rsp+18B8h+var_1348]; this
0x180052709  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18005270e  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180052715  lea     rcx, [rsp+18B8h+var_1348]; pExceptionObject
0x18005271d  call    _CxxThrowException_0
0x180052722  mov     dword ptr [rsp+18B8h+var_1898], ecx; int
0x180052726  lea     r9, aStringcchlengt_0; "StringCchLength(wszOwnerEmail, STRSAFE_"...
0x18005272d  lea     r8d, [rdx+53h]; unsigned int
0x180052731  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x180052738  lea     rcx, [rsp+18B8h+var_E88]; this
0x180052740  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180052745  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x18005274c  lea     rcx, [rsp+18B8h+var_E88]; pExceptionObject
0x180052754  call    _CxxThrowException_0
0x180052759  mov     dword ptr [rsp+18B8h+var_1898], ebx; int
0x18005275d  lea     r9, aPilboutputbyte; "pilbOutputByteStream"
0x180052764  lea     r8d, [r13+55h]; unsigned int
0x180052768  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x18005276f  lea     rcx, [rsp+18B8h+var_9C8]; this
0x180052777  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18005277c  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180052783  lea     rcx, [rsp+18B8h+var_9C8]; pExceptionObject
0x18005278b  call    _CxxThrowException_0
0x180052791  mov     dword ptr [rsp+18B8h+var_1898], ebx; int
0x180052795  lea     r9, aPprotectedfile; "pProtectedFile->IsValid()"
0x18005279c  mov     r8d, 58h ; 'X'; unsigned int
0x1800527a2  lea     rdx, aDsSecurityRmSr_7; "ds\\security\\rm\\src\\client\\promethi"...
0x1800527a9  lea     rcx, [rsp+18B8h+var_508]; this
0x1800527b1  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800527b6  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x1800527bd  lea     rcx, [rsp+18B8h+var_508]; pExceptionObject
0x1800527c5  call    _CxxThrowException_0
```
