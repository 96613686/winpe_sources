# CConfigAdvancedPage::OnCommand(HWND__ *,ushort,ushort,HWND__ *,int &)

- ea: `0x180014ad0`
- end: `0x180014bad`
- name: `?OnCommand@CConfigAdvancedPage@@UEAAKPEAUHWND__@@GG0AEAH@Z`
- size: `221`
- prototype: `unsigned int __usercall@<eax>(CConfigAdvancedPage *__hidden this@<rcx>, HWND@<rdx>, unsigned __int16@<r8w>, unsigned __int16@<r9w>, HWND, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005eac`
- `0x180014ad0`
- `0x180014df8`
- `0x180015200`
- `0x180017010`

## import_xrefs

- `USER32!GetDlgItemTextW` at `0x180014b91`
- `USER32!GetDlgItemTextW` at `0x180014b91`

## pseudocode

```c
__int64 __fastcall CConfigAdvancedPage::OnCommand(
        CConfigAdvancedPage *this,
        HWND a2,
        __int16 a3,
        unsigned __int16 a4,
        HWND a5,
        int *a6)
{
  int v6; // ebp
  __int16 v10; // ax

  v6 = a4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids);
  }
  *a6 = 1;
  switch ( v6 )
  {
    case 4522:
      CConfigAdvancedPage::OpenSelectFolderDialog((HINSTANCE *)this, a2);
      GetDlgItemTextW(a2, 4521, (LPWSTR)this + 20, 260);
      CConfigAdvancedPage::ValidateFolderForAchive(this, a2);
      return 0;
    case 4523:
      v10 = 0;
LABEL_14:
      if ( v10 != a3 )
        return 0;
LABEL_15:
      (*(void (__fastcall **)(CConfigAdvancedPage *, HWND))(*(_QWORD *)this + 80LL))(this, a2);
      return 0;
    case 4526:
      goto LABEL_12;
    case 4527:
      goto LABEL_15;
    case 4529:
LABEL_12:
      v10 = 768;
      goto LABEL_14;
    case 4530:
      goto LABEL_15;
  }
  *a6 = 0;
  return 0;
}

```

## disassembly

```asm
0x180014ad0  push    rbx
0x180014ad2  push    rbp
0x180014ad3  push    rsi
0x180014ad4  push    rdi
0x180014ad5  sub     rsp, 28h
0x180014ad9  movzx   ebp, r9w
0x180014add  movzx   esi, r8w
0x180014ae1  mov     rdi, rdx
0x180014ae4  mov     rbx, rcx
0x180014ae7  mov     rcx, cs:WPP_GLOBAL_Control
0x180014aee  lea     rax, WPP_GLOBAL_Control
0x180014af5  cmp     rcx, rax
0x180014af8  jz      short loc_180014B1E
0x180014afa  test    dword ptr [rcx+1Ch], 100h
0x180014b01  jz      short loc_180014B1E
0x180014b03  cmp     byte ptr [rcx+19h], 5
0x180014b07  jb      short loc_180014B1E
0x180014b09  mov     rcx, [rcx+10h]
0x180014b0d  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x180014b14  mov     edx, 1Ch
0x180014b19  call    WPP_SF_
0x180014b1e  mov     rdx, [rsp+48h+arg_28]
0x180014b23  mov     ecx, ebp
0x180014b25  mov     dword ptr [rdx], 1
0x180014b2b  sub     ecx, 11AAh
0x180014b31  jz      short loc_180014B74
0x180014b33  sub     ecx, 1
0x180014b36  jz      short loc_180014B59
0x180014b38  sub     ecx, 3
0x180014b3b  jz      short loc_180014B52
0x180014b3d  sub     ecx, 1
0x180014b40  jz      short loc_180014B60
0x180014b42  sub     ecx, 2
0x180014b45  jz      short loc_180014B52
0x180014b47  cmp     ecx, 1
0x180014b4a  jz      short loc_180014B60
0x180014b4c  xor     eax, eax
0x180014b4e  mov     [rdx], eax
0x180014b50  jmp     short loc_180014BA2
0x180014b52  mov     eax, 300h
0x180014b57  jmp     short loc_180014B5B
0x180014b59  xor     eax, eax
0x180014b5b  cmp     ax, si
0x180014b5e  jnz     short loc_180014BA2
0x180014b60  mov     rax, [rbx]
0x180014b63  mov     rdx, rdi
0x180014b66  mov     rcx, rbx
0x180014b69  mov     rax, [rax+50h]
0x180014b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b72  jmp     short loc_180014BA2
0x180014b74  mov     rdx, rdi; HWND
0x180014b77  mov     rcx, rbx; this
0x180014b7a  call    ?OpenSelectFolderDialog@CConfigAdvancedPage@@AEBAKPEAUHWND__@@@Z; CConfigAdvancedPage::OpenSelectFolderDialog(HWND__ *)
0x180014b7f  lea     r8, [rbx+28h]; lpString
0x180014b83  mov     edx, 11A9h; nIDDlgItem
0x180014b88  mov     r9d, 104h; cchMax
0x180014b8e  mov     rcx, rdi; hDlg
0x180014b91  call    cs:__imp_GetDlgItemTextW
0x180014b97  mov     rdx, rdi; HWND
0x180014b9a  mov     rcx, rbx; this
0x180014b9d  call    ?ValidateFolderForAchive@CConfigAdvancedPage@@AEBAXPEAUHWND__@@@Z; CConfigAdvancedPage::ValidateFolderForAchive(HWND__ *)
0x180014ba2  xor     eax, eax
0x180014ba4  add     rsp, 28h
0x180014ba8  pop     rdi
0x180014ba9  pop     rsi
0x180014baa  pop     rbp
0x180014bab  pop     rbx
0x180014bac  retn
```
