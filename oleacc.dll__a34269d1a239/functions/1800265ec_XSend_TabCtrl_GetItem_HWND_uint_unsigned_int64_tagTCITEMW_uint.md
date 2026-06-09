# XSend_TabCtrl_GetItem(HWND__ *,uint,unsigned __int64,tagTCITEMW *,uint)

- ea: `0x1800265ec`
- end: `0x1800266c6`
- name: `?XSend_TabCtrl_GetItem@@YAJPEAUHWND__@@I_KPEAUtagTCITEMW@@I@Z`
- size: `218`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, struct tagTCITEMW *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180041d58`
- `0x180042840`

## callees

- `0x18000c594`
- `0x18001e4c0`
- `0x180025744`
- `0x1800258b0`
- `0x1800265ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002662a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002662a`
- `USER32!GetWindowThreadProcessId` at `0x180026620`
- `USER32!GetWindowThreadProcessId` at `0x180026620`
- `USER32!SendMessageW` at `0x180026643`
- `USER32!SendMessageW` at `0x180026643`

## pseudocode

```c
__int64 __fastcall XSend_TabCtrl_GetItem(HWND a1, __int64 a2, WPARAM a3, struct tagTCITEMW *a4)
{
  __int64 v8; // r8
  DWORD dwProcessId; // [rsp+40h] [rbp-40h] BYREF
  int v10; // [rsp+44h] [rbp-3Ch] BYREF
  __m256i Buffer; // [rsp+48h] [rbp-38h] BYREF
  __int64 v12; // [rsp+68h] [rbp-18h]

  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(a1, &dwProcessId) )
    return 2147500037LL;
  if ( dwProcessId == GetCurrentProcessId() )
  {
    if ( SendMessageW(a1, 0x133Cu, a3, (LPARAM)a4) )
      return 0;
    return 2147500037LL;
  }
  v10 = 0;
  if ( (int)SameBitness(a1, &v10) < 0 )
    return 2147500037LL;
  *(_OWORD *)Buffer.m256i_i8 = 0;
  if ( v10 )
  {
    v12 = 0;
    *(_OWORD *)&Buffer.m256i_u64[2] = 0;
    return TabCtrl_Get_Handler<TCITEM_64>(&Buffer, a1, v8, a3, (__int64)a4);
  }
  else
  {
    *(_OWORD *)((char *)&Buffer.m256i_u64[1] + 4) = 0;
    return TabCtrl_Get_Handler<TCITEM_32>(Buffer.m256i_i32, a1, v8, a3, (__int64)a4);
  }
}

```

## disassembly

```asm
0x1800265ec  mov     [rsp-18h+arg_8], rbx
0x1800265f1  push    rbp
0x1800265f2  push    rsi
0x1800265f3  push    rdi
0x1800265f4  mov     rbp, rsp
0x1800265f7  sub     rsp, 80h
0x1800265fe  mov     rax, cs:__security_cookie
0x180026605  xor     rax, rsp
0x180026608  mov     [rbp+var_10], rax
0x18002660c  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180026610  mov     [rbp+dwProcessId], 0
0x180026617  mov     rsi, r9
0x18002661a  mov     rdi, r8
0x18002661d  mov     rbx, rcx
0x180026620  call    cs:__imp_GetWindowThreadProcessId
0x180026626  test    eax, eax
0x180026628  jz      short loc_1800266A2
0x18002662a  call    cs:__imp_GetCurrentProcessId
0x180026630  mov     rcx, rbx; HWND
0x180026633  cmp     [rbp+dwProcessId], eax
0x180026636  jnz     short loc_180026652
0x180026638  mov     r9, rsi; lParam
0x18002663b  mov     r8, rdi; wParam
0x18002663e  mov     edx, 133Ch; Msg
0x180026643  call    cs:__imp_SendMessageW
0x180026649  test    rax, rax
0x18002664c  jz      short loc_1800266A2
0x18002664e  xor     eax, eax
0x180026650  jmp     short loc_1800266A7
0x180026652  lea     rdx, [rbp+var_3C]; int *
0x180026656  mov     [rbp+var_3C], 0
0x18002665d  call    ?SameBitness@@YAJPEAUHWND__@@PEAH@Z; SameBitness(HWND__ *,int *)
0x180026662  test    eax, eax
0x180026664  js      short loc_1800266A2
0x180026666  cmp     [rbp+var_3C], 0
0x18002666a  xorps   xmm0, xmm0
0x18002666d  movups  [rbp+Buffer], xmm0
0x180026671  mov     [rsp+80h+var_60], rsi; __int64
0x180026676  mov     r9, rdi
0x180026679  mov     rdx, rbx; HWND
0x18002667c  jz      short loc_180026693
0x18002667e  xor     eax, eax
0x180026680  lea     rcx, [rbp+Buffer]; lpBuffer
0x180026684  mov     [rbp+var_18], rax
0x180026688  movups  [rbp+var_28], xmm0
0x18002668c  call    ??$TabCtrl_Get_Handler@UTCITEM_64@@@@YAJAEAUTCITEM_64@@PEAUHWND__@@I_KPEAUtagTCITEMW@@HI@Z; TabCtrl_Get_Handler<TCITEM_64>(TCITEM_64 &,HWND__ *,uint,unsigned __int64,tagTCITEMW *,int,uint)
0x180026691  jmp     short loc_1800266A7
0x180026693  lea     rcx, [rbp+Buffer]; lpBuffer
0x180026697  movups  [rbp+Buffer+0Ch], xmm0
0x18002669b  call    ??$TabCtrl_Get_Handler@UTCITEM_32@@@@YAJAEAUTCITEM_32@@PEAUHWND__@@I_KPEAUtagTCITEMW@@HI@Z; TabCtrl_Get_Handler<TCITEM_32>(TCITEM_32 &,HWND__ *,uint,unsigned __int64,tagTCITEMW *,int,uint)
0x1800266a0  jmp     short loc_1800266A7
0x1800266a2  mov     eax, 80004005h
0x1800266a7  mov     rcx, [rbp+var_10]
0x1800266ab  xor     rcx, rsp; StackCookie
0x1800266ae  call    __security_check_cookie
0x1800266b3  mov     rbx, [rsp+80h+arg_8]
0x1800266bb  add     rsp, 80h
0x1800266c2  pop     rdi
0x1800266c3  pop     rsi
0x1800266c4  pop     rbp
0x1800266c5  retn
```
