# UserPropSheet::OnCommand(HWND__ *,unsigned __int64,__int64)

- ea: `0x180017b7c`
- end: `0x180017ed5`
- name: `?OnCommand@UserPropSheet@@AEAA_JPEAUHWND__@@_K_J@Z`
- size: `857`
- prototype: `__int64(UserPropSheet *__hidden this, HWND, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017620`

## callees

- `0x180011160`
- `0x180011354`
- `0x180017b7c`
- `0x18001ad0c`
- `0x18001b120`
- `0x18001b1e0`
- `0x18001b26c`
- `0x18001b3b0`
- `0x18001f010`

## import_xrefs

- `USER32!IsWindowEnabled` at `0x180017c3e`
- `USER32!IsWindowEnabled` at `0x180017c98`
- `USER32!IsWindowEnabled` at `0x180017c3e`
- `USER32!IsWindowEnabled` at `0x180017c98`
- `USER32!SendDlgItemMessageW` at `0x180017e8c`
- `USER32!SendDlgItemMessageW` at `0x180017e8c`
- `USER32!GetParent` at `0x180017ea1`
- `USER32!GetParent` at `0x180017ea1`
- `USER32!SendMessageW` at `0x180017eb5`
- `USER32!SendMessageW` at `0x180017eb5`
- `USER32!GetDlgItem` at `0x180017c35`
- `USER32!GetDlgItem` at `0x180017c8f`
- `USER32!GetDlgItem` at `0x180017e66`
- `USER32!GetDlgItem` at `0x180017c35`
- `USER32!GetDlgItem` at `0x180017c8f`
- `USER32!GetDlgItem` at `0x180017e66`
- `USER32!SetFocus` at `0x180017e6f`
- `USER32!SetFocus` at `0x180017e6f`

## pseudocode

```c
__int64 __fastcall UserPropSheet::OnCommand(UserPropSheet *this, HWND a2, int a3, __int64 a4)
{
  __int64 v5; // r14
  XBytes *v7; // rcx
  HWND v8; // rax
  XBytes *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  HWND v12; // rax
  unsigned int v13; // r15d
  BOOL v14; // esi
  StructureList *v15; // rcx
  __int64 v16; // rdx
  int v17; // esi
  XBytes *v18; // rcx
  XBytes *v19; // rcx
  HWND DlgItem; // rax
  HWND Parent; // rax
  struct IDiskQuotaUser *v23[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v24; // [rsp+88h] [rbp+48h] BYREF

  v24 = a4;
  v5 = 0;
  if ( (unsigned __int16)a3 == 1020 )
  {
    if ( HIWORD(a3) == 256 && *((_DWORD *)this + 8) == 1027 )
    {
      DlgItem = GetDlgItem(a2, 1027);
      SetFocus(DlgItem);
      SendDlgItemMessageW(a2, 1027, 0xB1u, 0, -1);
      *((_DWORD *)this + 8) = -1;
    }
    goto LABEL_68;
  }
  if ( (unsigned __int16)a3 != 1026 && (unsigned __int16)a3 != 1027 )
  {
    if ( (unsigned __int16)a3 != 1028 )
    {
      if ( (unsigned __int16)a3 != 1029 )
      {
        if ( (unsigned int)(unsigned __int16)a3 - 1040 >= 2 )
        {
          v5 = 1;
          goto LABEL_68;
        }
        if ( HIWORD(a3) == 1 )
        {
          if ( (unsigned __int16)a3 == 1040 )
          {
            v7 = (XBytes *)*((_QWORD *)this + 24);
LABEL_13:
            if ( v7 )
              XBytes::OnComboNotifySelChange(v7, (__int64)a2);
            goto LABEL_18;
          }
          if ( (unsigned __int16)a3 == 1041 )
          {
            v7 = (XBytes *)*((_QWORD *)this + 25);
            goto LABEL_13;
          }
LABEL_18:
          *((_DWORD *)this + 36) = 1;
          goto LABEL_68;
        }
        goto LABEL_68;
      }
      v8 = GetDlgItem(*(HWND *)(*((_QWORD *)this + 25) + 8LL), *(_DWORD *)(*((_QWORD *)this + 25) + 16LL));
      if ( !IsWindowEnabled(v8) )
        goto LABEL_68;
      XBytes::SetBytes(*((XBytes **)this + 25), -1);
      v9 = (XBytes *)*((_QWORD *)this + 24);
      v10 = -1;
LABEL_17:
      XBytes::SetBytes(v9, v10);
      goto LABEL_18;
    }
    v11 = *((_QWORD *)this + 25);
    v24 = 0;
    v12 = GetDlgItem(*(HWND *)(v11 + 8), *(_DWORD *)(v11 + 16));
    if ( IsWindowEnabled(v12) )
      goto LABEL_68;
    v13 = StructureList::Count((StructureList *)(*((_QWORD *)this + 7) + 8LL));
    if ( !v13 )
    {
      v24 = 0;
LABEL_35:
      (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 5) + 112LL))(*((_QWORD *)this + 5), &v24);
      v16 = v24;
      if ( v24 != -1 )
        goto LABEL_38;
      v16 = 0;
LABEL_37:
      v24 = v16;
LABEL_38:
      XBytes::SetBytes(*((XBytes **)this + 24), v16);
      v10 = 0;
      v24 = 0;
      if ( !v13 )
        goto LABEL_47;
      if ( v13 == 1 )
      {
        if ( *((_QWORD *)this + 3) == -1 )
        {
          if ( *((_QWORD *)this + 3) != -1 )
          {
            if ( (*((_QWORD *)this + 3) == -1) == 2 )
            {
              v10 = -1;
LABEL_49:
              v24 = v10;
            }
LABEL_50:
            v9 = (XBytes *)*((_QWORD *)this + 25);
            goto LABEL_17;
          }
LABEL_47:
          (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 5) + 88LL))(*((_QWORD *)this + 5), &v24);
          v10 = v24;
          if ( v24 == -1 )
          {
            v10 = 0;
            goto LABEL_49;
          }
          goto LABEL_50;
        }
      }
      else if ( !*((_DWORD *)this + 37) || *((_QWORD *)this + 3) == -1 )
      {
        goto LABEL_47;
      }
      v10 = *((_QWORD *)this + 3);
      goto LABEL_49;
    }
    v14 = 0;
    if ( v13 == 1 )
    {
      v15 = (StructureList *)(*((_QWORD *)this + 7) + 8LL);
      *(_OWORD *)v23 = 0;
      if ( StructureList::Retrieve(v15, v23, 0) )
      {
        if ( (unsigned int)UserIsAdministrator(v23[0]) )
        {
          v24 = 0;
          goto LABEL_32;
        }
        v14 = *((_QWORD *)this + 2) == -1;
      }
    }
    else if ( !*((_DWORD *)this + 37) || *((_QWORD *)this + 2) == -1 )
    {
      v24 = 0;
      goto LABEL_35;
    }
    v16 = 0;
    v24 = 0;
    if ( !v14 )
    {
      v16 = *((_QWORD *)this + 2);
      goto LABEL_37;
    }
    v17 = v14 - 1;
    if ( !v17 )
      goto LABEL_35;
    if ( v17 != 1 )
      goto LABEL_38;
LABEL_32:
    v16 = -1;
    goto LABEL_37;
  }
  if ( HIWORD(a3) == 512 )
  {
    if ( (unsigned __int16)a3 == 1026 )
    {
      v19 = (XBytes *)*((_QWORD *)this + 24);
    }
    else
    {
      if ( (unsigned __int16)a3 != 1027 )
        goto LABEL_68;
      v19 = (XBytes *)*((_QWORD *)this + 25);
    }
    if ( v19 )
      XBytes::OnEditKillFocus(v19, (__int64)a2);
  }
  else if ( HIWORD(a3) == 1024 )
  {
    if ( (unsigned __int16)a3 == 1026 )
    {
      v18 = (XBytes *)*((_QWORD *)this + 24);
    }
    else
    {
      if ( (unsigned __int16)a3 != 1027 )
        goto LABEL_18;
      v18 = (XBytes *)*((_QWORD *)this + 25);
    }
    if ( v18 )
      XBytes::OnEditNotifyUpdate(v18, (__int64)a2);
    goto LABEL_18;
  }
LABEL_68:
  if ( *((_DWORD *)this + 36) )
  {
    Parent = GetParent(a2);
    SendMessageW(Parent, 0x468u, (WPARAM)a2, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x180017b7c  mov     [rsp-28h+arg_0], rbx
0x180017b81  mov     [rsp-28h+arg_8], rsi
0x180017b86  mov     [rsp-28h+arg_18], r9
0x180017b8b  push    rbp
0x180017b8c  push    rdi
0x180017b8d  push    r12
0x180017b8f  push    r14
0x180017b91  push    r15
0x180017b93  mov     rbp, rsp
0x180017b96  sub     rsp, 40h
0x180017b9a  mov     rax, r8
0x180017b9d  mov     rbx, rcx
0x180017ba0  shr     rax, 10h
0x180017ba4  xor     r14d, r14d
0x180017ba7  movzx   r9d, ax
0x180017bab  mov     r12, rdx
0x180017bae  movzx   ecx, r8w
0x180017bb2  mov     eax, ecx
0x180017bb4  sub     eax, 3FCh
0x180017bb9  jz      loc_180017E4E
0x180017bbf  sub     eax, 6
0x180017bc2  jz      loc_180017DDB
0x180017bc8  sub     eax, 1
0x180017bcb  jz      loc_180017DDB
0x180017bd1  sub     eax, 1
0x180017bd4  jz      loc_180017C7D
0x180017bda  sub     eax, 1
0x180017bdd  jz      short loc_180017C27
0x180017bdf  sub     eax, 0Bh
0x180017be2  jz      short loc_180017BF4
0x180017be4  cmp     eax, 1
0x180017be7  jz      short loc_180017BF4
0x180017be9  mov     r14d, 1
0x180017bef  jmp     loc_180017E95
0x180017bf4  cmp     r9d, 1
0x180017bf8  jnz     loc_180017E95
0x180017bfe  sub     ecx, 410h
0x180017c04  jz      short loc_180017C14
0x180017c06  cmp     ecx, r9d
0x180017c09  jnz     short loc_180017C6E
0x180017c0b  mov     rcx, [rbx+0C8h]
0x180017c12  jmp     short loc_180017C1B
0x180017c14  mov     rcx, [rbx+0C0h]; this
0x180017c1b  test    rcx, rcx
0x180017c1e  jz      short loc_180017C6E
0x180017c20  call    ?OnComboNotifySelChange@XBytes@@QEAAH_J@Z; XBytes::OnComboNotifySelChange(__int64)
0x180017c25  jmp     short loc_180017C6E
0x180017c27  mov     rcx, [rbx+0C8h]
0x180017c2e  mov     edx, [rcx+10h]; nIDDlgItem
0x180017c31  mov     rcx, [rcx+8]; hDlg
0x180017c35  call    cs:__imp_GetDlgItem
0x180017c3b  mov     rcx, rax; hWnd
0x180017c3e  call    cs:__imp_IsWindowEnabled
0x180017c44  test    eax, eax
0x180017c46  jz      loc_180017E95
0x180017c4c  mov     rcx, [rbx+0C8h]; this
0x180017c53  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180017c57  mov     rdx, rdi; __int64
0x180017c5a  call    ?SetBytes@XBytes@@QEAAX_J@Z; XBytes::SetBytes(__int64)
0x180017c5f  mov     rcx, [rbx+0C0h]; this
0x180017c66  mov     rdx, rdi; __int64
0x180017c69  call    ?SetBytes@XBytes@@QEAAX_J@Z; XBytes::SetBytes(__int64)
0x180017c6e  mov     dword ptr [rbx+90h], 1
0x180017c78  jmp     loc_180017E95
0x180017c7d  mov     rcx, [rbx+0C8h]
0x180017c84  mov     [rbp+arg_18], r14
0x180017c88  mov     edx, [rcx+10h]; nIDDlgItem
0x180017c8b  mov     rcx, [rcx+8]; hDlg
0x180017c8f  call    cs:__imp_GetDlgItem
0x180017c95  mov     rcx, rax; hWnd
0x180017c98  call    cs:__imp_IsWindowEnabled
0x180017c9e  test    eax, eax
0x180017ca0  jnz     loc_180017E95
0x180017ca6  mov     rcx, [rbx+38h]
0x180017caa  add     rcx, 8; this
0x180017cae  call    ?Count@StructureList@@QEAAIXZ; StructureList::Count(void)
0x180017cb3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180017cb7  mov     r15d, eax
0x180017cba  test    eax, eax
0x180017cbc  jnz     short loc_180017CC4
0x180017cbe  mov     [rbp+arg_18], r14
0x180017cc2  jmp     short loc_180017D3C
0x180017cc4  xor     esi, esi
0x180017cc6  cmp     r15d, 1
0x180017cca  jnz     short loc_180017D0B
0x180017ccc  mov     rcx, [rbx+38h]
0x180017cd0  lea     rdx, [rbp+var_10]; void *
0x180017cd4  xorps   xmm0, xmm0
0x180017cd7  add     rcx, 8; this
0x180017cdb  xor     r8d, r8d; unsigned int
0x180017cde  movups  xmmword ptr [rbp+var_10], xmm0
0x180017ce2  call    ?Retrieve@StructureList@@QEAAHPEAXI@Z; StructureList::Retrieve(void *,uint)
0x180017ce7  test    eax, eax
0x180017ce9  jz      short loc_180017D19
0x180017ceb  mov     rcx, [rbp+var_10]; struct IDiskQuotaUser *
0x180017cef  call    ?UserIsAdministrator@@YAHPEAUIDiskQuotaUser@@@Z; UserIsAdministrator(IDiskQuotaUser *)
0x180017cf4  test    eax, eax
0x180017cf6  jz      short loc_180017CFE
0x180017cf8  mov     [rbp+arg_18], rsi
0x180017cfc  jmp     short loc_180017D2D
0x180017cfe  cmp     [rbx+10h], rdi
0x180017d02  jnz     short loc_180017D19
0x180017d04  mov     esi, 1
0x180017d09  jmp     short loc_180017D19
0x180017d0b  cmp     [rbx+94h], esi
0x180017d11  jz      short loc_180017D38
0x180017d13  cmp     [rbx+10h], rdi
0x180017d17  jz      short loc_180017D38
0x180017d19  xor     edx, edx
0x180017d1b  mov     [rbp+arg_18], rdx
0x180017d1f  test    esi, esi
0x180017d21  jz      short loc_180017D32
0x180017d23  sub     esi, 1
0x180017d26  jz      short loc_180017D3C
0x180017d28  cmp     esi, 1
0x180017d2b  jnz     short loc_180017D5F
0x180017d2d  mov     rdx, rdi
0x180017d30  jmp     short loc_180017D5B
0x180017d32  mov     rdx, [rbx+10h]
0x180017d36  jmp     short loc_180017D5B
0x180017d38  mov     [rbp+arg_18], rsi
0x180017d3c  mov     rcx, [rbx+28h]
0x180017d40  lea     rdx, [rbp+arg_18]
0x180017d44  mov     rax, [rcx]
0x180017d47  mov     rax, [rax+70h]
0x180017d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d50  mov     rdx, [rbp+arg_18]
0x180017d54  cmp     rdx, rdi
0x180017d57  jnz     short loc_180017D5F
0x180017d59  xor     edx, edx; __int64
0x180017d5b  mov     [rbp+arg_18], rdx
0x180017d5f  mov     rcx, [rbx+0C0h]; this
0x180017d66  call    ?SetBytes@XBytes@@QEAAX_J@Z; XBytes::SetBytes(__int64)
0x180017d6b  xor     edx, edx
0x180017d6d  mov     [rbp+arg_18], rdx
0x180017d71  test    r15d, r15d
0x180017d74  jz      short loc_180017DAC
0x180017d76  cmp     r15d, 1
0x180017d7a  jnz     short loc_180017D98
0x180017d7c  xor     ecx, ecx
0x180017d7e  cmp     [rbx+18h], rdi
0x180017d82  setz    cl
0x180017d85  test    ecx, ecx
0x180017d87  jz      short loc_180017DA6
0x180017d89  sub     ecx, r15d
0x180017d8c  jz      short loc_180017DAC
0x180017d8e  cmp     ecx, r15d
0x180017d91  jnz     short loc_180017DCF
0x180017d93  mov     rdx, rdi
0x180017d96  jmp     short loc_180017DCB
0x180017d98  cmp     [rbx+94h], edx
0x180017d9e  jz      short loc_180017DAC
0x180017da0  cmp     [rbx+18h], rdi
0x180017da4  jz      short loc_180017DAC
0x180017da6  mov     rdx, [rbx+18h]
0x180017daa  jmp     short loc_180017DCB
0x180017dac  mov     rcx, [rbx+28h]
0x180017db0  lea     rdx, [rbp+arg_18]
0x180017db4  mov     rax, [rcx]
0x180017db7  mov     rax, [rax+58h]
0x180017dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dc0  mov     rdx, [rbp+arg_18]
0x180017dc4  cmp     rdx, rdi
0x180017dc7  jnz     short loc_180017DCF
0x180017dc9  xor     edx, edx; __int64
0x180017dcb  mov     [rbp+arg_18], rdx
0x180017dcf  mov     rcx, [rbx+0C8h]
0x180017dd6  jmp     loc_180017C69
0x180017ddb  cmp     r9d, 200h
0x180017de2  jz      short loc_180017E25
0x180017de4  cmp     r9d, 400h
0x180017deb  jnz     loc_180017E95
0x180017df1  sub     ecx, 402h
0x180017df7  jz      short loc_180017E0B
0x180017df9  cmp     ecx, 1
0x180017dfc  jnz     loc_180017C6E
0x180017e02  mov     rcx, [rbx+0C8h]
0x180017e09  jmp     short loc_180017E12
0x180017e0b  mov     rcx, [rbx+0C0h]; this
0x180017e12  test    rcx, rcx
0x180017e15  jz      loc_180017C6E
0x180017e1b  call    ?OnEditNotifyUpdate@XBytes@@QEAAH_J@Z; XBytes::OnEditNotifyUpdate(__int64)
0x180017e20  jmp     loc_180017C6E
0x180017e25  sub     ecx, 402h
0x180017e2b  jz      short loc_180017E3B
0x180017e2d  cmp     ecx, 1
0x180017e30  jnz     short loc_180017E95
0x180017e32  mov     rcx, [rbx+0C8h]
0x180017e39  jmp     short loc_180017E42
0x180017e3b  mov     rcx, [rbx+0C0h]; this
0x180017e42  test    rcx, rcx
0x180017e45  jz      short loc_180017E95
0x180017e47  call    ?OnEditKillFocus@XBytes@@QEAAH_J@Z; XBytes::OnEditKillFocus(__int64)
0x180017e4c  jmp     short loc_180017E95
0x180017e4e  cmp     r9d, 100h
0x180017e55  jnz     short loc_180017E95
0x180017e57  mov     esi, 403h
0x180017e5c  cmp     [rbx+20h], esi
0x180017e5f  jnz     short loc_180017E95
0x180017e61  mov     edx, esi; nIDDlgItem
0x180017e63  mov     rcx, r12; hDlg
0x180017e66  call    cs:__imp_GetDlgItem
0x180017e6c  mov     rcx, rax; hWnd
0x180017e6f  call    cs:__imp_SetFocus
0x180017e75  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180017e79  xor     r9d, r9d; wParam
0x180017e7c  mov     r8d, 0B1h; Msg
0x180017e82  mov     [rsp+40h+lParam], rdi; lParam
0x180017e87  mov     edx, esi; nIDDlgItem
0x180017e89  mov     rcx, r12; hDlg
0x180017e8c  call    cs:__imp_SendDlgItemMessageW
0x180017e92  mov     [rbx+20h], edi
0x180017e95  cmp     dword ptr [rbx+90h], 0
0x180017e9c  jz      short loc_180017EBB
0x180017e9e  mov     rcx, r12; hWnd
0x180017ea1  call    cs:__imp_GetParent
0x180017ea7  xor     r9d, r9d; lParam
0x180017eaa  mov     r8, r12; wParam
0x180017ead  mov     rcx, rax; hWnd
0x180017eb0  mov     edx, 468h; Msg
0x180017eb5  call    cs:__imp_SendMessageW
0x180017ebb  mov     rbx, [rsp+40h+arg_0]
0x180017ec0  mov     rax, r14
0x180017ec3  mov     rsi, [rsp+40h+arg_8]
0x180017ec8  add     rsp, 40h
0x180017ecc  pop     r15
0x180017ece  pop     r14
0x180017ed0  pop     r12
0x180017ed2  pop     rdi
0x180017ed3  pop     rbp
0x180017ed4  retn
```
