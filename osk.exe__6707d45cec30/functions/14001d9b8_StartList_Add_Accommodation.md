# StartList::Add(Accommodation *)

- ea: `0x14001d9b8`
- end: `0x14001daa8`
- name: `?Add@StartList@@QEAAJPEAVAccommodation@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(StartList *__hidden this, struct Accommodation *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140020938`

## callees

- `0x1400045c8`
- `0x140009524`
- `0x14001d9b8`
- `0x14001dab0`
- `0x14001e8b0`
- `0x14001f728`
- `0x1400205a8`
- `0x140025d42`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartList::Add(StartList *this, const wchar_t **a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  __int64 v6; // rbx
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  __int64 v9; // rbx
  _QWORD *v10; // rax
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  result = StartList::LoadSettings(this);
  if ( (int)result >= 0 )
  {
    if ( !wcscmp_0(a2[5], L"SystemSetting") )
    {
      v8 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                       &v11,
                       a2);
      v9 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
             (char *)this + 144,
             *v8);
      ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
      if ( !v9 )
      {
        v10 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                          &v11,
                          a2);
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          (char *)this + 144,
          *v10);
        goto LABEL_9;
      }
    }
    else
    {
      v5 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                       &v11,
                       a2);
      v6 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
             this,
             *v5);
      ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
      if ( !v6 )
      {
        v7 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                         &v11,
                         a2);
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          this,
          *v7);
LABEL_9:
        ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
      }
    }
    return StartList::SaveSettings(this);
  }
  return result;
}

```

## disassembly

```asm
0x14001d9b8  push    rbx
0x14001d9ba  push    rbp
0x14001d9bb  push    rsi
0x14001d9bc  push    rdi
0x14001d9bd  sub     rsp, 28h
0x14001d9c1  mov     rdi, rdx
0x14001d9c4  mov     rsi, rcx
0x14001d9c7  test    rdx, rdx
0x14001d9ca  jnz     short loc_14001D9D6
0x14001d9cc  mov     eax, 80070057h
0x14001d9d1  jmp     loc_14001DA9F
0x14001d9d6  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x14001d9db  test    eax, eax
0x14001d9dd  js      loc_14001DA9F
0x14001d9e3  lea     rdx, aSystemsetting; "SystemSetting"
0x14001d9ea  mov     rcx, [rdi+28h]; String1
0x14001d9ee  call    wcscmp_0
0x14001d9f3  nop
0x14001d9f4  mov     rdx, rdi
0x14001d9f7  lea     rcx, [rsp+48h+arg_8]
0x14001d9fc  test    eax, eax
0x14001d9fe  jz      short loc_14001DA42
0x14001da00  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001da05  mov     rdx, [rax]
0x14001da08  mov     rcx, rsi
0x14001da0b  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x14001da10  mov     rbx, rax
0x14001da13  mov     rcx, [rsp+48h+arg_8]
0x14001da18  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001da1c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001da21  test    rbx, rbx
0x14001da24  jnz     short loc_14001DA97
0x14001da26  mov     rdx, rdi
0x14001da29  lea     rcx, [rsp+48h+arg_8]
0x14001da2e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001da33  nop
0x14001da34  mov     rdx, [rax]
0x14001da37  mov     rcx, rsi
0x14001da3a  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x14001da3f  nop
0x14001da40  jmp     short loc_14001DA89
0x14001da42  lea     rbp, [rsi+90h]
0x14001da49  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001da4e  mov     rdx, [rax]
0x14001da51  mov     rcx, rbp
0x14001da54  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x14001da59  mov     rbx, rax
0x14001da5c  mov     rcx, [rsp+48h+arg_8]
0x14001da61  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001da65  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001da6a  test    rbx, rbx
0x14001da6d  jnz     short loc_14001DA97
0x14001da6f  mov     rdx, rdi
0x14001da72  lea     rcx, [rsp+48h+arg_8]
0x14001da77  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001da7c  nop
0x14001da7d  mov     rdx, [rax]
0x14001da80  mov     rcx, rbp
0x14001da83  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x14001da88  nop
0x14001da89  mov     rcx, [rsp+48h+arg_8]
0x14001da8e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001da92  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001da97  mov     rcx, rsi; this
0x14001da9a  call    ?SaveSettings@StartList@@AEAAJXZ; StartList::SaveSettings(void)
0x14001da9f  add     rsp, 28h
0x14001daa3  pop     rdi
0x14001daa4  pop     rsi
0x14001daa5  pop     rbp
0x14001daa6  pop     rbx
0x14001daa7  retn
```
