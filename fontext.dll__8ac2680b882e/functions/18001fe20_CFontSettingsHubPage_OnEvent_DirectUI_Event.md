# CFontSettingsHubPage::OnEvent(DirectUI::Event *)

- ea: `0x18001fe20`
- end: `0x18001ff72`
- name: `?OnEvent@CFontSettingsHubPage@@UEAAXPEAUEvent@DirectUI@@@Z`
- size: `338`
- prototype: `void __fastcall(CFontSettingsHubPage *__hidden this, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18001fe20`
- `0x18001ff78`
- `0x180020030`
- `0x180020060`
- `0x1800200f4`
- `0x18002015c`
- `0x180032010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryServiceForWebBrowserApp` at `0x18001ff1a`
- `SHLWAPI!__imp_IUnknown_QueryServiceForWebBrowserApp` at `0x18001ff1a`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18001fe46`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18001fe46`
- `DUI70!StrToID` at `0x18001fe6e`
- `DUI70!StrToID` at `0x18001fe8d`
- `DUI70!StrToID` at `0x18001fec3`
- `DUI70!StrToID` at `0x18001fee6`
- `DUI70!StrToID` at `0x18001fe6e`
- `DUI70!StrToID` at `0x18001fe8d`
- `DUI70!StrToID` at `0x18001fec3`
- `DUI70!StrToID` at `0x18001fee6`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18001fe54`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18001fe54`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001fe9b`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001fed1`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001fe9b`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001fed1`

## string_xrefs

- `0x18001fe86`: `InstallAsLinkCheck`

## pseudocode

```c
void __fastcall CFontSettingsHubPage::OnEvent(CFontSettingsHubPage *this, struct DirectUI::Event *a2)
{
  bool v2; // zf
  unsigned __int16 ID; // si
  __int64 v6; // rcx
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v2 = *((_DWORD *)a2 + 5) == 1;
  *((_BYTE *)a2 + 16) = 0;
  if ( v2 )
  {
    ID = DirectUI::Element::GetID(*(DirectUI::Element **)a2);
    if ( *(_QWORD *)DirectUI::Button::Click(&v7) == *((_QWORD *)a2 + 1) )
    {
      if ( (unsigned __int16)StrToID(L"SelectFontActivationClear") == ID )
      {
        CFontSettingsHubPage::_DoRestoreDefaultsClick(this);
      }
      else
      {
        if ( (unsigned __int16)StrToID(L"InstallAsLinkCheck") == ID )
        {
          *((_DWORD *)this + 9) = DirectUI::Element::GetSelected(*(DirectUI::Element **)a2);
        }
        else
        {
          if ( (unsigned __int16)StrToID(L"HideFontsCheckbox") != ID )
          {
            if ( (unsigned __int16)StrToID(L"OK") != ID )
              return;
            CFontSettingsHubPage::_SetActivationState(this);
            CFontSettingsHubPage::_SetInstallAsLinkState((const BYTE *)this);
            v6 = *((_QWORD *)this + 3);
            v7 = 0;
            if ( (int)IUnknown_QueryServiceForWebBrowserApp(v6, &GUID_0002df05_0000_0000_c000_000000000046, &v7) >= 0 )
            {
              if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v7 + 56LL))(v7) < 0 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 256LL))(v7);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
            }
            goto LABEL_15;
          }
          *((_DWORD *)this + 8) = DirectUI::Element::GetSelected(*(DirectUI::Element **)a2);
        }
        CFontSettingsHubPage::_EnableOkButton(this);
        CFontSettingsHubPage::_EnableRestoreButton(this);
      }
LABEL_15:
      *((_BYTE *)a2 + 16) = 1;
    }
  }
}

```

## disassembly

```asm
0x18001fe20  mov     [rsp+arg_0], rbx
0x18001fe25  mov     [rsp+arg_10], rsi
0x18001fe2a  push    rdi
0x18001fe2b  sub     rsp, 20h
0x18001fe2f  cmp     dword ptr [rdx+14h], 1
0x18001fe33  mov     rbx, rdx
0x18001fe36  mov     rdi, rcx
0x18001fe39  mov     byte ptr [rdx+10h], 0
0x18001fe3d  jnz     loc_18001FF62
0x18001fe43  mov     rcx, [rdx]
0x18001fe46  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x18001fe4c  lea     rcx, [rsp+28h+arg_8]
0x18001fe51  movzx   esi, ax
0x18001fe54  call    cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x18001fe5a  mov     rcx, [rax]
0x18001fe5d  cmp     rcx, [rbx+8]
0x18001fe61  jnz     loc_18001FF62
0x18001fe67  lea     rcx, aSelectfontacti; "SelectFontActivationClear"
0x18001fe6e  call    cs:__imp_StrToID
0x18001fe74  cmp     ax, si
0x18001fe77  jnz     short loc_18001FE86
0x18001fe79  mov     rcx, rdi; this
0x18001fe7c  call    ?_DoRestoreDefaultsClick@CFontSettingsHubPage@@AEAAXXZ; CFontSettingsHubPage::_DoRestoreDefaultsClick(void)
0x18001fe81  jmp     loc_18001FF5E
0x18001fe86  lea     rcx, aInstallaslinkc; "InstallAsLinkCheck"
0x18001fe8d  call    cs:__imp_StrToID
0x18001fe93  cmp     ax, si
0x18001fe96  jnz     short loc_18001FEBC
0x18001fe98  mov     rcx, [rbx]
0x18001fe9b  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x18001fea1  movzx   eax, al
0x18001fea4  mov     [rdi+24h], eax
0x18001fea7  mov     rcx, rdi; this
0x18001feaa  call    ?_EnableOkButton@CFontSettingsHubPage@@AEAAXXZ; CFontSettingsHubPage::_EnableOkButton(void)
0x18001feaf  mov     rcx, rdi; this
0x18001feb2  call    ?_EnableRestoreButton@CFontSettingsHubPage@@AEAAXXZ; CFontSettingsHubPage::_EnableRestoreButton(void)
0x18001feb7  jmp     loc_18001FF5E
0x18001febc  lea     rcx, aHidefontscheck; "HideFontsCheckbox"
0x18001fec3  call    cs:__imp_StrToID
0x18001fec9  cmp     ax, si
0x18001fecc  jnz     short loc_18001FEDF
0x18001fece  mov     rcx, [rbx]
0x18001fed1  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x18001fed7  movzx   eax, al
0x18001feda  mov     [rdi+20h], eax
0x18001fedd  jmp     short loc_18001FEA7
0x18001fedf  lea     rcx, aOk; "OK"
0x18001fee6  call    cs:__imp_StrToID
0x18001feec  cmp     ax, si
0x18001feef  jnz     short loc_18001FF62
0x18001fef1  mov     rcx, rdi; this
0x18001fef4  call    ?_SetActivationState@CFontSettingsHubPage@@AEAAXXZ; CFontSettingsHubPage::_SetActivationState(void)
0x18001fef9  mov     rcx, rdi; this
0x18001fefc  call    ?_SetInstallAsLinkState@CFontSettingsHubPage@@AEAAXXZ; CFontSettingsHubPage::_SetInstallAsLinkState(void)
0x18001ff01  mov     rcx, [rdi+18h]
0x18001ff05  lea     r8, [rsp+28h+arg_8]
0x18001ff0a  lea     rdx, _GUID_0002df05_0000_0000_c000_000000000046
0x18001ff11  mov     [rsp+28h+arg_8], 0
0x18001ff1a  call    cs:__imp_IUnknown_QueryServiceForWebBrowserApp
0x18001ff20  test    eax, eax
0x18001ff22  js      short loc_18001FF5E
0x18001ff24  mov     rcx, [rsp+28h+arg_8]
0x18001ff29  mov     rax, [rcx]
0x18001ff2c  mov     rax, [rax+38h]
0x18001ff30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff35  test    eax, eax
0x18001ff37  jns     short loc_18001FF4D
0x18001ff39  mov     rcx, [rsp+28h+arg_8]
0x18001ff3e  mov     rax, [rcx]
0x18001ff41  mov     rax, [rax+100h]
0x18001ff48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff4d  mov     rcx, [rsp+28h+arg_8]
0x18001ff52  mov     rax, [rcx]
0x18001ff55  mov     rax, [rax+10h]
0x18001ff59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff5e  mov     byte ptr [rbx+10h], 1
0x18001ff62  mov     rbx, [rsp+28h+arg_0]
0x18001ff67  mov     rsi, [rsp+28h+arg_10]
0x18001ff6c  add     rsp, 20h
0x18001ff70  pop     rdi
0x18001ff71  retn
```
