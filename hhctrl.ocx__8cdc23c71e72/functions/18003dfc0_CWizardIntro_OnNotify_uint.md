# CWizardIntro::OnNotify(uint)

- ea: `0x18003dfc0`
- end: `0x18003e195`
- name: `?OnNotify@CWizardIntro@@UEAAHI@Z`
- size: `469`
- prototype: `__int64 __fastcall(CWizardIntro *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18003dfc0`
- `0x18003e4d4`
- `0x180075c42`
- `0x180075c5a`

## import_xrefs

- `msvcrt!_msize` at `0x18003e088`
- `msvcrt!_msize` at `0x18003e094`
- `msvcrt!_msize` at `0x18003e0ae`
- `msvcrt!_msize` at `0x18003e136`
- `msvcrt!_msize` at `0x18003e16d`
- `msvcrt!_msize` at `0x18003e088`
- `msvcrt!_msize` at `0x18003e094`
- `msvcrt!_msize` at `0x18003e0ae`
- `msvcrt!_msize` at `0x18003e136`
- `msvcrt!_msize` at `0x18003e16d`
- `USER32!SendDlgItemMessageA` at `0x18003e01b`
- `USER32!SendDlgItemMessageA` at `0x18003e041`
- `USER32!SendDlgItemMessageA` at `0x18003e0fc`
- `USER32!SendDlgItemMessageA` at `0x18003e01b`
- `USER32!SendDlgItemMessageA` at `0x18003e041`
- `USER32!SendDlgItemMessageA` at `0x18003e0fc`
- `USER32!SetWindowLongA` at `0x18003e0d8`
- `USER32!SetWindowLongA` at `0x18003e0d8`

## pseudocode

```c
__int64 __fastcall CWizardIntro::OnNotify(HWND *this, int a2)
{
  int v3; // edx
  void **v4; // rcx
  void *v5; // rsi
  size_t v6; // rbx
  size_t v7; // rax
  int v9; // eax
  HWND v10; // rcx
  void *v11; // rbx
  size_t v12; // rax
  void *v13; // rbx
  size_t v14; // rax

  if ( a2 != -207 )
  {
    if ( a2 == -200 )
    {
      CPropPage::SetWizButtons((CPropPage *)this, 2u);
      v3 = 1110;
      if ( !*((_DWORD *)this[287] + 18) )
        v3 = 1108;
      SendDlgItemMessageA(this[3], v3, 0xF1u, 1u, 0);
    }
    return 0;
  }
  if ( (unsigned int)SendDlgItemMessageA(this[3], 1109, 0xF0u, 0, 0) )
  {
    *((_DWORD *)this[287] + 17) = 1;
    *((_DWORD *)this[287] + 16) = 0;
    *((_DWORD *)this[287] + 18) = 0;
    v4 = (void **)this[287];
    v5 = (void *)*((_QWORD *)*v4 + 11);
    if ( !v5 )
    {
LABEL_10:
      SetWindowLongA(this[3], 0, 117);
      return 1;
    }
    v6 = _msize(v4[2]);
    if ( v6 == _msize(v5) )
    {
      v7 = _msize(*((void **)this[287] + 2));
      memcpy_0(*((void **)this[287] + 2), *(const void **)(*(_QWORD *)this[287] + 88LL), v7);
      goto LABEL_10;
    }
  }
  else
  {
    v9 = SendDlgItemMessageA(this[3], 1108, 0xF0u, 0, 0);
    *((_DWORD *)this[287] + 17) = 0;
    v10 = this[287];
    if ( v9 )
    {
      *((_DWORD *)v10 + 16) = 1;
      *((_DWORD *)this[287] + 18) = 0;
      v11 = (void *)*((_QWORD *)this[287] + 2);
      v12 = _msize(v11);
      memset_0(v11, 255, v12);
      goto LABEL_10;
    }
    *((_DWORD *)v10 + 16) = 0;
    *((_DWORD *)this[287] + 18) = 1;
    v13 = (void *)*((_QWORD *)this[287] + 2);
    v14 = _msize(v13);
    memset_0(v13, 255, v14);
  }
  return 0;
}

```

## disassembly

```asm
0x18003dfc0  mov     [rsp+arg_0], rbx
0x18003dfc5  mov     [rsp+arg_8], rsi
0x18003dfca  push    rdi
0x18003dfcb  sub     rsp, 30h
0x18003dfcf  mov     rdi, rcx
0x18003dfd2  cmp     edx, 0FFFFFF31h
0x18003dfd8  jz      short loc_18003E026
0x18003dfda  cmp     edx, 0FFFFFF38h
0x18003dfe0  jnz     loc_18003E183
0x18003dfe6  mov     edx, 2; unsigned int
0x18003dfeb  call    ?SetWizButtons@CPropPage@@QEBAXK@Z; CPropPage::SetWizButtons(ulong)
0x18003dff0  mov     rax, [rdi+8F8h]
0x18003dff7  xor     ebx, ebx
0x18003dff9  mov     rcx, [rdi+18h]; hDlg
0x18003dffd  mov     r8d, 0F1h; Msg
0x18003e003  mov     [rsp+38h+lParam], rbx; lParam
0x18003e008  mov     edx, 456h
0x18003e00d  lea     r9d, [rbx+1]; wParam
0x18003e011  cmp     [rax+48h], ebx
0x18003e014  jnz     short loc_18003E01B
0x18003e016  mov     edx, 454h; nIDDlgItem
0x18003e01b  call    cs:__imp_SendDlgItemMessageA
0x18003e021  jmp     loc_18003E183
0x18003e026  mov     rcx, [rcx+18h]; hDlg
0x18003e02a  mov     esi, 0F0h
0x18003e02f  xor     ebx, ebx
0x18003e031  mov     r8d, esi; Msg
0x18003e034  xor     r9d, r9d; wParam
0x18003e037  mov     [rsp+38h+lParam], rbx; lParam
0x18003e03c  mov     edx, 455h; nIDDlgItem
0x18003e041  call    cs:__imp_SendDlgItemMessageA
0x18003e047  test    eax, eax
0x18003e049  jz      loc_18003E0E8
0x18003e04f  mov     rax, [rdi+8F8h]
0x18003e056  mov     dword ptr [rax+44h], 1
0x18003e05d  mov     rax, [rdi+8F8h]
0x18003e064  mov     [rax+40h], ebx
0x18003e067  mov     rax, [rdi+8F8h]
0x18003e06e  mov     [rax+48h], ebx
0x18003e071  mov     rcx, [rdi+8F8h]
0x18003e078  mov     rax, [rcx]
0x18003e07b  mov     rsi, [rax+58h]
0x18003e07f  test    rsi, rsi
0x18003e082  jz      short loc_18003E0CE
0x18003e084  mov     rcx, [rcx+10h]; Block
0x18003e088  call    cs:__imp__msize
0x18003e08e  mov     rcx, rsi; Block
0x18003e091  mov     rbx, rax
0x18003e094  call    cs:__imp__msize
0x18003e09a  cmp     rbx, rax
0x18003e09d  jnz     loc_18003E183
0x18003e0a3  mov     rcx, [rdi+8F8h]
0x18003e0aa  mov     rcx, [rcx+10h]; Block
0x18003e0ae  call    cs:__imp__msize
0x18003e0b4  mov     rcx, [rdi+8F8h]
0x18003e0bb  mov     r8, rax; Size
0x18003e0be  mov     rdx, [rcx]
0x18003e0c1  mov     rcx, [rcx+10h]; void *
0x18003e0c5  mov     rdx, [rdx+58h]; Src
0x18003e0c9  call    memcpy_0
0x18003e0ce  mov     rcx, [rdi+18h]; hWnd
0x18003e0d2  xor     edx, edx; nIndex
0x18003e0d4  lea     r8d, [rdx+75h]; dwNewLong
0x18003e0d8  call    cs:__imp_SetWindowLongA
0x18003e0de  mov     eax, 1
0x18003e0e3  jmp     loc_18003E185
0x18003e0e8  mov     rcx, [rdi+18h]; hDlg
0x18003e0ec  xor     r9d, r9d; wParam
0x18003e0ef  mov     r8d, esi; Msg
0x18003e0f2  mov     [rsp+38h+lParam], rbx; lParam
0x18003e0f7  mov     edx, 454h; nIDDlgItem
0x18003e0fc  call    cs:__imp_SendDlgItemMessageA
0x18003e102  mov     rcx, [rdi+8F8h]
0x18003e109  mov     [rcx+44h], ebx
0x18003e10c  mov     rcx, [rdi+8F8h]
0x18003e113  test    eax, eax
0x18003e115  jz      short loc_18003E14E
0x18003e117  mov     dword ptr [rcx+40h], 1
0x18003e11e  mov     rax, [rdi+8F8h]
0x18003e125  mov     [rax+48h], ebx
0x18003e128  mov     rax, [rdi+8F8h]
0x18003e12f  mov     rbx, [rax+10h]
0x18003e133  mov     rcx, rbx; Block
0x18003e136  call    cs:__imp__msize
0x18003e13c  mov     edx, 0FFh; Val
0x18003e141  mov     rcx, rbx; void *
0x18003e144  mov     r8, rax; Size
0x18003e147  call    memset_0
0x18003e14c  jmp     short loc_18003E0CE
0x18003e14e  mov     [rcx+40h], ebx
0x18003e151  mov     rax, [rdi+8F8h]
0x18003e158  mov     dword ptr [rax+48h], 1
0x18003e15f  mov     rax, [rdi+8F8h]
0x18003e166  mov     rbx, [rax+10h]
0x18003e16a  mov     rcx, rbx; Block
0x18003e16d  call    cs:__imp__msize
0x18003e173  mov     edx, 0FFh; Val
0x18003e178  mov     rcx, rbx; void *
0x18003e17b  mov     r8, rax; Size
0x18003e17e  call    memset_0
0x18003e183  xor     eax, eax
0x18003e185  mov     rbx, [rsp+38h+arg_0]
0x18003e18a  mov     rsi, [rsp+38h+arg_8]
0x18003e18f  add     rsp, 30h
0x18003e193  pop     rdi
0x18003e194  retn
```
