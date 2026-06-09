# CTsWindow::Create(HWND__ *,ushort const *,ulong,ulong,int,int,int,int,HINSTANCE__ *,HMENU__ *,ushort const *,ulong,HICON__ *,HICON__ *,HBRUSH__ *,int)

- ea: `0x140004470`
- end: `0x14000451c`
- name: `?Create@CTsWindow@@QEAAHPEAUHWND__@@PEBGKKHHHHPEAUHINSTANCE__@@PEAUHMENU__@@1KPEAUHICON__@@4PEAUHBRUSH__@@H@Z`
- size: `172`
- prototype: `__int64 __usercall@<rax>(CTsWindow *__hidden this@<rcx>, HWND@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, int, int, int, int, HINSTANCE, HMENU, const unsigned __int16 *, unsigned int, HICON, HICON, HBRUSH, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400048e0`

## callees

- `0x140004470`
- `0x14000481c`

## import_xrefs

- `USER32!CreateWindowExW` at `0x1400044fd`
- `USER32!CreateWindowExW` at `0x1400044fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400044a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400044a5`

## pseudocode

```c
_BOOL8 __fastcall CTsWindow::Create(
        CTsWindow *this,
        HWND a2,
        const unsigned __int16 *a3,
        HICON a4,
        unsigned int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        HINSTANCE hInstance)
{
  HICON X; // [rsp+20h] [rbp-48h]
  HBRUSH Y; // [rsp+28h] [rbp-40h]
  int nWidth; // [rsp+30h] [rbp-38h]

  if ( *((_QWORD *)this + 6)
    || !(unsigned int)CTsWindow::InitWindowClass(
                        L"RdpClipMainWindowClass",
                        hInstance,
                        (unsigned int)a3,
                        a4,
                        X,
                        Y,
                        nWidth) )
  {
    return 0;
  }
  SetLastError(0);
  return CreateWindowExW(0, L"RdpClipMainWindowClass", &WindowName, 0xCB0000u, 0, 0, 256, 100, 0, 0, hInstance, this) != 0;
}

```

## disassembly

```asm
0x140004470  mov     [rsp+arg_0], rbx
0x140004475  push    rdi
0x140004476  sub     rsp, 60h
0x14000447a  cmp     qword ptr [rcx+30h], 0
0x14000447f  mov     rbx, rcx
0x140004482  jnz     loc_14000450F
0x140004488  mov     rdi, [rsp+68h+arg_48]
0x140004490  lea     rcx, ClassName; "RdpClipMainWindowClass"
0x140004497  mov     rdx, rdi; hInstance
0x14000449a  call    ?InitWindowClass@CTsWindow@@KAHPEBGPEAUHINSTANCE__@@KPEAUHICON__@@2PEAUHBRUSH__@@H@Z; CTsWindow::InitWindowClass(ushort const *,HINSTANCE__ *,ulong,HICON__ *,HICON__ *,HBRUSH__ *,int)
0x14000449f  test    eax, eax
0x1400044a1  jz      short loc_14000450F
0x1400044a3  xor     ecx, ecx; dwErrCode
0x1400044a5  call    cs:__imp_SetLastError
0x1400044ab  mov     [rsp+68h+lpParam], rbx; lpParam
0x1400044b0  lea     r8, WindowName; lpWindowName
0x1400044b7  mov     [rsp+68h+hInstance], rdi; hInstance
0x1400044bc  lea     rdx, ClassName; "RdpClipMainWindowClass"
0x1400044c3  mov     [rsp+68h+hMenu], 0; hMenu
0x1400044cc  mov     r9d, 0CB0000h; dwStyle
0x1400044d2  mov     [rsp+68h+hWndParent], 0; hWndParent
0x1400044db  xor     ecx, ecx; dwExStyle
0x1400044dd  mov     [rsp+68h+nHeight], 64h ; 'd'; nHeight
0x1400044e5  mov     [rsp+68h+nWidth], 100h; nWidth
0x1400044ed  mov     dword ptr [rsp+68h+Y], 0; Y
0x1400044f5  mov     dword ptr [rsp+68h+X], 0; X
0x1400044fd  call    cs:__imp_CreateWindowExW
0x140004503  xor     ecx, ecx
0x140004505  test    rax, rax
0x140004508  setnz   cl
0x14000450b  mov     eax, ecx
0x14000450d  jmp     short loc_140004511
0x14000450f  xor     eax, eax
0x140004511  mov     rbx, [rsp+68h+arg_0]
0x140004516  add     rsp, 60h
0x14000451a  pop     rdi
0x14000451b  retn
```
