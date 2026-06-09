# CFontContextMenu::InvokeCommand(_CMINVOKECOMMANDINFO *)

- ea: `0x180010ff0`
- end: `0x1800110a1`
- name: `?InvokeCommand@CFontContextMenu@@UEAAJPEAU_CMINVOKECOMMANDINFO@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(CFontContextMenu *__hidden this, struct _CMINVOKECOMMANDINFO *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180010ff0`
- `0x180011384`

## import_xrefs

- `KERNEL32!lstrcmpiA` at `0x180011013`
- `KERNEL32!lstrcmpiA` at `0x180011028`
- `KERNEL32!lstrcmpiA` at `0x18001103d`
- `KERNEL32!lstrcmpiA` at `0x180011013`
- `KERNEL32!lstrcmpiA` at `0x180011028`
- `KERNEL32!lstrcmpiA` at `0x18001103d`

## string_xrefs

- `0x180011036`: `installLink`
- `0x180011021`: `installAllUsers`
- `0x18001100c`: `install`

## pseudocode

```c
__int64 __fastcall CFontContextMenu::InvokeCommand(struct IDataObject **this, struct _CMINVOKECOMMANDINFO *a2)
{
  int lpVerb_low; // eax
  unsigned int v5; // ecx
  int v6; // eax
  int v7; // r9d
  unsigned int v8; // r8d

  if ( WORD1(a2->lpVerb) )
  {
    if ( !lstrcmpiA(a2->lpVerb, "install") )
    {
LABEL_12:
      v7 = 0;
      v8 = 1;
      return (unsigned int)CFontContextMenu::_InstallFonts(this - 1, a2->hwnd, v8, v7);
    }
    if ( !lstrcmpiA(a2->lpVerb, "installAllUsers") )
    {
LABEL_11:
      v7 = 1;
      v8 = 1;
      return (unsigned int)CFontContextMenu::_InstallFonts(this - 1, a2->hwnd, v8, v7);
    }
    if ( !lstrcmpiA(a2->lpVerb, "installLink") )
    {
LABEL_10:
      v7 = 1;
      v8 = 0;
      return (unsigned int)CFontContextMenu::_InstallFonts(this - 1, a2->hwnd, v8, v7);
    }
    lpVerb_low = -1;
    v5 = -2147024809;
  }
  else
  {
    lpVerb_low = LOWORD(a2->lpVerb);
    v5 = -2147467259;
  }
  if ( !lpVerb_low )
    goto LABEL_12;
  v6 = lpVerb_low - 1;
  if ( !v6 )
    goto LABEL_11;
  if ( v6 == 1 )
    goto LABEL_10;
  return v5;
}

```

## disassembly

```asm
0x180010ff0  mov     [rsp+arg_0], rbx
0x180010ff5  push    rdi
0x180010ff6  sub     rsp, 20h
0x180010ffa  xor     eax, eax
0x180010ffc  mov     rbx, rdx
0x180010fff  mov     rdi, rcx
0x180011002  cmp     ax, [rdx+12h]
0x180011006  jz      short loc_180011051
0x180011008  mov     rcx, [rbx+10h]; lpString1
0x18001100c  lea     rdx, c_szShellVerb_InstallA; "install"
0x180011013  call    cs:__imp_lstrcmpiA
0x180011019  test    eax, eax
0x18001101b  jz      short loc_18001107E
0x18001101d  mov     rcx, [rbx+10h]; lpString1
0x180011021  lea     rdx, c_szShellVerb_InstallAllUsersA; "installAllUsers"
0x180011028  call    cs:__imp_lstrcmpiA
0x18001102e  test    eax, eax
0x180011030  jz      short loc_180011073
0x180011032  mov     rcx, [rbx+10h]; lpString1
0x180011036  lea     rdx, c_szShellVerb_InstallLinkA; "installLink"
0x18001103d  call    cs:__imp_lstrcmpiA
0x180011043  test    eax, eax
0x180011045  jz      short loc_180011068
0x180011047  or      eax, 0FFFFFFFFh
0x18001104a  mov     ecx, 80070057h
0x18001104f  jmp     short loc_18001105A
0x180011051  movzx   eax, word ptr [rdx+10h]
0x180011055  mov     ecx, 80004005h
0x18001105a  test    eax, eax
0x18001105c  jz      short loc_18001107E
0x18001105e  sub     eax, 1
0x180011061  jz      short loc_180011073
0x180011063  cmp     eax, 1
0x180011066  jnz     short loc_180011094
0x180011068  mov     r9d, 1
0x18001106e  xor     r8d, r8d
0x180011071  jmp     short loc_180011085
0x180011073  mov     r9d, 1
0x180011079  mov     r8d, r9d
0x18001107c  jmp     short loc_180011085
0x18001107e  xor     r9d, r9d; int
0x180011081  lea     r8d, [r9+1]; int
0x180011085  mov     rdx, [rbx+8]; HWND
0x180011089  lea     rcx, [rdi-8]; this
0x18001108d  call    ?_InstallFonts@CFontContextMenu@@AEAAJPEAUHWND__@@HH@Z; CFontContextMenu::_InstallFonts(HWND__ *,int,int)
0x180011092  mov     ecx, eax
0x180011094  mov     rbx, [rsp+28h+arg_0]
0x180011099  mov     eax, ecx
0x18001109b  add     rsp, 20h
0x18001109f  pop     rdi
0x1800110a0  retn
```
