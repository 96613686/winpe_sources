# XSend_ToolTip_GetTitle(HWND__ *,uint,unsigned __int64,_TTGETTITLE *,uint)

- ea: `0x1800267c0`
- end: `0x18002688b`
- name: `?XSend_ToolTip_GetTitle@@YAJPEAUHWND__@@I_KPEAU_TTGETTITLE@@I@Z`
- size: `203`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, struct _TTGETTITLE *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180044750`

## callees

- `0x18000c594`
- `0x18001e4c0`
- `0x180025a1c`
- `0x180025b50`
- `0x1800267c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800267f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800267f6`
- `USER32!GetWindowThreadProcessId` at `0x1800267ec`
- `USER32!GetWindowThreadProcessId` at `0x1800267ec`
- `USER32!SendMessageW` at `0x180026810`
- `USER32!SendMessageW` at `0x180026810`

## pseudocode

```c
__int64 __fastcall XSend_ToolTip_GetTitle(HWND hWnd, __int64 a2, __int64 a3, struct _TTGETTITLE *a4)
{
  __int64 v7; // r8
  __int64 v8; // r9
  DWORD dwProcessId; // [rsp+40h] [rbp-38h] BYREF
  int v10; // [rsp+44h] [rbp-34h] BYREF
  __int128 Buffer; // [rsp+48h] [rbp-30h] BYREF
  __int64 v12; // [rsp+58h] [rbp-20h]

  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(hWnd, &dwProcessId) )
    return 2147500037LL;
  if ( dwProcessId == GetCurrentProcessId() )
  {
    if ( SendMessageW(hWnd, 0x423u, 0, (LPARAM)a4) )
      return 0;
    return 2147500037LL;
  }
  v10 = 0;
  if ( (int)SameBitness(hWnd, &v10) < 0 )
    return 2147500037LL;
  Buffer = 0;
  if ( !v10 )
    return ToolInfo_GetTitle_Handler<TTGETTITLE_32>((unsigned int *)&Buffer, hWnd, v7, v8, (__int64)a4);
  v12 = 0;
  return ToolInfo_GetTitle_Handler<TTGETTITLE_64>(&Buffer, hWnd, v7, v8, (__int64)a4);
}

```

## disassembly

```asm
0x1800267c0  mov     [rsp+arg_8], rbx
0x1800267c5  push    rdi
0x1800267c6  sub     rsp, 70h
0x1800267ca  mov     rax, cs:__security_cookie
0x1800267d1  xor     rax, rsp
0x1800267d4  mov     [rsp+78h+var_18], rax
0x1800267d9  lea     rdx, [rsp+78h+dwProcessId]; lpdwProcessId
0x1800267de  mov     [rsp+78h+dwProcessId], 0
0x1800267e6  mov     rdi, r9
0x1800267e9  mov     rbx, rcx
0x1800267ec  call    cs:__imp_GetWindowThreadProcessId
0x1800267f2  test    eax, eax
0x1800267f4  jz      short loc_18002686B
0x1800267f6  call    cs:__imp_GetCurrentProcessId
0x1800267fc  mov     rcx, rbx; HWND
0x1800267ff  cmp     [rsp+78h+dwProcessId], eax
0x180026803  jnz     short loc_18002681F
0x180026805  mov     r9, rdi; lParam
0x180026808  xor     r8d, r8d; wParam
0x18002680b  mov     edx, 423h; Msg
0x180026810  call    cs:__imp_SendMessageW
0x180026816  test    rax, rax
0x180026819  jz      short loc_18002686B
0x18002681b  xor     eax, eax
0x18002681d  jmp     short loc_180026870
0x18002681f  lea     rdx, [rsp+78h+var_34]; int *
0x180026824  mov     [rsp+78h+var_34], 0
0x18002682c  call    ?SameBitness@@YAJPEAUHWND__@@PEAH@Z; SameBitness(HWND__ *,int *)
0x180026831  test    eax, eax
0x180026833  js      short loc_18002686B
0x180026835  cmp     [rsp+78h+var_34], 0
0x18002683a  xorps   xmm0, xmm0
0x18002683d  movups  [rsp+78h+Buffer], xmm0
0x180026842  mov     [rsp+78h+var_58], rdi; __int64
0x180026847  mov     rdx, rbx; hWnd
0x18002684a  jz      short loc_18002685F
0x18002684c  xor     eax, eax
0x18002684e  lea     rcx, [rsp+78h+Buffer]; lpBuffer
0x180026853  mov     [rsp+78h+var_20], rax
0x180026858  call    ??$ToolInfo_GetTitle_Handler@UTTGETTITLE_64@@@@YAJAEAUTTGETTITLE_64@@PEAUHWND__@@I_KPEAU_TTGETTITLE@@HI@Z; ToolInfo_GetTitle_Handler<TTGETTITLE_64>(TTGETTITLE_64 &,HWND__ *,uint,unsigned __int64,_TTGETTITLE *,int,uint)
0x18002685d  jmp     short loc_180026870
0x18002685f  lea     rcx, [rsp+78h+Buffer]; lpBuffer
0x180026864  call    ??$ToolInfo_GetTitle_Handler@UTTGETTITLE_32@@@@YAJAEAUTTGETTITLE_32@@PEAUHWND__@@I_KPEAU_TTGETTITLE@@HI@Z; ToolInfo_GetTitle_Handler<TTGETTITLE_32>(TTGETTITLE_32 &,HWND__ *,uint,unsigned __int64,_TTGETTITLE *,int,uint)
0x180026869  jmp     short loc_180026870
0x18002686b  mov     eax, 80004005h
0x180026870  mov     rcx, [rsp+78h+var_18]
0x180026875  xor     rcx, rsp; StackCookie
0x180026878  call    __security_check_cookie
0x18002687d  mov     rbx, [rsp+78h+arg_8]
0x180026885  add     rsp, 70h
0x180026889  pop     rdi
0x18002688a  retn
```
