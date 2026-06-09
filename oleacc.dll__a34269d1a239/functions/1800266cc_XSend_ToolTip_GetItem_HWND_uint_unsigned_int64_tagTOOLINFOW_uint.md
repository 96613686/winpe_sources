# XSend_ToolTip_GetItem(HWND__ *,uint,unsigned __int64,tagTOOLINFOW *,uint)

- ea: `0x1800266cc`
- end: `0x1800267ba`
- name: `?XSend_ToolTip_GetItem@@YAJPEAUHWND__@@I_KPEAUtagTOOLINFOW@@I@Z`
- size: `238`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, struct tagTOOLINFOW *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180041d58`
- `0x180043420`
- `0x180043638`

## callees

- `0x18000c594`
- `0x18001e4c0`
- `0x180025c84`
- `0x180025d84`
- `0x1800266cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026710`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026710`
- `USER32!GetWindowThreadProcessId` at `0x180026702`
- `USER32!GetWindowThreadProcessId` at `0x180026702`
- `USER32!SendMessageW` at `0x18002672c`
- `USER32!SendMessageW` at `0x18002672c`

## pseudocode

```c
__int64 __fastcall XSend_ToolTip_GetItem(HWND a1, __int64 a2, __int64 a3, struct tagTOOLINFOW *a4)
{
  int v7; // r8d
  int v8; // r9d
  DWORD dwProcessId; // [rsp+40h] [rbp-1h] BYREF
  int v10; // [rsp+44h] [rbp+3h] BYREF
  _OWORD v11[3]; // [rsp+48h] [rbp+7h] BYREF
  __int64 v12; // [rsp+78h] [rbp+37h]

  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(a1, &dwProcessId) )
    return 2147500037LL;
  if ( dwProcessId == GetCurrentProcessId() )
  {
    SendMessageW(a1, 0x438u, 0xFFu, (LPARAM)a4);
    return 0;
  }
  v10 = 0;
  if ( (int)SameBitness(a1, &v10) < 0 )
    return 2147500037LL;
  memset(v11, 0, sizeof(v11));
  if ( !v10 )
    return ToolInfo_Get_Handler<TOOLINFO_32>((unsigned int)v11, (_DWORD)a1, v7, v8, (__int64)a4, 0);
  v12 = 0;
  return ToolInfo_Get_Handler<TOOLINFO_64>((unsigned int)v11, (_DWORD)a1, v7, v8, (__int64)a4, 0);
}

```

## disassembly

```asm
0x1800266cc  mov     [rsp-8+arg_8], rbx
0x1800266d1  mov     [rsp-8+arg_10], rdi
0x1800266d6  push    rbp
0x1800266d7  lea     rbp, [rsp-4Fh]
0x1800266dc  sub     rsp, 90h
0x1800266e3  mov     rax, cs:__security_cookie
0x1800266ea  xor     rax, rsp
0x1800266ed  mov     [rbp+4Fh+var_10], rax
0x1800266f1  lea     rdx, [rbp+4Fh+dwProcessId]; lpdwProcessId
0x1800266f5  mov     [rbp+4Fh+dwProcessId], 0
0x1800266fc  mov     rdi, r9
0x1800266ff  mov     rbx, rcx
0x180026702  call    cs:__imp_GetWindowThreadProcessId
0x180026708  test    eax, eax
0x18002670a  jz      loc_180026794
0x180026710  call    cs:__imp_GetCurrentProcessId
0x180026716  mov     rcx, rbx; HWND
0x180026719  cmp     [rbp+4Fh+dwProcessId], eax
0x18002671c  jnz     short loc_180026736
0x18002671e  mov     r9, rdi; lParam
0x180026721  mov     edx, 438h; Msg
0x180026726  mov     r8d, 0FFh; wParam
0x18002672c  call    cs:__imp_SendMessageW
0x180026732  xor     eax, eax
0x180026734  jmp     short loc_180026799
0x180026736  lea     rdx, [rbp+4Fh+var_4C]; int *
0x18002673a  mov     [rbp+4Fh+var_4C], 0
0x180026741  call    ?SameBitness@@YAJPEAUHWND__@@PEAH@Z; SameBitness(HWND__ *,int *)
0x180026746  test    eax, eax
0x180026748  js      short loc_180026794
0x18002674a  cmp     [rbp+4Fh+var_4C], 0
0x18002674e  xorps   xmm0, xmm0
0x180026751  movups  [rbp+4Fh+var_48], xmm0
0x180026755  mov     rdx, rbx
0x180026758  movups  [rbp+4Fh+var_38], xmm0
0x18002675c  movups  [rbp+4Fh+var_28], xmm0
0x180026760  jz      short loc_18002677C
0x180026762  xor     eax, eax
0x180026764  lea     rcx, [rbp+4Fh+var_48]
0x180026768  mov     [rsp+90h+var_68], eax
0x18002676c  mov     [rsp+90h+var_70], rdi
0x180026771  mov     [rbp+4Fh+var_18], rax
0x180026775  call    ??$ToolInfo_Get_Handler@UTOOLINFO_64@@@@YAJAEAUTOOLINFO_64@@PEAUHWND__@@I_KPEAUtagTOOLINFOW@@HI@Z; ToolInfo_Get_Handler<TOOLINFO_64>(TOOLINFO_64 &,HWND__ *,uint,unsigned __int64,tagTOOLINFOW *,int,uint)
0x18002677a  jmp     short loc_180026799
0x18002677c  mov     [rsp+90h+var_68], 0
0x180026784  lea     rcx, [rbp+4Fh+var_48]
0x180026788  mov     [rsp+90h+var_70], rdi
0x18002678d  call    ??$ToolInfo_Get_Handler@UTOOLINFO_32@@@@YAJAEAUTOOLINFO_32@@PEAUHWND__@@I_KPEAUtagTOOLINFOW@@HI@Z; ToolInfo_Get_Handler<TOOLINFO_32>(TOOLINFO_32 &,HWND__ *,uint,unsigned __int64,tagTOOLINFOW *,int,uint)
0x180026792  jmp     short loc_180026799
0x180026794  mov     eax, 80004005h
0x180026799  mov     rcx, [rbp+4Fh+var_10]
0x18002679d  xor     rcx, rsp; StackCookie
0x1800267a0  call    __security_check_cookie
0x1800267a5  lea     r11, [rsp+90h+var_s0]
0x1800267ad  mov     rbx, [r11+18h]
0x1800267b1  mov     rdi, [r11+20h]
0x1800267b5  mov     rsp, r11
0x1800267b8  pop     rbp
0x1800267b9  retn
```
