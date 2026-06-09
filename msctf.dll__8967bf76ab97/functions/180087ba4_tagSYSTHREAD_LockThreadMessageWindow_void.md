# tagSYSTHREAD::LockThreadMessageWindow(void)

- ea: `0x180087ba4`
- end: `0x180087d62`
- name: `?LockThreadMessageWindow@tagSYSTHREAD@@QEAAPEAUHWND__@@XZ`
- size: `446`
- prototype: `HWND __fastcall(tagSYSTHREAD *__hidden this)`
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000cb3c`
- `0x18000fcf0`
- `0x18002da10`
- `0x180087718`
- `0x1800af870`

## callees

- `0x18000fcf0`
- `0x180033e50`
- `0x180044090`
- `0x180061ba4`
- `0x180087ba4`
- `0x180087d68`
- `0x18008ced0`
- `0x180106a60`

## import_xrefs

- `USER32!ChangeWindowMessageFilterEx` at `0x180087cb7`
- `USER32!ChangeWindowMessageFilterEx` at `0x180087cd1`
- `USER32!ChangeWindowMessageFilterEx` at `0x180087cb7`
- `USER32!ChangeWindowMessageFilterEx` at `0x180087cd1`
- `USER32!CreateWindowExW` at `0x180087c4f`
- `USER32!CreateWindowExW` at `0x180087c4f`
- `USER32!IsWindow` at `0x180087bcf`
- `USER32!IsWindow` at `0x180087bcf`

## pseudocode

```c
HWND __fastcall tagSYSTHREAD::LockThreadMessageWindow(tagSYSTHREAD *this)
{
  HWND Window; // rax
  __int64 v4; // r8
  _BYTE v5[40]; // [rsp+60h] [rbp-78h] BYREF
  int v6; // [rsp+88h] [rbp-50h]
  int v7; // [rsp+98h] [rbp-40h]
  _BYTE v8[16]; // [rsp+B0h] [rbp-28h] BYREF

  ++*((_DWORD *)this + 86);
  if ( !IsWindow(*((HWND *)this + 17)) )
  {
    if ( !(unsigned int)EnsurePrivateMessages() )
      return 0;
    RegisterMarshalWndClass();
    Window = CreateWindowExW(
               0,
               L"CicMarshalWndClass",
               L"CicMarshalWnd",
               0x88000000,
               0,
               0,
               0,
               0,
               HWND_MESSAGE,
               0,
               g_hInst,
               0);
    *((_QWORD *)this + 17) = Window;
    if ( Window )
    {
      if ( (Microsoft_Windows_TSF_msctfEnableBits & 0x10) != 0 )
        McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_TSF_msctf_Context, CreatedMessageWindow, v4, 1, v8);
      if ( (NtCurrentPeb()->BitField & 0x20) == 0 )
      {
        ChangeWindowMessageFilterEx(*((HWND *)this + 17), g_msgRpcSendReceive, 1u, 0);
        ChangeWindowMessageFilterEx(*((HWND *)this + 17), g_msgPrivate, 1u, 0);
      }
      if ( (unsigned int)tagSYSTHREAD::IsConnected(this) )
      {
        MsgBase::MsgBase((MsgBase *)v5);
        v7 = *((_DWORD *)this + 34);
        v6 = 16777249;
        MsgBase::Send((MsgBase *)v5, 0);
      }
    }
    else if ( (Microsoft_Windows_TSF_msctfEnableBits & 0x20) != 0 )
    {
      McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_TSF_msctf_Context, FailedCreateMessageWindow, v4, 1, v8);
    }
  }
  return (HWND)*((_QWORD *)this + 17);
}

```

## disassembly

```asm
0x180087ba4  push    rbx
0x180087ba6  sub     rsp, 0D0h
0x180087bad  mov     rax, cs:__security_cookie
0x180087bb4  xor     rax, rsp
0x180087bb7  mov     [rsp+0D8h+var_18], rax
0x180087bbf  inc     dword ptr [rcx+158h]
0x180087bc5  mov     rbx, rcx
0x180087bc8  mov     rcx, [rcx+88h]; hWnd
0x180087bcf  call    cs:__imp_IsWindow
0x180087bd5  test    eax, eax
0x180087bd7  jnz     loc_180087D42
0x180087bdd  call    ?EnsurePrivateMessages@@YAHXZ; EnsurePrivateMessages(void)
0x180087be2  test    eax, eax
0x180087be4  jnz     short loc_180087BED
0x180087be6  xor     eax, eax
0x180087be8  jmp     loc_180087D49
0x180087bed  call    ?RegisterMarshalWndClass@@YAHXZ; RegisterMarshalWndClass(void)
0x180087bf2  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x180087bf9  lea     r8, ?c_szCicMarshalWnd@@3QBGB; "CicMarshalWnd"
0x180087c00  mov     [rsp+0D8h+lpParam], 0; lpParam
0x180087c09  lea     rdx, ?c_szCicMarshalClass@@3QBGB; "CicMarshalWndClass"
0x180087c10  mov     [rsp+0D8h+hInstance], rax; hInstance
0x180087c15  mov     r9d, 88000000h; dwStyle
0x180087c1b  mov     [rsp+0D8h+hMenu], 0; hMenu
0x180087c24  xor     ecx, ecx; dwExStyle
0x180087c26  mov     [rsp+0D8h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x180087c2f  mov     [rsp+0D8h+nHeight], 0; nHeight
0x180087c37  mov     [rsp+0D8h+nWidth], 0; nWidth
0x180087c3f  mov     [rsp+0D8h+Y], 0; Y
0x180087c47  mov     [rsp+0D8h+X], 0; X
0x180087c4f  call    cs:__imp_CreateWindowExW
0x180087c55  mov     [rbx+88h], rax
0x180087c5c  test    rax, rax
0x180087c5f  jz      loc_180087D13
0x180087c65  test    cs:Microsoft_Windows_TSF_msctfEnableBits, 10h
0x180087c6c  jz      short loc_180087C94
0x180087c6e  lea     rax, [rsp+0D8h+var_28]
0x180087c76  mov     r9d, 1
0x180087c7c  lea     rdx, CreatedMessageWindow
0x180087c83  mov     qword ptr [rsp+0D8h+X], rax
0x180087c88  lea     rcx, Microsoft_Windows_TSF_msctf_Context
0x180087c8f  call    McGenEventWrite_EventWriteTransfer
0x180087c94  mov     rax, gs:60h
0x180087c9d  test    byte ptr [rax+3], 20h
0x180087ca1  jnz     short loc_180087CD7
0x180087ca3  mov     edx, cs:?g_msgRpcSendReceive@@3IA; message
0x180087ca9  xor     r9d, r9d; pChangeFilterStruct
0x180087cac  mov     rcx, [rbx+88h]; hwnd
0x180087cb3  lea     r8d, [r9+1]; action
0x180087cb7  call    cs:__imp_ChangeWindowMessageFilterEx
0x180087cbd  mov     edx, cs:?g_msgPrivate@@3IA; message
0x180087cc3  xor     r9d, r9d; pChangeFilterStruct
0x180087cc6  mov     rcx, [rbx+88h]; hwnd
0x180087ccd  lea     r8d, [r9+1]; action
0x180087cd1  call    cs:__imp_ChangeWindowMessageFilterEx
0x180087cd7  mov     rcx, rbx; this
0x180087cda  call    ?IsConnected@tagSYSTHREAD@@QEAAHXZ; tagSYSTHREAD::IsConnected(void)
0x180087cdf  test    eax, eax
0x180087ce1  jz      short loc_180087D42
0x180087ce3  lea     rcx, [rsp+0D8h+var_78]; this
0x180087ce8  call    ??0MsgBase@@QEAA@XZ; MsgBase::MsgBase(void)
0x180087ced  mov     eax, [rbx+88h]
0x180087cf3  lea     rcx, [rsp+0D8h+var_78]; this
0x180087cf8  xor     edx, edx; unsigned int
0x180087cfa  mov     [rsp+0D8h+var_40], eax
0x180087d01  mov     [rsp+0D8h+var_50], 1000021h
0x180087d0c  call    ?Send@MsgBase@@QEAAJK@Z; MsgBase::Send(ulong)
0x180087d11  jmp     short loc_180087D42
0x180087d13  test    cs:Microsoft_Windows_TSF_msctfEnableBits, 20h
0x180087d1a  jz      short loc_180087D42
0x180087d1c  lea     rax, [rsp+0D8h+var_28]
0x180087d24  mov     r9d, 1
0x180087d2a  lea     rdx, FailedCreateMessageWindow
0x180087d31  mov     qword ptr [rsp+0D8h+X], rax
0x180087d36  lea     rcx, Microsoft_Windows_TSF_msctf_Context
0x180087d3d  call    McGenEventWrite_EventWriteTransfer
0x180087d42  mov     rax, [rbx+88h]
0x180087d49  mov     rcx, [rsp+0D8h+var_18]
0x180087d51  xor     rcx, rsp; StackCookie
0x180087d54  call    __security_check_cookie
0x180087d59  add     rsp, 0D0h
0x180087d60  pop     rbx
0x180087d61  retn
```
