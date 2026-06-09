# CFileOwnerDialog::InitializeOwnerCombo(COwnerList const &,HWND__ *)

- ea: `0x18001387c`
- end: `0x180013a3f`
- name: `?InitializeOwnerCombo@CFileOwnerDialog@@AEAAXAEBVCOwnerList@@PEAUHWND__@@@Z`
- size: `451`
- prototype: `void(CFileOwnerDialog *__hidden this, const struct COwnerList *, HWND)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180014604`
- `0x180014980`
- `0x180014e68`

## callees

- `0x180001510`
- `0x180011f58`
- `0x18001387c`
- `0x1800155e8`
- `0x180019dd0`
- `0x180019ee0`
- `0x180019f38`
- `0x18001a468`

## import_xrefs

- `USER32!GetClientRect` at `0x1800139d2`
- `USER32!GetClientRect` at `0x1800139d2`
- `USER32!SetWindowPos` at `0x1800139fe`
- `USER32!SetWindowPos` at `0x1800139fe`
- `USER32!SendMessageW` at `0x1800138bb`
- `USER32!SendMessageW` at `0x1800138d2`
- `USER32!SendMessageW` at `0x18001392e`
- `USER32!SendMessageW` at `0x18001399b`
- `USER32!SendMessageW` at `0x1800139bd`
- `USER32!SendMessageW` at `0x1800138bb`
- `USER32!SendMessageW` at `0x1800138d2`
- `USER32!SendMessageW` at `0x18001392e`
- `USER32!SendMessageW` at `0x18001399b`
- `USER32!SendMessageW` at `0x1800139bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CFileOwnerDialog::InitializeOwnerCombo(CFileOwnerDialog *this, const struct COwnerList *a2, HWND a3)
{
  int v6; // esi
  int v7; // r12d
  unsigned int v8; // eax
  int v9; // r14d
  __int64 v10; // rax
  __int64 v11; // [rsp+20h] [rbp-60h]
  _BYTE v12[8]; // [rsp+40h] [rbp-40h] BYREF
  LPARAM *v13; // [rsp+48h] [rbp-38h]
  _BYTE v14[8]; // [rsp+50h] [rbp-30h] BYREF
  _QWORD *v15; // [rsp+58h] [rbp-28h]
  struct tagRECT Rect; // [rsp+60h] [rbp-20h] BYREF

  v6 = SendMessageW(a3, 0x147u, 0, 0);
  SendMessageW(a3, 0x14Bu, 0, 0);
  CString::CString((CString *)v12);
  CString::CString((CString *)v14);
  v7 = *((_DWORD *)a2 + 3);
  if ( v7 <= 1 )
  {
    v9 = 0;
    if ( v7 <= 0 )
      goto LABEL_5;
  }
  else
  {
    v8 = COwnerList::FileCount(a2, -1, 0);
    CString::Format((CString *)v12, *(HINSTANCE *)this, 0x9EADu, v8);
    SendMessageW(a3, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, *v13);
    v9 = 0;
  }
  do
  {
    v10 = CArray<COwnerListEntry *>::operator[](a2, (unsigned int)v9);
    CString::operator=(v14, v10 + 8);
    LODWORD(v11) = COwnerList::FileCount(a2, v9, 0);
    CString::Format((CString *)v12, *(HINSTANCE *)this, 0x9EAEu, *v15, v11);
    SendMessageW(a3, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, *v13);
    ++v9;
  }
  while ( v9 < v7 );
LABEL_5:
  if ( v6 == -1 )
    v6 = 0;
  SendMessageW(a3, 0x14Eu, v6, 0);
  Rect = 0;
  GetClientRect(*((HWND *)this + 4), &Rect);
  SetWindowPos(*((HWND *)this + 4), 0, 0, 0, Rect.right - Rect.left, 200, 0x1Eu);
  CString::~CString((CString *)v14);
  CString::~CString((CString *)v12);
}

```

## disassembly

```asm
0x18001387c  mov     [rsp-38h+arg_18], rbx
0x180013881  push    rbp
0x180013882  push    rsi
0x180013883  push    rdi
0x180013884  push    r12
0x180013886  push    r13
0x180013888  push    r14
0x18001388a  push    r15
0x18001388c  mov     rbp, rsp
0x18001388f  sub     rsp, 80h
0x180013896  mov     rax, cs:__security_cookie
0x18001389d  xor     rax, rsp
0x1800138a0  mov     [rbp+var_10], rax
0x1800138a4  mov     rdi, r8
0x1800138a7  mov     r13, rdx
0x1800138aa  mov     r15, rcx
0x1800138ad  xor     r9d, r9d; lParam
0x1800138b0  xor     r8d, r8d; wParam
0x1800138b3  mov     edx, 147h; Msg
0x1800138b8  mov     rcx, rdi; hWnd
0x1800138bb  call    cs:__imp_SendMessageW
0x1800138c1  mov     rsi, rax
0x1800138c4  xor     r9d, r9d; lParam
0x1800138c7  xor     r8d, r8d; wParam
0x1800138ca  mov     edx, 14Bh; Msg
0x1800138cf  mov     rcx, rdi; hWnd
0x1800138d2  call    cs:__imp_SendMessageW
0x1800138d8  lea     rcx, [rbp+var_40]; this
0x1800138dc  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x1800138e1  nop
0x1800138e2  lea     rcx, [rbp+var_30]; this
0x1800138e6  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x1800138eb  nop
0x1800138ec  mov     r12d, [r13+0Ch]
0x1800138f0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800138f4  cmp     r12d, 1
0x1800138f8  jle     short loc_18001393B
0x1800138fa  xor     r8d, r8d; bool
0x1800138fd  mov     edx, ebx; int
0x1800138ff  mov     rcx, r13; this
0x180013902  call    ?FileCount@COwnerList@@QEBAHH_N@Z; COwnerList::FileCount(int,bool)
0x180013907  mov     r9d, eax
0x18001390a  mov     r8d, 9EADh; unsigned int
0x180013910  mov     rdx, [r15]; HINSTANCE
0x180013913  lea     rcx, [rbp+var_40]; this
0x180013917  call    ?Format@CString@@QEAAHPEAUHINSTANCE__@@IZZ; CString::Format(HINSTANCE__ *,uint,...)
0x18001391c  mov     r9, [rbp+var_38]
0x180013920  mov     r9, [r9]; lParam
0x180013923  mov     r8, rbx; wParam
0x180013926  mov     edx, 14Ah; Msg
0x18001392b  mov     rcx, rdi; hWnd
0x18001392e  call    cs:__imp_SendMessageW
0x180013934  xor     ebx, ebx
0x180013936  mov     r14d, ebx
0x180013939  jmp     short loc_180013945
0x18001393b  xor     ebx, ebx
0x18001393d  mov     r14d, ebx
0x180013940  test    r12d, r12d
0x180013943  jle     short loc_1800139A9
0x180013945  mov     edx, r14d
0x180013948  mov     rcx, r13
0x18001394b  call    ??A?$CArray@PEAVCOwnerListEntry@@@@QEBAPEAVCOwnerListEntry@@H@Z; CArray<COwnerListEntry *>::operator[](int)
0x180013950  lea     rdx, [rax+8]
0x180013954  lea     rcx, [rbp+var_30]
0x180013958  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x18001395d  xor     r8d, r8d; bool
0x180013960  mov     edx, r14d; int
0x180013963  mov     rcx, r13; this
0x180013966  call    ?FileCount@COwnerList@@QEBAHH_N@Z; COwnerList::FileCount(int,bool)
0x18001396b  mov     dword ptr [rsp+80h+var_60], eax
0x18001396f  mov     r9, [rbp+var_28]
0x180013973  mov     r9, [r9]
0x180013976  mov     r8d, 9EAEh; unsigned int
0x18001397c  mov     rdx, [r15]; HINSTANCE
0x18001397f  lea     rcx, [rbp+var_40]; this
0x180013983  call    ?Format@CString@@QEAAHPEAUHINSTANCE__@@IZZ; CString::Format(HINSTANCE__ *,uint,...)
0x180013988  mov     r9, [rbp+var_38]
0x18001398c  mov     r9, [r9]; lParam
0x18001398f  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x180013993  mov     edx, 14Ah; Msg
0x180013998  mov     rcx, rdi; hWnd
0x18001399b  call    cs:__imp_SendMessageW
0x1800139a1  inc     r14d
0x1800139a4  cmp     r14d, r12d
0x1800139a7  jl      short loc_180013945
0x1800139a9  cmp     esi, 0FFFFFFFFh
0x1800139ac  cmovz   esi, ebx
0x1800139af  movsxd  r8, esi; wParam
0x1800139b2  xor     r9d, r9d; lParam
0x1800139b5  mov     edx, 14Eh; Msg
0x1800139ba  mov     rcx, rdi; hWnd
0x1800139bd  call    cs:__imp_SendMessageW
0x1800139c3  xorps   xmm0, xmm0
0x1800139c6  movups  xmmword ptr [rbp+Rect.left], xmm0
0x1800139ca  lea     rdx, [rbp+Rect]; lpRect
0x1800139ce  mov     rcx, [r15+20h]; hWnd
0x1800139d2  call    cs:__imp_GetClientRect
0x1800139d8  mov     eax, [rbp+Rect.right]
0x1800139db  sub     eax, [rbp+Rect.left]
0x1800139de  mov     [rsp+80h+uFlags], 1Eh; uFlags
0x1800139e6  mov     [rsp+80h+cy], 0C8h; cy
0x1800139ee  mov     dword ptr [rsp+80h+var_60], eax; cx
0x1800139f2  xor     r9d, r9d; Y
0x1800139f5  xor     r8d, r8d; X
0x1800139f8  xor     edx, edx; hWndInsertAfter
0x1800139fa  mov     rcx, [r15+20h]; hWnd
0x1800139fe  call    cs:__imp_SetWindowPos
0x180013a04  nop
0x180013a05  lea     rcx, [rbp+var_30]; this
0x180013a09  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180013a0e  nop
0x180013a0f  lea     rcx, [rbp+var_40]; this
0x180013a13  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180013a18  mov     rcx, [rbp+var_10]
0x180013a1c  xor     rcx, rsp; StackCookie
0x180013a1f  call    __security_check_cookie
0x180013a24  mov     rbx, [rsp+80h+arg_18]
0x180013a2c  add     rsp, 80h
0x180013a33  pop     r15
0x180013a35  pop     r14
0x180013a37  pop     r13
0x180013a39  pop     r12
0x180013a3b  pop     rdi
0x180013a3c  pop     rsi
0x180013a3d  pop     rbp
0x180013a3e  retn
```
