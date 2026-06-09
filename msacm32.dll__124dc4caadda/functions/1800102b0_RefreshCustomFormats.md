# RefreshCustomFormats

- ea: `0x1800102b0`
- end: `0x18001053f`
- name: `RefreshCustomFormats`
- size: `655`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dff8`
- `0x18000f330`
- `0x180011018`
- `0x1800115f0`

## callees

- `0x180001940`
- `0x18000a250`
- `0x1800102b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800104e3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800104e3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180010451`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180010451`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180010342`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180010342`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001038b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001039d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010436`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010448`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001038b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001039d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010436`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180010448`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180010394`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001043f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180010394`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001043f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x1800103ae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x1800103ae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001034b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800103b7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001034b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800103b7`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800102e4`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800102f9`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800103e3`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010402`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010417`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18001047e`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18001049d`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800104b2`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800104fd`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010512`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010526`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800102e4`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800102f9`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800103e3`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010402`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010417`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18001047e`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18001049d`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800104b2`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800104fd`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010512`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180010526`

## pseudocode

```c
char __fastcall RefreshCustomFormats(__int64 a1, int a2)
{
  char result; // al
  __int64 v4; // rcx
  unsigned int v5; // ebx
  HGLOBAL v6; // rax
  const void *v7; // r14
  _QWORD *i; // rsi
  _WORD *v9; // rax
  unsigned int v10; // ebp
  HGLOBAL v11; // rax
  HGLOBAL v12; // rax
  HGLOBAL v13; // rax
  const void *v14; // rax
  int v15; // eax
  HGLOBAL v16; // rax
  HGLOBAL v17; // rax
  _QWORD *j; // rbx
  int v19; // eax
  int v20; // eax
  SIZE_T dwBytes; // [rsp+48h] [rbp+10h] BYREF

  LODWORD(dwBytes) = a2;
  result = IsSendMessageWPresent();
  if ( result )
  {
    SendMessageW(*(HWND *)(a1 + 56), 0xBu, 0, 0);
    SendMessageW(*(HWND *)(a1 + 56), 0x14Bu, 0, 0);
    if ( *(_DWORD *)a1 )
    {
      if ( *(_DWORD *)a1 == 1 )
      {
        v4 = *(_QWORD *)(a1 + 264);
        LODWORD(dwBytes) = 0;
        if ( (unsigned int)IMetricsMaxSizeFormat(v4, 0, &dwBytes) )
          return SendMessageW(*(HWND *)(a1 + 56), 0xBu, 1u, 0);
        v5 = dwBytes;
        v6 = GlobalAlloc(0x42u, (unsigned int)dwBytes);
        v7 = GlobalLock(v6);
        if ( !v7 )
          return SendMessageW(*(HWND *)(a1 + 56), 0xBu, 1u, 0);
        for ( i = *(_QWORD **)(a1 + 136); i; i = (_QWORD *)*i )
        {
          v9 = (_WORD *)i[3];
          if ( *v9 == 1 )
            v10 = 16;
          else
            v10 = (unsigned __int16)v9[8] + 18;
          if ( v5 < v10 )
          {
            v11 = GlobalHandle(v7);
            GlobalUnlock(v11);
            v12 = GlobalHandle(v7);
            v13 = GlobalReAlloc(v12, v10, 0x42u);
            v14 = GlobalLock(v13);
            if ( !v14 )
              break;
            v7 = v14;
            v5 = v10;
          }
          if ( !*(_DWORD *)(a1 + 184) || SendMessageW(*(HWND *)(a1 + 16), 0x8000u, 2u, i[3]) )
          {
            v15 = SendMessageW(*(HWND *)(a1 + 56), 0x143u, 0, i[2] + 2LL);
            SendMessageW(*(HWND *)(a1 + 56), 0x151u, v15, (LPARAM)i);
          }
        }
        v16 = GlobalHandle(v7);
        GlobalUnlock(v16);
        v17 = GlobalHandle(v7);
        GlobalFree(v17);
      }
    }
    else
    {
      for ( j = *(_QWORD **)(a1 + 136); j; j = (_QWORD *)*j )
      {
        if ( !*(_DWORD *)(a1 + 184) || SendMessageW(*(HWND *)(a1 + 16), 0x8000u, 2u, j[3]) )
        {
          v19 = SendMessageW(*(HWND *)(a1 + 56), 0x143u, 0, j[2] + 2LL);
          SendMessageW(*(HWND *)(a1 + 56), 0x151u, v19, (LPARAM)j);
        }
      }
    }
    LoadStringW(
      *(HINSTANCE *)(*(_QWORD *)(a1 + 264) + 88LL),
      0x97u,
      (LPWSTR)(*(_QWORD *)(a1 + 120) + 2LL),
      ((unsigned __int64)**(unsigned __int16 **)(a1 + 120) - 2) >> 1);
    v20 = SendMessageW(*(HWND *)(a1 + 56), 0x14Au, 0, *(_QWORD *)(a1 + 120) + 2LL);
    SendMessageW(*(HWND *)(a1 + 56), 0x151u, v20, 0);
    return SendMessageW(*(HWND *)(a1 + 56), 0xBu, 1u, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1800102b0  mov     [rsp+arg_0], rbx
0x1800102b5  mov     [rsp+arg_10], rbp
0x1800102ba  mov     dword ptr [rsp+dwBytes], edx
0x1800102be  push    rsi
0x1800102bf  push    rdi
0x1800102c0  push    r14
0x1800102c2  sub     rsp, 20h
0x1800102c6  mov     rdi, rcx
0x1800102c9  call    IsSendMessageWPresent
0x1800102ce  test    al, al
0x1800102d0  jz      loc_18001052C
0x1800102d6  mov     rcx, [rdi+38h]; hWnd
0x1800102da  xor     r9d, r9d; lParam
0x1800102dd  xor     r8d, r8d; wParam
0x1800102e0  lea     edx, [r9+0Bh]; Msg
0x1800102e4  call    cs:__imp_SendMessageW
0x1800102ea  mov     rcx, [rdi+38h]; hWnd
0x1800102ee  xor     r9d, r9d; lParam
0x1800102f1  xor     r8d, r8d; wParam
0x1800102f4  mov     edx, 14Bh; Msg
0x1800102f9  call    cs:__imp_SendMessageW
0x1800102ff  mov     ecx, [rdi]
0x180010301  mov     ebp, 1
0x180010306  test    ecx, ecx
0x180010308  jz      loc_180010459
0x18001030e  cmp     ecx, ebp
0x180010310  jnz     loc_1800104C0
0x180010316  mov     rcx, [rdi+108h]
0x18001031d  lea     r8, [rsp+38h+dwBytes]
0x180010322  xor     edx, edx
0x180010324  mov     dword ptr [rsp+38h+dwBytes], 0
0x18001032c  call    IMetricsMaxSizeFormat
0x180010331  test    eax, eax
0x180010333  jnz     loc_180010518
0x180010339  mov     ebx, dword ptr [rsp+38h+dwBytes]
0x18001033d  lea     ecx, [rbp+41h]; uFlags
0x180010340  mov     edx, ebx; dwBytes
0x180010342  call    cs:__imp_GlobalAlloc
0x180010348  mov     rcx, rax; hMem
0x18001034b  call    cs:__imp_GlobalLock
0x180010351  mov     r14, rax
0x180010354  test    rax, rax
0x180010357  jz      loc_180010518
0x18001035d  mov     rsi, [rdi+88h]
0x180010364  test    rsi, rsi
0x180010367  jz      loc_180010433
0x18001036d  mov     rax, [rsi+18h]
0x180010371  cmp     bp, [rax]
0x180010374  jnz     short loc_18001037D
0x180010376  mov     ebp, 10h
0x18001037b  jmp     short loc_180010384
0x18001037d  movzx   ebp, word ptr [rax+10h]
0x180010381  add     ebp, 12h
0x180010384  cmp     ebx, ebp
0x180010386  jnb     short loc_1800103C7
0x180010388  mov     rcx, r14; pMem
0x18001038b  call    cs:__imp_GlobalHandle
0x180010391  mov     rcx, rax; hMem
0x180010394  call    cs:__imp_GlobalUnlock
0x18001039a  mov     rcx, r14; pMem
0x18001039d  call    cs:__imp_GlobalHandle
0x1800103a3  mov     r8d, 42h ; 'B'; uFlags
0x1800103a9  mov     edx, ebp; dwBytes
0x1800103ab  mov     rcx, rax; hMem
0x1800103ae  call    cs:__imp_GlobalReAlloc
0x1800103b4  mov     rcx, rax; hMem
0x1800103b7  call    cs:__imp_GlobalLock
0x1800103bd  test    rax, rax
0x1800103c0  jz      short loc_18001042E
0x1800103c2  mov     r14, rax
0x1800103c5  mov     ebx, ebp
0x1800103c7  cmp     dword ptr [rdi+0B8h], 0
0x1800103ce  jz      short loc_1800103EE
0x1800103d0  mov     r9, [rsi+18h]; lParam
0x1800103d4  mov     edx, 8000h; Msg
0x1800103d9  mov     rcx, [rdi+10h]; hWnd
0x1800103dd  mov     r8d, 2; wParam
0x1800103e3  call    cs:__imp_SendMessageW
0x1800103e9  test    rax, rax
0x1800103ec  jz      short loc_18001041D
0x1800103ee  mov     r9, [rsi+10h]
0x1800103f2  xor     r8d, r8d; wParam
0x1800103f5  mov     rcx, [rdi+38h]; hWnd
0x1800103f9  add     r9, 2; lParam
0x1800103fd  mov     edx, 143h; Msg
0x180010402  call    cs:__imp_SendMessageW
0x180010408  mov     rcx, [rdi+38h]; hWnd
0x18001040c  mov     r9, rsi; lParam
0x18001040f  movsxd  r8, eax; wParam
0x180010412  mov     edx, 151h; Msg
0x180010417  call    cs:__imp_SendMessageW
0x18001041d  mov     rsi, [rsi]
0x180010420  mov     ebp, 1
0x180010425  test    rsi, rsi
0x180010428  jnz     loc_18001036D
0x18001042e  mov     ebp, 1
0x180010433  mov     rcx, r14; pMem
0x180010436  call    cs:__imp_GlobalHandle
0x18001043c  mov     rcx, rax; hMem
0x18001043f  call    cs:__imp_GlobalUnlock
0x180010445  mov     rcx, r14; pMem
0x180010448  call    cs:__imp_GlobalHandle
0x18001044e  mov     rcx, rax; hMem
0x180010451  call    cs:__imp_GlobalFree
0x180010457  jmp     short loc_1800104C0
0x180010459  mov     rbx, [rdi+88h]
0x180010460  jmp     short loc_1800104BB
0x180010462  cmp     dword ptr [rdi+0B8h], 0
0x180010469  jz      short loc_180010489
0x18001046b  mov     r9, [rbx+18h]; lParam
0x18001046f  mov     edx, 8000h; Msg
0x180010474  mov     rcx, [rdi+10h]; hWnd
0x180010478  mov     r8d, 2; wParam
0x18001047e  call    cs:__imp_SendMessageW
0x180010484  test    rax, rax
0x180010487  jz      short loc_1800104B8
0x180010489  mov     r9, [rbx+10h]
0x18001048d  xor     r8d, r8d; wParam
0x180010490  mov     rcx, [rdi+38h]; hWnd
0x180010494  add     r9, 2; lParam
0x180010498  mov     edx, 143h; Msg
0x18001049d  call    cs:__imp_SendMessageW
0x1800104a3  mov     rcx, [rdi+38h]; hWnd
0x1800104a7  mov     r9, rbx; lParam
0x1800104aa  movsxd  r8, eax; wParam
0x1800104ad  mov     edx, 151h; Msg
0x1800104b2  call    cs:__imp_SendMessageW
0x1800104b8  mov     rbx, [rbx]
0x1800104bb  test    rbx, rbx
0x1800104be  jnz     short loc_180010462
0x1800104c0  mov     r8, [rdi+78h]
0x1800104c4  mov     edx, 97h; uID
0x1800104c9  mov     rcx, [rdi+108h]
0x1800104d0  movzx   r9d, word ptr [r8]
0x1800104d4  add     r8, 2; lpBuffer
0x1800104d8  mov     rcx, [rcx+58h]; hInstance
0x1800104dc  sub     r9, 2
0x1800104e0  shr     r9, 1; cchBufferMax
0x1800104e3  call    cs:__imp_LoadStringW
0x1800104e9  mov     r9, [rdi+78h]
0x1800104ed  xor     r8d, r8d; wParam
0x1800104f0  mov     rcx, [rdi+38h]; hWnd
0x1800104f4  add     r9, 2; lParam
0x1800104f8  mov     edx, 14Ah; Msg
0x1800104fd  call    cs:__imp_SendMessageW
0x180010503  mov     rcx, [rdi+38h]; hWnd
0x180010507  xor     r9d, r9d; lParam
0x18001050a  movsxd  r8, eax; wParam
0x18001050d  mov     edx, 151h; Msg
0x180010512  call    cs:__imp_SendMessageW
0x180010518  mov     rcx, [rdi+38h]; hWnd
0x18001051c  xor     r9d, r9d; lParam
0x18001051f  mov     r8, rbp; wParam
0x180010522  lea     edx, [r9+0Bh]; Msg
0x180010526  call    cs:__imp_SendMessageW
0x18001052c  mov     rbx, [rsp+38h+arg_0]
0x180010531  mov     rbp, [rsp+38h+arg_10]
0x180010536  add     rsp, 20h
0x18001053a  pop     r14
0x18001053c  pop     rdi
0x18001053d  pop     rsi
0x18001053e  retn
```
