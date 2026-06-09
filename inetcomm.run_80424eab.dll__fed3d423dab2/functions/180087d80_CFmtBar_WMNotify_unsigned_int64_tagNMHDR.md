# CFmtBar::WMNotify(unsigned __int64,tagNMHDR *)

- ea: `0x180087d80`
- end: `0x180087f99`
- name: `?WMNotify@CFmtBar@@AEAAX_KPEAUtagNMHDR@@@Z`
- size: `537`
- prototype: `void __fastcall(CFmtBar *__hidden this, unsigned __int64, struct tagNMHDR *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180087fa0`

## callees

- `0x180085830`
- `0x180085910`
- `0x1800868f4`
- `0x180087d80`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `USER32!SendMessageA` at `0x180087f09`
- `USER32!SendMessageA` at `0x180087f09`
- `USER32!GetWindowLongA` at `0x180087f2e`
- `USER32!GetWindowLongA` at `0x180087f2e`
- `USER32!MapWindowPoints` at `0x180087e40`
- `USER32!MapWindowPoints` at `0x180087f1f`
- `USER32!MapWindowPoints` at `0x180087e40`
- `USER32!MapWindowPoints` at `0x180087f1f`
- `ole32!CoCreateInstance` at `0x180087de1`
- `ole32!CoCreateInstance` at `0x180087de1`

## pseudocode

```c
void __fastcall CFmtBar::WMNotify(CFmtBar *this, __int64 a2, struct tagNMHDR *a3)
{
  __int64 v5; // rdx
  UINT_PTR idFrom; // rdx
  unsigned __int64 v7; // rcx
  unsigned __int16 v8; // dx
  bool v9; // zf
  WPARAM v10; // r8
  bool v11; // cf
  LONG v12; // eax
  unsigned int *v13; // r9
  struct tagPOINT ppv; // [rsp+30h] [rbp-20h] BYREF
  LPARAM lParam[2]; // [rsp+38h] [rbp-18h] BYREF

  if ( a3->idFrom == 45 && a3->code == -841 )
  {
    ppv = 0;
    CoCreateInstance(&CLSID_TrackShellMenu, 0, 1u, &IID_ITrackShellMenu, (LPVOID *)&ppv);
    if ( ppv )
    {
      (*(void (__fastcall **)(struct tagPOINT, _QWORD, _QWORD, _QWORD, int))(**(_QWORD **)&ppv + 24LL))(
        ppv,
        0,
        0,
        0,
        268435460);
      (*(void (__fastcall **)(struct tagPOINT, _QWORD, _QWORD, __int64))(**(_QWORD **)&ppv + 96LL))(
        ppv,
        *((_QWORD *)this + 4),
        0,
        0x10000000);
      MapWindowPoints(*((HWND *)this + 7), 0, (LPPOINT)&a3[1].code, 2u);
      v5 = *((_QWORD *)this + 7);
      LODWORD(lParam[0]) = a3[1].code;
      HIDWORD(lParam[0]) = a3[2].hwndFrom;
      (*(void (__fastcall **)(struct tagPOINT, __int64, LPARAM *, UINT *, unsigned int))(**(_QWORD **)&ppv + 104LL))(
        ppv,
        v5,
        lParam,
        &a3[1].code,
        0x80000000);
      (*(void (__fastcall **)(struct tagPOINT))(**(_QWORD **)&ppv + 16LL))(ppv);
    }
  }
  if ( a3->code != -710 )
  {
    if ( a3->code == -520 )
    {
      idFrom = a3->idFrom;
      v7 = idFrom - 100;
      v8 = idFrom + 5101;
      if ( v7 > 0x1388 )
        v8 = 0;
      a3[1].hwndFrom = (HWND)v8;
      *(_QWORD *)&a3[4].code = (unsigned __int64)g_hLocRes & -(__int64)(v8 != 0);
    }
    return;
  }
  v9 = LODWORD(a3[1].hwndFrom) == 172;
  *(_OWORD *)lParam = 0;
  if ( v9 )
  {
    v10 = 5;
LABEL_14:
    SendMessageA(*((HWND *)this + 4), 0x41Du, v10, (LPARAM)lParam);
    goto LABEL_15;
  }
  if ( LODWORD(a3[1].hwndFrom) == 196 )
  {
    v10 = 1;
    goto LABEL_14;
  }
LABEL_15:
  MapWindowPoints(*((HWND *)this + 4), 0, (LPPOINT)lParam, 2u);
  v11 = (GetWindowLongA(*((HWND *)this + 4), -20) & 0x400000) != 0;
  v12 = lParam[0];
  if ( v11 )
    v12 = lParam[1];
  ppv.x = v12;
  v9 = LODWORD(a3[1].hwndFrom) == 172;
  ppv.y = HIDWORD(lParam[1]) + 2;
  if ( v9 )
  {
    CFmtBar::CheckColor(this);
    ColorMenu_Show(*((HMENU *)this + 9), *((HWND *)this + 3), ppv, v13);
  }
  else if ( LODWORD(a3[1].hwndFrom) == 196 )
  {
    CFmtBar::HrShowTagMenu(this, ppv);
  }
}

```

## disassembly

```asm
0x180087d80  mov     [rsp-18h+arg_8], rbx
0x180087d85  push    rbp
0x180087d86  push    rsi
0x180087d87  push    rdi
0x180087d88  mov     rbp, rsp
0x180087d8b  sub     rsp, 50h
0x180087d8f  mov     rax, cs:__security_cookie
0x180087d96  xor     rax, rsp
0x180087d99  mov     [rbp+var_8], rax
0x180087d9d  cmp     qword ptr [r8+8], 2Dh ; '-'
0x180087da2  mov     rsi, r8
0x180087da5  mov     rdi, rcx
0x180087da8  jnz     loc_180087E84
0x180087dae  cmp     dword ptr [r8+10h], 0FFFFFCB7h
0x180087db6  jnz     loc_180087E84
0x180087dbc  xor     edx, edx; pUnkOuter
0x180087dbe  mov     qword ptr [rbp+var_20.x], 0
0x180087dc6  lea     rax, [rbp+var_20]
0x180087dca  lea     r9, IID_ITrackShellMenu; riid
0x180087dd1  mov     [rsp+50h+ppv], rax; ppv
0x180087dd6  lea     rcx, CLSID_TrackShellMenu; rclsid
0x180087ddd  lea     r8d, [rdx+1]; dwClsContext
0x180087de1  call    cs:__imp_CoCreateInstance
0x180087de7  mov     rcx, qword ptr [rbp+var_20.x]
0x180087deb  test    rcx, rcx
0x180087dee  jz      loc_180087E84
0x180087df4  mov     rax, [rcx]
0x180087df7  xor     r9d, r9d
0x180087dfa  xor     r8d, r8d
0x180087dfd  mov     dword ptr [rsp+50h+ppv], 10000004h
0x180087e05  xor     edx, edx
0x180087e07  mov     rax, [rax+18h]
0x180087e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087e10  mov     rcx, qword ptr [rbp+var_20.x]
0x180087e14  mov     r9d, 10000000h
0x180087e1a  mov     rdx, [rdi+20h]
0x180087e1e  xor     r8d, r8d
0x180087e21  mov     rax, [rcx]
0x180087e24  mov     rax, [rax+60h]
0x180087e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087e2d  mov     rcx, [rdi+38h]; hWndFrom
0x180087e31  lea     rbx, [rsi+28h]
0x180087e35  mov     r8, rbx; lpPoints
0x180087e38  mov     r9d, 2; cPoints
0x180087e3e  xor     edx, edx; hWndTo
0x180087e40  call    cs:__imp_MapWindowPoints
0x180087e46  mov     eax, [rbx]
0x180087e48  lea     r8, [rbp+lParam]
0x180087e4c  mov     rcx, qword ptr [rbp+var_20.x]
0x180087e50  mov     r9, rbx
0x180087e53  mov     rdx, [rdi+38h]
0x180087e57  mov     dword ptr [rbp+lParam], eax
0x180087e5a  mov     eax, [rsi+30h]
0x180087e5d  mov     dword ptr [rbp+lParam+4], eax
0x180087e60  mov     rax, [rcx]
0x180087e63  mov     dword ptr [rsp+50h+ppv], 80000000h
0x180087e6b  mov     rax, [rax+68h]
0x180087e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087e74  mov     rcx, qword ptr [rbp+var_20.x]
0x180087e78  mov     rax, [rcx]
0x180087e7b  mov     rax, [rax+10h]
0x180087e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087e84  cmp     dword ptr [rsi+10h], 0FFFFFD3Ah
0x180087e8b  jz      short loc_180087ED4
0x180087e8d  cmp     dword ptr [rsi+10h], 0FFFFFDF8h
0x180087e94  jnz     loc_180087F80
0x180087e9a  mov     rdx, [rsi+8]
0x180087e9e  mov     eax, 13EDh
0x180087ea3  lea     rcx, [rdx-64h]
0x180087ea7  add     dx, ax
0x180087eaa  xor     eax, eax
0x180087eac  cmp     rcx, 1388h
0x180087eb3  cmova   dx, ax
0x180087eb7  movzx   eax, dx
0x180087eba  mov     [rsi+18h], rax
0x180087ebe  neg     ax
0x180087ec1  sbb     rax, rax
0x180087ec4  and     rax, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hLocRes
0x180087ecb  mov     [rsi+70h], rax
0x180087ecf  jmp     loc_180087F80
0x180087ed4  cmp     dword ptr [rsi+18h], 0ACh
0x180087edb  xorps   xmm0, xmm0
0x180087ede  movups  xmmword ptr [rbp+lParam], xmm0
0x180087ee2  mov     ebx, 0C4h
0x180087ee7  jnz     short loc_180087EF1
0x180087ee9  mov     r8d, 5
0x180087eef  jmp     short loc_180087EFC
0x180087ef1  cmp     [rsi+18h], ebx
0x180087ef4  jnz     short loc_180087F0F
0x180087ef6  mov     r8d, 1; wParam
0x180087efc  mov     rcx, [rdi+20h]; hWnd
0x180087f00  lea     r9, [rbp+lParam]; lParam
0x180087f04  mov     edx, 41Dh; Msg
0x180087f09  call    cs:__imp_SendMessageA
0x180087f0f  mov     rcx, [rdi+20h]; hWndFrom
0x180087f13  lea     r8, [rbp+lParam]; lpPoints
0x180087f17  mov     r9d, 2; cPoints
0x180087f1d  xor     edx, edx; hWndTo
0x180087f1f  call    cs:__imp_MapWindowPoints
0x180087f25  mov     rcx, [rdi+20h]; hWnd
0x180087f29  mov     edx, 0FFFFFFECh; nIndex
0x180087f2e  call    cs:__imp_GetWindowLongA
0x180087f34  bt      eax, 16h
0x180087f38  mov     eax, dword ptr [rbp+lParam]
0x180087f3b  cmovb   eax, dword ptr [rbp+lParam+8]
0x180087f3f  mov     [rbp+var_20.x], eax
0x180087f42  mov     eax, dword ptr [rbp+lParam+0Ch]
0x180087f45  add     eax, 2
0x180087f48  cmp     dword ptr [rsi+18h], 0ACh
0x180087f4f  mov     [rbp+var_20.y], eax
0x180087f52  jnz     short loc_180087F6F
0x180087f54  mov     rcx, rdi; this
0x180087f57  call    ?CheckColor@CFmtBar@@AEAAJXZ; CFmtBar::CheckColor(void)
0x180087f5c  mov     r8, qword ptr [rbp+var_20.x]; struct tagPOINT
0x180087f60  mov     rdx, [rdi+18h]; HWND
0x180087f64  mov     rcx, [rdi+48h]; HMENU
0x180087f68  call    ?ColorMenu_Show@@YAJPEAUHMENU__@@PEAUHWND__@@UtagPOINT@@PEAK@Z; ColorMenu_Show(HMENU__ *,HWND__ *,tagPOINT,ulong *)
0x180087f6d  jmp     short loc_180087F80
0x180087f6f  cmp     [rsi+18h], ebx
0x180087f72  jnz     short loc_180087F80
0x180087f74  mov     rdx, qword ptr [rbp+var_20.x]; struct tagPOINT
0x180087f78  mov     rcx, rdi; this
0x180087f7b  call    ?HrShowTagMenu@CFmtBar@@AEAAJUtagPOINT@@@Z; CFmtBar::HrShowTagMenu(tagPOINT)
0x180087f80  mov     rcx, [rbp+var_8]
0x180087f84  xor     rcx, rsp; StackCookie
0x180087f87  call    __security_check_cookie
0x180087f8c  mov     rbx, [rsp+50h+arg_8]
0x180087f91  add     rsp, 50h
0x180087f95  pop     rdi
0x180087f96  pop     rsi
0x180087f97  pop     rbp
0x180087f98  retn
```
