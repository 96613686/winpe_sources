# XSend_ListView_GetItem(HWND__ *,uint,unsigned __int64,tagLVITEMW *,uint)

- ea: `0x18000d1cc`
- end: `0x18000d2aa`
- name: `?XSend_ListView_GetItem@@YAJPEAUHWND__@@I_KPEAUtagLVITEMW@@I@Z`
- size: `222`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, struct tagLVITEMW *, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000ce1c`
- `0x18001a670`
- `0x18002ef5c`
- `0x180031a60`

## callees

- `0x18000c594`
- `0x18000d1cc`
- `0x18001e4c0`
- `0x180024c84`
- `0x180024df4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d20c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d20c`
- `USER32!GetWindowThreadProcessId` at `0x18000d202`
- `USER32!GetWindowThreadProcessId` at `0x18000d202`
- `USER32!SendMessageW` at `0x18000d225`
- `USER32!SendMessageW` at `0x18000d225`

## pseudocode

```c
__int64 __fastcall XSend_ListView_GetItem(HWND a1, __int64 a2, __int64 a3, struct tagLVITEMW *a4)
{
  __int64 v7; // r8
  __int64 v8; // r9
  DWORD dwProcessId; // [rsp+40h] [rbp-1h] BYREF
  int v10; // [rsp+44h] [rbp+3h] BYREF
  _OWORD Buffer[2]; // [rsp+48h] [rbp+7h] BYREF
  __int128 v12; // [rsp+68h] [rbp+27h]
  __int64 v13; // [rsp+78h] [rbp+37h]

  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(a1, &dwProcessId) )
    return 2147500037LL;
  if ( dwProcessId == GetCurrentProcessId() )
  {
    if ( SendMessageW(a1, 0x104Bu, 0, (LPARAM)a4) )
      return 0;
    return 2147500037LL;
  }
  v10 = 0;
  if ( (int)SameBitness(a1, &v10) < 0 )
    return 2147500037LL;
  memset(Buffer, 0, sizeof(Buffer));
  if ( v10 )
  {
    v13 = 0;
    v12 = 0;
    return ListView_Get_Handler<LVITEM_64>(Buffer, a1, v7, v8, (__int64)a4);
  }
  else
  {
    *(_QWORD *)&v12 = 0;
    return ListView_Get_Handler<LVITEM_32>(Buffer, a1, (__int64)a4);
  }
}

```

## disassembly

```asm
0x18000d1cc  mov     [rsp-8+arg_8], rbx
0x18000d1d1  mov     [rsp-8+arg_10], rdi
0x18000d1d6  push    rbp
0x18000d1d7  lea     rbp, [rsp-4Fh]
0x18000d1dc  sub     rsp, 90h
0x18000d1e3  mov     rax, cs:__security_cookie
0x18000d1ea  xor     rax, rsp
0x18000d1ed  mov     [rbp+4Fh+var_10], rax
0x18000d1f1  lea     rdx, [rbp+4Fh+dwProcessId]; lpdwProcessId
0x18000d1f5  mov     [rbp+4Fh+dwProcessId], 0
0x18000d1fc  mov     rdi, r9
0x18000d1ff  mov     rbx, rcx
0x18000d202  call    cs:__imp_GetWindowThreadProcessId
0x18000d208  test    eax, eax
0x18000d20a  jz      short loc_18000D284
0x18000d20c  call    cs:__imp_GetCurrentProcessId
0x18000d212  mov     rcx, rbx; HWND
0x18000d215  cmp     [rbp+4Fh+dwProcessId], eax
0x18000d218  jnz     short loc_18000D234
0x18000d21a  mov     r9, rdi; lParam
0x18000d21d  xor     r8d, r8d; wParam
0x18000d220  mov     edx, 104Bh; Msg
0x18000d225  call    cs:__imp_SendMessageW
0x18000d22b  test    rax, rax
0x18000d22e  jz      short loc_18000D284
0x18000d230  xor     eax, eax
0x18000d232  jmp     short loc_18000D289
0x18000d234  lea     rdx, [rbp+4Fh+var_4C]; int *
0x18000d238  mov     [rbp+4Fh+var_4C], 0
0x18000d23f  call    ?SameBitness@@YAJPEAUHWND__@@PEAH@Z; SameBitness(HWND__ *,int *)
0x18000d244  test    eax, eax
0x18000d246  js      short loc_18000D284
0x18000d248  xorps   xmm0, xmm0
0x18000d24b  mov     [rsp+90h+var_70], rdi; __int64
0x18000d250  xor     eax, eax
0x18000d252  mov     rdx, rbx; HWND
0x18000d255  movups  [rbp+4Fh+Buffer], xmm0
0x18000d259  movups  [rbp+4Fh+var_38], xmm0
0x18000d25d  cmp     [rbp+4Fh+var_4C], eax
0x18000d260  jz      short loc_18000D275
0x18000d262  lea     rcx, [rbp+4Fh+Buffer]; lpBuffer
0x18000d266  mov     [rbp+4Fh+var_18], rax
0x18000d26a  movups  [rbp+4Fh+var_28], xmm0
0x18000d26e  call    ??$ListView_Get_Handler@ULVITEM_64@@@@YAJAEAULVITEM_64@@PEAUHWND__@@I_KPEAUtagLVITEMW@@HI@Z; ListView_Get_Handler<LVITEM_64>(LVITEM_64 &,HWND__ *,uint,unsigned __int64,tagLVITEMW *,int,uint)
0x18000d273  jmp     short loc_18000D289
0x18000d275  lea     rcx, [rbp+4Fh+Buffer]; lpBuffer
0x18000d279  mov     qword ptr [rbp+4Fh+var_28], rax
0x18000d27d  call    ??$ListView_Get_Handler@ULVITEM_32@@@@YAJAEAULVITEM_32@@PEAUHWND__@@I_KPEAUtagLVITEMW@@HI@Z; ListView_Get_Handler<LVITEM_32>(LVITEM_32 &,HWND__ *,uint,unsigned __int64,tagLVITEMW *,int,uint)
0x18000d282  jmp     short loc_18000D289
0x18000d284  mov     eax, 80004005h
0x18000d289  mov     rcx, [rbp+4Fh+var_10]
0x18000d28d  xor     rcx, rsp; StackCookie
0x18000d290  call    __security_check_cookie
0x18000d295  lea     r11, [rsp+90h+var_s0]
0x18000d29d  mov     rbx, [r11+18h]
0x18000d2a1  mov     rdi, [r11+20h]
0x18000d2a5  mov     rsp, r11
0x18000d2a8  pop     rbp
0x18000d2a9  retn
```
