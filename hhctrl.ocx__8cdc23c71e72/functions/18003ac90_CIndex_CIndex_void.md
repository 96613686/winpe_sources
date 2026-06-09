# CIndex::~CIndex(void)

- ea: `0x18003ac90`
- end: `0x18003ada5`
- name: `??1CIndex@@UEAA@XZ`
- size: `277`
- prototype: `void __fastcall(CIndex *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18003adc0`

## callees

- `0x18000171c`
- `0x180006708`
- `0x18003ac90`
- `0x180053e40`
- `0x18006c48c`

## import_xrefs

- `msvcrt!free` at `0x18003ad60`
- `msvcrt!free` at `0x18003ad60`
- `USER32!DestroyWindow` at `0x18003acce`
- `USER32!DestroyWindow` at `0x18003aceb`
- `USER32!DestroyWindow` at `0x18003ad08`
- `USER32!DestroyWindow` at `0x18003ad25`
- `USER32!DestroyWindow` at `0x18003acce`
- `USER32!DestroyWindow` at `0x18003aceb`
- `USER32!DestroyWindow` at `0x18003ad08`
- `USER32!DestroyWindow` at `0x18003ad25`
- `GDI32!DeleteObject` at `0x18003ad49`
- `GDI32!DeleteObject` at `0x18003ad49`

## pseudocode

```c
void __fastcall CIndex::~CIndex(CIndex *this)
{
  int v2; // eax
  int v3; // edi
  void *v4; // rdi

  *(_QWORD *)this = &CIndex::`vftable'{for `INavUI'};
  *((_QWORD *)this + 1) = &CIndex::`vftable'{for `CSiteMap'};
  if ( (unsigned int)IsValidWindow(*((HWND *)this + 55)) )
    DestroyWindow(*((HWND *)this + 55));
  if ( (unsigned int)IsValidWindow(*((HWND *)this + 56)) )
    DestroyWindow(*((HWND *)this + 56));
  if ( (unsigned int)IsValidWindow(*((HWND *)this + 54)) )
    DestroyWindow(*((HWND *)this + 54));
  if ( (unsigned int)IsValidWindow(*((HWND *)this + 57)) )
    DestroyWindow(*((HWND *)this + 57));
  v2 = *((_DWORD *)this + 88);
  if ( v2 )
  {
    v3 = 0;
    if ( v2 > 0 )
    {
      do
        DeleteObject(*(HGDIOBJ *)(*((_QWORD *)this + 45) + 8LL * v3++));
      while ( v3 < *((_DWORD *)this + 88) );
    }
    free(*((void **)this + 45));
  }
  v4 = (void *)*((_QWORD *)this + 64);
  if ( v4 )
  {
    CVirtualListCtrl::~CVirtualListCtrl(*((CVirtualListCtrl **)this + 64));
    operator delete(v4);
  }
  CSiteMap::~CSiteMap((CIndex *)((char *)this + 8));
  *(_QWORD *)this = &INavUI::`vftable';
}

```

## disassembly

```asm
0x18003ac90  mov     [rsp+arg_0], rbx
0x18003ac95  mov     [rsp+arg_8], rsi
0x18003ac9a  push    rdi
0x18003ac9b  sub     rsp, 20h
0x18003ac9f  lea     rax, ??_7CIndex@@6BINavUI@@@; const CIndex::`vftable'{for `INavUI'}
0x18003aca6  mov     rbx, rcx
0x18003aca9  mov     [rcx], rax
0x18003acac  lea     rax, ??_7CIndex@@6BCSiteMap@@@; const CIndex::`vftable'{for `CSiteMap'}
0x18003acb3  mov     [rcx+8], rax
0x18003acb7  mov     rcx, [rcx+1B8h]; HWND
0x18003acbe  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x18003acc3  test    eax, eax
0x18003acc5  jz      short loc_18003ACD4
0x18003acc7  mov     rcx, [rbx+1B8h]; hWnd
0x18003acce  call    cs:__imp_DestroyWindow
0x18003acd4  mov     rcx, [rbx+1C0h]; HWND
0x18003acdb  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x18003ace0  test    eax, eax
0x18003ace2  jz      short loc_18003ACF1
0x18003ace4  mov     rcx, [rbx+1C0h]; hWnd
0x18003aceb  call    cs:__imp_DestroyWindow
0x18003acf1  mov     rcx, [rbx+1B0h]; HWND
0x18003acf8  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x18003acfd  test    eax, eax
0x18003acff  jz      short loc_18003AD0E
0x18003ad01  mov     rcx, [rbx+1B0h]; hWnd
0x18003ad08  call    cs:__imp_DestroyWindow
0x18003ad0e  mov     rcx, [rbx+1C8h]; HWND
0x18003ad15  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x18003ad1a  test    eax, eax
0x18003ad1c  jz      short loc_18003AD2B
0x18003ad1e  mov     rcx, [rbx+1C8h]; hWnd
0x18003ad25  call    cs:__imp_DestroyWindow
0x18003ad2b  mov     eax, [rbx+160h]
0x18003ad31  test    eax, eax
0x18003ad33  jz      short loc_18003AD66
0x18003ad35  xor     edi, edi
0x18003ad37  test    eax, eax
0x18003ad39  jle     short loc_18003AD59
0x18003ad3b  mov     rcx, [rbx+168h]
0x18003ad42  movsxd  rax, edi
0x18003ad45  mov     rcx, [rcx+rax*8]; ho
0x18003ad49  call    cs:__imp_DeleteObject
0x18003ad4f  inc     edi
0x18003ad51  cmp     edi, [rbx+160h]
0x18003ad57  jl      short loc_18003AD3B
0x18003ad59  mov     rcx, [rbx+168h]; Block
0x18003ad60  call    cs:__imp_free
0x18003ad66  mov     rdi, [rbx+200h]
0x18003ad6d  test    rdi, rdi
0x18003ad70  jz      short loc_18003AD82
0x18003ad72  mov     rcx, rdi; this
0x18003ad75  call    ??1CVirtualListCtrl@@QEAA@XZ; CVirtualListCtrl::~CVirtualListCtrl(void)
0x18003ad7a  mov     rcx, rdi; Block
0x18003ad7d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003ad82  lea     rcx, [rbx+8]; this
0x18003ad86  call    ??1CSiteMap@@UEAA@XZ; CSiteMap::~CSiteMap(void)
0x18003ad8b  mov     rsi, [rsp+28h+arg_8]
0x18003ad90  lea     rax, ??_7INavUI@@6B@; const INavUI::`vftable'
0x18003ad97  mov     [rbx], rax
0x18003ad9a  mov     rbx, [rsp+28h+arg_0]
0x18003ad9f  add     rsp, 20h
0x18003ada3  pop     rdi
0x18003ada4  retn
```
