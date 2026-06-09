# RepopulatePurposeCombo(HWND__ *,_CERT_MGR_INFO *)

- ea: `0x180022178`
- end: `0x18002224a`
- name: `?RepopulatePurposeCombo@@YAXPEAUHWND__@@PEAU_CERT_MGR_INFO@@@Z`
- size: `210`
- prototype: `void __fastcall(HWND hDlg, struct _CERT_MGR_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001fda0`

## callees

- `0x180021810`
- `0x180022178`
- `0x18003317c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022234`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022234`
- `USER32!SendDlgItemMessageA` at `0x1800221be`
- `USER32!SendDlgItemMessageA` at `0x1800221be`
- `USER32!SendDlgItemMessageW` at `0x180022206`
- `USER32!SendDlgItemMessageW` at `0x18002222b`
- `USER32!SendDlgItemMessageW` at `0x180022206`
- `USER32!SendDlgItemMessageW` at `0x18002222b`

## pseudocode

```c
void __fastcall RepopulatePurposeCombo(HWND hDlg, struct _CERT_MGR_INFO *a2)
{
  int v4; // eax
  int v5; // edx
  __int64 v6; // rax
  void *lParam; // rsi
  int v8; // eax
  LPARAM v9; // [rsp+40h] [rbp+8h] BYREF

  if ( hDlg )
  {
    v9 = 0;
    if ( a2 )
    {
      v4 = SendDlgItemMessageA(hDlg, 1112, 0x147u, 0, 0);
      if ( v4 != -1 )
      {
        v6 = SendDlgItemMessageU_GETLBTEXT(hDlg, v5, v4, (unsigned __int16 **)&v9);
        lParam = (void *)v9;
        if ( v6 != -1 )
        {
          InitPurposeCombo(hDlg, a2);
          v8 = SendDlgItemMessageW(hDlg, 1112, 0x158u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)lParam);
          if ( v8 != -1 )
            SendDlgItemMessageW(hDlg, 1112, 0x14Eu, v8, 0);
        }
        LocalFree(lParam);
      }
    }
  }
}

```

## disassembly

```asm
0x180022178  test    rcx, rcx
0x18002217b  jz      locret_180022249
0x180022181  mov     rax, rsp
0x180022184  mov     [rax+10h], rbx
0x180022188  mov     [rax+18h], rsi
0x18002218c  push    rdi
0x18002218d  sub     rsp, 30h
0x180022191  mov     qword ptr [rax+8], 0
0x180022199  mov     rdi, rdx
0x18002219c  mov     rbx, rcx
0x18002219f  test    rdx, rdx
0x1800221a2  jz      loc_18002223A
0x1800221a8  xor     r9d, r9d; wParam
0x1800221ab  mov     qword ptr [rax-18h], 0
0x1800221b3  mov     edx, 458h; nIDDlgItem
0x1800221b8  mov     r8d, 147h; Msg
0x1800221be  call    cs:__imp_SendDlgItemMessageA
0x1800221c4  cmp     eax, 0FFFFFFFFh
0x1800221c7  jz      short loc_18002223A
0x1800221c9  lea     r9, [rsp+38h+arg_0]; unsigned __int16 **
0x1800221ce  mov     r8d, eax; int
0x1800221d1  mov     rcx, rbx; hDlg
0x1800221d4  call    ?SendDlgItemMessageU_GETLBTEXT@@YA_JPEAUHWND__@@HHPEAPEAG@Z; SendDlgItemMessageU_GETLBTEXT(HWND__ *,int,int,ushort * *)
0x1800221d9  mov     rsi, [rsp+38h+arg_0]
0x1800221de  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800221e2  jz      short loc_180022231
0x1800221e4  mov     rdx, rdi; struct _CERT_MGR_INFO *
0x1800221e7  mov     rcx, rbx; hDlg
0x1800221ea  call    ?InitPurposeCombo@@YAXPEAUHWND__@@PEAU_CERT_MGR_INFO@@@Z; InitPurposeCombo(HWND__ *,_CERT_MGR_INFO *)
0x1800221ef  or      r9, 0FFFFFFFFFFFFFFFFh; wParam
0x1800221f3  mov     [rsp+38h+lParam], rsi; lParam
0x1800221f8  mov     edx, 458h; nIDDlgItem
0x1800221fd  mov     r8d, 158h; Msg
0x180022203  mov     rcx, rbx; hDlg
0x180022206  call    cs:__imp_SendDlgItemMessageW
0x18002220c  cmp     eax, 0FFFFFFFFh
0x18002220f  jz      short loc_180022231
0x180022211  movsxd  r9, eax; wParam
0x180022214  mov     edx, 458h; nIDDlgItem
0x180022219  mov     r8d, 14Eh; Msg
0x18002221f  mov     [rsp+38h+lParam], 0; lParam
0x180022228  mov     rcx, rbx; hDlg
0x18002222b  call    cs:__imp_SendDlgItemMessageW
0x180022231  mov     rcx, rsi; hMem
0x180022234  call    cs:__imp_LocalFree
0x18002223a  mov     rbx, [rsp+38h+arg_8]
0x18002223f  mov     rsi, [rsp+38h+arg_10]
0x180022244  add     rsp, 30h
0x180022248  pop     rdi
0x180022249  retn
```
