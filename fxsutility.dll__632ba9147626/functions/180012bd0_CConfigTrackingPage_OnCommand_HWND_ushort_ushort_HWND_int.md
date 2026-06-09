# CConfigTrackingPage::OnCommand(HWND__ *,ushort,ushort,HWND__ *,int &)

- ea: `0x180012bd0`
- end: `0x180012ccf`
- name: `?OnCommand@CConfigTrackingPage@@UEAAKPEAUHWND__@@GG0AEAH@Z`
- size: `255`
- prototype: `unsigned int(CConfigTrackingPage *__hidden this, HWND, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005eac`
- `0x180012bd0`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012ca5`
- `KERNEL32!GetLastError` at `0x180012ca5`
- `USER32!DialogBoxParamW` at `0x180012c9a`
- `USER32!DialogBoxParamW` at `0x180012c9a`

## pseudocode

```c
__int64 __fastcall CConfigTrackingPage::OnCommand(
        HINSTANCE *this,
        HWND a2,
        __int16 a3,
        unsigned __int16 a4,
        HWND a5,
        int *a6)
{
  int v6; // ebx
  HINSTANCE v10; // rcx
  LPARAM dwInitParam[3]; // [rsp+30h] [rbp-58h] BYREF
  int v13; // [rsp+48h] [rbp-40h]
  char *v14; // [rsp+50h] [rbp-38h]

  v6 = a4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids);
  }
  *a6 = 1;
  if ( v6 == 4564 || v6 == 4565 || v6 == 4566 || v6 == 4569 || v6 == 4570 )
  {
    if ( !a3 )
      (*((void (__fastcall **)(HINSTANCE *, HWND))*this + 10))(this, a2);
  }
  else if ( v6 == 4571 )
  {
    if ( !a3 )
    {
      v10 = this[1];
      dwInitParam[0] = (LPARAM)&CSoundSettingsDialog::`vftable';
      dwInitParam[1] = (LPARAM)v10;
      v14 = (char *)(this + 4);
      dwInitParam[2] = (LPARAM)a2;
      v13 = 4604;
      if ( DialogBoxParamW(v10, (LPCWSTR)0x11FC, a2, CDialogUI::DlgProc, (LPARAM)dwInitParam) <= 0 )
        GetLastError();
    }
  }
  else
  {
    *a6 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180012bd0  push    rbx
0x180012bd2  push    rbp
0x180012bd3  push    rsi
0x180012bd4  push    rdi
0x180012bd5  sub     rsp, 68h
0x180012bd9  movzx   ebx, r9w
0x180012bdd  movzx   edi, r8w
0x180012be1  mov     rbp, rdx
0x180012be4  mov     rsi, rcx
0x180012be7  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bee  lea     rax, WPP_GLOBAL_Control
0x180012bf5  cmp     rcx, rax
0x180012bf8  jz      short loc_180012C1E
0x180012bfa  test    dword ptr [rcx+1Ch], 100h
0x180012c01  jz      short loc_180012C1E
0x180012c03  cmp     byte ptr [rcx+19h], 5
0x180012c07  jb      short loc_180012C1E
0x180012c09  mov     rcx, [rcx+10h]
0x180012c0d  lea     r8, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids
0x180012c14  mov     edx, 0Dh
0x180012c19  call    WPP_SF_
0x180012c1e  mov     rdx, [rsp+88h+arg_28]
0x180012c26  mov     ecx, ebx
0x180012c28  mov     dword ptr [rdx], 1
0x180012c2e  sub     ecx, 11D4h
0x180012c34  jz      short loc_180012CAD
0x180012c36  sub     ecx, 1
0x180012c39  jz      short loc_180012CAD
0x180012c3b  sub     ecx, 1
0x180012c3e  jz      short loc_180012CAD
0x180012c40  sub     ecx, 3
0x180012c43  jz      short loc_180012CAD
0x180012c45  sub     ecx, 1
0x180012c48  jz      short loc_180012CAD
0x180012c4a  cmp     ecx, 1
0x180012c4d  jz      short loc_180012C55
0x180012c4f  xor     ebx, ebx
0x180012c51  mov     [rdx], ebx
0x180012c53  jmp     short loc_180012CC4
0x180012c55  test    di, di
0x180012c58  jnz     short loc_180012CC4
0x180012c5a  mov     rcx, [rsi+8]; hInstance
0x180012c5e  lea     rax, ??_7CSoundSettingsDialog@@6B@; const CSoundSettingsDialog::`vftable'
0x180012c65  mov     [rsp+88h+var_58], rax
0x180012c6a  lea     r9, ?DlgProc@CDialogUI@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180012c71  lea     rax, [rsi+20h]
0x180012c75  mov     [rsp+88h+var_50], rcx
0x180012c7a  mov     [rsp+88h+var_38], rax
0x180012c7f  mov     edx, 11FCh; lpTemplateName
0x180012c84  lea     rax, [rsp+88h+var_58]
0x180012c89  mov     [rsp+88h+var_48], rbp
0x180012c8e  mov     r8, rbp; hWndParent
0x180012c91  mov     [rsp+88h+dwInitParam], rax; dwInitParam
0x180012c96  mov     [rsp+88h+var_40], edx
0x180012c9a  call    cs:__imp_DialogBoxParamW
0x180012ca0  test    rax, rax
0x180012ca3  jg      short loc_180012CC4
0x180012ca5  call    cs:__imp_GetLastError
0x180012cab  jmp     short loc_180012CC4
0x180012cad  test    di, di
0x180012cb0  jnz     short loc_180012CC4
0x180012cb2  mov     rax, [rsi]
0x180012cb5  mov     rdx, rbp
0x180012cb8  mov     rcx, rsi
0x180012cbb  mov     rax, [rax+50h]
0x180012cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cc4  xor     eax, eax
0x180012cc6  add     rsp, 68h
0x180012cca  pop     rdi
0x180012ccb  pop     rsi
0x180012ccc  pop     rbp
0x180012ccd  pop     rbx
0x180012cce  retn
```
