# CClipServer::ClipThreadWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x14003adc0`
- end: `0x14003b0c9`
- name: `?ClipThreadWndProc@CClipServer@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `777`
- prototype: `__int64 __fastcall(CClipServer *__hidden this, HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x14003ece0`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005750`
- `0x1400081d0`
- `0x14003adc0`
- `0x14003e790`
- `0x140050298`
- `0x140052780`
- `0x14006b010`

## import_xrefs

- `USER32!DestroyWindow` at `0x14003b0ae`
- `USER32!DestroyWindow` at `0x14003b0ae`
- `USER32!DefWindowProcW` at `0x14003afc7`
- `USER32!DefWindowProcW` at `0x14003afc7`

## string_xrefs

- `0x14003b050`: `SendServerReadyMessages failed!`
- `0x14003af88`: `OnClipboardChainUpdated failed!`

## pseudocode

```c
LRESULT __fastcall CClipServer::ClipThreadWndProc(HWND *this, HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  __int64 v5; // r14
  HWND v10; // rcx
  unsigned int v11; // eax
  HWND v12; // rbx
  __int64 v13; // rax
  int ready; // edi
  unsigned int v15; // eax
  int v16; // edx
  const char *v17; // rcx
  HWND v18; // rcx
  unsigned int v19; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  _QWORD v22[7]; // [rsp+30h] [rbp-38h] BYREF

  v5 = 0;
  if ( Msg == 16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        68,
        WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    CClipBase::DetachFromSystemClipboard((CClipBase *)this);
    DestroyWindow(this[29]);
    this[29] = 0;
  }
  else if ( Msg == 1067 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids, v19);
    }
    ready = CClipServer::SendServerReadyMessages((CClipServer *)this);
    if ( ready < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 67;
      v17 = "SendServerReadyMessages failed!";
      goto LABEL_25;
    }
  }
  else
  {
    v10 = this[44];
    if ( v10 && (*(unsigned int (__fastcall **)(HWND, _QWORD))(*(_QWORD *)v10 + 64LL))(v10, Msg) )
    {
      if ( !*((_BYTE *)this + 984) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v11 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids, v11);
        }
        v12 = this[124];
        v22[0] = 0;
        if ( v12 )
        {
          TCntPtr<IRdpHintApiEventSink>::SafeRelease(v22);
          v13 = *(_QWORD *)v12;
          v22[0] = v12;
          (*(void (__fastcall **)(HWND))(v13 + 8))(v12);
          (*(void (__fastcall **)(HWND))(*(_QWORD *)v12 + 24LL))(v12);
        }
        TCntPtr<IRdpHintApiEventSink>::SafeRelease(v22);
        return v5;
      }
      ready = CClipBase::OnDrawClipboard((CClipBase *)this);
      if ( ready >= 0
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v5;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 70;
      v17 = "OnDrawClipboard failed!";
LABEL_25:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        (unsigned int)WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids,
        v15,
        (__int64)v17,
        ready);
      return v5;
    }
    v18 = this[44];
    if ( !v18 || !(*(unsigned int (__fastcall **)(HWND, _QWORD))(*(_QWORD *)v18 + 72LL))(v18, Msg) )
      return DefWindowProcW(hWnd, Msg, wParam, lParam);
    ready = (*(__int64 (__fastcall **)(HWND, WPARAM, LPARAM))(*(_QWORD *)this[44] + 48LL))(this[44], wParam, lParam);
    if ( ready < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 71;
      v17 = "OnClipboardChainUpdated failed!";
      goto LABEL_25;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14003adc0  push    rbx
0x14003adc2  push    rbp
0x14003adc3  push    rsi
0x14003adc4  push    rdi
0x14003adc5  push    r14
0x14003adc7  sub     rsp, 40h
0x14003adcb  xor     r14d, r14d
0x14003adce  mov     rsi, r9
0x14003add1  mov     ebx, r8d
0x14003add4  mov     rbp, rdx
0x14003add7  mov     rdi, rcx
0x14003adda  cmp     r8d, 10h
0x14003adde  jz      loc_14003B05C
0x14003ade4  cmp     ebx, 42Bh
0x14003adea  jz      loc_14003AFD5
0x14003adf0  mov     rcx, [rcx+160h]
0x14003adf7  test    rcx, rcx
0x14003adfa  jz      loc_14003AF05
0x14003ae00  mov     rax, [rcx]
0x14003ae03  mov     edx, ebx
0x14003ae05  mov     rax, [rax+40h]
0x14003ae09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ae0e  test    eax, eax
0x14003ae10  jz      loc_14003AF05
0x14003ae16  cmp     [rdi+3D8h], r14b
0x14003ae1d  jnz     loc_14003AEB2
0x14003ae23  mov     rax, cs:WPP_GLOBAL_Control
0x14003ae2a  lea     rbx, WPP_GLOBAL_Control
0x14003ae31  cmp     rax, rbx
0x14003ae34  jz      short loc_14003AE65
0x14003ae36  test    byte ptr [rax+1Ch], 1
0x14003ae3a  jz      short loc_14003AE65
0x14003ae3c  cmp     byte ptr [rax+19h], 5
0x14003ae40  jb      short loc_14003AE65
0x14003ae42  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003ae47  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ae4e  lea     edx, [r14+45h]
0x14003ae52  mov     r9d, eax
0x14003ae55  lea     r8, WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids
0x14003ae5c  mov     rcx, [rcx+10h]
0x14003ae60  call    WPP_SF_d
0x14003ae65  mov     rbx, [rdi+3E0h]
0x14003ae6c  mov     [rsp+68h+var_38], r14
0x14003ae71  test    rbx, rbx
0x14003ae74  jz      short loc_14003AEA3
0x14003ae76  lea     rcx, [rsp+68h+var_38]
0x14003ae7b  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14003ae80  mov     rax, [rbx]
0x14003ae83  mov     rcx, rbx
0x14003ae86  mov     [rsp+68h+var_38], rbx
0x14003ae8b  mov     rax, [rax+8]
0x14003ae8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ae94  mov     rax, [rbx]
0x14003ae97  mov     rcx, rbx
0x14003ae9a  mov     rax, [rax+18h]
0x14003ae9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003aea3  lea     rcx, [rsp+68h+var_38]
0x14003aea8  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14003aead  jmp     loc_14003B0BB
0x14003aeb2  mov     rcx, rdi; this
0x14003aeb5  call    ?OnDrawClipboard@CClipBase@@MEAAJXZ; CClipBase::OnDrawClipboard(void)
0x14003aeba  mov     edi, eax
0x14003aebc  test    eax, eax
0x14003aebe  jns     loc_14003B0BB
0x14003aec4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aecb  lea     rbx, WPP_GLOBAL_Control
0x14003aed2  cmp     rcx, rbx
0x14003aed5  jz      loc_14003B0BB
0x14003aedb  test    byte ptr [rcx+1Ch], 8
0x14003aedf  jz      loc_14003B0BB
0x14003aee5  cmp     byte ptr [rcx+19h], 2
0x14003aee9  jb      loc_14003B0BB
0x14003aeef  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003aef4  mov     edx, 46h ; 'F'
0x14003aef9  lea     rcx, aOndrawclipboar; "OnDrawClipboard failed!"
0x14003af00  jmp     loc_14003AF8F
0x14003af05  mov     rcx, [rdi+160h]
0x14003af0c  test    rcx, rcx
0x14003af0f  jz      loc_14003AFB7
0x14003af15  mov     rax, [rcx]
0x14003af18  mov     edx, ebx
0x14003af1a  mov     rax, [rax+48h]
0x14003af1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003af23  test    eax, eax
0x14003af25  jz      loc_14003AFB7
0x14003af2b  mov     rcx, [rdi+160h]
0x14003af32  mov     rdx, rsi
0x14003af35  mov     r8, [rsp+68h+lParam]
0x14003af3d  mov     rax, [rcx]
0x14003af40  mov     rax, [rax+30h]
0x14003af44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003af49  mov     edi, eax
0x14003af4b  test    eax, eax
0x14003af4d  jns     loc_14003B0BB
0x14003af53  mov     rcx, cs:WPP_GLOBAL_Control
0x14003af5a  lea     rbx, WPP_GLOBAL_Control
0x14003af61  cmp     rcx, rbx
0x14003af64  jz      loc_14003B0BB
0x14003af6a  test    byte ptr [rcx+1Ch], 8
0x14003af6e  jz      loc_14003B0BB
0x14003af74  cmp     byte ptr [rcx+19h], 2
0x14003af78  jb      loc_14003B0BB
0x14003af7e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003af83  mov     edx, 47h ; 'G'
0x14003af88  lea     rcx, aOnclipboardcha; "OnClipboardChainUpdated failed!"
0x14003af8f  mov     [rsp+68h+var_40], edi
0x14003af93  lea     r8, WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids
0x14003af9a  mov     [rsp+68h+var_48], rcx
0x14003af9f  mov     r9d, eax
0x14003afa2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003afa9  mov     rcx, [rcx+10h]
0x14003afad  call    WPP_SF_DsD
0x14003afb2  jmp     loc_14003B0BB
0x14003afb7  mov     r9, [rsp+68h+lParam]; lParam
0x14003afbf  mov     r8, rsi; wParam
0x14003afc2  mov     edx, ebx; Msg
0x14003afc4  mov     rcx, rbp; hWnd
0x14003afc7  call    cs:__imp_DefWindowProcW
0x14003afcd  mov     r14, rax
0x14003afd0  jmp     loc_14003B0BB
0x14003afd5  mov     rax, cs:WPP_GLOBAL_Control
0x14003afdc  lea     rbx, WPP_GLOBAL_Control
0x14003afe3  cmp     rax, rbx
0x14003afe6  jz      short loc_14003B018
0x14003afe8  test    byte ptr [rax+1Ch], 1
0x14003afec  jz      short loc_14003B018
0x14003afee  cmp     byte ptr [rax+19h], 5
0x14003aff2  jb      short loc_14003B018
0x14003aff4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003aff9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b000  lea     r8, WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids
0x14003b007  mov     edx, 42h ; 'B'
0x14003b00c  mov     r9d, eax
0x14003b00f  mov     rcx, [rcx+10h]
0x14003b013  call    WPP_SF_d
0x14003b018  mov     rcx, rdi; this
0x14003b01b  call    ?SendServerReadyMessages@CClipServer@@AEAAJXZ; CClipServer::SendServerReadyMessages(void)
0x14003b020  mov     edi, eax
0x14003b022  test    eax, eax
0x14003b024  jns     loc_14003B0BB
0x14003b02a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b031  cmp     rcx, rbx
0x14003b034  jz      loc_14003B0BB
0x14003b03a  test    byte ptr [rcx+1Ch], 8
0x14003b03e  jz      short loc_14003B0BB
0x14003b040  cmp     byte ptr [rcx+19h], 2
0x14003b044  jb      short loc_14003B0BB
0x14003b046  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003b04b  mov     edx, 43h ; 'C'
0x14003b050  lea     rcx, aSendserverread_0; "SendServerReadyMessages failed!"
0x14003b057  jmp     loc_14003AF8F
0x14003b05c  mov     rax, cs:WPP_GLOBAL_Control
0x14003b063  lea     rbx, WPP_GLOBAL_Control
0x14003b06a  cmp     rax, rbx
0x14003b06d  jz      short loc_14003B09F
0x14003b06f  test    byte ptr [rax+1Ch], 1
0x14003b073  jz      short loc_14003B09F
0x14003b075  cmp     byte ptr [rax+19h], 5
0x14003b079  jb      short loc_14003B09F
0x14003b07b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003b080  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b087  lea     r8, WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids
0x14003b08e  mov     edx, 44h ; 'D'
0x14003b093  mov     r9d, eax
0x14003b096  mov     rcx, [rcx+10h]
0x14003b09a  call    WPP_SF_d
0x14003b09f  mov     rcx, rdi; this
0x14003b0a2  call    ?DetachFromSystemClipboard@CClipBase@@IEAAXXZ; CClipBase::DetachFromSystemClipboard(void)
0x14003b0a7  mov     rcx, [rdi+0E8h]; hWnd
0x14003b0ae  call    cs:__imp_DestroyWindow
0x14003b0b4  mov     [rdi+0E8h], r14
0x14003b0bb  mov     rax, r14
0x14003b0be  add     rsp, 40h
0x14003b0c2  pop     r14
0x14003b0c4  pop     rdi
0x14003b0c5  pop     rsi
0x14003b0c6  pop     rbp
0x14003b0c7  pop     rbx
0x14003b0c8  retn
```
