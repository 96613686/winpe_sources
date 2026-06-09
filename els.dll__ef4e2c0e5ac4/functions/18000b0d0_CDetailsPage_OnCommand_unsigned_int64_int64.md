# CDetailsPage::_OnCommand(unsigned __int64,__int64)

- ea: `0x18000b0d0`
- end: `0x18000b21d`
- name: `?_OnCommand@CDetailsPage@@EEAAK_K_J@Z`
- size: `333`
- prototype: `unsigned int __fastcall(CDetailsPage *__hidden this, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000aa10`
- `0x18000aac0`
- `0x18000b0d0`
- `0x18000b6b8`
- `0x180024010`

## import_xrefs

- `USER32!GetDlgItem` at `0x18000b1d0`
- `USER32!GetDlgItem` at `0x18000b1d0`
- `USER32!GetParent` at `0x18000b1f5`
- `USER32!GetParent` at `0x18000b1f5`
- `USER32!SetWindowTextW` at `0x18000b1dc`
- `USER32!SetWindowTextW` at `0x18000b1dc`
- `USER32!PostMessageW` at `0x18000b20a`
- `USER32!PostMessageW` at `0x18000b20a`

## pseudocode

```c
__int64 __fastcall CDetailsPage::_OnCommand(HWND *this, int a2)
{
  unsigned int v2; // edi
  unsigned int v4; // ebp
  unsigned int v5; // edx
  __int64 v6; // rax
  const WCHAR *v7; // rsi
  HWND DlgItem; // rax
  HWND Parent; // rax

  v2 = (unsigned __int16)a2;
  v4 = 0;
  if ( (unsigned __int16)a2 == 2 )
  {
    Parent = GetParent(this[2]);
    PostMessageW(Parent, 0x111u, 2u, 0);
  }
  else if ( (unsigned __int16)a2 != 129 )
  {
    switch ( (unsigned __int16)a2 )
    {
      case 0x82u:
      case 0x83u:
        if ( !HIWORD(a2) && *((_DWORD *)this + 25) != (unsigned __int16)a2 )
        {
          v6 = 7;
          if ( (_WORD)a2 != 130 )
            v6 = 9;
          v7 = (const WCHAR *)this[v6];
          if ( v7 && *v7 )
          {
            DlgItem = GetDlgItem(this[2], 129);
            SetWindowTextW(DlgItem, v7);
            *((_DWORD *)this + 25) = v2;
          }
          else
          {
            CDetailsPage::_RefreshControls((CDetailsPage *)this);
          }
        }
        break;
      case 0x143u:
      case 0x144u:
        if ( !(*(unsigned int (__fastcall **)(HWND, _QWORD, _QWORD))(*(_QWORD *)this[6] + 24LL))(
                this[6],
                (unsigned __int16)a2,
                0)
          && YesNoConfirm(this[2], v5, 237 - ((_WORD)v2 != 324)) == 6 )
        {
          (*(void (__fastcall **)(HWND, _QWORD, __int64))(*(_QWORD *)this[6] + 24LL))(this[6], v2, 1);
        }
        break;
      case 0x145u:
        CDetailsPage::_CopyToClipboard((CDetailsPage *)this);
        break;
      default:
        return 1;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000b0d0  push    rbx
0x18000b0d2  push    rbp
0x18000b0d3  push    rsi
0x18000b0d4  push    rdi
0x18000b0d5  push    r14
0x18000b0d7  sub     rsp, 20h
0x18000b0db  xor     r14d, r14d
0x18000b0de  movzx   edi, dx
0x18000b0e1  mov     r8d, edi
0x18000b0e4  mov     rbx, rcx
0x18000b0e7  mov     ebp, r14d
0x18000b0ea  sub     r8d, 2
0x18000b0ee  jz      loc_18000B1F1
0x18000b0f4  sub     r8d, 7Fh
0x18000b0f8  jz      loc_18000B210
0x18000b0fe  sub     r8d, 1
0x18000b102  jz      loc_18000B19B
0x18000b108  sub     r8d, 1
0x18000b10c  jz      loc_18000B19B
0x18000b112  sub     r8d, 0C0h
0x18000b119  jz      short loc_18000B13A
0x18000b11b  sub     r8d, 1
0x18000b11f  jz      short loc_18000B13A
0x18000b121  cmp     r8d, 1
0x18000b125  jz      short loc_18000B130
0x18000b127  lea     ebp, [r14+1]
0x18000b12b  jmp     loc_18000B210
0x18000b130  call    ?_CopyToClipboard@CDetailsPage@@AEAAXXZ; CDetailsPage::_CopyToClipboard(void)
0x18000b135  jmp     loc_18000B210
0x18000b13a  mov     rcx, [rcx+30h]
0x18000b13e  xor     r8d, r8d
0x18000b141  mov     edx, edi
0x18000b143  mov     rax, [rcx]
0x18000b146  mov     rax, [rax+18h]
0x18000b14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b14f  test    eax, eax
0x18000b151  jnz     loc_18000B210
0x18000b157  mov     ecx, 144h
0x18000b15c  movzx   eax, di
0x18000b15f  sub     ax, cx
0x18000b162  mov     rcx, [rbx+10h]; hWnd
0x18000b166  neg     ax
0x18000b169  sbb     r8d, r8d
0x18000b16c  add     r8d, 0EDh; unsigned int
0x18000b173  call    ?YesNoConfirm@@YAKPEAUHWND__@@KK@Z; YesNoConfirm(HWND__ *,ulong,ulong)
0x18000b178  cmp     eax, 6
0x18000b17b  jnz     loc_18000B210
0x18000b181  mov     rcx, [rbx+30h]
0x18000b185  mov     r8d, 1
0x18000b18b  mov     edx, edi
0x18000b18d  mov     rax, [rcx]
0x18000b190  mov     rax, [rax+18h]
0x18000b194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b199  jmp     short loc_18000B210
0x18000b19b  shr     rdx, 10h
0x18000b19f  test    dx, dx
0x18000b1a2  jnz     short loc_18000B210
0x18000b1a4  cmp     [rcx+64h], edi
0x18000b1a7  jz      short loc_18000B210
0x18000b1a9  mov     edx, 82h
0x18000b1ae  cmp     di, dx
0x18000b1b1  lea     eax, [rdx-4Ah]
0x18000b1b4  lea     ecx, [rdx-3Ah]
0x18000b1b7  cmovnz  eax, ecx
0x18000b1ba  mov     rsi, [rax+rbx]
0x18000b1be  test    rsi, rsi
0x18000b1c1  jz      short loc_18000B1E7
0x18000b1c3  cmp     [rsi], r14w
0x18000b1c7  jz      short loc_18000B1E7
0x18000b1c9  lea     edx, [rcx+39h]; nIDDlgItem
0x18000b1cc  mov     rcx, [rbx+10h]; hDlg
0x18000b1d0  call    cs:__imp_GetDlgItem
0x18000b1d6  mov     rcx, rax; hWnd
0x18000b1d9  mov     rdx, rsi; lpString
0x18000b1dc  call    cs:__imp_SetWindowTextW
0x18000b1e2  mov     [rbx+64h], edi
0x18000b1e5  jmp     short loc_18000B210
0x18000b1e7  mov     rcx, rbx; this
0x18000b1ea  call    ?_RefreshControls@CDetailsPage@@AEAAXXZ; CDetailsPage::_RefreshControls(void)
0x18000b1ef  jmp     short loc_18000B210
0x18000b1f1  mov     rcx, [rcx+10h]; hWnd
0x18000b1f5  call    cs:__imp_GetParent
0x18000b1fb  xor     r9d, r9d; lParam
0x18000b1fe  mov     edx, 111h; Msg
0x18000b203  mov     rcx, rax; hWnd
0x18000b206  lea     r8d, [r9+2]; wParam
0x18000b20a  call    cs:__imp_PostMessageW
0x18000b210  mov     eax, ebp
0x18000b212  add     rsp, 20h
0x18000b216  pop     r14
0x18000b218  pop     rdi
0x18000b219  pop     rsi
0x18000b21a  pop     rbp
0x18000b21b  pop     rbx
0x18000b21c  retn
```
