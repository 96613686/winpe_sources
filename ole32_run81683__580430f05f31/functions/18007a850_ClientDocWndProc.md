# ClientDocWndProc

- ea: `0x18007a850`
- end: `0x18007aa8a`
- name: `ClientDocWndProc`
- size: `570`
- prototype: `LRESULT __fastcall(HWND hwnd, UINT message, HWND__ *wParam, unsigned __int64 lParam)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x180076468`
- `0x1800765ec`
- `0x1800769dc`
- `0x180076a38`
- `0x180077738`
- `0x180077768`
- `0x18007a818`
- `0x18007a850`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007aa1b`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007aa2d`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007aa1b`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007aa2d`
- `USER32!GetWindowLongPtrW` at `0x18007a88a`
- `USER32!GetWindowLongPtrW` at `0x18007a935`
- `USER32!GetWindowLongPtrW` at `0x18007a88a`
- `USER32!GetWindowLongPtrW` at `0x18007a935`
- `USER32!PostMessageW` at `0x18007aa63`
- `USER32!PostMessageW` at `0x18007aa63`
- `USER32!DefWindowProcW` at `0x18007a95b`
- `USER32!DefWindowProcW` at `0x18007a95b`
- `USER32!PeekMessageW` at `0x18007a8f6`
- `USER32!PeekMessageW` at `0x18007a926`
- `USER32!PeekMessageW` at `0x18007a8f6`
- `USER32!PeekMessageW` at `0x18007a926`
- `USER32!DispatchMessageW` at `0x18007a90a`
- `USER32!DispatchMessageW` at `0x18007a90a`

## pseudocode

```c
LRESULT __fastcall ClientDocWndProc(HWND hwnd, UINT message, HWND__ *wParam, unsigned __int64 lParam)
{
  LONG_PTR WindowLongPtrW; // rax
  CDdeObject *v9; // rbp
  __int64 v10; // rdi
  int v11; // eax
  LONG_PTR v12; // rax
  void *v14; // rbx
  unsigned __int16 v15; // ax
  unsigned __int64 v16; // rsi
  __int64 v17; // rax
  tagMSG msg; // [rsp+30h] [rbp-68h] BYREF

  UploadSQMData<enum Ole32SQMFlags>(OLEDDEUsage);
  if ( message - 992 > 8 )
  {
    v9 = 0;
    v10 = 0;
  }
  else
  {
    WindowLongPtrW = GetWindowLongPtrW(hwnd, 0);
    v9 = (CDdeObject *)WindowLongPtrW;
    if ( !WindowLongPtrW )
      return DefWindowProcW(hwnd, message, (WPARAM)wParam, lParam);
    v10 = *(_QWORD *)(WindowLongPtrW + 344);
    if ( !v10 )
      return DefWindowProcW(hwnd, message, (WPARAM)wParam, lParam);
    v11 = *(_DWORD *)(v10 + 88);
    if ( ((v11 - 1) & 0xFFFFFFF8) == 0 && v11 != 7 )
    {
      memset(&msg, 0, sizeof(msg));
      if ( PeekMessageW(&msg, hwnd, 0x3E4u, 0x3E4u, 3u) )
      {
        do
          DispatchMessageW(&msg);
        while ( PeekMessageW(&msg, hwnd, 0x3E4u, 0x3E4u, 3u) );
        v12 = GetWindowLongPtrW(hwnd, 0);
        v9 = (CDdeObject *)v12;
        if ( v12 )
        {
          v10 = *(_QWORD *)(v12 + 344);
          if ( !v10 )
            return DefWindowProcW(hwnd, message, (WPARAM)wParam, lParam);
        }
      }
    }
  }
  switch ( message )
  {
    case 0x3E1u:
      if ( v9->m_fDoingSendOnDataChange && (v17 = *(_QWORD *)(v10 + 128)) != 0 )
      {
        *(_DWORD *)(v10 + 136) = 0;
        *(_DWORD *)(v10 + 92) = -2147418105;
        *(_DWORD *)(v17 + 44) = 1;
        PostMessageW(hwnd, 0x3E1u, (WPARAM)wParam, lParam);
      }
      else
      {
        CDdeObject::OnTerminate(v9, (DDE_CHANNEL *)v10, wParam);
      }
      break;
    case 0x3E4u:
      UploadSQMData<enum Ole32SQMFlags>(OLEDDEUsage);
      if ( !*(_DWORD *)(v10 + 40) )
      {
        switch ( *(_DWORD *)(v10 + 88) )
        {
          case 1:
          case 2:
          case 3:
          case 4:
          case 5:
            goto LABEL_24;
          case 6:
            CDdeObject::OnInitAck((CDdeObject *)(unsigned int)(*(_DWORD *)(v10 + 88) - 6), (DDE_CHANNEL *)v10, wParam);
            if ( (_WORD)lParam )
              GlobalDeleteAtom(lParam);
            v16 = lParam >> 16;
            if ( (_WORD)v16 )
              GlobalDeleteAtom(v16);
            return 0;
          case 8:
LABEL_24:
            CDdeObject::OnAck(v9, (DDE_CHANNEL *)v10, lParam);
            break;
        }
      }
      break;
    case 0x3E5u:
      v14 = (void *)MGetDDElParamLo(0x3E5u, lParam);
      v15 = MGetDDElParamHi(0x3E5u, lParam);
      CDdeObject::OnData(v9, (DDE_CHANNEL *)v10, v14, v15);
      break;
    default:
      return DefWindowProcW(hwnd, message, (WPARAM)wParam, lParam);
  }
  return 0;
}

```

## disassembly

```asm
0x18007a850  push    rbx
0x18007a852  push    rbp
0x18007a853  push    rsi
0x18007a854  push    rdi
0x18007a855  push    r13
0x18007a857  push    r14
0x18007a859  push    r15
0x18007a85b  sub     rsp, 60h
0x18007a85f  mov     r14, hwnd
0x18007a862  mov     rsi, lParam
0x18007a865  mov     ecx, 2; flags
0x18007a86a  mov     r15, wParam
0x18007a86d  mov     r13d, message
0x18007a870  call    ??$UploadSQMData@W4Ole32SQMFlags@@@@YAXW4Ole32SQMFlags@@@Z; UploadSQMData<Ole32SQMFlags>(Ole32SQMFlags)
0x18007a875  lea     eax, [r13-3E0h]
0x18007a87c  cmp     eax, 8
0x18007a87f  ja      loc_18007A966
0x18007a885  xor     message, message; nIndex
0x18007a887  mov     hwnd, r14; hWnd
0x18007a88a  call    cs:__imp_GetWindowLongPtrW
0x18007a890  xor     ebx, ebx
0x18007a892  mov     rbp, rax
0x18007a895  test    rax, rax
0x18007a898  jz      loc_18007A94F
0x18007a89e  mov     rdi, [rax+158h]
0x18007a8a5  test    rdi, rdi
0x18007a8a8  jz      loc_18007A94F
0x18007a8ae  mov     eax, [rdi+58h]
0x18007a8b1  lea     ecx, [rax-1]
0x18007a8b4  test    ecx, 0FFFFFFF8h
0x18007a8ba  jnz     loc_18007A96C
0x18007a8c0  cmp     eax, 7
0x18007a8c3  jz      loc_18007A96C
0x18007a8c9  xorps   xmm0, xmm0
0x18007a8cc  mov     [rsp+98h+wRemoveMsg], 3; wRemoveMsg
0x18007a8d4  mov     eax, 3E4h
0x18007a8d9  lea     hwnd, [rsp+98h+msg]; lpMsg
0x18007a8de  mov     r9d, eax; wMsgFilterMax
0x18007a8e1  mov     r8d, eax; wMsgFilterMin
0x18007a8e4  mov     rdx, r14; hWnd
0x18007a8e7  movups  xmmword ptr [rsp+98h+msg.hwnd], xmm0
0x18007a8ec  movups  xmmword ptr [rsp+98h+msg.wParam], xmm0
0x18007a8f1  movups  xmmword ptr [rsp+98h+msg.time], xmm0
0x18007a8f6  call    cs:__imp_PeekMessageW
0x18007a8fc  test    eax, eax
0x18007a8fe  jz      short loc_18007A96C
0x18007a900  mov     ebp, 3E4h
0x18007a905  lea     hwnd, [rsp+98h+msg]; lpMsg
0x18007a90a  call    cs:__imp_DispatchMessageW
0x18007a910  mov     r9d, ebp; wMsgFilterMax
0x18007a913  mov     [rsp+98h+wRemoveMsg], 3; wRemoveMsg
0x18007a91b  mov     r8d, ebp; wMsgFilterMin
0x18007a91e  lea     hwnd, [rsp+98h+msg]; lpMsg
0x18007a923  mov     rdx, r14; hWnd
0x18007a926  call    cs:__imp_PeekMessageW
0x18007a92c  test    eax, eax
0x18007a92e  jnz     short loc_18007A905
0x18007a930  xor     message, message; nIndex
0x18007a932  mov     hwnd, r14; hWnd
0x18007a935  call    cs:__imp_GetWindowLongPtrW
0x18007a93b  mov     rbp, rax
0x18007a93e  test    rax, rax
0x18007a941  jz      short loc_18007A96C
0x18007a943  mov     rdi, [rax+158h]
0x18007a94a  test    rdi, rdi
0x18007a94d  jnz     short loc_18007A96C
0x18007a94f  mov     lParam, rsi; lParam
0x18007a952  mov     wParam, r15; wParam
0x18007a955  mov     message, r13d; Msg
0x18007a958  mov     hwnd, r14; hWnd
0x18007a95b  call    cs:__imp_DefWindowProcW
0x18007a961  jmp     loc_18007AA7B
0x18007a966  xor     ebx, ebx
0x18007a968  mov     ebp, ebx
0x18007a96a  mov     edi, ebx
0x18007a96c  mov     eax, r13d
0x18007a96f  mov     message, 3E1h; Msg
0x18007a974  sub     eax, message
0x18007a976  jz      loc_18007AA35
0x18007a97c  sub     eax, 3
0x18007a97f  jz      short loc_18007A9BB
0x18007a981  cmp     eax, 1
0x18007a984  jnz     short loc_18007A94F
0x18007a986  mov     r14d, 3E5h
0x18007a98c  mov     rdx, rsi; lParam
0x18007a98f  mov     ecx, r14d; msg
0x18007a992  call    MGetDDElParamLo
0x18007a997  mov     rdx, rsi; lParam
0x18007a99a  mov     ecx, r14d; msg
0x18007a99d  mov     rbx, rax
0x18007a9a0  call    MGetDDElParamHi
0x18007a9a5  mov     lParam, rax; aItem
0x18007a9a8  mov     wParam, rbx; hDdeData
0x18007a9ab  mov     rdx, rdi; pChannel
0x18007a9ae  mov     hwnd, rbp; this
0x18007a9b1  call    ?OnData@CDdeObject@@QEAAJPEAVDDE_CHANNEL@@PEAXG@Z; CDdeObject::OnData(DDE_CHANNEL *,void *,ushort)
0x18007a9b6  jmp     loc_18007AA79
0x18007a9bb  mov     ecx, 2; flags
0x18007a9c0  call    ??$UploadSQMData@W4Ole32SQMFlags@@@@YAXW4Ole32SQMFlags@@@Z; UploadSQMData<Ole32SQMFlags>(Ole32SQMFlags)
0x18007a9c5  cmp     [rdi+28h], ebx
0x18007a9c8  jnz     loc_18007AA79
0x18007a9ce  mov     ecx, [rdi+58h]
0x18007a9d1  sub     ecx, 1
0x18007a9d4  jz      short loc_18007A9F8
0x18007a9d6  sub     ecx, 1
0x18007a9d9  jz      short loc_18007A9F8
0x18007a9db  sub     ecx, 1
0x18007a9de  jz      short loc_18007A9F8
0x18007a9e0  sub     ecx, 1
0x18007a9e3  jz      short loc_18007A9F8
0x18007a9e5  sub     ecx, 1
0x18007a9e8  jz      short loc_18007A9F8
0x18007a9ea  sub     ecx, 1; this
0x18007a9ed  jz      short loc_18007AA08
0x18007a9ef  cmp     ecx, 2
0x18007a9f2  jnz     loc_18007AA79
0x18007a9f8  mov     wParam, rsi; lParam
0x18007a9fb  mov     rdx, rdi; pChannel
0x18007a9fe  mov     hwnd, rbp; this
0x18007aa01  call    ?OnAck@CDdeObject@@QEAAHPEAVDDE_CHANNEL@@_J@Z; CDdeObject::OnAck(DDE_CHANNEL *,__int64)
0x18007aa06  jmp     short loc_18007AA79
0x18007aa08  mov     wParam, r15; hwndSvr
0x18007aa0b  mov     rdx, rdi; pChannel
0x18007aa0e  call    ?OnInitAck@CDdeObject@@QEAAXPEAVDDE_CHANNEL@@PEAUHWND__@@@Z; CDdeObject::OnInitAck(DDE_CHANNEL *,HWND__ *)
0x18007aa13  test    si, si
0x18007aa16  jz      short loc_18007AA21
0x18007aa18  movzx   ecx, si; nAtom
0x18007aa1b  call    cs:__imp_GlobalDeleteAtom
0x18007aa21  shr     rsi, 10h
0x18007aa25  test    si, si
0x18007aa28  jz      short loc_18007AA79
0x18007aa2a  movzx   ecx, si; nAtom
0x18007aa2d  call    cs:__imp_GlobalDeleteAtom
0x18007aa33  jmp     short loc_18007AA79
0x18007aa35  cmp     [rbp+0], ebx
0x18007aa38  jz      short loc_18007AA6B
0x18007aa3a  mov     rax, [rdi+80h]
0x18007aa41  test    rax, rax
0x18007aa44  jz      short loc_18007AA6B
0x18007aa46  mov     [rdi+88h], ebx
0x18007aa4c  mov     lParam, rsi; lParam
0x18007aa4f  mov     dword ptr [rdi+5Ch], 80010007h
0x18007aa56  mov     wParam, r15; wParam
0x18007aa59  mov     hwnd, r14; hWnd
0x18007aa5c  mov     dword ptr [rax+2Ch], 1
0x18007aa63  call    cs:__imp_PostMessageW
0x18007aa69  jmp     short loc_18007AA79
0x18007aa6b  mov     wParam, r15; hwndPost
0x18007aa6e  mov     rdx, rdi; pChannel
0x18007aa71  mov     hwnd, rbp; this
0x18007aa74  call    ?OnTerminate@CDdeObject@@QEAAJPEAVDDE_CHANNEL@@PEAUHWND__@@@Z; CDdeObject::OnTerminate(DDE_CHANNEL *,HWND__ *)
0x18007aa79  xor     eax, eax
0x18007aa7b  add     rsp, 60h
0x18007aa7f  pop     r15
0x18007aa81  pop     r14
0x18007aa83  pop     r13
0x18007aa85  pop     rdi
0x18007aa86  pop     rsi
0x18007aa87  pop     rbp
0x18007aa88  pop     rbx
0x18007aa89  retn
```
