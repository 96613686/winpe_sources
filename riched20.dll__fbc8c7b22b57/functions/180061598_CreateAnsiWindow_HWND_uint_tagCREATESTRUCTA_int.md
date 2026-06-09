# CreateAnsiWindow(HWND__ *,uint,tagCREATESTRUCTA *,int)

- ea: `0x180061598`
- end: `0x1800616e0`
- name: `?CreateAnsiWindow@@YA_JPEAUHWND__@@IPEAUtagCREATESTRUCTA@@H@Z`
- size: `328`
- prototype: `__int64 __fastcall(HWND, unsigned int, struct tagCREATESTRUCTA *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180033350`
- `0x180062f90`

## callees

- `0x1800499c8`
- `0x180061598`
- `0x180062234`
- `0x18008f410`
- `0x180090408`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `USER32!GetWindowLongPtrW` at `0x1800615d1`
- `USER32!GetWindowLongPtrW` at `0x1800615d1`

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
0x180061598  mov     [rsp-8+arg_8], rbx
0x18006159d  push    rbp
0x18006159e  push    rsi
0x18006159f  push    rdi
0x1800615a0  push    r14
0x1800615a2  push    r15
0x1800615a4  lea     rbp, [rsp-7C0h]
0x1800615ac  sub     rsp, 8C0h
0x1800615b3  mov     rax, cs:__security_cookie
0x1800615ba  xor     rax, rsp
0x1800615bd  mov     [rbp+7E0h+var_30], rax
0x1800615c4  mov     esi, edx
0x1800615c6  mov     r15d, r9d
0x1800615c9  xor     edx, edx; nIndex
0x1800615cb  mov     rbx, r8
0x1800615ce  mov     r14, rcx
0x1800615d1  call    cs:__imp_GetWindowLongPtrW
0x1800615d8  nop     dword ptr [rax+rax+00h]
0x1800615dd  movups  xmm0, xmmword ptr [rbx]
0x1800615e0  xor     ecx, ecx; unsigned int
0x1800615e2  mov     rdi, rax
0x1800615e5  movups  xmm1, xmmword ptr [rbx+10h]
0x1800615e9  movaps  xmmword ptr [rsp+8E0h+var_8C0.lpCreateParams], xmm0
0x1800615ee  movups  xmm0, xmmword ptr [rbx+20h]
0x1800615f2  movaps  xmmword ptr [rsp+8E0h+var_8C0.hMenu], xmm1
0x1800615f7  movups  xmm1, xmmword ptr [rbx+30h]
0x1800615fb  movaps  xmmword ptr [rsp+8E0h+var_8C0.cy], xmm0
0x180061600  movups  xmm0, xmmword ptr [rbx+40h]
0x180061604  movaps  xmmword ptr [rsp+8E0h+var_8C0.style], xmm1
0x180061609  movaps  xmmword ptr [rsp+8E0h+var_8C0.lpszClass], xmm0
0x18006160e  call    ?GetKeyboardCodePage@CW32System@@SAIK@Z; CW32System::GetKeyboardCodePage(ulong)
0x180061613  mov     rdx, [rbx+38h]; char *
0x180061617  lea     rcx, [rbp+7E0h+var_450]; this
0x18006161e  mov     r8d, eax; unsigned int
0x180061621  call    ??0CStrInW@@QEAA@PEBDI@Z; CStrInW::CStrInW(char const *,uint)
0x180061626  mov     rdx, [rbx+40h]; char *
0x18006162a  lea     rcx, [rsp+8E0h+var_870]; this
0x18006162f  xor     r8d, r8d; unsigned int
0x180061632  call    ??0CStrInW@@QEAA@PEBDI@Z; CStrInW::CStrInW(char const *,uint)
0x180061637  mov     rax, [rbp+7E0h+var_450]
0x18006163e  mov     [rsp+8E0h+var_8C0.lpszName], rax
0x180061643  mov     rax, [rsp+8E0h+var_870]
0x180061648  mov     [rsp+8E0h+var_8C0.lpszClass], rax
0x18006164d  test    rdi, rdi
0x180061650  jnz     short loc_180061669
0x180061652  mov     r9d, r15d; int
0x180061655  lea     r8d, [rdi+1]; int
0x180061659  lea     rdx, [rsp+8E0h+var_8C0]; struct tagCREATESTRUCTW *
0x18006165e  mov     rcx, r14; HWND
0x180061661  call    ?OnNCCreate@CTxtWinHost@@SAPEAV1@PEAUHWND__@@PEBUtagCREATESTRUCTW@@HH@Z; CTxtWinHost::OnNCCreate(HWND__ *,tagCREATESTRUCTW const *,int,int)
0x180061666  mov     rdi, rax
0x180061669  cmp     esi, 81h
0x18006166f  jnz     short loc_18006167B
0x180061671  xor     ebx, ebx
0x180061673  test    rdi, rdi
0x180061676  setnz   bl
0x180061679  jmp     short loc_1800616A0
0x18006167b  test    rdi, rdi
0x18006167e  jnz     short loc_180061686
0x180061680  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180061684  jmp     short loc_1800616A0
0x180061686  mov     rax, [rdi]
0x180061689  lea     rdx, [rsp+8E0h+var_8C0]
0x18006168e  mov     rcx, rdi
0x180061691  mov     rax, [rax+1D8h]
0x180061698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006169d  mov     rbx, rax
0x1800616a0  lea     rcx, [rsp+8E0h+var_870]; this
0x1800616a5  call    ?Free@CConvertStrW@@IEAAXXZ; CConvertStrW::Free(void)
0x1800616aa  lea     rcx, [rbp+7E0h+var_450]; this
0x1800616b1  call    ?Free@CConvertStrW@@IEAAXXZ; CConvertStrW::Free(void)
0x1800616b6  mov     rax, rbx
0x1800616b9  mov     rcx, [rbp+7E0h+var_30]
0x1800616c0  xor     rcx, rsp; StackCookie
0x1800616c3  call    __security_check_cookie
0x1800616c8  mov     rbx, [rsp+8E0h+arg_8]
0x1800616d0  add     rsp, 8C0h
0x1800616d7  pop     r15
0x1800616d9  pop     r14
0x1800616db  pop     rdi
0x1800616dc  pop     rsi
0x1800616dd  pop     rbp
0x1800616de  retn
```
