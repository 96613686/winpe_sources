# CChooserDlg::OnChooseTargetMachine(CComponentData *,__int64,IDataObject *)

- ea: `0x1800214b8`
- end: `0x18002157d`
- name: `?OnChooseTargetMachine@CChooserDlg@@SAXPEAVCComponentData@@_JPEAUIDataObject@@@Z`
- size: `197`
- prototype: `void __fastcall(struct CComponentData *, __int64, struct IDataObject *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800056c0`

## callees

- `0x180005f64`
- `0x18000bfe0`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180021526`
- `msvcrt!wcsncpy_s` at `0x180021526`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CChooserDlg::OnChooseTargetMachine(struct CComponentData *a1, __int64 a2, struct IDataObject *a3)
{
  wchar_t *CurrentFocus; // rax
  const wchar_t *v5; // r8
  HWND v6[2]; // [rsp+20h] [rbp-268h] BYREF
  _QWORD v7[5]; // [rsp+30h] [rbp-258h] BYREF
  wchar_t Destination[264]; // [rsp+58h] [rbp-230h] BYREF
  int v9; // [rsp+268h] [rbp-20h]

  v7[1] = 0;
  v7[0] = &CChooserDlg::`vftable';
  v7[2] = a1;
  v7[3] = a2;
  v7[4] = a3;
  v9 = 0;
  CurrentFocus = CComponentData::GetCurrentFocus(a1);
  v5 = &String;
  if ( CurrentFocus )
    v5 = CurrentFocus;
  wcsncpy_s(Destination, 0x108u, v5, 0xFFFFFFFFFFFFFFFFuLL);
  v6[0] = 0;
  (*(void (__fastcall **)(_QWORD, HWND *))(**((_QWORD **)a1 + 144) + 96LL))(*((_QWORD *)a1 + 144), v6);
  CDlg::_DoModalDlg((CDlg *)v7, v6[0], 971);
}

```

## disassembly

```asm
0x1800214b8  push    rbx
0x1800214ba  sub     rsp, 280h
0x1800214c1  mov     rax, cs:__security_cookie
0x1800214c8  xor     rax, rsp
0x1800214cb  mov     [rsp+288h+var_18], rax
0x1800214d3  mov     rbx, rcx
0x1800214d6  mov     [rsp+288h+var_250], 0
0x1800214df  lea     rax, ??_7CChooserDlg@@6B@; const CChooserDlg::`vftable'
0x1800214e6  mov     [rsp+288h+var_258], rax
0x1800214eb  mov     [rsp+288h+var_248], rcx
0x1800214f0  mov     [rsp+288h+var_240], rdx
0x1800214f5  mov     [rsp+288h+var_238], r8
0x1800214fa  mov     [rsp+288h+var_20], 0
0x180021505  call    ?GetCurrentFocus@CComponentData@@QEAAPEBGXZ; CComponentData::GetCurrentFocus(void)
0x18002150a  lea     r8, String
0x180021511  test    rax, rax
0x180021514  cmovnz  r8, rax; Source
0x180021518  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18002151c  mov     edx, 108h; SizeInWords
0x180021521  lea     rcx, [rsp+288h+Destination]; Destination
0x180021526  call    cs:__imp_wcsncpy_s
0x18002152c  nop
0x18002152d  mov     [rsp+288h+var_268], 0
0x180021536  mov     rcx, [rbx+480h]
0x18002153d  mov     rax, [rcx]
0x180021540  lea     rdx, [rsp+288h+var_268]
0x180021545  mov     rax, [rax+60h]
0x180021549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002154e  mov     r8d, 3CBh; int
0x180021554  mov     rdx, [rsp+288h+var_268]; HWND
0x180021559  lea     rcx, [rsp+288h+var_258]; this
0x18002155e  call    ?_DoModalDlg@CDlg@@IEAA_JPEAUHWND__@@H@Z; CDlg::_DoModalDlg(HWND__ *,int)
0x180021563  nop
0x180021564  mov     rcx, [rsp+288h+var_18]
0x18002156c  xor     rcx, rsp; StackCookie
0x18002156f  call    __security_check_cookie
0x180021574  add     rsp, 280h
0x18002157b  pop     rbx
0x18002157c  retn
```
