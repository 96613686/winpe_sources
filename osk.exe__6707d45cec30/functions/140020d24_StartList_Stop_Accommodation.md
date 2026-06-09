# StartList::Stop(Accommodation *)

- ea: `0x140020d24`
- end: `0x140020e05`
- name: `?Stop@StartList@@QEAAJPEAVAccommodation@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(StartList *__hidden this, struct Accommodation *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140020ebc`

## callees

- `0x14001c748`
- `0x14001c768`
- `0x14001e8b0`
- `0x14001f728`
- `0x14001fdc8`
- `0x14001ff08`
- `0x140020374`
- `0x140020d24`
- `0x140021e5c`
- `0x140025d42`

## import_xrefs

- `msvcrt!_wtoi` at `0x140020d98`
- `msvcrt!_wtoi` at `0x140020d98`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StartList::Stop(StartList *this, const wchar_t **a2)
{
  __int64 result; // rax
  signed int v5; // edi
  unsigned int v6; // eax
  __int64 v7; // r8
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // r11

  if ( !a2 )
    return 2147942487LL;
  if ( CATUtils::IsDesktopOOBEUserSessionActive() && !wcscmp_0(a2[5], L"SystemSetting") )
    StartList::Remove(this, (struct Accommodation *)a2);
  result = StartList::LoadSettings(this);
  v5 = result;
  if ( (int)result >= 0 )
  {
    if ( !wcscmp_0(a2[5], L"SystemSetting") )
    {
      v6 = _wtoi(a2[3]);
      if ( v6 < 0x16 )
        v5 = SystemSettings::TurnOff(a2, v6, v7, *((_DWORD *)this + 73));
    }
    v8 = (-(__int64)((unsigned int)CATUtils::IsInteractiveUser() != 0) & 0xFFFFFFFFFFFFFFD0uLL) + 96;
    if ( v5 >= 0 )
    {
      v9 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
             (char *)this + v8,
             *a2);
      if ( v9 )
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAt(
          v10,
          v9);
      StartList::SaveSessionKey(this);
    }
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x140020d24  mov     [rsp+arg_0], rbx
0x140020d29  mov     [rsp+arg_8], rsi
0x140020d2e  push    rdi
0x140020d2f  sub     rsp, 20h
0x140020d33  mov     rbx, rdx
0x140020d36  mov     rsi, rcx
0x140020d39  test    rdx, rdx
0x140020d3c  jnz     short loc_140020D48
0x140020d3e  mov     eax, 80070057h
0x140020d43  jmp     loc_140020DF5
0x140020d48  call    ?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBEUserSessionActive(void)
0x140020d4d  test    al, al
0x140020d4f  jz      short loc_140020D71
0x140020d51  lea     rdx, aSystemsetting; "SystemSetting"
0x140020d58  mov     rcx, [rbx+28h]; String1
0x140020d5c  call    wcscmp_0
0x140020d61  nop
0x140020d62  test    eax, eax
0x140020d64  jnz     short loc_140020D71
0x140020d66  mov     rdx, rbx; struct Accommodation *
0x140020d69  mov     rcx, rsi; this
0x140020d6c  call    ?Remove@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Remove(Accommodation *)
0x140020d71  mov     rcx, rsi; this
0x140020d74  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x140020d79  mov     edi, eax
0x140020d7b  test    eax, eax
0x140020d7d  js      short loc_140020DF5
0x140020d7f  lea     rdx, aSystemsetting; "SystemSetting"
0x140020d86  mov     rcx, [rbx+28h]; String1
0x140020d8a  call    wcscmp_0
0x140020d8f  nop
0x140020d90  test    eax, eax
0x140020d92  jnz     short loc_140020DB6
0x140020d94  mov     rcx, [rbx+18h]; String
0x140020d98  call    cs:__imp__wtoi
0x140020d9e  cmp     eax, 16h
0x140020da1  jnb     short loc_140020DB6
0x140020da3  mov     r9d, [rsi+124h]
0x140020daa  mov     edx, eax
0x140020dac  mov     rcx, rbx
0x140020daf  call    ?TurnOff@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z; SystemSettings::TurnOff(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)
0x140020db4  mov     edi, eax
0x140020db6  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x140020dbb  neg     eax
0x140020dbd  sbb     rcx, rcx
0x140020dc0  and     rcx, 0FFFFFFFFFFFFFFD0h
0x140020dc4  add     rcx, 60h ; '`'
0x140020dc8  test    edi, edi
0x140020dca  js      short loc_140020DF3
0x140020dcc  lea     r11, [rcx+rsi]
0x140020dd0  mov     rdx, [rbx]
0x140020dd3  mov     rcx, r11
0x140020dd6  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x140020ddb  test    rax, rax
0x140020dde  jz      short loc_140020DEB
0x140020de0  mov     rdx, rax
0x140020de3  mov     rcx, r11
0x140020de6  call    ?RemoveAt@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAt(__POSITION *)
0x140020deb  mov     rcx, rsi; this
0x140020dee  call    ?SaveSessionKey@StartList@@AEAAXXZ; StartList::SaveSessionKey(void)
0x140020df3  mov     eax, edi
0x140020df5  mov     rbx, [rsp+28h+arg_0]
0x140020dfa  mov     rsi, [rsp+28h+arg_8]
0x140020dff  add     rsp, 20h
0x140020e03  pop     rdi
0x140020e04  retn
```
