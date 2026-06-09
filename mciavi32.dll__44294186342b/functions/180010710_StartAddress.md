# StartAddress

- ea: `0x180010710`
- end: `0x18001089b`
- name: `StartAddress`
- size: `395`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180001400`
- `0x18000d1a8`
- `0x180010710`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010840`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010840`
- `GDI32!GdiFlush` at `0x180010875`
- `GDI32!GdiFlush` at `0x180010875`
- `USER32!TranslateMessage` at `0x18001084d`
- `USER32!TranslateMessage` at `0x18001084d`
- `USER32!GetSystemMetrics` at `0x18001076c`
- `USER32!GetSystemMetrics` at `0x180010776`
- `USER32!GetSystemMetrics` at `0x18001076c`
- `USER32!GetSystemMetrics` at `0x180010776`
- `USER32!DispatchMessageW` at `0x180010858`
- `USER32!DispatchMessageW` at `0x180010858`
- `USER32!CreateWindowExW` at `0x180010813`
- `USER32!CreateWindowExW` at `0x180010813`
- `USER32!GetMessageW` at `0x18001086b`
- `USER32!GetMessageW` at `0x18001086b`

## pseudocode

```c
DWORD __fastcall StartAddress(LPVOID lpThreadParameter)
{
  bool v1; // zf
  HWND hWndParent; // r15
  DWORD v4; // ebp
  const WCHAR *v5; // rbx
  int nHeight; // esi
  int nWidth; // edi
  const WCHAR *v8; // r8
  HWND Window; // rax
  const WCHAR *v10; // r8
  MSG Msg; // [rsp+60h] [rbp-78h] BYREF

  v1 = *((_DWORD *)lpThreadParameter + 122) == -1;
  hWndParent = (HWND)*((_QWORD *)lpThreadParameter + 62);
  memset(&Msg, 0, sizeof(Msg));
  if ( v1 )
  {
    *((_DWORD *)lpThreadParameter + 122) = 114163712;
    v10 = (const WCHAR *)sub_18000D1A8(*((LPCWSTR *)lpThreadParameter + 64));
    Window = CreateWindowExW(
               0,
               ClassName,
               v10,
               0x6CE0000u,
               0x80000000,
               0,
               0x80000000,
               0,
               hWndParent,
               0,
               hmod,
               lpThreadParameter);
  }
  else
  {
    v4 = *((_DWORD *)lpThreadParameter + 122);
    v5 = (const WCHAR *)*((_QWORD *)lpThreadParameter + 64);
    nHeight = GetSystemMetrics(1);
    nWidth = GetSystemMetrics(0);
    v8 = (const WCHAR *)sub_18000D1A8(v5);
    Window = CreateWindowExW(0, ClassName, v8, v4, 0, 0, nWidth, nHeight, hWndParent, 0, hmod, lpThreadParameter);
  }
  *((_QWORD *)lpThreadParameter + 51) = Window;
  *((_QWORD *)lpThreadParameter + 50) = Window;
  if ( Window )
  {
    SetEvent(*((HANDLE *)lpThreadParameter + 29));
    while ( GetMessageW(&Msg, 0, 0, 0) )
    {
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
    LODWORD(Window) = GdiFlush();
  }
  else
  {
    *((_DWORD *)lpThreadParameter + 32) = 347;
  }
  return (unsigned int)Window;
}

```

## disassembly

```asm
0x180010710  push    rbx
0x180010712  push    rbp
0x180010713  push    rsi
0x180010714  push    rdi
0x180010715  push    r14
0x180010717  push    r15
0x180010719  sub     rsp, 0A8h
0x180010720  mov     rax, cs:__security_cookie
0x180010727  xor     rax, rsp
0x18001072a  mov     [rsp+0D8h+var_48], rax
0x180010732  cmp     dword ptr [rcx+1E8h], 0FFFFFFFFh
0x180010739  xorps   xmm0, xmm0
0x18001073c  mov     r15, [rcx+1F0h]
0x180010743  mov     r14, rcx
0x180010746  movups  xmmword ptr [rsp+0D8h+Msg.hwnd], xmm0
0x18001074b  movups  xmmword ptr [rsp+0D8h+Msg.wParam], xmm0
0x180010750  movups  xmmword ptr [rsp+0D8h+Msg.time], xmm0
0x180010758  jz      short loc_1800107BB
0x18001075a  mov     ebp, [rcx+1E8h]
0x180010760  mov     rbx, [rcx+200h]
0x180010767  mov     ecx, 1; nIndex
0x18001076c  call    cs:GetSystemMetrics
0x180010772  xor     ecx, ecx; nIndex
0x180010774  mov     esi, eax
0x180010776  call    cs:GetSystemMetrics
0x18001077c  mov     rcx, rbx; lpszStart
0x18001077f  mov     edi, eax
0x180010781  call    sub_18000D1A8
0x180010786  mov     rcx, cs:hmod
0x18001078d  xor     ebx, ebx
0x18001078f  mov     [rsp+0D8h+lpParam], r14
0x180010794  mov     r8, rax
0x180010797  mov     [rsp+0D8h+hInstance], rcx
0x18001079c  mov     r9d, ebp
0x18001079f  mov     [rsp+0D8h+hMenu], rbx
0x1800107a4  mov     [rsp+0D8h+hWndParent], r15
0x1800107a9  mov     [rsp+0D8h+nHeight], esi
0x1800107ad  mov     [rsp+0D8h+nWidth], edi
0x1800107b1  mov     [rsp+0D8h+Y], ebx
0x1800107b5  mov     [rsp+0D8h+X], ebx
0x1800107b9  jmp     short loc_18001080A
0x1800107bb  mov     edi, 6CE0000h
0x1800107c0  mov     [rcx+1E8h], edi
0x1800107c6  mov     rcx, [rcx+200h]; lpszStart
0x1800107cd  call    sub_18000D1A8
0x1800107d2  mov     [rsp+0D8h+lpParam], r14; lpParam
0x1800107d7  xor     ebx, ebx
0x1800107d9  mov     r8, rax; lpWindowName
0x1800107dc  mov     r9d, edi; dwStyle
0x1800107df  mov     rax, cs:hmod
0x1800107e6  mov     [rsp+0D8h+hInstance], rax; hInstance
0x1800107eb  mov     eax, 80000000h
0x1800107f0  mov     [rsp+0D8h+hMenu], rbx; hMenu
0x1800107f5  mov     [rsp+0D8h+hWndParent], r15; hWndParent
0x1800107fa  mov     [rsp+0D8h+nHeight], ebx; nHeight
0x1800107fe  mov     [rsp+0D8h+nWidth], eax; nWidth
0x180010802  mov     [rsp+0D8h+Y], ebx; Y
0x180010806  mov     [rsp+0D8h+X], eax; X
0x18001080a  lea     rdx, ClassName; "AVIWnd32"
0x180010811  xor     ecx, ecx; dwExStyle
0x180010813  call    cs:CreateWindowExW
0x180010819  mov     [r14+198h], rax
0x180010820  mov     [r14+190h], rax
0x180010827  test    rax, rax
0x18001082a  jnz     short loc_180010839
0x18001082c  mov     dword ptr [r14+80h], 15Bh
0x180010837  jmp     short loc_18001087B
0x180010839  mov     rcx, [r14+0E8h]; hEvent
0x180010840  call    cs:SetEvent
0x180010846  jmp     short loc_18001085E
0x180010848  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x18001084d  call    cs:TranslateMessage
0x180010853  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180010858  call    cs:DispatchMessageW
0x18001085e  xor     r9d, r9d; wMsgFilterMax
0x180010861  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180010866  xor     r8d, r8d; wMsgFilterMin
0x180010869  xor     edx, edx; hWnd
0x18001086b  call    cs:GetMessageW
0x180010871  test    eax, eax
0x180010873  jnz     short loc_180010848
0x180010875  call    cs:GdiFlush
0x18001087b  mov     rcx, [rsp+0D8h+var_48]
0x180010883  xor     rcx, rsp; StackCookie
0x180010886  call    __security_check_cookie
0x18001088b  add     rsp, 0A8h
0x180010892  pop     r15
0x180010894  pop     r14
0x180010896  pop     rdi
0x180010897  pop     rsi
0x180010898  pop     rbp
0x180010899  pop     rbx
0x18001089a  retn
```
