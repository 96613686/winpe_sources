# DeviceSetWindow(_MCIGRAPHIC *,HWND__ *)

- ea: `0x180003210`
- end: `0x180003400`
- name: `?DeviceSetWindow@@YAKPEAU_MCIGRAPHIC@@PEAUHWND__@@@Z`
- size: `496`
- prototype: `unsigned int(struct _MCIGRAPHIC *, HWND)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180002448`
- `0x180006230`

## callees

- `0x180001460`
- `0x180001e7c`
- `0x180003210`
- `0x180007010`

## import_xrefs

- `USER32!IsIconic` at `0x18000329a`
- `USER32!IsIconic` at `0x18000329a`
- `USER32!IsZoomed` at `0x1800032ae`
- `USER32!IsZoomed` at `0x1800032ae`
- `USER32!IsWindowVisible` at `0x1800032c2`
- `USER32!IsWindowVisible` at `0x1800032c2`
- `USER32!ShowWindow` at `0x1800032f3`
- `USER32!ShowWindow` at `0x1800032f3`
- `USER32!IsWindow` at `0x18000325e`
- `USER32!IsWindow` at `0x18000325e`

## pseudocode

```c
__int64 __fastcall DeviceSetWindow(struct _MCIGRAPHIC *a1, HWND a2)
{
  HWND *v2; // rsi
  HWND v3; // rdi
  int v6; // ebp
  HWND v7; // rcx
  BOOL v8; // eax
  int v9; // edx
  int v10; // edx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // [rsp+38h] [rbp-30h] BYREF

  v2 = (HWND *)((char *)a1 + 48);
  v3 = a2;
  if ( !a2 )
    v3 = *v2;
  if ( v3 == *((HWND *)a1 + 37) )
    return 0;
  v6 = -2147467259;
  if ( v3 && IsWindow(v3) && *((_QWORD *)a1 + 22) )
  {
    v7 = *v2;
    if ( *((HWND *)a1 + 37) == *v2 )
    {
      if ( v3 != v7 )
      {
        *((_DWORD *)a1 + 61) = 0;
        if ( IsIconic(v7) )
          *((_DWORD *)a1 + 61) |= 6u;
        if ( IsZoomed(*v2) )
          *((_DWORD *)a1 + 61) |= 3u;
        v8 = IsWindowVisible(*v2);
        v9 = *((_DWORD *)a1 + 61) | 5;
        if ( !v8 )
          v9 = *((_DWORD *)a1 + 61);
        *((_DWORD *)a1 + 61) = v9;
        v10 = 0;
        v7 = *v2;
        goto LABEL_19;
      }
    }
    else if ( v3 != v7 )
    {
LABEL_20:
      v11 = *((_QWORD *)a1 + 22);
      *((_QWORD *)a1 + 37) = v3;
      (*(void (__fastcall **)(__int64, HWND))(*(_QWORD *)v11 + 248LL))(v11, v3);
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 22) + 120LL))(*((_QWORD *)a1 + 22), 0);
      (*(void (__fastcall **)(_QWORD, HWND))(**((_QWORD **)a1 + 22) + 232LL))(*((_QWORD *)a1 + 22), v3);
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a1 + 22) + 72LL))(*((_QWORD *)a1 + 22), 0x40000000);
      v12 = *((_QWORD *)a1 + 21);
      v13 = 0;
      (*(void (__fastcall **)(__int64, __int64 *, char *))(*(_QWORD *)v12 + 272LL))(v12, &v13, (char *)&v13 + 4);
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(**((_QWORD **)a1 + 22) + 312LL))(
        *((_QWORD *)a1 + 22),
        0,
        0,
        (unsigned int)v13,
        HIDWORD(v13));
      v6 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a1 + 22) + 120LL))(*((_QWORD *)a1 + 22), 1);
      return CheckResult(v6);
    }
    v10 = *((_DWORD *)a1 + 61);
LABEL_19:
    ShowWindow(v7, v10);
    goto LABEL_20;
  }
  return CheckResult(v6);
}

```

## disassembly

```asm
0x180003210  mov     [rsp+arg_10], rbx
0x180003215  push    rbp
0x180003216  push    rsi
0x180003217  push    rdi
0x180003218  sub     rsp, 50h
0x18000321c  mov     rax, cs:__security_cookie
0x180003223  xor     rax, rsp
0x180003226  mov     [rsp+68h+var_28], rax
0x18000322b  lea     rsi, [rcx+30h]
0x18000322f  mov     rdi, rdx
0x180003232  mov     rbx, rcx
0x180003235  test    rdx, rdx
0x180003238  jnz     short loc_18000323D
0x18000323a  mov     rdi, [rsi]
0x18000323d  cmp     rdi, [rcx+128h]
0x180003244  jnz     short loc_18000324D
0x180003246  xor     eax, eax
0x180003248  jmp     loc_1800033E3
0x18000324d  mov     ebp, 80004005h
0x180003252  test    rdi, rdi
0x180003255  jz      loc_1800033DC
0x18000325b  mov     rcx, rdi; hWnd
0x18000325e  call    cs:__imp_IsWindow
0x180003264  test    eax, eax
0x180003266  jz      loc_1800033DC
0x18000326c  cmp     qword ptr [rbx+0B0h], 0
0x180003274  jz      loc_1800033DC
0x18000327a  mov     rcx, [rsi]; hWnd
0x18000327d  mov     ebp, 1
0x180003282  cmp     [rbx+128h], rcx
0x180003289  jnz     short loc_1800032E8
0x18000328b  cmp     rdi, rcx
0x18000328e  jz      short loc_1800032ED
0x180003290  mov     dword ptr [rbx+0F4h], 0
0x18000329a  call    cs:__imp_IsIconic
0x1800032a0  cmp     eax, ebp
0x1800032a2  jnz     short loc_1800032AB
0x1800032a4  or      dword ptr [rbx+0F4h], 6
0x1800032ab  mov     rcx, [rsi]; hWnd
0x1800032ae  call    cs:__imp_IsZoomed
0x1800032b4  cmp     eax, ebp
0x1800032b6  jnz     short loc_1800032BF
0x1800032b8  or      dword ptr [rbx+0F4h], 3
0x1800032bf  mov     rcx, [rsi]; hWnd
0x1800032c2  call    cs:__imp_IsWindowVisible
0x1800032c8  mov     r8d, [rbx+0F4h]
0x1800032cf  mov     edx, r8d
0x1800032d2  or      edx, 5
0x1800032d5  cmp     eax, ebp
0x1800032d7  cmovnz  edx, r8d
0x1800032db  mov     [rbx+0F4h], edx
0x1800032e1  xor     edx, edx
0x1800032e3  mov     rcx, [rsi]
0x1800032e6  jmp     short loc_1800032F3
0x1800032e8  cmp     rdi, rcx
0x1800032eb  jnz     short loc_1800032F9
0x1800032ed  mov     edx, [rbx+0F4h]; nCmdShow
0x1800032f3  call    cs:__imp_ShowWindow
0x1800032f9  mov     rcx, [rbx+0B0h]
0x180003300  mov     rdx, rdi
0x180003303  mov     [rbx+128h], rdi
0x18000330a  mov     rax, [rcx]
0x18000330d  mov     rax, [rax+0F8h]
0x180003314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003319  mov     rcx, [rbx+0B0h]
0x180003320  xor     edx, edx
0x180003322  mov     rax, [rcx]
0x180003325  mov     rax, [rax+78h]
0x180003329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000332e  mov     rcx, [rbx+0B0h]
0x180003335  mov     rdx, rdi
0x180003338  mov     rax, [rcx]
0x18000333b  mov     rax, [rax+0E8h]
0x180003342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003347  mov     rcx, [rbx+0B0h]
0x18000334e  mov     edx, 40000000h
0x180003353  mov     rax, [rcx]
0x180003356  mov     rax, [rax+48h]
0x18000335a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000335f  mov     rcx, [rbx+0A8h]
0x180003366  lea     r8, [rsp+68h+var_2C]
0x18000336b  mov     qword ptr [rsp+38h], 0
0x180003374  lea     rdx, [rsp+68h+var_30]
0x180003379  mov     [rsp+68h+var_38], 0
0x180003382  mov     rax, [rcx]
0x180003385  mov     rax, [rax+110h]
0x18000338c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003391  mov     rcx, [rbx+0B0h]
0x180003398  xor     edx, edx
0x18000339a  mov     r8d, [rsp+68h+var_2C]
0x18000339f  sub     r8d, dword ptr [rsp+68h+var_38+4]
0x1800033a4  mov     r9d, [rsp+68h+var_30]
0x1800033a9  mov     rax, [rcx]
0x1800033ac  sub     r9d, dword ptr [rsp+68h+var_38]
0x1800033b1  mov     [rsp+68h+var_48], r8d
0x1800033b6  xor     r8d, r8d
0x1800033b9  mov     rax, [rax+138h]
0x1800033c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033c5  mov     rcx, [rbx+0B0h]
0x1800033cc  mov     edx, ebp
0x1800033ce  mov     rax, [rcx]
0x1800033d1  mov     rax, [rax+78h]
0x1800033d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033da  mov     ebp, eax
0x1800033dc  mov     ecx, ebp; int
0x1800033de  call    ?CheckResult@@YAKJ@Z; CheckResult(long)
0x1800033e3  mov     rcx, [rsp+68h+var_28]
0x1800033e8  xor     rcx, rsp; StackCookie
0x1800033eb  call    __security_check_cookie
0x1800033f0  mov     rbx, [rsp+68h+arg_10]
0x1800033f8  add     rsp, 50h
0x1800033fc  pop     rdi
0x1800033fd  pop     rsi
0x1800033fe  pop     rbp
0x1800033ff  retn
```
