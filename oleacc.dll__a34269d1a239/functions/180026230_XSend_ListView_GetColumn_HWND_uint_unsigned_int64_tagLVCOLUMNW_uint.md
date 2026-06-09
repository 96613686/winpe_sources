# XSend_ListView_GetColumn(HWND__ *,uint,unsigned __int64,tagLVCOLUMNW *,uint)

- ea: `0x180026230`
- end: `0x180026300`
- name: `?XSend_ListView_GetColumn@@YAJPEAUHWND__@@I_KPEAUtagLVCOLUMNW@@I@Z`
- size: `208`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, struct tagLVCOLUMNW *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002ef5c`

## callees

- `0x18000c594`
- `0x18001e4c0`
- `0x180024a04`
- `0x180024b44`
- `0x180026230`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002626b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002626b`
- `USER32!GetWindowThreadProcessId` at `0x180026261`
- `USER32!GetWindowThreadProcessId` at `0x180026261`
- `USER32!SendMessageW` at `0x180026284`
- `USER32!SendMessageW` at `0x180026284`

## pseudocode

```c
__int64 __fastcall XSend_ListView_GetColumn(HWND a1, __int64 a2, WPARAM a3, struct tagLVCOLUMNW *a4)
{
  __int64 v8; // r8
  DWORD dwProcessId; // [rsp+40h] [rbp-30h] BYREF
  int v10; // [rsp+44h] [rbp-2Ch] BYREF
  __int128 Buffer; // [rsp+48h] [rbp-28h] BYREF
  __int128 v12; // [rsp+58h] [rbp-18h]

  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(a1, &dwProcessId) )
    return 2147500037LL;
  if ( dwProcessId == GetCurrentProcessId() )
  {
    if ( SendMessageW(a1, 0x105Fu, a3, (LPARAM)a4) )
      return 0;
    return 2147500037LL;
  }
  v10 = 0;
  if ( (int)SameBitness(a1, &v10) < 0 )
    return 2147500037LL;
  Buffer = 0;
  if ( v10 )
  {
    v12 = 0;
    return ListView_GetCol_Handler<LVCOLUMN_64>(&Buffer, a1, v8, a3, (__int64)a4);
  }
  else
  {
    *(_QWORD *)&v12 = 0;
    return ListView_GetCol_Handler<LVCOLUMN_32>((unsigned int *)&Buffer, a1, v8, a3, (__int64)a4);
  }
}

```

## disassembly

```asm
0x180026230  mov     [rsp-18h+arg_8], rbx
0x180026235  push    rbp
0x180026236  push    rsi
0x180026237  push    rdi
0x180026238  mov     rbp, rsp
0x18002623b  sub     rsp, 70h
0x18002623f  mov     rax, cs:__security_cookie
0x180026246  xor     rax, rsp
0x180026249  mov     [rbp+var_8], rax
0x18002624d  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180026251  mov     [rbp+dwProcessId], 0
0x180026258  mov     rsi, r9
0x18002625b  mov     rdi, r8
0x18002625e  mov     rbx, rcx
0x180026261  call    cs:__imp_GetWindowThreadProcessId
0x180026267  test    eax, eax
0x180026269  jz      short loc_1800262DF
0x18002626b  call    cs:__imp_GetCurrentProcessId
0x180026271  mov     rcx, rbx; HWND
0x180026274  cmp     [rbp+dwProcessId], eax
0x180026277  jnz     short loc_180026293
0x180026279  mov     r9, rsi; lParam
0x18002627c  mov     r8, rdi; wParam
0x18002627f  mov     edx, 105Fh; Msg
0x180026284  call    cs:__imp_SendMessageW
0x18002628a  test    rax, rax
0x18002628d  jz      short loc_1800262DF
0x18002628f  xor     eax, eax
0x180026291  jmp     short loc_1800262E4
0x180026293  lea     rdx, [rbp+var_2C]; int *
0x180026297  mov     [rbp+var_2C], 0
0x18002629e  call    ?SameBitness@@YAJPEAUHWND__@@PEAH@Z; SameBitness(HWND__ *,int *)
0x1800262a3  test    eax, eax
0x1800262a5  js      short loc_1800262DF
0x1800262a7  cmp     [rbp+var_2C], 0
0x1800262ab  xorps   xmm0, xmm0
0x1800262ae  movups  [rbp+Buffer], xmm0
0x1800262b2  mov     [rsp+70h+var_50], rsi; __int64
0x1800262b7  mov     r9, rdi
0x1800262ba  mov     rdx, rbx; HWND
0x1800262bd  jz      short loc_1800262CE
0x1800262bf  lea     rcx, [rbp+Buffer]; lpBuffer
0x1800262c3  movups  [rbp+var_18], xmm0
0x1800262c7  call    ??$ListView_GetCol_Handler@ULVCOLUMN_64@@@@YAJAEAULVCOLUMN_64@@PEAUHWND__@@I_KPEAUtagLVCOLUMNW@@HI@Z; ListView_GetCol_Handler<LVCOLUMN_64>(LVCOLUMN_64 &,HWND__ *,uint,unsigned __int64,tagLVCOLUMNW *,int,uint)
0x1800262cc  jmp     short loc_1800262E4
0x1800262ce  xor     eax, eax
0x1800262d0  lea     rcx, [rbp+Buffer]; lpBuffer
0x1800262d4  mov     qword ptr [rbp+var_18], rax
0x1800262d8  call    ??$ListView_GetCol_Handler@ULVCOLUMN_32@@@@YAJAEAULVCOLUMN_32@@PEAUHWND__@@I_KPEAUtagLVCOLUMNW@@HI@Z; ListView_GetCol_Handler<LVCOLUMN_32>(LVCOLUMN_32 &,HWND__ *,uint,unsigned __int64,tagLVCOLUMNW *,int,uint)
0x1800262dd  jmp     short loc_1800262E4
0x1800262df  mov     eax, 80004005h
0x1800262e4  mov     rcx, [rbp+var_8]
0x1800262e8  xor     rcx, rsp; StackCookie
0x1800262eb  call    __security_check_cookie
0x1800262f0  mov     rbx, [rsp+70h+arg_8]
0x1800262f8  add     rsp, 70h
0x1800262fc  pop     rdi
0x1800262fd  pop     rsi
0x1800262fe  pop     rbp
0x1800262ff  retn
```
