# CAddPort::EditBoxSubclassWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180028ae0`
- end: `0x180028beb`
- name: `?EditBoxSubclassWndProc@CAddPort@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `267`
- prototype: `LRESULT __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180028ae0`
- `0x180028bf4`
- `0x1800299ac`

## import_xrefs

- `USER32!CallWindowProcW` at `0x180028b60`
- `USER32!CallWindowProcW` at `0x180028b60`
- `USER32!GetPropW` at `0x180028aff`
- `USER32!GetPropW` at `0x180028aff`
- `USER32!RemovePropW` at `0x180028be0`
- `USER32!RemovePropW` at `0x180028be0`
- `USER32!MessageBeep` at `0x180028bc8`
- `USER32!MessageBeep` at `0x180028bc8`
- `USER32!GetKeyState` at `0x180028b78`
- `USER32!GetKeyState` at `0x180028b8a`
- `USER32!GetKeyState` at `0x180028b78`
- `USER32!GetKeyState` at `0x180028b8a`

## pseudocode

```c
LRESULT __fastcall CAddPort::EditBoxSubclassWndProc(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  WNDPROC *PropW; // rax
  WNDPROC *v9; // rdi
  __int64 v11; // rcx

  PropW = (WNDPROC *)GetPropW(hWnd, L"pThis");
  v9 = PropW;
  switch ( Msg )
  {
    case 8u:
      goto LABEL_9;
    case 0x82u:
      RemovePropW(hWnd, L"pThis");
      return CallWindowProcW(v9[12], hWnd, Msg, wParam, lParam);
    case 0x100u:
      goto LABEL_9;
    case 0x102u:
      if ( GetKeyState(17) >= 0 && GetKeyState(18) >= 0 )
      {
        if ( (unsigned __int16)wParam > 0x39u || (v11 = 0x3FF000000002100LL, !_bittest64(&v11, wParam)) )
        {
          CTooltip::ShowErrBalloon((CTooltip *)(v9 + 16), 0x667u, 0x3Bu, 0x3Cu);
          MessageBeep(0);
          wParam = 0;
        }
      }
      break;
    case 0x201u:
    case 0x204u:
    case 0x207u:
    case 0x20Au:
LABEL_9:
      CTooltip::HideBalloon((CTooltip *)(PropW + 16));
      break;
  }
  return CallWindowProcW(v9[12], hWnd, Msg, wParam, lParam);
}

```

## disassembly

```asm
0x180028ae0  push    rbx
0x180028ae2  push    rbp
0x180028ae3  push    rsi
0x180028ae4  push    rdi
0x180028ae5  push    r14
0x180028ae7  push    r15
0x180028ae9  sub     rsp, 38h
0x180028aed  mov     ebp, edx
0x180028aef  mov     r14, r9
0x180028af2  lea     rdx, aPthis; "pThis"
0x180028af9  mov     rbx, r8
0x180028afc  mov     rsi, rcx
0x180028aff  call    cs:__imp_GetPropW
0x180028b05  mov     r10d, ebp
0x180028b08  mov     rdi, rax
0x180028b0b  sub     r10d, 8
0x180028b0f  jz      short loc_180028B42
0x180028b11  sub     r10d, 7Ah ; 'z'
0x180028b15  jz      loc_180028BD6
0x180028b1b  sub     r10d, 7Eh ; '~'
0x180028b1f  jz      short loc_180028B42
0x180028b21  sub     r10d, 2
0x180028b25  jz      short loc_180028B73
0x180028b27  sub     r10d, 0FFh
0x180028b2e  jz      short loc_180028B42
0x180028b30  sub     r10d, 3
0x180028b34  jz      short loc_180028B42
0x180028b36  sub     r10d, 3
0x180028b3a  jz      short loc_180028B42
0x180028b3c  cmp     r10d, 3
0x180028b40  jnz     short loc_180028B4E
0x180028b42  lea     rcx, [rax+80h]; this
0x180028b49  call    ?HideBalloon@CTooltip@@QEAAXXZ; CTooltip::HideBalloon(void)
0x180028b4e  mov     rcx, [rdi+60h]; lpPrevWndFunc
0x180028b52  mov     r9, rbx; wParam
0x180028b55  mov     r8d, ebp; Msg
0x180028b58  mov     [rsp+68h+lParam], r14; lParam
0x180028b5d  mov     rdx, rsi; hWnd
0x180028b60  call    cs:__imp_CallWindowProcW
0x180028b66  add     rsp, 38h
0x180028b6a  pop     r15
0x180028b6c  pop     r14
0x180028b6e  pop     rdi
0x180028b6f  pop     rsi
0x180028b70  pop     rbp
0x180028b71  pop     rbx
0x180028b72  retn
0x180028b73  mov     ecx, 11h; nVirtKey
0x180028b78  call    cs:__imp_GetKeyState
0x180028b7e  xor     r15d, r15d
0x180028b81  test    ax, ax
0x180028b84  js      short loc_180028B4E
0x180028b86  lea     ecx, [r15+12h]; nVirtKey
0x180028b8a  call    cs:__imp_GetKeyState
0x180028b90  test    ax, ax
0x180028b93  js      short loc_180028B4E
0x180028b95  cmp     bx, 39h ; '9'
0x180028b99  ja      short loc_180028BAB
0x180028b9b  mov     rcx, 3FF000000002100h
0x180028ba5  bt      rcx, rbx
0x180028ba9  jb      short loc_180028B4E
0x180028bab  mov     r9d, 3Ch ; '<'; unsigned int
0x180028bb1  lea     rcx, [rdi+80h]; this
0x180028bb8  mov     edx, 667h; unsigned int
0x180028bbd  lea     r8d, [r9-1]; unsigned int
0x180028bc1  call    ?ShowErrBalloon@CTooltip@@QEAAXIIIZZ; CTooltip::ShowErrBalloon(uint,uint,uint,...)
0x180028bc6  xor     ecx, ecx; uType
0x180028bc8  call    cs:__imp_MessageBeep
0x180028bce  mov     rbx, r15
0x180028bd1  jmp     loc_180028B4E
0x180028bd6  lea     rdx, aPthis; "pThis"
0x180028bdd  mov     rcx, rsi; hWnd
0x180028be0  call    cs:__imp_RemovePropW
0x180028be6  jmp     loc_180028B4E
```
