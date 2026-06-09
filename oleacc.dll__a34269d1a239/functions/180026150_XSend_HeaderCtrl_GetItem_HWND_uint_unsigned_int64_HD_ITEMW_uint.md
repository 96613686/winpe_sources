# XSend_HeaderCtrl_GetItem(HWND__ *,uint,unsigned __int64,_HD_ITEMW *,uint)

- ea: `0x180026150`
- end: `0x180026229`
- name: `?XSend_HeaderCtrl_GetItem@@YAJPEAUHWND__@@I_KPEAU_HD_ITEMW@@I@Z`
- size: `217`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, struct _HD_ITEMW *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002cc70`

## callees

- `0x18000c594`
- `0x18001e4c0`
- `0x18002473c`
- `0x1800248a0`
- `0x180026150`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002618e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002618e`
- `USER32!GetWindowThreadProcessId` at `0x180026184`
- `USER32!GetWindowThreadProcessId` at `0x180026184`
- `USER32!SendMessageW` at `0x1800261a7`
- `USER32!SendMessageW` at `0x1800261a7`

## pseudocode

```c
__int64 __fastcall XSend_HeaderCtrl_GetItem(HWND a1, __int64 a2, WPARAM a3, struct _HD_ITEMW *a4)
{
  __int64 v8; // r8
  DWORD dwProcessId; // [rsp+40h] [rbp-40h] BYREF
  int v10; // [rsp+44h] [rbp-3Ch] BYREF
  _OWORD Buffer[2]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v12; // [rsp+68h] [rbp-18h]

  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(a1, &dwProcessId) )
    return 2147500037LL;
  if ( dwProcessId == GetCurrentProcessId() )
  {
    if ( SendMessageW(a1, 0x120Bu, a3, (LPARAM)a4) )
      return 0;
    return 2147500037LL;
  }
  v10 = 0;
  if ( (int)SameBitness(a1, &v10) < 0 )
    return 2147500037LL;
  memset(Buffer, 0, sizeof(Buffer));
  if ( v10 )
  {
    v12 = 0;
    return HeaderCtrl_Get_Handler<HDITEM_64>(Buffer, a1, v8, a3, (__int64)a4);
  }
  else
  {
    LODWORD(v12) = 0;
    return HeaderCtrl_Get_Handler<HDITEM_32>((int *)Buffer, a1, v8, a3, (__int64)a4);
  }
}

```

## disassembly

```asm
0x180026150  mov     [rsp-18h+arg_8], rbx
0x180026155  push    rbp
0x180026156  push    rsi
0x180026157  push    rdi
0x180026158  mov     rbp, rsp
0x18002615b  sub     rsp, 80h
0x180026162  mov     rax, cs:__security_cookie
0x180026169  xor     rax, rsp
0x18002616c  mov     [rbp+var_8], rax
0x180026170  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180026174  mov     [rbp+dwProcessId], 0
0x18002617b  mov     rsi, r9
0x18002617e  mov     rdi, r8
0x180026181  mov     rbx, rcx
0x180026184  call    cs:__imp_GetWindowThreadProcessId
0x18002618a  test    eax, eax
0x18002618c  jz      short loc_180026205
0x18002618e  call    cs:__imp_GetCurrentProcessId
0x180026194  mov     rcx, rbx; HWND
0x180026197  cmp     [rbp+dwProcessId], eax
0x18002619a  jnz     short loc_1800261B6
0x18002619c  mov     r9, rsi; lParam
0x18002619f  mov     r8, rdi; wParam
0x1800261a2  mov     edx, 120Bh; Msg
0x1800261a7  call    cs:__imp_SendMessageW
0x1800261ad  test    rax, rax
0x1800261b0  jz      short loc_180026205
0x1800261b2  xor     eax, eax
0x1800261b4  jmp     short loc_18002620A
0x1800261b6  lea     rdx, [rbp+var_3C]; int *
0x1800261ba  mov     [rbp+var_3C], 0
0x1800261c1  call    ?SameBitness@@YAJPEAUHWND__@@PEAH@Z; SameBitness(HWND__ *,int *)
0x1800261c6  test    eax, eax
0x1800261c8  js      short loc_180026205
0x1800261ca  cmp     [rbp+var_3C], 0
0x1800261ce  xorps   xmm0, xmm0
0x1800261d1  movups  [rbp+Buffer], xmm0
0x1800261d5  mov     [rsp+80h+var_60], rsi; __int64
0x1800261da  mov     r9, rdi
0x1800261dd  movups  [rbp+var_28], xmm0
0x1800261e1  mov     rdx, rbx; HWND
0x1800261e4  jz      short loc_1800261F5
0x1800261e6  lea     rcx, [rbp+Buffer]; lpBuffer
0x1800261ea  movups  [rbp+var_18], xmm0
0x1800261ee  call    ??$HeaderCtrl_Get_Handler@UHDITEM_64@@@@YAJAEAUHDITEM_64@@PEAUHWND__@@I_KPEAU_HD_ITEMW@@HI@Z; HeaderCtrl_Get_Handler<HDITEM_64>(HDITEM_64 &,HWND__ *,uint,unsigned __int64,_HD_ITEMW *,int,uint)
0x1800261f3  jmp     short loc_18002620A
0x1800261f5  xor     eax, eax
0x1800261f7  lea     rcx, [rbp+Buffer]; lpBuffer
0x1800261fb  mov     dword ptr [rbp+var_18], eax
0x1800261fe  call    ??$HeaderCtrl_Get_Handler@UHDITEM_32@@@@YAJAEAUHDITEM_32@@PEAUHWND__@@I_KPEAU_HD_ITEMW@@HI@Z; HeaderCtrl_Get_Handler<HDITEM_32>(HDITEM_32 &,HWND__ *,uint,unsigned __int64,_HD_ITEMW *,int,uint)
0x180026203  jmp     short loc_18002620A
0x180026205  mov     eax, 80004005h
0x18002620a  mov     rcx, [rbp+var_8]
0x18002620e  xor     rcx, rsp; StackCookie
0x180026211  call    __security_check_cookie
0x180026216  mov     rbx, [rsp+80h+arg_8]
0x18002621e  add     rsp, 80h
0x180026225  pop     rdi
0x180026226  pop     rsi
0x180026227  pop     rbp
0x180026228  retn
```
