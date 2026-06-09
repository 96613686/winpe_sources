# CTimer::RunTimer(void)

- ea: `0x140008064`
- end: `0x1400081a1`
- name: `?RunTimer@CTimer@@IEAAKXZ`
- size: `317`
- prototype: `unsigned int __fastcall(CTimer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140009770`

## callees

- `0x140008064`
- `0x14001619a`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1400080e8`
- `KERNEL32!SetEvent` at `0x14000814d`
- `KERNEL32!SetEvent` at `0x1400080e8`
- `KERNEL32!SetEvent` at `0x14000814d`
- `KERNEL32!GetLastError` at `0x1400080ee`
- `KERNEL32!GetLastError` at `0x1400080ee`
- `USER32!RegisterClassA` at `0x1400080d9`
- `USER32!RegisterClassA` at `0x1400080d9`
- `USER32!CreateWindowExA` at `0x140008138`
- `USER32!CreateWindowExA` at `0x140008138`
- `USER32!GetClassInfoA` at `0x1400080a7`
- `USER32!GetClassInfoA` at `0x1400080a7`
- `USER32!GetMessageA` at `0x140008180`
- `USER32!GetMessageA` at `0x140008180`
- `USER32!DispatchMessageA` at `0x14000816d`
- `USER32!DispatchMessageA` at `0x14000816d`

## pseudocode

```c
DWORD __fastcall CTimer::RunTimer(CTimer *this)
{
  void *v2; // rcx
  DWORD result; // eax
  HWND Window; // rax
  int MessageA; // eax
  MSG Msg; // [rsp+60h] [rbp-29h] BYREF
  tagWNDCLASSA WndClass; // [rsp+90h] [rbp+7h] BYREF

  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.hInstance = Global::g_hInstance;
  WndClass.lpszClassName = "WSH-Timer";
  if ( !GetClassInfoA(Global::g_hInstance, "WSH-Timer", &WndClass) )
  {
    WndClass.style = 0;
    WndClass.lpfnWndProc = (WNDPROC)CTimer::WindowProc;
    memset(&WndClass.hIcon, 0, 32);
    *(_QWORD *)&WndClass.cbClsExtra = 0;
    if ( !RegisterClassA(&WndClass) )
    {
      v2 = (void *)*((_QWORD *)this + 6);
LABEL_4:
      SetEvent(v2);
      result = GetLastError();
      *((_DWORD *)this + 6) = result;
      return result;
    }
  }
  Window = CreateWindowExA(0, WndClass.lpszClassName, 0, 0, 0, 0, 1, 1, 0, 0, Global::g_hInstance, this);
  v2 = (void *)*((_QWORD *)this + 6);
  *(_QWORD *)this = Window;
  if ( !Window )
    goto LABEL_4;
  *((_DWORD *)this + 6) = 0;
  SetEvent(v2);
  memset(&Msg, 0, sizeof(Msg));
  while ( 1 )
  {
    MessageA = GetMessageA(&Msg, *(HWND *)this, 0, 0);
    if ( !MessageA || MessageA == -1 )
      break;
    DispatchMessageA(&Msg);
  }
  return 0;
}

```

## disassembly

```asm
0x140008064  mov     [rsp-8+arg_0], rbx
0x140008069  mov     [rsp-8+arg_8], rdi
0x14000806e  push    rbp
0x14000806f  lea     rbp, [rsp-57h]
0x140008074  sub     rsp, 0E0h
0x14000807b  xor     edx, edx; Val
0x14000807d  mov     rbx, rcx
0x140008080  lea     rcx, [rbp+57h+WndClass]; void *
0x140008084  lea     r8d, [rdx+48h]; Size
0x140008088  call    memset_0
0x14000808d  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x140008094  lea     rdx, ClassName; "WSH-Timer"
0x14000809b  lea     r8, [rbp+57h+WndClass]; lpWndClass
0x14000809f  mov     [rbp+57h+WndClass.hInstance], rcx
0x1400080a3  mov     [rbp+57h+WndClass.lpszClassName], rdx
0x1400080a7  call    cs:__imp_GetClassInfoA
0x1400080ad  xor     edi, edi
0x1400080af  test    eax, eax
0x1400080b1  jnz     short loc_1400080FC
0x1400080b3  lea     rax, ?WindowProc@CTimer@@KA_JPEAUHWND__@@I_K_J@Z; CTimer::WindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x1400080ba  mov     [rbp+57h+WndClass.style], edi
0x1400080bd  xorps   xmm0, xmm0
0x1400080c0  mov     [rbp+57h+WndClass.lpfnWndProc], rax
0x1400080c4  xorps   xmm1, xmm1
0x1400080c7  movdqa  xmmword ptr [rbp+57h+WndClass.hIcon], xmm0
0x1400080cc  lea     rcx, [rbp+57h+WndClass]; lpWndClass
0x1400080d0  movdqa  xmmword ptr [rbp+57h+WndClass.hbrBackground], xmm1
0x1400080d5  mov     qword ptr [rbp+57h+WndClass.cbClsExtra], rdi
0x1400080d9  call    cs:__imp_RegisterClassA
0x1400080df  test    ax, ax
0x1400080e2  jnz     short loc_1400080FC
0x1400080e4  mov     rcx, [rbx+30h]; hEvent
0x1400080e8  call    cs:__imp_SetEvent
0x1400080ee  call    cs:__imp_GetLastError
0x1400080f4  mov     [rbx+18h], eax
0x1400080f7  jmp     loc_14000818C
0x1400080fc  mov     rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x140008103  xor     r9d, r9d; dwStyle
0x140008106  mov     rdx, [rbp+57h+WndClass.lpszClassName]; lpClassName
0x14000810a  xor     r8d, r8d; lpWindowName
0x14000810d  mov     [rsp+0E0h+lpParam], rbx; lpParam
0x140008112  xor     ecx, ecx; dwExStyle
0x140008114  mov     [rsp+0E0h+hInstance], rax; hInstance
0x140008119  mov     eax, 1
0x14000811e  mov     [rsp+0E0h+hMenu], rdi; hMenu
0x140008123  mov     [rsp+0E0h+hWndParent], rdi; hWndParent
0x140008128  mov     [rsp+0E0h+nHeight], eax; nHeight
0x14000812c  mov     [rsp+0E0h+nWidth], eax; nWidth
0x140008130  mov     [rsp+0E0h+Y], edi; Y
0x140008134  mov     [rsp+0E0h+X], edi; X
0x140008138  call    cs:__imp_CreateWindowExA
0x14000813e  mov     rcx, [rbx+30h]; hEvent
0x140008142  mov     [rbx], rax
0x140008145  test    rax, rax
0x140008148  jz      short loc_1400080E8
0x14000814a  mov     [rbx+18h], edi
0x14000814d  call    cs:__imp_SetEvent
0x140008153  xorps   xmm0, xmm0
0x140008156  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x14000815a  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x14000815e  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x140008162  jmp     short loc_140008173
0x140008164  cmp     eax, 0FFFFFFFFh
0x140008167  jz      short loc_14000818A
0x140008169  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14000816d  call    cs:__imp_DispatchMessageA
0x140008173  mov     rdx, [rbx]; hWnd
0x140008176  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14000817a  xor     r9d, r9d; wMsgFilterMax
0x14000817d  xor     r8d, r8d; wMsgFilterMin
0x140008180  call    cs:__imp_GetMessageA
0x140008186  test    eax, eax
0x140008188  jnz     short loc_140008164
0x14000818a  xor     eax, eax
0x14000818c  lea     r11, [rsp+0E0h+var_s0]
0x140008194  mov     rbx, [r11+10h]
0x140008198  mov     rdi, [r11+18h]
0x14000819c  mov     rsp, r11
0x14000819f  pop     rbp
0x1400081a0  retn
```
