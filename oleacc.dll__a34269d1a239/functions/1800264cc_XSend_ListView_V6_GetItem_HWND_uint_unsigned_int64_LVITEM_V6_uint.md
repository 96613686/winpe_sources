# XSend_ListView_V6_GetItem(HWND__ *,uint,unsigned __int64,LVITEM_V6 *,uint)

- ea: `0x1800264cc`
- end: `0x1800265e4`
- name: `?XSend_ListView_V6_GetItem@@YAJPEAUHWND__@@I_KPEAULVITEM_V6@@I@Z`
- size: `280`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, struct LVITEM_V6 *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002f4a8`
- `0x180030560`

## callees

- `0x18000c594`
- `0x18001e4c0`
- `0x18001efc4`
- `0x18002546c`
- `0x1800255d8`
- `0x1800264cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026521`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026521`
- `USER32!GetWindowThreadProcessId` at `0x180026505`
- `USER32!GetWindowThreadProcessId` at `0x180026505`
- `USER32!SendMessageW` at `0x18002653a`
- `USER32!SendMessageW` at `0x18002653a`

## pseudocode

```c
__int64 __fastcall XSend_ListView_V6_GetItem(HWND hWnd, __int64 a2, __int64 a3, struct LVITEM_V6 *a4)
{
  __int64 v6; // rsi
  DWORD dwProcessId; // [rsp+40h] [rbp-31h] BYREF
  int v9[3]; // [rsp+44h] [rbp-2Dh] BYREF
  _OWORD Buffer[3]; // [rsp+50h] [rbp-21h] BYREF
  int v11; // [rsp+80h] [rbp+Fh]

  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(hWnd, &dwProcessId) )
    return 2147500037LL;
  v6 = *((_QWORD *)a4 + 8);
  if ( dwProcessId == GetCurrentProcessId() )
  {
    if ( SendMessageW(hWnd, 0x104Bu, 0, (LPARAM)a4) || !v6 )
      return 0;
    return 2147500037LL;
  }
  v9[0] = 0;
  if ( (int)SameBitness(hWnd, v9) < 0 )
    return 2147500037LL;
  if ( v9[0] )
  {
    memset_0(Buffer, 0, 0x48u);
    return ListView_V6_Get_Handler<LVITEM_V6_64>(Buffer, hWnd, (__int64)a4, v6 != 0);
  }
  else
  {
    v11 = 0;
    memset(Buffer, 0, sizeof(Buffer));
    return ListView_V6_Get_Handler<LVITEM_V6_32>(Buffer, hWnd, (__int64)a4, v6 != 0);
  }
}

```

## disassembly

```asm
0x1800264cc  mov     [rsp-8+arg_8], rbx
0x1800264d1  mov     [rsp-8+arg_10], rsi
0x1800264d6  push    rbp
0x1800264d7  push    rdi
0x1800264d8  push    r14
0x1800264da  lea     rbp, [rsp-3Fh]
0x1800264df  sub     rsp, 0B0h
0x1800264e6  mov     rax, cs:__security_cookie
0x1800264ed  xor     rax, rsp
0x1800264f0  mov     [rbp+4Fh+var_20], rax
0x1800264f4  lea     rdx, [rbp+4Fh+dwProcessId]; lpdwProcessId
0x1800264f8  mov     [rbp+4Fh+dwProcessId], 0
0x1800264ff  mov     rdi, r9
0x180026502  mov     rbx, rcx
0x180026505  call    cs:__imp_GetWindowThreadProcessId
0x18002650b  test    eax, eax
0x18002650d  jz      loc_1800265BB
0x180026513  mov     rsi, [rdi+40h]
0x180026517  xor     r14d, r14d
0x18002651a  test    rsi, rsi
0x18002651d  setnz   r14b
0x180026521  call    cs:__imp_GetCurrentProcessId
0x180026527  mov     rcx, rbx; HWND
0x18002652a  cmp     [rbp+4Fh+dwProcessId], eax
0x18002652d  jnz     short loc_18002654E
0x18002652f  mov     r9, rdi; lParam
0x180026532  xor     r8d, r8d; wParam
0x180026535  mov     edx, 104Bh; Msg
0x18002653a  call    cs:__imp_SendMessageW
0x180026540  test    rax, rax
0x180026543  jnz     short loc_18002654A
0x180026545  test    rsi, rsi
0x180026548  jnz     short loc_1800265BB
0x18002654a  xor     eax, eax
0x18002654c  jmp     short loc_1800265C0
0x18002654e  lea     rdx, [rbp+4Fh+var_7C]; int *
0x180026552  mov     [rbp+4Fh+var_7C], 0
0x180026559  call    ?SameBitness@@YAJPEAUHWND__@@PEAH@Z; SameBitness(HWND__ *,int *)
0x18002655e  test    eax, eax
0x180026560  js      short loc_1800265BB
0x180026562  cmp     [rbp+4Fh+var_7C], 0
0x180026566  jz      short loc_18002658F
0x180026568  xor     edx, edx; Val
0x18002656a  lea     rcx, [rbp+4Fh+Buffer]; void *
0x18002656e  lea     r8d, [rdx+48h]; Size
0x180026572  call    memset_0
0x180026577  mov     rdx, rbx; hWnd
0x18002657a  mov     [rsp+0C0h+var_98], r14d; int
0x18002657f  lea     rcx, [rbp+4Fh+Buffer]; lpBuffer
0x180026583  mov     [rsp+0C0h+var_A0], rdi; __int64
0x180026588  call    ??$ListView_V6_Get_Handler@ULVITEM_V6_64@@@@YAJAEAULVITEM_V6_64@@PEAUHWND__@@I_KPEAULVITEM_V6@@HI@Z; ListView_V6_Get_Handler<LVITEM_V6_64>(LVITEM_V6_64 &,HWND__ *,uint,unsigned __int64,LVITEM_V6 *,int,uint)
0x18002658d  jmp     short loc_1800265C0
0x18002658f  xorps   xmm0, xmm0
0x180026592  mov     [rsp+0C0h+var_98], r14d; int
0x180026597  xor     eax, eax
0x180026599  mov     [rsp+0C0h+var_A0], rdi; __int64
0x18002659e  mov     rdx, rbx; hWnd
0x1800265a1  mov     [rbp+4Fh+var_40], eax
0x1800265a4  lea     rcx, [rbp+4Fh+Buffer]; lpBuffer
0x1800265a8  movups  [rbp+4Fh+Buffer], xmm0
0x1800265ac  movups  [rbp+4Fh+var_60], xmm0
0x1800265b0  movups  [rbp+4Fh+var_50], xmm0
0x1800265b4  call    ??$ListView_V6_Get_Handler@ULVITEM_V6_32@@@@YAJAEAULVITEM_V6_32@@PEAUHWND__@@I_KPEAULVITEM_V6@@HI@Z; ListView_V6_Get_Handler<LVITEM_V6_32>(LVITEM_V6_32 &,HWND__ *,uint,unsigned __int64,LVITEM_V6 *,int,uint)
0x1800265b9  jmp     short loc_1800265C0
0x1800265bb  mov     eax, 80004005h
0x1800265c0  mov     rcx, [rbp+4Fh+var_20]
0x1800265c4  xor     rcx, rsp; StackCookie
0x1800265c7  call    __security_check_cookie
0x1800265cc  lea     r11, [rsp+0C0h+var_10]
0x1800265d4  mov     rbx, [r11+28h]
0x1800265d8  mov     rsi, [r11+30h]
0x1800265dc  mov     rsp, r11
0x1800265df  pop     r14
0x1800265e1  pop     rdi
0x1800265e2  pop     rbp
0x1800265e3  retn
```
