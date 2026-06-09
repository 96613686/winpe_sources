# XSend_ListView_V6_GetGroupInfo(HWND__ *,uint,unsigned __int64,LVGROUP_V6 *,uint)

- ea: `0x1800263e8`
- end: `0x1800264c3`
- name: `?XSend_ListView_V6_GetGroupInfo@@YAJPEAUHWND__@@I_KPEAULVGROUP_V6@@I@Z`
- size: `219`
- prototype: `__int64 __fastcall(HWND, UINT Msg, WPARAM wParam, struct LVGROUP_V6 *, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180030560`
- `0x180030bb0`
- `0x1800314f0`
- `0x180031a60`

## callees

- `0x18000c594`
- `0x18001e4c0`
- `0x1800251d8`
- `0x180025320`
- `0x1800263e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026429`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026429`
- `USER32!GetWindowThreadProcessId` at `0x18002641f`
- `USER32!GetWindowThreadProcessId` at `0x18002641f`
- `USER32!SendMessageW` at `0x18002643f`
- `USER32!SendMessageW` at `0x18002643f`

## pseudocode

```c
__int64 __fastcall XSend_ListView_V6_GetGroupInfo(HWND a1, UINT Msg, WPARAM wParam, struct LVGROUP_V6 *a4)
{
  unsigned int v9; // [rsp+28h] [rbp-39h]
  DWORD dwProcessId; // [rsp+40h] [rbp-21h] BYREF
  int v11; // [rsp+44h] [rbp-1Dh] BYREF
  _OWORD Buffer[2]; // [rsp+48h] [rbp-19h] BYREF
  __int128 v13; // [rsp+68h] [rbp+7h]
  __int64 v14; // [rsp+78h] [rbp+17h]

  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(a1, &dwProcessId) )
    return 2147500037LL;
  if ( dwProcessId == GetCurrentProcessId() )
  {
    if ( SendMessageW(a1, Msg, wParam, (LPARAM)a4) )
      return 0;
    return 2147500037LL;
  }
  v11 = 0;
  if ( (int)SameBitness(a1, &v11) < 0 )
    return 2147500037LL;
  memset(Buffer, 0, sizeof(Buffer));
  if ( v11 )
  {
    v14 = 0;
    v13 = 0;
    return ListView_V6_GetGroup_Handler<LVGROUP_V6_64>(Buffer, a1, Msg, wParam, (__int64)a4, v9);
  }
  else
  {
    *(_QWORD *)&v13 = 0;
    return ListView_V6_GetGroup_Handler<LVGROUP_V6_32>(Buffer, a1, Msg, wParam, (__int64)a4, v9);
  }
}

```

## disassembly

```asm
0x1800263e8  push    rbp
0x1800263ea  push    rbx
0x1800263eb  push    rsi
0x1800263ec  push    rdi
0x1800263ed  push    r14
0x1800263ef  lea     rbp, [rsp-2Fh]
0x1800263f4  sub     rsp, 90h
0x1800263fb  mov     rax, cs:__security_cookie
0x180026402  xor     rax, rsp
0x180026405  mov     [rbp+4Fh+var_30], rax
0x180026409  mov     edi, edx
0x18002640b  mov     [rbp+4Fh+dwProcessId], 0
0x180026412  lea     rdx, [rbp+4Fh+dwProcessId]; lpdwProcessId
0x180026416  mov     r14, r9
0x180026419  mov     rsi, r8
0x18002641c  mov     rbx, rcx
0x18002641f  call    cs:__imp_GetWindowThreadProcessId
0x180026425  test    eax, eax
0x180026427  jz      short loc_1800264A4
0x180026429  call    cs:__imp_GetCurrentProcessId
0x18002642f  mov     rcx, rbx; HWND
0x180026432  cmp     [rbp+4Fh+dwProcessId], eax
0x180026435  jnz     short loc_18002644E
0x180026437  mov     r9, r14; lParam
0x18002643a  mov     r8, rsi; wParam
0x18002643d  mov     edx, edi; Msg
0x18002643f  call    cs:__imp_SendMessageW
0x180026445  test    rax, rax
0x180026448  jz      short loc_1800264A4
0x18002644a  xor     eax, eax
0x18002644c  jmp     short loc_1800264A9
0x18002644e  lea     rdx, [rbp+4Fh+var_6C]; int *
0x180026452  mov     [rbp+4Fh+var_6C], 0
0x180026459  call    ?SameBitness@@YAJPEAUHWND__@@PEAH@Z; SameBitness(HWND__ *,int *)
0x18002645e  test    eax, eax
0x180026460  js      short loc_1800264A4
0x180026462  xorps   xmm0, xmm0
0x180026465  mov     [rsp+0B0h+var_90], r14; __int64
0x18002646a  xor     eax, eax
0x18002646c  mov     r9, rsi; wParam
0x18002646f  mov     r8d, edi; Msg
0x180026472  mov     rdx, rbx; HWND
0x180026475  movups  [rbp+4Fh+Buffer], xmm0
0x180026479  movups  [rbp+4Fh+var_58], xmm0
0x18002647d  cmp     [rbp+4Fh+var_6C], eax
0x180026480  jz      short loc_180026495
0x180026482  lea     rcx, [rbp+4Fh+Buffer]; lpBuffer
0x180026486  mov     [rbp+4Fh+var_38], rax
0x18002648a  movups  [rbp+4Fh+var_48], xmm0
0x18002648e  call    ??$ListView_V6_GetGroup_Handler@ULVGROUP_V6_64@@@@YAJAEAULVGROUP_V6_64@@PEAUHWND__@@I_KPEAULVGROUP_V6@@HI@Z; ListView_V6_GetGroup_Handler<LVGROUP_V6_64>(LVGROUP_V6_64 &,HWND__ *,uint,unsigned __int64,LVGROUP_V6 *,int,uint)
0x180026493  jmp     short loc_1800264A9
0x180026495  lea     rcx, [rbp+4Fh+Buffer]; lpBuffer
0x180026499  mov     qword ptr [rbp+4Fh+var_48], rax
0x18002649d  call    ??$ListView_V6_GetGroup_Handler@ULVGROUP_V6_32@@@@YAJAEAULVGROUP_V6_32@@PEAUHWND__@@I_KPEAULVGROUP_V6@@HI@Z; ListView_V6_GetGroup_Handler<LVGROUP_V6_32>(LVGROUP_V6_32 &,HWND__ *,uint,unsigned __int64,LVGROUP_V6 *,int,uint)
0x1800264a2  jmp     short loc_1800264A9
0x1800264a4  mov     eax, 80004005h
0x1800264a9  mov     rcx, [rbp+4Fh+var_30]
0x1800264ad  xor     rcx, rsp; StackCookie
0x1800264b0  call    __security_check_cookie
0x1800264b5  add     rsp, 90h
0x1800264bc  pop     r14
0x1800264be  pop     rdi
0x1800264bf  pop     rsi
0x1800264c0  pop     rbx
0x1800264c1  pop     rbp
0x1800264c2  retn
```
