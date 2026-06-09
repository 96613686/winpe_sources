# SysWndProc

- ea: `0x1800738d0`
- end: `0x180073af3`
- name: `SysWndProc`
- size: `547`
- prototype: `__int64 __fastcall(HWND__ *hwnd, unsigned int message, unsigned __int64 wParam, __int64 lParam)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18006e998`
- `0x18006efc8`
- `0x18006f02c`
- `0x1800709b4`
- `0x1800735f0`
- `0x1800738d0`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180073a3c`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180073a54`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180073a3c`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180073a54`
- `USER32!GetWindowLongPtrW` at `0x18007390a`
- `USER32!GetWindowLongPtrW` at `0x1800739c5`
- `USER32!GetWindowLongPtrW` at `0x18007390a`
- `USER32!GetWindowLongPtrW` at `0x1800739c5`
- `USER32!KillTimer` at `0x180073a80`
- `USER32!KillTimer` at `0x180073a80`
- `USER32!DefWindowProcW` at `0x180073ac7`
- `USER32!DefWindowProcW` at `0x180073ac7`
- `USER32!DispatchMessageW` at `0x18007398e`
- `USER32!DispatchMessageW` at `0x18007398e`
- `USER32!PeekMessageW` at `0x180073974`
- `USER32!PeekMessageW` at `0x1800739b0`
- `USER32!PeekMessageW` at `0x180073974`
- `USER32!PeekMessageW` at `0x1800739b0`

## pseudocode

```c
LRESULT __fastcall SysWndProc(HWND hwnd, UINT message, HWND__ *wParam, unsigned __int64 lParam)
{
  LONG_PTR WindowLongPtrW; // rax
  CDdeObject *v9; // rsi
  DDE_CHANNEL *v10; // rbx
  LONG_PTR v11; // rax
  CDdeObject *v12; // rcx
  unsigned __int64 v13; // rdi
  __int64 v14; // r8
  __int64 v15; // r8
  unsigned __int16 wMsg; // dx
  tagMSG msg; // [rsp+30h] [rbp-48h] BYREF

  if ( message - 992 <= 8 )
  {
    WindowLongPtrW = GetWindowLongPtrW(hwnd, 0);
    v9 = (CDdeObject *)WindowLongPtrW;
    if ( WindowLongPtrW )
    {
      v10 = *(DDE_CHANNEL **)(WindowLongPtrW + 336);
      if ( v10 )
      {
        if ( ((v10->iAwaitAck - 4) & 0xFFFFFFFD) != 0 )
          goto LABEL_9;
        memset(&msg, 0, sizeof(msg));
        if ( !PeekMessageW(&msg, hwnd, 0x3E4u, 0x3E4u, 3u) )
          goto LABEL_9;
        do
          DispatchMessageW(&msg);
        while ( PeekMessageW(&msg, hwnd, 0x3E4u, 0x3E4u, 3u) );
        v11 = GetWindowLongPtrW(hwnd, 0);
        v9 = (CDdeObject *)v11;
        if ( !v11 || (v10 = *(DDE_CHANNEL **)(v11 + 336)) != 0 )
        {
LABEL_9:
          switch ( message )
          {
            case 0x113u:
              KillTimer(v10->hwndCli, 1u);
              v15 = v10->lParam;
              wMsg = v10->wMsg;
              v10->wTimer = 0;
              if ( !wPostMessageToServer(v10, wMsg, v15, 0) )
              {
                v14 = v10->lParam;
LABEL_23:
                CDdeObject::OnAck(v9, v10, v14);
              }
              return 0;
            case 0x3E1u:
              CDdeObject::OnTerminate(v9, v10, wParam);
              return 0;
            case 0x3E4u:
              UploadSQMData<enum Ole32SQMFlags>(OLEDDEUsage);
              if ( !v10->bTerminating )
              {
                if ( v10->iAwaitAck != 4 )
                {
                  if ( v10->iAwaitAck == 6 )
                  {
                    CDdeObject::OnInitAck(v12, v10, wParam);
                    if ( (_WORD)lParam )
                      GlobalDeleteAtom(lParam);
                    v13 = lParam >> 16;
                    if ( (_WORD)v13 )
                      GlobalDeleteAtom(v13);
                  }
                  return 0;
                }
                v14 = lParam;
                goto LABEL_23;
              }
              return 0;
          }
        }
      }
    }
  }
  return DefWindowProcW(hwnd, message, (WPARAM)wParam, lParam);
}

```

## disassembly

```asm
0x1800738d0  mov     rax, rsp
0x1800738d3  mov     [rax+8], rbx
0x1800738d7  mov     [rax+10h], rbp
0x1800738db  mov     [rax+18h], rsi
0x1800738df  mov     [rax+20h], rdi
0x1800738e3  push    r12
0x1800738e5  push    r14
0x1800738e7  push    r15
0x1800738e9  sub     rsp, 60h
0x1800738ed  lea     eax, [rdx-3E0h]
0x1800738f3  mov     rdi, lParam
0x1800738f6  mov     r14, wParam
0x1800738f9  mov     r15d, message
0x1800738fc  mov     rbp, hwnd
0x1800738ff  cmp     eax, 8
0x180073902  ja      loc_180073ABB
0x180073908  xor     message, message; nIndex
0x18007390a  call    cs:__imp_GetWindowLongPtrW
0x180073911  nop     dword ptr [rax+rax+00h]
0x180073916  xor     r12d, r12d
0x180073919  mov     rsi, rax
0x18007391c  test    rax, rax
0x18007391f  jz      loc_180073ABB
0x180073925  mov     rbx, [rax+150h]
0x18007392c  test    rbx, rbx
0x18007392f  jz      loc_180073ABB
0x180073935  mov     ecx, [rbx+58h]
0x180073938  sub     ecx, 4
0x18007393b  test    ecx, 0FFFFFFFDh
0x180073941  jnz     loc_1800739E9
0x180073947  xorps   xmm0, xmm0
0x18007394a  mov     [rsp+78h+wRemoveMsg], 3; wRemoveMsg
0x180073952  mov     eax, 3E4h
0x180073957  lea     hwnd, [rsp+78h+msg]; lpMsg
0x18007395c  mov     r9d, eax; wMsgFilterMax
0x18007395f  mov     r8d, eax; wMsgFilterMin
0x180073962  mov     rdx, rbp; hWnd
0x180073965  movups  xmmword ptr [rsp+78h+msg.hwnd], xmm0
0x18007396a  movups  xmmword ptr [rsp+78h+msg.wParam], xmm0
0x18007396f  movups  xmmword ptr [rsp+78h+msg.time], xmm0
0x180073974  call    cs:__imp_PeekMessageW
0x18007397b  nop     dword ptr [rax+rax+00h]
0x180073980  test    eax, eax
0x180073982  jz      short loc_1800739E9
0x180073984  mov     esi, 3E4h
0x180073989  lea     hwnd, [rsp+78h+msg]; lpMsg
0x18007398e  call    cs:__imp_DispatchMessageW
0x180073995  nop     dword ptr [rax+rax+00h]
0x18007399a  mov     r9d, esi; wMsgFilterMax
0x18007399d  mov     [rsp+78h+wRemoveMsg], 3; wRemoveMsg
0x1800739a5  mov     r8d, esi; wMsgFilterMin
0x1800739a8  lea     hwnd, [rsp+78h+msg]; lpMsg
0x1800739ad  mov     rdx, rbp; hWnd
0x1800739b0  call    cs:__imp_PeekMessageW
0x1800739b7  nop     dword ptr [rax+rax+00h]
0x1800739bc  test    eax, eax
0x1800739be  jnz     short loc_180073989
0x1800739c0  xor     message, message; nIndex
0x1800739c2  mov     hwnd, rbp; hWnd
0x1800739c5  call    cs:__imp_GetWindowLongPtrW
0x1800739cc  nop     dword ptr [rax+rax+00h]
0x1800739d1  mov     rsi, rax
0x1800739d4  test    rax, rax
0x1800739d7  jz      short loc_1800739E9
0x1800739d9  mov     rbx, [rax+150h]
0x1800739e0  test    rbx, rbx
0x1800739e3  jz      loc_180073ABB
0x1800739e9  mov     eax, r15d
0x1800739ec  sub     eax, 113h
0x1800739f1  jz      loc_180073A77
0x1800739f7  sub     eax, 2CEh
0x1800739fc  jz      short loc_180073A67
0x1800739fe  cmp     eax, 3
0x180073a01  jnz     loc_180073ABB
0x180073a07  lea     ecx, [rax-1]; flags
0x180073a0a  call    ??$UploadSQMData@W4Ole32SQMFlags@@@@YAXW4Ole32SQMFlags@@@Z; UploadSQMData<Ole32SQMFlags>(Ole32SQMFlags)
0x180073a0f  cmp     [rbx+28h], r12d
0x180073a13  jnz     loc_180073AB7
0x180073a19  cmp     dword ptr [rbx+58h], 4
0x180073a1d  jz      short loc_180073A62
0x180073a1f  cmp     dword ptr [rbx+58h], 6
0x180073a23  jnz     loc_180073AB7
0x180073a29  mov     wParam, r14; hwndSvr
0x180073a2c  mov     rdx, rbx; pChannel
0x180073a2f  call    ?OnInitAck@CDdeObject@@QEAAXPEAVDDE_CHANNEL@@PEAUHWND__@@@Z; CDdeObject::OnInitAck(DDE_CHANNEL *,HWND__ *)
0x180073a34  test    di, di
0x180073a37  jz      short loc_180073A48
0x180073a39  movzx   ecx, di; nAtom
0x180073a3c  call    cs:__imp_GlobalDeleteAtom
0x180073a43  nop     dword ptr [rax+rax+00h]
0x180073a48  shr     rdi, 10h
0x180073a4c  test    di, di
0x180073a4f  jz      short loc_180073AB7
0x180073a51  movzx   ecx, di; nAtom
0x180073a54  call    cs:__imp_GlobalDeleteAtom
0x180073a5b  nop     dword ptr [rax+rax+00h]
0x180073a60  jmp     short loc_180073AB7
0x180073a62  mov     wParam, rdi
0x180073a65  jmp     short loc_180073AAC
0x180073a67  mov     wParam, r14; hwndPost
0x180073a6a  mov     rdx, rbx; pChannel
0x180073a6d  mov     hwnd, rsi; this
0x180073a70  call    ?OnTerminate@CDdeObject@@QEAAJPEAVDDE_CHANNEL@@PEAUHWND__@@@Z; CDdeObject::OnTerminate(DDE_CHANNEL *,HWND__ *)
0x180073a75  jmp     short loc_180073AB7
0x180073a77  mov     hwnd, [rbx+18h]; hWnd
0x180073a7b  mov     message, 1; uIDEvent
0x180073a80  call    cs:__imp_KillTimer
0x180073a87  nop     dword ptr [rax+rax+00h]
0x180073a8c  mov     wParam, [rbx+50h]; lParam
0x180073a90  xor     r9d, r9d; fFreeOnError
0x180073a93  movzx   message, word ptr [rbx+4Ch]; wMsg
0x180073a97  mov     hwnd, rbx; pChannel
0x180073a9a  mov     [rbx+30h], r12w
0x180073a9f  call    ?wPostMessageToServer@@YAHPEAVDDE_CHANNEL@@G_JH@Z; wPostMessageToServer(DDE_CHANNEL *,ushort,__int64,int)
0x180073aa4  test    eax, eax
0x180073aa6  jnz     short loc_180073AB7
0x180073aa8  mov     wParam, [rbx+50h]; lParam
0x180073aac  mov     rdx, rbx; pChannel
0x180073aaf  mov     hwnd, rsi; this
0x180073ab2  call    ?OnAck@CDdeObject@@QEAAHPEAVDDE_CHANNEL@@_J@Z; CDdeObject::OnAck(DDE_CHANNEL *,__int64)
0x180073ab7  xor     eax, eax
0x180073ab9  jmp     short loc_180073AD3
0x180073abb  mov     lParam, rdi; lParam
0x180073abe  mov     wParam, r14; wParam
0x180073ac1  mov     message, r15d; Msg
0x180073ac4  mov     hwnd, rbp; hWnd
0x180073ac7  call    cs:__imp_DefWindowProcW
0x180073ace  nop     dword ptr [rax+rax+00h]
0x180073ad3  lea     r11, [rsp+78h+var_18]
0x180073ad8  mov     rbx, [r11+20h]
0x180073adc  mov     rbp, [r11+28h]
0x180073ae0  mov     rsi, [r11+30h]
0x180073ae4  mov     rdi, [r11+38h]
0x180073ae8  mov     rsp, r11
0x180073aeb  pop     r15
0x180073aed  pop     r14
0x180073aef  pop     r12
0x180073af1  retn
```
