# XSend_ListView_SetItem(HWND__ *,uint,unsigned __int64,tagLVITEMW *,uint)

- ea: `0x180026308`
- end: `0x1800263e2`
- name: `?XSend_ListView_SetItem@@YAJPEAUHWND__@@I_KPEAUtagLVITEMW@@I@Z`
- size: `218`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, struct tagLVITEMW *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002f77c`
- `0x180030090`

## callees

- `0x18000c594`
- `0x18001e4c0`
- `0x180024f64`
- `0x18002509c`
- `0x180026308`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026348`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026348`
- `USER32!GetWindowThreadProcessId` at `0x18002633e`
- `USER32!GetWindowThreadProcessId` at `0x18002633e`
- `USER32!SendMessageW` at `0x180026361`
- `USER32!SendMessageW` at `0x180026361`

## pseudocode

```c
__int64 __fastcall XSend_ListView_SetItem(HWND a1, __int64 a2, WPARAM a3, struct tagLVITEMW *a4)
{
  DWORD dwProcessId; // [rsp+40h] [rbp-11h] BYREF
  int v9; // [rsp+44h] [rbp-Dh] BYREF
  _OWORD Buffer[2]; // [rsp+48h] [rbp-9h] BYREF
  __int128 v11; // [rsp+68h] [rbp+17h]
  __int64 v12; // [rsp+78h] [rbp+27h]

  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(a1, &dwProcessId) )
    return 2147500037LL;
  if ( dwProcessId == GetCurrentProcessId() )
  {
    SendMessageW(a1, 0x102Bu, a3, (LPARAM)a4);
    return 0;
  }
  v9 = 0;
  if ( (int)SameBitness(a1, &v9) < 0 )
    return 2147500037LL;
  memset(Buffer, 0, sizeof(Buffer));
  if ( v9 )
  {
    v12 = 0;
    v11 = 0;
    return ListView_Set_Handler<LVITEM_64>(Buffer, a1, (__int64)a4);
  }
  else
  {
    *(_QWORD *)&v11 = 0;
    return ListView_Set_Handler<LVITEM_32>(Buffer, a1, (__int64)a4);
  }
}

```

## disassembly

```asm
0x180026308  mov     [rsp-8+arg_8], rbx
0x18002630d  push    rbp
0x18002630e  push    rsi
0x18002630f  push    rdi
0x180026310  lea     rbp, [rsp-3Fh]
0x180026315  sub     rsp, 90h
0x18002631c  mov     rax, cs:__security_cookie
0x180026323  xor     rax, rsp
0x180026326  mov     [rbp+4Fh+var_20], rax
0x18002632a  lea     rdx, [rbp+4Fh+dwProcessId]; lpdwProcessId
0x18002632e  mov     [rbp+4Fh+dwProcessId], 0
0x180026335  mov     rsi, r9
0x180026338  mov     rdi, r8
0x18002633b  mov     rbx, rcx
0x18002633e  call    cs:__imp_GetWindowThreadProcessId
0x180026344  test    eax, eax
0x180026346  jz      short loc_1800263BE
0x180026348  call    cs:__imp_GetCurrentProcessId
0x18002634e  mov     rcx, rbx; HWND
0x180026351  cmp     [rbp+4Fh+dwProcessId], eax
0x180026354  jnz     short loc_18002636B
0x180026356  mov     r9, rsi; lParam
0x180026359  mov     r8, rdi; wParam
0x18002635c  mov     edx, 102Bh; Msg
0x180026361  call    cs:__imp_SendMessageW
0x180026367  xor     eax, eax
0x180026369  jmp     short loc_1800263C3
0x18002636b  lea     rdx, [rbp+4Fh+var_5C]; int *
0x18002636f  mov     [rbp+4Fh+var_5C], 0
0x180026376  call    ?SameBitness@@YAJPEAUHWND__@@PEAH@Z; SameBitness(HWND__ *,int *)
0x18002637b  test    eax, eax
0x18002637d  js      short loc_1800263BE
0x18002637f  xorps   xmm0, xmm0
0x180026382  mov     [rsp+0A0h+var_80], rsi; __int64
0x180026387  xor     eax, eax
0x180026389  mov     r9, rdi
0x18002638c  mov     rdx, rbx; HWND
0x18002638f  movups  [rbp+4Fh+Buffer], xmm0
0x180026393  movups  [rbp+4Fh+var_48], xmm0
0x180026397  cmp     [rbp+4Fh+var_5C], eax
0x18002639a  jz      short loc_1800263AF
0x18002639c  lea     rcx, [rbp+4Fh+Buffer]; lpBuffer
0x1800263a0  mov     [rbp+4Fh+var_28], rax
0x1800263a4  movups  [rbp+4Fh+var_38], xmm0
0x1800263a8  call    ??$ListView_Set_Handler@ULVITEM_64@@@@YAJAEAULVITEM_64@@PEAUHWND__@@I_KPEAUtagLVITEMW@@HI@Z; ListView_Set_Handler<LVITEM_64>(LVITEM_64 &,HWND__ *,uint,unsigned __int64,tagLVITEMW *,int,uint)
0x1800263ad  jmp     short loc_1800263C3
0x1800263af  lea     rcx, [rbp+4Fh+Buffer]; lpBuffer
0x1800263b3  mov     qword ptr [rbp+4Fh+var_38], rax
0x1800263b7  call    ??$ListView_Set_Handler@ULVITEM_32@@@@YAJAEAULVITEM_32@@PEAUHWND__@@I_KPEAUtagLVITEMW@@HI@Z; ListView_Set_Handler<LVITEM_32>(LVITEM_32 &,HWND__ *,uint,unsigned __int64,tagLVITEMW *,int,uint)
0x1800263bc  jmp     short loc_1800263C3
0x1800263be  mov     eax, 80004005h
0x1800263c3  mov     rcx, [rbp+4Fh+var_20]
0x1800263c7  xor     rcx, rsp; StackCookie
0x1800263ca  call    __security_check_cookie
0x1800263cf  mov     rbx, [rsp+0A0h+arg_8]
0x1800263d7  add     rsp, 90h
0x1800263de  pop     rdi
0x1800263df  pop     rsi
0x1800263e0  pop     rbp
0x1800263e1  retn
```
