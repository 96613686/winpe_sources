# NDXGI::CResource::CGdiInterop::CreateDeviceBitmap(D3D11_TEXTURE2D_DESC *,uint)

- ea: `0x18007df60`
- end: `0x18007e119`
- name: `?CreateDeviceBitmap@CGdiInterop@CResource@NDXGI@@AEAAJPEAUD3D11_TEXTURE2D_DESC@@I@Z`
- size: `441`
- prototype: `__int64 __fastcall(NDXGI::CResource::CGdiInterop *__hidden this, struct D3D11_TEXTURE2D_DESC *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800093f4`

## callees

- `0x180022400`
- `0x18002d730`
- `0x18007df60`
- `0x1800dd664`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e0bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e0bc`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x18007dfc1`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x18007dfc1`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x18007e041`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x18007e041`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18007e035`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18007e035`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18007dfd6`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18007dfd6`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18007e0de`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18007e0de`
- `ext-ms-win-gdi-render-l1-1-0!CreateBitmapFromDxSurface2` at `0x18007e014`
- `ext-ms-win-gdi-render-l1-1-0!CreateBitmapFromDxSurface2` at `0x18007e014`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x18007dfb5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x18007dfb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NDXGI::CResource::CGdiInterop::CreateDeviceBitmap(
        NDXGI::CResource::CGdiInterop *this,
        struct D3D11_TEXTURE2D_DESC *a2,
        int a3)
{
  void *v6; // rbx
  NDXGI::CResource *v7; // rcx
  void *v8; // rax
  HWND DesktopWindow; // r15
  HDC DC; // r14
  HDC CompatibleDC; // rsi
  void *BitmapFromDxSurface2; // rax
  int v13; // eax
  __int64 result; // rax
  _com_error *v15; // [rsp+40h] [rbp-58h] BYREF
  void **pExceptionObject; // [rsp+48h] [rbp-50h] BYREF
  int v17; // [rsp+50h] [rbp-48h]
  __int128 v18; // [rsp+58h] [rbp-40h]
  void *v19; // [rsp+A0h] [rbp+8h] BYREF
  void *v20; // [rsp+B8h] [rbp+20h]

  try
  {
    v6 = 0;
    v20 = 0;
    v19 = 0;
    v7 = (NDXGI::CResource *)*((_QWORD *)this + 3);
    if ( *((_BYTE *)v7 + 145) )
    {
      v13 = (*(__int64 (__fastcall **)(NDXGI::CResource *, _QWORD, __int64, _QWORD, void **))(*(_QWORD *)v7 + 80LL))(
              v7,
              0,
              0x10000000,
              0,
              &v19);
      if ( v13 < 0 )
        ThrowFailure(v13);
      v8 = v19;
      v6 = v19;
      v20 = v19;
    }
    else
    {
      NDXGI::CResource::GetSharedHandleInternal(v7, &v19);
      v8 = v19;
    }
    if ( !v8 )
      ThrowFailure(-2147467259);
    DesktopWindow = GetDesktopWindow();
    DC = GetDC(DesktopWindow);
    if ( !DC )
      ThrowFailure(-2147024882);
    CompatibleDC = CreateCompatibleDC(DC);
    if ( CompatibleDC )
    {
      BitmapFromDxSurface2 = (void *)CreateBitmapFromDxSurface2(
                                       DC,
                                       a2->Width,
                                       a2->Height,
                                       (unsigned int)a2->Format,
                                       a3,
                                       *(unsigned __int8 *)(*((_QWORD *)this + 3) + 145LL),
                                       v19);
      if ( BitmapFromDxSurface2 )
      {
        *((_QWORD *)this + 4) = BitmapFromDxSurface2;
        *((_QWORD *)this + 5) = CompatibleDC;
        *((_DWORD *)this + 12) = a3;
        SelectObject(CompatibleDC, BitmapFromDxSurface2);
      }
      else
      {
        DeleteObject(CompatibleDC);
      }
    }
    ReleaseDC(DesktopWindow, DC);
    if ( !*((_QWORD *)this + 4) )
    {
      pExceptionObject = &_com_error::`vftable';
      v17 = -2147467259;
      v18 = 0;
      throw (_com_error *)&pExceptionObject;
    }
    if ( v6 )
      CloseHandle(v6);
    result = 0;
  }
  catch ( _com_error *v15 )
  {
    LODWORD(v19) = *((_DWORD *)v15 + 2);
    return (unsigned int)v19;
  }
  return result;
}

```

## disassembly

```asm
0x18007df60  mov     rax, rsp
0x18007df63  mov     [rax+10h], rbx
0x18007df67  mov     [rax+18h], rsi
0x18007df6b  push    rdi
0x18007df6c  push    r12
0x18007df6e  push    r13
0x18007df70  push    r14
0x18007df72  push    r15
0x18007df74  sub     rsp, 70h
0x18007df78  mov     r12d, r8d
0x18007df7b  mov     r13, rdx
0x18007df7e  mov     rdi, rcx
0x18007df81  xor     ebx, ebx
0x18007df83  mov     [rax+20h], rbx
0x18007df87  mov     [rax+8], rbx
0x18007df8b  mov     rcx, [rcx+18h]; this
0x18007df8f  lea     rdx, [rax+8]; void **
0x18007df93  cmp     [rcx+91h], bl
0x18007df99  jnz     loc_18007E07C
0x18007df9f  call    ?GetSharedHandleInternal@CResource@NDXGI@@UEAAJPEAPEAX@Z; NDXGI::CResource::GetSharedHandleInternal(void * *)
0x18007dfa4  mov     rax, [rsp+98h+arg_0]
0x18007dfac  test    rax, rax
0x18007dfaf  jz      loc_18007E0F2
0x18007dfb5  call    cs:__imp_GetDesktopWindow
0x18007dfbb  mov     r15, rax
0x18007dfbe  mov     rcx, rax; hWnd
0x18007dfc1  call    cs:__imp_GetDC
0x18007dfc7  mov     r14, rax
0x18007dfca  test    rax, rax
0x18007dfcd  jz      loc_18007E101
0x18007dfd3  mov     rcx, r14; hdc
0x18007dfd6  call    cs:__imp_CreateCompatibleDC
0x18007dfdc  mov     rsi, rax
0x18007dfdf  test    rax, rax
0x18007dfe2  jz      short loc_18007E03B
0x18007dfe4  mov     rcx, [rdi+18h]
0x18007dfe8  movzx   edx, byte ptr [rcx+91h]
0x18007dfef  mov     rcx, [rsp+98h+arg_0]
0x18007dff7  mov     [rsp+98h+var_68], rcx
0x18007dffc  mov     [rsp+98h+var_70], edx
0x18007e000  mov     dword ptr [rsp+98h+var_78], r12d
0x18007e005  mov     r9d, [r13+10h]
0x18007e009  mov     r8d, [r13+4]
0x18007e00d  mov     edx, [r13+0]
0x18007e011  mov     rcx, r14
0x18007e014  call    cs:__imp_CreateBitmapFromDxSurface2
0x18007e01a  mov     rcx, rsi; ho
0x18007e01d  test    rax, rax
0x18007e020  jz      loc_18007E0DE
0x18007e026  mov     [rdi+20h], rax
0x18007e02a  mov     [rdi+28h], rsi
0x18007e02e  mov     [rdi+30h], r12d
0x18007e032  mov     rdx, rax; h
0x18007e035  call    cs:__imp_SelectObject
0x18007e03b  mov     rdx, r14; hDC
0x18007e03e  mov     rcx, r15; hWnd
0x18007e041  call    cs:__imp_ReleaseDC
0x18007e047  cmp     qword ptr [rdi+20h], 0
0x18007e04c  jnz     short loc_18007E0B4
0x18007e04e  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18007e055  mov     [rsp+98h+pExceptionObject], rax
0x18007e05a  mov     [rsp+98h+var_48], 80004005h
0x18007e062  xorps   xmm0, xmm0
0x18007e065  movdqu  [rsp+98h+var_40], xmm0
0x18007e06b  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18007e072  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18007e077  call    _CxxThrowException_0
0x18007e07c  mov     rax, [rcx]
0x18007e07f  mov     [rsp+98h+var_78], rdx
0x18007e084  xor     r9d, r9d
0x18007e087  xor     edx, edx
0x18007e089  mov     r8d, 10000000h
0x18007e08f  mov     rax, [rax+50h]
0x18007e093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e098  test    eax, eax
0x18007e09a  js      short loc_18007E0E9
0x18007e09c  mov     rax, [rsp+98h+arg_0]
0x18007e0a4  mov     rbx, rax
0x18007e0a7  mov     [rsp+98h+arg_18], rax
0x18007e0af  jmp     loc_18007DFAC
0x18007e0b4  test    rbx, rbx
0x18007e0b7  jz      short loc_18007E0C2
0x18007e0b9  mov     rcx, rbx; hObject
0x18007e0bc  call    cs:__imp_CloseHandle
0x18007e0c2  xor     eax, eax
0x18007e0c4  lea     r11, [rsp+98h+var_28]
0x18007e0c9  mov     rbx, [r11+38h]
0x18007e0cd  mov     rsi, [r11+40h]
0x18007e0d1  mov     rsp, r11
0x18007e0d4  pop     r15
0x18007e0d6  pop     r14
0x18007e0d8  pop     r13
0x18007e0da  pop     r12
0x18007e0dc  pop     rdi
0x18007e0dd  retn
0x18007e0de  call    cs:__imp_DeleteObject
0x18007e0e4  jmp     loc_18007E03B
0x18007e0e9  mov     ecx, eax; int
0x18007e0eb  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18007e0f0  jmp     short loc_18007E09C
0x18007e0f2  mov     ecx, 80004005h; int
0x18007e0f7  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18007e0fc  jmp     loc_18007DFB5
0x18007e101  mov     ecx, 8007000Eh; int
0x18007e106  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18007e10b  jmp     loc_18007DFD3
0x18007e110  mov     eax, dword ptr [rsp+98h+arg_0]
0x18007e117  jmp     short loc_18007E0C4
```
