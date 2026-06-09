# CMessageDlg::_OnCommand(unsigned __int64,__int64)

- ea: `0x140002270`
- end: `0x140002296`
- name: `?_OnCommand@CMessageDlg@@EEAA_N_K_J@Z`
- size: `38`
- prototype: `bool __fastcall(CMessageDlg *__hidden this, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002270`

## import_xrefs

- `USER32!EndDialog` at `0x140002288`
- `USER32!EndDialog` at `0x140002288`

## pseudocode

```c
char __fastcall CMessageDlg::_OnCommand(HWND *this, __int16 a2)
{
  char v2; // bl

  if ( a2 != 2 )
    return 1;
  v2 = 0;
  EndDialog(this[1], 0);
  return v2;
}

```

## disassembly

```asm
0x140002270  push    rbx
0x140002272  sub     rsp, 20h
0x140002276  cmp     dx, 2
0x14000227a  jz      short loc_140002280
0x14000227c  mov     bl, 1
0x14000227e  jmp     short loc_14000228E
0x140002280  mov     rcx, [rcx+8]; hDlg
0x140002284  xor     bl, bl
0x140002286  xor     edx, edx; nResult
0x140002288  call    cs:__imp_EndDialog
0x14000228e  mov     al, bl
0x140002290  add     rsp, 20h
0x140002294  pop     rbx
0x140002295  retn
```
