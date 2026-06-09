# CreateAnsiWindow(HWND__ *,uint,tagCREATESTRUCTA *,int)

- ea: `0x18005fe18`
- end: `0x18005ff59`
- name: `?CreateAnsiWindow@@YA_JPEAUHWND__@@IPEAUtagCREATESTRUCTA@@H@Z`
- size: `321`
- prototype: `__int64 __fastcall(HWND, unsigned int, struct tagCREATESTRUCTA *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800341c0`
- `0x180061670`

## callees

- `0x180048b64`
- `0x18005fe18`
- `0x1800609e0`
- `0x18008cc78`
- `0x18008dbf0`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `USER32!GetWindowLongPtrW` at `0x18005fe51`
- `USER32!GetWindowLongPtrW` at `0x18005fe51`

## pseudocode

```c
__int64 __fastcall CreateAnsiWindow(HWND a1, int a2, struct tagCREATESTRUCTA *a3, int a4)
{
  LONG_PTR WindowLongPtrW; // rdi
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  unsigned int KeyboardCodePage; // eax
  __int64 v14; // rbx
  tagCREATESTRUCTW v16; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v17[132]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v18[132]; // [rsp+490h] [rbp+390h] BYREF

  WindowLongPtrW = GetWindowLongPtrW(a1, 0);
  v9 = *(_OWORD *)&a3->hMenu;
  *(_OWORD *)&v16.lpCreateParams = *(_OWORD *)&a3->lpCreateParams;
  v10 = *(_OWORD *)&a3->cy;
  *(_OWORD *)&v16.hMenu = v9;
  v11 = *(_OWORD *)&a3->style;
  *(_OWORD *)&v16.cy = v10;
  v12 = *(_OWORD *)&a3->lpszClass;
  *(_OWORD *)&v16.style = v11;
  *(_OWORD *)&v16.lpszClass = v12;
  KeyboardCodePage = CW32System::GetKeyboardCodePage(0);
  CStrInW::CStrInW((CStrInW *)v18, a3->lpszName, KeyboardCodePage);
  CStrInW::CStrInW((CStrInW *)v17, a3->lpszClass, 0);
  v16.lpszName = (LPCWSTR)v18[0];
  v16.lpszClass = (LPCWSTR)v17[0];
  if ( !WindowLongPtrW )
    WindowLongPtrW = (LONG_PTR)CTxtWinHost::OnNCCreate(a1, &v16, 1u, a4);
  if ( a2 == 129 )
  {
    v14 = WindowLongPtrW != 0;
  }
  else if ( WindowLongPtrW )
  {
    v14 = (*(__int64 (__fastcall **)(LONG_PTR, tagCREATESTRUCTW *))(*(_QWORD *)WindowLongPtrW + 472LL))(
            WindowLongPtrW,
            &v16);
  }
  else
  {
    v14 = -1;
  }
  CConvertStrW::Free((CConvertStrW *)v17);
  CConvertStrW::Free((CConvertStrW *)v18);
  return v14;
}

```

## disassembly

```asm
0x18005fe18  mov     [rsp-8+arg_8], rbx
0x18005fe1d  push    rbp
0x18005fe1e  push    rsi
0x18005fe1f  push    rdi
0x18005fe20  push    r14
0x18005fe22  push    r15
0x18005fe24  lea     rbp, [rsp-7C0h]
0x18005fe2c  sub     rsp, 8C0h
0x18005fe33  mov     rax, cs:__security_cookie
0x18005fe3a  xor     rax, rsp
0x18005fe3d  mov     [rbp+7E0h+var_30], rax
0x18005fe44  mov     esi, edx
0x18005fe46  mov     r15d, r9d
0x18005fe49  xor     edx, edx; nIndex
0x18005fe4b  mov     rbx, r8
0x18005fe4e  mov     r14, rcx
0x18005fe51  call    cs:__imp_GetWindowLongPtrW
0x18005fe57  movups  xmm0, xmmword ptr [rbx]
0x18005fe5a  xor     ecx, ecx; unsigned int
0x18005fe5c  mov     rdi, rax
0x18005fe5f  movups  xmm1, xmmword ptr [rbx+10h]
0x18005fe63  movaps  xmmword ptr [rsp+8E0h+var_8C0.lpCreateParams], xmm0
0x18005fe68  movups  xmm0, xmmword ptr [rbx+20h]
0x18005fe6c  movaps  xmmword ptr [rsp+8E0h+var_8C0.hMenu], xmm1
0x18005fe71  movups  xmm1, xmmword ptr [rbx+30h]
0x18005fe75  movaps  xmmword ptr [rsp+8E0h+var_8C0.cy], xmm0
0x18005fe7a  movups  xmm0, xmmword ptr [rbx+40h]
0x18005fe7e  movaps  xmmword ptr [rsp+8E0h+var_8C0.style], xmm1
0x18005fe83  movaps  xmmword ptr [rsp+8E0h+var_8C0.lpszClass], xmm0
0x18005fe88  call    ?GetKeyboardCodePage@CW32System@@SAIK@Z; CW32System::GetKeyboardCodePage(ulong)
0x18005fe8d  mov     rdx, [rbx+38h]; char *
0x18005fe91  lea     rcx, [rbp+7E0h+var_450]; this
0x18005fe98  mov     r8d, eax; unsigned int
0x18005fe9b  call    ??0CStrInW@@QEAA@PEBDI@Z; CStrInW::CStrInW(char const *,uint)
0x18005fea0  mov     rdx, [rbx+40h]; char *
0x18005fea4  lea     rcx, [rsp+8E0h+var_870]; this
0x18005fea9  xor     r8d, r8d; unsigned int
0x18005feac  call    ??0CStrInW@@QEAA@PEBDI@Z; CStrInW::CStrInW(char const *,uint)
0x18005feb1  mov     rax, [rbp+7E0h+var_450]
0x18005feb8  mov     [rsp+8E0h+var_8C0.lpszName], rax
0x18005febd  mov     rax, [rsp+8E0h+var_870]
0x18005fec2  mov     [rsp+8E0h+var_8C0.lpszClass], rax
0x18005fec7  test    rdi, rdi
0x18005feca  jnz     short loc_18005FEE3
0x18005fecc  mov     r9d, r15d; int
0x18005fecf  lea     r8d, [rdi+1]; int
0x18005fed3  lea     rdx, [rsp+8E0h+var_8C0]; struct tagCREATESTRUCTW *
0x18005fed8  mov     rcx, r14; HWND
0x18005fedb  call    ?OnNCCreate@CTxtWinHost@@SAPEAV1@PEAUHWND__@@PEBUtagCREATESTRUCTW@@HH@Z; CTxtWinHost::OnNCCreate(HWND__ *,tagCREATESTRUCTW const *,int,int)
0x18005fee0  mov     rdi, rax
0x18005fee3  cmp     esi, 81h
0x18005fee9  jnz     short loc_18005FEF5
0x18005feeb  xor     ebx, ebx
0x18005feed  test    rdi, rdi
0x18005fef0  setnz   bl
0x18005fef3  jmp     short loc_18005FF1A
0x18005fef5  test    rdi, rdi
0x18005fef8  jnz     short loc_18005FF00
0x18005fefa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005fefe  jmp     short loc_18005FF1A
0x18005ff00  mov     rax, [rdi]
0x18005ff03  lea     rdx, [rsp+8E0h+var_8C0]
0x18005ff08  mov     rcx, rdi
0x18005ff0b  mov     rax, [rax+1D8h]
0x18005ff12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ff17  mov     rbx, rax
0x18005ff1a  lea     rcx, [rsp+8E0h+var_870]; this
0x18005ff1f  call    ?Free@CConvertStrW@@IEAAXXZ; CConvertStrW::Free(void)
0x18005ff24  lea     rcx, [rbp+7E0h+var_450]; this
0x18005ff2b  call    ?Free@CConvertStrW@@IEAAXXZ; CConvertStrW::Free(void)
0x18005ff30  mov     rax, rbx
0x18005ff33  mov     rcx, [rbp+7E0h+var_30]
0x18005ff3a  xor     rcx, rsp; StackCookie
0x18005ff3d  call    __security_check_cookie
0x18005ff42  mov     rbx, [rsp+8E0h+arg_8]
0x18005ff4a  add     rsp, 8C0h
0x18005ff51  pop     r15
0x18005ff53  pop     r14
0x18005ff55  pop     rdi
0x18005ff56  pop     rsi
0x18005ff57  pop     rbp
0x18005ff58  retn
```
