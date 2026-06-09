# CTscFrameWnd::CreateWnd(HINSTANCE__ *,HWND__ *,ushort const *,ushort const *,ulong,tagRECT *,HICON__ *)

- ea: `0x14004d04c`
- end: `0x14004d27e`
- name: `?CreateWnd@CTscFrameWnd@@QEAAPEAUHWND__@@PEAUHINSTANCE__@@PEAU2@PEBG2KPEAUtagRECT@@PEAUHICON__@@@Z`
- size: `562`
- prototype: `HWND __usercall@<rax>(LONG_PTR dwNewLong@<rcx>, HINSTANCE hInstance@<rdx>, HWND@<r8>, const unsigned __int16 *@<r9>, LPCWSTR lpWindowName, unsigned int, struct tagRECT *, HICON)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140014918`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14004d04c`

## import_xrefs

- `USER32!LoadCursorW` at `0x14004d0bd`
- `USER32!LoadCursorW` at `0x14004d0bd`
- `USER32!SetWindowLongPtrW` at `0x14004d1d1`
- `USER32!SetWindowLongPtrW` at `0x14004d1d1`
- `USER32!RegisterClassExW` at `0x14004d0e6`
- `USER32!RegisterClassExW` at `0x14004d0e6`
- `USER32!CreateWindowExW` at `0x14004d1ae`
- `USER32!CreateWindowExW` at `0x14004d1ae`
- `KERNEL32!GetLastError` at `0x14004d0f3`
- `KERNEL32!GetLastError` at `0x14004d12b`
- `KERNEL32!GetLastError` at `0x14004d1dc`
- `KERNEL32!GetLastError` at `0x14004d205`
- `KERNEL32!GetLastError` at `0x14004d23e`
- `KERNEL32!GetLastError` at `0x14004d0f3`
- `KERNEL32!GetLastError` at `0x14004d12b`
- `KERNEL32!GetLastError` at `0x14004d1dc`
- `KERNEL32!GetLastError` at `0x14004d205`
- `KERNEL32!GetLastError` at `0x14004d23e`
- `KERNEL32!SetLastError` at `0x14004d1bf`
- `KERNEL32!SetLastError` at `0x14004d1bf`

## pseudocode

```c
HWND __fastcall CTscFrameWnd::CreateWnd(
        LONG_PTR dwNewLong,
        HINSTANCE hInstance,
        HWND a3,
        const unsigned __int16 *a4,
        LPCWSTR lpWindowName,
        unsigned int a6,
        struct tagRECT *a7)
{
  HCURSOR CursorW; // rax
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HWND Window; // rax
  DWORD v13; // ebx
  unsigned int v14; // eax
  __int64 v15; // rdx
  WNDCLASSEXW v17; // [rsp+60h] [rbp-39h] BYREF

  if ( !hInstance || !a7 )
    return 0;
  *(_QWORD *)(dwNewLong + 16) = hInstance;
  memset_0(&v17, 0, sizeof(v17));
  *(_QWORD *)&v17.cbSize = 80;
  v17.lpfnWndProc = (WNDPROC)CTscFrameWnd::StaticTscFrameWndProc;
  *(_QWORD *)&v17.cbClsExtra = 0;
  v17.hInstance = hInstance;
  v17.hIcon = 0;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
  v17.hIconSm = 0;
  *(_OWORD *)&v17.hbrBackground = 0;
  v17.hCursor = CursorW;
  v17.lpszClassName = L"TscShellContainerClass";
  if ( !RegisterClassExW(&v17) && GetLastError() != 1410 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_f9a3c41804e03f33d37ef739edf3a6e3_Traceguids,
        CurrentThreadActivityIdPrefix,
        LastError);
    }
    return 0;
  }
  Window = CreateWindowExW(
             0,
             L"TscShellContainerClass",
             lpWindowName,
             0x6CF0100u,
             0,
             0,
             a7->right - a7->left,
             a7->bottom - a7->top,
             0,
             0,
             hInstance,
             (LPVOID)dwNewLong);
  *(_QWORD *)(dwNewLong + 8) = Window;
  if ( !Window )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v13 = GetLastError();
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 12;
    goto LABEL_21;
  }
  SetLastError(0);
  if ( SetWindowLongPtrW(*(HWND *)(dwNewLong + 8), -21, dwNewLong) || !GetLastError() )
    return *(HWND *)(dwNewLong + 8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = GetLastError();
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 11;
LABEL_21:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_f9a3c41804e03f33d37ef739edf3a6e3_Traceguids, v14, v13);
  }
  return 0;
}

```

## disassembly

```asm
0x14004d04c  push    rbp
0x14004d04e  push    rbx
0x14004d04f  push    rsi
0x14004d050  push    rdi
0x14004d051  push    r14
0x14004d053  lea     rbp, [rsp-17h]
0x14004d058  sub     rsp, 0B0h
0x14004d05f  mov     rsi, rdx
0x14004d062  mov     rbx, rcx
0x14004d065  test    rdx, rdx
0x14004d068  jz      loc_14004D26E
0x14004d06e  mov     rdi, [rbp+37h+arg_30]
0x14004d072  test    rdi, rdi
0x14004d075  jz      loc_14004D26E
0x14004d07b  mov     [rcx+10h], rdx
0x14004d07f  mov     r14d, 50h ; 'P'
0x14004d085  mov     r8d, r14d; Size
0x14004d088  lea     rcx, [rbp+37h+var_70]; void *
0x14004d08c  xor     edx, edx; Val
0x14004d08e  call    memset_0
0x14004d093  lea     rax, ?StaticTscFrameWndProc@CTscFrameWnd@@CA_JPEAUHWND__@@I_K_J@Z; CTscFrameWnd::StaticTscFrameWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x14004d09a  mov     qword ptr [rbp+37h+var_70.cbSize], r14
0x14004d09e  mov     edx, 7F00h; lpCursorName
0x14004d0a3  mov     [rbp+37h+var_70.lpfnWndProc], rax
0x14004d0a7  xor     ecx, ecx; hInstance
0x14004d0a9  mov     qword ptr [rbp+37h+var_70.cbClsExtra], 0
0x14004d0b1  mov     [rbp+37h+var_70.hInstance], rsi
0x14004d0b5  mov     [rbp+37h+var_70.hIcon], 0
0x14004d0bd  call    cs:__imp_LoadCursorW
0x14004d0c3  xorps   xmm0, xmm0
0x14004d0c6  mov     [rbp+37h+var_70.hIconSm], 0
0x14004d0ce  lea     r14, aTscshellcontai; "TscShellContainerClass"
0x14004d0d5  movdqa  xmmword ptr [rbp+37h+var_70.hbrBackground], xmm0
0x14004d0da  lea     rcx, [rbp+37h+var_70]; WNDCLASSEXW *
0x14004d0de  mov     [rbp+37h+var_70.hCursor], rax
0x14004d0e2  mov     [rbp+37h+var_70.lpszClassName], r14
0x14004d0e6  call    cs:__imp_RegisterClassExW
0x14004d0ec  xor     ecx, ecx
0x14004d0ee  cmp     cx, ax
0x14004d0f1  jnz     short loc_14004D160
0x14004d0f3  call    cs:__imp_GetLastError
0x14004d0f9  cmp     eax, 582h
0x14004d0fe  jz      short loc_14004D160
0x14004d100  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d107  lea     rax, WPP_GLOBAL_Control
0x14004d10e  cmp     rcx, rax
0x14004d111  jz      loc_14004D26E
0x14004d117  test    byte ptr [rcx+1Ch], 1
0x14004d11b  jz      loc_14004D26E
0x14004d121  cmp     byte ptr [rcx+19h], 2
0x14004d125  jb      loc_14004D26E
0x14004d12b  call    cs:__imp_GetLastError
0x14004d131  mov     ebx, eax
0x14004d133  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004d138  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d13f  lea     r8, WPP_f9a3c41804e03f33d37ef739edf3a6e3_Traceguids
0x14004d146  mov     edx, 0Ah
0x14004d14b  mov     [rsp+0D0h+X], ebx
0x14004d14f  mov     r9d, eax
0x14004d152  mov     rcx, [rcx+10h]
0x14004d156  call    WPP_SF_Dd
0x14004d15b  jmp     loc_14004D26E
0x14004d160  mov     ecx, [rdi+0Ch]
0x14004d163  mov     r9d, 6CF0100h; dwStyle
0x14004d169  sub     ecx, [rdi+4]
0x14004d16c  mov     rdx, r14; lpClassName
0x14004d16f  mov     eax, [rdi+8]
0x14004d172  sub     eax, [rdi]
0x14004d174  mov     r8, [rbp+37h+lpWindowName]; lpWindowName
0x14004d178  mov     [rsp+0D0h+lpParam], rbx; lpParam
0x14004d17d  mov     [rsp+0D0h+hInstance], rsi; hInstance
0x14004d182  mov     [rsp+0D0h+hMenu], 0; hMenu
0x14004d18b  mov     [rsp+0D0h+hWndParent], 0; hWndParent
0x14004d194  mov     [rsp+0D0h+nHeight], ecx; nHeight
0x14004d198  xor     ecx, ecx; dwExStyle
0x14004d19a  mov     [rsp+0D0h+nWidth], eax; nWidth
0x14004d19e  mov     [rsp+0D0h+Y], 0; Y
0x14004d1a6  mov     [rsp+0D0h+X], 0; X
0x14004d1ae  call    cs:__imp_CreateWindowExW
0x14004d1b4  mov     [rbx+8], rax
0x14004d1b8  test    rax, rax
0x14004d1bb  jz      short loc_14004D21F
0x14004d1bd  xor     ecx, ecx; dwErrCode
0x14004d1bf  call    cs:__imp_SetLastError
0x14004d1c5  mov     rcx, [rbx+8]; hWnd
0x14004d1c9  mov     r8, rbx; dwNewLong
0x14004d1cc  mov     edx, 0FFFFFFEBh; nIndex
0x14004d1d1  call    cs:__imp_SetWindowLongPtrW
0x14004d1d7  test    rax, rax
0x14004d1da  jnz     short loc_14004D219
0x14004d1dc  call    cs:__imp_GetLastError
0x14004d1e2  test    eax, eax
0x14004d1e4  jz      short loc_14004D219
0x14004d1e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d1ed  lea     rax, WPP_GLOBAL_Control
0x14004d1f4  cmp     rcx, rax
0x14004d1f7  jz      short loc_14004D26E
0x14004d1f9  test    byte ptr [rcx+1Ch], 1
0x14004d1fd  jz      short loc_14004D26E
0x14004d1ff  cmp     byte ptr [rcx+19h], 2
0x14004d203  jb      short loc_14004D26E
0x14004d205  call    cs:__imp_GetLastError
0x14004d20b  mov     ebx, eax
0x14004d20d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004d212  mov     edx, 0Bh
0x14004d217  jmp     short loc_14004D250
0x14004d219  mov     rax, [rbx+8]
0x14004d21d  jmp     short loc_14004D270
0x14004d21f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d226  lea     rax, WPP_GLOBAL_Control
0x14004d22d  cmp     rcx, rax
0x14004d230  jz      short loc_14004D26E
0x14004d232  test    byte ptr [rcx+1Ch], 1
0x14004d236  jz      short loc_14004D26E
0x14004d238  cmp     byte ptr [rcx+19h], 2
0x14004d23c  jb      short loc_14004D26E
0x14004d23e  call    cs:__imp_GetLastError
0x14004d244  mov     ebx, eax
0x14004d246  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004d24b  mov     edx, 0Ch
0x14004d250  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d257  lea     r8, WPP_f9a3c41804e03f33d37ef739edf3a6e3_Traceguids
0x14004d25e  mov     r9d, eax
0x14004d261  mov     [rsp+0D0h+X], ebx
0x14004d265  mov     rcx, [rcx+10h]
0x14004d269  call    WPP_SF_Dd
0x14004d26e  xor     eax, eax
0x14004d270  add     rsp, 0B0h
0x14004d277  pop     r14
0x14004d279  pop     rdi
0x14004d27a  pop     rsi
0x14004d27b  pop     rbx
0x14004d27c  pop     rbp
0x14004d27d  retn
```
