# CTscFrameWnd::CreateWnd(HINSTANCE__ *,HWND__ *,ushort const *,ushort const *,ulong,tagRECT *,HICON__ *)

- ea: `0x14004aedc`
- end: `0x14004b10e`
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
- `0x14004aedc`

## import_xrefs

- `USER32!LoadCursorW` at `0x14004af4d`
- `USER32!LoadCursorW` at `0x14004af4d`
- `USER32!SetWindowLongPtrW` at `0x14004b061`
- `USER32!SetWindowLongPtrW` at `0x14004b061`
- `USER32!RegisterClassExW` at `0x14004af76`
- `USER32!RegisterClassExW` at `0x14004af76`
- `USER32!CreateWindowExW` at `0x14004b03e`
- `USER32!CreateWindowExW` at `0x14004b03e`
- `KERNEL32!GetLastError` at `0x14004af83`
- `KERNEL32!GetLastError` at `0x14004afbb`
- `KERNEL32!GetLastError` at `0x14004b06c`
- `KERNEL32!GetLastError` at `0x14004b095`
- `KERNEL32!GetLastError` at `0x14004b0ce`
- `KERNEL32!GetLastError` at `0x14004af83`
- `KERNEL32!GetLastError` at `0x14004afbb`
- `KERNEL32!GetLastError` at `0x14004b06c`
- `KERNEL32!GetLastError` at `0x14004b095`
- `KERNEL32!GetLastError` at `0x14004b0ce`
- `KERNEL32!SetLastError` at `0x14004b04f`
- `KERNEL32!SetLastError` at `0x14004b04f`

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
0x14004aedc  push    rbp
0x14004aede  push    rbx
0x14004aedf  push    rsi
0x14004aee0  push    rdi
0x14004aee1  push    r14
0x14004aee3  lea     rbp, [rsp-17h]
0x14004aee8  sub     rsp, 0B0h
0x14004aeef  mov     rsi, rdx
0x14004aef2  mov     rbx, rcx
0x14004aef5  test    rdx, rdx
0x14004aef8  jz      loc_14004B0FE
0x14004aefe  mov     rdi, [rbp+37h+arg_30]
0x14004af02  test    rdi, rdi
0x14004af05  jz      loc_14004B0FE
0x14004af0b  mov     [rcx+10h], rdx
0x14004af0f  mov     r14d, 50h ; 'P'
0x14004af15  mov     r8d, r14d; Size
0x14004af18  lea     rcx, [rbp+37h+var_70]; void *
0x14004af1c  xor     edx, edx; Val
0x14004af1e  call    memset_0
0x14004af23  lea     rax, ?StaticTscFrameWndProc@CTscFrameWnd@@CA_JPEAUHWND__@@I_K_J@Z; CTscFrameWnd::StaticTscFrameWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x14004af2a  mov     qword ptr [rbp+37h+var_70.cbSize], r14
0x14004af2e  mov     edx, 7F00h; lpCursorName
0x14004af33  mov     [rbp+37h+var_70.lpfnWndProc], rax
0x14004af37  xor     ecx, ecx; hInstance
0x14004af39  mov     qword ptr [rbp+37h+var_70.cbClsExtra], 0
0x14004af41  mov     [rbp+37h+var_70.hInstance], rsi
0x14004af45  mov     [rbp+37h+var_70.hIcon], 0
0x14004af4d  call    cs:__imp_LoadCursorW
0x14004af53  xorps   xmm0, xmm0
0x14004af56  mov     [rbp+37h+var_70.hIconSm], 0
0x14004af5e  lea     r14, aTscshellcontai; "TscShellContainerClass"
0x14004af65  movdqa  xmmword ptr [rbp+37h+var_70.hbrBackground], xmm0
0x14004af6a  lea     rcx, [rbp+37h+var_70]; WNDCLASSEXW *
0x14004af6e  mov     [rbp+37h+var_70.hCursor], rax
0x14004af72  mov     [rbp+37h+var_70.lpszClassName], r14
0x14004af76  call    cs:__imp_RegisterClassExW
0x14004af7c  xor     ecx, ecx
0x14004af7e  cmp     cx, ax
0x14004af81  jnz     short loc_14004AFF0
0x14004af83  call    cs:__imp_GetLastError
0x14004af89  cmp     eax, 582h
0x14004af8e  jz      short loc_14004AFF0
0x14004af90  mov     rcx, cs:WPP_GLOBAL_Control
0x14004af97  lea     rax, WPP_GLOBAL_Control
0x14004af9e  cmp     rcx, rax
0x14004afa1  jz      loc_14004B0FE
0x14004afa7  test    byte ptr [rcx+1Ch], 1
0x14004afab  jz      loc_14004B0FE
0x14004afb1  cmp     byte ptr [rcx+19h], 2
0x14004afb5  jb      loc_14004B0FE
0x14004afbb  call    cs:__imp_GetLastError
0x14004afc1  mov     ebx, eax
0x14004afc3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004afc8  mov     rcx, cs:WPP_GLOBAL_Control
0x14004afcf  lea     r8, WPP_f9a3c41804e03f33d37ef739edf3a6e3_Traceguids
0x14004afd6  mov     edx, 0Ah
0x14004afdb  mov     [rsp+0D0h+X], ebx
0x14004afdf  mov     r9d, eax
0x14004afe2  mov     rcx, [rcx+10h]
0x14004afe6  call    WPP_SF_Dd
0x14004afeb  jmp     loc_14004B0FE
0x14004aff0  mov     ecx, [rdi+0Ch]
0x14004aff3  mov     r9d, 6CF0100h; dwStyle
0x14004aff9  sub     ecx, [rdi+4]
0x14004affc  mov     rdx, r14; lpClassName
0x14004afff  mov     eax, [rdi+8]
0x14004b002  sub     eax, [rdi]
0x14004b004  mov     r8, [rbp+37h+lpWindowName]; lpWindowName
0x14004b008  mov     [rsp+0D0h+lpParam], rbx; lpParam
0x14004b00d  mov     [rsp+0D0h+hInstance], rsi; hInstance
0x14004b012  mov     [rsp+0D0h+hMenu], 0; hMenu
0x14004b01b  mov     [rsp+0D0h+hWndParent], 0; hWndParent
0x14004b024  mov     [rsp+0D0h+nHeight], ecx; nHeight
0x14004b028  xor     ecx, ecx; dwExStyle
0x14004b02a  mov     [rsp+0D0h+nWidth], eax; nWidth
0x14004b02e  mov     [rsp+0D0h+Y], 0; Y
0x14004b036  mov     [rsp+0D0h+X], 0; X
0x14004b03e  call    cs:__imp_CreateWindowExW
0x14004b044  mov     [rbx+8], rax
0x14004b048  test    rax, rax
0x14004b04b  jz      short loc_14004B0AF
0x14004b04d  xor     ecx, ecx; dwErrCode
0x14004b04f  call    cs:__imp_SetLastError
0x14004b055  mov     rcx, [rbx+8]; hWnd
0x14004b059  mov     r8, rbx; dwNewLong
0x14004b05c  mov     edx, 0FFFFFFEBh; nIndex
0x14004b061  call    cs:__imp_SetWindowLongPtrW
0x14004b067  test    rax, rax
0x14004b06a  jnz     short loc_14004B0A9
0x14004b06c  call    cs:__imp_GetLastError
0x14004b072  test    eax, eax
0x14004b074  jz      short loc_14004B0A9
0x14004b076  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b07d  lea     rax, WPP_GLOBAL_Control
0x14004b084  cmp     rcx, rax
0x14004b087  jz      short loc_14004B0FE
0x14004b089  test    byte ptr [rcx+1Ch], 1
0x14004b08d  jz      short loc_14004B0FE
0x14004b08f  cmp     byte ptr [rcx+19h], 2
0x14004b093  jb      short loc_14004B0FE
0x14004b095  call    cs:__imp_GetLastError
0x14004b09b  mov     ebx, eax
0x14004b09d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004b0a2  mov     edx, 0Bh
0x14004b0a7  jmp     short loc_14004B0E0
0x14004b0a9  mov     rax, [rbx+8]
0x14004b0ad  jmp     short loc_14004B100
0x14004b0af  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b0b6  lea     rax, WPP_GLOBAL_Control
0x14004b0bd  cmp     rcx, rax
0x14004b0c0  jz      short loc_14004B0FE
0x14004b0c2  test    byte ptr [rcx+1Ch], 1
0x14004b0c6  jz      short loc_14004B0FE
0x14004b0c8  cmp     byte ptr [rcx+19h], 2
0x14004b0cc  jb      short loc_14004B0FE
0x14004b0ce  call    cs:__imp_GetLastError
0x14004b0d4  mov     ebx, eax
0x14004b0d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004b0db  mov     edx, 0Ch
0x14004b0e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b0e7  lea     r8, WPP_f9a3c41804e03f33d37ef739edf3a6e3_Traceguids
0x14004b0ee  mov     r9d, eax
0x14004b0f1  mov     [rsp+0D0h+X], ebx
0x14004b0f5  mov     rcx, [rcx+10h]
0x14004b0f9  call    WPP_SF_Dd
0x14004b0fe  xor     eax, eax
0x14004b100  add     rsp, 0B0h
0x14004b107  pop     r14
0x14004b109  pop     rdi
0x14004b10a  pop     rsi
0x14004b10b  pop     rbx
0x14004b10c  pop     rbp
0x14004b10d  retn
```
