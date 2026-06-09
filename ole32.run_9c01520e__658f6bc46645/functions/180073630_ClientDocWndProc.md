# ClientDocWndProc

- ea: `0x180073630`
- end: `0x1800738c3`
- name: `ClientDocWndProc`
- size: `659`
- prototype: `__int64 __fastcall(HWND__ *hwnd, unsigned int message, unsigned __int64 wParam, __int64 lParam)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x18006e998`
- `0x18006eb58`
- `0x18006efc8`
- `0x18006f02c`
- `0x18006fef4`
- `0x18006ff28`
- `0x1800735f0`
- `0x180073630`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007382f`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180073847`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007382f`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180073847`
- `USER32!GetWindowLongPtrW` at `0x180073681`
- `USER32!GetWindowLongPtrW` at `0x18007373e`
- `USER32!GetWindowLongPtrW` at `0x180073681`
- `USER32!GetWindowLongPtrW` at `0x18007373e`
- `USER32!PostMessageW` at `0x180073885`
- `USER32!PostMessageW` at `0x180073885`
- `USER32!DefWindowProcW` at `0x18007376a`
- `USER32!DefWindowProcW` at `0x18007376a`
- `USER32!DispatchMessageW` at `0x180073704`
- `USER32!DispatchMessageW` at `0x180073704`
- `USER32!PeekMessageW` at `0x1800736ef`
- `USER32!PeekMessageW` at `0x180073729`
- `USER32!PeekMessageW` at `0x1800736ef`
- `USER32!PeekMessageW` at `0x180073729`

## pseudocode

```c
LRESULT __fastcall ClientDocWndProc(HWND hwnd, UINT message, HWND__ *wParam, unsigned __int64 lParam)
{
  CDdeObject *v8; // rbp
  __int64 v9; // rdi
  LONG_PTR WindowLongPtrW; // rax
  int v11; // eax
  LONG_PTR v12; // rax
  void *v14; // rbx
  unsigned __int16 v15; // ax
  unsigned __int64 v16; // rsi
  __int64 v17; // rax
  tagMSG msg; // [rsp+30h] [rbp-48h] BYREF

  UploadSQMData<enum Ole32SQMFlags>(OLEDDEUsage);
  v8 = 0;
  v9 = 0;
  if ( message - 992 <= 8 )
  {
    WindowLongPtrW = GetWindowLongPtrW(hwnd, 0);
    v8 = (CDdeObject *)WindowLongPtrW;
    if ( !WindowLongPtrW )
      return DefWindowProcW(hwnd, message, (WPARAM)wParam, lParam);
    v9 = *(_QWORD *)(WindowLongPtrW + 344);
    if ( !v9 )
      return DefWindowProcW(hwnd, message, (WPARAM)wParam, lParam);
    v11 = *(_DWORD *)(v9 + 88);
    if ( ((v11 - 1) & 0xFFFFFFF8) == 0 && v11 != 7 )
    {
      memset(&msg, 0, sizeof(msg));
      if ( PeekMessageW(&msg, hwnd, 0x3E4u, 0x3E4u, 3u) )
      {
        do
          DispatchMessageW(&msg);
        while ( PeekMessageW(&msg, hwnd, 0x3E4u, 0x3E4u, 3u) );
        v12 = GetWindowLongPtrW(hwnd, 0);
        v8 = (CDdeObject *)v12;
        if ( v12 )
        {
          v9 = *(_QWORD *)(v12 + 344);
          if ( !v9 )
            return DefWindowProcW(hwnd, message, (WPARAM)wParam, lParam);
        }
      }
    }
  }
  switch ( message )
  {
    case 0x3E1u:
      if ( v8->m_fDoingSendOnDataChange && (v17 = *(_QWORD *)(v9 + 128)) != 0 )
      {
        *(_DWORD *)(v9 + 136) = 0;
        *(_DWORD *)(v9 + 92) = -2147418105;
        *(_DWORD *)(v17 + 44) = 1;
        PostMessageW(hwnd, 0x3E1u, (WPARAM)wParam, lParam);
      }
      else
      {
        CDdeObject::OnTerminate(v8, (DDE_CHANNEL *)v9, wParam);
      }
      break;
    case 0x3E4u:
      UploadSQMData<enum Ole32SQMFlags>(OLEDDEUsage);
      if ( !*(_DWORD *)(v9 + 40) )
      {
        switch ( *(_DWORD *)(v9 + 88) )
        {
          case 1:
          case 2:
          case 3:
          case 4:
          case 5:
            goto LABEL_23;
          case 6:
            CDdeObject::OnInitAck((CDdeObject *)(unsigned int)(*(_DWORD *)(v9 + 88) - 6), (DDE_CHANNEL *)v9, wParam);
            if ( (_WORD)lParam )
              GlobalDeleteAtom(lParam);
            v16 = lParam >> 16;
            if ( (_WORD)v16 )
              GlobalDeleteAtom(v16);
            return 0;
          case 8:
LABEL_23:
            CDdeObject::OnAck(v8, (DDE_CHANNEL *)v9, lParam);
            break;
        }
      }
      break;
    case 0x3E5u:
      v14 = (void *)MGetDDElParamLo(0x3E5u, lParam);
      v15 = MGetDDElParamHi(0x3E5u, lParam);
      CDdeObject::OnData(v8, (DDE_CHANNEL *)v9, v14, v15);
      break;
    default:
      return DefWindowProcW(hwnd, message, (WPARAM)wParam, lParam);
  }
  return 0;
}

```

## disassembly

```asm
0x180073630  mov     rax, rsp
0x180073633  mov     [rax+8], rbx
0x180073637  mov     [rax+10h], rbp
0x18007363b  mov     [rax+18h], rsi
0x18007363f  mov     [rax+20h], rdi
0x180073643  push    r12
0x180073645  push    r14
0x180073647  push    r15
0x180073649  sub     rsp, 60h
0x18007364d  mov     rbx, hwnd
0x180073650  mov     rsi, lParam
0x180073653  mov     ecx, 2; flags
0x180073658  mov     r14, wParam
0x18007365b  mov     r15d, message
0x18007365e  call    ??$UploadSQMData@W4Ole32SQMFlags@@@@YAXW4Ole32SQMFlags@@@Z; UploadSQMData<Ole32SQMFlags>(Ole32SQMFlags)
0x180073663  xor     r12d, r12d
0x180073666  lea     eax, [r15-3E0h]
0x18007366d  mov     ebp, r12d
0x180073670  mov     edi, r12d
0x180073673  cmp     eax, 8
0x180073676  ja      loc_18007377B
0x18007367c  xor     message, message; nIndex
0x18007367e  mov     hwnd, rbx; hWnd
0x180073681  call    cs:__imp_GetWindowLongPtrW
0x180073688  nop     dword ptr [rax+rax+00h]
0x18007368d  mov     rbp, rax
0x180073690  test    rax, rax
0x180073693  jz      loc_18007375E
0x180073699  mov     rdi, [rax+158h]
0x1800736a0  test    rdi, rdi
0x1800736a3  jz      loc_18007375E
0x1800736a9  mov     eax, [rdi+58h]
0x1800736ac  lea     ecx, [rax-1]
0x1800736af  test    ecx, 0FFFFFFF8h
0x1800736b5  jnz     loc_18007377B
0x1800736bb  cmp     eax, 7
0x1800736be  jz      loc_18007377B
0x1800736c4  xorps   xmm0, xmm0
0x1800736c7  mov     [rsp+78h+wRemoveMsg], 3; wRemoveMsg
0x1800736cf  mov     r9d, 3E4h; wMsgFilterMax
0x1800736d5  lea     hwnd, [rsp+78h+msg]; lpMsg
0x1800736da  mov     r8d, r9d; wMsgFilterMin
0x1800736dd  mov     rdx, rbx; hWnd
0x1800736e0  movups  xmmword ptr [rsp+78h+msg.hwnd], xmm0
0x1800736e5  movups  xmmword ptr [rsp+78h+msg.wParam], xmm0
0x1800736ea  movups  xmmword ptr [rsp+78h+msg.time], xmm0
0x1800736ef  call    cs:__imp_PeekMessageW
0x1800736f6  nop     dword ptr [rax+rax+00h]
0x1800736fb  test    eax, eax
0x1800736fd  jz      short loc_18007377B
0x1800736ff  lea     hwnd, [rsp+78h+msg]; lpMsg
0x180073704  call    cs:__imp_DispatchMessageW
0x18007370b  nop     dword ptr [rax+rax+00h]
0x180073710  mov     r9d, 3E4h; wMsgFilterMax
0x180073716  mov     [rsp+78h+wRemoveMsg], 3; wRemoveMsg
0x18007371e  mov     r8d, r9d; wMsgFilterMin
0x180073721  lea     hwnd, [rsp+78h+msg]; lpMsg
0x180073726  mov     rdx, rbx; hWnd
0x180073729  call    cs:__imp_PeekMessageW
0x180073730  nop     dword ptr [rax+rax+00h]
0x180073735  test    eax, eax
0x180073737  jnz     short loc_1800736FF
0x180073739  xor     message, message; nIndex
0x18007373b  mov     hwnd, rbx; hWnd
0x18007373e  call    cs:__imp_GetWindowLongPtrW
0x180073745  nop     dword ptr [rax+rax+00h]
0x18007374a  mov     rbp, rax
0x18007374d  test    rax, rax
0x180073750  jz      short loc_18007377B
0x180073752  mov     rdi, [rax+158h]
0x180073759  test    rdi, rdi
0x18007375c  jnz     short loc_18007377B
0x18007375e  mov     lParam, rsi; lParam
0x180073761  mov     wParam, r14; wParam
0x180073764  mov     message, r15d; Msg
0x180073767  mov     hwnd, rbx; hWnd
0x18007376a  call    cs:__imp_DefWindowProcW
0x180073771  nop     dword ptr [rax+rax+00h]
0x180073776  jmp     loc_1800738A3
0x18007377b  mov     eax, r15d
0x18007377e  mov     message, 3E1h; Msg
0x180073783  sub     eax, message
0x180073785  jz      loc_180073855
0x18007378b  sub     eax, 3
0x18007378e  jz      short loc_1800737CB
0x180073790  cmp     eax, 1
0x180073793  jnz     short loc_18007375E
0x180073795  mov     r14d, 3E5h
0x18007379b  mov     rdx, rsi; lParam
0x18007379e  mov     ecx, r14d; msg
0x1800737a1  call    MGetDDElParamLo
0x1800737a6  mov     rdx, rsi; lParam
0x1800737a9  mov     ecx, r14d; msg
0x1800737ac  mov     rbx, rax
0x1800737af  call    MGetDDElParamHi
0x1800737b4  movzx   r9d, ax; aItem
0x1800737b8  mov     wParam, rbx; hDdeData
0x1800737bb  mov     rdx, rdi; pChannel
0x1800737be  mov     hwnd, rbp; this
0x1800737c1  call    ?OnData@CDdeObject@@QEAAJPEAVDDE_CHANNEL@@PEAXG@Z; CDdeObject::OnData(DDE_CHANNEL *,void *,ushort)
0x1800737c6  jmp     loc_1800738A1
0x1800737cb  mov     ecx, 2; flags
0x1800737d0  call    ??$UploadSQMData@W4Ole32SQMFlags@@@@YAXW4Ole32SQMFlags@@@Z; UploadSQMData<Ole32SQMFlags>(Ole32SQMFlags)
0x1800737d5  cmp     [rdi+28h], r12d
0x1800737d9  jnz     loc_1800738A1
0x1800737df  mov     ecx, [rdi+58h]
0x1800737e2  sub     ecx, 1
0x1800737e5  jz      short loc_180073809
0x1800737e7  sub     ecx, 1
0x1800737ea  jz      short loc_180073809
0x1800737ec  sub     ecx, 1
0x1800737ef  jz      short loc_180073809
0x1800737f1  sub     ecx, 1
0x1800737f4  jz      short loc_180073809
0x1800737f6  sub     ecx, 1
0x1800737f9  jz      short loc_180073809
0x1800737fb  sub     ecx, 1; this
0x1800737fe  jz      short loc_18007381C
0x180073800  cmp     ecx, 2
0x180073803  jnz     loc_1800738A1
0x180073809  mov     wParam, rsi; lParam
0x18007380c  mov     rdx, rdi; pChannel
0x18007380f  mov     hwnd, rbp; this
0x180073812  call    ?OnAck@CDdeObject@@QEAAHPEAVDDE_CHANNEL@@_J@Z; CDdeObject::OnAck(DDE_CHANNEL *,__int64)
0x180073817  jmp     loc_1800738A1
0x18007381c  mov     wParam, r14; hwndSvr
0x18007381f  mov     rdx, rdi; pChannel
0x180073822  call    ?OnInitAck@CDdeObject@@QEAAXPEAVDDE_CHANNEL@@PEAUHWND__@@@Z; CDdeObject::OnInitAck(DDE_CHANNEL *,HWND__ *)
0x180073827  test    si, si
0x18007382a  jz      short loc_18007383B
0x18007382c  movzx   ecx, si; nAtom
0x18007382f  call    cs:__imp_GlobalDeleteAtom
0x180073836  nop     dword ptr [rax+rax+00h]
0x18007383b  shr     rsi, 10h
0x18007383f  test    si, si
0x180073842  jz      short loc_1800738A1
0x180073844  movzx   ecx, si; nAtom
0x180073847  call    cs:__imp_GlobalDeleteAtom
0x18007384e  nop     dword ptr [rax+rax+00h]
0x180073853  jmp     short loc_1800738A1
0x180073855  cmp     [rbp+0], r12d
0x180073859  jz      short loc_180073893
0x18007385b  mov     rax, [rdi+80h]
0x180073862  test    rax, rax
0x180073865  jz      short loc_180073893
0x180073867  mov     [rdi+88h], r12d
0x18007386e  mov     lParam, rsi; lParam
0x180073871  mov     dword ptr [rdi+5Ch], 80010007h
0x180073878  mov     wParam, r14; wParam
0x18007387b  mov     hwnd, rbx; hWnd
0x18007387e  mov     dword ptr [rax+2Ch], 1
0x180073885  call    cs:__imp_PostMessageW
0x18007388c  nop     dword ptr [rax+rax+00h]
0x180073891  jmp     short loc_1800738A1
0x180073893  mov     wParam, r14; hwndPost
0x180073896  mov     rdx, rdi; pChannel
0x180073899  mov     hwnd, rbp; this
0x18007389c  call    ?OnTerminate@CDdeObject@@QEAAJPEAVDDE_CHANNEL@@PEAUHWND__@@@Z; CDdeObject::OnTerminate(DDE_CHANNEL *,HWND__ *)
0x1800738a1  xor     eax, eax
0x1800738a3  lea     r11, [rsp+78h+var_18]
0x1800738a8  mov     rbx, [r11+20h]
0x1800738ac  mov     rbp, [r11+28h]
0x1800738b0  mov     rsi, [r11+30h]
0x1800738b4  mov     rdi, [r11+38h]
0x1800738b8  mov     rsp, r11
0x1800738bb  pop     r15
0x1800738bd  pop     r14
0x1800738bf  pop     r12
0x1800738c1  retn
```
