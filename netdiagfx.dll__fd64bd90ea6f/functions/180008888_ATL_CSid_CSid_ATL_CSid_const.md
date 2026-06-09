# ATL::CSid::CSid(ATL::CSid const &)

- ea: `0x180008888`
- end: `0x18000893d`
- name: `??0CSid@ATL@@QEAA@AEBV01@@Z`
- size: `181`
- prototype: `ATL::CSid *__fastcall(ATL::CSid *this, const struct ATL::CSid *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800095a4`

## callees

- `0x18000579c`
- `0x180005c18`
- `0x18000821c`
- `0x180008888`
- `0x180009904`
- `0x18000d60c`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x180008908`
- `ADVAPI32!GetLengthSid` at `0x180008908`
- `ADVAPI32!CopySid` at `0x180008918`
- `ADVAPI32!CopySid` at `0x180008918`

## pseudocode

```c
ATL::CSid *__fastcall ATL::CSid::CSid(ATL::CSid *this, const struct ATL::CSid *a2)
{
  DWORD LengthSid; // eax
  int Error; // eax

  *(_QWORD *)this = &ATL::CSid::`vftable';
  *((_BYTE *)this + 76) = *((_BYTE *)a2 + 76);
  *((_DWORD *)this + 20) = *((_DWORD *)a2 + 20);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (_QWORD *)this + 11,
    (_QWORD *)a2 + 11);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (_QWORD *)this + 12,
    (_QWORD *)a2 + 12);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (_QWORD *)this + 13,
    (_QWORD *)a2 + 13);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)this + 112);
  if ( *((_BYTE *)a2 + 76) )
  {
    if ( !ATL::CSid::IsValid(a2) )
      ATL::AtlThrowImpl(-2147024809);
    LengthSid = GetLengthSid((char *)a2 + 8);
    if ( !CopySid(LengthSid, (char *)this + 8, (char *)a2 + 8) )
    {
      Error = ATL::AtlHresultFromLastError();
      ATL::AtlThrowImpl(Error);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180008888  mov     [rsp+arg_8], rbx
0x18000888d  mov     [rsp+arg_0], rcx
0x180008892  push    rdi
0x180008893  sub     rsp, 20h
0x180008897  mov     rbx, rdx
0x18000889a  mov     rdi, rcx
0x18000889d  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x1800088a4  mov     [rcx], rax
0x1800088a7  mov     al, [rdx+4Ch]
0x1800088aa  mov     [rcx+4Ch], al
0x1800088ad  mov     eax, [rdx+50h]
0x1800088b0  mov     [rcx+50h], eax
0x1800088b3  add     rdx, 58h ; 'X'
0x1800088b7  add     rcx, 58h ; 'X'
0x1800088bb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800088c0  nop
0x1800088c1  lea     rdx, [rbx+60h]
0x1800088c5  lea     rcx, [rdi+60h]
0x1800088c9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800088ce  nop
0x1800088cf  lea     rdx, [rbx+68h]
0x1800088d3  lea     rcx, [rdi+68h]
0x1800088d7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800088dc  nop
0x1800088dd  lea     rcx, [rdi+70h]
0x1800088e1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800088e6  nop
0x1800088e7  cmp     byte ptr [rbx+4Ch], 0
0x1800088eb  jz      short loc_18000892F
0x1800088ed  mov     rcx, rbx; this
0x1800088f0  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x1800088f5  test    al, al
0x1800088f7  jnz     short loc_180008904
0x1800088f9  mov     ecx, 80070057h; int
0x1800088fe  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008904  lea     rcx, [rbx+8]; pSid
0x180008908  call    cs:__imp_GetLengthSid
0x18000890e  lea     rdx, [rdi+8]; pDestinationSid
0x180008912  lea     r8, [rbx+8]; pSourceSid
0x180008916  mov     ecx, eax; nDestinationSidLength
0x180008918  call    cs:__imp_CopySid
0x18000891e  test    eax, eax
0x180008920  jnz     short loc_18000892F
0x180008922  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008927  mov     ecx, eax; int
0x180008929  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000892f  mov     rax, rdi
0x180008932  mov     rbx, [rsp+28h+arg_8]
0x180008937  add     rsp, 20h
0x18000893b  pop     rdi
0x18000893c  retn
```
