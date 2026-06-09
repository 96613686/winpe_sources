# CAdvancedPage::_EnsureProfileArea(void)

- ea: `0x180009b64`
- end: `0x180009d53`
- name: `?_EnsureProfileArea@CAdvancedPage@@AEAAXXZ`
- size: `495`
- prototype: `void __fastcall(CAdvancedPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800076f0`

## callees

- `0x180009b64`
- `0x18000a4e0`
- `0x180013600`

## import_xrefs

- `SHLWAPI!__imp_IsOS` at `0x180009c6f`
- `SHLWAPI!__imp_IsOS` at `0x180009cae`
- `SHLWAPI!__imp_IsOS` at `0x180009c6f`
- `SHLWAPI!__imp_IsOS` at `0x180009cae`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009baa`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009be3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009c45`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009c8c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009ce2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009cfe`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009d23`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009baa`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009be3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009c45`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009c8c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009ce2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009cfe`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009d23`
- `DUI70!StrToID` at `0x180009b9e`
- `DUI70!StrToID` at `0x180009bd7`
- `DUI70!StrToID` at `0x180009c39`
- `DUI70!StrToID` at `0x180009c80`
- `DUI70!StrToID` at `0x180009cd6`
- `DUI70!StrToID` at `0x180009cf2`
- `DUI70!StrToID` at `0x180009d17`
- `DUI70!StrToID` at `0x180009b9e`
- `DUI70!StrToID` at `0x180009bd7`
- `DUI70!StrToID` at `0x180009c39`
- `DUI70!StrToID` at `0x180009c80`
- `DUI70!StrToID` at `0x180009cd6`
- `DUI70!StrToID` at `0x180009cf2`
- `DUI70!StrToID` at `0x180009d17`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180009bf6`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180009c57`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180009c98`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180009cbe`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180009d0a`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180009bf6`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180009c57`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180009c98`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180009cbe`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180009d0a`

## string_xrefs

- `0x180009c14`: `IsInstalled`
- `0x180009c1b`: `Software\Microsoft\Active Setup\Installed Components\{6BF52A52-394A-11d3-B153-00C04F79FAA6}`

## pseudocode

```c
void __fastcall CAdvancedPage::_EnsureProfileArea(CAdvancedPage *this)
{
  __int64 v1; // rbp
  __int64 v2; // rdi
  int v4; // r14d
  DirectUI::Element *v5; // rbx
  unsigned __int16 v6; // ax
  DirectUI::Element *Descendent; // rsi
  __int64 i; // rbx
  __int64 v9; // rcx
  unsigned __int16 v10; // ax
  DirectUI::Element *v11; // rax
  unsigned __int16 v12; // ax
  DirectUI::Element *v13; // rax
  unsigned __int16 v14; // ax
  DirectUI::Element *v15; // rax
  unsigned __int16 v16; // ax
  DirectUI::Element *v17; // rbx
  unsigned __int16 v18; // ax
  DirectUI::Element *v19; // rax
  unsigned __int16 v20; // ax
  struct DirectUI::Expando *v21; // rax
  CAdvancedPage *v22; // rcx
  unsigned int v23; // [rsp+78h] [rbp+10h] BYREF

  v1 = 0;
  v2 = 0;
  do
  {
    v4 = HIDWORD(qword_18001C220[v2]);
    v5 = (DirectUI::Element *)*((_QWORD *)this + 2);
    v6 = StrToID((&off_18001C228)[v2]);
    Descendent = DirectUI::Element::FindDescendent(v5, v6);
    if ( Descendent )
    {
      for ( i = 0; i != 12; ++i )
      {
        v9 = 4 * i;
        if ( (v4 == 0) != algn_18001C278[32 * i] )
        {
          v10 = StrToID((&off_18001C270)[v9]);
          v11 = DirectUI::Element::FindDescendent(Descendent, v10);
          if ( v11 )
            DirectUI::Element::SetLayoutPos(v11, -3);
        }
      }
      if ( !v4
        && (v23 = 0,
            (int)SHRegGetDWORD(
                   (HKEY)(v9 * 8),
                   L"Software\\Microsoft\\Active Setup\\Installed Components\\{6BF52A52-394A-11d3-B153-00C04F79FAA6}",
                   L"IsInstalled",
                   &v23) >= 0)
        && v23 == 1
        || (v12 = StrToID(L"MediaSharingSection"),
            v13 = DirectUI::Element::FindDescendent(Descendent, v12),
            DirectUI::Element::SetLayoutPos(v13, -3),
            !v4) )
      {
        if ( IsOS(0x1Du) )
        {
          v14 = StrToID(L"FileSharingMinEncryptionSetting");
          v15 = DirectUI::Element::FindDescendent(Descendent, v14);
          DirectUI::Element::SetLayoutPos(v15, -3);
        }
      }
      if ( HIDWORD(qword_18001C220[v2]) == 3 && !IsOS(0x1Cu) )
        DirectUI::Element::SetLayoutPos(Descendent, -3);
      if ( HIDWORD(qword_18001C220[v2]) != 1 )
      {
        v16 = StrToID(L"NetworkDiscoverySetting");
        v17 = DirectUI::Element::FindDescendent(Descendent, v16);
        v18 = StrToID(L"Button0OptionArea");
        v19 = DirectUI::Element::FindDescendent(v17, v18);
        DirectUI::Element::SetLayoutPos(v19, -3);
      }
      v20 = StrToID(L"Expando");
      v21 = DirectUI::Element::FindDescendent(Descendent, v20);
      CAdvancedPage::_SetExpandoAccNameFromHeaderText(v22, v21);
    }
    ++v1;
    v2 += 2;
  }
  while ( v1 != 4 );
}

```

## disassembly

```asm
0x180009b64  push    rbx
0x180009b66  push    rbp
0x180009b67  push    rsi
0x180009b68  push    rdi
0x180009b69  push    r12
0x180009b6b  push    r13
0x180009b6d  push    r14
0x180009b6f  push    r15
0x180009b71  sub     rsp, 28h
0x180009b75  xor     ebp, ebp
0x180009b77  lea     r12, __ImageBase
0x180009b7e  xor     edi, edi
0x180009b80  mov     r13, rcx
0x180009b83  mov     r14d, [rdi+r12+1C224h]
0x180009b8b  test    r14d, r14d
0x180009b8e  mov     rcx, [rdi+r12+1C228h]
0x180009b96  mov     rbx, [r13+10h]
0x180009b9a  setz    r15b
0x180009b9e  call    cs:__imp_StrToID
0x180009ba4  movzx   edx, ax
0x180009ba7  mov     rcx, rbx
0x180009baa  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180009bb0  mov     rsi, rax
0x180009bb3  test    rax, rax
0x180009bb6  jz      loc_180009D31
0x180009bbc  xor     ebx, ebx
0x180009bbe  mov     rcx, rbx
0x180009bc1  shl     rcx, 5
0x180009bc5  cmp     r15b, [rcx+r12+1C278h]
0x180009bcd  jz      short loc_180009BFC
0x180009bcf  mov     rcx, [rcx+r12+1C270h]
0x180009bd7  call    cs:__imp_StrToID
0x180009bdd  movzx   edx, ax
0x180009be0  mov     rcx, rsi
0x180009be3  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180009be9  test    rax, rax
0x180009bec  jz      short loc_180009BFC
0x180009bee  mov     edx, 0FFFFFFFDh
0x180009bf3  mov     rcx, rax
0x180009bf6  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180009bfc  inc     rbx
0x180009bff  cmp     rbx, 0Ch
0x180009c03  jnz     short loc_180009BBE
0x180009c05  test    r14d, r14d
0x180009c08  jnz     short loc_180009C32
0x180009c0a  lea     r9, [rsp+68h+arg_8]; unsigned int *
0x180009c0f  mov     [rsp+68h+arg_8], r14d
0x180009c14  lea     r8, aIsinstalled; "IsInstalled"
0x180009c1b  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Active Setup\\Inst"...
0x180009c22  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180009c27  test    eax, eax
0x180009c29  js      short loc_180009C32
0x180009c2b  cmp     [rsp+68h+arg_8], 1
0x180009c30  jz      short loc_180009C64
0x180009c32  lea     rcx, aMediasharingse; "MediaSharingSection"
0x180009c39  call    cs:__imp_StrToID
0x180009c3f  movzx   edx, ax
0x180009c42  mov     rcx, rsi
0x180009c45  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180009c4b  mov     r15d, 0FFFFFFFDh
0x180009c51  mov     rcx, rax
0x180009c54  mov     edx, r15d
0x180009c57  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180009c5d  test    r14d, r14d
0x180009c60  jnz     short loc_180009C9E
0x180009c62  jmp     short loc_180009C6A
0x180009c64  mov     r15d, 0FFFFFFFDh
0x180009c6a  mov     ecx, 1Dh; dwOS
0x180009c6f  call    cs:__imp_IsOS
0x180009c75  test    eax, eax
0x180009c77  jz      short loc_180009C9E
0x180009c79  lea     rcx, aFilesharingmin; "FileSharingMinEncryptionSetting"
0x180009c80  call    cs:__imp_StrToID
0x180009c86  movzx   edx, ax
0x180009c89  mov     rcx, rsi
0x180009c8c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180009c92  mov     rcx, rax
0x180009c95  mov     edx, r15d
0x180009c98  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180009c9e  cmp     dword ptr [rdi+r12+1C224h], 3
0x180009ca7  jnz     short loc_180009CC4
0x180009ca9  mov     ecx, 1Ch; dwOS
0x180009cae  call    cs:__imp_IsOS
0x180009cb4  test    eax, eax
0x180009cb6  jnz     short loc_180009CC4
0x180009cb8  mov     edx, r15d
0x180009cbb  mov     rcx, rsi
0x180009cbe  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180009cc4  cmp     dword ptr [rdi+r12+1C224h], 1
0x180009ccd  jz      short loc_180009D10
0x180009ccf  lea     rcx, String2; "NetworkDiscoverySetting"
0x180009cd6  call    cs:__imp_StrToID
0x180009cdc  movzx   edx, ax
0x180009cdf  mov     rcx, rsi
0x180009ce2  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180009ce8  lea     rcx, aButton0optiona; "Button0OptionArea"
0x180009cef  mov     rbx, rax
0x180009cf2  call    cs:__imp_StrToID
0x180009cf8  movzx   edx, ax
0x180009cfb  mov     rcx, rbx
0x180009cfe  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180009d04  mov     rcx, rax
0x180009d07  mov     edx, r15d
0x180009d0a  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180009d10  lea     rcx, aExpando; "Expando"
0x180009d17  call    cs:__imp_StrToID
0x180009d1d  movzx   edx, ax
0x180009d20  mov     rcx, rsi
0x180009d23  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180009d29  mov     rdx, rax; struct DirectUI::Expando *
0x180009d2c  call    ?_SetExpandoAccNameFromHeaderText@CAdvancedPage@@AEAAXPEAVExpando@DirectUI@@@Z; CAdvancedPage::_SetExpandoAccNameFromHeaderText(DirectUI::Expando *)
0x180009d31  inc     rbp
0x180009d34  add     rdi, 10h
0x180009d38  cmp     rbp, 4
0x180009d3c  jnz     loc_180009B83
0x180009d42  add     rsp, 28h
0x180009d46  pop     r15
0x180009d48  pop     r14
0x180009d4a  pop     r13
0x180009d4c  pop     r12
0x180009d4e  pop     rdi
0x180009d4f  pop     rsi
0x180009d50  pop     rbp
0x180009d51  pop     rbx
0x180009d52  retn
```
