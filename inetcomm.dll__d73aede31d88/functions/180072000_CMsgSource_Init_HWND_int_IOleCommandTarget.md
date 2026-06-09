# CMsgSource::Init(HWND__ *,int,IOleCommandTarget *)

- ea: `0x180072000`
- end: `0x1800721e3`
- name: `?Init@CMsgSource@@QEAAJPEAUHWND__@@HPEAUIOleCommandTarget@@@Z`
- size: `483`
- prototype: `int(CMsgSource *__hidden this, HWND, int, struct IOleCommandTarget *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180080be8`

## callees

- `0x1800055bc`
- `0x1800247c8`
- `0x180071ba0`
- `0x180072000`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!FInitializeRichEdit` at `0x180072034`
- `MSOERT2!FInitializeRichEdit` at `0x180072034`
- `MSOERT2!GetRichEdClassStringW` at `0x18007206c`
- `MSOERT2!GetRichEdClassStringW` at `0x18007206c`
- `USER32!SendMessageW` at `0x18007212f`
- `USER32!SendMessageW` at `0x180072147`
- `USER32!SendMessageW` at `0x180072162`
- `USER32!SendMessageW` at `0x180072195`
- `USER32!SendMessageW` at `0x18007212f`
- `USER32!SendMessageW` at `0x180072147`
- `USER32!SendMessageW` at `0x180072162`
- `USER32!SendMessageW` at `0x180072195`
- `USER32!GetWindowLongA` at `0x180072050`
- `USER32!GetWindowLongA` at `0x180072050`
- `USER32!CreateWindowExW` at `0x1800720c0`
- `USER32!CreateWindowExW` at `0x1800720c0`

## string_xrefs

- `0x1800720e2`: `Courier New`

## pseudocode

```c
__int64 __fastcall CMsgSource::Init(CMsgSource *this, HWND a2, __int64 a3, struct IOleCommandTarget *a4)
{
  unsigned int v7; // ebx
  LONG WindowLongA; // eax
  HINSTANCE hInstance; // rbx
  int v10; // edi
  const WCHAR *RichEdClassStringW; // rax
  HWND Window; // rax
  HWND v13; // rcx
  struct CREMenu *v14; // rax
  struct CREMenu *v15; // rdi
  LPARAM lParam; // [rsp+60h] [rbp-39h] BYREF
  int v18; // [rsp+68h] [rbp-31h] BYREF
  __int64 v19; // [rsp+6Ch] [rbp-2Dh]
  int v20; // [rsp+74h] [rbp-25h]
  __int16 v21; // [rsp+78h] [rbp-21h]
  unsigned __int16 v22[35]; // [rsp+7Ah] [rbp-1Fh] BYREF

  if ( FInitializeRichEdit(1) )
  {
    WindowLongA = GetWindowLongA(a2, -20);
    hInstance = g_hLocRes;
    v10 = (WindowLongA & 0x400000) != 0 ? 0x5000 : 0;
    RichEdClassStringW = GetRichEdClassStringW();
    Window = CreateWindowExW(v10 + 512, RichEdClassStringW, 0, 0x40219044u, 0, 0, 0, 0, a2, (HMENU)0x3E6, hInstance, 0);
    *((_QWORD *)this + 2) = Window;
    if ( Window )
    {
      memset_0(&v18, 0, 0x54u);
      lParam = 0xE000000F0000005CuLL;
      StringCchCopyW(v22, 0x20u, aCourierNew);
      v13 = (HWND)*((_QWORD *)this + 2);
      v18 |= 0x40000000u;
      v19 = 200;
      v20 = 0;
      v21 = 257;
      SendMessageW(v13, 0x444u, 0, (LPARAM)&lParam);
      SendMessageW(*((HWND *)this + 2), 0x445u, 0, 589827);
      SendMessageW(*((HWND *)this + 2), 0x44Du, 2u, 0x1000000);
      v14 = CREMenu::Create();
      v15 = v14;
      if ( v14 )
      {
        *((_QWORD *)v14 + 1) = *((_QWORD *)this + 2);
        *((_DWORD *)v14 + 5) = 4;
        v7 = 0;
        SendMessageW(*((HWND *)this + 2), 0x446u, 0, (LPARAM)v14);
        (*(void (__fastcall **)(struct CREMenu *))(*(_QWORD *)v15 + 16LL))(v15);
        *((_QWORD *)this + 6) = a4;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)HrGetLastError();
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v7;
}

```

## disassembly

```asm
0x180072000  mov     [rsp-8+arg_10], rbx
0x180072005  push    rbp
0x180072006  push    rsi
0x180072007  push    rdi
0x180072008  push    r14
0x18007200a  push    r15
0x18007200c  lea     rbp, [rsp-37h]
0x180072011  sub     rsp, 0D0h
0x180072018  mov     rax, cs:__security_cookie
0x18007201f  xor     rax, rsp
0x180072022  mov     [rbp+57h+var_30], rax
0x180072026  mov     rsi, rcx
0x180072029  mov     r15, r9
0x18007202c  mov     ecx, 1
0x180072031  mov     r14, rdx
0x180072034  call    cs:__imp_?FInitializeRichEdit@@YAHH@Z; FInitializeRichEdit(int)
0x18007203a  test    eax, eax
0x18007203c  jnz     short loc_180072048
0x18007203e  mov     ebx, 80004005h
0x180072043  jmp     loc_1800721BE
0x180072048  mov     edx, 0FFFFFFECh; nIndex
0x18007204d  mov     rcx, r14; hWnd
0x180072050  call    cs:__imp_GetWindowLongA
0x180072056  mov     rbx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hLocRes
0x18007205d  and     eax, 400000h
0x180072062  neg     eax
0x180072064  sbb     edi, edi
0x180072066  and     edi, 5000h
0x18007206c  call    cs:__imp_?GetRichEdClassStringW@@YAPEBGXZ; GetRichEdClassStringW(void)
0x180072072  mov     [rsp+0F0h+lpParam], 0; lpParam
0x18007207b  lea     ecx, [rdi+200h]; dwExStyle
0x180072081  mov     [rsp+0F0h+hInstance], rbx; hInstance
0x180072086  mov     r9d, 40219044h; dwStyle
0x18007208c  mov     [rsp+0F0h+hMenu], 3E6h; hMenu
0x180072095  xor     r8d, r8d; lpWindowName
0x180072098  mov     [rsp+0F0h+hWndParent], r14; hWndParent
0x18007209d  mov     rdx, rax; lpClassName
0x1800720a0  mov     [rsp+0F0h+nHeight], 0; nHeight
0x1800720a8  mov     [rsp+0F0h+nWidth], 0; nWidth
0x1800720b0  mov     [rsp+0F0h+Y], 0; Y
0x1800720b8  mov     [rsp+0F0h+X], 0; X
0x1800720c0  call    cs:__imp_CreateWindowExW
0x1800720c6  mov     [rsi+10h], rax
0x1800720ca  test    rax, rax
0x1800720cd  jz      loc_1800721B7
0x1800720d3  xor     edx, edx; Val
0x1800720d5  lea     rcx, [rbp+57h+var_88]; void *
0x1800720d9  lea     r8d, [rdx+54h]; Size
0x1800720dd  call    memset_0
0x1800720e2  lea     r8, aCourierNew; "Courier New"
0x1800720e9  mov     dword ptr [rbp+57h+lParam], 5Ch ; '\'
0x1800720f0  mov     edx, 20h ; ' '; unsigned __int64
0x1800720f5  mov     dword ptr [rbp+57h+lParam+4], 0E000000Fh
0x1800720fc  lea     rcx, [rbp+57h+var_76]; unsigned __int16 *
0x180072100  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180072105  mov     rcx, [rsi+10h]; hWnd
0x180072109  lea     r9, [rbp+57h+lParam]; lParam
0x18007210d  bts     [rbp+57h+var_88], 1Eh
0x180072112  xor     r8d, r8d; wParam
0x180072115  mov     edx, 444h; Msg
0x18007211a  mov     [rbp+57h+var_84], 0C8h
0x180072122  mov     [rbp+57h+var_7C], 0
0x180072129  mov     [rbp+57h+var_78], 101h
0x18007212f  call    cs:__imp_SendMessageW
0x180072135  mov     rcx, [rsi+10h]; hWnd
0x180072139  mov     r9d, 90003h; lParam
0x18007213f  xor     r8d, r8d; wParam
0x180072142  mov     edx, 445h; Msg
0x180072147  call    cs:__imp_SendMessageW
0x18007214d  mov     rcx, [rsi+10h]; hWnd
0x180072151  mov     edx, 44Dh; Msg
0x180072156  mov     r9d, 1000000h; lParam
0x18007215c  mov     r8d, 2; wParam
0x180072162  call    cs:__imp_SendMessageW
0x180072168  call    ?Create@CREMenu@@SAPEAV1@XZ; CREMenu::Create(void)
0x18007216d  mov     rdi, rax
0x180072170  test    rax, rax
0x180072173  jz      short loc_1800721B0
0x180072175  mov     rcx, [rsi+10h]
0x180072179  mov     r9, rax; lParam
0x18007217c  mov     [rax+8], rcx
0x180072180  xor     r8d, r8d; wParam
0x180072183  mov     dword ptr [rax+14h], 4
0x18007218a  mov     edx, 446h; Msg
0x18007218f  mov     rcx, [rsi+10h]; hWnd
0x180072193  xor     ebx, ebx
0x180072195  call    cs:__imp_SendMessageW
0x18007219b  mov     rcx, [rdi]
0x18007219e  mov     rax, [rcx+10h]
0x1800721a2  mov     rcx, rdi
0x1800721a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800721aa  mov     [rsi+30h], r15
0x1800721ae  jmp     short loc_1800721BE
0x1800721b0  mov     ebx, 8007000Eh
0x1800721b5  jmp     short loc_1800721BE
0x1800721b7  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x1800721bc  mov     ebx, eax
0x1800721be  mov     eax, ebx
0x1800721c0  mov     rcx, [rbp+57h+var_30]
0x1800721c4  xor     rcx, rsp; StackCookie
0x1800721c7  call    __security_check_cookie
0x1800721cc  mov     rbx, [rsp+0F0h+arg_10]
0x1800721d4  add     rsp, 0D0h
0x1800721db  pop     r15
0x1800721dd  pop     r14
0x1800721df  pop     rdi
0x1800721e0  pop     rsi
0x1800721e1  pop     rbp
0x1800721e2  retn
```
