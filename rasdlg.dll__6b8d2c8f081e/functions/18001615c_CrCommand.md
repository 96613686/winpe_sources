# CrCommand

- ea: `0x18001615c`
- end: `0x1800162c4`
- name: `CrCommand`
- size: `360`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800162d0`

## callees

- `0x18001615c`
- `0x1800165b4`
- `0x180016650`
- `0x1800286ec`
- `0x1800287c0`
- `0x18004d0d2`

## import_xrefs

- `USER32!SendMessageW` at `0x180016225`
- `USER32!SendMessageW` at `0x180016260`
- `USER32!SendMessageW` at `0x180016225`
- `USER32!SendMessageW` at `0x180016260`
- `USER32!EndDialog` at `0x1800162ad`
- `USER32!EndDialog` at `0x1800162ad`
- `rtutils!TracePrintfExA` at `0x18001619a`
- `rtutils!TracePrintfExA` at `0x18001627b`
- `rtutils!TracePrintfExA` at `0x180016296`
- `rtutils!TracePrintfExA` at `0x18001619a`
- `rtutils!TracePrintfExA` at `0x18001627b`
- `rtutils!TracePrintfExA` at `0x180016296`

## string_xrefs

- `0x180016187`: `CrCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall CrCommand(__int64 a1, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  DWORD v6; // ecx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  HWND v14; // rcx
  INT_PTR v16; // rdx
  LPARAM lParam; // [rsp+30h] [rbp-88h] BYREF
  int v18; // [rsp+3Ch] [rbp-7Ch]
  int v19; // [rsp+40h] [rbp-78h]

  v6 = g_dwTraceId;
  v8 = a3;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "CrCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
    v6 = g_dwTraceId;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "OK pressed");
    CrSave(a1);
    v16 = 1;
    goto LABEL_24;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "Cancel pressed");
    v16 = 0;
LABEL_24:
    EndDialog(*(HWND *)(a1 + 8), v16);
    return 1;
  }
  v11 = v10 - 1499;
  if ( v11 && (v12 = v11 - 1) != 0 )
  {
    v13 = v12 - 2;
    if ( v13 )
    {
      if ( v13 == 1 && !a2 )
        CbutilDelete(*(HWND *)(a1 + 8), *(HWND *)(a1 + 32));
    }
    else if ( !a2 )
    {
      CbutilEdit(*(HWND *)(a1 + 8), *(HWND *)(a1 + 32));
    }
  }
  else if ( !a2 )
  {
    CrUpdateLvAndPbState(a1);
    if ( a3 == 1502 && !(unsigned int)SendMessageW(*(HWND *)(a1 + 32), 0x1032u, 0, 0) )
    {
      memset_0(&lParam, 0, 0x58u);
      v14 = *(HWND *)(a1 + 32);
      v19 = 2;
      v18 = 2;
      SendMessageW(v14, 0x102Bu, 0, (LPARAM)&lParam);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001615c  push    rbx
0x18001615e  push    rbp
0x18001615f  push    rsi
0x180016160  push    rdi
0x180016161  sub     rsp, 98h
0x180016168  mov     rdi, rcx
0x18001616b  movzx   ebp, r8w
0x18001616f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180016175  mov     rax, r9
0x180016178  movzx   esi, dx
0x18001617b  mov     ebx, ebp
0x18001617d  cmp     ecx, 0FFFFFFFFh
0x180016180  jz      short loc_1800161A6
0x180016182  mov     [rsp+0B8h+var_90], rax
0x180016187  lea     r8, aCrcommandNDIDC; "CrCommand(n=%d,i=%d,c=$%x)"
0x18001618e  mov     r9d, esi
0x180016191  mov     [rsp+0B8h+var_98], ebx
0x180016195  mov     edx, 0Ch; dwFlags
0x18001619a  call    cs:__imp_TracePrintfExA
0x1800161a0  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800161a6  sub     ebx, 1
0x1800161a9  jz      loc_180016285
0x1800161af  sub     ebx, 1
0x1800161b2  jz      loc_18001626A
0x1800161b8  sub     ebx, 5DBh
0x1800161be  jz      short loc_1800161FF
0x1800161c0  sub     ebx, 1
0x1800161c3  jz      short loc_1800161FF
0x1800161c5  sub     ebx, 2
0x1800161c8  jz      short loc_1800161EB
0x1800161ca  cmp     ebx, 1
0x1800161cd  jnz     loc_180016266
0x1800161d3  test    si, si
0x1800161d6  jnz     loc_180016266
0x1800161dc  mov     rdx, [rdi+20h]; HWND
0x1800161e0  mov     rcx, [rdi+8]; hWnd
0x1800161e4  call    CbutilDelete
0x1800161e9  jmp     short loc_180016266
0x1800161eb  test    si, si
0x1800161ee  jnz     short loc_180016266
0x1800161f0  mov     rdx, [rdi+20h]; HWND
0x1800161f4  mov     rcx, [rdi+8]; hWnd
0x1800161f8  call    CbutilEdit
0x1800161fd  jmp     short loc_180016266
0x1800161ff  test    si, si
0x180016202  jnz     short loc_180016266
0x180016204  mov     rcx, rdi
0x180016207  call    CrUpdateLvAndPbState
0x18001620c  mov     eax, 5DEh
0x180016211  cmp     bp, ax
0x180016214  jnz     short loc_180016266
0x180016216  mov     rcx, [rdi+20h]; hWnd
0x18001621a  xor     r9d, r9d; lParam
0x18001621d  xor     r8d, r8d; wParam
0x180016220  mov     edx, 1032h; Msg
0x180016225  call    cs:__imp_SendMessageW
0x18001622b  test    eax, eax
0x18001622d  jnz     short loc_180016266
0x18001622f  xor     edx, edx; Val
0x180016231  lea     r8d, [rax+58h]; Size
0x180016235  lea     rcx, [rsp+0B8h+lParam]; void *
0x18001623a  call    memset_0
0x18001623f  mov     rcx, [rdi+20h]; hWnd
0x180016243  lea     r9, [rsp+0B8h+lParam]; lParam
0x180016248  xor     r8d, r8d; wParam
0x18001624b  mov     [rsp+0B8h+var_78], 2
0x180016253  mov     edx, 102Bh; Msg
0x180016258  mov     [rsp+0B8h+var_7C], 2
0x180016260  call    cs:__imp_SendMessageW
0x180016266  xor     eax, eax
0x180016268  jmp     short loc_1800162B8
0x18001626a  cmp     ecx, 0FFFFFFFFh
0x18001626d  jz      short loc_180016281
0x18001626f  lea     r8, aCancelPressed; "Cancel pressed"
0x180016276  mov     edx, 0Ch; dwFlags
0x18001627b  call    cs:__imp_TracePrintfExA
0x180016281  xor     edx, edx
0x180016283  jmp     short loc_1800162A9
0x180016285  cmp     ecx, 0FFFFFFFFh
0x180016288  jz      short loc_18001629C
0x18001628a  lea     r8, aOkPressed; "OK pressed"
0x180016291  mov     edx, 0Ch; dwFlags
0x180016296  call    cs:__imp_TracePrintfExA
0x18001629c  mov     rcx, rdi
0x18001629f  call    CrSave
0x1800162a4  mov     edx, 1; nResult
0x1800162a9  mov     rcx, [rdi+8]; hDlg
0x1800162ad  call    cs:__imp_EndDialog
0x1800162b3  mov     eax, 1
0x1800162b8  add     rsp, 98h
0x1800162bf  pop     rdi
0x1800162c0  pop     rsi
0x1800162c1  pop     rbp
0x1800162c2  pop     rbx
0x1800162c3  retn
```
