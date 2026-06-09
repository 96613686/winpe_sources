# ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)

- ea: `0x180008754`
- end: `0x180008880`
- name: `??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ`
- size: `300`
- prototype: `ATL::CSid *(ATL::CSid *this, PSID_IDENTIFIER_AUTHORITY pIdentifierAuthority, UCHAR, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000c478`

## callees

- `0x18000579c`
- `0x180005c18`
- `0x180007bc8`
- `0x180008754`
- `0x180009ee4`
- `0x18002c840`

## import_xrefs

- `ADVAPI32!GetSidSubAuthority` at `0x18000882c`
- `ADVAPI32!GetSidSubAuthority` at `0x18000882c`
- `ADVAPI32!InitializeSid` at `0x1800087f1`
- `ADVAPI32!InitializeSid` at `0x1800087f1`
- `ADVAPI32!GetSidLengthRequired` at `0x1800087d2`
- `ADVAPI32!GetSidLengthRequired` at `0x1800087d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ATL::CSid *ATL::CSid::CSid(ATL::CSid *this, PSID_IDENTIFIER_AUTHORITY pIdentifierAuthority, UCHAR a3, ...)
{
  va_list v5; // rbp
  DWORD i; // esi
  DWORD v7; // ebx
  struct _SID Sid[6]; // [rsp+30h] [rbp-88h] BYREF
  va_list va; // [rsp+D8h] [rbp+20h] BYREF

  va_start(va, a3);
  *(_QWORD *)this = &ATL::CSid::`vftable';
  *((_BYTE *)this + 76) = 0;
  *((_DWORD *)this + 20) = 7;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)this + 88);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)this + 96);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)this + 104);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)this + 112);
  if ( !a3 || GetSidLengthRequired(a3) > 0x44 )
    ATL::AtlThrowImpl(-2147024809);
  if ( !InitializeSid(Sid, pIdentifierAuthority, a3) )
    ATL::AtlThrowLastWin32();
  va_copy(v5, va);
  for ( i = 0; i < a3; *GetSidSubAuthority(Sid, i++) = v7 )
  {
    v5 += 8;
    v7 = *((_DWORD *)v5 - 2);
  }
  ATL::CSid::Copy(this, Sid);
  *((_DWORD *)this + 20) = 8;
  return this;
}

```

## disassembly

```asm
0x180008754  mov     [rsp+nSubAuthorityCount], r8b
0x180008759  mov     [rsp+arg_18], r9
0x18000875e  push    rbx
0x18000875f  push    rbp
0x180008760  push    rsi
0x180008761  push    rdi
0x180008762  sub     rsp, 98h
0x180008769  mov     rax, cs:__security_cookie
0x180008770  xor     rax, rsp
0x180008773  mov     [rsp+0B8h+var_38], rax
0x18000877b  mov     rbx, rdx
0x18000877e  mov     rdi, rcx
0x180008781  mov     [rsp+0B8h+var_98], rcx
0x180008786  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x18000878d  mov     [rcx], rax
0x180008790  mov     byte ptr [rcx+4Ch], 0
0x180008794  mov     dword ptr [rcx+50h], 7
0x18000879b  add     rcx, 58h ; 'X'
0x18000879f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800087a4  nop
0x1800087a5  lea     rcx, [rdi+60h]
0x1800087a9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800087ae  nop
0x1800087af  lea     rcx, [rdi+68h]
0x1800087b3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800087b8  nop
0x1800087b9  lea     rcx, [rdi+70h]
0x1800087bd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800087c2  nop
0x1800087c3  mov     cl, [rsp+0B8h+nSubAuthorityCount]; nSubAuthorityCount
0x1800087ca  test    cl, cl
0x1800087cc  jz      loc_180008875
0x1800087d2  call    cs:__imp_GetSidLengthRequired
0x1800087d8  cmp     eax, 44h ; 'D'
0x1800087db  ja      loc_180008875
0x1800087e1  mov     r8b, [rsp+0B8h+nSubAuthorityCount]; nSubAuthorityCount
0x1800087e9  mov     rdx, rbx; pIdentifierAuthority
0x1800087ec  lea     rcx, [rsp+0B8h+Sid]; Sid
0x1800087f1  call    cs:__imp_InitializeSid
0x1800087f7  test    eax, eax
0x1800087f9  jnz     short loc_180008801
0x1800087fb  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180008801  mov     [rsp+0B8h+var_90], 0
0x18000880a  lea     rbp, [rsp+0B8h+arg_18]
0x180008812  xor     esi, esi
0x180008814  cmp     [rsp+0B8h+nSubAuthorityCount], sil
0x18000881c  jbe     short loc_180008842
0x18000881e  lea     rbp, [rbp+8]
0x180008822  mov     ebx, [rbp-8]
0x180008825  mov     edx, esi; nSubAuthority
0x180008827  lea     rcx, [rsp+0B8h+Sid]; pSid
0x18000882c  call    cs:__imp_GetSidSubAuthority
0x180008832  mov     [rax], ebx
0x180008834  inc     esi
0x180008836  movzx   ecx, [rsp+0B8h+nSubAuthorityCount]
0x18000883e  cmp     esi, ecx
0x180008840  jb      short loc_18000881E
0x180008842  lea     rdx, [rsp+0B8h+Sid]; struct _SID *
0x180008847  mov     rcx, rdi; this
0x18000884a  call    ?Copy@CSid@ATL@@AEAAXAEBU_SID@@@Z; ATL::CSid::Copy(_SID const &)
0x18000884f  mov     dword ptr [rdi+50h], 8
0x180008856  mov     rax, rdi
0x180008859  mov     rcx, [rsp+0B8h+var_38]
0x180008861  xor     rcx, rsp; StackCookie
0x180008864  call    __security_check_cookie
0x180008869  add     rsp, 98h
0x180008870  pop     rdi
0x180008871  pop     rsi
0x180008872  pop     rbp
0x180008873  pop     rbx
0x180008874  retn
0x180008875  mov     ecx, 80070057h; int
0x18000887a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
