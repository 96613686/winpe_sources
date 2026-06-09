# CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::InitAsyncEvents(void)

- ea: `0x18006c4c8`
- end: `0x18006c5d5`
- name: `?InitAsyncEvents@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents@@3U_GUID@@B$1?IID_IADORecordsetEventsVt@@3U3@B@@QEAAXXZ`
- size: `269`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180065ba0`
- `0x180065e00`
- `0x180066060`
- `0x1800662c0`

## callees

- `0x18006c4c8`
- `0x1800cdaea`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18006c5b0`
- `KERNEL32!GetCurrentThreadId` at `0x18006c5b0`
- `USER32!RegisterClassExW` at `0x18006c53e`
- `USER32!RegisterClassExW` at `0x18006c53e`
- `USER32!CreateWindowExW` at `0x18006c59b`
- `USER32!CreateWindowExW` at `0x18006c59b`

## pseudocode

```c
void __fastcall CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::InitAsyncEvents(
        __int64 a1)
{
  HWND Window; // rax
  WNDCLASSEXW v3; // [rsp+60h] [rbp-78h] BYREF

  if ( !*(_QWORD *)(a1 + 32) )
  {
    if ( !*(_BYTE *)(a1 + 40) )
    {
      memset_0(&v3, 0, sizeof(v3));
      v3.cbSize = 80;
      v3.lpfnWndProc = (WNDPROC)FireEventOnMainThread;
      v3.hInstance = hInstance;
      v3.lpszMenuName = &WindowName;
      v3.lpszClassName = L"ADODB.AsyncEventMessenger";
      if ( RegisterClassExW(&v3) )
        g_fAsyncEventsWndClass = 1;
      *(_BYTE *)(a1 + 40) = 1;
    }
    Window = CreateWindowExW(0, L"ADODB.AsyncEventMessenger", &WindowName, 0, 0, 0, 1, 1, 0, 0, hInstance, 0);
    *(_QWORD *)(a1 + 32) = Window;
    if ( Window )
    {
      *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
      _InterlockedIncrement((volatile signed __int32 *)&g_cAsyncEventsWnd);
    }
  }
}

```

## disassembly

```asm
0x18006c4c8  push    rbx
0x18006c4ca  push    rsi
0x18006c4cb  push    r14
0x18006c4cd  push    r15
0x18006c4cf  sub     rsp, 0B8h
0x18006c4d6  xor     esi, esi
0x18006c4d8  mov     rbx, rcx
0x18006c4db  cmp     [rcx+20h], rsi
0x18006c4df  jnz     loc_18006C5C6
0x18006c4e5  lea     r14, WindowName
0x18006c4ec  lea     r15, ClassName; "ADODB.AsyncEventMessenger"
0x18006c4f3  cmp     [rcx+28h], sil
0x18006c4f7  jnz     short loc_18006C55D
0x18006c4f9  xor     edx, edx; Val
0x18006c4fb  lea     r8d, [rsi+50h]; Size
0x18006c4ff  lea     rcx, [rsp+0D8h+var_78]; void *
0x18006c504  call    memset_0
0x18006c509  lea     rax, _FireEventOnMainThread
0x18006c510  mov     [rsp+0D8h+var_78.cbSize], 50h ; 'P'
0x18006c518  mov     [rsp+0D8h+var_78.lpfnWndProc], rax
0x18006c51d  lea     rcx, [rsp+0D8h+var_78]; WNDCLASSEXW *
0x18006c522  mov     rax, cs:hInstance
0x18006c529  mov     [rsp+0D8h+var_78.hInstance], rax
0x18006c52e  mov     [rsp+0D8h+var_78.lpszMenuName], r14
0x18006c536  mov     [rsp+0D8h+var_78.lpszClassName], r15
0x18006c53e  call    cs:__imp_RegisterClassExW
0x18006c545  nop     dword ptr [rax+rax+00h]
0x18006c54a  test    ax, ax
0x18006c54d  jz      short loc_18006C559
0x18006c54f  mov     cs:?g_fAsyncEventsWndClass@@3HA, 1; int g_fAsyncEventsWndClass
0x18006c559  mov     byte ptr [rbx+28h], 1
0x18006c55d  mov     rax, cs:hInstance
0x18006c564  xor     r9d, r9d; dwStyle
0x18006c567  mov     [rsp+0D8h+lpParam], rsi; lpParam
0x18006c56c  mov     r8, r14; lpWindowName
0x18006c56f  mov     [rsp+0D8h+hInstance], rax; hInstance
0x18006c574  mov     rdx, r15; lpClassName
0x18006c577  mov     [rsp+0D8h+hMenu], rsi; hMenu
0x18006c57c  xor     ecx, ecx; dwExStyle
0x18006c57e  mov     [rsp+0D8h+hWndParent], rsi; hWndParent
0x18006c583  mov     [rsp+0D8h+nHeight], 1; nHeight
0x18006c58b  mov     [rsp+0D8h+nWidth], 1; nWidth
0x18006c593  mov     [rsp+0D8h+Y], esi; Y
0x18006c597  mov     [rsp+0D8h+X], esi; X
0x18006c59b  call    cs:__imp_CreateWindowExW
0x18006c5a2  nop     dword ptr [rax+rax+00h]
0x18006c5a7  mov     [rbx+20h], rax
0x18006c5ab  test    rax, rax
0x18006c5ae  jz      short loc_18006C5C6
0x18006c5b0  call    cs:__imp_GetCurrentThreadId
0x18006c5b7  nop     dword ptr [rax+rax+00h]
0x18006c5bc  mov     [rbx+18h], eax
0x18006c5bf  lock inc cs:?g_cAsyncEventsWnd@@3KA; ulong g_cAsyncEventsWnd
0x18006c5c6  add     rsp, 0B8h
0x18006c5cd  pop     r15
0x18006c5cf  pop     r14
0x18006c5d1  pop     rsi
0x18006c5d2  pop     rbx
0x18006c5d3  retn
```
