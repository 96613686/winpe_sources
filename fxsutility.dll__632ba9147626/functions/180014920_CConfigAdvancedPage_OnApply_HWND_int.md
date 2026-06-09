# CConfigAdvancedPage::OnApply(HWND__ *,int &)

- ea: `0x180014920`
- end: `0x180014ac8`
- name: `?OnApply@CConfigAdvancedPage@@UEAAKPEAUHWND__@@AEAH@Z`
- size: `424`
- prototype: `unsigned int __fastcall(CConfigAdvancedPage *__hidden this, HWND, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000edb0`
- `0x180014920`
- `0x180014ef0`
- `0x180015018`
- `0x18001514c`
- `0x180017010`

## import_xrefs

- `USER32!GetDlgItemTextW` at `0x1800149a3`
- `USER32!GetDlgItemTextW` at `0x1800149a3`

## pseudocode

```c
__int64 __fastcall CConfigAdvancedPage::OnApply(CConfigAdvancedPage *this, HWND a2, int *a3)
{
  unsigned int OutboxConfiguration; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids);
  }
  *a3 = 0;
  if ( !*((_DWORD *)this + 144) )
    return 0;
  if ( *((_DWORD *)this + 140) )
    GetDlgItemTextW(a2, 4521, (LPWSTR)this + 20, 260);
  OutboxConfiguration = CConfigAdvancedPage::ReadOutboxConfiguration(this, a2);
  v8 = OutboxConfiguration;
  if ( OutboxConfiguration )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v10 = 30;
LABEL_25:
    WPP_SF_d(v9[2], v10, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids, OutboxConfiguration);
LABEL_26:
    *a3 = 1;
    (*(__int64 (__fastcall **)(CConfigAdvancedPage *, _QWORD))(*(_QWORD *)this + 48LL))(this, v8);
    FaxMsgBox(a2, *((_QWORD *)this + 1), 4656);
    return v8;
  }
  if ( *((_DWORD *)this + 140) )
  {
    OutboxConfiguration = CConfigAdvancedPage::SetArchiveSettings(this);
    v8 = OutboxConfiguration;
    if ( OutboxConfiguration )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_26;
      }
      v10 = 31;
      goto LABEL_25;
    }
  }
  OutboxConfiguration = CConfigAdvancedPage::SetOutboxConfiguration(this);
  v8 = OutboxConfiguration;
  if ( OutboxConfiguration )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v10 = 32;
    goto LABEL_25;
  }
  return v8;
}

```

## disassembly

```asm
0x180014920  push    rbx
0x180014922  push    rsi
0x180014923  push    rdi
0x180014924  push    r12
0x180014926  push    r14
0x180014928  push    r15
0x18001492a  sub     rsp, 38h
0x18001492e  mov     r14, r8
0x180014931  mov     rsi, rdx
0x180014934  mov     rdi, rcx
0x180014937  mov     rcx, cs:WPP_GLOBAL_Control
0x18001493e  lea     r12, WPP_GLOBAL_Control
0x180014945  mov     r15d, 100h
0x18001494b  cmp     rcx, r12
0x18001494e  jz      short loc_180014971
0x180014950  test    [rcx+1Ch], r15d
0x180014954  jz      short loc_180014971
0x180014956  cmp     byte ptr [rcx+19h], 5
0x18001495a  jb      short loc_180014971
0x18001495c  mov     rcx, [rcx+10h]
0x180014960  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x180014967  mov     edx, 1Dh
0x18001496c  call    WPP_SF_
0x180014971  mov     dword ptr [r14], 0
0x180014978  cmp     dword ptr [rdi+240h], 0
0x18001497f  jnz     short loc_180014988
0x180014981  xor     eax, eax
0x180014983  jmp     loc_180014ABA
0x180014988  cmp     dword ptr [rdi+230h], 0
0x18001498f  jz      short loc_1800149A9
0x180014991  lea     r8, [rdi+28h]; lpString
0x180014995  mov     edx, 11A9h; nIDDlgItem
0x18001499a  mov     r9d, 104h; cchMax
0x1800149a0  mov     rcx, rsi; hDlg
0x1800149a3  call    cs:__imp_GetDlgItemTextW
0x1800149a9  mov     rdx, rsi; HWND
0x1800149ac  mov     rcx, rdi; this
0x1800149af  call    ?ReadOutboxConfiguration@CConfigAdvancedPage@@AEAAKPEAUHWND__@@@Z; CConfigAdvancedPage::ReadOutboxConfiguration(HWND__ *)
0x1800149b4  mov     ebx, eax
0x1800149b6  test    eax, eax
0x1800149b8  jz      short loc_1800149E1
0x1800149ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149c1  cmp     rcx, r12
0x1800149c4  jz      loc_180014A59
0x1800149ca  test    [rcx+1Ch], r15d
0x1800149ce  jz      loc_180014A59
0x1800149d4  cmp     byte ptr [rcx+19h], 2
0x1800149d8  jb      short loc_180014A59
0x1800149da  mov     edx, 1Eh
0x1800149df  jmp     short loc_180014A46
0x1800149e1  cmp     dword ptr [rdi+230h], 0
0x1800149e8  jz      short loc_180014A17
0x1800149ea  mov     rcx, rdi; this
0x1800149ed  call    ?SetArchiveSettings@CConfigAdvancedPage@@AEBAKXZ; CConfigAdvancedPage::SetArchiveSettings(void)
0x1800149f2  mov     ebx, eax
0x1800149f4  test    eax, eax
0x1800149f6  jz      short loc_180014A17
0x1800149f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149ff  cmp     rcx, r12
0x180014a02  jz      short loc_180014A59
0x180014a04  test    [rcx+1Ch], r15d
0x180014a08  jz      short loc_180014A59
0x180014a0a  cmp     byte ptr [rcx+19h], 2
0x180014a0e  jb      short loc_180014A59
0x180014a10  mov     edx, 1Fh
0x180014a15  jmp     short loc_180014A46
0x180014a17  mov     rcx, rdi; this
0x180014a1a  call    ?SetOutboxConfiguration@CConfigAdvancedPage@@AEBAKXZ; CConfigAdvancedPage::SetOutboxConfiguration(void)
0x180014a1f  mov     ebx, eax
0x180014a21  test    eax, eax
0x180014a23  jz      loc_180014AB8
0x180014a29  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a30  cmp     rcx, r12
0x180014a33  jz      short loc_180014A59
0x180014a35  test    [rcx+1Ch], r15d
0x180014a39  jz      short loc_180014A59
0x180014a3b  cmp     byte ptr [rcx+19h], 2
0x180014a3f  jb      short loc_180014A59
0x180014a41  mov     edx, 20h ; ' '
0x180014a46  mov     rcx, [rcx+10h]
0x180014a4a  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x180014a51  mov     r9d, eax
0x180014a54  call    WPP_SF_d
0x180014a59  mov     dword ptr [r14], 1
0x180014a60  mov     edx, ebx
0x180014a62  mov     rax, [rdi]
0x180014a65  mov     rcx, rdi
0x180014a68  mov     rax, [rax+30h]
0x180014a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a71  test    eax, eax
0x180014a73  jnz     short loc_180014A9B
0x180014a75  cmp     ebx, 5
0x180014a78  jz      short loc_180014A96
0x180014a7a  cmp     ebx, 8
0x180014a7d  jz      short loc_180014A8F
0x180014a7f  mov     eax, 1234h
0x180014a84  cmp     ebx, 7Ah ; 'z'
0x180014a87  lea     ecx, [rax+2]
0x180014a8a  cmovnz  eax, ecx
0x180014a8d  jmp     short loc_180014A9B
0x180014a8f  mov     eax, 1237h
0x180014a94  jmp     short loc_180014A9B
0x180014a96  mov     eax, 1235h
0x180014a9b  mov     rdx, [rdi+8]
0x180014a9f  mov     r9d, eax
0x180014aa2  mov     r8d, 1230h
0x180014aa8  mov     [rsp+68h+var_48], 10h
0x180014ab0  mov     rcx, rsi
0x180014ab3  call    FaxMsgBox
0x180014ab8  mov     eax, ebx
0x180014aba  add     rsp, 38h
0x180014abe  pop     r15
0x180014ac0  pop     r14
0x180014ac2  pop     r12
0x180014ac4  pop     rdi
0x180014ac5  pop     rsi
0x180014ac6  pop     rbx
0x180014ac7  retn
```
