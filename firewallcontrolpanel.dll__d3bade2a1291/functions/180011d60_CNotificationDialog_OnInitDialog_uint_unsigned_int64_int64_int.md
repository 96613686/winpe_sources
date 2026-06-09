# CNotificationDialog::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x180011d60`
- end: `0x180011e8b`
- name: `?OnInitDialog@CNotificationDialog@@AEAA_JI_K_JAEAH@Z`
- size: `299`
- prototype: `__int64 __usercall@<rax>(CNotificationDialog *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180012270`

## callees

- `0x180011278`
- `0x180011328`
- `0x180011678`
- `0x180011710`
- `0x180011a00`
- `0x180011c0c`
- `0x180011d60`
- `0x180012704`
- `0x1800127ac`
- `0x1800128b8`
- `0x1800129ac`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180011e78`
- `ntdll!EtwEventWrite` at `0x180011e78`
- `USER32!SetWindowPos` at `0x180011e59`
- `USER32!SetWindowPos` at `0x180011e59`
- `USER32!SetActiveWindow` at `0x180011e23`
- `USER32!SetActiveWindow` at `0x180011e23`
- `USER32!SetForegroundWindow` at `0x180011e2d`
- `USER32!SetForegroundWindow` at `0x180011e2d`

## pseudocode

```c
__int64 __fastcall CNotificationDialog::OnInitDialog(
        CNotificationDialog *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int *a5)
{
  bool v5; // zf

  v5 = *((_DWORD *)this + 422) == 0;
  *a5 = 0;
  if ( v5 )
    CNotificationDialog::GetEffectiveProfiles(this);
  CNotificationDialog::SetDialogIcon(this);
  CNotificationDialog::SetCmdLinkCaptionText(this);
  CNotificationDialog::SetApplicationDetails(this);
  CNotificationDialog::SetCaptionText(this);
  if ( !CTooltip::Init((CNotificationDialog *)((char *)this + 1720), *((HWND *)this + 1)) )
  {
    CTooltip::AddTool((CNotificationDialog *)((char *)this + 1720), 0x644u, (const unsigned __int16 *)this + 52);
    CTooltip::AddTool((CNotificationDialog *)((char *)this + 1720), 0x642u, (const unsigned __int16 *)this + 312);
    CTooltip::AddTool((CNotificationDialog *)((char *)this + 1720), 0x643u, (const unsigned __int16 *)this + 572);
  }
  if ( *((_DWORD *)this + 422) )
    CNotificationDialog::MakeReadOnlyUI(this);
  else
    CNotificationDialog::MakeMultiProfileUI(this);
  CNotificationDialog::CenterWindow(this);
  if ( !*((_DWORD *)this + 421) )
  {
    SetActiveWindow(*((HWND *)this + 1));
    SetForegroundWindow(*((HWND *)this + 1));
    SetWindowPos(*((HWND *)this + 1), HWND_MESSAGE|0x2LL, 0, 0, 0, 0, 0x43u);
  }
  if ( g_Provider )
    EtwEventWrite(g_Provider, QUInitialize_End, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x180011d60  mov     [rsp+arg_0], rbx
0x180011d65  push    rdi
0x180011d66  sub     rsp, 40h
0x180011d6a  cmp     dword ptr [rcx+698h], 0
0x180011d71  mov     rbx, rcx
0x180011d74  mov     rax, [rsp+48h+arg_20]
0x180011d79  mov     dword ptr [rax], 0
0x180011d7f  jnz     short loc_180011D86
0x180011d81  call    ?GetEffectiveProfiles@CNotificationDialog@@AEAAXXZ; CNotificationDialog::GetEffectiveProfiles(void)
0x180011d86  mov     rcx, rbx; this
0x180011d89  call    ?SetDialogIcon@CNotificationDialog@@AEAAXXZ; CNotificationDialog::SetDialogIcon(void)
0x180011d8e  mov     rcx, rbx; this
0x180011d91  call    ?SetCmdLinkCaptionText@CNotificationDialog@@AEAAXXZ; CNotificationDialog::SetCmdLinkCaptionText(void)
0x180011d96  mov     rcx, rbx; this
0x180011d99  call    ?SetApplicationDetails@CNotificationDialog@@AEAAXXZ; CNotificationDialog::SetApplicationDetails(void)
0x180011d9e  mov     rcx, rbx; this
0x180011da1  call    ?SetCaptionText@CNotificationDialog@@AEAAXXZ; CNotificationDialog::SetCaptionText(void)
0x180011da6  mov     rdx, [rbx+8]; HWND
0x180011daa  lea     rdi, [rbx+6B8h]
0x180011db1  mov     rcx, rdi; this
0x180011db4  call    ?Init@CTooltip@@QEAAKPEAUHWND__@@@Z; CTooltip::Init(HWND__ *)
0x180011db9  test    eax, eax
0x180011dbb  jnz     short loc_180011DF6
0x180011dbd  lea     r8, [rbx+68h]; unsigned __int16 *
0x180011dc1  mov     edx, 644h; unsigned int
0x180011dc6  mov     rcx, rdi; this
0x180011dc9  call    ?AddTool@CTooltip@@QEBAXIPEBG@Z; CTooltip::AddTool(uint,ushort const *)
0x180011dce  lea     r8, [rbx+270h]; unsigned __int16 *
0x180011dd5  mov     edx, 642h; unsigned int
0x180011dda  mov     rcx, rdi; this
0x180011ddd  call    ?AddTool@CTooltip@@QEBAXIPEBG@Z; CTooltip::AddTool(uint,ushort const *)
0x180011de2  lea     r8, [rbx+478h]; unsigned __int16 *
0x180011de9  mov     edx, 643h; unsigned int
0x180011dee  mov     rcx, rdi; this
0x180011df1  call    ?AddTool@CTooltip@@QEBAXIPEBG@Z; CTooltip::AddTool(uint,ushort const *)
0x180011df6  cmp     dword ptr [rbx+698h], 0
0x180011dfd  mov     rcx, rbx; this
0x180011e00  jz      short loc_180011E09
0x180011e02  call    ?MakeReadOnlyUI@CNotificationDialog@@AEAAXXZ; CNotificationDialog::MakeReadOnlyUI(void)
0x180011e07  jmp     short loc_180011E0E
0x180011e09  call    ?MakeMultiProfileUI@CNotificationDialog@@AEAAXXZ; CNotificationDialog::MakeMultiProfileUI(void)
0x180011e0e  mov     rcx, rbx; this
0x180011e11  call    ?CenterWindow@CNotificationDialog@@AEAAXXZ; CNotificationDialog::CenterWindow(void)
0x180011e16  cmp     dword ptr [rbx+694h], 0
0x180011e1d  jnz     short loc_180011E5F
0x180011e1f  mov     rcx, [rbx+8]; hWnd
0x180011e23  call    cs:__imp_SetActiveWindow
0x180011e29  mov     rcx, [rbx+8]; hWnd
0x180011e2d  call    cs:__imp_SetForegroundWindow
0x180011e33  mov     rcx, [rbx+8]; hWnd
0x180011e37  xor     r9d, r9d; Y
0x180011e3a  mov     [rsp+48h+uFlags], 43h ; 'C'; uFlags
0x180011e42  xor     r8d, r8d; X
0x180011e45  mov     [rsp+48h+cy], 0; cy
0x180011e4d  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x180011e51  mov     [rsp+48h+var_28], 0; cx
0x180011e59  call    cs:__imp_SetWindowPos
0x180011e5f  mov     rcx, cs:g_Provider
0x180011e66  test    rcx, rcx
0x180011e69  jz      short loc_180011E7E
0x180011e6b  xor     r9d, r9d
0x180011e6e  lea     rdx, QUInitialize_End
0x180011e75  xor     r8d, r8d
0x180011e78  call    cs:__imp_EtwEventWrite
0x180011e7e  mov     rbx, [rsp+48h+arg_0]
0x180011e83  xor     eax, eax
0x180011e85  add     rsp, 40h
0x180011e89  pop     rdi
0x180011e8a  retn
```
