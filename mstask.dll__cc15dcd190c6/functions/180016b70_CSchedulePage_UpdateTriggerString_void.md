# CSchedulePage::_UpdateTriggerString(void)

- ea: `0x180016b70`
- end: `0x180016c7c`
- name: `?_UpdateTriggerString@CSchedulePage@@AEAAXXZ`
- size: `268`
- prototype: `void __fastcall(CSchedulePage *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180014aa0`
- `0x1800159c0`
- `0x180015af0`
- `0x180015db8`

## callees

- `0x180013504`
- `0x180016b70`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `USER32!SendMessageW` at `0x180016bf9`
- `USER32!SendMessageW` at `0x180016c13`
- `USER32!SendMessageW` at `0x180016c2b`
- `USER32!SendMessageW` at `0x180016c43`
- `USER32!SendMessageW` at `0x180016bf9`
- `USER32!SendMessageW` at `0x180016c13`
- `USER32!SendMessageW` at `0x180016c2b`
- `USER32!SendMessageW` at `0x180016c43`
- `USER32!GetDlgItem` at `0x180016bd9`
- `USER32!GetDlgItem` at `0x180016bd9`
- `USER32!SetDlgItemTextW` at `0x180016c55`
- `USER32!SetDlgItemTextW` at `0x180016c55`

## pseudocode

```c
void __fastcall CSchedulePage::_UpdateTriggerString(CSchedulePage *this)
{
  CJobTrigger *v1; // rdi
  HWND v3; // rcx
  HWND DlgItem; // rax
  HWND v5; // rdi
  int v6; // eax
  WCHAR lParam[512]; // [rsp+20h] [rbp-418h] BYREF

  v1 = (CJobTrigger *)*((_QWORD *)this + 91);
  if ( v1 )
  {
    memset_0(lParam, 0, sizeof(lParam));
    CJobTrigger::TriggerString(v1, *((_DWORD *)this + 190), lParam);
    v3 = (HWND)*((_QWORD *)this + 14);
    if ( *((_DWORD *)this + 190) == 1 )
    {
      DlgItem = GetDlgItem(v3, 1692);
      v5 = DlgItem;
      if ( DlgItem )
      {
        SendMessageW(DlgItem, 0x144u, *((int *)this + 188), 0);
        v6 = SendMessageW(v5, 0x14Au, *((int *)this + 188), (LPARAM)lParam);
        SendMessageW(v5, 0x151u, v6, *((_QWORD *)this + 91));
        SendMessageW(v5, 0x14Eu, *((int *)this + 188), 0);
      }
    }
    else
    {
      SetDlgItemTextW(v3, 1693, lParam);
    }
  }
}

```

## disassembly

```asm
0x180016b70  mov     [rsp+arg_8], rbx
0x180016b75  push    rdi
0x180016b76  sub     rsp, 430h
0x180016b7d  mov     rax, cs:__security_cookie
0x180016b84  xor     rax, rsp
0x180016b87  mov     [rsp+438h+var_18], rax
0x180016b8f  mov     rdi, [rcx+2D8h]
0x180016b96  mov     rbx, rcx
0x180016b99  test    rdi, rdi
0x180016b9c  jz      loc_180016C5B
0x180016ba2  xor     edx, edx; Val
0x180016ba4  lea     rcx, [rsp+438h+lParam]; void *
0x180016ba9  mov     r8d, 400h; Size
0x180016baf  call    memset_0
0x180016bb4  mov     edx, [rbx+2F8h]; int
0x180016bba  lea     r8, [rsp+438h+lParam]; unsigned __int16 *
0x180016bbf  mov     rcx, rdi; this
0x180016bc2  call    ?TriggerString@CJobTrigger@@QEAAPEAGHQEAG_K@Z; CJobTrigger::TriggerString(int,ushort * const,unsigned __int64)
0x180016bc7  cmp     dword ptr [rbx+2F8h], 1
0x180016bce  mov     rcx, [rbx+70h]; hDlg
0x180016bd2  jnz     short loc_180016C4B
0x180016bd4  mov     edx, 69Ch; nIDDlgItem
0x180016bd9  call    cs:__imp_GetDlgItem
0x180016bdf  mov     rdi, rax
0x180016be2  test    rax, rax
0x180016be5  jz      short loc_180016C5B
0x180016be7  movsxd  r8, dword ptr [rbx+2F0h]; wParam
0x180016bee  xor     r9d, r9d; lParam
0x180016bf1  mov     edx, 144h; Msg
0x180016bf6  mov     rcx, rax; hWnd
0x180016bf9  call    cs:__imp_SendMessageW
0x180016bff  movsxd  r8, dword ptr [rbx+2F0h]; wParam
0x180016c06  lea     r9, [rsp+438h+lParam]; lParam
0x180016c0b  mov     edx, 14Ah; Msg
0x180016c10  mov     rcx, rdi; hWnd
0x180016c13  call    cs:__imp_SendMessageW
0x180016c19  mov     r9, [rbx+2D8h]; lParam
0x180016c20  mov     edx, 151h; Msg
0x180016c25  movsxd  r8, eax; wParam
0x180016c28  mov     rcx, rdi; hWnd
0x180016c2b  call    cs:__imp_SendMessageW
0x180016c31  movsxd  r8, dword ptr [rbx+2F0h]; wParam
0x180016c38  xor     r9d, r9d; lParam
0x180016c3b  mov     edx, 14Eh; Msg
0x180016c40  mov     rcx, rdi; hWnd
0x180016c43  call    cs:__imp_SendMessageW
0x180016c49  jmp     short loc_180016C5B
0x180016c4b  lea     r8, [rsp+438h+lParam]; lpString
0x180016c50  mov     edx, 69Dh; nIDDlgItem
0x180016c55  call    cs:__imp_SetDlgItemTextW
0x180016c5b  mov     rcx, [rsp+438h+var_18]
0x180016c63  xor     rcx, rsp; StackCookie
0x180016c66  call    __security_check_cookie
0x180016c6b  mov     rbx, [rsp+438h+arg_8]
0x180016c73  add     rsp, 430h
0x180016c7a  pop     rdi
0x180016c7b  retn
```
