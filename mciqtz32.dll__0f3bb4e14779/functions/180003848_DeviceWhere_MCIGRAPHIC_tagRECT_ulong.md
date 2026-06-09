# DeviceWhere(_MCIGRAPHIC *,tagRECT *,ulong)

- ea: `0x180003848`
- end: `0x1800039fe`
- name: `?DeviceWhere@@YAKPEAU_MCIGRAPHIC@@PEAUtagRECT@@K@Z`
- size: `438`
- prototype: `unsigned int(struct _MCIGRAPHIC *, struct tagRECT *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000617c`

## callees

- `0x180001e7c`
- `0x180003848`
- `0x180007010`

## import_xrefs

- `USER32!GetClientRect` at `0x18000390e`
- `USER32!GetClientRect` at `0x18000390e`
- `USER32!SetRectEmpty` at `0x1800039c0`
- `USER32!SetRectEmpty` at `0x1800039c0`
- `USER32!GetWindowRect` at `0x1800038d7`
- `USER32!GetWindowRect` at `0x1800038d7`
- `USER32!ScreenToClient` at `0x180003971`
- `USER32!ScreenToClient` at `0x180003971`
- `USER32!GetSystemMetrics` at `0x1800038a0`
- `USER32!GetSystemMetrics` at `0x1800038ae`
- `USER32!GetSystemMetrics` at `0x1800038a0`
- `USER32!GetSystemMetrics` at `0x1800038ae`
- `USER32!GetWindowLongPtrW` at `0x180003955`
- `USER32!GetWindowLongPtrW` at `0x180003955`

## pseudocode

```c
unsigned int __fastcall DeviceWhere(struct _MCIGRAPHIC *a1, struct tagRECT *a2, int a3)
{
  int v4; // eax
  int v6; // esi
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // eax

  v4 = a3 & 0x260000;
  v6 = 0;
  if ( (a3 & 0x260000) == 0x20000 )
  {
    v9 = *((_QWORD *)a1 + 21);
    if ( !v9 )
      return 346;
    if ( (a3 & 0x400000) != 0 )
    {
      *(_QWORD *)&a2->left = 0;
      v10 = (*(__int64 (__fastcall **)(_QWORD, LONG *, LONG *))(**((_QWORD **)a1 + 21) + 272LL))(
              *((_QWORD *)a1 + 21),
              &a2->right,
              &a2->bottom);
    }
    else
    {
      if ( (a3 & 0x800000) != 0 )
        goto LABEL_23;
      v10 = (*(__int64 (__fastcall **)(__int64, struct tagRECT *, LONG *, LONG *, LONG *))(*(_QWORD *)v9 + 232LL))(
              v9,
              a2,
              &a2->top,
              &a2->right,
              &a2->bottom);
    }
    v6 = v10;
    return CheckResult(v6);
  }
  if ( v4 == 0x40000 )
  {
    v8 = *((_QWORD *)a1 + 22);
    if ( !v8 )
      return 346;
    if ( (a3 & 0x400000) != 0 )
    {
      GetClientRect(*((HWND *)a1 + 37), a2);
      return CheckResult(v6);
    }
    if ( (a3 & 0x800000) == 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, struct tagRECT *, LONG *, LONG *, LONG *))(*(_QWORD *)v8 + 320LL))(
             v8,
             a2,
             &a2->top,
             &a2->right,
             &a2->bottom);
      if ( (GetWindowLongPtrW(*((HWND *)a1 + 37), -20) & 0x400000) != 0 )
        a2->left += a2->right;
      ScreenToClient(*((HWND *)a1 + 37), (LPPOINT)a2);
      return CheckResult(v6);
    }
LABEL_23:
    SetRectEmpty(a2);
    return CheckResult(v6);
  }
  if ( v4 == 0x200000 )
  {
    if ( *((_QWORD *)a1 + 22) )
    {
      if ( (a3 & 0x400000) != 0 )
      {
        *(_QWORD *)&a2->left = 0;
        a2->right = GetSystemMetrics(0);
        a2->bottom = GetSystemMetrics(1);
      }
      else
      {
        if ( (a3 & 0x800000) != 0 )
          return 274;
        GetWindowRect(*((HWND *)a1 + 37), a2);
        a2->right -= a2->left;
        a2->bottom -= a2->top;
      }
      return CheckResult(v6);
    }
    return 346;
  }
  v6 = -2147467263;
  return CheckResult(v6);
}

```

## disassembly

```asm
0x180003848  push    rbx
0x18000384a  push    rsi
0x18000384b  push    rdi
0x18000384c  push    r14
0x18000384e  sub     rsp, 38h
0x180003852  mov     eax, r8d
0x180003855  mov     rbx, rdx
0x180003858  xor     edx, edx
0x18000385a  and     eax, 260000h
0x18000385f  mov     rdi, rcx
0x180003862  mov     esi, edx
0x180003864  cmp     eax, 20000h
0x180003869  jz      loc_180003979
0x18000386f  cmp     eax, 40000h
0x180003874  jz      short loc_1800038ED
0x180003876  cmp     eax, 200000h
0x18000387b  jz      short loc_180003887
0x18000387d  mov     esi, 80004001h
0x180003882  jmp     loc_1800039ED
0x180003887  cmp     [rcx+0B0h], rdx
0x18000388e  jz      loc_180003985
0x180003894  bt      r8d, 16h
0x180003899  jnb     short loc_1800038BC
0x18000389b  xor     ecx, ecx; nIndex
0x18000389d  mov     [rbx], rdx
0x1800038a0  call    cs:__imp_GetSystemMetrics
0x1800038a6  mov     ecx, 1; nIndex
0x1800038ab  mov     [rbx+8], eax
0x1800038ae  call    cs:__imp_GetSystemMetrics
0x1800038b4  mov     [rbx+0Ch], eax
0x1800038b7  jmp     loc_1800039ED
0x1800038bc  bt      r8d, 17h
0x1800038c1  jnb     short loc_1800038CD
0x1800038c3  mov     eax, 112h
0x1800038c8  jmp     loc_1800039F4
0x1800038cd  mov     rcx, [rcx+128h]; hWnd
0x1800038d4  mov     rdx, rbx; lpRect
0x1800038d7  call    cs:__imp_GetWindowRect
0x1800038dd  mov     eax, [rbx]
0x1800038df  sub     [rbx+8], eax
0x1800038e2  mov     eax, [rbx+4]
0x1800038e5  sub     [rbx+0Ch], eax
0x1800038e8  jmp     loc_1800039ED
0x1800038ed  mov     rcx, [rcx+0B0h]
0x1800038f4  test    rcx, rcx
0x1800038f7  jz      loc_180003985
0x1800038fd  bt      r8d, 16h
0x180003902  jnb     short loc_180003919
0x180003904  mov     rcx, [rdi+128h]; hWnd
0x18000390b  mov     rdx, rbx; lpRect
0x18000390e  call    cs:__imp_GetClientRect
0x180003914  jmp     loc_1800039ED
0x180003919  bt      r8d, 17h
0x18000391e  jb      loc_1800039BD
0x180003924  mov     rax, [rcx]
0x180003927  lea     rdx, [rbx+0Ch]
0x18000392b  mov     [rsp+58h+var_38], rdx
0x180003930  lea     r8, [rbx+4]
0x180003934  lea     r9, [rbx+8]
0x180003938  mov     rdx, rbx
0x18000393b  mov     rax, [rax+140h]
0x180003942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003947  mov     rcx, [rdi+128h]; hWnd
0x18000394e  mov     edx, 0FFFFFFECh; nIndex
0x180003953  mov     esi, eax
0x180003955  call    cs:__imp_GetWindowLongPtrW
0x18000395b  bt      rax, 16h
0x180003960  jnb     short loc_180003967
0x180003962  mov     ecx, [rbx+8]
0x180003965  add     [rbx], ecx
0x180003967  mov     rcx, [rdi+128h]; hWnd
0x18000396e  mov     rdx, rbx; lpPoint
0x180003971  call    cs:__imp_ScreenToClient
0x180003977  jmp     short loc_1800039ED
0x180003979  mov     rcx, [rcx+0A8h]
0x180003980  test    rcx, rcx
0x180003983  jnz     short loc_18000398C
0x180003985  mov     eax, 15Ah
0x18000398a  jmp     short loc_1800039F4
0x18000398c  bt      r8d, 16h
0x180003991  jnb     short loc_1800039B6
0x180003993  mov     [rbx], rdx
0x180003996  lea     r8, [rbx+0Ch]
0x18000399a  mov     rcx, [rdi+0A8h]
0x1800039a1  lea     rdx, [rbx+8]
0x1800039a5  mov     rax, [rcx]
0x1800039a8  mov     rax, [rax+110h]
0x1800039af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039b4  jmp     short loc_1800039EB
0x1800039b6  bt      r8d, 17h
0x1800039bb  jnb     short loc_1800039C8
0x1800039bd  mov     rcx, rbx; lprc
0x1800039c0  call    cs:__imp_SetRectEmpty
0x1800039c6  jmp     short loc_1800039ED
0x1800039c8  mov     rax, [rcx]
0x1800039cb  lea     rdx, [rbx+0Ch]
0x1800039cf  mov     [rsp+58h+var_38], rdx
0x1800039d4  lea     r9, [rbx+8]
0x1800039d8  lea     r8, [rbx+4]
0x1800039dc  mov     rdx, rbx
0x1800039df  mov     rax, [rax+0E8h]
0x1800039e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039eb  mov     esi, eax
0x1800039ed  mov     ecx, esi; int
0x1800039ef  call    ?CheckResult@@YAKJ@Z; CheckResult(long)
0x1800039f4  add     rsp, 38h
0x1800039f8  pop     r14
0x1800039fa  pop     rdi
0x1800039fb  pop     rsi
0x1800039fc  pop     rbx
0x1800039fd  retn
```
