# CContextConnection::CreateInstance(IInputProviderContext *,_GUID const &,_GUID const &,ushort)

- ea: `0x180076214`
- end: `0x1800763f9`
- name: `?CreateInstance@CContextConnection@@SAPEAU1@PEAUIInputProviderContext@@AEBU_GUID@@1G@Z`
- size: `485`
- prototype: `struct CContextConnection *__fastcall(struct IInputProviderContext *, const struct _GUID *, const struct _GUID *, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800760a0`

## callees

- `0x180076214`
- `0x180076400`
- `0x1800909cc`
- `0x18009eaea`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076343`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076361`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007637b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076395`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800763af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076343`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076361`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007637b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076395`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800763af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180076239`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180076239`
- `USER32!SetWindowLongPtrW` at `0x18007632e`
- `USER32!SetWindowLongPtrW` at `0x18007632e`
- `USER32!RegisterClassExW` at `0x1800762ae`
- `USER32!RegisterClassExW` at `0x1800762ae`
- `USER32!CreateWindowExW` at `0x18007630e`
- `USER32!CreateWindowExW` at `0x18007630e`

## pseudocode

```c
struct CContextConnection *__fastcall CContextConnection::CreateInstance(
        struct IInputProviderContext *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        __int16 a4)
{
  CContextConnection *v8; // rax
  CContextConnection *v9; // rbx
  HWND Window; // rax
  unsigned int v11; // edx
  HANDLE EventW; // rax
  HANDLE v13; // rax
  HANDLE v14; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  __int128 v17; // xmm1
  WNDCLASSEXW v19; // [rsp+60h] [rbp-88h] BYREF

  v8 = (CContextConnection *)LocalAlloc(0x40u, 0xC0u);
  if ( !v8 )
    return 0;
  v9 = CContextConnection::CContextConnection(v8);
  if ( v9 )
  {
    memset_0(&v19, 0, sizeof(v19));
    v19.hInstance = g_hInst;
    v19.lpfnWndProc = (WNDPROC)CContextConnection::MsgWndProc;
    v19.lpszClassName = L"TsfCtxMsgWnd";
    v19.cbSize = 80;
    v19.hCursor = 0;
    RegisterClassExW(&v19);
    Window = CreateWindowExW(0, v19.lpszClassName, 0, 0x88000000, 0, 0, 0, 0, HWND_MESSAGE, 0, g_hInst, 0);
    *((_QWORD *)v9 + 23) = Window;
    if ( Window )
    {
      SetWindowLongPtrW(Window, -21, (LONG_PTR)v9);
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)v9 + 10) = EventW;
      if ( EventW )
      {
        v13 = CreateEventW(0, 1, 0, 0);
        *((_QWORD *)v9 + 11) = v13;
        if ( v13 )
        {
          v14 = CreateEventW(0, 1, 0, 0);
          *((_QWORD *)v9 + 12) = v14;
          if ( v14 )
          {
            v15 = CreateEventW(0, 1, 1, 0);
            *((_QWORD *)v9 + 13) = v15;
            if ( v15 )
            {
              v16 = CreateEventW(0, 1, 1, 0);
              *((_QWORD *)v9 + 14) = v16;
              if ( v16 )
              {
                *(struct _GUID *)((char *)v9 + 40) = *a2;
                v17 = (__int128)*a3;
                *((_WORD *)v9 + 36) = a4;
                *((_QWORD *)v9 + 22) = a1;
                *(_OWORD *)((char *)v9 + 56) = v17;
                return v9;
              }
            }
          }
        }
      }
    }
    CContextConnection::`scalar deleting destructor'(v9, v11);
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180076214  push    rbx
0x180076216  push    rbp
0x180076217  push    rsi
0x180076218  push    rdi
0x180076219  push    r14
0x18007621b  push    r15
0x18007621d  sub     rsp, 0B8h
0x180076224  mov     rbp, rdx
0x180076227  mov     r14, rcx
0x18007622a  mov     edx, 0C0h; uBytes
0x18007622f  movzx   edi, r9w
0x180076233  mov     rsi, r8
0x180076236  lea     ecx, [rdx-80h]; uFlags
0x180076239  call    cs:__imp_LocalAlloc
0x18007623f  test    rax, rax
0x180076242  jz      loc_1800763E4
0x180076248  mov     rcx, rax; this
0x18007624b  call    ??0CContextConnection@@QEAA@XZ; CContextConnection::CContextConnection(void)
0x180076250  mov     rbx, rax
0x180076253  test    rax, rax
0x180076256  jz      loc_1800763E6
0x18007625c  mov     r15d, 50h ; 'P'
0x180076262  lea     rcx, [rsp+0E8h+var_88]; void *
0x180076267  mov     r8d, r15d; Size
0x18007626a  xor     edx, edx; Val
0x18007626c  call    memset_0
0x180076271  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x180076278  lea     rcx, [rsp+0E8h+var_88]; WNDCLASSEXW *
0x18007627d  mov     [rsp+0E8h+var_88.hInstance], rax
0x180076282  lea     rax, ?MsgWndProc@CContextConnection@@SA_JPEAUHWND__@@I_K_J@Z; CContextConnection::MsgWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180076289  mov     [rsp+0E8h+var_88.lpfnWndProc], rax
0x18007628e  lea     rax, aTsfctxmsgwnd; "TsfCtxMsgWnd"
0x180076295  mov     [rsp+0E8h+var_88.lpszClassName], rax
0x18007629d  mov     [rsp+0E8h+var_88.cbSize], r15d
0x1800762a2  mov     [rsp+0E8h+var_88.hCursor], 0
0x1800762ae  call    cs:__imp_RegisterClassExW
0x1800762b4  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x1800762bb  mov     r9d, 88000000h; dwStyle
0x1800762c1  mov     rdx, [rsp+0E8h+var_88.lpszClassName]; lpClassName
0x1800762c9  xor     r8d, r8d; lpWindowName
0x1800762cc  mov     [rsp+0E8h+lpParam], 0; lpParam
0x1800762d5  xor     ecx, ecx; dwExStyle
0x1800762d7  mov     [rsp+0E8h+hInstance], rax; hInstance
0x1800762dc  mov     [rsp+0E8h+hMenu], 0; hMenu
0x1800762e5  mov     [rsp+0E8h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x1800762ee  mov     [rsp+0E8h+nHeight], 0; nHeight
0x1800762f6  mov     [rsp+0E8h+nWidth], 0; nWidth
0x1800762fe  mov     [rsp+0E8h+Y], 0; Y
0x180076306  mov     [rsp+0E8h+X], 0; X
0x18007630e  call    cs:__imp_CreateWindowExW
0x180076314  mov     [rbx+0B8h], rax
0x18007631b  test    rax, rax
0x18007631e  jz      loc_1800763DC
0x180076324  mov     r8, rbx; dwNewLong
0x180076327  lea     edx, [r15-65h]; nIndex
0x18007632b  mov     rcx, rax; hWnd
0x18007632e  call    cs:__imp_SetWindowLongPtrW
0x180076334  xor     r9d, r9d; lpName
0x180076337  xor     r8d, r8d; bInitialState
0x18007633a  xor     ecx, ecx; lpEventAttributes
0x18007633c  lea     r15d, [r9+1]
0x180076340  mov     edx, r15d; bManualReset
0x180076343  call    cs:__imp_CreateEventW
0x180076349  mov     [rbx+50h], rax
0x18007634d  test    rax, rax
0x180076350  jz      loc_1800763DC
0x180076356  xor     r9d, r9d; lpName
0x180076359  xor     r8d, r8d; bInitialState
0x18007635c  mov     edx, r15d; bManualReset
0x18007635f  xor     ecx, ecx; lpEventAttributes
0x180076361  call    cs:__imp_CreateEventW
0x180076367  mov     [rbx+58h], rax
0x18007636b  test    rax, rax
0x18007636e  jz      short loc_1800763DC
0x180076370  xor     r9d, r9d; lpName
0x180076373  xor     r8d, r8d; bInitialState
0x180076376  mov     edx, r15d; bManualReset
0x180076379  xor     ecx, ecx; lpEventAttributes
0x18007637b  call    cs:__imp_CreateEventW
0x180076381  mov     [rbx+60h], rax
0x180076385  test    rax, rax
0x180076388  jz      short loc_1800763DC
0x18007638a  xor     r9d, r9d; lpName
0x18007638d  mov     r8d, r15d; bInitialState
0x180076390  mov     edx, r15d; bManualReset
0x180076393  xor     ecx, ecx; lpEventAttributes
0x180076395  call    cs:__imp_CreateEventW
0x18007639b  mov     [rbx+68h], rax
0x18007639f  test    rax, rax
0x1800763a2  jz      short loc_1800763DC
0x1800763a4  xor     r9d, r9d; lpName
0x1800763a7  mov     r8d, r15d; bInitialState
0x1800763aa  mov     edx, r15d; bManualReset
0x1800763ad  xor     ecx, ecx; lpEventAttributes
0x1800763af  call    cs:__imp_CreateEventW
0x1800763b5  mov     [rbx+70h], rax
0x1800763b9  test    rax, rax
0x1800763bc  jz      short loc_1800763DC
0x1800763be  movups  xmm0, xmmword ptr [rbp+0]
0x1800763c2  movdqu  xmmword ptr [rbx+28h], xmm0
0x1800763c7  movups  xmm1, xmmword ptr [rsi]
0x1800763ca  mov     [rbx+48h], di
0x1800763ce  mov     [rbx+0B0h], r14
0x1800763d5  movdqu  xmmword ptr [rbx+38h], xmm1
0x1800763da  jmp     short loc_1800763E6
0x1800763dc  mov     rcx, rbx; this
0x1800763df  call    ??_GCContextConnection@@QEAAPEAXI@Z; CContextConnection::`scalar deleting destructor'(uint)
0x1800763e4  xor     ebx, ebx
0x1800763e6  mov     rax, rbx
0x1800763e9  add     rsp, 0B8h
0x1800763f0  pop     r15
0x1800763f2  pop     r14
0x1800763f4  pop     rdi
0x1800763f5  pop     rsi
0x1800763f6  pop     rbp
0x1800763f7  pop     rbx
0x1800763f8  retn
```
