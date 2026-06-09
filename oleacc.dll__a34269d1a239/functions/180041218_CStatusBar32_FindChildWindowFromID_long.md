# CStatusBar32::FindChildWindowFromID(long)

- ea: `0x180041218`
- end: `0x180041385`
- name: `?FindChildWindowFromID@CStatusBar32@@QEAAJJ@Z`
- size: `365`
- prototype: `__int64 __fastcall(CStatusBar32 *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180041900`

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x180015b10`
- `0x18001e4c0`
- `0x180041218`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800412d1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800412d1`
- `USER32!MapWindowPoints` at `0x1800412e7`
- `USER32!MapWindowPoints` at `0x1800412e7`
- `USER32!GetWindowRect` at `0x18004130b`
- `USER32!GetWindowRect` at `0x18004130b`
- `USER32!GetWindow` at `0x1800412f6`
- `USER32!GetWindow` at `0x1800412f6`

## pseudocode

```c
unsigned int __fastcall CStatusBar32::FindChildWindowFromID(CStatusBar32 *this, int a2)
{
  HWND v3; // rdx
  void *v5; // rbx
  HWND v7; // rcx
  UINT i; // edx
  HWND Window; // rax
  HWND v10; // rdi
  HANDLE hProcess; // [rsp+40h] [rbp-30h] BYREF
  __int128 Buffer; // [rsp+48h] [rbp-28h] BYREF
  struct tagRECT Rect; // [rsp+58h] [rbp-18h] BYREF

  hProcess = 0;
  v3 = (HWND)*((_QWORD *)this + 10);
  Rect = 0;
  Buffer = 0;
  v5 = SharedAlloc(0x10u, v3, &hProcess);
  if ( !v5 )
    return 0;
  if ( CAccessible::AccSendMessageTimeout(this, 0, *((HWND *)this + 10), 0x40Au, a2 - 1, (__int64)v5, 0) < 0 )
  {
    SharedFree(v5, hProcess);
    return 0;
  }
  ReadProcessMemory(hProcess, v5, &Buffer, 0x10u, 0);
  MapWindowPoints(*((HWND *)this + 10), 0, (LPPOINT)&Buffer, 2u);
  v7 = (HWND)*((_QWORD *)this + 10);
  for ( i = 5; ; i = 2 )
  {
    Window = GetWindow(v7, i);
    v10 = Window;
    if ( !Window )
      break;
    GetWindowRect(Window, &Rect);
    if ( Rect.left >= (int)Buffer
      && Rect.right <= SDWORD2(Buffer)
      && Rect.top >= SDWORD1(Buffer)
      && Rect.bottom <= SHIDWORD(Buffer) )
    {
      SharedFree(v5, hProcess);
      return HWNDIDFromHwnd(*((HWND *)this + 10), v10);
    }
    v7 = v10;
  }
  SharedFree(v5, hProcess);
  return a2;
}

```

## disassembly

```asm
0x180041218  mov     [rsp-18h+arg_8], rbx
0x18004121d  mov     [rsp-18h+arg_10], rsi
0x180041222  push    rbp
0x180041223  push    rdi
0x180041224  push    r15
0x180041226  mov     rbp, rsp
0x180041229  sub     rsp, 70h
0x18004122d  mov     rax, cs:__security_cookie
0x180041234  xor     rax, rsp
0x180041237  mov     [rbp+var_8], rax
0x18004123b  mov     r15d, edx
0x18004123e  mov     [rbp+hProcess], 0
0x180041246  mov     rdx, [rcx+50h]; HWND
0x18004124a  lea     r8, [rbp+hProcess]; void **
0x18004124e  mov     rsi, rcx
0x180041251  xorps   xmm0, xmm0
0x180041254  xorps   xmm1, xmm1
0x180041257  mov     edi, 10h
0x18004125c  mov     ecx, edi; dwSize
0x18004125e  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180041262  movups  [rbp+Buffer], xmm1
0x180041266  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18004126b  mov     rbx, rax
0x18004126e  test    rax, rax
0x180041271  jnz     short loc_18004127A
0x180041273  xor     eax, eax
0x180041275  jmp     loc_180041364
0x18004127a  mov     r8, [rsi+50h]; HWND
0x18004127e  lea     eax, [r15-1]
0x180041282  movsxd  rcx, eax
0x180041285  mov     r9d, 40Ah; unsigned int
0x18004128b  mov     [rsp+70h+var_40], 0; __int64 *
0x180041294  xor     edx, edx; bool
0x180041296  mov     [rsp+70h+var_48], rbx; __int64
0x18004129b  mov     [rsp+70h+lpNumberOfBytesRead], rcx; unsigned __int64
0x1800412a0  mov     rcx, rsi; this
0x1800412a3  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x1800412a8  test    eax, eax
0x1800412aa  jns     short loc_1800412BA
0x1800412ac  mov     rdx, [rbp+hProcess]; hProcess
0x1800412b0  mov     rcx, rbx; lpAddress
0x1800412b3  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x1800412b8  jmp     short loc_180041273
0x1800412ba  mov     rcx, [rbp+hProcess]; hProcess
0x1800412be  lea     r8, [rbp+Buffer]; lpBuffer
0x1800412c2  mov     r9, rdi; nSize
0x1800412c5  mov     [rsp+70h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x1800412ce  mov     rdx, rbx; lpBaseAddress
0x1800412d1  call    cs:__imp_ReadProcessMemory
0x1800412d7  mov     rcx, [rsi+50h]; hWndFrom
0x1800412db  lea     r8, [rbp+Buffer]; lpPoints
0x1800412df  mov     r9d, 2; cPoints
0x1800412e5  xor     edx, edx; hWndTo
0x1800412e7  call    cs:__imp_MapWindowPoints
0x1800412ed  mov     rcx, [rsi+50h]; hWnd
0x1800412f1  mov     edx, 5; uCmd
0x1800412f6  call    cs:__imp_GetWindow
0x1800412fc  mov     rdi, rax
0x1800412ff  test    rax, rax
0x180041302  jz      short loc_180041355
0x180041304  lea     rdx, [rbp+Rect]; lpRect
0x180041308  mov     rcx, rax; hWnd
0x18004130b  call    cs:__imp_GetWindowRect
0x180041311  mov     ecx, dword ptr [rbp+Buffer]
0x180041314  cmp     [rbp+Rect.left], ecx
0x180041317  jl      short loc_180041331
0x180041319  mov     ecx, dword ptr [rbp+Buffer+8]
0x18004131c  cmp     [rbp+Rect.right], ecx
0x18004131f  jg      short loc_180041331
0x180041321  mov     eax, dword ptr [rbp+Buffer+4]
0x180041324  cmp     [rbp+Rect.top], eax
0x180041327  jl      short loc_180041331
0x180041329  mov     eax, dword ptr [rbp+Buffer+0Ch]
0x18004132c  cmp     [rbp+Rect.bottom], eax
0x18004132f  jle     short loc_18004133B
0x180041331  mov     edx, 2
0x180041336  mov     rcx, rdi
0x180041339  jmp     short loc_1800412F6
0x18004133b  mov     rdx, [rbp+hProcess]; hProcess
0x18004133f  mov     rcx, rbx; lpAddress
0x180041342  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180041347  mov     rcx, [rsi+50h]; HWND
0x18004134b  mov     rdx, rdi; HWND
0x18004134e  call    ?HWNDIDFromHwnd@@YAKPEAUHWND__@@0@Z; HWNDIDFromHwnd(HWND__ *,HWND__ *)
0x180041353  jmp     short loc_180041364
0x180041355  mov     rdx, [rbp+hProcess]; hProcess
0x180041359  mov     rcx, rbx; lpAddress
0x18004135c  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180041361  mov     eax, r15d
0x180041364  mov     rcx, [rbp+var_8]
0x180041368  xor     rcx, rsp; StackCookie
0x18004136b  call    __security_check_cookie
0x180041370  lea     r11, [rsp+70h+var_s0]
0x180041375  mov     rbx, [r11+28h]
0x180041379  mov     rsi, [r11+30h]
0x18004137d  mov     rsp, r11
0x180041380  pop     r15
0x180041382  pop     rdi
0x180041383  pop     rbp
0x180041384  retn
```
