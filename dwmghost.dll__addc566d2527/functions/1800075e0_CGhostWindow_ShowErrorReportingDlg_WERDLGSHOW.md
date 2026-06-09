# CGhostWindow::ShowErrorReportingDlg(WERDLGSHOW)

- ea: `0x1800075e0`
- end: `0x18000769b`
- name: `?ShowErrorReportingDlg@CGhostWindow@@IEAAJW4WERDLGSHOW@@@Z`
- size: `187`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180006bb8`
- `0x180007190`
- `0x180007280`
- `0x1800072d0`
- `0x18000a020`

## callees

- `0x180006bac`
- `0x1800075e0`
- `0x1800076a4`
- `0x180008dfc`
- `0x1800092a8`
- `0x1800097dc`

## pseudocode

```c
__int64 __fastcall CGhostWindow::ShowErrorReportingDlg(LPARAM a1, unsigned int a2)
{
  int v4; // edx
  __int64 v5; // rcx
  CGhostProcess **v6; // rsi
  int v7; // r8d

  if ( (unsigned int)CGhostWindow::GetState(a1) != 2 )
    return 1;
  v6 = (CGhostProcess **)(v5 + 16);
  v7 = -2147467259;
  if ( v4 == 2 )
  {
    CGhostProcess::CallReportHang(*v6, *(HWND *)(v5 + 40));
    goto LABEL_4;
  }
  if ( !a2 )
    return (unsigned int)CGhostProcess::ShowWerDlg(*v6, a1, a2);
  if ( a2 != 1 && a2 != 2 )
  {
    if ( a2 != 3 )
      return (unsigned int)v7;
    return (unsigned int)CGhostProcess::ShowWerDlg(*v6, a1, a2);
  }
LABEL_4:
  if ( !(unsigned int)CGhostProcess::HasErrorReportingStarted(*v6) && *(_DWORD *)(a1 + 216) )
    return 1;
  v7 = CGhostProcess::ShowWerDlg(*v6, a1, a2);
  if ( v7 < 0 && a2 == 2 && *(_DWORD *)(a1 + 24) == 1 )
    return (unsigned int)CGhostWindow::ShowTerminateDlg(a1);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800075e0  mov     [rsp+arg_0], rbx
0x1800075e5  mov     [rsp+arg_8], rsi
0x1800075ea  push    rdi
0x1800075eb  sub     rsp, 20h
0x1800075ef  mov     edi, edx
0x1800075f1  mov     rbx, rcx
0x1800075f4  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x1800075f9  cmp     eax, 2
0x1800075fc  jnz     loc_180007682
0x180007602  lea     rsi, [rcx+10h]
0x180007606  mov     r8d, 80004005h
0x18000760c  cmp     edx, eax
0x18000760e  jnz     short loc_18000765A
0x180007610  mov     rdx, [rcx+28h]; HWND
0x180007614  mov     rcx, [rsi]; this
0x180007617  call    ?CallReportHang@CGhostProcess@@QEAAHPEAUHWND__@@@Z; CGhostProcess::CallReportHang(HWND__ *)
0x18000761c  mov     rcx, [rsi]; this
0x18000761f  call    ?HasErrorReportingStarted@CGhostProcess@@QEAAHXZ; CGhostProcess::HasErrorReportingStarted(void)
0x180007624  test    eax, eax
0x180007626  jnz     short loc_180007630
0x180007628  cmp     [rbx+0D8h], eax
0x18000762e  jnz     short loc_180007682
0x180007630  mov     rcx, [rsi]
0x180007633  mov     r8d, edi
0x180007636  mov     rdx, rbx
0x180007639  call    ?ShowWerDlg@CGhostProcess@@QEAAJPEAVCGhostWindow@@W4WERDLGSHOW@@@Z; CGhostProcess::ShowWerDlg(CGhostWindow *,WERDLGSHOW)
0x18000763e  mov     r8d, eax
0x180007641  test    eax, eax
0x180007643  jns     short loc_180007688
0x180007645  cmp     edi, 2
0x180007648  jnz     short loc_180007688
0x18000764a  cmp     dword ptr [rbx+18h], 1
0x18000764e  jnz     short loc_180007688
0x180007650  mov     rcx, rbx; dwInitParam
0x180007653  call    ?ShowTerminateDlg@CGhostWindow@@AEAAJXZ; CGhostWindow::ShowTerminateDlg(void)
0x180007658  jmp     short loc_18000767D
0x18000765a  mov     ecx, edi
0x18000765c  test    edi, edi
0x18000765e  jz      short loc_18000766F
0x180007660  sub     ecx, 1
0x180007663  jz      short loc_18000761C
0x180007665  sub     ecx, 1
0x180007668  jz      short loc_18000761C
0x18000766a  cmp     ecx, 1
0x18000766d  jnz     short loc_180007688
0x18000766f  mov     rcx, [rsi]
0x180007672  mov     r8d, edi
0x180007675  mov     rdx, rbx
0x180007678  call    ?ShowWerDlg@CGhostProcess@@QEAAJPEAVCGhostWindow@@W4WERDLGSHOW@@@Z; CGhostProcess::ShowWerDlg(CGhostWindow *,WERDLGSHOW)
0x18000767d  mov     r8d, eax
0x180007680  jmp     short loc_180007688
0x180007682  mov     r8d, 1
0x180007688  mov     rbx, [rsp+28h+arg_0]
0x18000768d  mov     eax, r8d
0x180007690  mov     rsi, [rsp+28h+arg_8]
0x180007695  add     rsp, 20h
0x180007699  pop     rdi
0x18000769a  retn
```
