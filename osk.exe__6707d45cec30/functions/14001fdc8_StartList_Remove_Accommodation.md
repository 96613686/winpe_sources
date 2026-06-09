# StartList::Remove(Accommodation *)

- ea: `0x14001fdc8`
- end: `0x14001fe94`
- name: `?Remove@StartList@@QEAAJPEAVAccommodation@@@Z`
- size: `204`
- prototype: `__int64 __fastcall(StartList *__hidden this, struct Accommodation *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140020d24`

## callees

- `0x1400045c8`
- `0x140009524`
- `0x14001e8b0`
- `0x14001f728`
- `0x14001fdc8`
- `0x14001ff08`
- `0x1400205a8`
- `0x140025d42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StartList::Remove(StartList *this, const wchar_t **a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rdx
  StartList *v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rsi
  __int64 v11; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  result = StartList::LoadSettings(this);
  if ( (int)result >= 0 )
  {
    if ( !wcscmp_0(a2[5], L"SystemSetting") )
    {
      v9 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                       &v11,
                       a2);
      v10 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
              (char *)this + 144,
              *v9);
      ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
      if ( v10 )
      {
        v7 = v10;
        v8 = (StartList *)((char *)this + 144);
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
      if ( v6 )
      {
        v7 = v6;
        v8 = this;
LABEL_9:
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAt(
          v8,
          v7);
      }
    }
    return StartList::SaveSettings(this);
  }
  return result;
}

```

## disassembly

```asm
0x14001fdc8  mov     [rsp+arg_0], rbx
0x14001fdcd  mov     [rsp+arg_10], rsi
0x14001fdd2  push    rdi
0x14001fdd3  sub     rsp, 20h
0x14001fdd7  mov     rdi, rdx
0x14001fdda  mov     rbx, rcx
0x14001fddd  test    rdx, rdx
0x14001fde0  jnz     short loc_14001FDEC
0x14001fde2  mov     eax, 80070057h
0x14001fde7  jmp     loc_14001FE84
0x14001fdec  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x14001fdf1  test    eax, eax
0x14001fdf3  js      loc_14001FE84
0x14001fdf9  lea     rdx, aSystemsetting; "SystemSetting"
0x14001fe00  mov     rcx, [rdi+28h]; String1
0x14001fe04  call    wcscmp_0
0x14001fe09  nop
0x14001fe0a  mov     rdx, rdi
0x14001fe0d  lea     rcx, [rsp+28h+arg_8]
0x14001fe12  test    eax, eax
0x14001fe14  jz      short loc_14001FE44
0x14001fe16  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001fe1b  mov     rdx, [rax]
0x14001fe1e  mov     rcx, rbx
0x14001fe21  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x14001fe26  mov     rdi, rax
0x14001fe29  mov     rcx, [rsp+28h+arg_8]
0x14001fe2e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001fe32  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001fe37  test    rdi, rdi
0x14001fe3a  jz      short loc_14001FE7C
0x14001fe3c  mov     rdx, rdi
0x14001fe3f  mov     rcx, rbx
0x14001fe42  jmp     short loc_14001FE77
0x14001fe44  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001fe49  lea     rdi, [rbx+90h]
0x14001fe50  mov     rdx, [rax]
0x14001fe53  mov     rcx, rdi
0x14001fe56  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x14001fe5b  mov     rsi, rax
0x14001fe5e  mov     rcx, [rsp+28h+arg_8]
0x14001fe63  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001fe67  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001fe6c  test    rsi, rsi
0x14001fe6f  jz      short loc_14001FE7C
0x14001fe71  mov     rdx, rsi
0x14001fe74  mov     rcx, rdi
0x14001fe77  call    ?RemoveAt@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAt(__POSITION *)
0x14001fe7c  mov     rcx, rbx; this
0x14001fe7f  call    ?SaveSettings@StartList@@AEAAJXZ; StartList::SaveSettings(void)
0x14001fe84  mov     rbx, [rsp+28h+arg_0]
0x14001fe89  mov     rsi, [rsp+28h+arg_10]
0x14001fe8e  add     rsp, 20h
0x14001fe92  pop     rdi
0x14001fe93  retn
```
